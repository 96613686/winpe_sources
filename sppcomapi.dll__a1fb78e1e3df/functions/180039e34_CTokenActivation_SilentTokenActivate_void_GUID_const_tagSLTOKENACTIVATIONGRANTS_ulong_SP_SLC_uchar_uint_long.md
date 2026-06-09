# CTokenActivation::SilentTokenActivate(void *,_GUID const *,_tagSLTOKENACTIVATIONGRANTS *,ulong,SP_SLC<uchar> &,uint &,long *)

- ea: `0x180039e34`
- end: `0x18003a013`
- name: `?SilentTokenActivate@CTokenActivation@@IEAAJPEAXPEBU_GUID@@PEAU_tagSLTOKENACTIVATIONGRANTS@@KAEAV?$SP_SLC@E@@AEAIPEAJ@Z`
- size: `479`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int, HLOCAL *, _DWORD *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003a020`

## callees

- `0x180003520`
- `0x180004288`
- `0x180039e34`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039f51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039f6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039fe7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039f51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039f6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039fe7`
- `sppcext!SLSignTokenActivationChallenge` at `0x180039f19`
- `sppcext!SLSignTokenActivationChallenge` at `0x180039f19`
- `sppcext!SLFreeTokenActivationCertificates` at `0x180039f83`
- `sppcext!SLFreeTokenActivationCertificates` at `0x180039f83`
- `sppcext!SLGetTokenActivationCertificates` at `0x180039e73`
- `sppcext!SLGetTokenActivationCertificates` at `0x180039e73`
- `sppcext!SLGenerateTokenActivationChallenge` at `0x180039eb7`
- `sppcext!SLGenerateTokenActivationChallenge` at `0x180039eb7`
- `sppcext!SLDepositTokenActivationResponse` at `0x180039fd1`
- `sppcext!SLDepositTokenActivationResponse` at `0x180039fd1`

## pseudocode

```c
__int64 __fastcall CTokenActivation::SilentTokenActivate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        HLOCAL *a6,
        _DWORD *a7,
        int *a8)
{
  int v10; // eax
  int v11; // esi
  unsigned int v12; // ebx
  __int64 v13; // rcx
  HLOCAL *v14; // rdi
  _DWORD *v15; // r14
  _DWORD *v16; // rax
  int v17; // ebx
  int v19; // [rsp+50h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-20h] BYREF
  HLOCAL v21; // [rsp+60h] [rbp-18h] BYREF
  _DWORD *v22; // [rsp+68h] [rbp-10h] BYREF
  int v23; // [rsp+C0h] [rbp+48h] BYREF
  int v24; // [rsp+C4h] [rbp+4Ch]

  v24 = HIDWORD(a1);
  v22 = 0;
  v21 = 0;
  v19 = 0;
  v23 = 0;
  hMem = 0;
  v10 = SLGetTokenActivationCertificates(a4, a5, &v22);
  v11 = -1073417467;
  v12 = v10;
  if ( v10 == -1073417467 )
    goto LABEL_10;
  if ( v10 < 0
    || (v14 = a6, v15 = a7, !*a6) && (v10 = SLGenerateTokenActivationChallenge(a2, a3, a7, a6), v12 = v10, v10 < 0) )
  {
    v13 = (unsigned int)v10;
LABEL_4:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
    goto LABEL_11;
  }
  v16 = v22;
  v17 = 0;
  v19 = 0;
  v23 = 0;
  if ( !*v22 )
  {
LABEL_10:
    v12 = 0;
    *a8 = v11;
  }
  else
  {
    while ( 1 )
    {
      v11 = SLSignTokenActivationChallenge(
              *(_QWORD *)&v16[2 * v17 + 2],
              (unsigned int)*v15,
              *v14,
              0,
              1,
              &v19,
              &v21,
              &v23,
              &hMem);
      if ( v11 >= 0 )
        break;
      v16 = v22;
      if ( (unsigned int)++v17 >= *v22 )
        goto LABEL_10;
    }
    v12 = SLDepositTokenActivationResponse(a2, a3, (unsigned int)*v15, *v14, v19, v21, v23, hMem);
    if ( *v14 )
    {
      LocalFree(*v14);
      *v14 = 0;
    }
    *v15 = 0;
    if ( (v12 & 0x80000000) != 0 )
    {
      v13 = v12;
      goto LABEL_4;
    }
    *a8 = 0;
  }
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v21 )
  {
    LocalFree(v21);
    v21 = 0;
  }
  if ( v22 )
    SLFreeTokenActivationCertificates();
  return v12;
}

```

## disassembly

```asm
0x180039e34  mov     [rsp-40h+arg_0], rcx
0x180039e39  push    rbp
0x180039e3a  push    rbx
0x180039e3b  push    rsi
0x180039e3c  push    rdi
0x180039e3d  push    r12
0x180039e3f  push    r13
0x180039e41  push    r14
0x180039e43  push    r15
0x180039e45  mov     rbp, rsp
0x180039e48  sub     rsp, 78h
0x180039e4c  xor     r13d, r13d
0x180039e4f  mov     r15, r8
0x180039e52  mov     r12, rdx
0x180039e55  mov     [rbp+var_10], r13
0x180039e59  mov     edx, [rbp+arg_20]
0x180039e5c  lea     r8, [rbp+var_10]
0x180039e60  mov     rcx, r9
0x180039e63  mov     [rbp+var_18], r13
0x180039e67  mov     [rbp+var_28], r13d
0x180039e6b  mov     dword ptr [rbp+arg_0], r13d
0x180039e6f  mov     [rbp+hMem], r13
0x180039e73  call    cs:__imp_SLGetTokenActivationCertificates
0x180039e7a  nop     dword ptr [rax+rax+00h]
0x180039e7f  mov     esi, 0C004F305h
0x180039e84  mov     ebx, eax
0x180039e86  cmp     eax, esi
0x180039e88  jz      loc_180039F35
0x180039e8e  test    eax, eax
0x180039e90  jns     short loc_180039E9E
0x180039e92  mov     ecx, eax
0x180039e94  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180039e99  jmp     loc_180039F41
0x180039e9e  mov     rdi, [rbp+arg_28]
0x180039ea2  mov     r14, [rbp+arg_30]
0x180039ea6  cmp     [rdi], r13
0x180039ea9  jnz     short loc_180039EC9
0x180039eab  mov     r9, rdi
0x180039eae  mov     r8, r14
0x180039eb1  mov     rdx, r15
0x180039eb4  mov     rcx, r12
0x180039eb7  call    cs:__imp_SLGenerateTokenActivationChallenge
0x180039ebe  nop     dword ptr [rax+rax+00h]
0x180039ec3  mov     ebx, eax
0x180039ec5  test    eax, eax
0x180039ec7  js      short loc_180039E92
0x180039ec9  mov     rax, [rbp+var_10]
0x180039ecd  mov     ebx, r13d
0x180039ed0  mov     [rbp+var_28], r13d
0x180039ed4  mov     dword ptr [rbp+arg_0], r13d
0x180039ed8  cmp     [rax], r13d
0x180039edb  jbe     short loc_180039F35
0x180039edd  mov     r8, [rdi]
0x180039ee0  lea     rdx, [rbp+hMem]
0x180039ee4  mov     [rsp+78h+var_38], rdx
0x180039ee9  xor     r9d, r9d
0x180039eec  lea     rdx, [rbp+arg_0]
0x180039ef0  mov     ecx, ebx
0x180039ef2  mov     [rsp+78h+var_40], rdx
0x180039ef7  lea     rdx, [rbp+var_18]
0x180039efb  mov     [rsp+78h+var_48], rdx
0x180039f00  lea     rdx, [rbp+var_28]
0x180039f04  mov     [rsp+78h+var_50], rdx
0x180039f09  mov     edx, [r14]
0x180039f0c  mov     rcx, [rax+rcx*8+8]
0x180039f11  mov     [rsp+78h+var_58], 1
0x180039f19  call    cs:__imp_SLSignTokenActivationChallenge
0x180039f20  nop     dword ptr [rax+rax+00h]
0x180039f25  mov     esi, eax
0x180039f27  test    eax, eax
0x180039f29  jns     short loc_180039FA3
0x180039f2b  mov     rax, [rbp+var_10]
0x180039f2f  inc     ebx
0x180039f31  cmp     ebx, [rax]
0x180039f33  jb      short loc_180039EDD
0x180039f35  mov     rax, [rbp+arg_38]
0x180039f3c  mov     ebx, r13d
0x180039f3f  mov     [rax], esi
0x180039f41  mov     ecx, ebx
0x180039f43  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180039f48  mov     rcx, [rbp+hMem]; hMem
0x180039f4c  test    rcx, rcx
0x180039f4f  jz      short loc_180039F61
0x180039f51  call    cs:__imp_LocalFree
0x180039f58  nop     dword ptr [rax+rax+00h]
0x180039f5d  mov     [rbp+hMem], r13
0x180039f61  mov     rcx, [rbp+var_18]; hMem
0x180039f65  test    rcx, rcx
0x180039f68  jz      short loc_180039F7A
0x180039f6a  call    cs:__imp_LocalFree
0x180039f71  nop     dword ptr [rax+rax+00h]
0x180039f76  mov     [rbp+var_18], r13
0x180039f7a  mov     rcx, [rbp+var_10]
0x180039f7e  test    rcx, rcx
0x180039f81  jz      short loc_180039F8F
0x180039f83  call    cs:__imp_SLFreeTokenActivationCertificates
0x180039f8a  nop     dword ptr [rax+rax+00h]
0x180039f8f  mov     eax, ebx
0x180039f91  add     rsp, 78h
0x180039f95  pop     r15
0x180039f97  pop     r14
0x180039f99  pop     r13
0x180039f9b  pop     r12
0x180039f9d  pop     rdi
0x180039f9e  pop     rsi
0x180039f9f  pop     rbx
0x180039fa0  pop     rbp
0x180039fa1  retn
0x180039fa3  mov     ecx, dword ptr [rbp+arg_0]
0x180039fa6  mov     rdx, [rbp+var_18]
0x180039faa  mov     r8d, [rbp+var_28]
0x180039fae  mov     rax, [rbp+hMem]
0x180039fb2  mov     r9, [rdi]
0x180039fb5  mov     [rsp+78h+var_40], rax
0x180039fba  mov     dword ptr [rsp+78h+var_48], ecx
0x180039fbe  mov     rcx, r12
0x180039fc1  mov     [rsp+78h+var_50], rdx
0x180039fc6  mov     rdx, r15
0x180039fc9  mov     [rsp+78h+var_58], r8d
0x180039fce  mov     r8d, [r14]
0x180039fd1  call    cs:__imp_SLDepositTokenActivationResponse
0x180039fd8  nop     dword ptr [rax+rax+00h]
0x180039fdd  mov     rcx, [rdi]; hMem
0x180039fe0  mov     ebx, eax
0x180039fe2  test    rcx, rcx
0x180039fe5  jz      short loc_180039FF6
0x180039fe7  call    cs:__imp_LocalFree
0x180039fee  nop     dword ptr [rax+rax+00h]
0x180039ff3  mov     [rdi], r13
0x180039ff6  mov     [r14], r13d
0x180039ff9  test    ebx, ebx
0x180039ffb  jns     short loc_18003A004
0x180039ffd  mov     ecx, ebx
0x180039fff  jmp     loc_180039E94
0x18003a004  mov     rax, [rbp+arg_38]
0x18003a00b  mov     [rax], r13d
0x18003a00e  jmp     loc_180039F41
```
