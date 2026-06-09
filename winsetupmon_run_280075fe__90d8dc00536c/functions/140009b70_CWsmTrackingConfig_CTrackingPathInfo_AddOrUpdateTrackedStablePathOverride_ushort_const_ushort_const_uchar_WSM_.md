# CWsmTrackingConfig::CTrackingPathInfo::AddOrUpdateTrackedStablePathOverride(ushort const *,ushort const *,uchar,_WSM_TRACKING_MODE)

- ea: `0x140009b70`
- end: `0x140009ed8`
- name: `?AddOrUpdateTrackedStablePathOverride@CTrackingPathInfo@CWsmTrackingConfig@@QEAAJPEBG0EW4_WSM_TRACKING_MODE@@@Z`
- size: `872`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, unsigned __int8, enum _WSM_TRACKING_MODE)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x140009ee0`

## callees

- `0x140008b58`
- `0x140009120`
- `0x140009b70`
- `0x14000a7a4`
- `0x14000d0a8`
- `0x14000d174`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009c83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009cc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009d0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009d48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009dcf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009e15`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009e55`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009c83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009cc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009d0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009d48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009dcf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009e15`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009e55`
- `ntoskrnl!_wcsicmp` at `0x140009bea`
- `ntoskrnl!_wcsicmp` at `0x140009c22`
- `ntoskrnl!_wcsicmp` at `0x140009bea`
- `ntoskrnl!_wcsicmp` at `0x140009c22`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::CTrackingPathInfo::AddOrUpdateTrackedStablePathOverride(
        __int64 a1,
        const wchar_t *a2,
        PVOID a3,
        char a4,
        int a5)
{
  int Instance; // edi
  char v6; // r13
  __int64 v7; // r15
  const wchar_t *v8; // r10
  __int64 v10; // rsi
  const wchar_t *v11; // rdx
  int v12; // eax
  const wchar_t *v13; // rdx
  struct CWsmTrackingConfig::CTrackingOverrideInfo **v14; // rax
  CWsmTrackingConfig::CTrackingOverrideInfo *v15; // rsi
  __int64 v16; // rax
  PVOID v17; // rdx
  CWsmTrackingConfig::CTrackingOverrideInfo *v18; // rsi
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // xmm1_8
  PVOID v22; // rsi
  CWsmTrackingConfig::CTrackingOverrideInfo *v23; // rbx
  struct CWsmTrackingConfig::CTrackingOverrideInfo **v25; // rax
  CWsmTrackingConfig::CTrackingOverrideInfo *v26; // r14
  __int64 v27; // rdx
  PVOID v28; // rax
  CWsmTrackingConfig::CTrackingOverrideInfo *v29; // r14
  __int64 *v30; // r14
  PVOID v31; // rbx
  __int64 v32; // r8
  unsigned __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int128 v36; // xmm0
  __int64 v37; // xmm1_8
  __int64 v38; // rcx
  _QWORD v39[2]; // [rsp+20h] [rbp-30h] BYREF
  char v40; // [rsp+30h] [rbp-20h]
  __int16 v41; // [rsp+31h] [rbp-1Fh]
  char v42; // [rsp+33h] [rbp-1Dh]
  int v43; // [rsp+34h] [rbp-1Ch]
  CWsmTrackingConfig::CTrackingOverrideInfo *v44; // [rsp+38h] [rbp-18h] BYREF
  CWsmTrackingConfig::CTrackingOverrideInfo **v45; // [rsp+40h] [rbp-10h]
  PVOID P; // [rsp+90h] [rbp+40h] BYREF
  const wchar_t *v47; // [rsp+98h] [rbp+48h]
  PVOID v48; // [rsp+A0h] [rbp+50h] BYREF

  v48 = a3;
  v47 = a2;
  v39[0] = a2;
  Instance = 0;
  v41 = 0;
  v6 = 0;
  v42 = 0;
  v7 = 0;
  v8 = a2;
  v43 = a5;
  v39[1] = a3;
  v40 = a4;
  if ( !*(_DWORD *)(a1 + 84) )
  {
LABEL_28:
    if ( (unsigned __int8)utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>::resize(
                            a1 + 8,
                            ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8)) >> 3) + 1) )
    {
      v48 = 0;
      v25 = (struct CWsmTrackingConfig::CTrackingOverrideInfo **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,>(
                                                                   &v44,
                                                                   &v48);
      Instance = CWsmTrackingConfig::CTrackingOverrideInfo::CreateInstance(
                   (struct _WSM_TRACKING_OVERRIDE_INFO *const)v39,
                   1,
                   v25);
      if ( v44 )
      {
        v26 = *v45;
        *v45 = v44;
        if ( v26 )
        {
          CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(v26);
          ExFreePoolWithTag(v26, 0x6E6D7377u);
        }
      }
      if ( Instance < 0 )
      {
LABEL_33:
        v23 = (CWsmTrackingConfig::CTrackingOverrideInfo *)v48;
LABEL_24:
        if ( v23 )
        {
          CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(v23);
          ExFreePoolWithTag(v23, 0x6E6D7377u);
        }
        return (unsigned int)Instance;
      }
      v27 = *(_QWORD *)(a1 + 16);
      v28 = v48;
      v48 = 0;
      v29 = *(CWsmTrackingConfig::CTrackingOverrideInfo **)(v27 - 8);
      *(_QWORD *)(v27 - 8) = v28;
      if ( v29 )
      {
        CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(v29);
        ExFreePoolWithTag(v29, 0x6E6D7377u);
      }
      v30 = (__int64 *)(a1 + 48);
      if ( (unsigned __int8)utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(
                              a1 + 48,
                              (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8)) >> 3) )
      {
        v32 = 0;
        v33 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a1 + 56) - *(_QWORD *)(a1 + 48)) >> 3);
        *(_DWORD *)(a1 + 84) = v33;
        if ( (_DWORD)v33 )
        {
          do
          {
            v34 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v32);
            v35 = *v30;
            v36 = *(_OWORD *)(v34 + 40);
            v37 = *(_QWORD *)(v34 + 56);
            v38 = 3 * v32;
            *(_OWORD *)(v35 + 8 * v38) = v36;
            v32 = (unsigned int)(v32 + 1);
            *(_QWORD *)(v35 + 8 * v38 + 16) = v37;
          }
          while ( (unsigned int)v32 < *(_DWORD *)(a1 + 84) );
        }
        *(_QWORD *)(a1 + 88) = *v30;
        goto LABEL_33;
      }
      v31 = v48;
      if ( v48 )
      {
        CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo((CWsmTrackingConfig::CTrackingOverrideInfo *)v48);
        ExFreePoolWithTag(v31, 0x6E6D7377u);
      }
    }
    return 3221225626LL;
  }
  while ( 1 )
  {
    v10 = *(_QWORD *)(a1 + 88);
    v11 = *(const wchar_t **)(v10 + 24 * v7);
    if ( v8 )
    {
      if ( !v11 )
        goto LABEL_21;
      v12 = _wcsicmp(v8, v11);
      a3 = v48;
      if ( v12 )
        goto LABEL_21;
    }
    else if ( v11 )
    {
      goto LABEL_21;
    }
    v13 = *(const wchar_t **)(v10 + 24 * v7 + 8);
    if ( a3 )
    {
      if ( !v13 )
        goto LABEL_21;
      if ( !_wcsicmp((const wchar_t *)a3, v13) )
      {
LABEL_12:
        P = 0;
        v14 = (struct CWsmTrackingConfig::CTrackingOverrideInfo **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,>(
                                                                     &v44,
                                                                     &P);
        Instance = CWsmTrackingConfig::CTrackingOverrideInfo::CreateInstance(
                     (struct _WSM_TRACKING_OVERRIDE_INFO *const)v39,
                     1,
                     v14);
        if ( v44 )
        {
          v15 = *v45;
          *v45 = v44;
          if ( v15 )
          {
            CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(v15);
            ExFreePoolWithTag(v15, 0x6E6D7377u);
          }
        }
        if ( Instance < 0 )
        {
          v23 = (CWsmTrackingConfig::CTrackingOverrideInfo *)P;
          goto LABEL_24;
        }
        v16 = *(_QWORD *)(a1 + 8);
        v17 = P;
        P = 0;
        v18 = *(CWsmTrackingConfig::CTrackingOverrideInfo **)(v16 + 8 * v7);
        *(_QWORD *)(v16 + 8 * v7) = v17;
        if ( v18 )
        {
          CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(v18);
          ExFreePoolWithTag(v18, 0x6E6D7377u);
        }
        v6 = 1;
        v19 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v7);
        v20 = *(_QWORD *)(a1 + 48);
        v21 = *(_QWORD *)(v19 + 56);
        *(_OWORD *)(v20 + 24 * v7) = *(_OWORD *)(v19 + 40);
        *(_QWORD *)(v20 + 24 * v7 + 16) = v21;
        v22 = P;
        if ( P )
        {
          CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo((CWsmTrackingConfig::CTrackingOverrideInfo *)P);
          ExFreePoolWithTag(v22, 0x6E6D7377u);
        }
      }
      a3 = v48;
      goto LABEL_21;
    }
    if ( !v13 )
      goto LABEL_12;
LABEL_21:
    v7 = (unsigned int)(v7 + 1);
    if ( (unsigned int)v7 >= *(_DWORD *)(a1 + 84) )
      break;
    v8 = v47;
  }
  if ( !v6 )
    goto LABEL_28;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140009b70  mov     [rsp-38h+arg_18], rbx
0x140009b75  mov     [rsp-38h+arg_10], r8
0x140009b7a  mov     [rsp-38h+arg_8], rdx
0x140009b7f  push    rbp
0x140009b80  push    rsi
0x140009b81  push    rdi
0x140009b82  push    r12
0x140009b84  push    r13
0x140009b86  push    r14
0x140009b88  push    r15
0x140009b8a  mov     rbp, rsp
0x140009b8d  sub     rsp, 50h
0x140009b91  xor     eax, eax
0x140009b93  mov     [rbp+var_30], rdx
0x140009b97  xor     edi, edi
0x140009b99  mov     [rbp+var_1F], ax
0x140009b9d  xor     r13b, r13b
0x140009ba0  mov     [rbp+var_1D], al
0x140009ba3  mov     eax, [rbp+arg_20]
0x140009ba6  xor     r15d, r15d
0x140009ba9  mov     r10, rdx
0x140009bac  mov     [rbp+var_1C], eax
0x140009baf  mov     rbx, rcx
0x140009bb2  mov     [rbp+var_28], r8
0x140009bb6  mov     [rbp+var_20], r9b
0x140009bba  cmp     [rcx+54h], edi
0x140009bbd  jbe     loc_140009D60
0x140009bc3  mov     rsi, [rbx+58h]
0x140009bc7  lea     r12, [r15+r15*2]
0x140009bcb  mov     rdx, [rsi+r12*8]; Str2
0x140009bcf  test    r10, r10
0x140009bd2  jnz     short loc_140009BDE
0x140009bd4  test    rdx, rdx
0x140009bd7  jz      short loc_140009C02
0x140009bd9  jmp     loc_140009D1D
0x140009bde  test    rdx, rdx
0x140009be1  jz      loc_140009D1D
0x140009be7  mov     rcx, r10; Str1
0x140009bea  call    cs:__imp__wcsicmp
0x140009bf1  nop     dword ptr [rax+rax+00h]
0x140009bf6  mov     r8, [rbp+arg_10]
0x140009bfa  test    eax, eax
0x140009bfc  jnz     loc_140009D1D
0x140009c02  mov     rdx, [rsi+r12*8+8]; Str2
0x140009c07  test    r8, r8
0x140009c0a  jnz     short loc_140009C16
0x140009c0c  test    rdx, rdx
0x140009c0f  jz      short loc_140009C36
0x140009c11  jmp     loc_140009D1D
0x140009c16  test    rdx, rdx
0x140009c19  jz      loc_140009D1D
0x140009c1f  mov     rcx, r8; Str1
0x140009c22  call    cs:__imp__wcsicmp
0x140009c29  nop     dword ptr [rax+rax+00h]
0x140009c2e  test    eax, eax
0x140009c30  jnz     loc_140009D19
0x140009c36  lea     rdx, [rbp+P]
0x140009c3a  mov     [rbp+P], 0
0x140009c42  lea     rcx, [rbp+var_18]
0x140009c46  call    ??$out_ptr@XV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@0@@Z
0x140009c4b  mov     r8, rax; struct CWsmTrackingConfig::CTrackingOverrideInfo **
0x140009c4e  lea     rcx, [rbp+var_30]; struct _WSM_TRACKING_OVERRIDE_INFO *
0x140009c52  mov     dl, 1; bool
0x140009c54  call    ?CreateInstance@CTrackingOverrideInfo@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_OVERRIDE_INFO@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingOverrideInfo::CreateInstance(_WSM_TRACKING_OVERRIDE_INFO * const,bool,CWsmTrackingConfig::CTrackingOverrideInfo * *)
0x140009c59  mov     edi, eax
0x140009c5b  mov     rax, [rbp+var_18]
0x140009c5f  test    rax, rax
0x140009c62  jz      short loc_140009C8F
0x140009c64  mov     rdx, [rbp+var_10]
0x140009c68  mov     rsi, [rdx]
0x140009c6b  mov     [rdx], rax
0x140009c6e  test    rsi, rsi
0x140009c71  jz      short loc_140009C8F
0x140009c73  mov     rcx, rsi; this
0x140009c76  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x140009c7b  mov     edx, 6E6D7377h; Tag
0x140009c80  mov     rcx, rsi; P
0x140009c83  call    cs:__imp_ExFreePoolWithTag
0x140009c8a  nop     dword ptr [rax+rax+00h]
0x140009c8f  test    edi, edi
0x140009c91  js      loc_140009D2F
0x140009c97  mov     rax, [rbx+8]
0x140009c9b  mov     rdx, [rbp+P]
0x140009c9f  mov     [rbp+P], 0
0x140009ca7  mov     rsi, [rax+r15*8]
0x140009cab  mov     [rax+r15*8], rdx
0x140009caf  test    rsi, rsi
0x140009cb2  jz      short loc_140009CD0
0x140009cb4  mov     rcx, rsi; this
0x140009cb7  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x140009cbc  mov     edx, 6E6D7377h; Tag
0x140009cc1  mov     rcx, rsi; P
0x140009cc4  call    cs:__imp_ExFreePoolWithTag
0x140009ccb  nop     dword ptr [rax+rax+00h]
0x140009cd0  mov     rax, [rbx+8]
0x140009cd4  mov     r13b, 1
0x140009cd7  mov     rcx, [rax+r15*8]
0x140009cdb  mov     rax, [rbx+30h]
0x140009cdf  movups  xmm0, xmmword ptr [rcx+28h]
0x140009ce3  movsd   xmm1, qword ptr [rcx+38h]
0x140009ce8  movups  xmmword ptr [rax+r12*8], xmm0
0x140009ced  movsd   qword ptr [rax+r12*8+10h], xmm1
0x140009cf4  mov     rsi, [rbp+P]
0x140009cf8  test    rsi, rsi
0x140009cfb  jz      short loc_140009D19
0x140009cfd  mov     rcx, rsi; this
0x140009d00  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x140009d05  mov     edx, 6E6D7377h; Tag
0x140009d0a  mov     rcx, rsi; P
0x140009d0d  call    cs:__imp_ExFreePoolWithTag
0x140009d14  nop     dword ptr [rax+rax+00h]
0x140009d19  mov     r8, [rbp+arg_10]
0x140009d1d  inc     r15d
0x140009d20  cmp     r15d, [rbx+54h]
0x140009d24  jnb     short loc_140009D5B
0x140009d26  mov     r10, [rbp+arg_8]
0x140009d2a  jmp     loc_140009BC3
0x140009d2f  mov     rbx, [rbp+P]
0x140009d33  test    rbx, rbx
0x140009d36  jz      short loc_140009D54
0x140009d38  mov     rcx, rbx; this
0x140009d3b  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x140009d40  mov     edx, 6E6D7377h; Tag
0x140009d45  mov     rcx, rbx; P
0x140009d48  call    cs:__imp_ExFreePoolWithTag
0x140009d4f  nop     dword ptr [rax+rax+00h]
0x140009d54  mov     eax, edi
0x140009d56  jmp     loc_140009E66
0x140009d5b  test    r13b, r13b
0x140009d5e  jnz     short loc_140009D54
0x140009d60  lea     rsi, [rbx+8]
0x140009d64  mov     rdx, [rsi+8]
0x140009d68  mov     rcx, rsi
0x140009d6b  sub     rdx, [rsi]
0x140009d6e  sar     rdx, 3
0x140009d72  inc     rdx
0x140009d75  call    ?resize@?$vector@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@2@@utl@@QEAA_N_K@Z; utl::vector<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>::resize(unsigned __int64)
0x140009d7a  test    al, al
0x140009d7c  jz      loc_140009E61
0x140009d82  lea     rdx, [rbp+arg_10]
0x140009d86  mov     [rbp+arg_10], 0
0x140009d8e  lea     rcx, [rbp+var_18]
0x140009d92  call    ??$out_ptr@XV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@0@@Z
0x140009d97  mov     r8, rax; struct CWsmTrackingConfig::CTrackingOverrideInfo **
0x140009d9a  lea     rcx, [rbp+var_30]; struct _WSM_TRACKING_OVERRIDE_INFO *
0x140009d9e  mov     dl, 1; bool
0x140009da0  call    ?CreateInstance@CTrackingOverrideInfo@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_OVERRIDE_INFO@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingOverrideInfo::CreateInstance(_WSM_TRACKING_OVERRIDE_INFO * const,bool,CWsmTrackingConfig::CTrackingOverrideInfo * *)
0x140009da5  mov     rcx, [rbp+var_18]
0x140009da9  mov     edi, eax
0x140009dab  test    rcx, rcx
0x140009dae  jz      short loc_140009DDB
0x140009db0  mov     rax, [rbp+var_10]
0x140009db4  mov     r14, [rax]
0x140009db7  mov     [rax], rcx
0x140009dba  test    r14, r14
0x140009dbd  jz      short loc_140009DDB
0x140009dbf  mov     rcx, r14; this
0x140009dc2  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x140009dc7  mov     edx, 6E6D7377h; Tag
0x140009dcc  mov     rcx, r14; P
0x140009dcf  call    cs:__imp_ExFreePoolWithTag
0x140009dd6  nop     dword ptr [rax+rax+00h]
0x140009ddb  test    edi, edi
0x140009ddd  jns     short loc_140009DE8
0x140009ddf  mov     rbx, [rbp+arg_10]
0x140009de3  jmp     loc_140009D33
0x140009de8  mov     rdx, [rbx+10h]
0x140009dec  mov     rax, [rbp+arg_10]
0x140009df0  mov     [rbp+arg_10], 0
0x140009df8  mov     r14, [rdx-8]
0x140009dfc  mov     [rdx-8], rax
0x140009e00  test    r14, r14
0x140009e03  jz      short loc_140009E21
0x140009e05  mov     rcx, r14; this
0x140009e08  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x140009e0d  mov     edx, 6E6D7377h; Tag
0x140009e12  mov     rcx, r14; P
0x140009e15  call    cs:__imp_ExFreePoolWithTag
0x140009e1c  nop     dword ptr [rax+rax+00h]
0x140009e21  mov     rdx, [rsi+8]
0x140009e25  lea     r14, [rbx+30h]
0x140009e29  sub     rdx, [rsi]
0x140009e2c  mov     rcx, r14
0x140009e2f  sar     rdx, 3
0x140009e33  call    ?resize@?$vector@U_WSM_TRACKING_PATH_INFO@@V?$allocator@U_WSM_TRACKING_PATH_INFO@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<_WSM_TRACKING_PATH_INFO,utl::allocator<_WSM_TRACKING_PATH_INFO>>::resize(unsigned __int64)
0x140009e38  test    al, al
0x140009e3a  jnz     short loc_140009E7F
0x140009e3c  mov     rbx, [rbp+arg_10]
0x140009e40  test    rbx, rbx
0x140009e43  jz      short loc_140009E61
0x140009e45  mov     rcx, rbx; this
0x140009e48  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x140009e4d  mov     edx, 6E6D7377h; Tag
0x140009e52  mov     rcx, rbx; P
0x140009e55  call    cs:__imp_ExFreePoolWithTag
0x140009e5c  nop     dword ptr [rax+rax+00h]
0x140009e61  mov     eax, 0C000009Ah
0x140009e66  mov     rbx, [rsp+50h+arg_18]
0x140009e6e  add     rsp, 50h
0x140009e72  pop     r15
0x140009e74  pop     r14
0x140009e76  pop     r13
0x140009e78  pop     r12
0x140009e7a  pop     rdi
0x140009e7b  pop     rsi
0x140009e7c  pop     rbp
0x140009e7d  retn
0x140009e7f  mov     rcx, [r14+8]
0x140009e83  mov     rax, 0AAAAAAAAAAAAAAABh
0x140009e8d  sub     rcx, [r14]
0x140009e90  xor     r8d, r8d
0x140009e93  sar     rcx, 3
0x140009e97  imul    rcx, rax
0x140009e9b  mov     [rbx+54h], ecx
0x140009e9e  test    ecx, ecx
0x140009ea0  jz      short loc_140009ECC
0x140009ea2  mov     rax, [rsi]
0x140009ea5  mov     rcx, [rax+r8*8]
0x140009ea9  mov     rax, [r14]
0x140009eac  movups  xmm0, xmmword ptr [rcx+28h]
0x140009eb0  movsd   xmm1, qword ptr [rcx+38h]
0x140009eb5  lea     rcx, [r8+r8*2]
0x140009eb9  movups  xmmword ptr [rax+rcx*8], xmm0
0x140009ebd  inc     r8d
0x140009ec0  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x140009ec6  cmp     r8d, [rbx+54h]
0x140009eca  jb      short loc_140009EA2
0x140009ecc  mov     rax, [r14]
0x140009ecf  mov     [rbx+58h], rax
0x140009ed3  jmp     loc_140009DDF
```
