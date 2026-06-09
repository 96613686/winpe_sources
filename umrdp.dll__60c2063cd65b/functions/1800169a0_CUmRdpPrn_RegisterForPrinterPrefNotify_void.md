# CUmRdpPrn::RegisterForPrinterPrefNotify(void)

- ea: `0x1800169a0`
- end: `0x180016af1`
- name: `?RegisterForPrinterPrefNotify@CUmRdpPrn@@AEAAPEAXXZ`
- size: `337`
- prototype: `void *__fastcall(CUmRdpPrn *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015428`

## callees

- `0x1800169a0`
- `0x1800197e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800169d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016aa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016aaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016aaf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800169c5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800169c5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016a78`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016a78`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800169ef`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800169ef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016a5c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016a5c`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180016a9a`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180016a9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016ac2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016ac2`
- `ntdll!RtlOpenCurrentUser` at `0x180016a07`
- `ntdll!RtlOpenCurrentUser` at `0x180016a07`

## pseudocode

```c
HANDLE __fastcall CUmRdpPrn::RegisterForPrinterPrefNotify(CUmRdpPrn *this)
{
  HANDLE EventW; // rbx
  unsigned int v3; // r9d
  void *v4; // rcx
  void *KeyHandle; // [rsp+68h] [rbp+10h] BYREF

  KeyHandle = (void *)-1LL;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    GetLastError();
    goto LABEL_15;
  }
  v4 = (void *)*((_QWORD *)this + 23);
  if ( v4 == (void *)-1LL || !ImpersonateLoggedOnUser(v4) )
  {
    GetLastError();
LABEL_14:
    CloseHandle(EventW);
    EventW = 0;
    goto LABEL_15;
  }
  if ( RtlOpenCurrentUser(0xF003Fu, &KeyHandle) < 0 )
  {
    CloseHandle(EventW);
LABEL_9:
    EventW = 0;
    goto LABEL_10;
  }
  if ( RegCreateKeyExW((HKEY)KeyHandle, L"Printers\\DevModePerUser", 0, 0, 0, 0xF003Fu, 0, (PHKEY)this + 16, 0) )
  {
    CloseHandle(EventW);
    *((_QWORD *)this + 16) = -1;
    goto LABEL_9;
  }
LABEL_10:
  RevertToSelf();
  if ( EventW && RegNotifyChangeKeyValue(*((HKEY *)this + 16), 1, 5u, EventW, 1) )
    goto LABEL_14;
LABEL_15:
  if ( KeyHandle != (void *)-1LL )
    RegCloseKey((HKEY)KeyHandle);
  if ( !EventW )
    TsLogError(&EVENT_NOTIFY_FAILEDTOREGFOR_SETTING_NOTIFY, 0, 0, v3);
  return EventW;
}

```

## disassembly

```asm
0x1800169a0  mov     [rsp+arg_0], rbx
0x1800169a5  mov     [rsp+arg_10], rsi
0x1800169aa  push    rdi
0x1800169ab  sub     rsp, 50h
0x1800169af  mov     rdi, rcx
0x1800169b2  mov     [rsp+58h+KeyHandle], 0FFFFFFFFFFFFFFFFh
0x1800169bb  xor     ecx, ecx; lpEventAttributes
0x1800169bd  xor     r9d, r9d; lpName
0x1800169c0  xor     r8d, r8d; bInitialState
0x1800169c3  xor     edx, edx; bManualReset
0x1800169c5  call    cs:__imp_CreateEventW
0x1800169cb  mov     rbx, rax
0x1800169ce  test    rax, rax
0x1800169d1  jnz     short loc_1800169DE
0x1800169d3  call    cs:__imp_GetLastError
0x1800169d9  jmp     loc_180016AB7
0x1800169de  mov     rcx, [rdi+0B8h]; hToken
0x1800169e5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800169e9  jz      loc_180016AA6
0x1800169ef  call    cs:__imp_ImpersonateLoggedOnUser
0x1800169f5  test    eax, eax
0x1800169f7  jz      loc_180016AA6
0x1800169fd  lea     rdx, [rsp+58h+KeyHandle]; KeyHandle
0x180016a02  mov     ecx, 0F003Fh; DesiredAccess
0x180016a07  call    cs:__imp_RtlOpenCurrentUser
0x180016a0d  test    eax, eax
0x180016a0f  jns     short loc_180016A1C
0x180016a11  mov     rcx, rbx; hObject
0x180016a14  call    cs:__imp_CloseHandle
0x180016a1a  jmp     short loc_180016A76
0x180016a1c  mov     rcx, [rsp+58h+KeyHandle]; hKey
0x180016a21  lea     rsi, [rdi+80h]
0x180016a28  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180016a31  lea     rdx, aPrintersDevmod; "Printers\\DevModePerUser"
0x180016a38  mov     [rsp+58h+phkResult], rsi; phkResult
0x180016a3d  xor     r9d, r9d; lpClass
0x180016a40  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180016a49  xor     r8d, r8d; Reserved
0x180016a4c  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180016a54  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180016a5c  call    cs:__imp_RegCreateKeyExW
0x180016a62  test    eax, eax
0x180016a64  jz      short loc_180016A78
0x180016a66  mov     rcx, rbx; hObject
0x180016a69  call    cs:__imp_CloseHandle
0x180016a6f  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180016a76  xor     ebx, ebx
0x180016a78  call    cs:__imp_RevertToSelf
0x180016a7e  test    rbx, rbx
0x180016a81  jz      short loc_180016AB7
0x180016a83  mov     rcx, [rdi+80h]; hKey
0x180016a8a  mov     edx, 1; bWatchSubtree
0x180016a8f  mov     r9, rbx; hEvent
0x180016a92  mov     [rsp+58h+dwOptions], edx; fAsynchronous
0x180016a96  lea     r8d, [rdx+4]; dwNotifyFilter
0x180016a9a  call    cs:__imp_RegNotifyChangeKeyValue
0x180016aa0  test    eax, eax
0x180016aa2  jz      short loc_180016AB7
0x180016aa4  jmp     short loc_180016AAC
0x180016aa6  call    cs:__imp_GetLastError
0x180016aac  mov     rcx, rbx; hObject
0x180016aaf  call    cs:__imp_CloseHandle
0x180016ab5  xor     ebx, ebx
0x180016ab7  mov     rcx, [rsp+58h+KeyHandle]; hKey
0x180016abc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180016ac0  jz      short loc_180016AC8
0x180016ac2  call    cs:__imp_RegCloseKey
0x180016ac8  test    rbx, rbx
0x180016acb  jnz     short loc_180016ADE
0x180016acd  xor     r8d, r8d; unsigned __int16 **
0x180016ad0  lea     rcx, EVENT_NOTIFY_FAILEDTOREGFOR_SETTING_NOTIFY; struct _EVENT_DESCRIPTOR *
0x180016ad7  xor     edx, edx; int
0x180016ad9  call    ?TsLogError@@YAXAEBU_EVENT_DESCRIPTOR@@HQEAPEAGK@Z; TsLogError(_EVENT_DESCRIPTOR const &,int,ushort * * const,ulong)
0x180016ade  mov     rsi, [rsp+58h+arg_10]
0x180016ae3  mov     rax, rbx
0x180016ae6  mov     rbx, [rsp+58h+arg_0]
0x180016aeb  add     rsp, 50h
0x180016aef  pop     rdi
0x180016af0  retn
```
