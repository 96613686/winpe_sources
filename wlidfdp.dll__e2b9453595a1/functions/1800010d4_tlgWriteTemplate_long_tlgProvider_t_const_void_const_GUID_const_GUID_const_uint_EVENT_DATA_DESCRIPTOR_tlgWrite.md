# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800010d4`
- end: `0x18000119d`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c618`

## callees

- `0x1800010d4`
- `0x180002018`
- `0x1800027f0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  int v11; // edx
  const unsigned __int16 *v12; // rcx
  __int64 v13; // rax
  _BYTE v15[32]; // [rsp+30h] [rbp-51h] BYREF
  const unsigned __int16 *v16; // [rsp+50h] [rbp-31h]
  int v17; // [rsp+58h] [rbp-29h]
  int v18; // [rsp+5Ch] [rbp-25h]
  __int64 v19; // [rsp+60h] [rbp-21h]
  __int64 v20; // [rsp+68h] [rbp-19h]
  __int64 v21; // [rsp+70h] [rbp-11h]
  __int64 v22; // [rsp+78h] [rbp-9h]
  __int64 v23; // [rsp+80h] [rbp-1h]
  __int64 v24; // [rsp+88h] [rbp+7h]
  __int64 v25; // [rsp+90h] [rbp+Fh]
  __int64 v26; // [rsp+98h] [rbp+17h]

  v25 = a9;
  v23 = a8;
  v11 = 1;
  v21 = a7;
  v19 = a6;
  v26 = 8;
  v24 = 4;
  v22 = 4;
  v12 = *a5;
  v20 = 1;
  if ( v12 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_BYTE *)v12 + v13) );
    v11 = v13 + 1;
  }
  else
  {
    v12 = &word_180017D52;
  }
  v16 = v12;
  v17 = v11;
  v18 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 7, v15);
}

```

## disassembly

```asm
0x1800010d4  push    rbp
0x1800010d6  lea     rbp, [rsp-2Fh]
0x1800010db  sub     rsp, 0B0h
0x1800010e2  mov     rax, cs:__security_cookie
0x1800010e9  xor     rax, rsp
0x1800010ec  mov     [rbp+2Fh+var_10], rax
0x1800010f0  mov     rax, [rbp+2Fh+arg_40]
0x1800010f4  xor     r8d, r8d
0x1800010f7  mov     [rbp+2Fh+var_20], rax
0x1800010fb  mov     r10, rcx
0x1800010fe  mov     rax, [rbp+2Fh+arg_38]
0x180001102  mov     r11, rdx
0x180001105  mov     [rbp+2Fh+var_30], rax
0x180001109  mov     rax, [rbp+2Fh+arg_30]
0x18000110d  lea     edx, [r8+1]
0x180001111  mov     [rbp+2Fh+var_40], rax
0x180001115  mov     rax, [rbp+2Fh+arg_28]
0x180001119  mov     [rbp+2Fh+var_50], rax
0x18000111d  mov     rax, [rbp+2Fh+arg_20]
0x180001121  mov     [rbp+2Fh+var_18], 8
0x180001129  mov     [rbp+2Fh+var_28], 4
0x180001131  mov     [rbp+2Fh+var_38], 4
0x180001139  mov     rcx, [rax]
0x18000113c  mov     [rbp+2Fh+var_48], rdx
0x180001140  test    rcx, rcx
0x180001143  jz      short loc_180001157
0x180001145  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001149  inc     rax
0x18000114c  cmp     [rcx+rax], r8b
0x180001150  jnz     short loc_180001149
0x180001152  lea     edx, [rax+1]
0x180001155  jmp     short loc_18000115E
0x180001157  lea     rcx, word_180017D52
0x18000115e  lea     rax, [rbp+2Fh+var_80]
0x180001162  mov     [rbp+2Fh+var_60], rcx
0x180001166  mov     [rbp+2Fh+var_58], edx
0x180001169  xor     r9d, r9d
0x18000116c  mov     [rsp+0B0h+var_88], rax
0x180001171  mov     rdx, r11
0x180001174  mov     rcx, r10
0x180001177  mov     [rsp+0B0h+var_90], 7
0x18000117f  mov     [rbp+2Fh+var_54], r8d
0x180001183  call    _tlgWriteTransfer_EventWriteTransfer
0x180001188  mov     rcx, [rbp+2Fh+var_10]
0x18000118c  xor     rcx, rsp; StackCookie
0x18000118f  call    __security_check_cookie
0x180001194  add     rsp, 0B0h
0x18000119b  pop     rbp
0x18000119c  retn
```
