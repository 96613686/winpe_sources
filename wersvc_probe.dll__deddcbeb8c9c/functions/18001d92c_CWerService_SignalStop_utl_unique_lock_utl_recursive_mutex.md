# CWerService::_SignalStop(utl::unique_lock<utl::recursive_mutex> &)

- ea: `0x18001d92c`
- end: `0x18001d9e2`
- name: `?_SignalStop@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z`
- size: `182`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800154e4`
- `0x180015d18`
- `0x1800181f8`
- `0x180018700`

## callees

- `0x180006a80`
- `0x18001d7c0`
- `0x18001d92c`
- `0x18001e054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9c4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d9ba`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d9ba`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d9a7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d9a7`

## pseudocode

```c
signed int __fastcall CWerService::_SignalStop(HANDLE *this, __int64 a2)
{
  unsigned int v4; // r8d
  HANDLE v5; // rcx
  signed int result; // eax

  CWerService::_SetServiceStatus((CWerService *)this, 3u);
  v5 = this[41];
  if ( (unsigned __int64)v5 + 1 <= 1 )
  {
    CWerService::_Stop((struct _TP_CLEANUP_GROUP **)this, a2, v4);
LABEL_3:
    if ( this[43] != (HANDLE)-1LL && (char *)this[43] + 1 != HANDLE_FLAG_INHERIT )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
      ResetEvent(this[43]);
    }
    return 0;
  }
  if ( SetEvent(v5) )
    goto LABEL_3;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x18001d92c  mov     [rsp+arg_0], rbx
0x18001d931  push    rdi
0x18001d932  sub     rsp, 20h
0x18001d936  mov     rdi, rdx
0x18001d939  mov     rbx, rcx
0x18001d93c  mov     edx, 3; unsigned int
0x18001d941  call    ?_SetServiceStatus@CWerService@@AEAAJKK@Z; CWerService::_SetServiceStatus(ulong,ulong)
0x18001d946  mov     rcx, [rbx+148h]; hEvent
0x18001d94d  lea     rax, [rcx+1]
0x18001d951  cmp     rax, 1
0x18001d955  ja      short loc_18001D9BA
0x18001d957  mov     rdx, rdi
0x18001d95a  mov     rcx, rbx; this
0x18001d95d  call    ?_Stop@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z; CWerService::_Stop(utl::unique_lock<utl::recursive_mutex> &)
0x18001d962  mov     rax, [rbx+158h]
0x18001d969  inc     rax
0x18001d96c  cmp     rax, 1
0x18001d970  jbe     short loc_18001D9AD
0x18001d972  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d979  lea     rax, WPP_GLOBAL_Control
0x18001d980  cmp     rcx, rax
0x18001d983  jz      short loc_18001D9A0
0x18001d985  test    byte ptr [rcx+1Ch], 8
0x18001d989  jz      short loc_18001D9A0
0x18001d98b  mov     rcx, [rcx+10h]
0x18001d98f  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001d996  mov     edx, 33h ; '3'
0x18001d99b  call    WPP_SF_
0x18001d9a0  mov     rcx, [rbx+158h]; hEvent
0x18001d9a7  call    cs:__imp_ResetEvent
0x18001d9ad  xor     eax, eax
0x18001d9af  mov     rbx, [rsp+28h+arg_0]
0x18001d9b4  add     rsp, 20h
0x18001d9b8  pop     rdi
0x18001d9b9  retn
0x18001d9ba  call    cs:__imp_SetEvent
0x18001d9c0  test    eax, eax
0x18001d9c2  jnz     short loc_18001D962
0x18001d9c4  call    cs:__imp_GetLastError
0x18001d9ca  test    eax, eax
0x18001d9cc  jle     short loc_18001D9D6
0x18001d9ce  movzx   eax, ax
0x18001d9d1  or      eax, 80070000h
0x18001d9d6  test    eax, eax
0x18001d9d8  mov     ecx, 80004005h
0x18001d9dd  cmovns  eax, ecx
0x18001d9e0  jmp     short loc_18001D9AF
```
