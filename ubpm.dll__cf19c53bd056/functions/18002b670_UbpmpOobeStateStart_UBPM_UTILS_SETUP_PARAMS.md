# UbpmpOobeStateStart(_UBPM_UTILS_SETUP_PARAMS *)

- ea: `0x18002b670`
- end: `0x18002b758`
- name: `?UbpmpOobeStateStart@@YAKPEAU_UBPM_UTILS_SETUP_PARAMS@@@Z`
- size: `232`
- prototype: `unsigned int __fastcall(struct _UBPM_UTILS_SETUP_PARAMS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180034034`

## callees

- `0x18000a6e0`
- `0x18002978c`
- `0x18002b670`
- `0x180033f58`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b73e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b73e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b6d1`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x18002b6a0`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x18002b6a0`

## pseudocode

```c
__int64 __fastcall UbpmpOobeStateStart(struct _UBPM_UTILS_SETUP_PARAMS *a1)
{
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  _BYTE v5[4]; // [rsp+30h] [rbp-28h] BYREF
  DWORD LastError; // [rsp+34h] [rbp-24h] BYREF
  __int128 v7; // [rsp+38h] [rbp-20h] BYREF

  v5[0] = 0;
  v7 = 0;
  if ( !(unsigned int)RegisterWaitUntilOOBECompleted(UbpmpUserOOBECompletedCallback, 0, &qword_18004CA68) )
  {
    if ( GetLastError() != 5023 && GetLastError() != 50 && (unsigned int)dword_18004C0F0 > 2 )
    {
      LastError = GetLastError();
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v1,
        (unsigned __int8 *)&dword_180042F4C,
        v2,
        v3,
        (__int64)&LastError);
    }
    if ( (int)OOBE::CompleteTime::TryGetTime(v5, &v7) < 0 )
      v7 = 0;
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_SystemSetup);
    unk_18004CA50 |= 3u;
    dword_18004CA48 = 0;
    xmmword_18004CA52 = v7;
    RtlReleaseSRWLockExclusive(&g_SystemSetup);
  }
  return 0;
}

```

## disassembly

```asm
0x18002b670  sub     rsp, 58h
0x18002b674  mov     rax, cs:__security_cookie
0x18002b67b  xor     rax, rsp
0x18002b67e  mov     [rsp+58h+var_10], rax
0x18002b683  xorps   xmm0, xmm0
0x18002b686  mov     [rsp+58h+var_28], 0
0x18002b68b  lea     r8, qword_18004CA68
0x18002b692  xor     edx, edx
0x18002b694  lea     rcx, ?UbpmpUserOOBECompletedCallback@@YAXPEAX@Z; UbpmpUserOOBECompletedCallback(void *)
0x18002b69b  movups  [rsp+58h+var_20], xmm0
0x18002b6a0  call    cs:__imp_RegisterWaitUntilOOBECompleted
0x18002b6a6  test    eax, eax
0x18002b6a8  jnz     loc_18002B744
0x18002b6ae  call    cs:__imp_GetLastError
0x18002b6b4  cmp     eax, 139Fh
0x18002b6b9  jz      short loc_18002B6F1
0x18002b6bb  call    cs:__imp_GetLastError
0x18002b6c1  cmp     eax, 32h ; '2'
0x18002b6c4  jz      short loc_18002B6F1
0x18002b6c6  mov     eax, cs:dword_18004C0F0
0x18002b6cc  cmp     eax, 2
0x18002b6cf  jbe     short loc_18002B6F1
0x18002b6d1  call    cs:__imp_GetLastError
0x18002b6d7  mov     [rsp+58h+var_24], eax
0x18002b6db  lea     rdx, dword_180042F4C
0x18002b6e2  lea     rax, [rsp+58h+var_24]
0x18002b6e7  mov     [rsp+58h+var_38], rax
0x18002b6ec  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002b6f1  lea     rdx, [rsp+58h+var_20]
0x18002b6f6  lea     rcx, [rsp+58h+var_28]
0x18002b6fb  call    OOBE__CompleteTime__TryGetTime
0x18002b700  test    eax, eax
0x18002b702  jns     short loc_18002B70C
0x18002b704  xorps   xmm0, xmm0
0x18002b707  movups  [rsp+58h+var_20], xmm0
0x18002b70c  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; struct _UBPM_SRWLOCK *
0x18002b713  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002b718  movups  xmm0, [rsp+58h+var_20]
0x18002b71d  or      word ptr cs:unk_18004CA50, 3
0x18002b725  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x18002b72c  mov     cs:dword_18004CA48, 0
0x18002b736  movdqu  cs:xmmword_18004CA52, xmm0
0x18002b73e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b744  xor     eax, eax
0x18002b746  mov     rcx, [rsp+58h+var_10]
0x18002b74b  xor     rcx, rsp; StackCookie
0x18002b74e  call    __security_check_cookie
0x18002b753  add     rsp, 58h
0x18002b757  retn
```
