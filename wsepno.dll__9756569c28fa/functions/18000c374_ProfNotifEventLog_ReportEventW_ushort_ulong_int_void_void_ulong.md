# ProfNotifEventLog::ReportEventW(ushort,ulong,int,void *,void *,ulong)

- ea: `0x18000c374`
- end: `0x18000c43e`
- name: `?ReportEventW@ProfNotifEventLog@@QEAAJGKHPEAX0K@Z`
- size: `202`
- prototype: `int(ProfNotifEventLog *__hidden this, unsigned __int16, unsigned int, int, void *, void *, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180007d30`
- `0x180007de0`
- `0x180007e90`
- `0x180008510`
- `0x180008648`
- `0x1800087a8`

## callees

- `0x18000c324`
- `0x18000c374`
- `0x18000d3b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c40c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c40c`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x18000c395`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x18000c395`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18000c402`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18000c402`

## string_xrefs

- `0x18000c38c`: `Windows Search Service Profile Notification`

## pseudocode

```c
__int64 __fastcall ProfNotifEventLog::ReportEventW(ProfNotifEventLog *this, WORD a2, unsigned int a3)
{
  HANDLE v6; // rax
  signed int LastError; // eax
  signed int v8; // ebx
  signed int v9; // eax

  if ( *(_QWORD *)this )
    goto LABEL_18;
  v6 = RegisterEventSourceW(0, L"Windows Search Service Profile Notification");
  *(_QWORD *)this = v6;
  if ( v6 )
    goto LABEL_18;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( v8 >= 0 )
  {
LABEL_18:
    if ( *(_QWORD *)this )
    {
      v8 = 0;
      if ( !CEventThrottleManager::ShouldThrottle(this, a3)
        && !ReportEventW(*(HANDLE *)this, a2, 0, a3, 0, *((_WORD *)this + 4), 0, (LPCWSTR *)this + 2, 0) )
      {
        v9 = GetLastError();
        if ( v9 != 997 )
        {
          if ( v9 > 0 )
            v8 = (unsigned __int16)v9 | 0x80070000;
          else
            v8 = v9;
        }
      }
      CEventLog::CStrArray::Destroy((ProfNotifEventLog *)((char *)this + 8));
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c374  push    rbx
0x18000c376  push    rbp
0x18000c377  push    rsi
0x18000c378  push    rdi
0x18000c379  sub     rsp, 58h
0x18000c37d  cmp     qword ptr [rcx], 0
0x18000c381  mov     esi, r8d
0x18000c384  movzx   ebp, dx
0x18000c387  mov     rdi, rcx
0x18000c38a  jnz     short loc_18000C3BC
0x18000c38c  lea     rdx, SourceName; "Windows Search Service Profile Notifica"...
0x18000c393  xor     ecx, ecx; lpUNCServerName
0x18000c395  call    cs:__imp_RegisterEventSourceW
0x18000c39b  mov     [rdi], rax
0x18000c39e  test    rax, rax
0x18000c3a1  jnz     short loc_18000C3BC
0x18000c3a3  call    cs:__imp_GetLastError
0x18000c3a9  mov     ebx, eax
0x18000c3ab  test    eax, eax
0x18000c3ad  jle     short loc_18000C3B8
0x18000c3af  movzx   ebx, ax
0x18000c3b2  or      ebx, 80070000h
0x18000c3b8  test    ebx, ebx
0x18000c3ba  js      short loc_18000C433
0x18000c3bc  cmp     qword ptr [rdi], 0
0x18000c3c0  jnz     short loc_18000C3C9
0x18000c3c2  mov     ebx, 80004005h
0x18000c3c7  jmp     short loc_18000C433
0x18000c3c9  mov     edx, esi; unsigned int
0x18000c3cb  xor     ebx, ebx
0x18000c3cd  call    ?ShouldThrottle@CEventThrottleManager@@QEAA_NK@Z; CEventThrottleManager::ShouldThrottle(ulong)
0x18000c3d2  test    al, al
0x18000c3d4  jnz     short loc_18000C42A
0x18000c3d6  mov     rcx, [rdi]; hEventLog
0x18000c3d9  lea     rax, [rdi+10h]
0x18000c3dd  mov     [rsp+78h+lpRawData], rbx; lpRawData
0x18000c3e2  xor     r8d, r8d; wCategory
0x18000c3e5  mov     [rsp+78h+lpStrings], rax; lpStrings
0x18000c3ea  mov     r9d, esi; dwEventID
0x18000c3ed  movzx   eax, word ptr [rdi+8]
0x18000c3f1  movzx   edx, bp; wType
0x18000c3f4  mov     [rsp+78h+dwDataSize], ebx; dwDataSize
0x18000c3f8  mov     [rsp+78h+wNumStrings], ax; wNumStrings
0x18000c3fd  mov     [rsp+78h+lpUserSid], rbx; lpUserSid
0x18000c402  call    cs:__imp_ReportEventW
0x18000c408  test    eax, eax
0x18000c40a  jnz     short loc_18000C42A
0x18000c40c  call    cs:__imp_GetLastError
0x18000c412  cmp     eax, 3E5h
0x18000c417  jz      short loc_18000C42A
0x18000c419  test    eax, eax
0x18000c41b  jg      short loc_18000C421
0x18000c41d  mov     ebx, eax
0x18000c41f  jmp     short loc_18000C42A
0x18000c421  movzx   ebx, ax
0x18000c424  or      ebx, 80070000h
0x18000c42a  lea     rcx, [rdi+8]; this
0x18000c42e  call    ?Destroy@CStrArray@CEventLog@@AEAAXXZ; CEventLog::CStrArray::Destroy(void)
0x18000c433  mov     eax, ebx
0x18000c435  add     rsp, 58h
0x18000c439  pop     rdi
0x18000c43a  pop     rsi
0x18000c43b  pop     rbp
0x18000c43c  pop     rbx
0x18000c43d  retn
```
