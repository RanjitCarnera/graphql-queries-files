# GraphQL Documentation

This document includes the queries and mutations defined in the Harkins Teambuilder Webapp. These Queries and mutations are categorized based on sections.

### Projects

#### Projects 1: `NOT_YET_IMPORTED_PROJECTS_FROM_RAND_QUERY`
**GraphQL Query/Mutation:**
```graphql

	query projectFromRandSelect_Query {
		Rand {
			NotYetImportedProjectsFromRand {
				id
				name
				projectIdentifier
			}
		}
	}

```

#### Projects 2: `PROJECTS_QUERY`
**GraphQL Query/Mutation:**
```graphql

	query projectsSelect_Query($filterByName: String, $alwaysIncludeIds: [ID!]) {
		Project {
			Projects(first: 100, filterByName: $filterByName, alwaysIncludeIds: $alwaysIncludeIds) {
				edges {
					node {
						...projectsSelect_ProjectInlineFragment
					}
				}
			}
		}
	}

```

#### Projects 3: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query ProjectDetailsModalContent_Query($projectId: ID!, $scenarioId: ID!) {
		Scenario {
			ProjectInScenario(projectId: $projectId, scenarioId: $scenarioId) {
				...projectDetailsControl_ProjectInScenarioFragment
			}
		}
	}

```

#### Projects 4: `PROJECTS_QUERY`
**GraphQL Query/Mutation:**
```graphql

	query ProjectFromDynamicsSelect_Query {
		Dynamics {
			NotYetImportedProjectsFromDynamics {
				id
				name
				projectIdentifier
			}
		}
	}

```

#### Projects 5: `PEOPLE_QUERY`
**GraphQL Query/Mutation:**
```graphql

    query ProjectStageSelect_Query($filterByName: String, $excludeIds: [ID!], $alwaysIncludeIds: [ID!]) {
        Project {
            ProjectStages(first: 20, excludeIds: $excludeIds, filterByName: $filterByName, alwaysIncludeIds: $alwaysIncludeIds) {
                edges {
                    node {
                        ...ProjectStageSelect_ProjectStageFragment
                    }
                }
            }
        }
    }

```

#### Projects 6: `PEOPLE_QUERY`
**GraphQL Query/Mutation:**
```graphql

    query ProjectStagesSelect_Query($filterByName: String, $excludeIds: [ID!], $alwaysIncludeIds: [ID!]) {
        Project {
            ProjectStages(first: 20, excludeIds: $excludeIds, filterByName: $filterByName, alwaysIncludeIds: $alwaysIncludeIds) {
                edges {
                    node {
                        ...ProjectStagesSelect_ProjectStageFragment
                    }
                }
            }
        }
    }

```

#### Projects 7: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query ProjectStagesTable_Query($first: Int, $filterByName: String) {
		...ProjectStagesTable_ProjectStageListFragment
			@arguments(first: $first, filterByName: $filterByName)
	}

```

#### Projects 8: `PROJECTS_QUERY`
**GraphQL Query/Mutation:**
```graphql

    query ProjectsSelectField_Query($filterByName: String, $excludeIds: [ID!], $alwaysIncludeIds: [ID!]) {
        Project {
            Projects(first: 250, excludeIds: $excludeIds, filterByName: $filterByName, alwaysIncludeIds: $alwaysIncludeIds) {
                edges {
                    node {
                        ...ProjectsSelectField_ProjectFragment
                    }
                }
            }
        }
    }

```

#### Projects 9: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query ProjectsTable_Query(
		$first: Int
		$filterByName: String
		$filterByRegions: [ID!]
		$filterByDivisions: [ID!]
		$filterByStages: [ID!]
	) {
		...ProjectsTable_ProjectsListFragment
			@arguments(
				first: $first
				filterByName: $filterByName
				filterByRegions: $filterByRegions
				filterByDivisions: $filterByDivisions
				filterByStages: $filterByStages
			)
	}

```

#### Projects 10: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query ScenarioMapViewScreen_Query(
		$id: ID!
		$filterByName: String
		$filterByAssignmentRoles: [ID!]
		$filterByUtilizationStatus: [UtilizationStatus!]
		$filterBySalaryMinimum: BigDecimal
		$filterBySalaryMaximum: BigDecimal
		$filterByFreeDateMinimum: LocalDate
		$filterByFreeDateMaximum: LocalDate
		$filterByAllocatedDateMinimum: LocalDate
		$filterByAllocatedDateMaximum: LocalDate
		$filterByGapDaysMinimum: Int
		$filterByGapDaysMaximum: Int
		$filterByDistanceMinimum: Int
		$filterByDistanceMaximum: Int
		$sortByClosestToProject: ID
		$utilizationWindow: UtilizationWindowInput
	) {
		node(id: $id) {
			... on Scenario {
				...ScenarioMapViewScreen_ScenarioFragment
			}
		}
		...rosterPart_StaffFragment
			@arguments(
				filterByName: $filterByName
				scenarioRef: $id
				filterByAssignmentRoles: $filterByAssignmentRoles
				filterByUtilizationStatus: $filterByUtilizationStatus
				filterBySalaryMinimum: $filterBySalaryMinimum
				filterBySalaryMaximum: $filterBySalaryMaximum
				filterByFreeDateMinimum: $filterByFreeDateMinimum
				filterByFreeDateMaximum: $filterByFreeDateMaximum
				filterByAllocatedDateMinimum: $filterByAllocatedDateMinimum
				filterByAllocatedDateMaximum: $filterByAllocatedDateMaximum
				filterByGapDaysMinimum: $filterByGapDaysMinimum
				filterByGapDaysMaximum: $filterByGapDaysMaximum
				filterByDistanceMinimum: $filterByDistanceMinimum
				filterByDistanceMaximum: $filterByDistanceMaximum
				sortByClosestToProject: $sortByClosestToProject
				utilizationWindow: $utilizationWindow
			)
		...baseScreen_QueryFragment
		...rosterPart_FilterFragment
	}

```

#### Projects 11: `PROJECT_QUERY`
**GraphQL Query/Mutation:**
```graphql

	query LoadDriveTimesButton_ProjectQuery($projectId: ID!) {
		node(id: $projectId) {
			... on Project {
				id
				address {
					latitude
					longitude
				}
			}
		}
	}

```

#### Projects 12: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query ScenarioProjectViewScreen_Query(
		$id: ID!
		$filterByName: String
		$filterByAssignmentRoles: [ID!]
		$filterByUtilizationStatus: [UtilizationStatus!]
		$filterBySalaryMinimum: BigDecimal
		$filterBySalaryMaximum: BigDecimal
		$filterByFreeDateMinimum: LocalDate
		$filterByFreeDateMaximum: LocalDate
		$filterByAllocatedDateMinimum: LocalDate
		$filterByAllocatedDateMaximum: LocalDate
		$filterByGapDaysMinimum: Int
		$filterByGapDaysMaximum: Int
		$filterByDistanceMinimum: Int
		$filterByDistanceMaximum: Int
		$sortByClosestToProject: ID
		$utilizationWindow: UtilizationWindowInput
		$projectFilters: ProjectWithAssignmentsFiltersInput
		$peopleOnAssignmentFilters: PersonOnAssignmentFiltersInput
	) {
		node(id: $id) {
			... on Scenario {
				...ScenarioProjectViewScreen_ScenarioFragment
					@arguments(
						utilizationWindow: $utilizationWindow
						projectFilters: $projectFilters
						personOnAssignmentFilters: $peopleOnAssignmentFilters
					)
			}
		}
		...rosterPart_StaffFragment
			@arguments(
				filterByName: $filterByName
				scenarioRef: $id
				filterByAssignmentRoles: $filterByAssignmentRoles
				filterByUtilizationStatus: $filterByUtilizationStatus
				filterBySalaryMinimum: $filterBySalaryMinimum
				filterBySalaryMaximum: $filterBySalaryMaximum
				filterByFreeDateMinimum: $filterByFreeDateMinimum
				filterByFreeDateMaximum: $filterByFreeDateMaximum
				filterByAllocatedDateMinimum: $filterByAllocatedDateMinimum
				filterByAllocatedDateMaximum: $filterByAllocatedDateMaximum
				filterByGapDaysMinimum: $filterByGapDaysMinimum
				filterByGapDaysMaximum: $filterByGapDaysMaximum
				filterByDistanceMinimum: $filterByDistanceMinimum
				filterByDistanceMaximum: $filterByDistanceMaximum
				sortByClosestToProject: $sortByClosestToProject
				utilizationWindow: $utilizationWindow
			)
		...ProjectsGridPart_QueryFragment

		...baseScreen_QueryFragment
		...rosterPart_FilterFragment

		Views {
			ViewOptions(first: 20, filterByViewType: ProjectView)
				@connection(key: "FilterViewSelector_ViewOptions") {
				__id
				edges {
					node {
						id
						name
						viewType
						url
						isDefault
					}
				}
			}
		}
	}

```

#### Projects 13: `STAFF_VIEW_QUERY`
**GraphQL Query/Mutation:**
```graphql

	query staffViewPart_Query(
		$id: ID!
		$intervalType: IntervalType!
		$personFiltersOpt: PersonOnAssignmentFiltersInput
		$projectFiltersOpt: ProjectWithAssignmentsFiltersInput
		$showAll: Boolean
		$sort: StaffViewSort
		$utilizationWindow: UtilizationWindowInput
	) {
		node(id: $id) {
			... on Scenario {
				...staffViewPart_ScenarioFragment
					@arguments(
						scenarioId: $id
						intervalType: $intervalType
						personFiltersOpt: $personFiltersOpt
						projectFiltersOpt: $projectFiltersOpt
						showAll: $showAll
						sort: $sort
						utilizationWindow: $utilizationWindow
					)
			}
		}
	}

```

#### Projects 14: `ADD_EXISTING_PROJECTS_TO_SCENARIO_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation addSelectedProjectsToScenarioButton_AddExistingProjectsToScenarioMutation(
		$input: AddExistingProjectsToScenarioInput!
	) {
		Scenario {
			addExistingProjectsToScenario(input: $input) {
				edge {
					node {
						id
						...ProjectsGridPart_ScenarioFragment
					}
				}
			}
		}
	}

```

#### Projects 15: `IMPORT_FROM_RAND_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation importFromRandButton_ImportFromRandMutation(
		$input: ImportProjectFromRandInput!
		$connectionIds: [ID!]!
	) {
		Rand {
			importProjectFromRand(input: $input) {
				edge @appendEdge(connections: $connectionIds) {
					node {
						...ProjectsTable_ProjectFragment
					}
				}
			}
		}
	}

```

#### Projects 16: `LOAD_PURSUIT_PROJECTS_FROM_DWH_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation loadPursuitProjectsFromRandDwhButton_loadPursuitProjectsFromDWHMutation(
		$input: LoadPursuitProjectsFromDWHInput!
	) {
		Rand {
			loadPursuitProjectsFromDWH(input: $input) {
				syncResult {
					editedEntities
					issues {
						id
						issue
					}
				}
				clientMutationId
			}
		}
	}

```

#### Projects 17: `ASSIGN_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation AssignmentCard_AssignMutation($input: FillAssignmentInput!) {
		Scenario {
			fillAssignment(input: $input) {
				update {
					project {
						id
						...projectCard_ProjectFragment
					}
				}
			}
		}
	}

```

#### Projects 18: `REMOVE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ChangeProjectActivationButton_Mutation($input: SetProjectActivationInput!) {
		Project {
			setProjectActivation(input: $input) {
				edge {
					node {
						id
						isDeactivated
					}
				}
			}
		}
	}

```

#### Projects 19: `CREATE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation CreateAssignmentButton_CreateMutation($input: CreateAssignmentInput!) {
		Scenario {
			createAssignment(input: $input) {
				edge {
					node {
						id
						...AssignmentsInProjectList_ProjectFragment
						...projectCard_ProjectFragment
					}
				}
			}
		}
	}

```

#### Projects 20: `CREATE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation CreateAssignmentsFromTemplateButton_CreateMutation(
		$input: CreateAssignmentsFromTemplateInput!
	) {
		Scenario {
			createAssignmentsFromTemplate(input: $input) {
				edge {
					node {
						id
						...AssignmentsInProjectList_ProjectFragment
						...projectCard_ProjectFragment
					}
				}
			}
		}
	}

```

#### Projects 21: `REMOVE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation DeleteAssignmentButton_DeleteMutation($input: DeleteAssignmentInput!) {
		Scenario {
			deleteAssignment(input: $input) {
				update {
					project {
						id
						...projectCard_ProjectFragment
					}
				}
			}
		}
	}

```

#### Projects 22: `REMOVE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

    mutation DeleteProjectStagesButton_DeleteMutation($input: DeleteProjectStageInput!, $connections: [ID!]!) {
        Project {
            deleteProjectStage(input: $input) {
                deletedIds @deleteEdge(connections: $connections)
            }
        }

    }

```

#### Projects 23: `REMOVE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

    mutation DeleteProjectsButton_DeleteMutation($input: DeleteProjectInput!, $connections: [ID!]!) {
        Project {
            deleteProject(input: $input) {
                deletedIds @deleteEdge(connections: $connections)
            }
        }

    }

```

#### Projects 24: `EDIT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation EditAssignmentButton_EditMutation($input: EditAssignmentInput!) {
		Scenario {
			editAssignment(input: $input) {
				update {
					project {
						id
						...AssignmentsInProjectList_ProjectFragment
						...projectCard_ProjectFragment

						assignments {
							edges {
								node {
									...EditAssignmentButton_AssignmentFragment
								}
							}
						}
					}
				}
			}
		}
	}

```

#### Projects 25: `EMPTY_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation EmptyAssignmentButton_EmptyMutation($input: EmptyAssignmentInput!) {
		Scenario {
			emptyAssignment(input: $input) {
				update {
					project {
						id
						...projectCard_ProjectFragment
					}
				}
			}
		}
	}

```

#### Projects 26: `MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ExportProjectStagesButton_ExportMutation {
		Project {
			exportProjectStages(input: {}) {
				file {
					url
				}
			}
		}
	}

```

#### Projects 27: `MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ExportProjectsButton_ExportMutation {
		Project {
			exportProjects(input: {}) {
				file {
					url
				}
			}
		}
	}

```

#### Projects 28: `GENERATE_PROJECT_REPORT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation GenerateReportButton_GenerateReportMutation(
		$input: GenerateProjectManagerReportInput!
	) {
		Pdf {
			generateProjectManagerReport(input: $input) {
				file {
					name
					url
				}
			}
		}
	}

```

#### Projects 29: `MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ImportFromDynamicsButton_ImportFromDynamicsMutation(
		$input: ImportProjectFromDynamicsInput!
		$connectionIds: [ID!]!
	) {
		Dynamics {
			importProjectFromDynamics(input: $input) {
				edge @appendEdge(connections: $connectionIds) {
					node {
						...ProjectsTable_ProjectFragment
					}
				}
			}
		}
	}

```

#### Projects 30: `IMPORT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ImportProjectStagesButton_ImportMutation($input: ImportProjectStagesInput!) {
		Project {
			importProjectStages(input: $input) {
				result {
					editedEntities
					newEntities
					issues {
						row
						issue
					}
				}
			}
		}
	}

```

#### Projects 31: `IMPORT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ImportProjectsButton_ImportMutation($input: ImportProjectsInput!) {
		Project {
			importProjects(input: $input) {
				result {
					editedEntities
					newEntities
					issues {
						row
						issue
					}
				}
			}
		}
	}

```

#### Projects 32: `INCREASE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

    mutation ProjectStageSortOrderButtons_IncreaseMutation($input: IncreaseProjectStageSortOrderInput!) {
        Project {
            increaseProjectStageSortOrder(input: $input) {
                edge {
                    node {
                        id
                        sortOrder
                    }
                }
            }
        }
    }

```

#### Projects 33: `DECREASE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

    mutation ProjectStageSortOrderButtons_DecreaseMutation($input: DecreaseProjectStageSortOrderInput!) {
        Project {
            decreaseProjectStageSortOrder(input: $input) {
                edge {
                    node {
                        id
                        sortOrder
                    }
                }
            }
        }
    }

```

#### Projects 34: `IMPORT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

    mutation ResolveProjectsGpsCoordinatesButton_FetchMutation($input: ResolveProjectsGpsCoordinatesInput!) {
        Project {
            resolveProjectsGpsCoordinates(input: $input) {
                updatedProjects {
                    id
                    address {
                        latitude
                        longitude
                    }
                }
            }
        }
    }

```

#### Projects 35: `ADD_NEW_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation addProjectToScenarioModal_AddNewMutation(
		$input: AddNewProjectToScenarioInput!
		$connectionIds: [ID!]!
	) {
		Scenario {
			addNewProjectToScenario(input: $input) {
				edge @appendEdge(connections: $connectionIds) {
					node {
						id
						...ProjectsGridPart_ScenarioFragment
					}
				}
			}
		}
	}

```

#### Projects 36: `ADD_EXISTING_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation addProjectToScenarioModal_AddExistingMutation(
		$input: AddExistingProjectsToScenarioInput!
	) {
		Scenario {
			addExistingProjectsToScenario(input: $input) {
				edge {
					node {
						id
						...ProjectsGridPart_ScenarioFragment
					}
				}
			}
		}
	}

```

#### Projects 37: `CREATE_PROJECT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation createProjectButton_CreateProjectMutation(
		$input: CreateProjectInput!
		$connectionId: ID!
	) {
		Project {
			createProject(input: $input) {
				edge @appendEdge(connections: [$connectionId]) {
					node {
						id
						...editProjectButton_ProjectFragment
					}
				}
			}
		}
	}

```

#### Projects 38: `EDIT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation editProjectButton_EditMutation($input: EditProjectInput!) {
		Project {
			editProject(input: $input) {
				edge {
					node {
						id
						...editProjectButton_ProjectFragment
					}
				}
				changedAssignments {
					...AssignmentProjectCard_AssignmentFragment
				}
			}
		}
	}

```

#### Projects 39: `CREATE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation editProjectStageModal_CreateMutation(
		$input: CreateProjectStageInput!
		$connections: [ID!]!
	) {
		Project {
			createProjectStage(input: $input) {
				edge @appendEdge(connections: $connections) {
					node {
						id
						...editProjectStageButton_ProjectStageFragment
					}
				}
			}
		}
	}

```

#### Projects 40: `EDIT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation editProjectStageModal_EditMutation($input: EditProjectStageInput!) {
		Project {
			editProjectStage(input: $input) {
				edge {
					node {
						id
						...editProjectStageButton_ProjectStageFragment
					}
				}
			}
		}
	}

```

#### Projects 41: `REMOVE_PROJECT_FROM_SCENARIO_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation removeProjectFromScenarioButton_RemoveProjectFromScenarioMutation(
		$input: RemoveProjectFromScenarioInput!
	) {
		Scenario {
			removeProjectFromScenario(input: $input) {
				edge {
					node {
						id
						...ProjectsGridPart_ScenarioFragment
					}
				}
			}
		}
	}

```

#### Projects 42: `SYNC_DYNAMICS_PROJECTS_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation syncDynamicsProjectsButton_SyncProjectsFromDynamicsMutation(
		$input: SynchronizeProjectsFromDynamicsInput!
	) {
		Dynamics {
			synchronizeProjectsFromDynamics(input: $input) {
				edges {
					node {
						id
						...ProjectsTable_ProjectFragment
						...syncProjectFromDynamicsButton_SyncProjectFragment
					}
				}
			}
		}
	}

```

#### Projects 43: `SYNC_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation syncProjectFromDynamicsButton_SyncFromDynamicsMutation(
		$input: LoadProjectDataFromDynamicsInput!
	) {
		Dynamics {
			loadProjectDataFromDynamics(input: $input) {
				edge {
					node {
						...ProjectsTable_ProjectFragment
						...syncProjectFromDynamicsButton_SyncProjectFragment
					}
				}
			}
		}
	}

```

#### Projects 44: `EDIT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation syncProjectFromDynamicsButton_EditMutation($input: EditProjectInput!) {
		Project {
			editProject(input: $input) {
				edge {
					node {
						...ProjectsTable_ProjectFragment
						...syncProjectFromDynamicsButton_SyncProjectFragment
					}
				}
			}
		}
	}

```

#### Projects 45: `SYNC_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation syncProjectFromRandButton_SyncFromRandMutation($input: LoadProjectDataFromRandInput!) {
		Rand {
			loadProjectDataFromRand(input: $input) {
				edge {
					node {
						...ProjectsTable_ProjectFragment
						...syncProjectFromRandButton_SyncProjectFragment
					}
				}
			}
		}
	}

```

#### Projects 46: `EDIT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation syncProjectFromRandButton_EditMutation($input: EditProjectInput!) {
		Project {
			editProject(input: $input) {
				edge {
					node {
						...ProjectsTable_ProjectFragment
						...syncProjectFromRandButton_SyncProjectFragment
					}
				}
			}
		}
	}

```

#### Projects 47: `SYNC_RAND_PROJECTS_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation syncRandProjectsButton_SyncProjectsFromRandMutation(
		$input: SynchronizeProjectsFromRandInput!
	) {
		Rand {
			synchronizeProjectsFromRand(input: $input) {
				syncResult {
					editedEntities
					issues {
						id
						issue
					}
				}
				edges {
					node {
						id
						...ProjectsTable_ProjectFragment
						...syncProjectFromRandButton_SyncProjectFragment
					}
				}
			}
		}
	}

```

#### Projects 48: `SYNC_WITH_RAND_PRECON_DWH_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation syncWithRandPreconDwhButton_SyncWithRandPreconDwhMutation(
		$input: SyncRandPreconAccountWithRandDwhInput!
	) {
		Rand {
			syncRandPreconAccountWithRandDwh(input: $input) {
				projectStageEdges {
					node {
						id
						#						project view only
						...projectStagesTab_ProjectStageFragment
					}
				}
				regionEdges {
					node {
						id
						#						project view only
						...rosterListActiveFilters_RegionFragment
					}
				}
				projectEdges {
					node {
						id
						#						project view only
						...editProjectButton_ProjectFragment
					}
				}
				personEdges {
					node {
						id
						#						project only?
						...personDetailsButton_PersonFragment
					}
				}
				assignmentEdges {
					node {
						id
						#						project view only
						...AssignmentCard_AssignmentFragment
					}
				}
			}
		}
	}

```

#### Projects 49: `GENERATE_AVAILABILITY_FORECAST_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation GenerateAvailabilityForecastForm_GenerateAvailabilityForecastMutation(
		$input: GenerateAvailabilityForecastInput!
	) {
		Availabilityforecast {
			generateAvailabilityForecast(input: $input) {
				availabilityForecast {
					rows {
						columns {
							available
							difference
							needed
							availablePeople {
								id
								name
							}
							yearMonth
							projects
						}
						roles {
							name
						}
					}
					summary {
						yearMonth
						needed
						difference
						available
						projects
					}
					yearAndMonths
					countPossibleUtilizationNotPeople
				}
			}
		}
	}

```

### Scenarios

#### Scenarios 1: `EXECUTIVES_QUERY`
**GraphQL Query/Mutation:**
```graphql

	query executivesSelect_Query($filterByName: String, $alwaysIncludeIds: [ID!], $scenarioId: ID) {
		Staff {
			Executives(
				first: 20
				filterByName: $filterByName
				alwaysIncludeIds: $alwaysIncludeIds
				scenarioId: $scenarioId
			) {
				edges {
					node {
						...executivesSelect_PersonFragment
					}
				}
			}
		}
	}

```

#### Scenarios 2: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query personDetailsModalContent_Query($personId: ID!, $scenarioId: ID!) {
		node(id: $personId) {
			... on Person {
				...personDetailsControl_PersonFragment @arguments(scenarioId: $scenarioId)
			}
		}
		...personDetailsControl_AssignmentListFragment
			@arguments(filterByPerson: $personId, filterByScenario: $scenarioId)
	}

```

#### Scenarios 3: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query ScenariosTable_Query($first: Int, $filterByName: String) {
		...ScenariosTable_ScenariosListFragment
			@arguments(first: $first, filterByName: $filterByName)
	}

```

#### Scenarios 4: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query UserScenariosTable_Query($first: Int, $onlyShowMine: Boolean) {
		...UserScenariosTable_ScenariosListFragment
			@arguments(first: $first, onlyShowMine: $onlyShowMine)
	}

```

#### Scenarios 5: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query scenarioSelectField_Query(
		$last: Int
		$after: String
		$before: String
		$filterByName: String
		$onlyMaster: Boolean
		$onlyMine: Boolean
		$alwaysIncludeIds: [ID!]
		$excludeIds: [ID!]
	) {
		Scenario {
			Scenarios(
				first: 20
				last: $last
				after: $after
				before: $before
				alwaysIncludeIds: $alwaysIncludeIds
				excludeIds: $excludeIds
				filterByName: $filterByName
				onlyMaster: $onlyMaster
				onlyShowMine: $onlyMine
			) {
				pageInfo {
					startCursor
					endCursor
					hasNextPage
					hasPreviousPage
				}
				edges {
					cursor
					node {
						id
						...scenarioSelectField_ScenarioInlineFragment
					}
				}
			}
		}
	}

```

#### Scenarios 6: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query availabilityForecastScreen_Query($id: ID!) {
		node(id: $id) {
			... on Scenario {
				...availabilityForecastScreen_ScenarioFragment
			}
		}
		...baseScreen_QueryFragment
	}

```

#### Scenarios 7: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query ScenarioStaffViewScreen_Query($id: ID!) {
		node(id: $id) {
			... on Scenario {
				...ScenarioStaffViewScreen_ScenarioFragment
			}
		}
		...baseScreen_QueryFragment
		...FilterViewSelector_QueryFragment @arguments(filterByViewType: StaffView)
		...staffViewFiltersPart_QueryFragment

		Views {
			ViewOptions(first: 20, filterByViewType: StaffView)
				@connection(key: "FilterViewSelector_ViewOptions") {
				__id
				edges {
					node {
						id
						name
						viewType
						url
						isDefault
					}
				}
			}
		}
	}

```

#### Scenarios 8: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query StartScreen_Query {
		Scenario {
			Scenarios(first: 1, onlyMaster: true) {
				edges {
					node {
						id
					}
				}
			}
		}
		...baseScreen_QueryFragment
	}

```

#### Scenarios 9: `MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation CloneScenarioButton_CloneMutation($input: CloneScenarioInput!, $connections: [ID!]!) {
		Scenario {
			cloneScenario(input: $input) {
				edge @appendEdge(connections: $connections) {
					node {
						id
						...UserScenariosTable_ScenarioFragment
						...ScenariosTable_ScenarioFragment
					}
				}
			}
		}
	}

```

#### Scenarios 10: `DELETE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

    mutation DeleteScenariosButton_DeleteMutation($input: DeleteScenarioInput!, $connections: [ID!]!) {
        Scenario {
            deleteScenario(input: $input) {
                deletedIds @deleteEdge(connections: $connections)
            }
        }
    }

```

#### Scenarios 11: `EDIT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

    mutation EditScenarioButton_EditMutation($input: EditScenarioInput!) {
        Scenario {
            editScenario(input: $input) {
                edge {
                    node {
                        id
                        name
                        isMasterPlan
                    }
                }
            }
        }
    }

```

#### Scenarios 12: `MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ExportAssignmentsButton_ExportMutation($input: ExportAssignmentsInput!) {
		Scenario {
			exportAssignments(input: $input) {
				file {
					url
				}
			}
		}
	}

```

#### Scenarios 13: `MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ExportScenariosButton_ExportMutation {
		Scenario {
			exportScenarios(input: {}) {
				file {
					url
				}
			}
		}
	}

```

#### Scenarios 14: `IMPORT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ImportAssignmentsButton_ImportMutation($input: ImportAssignmentsInput!) {
		Scenario {
			importAssignments(input: $input) {
				result {
					editedEntities
					newEntities
					issues {
						row
						issue
					}
				}
			}
		}
	}

```

#### Scenarios 15: `IMPORT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ImportScenariosButton_ImportMutation($input: ImportScenariosInput!) {
		Scenario {
			importScenarios(input: $input) {
				result {
					editedEntities
					newEntities
					issues {
						row
						issue
					}
				}
			}
		}
	}

```

#### Scenarios 16: `MAKE_MASTER_MUTATION`
**GraphQL Query/Mutation:**
```graphql

    mutation MakeMasterPlanButton_MakeMasterPlanMutation($input: ChangeMasterPlanInput!) {
        Scenario {
            changeMasterPlan(input: $input) {
                edge {
                    node {
                        ...MakeMasterPlanButton_ScenarioFragment
                    }
                }
            }
        }
    }

```

#### Scenarios 17: `MUTATION`
**GraphQL Query/Mutation:**
```graphql

    mutation ToggleVisibilityButton_ToggleVisibilityMutation($input: ChangeScenarioVisibilityInput!) {
        Scenario {
            changeScenarioVisibility(input: $input) {
                edge {
                    node {
                        ...ToggleVisibilityButton_ScenarioFragment
                    }
                }
            }
        }
    }

```

#### Scenarios 18: `CREATE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation CreateScenarioButton_CreateMutation($input: CreateScenarioInput!, $connectionId: ID!) {
		Scenario {
			createScenario(input: $input) {
				edge @appendEdge(connections: [$connectionId]) {
					node {
						id
						name
						isMasterPlan
					}
				}
			}
		}
	}

```

#### Scenarios 19: `UPDATE_ASSIGMENT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation moveAssignmentDialogue_UpdateAssigmentMutation($input: EditAssignmentInput!) {
		Scenario {
			editAssignment(input: $input) {
				clientMutationId
			}
		}
	}

```

#### Scenarios 20: `UPDATE_ASSIGMENT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation resizeAssignmentDialogue_UpdateAssigmentMutation($input: EditAssignmentInput!) {
		Scenario {
			editAssignment(input: $input) {
				clientMutationId
			}
		}
	}

```

### Roaster

#### Roaster 1: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query PeopleTable_Query($first: Int, $filterByName: String) {
		...PeopleTable_PeopleListFragment @arguments(first: $first, filterByName: $filterByName)
	}

```

#### Roaster 2: `PEOPLE_QUERY`
**GraphQL Query/Mutation:**
```graphql

	query PersonSelect_Query($filterByName: String, $excludeIds: [ID!], $alwaysIncludeIds: [ID!]) {
		Staff {
			People(
				first: 20
				excludeIds: $excludeIds
				filterByName: $filterByName
				alwaysIncludeIds: $alwaysIncludeIds
			) {
				edges {
					node {
						...PersonSelect_PersonFragment
					}
				}
			}
		}
	}

```

#### Roaster 3: `QUERY`
**GraphQL Query/Mutation:**
```graphql

    query StaffingTemplateSelect_Query($filterByName: String,  $alwaysIncludeIds: [ID!]) {
        Template {
            StaffingTemplates(first: 20, filterByName: $filterByName, alwaysIncludeIds: $alwaysIncludeIds) {
                edges {
                    node {
                        ...StaffingTemplateSelect_StaffingTemplateFragment
                    }
                }
            }
        }
    }

```

#### Roaster 4: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query StaffingTemplatesTable_Query($first: Int, $filterByName: String) {
		...StaffingTemplatesTable_StaffingTemplateListFragment
			@arguments(first: $first, filterByName: $filterByName)
	}

```

#### Roaster 5: `PEOPLE_QUERY`
**GraphQL Query/Mutation:**
```graphql

	query peopleSelect_Query($filterByName: String, $excludeIds: [ID!], $alwaysIncludeIds: [ID!]) {
		Staff {
			People(
				first: 20
				excludeIds: $excludeIds
				filterByName: $filterByName
				alwaysIncludeIds: $alwaysIncludeIds
			) {
				edges {
					node {
						...peopleSelect_PersonFragment
					}
				}
			}
		}
	}

```

#### Roaster 6: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query selectUserInAccountField_PeopleQuery(
		$accountId: ID!
		$filterByName: String
		$alwaysIncludeIds: [ID!]
		$excludeIds: [ID!]
		$first: Int
	) {
		Assessment {
			PeopleInAccount(
				accountId: $accountId
				first: $first
				filterByName: $filterByName
				alwaysIncludeIds: $alwaysIncludeIds
				excludeIds: $excludeIds
			) {
				edges {
					node {
						...selectUserInAccountField_PersonFragment
					}
				}
			}
		}
	}

```

#### Roaster 7: `REMOVE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ChangePersonActivationButton_Mutation($input: SetPersonActivationInput!) {
		Staff {
			setPersonActivation(input: $input) {
				edge {
					node {
						id
						isDeactivated
					}
				}
			}
		}
	}

```

#### Roaster 8: `REMOVE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

    mutation DeletePeopleButton_DeleteMutation($input: DeletePersonInput!, $connections: [ID!]!) {
        Staff {
            deletePerson(input: $input) {
                deletedIds @deleteEdge(connections: $connections)
            }
        }

    }

```

#### Roaster 9: `REMOVE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

    mutation DeleteStaffingTemplatesButton_DeleteMutation($input: DeleteStaffingTemplateInput!, $connections: [ID!]!) {
        Template {
            deleteStaffingTemplate(input: $input) {
                deletedIds @deleteEdge(connections: $connections)
            }
        }

    }

```

#### Roaster 10: `CREATE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation EditPersonModal_CreateMutation($input: CreatePersonInput!, $connections: [ID!]!) {
		Staff {
			createPerson(input: $input) {
				edge @appendEdge(connections: $connections) {
					node {
						id
						...EditPersonButton_PersonFragment
					}
				}
			}
		}
	}

```

#### Roaster 11: `EDIT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation EditPersonModal_EditMutation($input: EditPersonInput!) {
		Staff {
			editPerson(input: $input) {
				edge {
					node {
						id
						...EditPersonButton_PersonFragment
					}
				}
			}
		}
	}

```

#### Roaster 12: `CREATE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation EditStaffingTemplateModal_CreateMutation(
		$input: CreateStaffingTemplateInput!
		$connections: [ID!]!
	) {
		Template {
			createStaffingTemplate(input: $input) {
				edge @appendEdge(connections: $connections) {
					node {
						id
						...EditStaffingTemplateButton_StaffingTemplateFragment
					}
				}
			}
		}
	}

```

#### Roaster 13: `EDIT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation EditStaffingTemplateModal_EditMutation($input: EditStaffingTemplateInput!) {
		Template {
			editStaffingTemplate(input: $input) {
				edge {
					node {
						id
						...EditStaffingTemplateButton_StaffingTemplateFragment
					}
				}
			}
		}
	}

```

#### Roaster 14: `MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ExportPeopleButton_ExportMutation {
		Staff {
			exportPeople(input: {}) {
				file {
					url
				}
			}
		}
	}

```

#### Roaster 15: `MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ExportStaffingTemplatesButton_ExportMutation {
		Template {
			exportStaffingTemplates(input: {}) {
				file {
					url
				}
			}
		}
	}

```

#### Roaster 16: `IMPORT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ImportPeopleButton_ImportMutation($input: ImportPeopleInput!) {
		Staff {
			importPeople(input: $input) {
				result {
					editedEntities
					newEntities
					issues {
						row
						issue
					}
				}
			}
		}
	}

```

#### Roaster 17: `IMPORT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ImportStaffingTemplatesButton_ImportMutation($input: ImportStaffingTemplatesInput!) {
		Template {
			importStaffingTemplates(input: $input) {
				result {
					editedEntities
					newEntities
					issues {
						row
						issue
					}
				}
			}
		}
	}

```

#### Roaster 18: `IMPORT_PEOPLESOFT_BUTTON_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation importPeoplesoftButton_DownloadPeopleDataFromS3Mutation(
		$input: DownloadPeopleDataFromS3Input!
	) {
		Peoplesoft {
			downloadPeopleDataFromS3(input: $input) {
				edited
				imported
				clientMutationId
			}
		}
	}

```

#### Roaster 19: `APPROXIMATE_ASSIGNMENT_RESIZE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation allocationBarProvider_ApproximateAssignmentResizeMutation(
		$input: ApproximateAssignmentResizeInput!
	) {
		Staffview {
			approximateAssignmentResize(input: $input) {
				startDate
				endDate
			}
		}
	}

```

#### Roaster 20: `APPROXIMATE_MOVE_ASSIGNMENT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation allocationBarProvider_ApproximateMoveAssignmentMutation(
		$input: ApproximateMoveAssignmentInput!
	) {
		Staffview {
			approximateMoveAssignment(input: $input) {
				startDate
				endDate
			}
		}
	}

```

### Access

#### Access 1: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query AccountsAdminTable_Query($first: Int) {
		...AccountsAdminTable_AccountsListFragment @arguments(first: $first)
	}

```

#### Access 2: `SELECT_ACCOUNT_GROUPS_FIELD_QUERY`
**GraphQL Query/Mutation:**
```graphql

	query selectAccountGroupsField_Query {
		Admin {
			Management {
				AccountGroups(first: 50) {
					edges {
						node {
							id
							name
						}
					}
				}
			}
		}
	}

```

#### Access 3: `ASSESSMENT_TEMPLATES_QUERY`
**GraphQL Query/Mutation:**
```graphql

	query selectSkillAssessmentTemplates_AssessmentTemplatesQuery($accountId: ID!) {
		Assessment {
			AssessmentTemplates(accountId: $accountId, first: 20) {
				edges {
					node {
						name
						id
					}
				}
			}
		}
	}

```

#### Access 4: `SELECT_USER_IN_ACCOUNT_GROUPS_OF_ACCOUNT_ADMIN_QUERY`
**GraphQL Query/Mutation:**
```graphql

	query selectUserInAccountGroupsOfAccountAdminField_Query($accountId: ID!) {
		Admin {
			Management {
				UserInAccountGroupsInAccountAdmin(first: 50, accountId: $accountId) {
					edges {
						node {
							id
							name
						}
					}
				}
			}
		}
	}

```

#### Access 5: `USER_IN_ACCOUNT_GROUPS_TABLE_QUERY`
**GraphQL Query/Mutation:**
```graphql

	query userInAccountGroupsTable_Query($first: Int) {
		...userInAccountGroupsTable_GroupListFragment @arguments(first: $first)
	}

```

#### Access 6: `USERS_IN_ACCOUNT_ADMIN_TABLE_QUERY`
**GraphQL Query/Mutation:**
```graphql

	query usersInAccountAdminTable_Query($first: Int, $accountId: ID!) {
		...usersInAccountAdminTable_UsersInAccountListFragment
			@arguments(first: $first, accountId: $accountId)
	}

```

#### Access 7: `USERS_IN_ACCOUNT_TABLE_QUERY`
**GraphQL Query/Mutation:**
```graphql

	query usersInAccountTable_Query($first: Int) {
		...usersInAccountTable_UsersInAccountListFragment @arguments(first: $first)
	}

```

#### Access 8: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query AcceptInvitationScreen_Query($token: String!) {
		Auth {
			InvitationByToken(token: $token) {
				invitingUserName
				accountName
			}
		}
	}

```

#### Access 9: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query accountSettingsScreen_Query {
		...ChangeLogoForm_CurrentUser
		...editNumericalDimensionExplanationsForm_QueryFragment
		...editAccountSettingsForm_QueryFragment
		...editAssessmentPasswordForm_QueryFragment
		...editAzureAdSsoConfigurationForm_QueryFragment
	}

```

#### Access 10: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query activate2fa_Query {
		Viewer {
			Auth {
				twoFactorAuthToken {
					id
					createdAt
					data {
						qrCodeUri
						isActivated
						activatedAt
						secretKey
					}
				}
			}
		}
	}

```

#### Access 11: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query recoveryCodesScreen_Query {
		Viewer {
			Auth {
				recoveryCodeCredentials {
					...recoveryCodesScreen_RecoveryCodeCredentialsInlineFragment
				}
				twoFactorAuthToken {
					data {
						isActivated
					}
				}
			}
		}
	}

```

#### Access 12: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query skillAssessmentLogin_Query($accountId: ID!) {
		Assessment {
			AccountLogo(accountId: $accountId) {
				url
			}
		}
	}

```

#### Access 13: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query skillAssessment_Query(
		$accountId: ID!
		$password: String
		$personId: ID
		$templateId: ID
	) {
		Assessment {
			AccountLogo(accountId: $accountId) {
				url
			}
		}
		...skillAssessment_GetLastUpdatedDateQuery
			@arguments(
				accountId: $accountId
				password: $password
				personId: $personId
				templateId: $templateId
			)
	}

```

#### Access 14: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query skillAssessmentExecution_Query($accountId: ID!, $assessmentId: ID!, $password: String) {
		Assessment {
			MyAssessment(accountId: $accountId, assessmentId: $assessmentId, password: $password) {
				person {
					id
					name
				}
				supervisor {
					id
					name
				}
				template {
					id
					name
					assessedSkills {
						id
						name
						skillCategory {
							id
							name
							sortOrder
							...categoryForm_SkillCategoryFragment
						}
						dimension {
							... on NumericalDimension {
								kind
								dimensionCount
								dimensionExplanations
							}
							... on BinaryDimension {
								kind
							}
						}
					}
					...categoryForm_AssessmentTemplateFragment
				}
				skillAssessments {
					skill {
						id
						name
						dimension {
							... on NumericalDimension {
								kind
								dimensionCount
								dimensionExplanations
							}
							... on BinaryDimension {
								kind
							}
						}
					}
					value {
						... on NumericalAssessmentValue {
							kind
							number
						}
						... on BinaryAssessmentValue {
							kind
							hasSkill
						}
					}
				}
				status {
					kind
					... on InProgress {
						kind
						lastUpdate
					}
					... on Finished {
						kind
						finishedAt
					}
				}
				...categoryForm_AssessmentFragment
				...navigation_AssessmentFragment
				...skillAssessmentExecution_AssessmentFragment
			}
		}
	}

```

#### Access 15: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query skillAssessmentSuccess_AssessmentNodeQuery($accountId: ID!, $id: ID!, $password: String) {
		Assessment {
			MyAssessment(accountId: $accountId, assessmentId: $id, password: $password) {
				id
				person {
					name
				}
				template {
					name
				}
			}
		}
	}

```

#### Access 16: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query skillAssessmentTemplatesTable_Query($first: Int, $filterByName: String) {
		Viewer {
			Auth {
				currentAccount {
					id
				}
			}
		}

		...skillAssessmentTemplatesTable_AssessmentTemplatesFragment
			@arguments(first: $first, filterByName: $filterByName)
	}

```

#### Access 17: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query skillAssessmentsTable_Query($first: Int, $after: String) {
		Viewer {
			Auth {
				currentAccount {
					id
				}
			}
		}
		...skillAssessmentsTable_AssessmentsFragment @arguments(first: $first, after: $after)
	}

```

#### Access 18: `QUERY`
**GraphQL Query/Mutation:**
```graphql

	query skillAssessments_Query {
		Viewer {
			Auth {
				currentAccount {
					id
				}
			}
		}
	}

```

#### Access 19: `REMOVE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

    mutation AnonymizeAccountButton_DeleteMutation($input: AnonymizeAccountAdminInput!, $connections: [ID!]!) {
        Admin {
            Management {
                anonymizeAccountAdmin(input: $input) {
                    deletedIds @deleteEdge(connections: $connections)
                    clientMutationId
                }
            }
        }

    }

```

#### Access 20: `CHANGE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ChangeAccountGroupsAdminModal_ChangeMutation($input: ChangeAccountGroupsInput!) {
		Admin {
			Management {
				changeAccountGroups(input: $input) {
					account {
						groupAssociations {
							group {
								id
								name
							}
						}
					}
				}
			}
		}
	}

```

#### Access 21: `CHANGE_EMAIL_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ChangeLogoForm_ChangeLogoMutation($input: SetAccountLogoInput!) {
		Admin {
			Auth {
				setAccountLogo(input: $input) {
					clientMutationId
				}
			}
		}
	}

```

#### Access 22: `CHANGE_PASSWORD_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ChangePasswordForm_ChangePasswordMutation($input: ChangePasswordInput!) {
		Auth {
			changePassword(input: $input) {
				clientMutationId
			}
		}
	}

```

#### Access 23: `CHANGE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ChangeUserGroupsAdminModal_ChangeMutation($input: ChangeUserGroupsAdminInput!) {
		Admin {
			Management {
				changeUserGroupsAdmin(input: $input) {
					edge {
						node {
							id
							...ChangeUserGroupsAdminModal_UserInAccountFragment
						}
					}
				}
			}
		}
	}

```

#### Access 24: `CREATE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation EditAccountModal_CreateMutation(
		$input: CreateAccountAdminInput!
		$connections: [ID!]!
	) {
		Admin {
			Management {
				createAccountAdmin(input: $input) {
					edge @appendEdge(connections: $connections) {
						node {
							id
							...EditAccountButton_AccountFragment
						}
					}
				}
			}
		}
	}

```

#### Access 25: `EDIT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation EditAccountModal_EditMutation($input: EditAccountAdminInput!) {
		Admin {
			Management {
				editAccountAdmin(input: $input) {
					edge {
						node {
							id
							...EditAccountButton_AccountFragment
						}
					}
				}
			}
		}
	}

```

#### Access 26: `LOGIN_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ForgotPasswordForm_ForgotPasswordMutation($input: ForgotPasswordInput!) {
		Auth {
			forgotPassword(input: $input) {
				clientMutationId
			}
		}
	}

```

#### Access 27: `CREATE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation InviteUserToAccountModal_InviteMutation(
		$input: InviteUserToAccountInput!
		$connections: [ID!]!
	) {
		Management {
			inviteUserToAccount(input: $input) {
				edge @appendEdge(connections: $connections) {
					cursor
					node {
						id
						email
						invitingUserName
					}
				}
			}
		}
	}

```

#### Access 28: `LOGIN_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation LoginAsUsersControl_LoginAsUserMutation($input: LoginAsUserJwtInput!) {
		Admin {
			Auth {
				loginAsUserJwt(input: $input) {
					jwtTokens {
						accessToken
						refreshToken
					}
				}
			}
		}
	}

```

#### Access 29: `DELETE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

    mutation RemoveUserFromAccountAdminButton_RemoveMutation($input: RemoveUserFromAccountAdminInput!, $connections: [ID!]!) {
        Admin {
            Management {
                removeUserFromAccountAdmin(input: $input) {
                    deletedIds @deleteEdge(connections: $connections)
                }
            }
        }
    }

```

#### Access 30: `DELETE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

    mutation RemoveUserFromAccountButton_RemoveMutation($input: RemoveUserFromAccountInput!, $connections: [ID!]!) {
        Management {
            removeUserFromAccount(input: $input) {
                deletedIds @deleteEdge(connections: $connections)
            }
        }
    }

```

#### Access 31: `LOGIN_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation ResetPasswordForm_ResetPasswordMutation($input: ResetPasswordInput!) {
		Auth {
			resetPassword(input: $input) {
				clientMutationId
			}
		}
	}

```

#### Access 32: `CHANGE_USER_IN_ACCOUNT_GROUPS_MODAL_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation changeUserInAccountGroupsModal_ChangeMutation(
		$input: ChangeUserInAccountGroupsInput!
	) {
		Management {
			changeUserInAccountGroups(input: $input) {
				edge {
					node {
						id
						...changeUserInAccountGroupsModal_UserInAccountFragment
					}
				}
			}
		}
	}

```

#### Access 33: `CREATE_USER_IN_ACCOUNT_MODAL_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation createUserInAccountModal_CreateMutation(
		$input: CreateUserInAccountAdminInput!
		$connections: [ID!]!
	) {
		Admin {
			Management {
				createUserInAccountAdmin(input: $input) {
					edge @appendEdge(connections: $connections) {
						node {
							id
							user {
								id
								email
								name
							}
							groups {
								id
								name
							}
							...ChangeUserGroupsAdminButton_UserInAccountFragment
						}
					}
				}
			}
		}
	}

```

#### Access 34: `CREATE_USER_IN_ACCOUNT_ADD_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation createUserInAccountModal_AddMutation(
		$input: AddUserToAccountAdminInput!
		$connections: [ID!]!
	) {
		Admin {
			Management {
				addUserToAccountAdmin(input: $input) {
					edge @appendEdge(connections: $connections) {
						node {
							id
							user {
								id
								email
								name
							}
							groups {
								id
								name
							}
							...ChangeUserGroupsAdminButton_UserInAccountFragment
						}
					}
				}
			}
		}
	}

```

#### Access 35: `EDIT_USER_IN_ACCOUNT_GROUP_MODAL_CREATE_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation editUserInAccountGroupModal_CreateMutation(
		$input: CreateGroupInput!
		$connections: [ID!]!
	) {
		Management {
			createGroup(input: $input) {
				edge @appendEdge(connections: $connections) {
					node {
						id
						...editUserInAccountGroupModal_GroupFragment
					}
				}
			}
		}
	}

```

#### Access 36: `EDIT_USER_IN_ACCOUNT_GROUP_MODAL_EDIT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation editUserInAccountGroupModal_EditMutation(
		$input: EditGroupInput!
		$connections: [ID!]!
	) {
		Management {
			editGroup(input: $input) {
				edge @appendEdge(connections: $connections) {
					node {
						id
						...editUserInAccountGroupModal_GroupFragment
					}
				}
			}
		}
	}

```

#### Access 37: `MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation AccountSwitcher_SwitchAccountMutation($input: SwitchAccountInput!) {
		Auth {
			switchAccount(input: $input) {
				jwtTokens {
					refreshToken
					accessToken
				}
			}
		}
	}

```

#### Access 38: `SET_ACCOUNT_SETTINGS_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation editAccountSettingsForm_SetAccountSettingsMutation($input: SetForce2FAInput!) {
		Admin {
			Auth {
				setForce2FA(input: $input) {
					account {
						extensions {
							... on TwoFAAccountExtension {
								force2FA
							}
						}
					}
					clientMutationId
				}
			}
		}
	}

```

#### Access 39: `SET_PASSWORD_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation editAssessmentPasswordForm_SetAccountAssessmentPasswordMutation(
		$input: SetAccountAssessmentPasswordInput!
	) {
		Admin {
			Auth {
				setAccountAssessmentPassword(input: $input) {
					account {
						id
					}
				}
			}
		}
	}

```

#### Access 40: `SET_AZURE_AD_SSO_CONFIGURATION_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation editAzureAdSsoConfigurationForm_SetAzureAdSsoConfigurationMutation(
		$input: SetAzureAdSsoConfigurationInput!
	) {
		Auth {
			setAzureAdSsoConfiguration(input: $input) {
				account {
					extensions {
						... on AuthProviderAccountExtension {
							authProviders {
								... on AzureAdAuthProvider {
									isActivated
									applicationId
									authorityUrl
									domain
									tenantId
									secret
									kind
								}
							}
						}
					}
				}
			}
		}
	}

```

#### Access 41: `LOGIN_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation loginForm_LoginMutation($input: LoginJwtInput!) {
		Auth {
			loginJwt(input: $input) {
				status {
					kind
					... on TwoFactorAuthRequired {
						qrCodeUri
						userName
						password
						email
					}
					... on twoFactorAuthCredentialsIncorrect {
						email
						password
						userName
					}
					... on authCredentialsCorrect {
						jwtTokens {
							refreshToken
							accessToken
						}
					}
				}
			}
		}
	}

```

#### Access 42: `EMAIL_HAS_AZURE_AD_SSO_SETUP_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation loginForm_EmailHasAzureADSSOSetupMutation($input: EmailHasAzureAdSsoSetupInput!) {
		AuthAzureAd {
			emailHasAzureAdSsoSetup(input: $input) {
				hasSetup
			}
		}
	}

```

#### Access 43: `LOGIN_AZURE_AD_USER_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation loginForm_LoginAzureAdUserMutation(
		$input: LoginAzureAdUserWithHarkinsUserExtensionInput!
	) {
		Sso {
			loginAzureAdUserWithHarkinsUserExtension(input: $input) {
				jwtTokens {
					accessToken
					refreshToken
				}
			}
		}
	}

```

#### Access 44: `GET_AZURE_AD_AUTHENTICATION_URL_FOR_EMAIL`
**GraphQL Query/Mutation:**
```graphql

	mutation loginForm_GetAzureAdAuthenticationUrlForEmailMutation(
		$input: GetAzureAdAuthenticationUrlForEmailInput!
	) {
		AuthAzureAd {
			getAzureAdAuthenticationUrlForEmail(input: $input) {
				redirectUri
			}
		}
	}

```

#### Access 45: `SETUP_TWO_FACTOR_AUTH_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation authenticatorAppSlot_SetupTwoFactorAuthMutation($input: SetupTwoFactorAuthInput!) {
		Auth {
			setupTwoFactorAuth(input: $input) {
				twoFactorAuthToken {
					...authenticatorAppSlot_TwoFactorAuthTokenInlineFragment
				}
			}
		}
	}

```

#### Access 46: `REGISTRATION_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation RegistrationScreen_LoginMutation($input: RegistrationInput!) {
		Auth {
			register(input: $input) {
				accountId
			}
		}
	}

```

#### Access 47: `LOGIN_TO_ASSESSMENT_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation skillAssessmentLogin_LoginToAssessmentMutation($input: LoginToAssessmentInput!) {
		Assessment {
			loginToAssessment(input: $input) {
				password
			}
		}
	}

```

#### Access 48: `LOGIN_2FA_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation twoFactorAuthOtp_login2FAMutation($input: Login2FAInput!) {
		Auth {
			login2FA(input: $input) {
				jwtTokens {
					accessToken
					refreshToken
				}
			}
		}
	}

```

#### Access 49: `TWO_FACTOR_AUTH_RECOVERY_MUTATION`
**GraphQL Query/Mutation:**
```graphql

	mutation twoFactorAuthRecovery_TwoFactorAuthRecoveryMutation(
		$input: Login2FARecoveryCodeInput!
	) {
		Auth {
			login2FARecoveryCode(input: $input) {
				status {
					kind
					... on authCredentialsCorrect {
						kind
						jwtTokens {
							refreshToken
							accessToken
						}
					}
				}
			}
		}
	}

```

### Common Data & Action

No Common Data & Action found.

### Fragments 


#### Fragments 1: `ASSIGNMENT_ROLE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editAssignmentRoleButton_AssignmentRoleFragment on AssignmentRole {
		id
		name
		sortOrder
		maxNumberOfProjects
		utilizationProjectionCapInMonths
		countAsFullyAllocatedAtPercentage
		countAsOverallocatedAtPercentage
		useEndDateOfLastAssignmentOverProjectionCap
	}

```


#### Fragments 2: `SKILL_CATEGORY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editSkillCategoryButton_SkillCategoryFragment on SkillCategory {
		id
		name
	}

```


#### Fragments 3: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment executivesSelect_PersonFragment on Person @inline {
		id
		name
	}

```


#### Fragments 4: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment loadPursuitProjectsFromRandDwhButton_ScenarioFragment on Scenario {
		id
		isMasterPlan
	}

```


#### Fragments 5: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment personCardDraggable_ScenarioFragment on Scenario {
		id
		utilization {
			personUtilizations {
				personRef
				status
			}
			...personCard_ScenarioUtilizationFragment
		}
		...personCard_ScenarioFragment
	}

```


#### Fragments 6: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment personCardDraggable_PersonFragment on Person
	@argumentDefinitions(scenarioId: { type: "ID!" }) {
		id
		name
		assignmentRole {
			id
			name
		}
		...personCard_PersonFragment @arguments(scenarioId: $scenarioId)
	}

```


#### Fragments 7: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment personCard_ScenarioFragment on Scenario {
		id
		...personDetailsButton_ScenarioFragment
	}

```


#### Fragments 8: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment personCard_PersonFragment on Person @argumentDefinitions(scenarioId: { type: "ID!" }) {
		id
		name
		assignmentRole {
			id
			name
		}
		sumOfProjectVolume(scenarioRef: $scenarioId)
		comment
		...personDetailsButton_PersonFragment
	}

```


#### Fragments 9: `SCENARIO_UTILIZATION_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment personCard_ScenarioUtilizationFragment on ScenarioUtilization {
		personUtilizations {
			personRef
			utilizationPercentage
			status
		}
		...personDetailsButton_ScenarioUtilizationFragment
	}

```


#### Fragments 10: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment skillsDisplay_PersonFragment on Person {
		id
		skills(first: 100) {
			edges {
				node {
					...skillsDisplay_SkillAssociationInlineFragment
				}
			}
		}
	}

```


#### Fragments 11: `SKILL_ASSOCIATION_INLINE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment skillsDisplay_SkillAssociationInlineFragment on SkillAssociation @inline {
		id
		data {
			value {
				... on NumericalAssessmentValue {
					kind
					number
				}
				... on BinaryAssessmentValue {
					hasSkill
					kind
				}
			}

			skill {
				id
				name
				dimension {
					kind
					... on NumericalDimension {
						kind
						dimensionCount
					}
				}
				skillCategory {
					id
					name
				}
			}
		}
	}

```


#### Fragments 12: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment personDetailsControl_PersonFragment on Person
	@argumentDefinitions(scenarioId: { type: "ID!" }) {
		id
		name
		assignmentRole {
			name
		}
		phone
		email
		address {
			lineOne
			postalCode
			city
			country
			state
			latitude
			longitude
		}
		comment
		avatar {
			url
		}
		associatedWithRegions {
			id
			name
		}
		associatedWithDivisions {
			id
			name
		}

		...skillsDisplay_PersonFragment
		...UtilizationOverTimeGraph_PersonFragment @arguments(scenarioId: $scenarioId)
	}

```


#### Fragments 13: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment personDetailsControl_AssignmentListFragment on Query
	@refetchable(queryName: "PersonDetailsControl_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 50 }
		after: { type: "String" }
		filterByPerson: { type: "ID" }
		filterByScenario: { type: "ID" }
	) {
		Assignments {
			Assignments(
				first: $first
				after: $after
				filterByPerson: $filterByPerson
				filterByScenario: $filterByScenario
			) @connection(key: "PersonDetailsControl_Assignments") {
				pageInfo {
					endCursor
					hasPreviousPage
					hasNextPage
					startCursor
				}
				edges {
					node {
						id
						time
						...AssignmentProjectCard_AssignmentFragment
					}
				}
			}
		}
	}

```


#### Fragments 14: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment personDetailsButton_ScenarioFragment on Scenario {
		id
		gapDays {
			personGapDays {
				personRef
				gapDays
			}
		}
	}

```


#### Fragments 15: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment personDetailsButton_PersonFragment on Person {
		id
		name
		comment
		assignmentRole {
			name
		}
	}

```


#### Fragments 16: `SCENARIO_UTILIZATION_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment personDetailsButton_ScenarioUtilizationFragment on ScenarioUtilization {
		personUtilizations {
			personRef
			utilizationPercentage
		}
	}

```


#### Fragments 17: `PROJECT_INLINE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment projectsSelect_ProjectInlineFragment on Project @inline {
		id
		name
	}

```


#### Fragments 18: `LIST_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment AccountsAdminTable_AccountsListFragment on Query
	@refetchable(queryName: "AccountsTable_Refetch")
	@argumentDefinitions(first: { type: "Int", defaultValue: 20 }, after: { type: "String" }) {
		Admin {
			Management {
				AccountsAdmin(first: $first, after: $after)
					@connection(key: "AccountsTable_AccountsAdmin") {
					__id
					edges {
						node {
							...AccountsAdminTable_AccountInlineFragment
						}
					}
				}
			}
		}
	}

```


#### Fragments 19: `ACCOUNT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment AccountsAdminTable_AccountInlineFragment on Account @inline {
		id
		name
		groupAssociations {
			group {
				id
				name
			}
		}
		registeredAt
		...EditAccountButton_AccountFragment
		...EditUsersInAccountAdminButton_AccountFragment
		...AnonymizeAccountButton_AccountFragment
		...ChangeAccountGroupsAdminButton_AccountFragment
	}

```


#### Fragments 20: `AccountT_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment AnonymizeAccountButton_AccountFragment on Account {
        id
        name
    }

```


#### Fragments 21: `FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment AnonymizeUserButton_UserFragment on User {
        id
        name
    }

```


#### Fragments 22: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment AssignmentCard_ScenarioFragment on Scenario {
		...CheckScenarioPermissions_ScenarioFragment
		...personDetailsButton_ScenarioFragment
		budget {
			projectBudgets {
				projectRef
				assignmentBudgets {
					assignmentRef
					budgetedCost
					utilizedCost
					months
				}
			}
		}
		utilization {
			...personDetailsButton_ScenarioUtilizationFragment
		}
	}

```


#### Fragments 23: `ASSIGMENT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment AssignmentCard_AssignmentFragment on Assignment {
		id
		comment
		person {
			name
			assignmentRole {
				id
			}
			...personDetailsButton_PersonFragment
		}
		project {
			id
			...EditAssignmentButton_ProjectFragment
		}
		startDate
		endDate
		validAssignmentRoles {
			id
			name
		}
		isExecutive
		...EditAssignmentButton_AssignmentFragment
		...EmptyAssignmentButton_AssignmentFragment
		...DeleteAssignmentButton_AssignmentFragment
	}

```


#### Fragments 24: `ASSIGMENT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment AssignmentProjectCard_AssignmentFragment on Assignment {
		id

		project {
			name
			id
			isDeactivated
		}
		person {
			name
		}
		startDate
		endDate
		validAssignmentRoles {
			id
			name
		}
	}

```


#### Fragments 25: `ASSIGNMENT_ROLE_INLINE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment AssignmentRoleSelect_AssignmentRoleFragment on AssignmentRole @inline {
		id
		name
	}

```


#### Fragments 26: `FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment AssignmentRoleSortOrderButtons_AssignmentRoleFragment on AssignmentRole {
        id
        sortOrder
    }

```


#### Fragments 27: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment AssignmentRolesSelect_AssignmentRoleFragment on AssignmentRole @inline {
		id
		name
	}

```


#### Fragments 28: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment AssignmentsInProjectList_ScenarioFragment on Scenario {
		id
		...AssignmentCard_ScenarioFragment
		...CheckScenarioPermissions_ScenarioFragment
	}

```


#### Fragments 29: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment AssignmentsInProjectList_ProjectFragment on ProjectInScenario {
		id

		project {
			...CreateAssignmentButton_ProjectFragment
			...CreateAssignmentsFromTemplateButton_ProjectFragment
		}
		assignments {
			__id
			edges {
				node {
					id
					endDate
					...AssignmentCard_AssignmentFragment
					validAssignmentRoles {
						sortOrder
					}
				}
			}
		}
	}

```


#### Fragments 30: `FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment ChangeAccountGroupsAdminButton_AccountFragment on Account {
        ...ChangeAccountGroupsAdminModal_AccountFragment
    }

```


#### Fragments 31: `ACCOUNT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ChangeAccountGroupsAdminModal_AccountFragment on Account {
		id
		groupAssociations {
			group {
				id
				name
			}
		}
	}

```


#### Fragments 32: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ChangeLogoForm_CurrentUser on Query {
		Viewer {
			Auth {
				currentAccount {
					extensions {
						kind
						... on AccountSettingsAccountExtension {
							kind
							logo {
								id
							}
						}
					}
				}
			}
		}
	}

```


#### Fragments 33: `ASSIGNMENT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ChangePersonActivationButton_PersonFragment on Person {
		id
		isDeactivated
	}

```


#### Fragments 34: `ASSIGNMENT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ChangeProjectActivationButton_ProjectFragment on Project {
		id
		isDeactivated
	}

```


#### Fragments 35: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ChangeShowBudgetForm_CurrentUser on Query {
		Viewer {
			Auth {
				currentUser {
					user {
						extension {
							... on HarkinsUserExtensionAndId {
								showBudget
							}
						}
					}
				}
			}
		}
	}

```


#### Fragments 36: `FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment ChangeUserGroupsAdminButton_UserInAccountFragment on UserInAccount {
        ...ChangeUserGroupsAdminModal_UserInAccountFragment
    }

```


#### Fragments 37: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ChangeUserGroupsAdminModal_UserInAccountFragment on UserInAccount {
		id
		user {
			id
		}
		groups {
			id
		}
	}

```


#### Fragments 38: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment CheckScenarioPermissions_ScenarioFragment on Scenario {
		isMasterPlan
	}

```


#### Fragments 39: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment CloneScenarioButton_ScenarioFragment on Scenario {
		id
		name
	}

```


#### Fragments 40: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment CreateAssignmentButton_ProjectFragment on Project {
		id
		...EditAssignmentForm_ProjectFragment
	}

```


#### Fragments 41: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment CreateAssignmentsFromTemplateButton_ProjectFragment on Project {
		id
		...EditAssignmentForm_ProjectFragment
	}

```


#### Fragments 42: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment CurrentScenarioControl_ScenarioFragment on Scenario {
		id
		name
		isMasterPlan
	}

```


#### Fragments 43: `FRAGMENT`
**GraphQL Fragments:**
```graphql

  fragment DashboardHeader_ScenarioFragment on Scenario {
    id
    ...CurrentScenarioControl_ScenarioFragment
    ...ScenarioStatistics_ScenarioFragment
  }

```


#### Fragments 44: `ASSIGNMENT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment DeleteAssignmentButton_AssignmentFragment on Assignment {
		id
		validAssignmentRoles {
			name
		}
	}

```


#### Fragments 45: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment DivisionSelect_DivisionFragment on Division @inline{
        id
        name
    }


```


#### Fragments 46: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment DivisionsSelect_DivisionFragment on Division @inline{
        id
        name
    }


```


#### Fragments 47: `PROJECTS_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment DivisionsTable_DivisionListFragment on Query
	@refetchable(queryName: "DivisionsTable_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 20 }
		after: { type: "String" }
		filterByName: { type: "String" }
	) {
		Division {
			Divisions(first: $first, after: $after, filterByName: $filterByName)
				@connection(key: "DivisionsTable_Divisions") {
				__id
				pageInfo {
					endCursor
					hasPreviousPage
					hasNextPage
					startCursor
				}
				edges {
					node {
						id
						name
						...EditDivisionButton_DivisionFragment
					}
				}
			}
		}
	}

```


#### Fragments 48: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment EditAccountButton_AccountFragment on Account {
		...EditAccountModal_AccountFragment
	}

```


#### Fragments 49: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment EditAccountModal_AccountFragment on Account {
		id
		name
		registeredAt
	}

```


#### Fragments 50: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment EditAssignmentButton_ProjectFragment on Project {
		id
		...EditAssignmentForm_ProjectFragment
	}

```


#### Fragments 51: `ASSIGNMENT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment EditAssignmentButton_AssignmentFragment on Assignment {
		id
		startDate
		endDate
		person {
			id
		}
		validAssignmentRoles {
			id
		}
		importId
		isExecutive
		comment
		weight
	}

```


#### Fragments 52: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment EditDivisionButton_DivisionFragment on Division {
        ...EditDivisionModal_DivisionFragment
    }

```


#### Fragments 53: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment EditDivisionModal_DivisionFragment on Division {
		id
		name
	}

```


#### Fragments 54: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment EditPersonButton_PersonFragment on Person {
        ...EditPersonModal_PersonFragment
    }

```


#### Fragments 55: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment EditPersonModal_PersonFragment on Person {
		id
		name
		email
		phone
		salary
		laborBurdenMultiplier
		startDate
		assignmentRole {
			id
			name
		}
		associatedWithDivisions {
			id
			name
		}
		associatedWithRegions {
			id
			name
		}
		address {
			lineOne
			postalCode
			city
			state
			country
			longitude
			latitude
		}
		comment
		avatar {
			id
			url
		}
	}

```


#### Fragments 56: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment EditRegionButton_RegionFragment on Region {
        ...EditRegionModal_RegionFragment
    }

```


#### Fragments 57: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment EditRegionModal_RegionFragment on Region {
		id
		name
	}

```


#### Fragments 58: `FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment EditScenarioButton_ScenarioFragment on Scenario {
        id
        name
    }

```


#### Fragments 59: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment EditStaffingTemplateButton_StaffingTemplateFragment on StaffingTemplate {
        ...EditStaffingTemplateModal_StaffingTemplateFragment
    }

```


#### Fragments 60: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment EditStaffingTemplateModal_StaffingTemplateFragment on StaffingTemplate {
		id
		name
		assignmentRoleAssociations {
			assignmentRoleRef
			isExecutive
		}
	}

```


#### Fragments 61: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment EditUserButton_UserFragment on User {
		id
		name
		email
		activated
	}

```


#### Fragments 62: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment EditUsersInAccountAdminButton_AccountFragment on Account {
		...EditUsersInAccountAdminModal_AccountFragment
	}

```


#### Fragments 63: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment EditUsersInAccountAdminModal_AccountFragment on Account {
		id
		name
		registeredAt
	}

```


#### Fragments 64: `EmailTemplates_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment EmailTemplatesTable_EmailTemplatesListFragment on Query @refetchable(queryName: "EmailTemplatesTable_Refetch") @argumentDefinitions(
        first: {type: "Int"},
        after: {type: "String"},
    ){
        Admin {
            Email {
                PersonalizedEmailTemplates( first: $first, after: $after) @connection(key: "EmailTemplatesTable_PersonalizedEmailTemplates") {
                    pageInfo {
                        endCursor
                        hasPreviousPage
                        hasNextPage
                        startCursor
                    }
                    edges {
                        node {
                            id
                            template {
                                key
                                subject
                            }
                        }
                    }
                }
            }
        }
        ...NewEmailTemplateButton_AvailableTemplatesFragment
    }

```


#### Fragments 65: `ASSIGNMENT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment EmptyAssignmentButton_AssignmentFragment on Assignment {
		id
		validAssignmentRoles {
			name
		}
	}

```


#### Fragments 66: `FILES_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment FilesTable_FilesListFragment on Query
	@refetchable(queryName: "FilesTable_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 20 }
		after: { type: "String" }
		filterByName: { type: "String" }
		filterByFileTypes: { type: "[String!]" }
		filterByFromDateTimeInclusive: { type: "ZonedDateTIme" }
		filterByToDateTimeInclusive: { type: "ZonedDateTIme" }
		tagsIncluded: { type: "[String!]" }
	) {
		Admin {
			Files {
				Files(
					first: $first
					after: $after
					name: $filterByName
					fileType: $filterByFileTypes
					fromDateTimeInclusive: $filterByFromDateTimeInclusive
					toDateTimeInclusive: $filterByToDateTimeInclusive
					tagsIncluded: $tagsIncluded
				) @connection(key: "FilesTable_Files") {
					__id
					pageInfo {
						endCursor
						hasPreviousPage
						hasNextPage
						startCursor
					}
					edges {
						node {
							id
							name
							fileType
							accessType
							uploadDateTime
							thumbnail
							url
						}
					}
				}
			}
		}
	}

```


#### Fragments 67: `GAP_DAYS_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment GapDaysDisplay_GapDaysFragment on ScenarioGapDays {
        gapDays
        gapSalary
    }

```


#### Fragments 68: `ADDRESS_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment GoogleMapsClickout_AddressFragment on Address {
		latitude
		longitude
	}

```


#### Fragments 69: `LIST_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment InvitationsTable_InvitationsListFragment on Query @refetchable(queryName: "InvitationsTable_Refetch") @argumentDefinitions(
        first: {type: "Int", defaultValue: 20},
        after: {type: "String"},
    ){
        Management {
            InvitationsToAccount(first: $first, after: $after)  @connection(key: "InvitationsTable_InvitationsToAccount"){
                __id
                edges {
                    node {
                        id
                        email
                        invitingUserName
                    }
                }
            }
        }
    }

```


#### Fragments 70: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment MakeMasterPlanButton_ScenarioFragment on Scenario {
        id
        isMasterPlan
    }

```


#### Fragments 71: `AVAILABLE_EMAIL_TEMPLATES_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment NewEmailTemplateButton_AvailableTemplatesFragment on Query {
        Admin {
            Email {
                AvailableSystemTemplates {
                    key
                    previewText
                    subject
                    body
                    variables
                }
            }
        }
    }

```


#### Fragments 72: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment PeopleTable_PeopleListFragment on Query
	@refetchable(queryName: "PeopleTable_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 250 }
		after: { type: "String" }
		filterByName: { type: "String" }
	) {
		Staff {
			People(
				first: $first
				after: $after
				filterByName: $filterByName
				showDeactivated: true
			) @connection(key: "PeopleTable_People") {
				__id
				pageInfo {
					endCursor
					hasPreviousPage
					hasNextPage
					startCursor
				}
				edges {
					node {
						id
						...PeopleTable_PersonFragment
					}
				}
			}
		}
	}

```


#### Fragments 73: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment PeopleTable_PersonFragment on Person @inline {
		id
		isDeactivated
		name
		address {
			longitude
			latitude
			...GoogleMapsClickout_AddressFragment
		}
		startDate
		assignmentRole {
			name
		}
		associatedWithDivisions {
			id
			name
		}
		associatedWithRegions {
			id
			name
		}
		skills(first: 100) {
			edges {
				node {
					id
					data {
						value {
							... on NumericalAssessmentValue {
								kind
								number
							}
							... on BinaryAssessmentValue {
								hasSkill
								kind
							}
						}
					}
				}
			}
		}
		avatar {
			url
		}
		comment
		...EditPersonButton_PersonFragment
		...editPersonSkillAssociationsButton_PersonFragment
		...ChangePersonActivationButton_PersonFragment
	}

```


#### Fragments 74: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment PersonSelect_PersonFragment on Person @inline {
		id
		name
	}

```


#### Fragments 75: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ProjectDateTimeDisplay_ProjectFragment on Project {
		startDate
		endDate
		durationInMonths
	}

```


#### Fragments 76: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment ProjectStageSelect_ProjectStageFragment on ProjectStage @inline{
        id
        name
    }


```


#### Fragments 77: `FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment ProjectStageSortOrderButtons_ProjectStageFragment on ProjectStage {
        id
        sortOrder
    }

```


#### Fragments 78: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment ProjectStagesSelect_ProjectStageFragment on ProjectStage @inline{
        id
        name
    }


```


#### Fragments 79: `PROJECTS_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ProjectStagesTable_ProjectStageListFragment on Query
	@refetchable(queryName: "ProjectStagesTable_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 20 }
		after: { type: "String" }
		filterByName: { type: "String" }
	) {
		Project {
			ProjectStages(first: $first, after: $after, filterByName: $filterByName)
				@connection(key: "ProjectStagesTable_ProjectStages") {
				__id
				pageInfo {
					endCursor
					hasPreviousPage
					hasNextPage
					startCursor
				}
				edges {
					node {
						...ProjectStagesTable_ProjectStageFragment
					}
				}
			}
		}
	}

```


#### Fragments 80: `PROJECT_STAGE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ProjectStagesTable_ProjectStageFragment on ProjectStage @inline {
		id
		name
		sortOrder
		reverseProjectOrderInReports
		color
		...ProjectStageSortOrderButtons_ProjectStageFragment
		...editProjectStageButton_ProjectStageFragment
	}

```


#### Fragments 81: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment ProjectsSelectField_ProjectFragment on Project @inline{
        id
        name
    }


```


#### Fragments 82: `PROJECTS_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ProjectsTable_ProjectsListFragment on Query
	@refetchable(queryName: "ProjectsTable_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 200 }
		after: { type: "String" }
		filterByName: { type: "String" }
		filterByRegions: { type: "[ID!]" }
		filterByDivisions: { type: "[ID!]" }
		filterByStages: { type: "[ID!]" }
	) {
		Project {
			Projects(
				first: $first
				after: $after
				filterByName: $filterByName
				filterByRegions: $filterByRegions
				filterByDivisions: $filterByDivisions
				filterByStages: $filterByStages
				showDeactivated: true
			) @connection(key: "ProjectsTable_Projects") {
				__id
				pageInfo {
					endCursor
					hasPreviousPage
					hasNextPage
					startCursor
				}
				edges {
					node {
						id
						...ProjectsTable_ProjectFragment
					}
				}
			}
		}
	}

```


#### Fragments 83: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ProjectsTable_ProjectFragment on Project @inline {
		id
		name
		isDeactivated
		source

		division {
			id
			name
		}
		region {
			id
			name
		}
		startDate
		endDate

		stage {
			id
			name
		}

		address {
			latitude
			longitude
			...GoogleMapsClickout_AddressFragment
		}

		avatar {
			id
			url
		}

		...editProjectButton_ProjectFragment
		...ChangeProjectActivationButton_ProjectFragment
		...syncProjectFromDynamicsButton_ProjectFragment
		...syncProjectFromRandButton_ProjectFragment
	}

```


#### Fragments 84: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment RegionSelect_RegionFragment on Region @inline{
        id
        name
    }


```


#### Fragments 85: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment RegionsSelect_RegionFragment on Region @inline{
        id
        name
    }


```


#### Fragments 86: `PROJECTS_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment RegionsTable_RegionListFragment on Query
	@refetchable(queryName: "RegionsTable_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 20 }
		after: { type: "String" }
		filterByName: { type: "String" }
	) {
		Region {
			Regions(first: $first, after: $after, filterByName: $filterByName)
				@connection(key: "RegionsTable_Regions") {
				__id
				pageInfo {
					endCursor
					hasPreviousPage
					hasNextPage
					startCursor
				}
				edges {
					node {
						id
						name
						...EditRegionButton_RegionFragment
					}
				}
			}
		}
	}

```


#### Fragments 87: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment RosterList_ScenarioFragment on Scenario {
		id
		...CheckScenarioPermissions_ScenarioFragment
		...personCardDraggable_ScenarioFragment
		...personCard_ScenarioFragment

		utilization {
			...personCard_ScenarioUtilizationFragment
		}
	}

```


#### Fragments 88: `STAFF_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment RosterList_StaffFragment on Query
	@refetchable(queryName: "RosterList_StaffRefetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 250 }
		after: { type: "String" }
		filterByName: { type: "String" }
		scenarioRef: { type: "ID!" }
		filterByAssignmentRoles: { type: "[ID!]" }
		filterByUtilizationStatus: { type: "[UtilizationStatus!]" }
		filterBySalaryMinimum: { type: "BigDecimal" }
		filterBySalaryMaximum: { type: "BigDecimal" }
		filterByFreeDateMinimum: { type: "LocalDate" }
		filterByFreeDateMaximum: { type: "LocalDate" }
		filterByAllocatedDateMinimum: { type: "LocalDate" }
		filterByAllocatedDateMaximum: { type: "LocalDate" }
		filterByGapDaysMinimum: { type: "Int" }
		filterByGapDaysMaximum: { type: "Int" }
		filterByDistanceMinimum: { type: "Int" }
		filterByDistanceMaximum: { type: "Int" }
		filterBySkills: { type: "[SkillFilter!]" }
		filterByStaff: { type: "[ID!]" }
		sortByClosestToProject: { type: "ID" }
		filterByRegions: { type: "[ID!]" }
		filterByDivisions: { type: "[ID!]" }
		utilizationWindow: { type: "UtilizationWindowInput" }
	) {
		node(id: $scenarioRef) {
			... on Scenario {
				utilizationWithStandAndEndDate(utilizationWindow: $utilizationWindow) {
					...personCard_ScenarioUtilizationFragment
				}
			}
		}
		Staff {
			People(
				first: $first
				after: $after
				filterByName: $filterByName
				scenarioRef: $scenarioRef
				alwaysIncludeIds: $filterByStaff
				filterByAssignmentRoles: $filterByAssignmentRoles
				filterByUtilizationStatus: $filterByUtilizationStatus
				filterBySalaryMinimum: $filterBySalaryMinimum
				filterBySalaryMaximum: $filterBySalaryMaximum
				filterByFreeDateMinimum: $filterByFreeDateMinimum
				filterByFreeDateMaximum: $filterByFreeDateMaximum
				filterByAllocatedDateMinimum: $filterByAllocatedDateMinimum
				filterByAllocatedDateMaximum: $filterByAllocatedDateMaximum
				filterByGapDaysMinimum: $filterByGapDaysMinimum
				filterByGapDaysMaximum: $filterByGapDaysMaximum
				filterByDistanceMinimum: $filterByDistanceMinimum
				filterByDistanceMaximum: $filterByDistanceMaximum
				filterBySkills: $filterBySkills
				sortByClosestToProject: $sortByClosestToProject
				filterByDivisions: $filterByDivisions
				filterByRegions: $filterByRegions
				utilizationWindow: $utilizationWindow
			) @connection(key: "RosterList_People") {
				pageInfo {
					endCursor
					hasPreviousPage
					hasNextPage
					startCursor
				}
				edges {
					node {
						id
						...personCardDraggable_PersonFragment @arguments(scenarioId: $scenarioRef)
						...personCard_PersonFragment @arguments(scenarioId: $scenarioRef)

						distance(projectRef: $sortByClosestToProject)
						name
						address {
							latitude
							longitude
							lineOne
							postalCode
							city
							state
						}
					}
				}
			}
		}
	}

```


#### Fragments 89: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ScenarioStatistics_ScenarioFragment on Scenario {
		gapDays {
			...GapDaysDisplay_GapDaysFragment
		}
		utilization {
			...UtilizationDisplay_UtilizationFragment
		}
	}

```


#### Fragments 90: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ScenariosTable_ScenariosListFragment on Query
	@refetchable(queryName: "ScenariosTable_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 20 }
		after: { type: "String" }
		filterByName: { type: "String" }
	) {
		Scenario {
			Scenarios(first: $first, after: $after, filterByName: $filterByName)
				@connection(key: "ScenariosTable_Scenarios") {
				__id
				pageInfo {
					endCursor
					hasPreviousPage
					hasNextPage
					startCursor
				}
				edges {
					node {
						id
						...ScenariosTable_ScenarioFragment
					}
				}
			}
		}
	}

```


#### Fragments 91: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ScenariosTable_ScenarioFragment on Scenario @inline {
		id
		name
		isMasterPlan
		lastUpdatedAt
		...EditScenarioButton_ScenarioFragment
		...CheckScenarioPermissions_ScenarioFragment
		...MakeMasterPlanButton_ScenarioFragment
		...CloneScenarioButton_ScenarioFragment
		...ToggleVisibilityButton_ScenarioFragment
	}

```


#### Fragments 92: `USERS_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment SelectUserField_UserFragment on User @inline {
		id
		name
	}

```


#### Fragments 93: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment SkillCategorySelect_SkillCategoryFragment on SkillCategory @inline {
		id
		name
	}

```


#### Fragments 94: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment SkillCategorySortOrderButtons_AssignmentRoleFragment on SkillCategory {
		id
		name
		sortOrder
	}

```


#### Fragments 95: `PROJECTS_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment SkillsTable_SkillsListFragment on Query
	@refetchable(queryName: "SkillsTable_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 20 }
		after: { type: "String" }
		filterByName: { type: "String" }
		filterBySkillCategoryRef: { type: "ID" }
	) {
		Skills {
			Skills(
				first: $first
				after: $after
				filterByName: $filterByName
				filterBySkillCategoryRef: $filterBySkillCategoryRef
			) @connection(key: "SkillsTable_Skills") {
				__id
				pageInfo {
					endCursor
					hasPreviousPage
					hasNextPage
					startCursor
				}
				edges {
					node {
						id
						name
						skillCategory {
							id
							name
							sortOrder
						}
						...editSkillButton_SkillFragment
					}
				}
			}
		}
	}

```


#### Fragments 96: `FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment StaffingTemplateSelect_StaffingTemplateFragment on StaffingTemplate @inline{
        id
        name
    }


```


#### Fragments 97: `PROJECTS_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment StaffingTemplatesTable_StaffingTemplateListFragment on Query
	@refetchable(queryName: "StaffingTemplatesTable_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 20 }
		after: { type: "String" }
		filterByName: { type: "String" }
	) {
		Template {
			StaffingTemplates(first: $first, after: $after, filterByName: $filterByName)
				@connection(key: "StaffingTemplatesTable_StaffingTemplates") {
				__id
				pageInfo {
					endCursor
					hasPreviousPage
					hasNextPage
					startCursor
				}
				edges {
					node {
						id
						name
						assignmentRoleAssociations {
							assignmentRole {
								id
								name
							}
							isExecutive
						}
						...EditStaffingTemplateButton_StaffingTemplateFragment
					}
				}
			}
		}
	}

```


#### Fragments 98: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment ToggleVisibilityButton_ScenarioFragment on Scenario {
        id
        isPublic
        isMasterPlan
    }

```


#### Fragments 99: `SCENARIOS_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment UserScenariosTable_ScenariosListFragment on Query
	@refetchable(queryName: "UserScenariosTable_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 20 }
		after: { type: "String" }
		onlyShowMine: { type: "Boolean" }
	) {
		Scenario {
			Scenarios(first: $first, after: $after, onlyShowMine: $onlyShowMine)
				@connection(key: "UserScenariosTable_Scenarios") {
				__id
				pageInfo {
					endCursor
					hasPreviousPage
					hasNextPage
					startCursor
				}
				edges {
					node {
						id
						...UserScenariosTable_ScenarioFragment
					}
				}
			}
		}
	}

```


#### Fragments 100: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment UserScenariosTable_ScenarioFragment on Scenario @inline {
		id
		name
		isMasterPlan
		lastUpdatedAt
		gapDays {
			gapDays
			gapSalary
		}
		utilization {
			unusedSalary
			averageUtilizationPercentage
		}
		...CheckScenarioPermissions_ScenarioFragment
		...MakeMasterPlanButton_ScenarioFragment
		...CloneScenarioButton_ScenarioFragment
		...ToggleVisibilityButton_ScenarioFragment
	}

```


#### Fragments 101: `LIST_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment UsersTable_UsersListFragment on Query @refetchable(queryName: "UsersTable_Refetch") @argumentDefinitions(
        first: {type: "Int", defaultValue: 20},
        after: {type: "String"},
    ){
        Admin {
            Management {
                UsersAdmin(first: $first, after: $after)  @connection(key: "UsersTable_UsersAdmin"){
                    __id
                    edges {
                        node {
                            id
                            name
                            email
                            activated
                            groupAssociations {
                                account {
                                    name
                                }
                                group {
                                    id
                                    name
                                }
                            }
                            ...EditUserButton_UserFragment
                            ...AnonymizeUserButton_UserFragment
                        }
                    }
                }
            }
        }
    }

```


#### Fragments 102: `GAP_DAYS_FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment UtilizationDisplay_UtilizationFragment on ScenarioUtilization {
        averageUtilizationPercentage
        unusedSalary
    }

```


#### Fragments 103: `FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment UtilizationOverTimeGraph_PersonFragment on Person @argumentDefinitions(scenarioId: {type: "ID!"}) {
        name
        utilizationOverTime(scenarioRef: $scenarioId) {
            date
            utilizationPercentage
        }
    }

```


#### Fragments 104: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment addProjectToScenarioCard_ScenarioFragment on Scenario
	@argumentDefinitions(
		projectFilters: { type: "ProjectWithAssignmentsFiltersInput" }
		personOnAssignmentFilters: { type: "PersonOnAssignmentFiltersInput" }
	) {
		...addProjectToScenarioModal_ScenarioFragment
			@arguments(
				projectFilters: $projectFilters
				personOnAssignmentFilters: $personOnAssignmentFilters
			)
		isMasterPlan
	}

```


#### Fragments 105: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment addProjectToScenarioModal_ScenarioFragment on Scenario
	@argumentDefinitions(
		projectFilters: { type: "ProjectWithAssignmentsFiltersInput" }
		personOnAssignmentFilters: { type: "PersonOnAssignmentFiltersInput" }
	) {
		id
		projects(
			projectWithAssignmentsFilters: $projectFilters
			peopleOnAssignmentFilters: $personOnAssignmentFilters
		) {
			edges {
				node {
					id
					project {
						name
						source
					}
				}
			}
		}
	}

```


#### Fragments 106: `CHANGE_USER_IN_ACCOUNT_GROUPS_BUTTON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment changeUserInAccountGroupsButton_UserInAccountFragment on UserInAccount {
		...changeUserInAccountGroupsModal_UserInAccountFragment
	}

```


#### Fragments 107: `CHANGE_USER_IN_ACCOUNT_GROUPS_MODAL_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment changeUserInAccountGroupsModal_UserInAccountFragment on UserInAccount {
		id
		user {
			id
		}
		groups {
			id
		}
	}

```


#### Fragments 108: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editProjectButton_ProjectFragment on Project {
		id
		name
		startDate
		endDate
		address {
			lineOne
			city
			postalCode
			state
			country
			latitude
			longitude
		}
		source
		architectName
		clientName
		stage {
			id
			name
		}
		skills {
			id
		}
		volume
		generalConditionsPercentage
		budgetedLaborCosts
		division {
			id
		}
		region {
			id
		}
		projectIdentifier
		durationInMonths
		avatar {
			id
			url
		}
		milestones {
			name
			date
		}
		comments
		source
	}

```


#### Fragments 109: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editProjectStageButton_ProjectStageFragment on ProjectStage {
		...editProjectStageModal_ProjectStageFragment
	}

```


#### Fragments 110: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editProjectStageModal_ProjectStageFragment on ProjectStage {
		id
		name
		reverseProjectOrderInReports
		sortOrder
		color
	}

```


#### Fragments 111: `SKILL_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editSkillAssociationModal_SkillFragment on Skill {
		name
		dimension {
			kind
			... on NumericalDimension {
				kind
			}
			... on SkillDimensionInterface {
				kind
			}
		}
		...editBinarySkillAssociationModal_SkillFragment
		...editNumericalSkillAssociationModal_SkillFragment
	}

```


#### Fragments 112: `SKILL_ASSOCIATION_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editSkillAssociationModal_SkillAssociationFragment on SkillAssociation {
		id
		data {
			value {
				... on NumericalAssessmentValue {
					kind
					number
				}
				... on BinaryAssessmentValue {
					kind
					hasSkill
				}
			}
			skill {
				name
				skillCategory {
					name
				}
				dimension {
					... on BinaryDimension {
						kind
					}
					... on NumericalDimension {
						dimensionCount
						kind
					}
				}
			}
		}

		...editNumericalSkillAssociationModal_SkillAssociationFragment
		...editBinarySkillAssociationModal_SkillAssociationFragment
	}

```


#### Fragments 113: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editSkillAssociationModal_PersonFragment on Person {
		name
		id
		...editNumericalSkillAssociationModal_PersonFragment
		...editBinarySkillAssociationModal_PersonFragment
	}

```


#### Fragments 114: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editBinarySkillAssociationModal_PersonFragment on Person {
		id
		name
	}

```


#### Fragments 115: `SKILL_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editBinarySkillAssociationModal_SkillFragment on Skill {
		id
		name
	}

```


#### Fragments 116: `SKILL_ASSOCIATION_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editBinarySkillAssociationModal_SkillAssociationFragment on SkillAssociation {
		id
		data {
			value {
				... on BinaryAssessmentValue {
					kind
					hasSkill
				}
				... on NumericalAssessmentValue {
					kind
					number
				}
			}
			skill {
				id
				name
				skillCategory {
					name
				}
				dimension {
					... on BinaryDimension {
						kind
					}
					... on NumericalDimension {
						dimensionCount
						kind
					}
				}
			}
		}
	}

```


#### Fragments 117: `SKILL_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editNumericalSkillAssociationModal_SkillFragment on Skill {
		id
		name
	}

```


#### Fragments 118: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editNumericalSkillAssociationModal_PersonFragment on Person {
		id
		name
	}

```


#### Fragments 119: `SKILL_ASSOCIATION_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editNumericalSkillAssociationModal_SkillAssociationFragment on SkillAssociation {
		id
		data {
			skill {
				id
				name
				skillCategory {
					name
				}
				dimension {
					... on BinaryDimension {
						kind
					}
					... on NumericalDimension {
						dimensionCount
						kind
					}
				}
			}
			value {
				... on BinaryAssessmentValue {
					hasSkill
					kind
				}
				... on NumericalAssessmentValue {
					number
					kind
				}
			}
		}
	}

```


#### Fragments 120: `SKILL_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editSkillButton_SkillFragment on Skill {
		id
		name
		skillCategory {
			id
		}
		description
		dimension {
			kind
			... on NumericalDimension {
				kind
				dimensionCount
				dimensionExplanations
			}
			... on BinaryDimension {
				kind
			}
		}
	}

```


#### Fragments 121: `EDIT_USER_IN_ACCOUNT_GROUP_BUTTON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editUserInAccountGroupButton_GroupFragment on UserInAccountGroup {
		...editUserInAccountGroupModal_GroupFragment
	}

```


#### Fragments 122: `EDIT_USER_IN_ACCOUNT_GROUP_MODAL_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editUserInAccountGroupModal_GroupFragment on UserInAccountGroup {
		id
		name
		permissions
	}

```


#### Fragments 123: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment peopleSelect_PersonFragment on Person @inline {
		id
		name
	}

```


#### Fragments 124: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment projectCard_ScenarioFragment on Scenario {
		id
		...AssignmentsInProjectList_ScenarioFragment

		budget {
			projectBudgets {
				projectRef
				maximumBudget
				budgetedCost
				utilizedCost
			}
		}
	}

```


#### Fragments 125: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment projectCard_ProjectFragment on ProjectInScenario {
		id
		project {
			id
			name
			startDate
			endDate
			address {
				lineOne
				city
				country
				postalCode
				state
				latitude
				longitude
			}
			stage {
				color
			}
			...editProjectButton_ProjectFragment
			...ProjectDateTimeDisplay_ProjectFragment
		}
		assignments {
			edges {
				node {
					person {
						id
					}
				}
			}
		}
		...AssignmentsInProjectList_ProjectFragment
		...projectDetailsButton_ProjectInScenario
	}

```


#### Fragments 126: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment projectDetailsButton_ProjectInScenario on ProjectInScenario {
		project {
			id
			name
		}
	}

```


#### Fragments 127: `PROJECT_IN_SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment projectDetailsControl_ProjectInScenarioFragment on ProjectInScenario {
		id
		project {
			id
			name
			startDate
			endDate
			skills {
				name
			}
			address {
				lineOne
				postalCode
				city
				country
				state
				latitude
				longitude
			}
			avatar {
				url
			}
			skillMatrixByCategories {
				...projectDetailsControl_CategoryWithMatrixTypeInlineFragment
			}
			...ProjectDateTimeDisplay_ProjectFragment
		}
	}

```


#### Fragments 128: `CATEGORY_WITH_MATRIX_TYPE_INLINE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment projectDetailsControl_CategoryWithMatrixTypeInlineFragment on CategoryWithMatrixType
	@inline {
		matrix {
			columns {
				key
			}
			headerRow {
				key
				entries {
					id
					name
					skillCategory {
						id
						name
					}
				}
			}
			bodyRows {
				key
				entries {
					value {
						id
						data {
							value {
								kind
								... on BinaryAssessmentValue {
									hasSkill
									kind
								}
								... on NumericalAssessmentValue {
									kind
									number
								}
							}
							skill {
								id
								name
								dimension {
									kind
									... on NumericalDimension {
										dimensionCount
										kind
									}
									... on BinaryDimension {
										kind
									}
								}
							}
						}
					}
				}
			}
		}
		category {
			id
			name
		}
	}

```


#### Fragments 129: `USER_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment selectUserInAccountField_PersonFragment on Person @inline {
		id
		name
	}

```


#### Fragments 130: `SKILL_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment skillMultiSelect_SkillFragment on Skill @inline {
		name
		id
	}

```


#### Fragments 131: `SKILL_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment skillMultiSelectV2_SkillFragment on Skill @inline {
		name
		id
		skillCategory {
			id
			name
		}
	}

```


#### Fragments 132: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment syncProjectFromDynamicsButton_ProjectFragment on Project {
		id
		name
		address {
			lineOne
			city
			postalCode
			state
			country
			latitude
			longitude
		}
		projectIdentifier
		architectName
		avatar {
			id
			url
		}
		skills {
			id
		}
		clientName
		startDate
		endDate
		division {
			id
		}
		region {
			id
		}
		stage {
			id
		}
		volume
		generalConditionsPercentage
		budgetedLaborCosts
		milestones {
			name
			date
		}
		comments
	}

```


#### Fragments 133: `PROJECT_SYNC_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment syncProjectFromDynamicsButton_SyncProjectFragment on Project @inline {
		id
		name
		address {
			lineOne
			city
			postalCode
			state
			country
			latitude
			longitude
		}
		projectIdentifier
		architectName
		avatar {
			id
			url
		}
		skills {
			id
		}
		clientName
		startDate
		endDate
		division {
			id
		}
		region {
			id
		}
		stage {
			id
		}
		volume
		generalConditionsPercentage
		budgetedLaborCosts
		milestones {
			name
			date
		}
		comments
	}

```


#### Fragments 134: `USER_IN_ACCOUNT_GROUPS_TABLE_LIST_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment userInAccountGroupsTable_GroupListFragment on Query
	@refetchable(queryName: "userInAccountGroupsTable_Refetch")
	@argumentDefinitions(first: { type: "Int", defaultValue: 20 }, after: { type: "String" }) {
		Management {
			Groups(first: $first, after: $after)
				@connection(key: "userInAccountGroupsTable_Groups") {
				__id
				edges {
					node {
						...userInAccountGroupsTable_userInAccountGroupInlineFragment
					}
				}
			}
		}
	}

```


#### Fragments 135: `USER_IN_ACCOUNT_GROUP_INLINE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment userInAccountGroupsTable_userInAccountGroupInlineFragment on UserInAccountGroup
	@inline {
		id
		name
		permissions
		...editUserInAccountGroupButton_GroupFragment
	}

```


#### Fragments 136: `USERS_IN_ACCOUNT_ADMIN_TABLE_LIST_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment usersInAccountAdminTable_UsersInAccountListFragment on Query
	@refetchable(queryName: "usersInAccountAdminTable_Refetch")
	@argumentDefinitions(
		accountId: { type: "ID!" }
		first: { type: "Int", defaultValue: 20 }
		after: { type: "String" }
	) {
		Admin {
			Management {
				UsersInAccountAdmin(accountId: $accountId, first: $first, after: $after)
					@connection(key: "usersInAccountAdminTable_UsersInAccountAdmin") {
					__id
					pageInfo {
						endCursor
						hasPreviousPage
						hasNextPage
						startCursor
					}
					edges {
						node {
							...usersInAccountAdminTable_UserInlineFragment
						}
					}
				}
			}
		}
	}

```


#### Fragments 137: `USERS_IN_ACCOUNT_ADMIN_TABLE_INLINE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment usersInAccountAdminTable_UserInlineFragment on UserInAccount @inline {
		id
		user {
			id
			email
			name
			activated
		}
		groups {
			id
			name
		}
		...ChangeUserGroupsAdminButton_UserInAccountFragment
	}

```


#### Fragments 138: `USERS_IN_ACCOUNT_TABLE_LIST_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment usersInAccountTable_UsersInAccountListFragment on Query
	@refetchable(queryName: "usersInAccountTable_Refetch")
	@argumentDefinitions(first: { type: "Int", defaultValue: 20 }, after: { type: "String" }) {
		Management {
			UsersInAccount(first: $first, after: $after)
				@connection(key: "usersInAccountTable_UsersInAccount") {
				__id
				edges {
					node {
						id
						user {
							id
							email
							name
						}
						groups {
							id
							name
						}
						...changeUserInAccountGroupsButton_UserInAccountFragment
					}
				}
			}
		}
	}

```


#### Fragments 139: `SCENARIO_INLINE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment scenarioSelectField_ScenarioInlineFragment on Scenario @inline {
		id
		name
		isMasterPlan
		isPublic
	}

```


#### Fragments 140: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment syncProjectFromRandButton_ProjectFragment on Project {
		id
		name
		address {
			lineOne
			city
			postalCode
			state
			country
			latitude
			longitude
		}
		projectIdentifier
		architectName
		avatar {
			id
			url
		}
		skills {
			id
		}
		clientName
		startDate
		endDate
		division {
			id
		}
		region {
			id
		}
		stage {
			id
		}
		volume
		generalConditionsPercentage
		budgetedLaborCosts
		milestones {
			name
			date
		}
		comments
		source
	}

```


#### Fragments 141: `PROJECT_SYNC_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment syncProjectFromRandButton_SyncProjectFragment on Project @inline {
		id
		name
		address {
			lineOne
			city
			postalCode
			state
			country
			latitude
			longitude
		}
		projectIdentifier
		architectName
		avatar {
			id
			url
		}
		skills {
			id
		}
		clientName
		startDate
		endDate
		division {
			id
		}
		region {
			id
		}
		stage {
			id
		}
		volume
		generalConditionsPercentage
		budgetedLaborCosts
		milestones {
			name
			date
		}
		comments
		source
	}

```


#### Fragments 142: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment syncWithRandPreconDwhButton_ScenarioFragment on Scenario {
		id
		isMasterPlan
	}

```


#### Fragments 143: `FRAGMENT`
**GraphQL Fragments:**
```graphql

    fragment BaseHeader_LogoFragment on File {
        url
    }

```


#### Fragments 144: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment EditAssignmentForm_ProjectFragment on Project {
		startDate
		endDate
	}

```


#### Fragments 145: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment FilterViewSelector_QueryFragment on Query
	@argumentDefinitions(filterByViewType: { type: "ViewType!" }) {
		Views {
			ViewOptions(first: 20, filterByViewType: $filterByViewType)
				@connection(key: "FilterViewSelector_ViewOptions") {
				__id
				edges {
					node {
						id
						name
						viewType
						url
						isDefault
					}
				}
			}
		}
	}

```


#### Fragments 146: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment baseScreen_QueryFragment on Query {
		Viewer {
			Auth {
				currentAccount {
					extensions {
						kind
						... on AccountSettingsAccountExtension {
							kind
							logo {
								...BaseHeader_LogoFragment
							}
						}
					}
				}
			}
		}
	}

```


#### Fragments 147: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment updateAssignmentsFromDynamicsButton_ScenarioFragment on Scenario {
		id
	}

```


#### Fragments 148: `ACCOUNT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment updateAssignmentsFromDynamicsButton_AccountFragment on Account {
		id
	}

```


#### Fragments 149: `CURRENT_USER_INLINE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment PermissionBasedNavigation_CurrentUser on CurrentUser @inline {
		permissionsInAccount
		user {
			name
			id
			extension {
				... on HarkinsUserExtensionAndId {
					showBudget
					preferredViewType
					showVolumePerPerson
				}
			}
		}
		accounts {
			id
			name
		}
	}

```


#### Fragments 150: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editAccountSettingsForm_QueryFragment on Query {
		Viewer {
			Auth {
				currentAccount {
					extensions {
						kind
						... on TwoFAAccountExtension {
							kind
							force2FA
						}
					}
				}
			}
		}
	}

```


#### Fragments 151: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editAssessmentPasswordForm_QueryFragment on Query {
		Viewer {
			Auth {
				currentAccount {
					extensions {
						kind
						... on AssessmentAccountExtension {
							kind
							password
						}
					}
				}
			}
		}
	}

```


#### Fragments 152: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editAzureAdSsoConfigurationForm_QueryFragment on Query {
		Viewer {
			Auth {
				currentAccount {
					extensions {
						kind
						... on TwoFAAccountExtension {
							force2FA
							kind
						}
						... on AuthProviderAccountExtension {
							kind
							authProviders {
								... on AzureAdAuthProvider {
									isActivated
									applicationId
									authorityUrl
									domain
									tenantId
									secret
									kind
								}
							}
						}
					}
				}
			}
		}
	}

```


#### Fragments 153: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editNumericalDimensionExplanationsForm_QueryFragment on Query {
		Viewer {
			Auth {
				currentAccount {
					extensions {
						kind
						... on AccountSettingsAccountExtension {
							kind
							numericalDimensionExplanations
						}
					}
				}
			}
		}
	}

```


#### Fragments 154: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment assignmentRolesTable_AssignmentRolesQueryFragment on Query
	@refetchable(queryName: "assignmentRolesTable_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 20 }
		after: { type: "String" }
		filterByName: { type: "String" }
	) {
		Assignments {
			AssignmentRoles(first: $first, after: $after, filterByName: $filterByName)
				@connection(key: "assignmentRolesTable_AssignmentRoles") {
				__id
				pageInfo {
					endCursor
					hasPreviousPage
					hasNextPage
					startCursor
				}
				edges {
					node {
						id
						name
						sortOrder
						maxNumberOfProjects
						utilizationProjectionCapInMonths
						countAsFullyAllocatedAtPercentage
						countAsOverallocatedAtPercentage
						...editAssignmentRoleButton_AssignmentRoleFragment
						...AssignmentRoleSortOrderButtons_AssignmentRoleFragment
					}
				}
			}
		}
	}

```


#### Fragments 155: `SCENARIO_QUERY`
**GraphQL Fragments:**
```graphql

	fragment availabilityForecastScreen_ScenarioFragment on Scenario {
		id
		...DashboardHeader_ScenarioFragment
	}

```


#### Fragments 156: `EMAIL_TEMPLATE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment EditEmailTemplateScreen_EmailTemplateFragment on PersonalizedEmailTemplate {
		id
		template {
			key
			subject
			previewText
			body
			variables
		}
	}

```


#### Fragments 157: `SCENARIO_QUERY`
**GraphQL Fragments:**
```graphql

	fragment ScenarioMapViewScreen_ScenarioFragment on Scenario {
		id
		...ProjectMapPart_ScenarioFragment
		...rosterPart_ScenarioFragment
		...DashboardHeader_ScenarioFragment
		projects {
			edges {
				node {
					id
					project {
						id
					}
					...ProjectMapPart_ProjectInScenarioFragment
				}
			}
		}
	}

```


#### Fragments 158: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ProjectMap_ProjectFragment on ProjectInScenario {
		id
		project {
			name
			address {
				latitude
				longitude
			}
		}
	}

```


#### Fragments 159: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ProjectMapPart_ScenarioFragment on Scenario {
		id
		...AssignmentsInProjectList_ScenarioFragment
	}

```


#### Fragments 160: `PROJECT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ProjectMapPart_ProjectInScenarioFragment on ProjectInScenario {
		project {
			name
		}
		...AssignmentsInProjectList_ProjectFragment
		...ProjectMap_ProjectFragment
	}

```


#### Fragments 161: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editPersonSkillAssociationsButton_PersonFragment on Person {
		name
		...editPersonSkillAssociationsModalContent_PersonFragment
	}

```


#### Fragments 162: `PERSON_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editPersonSkillAssociationsModalContent_PersonFragment on Person {
		id
		name
		skills(first: 100) @connection(key: "Person_skills") {
			__id
			edges {
				node {
					id
					data {
						value {
							... on NumericalAssessmentValue {
								kind
								number
							}
							... on BinaryAssessmentValue {
								hasSkill
								kind
							}
						}
						skill {
							id
							name
							dimension {
								... on NumericalDimension {
									kind
									dimensionCount
									dimensionExplanations
								}
								... on BinaryDimension {
									kind
								}
							}
						}
					}
					...editSkillAssociationModal_SkillAssociationFragment
				}
			}
		}
		...editSkillAssociationModal_PersonFragment
	}

```


#### Fragments 163: `SKILL_INLINE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editPersonSkillAssociationsModalContent_SkillInlineFragment on Skill @inline {
		id
		name
		description
		skillCategory {
			id
			name
		}

		dimension {
			kind
			... on NumericalDimension {
				kind
				dimensionCount
				dimensionExplanations
			}
			... on BinaryDimension {
				kind
			}
		}
		...editSkillAssociationModal_SkillFragment
		...numericalSkillTooltipIcon_SkillFragment
	}

```


#### Fragments 164: `SKILL_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment numericalSkillTooltipIcon_SkillFragment on Skill {
		dimension {
			kind
			... on NumericalDimension {
				dimensionExplanations
				dimensionCount
			}
		}
	}

```


#### Fragments 165: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment authenticatorAppSlot_QueryFragment on Query {
		Viewer {
			Auth {
				twoFactorAuthToken {
					...authenticatorAppSlot_TwoFactorAuthTokenInlineFragment
				}
			}
		}
	}

```


#### Fragments 166: `TWO_FACTOR_AUTH_TOKEN_INLINE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment authenticatorAppSlot_TwoFactorAuthTokenInlineFragment on TwoFactorAuthToken @inline {
		id
		data {
			isActivated
			activatedAt
		}
	}

```


#### Fragments 167: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment recoveryCodesSlot_QueryFragment on Query {
		Viewer {
			Auth {
				recoveryCodeCredentials {
					...recoveryCodesSlot_RecoveryCodeCredentialsInlineFragment
				}
				twoFactorAuthToken {
					data {
						isActivated
					}
				}
			}
		}
	}

```


#### Fragments 168: `RECOVERY_CODE_CREDENTIALS_INLINE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment recoveryCodesSlot_RecoveryCodeCredentialsInlineFragment on RecoveryCodeCredentials
	@inline {
		id
		data {
			credentials
		}
	}

```


#### Fragments 169: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment twoFactorAuthForm_QueryFragment on Query {
		Viewer {
			Auth {
				twoFactorAuthToken {
					id
					createdAt
					data {
						isActivated
					}
				}
			}
		}
		...authenticatorAppSlot_QueryFragment
		...recoveryCodesSlot_QueryFragment
	}

```


#### Fragments 170: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment preferredViewTypeForm_CurrentUser on Query {
		Viewer {
			Auth {
				currentUser {
					user {
						extension {
							... on HarkinsUserExtensionAndId {
								preferredViewType
							}
						}
					}
				}
			}
		}
	}

```


#### Fragments 171: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment volumePerPersonForm_CurrentUser on Query {
		Viewer {
			Auth {
				currentUser {
					user {
						extension {
							... on HarkinsUserExtensionAndId {
								showVolumePerPerson
							}
						}
					}
				}
			}
		}
	}

```


#### Fragments 172: `SCENARIO_QUERY`
**GraphQL Fragments:**
```graphql

	fragment ScenarioProjectViewScreen_ScenarioFragment on Scenario
	@argumentDefinitions(
		utilizationWindow: { type: "UtilizationWindowInput" }
		projectFilters: { type: "ProjectWithAssignmentsFiltersInput" }
		personOnAssignmentFilters: { type: "PersonOnAssignmentFiltersInput" }
	) {
		id
		...ProjectsGridPart_ScenarioFragment
			@arguments(
				projectFilters: $projectFilters
				personOnAssignmentFilters: $personOnAssignmentFilters
			)
		...rosterPart_ScenarioFragment
		...DashboardHeader_ScenarioFragment

		utilizationWithStandAndEndDate(utilizationWindow: $utilizationWindow) {
			...personCard_ScenarioUtilizationFragment
		}
	}

```


#### Fragments 173: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment projectStagesTabs_ProjectStages on Query {
		Project {
			ProjectStages(first: 100) {
				edges {
					node {
						id
						name
						sortOrder
						...projectStagesTab_ProjectStageFragment
					}
				}
			}
		}
	}

```


#### Fragments 174: `PROJECT_STAGE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment projectStagesTab_ProjectStageFragment on ProjectStage {
		id
		name
		sortOrder
	}

```


#### Fragments 175: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment projectViewFiltersPart_ScenarioFragment on Scenario {
		id
	}

```


#### Fragments 176: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment projectViewFiltersPart_QueryFragment on Query {
		Division {
			Divisions {
				edges {
					node {
						id
						name
					}
				}
			}
		}
		Region {
			Regions {
				edges {
					node {
						id
						name
					}
				}
			}
		}
		Project {
			ProjectStages(first: 100) {
				edges {
					node {
						id
						name
					}
				}
			}
		}
	}

```


#### Fragments 177: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ProjectsGridPart_QueryFragment on Query {
		...projectStagesTabs_ProjectStages
		...FilterViewSelector_QueryFragment @arguments(filterByViewType: ProjectView)
		...projectViewFiltersPart_QueryFragment
		Viewer {
			Auth {
				currentAccount {
					...updateAssignmentsFromDynamicsButton_AccountFragment
				}
			}
		}
	}

```


#### Fragments 178: `FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment ProjectsGridPart_ScenarioFragment on Scenario
	@argumentDefinitions(
		projectFilters: { type: "ProjectWithAssignmentsFiltersInput" }
		personOnAssignmentFilters: { type: "PersonOnAssignmentFiltersInput" }
	) {
		id
		...projectsGridPartContent_ScenarioFragment
			@arguments(
				projectFilters: $projectFilters
				personOnAssignmentFilters: $personOnAssignmentFilters
			)
		...updateAssignmentsFromDynamicsButton_ScenarioFragment
		...projectViewFiltersPart_ScenarioFragment
		...syncWithRandPreconDwhButton_ScenarioFragment
		...loadPursuitProjectsFromRandDwhButton_ScenarioFragment
	}

```


#### Fragments 179: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment projectsGridPartContent_ScenarioFragment on Scenario
	@argumentDefinitions(
		projectFilters: { type: "ProjectWithAssignmentsFiltersInput" }
		personOnAssignmentFilters: { type: "PersonOnAssignmentFiltersInput" }
	) {
		id
		...projectsGridPartContent_ScenarioRefetchableFragment
			@arguments(
				projectFilters: $projectFilters
				personOnAssignmentFilters: $personOnAssignmentFilters
			)
		...addProjectToScenarioCard_ScenarioFragment
			@arguments(
				projectFilters: $projectFilters
				personOnAssignmentFilters: $personOnAssignmentFilters
			)
		...projectCard_ScenarioFragment
	}

```


#### Fragments 180: `SCENARIO_REFETCHABLE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment projectsGridPartContent_ScenarioRefetchableFragment on Scenario
	@refetchable(queryName: "projectsGridPartContent_Refetch")
	@argumentDefinitions(
		projectFilters: { type: "ProjectWithAssignmentsFiltersInput" }
		personOnAssignmentFilters: { type: "PersonOnAssignmentFiltersInput" }
	) {
		projects(
			projectWithAssignmentsFilters: $projectFilters
			peopleOnAssignmentFilters: $personOnAssignmentFilters
		) {
			edges {
				node {
					id
					...projectsGridPartContent_ProjectInScenarioInlineFragment
				}
			}
		}
	}

```


#### Fragments 181: `PROJECT_IN_SCENARIO_INLINE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment projectsGridPartContent_ProjectInScenarioInlineFragment on ProjectInScenario @inline {
		id
		project {
			name
			startDate
			endDate
			stage {
				id
				name
			}

			division {
				id
			}
			region {
				id
			}
		}
		assignments {
			edges {
				node {
					isExecutive
					validAssignmentRoles {
						name
					}
					project {
						id
					}
					person {
						id
						assignmentRole {
							name
							id
						}
					}
				}
			}
		}
		...projectCard_ProjectFragment
	}

```


#### Fragments 182: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment rosterListActiveFilters_ScenarioFragment on Scenario {
		utilization {
			personUtilizations {
				status
			}
		}
	}

```


#### Fragments 183: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment rosterListActiveFilters_DivisionRegionFragment on Query {
		Skills {
			Skills {
				edges {
					node {
						id
						name
						skillCategory {
							id
							name
							sortOrder
						}
					}
				}
			}
			SkillCategories {
				edges {
					node {
						id
						name
						sortOrder
					}
				}
			}
		}
		Assignments {
			AssignmentRoles {
				edges {
					node {
						id
						name
					}
				}
			}
		}
		Division {
			Divisions {
				edges {
					node {
						id
						name
					}
				}
			}
		}
		Region {
			Regions {
				edges {
					node {
						id
						name
						...rosterListActiveFilters_RegionFragment
					}
				}
			}
		}
	}

```


#### Fragments 184: `REGION_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment rosterListActiveFilters_RegionFragment on Region {
		id
		name
	}

```


#### Fragments 185: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment rosterPart_ScenarioFragment on Scenario
	{
		...RosterList_ScenarioFragment
		...rosterListActiveFilters_ScenarioFragment
	}

```


#### Fragments 186: `STAFF_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment rosterPart_StaffFragment on Query
	@argumentDefinitions(
		scenarioRef: { type: "ID!" }
		first: { type: "Int", defaultValue: 250 }
		after: { type: "String" }
		filterByName: { type: "String" }
		filterByAssignmentRoles: { type: "[ID!]" }
		filterByUtilizationStatus: { type: "[UtilizationStatus!]" }
		filterBySalaryMinimum: { type: "BigDecimal" }
		filterBySalaryMaximum: { type: "BigDecimal" }
		filterByFreeDateMinimum: { type: "LocalDate" }
		filterByFreeDateMaximum: { type: "LocalDate" }
		filterByAllocatedDateMinimum: { type: "LocalDate" }
		filterByAllocatedDateMaximum: { type: "LocalDate" }
		filterByGapDaysMinimum: { type: "Int" }
		filterByGapDaysMaximum: { type: "Int" }
		filterByDistanceMinimum: { type: "Int" }
		filterByDistanceMaximum: { type: "Int" }
		filterBySkills: { type: "[SkillFilter!]" }
		sortByClosestToProject: { type: "ID" }
		filterByRegions: { type: "[ID!]" }
		filterByDivisions: { type: "[ID!]" }
		utilizationWindow: { type: "UtilizationWindowInput" }
	) {
		...RosterList_StaffFragment
			@arguments(
				first: $first
				after: $after
				filterByName: $filterByName
				scenarioRef: $scenarioRef
				filterBySkills: $filterBySkills
				filterByRegions: $filterByRegions
				filterByDivisions: $filterByDivisions
				filterByAssignmentRoles: $filterByAssignmentRoles
				filterByUtilizationStatus: $filterByUtilizationStatus
				filterBySalaryMinimum: $filterBySalaryMinimum
				filterBySalaryMaximum: $filterBySalaryMaximum
				filterByFreeDateMinimum: $filterByFreeDateMinimum
				filterByFreeDateMaximum: $filterByFreeDateMaximum
				filterByAllocatedDateMinimum: $filterByAllocatedDateMinimum
				filterByAllocatedDateMaximum: $filterByAllocatedDateMaximum
				filterByGapDaysMinimum: $filterByGapDaysMinimum
				filterByGapDaysMaximum: $filterByGapDaysMaximum
				filterByDistanceMinimum: $filterByDistanceMinimum
				filterByDistanceMaximum: $filterByDistanceMaximum
				sortByClosestToProject: $sortByClosestToProject
				utilizationWindow: $utilizationWindow
			)
	}

```


#### Fragments 187: `ROSTER_LIST_FILTERS_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment rosterPart_FilterFragment on Query {
		...rosterListActiveFilters_DivisionRegionFragment
	}

```


#### Fragments 188: `RECOVERY_CODE_CREDENTIALS_INLINE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment recoveryCodesScreen_RecoveryCodeCredentialsInlineFragment on RecoveryCodeCredentials
	@inline {
		id
		data {
			credentials
		}
	}

```


#### Fragments 189: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment skillAssessment_GetLastUpdatedDateQuery on Query
	@refetchable(queryName: "skillAssessment_Refetch")
	@argumentDefinitions(
		accountId: { type: "ID!" }
		password: { type: "String" }
		personId: { type: "ID" }
		templateId: { type: "ID" }
	) {
		Assessment {
			GetContinueFromDate(
				accountId: $accountId
				password: $password
				personId: $personId
				templateId: $templateId
			) @connection(key: "skillAssessment_GetContinueFrom")
		}
	}

```


#### Fragments 190: `ASSESSMENT_TEMPLATE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment categoryForm_AssessmentTemplateFragment on AssessmentTemplate {
		assessedSkills {
			skillCategory {
				name
				id
				sortOrder
			}
		}
	}

```


#### Fragments 191: `SKILL_CATEGORY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment categoryForm_SkillCategoryFragment on SkillCategory {
		name
		id
		sortOrder
	}

```


#### Fragments 192: `SKILL_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment categoryForm_SkillFragment on Skill @inline {
		name
		id
		description
		skillCategory {
			name
			id
		}
		dimension {
			... on NumericalDimension {
				kind
				dimensionExplanations
				dimensionCount
			}
			... on BinaryDimension {
				kind
			}
		}
	}

```


#### Fragments 193: `ASSESSMENT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment categoryForm_AssessmentFragment on Assessment {
		skillAssessments {
			value {
				kind
				... on BinaryAssessmentValue {
					hasSkill
					kind
				}
				... on NumericalAssessmentValue {
					number
					kind
				}
			}
		}
		template {
			assessedSkills {
				id
				name
				dimension {
					... on BinaryDimension {
						kind
					}
					... on NumericalDimension {
						kind
						dimensionCount
						dimensionExplanations
					}
				}
				description
				skillCategory {
					id
					name
					sortOrder
				}
				...numericalSkillTooltipIcon_SkillFragment
			}
			name
		}
	}

```


#### Fragments 194: `ASSESSMENT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment navigation_AssessmentFragment on Assessment {
		id
		supervisor {
			name
		}
		template {
			name
		}
		createdAt
		person {
			name
		}
		status {
			kind
			... on Finished {
				kind
			}
			... on PdfGenerated {
				kind
				file {
					url
					name
				}
			}
		}

		skillAssessments {
			value {
				... on NumericalAssessmentValue {
					number
					kind
				}
				... on BinaryAssessmentValue {
					hasSkill
					kind
				}
			}
			skill {
				id
				name
				dimension {
					... on NumericalDimension {
						kind
						dimensionCount
					}
					... on BinaryDimension {
						kind
					}
				}
				skillCategory {
					id
					name
				}
			}
		}
	}

```


#### Fragments 195: `ASSESSMENT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment skillAssessmentExecution_AssessmentFragment on Assessment {
		id
		status {
			kind
			... on InProgress {
				kind
			}
			... on PdfGenerated {
				kind
			}
			... on Finished {
				kind
			}
		}
		template {
			assessedSkills {
				id
				dimension {
					... on BinaryDimension {
						kind
					}
					... on NumericalDimension {
						dimensionCount
						kind
					}
				}
			}
		}
		skillAssessments {
			skill {
				id
			}
			value {
				kind
				... on BinaryAssessmentValue {
					kind
					hasSkill
				}
				... on NumericalAssessmentValue {
					kind
					number
				}
			}
		}
		status {
			kind
			... on InProgress {
				kind
			}
			... on PdfGenerated {
				kind
			}
		}
	}

```


#### Fragments 196: `ASSESSMENT_TEMPLATE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment editTemplateButton_AssessmentTemplateFragment on AssessmentTemplate {
		name
		id
		assessedSkills {
			id
			name
			skillCategory {
				id
				name
			}
		}
		associatedRoles {
			id
			name
		}
		distributionList {
			role
			emails
		}
	}

```


#### Fragments 197: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment skillAssessmentTemplatesTable_AssessmentTemplatesFragment on Query
	@refetchable(queryName: "skillAssessmentTemplatesTable_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 250 }
		after: { type: "String" }
		before: { type: "String" }
		last: { type: "Int" }
		filterByName: { type: "String" }
		alwaysIncludeIds: { type: "[ID!]" }
		excludeIds: { type: "[ID!]" }
	) {
		Admin {
			Assessment {
				AssessmentTemplates(
					alwaysIncludeIds: $alwaysIncludeIds
					filterByName: $filterByName
					excludeIds: $excludeIds
					first: $first
					after: $after
					before: $before
					last: $last
				) @connection(key: "skillAssessmentTemplatesTable_AssessmentTemplates") {
					__id
					edges {
						node {
							id
							name
							...skillAssessmentTemplatesTable_AssessmentTemplateFragment
						}
					}
				}
			}
		}
	}

```


#### Fragments 198: `ASSESSMENT_TEMPLATE_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment skillAssessmentTemplatesTable_AssessmentTemplateFragment on AssessmentTemplate
	@inline {
		id
		name
		associatedRoles {
			name
			id
		}
		assessedSkills {
			name
			id
		}
		distributionList {
			emails
			role
		}
		...editTemplateButton_AssessmentTemplateFragment
	}

```


#### Fragments 199: `ASSESSMENT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment revertToAssessmentForm_AssessmentFragment on Assessment {
		id
		status {
			... on PdfGenerated {
				finishedAt
			}
		}
		template {
			name
		}
		skillAssessments {
			skill {
				name
			}
			value {
				kind
				... on NumericalAssessmentValue {
					kind
					number
				}
				... on BinaryAssessmentValue {
					kind
					hasSkill
				}
			}
		}
		person {
			id
			name
		}
	}

```


#### Fragments 200: `ASSESSMENT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment revertToAssessmentButton_AssessmentFragment on Assessment {
		id
		person {
			id
		}
		...revertToAssessmentForm_AssessmentFragment
	}

```


#### Fragments 201: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment skillAssessmentsTable_AssessmentsFragment on Query
	@refetchable(queryName: "skillAssessmentsTable_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 250 }
		last: { type: "Int" }
		after: { type: "String" }
		before: { type: "String" }
		filterByName: { type: "String" }
	) {
		Admin {
			Assessment {
				Assessments(
					last: $last
					before: $before
					after: $after
					first: $first
					filterByName: $filterByName
				) @connection(key: "skillAssessmentsTable_Assessments") {
					__id
					pageInfo {
						endCursor
						hasPreviousPage
						hasNextPage
						startCursor
					}
					edges {
						node {
							...skillAssessmentsTable_AssessmentInlineFragment
						}
					}
				}
			}
		}
	}

```


#### Fragments 202: `ASSESSMENT_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment skillAssessmentsTable_AssessmentInlineFragment on Assessment @inline {
		id
		person {
			name
			id
		}
		supervisor {
			name
		}
		status {
			kind
			... on InProgress {
				kind
				lastUpdate
			}
			... on Finished {
				kind
				finishedAt
			}
			... on PdfGenerated {
				kind
				finishedAt
				file {
					id
					name
					url
				}
			}
		}
		skillAssessments {
			skill {
				id
				dimension {
					kind
				}
				name
				skillCategory {
					id
					name
				}
			}
			value {
				kind
				... on BinaryAssessmentValue {
					kind
					hasSkill
				}
				... on NumericalAssessmentValue {
					kind
					number
				}
			}
		}
		template {
			id
			name
			assessedSkills {
				id
			}
			associatedRoles {
				id
			}
		}
		createdAt
		...revertToAssessmentButton_AssessmentFragment
	}

```


#### Fragments 203: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment skillCategoriesTable_QueryFragment on Query
	@refetchable(queryName: "skillCategoriesTable_Refetch")
	@argumentDefinitions(
		first: { type: "Int", defaultValue: 20 }
		after: { type: "String" }
		filterByName: { type: "String" }
	) {
		Skills {
			SkillCategories(first: $first, after: $after, filterByName: $filterByName)
				@connection(key: "skillCategoriesTable_SkillCategories") {
				__id
				pageInfo {
					endCursor
					hasPreviousPage
					hasNextPage
					startCursor
				}
				edges {
					node {
						id
						name
						sortOrder
						...editSkillCategoryButton_SkillCategoryFragment

						...SkillCategorySortOrderButtons_AssignmentRoleFragment
					}
				}
			}
		}
	}

```


#### Fragments 204: `SCENARIO_QUERY`
**GraphQL Fragments:**
```graphql

	fragment ScenarioStaffViewScreen_ScenarioFragment on Scenario {
		id
		...DashboardHeader_ScenarioFragment
		...staffViewFiltersPart_ScenarioFragment
		...updateAssignmentsFromDynamicsButton_ScenarioFragment
		...syncWithRandPreconDwhButton_ScenarioFragment
		...loadPursuitProjectsFromRandDwhButton_ScenarioFragment
	}

```


#### Fragments 205: `INTERVAL_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment IntervalHeaderComponent_IntervalFragment on IntervalDescription {
		startDate
		endDate
		fallsIntoCustomUtilizationWindow
	}

```


#### Fragments 206: `INTERVAL_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment allocationBarProvider_IntervalFragment on IntervalDescription @inline {
		index
		startDate
		endDate
		fallsIntoCustomUtilizationWindow
	}

```


#### Fragments 207: `ALLOCATION_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment allocationBarProvider_AllocationFragment on LaneAllocation @inline {
		id
		fromInterval
		fromIntervalPercentage
		toInterval
		toIntervalPercentage
		startDate
		endDate
		assignment {
			id
			startDate
			endDate
			isExecutive
			validAssignmentRoles {
				id
			}
			comment
			importId
			weight
			person {
				id
			}

			project {
				id
				name
				volume
				stage {
					id
					name
					color
				}
				milestones {
					name
					date
				}
			}
			validAssignmentRoles {
				name
			}
			person {
				name
				assignmentRole {
					id
					name
				}
			}
		}
		isGap
		lengthInDays
	}

```


#### Fragments 208: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment allocationBarProvider_ScenarioFragment on Scenario {
		id
		isMasterPlan
	}

```


#### Fragments 209: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment staffViewFiltersPart_ScenarioFragment on Scenario {
		id
		utilization {
			personUtilizations {
				status
			}
		}
	}

```


#### Fragments 210: `QUERY_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment staffViewFiltersPart_QueryFragment on Query {
		Assignments {
			AssignmentRoles {
				edges {
					node {
						id
						name
					}
				}
			}
		}
		Division {
			Divisions {
				edges {
					node {
						id
						name
					}
				}
			}
		}
		Region {
			Regions {
				edges {
					node {
						id
						name
					}
				}
			}
		}
	}

```


#### Fragments 211: `SCENARIO_FRAGMENT`
**GraphQL Fragments:**
```graphql

	fragment staffViewPart_ScenarioFragment on Scenario
	@argumentDefinitions(
		scenarioId: { type: "ID!" }
		intervalType: { type: "IntervalType!" }
		showAll: { type: "Boolean" }
		personFiltersOpt: { type: "PersonOnAssignmentFiltersInput" }
		projectFiltersOpt: { type: "ProjectWithAssignmentsFiltersInput" }
		sort: { type: "StaffViewSort" }
		utilizationWindow: { type: "UtilizationWindowInput" }
	)
	@refetchable(queryName: "staffViewPart_RefetchQuery") {
		staffView(
			intervalType: $intervalType
			showAll: $showAll
			sort: $sort
			projectWithAssignmentsFilters: $projectFiltersOpt
			peopleOnAssignmentFilters: $personFiltersOpt
			utilizationWindow: $utilizationWindow
		) {
			intervalType
			intervals {
				index
				...IntervalHeaderComponent_IntervalFragment
				...allocationBarProvider_IntervalFragment
			}
			allocationGroups {
				groupType
				allocations {
					person {
						id
						assignmentRole {
							id
							name
						}
						name
						sumOfProjectVolume(scenarioRef: $scenarioId)
						...personCard_PersonFragment @arguments(scenarioId: $scenarioId)
					}
					lanes {
						allocations {
							id
							assignment {
								person {
									id
									name
								}
								id
							}
							startDate
							endDate

							...allocationBarProvider_AllocationFragment
						}
					}
					gapDays
				}
				... on ProjectGroup {
					project {
						name
					}
				}
				... on AssignmentRoleGroup {
					assignmentRole {
						name
					}
				}
			}
		}
		utilizationWithStandAndEndDate(utilizationWindow: $utilizationWindow) {
			...personCard_ScenarioUtilizationFragment
		}
		...personCard_ScenarioFragment
		...allocationBarProvider_ScenarioFragment
	}

```

