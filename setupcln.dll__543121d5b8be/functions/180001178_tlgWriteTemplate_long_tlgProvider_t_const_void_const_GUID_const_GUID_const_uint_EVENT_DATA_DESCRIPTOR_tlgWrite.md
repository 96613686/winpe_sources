# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001178`
- end: `0x1800012a5`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U1@U1@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@433AEBU?$_tlgWrapperByVal@$03@@55@Z`
- size: `301`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005c30`

## callees

- `0x180001178`
- `0x1800016a0`
- `0x1800131e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        _QWORD *a7)
{
  __int64 v7; // rcx
  __int64 v8; // rax

  v7 = -1;
  if ( *a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(*a7 + 2 * v8) );
  }
  if ( *a6 )
  {
    do
      ++v7;
    while ( *(_WORD *)(*a6 + 2 * v7) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001F018, a2, 0);
}

```

## disassembly

```asm
0x180001178  push    rbp
0x18000117a  lea     rbp, [rsp-17h]
0x18000117f  sub     rsp, 0E0h
0x180001186  mov     rax, cs:__security_cookie
0x18000118d  xor     rax, rsp
0x180001190  mov     [rbp+17h+var_10], rax
0x180001194  mov     rax, [rbp+17h+arg_58]
0x180001198  xor     r9d, r9d
0x18000119b  mov     [rbp+17h+var_20], rax
0x18000119f  mov     r10, rdx
0x1800011a2  mov     rax, [rbp+17h+arg_50]
0x1800011a6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800011aa  mov     [rbp+17h+var_30], rax
0x1800011ae  mov     rax, [rbp+17h+arg_48]
0x1800011b2  lea     r8d, [r9+2]
0x1800011b6  mov     [rbp+17h+var_40], rax
0x1800011ba  mov     rax, [rbp+17h+arg_40]
0x1800011be  mov     [rbp+17h+var_50], rax
0x1800011c2  mov     rax, [rbp+17h+arg_38]
0x1800011c6  mov     [rbp+17h+var_60], rax
0x1800011ca  mov     rax, [rbp+17h+arg_30]
0x1800011ce  mov     [rbp+17h+var_18], 4
0x1800011d6  mov     [rbp+17h+var_28], 4
0x1800011de  mov     [rbp+17h+var_38], 4
0x1800011e6  mov     rdx, [rax]
0x1800011e9  mov     [rbp+17h+var_48], 8
0x1800011f1  mov     [rbp+17h+var_58], 8
0x1800011f9  test    rdx, rdx
0x1800011fc  jz      short loc_180001214
0x1800011fe  mov     rax, rcx
0x180001201  inc     rax
0x180001204  cmp     [rdx+rax*2], r9w
0x180001209  jnz     short loc_180001201
0x18000120b  lea     eax, ds:2[rax*2]
0x180001212  jmp     short loc_18000121E
0x180001214  lea     rdx, dword_180017A6C
0x18000121b  mov     eax, r8d
0x18000121e  mov     [rbp+17h+var_68], eax
0x180001221  mov     rax, [rbp+17h+arg_28]
0x180001225  mov     [rbp+17h+var_70], rdx
0x180001229  mov     [rbp+17h+var_64], r9d
0x18000122d  mov     rdx, [rax]
0x180001230  test    rdx, rdx
0x180001233  jz      short loc_180001249
0x180001235  inc     rcx
0x180001238  cmp     [rdx+rcx*2], r9w
0x18000123d  jnz     short loc_180001235
0x18000123f  lea     r8d, ds:2[rcx*2]
0x180001247  jmp     short loc_180001250
0x180001249  lea     rdx, dword_180017A6C
0x180001250  mov     rax, [rbp+17h+arg_20]
0x180001254  lea     rcx, dword_18001F018
0x18000125b  mov     [rbp+17h+var_90], rax
0x18000125f  lea     rax, [rsp+0E0h+var_B0]
0x180001264  mov     [rbp+17h+var_80], rdx
0x180001268  mov     rdx, r10
0x18000126b  mov     [rbp+17h+var_78], r8d
0x18000126f  xor     r8d, r8d
0x180001272  mov     [rsp+0E0h+var_B8], rax
0x180001277  mov     [rsp+0E0h+var_C0], 0Ah
0x18000127f  mov     [rbp+17h+var_74], r9d
0x180001283  mov     [rbp+17h+var_88], 8
0x18000128b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001290  mov     rcx, [rbp+17h+var_10]
0x180001294  xor     rcx, rsp; StackCookie
0x180001297  call    __security_check_cookie
0x18000129c  add     rsp, 0E0h
0x1800012a3  pop     rbp
0x1800012a4  retn
```
