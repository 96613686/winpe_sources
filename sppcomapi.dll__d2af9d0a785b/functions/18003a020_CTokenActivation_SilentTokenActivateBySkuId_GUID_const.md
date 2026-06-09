# CTokenActivation::SilentTokenActivateBySkuId(_GUID const *)

- ea: `0x18003a020`
- end: `0x18003a17a`
- name: `?SilentTokenActivateBySkuId@CTokenActivation@@UEAAJPEBU_GUID@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(CTokenActivation *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180003520`
- `0x180004288`
- `0x180039e34`
- `0x18003a020`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a140`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a140`
- `sppcext!SLGetTokenActivationGrants` at `0x18003a067`
- `sppcext!SLGetTokenActivationGrants` at `0x18003a067`
- `sppcext!SLFreeTokenActivationGrants` at `0x18003a15d`
- `sppcext!SLFreeTokenActivationGrants` at `0x18003a15d`

## pseudocode

```c
__int64 __fastcall CTokenActivation::SilentTokenActivateBySkuId(CTokenActivation *this, const struct _GUID *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  HLOCAL hMem; // [rsp+40h] [rbp-10h] BYREF
  __int64 v13; // [rsp+48h] [rbp-8h] BYREF
  int v14; // [rsp+78h] [rbp+28h] BYREF
  int v15; // [rsp+80h] [rbp+30h] BYREF
  int v16; // [rsp+88h] [rbp+38h] BYREF

  v13 = 0;
  v15 = 0;
  hMem = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
LABEL_13:
    v7 = v4;
    goto LABEL_14;
  }
  v5 = SLGetTokenActivationGrants(*((_QWORD *)this + 24), a2, &v13);
  v4 = v5;
  if ( v5 < 0 )
    goto LABEL_4;
  v8 = *((_QWORD *)this + 24);
  v14 = 0;
  v5 = CTokenActivation::SilentTokenActivate(v6, v8, (__int64)a2, v13, 2u, &hMem, &v15, &v14);
  v4 = v5;
  if ( v5 < 0 )
    goto LABEL_4;
  if ( v14 >= 0 )
  {
LABEL_7:
    v4 = 0;
    goto LABEL_15;
  }
  v10 = *((_QWORD *)this + 24);
  v16 = 0;
  v5 = CTokenActivation::SilentTokenActivate(v9, v10, (__int64)a2, v13, 1u, &hMem, &v15, &v16);
  v4 = v5;
  if ( v5 < 0 )
  {
LABEL_4:
    v7 = (unsigned int)v5;
LABEL_14:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_15;
  }
  v4 = v16;
  if ( v16 >= 0 )
    goto LABEL_7;
  if ( v16 == -1073417467 )
    v4 = v14;
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_13;
LABEL_15:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v13 )
    SLFreeTokenActivationGrants();
  return v4;
}

```

## disassembly

```asm
0x18003a020  mov     [rsp-18h+arg_0], rbx
0x18003a025  push    rbp
0x18003a026  push    rdi
0x18003a027  push    r14
0x18003a029  mov     rbp, rsp
0x18003a02c  sub     rsp, 50h
0x18003a030  mov     [rbp+var_8], 0
0x18003a038  mov     rdi, rdx
0x18003a03b  mov     [rbp+arg_10], 0
0x18003a042  mov     r14, rcx
0x18003a045  mov     [rbp+hMem], 0
0x18003a04d  test    rdx, rdx
0x18003a050  jnz     short loc_18003A05C
0x18003a052  mov     ebx, 80070057h
0x18003a057  jmp     loc_18003A129
0x18003a05c  mov     rcx, [rcx+0C0h]
0x18003a063  lea     r8, [rbp+var_8]
0x18003a067  call    cs:__imp_SLGetTokenActivationGrants
0x18003a06e  nop     dword ptr [rax+rax+00h]
0x18003a073  mov     ebx, eax
0x18003a075  test    eax, eax
0x18003a077  jns     short loc_18003A080
0x18003a079  mov     ecx, eax
0x18003a07b  jmp     loc_18003A12B
0x18003a080  mov     r9, [rbp+var_8]
0x18003a084  lea     rax, [rbp+arg_8]
0x18003a088  mov     rdx, [r14+0C0h]
0x18003a08f  mov     r8, rdi
0x18003a092  mov     [rsp+50h+var_18], rax
0x18003a097  lea     rax, [rbp+arg_10]
0x18003a09b  mov     [rsp+50h+var_20], rax
0x18003a0a0  lea     rax, [rbp+hMem]
0x18003a0a4  mov     [rsp+50h+var_28], rax
0x18003a0a9  mov     [rsp+50h+var_30], 2
0x18003a0b1  mov     [rbp+arg_8], 0
0x18003a0b8  call    ?SilentTokenActivate@CTokenActivation@@IEAAJPEAXPEBU_GUID@@PEAU_tagSLTOKENACTIVATIONGRANTS@@KAEAV?$SP_SLC@E@@AEAIPEAJ@Z; CTokenActivation::SilentTokenActivate(void *,_GUID const *,_tagSLTOKENACTIVATIONGRANTS *,ulong,SP_SLC<uchar> &,uint &,long *)
0x18003a0bd  mov     ebx, eax
0x18003a0bf  test    eax, eax
0x18003a0c1  js      short loc_18003A079
0x18003a0c3  cmp     [rbp+arg_8], 0
0x18003a0c7  jl      short loc_18003A0CD
0x18003a0c9  xor     ebx, ebx
0x18003a0cb  jmp     short loc_18003A130
0x18003a0cd  mov     r9, [rbp+var_8]
0x18003a0d1  lea     rax, [rbp+arg_18]
0x18003a0d5  mov     rdx, [r14+0C0h]
0x18003a0dc  mov     r8, rdi
0x18003a0df  mov     [rsp+50h+var_18], rax
0x18003a0e4  lea     rax, [rbp+arg_10]
0x18003a0e8  mov     [rsp+50h+var_20], rax
0x18003a0ed  lea     rax, [rbp+hMem]
0x18003a0f1  mov     [rsp+50h+var_28], rax
0x18003a0f6  mov     [rsp+50h+var_30], 1
0x18003a0fe  mov     [rbp+arg_18], 0
0x18003a105  call    ?SilentTokenActivate@CTokenActivation@@IEAAJPEAXPEBU_GUID@@PEAU_tagSLTOKENACTIVATIONGRANTS@@KAEAV?$SP_SLC@E@@AEAIPEAJ@Z; CTokenActivation::SilentTokenActivate(void *,_GUID const *,_tagSLTOKENACTIVATIONGRANTS *,ulong,SP_SLC<uchar> &,uint &,long *)
0x18003a10a  mov     ebx, eax
0x18003a10c  test    eax, eax
0x18003a10e  js      loc_18003A079
0x18003a114  mov     ebx, [rbp+arg_18]
0x18003a117  test    ebx, ebx
0x18003a119  jns     short loc_18003A0C9
0x18003a11b  cmp     ebx, 0C004F305h
0x18003a121  cmovz   ebx, [rbp+arg_8]
0x18003a125  test    ebx, ebx
0x18003a127  jns     short loc_18003A130
0x18003a129  mov     ecx, ebx
0x18003a12b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003a130  mov     ecx, ebx
0x18003a132  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003a137  mov     rcx, [rbp+hMem]; hMem
0x18003a13b  test    rcx, rcx
0x18003a13e  jz      short loc_18003A154
0x18003a140  call    cs:__imp_LocalFree
0x18003a147  nop     dword ptr [rax+rax+00h]
0x18003a14c  mov     [rbp+hMem], 0
0x18003a154  mov     rcx, [rbp+var_8]
0x18003a158  test    rcx, rcx
0x18003a15b  jz      short loc_18003A169
0x18003a15d  call    cs:__imp_SLFreeTokenActivationGrants
0x18003a164  nop     dword ptr [rax+rax+00h]
0x18003a169  mov     eax, ebx
0x18003a16b  mov     rbx, [rsp+50h+arg_0]
0x18003a170  add     rsp, 50h
0x18003a174  pop     r14
0x18003a176  pop     rdi
0x18003a177  pop     rbp
0x18003a178  retn
```
