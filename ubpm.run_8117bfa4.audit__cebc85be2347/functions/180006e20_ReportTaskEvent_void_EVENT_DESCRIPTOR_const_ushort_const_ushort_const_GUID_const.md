# ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,_GUID const *)

- ea: `0x180006e20`
- end: `0x180006ff5`
- name: `?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBG2PEBU_GUID@@@Z`
- size: `469`
- prototype: `unsigned int __fastcall(void *, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800057e0`

## callees

- `0x180006e20`
- `0x180007e9c`
- `0x18001d0ec`
- `0x180040260`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180006f0e`
- `ntdll!EtwEventActivityIdControl` at `0x180006f49`
- `ntdll!EtwEventActivityIdControl` at `0x180006f0e`
- `ntdll!EtwEventActivityIdControl` at `0x180006f49`
- `ntdll!EtwEventWrite` at `0x180006f2a`
- `ntdll!EtwEventWrite` at `0x180006f2a`
- `ntdll!EtwEventEnabled` at `0x180006e6a`
- `ntdll!EtwEventEnabled` at `0x180006e6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006efa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006efa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f59`

## string_xrefs

- `0x180006f75`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x180006fb8`: `EventWrite error`

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
  __int64 *v19; // [rsp+30h] [rbp-40h] BYREF
  __int64 v20; // [rsp+38h] [rbp-38h]
  __int64 *v21; // [rsp+40h] [rbp-30h]
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
      v19 = (__int64 *)a3;
      v10 = -1;
      do
        v11 = a3[++v10] == 0;
      while ( !v11 );
      v20 = (unsigned int)(2 * v10 + 2);
    }
    else
    {
      v19 = &qword_1800439C0;
      v20 = 2;
    }
    if ( a4 )
    {
      v21 = (__int64 *)a4;
      do
        v11 = a4[++v9] == 0;
      while ( !v11 );
      v22 = (unsigned int)(2 * v9 + 2);
    }
    else
    {
      v21 = &qword_1800439C0;
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
0x180006e20  mov     [rsp-28h+arg_0], rbx
0x180006e25  mov     [rsp-28h+arg_10], rsi
0x180006e2a  push    rbp
0x180006e2b  push    rdi
0x180006e2c  push    r12
0x180006e2e  push    r14
0x180006e30  push    r15
0x180006e32  mov     rbp, rsp
0x180006e35  sub     rsp, 70h
0x180006e39  mov     rax, cs:__security_cookie
0x180006e40  xor     rax, rsp
0x180006e43  mov     [rbp+var_10], rax
0x180006e47  mov     r14, cs:g_hTaskEventManager
0x180006e4e  xor     r12d, r12d
0x180006e51  mov     r15, [rbp+arg_20]
0x180006e55  mov     rbx, r9
0x180006e58  mov     rdi, r8
0x180006e5b  mov     rsi, rdx
0x180006e5e  mov     rcx, [r14]
0x180006e61  test    rcx, rcx
0x180006e64  jz      loc_180006FAE
0x180006e6a  call    cs:__imp_EtwEventEnabled
0x180006e71  nop     dword ptr [rax+rax+00h]
0x180006e76  test    al, al
0x180006e78  jz      loc_180006F69
0x180006e7e  lea     rdx, qword_1800439C0
0x180006e85  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006e8c  test    rdi, rdi
0x180006e8f  jz      loc_180006FD3
0x180006e95  mov     [rbp+var_40], rdi
0x180006e99  mov     rcx, rax
0x180006e9c  nop     dword ptr [rax+00h]
0x180006ea0  cmp     [rdi+rcx*2+2], r12w
0x180006ea6  lea     rcx, [rcx+1]
0x180006eaa  jnz     short loc_180006EA0
0x180006eac  lea     ecx, ds:2[rcx*2]
0x180006eb3  mov     dword ptr [rbp+var_38+4], r12d
0x180006eb7  mov     dword ptr [rbp+var_38], ecx
0x180006eba  test    rbx, rbx
0x180006ebd  jz      loc_180006FE4
0x180006ec3  mov     [rbp+var_30], rbx
0x180006ec7  nop     word ptr [rax+rax+00000000h]
0x180006ed0  cmp     [rbx+rax*2+2], r12w
0x180006ed6  lea     rax, [rax+1]
0x180006eda  jnz     short loc_180006ED0
0x180006edc  lea     eax, ds:2[rax*2]
0x180006ee3  mov     dword ptr [rbp+var_28+4], r12d
0x180006ee7  mov     dword ptr [rbp+var_28], eax
0x180006eea  lea     rcx, [r14+8]; lpCriticalSection
0x180006eee  mov     [rbp+var_20], r15
0x180006ef2  mov     [rbp+var_18], 10h
0x180006efa  call    cs:__imp_EnterCriticalSection
0x180006f01  nop     dword ptr [rax+rax+00h]
0x180006f06  mov     rdx, r15
0x180006f09  mov     ecx, 2
0x180006f0e  call    cs:__imp_EtwEventActivityIdControl
0x180006f15  nop     dword ptr [rax+rax+00h]
0x180006f1a  mov     rcx, [r14]
0x180006f1d  lea     r9, [rbp+var_40]
0x180006f21  mov     r8d, 3
0x180006f27  mov     rdx, rsi
0x180006f2a  call    cs:__imp_EtwEventWrite
0x180006f31  nop     dword ptr [rax+rax+00h]
0x180006f36  lea     rdx, [rbp+var_50]
0x180006f3a  mov     [rbp+var_50], r12
0x180006f3e  mov     ecx, 2
0x180006f43  mov     [rbp+var_48], r12
0x180006f47  mov     edi, eax
0x180006f49  call    cs:__imp_EtwEventActivityIdControl
0x180006f50  nop     dword ptr [rax+rax+00h]
0x180006f55  lea     rcx, [r14+8]; lpCriticalSection
0x180006f59  call    cs:__imp_LeaveCriticalSection
0x180006f60  nop     dword ptr [rax+rax+00h]
0x180006f65  test    edi, edi
0x180006f67  jnz     short loc_180006FB5
0x180006f69  mov     edi, r12d
0x180006f6c  test    edi, edi
0x180006f6e  movzx   r8d, di
0x180006f72  mov     rdx, rsi
0x180006f75  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x180006f7c  cmovns  r8d, r12d
0x180006f80  call    TaskEventTrace
0x180006f85  mov     eax, r8d
0x180006f88  mov     rcx, [rbp+var_10]
0x180006f8c  xor     rcx, rsp; StackCookie
0x180006f8f  call    __security_check_cookie
0x180006f94  lea     r11, [rsp+70h+var_s0]
0x180006f99  mov     rbx, [r11+30h]
0x180006f9d  mov     rsi, [r11+40h]
0x180006fa1  mov     rsp, r11
0x180006fa4  pop     r15
0x180006fa6  pop     r14
0x180006fa8  pop     r12
0x180006faa  pop     rdi
0x180006fab  pop     rbp
0x180006fac  retn
0x180006fae  mov     edi, 1
0x180006fb3  jmp     short loc_180006F6C
0x180006fb5  mov     r8d, edi; unsigned int
0x180006fb8  lea     rdx, aEventwriteErro; "EventWrite error"
0x180006fbf  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180006fc4  test    edi, edi
0x180006fc6  jle     short loc_180006F6C
0x180006fc8  movzx   edi, di
0x180006fcb  or      edi, 80070000h
0x180006fd1  jmp     short loc_180006F6C
0x180006fd3  mov     [rbp+var_40], rdx
0x180006fd7  mov     [rbp+var_38], 2
0x180006fdf  jmp     loc_180006EBA
0x180006fe4  mov     [rbp+var_30], rdx
0x180006fe8  mov     [rbp+var_28], 2
0x180006ff0  jmp     loc_180006EEA
```
