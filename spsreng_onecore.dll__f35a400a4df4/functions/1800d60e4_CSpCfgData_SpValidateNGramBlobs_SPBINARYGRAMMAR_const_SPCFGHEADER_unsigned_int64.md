# CSpCfgData::SpValidateNGramBlobs(SPBINARYGRAMMAR const *,SPCFGHEADER *,unsigned __int64)

- ea: `0x1800d60e4`
- end: `0x1800d6278`
- name: `?SpValidateNGramBlobs@CSpCfgData@@AEAAJPEBUSPBINARYGRAMMAR@@PEAUSPCFGHEADER@@_K@Z`
- size: `404`
- prototype: `__int64 __fastcall(CSpCfgData *__hidden this, const struct SPBINARYGRAMMAR *, struct SPCFGHEADER *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d53ec`

## callees

- `0x1800034b0`
- `0x1800d48b8`
- `0x1800d4920`
- `0x1800d4a2c`
- `0x1800d60e4`
- `0x1800d6338`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d622e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d6248`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d622e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d6248`

## pseudocode

```c
__int64 __fastcall CSpCfgData::SpValidateNGramBlobs(
        CSpCfgData *this,
        const struct SPBINARYGRAMMAR *a2,
        struct SPCFGHEADER *a3)
{
  ULONG ulTotalSerializedSize; // r14d
  int ElementSerializedSize; // ebx
  ULONG v5; // esi
  char *v9; // rdx
  unsigned int v10; // r9d
  int v11; // eax
  void *v12; // rcx
  unsigned int v14; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v15[16]; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v16; // [rsp+38h] [rbp-C8h]
  _BYTE v17[16]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v18; // [rsp+58h] [rbp-A8h]
  _BYTE v19[112]; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv[2]; // [rsp+E0h] [rbp-20h]

  ulTotalSerializedSize = a2->ulTotalSerializedSize;
  ElementSerializedSize = 0;
  v5 = 0;
  v16 = 0;
  while ( v5 < a2[16].ulTotalSerializedSize )
  {
    CSpCfgData::GetRuleDataByIndex(this, v5, (struct SPRULEDATA *)v15);
    if ( BYTE8(v16) )
    {
      v18 = 0;
      CSpCfgData::GetRuleDataByIndex(this, v5, (struct SPRULEDATA *)v17);
      v14 = 0;
      ElementSerializedSize = CSpNGramRule::GetElementSerializedSize(0, 0, &v14);
      if ( ElementSerializedSize < 0 )
        return (unsigned int)ElementSerializedSize;
      v9 = (char *)a2 + HIDWORD(v18);
      if ( v9 < (char *)a2
        || HIDWORD(v18) > ulTotalSerializedSize
        || (const struct SPBINARYGRAMMAR *)((char *)a2 + HIDWORD(v18) + v14) < a2
        || HIDWORD(v18) + v14 > ulTotalSerializedSize )
      {
        return (unsigned int)-2147200890;
      }
      ElementSerializedSize = CSpNGramRule::GetElementSerializedSize((unsigned __int8)v9[28], *((_DWORD *)v9 + 8), &v14);
      if ( ElementSerializedSize < 0 )
        return (unsigned int)ElementSerializedSize;
      if ( (const struct SPBINARYGRAMMAR *)((char *)a2 + v14) < a2
        || v14 > ulTotalSerializedSize
        || (const struct SPBINARYGRAMMAR *)((char *)a2 + v10 + v14) < a2
        || v10 + v14 > ulTotalSerializedSize )
      {
        return (unsigned int)-2147200890;
      }
      *(_OWORD *)pv = 0;
      ElementSerializedSize = CSpCfgData::GetNGramRuleByIndex(this, v5, (struct CSpNGramRule *)v19, v10);
      if ( ElementSerializedSize < 0 )
      {
        v12 = pv[1];
LABEL_20:
        CoTaskMemFree(v12);
        return (unsigned int)ElementSerializedSize;
      }
      v11 = CSpNGramRule::ValidateBlobs((CSpNGramRule *)v19, (const struct SPCFGSERIALIZEDHEADER *)a2, a3);
      v12 = pv[1];
      ElementSerializedSize = v11;
      if ( v11 < 0 )
        goto LABEL_20;
      CoTaskMemFree(pv[1]);
    }
    else if ( HIDWORD(v16) )
    {
      return (unsigned int)-2147200890;
    }
    ++v5;
  }
  return (unsigned int)ElementSerializedSize;
}

```

## disassembly

```asm
0x1800d60e4  push    rbp
0x1800d60e6  push    rbx
0x1800d60e7  push    rsi
0x1800d60e8  push    rdi
0x1800d60e9  push    r12
0x1800d60eb  push    r14
0x1800d60ed  push    r15
0x1800d60ef  lea     rbp, [rsp-280h]
0x1800d60f7  sub     rsp, 380h
0x1800d60fe  mov     rax, cs:__security_cookie
0x1800d6105  xor     rax, rsp
0x1800d6108  mov     [rbp+2B0h+var_40], rax
0x1800d610f  mov     r14d, [rdx]
0x1800d6112  xor     ebx, ebx
0x1800d6114  xorps   xmm0, xmm0
0x1800d6117  xor     esi, esi
0x1800d6119  movups  [rsp+3B0h+var_378], xmm0
0x1800d611e  mov     r12, r8
0x1800d6121  mov     rdi, rdx
0x1800d6124  mov     r15, rcx
0x1800d6127  cmp     esi, [rdi+40h]
0x1800d612a  jnb     loc_1800D6255
0x1800d6130  lea     r8, [rsp+3B0h+var_388]; struct SPRULEDATA *
0x1800d6135  mov     edx, esi; unsigned int
0x1800d6137  mov     rcx, r15; this
0x1800d613a  call    ?GetRuleDataByIndex@CSpCfgData@@QEAAXKPEAUSPRULEDATA@@@Z; CSpCfgData::GetRuleDataByIndex(ulong,SPRULEDATA *)
0x1800d613f  cmp     byte ptr [rsp+3B0h+var_378+8], 0
0x1800d6144  jz      loc_1800D6236
0x1800d614a  xorps   xmm0, xmm0
0x1800d614d  lea     r8, [rsp+3B0h+var_368]; struct SPRULEDATA *
0x1800d6152  mov     edx, esi; unsigned int
0x1800d6154  mov     rcx, r15; this
0x1800d6157  movups  [rsp+3B0h+var_358], xmm0
0x1800d615c  call    ?GetRuleDataByIndex@CSpCfgData@@QEAAXKPEAUSPRULEDATA@@@Z; CSpCfgData::GetRuleDataByIndex(ulong,SPRULEDATA *)
0x1800d6161  xor     edx, edx; unsigned int
0x1800d6163  mov     [rsp+3B0h+var_390], 0
0x1800d616b  xor     ecx, ecx; unsigned int
0x1800d616d  lea     r8, [rsp+3B0h+var_390]; unsigned int *
0x1800d6172  call    ?GetElementSerializedSize@CSpNGramRule@@SAJKKPEAK@Z; CSpNGramRule::GetElementSerializedSize(ulong,ulong,ulong *)
0x1800d6177  mov     ebx, eax
0x1800d6179  test    eax, eax
0x1800d617b  js      loc_1800D6255
0x1800d6181  mov     r9d, dword ptr [rsp+3B0h+var_358+0Ch]
0x1800d6186  lea     rdx, [rdi+r9]
0x1800d618a  cmp     rdx, rdi
0x1800d618d  jb      loc_1800D6250
0x1800d6193  cmp     r9d, r14d
0x1800d6196  ja      loc_1800D6250
0x1800d619c  mov     ecx, [rsp+3B0h+var_390]
0x1800d61a0  add     ecx, r9d
0x1800d61a3  mov     eax, ecx
0x1800d61a5  add     rax, rdi
0x1800d61a8  cmp     rax, rdi
0x1800d61ab  jb      loc_1800D6250
0x1800d61b1  cmp     ecx, r14d
0x1800d61b4  ja      loc_1800D6250
0x1800d61ba  movzx   ecx, byte ptr [rdx+1Ch]; unsigned int
0x1800d61be  lea     r8, [rsp+3B0h+var_390]; unsigned int *
0x1800d61c3  mov     edx, [rdx+20h]; unsigned int
0x1800d61c6  call    ?GetElementSerializedSize@CSpNGramRule@@SAJKKPEAK@Z; CSpNGramRule::GetElementSerializedSize(ulong,ulong,ulong *)
0x1800d61cb  mov     ebx, eax
0x1800d61cd  test    eax, eax
0x1800d61cf  js      loc_1800D6255
0x1800d61d5  mov     ecx, [rsp+3B0h+var_390]
0x1800d61d9  lea     rax, [rdi+rcx]
0x1800d61dd  cmp     rax, rdi
0x1800d61e0  jb      short loc_1800D6250
0x1800d61e2  cmp     ecx, r14d
0x1800d61e5  ja      short loc_1800D6250
0x1800d61e7  lea     edx, [r9+rcx]
0x1800d61eb  mov     eax, edx
0x1800d61ed  add     rax, rdi
0x1800d61f0  cmp     rax, rdi
0x1800d61f3  jb      short loc_1800D6250
0x1800d61f5  cmp     edx, r14d
0x1800d61f8  ja      short loc_1800D6250
0x1800d61fa  lea     r8, [rsp+3B0h+var_340]; struct CSpNGramRule *
0x1800d61ff  movdqa  xmmword ptr [rbp+2B0h+pv], xmm0
0x1800d6204  mov     edx, esi; unsigned int
0x1800d6206  mov     rcx, r15; this
0x1800d6209  call    ?GetNGramRuleByIndex@CSpCfgData@@QEAAJKPEAVCSpNGramRule@@K@Z; CSpCfgData::GetNGramRuleByIndex(ulong,CSpNGramRule *,ulong)
0x1800d620e  mov     ebx, eax
0x1800d6210  test    eax, eax
0x1800d6212  js      short loc_1800D6244
0x1800d6214  mov     r8, r12; struct SPCFGHEADER *
0x1800d6217  lea     rcx, [rsp+3B0h+var_340]; this
0x1800d621c  mov     rdx, rdi; struct SPCFGSERIALIZEDHEADER *
0x1800d621f  call    ?ValidateBlobs@CSpNGramRule@@QEAAJPEBUSPCFGSERIALIZEDHEADER@@PEAUSPCFGHEADER@@@Z; CSpNGramRule::ValidateBlobs(SPCFGSERIALIZEDHEADER const *,SPCFGHEADER *)
0x1800d6224  mov     rcx, [rbp+2B0h+pv+8]; pv
0x1800d6228  mov     ebx, eax
0x1800d622a  test    eax, eax
0x1800d622c  js      short loc_1800D6248
0x1800d622e  call    cs:__imp_CoTaskMemFree
0x1800d6234  jmp     short loc_1800D623D
0x1800d6236  cmp     dword ptr [rsp+3B0h+var_378+0Ch], 0
0x1800d623b  jnz     short loc_1800D6250
0x1800d623d  inc     esi
0x1800d623f  jmp     loc_1800D6127
0x1800d6244  mov     rcx, [rbp+2B0h+pv+8]; pv
0x1800d6248  call    cs:__imp_CoTaskMemFree
0x1800d624e  jmp     short loc_1800D6255
0x1800d6250  mov     ebx, 80045086h
0x1800d6255  mov     eax, ebx
0x1800d6257  mov     rcx, [rbp+2B0h+var_40]
0x1800d625e  xor     rcx, rsp; StackCookie
0x1800d6261  call    __security_check_cookie
0x1800d6266  add     rsp, 380h
0x1800d626d  pop     r15
0x1800d626f  pop     r14
0x1800d6271  pop     r12
0x1800d6273  pop     rdi
0x1800d6274  pop     rsi
0x1800d6275  pop     rbx
0x1800d6276  pop     rbp
0x1800d6277  retn
```
