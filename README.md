# DIRS21-DynamicMappingSystem
DynamicMappingSystem DIRS21 Code-Base.

Dynamic Mapping System - DIRS21 to External Systems
This project implements a dynamic mapping system for the DIRS21 platform, providing a flexible and scalable way to map data between DIRS21 internal models and external models used by partners (e.g., Google). The system is designed to be extensible, following SOLID principles and leveraging design patterns like the Factory Pattern to handle multiple mappings between internal models, DTOs (Data Transfer Objects), and external models.

Project Structure

Core Components:

Models:

DIRS21 Models: Internal models representing data within the DIRS21 system.
DTO (Data Transfer Objects): Intermediary objects used to decouple internal models from external systems.
Partner Models: External models representing data formats used by partners like Google.

Mappers:

Mapper Interface (IModelMapper): Defines the contract for all mappers, allowing flexibility in adding new mappers for different models.
Concrete Mappers: Implementations of the IModelMapper interface that handle specific model-to-model mappings (e.g., Room to GoogleRoom via RoomDTO).

MapHandler:

Centralized handler that retrieves and applies mappers based on the source and target model types.
It supports both single-step mappings (e.g., internal to external) and multi-step mappings (e.g., internal → DTO → external).

MapperFactory:

Factory that registers and provides mappers based on the model types being mapped.
Uses a Dictionary<string, IModelMapper> to map specific model transformations.
