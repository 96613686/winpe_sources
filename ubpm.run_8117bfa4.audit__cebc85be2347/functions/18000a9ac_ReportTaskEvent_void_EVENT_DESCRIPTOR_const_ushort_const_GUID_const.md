# ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)

- ea: `0x18000a9ac`
- end: `0x18000ab27`
- name: `?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z`
- size: `379`
- prototype: `unsigned int __fastcall(void *, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800057e0`
- `0x180007ec0`
- `0x180008b30`
- `0x180009a30`
- `0x18000a230`
- `0x180030914`

## callees

- `0x180007e9c`
- `0x18000a9ac`
- `0x18001d0ec`
- `0x180040260`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18000aa50`
- `ntdll!EtwEventActivityIdControl` at `0x18000aa8b`
- `ntdll!EtwEventActivityIdControl` at `0x18000aa50`
- `ntdll!EtwEventActivityIdControl` at `0x18000aa8b`
- `ntdll!EtwEventWrite` at `0x18000aa6c`
- `ntdll!EtwEventWrite` at `0x18000aa6c`
- `ntdll!EtwEventEnabled` at `0x18000a9ec`
- `ntdll!EtwEventEnabled` at `0x18000a9ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa9a`

## string_xrefs

- `0x18000aab6`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x18000ab0c`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall ReportTaskEvent(
        void *a1,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned __int16 *a3,
        const struct _GUID *a4)
{
  EventManager *v4; // rdi
  __int64 v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  int v10; // eax
  int v11; // edi
  EventManager *v12; // rcx
  __int64 v13; // r8
  unsigned int v14; // r8d
  _QWORD v16[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 *v17; // [rsp+30h] [rbp-30h] BYREF
  __int64 v18; // [rsp+38h] [rbp-28h]
  const struct _GUID *v19; // [rsp+40h] [rbp-20h]
  __int64 v20; // [rsp+48h] [rbp-18h]

  v4 = g_hTaskEventManager;
  if ( *(_QWORD *)g_hTaskEventManager )
  {
    if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_hTaskEventManager, a2) )
      goto LABEL_8;
    if ( a3 )
    {
      v17 = (__int64 *)a3;
      v8 = -1;
      do
        ++v8;
      while ( a3[v8] );
      v18 = (unsigned int)(2 * v8 + 2);
    }
    else
    {
      v18 = 2;
      v17 = &qword_1800439C0;
    }
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)v4 + 8);
    v19 = a4;
    v20 = 16;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 8));
    EtwEventActivityIdControl(2, a4);
    v10 = EtwEventWrite(*(_QWORD *)v4, a2, 2, &v17);
    v16[0] = 0;
    v16[1] = 0;
    v11 = v10;
    EtwEventActivityIdControl(2, v16);
    LeaveCriticalSection(v9);
    if ( v11 )
    {
      EventManager::LogIt(v12, L"EventWrite error", v11);
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
LABEL_8:
      v11 = 0;
    }
  }
  else
  {
    v11 = 1;
  }
  v13 = (unsigned __int16)v11;
  if ( v11 >= 0 )
    v13 = 0;
  TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", a2, v13);
  return v14;
}

```

## disassembly

```asm
0x18000a9ac  mov     [rsp-28h+arg_0], rbx
0x18000a9b1  push    rbp
0x18000a9b2  push    rsi
0x18000a9b3  push    rdi
0x18000a9b4  push    r14
0x18000a9b6  push    r15
0x18000a9b8  mov     rbp, rsp
0x18000a9bb  sub     rsp, 60h
0x18000a9bf  mov     rax, cs:__security_cookie
0x18000a9c6  xor     rax, rsp
0x18000a9c9  mov     [rbp+var_10], rax
0x18000a9cd  mov     rdi, cs:g_hTaskEventManager
0x18000a9d4  xor     r15d, r15d
0x18000a9d7  mov     r14, r9
0x18000a9da  mov     rbx, r8
0x18000a9dd  mov     rsi, rdx
0x18000a9e0  mov     rcx, [rdi]
0x18000a9e3  test    rcx, rcx
0x18000a9e6  jz      loc_18000AAEA
0x18000a9ec  call    cs:__imp_EtwEventEnabled
0x18000a9f3  nop     dword ptr [rax+rax+00h]
0x18000a9f8  test    al, al
0x18000a9fa  jz      loc_18000AAAA
0x18000aa00  test    rbx, rbx
0x18000aa03  jz      loc_18000AAF1
0x18000aa09  mov     [rbp+var_30], rbx
0x18000aa0d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000aa11  inc     rax
0x18000aa14  cmp     [rbx+rax*2], r15w
0x18000aa19  jnz     short loc_18000AA11
0x18000aa1b  lea     eax, ds:2[rax*2]
0x18000aa22  mov     dword ptr [rbp+var_28+4], r15d
0x18000aa26  mov     dword ptr [rbp+var_28], eax
0x18000aa29  lea     rbx, [rdi+8]
0x18000aa2d  mov     [rbp+var_20], r14
0x18000aa31  mov     rcx, rbx; lpCriticalSection
0x18000aa34  mov     [rbp+var_18], 10h
0x18000aa3c  call    cs:__imp_EnterCriticalSection
0x18000aa43  nop     dword ptr [rax+rax+00h]
0x18000aa48  mov     rdx, r14
0x18000aa4b  mov     ecx, 2
0x18000aa50  call    cs:__imp_EtwEventActivityIdControl
0x18000aa57  nop     dword ptr [rax+rax+00h]
0x18000aa5c  mov     rcx, [rdi]
0x18000aa5f  lea     r9, [rbp+var_30]
0x18000aa63  mov     r8d, 2
0x18000aa69  mov     rdx, rsi
0x18000aa6c  call    cs:__imp_EtwEventWrite
0x18000aa73  nop     dword ptr [rax+rax+00h]
0x18000aa78  lea     rdx, [rbp+var_40]
0x18000aa7c  mov     [rbp+var_40], r15
0x18000aa80  mov     ecx, 2
0x18000aa85  mov     [rbp+var_38], r15
0x18000aa89  mov     edi, eax
0x18000aa8b  call    cs:__imp_EtwEventActivityIdControl
0x18000aa92  nop     dword ptr [rax+rax+00h]
0x18000aa97  mov     rcx, rbx; lpCriticalSection
0x18000aa9a  call    cs:__imp_LeaveCriticalSection
0x18000aaa1  nop     dword ptr [rax+rax+00h]
0x18000aaa6  test    edi, edi
0x18000aaa8  jnz     short loc_18000AB09
0x18000aaaa  mov     edi, r15d
0x18000aaad  test    edi, edi
0x18000aaaf  movzx   r8d, di
0x18000aab3  mov     rdx, rsi
0x18000aab6  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x18000aabd  cmovns  r8d, r15d
0x18000aac1  call    TaskEventTrace
0x18000aac6  mov     eax, r8d
0x18000aac9  mov     rcx, [rbp+var_10]
0x18000aacd  xor     rcx, rsp; StackCookie
0x18000aad0  call    __security_check_cookie
0x18000aad5  mov     rbx, [rsp+60h+arg_0]
0x18000aadd  add     rsp, 60h
0x18000aae1  pop     r15
0x18000aae3  pop     r14
0x18000aae5  pop     rdi
0x18000aae6  pop     rsi
0x18000aae7  pop     rbp
0x18000aae8  retn
0x18000aaea  mov     edi, 1
0x18000aaef  jmp     short loc_18000AAAD
0x18000aaf1  lea     rax, qword_1800439C0
0x18000aaf8  mov     [rbp+var_28], 2
0x18000ab00  mov     [rbp+var_30], rax
0x18000ab04  jmp     loc_18000AA29
0x18000ab09  mov     r8d, edi; unsigned int
0x18000ab0c  lea     rdx, aEventwriteErro; "EventWrite error"
0x18000ab13  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18000ab18  test    edi, edi
0x18000ab1a  jle     short loc_18000AAAD
0x18000ab1c  movzx   edi, di
0x18000ab1f  or      edi, 80070000h
0x18000ab25  jmp     short loc_18000AAAD
```
