# I_ParseCatalog

- ea: `0x180045408`
- end: `0x1800455bf`
- name: `I_ParseCatalog`
- size: `439`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800455c8`

## callees

- `0x180010ab0`
- `0x180015624`
- `0x18003391a`
- `0x180044b10`
- `0x180045408`
- `0x18004cb6c`
- `0x18004dd2c`
- `0x18004e128`

## import_xrefs

- `securekernel!RtlCompareMemory` at `0x1800454ad`
- `securekernel!RtlCompareMemory` at `0x1800454ad`

## pseudocode

```c
__int64 __fastcall I_ParseCatalog(__int64 a1, __int64 a2, int a3, int a4, __int64 a5)
{
  __int64 v7; // r14
  __int64 v8; // r12
  __int64 v9; // rcx
  __int64 *v10; // rax
  int NamedCatalogAttributeValue; // ebx
  __int64 *i; // rbx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v18; // [rsp+60h] [rbp-48h] BYREF
  int v19; // [rsp+68h] [rbp-40h]

  v7 = a2 + 32;
  v19 = 0;
  v18 = 0;
  v8 = a1 + 72;
  v9 = a1 + 120;
  v10 = qword_180035A70;
  if ( (g_CiPolicyState & 0x10000) == 0 )
    v10 = (__int64 *)&qword_1800359F0;
  NamedCatalogAttributeValue = MinCrypK_VerifySignedDataKModeEx(
                                 a3,
                                 a4,
                                 0,
                                 0,
                                 (__int64)v10,
                                 v8,
                                 (void *)(a2 + 32),
                                 a1 + 168,
                                 v9);
  if ( NamedCatalogAttributeValue >= 0 )
  {
    if ( *(_DWORD *)v7 == 9
      && RtlCompareMemory(qword_180037590, *(const void **)(v7 + 8), 9u) == 9
      && (int)MinAsn1ParseCTL(v7 + 16, a2 + 112) >= 0 )
    {
      for ( i = &qword_180035990; *(_DWORD *)i; i += 4 )
      {
        v13 = *((_DWORD *)i + 4);
        if ( v13 == *(_DWORD *)(a2 + 240) && !memcmp_0((const void *)i[1], *(const void **)(a2 + 248), v13) )
        {
          *(_QWORD *)(a1 + 176) = i;
          if ( (unsigned __int8)MinAsn1FindExtensionMatchingValue(v15, v14, a2 + 272) )
            *(_DWORD *)(a1 + 64) |= 1u;
          NamedCatalogAttributeValue = I_GetNamedCatalogAttributeValue(a2, a2 + 272, v16, &v18);
          if ( NamedCatalogAttributeValue < 0 )
          {
            if ( NamedCatalogAttributeValue == -1073741275 )
              NamedCatalogAttributeValue = 0;
          }
          else
          {
            NamedCatalogAttributeValue = CipSetPlatformManifestFromPackageName(v8, &v18);
            if ( NamedCatalogAttributeValue < 0 )
              return (unsigned int)NamedCatalogAttributeValue;
          }
          if ( (int)MinAsn1ExtractContent(*(_QWORD *)(a2 + 264), *(unsigned int *)(a2 + 256), a5, a5 + 8) >= 0 )
            return (unsigned int)NamedCatalogAttributeValue;
          break;
        }
      }
    }
    return (unsigned int)-1073740760;
  }
  return (unsigned int)NamedCatalogAttributeValue;
}

```

## disassembly

```asm
0x180045408  push    rbx
0x18004540a  push    rsi
0x18004540b  push    rdi
0x18004540c  push    r12
0x18004540e  push    r14
0x180045410  push    r15
0x180045412  sub     rsp, 78h
0x180045416  mov     r10d, r9d
0x180045419  mov     r11, r8
0x18004541c  mov     r15, rdx
0x18004541f  mov     rsi, rcx
0x180045422  lea     r14, [rdx+20h]
0x180045426  xor     eax, eax
0x180045428  mov     [rsp+0A8h+var_48+4], rax
0x18004542d  mov     [rsp+0A8h+var_48], rax
0x180045432  lea     r12, [rcx+48h]
0x180045436  add     rcx, 78h ; 'x'
0x18004543a  lea     rdx, [rsi+0A8h]
0x180045441  test    byte ptr cs:g_CiPolicyState+2, 1
0x180045448  lea     r8, qword_1800359F0
0x18004544f  lea     rax, qword_180035A70
0x180045456  cmovz   rax, r8
0x18004545a  mov     [rsp+0A8h+var_68], rcx; __int64
0x18004545f  mov     [rsp+0A8h+var_70], rdx; __int64
0x180045464  mov     [rsp+0A8h+var_78], r14; void *
0x180045469  mov     qword ptr [rsp+0A8h+var_80], r12; int
0x18004546e  mov     [rsp+0A8h+var_88], rax; __int64
0x180045473  xor     r9d, r9d; int
0x180045476  xor     r8d, r8d; int
0x180045479  mov     edx, r10d; int
0x18004547c  mov     rcx, r11; int
0x18004547f  call    MinCrypK_VerifySignedDataKModeEx
0x180045484  mov     ebx, eax
0x180045486  mov     [rsp+0A8h+var_58], eax
0x18004548a  test    eax, eax
0x18004548c  js      loc_1800455AE
0x180045492  cmp     dword ptr [r14], 9
0x180045496  jnz     loc_1800455A5
0x18004549c  mov     r8d, 9; Length
0x1800454a2  mov     rdx, [r14+8]; Source2
0x1800454a6  lea     rcx, qword_180037590; Source1
0x1800454ad  call    cs:__imp_RtlCompareMemory
0x1800454b4  nop     dword ptr [rax+rax+00h]
0x1800454b9  cmp     rax, 9
0x1800454bd  jnz     loc_1800455A5
0x1800454c3  lea     rcx, [r14+10h]
0x1800454c7  lea     rdx, [r15+70h]
0x1800454cb  call    MinAsn1ParseCTL
0x1800454d0  test    eax, eax
0x1800454d2  js      loc_1800455A5
0x1800454d8  lea     rbx, qword_180035990
0x1800454df  mov     [rsp+0A8h+var_50], rbx
0x1800454e4  mov     r14d, [rbx]
0x1800454e7  test    r14d, r14d
0x1800454ea  jz      loc_1800455A5
0x1800454f0  mov     eax, [rbx+10h]
0x1800454f3  cmp     eax, [r15+0F0h]
0x1800454fa  jnz     short loc_180045513
0x1800454fc  mov     r8d, eax; Size
0x1800454ff  mov     rdx, [r15+0F8h]; Buf2
0x180045506  mov     rcx, [rbx+8]; Buf1
0x18004550a  call    memcmp_0
0x18004550f  test    eax, eax
0x180045511  jz      short loc_180045519
0x180045513  add     rbx, 20h ; ' '
0x180045517  jmp     short loc_1800454DF
0x180045519  test    r14d, r14d
0x18004551c  jz      loc_1800455A5
0x180045522  mov     [rsi+0B0h], rbx
0x180045529  lea     rbx, [r15+110h]
0x180045530  mov     r8, rbx
0x180045533  call    MinAsn1FindExtensionMatchingValue
0x180045538  test    al, al
0x18004553a  jz      short loc_180045540
0x18004553c  or      dword ptr [rsi+40h], 1
0x180045540  lea     r9, [rsp+0A8h+var_48]
0x180045545  mov     rdx, rbx
0x180045548  mov     rcx, r15
0x18004554b  call    I_GetNamedCatalogAttributeValue
0x180045550  mov     ebx, eax
0x180045552  mov     [rsp+0A8h+var_58], eax
0x180045556  test    eax, eax
0x180045558  js      short loc_180045573
0x18004555a  lea     rdx, [rsp+0A8h+var_48]
0x18004555f  mov     rcx, r12
0x180045562  call    CipSetPlatformManifestFromPackageName
0x180045567  mov     ebx, eax
0x180045569  mov     [rsp+0A8h+var_58], eax
0x18004556d  test    eax, eax
0x18004556f  js      short loc_1800455AE
0x180045571  jmp     short loc_180045582
0x180045573  xor     eax, eax
0x180045575  cmp     ebx, 0C0000225h
0x18004557b  cmovz   ebx, eax
0x18004557e  mov     [rsp+0A8h+var_58], ebx
0x180045582  mov     r8, [rsp+0A8h+arg_20]
0x18004558a  lea     r9, [r8+8]
0x18004558e  mov     edx, [r15+100h]
0x180045595  mov     rcx, [r15+108h]
0x18004559c  call    MinAsn1ExtractContent
0x1800455a1  test    eax, eax
0x1800455a3  jns     short loc_1800455AE
0x1800455a5  mov     ebx, 0C0000428h
0x1800455aa  mov     [rsp+0A8h+var_58], ebx
0x1800455ae  mov     eax, ebx
0x1800455b0  add     rsp, 78h
0x1800455b4  pop     r15
0x1800455b6  pop     r14
0x1800455b8  pop     r12
0x1800455ba  pop     rdi
0x1800455bb  pop     rsi
0x1800455bc  pop     rbx
0x1800455bd  retn
0x18004fe2b  push    rbp
0x18004fe2d  sub     rsp, 50h
0x18004fe31  mov     rbp, rdx
0x18004fe34  movzx   eax, cl
0x18004fe37  mov     ecx, [rbp+50h]
0x18004fe3a  mov     edx, 0C00000E8h
0x18004fe3f  test    eax, eax
0x18004fe41  cmovnz  ecx, edx
0x18004fe44  mov     [rbp+50h], ecx
0x18004fe47  add     rsp, 50h
0x18004fe4b  pop     rbp
0x18004fe4c  retn
```
