# ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)

- ea: `0x18000a03c`
- end: `0x18000a192`
- name: `?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z`
- size: `342`
- prototype: `unsigned int __fastcall(void *, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180003050`
- `0x180004f40`
- `0x180007480`
- `0x180008030`
- `0x180008f30`
- `0x18002e764`

## callees

- `0x180007460`
- `0x18000a03c`
- `0x1800207e8`
- `0x18003d810`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18000a0d4`
- `ntdll!EtwEventActivityIdControl` at `0x18000a103`
- `ntdll!EtwEventActivityIdControl` at `0x18000a0d4`
- `ntdll!EtwEventActivityIdControl` at `0x18000a103`
- `ntdll!EtwEventWrite` at `0x18000a0ea`
- `ntdll!EtwEventWrite` at `0x18000a0ea`
- `ntdll!EtwEventEnabled` at `0x18000a07c`
- `ntdll!EtwEventEnabled` at `0x18000a07c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a0c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a0c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a10c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a10c`

## string_xrefs

- `0x18000a122`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x18000a177`: `EventWrite error`

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
  int *v17; // [rsp+30h] [rbp-30h] BYREF
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
      v17 = (int *)a3;
      v8 = -1;
      do
        ++v8;
      while ( a3[v8] );
      v18 = (unsigned int)(2 * v8 + 2);
    }
    else
    {
      v18 = 2;
      v17 = &dword_1800405F4;
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
0x18000a03c  mov     [rsp-28h+arg_0], rbx
0x18000a041  push    rbp
0x18000a042  push    rsi
0x18000a043  push    rdi
0x18000a044  push    r14
0x18000a046  push    r15
0x18000a048  mov     rbp, rsp
0x18000a04b  sub     rsp, 60h
0x18000a04f  mov     rax, cs:__security_cookie
0x18000a056  xor     rax, rsp
0x18000a059  mov     [rbp+var_10], rax
0x18000a05d  mov     rdi, cs:g_hTaskEventManager
0x18000a064  xor     r15d, r15d
0x18000a067  mov     r14, r9
0x18000a06a  mov     rbx, r8
0x18000a06d  mov     rsi, rdx
0x18000a070  mov     rcx, [rdi]
0x18000a073  test    rcx, rcx
0x18000a076  jz      loc_18000A155
0x18000a07c  call    cs:__imp_EtwEventEnabled
0x18000a082  test    al, al
0x18000a084  jz      loc_18000A116
0x18000a08a  test    rbx, rbx
0x18000a08d  jz      loc_18000A15C
0x18000a093  mov     [rbp+var_30], rbx
0x18000a097  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a09b  inc     rax
0x18000a09e  cmp     [rbx+rax*2], r15w
0x18000a0a3  jnz     short loc_18000A09B
0x18000a0a5  lea     eax, ds:2[rax*2]
0x18000a0ac  mov     dword ptr [rbp+var_28+4], r15d
0x18000a0b0  mov     dword ptr [rbp+var_28], eax
0x18000a0b3  lea     rbx, [rdi+8]
0x18000a0b7  mov     [rbp+var_20], r14
0x18000a0bb  mov     rcx, rbx; lpCriticalSection
0x18000a0be  mov     [rbp+var_18], 10h
0x18000a0c6  call    cs:__imp_EnterCriticalSection
0x18000a0cc  mov     rdx, r14
0x18000a0cf  mov     ecx, 2
0x18000a0d4  call    cs:__imp_EtwEventActivityIdControl
0x18000a0da  mov     rcx, [rdi]
0x18000a0dd  lea     r9, [rbp+var_30]
0x18000a0e1  mov     r8d, 2
0x18000a0e7  mov     rdx, rsi
0x18000a0ea  call    cs:__imp_EtwEventWrite
0x18000a0f0  lea     rdx, [rbp+var_40]
0x18000a0f4  mov     [rbp+var_40], r15
0x18000a0f8  mov     ecx, 2
0x18000a0fd  mov     [rbp+var_38], r15
0x18000a101  mov     edi, eax
0x18000a103  call    cs:__imp_EtwEventActivityIdControl
0x18000a109  mov     rcx, rbx; lpCriticalSection
0x18000a10c  call    cs:__imp_LeaveCriticalSection
0x18000a112  test    edi, edi
0x18000a114  jnz     short loc_18000A174
0x18000a116  mov     edi, r15d
0x18000a119  test    edi, edi
0x18000a11b  movzx   r8d, di
0x18000a11f  mov     rdx, rsi
0x18000a122  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x18000a129  cmovns  r8d, r15d
0x18000a12d  call    TaskEventTrace
0x18000a132  mov     eax, r8d
0x18000a135  mov     rcx, [rbp+var_10]
0x18000a139  xor     rcx, rsp; StackCookie
0x18000a13c  call    __security_check_cookie
0x18000a141  mov     rbx, [rsp+60h+arg_0]
0x18000a149  add     rsp, 60h
0x18000a14d  pop     r15
0x18000a14f  pop     r14
0x18000a151  pop     rdi
0x18000a152  pop     rsi
0x18000a153  pop     rbp
0x18000a154  retn
0x18000a155  mov     edi, 1
0x18000a15a  jmp     short loc_18000A119
0x18000a15c  lea     rax, dword_1800405F4
0x18000a163  mov     [rbp+var_28], 2
0x18000a16b  mov     [rbp+var_30], rax
0x18000a16f  jmp     loc_18000A0B3
0x18000a174  mov     r8d, edi; unsigned int
0x18000a177  lea     rdx, aEventwriteErro; "EventWrite error"
0x18000a17e  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18000a183  test    edi, edi
0x18000a185  jle     short loc_18000A119
0x18000a187  movzx   edi, di
0x18000a18a  or      edi, 80070000h
0x18000a190  jmp     short loc_18000A119
```
