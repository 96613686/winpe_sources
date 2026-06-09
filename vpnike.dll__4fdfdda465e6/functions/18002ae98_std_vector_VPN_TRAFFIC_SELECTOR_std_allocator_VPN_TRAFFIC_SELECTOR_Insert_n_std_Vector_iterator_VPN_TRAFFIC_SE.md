# std::vector<_VPN_TRAFFIC_SELECTOR_ *,std::allocator<_VPN_TRAFFIC_SELECTOR_ *>>::_Insert_n(std::_Vector_iterator<_VPN_TRAFFIC_SELECTOR_ *,std::allocator<_VPN_TRAFFIC_SELECTOR_ *>>,unsigned __int64,_VPN_TRAFFIC_SELECTOR_ * const &)

- ea: `0x18002ae98`
- end: `0x18002b0cb`
- name: `?_Insert_n@?$vector@PEAU_VPN_TRAFFIC_SELECTOR_@@V?$allocator@PEAU_VPN_TRAFFIC_SELECTOR_@@@std@@@std@@IEAAXV?$_Vector_iterator@PEAU_VPN_TRAFFIC_SELECTOR_@@V?$allocator@PEAU_VPN_TRAFFIC_SELECTOR_@@@std@@@2@_KAEBQEAU_VPN_TRAFFIC_SELECTOR_@@@Z`
- size: `563`
- prototype: `__int64 __fastcall(__int64, char *, const char *, const char **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180028ef0`

## callees

- `0x180001514`
- `0x180001564`
- `0x180001f78`
- `0x1800272ec`
- `0x18002ae98`
- `0x18002b5ac`
- `0x18002c19c`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18002af66`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18002af66`
- `msvcrt!memmove_s` at `0x18002afc5`
- `msvcrt!memmove_s` at `0x18002aff0`
- `msvcrt!memmove_s` at `0x18002b078`
- `msvcrt!memmove_s` at `0x18002b0a3`
- `msvcrt!memmove_s` at `0x18002afc5`
- `msvcrt!memmove_s` at `0x18002aff0`
- `msvcrt!memmove_s` at `0x18002b078`
- `msvcrt!memmove_s` at `0x18002b0a3`

## pseudocode

```c
__int64 __fastcall std::vector<_VPN_TRAFFIC_SELECTOR_ *>::_Insert_n(
        __int64 a1,
        char *a2,
        const char *a3,
        const char **a4)
{
  const char *v6; // r12
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rax
  unsigned __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int64 v12; // r8
  __int64 v13; // r9
  unsigned __int64 v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // r8
  unsigned __int64 v21; // rcx
  char *v22; // rax
  char *v23; // r14
  _BYTE *v24; // r8
  __int64 v25; // rcx
  __int64 v26; // r15
  __int64 v27; // rdx
  __int64 v28; // rbx
  void *v29; // rcx
  __int64 result; // rax
  _BYTE *v31; // rdi
  unsigned __int64 v32; // r8
  char *v33; // rdx
  __int64 v34; // rdx
  _QWORD pExceptionObject[11]; // [rsp+20h] [rbp-58h] BYREF
  char *v36; // [rsp+90h] [rbp+18h] BYREF

  v36 = (char *)a3;
  v6 = *a4;
  v36 = (char *)*a4;
  if ( *(_QWORD *)(a1 + 8) )
    v7 = (__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 8)) >> 3;
  else
    v7 = 0;
  if ( std::vector<_VPN_TRAFFIC_SELECTOR_ *>::size(a1, v7) == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<_VPN_TRAFFIC_SELECTOR_ *>::_Xlen();
  v9 = std::vector<_VPN_TRAFFIC_SELECTOR_ *>::size(a1, v8);
  if ( v10 >= v12 + v9 )
  {
    v31 = *(_BYTE **)(a1 + 16);
    if ( (v31 - a2) >> 3 >= v12 )
    {
      memmove_s(*(void *const *)(a1 + 16), 8u, v31 - 8, 8u);
      *(_QWORD *)(a1 + 16) = v31 + 8;
      v34 = (v31 - a2 - 8) >> 3;
      if ( v34 > 0 )
        memmove_s(&v31[-8 * v34], 8 * v34, a2, 8 * v34);
      v33 = a2 + 8;
    }
    else
    {
      v32 = v12 - ((v31 - a2) >> 3);
      if ( v32 )
        memset64(v31, (unsigned __int64)v6, v32);
      v33 = *(char **)(a1 + 16);
      *(_QWORD *)(a1 + 16) = v33 + 8;
    }
    return std::fill<_VPN_TRAFFIC_SELECTOR_ * *,_VPN_TRAFFIC_SELECTOR_ *>(a2, v33, &v36);
  }
  else
  {
    v14 = 0;
    if ( v13 - (v10 >> 1) >= v10 )
      v14 = v10 + (v10 >> 1);
    v15 = std::vector<_VPN_TRAFFIC_SELECTOR_ *>::size(v11, v10);
    if ( v14 < v18 + v15 )
    {
      v19 = std::vector<_VPN_TRAFFIC_SELECTOR_ *>::size(v17, v16);
      v14 = v20 + v19;
    }
    if ( v14 )
    {
      if ( 0xFFFFFFFFFFFFFFFFuLL / v14 < 8 )
      {
        v36 = 0;
        exception::exception((exception *)pExceptionObject, (const char *const *)&v36);
        pExceptionObject[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)pExceptionObject;
      }
      v21 = v14;
    }
    else
    {
      v21 = 0;
    }
    v22 = (char *)operator new(8 * v21);
    v23 = v22;
    v36 = v22;
    try
    {
      v24 = *(_BYTE **)(a1 + 8);
      v25 = (a2 - v24) >> 3;
      v26 = 8 * v25;
      if ( v25 )
        memmove_s(v22, 8 * v25, v24, 8 * v25);
      *(_QWORD *)&v23[v26] = v6;
      v27 = (__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)a2) >> 3;
      if ( v27 )
        memmove_s(&v23[v26 + 8], 8 * v27, a2, 8 * v27);
      v28 = std::vector<_VPN_TRAFFIC_SELECTOR_ *>::size(a1, v27);
      v29 = *(void **)(a1 + 8);
      if ( v29 )
        operator delete(v29);
      *(_QWORD *)(a1 + 24) = &v23[8 * v14];
      result = (__int64)&v23[8 * v28 + 8];
      *(_QWORD *)(a1 + 16) = result;
      *(_QWORD *)(a1 + 8) = v23;
    }
    catch ( ... )
    {
      operator delete(v36);
      throw;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002ae98  mov     rax, rsp
0x18002ae9b  mov     [rax+18h], r8
0x18002ae9f  push    rbx
0x18002aea0  push    rsi
0x18002aea1  push    rdi
0x18002aea2  push    r12
0x18002aea4  push    r14
0x18002aea6  push    r15
0x18002aea8  sub     rsp, 48h
0x18002aeac  mov     rbx, rdx
0x18002aeaf  mov     rsi, rcx
0x18002aeb2  mov     r12, [r9]
0x18002aeb5  mov     [rax+18h], r12
0x18002aeb9  cmp     qword ptr [rcx+8], 0
0x18002aebe  jnz     short loc_18002AEC4
0x18002aec0  xor     edx, edx
0x18002aec2  jmp     short loc_18002AED0
0x18002aec4  mov     rdx, [rcx+18h]
0x18002aec8  sub     rdx, [rcx+8]
0x18002aecc  sar     rdx, 3
0x18002aed0  call    ?size@?$vector@PEAU_VPN_TRAFFIC_SELECTOR_@@V?$allocator@PEAU_VPN_TRAFFIC_SELECTOR_@@@std@@@std@@QEBA_KXZ; std::vector<_VPN_TRAFFIC_SELECTOR_ *>::size(void)
0x18002aed5  mov     r9, 1FFFFFFFFFFFFFFFh
0x18002aedf  mov     rcx, r9
0x18002aee2  sub     rcx, rax
0x18002aee5  mov     r8d, 1
0x18002aeeb  cmp     rcx, r8
0x18002aeee  jnb     short loc_18002AEF6
0x18002aef0  call    ?_Xlen@?$vector@PEAU_VPN_TRAFFIC_SELECTOR_@@V?$allocator@PEAU_VPN_TRAFFIC_SELECTOR_@@@std@@@std@@KAXXZ; std::vector<_VPN_TRAFFIC_SELECTOR_ *>::_Xlen(void)
0x18002aef6  mov     rcx, rsi
0x18002aef9  call    ?size@?$vector@PEAU_VPN_TRAFFIC_SELECTOR_@@V?$allocator@PEAU_VPN_TRAFFIC_SELECTOR_@@@std@@@std@@QEBA_KXZ; std::vector<_VPN_TRAFFIC_SELECTOR_ *>::size(void)
0x18002aefe  add     rax, r8
0x18002af01  cmp     rdx, rax
0x18002af04  jnb     loc_18002B02D
0x18002af0a  mov     rax, rdx
0x18002af0d  shr     rax, 1
0x18002af10  sub     r9, rax
0x18002af13  add     rax, rdx
0x18002af16  xor     edi, edi
0x18002af18  cmp     r9, rdx
0x18002af1b  cmovnb  rdi, rax
0x18002af1f  call    ?size@?$vector@PEAU_VPN_TRAFFIC_SELECTOR_@@V?$allocator@PEAU_VPN_TRAFFIC_SELECTOR_@@@std@@@std@@QEBA_KXZ; std::vector<_VPN_TRAFFIC_SELECTOR_ *>::size(void)
0x18002af24  add     rax, r8
0x18002af27  cmp     rdi, rax
0x18002af2a  jnb     short loc_18002AF35
0x18002af2c  call    ?size@?$vector@PEAU_VPN_TRAFFIC_SELECTOR_@@V?$allocator@PEAU_VPN_TRAFFIC_SELECTOR_@@@std@@@std@@QEBA_KXZ; std::vector<_VPN_TRAFFIC_SELECTOR_ *>::size(void)
0x18002af31  lea     rdi, [r8+rax]
0x18002af35  test    rdi, rdi
0x18002af38  jnz     short loc_18002AF3E
0x18002af3a  xor     ecx, ecx
0x18002af3c  jmp     short loc_18002AF8D
0x18002af3e  xor     edx, edx
0x18002af40  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002af44  div     rdi
0x18002af47  cmp     rax, 8
0x18002af4b  jnb     short loc_18002AF8A
0x18002af4d  mov     [rsp+78h+arg_10], 0
0x18002af59  lea     rdx, [rsp+78h+arg_10]
0x18002af61  lea     rcx, [rsp+78h+pExceptionObject]
0x18002af66  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18002af6c  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18002af73  mov     [rsp+78h+pExceptionObject], rax
0x18002af78  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18002af7f  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18002af84  call    _CxxThrowException_0
0x18002af8a  mov     rcx, rdi
0x18002af8d  shl     rcx, 3; Size
0x18002af91  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002af96  mov     r14, rax
0x18002af99  mov     [rsp+78h+arg_10], rax
0x18002afa1  mov     r8, [rsi+8]; Source
0x18002afa5  mov     rcx, rbx
0x18002afa8  sub     rcx, r8
0x18002afab  sar     rcx, 3
0x18002afaf  lea     r15, ds:0[rcx*8]
0x18002afb7  test    rcx, rcx
0x18002afba  jz      short loc_18002AFCB
0x18002afbc  mov     r9, r15; SourceSize
0x18002afbf  mov     rdx, r15; DestinationSize
0x18002afc2  mov     rcx, rax; Destination
0x18002afc5  call    cs:__imp_memmove_s
0x18002afcb  mov     [r15+r14], r12
0x18002afcf  mov     rdx, [rsi+10h]
0x18002afd3  sub     rdx, rbx
0x18002afd6  sar     rdx, 3
0x18002afda  test    rdx, rdx
0x18002afdd  jz      short loc_18002AFF7
0x18002afdf  shl     rdx, 3; DestinationSize
0x18002afe3  lea     rcx, [r15+8]
0x18002afe7  add     rcx, r14; Destination
0x18002afea  mov     r9, rdx; SourceSize
0x18002afed  mov     r8, rbx; Source
0x18002aff0  call    cs:__imp_memmove_s
0x18002aff6  nop
0x18002aff7  mov     rcx, rsi
0x18002affa  call    ?size@?$vector@PEAU_VPN_TRAFFIC_SELECTOR_@@V?$allocator@PEAU_VPN_TRAFFIC_SELECTOR_@@@std@@@std@@QEBA_KXZ; std::vector<_VPN_TRAFFIC_SELECTOR_ *>::size(void)
0x18002afff  mov     rbx, rax
0x18002b002  mov     rcx, [rsi+8]; Block
0x18002b006  test    rcx, rcx
0x18002b009  jz      short loc_18002B010
0x18002b00b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002b010  lea     rax, [r14+rdi*8]
0x18002b014  mov     [rsi+18h], rax
0x18002b018  lea     rax, [rbx+1]
0x18002b01c  lea     rax, [r14+rax*8]
0x18002b020  mov     [rsi+10h], rax
0x18002b024  mov     [rsi+8], r14
0x18002b028  jmp     loc_18002B0BD
0x18002b02d  mov     rdi, [rsi+10h]
0x18002b031  mov     r14, rdi
0x18002b034  sub     r14, rbx
0x18002b037  mov     rax, r14
0x18002b03a  sar     rax, 3
0x18002b03e  cmp     rax, r8
0x18002b041  jnb     short loc_18002B069
0x18002b043  mov     rdx, rdi
0x18002b046  sub     rdx, rbx
0x18002b049  sar     rdx, 3
0x18002b04d  sub     r8, rdx
0x18002b050  jz      short loc_18002B05B
0x18002b052  mov     rax, r12
0x18002b055  mov     rcx, r8
0x18002b058  rep stosq
0x18002b05b  mov     rdx, [rsi+10h]
0x18002b05f  lea     rax, [rdx+8]
0x18002b063  mov     [rsi+10h], rax
0x18002b067  jmp     short loc_18002B0AD
0x18002b069  lea     r8, [rdi-8]; Source
0x18002b06d  mov     edx, 8; DestinationSize
0x18002b072  mov     r9d, edx; SourceSize
0x18002b075  mov     rcx, rdi; Destination
0x18002b078  call    cs:__imp_memmove_s
0x18002b07e  lea     rax, [rdi+8]
0x18002b082  mov     [rsi+10h], rax
0x18002b086  lea     rdx, [r14-8]
0x18002b08a  sar     rdx, 3
0x18002b08e  test    rdx, rdx
0x18002b091  jle     short loc_18002B0A9
0x18002b093  shl     rdx, 3; DestinationSize
0x18002b097  sub     rdi, rdx
0x18002b09a  mov     r9, rdx; SourceSize
0x18002b09d  mov     r8, rbx; Source
0x18002b0a0  mov     rcx, rdi; Destination
0x18002b0a3  call    cs:__imp_memmove_s
0x18002b0a9  lea     rdx, [rbx+8]
0x18002b0ad  lea     r8, [rsp+78h+arg_10]
0x18002b0b5  mov     rcx, rbx
0x18002b0b8  call    ??$fill@PEAPEAU_VPN_TRAFFIC_SELECTOR_@@PEAU1@@std@@YAXPEAPEAU_VPN_TRAFFIC_SELECTOR_@@0AEBQEAU1@@Z; std::fill<_VPN_TRAFFIC_SELECTOR_ * *,_VPN_TRAFFIC_SELECTOR_ *>(_VPN_TRAFFIC_SELECTOR_ * *,_VPN_TRAFFIC_SELECTOR_ * *,_VPN_TRAFFIC_SELECTOR_ * const &)
0x18002b0bd  add     rsp, 48h
0x18002b0c1  pop     r15
0x18002b0c3  pop     r14
0x18002b0c5  pop     r12
0x18002b0c7  pop     rdi
0x18002b0c8  pop     rsi
0x18002b0c9  pop     rbx
0x18002b0ca  retn
```
