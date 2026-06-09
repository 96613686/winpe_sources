# CUHOSDeploymentInformation::GetSecurityData(wchar_t const *,ulong *,tagDeploymentSecurityData * *)

- ea: `0x18003de00`
- end: `0x18003dff4`
- name: `?GetSecurityData@CUHOSDeploymentInformation@@UEAAJPEB_WPEAKPEAPEAUtagDeploymentSecurityData@@@Z`
- size: `500`
- prototype: `__int64 __fastcall(CUHOSDeploymentInformation *this, const wchar_t *, struct tagDSSecurityData *, struct tagDeploymentSecurityData **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003950`
- `0x18001cabc`
- `0x180032c70`
- `0x180032e9c`
- `0x18003de00`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003df1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003df1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CUHOSDeploymentInformation::GetSecurityData(
        CUHOSDeploymentInformation *this,
        const wchar_t *a2,
        struct tagDSSecurityData *a3,
        struct tagDeploymentSecurityData **a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  char v8; // r15
  unsigned int v9; // r14d
  unsigned int v10; // r13d
  unsigned int v11; // ebx
  int v12; // eax
  struct tagDSSecurityData *v13; // r12
  __int64 v14; // rax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rdx
  unsigned int v19; // ecx
  struct tagDeploymentSecurityData *v20; // rax
  unsigned int i; // r9d
  __int64 v22; // r8
  unsigned int v24; // [rsp+20h] [rbp-38h] BYREF
  struct tagDSSecurityData *v25; // [rsp+28h] [rbp-30h] BYREF
  _QWORD v26[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]

  v25 = a3;
  if ( a3 )
  {
    if ( !a4 )
    {
      v6 = -2147467261;
      v7 = 268;
      goto LABEL_30;
    }
    *(_DWORD *)a3 = 0;
    v8 = 0;
    *a4 = 0;
    v9 = *((_DWORD *)this + 11);
    v26[0] = 0;
    v26[1] = a2;
    if ( !v9 )
      goto LABEL_29;
    v10 = 0;
    do
    {
      v11 = (v9 + v10) >> 1;
      v12 = CSusSortedArrayList<CSusMap<wchar_t *,CUHOSDeploymentInformation::CDeploymentFileInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpSusFree<CUHOSDeploymentInformation::CDeploymentFileInfo *>>::_tagMapEntry,CSusMap<wchar_t *,CUHOSDeploymentInformation::CDeploymentFileInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpSusFree<CUHOSDeploymentInformation::CDeploymentFileInfo *>>::CMapEntryOps>::InternalCompare(
              (char *)this + 24,
              v26,
              v11);
      if ( v12 )
      {
        if ( v12 <= 0 )
          v9 = (v9 + v10) >> 1;
        else
          v10 = v11 + 1;
      }
      else
      {
        v8 = 1;
      }
    }
    while ( v9 > v10 && !v8 );
    v13 = v25;
    if ( !v8 || v11 >= *((_DWORD *)this + 11) )
    {
LABEL_29:
      v6 = -2145124345;
      v7 = 274;
      goto LABEL_30;
    }
    v14 = *((_QWORD *)this + 4);
    v24 = 0;
    v25 = 0;
    v15 = *(_QWORD *)(v14 + 16LL * v11);
    *(_DWORD *)v13 = 0;
    *a4 = 0;
    if ( *(_DWORD *)v15 )
    {
      v16 = DecryptSecurityData(*(_DWORD *)v15, *(struct tagDSSecurityData **)(v15 + 8), &v24, &v25);
      v6 = v16;
      if ( v16 < 0 )
      {
        v17 = (unsigned int)v16;
        v18 = 116;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeploymentInformation.cpp",
          (const char *)v17,
          v24);
        FreeSecurityData(v24, v25);
        v7 = 276;
        goto LABEL_30;
      }
      if ( v24 )
      {
        v20 = (struct tagDeploymentSecurityData *)CoTaskMemAlloc(16LL * v24);
        *a4 = v20;
        if ( !v20 )
        {
          v6 = -2147024882;
          v18 = 125;
          v17 = 2147942414LL;
          goto LABEL_23;
        }
        v19 = v24;
        for ( i = 0; i < v24; v19 = v24 )
        {
          v22 = i++;
          v22 *= 2;
          *((_QWORD *)*a4 + v22 + 1) = *((_QWORD *)v25 + v22 + 1);
          *((_DWORD *)*a4 + 2 * v22) = *((_DWORD *)v25 + 2 * v22);
          *((_QWORD *)v25 + v22 + 1) = 0;
          *((_DWORD *)v25 + 2 * v22) = 0;
        }
        *(_DWORD *)v13 = v19;
      }
      else
      {
        v19 = 0;
      }
      FreeSecurityData(v19, v25);
    }
    return 0;
  }
  v6 = -2147467261;
  v7 = 267;
LABEL_30:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeploymentInformation.cpp",
    (const char *)v6,
    v24);
  return v6;
}

```

## disassembly

```asm
0x18003de00  push    rbp
0x18003de02  push    rbx
0x18003de03  push    rsi
0x18003de04  push    rdi
0x18003de05  push    r12
0x18003de07  push    r13
0x18003de09  push    r14
0x18003de0b  push    r15
0x18003de0d  mov     rbp, rsp
0x18003de10  sub     rsp, 58h
0x18003de14  mov     rax, cs:__security_cookie
0x18003de1b  xor     rax, rsp
0x18003de1e  mov     [rbp+var_18], rax
0x18003de22  mov     rsi, rcx
0x18003de25  mov     [rbp+var_30], r8
0x18003de29  xor     ecx, ecx
0x18003de2b  mov     rdi, r9
0x18003de2e  test    r8, r8
0x18003de31  jnz     short loc_18003DE42
0x18003de33  mov     ebx, 80004003h
0x18003de38  mov     edx, 10Bh
0x18003de3d  jmp     loc_18003DFC2
0x18003de42  test    rdi, rdi
0x18003de45  jnz     short loc_18003DE56
0x18003de47  mov     ebx, 80004003h
0x18003de4c  mov     edx, 10Ch
0x18003de51  jmp     loc_18003DFC2
0x18003de56  mov     [r8], ecx
0x18003de59  mov     r15b, cl
0x18003de5c  mov     [r9], rcx
0x18003de5f  mov     r14d, [rsi+2Ch]
0x18003de63  mov     [rbp+var_28], rcx
0x18003de67  mov     [rbp+var_20], rdx
0x18003de6b  test    r14d, r14d
0x18003de6e  jz      loc_18003DFB8
0x18003de74  mov     r13d, ecx
0x18003de77  lea     ebx, [r14+r13]
0x18003de7b  shr     ebx, 1
0x18003de7d  lea     rdx, [rbp+var_28]
0x18003de81  mov     r8d, ebx
0x18003de84  lea     rcx, [rsi+18h]
0x18003de88  call    ?InternalCompare@?$CSusSortedArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAVCDeploymentFileInfo@CUHOSDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpSusFree@PEAVCDeploymentFileInfo@CUHOSDeploymentInformation@@@@@@VCMapEntryOps@2@@@IEBAHAEBU_tagMapEntry@?$CSusMap@PEA_WPEAVCDeploymentFileInfo@CUHOSDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpSusFree@PEAVCDeploymentFileInfo@CUHOSDeploymentInformation@@@@@@K@Z; CSusSortedArrayList<CSusMap<wchar_t *,CUHOSDeploymentInformation::CDeploymentFileInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpSusFree<CUHOSDeploymentInformation::CDeploymentFileInfo *>>::_tagMapEntry,CSusMap<wchar_t *,CUHOSDeploymentInformation::CDeploymentFileInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpSusFree<CUHOSDeploymentInformation::CDeploymentFileInfo *>>::CMapEntryOps>::InternalCompare(CSusMap<wchar_t *,CUHOSDeploymentInformation::CDeploymentFileInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpSusFree<CUHOSDeploymentInformation::CDeploymentFileInfo *>>::_tagMapEntry const &,ulong)
0x18003de8d  test    eax, eax
0x18003de8f  jnz     short loc_18003DE96
0x18003de91  mov     r15b, 1
0x18003de94  jmp     short loc_18003DEA1
0x18003de96  jle     short loc_18003DE9E
0x18003de98  lea     r13d, [rbx+1]
0x18003de9c  jmp     short loc_18003DEA1
0x18003de9e  mov     r14d, ebx
0x18003dea1  cmp     r14d, r13d
0x18003dea4  jbe     short loc_18003DEAB
0x18003dea6  test    r15b, r15b
0x18003dea9  jz      short loc_18003DE77
0x18003deab  mov     r12, [rbp+var_30]
0x18003deaf  xor     r14d, r14d
0x18003deb2  test    r15b, r15b
0x18003deb5  jz      loc_18003DFB8
0x18003debb  cmp     ebx, [rsi+2Ch]
0x18003debe  jnb     loc_18003DFB8
0x18003dec4  mov     rax, [rsi+20h]
0x18003dec8  mov     ecx, ebx
0x18003deca  add     rcx, rcx
0x18003decd  mov     [rbp+var_38], r14d
0x18003ded1  mov     [rbp+var_30], r14
0x18003ded5  mov     rdx, [rax+rcx*8]
0x18003ded9  mov     [r12], r14d
0x18003dedd  mov     [rdi], r14
0x18003dee0  mov     ecx, [rdx]; unsigned int
0x18003dee2  test    ecx, ecx
0x18003dee4  jz      loc_18003DFB4
0x18003deea  mov     rdx, [rdx+8]; struct tagDSSecurityData *
0x18003deee  lea     r9, [rbp+var_30]; struct tagDSSecurityData **
0x18003def2  lea     r8, [rbp+var_38]; unsigned int *
0x18003def6  call    ?DecryptSecurityData@@YAJKPEAUtagDSSecurityData@@PEAKPEAPEAU1@@Z; DecryptSecurityData(ulong,tagDSSecurityData *,ulong *,tagDSSecurityData * *)
0x18003defb  mov     ebx, eax
0x18003defd  test    eax, eax
0x18003deff  jns     short loc_18003DF0A
0x18003df01  mov     r9d, eax
0x18003df04  lea     edx, [r14+74h]
0x18003df08  jmp     short loc_18003DF38
0x18003df0a  mov     eax, [rbp+var_38]
0x18003df0d  test    eax, eax
0x18003df0f  jnz     short loc_18003DF18
0x18003df11  xor     ecx, ecx
0x18003df13  jmp     loc_18003DFAB
0x18003df18  mov     rcx, rax
0x18003df1b  shl     rcx, 4; cb
0x18003df1f  call    cs:__imp_CoTaskMemAlloc
0x18003df25  mov     [rdi], rax
0x18003df28  test    rax, rax
0x18003df2b  jnz     short loc_18003DF5B
0x18003df2d  mov     ebx, 8007000Eh
0x18003df32  lea     edx, [rax+7Dh]; void *
0x18003df35  mov     r9d, ebx; char *
0x18003df38  mov     rcx, [rbp+40h]; this
0x18003df3c  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003df43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003df48  mov     rdx, [rbp+var_30]; struct tagDSSecurityData *
0x18003df4c  mov     ecx, [rbp+var_38]; unsigned int
0x18003df4f  call    ?FreeSecurityData@@YAXKPEAUtagDSSecurityData@@@Z; FreeSecurityData(ulong,tagDSSecurityData *)
0x18003df54  mov     edx, 114h
0x18003df59  jmp     short loc_18003DFC2
0x18003df5b  mov     ecx, [rbp+var_38]
0x18003df5e  mov     r9d, r14d
0x18003df61  test    ecx, ecx
0x18003df63  jz      short loc_18003DFA7
0x18003df65  mov     rax, [rbp+var_30]
0x18003df69  mov     rdx, [rdi]
0x18003df6c  mov     r8d, r9d
0x18003df6f  inc     r9d
0x18003df72  add     r8, r8
0x18003df75  mov     rcx, [rax+r8*8+8]
0x18003df7a  mov     [rdx+r8*8+8], rcx
0x18003df7f  mov     rax, [rbp+var_30]
0x18003df83  mov     rdx, [rdi]
0x18003df86  mov     ecx, [rax+r8*8]
0x18003df8a  mov     [rdx+r8*8], ecx
0x18003df8e  mov     rax, [rbp+var_30]
0x18003df92  mov     [rax+r8*8+8], r14
0x18003df97  mov     rax, [rbp+var_30]
0x18003df9b  mov     [rax+r8*8], r14d
0x18003df9f  mov     ecx, [rbp+var_38]; unsigned int
0x18003dfa2  cmp     r9d, ecx
0x18003dfa5  jb      short loc_18003DF65
0x18003dfa7  mov     [r12], ecx
0x18003dfab  mov     rdx, [rbp+var_30]; struct tagDSSecurityData *
0x18003dfaf  call    ?FreeSecurityData@@YAXKPEAUtagDSSecurityData@@@Z; FreeSecurityData(ulong,tagDSSecurityData *)
0x18003dfb4  xor     eax, eax
0x18003dfb6  jmp     short loc_18003DFD7
0x18003dfb8  mov     ebx, 80240007h
0x18003dfbd  mov     edx, 112h; void *
0x18003dfc2  mov     rcx, [rbp+40h]; this
0x18003dfc6  lea     r8, aCW1SSrcClientE_7; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18003dfcd  mov     r9d, ebx; char *
0x18003dfd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dfd5  mov     eax, ebx
0x18003dfd7  mov     rcx, [rbp+var_18]
0x18003dfdb  xor     rcx, rsp; StackCookie
0x18003dfde  call    __security_check_cookie
0x18003dfe3  add     rsp, 58h
0x18003dfe7  pop     r15
0x18003dfe9  pop     r14
0x18003dfeb  pop     r13
0x18003dfed  pop     r12
0x18003dfef  pop     rdi
0x18003dff0  pop     rsi
0x18003dff1  pop     rbx
0x18003dff2  pop     rbp
0x18003dff3  retn
```
