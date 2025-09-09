# Jervis — AI T-Shirt Shop with Midjourney Integration

Jervis is a side project where we mixed AI image generation with a small online shop for t-shirts.
It allowed users to generate custom images via a Telegram bot and purchase them as printed t-shirts (we printed t-shirts ourselves).   

---
![Me and almost happy customer](/Jervis/docs/jervis_photo.jpg)

## Features
- AI image generation through a custom Midjourney integration.  
- Chatbot workflow:  
  - Users send prompts to a Telegram bot.  
  - The bot requests images through a Discord bot → Django backend → Midjourney.  
- E-commerce flow: users could order t-shirts with their generated prints.  
- Reached €500 worth of sales in custom AI-designed merchandise.  

---

## Tech Stack
- **Backend:** Django, Django REST Framework  
- **Bots:**  
  - Discord bot (bridge to Midjourney)  
  - Telegram bot (user-facing)   
- **Infrastructure:** Docker, docker-compose  
- **Async / Scheduling:** Celery + Redis  
- **Integrations:** Custom Midjourney API wrapper, payment handling  

---

## Architecture
User (Telegram) → Telegram Bot → Django Backend → Discord Bot → Midjourney → Django Backend → Telegram Bot → User


- **Telegram bot** serves as the main user interface for generating images and placing orders.  
- **Django backend** manages business logic, user data, order processing, and communication between services.  
- **Discord bot** connects with Midjourney, submits prompts, and retrieves generated images.  
- **Midjourney** provides the AI-based image generation used in the product.  
