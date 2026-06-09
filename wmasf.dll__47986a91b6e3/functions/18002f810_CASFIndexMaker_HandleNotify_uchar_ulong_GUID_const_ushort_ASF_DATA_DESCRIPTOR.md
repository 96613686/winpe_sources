# CASFIndexMaker::HandleNotify(uchar *,ulong,_GUID const *,ushort,_ASF_DATA_DESCRIPTOR *)

- ea: `0x18002f810`
- end: `0x18002f9fc`
- name: `?HandleNotify@CASFIndexMaker@@MEAAJPEAEKPEBU_GUID@@GPEAU_ASF_DATA_DESCRIPTOR@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(CASFIndexMaker *__hidden this, unsigned __int8 *, unsigned int, const struct _GUID *, unsigned __int16, struct _ASF_DATA_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800015d0`
- `0x18002e900`
- `0x18002ebb0`
- `0x18002f704`
- `0x18002f810`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFIndexMaker::HandleNotify(
        CASFIndexMaker *this,
        unsigned __int8 *a2,
        unsigned int a3,
        const struct _GUID *a4,
        unsigned __int16 a5,
        struct _ASF_DATA_DESCRIPTOR *a6)
{
  struct _ASF_DATA_DESCRIPTOR *v7; // rcx
  __int64 result; // rax
  unsigned int v9; // r15d
  char *v10; // rsi
  __int64 v11; // rcx
  unsigned int v12; // r12d
  __int64 v13; // r13
  __int64 v14; // rax
  unsigned int v15; // kr00_4
  __int64 Ptr; // rax
  unsigned int v17; // r10d
  __int64 v18; // rdi
  __int64 v19; // rax
  __int64 v20; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v21; // [rsp+28h] [rbp-50h]
  unsigned int v22; // [rsp+2Ch] [rbp-4Ch]
  struct _ASF_DATA_DESCRIPTOR *v23; // [rsp+30h] [rbp-48h]
  __int64 v24; // [rsp+38h] [rbp-40h] BYREF
  int v25; // [rsp+40h] [rbp-38h]
  __int64 v26; // [rsp+48h] [rbp-30h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-28h]
  int v28; // [rsp+54h] [rbp-24h]
  __int64 v29; // [rsp+58h] [rbp-20h]

  v22 = a3;
  v7 = a6;
  v23 = a6;
  if ( !a6 )
    return 1;
  v9 = 0;
LABEL_4:
  v21 = v9;
  if ( v9 < a5 )
  {
    v20 = 0;
    v10 = (char *)v7 + 88 * v9;
    v24 = 0;
    v11 = *((_QWORD *)this + 10);
    v25 = 0;
    result = ASFGetTimeBase(v11, *((unsigned __int16 *)v10 + 4), &v24);
    if ( (int)result < 0 )
      return result;
    ASFPresTimeToTime(&v24, v10 + 28, &v20);
    v28 = 0;
    v12 = 0;
    v13 = v20 / 10000;
    v14 = *((_QWORD *)this + 14);
    v15 = *((_DWORD *)v10 + 10);
    v26 = v20 / 10000;
    LODWORD(v20) = v15 / 0x2710;
    v27 = v15 / 0x2710;
    v29 = v14;
    if ( !*((_DWORD *)this + 3250) )
      goto LABEL_22;
    while ( 1 )
    {
      Ptr = CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr((char *)this + 352, v12);
      v18 = Ptr;
      if ( !Ptr || *(_WORD *)(Ptr + 2) != *((_WORD *)v10 + 4) )
        goto LABEL_20;
      v19 = v13 + v17;
      if ( v19 > *(_QWORD *)(v18 + 24) )
        *(_QWORD *)(v18 + 24) = v19;
      if ( *(_WORD *)(v18 + 4) != 1 )
      {
        if ( *(_WORD *)(v18 + 4) == 2 )
        {
          if ( *(_BYTE *)v18 != v10[10] )
          {
            (*(void (__fastcall **)(CASFIndexMaker *, __int64, __int64 *))(*(_QWORD *)this + 128LL))(this, v18, &v26);
            *(_BYTE *)v18 = v10[10];
          }
          goto LABEL_20;
        }
        if ( *(_WORD *)(v18 + 4) != 3 || (v10[24] & 2) == 0 || (v10[24] & 4) != 0 && *((_DWORD *)v10 + 11) )
          goto LABEL_20;
      }
      (*(void (__fastcall **)(CASFIndexMaker *, __int64, __int64 *))(*(_QWORD *)this + 128LL))(this, v18, &v26);
LABEL_20:
      if ( ++v12 >= *((_DWORD *)this + 3250) )
      {
        v9 = v21;
LABEL_22:
        (*(void (__fastcall **)(CASFIndexMaker *, __int64))(*(_QWORD *)this + 112LL))(this, v13);
        v7 = v23;
        ++v9;
        goto LABEL_4;
      }
    }
  }
  *((_QWORD *)this + 14) += v22;
  return 0;
}

```

## disassembly

```asm
0x18002f810  push    rbp
0x18002f812  push    rbx
0x18002f813  push    rsi
0x18002f814  push    rdi
0x18002f815  push    r12
0x18002f817  push    r13
0x18002f819  push    r14
0x18002f81b  push    r15
0x18002f81d  mov     rbp, rsp
0x18002f820  sub     rsp, 78h
0x18002f824  mov     rax, cs:__security_cookie
0x18002f82b  xor     rax, rsp
0x18002f82e  mov     [rbp+var_18], rax
0x18002f832  mov     rbx, rcx
0x18002f835  mov     [rbp+var_4C], r8d
0x18002f839  mov     rcx, [rbp+arg_28]
0x18002f83d  mov     [rbp+var_48], rcx
0x18002f841  test    rcx, rcx
0x18002f844  jnz     short loc_18002F84E
0x18002f846  lea     eax, [rcx+1]
0x18002f849  jmp     loc_18002F9DF
0x18002f84e  xor     r15d, r15d
0x18002f851  lea     r14d, [r15+1]
0x18002f855  movzx   eax, [rbp+arg_20]
0x18002f859  mov     [rbp+var_50], r15d
0x18002f85d  cmp     r15d, eax
0x18002f860  jnb     loc_18002F9D6
0x18002f866  mov     eax, r15d
0x18002f869  lea     r8, [rbp+var_40]
0x18002f86d  imul    rsi, rax, 58h ; 'X'
0x18002f871  xor     eax, eax
0x18002f873  mov     [rbp+var_58], 0
0x18002f87b  add     rsi, rcx
0x18002f87e  mov     [rbp+var_40], rax
0x18002f882  mov     rcx, [rbx+50h]
0x18002f886  mov     [rbp+var_38], eax
0x18002f889  movzx   edx, word ptr [rsi+8]
0x18002f88d  call    ASFGetTimeBase
0x18002f892  test    eax, eax
0x18002f894  js      loc_18002F9DF
0x18002f89a  lea     rdx, [rsi+1Ch]
0x18002f89e  lea     r8, [rbp+var_58]
0x18002f8a2  lea     rcx, [rbp+var_40]
0x18002f8a6  call    ASFPresTimeToTime
0x18002f8ab  mov     rax, 346DC5D63886594Bh
0x18002f8b5  mov     [rbp+var_24], 0
0x18002f8bc  imul    [rbp+var_58]
0x18002f8c0  xor     r12d, r12d
0x18002f8c3  mov     r13, rdx
0x18002f8c6  sar     r13, 0Bh
0x18002f8ca  mov     rax, r13
0x18002f8cd  shr     rax, 3Fh
0x18002f8d1  add     r13, rax
0x18002f8d4  mov     eax, 0D1B71759h
0x18002f8d9  mul     dword ptr [rsi+28h]
0x18002f8dc  mov     rax, [rbx+70h]
0x18002f8e0  mov     r10d, edx
0x18002f8e3  mov     [rbp+var_30], r13
0x18002f8e7  shr     r10d, 0Dh
0x18002f8eb  mov     dword ptr [rbp+var_58], r10d
0x18002f8ef  mov     [rbp+var_28], r10d
0x18002f8f3  mov     [rbp+var_20], rax
0x18002f8f7  cmp     [rbx+32C8h], r12d
0x18002f8fe  jbe     loc_18002F9B8
0x18002f904  mov     edx, r12d
0x18002f907  lea     rcx, [rbx+160h]
0x18002f90e  call    ?GetPtr@?$CTDynArray@USTREAM_INFO@CASFBaseIndexMaker@@$0BE@@@QEAAPEAUSTREAM_INFO@CASFBaseIndexMaker@@K@Z; CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::GetPtr(ulong)
0x18002f913  mov     rdi, rax
0x18002f916  test    rax, rax
0x18002f919  jz      loc_18002F9A4
0x18002f91f  movzx   ecx, word ptr [rsi+8]
0x18002f923  cmp     [rax+2], cx
0x18002f927  jnz     short loc_18002F9A4
0x18002f929  mov     eax, r10d
0x18002f92c  add     rax, r13
0x18002f92f  cmp     rax, [rdi+18h]
0x18002f933  jle     short loc_18002F939
0x18002f935  mov     [rdi+18h], rax
0x18002f939  cmp     [rdi+4], r14w
0x18002f93e  jz      short loc_18002F987
0x18002f940  cmp     word ptr [rdi+4], 2
0x18002f945  jnz     short loc_18002F96E
0x18002f947  mov     al, [rsi+0Ah]
0x18002f94a  cmp     [rdi], al
0x18002f94c  jz      short loc_18002F9A4
0x18002f94e  mov     rax, [rbx]
0x18002f951  lea     r8, [rbp+var_30]
0x18002f955  mov     rdx, rdi
0x18002f958  mov     rcx, rbx
0x18002f95b  mov     rax, [rax+80h]
0x18002f962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f967  mov     al, [rsi+0Ah]
0x18002f96a  mov     [rdi], al
0x18002f96c  jmp     short loc_18002F9A0
0x18002f96e  cmp     word ptr [rdi+4], 3
0x18002f973  jnz     short loc_18002F9A4
0x18002f975  test    byte ptr [rsi+18h], 2
0x18002f979  jz      short loc_18002F9A4
0x18002f97b  test    byte ptr [rsi+18h], 4
0x18002f97f  jz      short loc_18002F987
0x18002f981  cmp     dword ptr [rsi+2Ch], 0
0x18002f985  jnz     short loc_18002F9A4
0x18002f987  mov     rax, [rbx]
0x18002f98a  lea     r8, [rbp+var_30]
0x18002f98e  mov     rdx, rdi
0x18002f991  mov     rcx, rbx
0x18002f994  mov     rax, [rax+80h]
0x18002f99b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9a0  mov     r10d, dword ptr [rbp+var_58]
0x18002f9a4  add     r12d, r14d
0x18002f9a7  cmp     r12d, [rbx+32C8h]
0x18002f9ae  jb      loc_18002F904
0x18002f9b4  mov     r15d, [rbp+var_50]
0x18002f9b8  mov     rax, [rbx]
0x18002f9bb  mov     rdx, r13
0x18002f9be  mov     rcx, rbx
0x18002f9c1  mov     rax, [rax+70h]
0x18002f9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9ca  mov     rcx, [rbp+var_48]
0x18002f9ce  add     r15d, r14d
0x18002f9d1  jmp     loc_18002F855
0x18002f9d6  mov     eax, [rbp+var_4C]
0x18002f9d9  add     [rbx+70h], rax
0x18002f9dd  xor     eax, eax
0x18002f9df  mov     rcx, [rbp+var_18]
0x18002f9e3  xor     rcx, rsp; StackCookie
0x18002f9e6  call    __security_check_cookie
0x18002f9eb  add     rsp, 78h
0x18002f9ef  pop     r15
0x18002f9f1  pop     r14
0x18002f9f3  pop     r13
0x18002f9f5  pop     r12
0x18002f9f7  pop     rdi
0x18002f9f8  pop     rsi
0x18002f9f9  pop     rbx
0x18002f9fa  pop     rbp
0x18002f9fb  retn
```
