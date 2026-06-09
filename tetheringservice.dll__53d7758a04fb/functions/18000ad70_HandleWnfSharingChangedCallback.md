# HandleWnfSharingChangedCallback

- ea: `0x18000ad70`
- end: `0x18000ae23`
- name: `HandleWnfSharingChangedCallback`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000ad70`
- `0x18000bf4c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000adbf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000adbf`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000adcc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000adcc`

## pseudocode

```c
__int64 HandleWnfSharingChangedCallback()
{
  TetheringServiceTelemetry *v0; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( g_ProcessOutOfBandEntitelmentCheckBackgroundWork )
  {
    WaitForThreadpoolWorkCallbacks(g_ProcessOutOfBandEntitelmentCheckBackgroundWork, 1);
    SubmitThreadpoolWork(g_ProcessOutOfBandEntitelmentCheckBackgroundWork);
LABEL_9:
    v0 = WPP_GLOBAL_Control;
    goto LABEL_10;
  }
  if ( v0 == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    return 0;
  if ( (*((_BYTE *)v0 + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)v0 + 2), 48, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
    goto LABEL_9;
  }
LABEL_10:
  if ( v0 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v0 + 2), 49, &WPP_44e4735379a936cf4f13ce357ad19005_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000ad70  push    rbx
0x18000ad72  sub     rsp, 20h
0x18000ad76  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad7d  lea     rbx, WPP_GLOBAL_Control
0x18000ad84  cmp     rcx, rbx
0x18000ad87  jz      short loc_18000ADAB
0x18000ad89  test    byte ptr [rcx+1Ch], 8
0x18000ad8d  jz      short loc_18000ADAB
0x18000ad8f  mov     rcx, [rcx+10h]
0x18000ad93  lea     r8, WPP_44e4735379a936cf4f13ce357ad19005_Traceguids
0x18000ad9a  mov     edx, 2Fh ; '/'
0x18000ad9f  call    WPP_SF_
0x18000ada4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adab  mov     rax, cs:?g_ProcessOutOfBandEntitelmentCheckBackgroundWork@@3PEAU_TP_WORK@@EA; _TP_WORK * g_ProcessOutOfBandEntitelmentCheckBackgroundWork
0x18000adb2  test    rax, rax
0x18000adb5  jz      short loc_18000ADD4
0x18000adb7  mov     edx, 1; fCancelPendingCallbacks
0x18000adbc  mov     rcx, rax; pwk
0x18000adbf  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000adc5  mov     rcx, cs:?g_ProcessOutOfBandEntitelmentCheckBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18000adcc  call    cs:__imp_SubmitThreadpoolWork
0x18000add2  jmp     short loc_18000ADF4
0x18000add4  cmp     rcx, rbx
0x18000add7  jz      short loc_18000AE1B
0x18000add9  test    byte ptr [rcx+1Ch], 1
0x18000addd  jz      short loc_18000ADFB
0x18000addf  mov     rcx, [rcx+10h]
0x18000ade3  lea     r8, WPP_44e4735379a936cf4f13ce357ad19005_Traceguids
0x18000adea  mov     edx, 30h ; '0'
0x18000adef  call    WPP_SF_
0x18000adf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adfb  cmp     rcx, rbx
0x18000adfe  jz      short loc_18000AE1B
0x18000ae00  test    byte ptr [rcx+1Ch], 8
0x18000ae04  jz      short loc_18000AE1B
0x18000ae06  mov     rcx, [rcx+10h]
0x18000ae0a  lea     r8, WPP_44e4735379a936cf4f13ce357ad19005_Traceguids
0x18000ae11  mov     edx, 31h ; '1'
0x18000ae16  call    WPP_SF_
0x18000ae1b  xor     eax, eax
0x18000ae1d  add     rsp, 20h
0x18000ae21  pop     rbx
0x18000ae22  retn
```
