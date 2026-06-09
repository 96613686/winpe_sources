# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800013a4`
- end: `0x18000164f`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d4fc`

## callees

- `0x1800013a4`
- `0x1800019cc`
- `0x1800026d0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8,
        __int64 a9,
        _QWORD *a10,
        __int64 a11,
        _QWORD *a12,
        __int64 a13,
        _QWORD *a14,
        __int64 a15,
        _QWORD *a16,
        _QWORD *a17,
        __int64 a18,
        _QWORD *a19,
        _QWORD *a20)
{
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax

  v21 = -1;
  if ( *a20 )
  {
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(*a20 + 2 * v22) );
  }
  if ( *a19 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_BYTE *)(*a19 + v23) );
  }
  if ( *a17 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)(*a17 + 2 * v24) );
  }
  if ( *a16 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_BYTE *)(*a16 + v25) );
  }
  if ( *a14 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(*a14 + v26) );
  }
  if ( *a12 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(*a12 + 2 * v27) );
  }
  if ( *a10 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *(_BYTE *)(*a10 + v28) );
  }
  if ( *a8 )
  {
    do
      ++v21;
    while ( *(_BYTE *)(*a8 + v21) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x1800013a4  mov     [rsp-8+arg_10], rbx
0x1800013a9  push    rbp
0x1800013aa  push    rsi
0x1800013ab  push    rdi
0x1800013ac  lea     rbp, [rsp-60h]
0x1800013b1  sub     rsp, 160h
0x1800013b8  mov     rax, cs:__security_cookie
0x1800013bf  xor     rax, rsp
0x1800013c2  mov     [rbp+70h+var_20], rax
0x1800013c6  mov     rax, [rbp+70h+arg_98]
0x1800013cd  mov     r11, rdx
0x1800013d0  mov     r10, rcx
0x1800013d3  xor     ebx, ebx
0x1800013d5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800013d9  mov     r9d, 2
0x1800013df  mov     rdx, [rax]
0x1800013e2  test    rdx, rdx
0x1800013e5  jz      short loc_1800013FC
0x1800013e7  mov     rax, rcx
0x1800013ea  inc     rax
0x1800013ed  cmp     [rdx+rax*2], bx
0x1800013f1  jnz     short loc_1800013EA
0x1800013f3  lea     eax, ds:2[rax*2]
0x1800013fa  jmp     short loc_180001406
0x1800013fc  lea     rdx, qword_180011258
0x180001403  mov     eax, r9d
0x180001406  mov     [rbp+70h+var_28], eax
0x180001409  lea     rdi, word_180010AD2
0x180001410  mov     rax, [rbp+70h+arg_90]
0x180001417  mov     r8d, 1
0x18000141d  mov     [rbp+70h+var_30], rdx
0x180001421  mov     [rbp+70h+var_24], ebx
0x180001424  mov     rdx, [rax]
0x180001427  test    rdx, rdx
0x18000142a  jz      short loc_18000143B
0x18000142c  mov     rax, rcx
0x18000142f  inc     rax
0x180001432  cmp     [rdx+rax], bl
0x180001435  jnz     short loc_18000142F
0x180001437  inc     eax
0x180001439  jmp     short loc_180001441
0x18000143b  mov     rdx, rdi
0x18000143e  mov     eax, r8d
0x180001441  mov     [rbp+70h+var_38], eax
0x180001444  mov     rax, [rbp+70h+arg_88]
0x18000144b  mov     [rbp+70h+var_50], rax
0x18000144f  mov     rax, [rbp+70h+arg_80]
0x180001456  mov     [rbp+70h+var_40], rdx
0x18000145a  mov     [rbp+70h+var_34], ebx
0x18000145d  mov     [rbp+70h+var_48], 4
0x180001465  mov     rdx, [rax]
0x180001468  test    rdx, rdx
0x18000146b  jz      short loc_180001482
0x18000146d  mov     rax, rcx
0x180001470  inc     rax
0x180001473  cmp     [rdx+rax*2], bx
0x180001477  jnz     short loc_180001470
0x180001479  lea     eax, ds:2[rax*2]
0x180001480  jmp     short loc_18000148C
0x180001482  lea     rdx, qword_180011258
0x180001489  mov     eax, r9d
0x18000148c  mov     [rbp+70h+var_58], eax
0x18000148f  mov     rax, [rbp+70h+arg_78]
0x180001496  mov     [rbp+70h+var_60], rdx
0x18000149a  mov     [rbp+70h+var_54], ebx
0x18000149d  mov     rdx, [rax]
0x1800014a0  test    rdx, rdx
0x1800014a3  jz      short loc_1800014B4
0x1800014a5  mov     rax, rcx
0x1800014a8  inc     rax
0x1800014ab  cmp     [rdx+rax], bl
0x1800014ae  jnz     short loc_1800014A8
0x1800014b0  inc     eax
0x1800014b2  jmp     short loc_1800014BA
0x1800014b4  mov     rdx, rdi
0x1800014b7  mov     eax, r8d
0x1800014ba  mov     [rbp+70h+var_68], eax
0x1800014bd  mov     rax, [rbp+70h+arg_70]
0x1800014c4  mov     [rbp+70h+var_80], rax
0x1800014c8  mov     rax, [rbp+70h+arg_68]
0x1800014cf  mov     [rbp+70h+var_70], rdx
0x1800014d3  mov     [rbp+70h+var_64], ebx
0x1800014d6  mov     [rbp+70h+var_78], 4
0x1800014de  mov     rdx, [rax]
0x1800014e1  test    rdx, rdx
0x1800014e4  jz      short loc_1800014F5
0x1800014e6  mov     rax, rcx
0x1800014e9  inc     rax
0x1800014ec  cmp     [rdx+rax], bl
0x1800014ef  jnz     short loc_1800014E9
0x1800014f1  inc     eax
0x1800014f3  jmp     short loc_1800014FB
0x1800014f5  mov     rdx, rdi
0x1800014f8  mov     eax, r8d
0x1800014fb  mov     [rbp+70h+var_88], eax
0x1800014fe  mov     rax, [rbp+70h+arg_60]
0x180001505  mov     [rbp+70h+var_A0], rax
0x180001509  mov     rax, [rbp+70h+arg_58]
0x180001510  mov     [rbp+70h+var_90], rdx
0x180001514  mov     [rbp+70h+var_84], ebx
0x180001517  mov     [rbp+70h+var_98], 4
0x18000151f  mov     rdx, [rax]
0x180001522  test    rdx, rdx
0x180001525  jz      short loc_18000153D
0x180001527  mov     rax, rcx
0x18000152a  inc     rax
0x18000152d  cmp     [rdx+rax*2], bx
0x180001531  jnz     short loc_18000152A
0x180001533  lea     r9d, ds:2[rax*2]
0x18000153b  jmp     short loc_180001544
0x18000153d  lea     rdx, qword_180011258
0x180001544  mov     rax, [rbp+70h+arg_50]
0x18000154b  mov     [rbp+70h+var_C0], rax
0x18000154f  mov     rax, [rbp+70h+arg_48]
0x180001556  mov     [rbp+70h+var_B0], rdx
0x18000155a  mov     [rbp+70h+var_A8], r9d
0x18000155e  mov     [rbp+70h+var_A4], ebx
0x180001561  mov     rdx, [rax]
0x180001564  mov     [rbp+70h+var_B8], 4
0x18000156c  test    rdx, rdx
0x18000156f  jz      short loc_180001580
0x180001571  mov     rax, rcx
0x180001574  inc     rax
0x180001577  cmp     [rdx+rax], bl
0x18000157a  jnz     short loc_180001574
0x18000157c  inc     eax
0x18000157e  jmp     short loc_180001586
0x180001580  mov     rdx, rdi
0x180001583  mov     eax, r8d
0x180001586  mov     [rbp+70h+var_C8], eax
0x180001589  mov     rax, [rbp+70h+arg_40]
0x180001590  mov     [rbp+70h+var_E0], rax
0x180001594  mov     rax, [rbp+70h+arg_38]
0x18000159b  mov     [rbp+70h+var_D0], rdx
0x18000159f  mov     [rbp+70h+var_C4], ebx
0x1800015a2  mov     [rbp+70h+var_D8], 4
0x1800015aa  mov     rdx, [rax]
0x1800015ad  test    rdx, rdx
0x1800015b0  jz      short loc_1800015C0
0x1800015b2  inc     rcx
0x1800015b5  cmp     [rdx+rcx], bl
0x1800015b8  jnz     short loc_1800015B2
0x1800015ba  lea     r8d, [rcx+1]
0x1800015be  jmp     short loc_1800015C3
0x1800015c0  mov     rdx, rdi
0x1800015c3  mov     rax, [rbp+70h+arg_30]
0x1800015ca  xor     r9d, r9d
0x1800015cd  mov     [rsp+170h+var_100], rax
0x1800015d2  mov     rcx, r10
0x1800015d5  mov     rax, [rbp+70h+arg_28]
0x1800015dc  mov     [rsp+170h+var_110], rax
0x1800015e1  mov     rax, [rbp+70h+arg_20]
0x1800015e8  mov     [rsp+170h+var_120], rax
0x1800015ed  lea     rax, [rsp+170h+var_140]
0x1800015f2  mov     [rbp+70h+var_F0], rdx
0x1800015f6  mov     rdx, r11
0x1800015f9  mov     [rbp+70h+var_E8], r8d
0x1800015fd  xor     r8d, r8d
0x180001600  mov     [rsp+170h+var_148], rax
0x180001605  mov     [rsp+170h+var_150], 12h
0x18000160d  mov     [rbp+70h+var_E4], ebx
0x180001610  mov     [rsp+170h+var_F8], 4
0x180001619  mov     [rsp+170h+var_108], 8
0x180001622  mov     [rsp+170h+var_118], 8
0x18000162b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001630  mov     rcx, [rbp+70h+var_20]
0x180001634  xor     rcx, rsp; StackCookie
0x180001637  call    __security_check_cookie
0x18000163c  mov     rbx, [rsp+170h+arg_10]
0x180001644  add     rsp, 160h
0x18000164b  pop     rdi
0x18000164c  pop     rsi
0x18000164d  pop     rbp
0x18000164e  retn
```
