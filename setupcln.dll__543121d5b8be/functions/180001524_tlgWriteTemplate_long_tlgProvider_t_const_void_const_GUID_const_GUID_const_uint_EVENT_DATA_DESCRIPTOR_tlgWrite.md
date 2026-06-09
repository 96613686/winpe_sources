# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001524`
- end: `0x180001666`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U1@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@43AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapSz@D@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, _QWORD *, _QWORD *, __int64, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004c70`

## callees

- `0x180001524`
- `0x1800016a0`
- `0x1800131e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        _QWORD *a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        _QWORD *a11)
{
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax

  v11 = -1;
  if ( *a11 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_BYTE *)(*a11 + v12) );
  }
  if ( *a7 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(*a7 + 2 * v13) );
  }
  if ( *a6 )
  {
    do
      ++v11;
    while ( *(_WORD *)(*a6 + 2 * v11) );
  }
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001F018, a2, 0);
}

```

## disassembly

```asm
0x180001524  push    rbp
0x180001526  lea     rbp, [rsp-1Fh]
0x18000152b  sub     rsp, 0D0h
0x180001532  mov     rax, cs:__security_cookie
0x180001539  xor     rax, rsp
0x18000153c  mov     [rbp+1Fh+var_10], rax
0x180001540  mov     rax, [rbp+1Fh+arg_50]
0x180001544  mov     r10, rdx
0x180001547  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000154b  xor     r9d, r9d
0x18000154e  mov     rdx, [rax]
0x180001551  test    rdx, rdx
0x180001554  jz      short loc_180001566
0x180001556  mov     rax, rcx
0x180001559  inc     rax
0x18000155c  cmp     [rdx+rax], r9b
0x180001560  jnz     short loc_180001559
0x180001562  inc     eax
0x180001564  jmp     short loc_180001572
0x180001566  lea     rdx, dword_1800191A4
0x18000156d  mov     eax, 1
0x180001572  mov     [rbp+1Fh+var_18], eax
0x180001575  mov     r8d, 2
0x18000157b  mov     rax, [rbp+1Fh+arg_48]
0x18000157f  mov     [rbp+1Fh+var_30], rax
0x180001583  mov     rax, [rbp+1Fh+arg_40]
0x180001587  mov     [rbp+1Fh+var_40], rax
0x18000158b  mov     rax, [rbp+1Fh+arg_38]
0x18000158f  mov     [rbp+1Fh+var_50], rax
0x180001593  mov     rax, [rbp+1Fh+arg_30]
0x180001597  mov     [rbp+1Fh+var_20], rdx
0x18000159b  mov     [rbp+1Fh+var_14], r9d
0x18000159f  mov     [rbp+1Fh+var_28], 4
0x1800015a7  mov     rdx, [rax]
0x1800015aa  mov     [rbp+1Fh+var_38], 4
0x1800015b2  mov     [rbp+1Fh+var_48], 8
0x1800015ba  test    rdx, rdx
0x1800015bd  jz      short loc_1800015D5
0x1800015bf  mov     rax, rcx
0x1800015c2  inc     rax
0x1800015c5  cmp     [rdx+rax*2], r9w
0x1800015ca  jnz     short loc_1800015C2
0x1800015cc  lea     eax, ds:2[rax*2]
0x1800015d3  jmp     short loc_1800015DF
0x1800015d5  lea     rdx, dword_180017A6C
0x1800015dc  mov     eax, r8d
0x1800015df  mov     [rbp+1Fh+var_58], eax
0x1800015e2  mov     rax, [rbp+1Fh+arg_28]
0x1800015e6  mov     [rbp+1Fh+var_60], rdx
0x1800015ea  mov     [rbp+1Fh+var_54], r9d
0x1800015ee  mov     rdx, [rax]
0x1800015f1  test    rdx, rdx
0x1800015f4  jz      short loc_18000160A
0x1800015f6  inc     rcx
0x1800015f9  cmp     [rdx+rcx*2], r9w
0x1800015fe  jnz     short loc_1800015F6
0x180001600  lea     r8d, ds:2[rcx*2]
0x180001608  jmp     short loc_180001611
0x18000160a  lea     rdx, dword_180017A6C
0x180001611  mov     rax, [rbp+1Fh+arg_20]
0x180001615  lea     rcx, dword_18001F018
0x18000161c  mov     [rbp+1Fh+var_80], rax
0x180001620  lea     rax, [rsp+0D0h+var_A0]
0x180001625  mov     [rbp+1Fh+var_70], rdx
0x180001629  mov     rdx, r10
0x18000162c  mov     [rbp+1Fh+var_68], r8d
0x180001630  xor     r8d, r8d
0x180001633  mov     [rsp+0D0h+var_A8], rax
0x180001638  mov     [rsp+0D0h+var_B0], 9
0x180001640  mov     [rbp+1Fh+var_64], r9d
0x180001644  mov     [rbp+1Fh+var_78], 8
0x18000164c  call    _tlgWriteTransfer_EventWriteTransfer
0x180001651  mov     rcx, [rbp+1Fh+var_10]
0x180001655  xor     rcx, rsp; StackCookie
0x180001658  call    __security_check_cookie
0x18000165d  add     rsp, 0D0h
0x180001664  pop     rbp
0x180001665  retn
```
