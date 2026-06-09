# SkpsReadPolicyMetadata

- ea: `0x1400b1f70`
- end: `0x1400b215b`
- name: `SkpsReadPolicyMetadata`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14002b5f4`

## callees

- `0x14002ba08`
- `0x140063694`
- `0x1400b1f70`
- `0x1400b2164`
- `0x1400fc664`
- `0x1400fe7e0`
- `0x1400feba8`

## string_xrefs

- `0x1400b1fc8`: `SkpsReadPolicyMetadata`
- `0x1400b2006`: `SkpsReadPolicyMetadata: Failed to lookup policy metadata, 0x%x.\n`
- `0x1400b2067`: `SkpsReadPolicyMetadata: Failed to lookup policy metadata, 0x%x.\n`
- `0x1400b213b`: `SkpsReadPolicyMetadata: Exception generated with status 0x%x.\n`
- `0x1400b2120`: `SkpsReadPolicyMetadata: TrustletId incorrect: TrustletId = %I64u, Process->Trustlet.Identity = %I64u.\n`
- `0x1400b20d6`: `SkpsReadPolicyMetadata: Owner process verification failed with error 0x%x.\n`
- `0x1400b2112`: `SkpsReadPolicyMetadata: PolicyMetadata missing either parent SD or parent SD revision.\n`

## pseudocode

```c
__int64 __fastcall SkpsReadPolicyMetadata(__int64 a1)
{
  int SecureImageInfo; // eax
  unsigned int v3; // ebx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // rdx
  int v9; // eax
  __int128 v10; // [rsp+28h] [rbp-80h] BYREF
  __int64 v11; // [rsp+38h] [rbp-70h]
  __int128 v12; // [rsp+40h] [rbp-68h] BYREF
  __int128 v13; // [rsp+50h] [rbp-58h]
  __int128 v14; // [rsp+60h] [rbp-48h]
  __int64 v15; // [rsp+70h] [rbp-38h]
  __int64 v16; // [rsp+78h] [rbp-30h] BYREF
  __int128 v17; // [rsp+88h] [rbp-20h]

  v10 = 0;
  v11 = 0;
  v17 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  SecureImageInfo = SkmmGetSecureImageInfo(*(_QWORD *)(a1 + 168), &v16);
  v3 = SecureImageInfo;
  if ( SecureImageInfo < 0 )
  {
    DbgPrint("%hs: SkmmGetSecureImageInfo returned 0x%x.\n", "SkpsReadPolicyMetadata", SecureImageInfo);
    return v3;
  }
  v5 = RtlLookupImagePolicyMetadata(*(_QWORD *)(a1 + 176), DWORD2(v17), &v10);
  v6 = v5;
  if ( v5 < 0 )
    goto LABEL_4;
  if ( !(_QWORD)v10 )
    return 3221225506LL;
  BYTE4(v12) = 1;
  v15 = a1;
  *(_QWORD *)&v13 = RtlReadULong64FromUser(v10 + 8);
  v5 = RtlWalkImagePolicies(&v10, SkpspReadPolicyMetadataCallback, &v12);
  v6 = v5;
  if ( v5 < 0 )
  {
LABEL_4:
    DbgPrint("SkpsReadPolicyMetadata: Failed to lookup policy metadata, 0x%x.\n", v5);
    return v6;
  }
  v7 = *(_QWORD *)(a1 + 432);
  v8 = v13;
  if ( !v7 )
  {
    *(_QWORD *)(a1 + 432) = v13;
    v7 = v8;
  }
  if ( v8 && v8 == v7 )
  {
    if ( (((unsigned int)v12 >> 2) & 1) != 0 && (v12 & 2) != 0 && *((_QWORD *)&v14 + 1) )
    {
      v9 = SkpsVerifyParentProcess((unsigned int)v14, *((_QWORD *)&v13 + 1));
      v6 = v9;
      if ( v9 < 0 )
      {
        DbgPrint("SkpsReadPolicyMetadata: Owner process verification failed with error 0x%x.\n", v9);
        return v6;
      }
LABEL_20:
      *(_OWORD *)(a1 + 472) = v10;
      *(_QWORD *)(a1 + 488) = v11;
      _InterlockedOr((volatile signed __int32 *)a1, DWORD2(v12));
      return v6;
    }
    if ( (((unsigned int)v12 >> 2) & 1) == 0 && (v12 & 2) == 0 )
      goto LABEL_20;
    DbgPrint("SkpsReadPolicyMetadata: PolicyMetadata missing either parent SD or parent SD revision.\n");
  }
  else
  {
    DbgPrint(
      "SkpsReadPolicyMetadata: TrustletId incorrect: TrustletId = %I64u, Process->Trustlet.Identity = %I64u.\n",
      v8,
      v7);
  }
  return 3221225506LL;
}

```

## disassembly

```asm
0x1400b1f70  mov     r11, rsp
0x1400b1f73  mov     [r11+8], rbx
0x1400b1f77  push    rdi
0x1400b1f78  sub     rsp, 0A0h
0x1400b1f7f  mov     rdi, rcx
0x1400b1f82  xorps   xmm0, xmm0
0x1400b1f85  xor     eax, eax
0x1400b1f87  movups  [rsp+0A8h+var_80], xmm0
0x1400b1f8c  mov     [r11-70h], rax
0x1400b1f90  xorps   xmm1, xmm1
0x1400b1f93  movups  xmmword ptr [r11-20h], xmm1
0x1400b1f98  movups  [rsp+0A8h+var_68], xmm0
0x1400b1f9d  movups  [rsp+0A8h+var_58], xmm0
0x1400b1fa2  movups  [rsp+0A8h+var_48], xmm0
0x1400b1fa7  mov     [r11-38h], rax
0x1400b1fab  lea     rdx, [r11-30h]
0x1400b1faf  mov     rcx, [rcx+0A8h]
0x1400b1fb6  call    SkmmGetSecureImageInfo
0x1400b1fbb  mov     ebx, eax
0x1400b1fbd  mov     [rsp+0A8h+var_88], eax
0x1400b1fc1  test    eax, eax
0x1400b1fc3  jns     short loc_1400B1FE2
0x1400b1fc5  mov     r8d, eax
0x1400b1fc8  lea     rdx, aSkpsreadpolicy_4; "SkpsReadPolicyMetadata"
0x1400b1fcf  lea     rcx, aHsSkmmgetsecur; "%hs: SkmmGetSecureImageInfo returned 0x"...
0x1400b1fd6  call    DbgPrint
0x1400b1fdb  mov     eax, ebx
0x1400b1fdd  jmp     loc_1400B2149
0x1400b1fe2  mov     edx, [rsp+0A8h+var_18]
0x1400b1fe9  lea     r8, [rsp+0A8h+var_80]
0x1400b1fee  mov     rcx, [rdi+0B0h]
0x1400b1ff5  call    RtlLookupImagePolicyMetadata
0x1400b1ffa  mov     ebx, eax
0x1400b1ffc  mov     [rsp+0A8h+var_88], eax
0x1400b2000  test    eax, eax
0x1400b2002  jns     short loc_1400B2019
0x1400b2004  mov     edx, eax
0x1400b2006  lea     rcx, aSkpsreadpolicy_2; "SkpsReadPolicyMetadata: Failed to looku"...
0x1400b200d  call    DbgPrint
0x1400b2012  mov     eax, ebx
0x1400b2014  jmp     loc_1400B2149
0x1400b2019  mov     rcx, qword ptr [rsp+0A8h+var_80]
0x1400b201e  test    rcx, rcx
0x1400b2021  jnz     short loc_1400B202D
0x1400b2023  mov     eax, 0C0000022h
0x1400b2028  jmp     loc_1400B2149
0x1400b202d  mov     byte ptr [rsp+0A8h+var_68+4], 1
0x1400b2032  mov     [rsp+0A8h+var_38], rdi
0x1400b2037  add     rcx, 8
0x1400b203b  call    RtlReadULong64FromUser
0x1400b2040  mov     qword ptr [rsp+0A8h+var_58], rax
0x1400b2045  lea     r8, [rsp+0A8h+var_68]
0x1400b204a  lea     rdx, SkpspReadPolicyMetadataCallback
0x1400b2051  lea     rcx, [rsp+0A8h+var_80]
0x1400b2056  call    RtlWalkImagePolicies
0x1400b205b  mov     ebx, eax
0x1400b205d  mov     [rsp+0A8h+var_88], eax
0x1400b2061  test    eax, eax
0x1400b2063  jns     short loc_1400B207A
0x1400b2065  mov     edx, eax
0x1400b2067  lea     rcx, aSkpsreadpolicy_2; "SkpsReadPolicyMetadata: Failed to looku"...
0x1400b206e  call    DbgPrint
0x1400b2073  mov     eax, ebx
0x1400b2075  jmp     loc_1400B2149
0x1400b207a  mov     r8, [rdi+1B0h]
0x1400b2081  mov     rdx, qword ptr [rsp+0A8h+var_58]
0x1400b2086  test    r8, r8
0x1400b2089  jnz     short loc_1400B2095
0x1400b208b  mov     [rdi+1B0h], rdx
0x1400b2092  mov     r8, rdx
0x1400b2095  test    rdx, rdx
0x1400b2098  jz      loc_1400B2120
0x1400b209e  cmp     rdx, r8
0x1400b20a1  jnz     short loc_1400B2120
0x1400b20a3  mov     ecx, dword ptr [rsp+0A8h+var_68]
0x1400b20a7  mov     eax, ecx
0x1400b20a9  shr     eax, 2
0x1400b20ac  and     eax, 1
0x1400b20af  jz      short loc_1400B20E6
0x1400b20b1  test    cl, 2
0x1400b20b4  jz      short loc_1400B20E6
0x1400b20b6  mov     r8, qword ptr [rsp+0A8h+var_48+8]
0x1400b20bb  test    r8, r8
0x1400b20be  jz      short loc_1400B20E6
0x1400b20c0  mov     rdx, qword ptr [rsp+0A8h+var_58+8]
0x1400b20c5  mov     ecx, dword ptr [rsp+0A8h+var_48]
0x1400b20c9  call    SkpsVerifyParentProcess
0x1400b20ce  mov     ebx, eax
0x1400b20d0  test    eax, eax
0x1400b20d2  jns     short loc_1400B20EF
0x1400b20d4  mov     edx, eax
0x1400b20d6  lea     rcx, aSkpsreadpolicy_1; "SkpsReadPolicyMetadata: Owner process v"...
0x1400b20dd  call    DbgPrint
0x1400b20e2  mov     eax, ebx
0x1400b20e4  jmp     short loc_1400B2149
0x1400b20e6  test    eax, eax
0x1400b20e8  jnz     short loc_1400B2112
0x1400b20ea  test    cl, 2
0x1400b20ed  jnz     short loc_1400B2112
0x1400b20ef  movups  xmm0, [rsp+0A8h+var_80]
0x1400b20f4  movups  xmmword ptr [rdi+1D8h], xmm0
0x1400b20fb  movsd   xmm1, [rsp+0A8h+var_70]
0x1400b2101  movsd   qword ptr [rdi+1E8h], xmm1
0x1400b2109  mov     eax, dword ptr [rsp+0A8h+var_68+8]
0x1400b210d  lock or [rdi], eax
0x1400b2110  jmp     short loc_1400B20E2
0x1400b2112  lea     rcx, aSkpsreadpolicy_3; "SkpsReadPolicyMetadata: PolicyMetadata "...
0x1400b2119  call    DbgPrint
0x1400b211e  jmp     short loc_1400B212C
0x1400b2120  lea     rcx, aSkpsreadpolicy; "SkpsReadPolicyMetadata: TrustletId inco"...
0x1400b2127  call    DbgPrint
0x1400b212c  mov     eax, 0C0000022h
0x1400b2131  jmp     short loc_1400B2149
0x1400b2133  mov     ebx, eax
0x1400b2135  mov     [rsp+0A8h+var_88], eax
0x1400b2139  mov     edx, eax
0x1400b213b  lea     rcx, aSkpsreadpolicy_0; "SkpsReadPolicyMetadata: Exception gener"...
0x1400b2142  call    DbgPrint
0x1400b2147  mov     eax, ebx
0x1400b2149  mov     rbx, [rsp+0A8h+arg_0]
0x1400b2151  add     rsp, 0A0h
0x1400b2158  pop     rdi
0x1400b2159  retn
```
