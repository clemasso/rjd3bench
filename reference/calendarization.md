# Calendarization

Based on "Calendarization with splines and state space models" B.
Quenneville, F.Picard and S.Fortier Appl. Statistics (2013) 62, part 3,
pp 371-399. State space implementation.

## Usage

``` r
calendarization(
  calendarobs,
  freq,
  start = NULL,
  end = NULL,
  dailyweights = NULL,
  stde = FALSE
)
```

## Arguments

- calendarobs:

  Observations (list of start, end, value). See the example.

- freq:

  Annual frequency. If 0, only the daily series are computed

- start:

  Starting day of the calendarization. Could be before the calendar obs
  (extrapolation)

- end:

  Final day of the calendarization. Could be after the calendar obs
  (extrapolation)

- dailyweights:

  Daily weights. Should have the same length as the requested series

- stde:

## Examples

``` r
obs <- list(
    list(start = "1980-01-01", end = "1989-12-31", value = 100),
    list(start = "1990-01-01", end = "1999-12-31", value = -10),
    list(start = "2000-01-01", end = "2002-12-31", value = 50))
cal <- calendarization(obs, 4, end = "2003-12-31", stde = TRUE)
Q <- cal$rslt
eQ <- cal$erslt
```
