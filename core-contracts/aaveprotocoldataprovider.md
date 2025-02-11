# AaveProtocolDataProvider

Peripheral contract to collect and pre-process information from the Pool.

Code available on [github](https://github.com/aave/aave-v3-core/blob/master/contracts/misc/AaveProtocolDataProvider.sol#L164).

## Methods

### getAllReservesTokens
`function getAllReservesTokens() external view returns (TokenData[] memory)`

Returns list of the existing reserves in the pool.

Return Value
| Type      | Description                                 |
| --------- | ------------------------------------------- |
| `string`  | The symbol of the underlying reserve asset  |
| `address` | The address of the underlying reserve asset |

### getAllATokens
`function getAllATokens() external view returns (TokenData[] memory)`

Returns list of the existing ATokens in the pool.

Return Value
| Type      | Description                              |
| --------- | ---------------------------------------- |
| `string`  | The symbol of aToken of the reserve  |
| `address` | The address of aToken of the reserve |

### getReserveConfigurationData
`function getReserveConfigurationData(address asset) external view returns (....)`

Returns the configuration data of the reserve as described below:

Call Params
| Name  | Type      | Description                                        |
| ----- | --------- | -------------------------------------------------- |
| asset | `address` | The address of the underlying asset of the reserve |

Return Value
| Type      | Description                                 |
| --------- | ------------------------------------------- |
| `uint256` | The number of decimals of the reserve       |
| `uint256` | The ltv of the reserve                      |
| `uint256` | The liquidationThreshold of the reserve     |
| `uint256` | The liquidationBonus of the reserve         |
| `uint256` | The reserveFactor of the reserve |
| `bool`    | True if the usage as collateral is enabled, false otherwise |
| `bool`    | True if borrowing is enabled, false otherwise |
| `bool`    | True if stable rate borrowing is enabled, false otherwise |
| `bool`    | True if reserve is active, false otherwise |
| `bool`    | True if reserve is frozen, false otherwise |

### getReserveEModeCategory
`function getReserveEModeCategory(address asset) external view returns (uint256)`

Returns reserve's efficiency mode category.

Call Params
| Name  | Type      | Description                                        |
| ----- | --------- | -------------------------------------------------- |
| asset | `address` | The address of the underlying asset of the reserve |

Return Value
| Type      | Description                                 |
| --------- | ------------------------------------------- |
| `uint256` | The number of decimals of the reserve       |

### getReserveCaps
`function getReserveCaps(address asset) external view returns (uint256 borrowCap, uint256 supplyCap)`

Returns the caps parameters of the reserve

Call Params
| Name  | Type      | Description                                        |
| ----- | --------- | -------------------------------------------------- |
| asset | `address` | The address of the underlying asset of the reserve |

Return Value
| Type      | Description                   |
| --------- | ----------------------------- |
| `uint256` | The borrow cap of the reserve |
| `uint256` | The supply cap of the reserve |

### getPaused
`function getPaused(address asset) external view returns (bool isPaused)`

Returns true if the pool is paused.

Call Params
| Name  | Type      | Description                                        |
| ----- | --------- | -------------------------------------------------- |
| asset | `address` | The address of the underlying asset of the reserve |

Return Value
| Type      | Description                            |
| --------- | -------------------------------------- |
| `bool` | True if the pool is paused                |

### getSiloedBorrowing

`function getSiloedBorrowing(address asset) external view returns (bool)`

Returns true if the asset is _**siloed for borrowing**_.

Call Params
| Name  | Type      | Description                                        |
| ----- | --------- | -------------------------------------------------- |
| asset | `address` | The address of the underlying asset of the reserve |

Return Value
| Type      | Description                            |
| --------- | -------------------------------------- |
| `bool` | True if the pool is paused                |

### getLiquidationProtocolFee
`function getLiquidationProtocolFee(address asset) external view returns (uint256)`

Returns the protocol fee on the liquidation bonus.

Call Params
| Name  | Type      | Description                                        |
| ----- | --------- | -------------------------------------------------- |
| asset | `address` | The address of the underlying asset of the reserve |

Return Value
| Type      | Description                            |
| --------- | -------------------------------------- |
| `uint256` | The protocol fee on liquidation        |

### getUnbackedMintCap
`function getUnbackedMintCap(address asset) external view returns (uint256)`

Returns the unbacked mint cap of the reserve

Call Params
| Name  | Type      | Description                                        |
| ----- | --------- | -------------------------------------------------- |
| asset | `address` | The address of the underlying asset of the reserve |

Return Value
| Type      | Description                            |
| --------- | -------------------------------------- |
| `uint256` | The unbacked mint cap of the reserve   |

### getDebtCeiling
`function getDebtCeiling(address asset) external view returns (uint256)`

Returns the debt ceiling of the reserve

Call Params
| Name  | Type      | Description                                        |
| ----- | --------- | -------------------------------------------------- |
| asset | `address` | The address of the underlying asset of the reserve |

Return Value
| Type       | Description                    |
| --------- | ------------------------------- |
| `uint256` | The debt ceiling of the reserve |

### getDebtCeilingDecimals
`function getDebtCeilingDecimals() external pure returns (uint256)`

Returns the debt ceiling decimals

Return Value
| Type      | Description               |
| --------- | ------------------------- |
| `uint256` | The debt ceiling decimals |

### getReserveData
`function getReserveData(address asset) external view override returns(....)`

Returns the following reserve data 👇🏻

Call Params
| Name  | Type      | Description                                        |
| ----- | --------- | -------------------------------------------------- |
| asset | `address` | The address of the underlying asset of the reserve |

Return Value
| Type      | Description                                     |
| --------- | ----------------------------------------------- |
| `uint256` | The amount of unbacked aTokens of the reserve   |
| `uint256` | The scaled amount of tokens accrued to treasury that is to be minted |
| `uint256` | The total supply of the aToken |
| `uint256` | The total stable debt of the reserve |
| `uint256` | The total variable debt of the reserve |
| `uint256` | The liquidity rate of the reserve |
| `uint256` | The variable borrow rate of the reserve |
| `uint256` | The stable borrow rate of the reserve |
| `uint256` | The average stable borrow rate of the reserve |
| `uint256` | The liquidity index of the reserve |
| `uint256` | The variable borrow index of the reserve |
| `uint40`  | The timestamp of the last update of the reserve | 

### getATokenTotalSupply
`function getATokenTotalSupply(address asset) external view override returns (uint256)`

Returns the total supply of aTokens for a given asset

Call Params
| Name  | Type      | Description                       |
| ----- | --------- | --------------------------------- |
| asset | `address` | The address of the underlying asset of the reserve |

Return Value
| Type      | Description                                     |
| --------- | ----------------------------------------------- |
| `uint256` | The total supply of the aToken |

### getTotalDebt
`function getTotalDebt(address asset) external view override returns (uint256)`

Returns the total debt for a given asset

Call Params
| Name  | Type      | Description                       |
| ----- | --------- | --------------------------------- |
| asset | `address` | The address of the underlying asset of the reserve |


Return Value
| Type      | Description                                     |
| --------- | ----------------------------------------------- |
| `uint256` | The total debt (stable + variable) for an asset |

### getUserReserveData
`function getUserReserveData(address asset, address user) external view returns (...)`

Returns the following user reserve data

Call Params
| Name  | Type      | Description                       |
| ----- | --------- | --------------------------------- |
| asset | `address` | The address of the underlying asset of the reserve |
| user  | `address` | The address of the user |

Return Value
| Type      | Description                                     |
| --------- | ----------------------------------------------- |
| `uint256` | The current AToken balance of the user |
| `uint256` | The current stable debt of the user |
| `uint256` | The current variable debt of the user |
| `uint256` | The principal stable debt of the user |
| `uint256` | The scaled variable debt of the user |
| `uint256` | The stable borrow rate of the user |
| `uint256` | The liquidity rate of the reserve |
| `uint40`  | The timestamp of the last update of the user stable rate |
| `bool`    | True if the user is using the asset as collateral, else false |

### getReserveTokensAddresses
`function getReserveTokensAddresses(address asset) external view returns (address aTokenAddress, address stableDebtTokenAddress, address variableDebtTokenAddress)`

Returns the addresses of aToken, stableDebtToken and variableDebtToken of the reserve

Call Params
| Name  | Type      | Description                       |
| ----- | --------- | --------------------------------- |
| asset | `address` | The address of the underlying asset of the reserve |


Return Value
| Type      | Description                                     |
| --------- | ----------------------------------------------- |
| `address` |  The AToken address of the reserve |
| `address` | The StableDebtToken address of the reserve |
| `address` | The VariableDebtToken address of the reserve |

### getInterestRateStrategyAddress
`function getInterestRateStrategyAddress(address asset) external view returns (address irStrategyAddress)`

Returns the address of the Interest Rate strategy

Call Params
| Name  | Type      | Description                       |
| ----- | --------- | --------------------------------- |
| asset | `address`| The address of the underlying asset of the reserve |

Return Value
| Type      | Description                              |
| --------- | ---------------------------------------- |
| `address` | The address of the Interest Rate strategy |