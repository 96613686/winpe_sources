# UpdateTraceFlags(wchar_t const *,uchar *,CGlobalTraceFlags::FlagUsage)

- ea: `0x100423bb0`
- end: `0x100423e3e`
- name: `?UpdateTraceFlags@@YAXPEB_WPEAEW4FlagUsage@CGlobalTraceFlags@@@Z`
- size: `654`
- prototype: `void __high(const wchar_t *, unsigned __int8 *, enum CGlobalTraceFlags::FlagUsage)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x100423e50`
- `0x100425030`

## callees

- `0x100402880`
- `0x100422b70`
- `0x1004233a0`
- `0x100423bb0`
- `0x1004403d0`
- `0x1004534f8`

## import_xrefs

- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x100423db7`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x100423db7`
- `sqldk!?Execute@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@W4DkParameterFlags@@@Z` at `0x100423cbc`
- `sqldk!?Execute@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@W4DkParameterFlags@@@Z` at `0x100423cbc`
- `sqldk!?ProcessBuffer@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@PEB_W_N@Z` at `0x100423cac`
- `sqldk!?ProcessBuffer@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@PEB_W_N@Z` at `0x100423cac`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x100423d57`
- `sqldk!?UtilDbccTraceOff@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x100423d57`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x100423d8d`
- `sqldk!?UtilDbccTraceOn@@YA_NKFW4FlagScope@CGlobalTraceFlags@@W4FlagUsage@2@@Z` at `0x100423d8d`

## pseudocode

```c

```
