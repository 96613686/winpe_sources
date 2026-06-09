# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,void *,_GUID const *)

- ea: `0x18004510c`
- end: `0x18004527e`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@1PEAX2@Z`
- size: `370`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *, const unsigned __int16 *, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18004c6d0`

## callees

- `0x18004510c`
- `0x18004ff54`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045231`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045231`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800451e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800451e7`
- `ntdll!EtwEventEnabled` at `0x180045156`
- `ntdll!EtwEventEnabled` at `0x180045156`
- `ntdll!EtwEventActivityIdControl` at `0x1800451f5`
- `ntdll!EtwEventActivityIdControl` at `0x180045228`
- `ntdll!EtwEventActivityIdControl` at `0x1800451f5`
- `ntdll!EtwEventActivityIdControl` at `0x180045228`
- `ntdll!EtwEventWrite` at `0x18004520f`
- `ntdll!EtwEventWrite` at `0x18004520f`

## string_xrefs

- `0x18004523e`: `EventWrite error`

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
0x18004510c  mov     [rsp-18h+arg_0], rbx
0x180045111  mov     [rsp-18h+arg_8], rsi
0x180045116  push    rbp
0x180045117  push    rdi
0x180045118  push    r14
0x18004511a  mov     rbp, rsp
0x18004511d  sub     rsp, 70h
0x180045121  mov     rax, cs:__security_cookie
0x180045128  xor     rax, rsp
0x18004512b  mov     [rbp+var_10], rax
0x18004512f  mov     rdi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180045136  xor     r14d, r14d
0x180045139  mov     rsi, r9
0x18004513c  mov     rbx, r8
0x18004513f  mov     rcx, [rdi]
0x180045142  test    rcx, rcx
0x180045145  jnz     short loc_18004514F
0x180045147  lea     eax, [rcx+1]
0x18004514a  jmp     loc_18004525D
0x18004514f  lea     rdx, RUN
0x180045156  call    cs:__imp_EtwEventEnabled
0x18004515c  test    al, al
0x18004515e  jz      loc_18004525B
0x180045164  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180045168  lea     rdx, ChannelPath
0x18004516f  test    rbx, rbx
0x180045172  jz      short loc_180045195
0x180045174  mov     [rbp+var_40], rbx
0x180045178  mov     rax, rcx
0x18004517b  inc     rax
0x18004517e  cmp     [rbx+rax*2], r14w
0x180045183  jnz     short loc_18004517B
0x180045185  lea     eax, ds:2[rax*2]
0x18004518c  mov     dword ptr [rbp+var_38+4], r14d
0x180045190  mov     dword ptr [rbp+var_38], eax
0x180045193  jmp     short loc_1800451A1
0x180045195  mov     [rbp+var_40], rdx
0x180045199  mov     [rbp+var_38], 2
0x1800451a1  mov     rax, [rbp+arg_20]
0x1800451a5  mov     [rbp+var_30], rsi
0x1800451a9  mov     [rbp+var_28], 10h
0x1800451b1  test    rax, rax
0x1800451b4  jz      short loc_1800451D4
0x1800451b6  mov     [rbp+var_20], rax
0x1800451ba  inc     rcx
0x1800451bd  cmp     [rax+rcx*2], r14w
0x1800451c2  jnz     short loc_1800451BA
0x1800451c4  lea     eax, ds:2[rcx*2]
0x1800451cb  mov     dword ptr [rbp+var_18+4], r14d
0x1800451cf  mov     dword ptr [rbp+var_18], eax
0x1800451d2  jmp     short loc_1800451E0
0x1800451d4  mov     [rbp+var_20], rdx
0x1800451d8  mov     [rbp+var_18], 2
0x1800451e0  lea     rbx, [rdi+8]
0x1800451e4  mov     rcx, rbx; lpCriticalSection
0x1800451e7  call    cs:__imp_EnterCriticalSection
0x1800451ed  mov     rdx, rsi
0x1800451f0  mov     ecx, 2
0x1800451f5  call    cs:__imp_EtwEventActivityIdControl
0x1800451fb  mov     rcx, [rdi]
0x1800451fe  lea     r9, [rbp+var_40]
0x180045202  mov     r8d, 3
0x180045208  lea     rdx, RUN
0x18004520f  call    cs:__imp_EtwEventWrite
0x180045215  lea     rdx, [rbp+var_50]
0x180045219  mov     [rbp+var_50], r14
0x18004521d  mov     ecx, 2
0x180045222  mov     [rbp+var_48], r14
0x180045226  mov     edi, eax
0x180045228  call    cs:__imp_EtwEventActivityIdControl
0x18004522e  mov     rcx, rbx; lpCriticalSection
0x180045231  call    cs:__imp_LeaveCriticalSection
0x180045237  test    edi, edi
0x180045239  jz      short loc_18004525B
0x18004523b  mov     r8d, edi; unsigned int
0x18004523e  lea     rdx, aEventwriteErro; "EventWrite error"
0x180045245  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18004524a  test    edi, edi
0x18004524c  jle     short loc_180045257
0x18004524e  movzx   edi, di
0x180045251  or      edi, 80070000h
0x180045257  mov     eax, edi
0x180045259  jmp     short loc_18004525D
0x18004525b  xor     eax, eax
0x18004525d  mov     rcx, [rbp+var_10]
0x180045261  xor     rcx, rsp; StackCookie
0x180045264  call    __security_check_cookie
0x180045269  lea     r11, [rsp+70h+var_s0]
0x18004526e  mov     rbx, [r11+20h]
0x180045272  mov     rsi, [r11+28h]
0x180045276  mov     rsp, r11
0x180045279  pop     r14
0x18004527b  pop     rdi
0x18004527c  pop     rbp
0x18004527d  retn
```
