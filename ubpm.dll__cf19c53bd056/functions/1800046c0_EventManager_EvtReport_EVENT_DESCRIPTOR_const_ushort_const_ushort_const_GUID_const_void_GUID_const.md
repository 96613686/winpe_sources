# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,_GUID const *,void *,_GUID const *)

- ea: `0x1800046c0`
- end: `0x180004853`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1PEBU_GUID@@PEAX2@Z`
- size: `403`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void *, const struct _GUID *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800057b0`
- `0x180006650`
- `0x18000c650`

## callees

- `0x1800046c0`
- `0x1800207e8`
- `0x18003d810`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18000479a`
- `ntdll!EtwEventActivityIdControl` at `0x1800047d1`
- `ntdll!EtwEventActivityIdControl` at `0x18000479a`
- `ntdll!EtwEventActivityIdControl` at `0x1800047d1`
- `ntdll!EtwEventWrite` at `0x1800047b0`
- `ntdll!EtwEventWrite` at `0x1800047b0`
- `ntdll!EtwEventEnabled` at `0x1800046fd`
- `ntdll!EtwEventEnabled` at `0x1800046fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000478c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000478c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800047da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800047da`

## string_xrefs

- `0x180004810`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        const struct _GUID *a5)
{
  __int64 v6; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  bool v12; // zf
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  signed int v14; // eax
  signed int v15; // esi
  EventManager *v16; // rcx
  _QWORD v18[2]; // [rsp+20h] [rbp-50h] BYREF
  int *v19; // [rsp+30h] [rbp-40h] BYREF
  __int64 v20; // [rsp+38h] [rbp-38h]
  int *v21; // [rsp+40h] [rbp-30h]
  __int64 v22; // [rsp+48h] [rbp-28h]
  const struct _GUID *v23; // [rsp+50h] [rbp-20h]
  __int64 v24; // [rsp+58h] [rbp-18h]

  v6 = *(_QWORD *)this;
  if ( !v6 )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(v6, a2) )
    return 0;
  v10 = -1;
  if ( a3 )
  {
    v19 = (int *)a3;
    v11 = -1;
    do
      v12 = a3[++v11] == 0;
    while ( !v12 );
    v20 = (unsigned int)(2 * v11 + 2);
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
      v12 = a4[++v10] == 0;
    while ( !v12 );
    v22 = (unsigned int)(2 * v10 + 2);
  }
  else
  {
    v21 = &dword_1800405F4;
    v22 = 2;
  }
  v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v23 = a5;
  v24 = 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  EtwEventActivityIdControl(2, a5);
  v14 = EtwEventWrite(*(_QWORD *)this, a2, 3, &v19);
  v18[0] = 0;
  v18[1] = 0;
  v15 = v14;
  EtwEventActivityIdControl(2, v18);
  LeaveCriticalSection(v13);
  if ( !v15 )
    return 0;
  EventManager::LogIt(v16, L"EventWrite error", v15);
  if ( v15 > 0 )
    return (unsigned __int16)v15 | 0x80070000;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800046c0  mov     [rsp-28h+arg_10], rbx
0x1800046c5  push    rbp
0x1800046c6  push    rsi
0x1800046c7  push    rdi
0x1800046c8  push    r14
0x1800046ca  push    r15
0x1800046cc  mov     rbp, rsp
0x1800046cf  sub     rsp, 70h
0x1800046d3  mov     rax, cs:__security_cookie
0x1800046da  xor     rax, rsp
0x1800046dd  mov     [rbp+var_10], rax
0x1800046e1  mov     r15, [rbp+arg_20]
0x1800046e5  mov     rsi, rcx
0x1800046e8  mov     rcx, [rcx]
0x1800046eb  mov     rbx, r9
0x1800046ee  mov     rdi, r8
0x1800046f1  mov     r14, rdx
0x1800046f4  test    rcx, rcx
0x1800046f7  jz      loc_180004806
0x1800046fd  call    cs:__imp_EtwEventEnabled
0x180004703  test    al, al
0x180004705  jz      loc_1800047E4
0x18000470b  lea     rdx, dword_1800405F4
0x180004712  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004719  test    rdi, rdi
0x18000471c  jz      loc_18000482F
0x180004722  mov     [rbp+var_40], rdi
0x180004726  mov     rcx, rax
0x180004729  nop     dword ptr [rax+00000000h]
0x180004730  cmp     word ptr [rdi+rcx*2+2], 0
0x180004736  lea     rcx, [rcx+1]
0x18000473a  jnz     short loc_180004730
0x18000473c  lea     ecx, ds:2[rcx*2]
0x180004743  xor     edi, edi
0x180004745  mov     dword ptr [rbp+var_38], ecx
0x180004748  mov     dword ptr [rbp+var_38+4], edi
0x18000474b  test    rbx, rbx
0x18000474e  jz      loc_180004842
0x180004754  mov     [rbp+var_30], rbx
0x180004758  nop     dword ptr [rax+rax+00000000h]
0x180004760  cmp     word ptr [rbx+rax*2+2], 0
0x180004766  lea     rax, [rax+1]
0x18000476a  jnz     short loc_180004760
0x18000476c  lea     eax, ds:2[rax*2]
0x180004773  mov     dword ptr [rbp+var_28+4], edi
0x180004776  mov     dword ptr [rbp+var_28], eax
0x180004779  lea     rbx, [rsi+8]
0x18000477d  mov     [rbp+var_20], r15
0x180004781  mov     rcx, rbx; lpCriticalSection
0x180004784  mov     [rbp+var_18], 10h
0x18000478c  call    cs:__imp_EnterCriticalSection
0x180004792  mov     rdx, r15
0x180004795  mov     ecx, 2
0x18000479a  call    cs:__imp_EtwEventActivityIdControl
0x1800047a0  mov     rcx, [rsi]
0x1800047a3  lea     r9, [rbp+var_40]
0x1800047a7  mov     r8d, 3
0x1800047ad  mov     rdx, r14
0x1800047b0  call    cs:__imp_EtwEventWrite
0x1800047b6  lea     rdx, [rbp+var_50]
0x1800047ba  mov     [rbp+var_50], 0
0x1800047c2  mov     ecx, 2
0x1800047c7  mov     [rbp+var_48], 0
0x1800047cf  mov     esi, eax
0x1800047d1  call    cs:__imp_EtwEventActivityIdControl
0x1800047d7  mov     rcx, rbx; lpCriticalSection
0x1800047da  call    cs:__imp_LeaveCriticalSection
0x1800047e0  test    esi, esi
0x1800047e2  jnz     short loc_18000480D
0x1800047e4  xor     eax, eax
0x1800047e6  mov     rcx, [rbp+var_10]
0x1800047ea  xor     rcx, rsp; StackCookie
0x1800047ed  call    __security_check_cookie
0x1800047f2  mov     rbx, [rsp+70h+arg_10]
0x1800047fa  add     rsp, 70h
0x1800047fe  pop     r15
0x180004800  pop     r14
0x180004802  pop     rdi
0x180004803  pop     rsi
0x180004804  pop     rbp
0x180004805  retn
0x180004806  mov     eax, 1
0x18000480b  jmp     short loc_1800047E6
0x18000480d  mov     r8d, esi; unsigned int
0x180004810  lea     rdx, aEventwriteErro; "EventWrite error"
0x180004817  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18000481c  test    esi, esi
0x18000481e  jg      short loc_180004824
0x180004820  mov     eax, esi
0x180004822  jmp     short loc_1800047E6
0x180004824  movzx   esi, si
0x180004827  or      esi, 80070000h
0x18000482d  jmp     short loc_180004820
0x18000482f  mov     [rbp+var_40], rdx
0x180004833  xor     edi, edi
0x180004835  mov     [rbp+var_38], 2
0x18000483d  jmp     loc_18000474B
0x180004842  mov     [rbp+var_30], rdx
0x180004846  mov     [rbp+var_28], 2
0x18000484e  jmp     loc_180004779
```
