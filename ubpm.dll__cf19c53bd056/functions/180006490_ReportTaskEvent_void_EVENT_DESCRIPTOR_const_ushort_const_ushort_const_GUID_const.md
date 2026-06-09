# ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,_GUID const *)

- ea: `0x180006490`
- end: `0x180006646`
- name: `?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBG2PEBU_GUID@@@Z`
- size: `438`
- prototype: `unsigned int __fastcall(void *, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180004f40`

## callees

- `0x180006490`
- `0x180007460`
- `0x1800207e8`
- `0x18003d810`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180006578`
- `ntdll!EtwEventActivityIdControl` at `0x1800065a7`
- `ntdll!EtwEventActivityIdControl` at `0x180006578`
- `ntdll!EtwEventActivityIdControl` at `0x1800065a7`
- `ntdll!EtwEventWrite` at `0x18000658e`
- `ntdll!EtwEventWrite` at `0x18000658e`
- `ntdll!EtwEventEnabled` at `0x1800064da`
- `ntdll!EtwEventEnabled` at `0x1800064da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000656a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000656a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065b1`

## string_xrefs

- `0x1800065c7`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x180006609`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall ReportTaskEvent(
        void *a1,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        const struct _GUID *a5)
{
  EventManager *v5; // r14
  __int64 v9; // rax
  __int64 v10; // rcx
  bool v11; // zf
  int v12; // eax
  int v13; // edi
  EventManager *v14; // rcx
  __int64 v15; // r8
  unsigned int v16; // r8d
  _QWORD v18[2]; // [rsp+20h] [rbp-50h] BYREF
  int *v19; // [rsp+30h] [rbp-40h] BYREF
  __int64 v20; // [rsp+38h] [rbp-38h]
  int *v21; // [rsp+40h] [rbp-30h]
  __int64 v22; // [rsp+48h] [rbp-28h]
  const struct _GUID *v23; // [rsp+50h] [rbp-20h]
  __int64 v24; // [rsp+58h] [rbp-18h]

  v5 = g_hTaskEventManager;
  if ( *(_QWORD *)g_hTaskEventManager )
  {
    if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_hTaskEventManager, a2) )
      goto LABEL_12;
    v9 = -1;
    if ( a3 )
    {
      v19 = (int *)a3;
      v10 = -1;
      do
        v11 = a3[++v10] == 0;
      while ( !v11 );
      v20 = (unsigned int)(2 * v10 + 2);
    }
    else
    {
      v19 = &dword_1800405F4;
      v20 = 2;
    }
    if ( a4 )
    {
      v21 = (int *)a4;
      do
        v11 = a4[++v9] == 0;
      while ( !v11 );
      v22 = (unsigned int)(2 * v9 + 2);
    }
    else
    {
      v21 = &dword_1800405F4;
      v22 = 2;
    }
    v23 = a5;
    v24 = 16;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 8));
    EtwEventActivityIdControl(2, a5);
    v12 = EtwEventWrite(*(_QWORD *)v5, a2, 3, &v19);
    v18[0] = 0;
    v18[1] = 0;
    v13 = v12;
    EtwEventActivityIdControl(2, v18);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 8));
    if ( v13 )
    {
      EventManager::LogIt(v14, L"EventWrite error", v13);
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
LABEL_12:
      v13 = 0;
    }
  }
  else
  {
    v13 = 1;
  }
  v15 = (unsigned __int16)v13;
  if ( v13 >= 0 )
    v15 = 0;
  TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", a2, v15);
  return v16;
}

```

## disassembly

```asm
0x180006490  mov     [rsp-28h+arg_0], rbx
0x180006495  mov     [rsp-28h+arg_10], rsi
0x18000649a  push    rbp
0x18000649b  push    rdi
0x18000649c  push    r12
0x18000649e  push    r14
0x1800064a0  push    r15
0x1800064a2  mov     rbp, rsp
0x1800064a5  sub     rsp, 70h
0x1800064a9  mov     rax, cs:__security_cookie
0x1800064b0  xor     rax, rsp
0x1800064b3  mov     [rbp+var_10], rax
0x1800064b7  mov     r14, cs:g_hTaskEventManager
0x1800064be  xor     r12d, r12d
0x1800064c1  mov     r15, [rbp+arg_20]
0x1800064c5  mov     rbx, r9
0x1800064c8  mov     rdi, r8
0x1800064cb  mov     rsi, rdx
0x1800064ce  mov     rcx, [r14]
0x1800064d1  test    rcx, rcx
0x1800064d4  jz      loc_1800065FF
0x1800064da  call    cs:__imp_EtwEventEnabled
0x1800064e0  test    al, al
0x1800064e2  jz      loc_1800065BB
0x1800064e8  lea     rdx, dword_1800405F4
0x1800064ef  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800064f6  test    rdi, rdi
0x1800064f9  jz      loc_180006624
0x1800064ff  mov     [rbp+var_40], rdi
0x180006503  mov     rcx, rax
0x180006506  nop     word ptr [rax+rax+00000000h]
0x180006510  cmp     [rdi+rcx*2+2], r12w
0x180006516  lea     rcx, [rcx+1]
0x18000651a  jnz     short loc_180006510
0x18000651c  lea     ecx, ds:2[rcx*2]
0x180006523  mov     dword ptr [rbp+var_38+4], r12d
0x180006527  mov     dword ptr [rbp+var_38], ecx
0x18000652a  test    rbx, rbx
0x18000652d  jz      loc_180006635
0x180006533  mov     [rbp+var_30], rbx
0x180006537  nop     word ptr [rax+rax+00000000h]
0x180006540  cmp     [rbx+rax*2+2], r12w
0x180006546  lea     rax, [rax+1]
0x18000654a  jnz     short loc_180006540
0x18000654c  lea     eax, ds:2[rax*2]
0x180006553  mov     dword ptr [rbp+var_28+4], r12d
0x180006557  mov     dword ptr [rbp+var_28], eax
0x18000655a  lea     rcx, [r14+8]; lpCriticalSection
0x18000655e  mov     [rbp+var_20], r15
0x180006562  mov     [rbp+var_18], 10h
0x18000656a  call    cs:__imp_EnterCriticalSection
0x180006570  mov     rdx, r15
0x180006573  mov     ecx, 2
0x180006578  call    cs:__imp_EtwEventActivityIdControl
0x18000657e  mov     rcx, [r14]
0x180006581  lea     r9, [rbp+var_40]
0x180006585  mov     r8d, 3
0x18000658b  mov     rdx, rsi
0x18000658e  call    cs:__imp_EtwEventWrite
0x180006594  lea     rdx, [rbp+var_50]
0x180006598  mov     [rbp+var_50], r12
0x18000659c  mov     ecx, 2
0x1800065a1  mov     [rbp+var_48], r12
0x1800065a5  mov     edi, eax
0x1800065a7  call    cs:__imp_EtwEventActivityIdControl
0x1800065ad  lea     rcx, [r14+8]; lpCriticalSection
0x1800065b1  call    cs:__imp_LeaveCriticalSection
0x1800065b7  test    edi, edi
0x1800065b9  jnz     short loc_180006606
0x1800065bb  mov     edi, r12d
0x1800065be  test    edi, edi
0x1800065c0  movzx   r8d, di
0x1800065c4  mov     rdx, rsi
0x1800065c7  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x1800065ce  cmovns  r8d, r12d
0x1800065d2  call    TaskEventTrace
0x1800065d7  mov     eax, r8d
0x1800065da  mov     rcx, [rbp+var_10]
0x1800065de  xor     rcx, rsp; StackCookie
0x1800065e1  call    __security_check_cookie
0x1800065e6  lea     r11, [rsp+70h+var_s0]
0x1800065eb  mov     rbx, [r11+30h]
0x1800065ef  mov     rsi, [r11+40h]
0x1800065f3  mov     rsp, r11
0x1800065f6  pop     r15
0x1800065f8  pop     r14
0x1800065fa  pop     r12
0x1800065fc  pop     rdi
0x1800065fd  pop     rbp
0x1800065fe  retn
0x1800065ff  mov     edi, 1
0x180006604  jmp     short loc_1800065BE
0x180006606  mov     r8d, edi; unsigned int
0x180006609  lea     rdx, aEventwriteErro; "EventWrite error"
0x180006610  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180006615  test    edi, edi
0x180006617  jle     short loc_1800065BE
0x180006619  movzx   edi, di
0x18000661c  or      edi, 80070000h
0x180006622  jmp     short loc_1800065BE
0x180006624  mov     [rbp+var_40], rdx
0x180006628  mov     [rbp+var_38], 2
0x180006630  jmp     loc_18000652A
0x180006635  mov     [rbp+var_30], rdx
0x180006639  mov     [rbp+var_28], 2
0x180006641  jmp     loc_18000655A
```
