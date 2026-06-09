# CVaultSchema::DeserializeSchema(uchar *,ulong)

- ea: `0x18001bdb4`
- end: `0x18001c0c3`
- name: `?DeserializeSchema@CVaultSchema@@AEAAKPEAEK@Z`
- size: `783`
- prototype: `unsigned int __fastcall(CVaultSchema *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b798`

## callees

- `0x18001a640`
- `0x18001bdb4`
- `0x18001c0d0`
- `0x18001cbbc`
- `0x18001cc1c`
- `0x18004b43c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001be55`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c039`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001be55`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c039`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18001be2e`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18001be2e`

## pseudocode

```c
__int64 __fastcall CVaultSchema::DeserializeSchema(CVaultSchema *this, unsigned __int8 *a2, unsigned int a3)
{
  SIZE_T v4; // r14
  unsigned __int8 *v5; // rbx
  unsigned int v6; // edi
  __int64 i; // r15
  HLOCAL v8; // rax
  _DWORD *v9; // rcx
  unsigned int v10; // edi
  _DWORD *v11; // rcx
  unsigned int v12; // edi
  __int16 v13; // ax
  unsigned __int8 *v14; // rbx
  unsigned int v15; // edi
  unsigned int j; // r14d
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r15
  __int64 result; // rax
  _WORD *v21; // rcx
  int v22; // [rsp+20h] [rbp-48h] BYREF
  __int64 v23; // [rsp+28h] [rbp-40h]
  char v24[56]; // [rsp+30h] [rbp-38h] BYREF
  __int16 Source2; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int8 *v26; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v27; // [rsp+80h] [rbp+18h] BYREF

  Source2 = 0;
  if ( a3 < 4 )
    return 122;
  v4 = *(unsigned int *)a2;
  v5 = a2 + 4;
  v26 = a2 + 4;
  v6 = a3 - 4;
  v27 = a3 - 4;
  if ( (unsigned int)v4 >= 2 )
  {
    if ( (unsigned int)v4 <= v6 )
    {
      if ( (v4 & 1) == 0 )
      {
        for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 2) )
        {
          if ( RtlCompareMemory(&v5[i], &Source2, 2u) == 2 )
          {
            if ( (unsigned int)i != v4 - 2 )
              return 1358;
            v8 = LocalAlloc(0x40u, v4);
            *((_QWORD *)this + 4) = v8;
            if ( !v8 )
              return 14;
            memcpy_0(v8, v5, v4);
            v5 += v4;
            v26 = v5;
            v6 -= v4;
            v27 = v6;
            if ( !*((_QWORD *)this + 4) )
              goto LABEL_35;
            goto LABEL_12;
          }
        }
      }
      return 1358;
    }
    return 122;
  }
  *((_QWORD *)this + 4) = 0;
LABEL_35:
  v21 = LocalAlloc(0x40u, 2u);
  *((_QWORD *)this + 4) = v21;
  if ( !v21 )
    return 14;
  *v21 = 0;
LABEL_12:
  if ( (*((_BYTE *)this + 96) & 1) == 0 )
  {
    result = VaultDeserialize<CVaultSchemaElement>(&v26, &v27, *((_QWORD *)this + 5));
    if ( (_DWORD)result )
      return result;
    v6 = v27;
    v5 = v26;
  }
  if ( v6 < 0x10 )
    return 122;
  v9 = (_DWORD *)*((_QWORD *)this + 6);
  v9[2] = *(_DWORD *)v5;
  if ( v6 - 4 < 4 )
    return 122;
  v9[3] = *((_DWORD *)v5 + 1);
  if ( v6 - 8 < 4 )
    return 122;
  v9[4] = *((_DWORD *)v5 + 2);
  if ( v6 - 12 < 4 )
    return 122;
  v9[5] = *((_DWORD *)v5 + 3);
  v10 = v6 - 16;
  if ( v10 < 0x10 )
    return 122;
  v11 = (_DWORD *)*((_QWORD *)this + 7);
  v11[2] = *((_DWORD *)v5 + 4);
  if ( v10 - 4 < 4 )
    return 122;
  v11[3] = *((_DWORD *)v5 + 5);
  if ( v10 - 8 < 4 )
    return 122;
  v11[4] = *((_DWORD *)v5 + 6);
  if ( v10 - 12 < 4 )
    return 122;
  v11[5] = *((_DWORD *)v5 + 7);
  v12 = v10 - 16;
  if ( v12 < 2 )
    return 122;
  v13 = *((_WORD *)v5 + 16);
  v14 = v5 + 34;
  v26 = v14;
  v15 = v12 - 2;
  v27 = v15;
  if ( v13 != *((_WORD *)this + 34) )
    return 1358;
  for ( j = 0; j < *((unsigned __int16 *)this + 34); ++j )
  {
    if ( v15 < 0x10 )
      return 122;
    v17 = 32LL * j;
    v18 = *((_QWORD *)this + 9);
    *(_DWORD *)(v17 + v18 + 8) = *(_DWORD *)v14;
    if ( v15 - 4 < 4 )
      return 122;
    *(_DWORD *)(v17 + v18 + 12) = *((_DWORD *)v14 + 1);
    if ( v15 - 8 < 4 )
      return 122;
    *(_DWORD *)(v17 + v18 + 16) = *((_DWORD *)v14 + 2);
    if ( v15 - 12 < 4 )
      return 122;
    *(_DWORD *)(v17 + v18 + 20) = *((_DWORD *)v14 + 3);
    v14 += 16;
    v26 = v14;
    v15 -= 16;
    v27 = v15;
    v19 = v17 + *((_QWORD *)this + 9);
    try
    {
      v22 = (*(__int64 (**)(void))(*(_QWORD *)v19 + 8LL))();
      v23 = v19;
      std::map<enum VAULT_SCHEMA_ELEMENT_ID,CVaultSchemaElement *>::insert<std::pair<enum VAULT_SCHEMA_ELEMENT_ID,CVaultSchemaElement *>,0>(
        (char *)this + 80,
        v24,
        &v22);
    }
    catch ( std::bad_alloc )
    {
      return 14;
    }
  }
  result = CVaultGenericPropertyCollection<enum ESchemaPropertyId,0>::DeserializeCollection(
             (char *)this + 104,
             &v26,
             &v27);
  if ( !(_DWORD)result )
    return VaultCreateVaultSecurable(2, (char *)this + 12, 0, (char *)this + 144);
  return result;
}

```

## disassembly

```asm
0x18001bdb4  mov     r11, rsp
0x18001bdb7  mov     [r11+20h], rbx
0x18001bdbb  push    rsi
0x18001bdbc  push    rdi
0x18001bdbd  push    r12
0x18001bdbf  push    r14
0x18001bdc1  push    r15
0x18001bdc3  sub     rsp, 40h
0x18001bdc7  mov     edi, r8d
0x18001bdca  mov     rbx, rdx
0x18001bdcd  mov     rsi, rcx
0x18001bdd0  xor     eax, eax
0x18001bdd2  mov     [rsp+68h+Source2], ax
0x18001bdd7  cmp     r8d, 4
0x18001bddb  jb      loc_18001C026
0x18001bde1  mov     r14d, [rdx]
0x18001bde4  add     rbx, 4
0x18001bde8  mov     [r11+10h], rbx
0x18001bdec  add     edi, 0FFFFFFFCh
0x18001bdef  mov     [r11+18h], edi
0x18001bdf3  cmp     r14d, 2
0x18001bdf7  jb      loc_18001C02D
0x18001bdfd  cmp     r14d, edi
0x18001be00  ja      loc_18001C026
0x18001be06  test    r14b, 1
0x18001be0a  jnz     loc_18001C00C
0x18001be10  xor     r15d, r15d
0x18001be13  cmp     r15d, r14d
0x18001be16  jnb     loc_18001C00C
0x18001be1c  mov     r12d, r15d
0x18001be1f  lea     rcx, [r15+rbx]; Source1
0x18001be23  mov     r8d, 2; Length
0x18001be29  lea     rdx, [rsp+68h+Source2]; Source2
0x18001be2e  call    cs:__imp_RtlCompareMemory
0x18001be34  cmp     rax, 2
0x18001be38  jz      short loc_18001BE40
0x18001be3a  add     r15d, 2
0x18001be3e  jmp     short loc_18001BE13
0x18001be40  lea     rax, [r14-2]
0x18001be44  cmp     r12, rax
0x18001be47  jnz     loc_18001C00C
0x18001be4d  mov     rdx, r14; uBytes
0x18001be50  mov     ecx, 40h ; '@'; uFlags
0x18001be55  call    cs:__imp_LocalAlloc
0x18001be5b  mov     [rsi+20h], rax
0x18001be5f  test    rax, rax
0x18001be62  jz      loc_18001C0B9
0x18001be68  mov     r8, r14; Size
0x18001be6b  mov     rdx, rbx; Src
0x18001be6e  mov     rcx, rax; void *
0x18001be71  call    memcpy_0
0x18001be76  add     rbx, r14
0x18001be79  mov     [rsp+68h+arg_8], rbx
0x18001be7e  sub     edi, r14d
0x18001be81  mov     [rsp+68h+arg_10], edi
0x18001be88  cmp     qword ptr [rsi+20h], 0
0x18001be8d  jz      loc_18001C031
0x18001be93  test    byte ptr [rsi+60h], 1
0x18001be97  jz      loc_18001C055
0x18001be9d  cmp     edi, 10h
0x18001bea0  jb      loc_18001C026
0x18001bea6  mov     rcx, [rsi+30h]
0x18001beaa  mov     eax, [rbx]
0x18001beac  mov     [rcx+8], eax
0x18001beaf  lea     edx, [rdi-4]
0x18001beb2  cmp     edx, 4
0x18001beb5  jb      loc_18001C026
0x18001bebb  mov     eax, [rbx+4]
0x18001bebe  mov     [rcx+0Ch], eax
0x18001bec1  add     edx, 0FFFFFFFCh
0x18001bec4  cmp     edx, 4
0x18001bec7  jb      loc_18001C026
0x18001becd  mov     eax, [rbx+8]
0x18001bed0  mov     [rcx+10h], eax
0x18001bed3  lea     eax, [rdx-4]
0x18001bed6  cmp     eax, 4
0x18001bed9  jb      loc_18001C026
0x18001bedf  mov     eax, [rbx+0Ch]
0x18001bee2  mov     [rcx+14h], eax
0x18001bee5  add     edi, 0FFFFFFF0h
0x18001bee8  cmp     edi, 10h
0x18001beeb  jb      loc_18001C026
0x18001bef1  mov     rcx, [rsi+38h]
0x18001bef5  mov     eax, [rbx+10h]
0x18001bef8  mov     [rcx+8], eax
0x18001befb  lea     edx, [rdi-4]
0x18001befe  cmp     edx, 4
0x18001bf01  jb      loc_18001C026
0x18001bf07  mov     eax, [rbx+14h]
0x18001bf0a  mov     [rcx+0Ch], eax
0x18001bf0d  add     edx, 0FFFFFFFCh
0x18001bf10  cmp     edx, 4
0x18001bf13  jb      loc_18001C026
0x18001bf19  mov     eax, [rbx+18h]
0x18001bf1c  mov     [rcx+10h], eax
0x18001bf1f  lea     eax, [rdx-4]
0x18001bf22  cmp     eax, 4
0x18001bf25  jb      loc_18001C026
0x18001bf2b  mov     eax, [rbx+1Ch]
0x18001bf2e  mov     [rcx+14h], eax
0x18001bf31  add     edi, 0FFFFFFF0h
0x18001bf34  cmp     edi, 2
0x18001bf37  jb      loc_18001C026
0x18001bf3d  movzx   eax, word ptr [rbx+20h]
0x18001bf41  add     rbx, 22h ; '"'
0x18001bf45  mov     [rsp+68h+arg_8], rbx
0x18001bf4a  add     edi, 0FFFFFFFEh
0x18001bf4d  mov     [rsp+68h+arg_10], edi
0x18001bf54  cmp     ax, [rsi+44h]
0x18001bf58  jnz     loc_18001C00C
0x18001bf5e  xor     r14d, r14d
0x18001bf61  movzx   eax, word ptr [rsi+44h]
0x18001bf65  cmp     r14d, eax
0x18001bf68  jnb     loc_18001C080
0x18001bf6e  cmp     edi, 10h
0x18001bf71  jb      loc_18001C026
0x18001bf77  mov     edx, r14d
0x18001bf7a  shl     rdx, 5
0x18001bf7e  mov     rcx, [rsi+48h]
0x18001bf82  mov     eax, [rbx]
0x18001bf84  mov     [rdx+rcx+8], eax
0x18001bf88  lea     r8d, [rdi-4]
0x18001bf8c  cmp     r8d, 4
0x18001bf90  jb      loc_18001C026
0x18001bf96  mov     eax, [rbx+4]
0x18001bf99  mov     [rdx+rcx+0Ch], eax
0x18001bf9d  add     r8d, 0FFFFFFFCh
0x18001bfa1  cmp     r8d, 4
0x18001bfa5  jb      short loc_18001C026
0x18001bfa7  mov     eax, [rbx+8]
0x18001bfaa  mov     [rdx+rcx+10h], eax
0x18001bfae  lea     eax, [r8-4]
0x18001bfb2  cmp     eax, 4
0x18001bfb5  jb      short loc_18001C026
0x18001bfb7  mov     eax, [rbx+0Ch]
0x18001bfba  mov     [rdx+rcx+14h], eax
0x18001bfbe  add     rbx, 10h
0x18001bfc2  mov     [rsp+68h+arg_8], rbx
0x18001bfc7  add     edi, 0FFFFFFF0h
0x18001bfca  mov     [rsp+68h+arg_10], edi
0x18001bfd1  mov     r15, [rsi+48h]
0x18001bfd5  add     r15, rdx
0x18001bfd8  mov     rax, [r15]
0x18001bfdb  mov     rcx, r15
0x18001bfde  mov     rax, [rax+8]
0x18001bfe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfe7  mov     [rsp+68h+var_48], eax
0x18001bfeb  mov     [rsp+68h+var_40], r15
0x18001bff0  lea     r8, [rsp+68h+var_48]
0x18001bff5  lea     rdx, [rsp+68h+var_38]
0x18001bffa  lea     rcx, [rsi+50h]
0x18001bffe  call    ??$insert@U?$pair@W4VAULT_SCHEMA_ELEMENT_ID@@PEAVCVaultSchemaElement@@@std@@$0A@@?$map@W4VAULT_SCHEMA_ELEMENT_ID@@PEAVCVaultSchemaElement@@U?$less@W4VAULT_SCHEMA_ELEMENT_ID@@@std@@V?$allocator@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@PEAVCVaultSchemaElement@@@std@@@4@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4VAULT_SCHEMA_ELEMENT_ID@@PEAVCVaultSchemaElement@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4VAULT_SCHEMA_ELEMENT_ID@@PEAVCVaultSchemaElement@@@1@@Z; std::map<VAULT_SCHEMA_ELEMENT_ID,CVaultSchemaElement *>::insert<std::pair<VAULT_SCHEMA_ELEMENT_ID,CVaultSchemaElement *>,0>(std::pair<VAULT_SCHEMA_ELEMENT_ID,CVaultSchemaElement *> &&)
0x18001c003  nop
0x18001c004  inc     r14d
0x18001c007  jmp     loc_18001BF61
0x18001c00c  mov     eax, 54Eh
0x18001c011  mov     rbx, [rsp+68h+arg_18]
0x18001c019  add     rsp, 40h
0x18001c01d  pop     r15
0x18001c01f  pop     r14
0x18001c021  pop     r12
0x18001c023  pop     rdi
0x18001c024  pop     rsi
0x18001c025  retn
0x18001c026  mov     eax, 7Ah ; 'z'
0x18001c02b  jmp     short loc_18001C011
0x18001c02d  mov     [rcx+20h], rax
0x18001c031  mov     edx, 2; uBytes
0x18001c036  lea     ecx, [rdx+3Eh]; uFlags
0x18001c039  call    cs:__imp_LocalAlloc
0x18001c03f  mov     rcx, rax
0x18001c042  mov     [rsi+20h], rax
0x18001c046  test    rax, rax
0x18001c049  jz      short loc_18001C0B9
0x18001c04b  xor     eax, eax
0x18001c04d  mov     [rcx], ax
0x18001c050  jmp     loc_18001BE93
0x18001c055  mov     r8, [rsi+28h]
0x18001c059  lea     rdx, [rsp+68h+arg_10]
0x18001c061  lea     rcx, [rsp+68h+arg_8]
0x18001c066  call    ??$VaultDeserialize@VCVaultSchemaElement@@@@YAKAEAPEAEAEAKAEAVCVaultSchemaElement@@@Z; VaultDeserialize<CVaultSchemaElement>(uchar * &,ulong &,CVaultSchemaElement &)
0x18001c06b  test    eax, eax
0x18001c06d  jnz     short loc_18001C011
0x18001c06f  mov     edi, [rsp+68h+arg_10]
0x18001c076  mov     rbx, [rsp+68h+arg_8]
0x18001c07b  jmp     loc_18001BE9D
0x18001c080  lea     rcx, [rsi+68h]
0x18001c084  lea     r8, [rsp+68h+arg_10]
0x18001c08c  lea     rdx, [rsp+68h+arg_8]
0x18001c091  call    ?DeserializeCollection@?$CVaultGenericPropertyCollection@W4ESchemaPropertyId@@$0A@@@QEAAKAEAPEAEAEAK@Z; CVaultGenericPropertyCollection<ESchemaPropertyId,0>::DeserializeCollection(uchar * &,ulong &)
0x18001c096  test    eax, eax
0x18001c098  jnz     loc_18001C011
0x18001c09e  lea     r9, [rsi+90h]
0x18001c0a5  lea     rdx, [rsi+0Ch]
0x18001c0a9  xor     r8d, r8d
0x18001c0ac  lea     ecx, [rax+2]
0x18001c0af  call    ?VaultCreateVaultSecurable@@YAKW4EVaultSecurableType@@AEBU_GUID@@PEAVCVaultSid@@PEAPEAVIVaultSecurable@@@Z; VaultCreateVaultSecurable(EVaultSecurableType,_GUID const &,CVaultSid *,IVaultSecurable * *)
0x18001c0b4  jmp     loc_18001C011
0x18001c0b9  mov     eax, 0Eh
0x18001c0be  jmp     loc_18001C011
```
