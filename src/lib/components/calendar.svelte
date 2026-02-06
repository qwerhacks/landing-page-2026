<script>
    import { onMount, onDestroy } from 'svelte';
    import { Calendar } from '@fullcalendar/core';
    import dayGridPlugin from '@fullcalendar/daygrid';
    import listPlugin from '@fullcalendar/list';
    import iCalendarPlugin from '@fullcalendar/icalendar';
    import WorkshopCarousel from './workshop_carousel.svelte';

    let calendarEl;
    let calendar;

    onMount(() => {
        const isMobile = window.innerWidth < 768;

        calendar = new Calendar(calendarEl, {
            plugins: [dayGridPlugin, listPlugin, iCalendarPlugin],
            initialView: 'dayGridMonth',
            height: 'auto',
            aspectRatio: isMobile ? 0.65 : 1.35,
            firstDay: 1, // Start week on Monday so Sat/Sun appear in the same view
            headerToolbar: {
                left: 'prev,next',
                center: 'title',
                right: isMobile ? '' : 'dayGridMonth,listWeek' 
            },
            footerToolbar: isMobile ? {
                left: '',
                center: 'dayGridMonth,listWeek',
                right: ''
            } : {},
            events: {
                // Ensure this file exists in your static folder or provide a valid URL
                url: '/qwerhacks@gmail.com.ics', 
                format: 'ics'
            }
        });

        calendar.render();
    });

    onDestroy(() => {
        if (calendar) {
            calendar.destroy();
        }
    });
</script>

<div bind:this={calendarEl} class="calendar-container"></div>
<WorkshopCarousel />

<style>
    .calendar-container {
        width: 90%;
        max-width: 900px;
        margin: 2rem auto;
        padding: 20px;
        border-radius: 16px;

        /* Theme Styling */
        font-family: 'Ranille Normal', serif;
        color: #ffffff;
        background-color: rgba(0, 0, 0, 0.5); /* Dark semi-transparent background */
        backdrop-filter: blur(5px); /* Glass effect */
        border: 1px solid rgba(255, 255, 255, 0.1); 

        /* FullCalendar CSS Variable Overrides to match theme */
        --fc-page-bg-color: transparent;
        --fc-neutral-bg-color: rgba(255, 255, 255, 0.05); /* Header backgrounds */
        --fc-list-event-hover-bg-color: rgba(255, 255, 255, 0.1);
        --fc-theme-standard-border-color: rgba(255, 255, 255, 0.15); /* Subtler borders */
        
        /* Buttons (Gold Theme) */
        --fc-button-text-color: #ffffff;
        --fc-button-bg-color: #C5A059;
        --fc-button-border-color: #C5A059;
        --fc-button-hover-bg-color: #b08d4d;
        --fc-button-hover-border-color: #b08d4d;
        --fc-button-active-bg-color: #8c6f3b;
        --fc-button-active-border-color: #8c6f3b;
        
        /* Events */
        --fc-event-bg-color: #C5A059;
        --fc-event-border-color: #C5A059;
        --fc-event-text-color: #ffffff;
        
        /* Today Cell Highlight */
        --fc-today-bg-color: rgba(197, 160, 89, 0.15);
    }

    /* Target inner FullCalendar elements for finer control */
    :global(.fc-toolbar-title) {
        font-family: 'Milonga', serif;
        font-size: 1.8rem;
    }

    @media (max-width: 768px) {
        :global(.fc-header-toolbar) {
            display: flex !important;
            flex-direction: column !important;
            gap: 1rem !important;
        }

        :global(.fc-toolbar-title) {
            font-size: 1.5rem !important;
            margin: 0 !important;
        }

        :global(.fc-footer-toolbar) {
            margin-top: 1rem !important;
        }
    }

    /* Day of Week Headers (Mon, Tue, Wed...) */
    :global(.fc-col-header-cell) {
        background-color: #C5A059 !important;
        color: white !important;
    }
    
    /* List View Day Headers (Sticky Date Headers) */
    :global(.fc-list-day-cushion) {
        background-color: #C5A059 !important;
        color: white !important;
    }

    :global(.fc-col-header-cell-cushion),
    :global(.fc-daygrid-day-number),
    :global(.fc-list-day-text),
    :global(.fc-list-day-side-text) {
        color: white !important; /* Force white text on dates/headers */
        text-decoration: none !important;
    }

    /* Remove underlined links on dates */
    :global(a.fc-col-header-cell-cushion:hover),
    :global(a.fc-daygrid-day-number:hover) {
        text-decoration: none;
        color: #C5A059 !important; /* Gold on hover */
    }
</style>