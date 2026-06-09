# SkciValidateAmeCertChain

- ea: `0x1800115e0`
- end: `0x180011741`
- name: `SkciValidateAmeCertChain`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001156c`
- `0x1800115e0`
- `0x1800118c8`
- `0x180011ac0`
- `0x1800187d4`
- `0x180018a3c`

## import_xrefs

- `securekernel!RtlCompareMemory` at `0x1800116d5`
- `securekernel!RtlCompareMemory` at `0x1800116fe`
- `securekernel!RtlCompareMemory` at `0x1800116d5`
- `securekernel!RtlCompareMemory` at `0x1800116fe`

## pseudocode

```c
__int64 __fastcall SkciValidateAmeCertChain(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int CertificateThumbprint; // ebx
  __int64 v7; // rdi
  __int64 v9; // r8
  int v10; // eax
  __int64 v11; // r9
  __int64 LeafKeyFromPolicy; // rax
  char v13; // dl
  __int64 v14; // r9
  __int64 v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int128 v18; // [rsp+20h] [rbp-38h] BYREF
  __int128 v19; // [rsp+30h] [rbp-28h]
  __int128 v20; // [rsp+40h] [rbp-18h]

  v18 = 0;
  v19 = 0;
  v20 = 0;
  if ( !a3 )
  {
    CertificateThumbprint = -1073741583;
LABEL_3:
    v7 = v19;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    CertificateThumbprint = -1073741582;
    goto LABEL_3;
  }
  CertificateThumbprint = SkcipBuildCertificateChain(a1, a2, &v18);
  if ( CertificateThumbprint < 0 )
    goto LABEL_3;
  v7 = v19;
  if ( (_DWORD)v18
    && (_QWORD)v19
    && (DWORD2(v18) & 0xFFFF0000) == 0
    && (DWORD2(v18) & 0x20000) == 0
    && (v10 = *(_DWORD *)(v19 + 16)) != 0 )
  {
    v11 = *(_QWORD *)(v19 + 8) + 16LL * (unsigned int)(v10 - 1);
  }
  else
  {
    v11 = 0;
  }
  LeafKeyFromPolicy = MincryptGetLeafKeyFromPolicy(&v18, DWORD2(v18), v9, v11);
  v15 = LeafKeyFromPolicy;
  if ( v14
    && LeafKeyFromPolicy
    && ((v16 = (unsigned int)g_CiOptions, (g_CiOptions & 8) != 0) && (v13 & 4) != 0
     || *(_DWORD *)(v7 + 48) == 3
     && *(_DWORD *)(v7 + 16) == 3
     && *(_DWORD *)v14 == 8
     && RtlCompareMemory(*(const void **)(v14 + 8), &rgbMicrosoftAzureAmeRoot0_PubKeyInfo, 8u) == 8
     && (v17 = *(_QWORD *)(v7 + 40), *(_WORD *)(v17 + 80) == 8)
     && RtlCompareMemory(
          *(const void **)(v17 + 72),
          "deadbeefM\x00i\x00c\x00r\x00o\x00s\x00o\x00f\x00t\x00 \x00W\x00i\x00n\x00d\x00o\x00w\x00s",
          8u) == 8) )
  {
    CertificateThumbprint = SkciGetCertificateThumbprint(v16, &v18, a4);
    if ( CertificateThumbprint >= 0 )
      CertificateThumbprint = SkcipConvertToRsaBlob(v15, a3);
  }
  else
  {
    CertificateThumbprint = -1073740760;
  }
LABEL_4:
  if ( (_DWORD)v18 )
    SIPolicyFree(v7);
  return (unsigned int)CertificateThumbprint;
}

```

## disassembly

```asm
0x1800115e0  push    rbp
0x1800115e2  push    rbx
0x1800115e3  push    rsi
0x1800115e4  push    rdi
0x1800115e5  push    r14
0x1800115e7  push    r15
0x1800115e9  mov     rbp, rsp
0x1800115ec  sub     rsp, 58h
0x1800115f0  xorps   xmm0, xmm0
0x1800115f3  mov     r14, r9
0x1800115f6  mov     r15, r8
0x1800115f9  movups  [rbp+var_38], xmm0
0x1800115fd  movups  [rbp+var_28], xmm0
0x180011601  movups  [rbp+var_18], xmm0
0x180011605  test    r8, r8
0x180011608  jnz     short loc_180011631
0x18001160a  mov     ebx, 0C00000F1h
0x18001160f  mov     rdi, qword ptr [rbp+var_28]
0x180011613  cmp     dword ptr [rbp+var_38], 0
0x180011617  jz      short loc_180011621
0x180011619  mov     rcx, rdi
0x18001161c  call    SIPolicyFree
0x180011621  mov     eax, ebx
0x180011623  add     rsp, 58h
0x180011627  pop     r15
0x180011629  pop     r14
0x18001162b  pop     rdi
0x18001162c  pop     rsi
0x18001162d  pop     rbx
0x18001162e  pop     rbp
0x18001162f  retn
0x180011631  test    r14, r14
0x180011634  jnz     short loc_18001163D
0x180011636  mov     ebx, 0C00000F2h
0x18001163b  jmp     short loc_18001160F
0x18001163d  lea     r8, [rbp+var_38]
0x180011641  call    SkcipBuildCertificateChain
0x180011646  mov     ebx, eax
0x180011648  test    eax, eax
0x18001164a  js      short loc_18001160F
0x18001164c  cmp     dword ptr [rbp+var_38], 0
0x180011650  mov     rdi, qword ptr [rbp+var_28]
0x180011654  mov     edx, dword ptr [rbp+var_38+8]
0x180011657  jz      short loc_180011681
0x180011659  test    rdi, rdi
0x18001165c  jz      short loc_180011681
0x18001165e  test    edx, 0FFFF0000h
0x180011664  jnz     short loc_180011681
0x180011666  bt      edx, 11h
0x18001166a  jb      short loc_180011681
0x18001166c  mov     eax, [rdi+10h]
0x18001166f  test    eax, eax
0x180011671  jz      short loc_180011681
0x180011673  lea     r9d, [rax-1]
0x180011677  shl     r9, 4
0x18001167b  add     r9, [rdi+8]
0x18001167f  jmp     short loc_180011684
0x180011681  xor     r9d, r9d
0x180011684  lea     rcx, [rbp+var_38]
0x180011688  call    MincryptGetLeafKeyFromPolicy
0x18001168d  mov     rsi, rax
0x180011690  test    r9, r9
0x180011693  jz      loc_180011737
0x180011699  test    rax, rax
0x18001169c  jz      loc_180011737
0x1800116a2  mov     ecx, cs:g_CiOptions
0x1800116a8  mov     ebx, 8
0x1800116ad  test    bl, cl
0x1800116af  jz      short loc_1800116B6
0x1800116b1  test    dl, 4
0x1800116b4  jnz     short loc_18001170F
0x1800116b6  cmp     dword ptr [rdi+30h], 3
0x1800116ba  jnz     short loc_180011737
0x1800116bc  cmp     dword ptr [rdi+10h], 3
0x1800116c0  jnz     short loc_180011737
0x1800116c2  cmp     [r9], ebx
0x1800116c5  jnz     short loc_180011737
0x1800116c7  mov     rcx, [r9+8]; Source1
0x1800116cb  lea     rdx, rgbMicrosoftAzureAmeRoot0_PubKeyInfo; Source2
0x1800116d2  mov     r8, rbx; Length
0x1800116d5  call    cs:__imp_RtlCompareMemory
0x1800116dc  nop     dword ptr [rax+rax+00h]
0x1800116e1  cmp     rax, rbx
0x1800116e4  jnz     short loc_180011737
0x1800116e6  mov     rcx, [rdi+28h]
0x1800116ea  cmp     [rcx+50h], bx
0x1800116ee  jnz     short loc_180011737
0x1800116f0  mov     rcx, [rcx+48h]; Source1
0x1800116f4  lea     rdx, rgbMicrosoftAzureSkCertDomain0_Name; "deadbeefM\x00i\x00c\x00r\x00o\x00s\x00o"...
0x1800116fb  mov     r8, rbx; Length
0x1800116fe  call    cs:__imp_RtlCompareMemory
0x180011705  nop     dword ptr [rax+rax+00h]
0x18001170a  cmp     rax, rbx
0x18001170d  jnz     short loc_180011737
0x18001170f  mov     r8, r14
0x180011712  lea     rdx, [rbp+var_38]
0x180011716  call    SkciGetCertificateThumbprint
0x18001171b  mov     ebx, eax
0x18001171d  test    eax, eax
0x18001171f  js      loc_180011613
0x180011725  mov     rdx, r15
0x180011728  mov     rcx, rsi
0x18001172b  call    SkcipConvertToRsaBlob
0x180011730  mov     ebx, eax
0x180011732  jmp     loc_180011613
0x180011737  mov     ebx, 0C0000428h
0x18001173c  jmp     loc_180011613
```
