# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001418`
- end: `0x18000151d`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@43AEBU?$_tlgWrapperByVal@$03@@5@Z`
- size: `261`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004c70`

## callees

- `0x180001418`
- `0x1800016a0`
- `0x1800131e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
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
0x180001418  push    rbp
0x18000141a  lea     rbp, [rsp-27h]
0x18000141f  sub     rsp, 0C0h
0x180001426  mov     rax, cs:__security_cookie
0x18000142d  xor     rax, rsp
0x180001430  mov     [rbp+27h+var_10], rax
0x180001434  mov     rax, [rbp+27h+arg_48]
0x180001438  xor     r9d, r9d
0x18000143b  mov     [rbp+27h+var_20], rax
0x18000143f  mov     r10, rdx
0x180001442  mov     rax, [rbp+27h+arg_40]
0x180001446  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000144a  mov     [rbp+27h+var_30], rax
0x18000144e  mov     rax, [rbp+27h+arg_38]
0x180001452  lea     r11d, [r9+8]
0x180001456  mov     [rbp+27h+var_40], rax
0x18000145a  lea     r8d, [r9+2]
0x18000145e  mov     rax, [rbp+27h+arg_30]
0x180001462  mov     [rbp+27h+var_18], 4
0x18000146a  mov     [rbp+27h+var_28], 4
0x180001472  mov     [rbp+27h+var_38], r11
0x180001476  mov     rdx, [rax]
0x180001479  test    rdx, rdx
0x18000147c  jz      short loc_180001494
0x18000147e  mov     rax, rcx
0x180001481  inc     rax
0x180001484  cmp     [rdx+rax*2], r9w
0x180001489  jnz     short loc_180001481
0x18000148b  lea     eax, ds:2[rax*2]
0x180001492  jmp     short loc_18000149E
0x180001494  lea     rdx, dword_180017A6C
0x18000149b  mov     eax, r8d
0x18000149e  mov     [rbp+27h+var_48], eax
0x1800014a1  mov     rax, [rbp+27h+arg_28]
0x1800014a5  mov     [rbp+27h+var_50], rdx
0x1800014a9  mov     [rbp+27h+var_44], r9d
0x1800014ad  mov     rdx, [rax]
0x1800014b0  test    rdx, rdx
0x1800014b3  jz      short loc_1800014C9
0x1800014b5  inc     rcx
0x1800014b8  cmp     [rdx+rcx*2], r9w
0x1800014bd  jnz     short loc_1800014B5
0x1800014bf  lea     r8d, ds:2[rcx*2]
0x1800014c7  jmp     short loc_1800014D0
0x1800014c9  lea     rdx, dword_180017A6C
0x1800014d0  mov     rax, [rbp+27h+arg_20]
0x1800014d4  lea     rcx, dword_18001F018
0x1800014db  mov     [rbp+27h+var_70], rax
0x1800014df  lea     rax, [rbp+27h+var_90]
0x1800014e3  mov     [rbp+27h+var_60], rdx
0x1800014e7  mov     rdx, r10
0x1800014ea  mov     [rbp+27h+var_58], r8d
0x1800014ee  xor     r8d, r8d
0x1800014f1  mov     [rsp+0C0h+var_98], rax
0x1800014f6  mov     [rsp+0C0h+var_A0], r11d
0x1800014fb  mov     [rbp+27h+var_54], r9d
0x1800014ff  mov     [rbp+27h+var_68], r11
0x180001503  call    _tlgWriteTransfer_EventWriteTransfer
0x180001508  mov     rcx, [rbp+27h+var_10]
0x18000150c  xor     rcx, rsp; StackCookie
0x18000150f  call    __security_check_cookie
0x180001514  add     rsp, 0C0h
0x18000151b  pop     rbp
0x18000151c  retn
```
