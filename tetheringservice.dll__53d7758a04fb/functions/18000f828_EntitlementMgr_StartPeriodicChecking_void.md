# EntitlementMgr::StartPeriodicChecking(void)

- ea: `0x18000f828`
- end: `0x18000f918`
- name: `?StartPeriodicChecking@EntitlementMgr@@QEAAJXZ`
- size: `240`
- prototype: `__int64 __fastcall(void **Parameter)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18001e4a4`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x18000f828`
- `0x18002bc08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f905`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f905`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f8be`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000f8b4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000f8b4`

## pseudocode

```c
__int64 __fastcall EntitlementMgr::StartPeriodicChecking(void **Parameter)
{
  unsigned int v3; // ebx
  _DWORD *SettingValueWithIccidInternal; // rax
  void *v5; // rsi
  DWORD DueTime; // ebp
  signed int LastError; // eax

  if ( !*((_BYTE *)Parameter + 94) )
    return 2147942421LL;
  v3 = 0;
  SettingValueWithIccidInternal = (_DWORD *)TetheringSettingsGetSettingValueWithIccidInternal(2, (char *)Parameter + 52);
  v5 = SettingValueWithIccidInternal;
  if ( SettingValueWithIccidInternal )
  {
    DueTime = 1000 * *SettingValueWithIccidInternal;
  }
  else
  {
    DueTime = 86400000;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_c5412e6d3d8031ad90ef7472f24b0e8b_Traceguids);
    }
  }
  if ( !CreateTimerQueueTimer(
          Parameter + 1,
          *Parameter,
          EntitlementMgr::EntitlementCallback,
          Parameter,
          DueTime,
          DueTime,
          0) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_c5412e6d3d8031ad90ef7472f24b0e8b_Traceguids, v3);
    }
  }
  if ( v5 )
    free(v5);
  return v3;
}

```

## disassembly

```asm
0x18000f828  push    rbx
0x18000f82a  push    rbp
0x18000f82b  push    rsi
0x18000f82c  push    rdi
0x18000f82d  push    r14
0x18000f82f  sub     rsp, 40h
0x18000f833  cmp     byte ptr [rcx+5Eh], 0
0x18000f837  mov     rdi, rcx
0x18000f83a  jnz     short loc_18000F846
0x18000f83c  mov     eax, 80070015h
0x18000f841  jmp     loc_18000F90D
0x18000f846  lea     rdx, [rcx+34h]
0x18000f84a  xor     ebx, ebx
0x18000f84c  lea     ecx, [rbx+2]
0x18000f84f  call    ?TetheringSettingsGetSettingValueWithIccidInternal@@YAPEAXW4TetheringSettingPerIccid@@PEBG@Z; TetheringSettingsGetSettingValueWithIccidInternal(TetheringSettingPerIccid,ushort const *)
0x18000f854  lea     r14, WPP_GLOBAL_Control
0x18000f85b  mov     rsi, rax
0x18000f85e  test    rax, rax
0x18000f861  jz      short loc_18000F86B
0x18000f863  imul    ebp, [rax], 3E8h
0x18000f869  jmp     short loc_18000F897
0x18000f86b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f872  mov     ebp, 5265C00h
0x18000f877  cmp     rcx, r14
0x18000f87a  jz      short loc_18000F897
0x18000f87c  test    byte ptr [rcx+1Ch], 2
0x18000f880  jz      short loc_18000F897
0x18000f882  mov     rcx, [rcx+10h]
0x18000f886  lea     r8, WPP_c5412e6d3d8031ad90ef7472f24b0e8b_Traceguids
0x18000f88d  mov     edx, 0Dh
0x18000f892  call    WPP_SF_
0x18000f897  mov     rdx, [rdi]; TimerQueue
0x18000f89a  lea     rcx, [rdi+8]; phNewTimer
0x18000f89e  mov     [rsp+68h+Flags], ebx; Flags
0x18000f8a2  lea     r8, ?EntitlementCallback@EntitlementMgr@@CAXPEAXE@Z; Callback
0x18000f8a9  mov     [rsp+68h+Period], ebp; Period
0x18000f8ad  mov     r9, rdi; Parameter
0x18000f8b0  mov     [rsp+68h+DueTime], ebp; DueTime
0x18000f8b4  call    cs:__imp_CreateTimerQueueTimer
0x18000f8ba  test    eax, eax
0x18000f8bc  jnz     short loc_18000F8FD
0x18000f8be  call    cs:__imp_GetLastError
0x18000f8c4  mov     ebx, eax
0x18000f8c6  test    eax, eax
0x18000f8c8  jle     short loc_18000F8D3
0x18000f8ca  movzx   ebx, ax
0x18000f8cd  or      ebx, 80070000h
0x18000f8d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8da  cmp     rcx, r14
0x18000f8dd  jz      short loc_18000F8FD
0x18000f8df  test    byte ptr [rcx+1Ch], 1
0x18000f8e3  jz      short loc_18000F8FD
0x18000f8e5  mov     rcx, [rcx+10h]
0x18000f8e9  lea     r8, WPP_c5412e6d3d8031ad90ef7472f24b0e8b_Traceguids
0x18000f8f0  mov     edx, 0Eh
0x18000f8f5  mov     r9d, ebx
0x18000f8f8  call    WPP_SF_d
0x18000f8fd  test    rsi, rsi
0x18000f900  jz      short loc_18000F90B
0x18000f902  mov     rcx, rsi; Block
0x18000f905  call    cs:__imp_free
0x18000f90b  mov     eax, ebx
0x18000f90d  add     rsp, 40h
0x18000f911  pop     r14
0x18000f913  pop     rdi
0x18000f914  pop     rsi
0x18000f915  pop     rbp
0x18000f916  pop     rbx
0x18000f917  retn
```
