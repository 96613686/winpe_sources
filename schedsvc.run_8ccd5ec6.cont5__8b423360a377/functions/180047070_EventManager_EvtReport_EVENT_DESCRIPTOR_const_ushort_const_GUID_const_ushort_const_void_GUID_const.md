# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,void *,_GUID const *)

- ea: `0x180047070`
- end: `0x180047207`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@1PEAX2@Z`
- size: `407`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *, const unsigned __int16 *, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18004e9d0`

## callees

- `0x180047070`
- `0x180052888`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800471b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800471b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047151`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047151`
- `ntdll!EtwEventEnabled` at `0x1800470ba`
- `ntdll!EtwEventEnabled` at `0x1800470ba`
- `ntdll!EtwEventActivityIdControl` at `0x180047165`
- `ntdll!EtwEventActivityIdControl` at `0x1800471a4`
- `ntdll!EtwEventActivityIdControl` at `0x180047165`
- `ntdll!EtwEventActivityIdControl` at `0x1800471a4`
- `ntdll!EtwEventWrite` at `0x180047185`
- `ntdll!EtwEventWrite` at `0x180047185`

## string_xrefs

- `0x1800471c6`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        const unsigned __int16 *a5)
{
  EventManager *v5; // rdi
  __int64 v9; // rcx
  __int64 v10; // rax
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  signed int v12; // eax
  signed int v13; // edi
  EventManager *v14; // rcx
  _QWORD v15[2]; // [rsp+20h] [rbp-50h] BYREF
  const OLECHAR *v16; // [rsp+30h] [rbp-40h] BYREF
  __int64 v17; // [rsp+38h] [rbp-38h]
  const struct _GUID *v18; // [rsp+40h] [rbp-30h]
  __int64 v19; // [rsp+48h] [rbp-28h]
  const OLECHAR *v20; // [rsp+50h] [rbp-20h]
  __int64 v21; // [rsp+58h] [rbp-18h]

  v5 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, RUN) )
    return 0;
  v9 = -1;
  if ( a3 )
  {
    v16 = a3;
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    v17 = (unsigned int)(2 * v10 + 2);
  }
  else
  {
    v16 = &ChannelPath;
    v17 = 2;
  }
  v18 = a4;
  v19 = 16;
  if ( a5 )
  {
    v20 = a5;
    do
      ++v9;
    while ( a5[v9] );
    v21 = (unsigned int)(2 * v9 + 2);
  }
  else
  {
    v20 = &ChannelPath;
    v21 = 2;
  }
  v11 = (struct _RTL_CRITICAL_SECTION *)((char *)v5 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 8));
  EtwEventActivityIdControl(2, a4);
  v12 = EtwEventWrite(*(_QWORD *)v5, RUN, 3, &v16);
  v15[0] = 0;
  v15[1] = 0;
  v13 = v12;
  EtwEventActivityIdControl(2, v15);
  LeaveCriticalSection(v11);
  if ( !v13 )
    return 0;
  EventManager::LogIt(v14, L"EventWrite error", v13);
  if ( v13 > 0 )
    return (unsigned __int16)v13 | 0x80070000;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180047070  mov     [rsp-18h+arg_0], rbx
0x180047075  mov     [rsp-18h+arg_8], rsi
0x18004707a  push    rbp
0x18004707b  push    rdi
0x18004707c  push    r14
0x18004707e  mov     rbp, rsp
0x180047081  sub     rsp, 70h
0x180047085  mov     rax, cs:__security_cookie
0x18004708c  xor     rax, rsp
0x18004708f  mov     [rbp+var_10], rax
0x180047093  mov     rdi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x18004709a  xor     r14d, r14d
0x18004709d  mov     rsi, r9
0x1800470a0  mov     rbx, r8
0x1800470a3  mov     rcx, [rdi]
0x1800470a6  test    rcx, rcx
0x1800470a9  jnz     short loc_1800470B3
0x1800470ab  lea     eax, [rcx+1]
0x1800470ae  jmp     loc_1800471E5
0x1800470b3  lea     rdx, RUN
0x1800470ba  call    cs:__imp_EtwEventEnabled
0x1800470c1  nop     dword ptr [rax+rax+00h]
0x1800470c6  test    al, al
0x1800470c8  jz      loc_1800471E3
0x1800470ce  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800470d2  lea     rdx, ChannelPath
0x1800470d9  test    rbx, rbx
0x1800470dc  jz      short loc_1800470FF
0x1800470de  mov     [rbp+var_40], rbx
0x1800470e2  mov     rax, rcx
0x1800470e5  inc     rax
0x1800470e8  cmp     [rbx+rax*2], r14w
0x1800470ed  jnz     short loc_1800470E5
0x1800470ef  lea     eax, ds:2[rax*2]
0x1800470f6  mov     dword ptr [rbp+var_38+4], r14d
0x1800470fa  mov     dword ptr [rbp+var_38], eax
0x1800470fd  jmp     short loc_18004710B
0x1800470ff  mov     [rbp+var_40], rdx
0x180047103  mov     [rbp+var_38], 2
0x18004710b  mov     rax, [rbp+arg_20]
0x18004710f  mov     [rbp+var_30], rsi
0x180047113  mov     [rbp+var_28], 10h
0x18004711b  test    rax, rax
0x18004711e  jz      short loc_18004713E
0x180047120  mov     [rbp+var_20], rax
0x180047124  inc     rcx
0x180047127  cmp     [rax+rcx*2], r14w
0x18004712c  jnz     short loc_180047124
0x18004712e  lea     eax, ds:2[rcx*2]
0x180047135  mov     dword ptr [rbp+var_18+4], r14d
0x180047139  mov     dword ptr [rbp+var_18], eax
0x18004713c  jmp     short loc_18004714A
0x18004713e  mov     [rbp+var_20], rdx
0x180047142  mov     [rbp+var_18], 2
0x18004714a  lea     rbx, [rdi+8]
0x18004714e  mov     rcx, rbx; lpCriticalSection
0x180047151  call    cs:__imp_EnterCriticalSection
0x180047158  nop     dword ptr [rax+rax+00h]
0x18004715d  mov     rdx, rsi
0x180047160  mov     ecx, 2
0x180047165  call    cs:__imp_EtwEventActivityIdControl
0x18004716c  nop     dword ptr [rax+rax+00h]
0x180047171  mov     rcx, [rdi]
0x180047174  lea     r9, [rbp+var_40]
0x180047178  mov     r8d, 3
0x18004717e  lea     rdx, RUN
0x180047185  call    cs:__imp_EtwEventWrite
0x18004718c  nop     dword ptr [rax+rax+00h]
0x180047191  lea     rdx, [rbp+var_50]
0x180047195  mov     [rbp+var_50], r14
0x180047199  mov     ecx, 2
0x18004719e  mov     [rbp+var_48], r14
0x1800471a2  mov     edi, eax
0x1800471a4  call    cs:__imp_EtwEventActivityIdControl
0x1800471ab  nop     dword ptr [rax+rax+00h]
0x1800471b0  mov     rcx, rbx; lpCriticalSection
0x1800471b3  call    cs:__imp_LeaveCriticalSection
0x1800471ba  nop     dword ptr [rax+rax+00h]
0x1800471bf  test    edi, edi
0x1800471c1  jz      short loc_1800471E3
0x1800471c3  mov     r8d, edi; unsigned int
0x1800471c6  lea     rdx, aEventwriteErro; "EventWrite error"
0x1800471cd  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x1800471d2  test    edi, edi
0x1800471d4  jle     short loc_1800471DF
0x1800471d6  movzx   edi, di
0x1800471d9  or      edi, 80070000h
0x1800471df  mov     eax, edi
0x1800471e1  jmp     short loc_1800471E5
0x1800471e3  xor     eax, eax
0x1800471e5  mov     rcx, [rbp+var_10]
0x1800471e9  xor     rcx, rsp; StackCookie
0x1800471ec  call    __security_check_cookie
0x1800471f1  lea     r11, [rsp+70h+var_s0]
0x1800471f6  mov     rbx, [r11+20h]
0x1800471fa  mov     rsi, [r11+28h]
0x1800471fe  mov     rsp, r11
0x180047201  pop     r14
0x180047203  pop     rdi
0x180047204  pop     rbp
0x180047205  retn
```
