# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x180001010`
- end: `0x1800010cb`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c47c`
- `0x18000c508`
- `0x18000c590`

## callees

- `0x180001010`
- `0x180002018`
- `0x1800027f0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 a7)
{
  const unsigned __int16 *v7; // rax
  __int64 v8; // r8
  int v9; // r8d
  _BYTE v11[32]; // [rsp+30h] [rbp-68h] BYREF
  const unsigned __int16 *v12; // [rsp+50h] [rbp-48h]
  int v13; // [rsp+58h] [rbp-40h]
  int v14; // [rsp+5Ch] [rbp-3Ch]
  __int64 v15; // [rsp+60h] [rbp-38h]
  __int64 v16; // [rsp+68h] [rbp-30h]
  __int64 v17; // [rsp+70h] [rbp-28h]
  __int64 v18; // [rsp+78h] [rbp-20h]

  v17 = a7;
  v15 = a6;
  v18 = 8;
  v16 = 4;
  v7 = *a5;
  if ( *a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_BYTE *)v7 + v8) );
    v9 = v8 + 1;
  }
  else
  {
    v7 = &word_180017D52;
    v9 = 1;
  }
  v12 = v7;
  v13 = v9;
  v14 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 5, v11);
}

```

## disassembly

```asm
0x180001010  sub     rsp, 98h
0x180001017  mov     rax, cs:__security_cookie
0x18000101e  xor     rax, rsp
0x180001021  mov     [rsp+98h+var_18], rax
0x180001029  mov     rax, [rsp+98h+arg_30]
0x180001031  xor     r9d, r9d
0x180001034  mov     [rsp+98h+var_28], rax
0x180001039  mov     rax, [rsp+98h+arg_28]
0x180001041  mov     [rsp+98h+var_38], rax
0x180001046  mov     rax, [rsp+98h+arg_20]
0x18000104e  mov     [rsp+98h+var_20], 8
0x180001057  mov     [rsp+98h+var_30], 4
0x180001060  mov     rax, [rax]
0x180001063  test    rax, rax
0x180001066  jz      short loc_18000107D
0x180001068  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000106f  inc     r8
0x180001072  cmp     [rax+r8], r9b
0x180001076  jnz     short loc_18000106F
0x180001078  inc     r8d
0x18000107b  jmp     short loc_18000108A
0x18000107d  lea     rax, word_180017D52
0x180001084  mov     r8d, 1
0x18000108a  mov     [rsp+98h+var_48], rax
0x18000108f  lea     rax, [rsp+98h+var_68]
0x180001094  mov     [rsp+98h+var_40], r8d
0x180001099  xor     r8d, r8d
0x18000109c  mov     [rsp+98h+var_70], rax
0x1800010a1  mov     [rsp+98h+var_78], 5
0x1800010a9  mov     [rsp+98h+var_3C], r9d
0x1800010ae  call    _tlgWriteTransfer_EventWriteTransfer
0x1800010b3  mov     rcx, [rsp+98h+var_18]
0x1800010bb  xor     rcx, rsp; StackCookie
0x1800010be  call    __security_check_cookie
0x1800010c3  add     rsp, 98h
0x1800010ca  retn
```
