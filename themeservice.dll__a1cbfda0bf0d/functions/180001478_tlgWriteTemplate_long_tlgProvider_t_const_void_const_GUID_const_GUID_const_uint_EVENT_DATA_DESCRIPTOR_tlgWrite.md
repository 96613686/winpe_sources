# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001478`
- end: `0x180001723`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e798`

## callees

- `0x180001478`
- `0x180001ba8`
- `0x18000fa00`

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
0x180001478  mov     [rsp-8+arg_10], rbx
0x18000147d  push    rbp
0x18000147e  push    rsi
0x18000147f  push    rdi
0x180001480  lea     rbp, [rsp-60h]
0x180001485  sub     rsp, 160h
0x18000148c  mov     rax, cs:__security_cookie
0x180001493  xor     rax, rsp
0x180001496  mov     [rbp+70h+var_20], rax
0x18000149a  mov     rax, [rbp+70h+arg_98]
0x1800014a1  mov     r11, rdx
0x1800014a4  mov     r10, rcx
0x1800014a7  xor     ebx, ebx
0x1800014a9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800014ad  mov     r9d, 2
0x1800014b3  mov     rdx, [rax]
0x1800014b6  test    rdx, rdx
0x1800014b9  jz      short loc_1800014D0
0x1800014bb  mov     rax, rcx
0x1800014be  inc     rax
0x1800014c1  cmp     [rdx+rax*2], bx
0x1800014c5  jnz     short loc_1800014BE
0x1800014c7  lea     eax, ds:2[rax*2]
0x1800014ce  jmp     short loc_1800014DA
0x1800014d0  lea     rdx, qword_1800125E0
0x1800014d7  mov     eax, r9d
0x1800014da  mov     [rbp+70h+var_28], eax
0x1800014dd  lea     rdi, byte_180011FBB
0x1800014e4  mov     rax, [rbp+70h+arg_90]
0x1800014eb  mov     r8d, 1
0x1800014f1  mov     [rbp+70h+var_30], rdx
0x1800014f5  mov     [rbp+70h+var_24], ebx
0x1800014f8  mov     rdx, [rax]
0x1800014fb  test    rdx, rdx
0x1800014fe  jz      short loc_18000150F
0x180001500  mov     rax, rcx
0x180001503  inc     rax
0x180001506  cmp     [rdx+rax], bl
0x180001509  jnz     short loc_180001503
0x18000150b  inc     eax
0x18000150d  jmp     short loc_180001515
0x18000150f  mov     rdx, rdi
0x180001512  mov     eax, r8d
0x180001515  mov     [rbp+70h+var_38], eax
0x180001518  mov     rax, [rbp+70h+arg_88]
0x18000151f  mov     [rbp+70h+var_50], rax
0x180001523  mov     rax, [rbp+70h+arg_80]
0x18000152a  mov     [rbp+70h+var_40], rdx
0x18000152e  mov     [rbp+70h+var_34], ebx
0x180001531  mov     [rbp+70h+var_48], 4
0x180001539  mov     rdx, [rax]
0x18000153c  test    rdx, rdx
0x18000153f  jz      short loc_180001556
0x180001541  mov     rax, rcx
0x180001544  inc     rax
0x180001547  cmp     [rdx+rax*2], bx
0x18000154b  jnz     short loc_180001544
0x18000154d  lea     eax, ds:2[rax*2]
0x180001554  jmp     short loc_180001560
0x180001556  lea     rdx, qword_1800125E0
0x18000155d  mov     eax, r9d
0x180001560  mov     [rbp+70h+var_58], eax
0x180001563  mov     rax, [rbp+70h+arg_78]
0x18000156a  mov     [rbp+70h+var_60], rdx
0x18000156e  mov     [rbp+70h+var_54], ebx
0x180001571  mov     rdx, [rax]
0x180001574  test    rdx, rdx
0x180001577  jz      short loc_180001588
0x180001579  mov     rax, rcx
0x18000157c  inc     rax
0x18000157f  cmp     [rdx+rax], bl
0x180001582  jnz     short loc_18000157C
0x180001584  inc     eax
0x180001586  jmp     short loc_18000158E
0x180001588  mov     rdx, rdi
0x18000158b  mov     eax, r8d
0x18000158e  mov     [rbp+70h+var_68], eax
0x180001591  mov     rax, [rbp+70h+arg_70]
0x180001598  mov     [rbp+70h+var_80], rax
0x18000159c  mov     rax, [rbp+70h+arg_68]
0x1800015a3  mov     [rbp+70h+var_70], rdx
0x1800015a7  mov     [rbp+70h+var_64], ebx
0x1800015aa  mov     [rbp+70h+var_78], 4
0x1800015b2  mov     rdx, [rax]
0x1800015b5  test    rdx, rdx
0x1800015b8  jz      short loc_1800015C9
0x1800015ba  mov     rax, rcx
0x1800015bd  inc     rax
0x1800015c0  cmp     [rdx+rax], bl
0x1800015c3  jnz     short loc_1800015BD
0x1800015c5  inc     eax
0x1800015c7  jmp     short loc_1800015CF
0x1800015c9  mov     rdx, rdi
0x1800015cc  mov     eax, r8d
0x1800015cf  mov     [rbp+70h+var_88], eax
0x1800015d2  mov     rax, [rbp+70h+arg_60]
0x1800015d9  mov     [rbp+70h+var_A0], rax
0x1800015dd  mov     rax, [rbp+70h+arg_58]
0x1800015e4  mov     [rbp+70h+var_90], rdx
0x1800015e8  mov     [rbp+70h+var_84], ebx
0x1800015eb  mov     [rbp+70h+var_98], 4
0x1800015f3  mov     rdx, [rax]
0x1800015f6  test    rdx, rdx
0x1800015f9  jz      short loc_180001611
0x1800015fb  mov     rax, rcx
0x1800015fe  inc     rax
0x180001601  cmp     [rdx+rax*2], bx
0x180001605  jnz     short loc_1800015FE
0x180001607  lea     r9d, ds:2[rax*2]
0x18000160f  jmp     short loc_180001618
0x180001611  lea     rdx, qword_1800125E0
0x180001618  mov     rax, [rbp+70h+arg_50]
0x18000161f  mov     [rbp+70h+var_C0], rax
0x180001623  mov     rax, [rbp+70h+arg_48]
0x18000162a  mov     [rbp+70h+var_B0], rdx
0x18000162e  mov     [rbp+70h+var_A8], r9d
0x180001632  mov     [rbp+70h+var_A4], ebx
0x180001635  mov     rdx, [rax]
0x180001638  mov     [rbp+70h+var_B8], 4
0x180001640  test    rdx, rdx
0x180001643  jz      short loc_180001654
0x180001645  mov     rax, rcx
0x180001648  inc     rax
0x18000164b  cmp     [rdx+rax], bl
0x18000164e  jnz     short loc_180001648
0x180001650  inc     eax
0x180001652  jmp     short loc_18000165A
0x180001654  mov     rdx, rdi
0x180001657  mov     eax, r8d
0x18000165a  mov     [rbp+70h+var_C8], eax
0x18000165d  mov     rax, [rbp+70h+arg_40]
0x180001664  mov     [rbp+70h+var_E0], rax
0x180001668  mov     rax, [rbp+70h+arg_38]
0x18000166f  mov     [rbp+70h+var_D0], rdx
0x180001673  mov     [rbp+70h+var_C4], ebx
0x180001676  mov     [rbp+70h+var_D8], 4
0x18000167e  mov     rdx, [rax]
0x180001681  test    rdx, rdx
0x180001684  jz      short loc_180001694
0x180001686  inc     rcx
0x180001689  cmp     [rdx+rcx], bl
0x18000168c  jnz     short loc_180001686
0x18000168e  lea     r8d, [rcx+1]
0x180001692  jmp     short loc_180001697
0x180001694  mov     rdx, rdi
0x180001697  mov     rax, [rbp+70h+arg_30]
0x18000169e  xor     r9d, r9d
0x1800016a1  mov     [rsp+170h+var_100], rax
0x1800016a6  mov     rcx, r10
0x1800016a9  mov     rax, [rbp+70h+arg_28]
0x1800016b0  mov     [rsp+170h+var_110], rax
0x1800016b5  mov     rax, [rbp+70h+arg_20]
0x1800016bc  mov     [rsp+170h+var_120], rax
0x1800016c1  lea     rax, [rsp+170h+var_140]
0x1800016c6  mov     [rbp+70h+var_F0], rdx
0x1800016ca  mov     rdx, r11
0x1800016cd  mov     [rbp+70h+var_E8], r8d
0x1800016d1  xor     r8d, r8d
0x1800016d4  mov     [rsp+170h+var_148], rax
0x1800016d9  mov     [rsp+170h+var_150], 12h
0x1800016e1  mov     [rbp+70h+var_E4], ebx
0x1800016e4  mov     [rsp+170h+var_F8], 4
0x1800016ed  mov     [rsp+170h+var_108], 8
0x1800016f6  mov     [rsp+170h+var_118], 8
0x1800016ff  call    _tlgWriteTransfer_EventWriteTransfer
0x180001704  mov     rcx, [rbp+70h+var_20]
0x180001708  xor     rcx, rsp; StackCookie
0x18000170b  call    __security_check_cookie
0x180001710  mov     rbx, [rsp+170h+arg_10]
0x180001718  add     rsp, 160h
0x18000171f  pop     rdi
0x180001720  pop     rsi
0x180001721  pop     rbp
0x180001722  retn
```
