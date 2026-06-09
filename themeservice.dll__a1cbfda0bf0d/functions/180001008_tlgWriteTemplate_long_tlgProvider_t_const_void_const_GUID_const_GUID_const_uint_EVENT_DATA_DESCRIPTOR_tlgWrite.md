# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001008`
- end: `0x1800012da`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U1@U?$_tlgWrapSz@D@@U2@U3@U3@U3@U2@U3@U3@U3@U3@U1@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@3AEBU?$_tlgWrapSz@D@@455545555353@Z`
- size: `722`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, __int64, _QWORD *, _QWORD *, _QWORD *, __int64, _QWORD *, _QWORD *, _QWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e270`

## callees

- `0x180001008`
- `0x180001ba8`
- `0x18000fa00`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        _QWORD *a10,
        __int64 a11,
        _QWORD *a12,
        _QWORD *a13,
        _QWORD *a14,
        __int64 a15,
        _QWORD *a16,
        _QWORD *a17,
        _QWORD *a18,
        _QWORD *a19,
        __int64 a20,
        _QWORD *a21)
{
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax

  v22 = -1;
  if ( *a21 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_BYTE *)(*a21 + v23) );
  }
  if ( *a19 )
  {
    v24 = -1;
    do
      ++v24;
    while ( *(_BYTE *)(*a19 + v24) );
  }
  if ( *a18 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_BYTE *)(*a18 + v25) );
  }
  if ( *a17 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(*a17 + v26) );
  }
  if ( *a16 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *(_BYTE *)(*a16 + v27) );
  }
  if ( *a14 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *(_BYTE *)(*a14 + v28) );
  }
  if ( *a13 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *(_BYTE *)(*a13 + v29) );
  }
  if ( *a12 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *(_BYTE *)(*a12 + v30) );
  }
  if ( *a10 )
  {
    do
      ++v22;
    while ( *(_BYTE *)(*a10 + v22) );
  }
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x180001008  mov     [rsp-8+arg_10], rbx
0x18000100d  mov     [rsp-8+arg_18], rsi
0x180001012  push    rbp
0x180001013  lea     rbp, [rsp-80h]
0x180001018  sub     rsp, 180h
0x18000101f  mov     rax, cs:__security_cookie
0x180001026  xor     rax, rsp
0x180001029  mov     [rbp+80h+var_10], rax
0x18000102d  mov     rax, [rbp+80h+arg_A8]
0x180001034  lea     rbx, byte_180011FBB
0x18000103b  xor     r9d, r9d
0x18000103e  mov     [rbp+80h+var_20], rax
0x180001042  mov     rax, [rbp+80h+arg_A0]
0x180001049  mov     r10, rcx
0x18000104c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001050  mov     [rbp+80h+var_18], 4
0x180001058  mov     r11, rdx
0x18000105b  lea     edx, [r9+1]
0x18000105f  mov     r8, [rax]
0x180001062  test    r8, r8
0x180001065  jz      short loc_180001077
0x180001067  mov     rax, rcx
0x18000106a  inc     rax
0x18000106d  cmp     [r8+rax], r9b
0x180001071  jnz     short loc_18000106A
0x180001073  inc     eax
0x180001075  jmp     short loc_18000107C
0x180001077  mov     r8, rbx
0x18000107a  mov     eax, edx
0x18000107c  mov     [rbp+80h+var_28], eax
0x18000107f  mov     rax, [rbp+80h+arg_98]
0x180001086  mov     [rbp+80h+var_40], rax
0x18000108a  mov     rax, [rbp+80h+arg_90]
0x180001091  mov     [rbp+80h+var_30], r8
0x180001095  mov     [rbp+80h+var_24], r9d
0x180001099  mov     [rbp+80h+var_38], 4
0x1800010a1  mov     r8, [rax]
0x1800010a4  test    r8, r8
0x1800010a7  jz      short loc_1800010B9
0x1800010a9  mov     rax, rcx
0x1800010ac  inc     rax
0x1800010af  cmp     [r8+rax], r9b
0x1800010b3  jnz     short loc_1800010AC
0x1800010b5  inc     eax
0x1800010b7  jmp     short loc_1800010BE
0x1800010b9  mov     r8, rbx
0x1800010bc  mov     eax, edx
0x1800010be  mov     [rbp+80h+var_48], eax
0x1800010c1  mov     rax, [rbp+80h+arg_88]
0x1800010c8  mov     [rbp+80h+var_50], r8
0x1800010cc  mov     [rbp+80h+var_44], r9d
0x1800010d0  mov     r8, [rax]
0x1800010d3  test    r8, r8
0x1800010d6  jz      short loc_1800010E8
0x1800010d8  mov     rax, rcx
0x1800010db  inc     rax
0x1800010de  cmp     [r8+rax], r9b
0x1800010e2  jnz     short loc_1800010DB
0x1800010e4  inc     eax
0x1800010e6  jmp     short loc_1800010ED
0x1800010e8  mov     r8, rbx
0x1800010eb  mov     eax, edx
0x1800010ed  mov     [rbp+80h+var_58], eax
0x1800010f0  mov     rax, [rbp+80h+arg_80]
0x1800010f7  mov     [rbp+80h+var_60], r8
0x1800010fb  mov     [rbp+80h+var_54], r9d
0x1800010ff  mov     r8, [rax]
0x180001102  test    r8, r8
0x180001105  jz      short loc_180001117
0x180001107  mov     rax, rcx
0x18000110a  inc     rax
0x18000110d  cmp     [r8+rax], r9b
0x180001111  jnz     short loc_18000110A
0x180001113  inc     eax
0x180001115  jmp     short loc_18000111C
0x180001117  mov     r8, rbx
0x18000111a  mov     eax, edx
0x18000111c  mov     [rbp+80h+var_68], eax
0x18000111f  mov     rax, [rbp+80h+arg_78]
0x180001126  mov     [rbp+80h+var_70], r8
0x18000112a  mov     [rbp+80h+var_64], r9d
0x18000112e  mov     r8, [rax]
0x180001131  test    r8, r8
0x180001134  jz      short loc_180001146
0x180001136  mov     rax, rcx
0x180001139  inc     rax
0x18000113c  cmp     [r8+rax], r9b
0x180001140  jnz     short loc_180001139
0x180001142  inc     eax
0x180001144  jmp     short loc_18000114B
0x180001146  mov     r8, rbx
0x180001149  mov     eax, edx
0x18000114b  mov     [rbp+80h+var_78], eax
0x18000114e  mov     rax, [rbp+80h+arg_70]
0x180001155  mov     [rbp+80h+var_90], rax
0x180001159  mov     rax, [rbp+80h+arg_68]
0x180001160  mov     [rbp+80h+var_80], r8
0x180001164  mov     [rbp+80h+var_74], r9d
0x180001168  mov     [rbp+80h+var_88], 2
0x180001170  mov     r8, [rax]
0x180001173  test    r8, r8
0x180001176  jz      short loc_180001188
0x180001178  mov     rax, rcx
0x18000117b  inc     rax
0x18000117e  cmp     [r8+rax], r9b
0x180001182  jnz     short loc_18000117B
0x180001184  inc     eax
0x180001186  jmp     short loc_18000118D
0x180001188  mov     r8, rbx
0x18000118b  mov     eax, edx
0x18000118d  mov     [rbp+80h+var_98], eax
0x180001190  mov     rax, [rbp+80h+arg_60]
0x180001197  mov     [rbp+80h+var_A0], r8
0x18000119b  mov     [rbp+80h+var_94], r9d
0x18000119f  mov     r8, [rax]
0x1800011a2  test    r8, r8
0x1800011a5  jz      short loc_1800011B7
0x1800011a7  mov     rax, rcx
0x1800011aa  inc     rax
0x1800011ad  cmp     [r8+rax], r9b
0x1800011b1  jnz     short loc_1800011AA
0x1800011b3  inc     eax
0x1800011b5  jmp     short loc_1800011BC
0x1800011b7  mov     r8, rbx
0x1800011ba  mov     eax, edx
0x1800011bc  mov     [rbp+80h+var_A8], eax
0x1800011bf  mov     rax, [rbp+80h+arg_58]
0x1800011c6  mov     [rbp+80h+var_B0], r8
0x1800011ca  mov     [rbp+80h+var_A4], r9d
0x1800011ce  mov     r8, [rax]
0x1800011d1  test    r8, r8
0x1800011d4  jz      short loc_1800011E6
0x1800011d6  mov     rax, rcx
0x1800011d9  inc     rax
0x1800011dc  cmp     [r8+rax], r9b
0x1800011e0  jnz     short loc_1800011D9
0x1800011e2  inc     eax
0x1800011e4  jmp     short loc_1800011EB
0x1800011e6  mov     r8, rbx
0x1800011e9  mov     eax, edx
0x1800011eb  mov     [rbp+80h+var_B8], eax
0x1800011ee  mov     rax, [rbp+80h+arg_50]
0x1800011f5  mov     [rbp+80h+var_D0], rax
0x1800011f9  mov     rax, [rbp+80h+arg_48]
0x180001200  mov     [rbp+80h+var_C0], r8
0x180001204  mov     [rbp+80h+var_B4], r9d
0x180001208  mov     [rbp+80h+var_C8], 2
0x180001210  mov     r8, [rax]
0x180001213  test    r8, r8
0x180001216  jz      short loc_180001226
0x180001218  inc     rcx
0x18000121b  cmp     [r8+rcx], r9b
0x18000121f  jnz     short loc_180001218
0x180001221  lea     edx, [rcx+1]
0x180001224  jmp     short loc_180001229
0x180001226  mov     r8, rbx
0x180001229  mov     rax, [rbp+80h+arg_40]
0x180001230  mov     rcx, r10
0x180001233  mov     [rbp+80h+var_F0], rax
0x180001237  mov     rax, [rbp+80h+arg_38]
0x18000123e  mov     [rbp+80h+var_100], rax
0x180001242  mov     rax, [rbp+80h+arg_30]
0x180001249  mov     [rsp+180h+var_110], rax
0x18000124e  mov     rax, [rbp+80h+arg_28]
0x180001255  mov     [rsp+180h+var_120], rax
0x18000125a  mov     rax, [rbp+80h+arg_20]
0x180001261  mov     [rsp+180h+var_130], rax
0x180001266  lea     rax, [rsp+180h+var_150]
0x18000126b  mov     [rbp+80h+var_E0], r8
0x18000126f  xor     r8d, r8d
0x180001272  mov     [rbp+80h+var_D8], edx
0x180001275  mov     rdx, r11
0x180001278  mov     [rsp+180h+var_158], rax
0x18000127d  mov     [rsp+180h+var_160], 14h
0x180001285  mov     [rbp+80h+var_D4], r9d
0x180001289  mov     [rbp+80h+var_E8], 4
0x180001291  mov     [rbp+80h+var_F8], 2
0x180001299  mov     [rsp+180h+var_108], 4
0x1800012a2  mov     [rsp+180h+var_118], 4
0x1800012ab  mov     [rsp+180h+var_128], 4
0x1800012b4  call    _tlgWriteTransfer_EventWriteTransfer
0x1800012b9  mov     rcx, [rbp+80h+var_10]
0x1800012bd  xor     rcx, rsp; StackCookie
0x1800012c0  call    __security_check_cookie
0x1800012c5  lea     r11, [rsp+180h+var_s0]
0x1800012cd  mov     rbx, [r11+20h]
0x1800012d1  mov     rsi, [r11+28h]
0x1800012d5  mov     rsp, r11
0x1800012d8  pop     rbp
0x1800012d9  retn
```
