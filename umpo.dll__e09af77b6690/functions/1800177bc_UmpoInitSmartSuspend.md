# UmpoInitSmartSuspend

- ea: `0x1800177bc`
- end: `0x180017860`
- name: `UmpoInitSmartSuspend`
- size: `164`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000ed10`

## callees

- `0x1800177bc`

## import_xrefs

- `ntdll!NtPowerInformation` at `0x1800177f2`
- `ntdll!NtPowerInformation` at `0x1800177f2`
- `ext-ms-win-sysmain-pfapi-l1-1-1!PfIuPredictionsDataOpen` at `0x18001780a`
- `ext-ms-win-sysmain-pfapi-l1-1-1!PfIuPredictionsDataOpen` at `0x18001780a`
- `ext-ms-win-sysmain-pfapi-l1-1-1!PfIuPredictionsDataClose` at `0x18001784b`
- `ext-ms-win-sysmain-pfapi-l1-1-1!PfIuPredictionsDataClose` at `0x18001784b`

## pseudocode

```c
NTSTATUS UmpoInitSmartSuspend()
{
  NTSTATUS result; // eax
  char v1; // [rsp+40h] [rbp+8h] BYREF
  __int64 v2; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  UmpoSmartSuspendDisableReason = 0;
  v2 = 4;
  result = NtPowerInformation(SystemPowerStateLogging|0x40, &v2, 8u, &v1, 1u);
  if ( result >= 0 && v1 )
  {
    result = PfIuPredictionsDataOpen(&UmpoSmartSuspendPFIUData);
    if ( result )
    {
      UmpoSmartSuspendDisableReason = 3;
    }
    else
    {
      UmpoSmartSuspendState = 1;
      if ( !UmpoSmartSuspendDisableReason )
        return result;
    }
  }
  else
  {
    UmpoSmartSuspendDisableReason = 2;
  }
  if ( UmpoSmartSuspendPFIUData )
    result = PfIuPredictionsDataClose();
  UmpoSmartSuspendState = 2;
  return result;
}

```

## disassembly

```asm
0x1800177bc  mov     rax, rsp
0x1800177bf  sub     rsp, 38h
0x1800177c3  mov     r8d, 8; InputBufferLength
0x1800177c9  mov     byte ptr [rax+8], 0
0x1800177cd  lea     r9, [rax+8]; OutputBuffer
0x1800177d1  mov     cs:UmpoSmartSuspendDisableReason, 0
0x1800177db  lea     rdx, [rax+10h]; InputBuffer
0x1800177df  mov     qword ptr [rax+10h], 4
0x1800177e7  mov     dword ptr [rax-18h], 1
0x1800177ee  lea     ecx, [r8+4Fh]; PowerInformationLevel
0x1800177f2  call    cs:__imp_NtPowerInformation
0x1800177f8  test    eax, eax
0x1800177fa  js      short loc_180017835
0x1800177fc  cmp     [rsp+38h+arg_0], 0
0x180017801  jz      short loc_180017835
0x180017803  lea     rcx, UmpoSmartSuspendPFIUData
0x18001780a  call    cs:__imp_PfIuPredictionsDataOpen
0x180017810  test    eax, eax
0x180017812  jz      short loc_180017820
0x180017814  mov     cs:UmpoSmartSuspendDisableReason, 3
0x18001781e  jmp     short loc_18001783F
0x180017820  mov     cs:UmpoSmartSuspendState, 1
0x18001782a  cmp     cs:UmpoSmartSuspendDisableReason, 0
0x180017831  jz      short loc_18001785B
0x180017833  jmp     short loc_18001783F
0x180017835  mov     cs:UmpoSmartSuspendDisableReason, 2
0x18001783f  mov     rcx, cs:UmpoSmartSuspendPFIUData
0x180017846  test    rcx, rcx
0x180017849  jz      short loc_180017851
0x18001784b  call    cs:__imp_PfIuPredictionsDataClose
0x180017851  mov     cs:UmpoSmartSuspendState, 2
0x18001785b  add     rsp, 38h
0x18001785f  retn
```
