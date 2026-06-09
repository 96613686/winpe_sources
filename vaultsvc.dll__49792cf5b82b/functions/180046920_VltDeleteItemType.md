# VltDeleteItemType

- ea: `0x180046920`
- end: `0x180046d86`
- name: `VltDeleteItemType`
- size: `1126`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation`

## callees

- `0x180003140`
- `0x180006610`
- `0x180013390`
- `0x180015568`
- `0x18001eda0`
- `0x180020a24`
- `0x180021b70`
- `0x180028ce0`
- `0x18002e9c0`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x180046920`
- `0x180048b80`
- `0x18004a1e0`
- `0x18004d010`

## string_xrefs

- `0x1800469a5`: `VltDeleteItemType`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VltDeleteItemType(__int64 a1, const struct _GUID *a2, const struct _GUID *a3, unsigned int a4)
{
  int v7; // r8d
  PVOID *v9; // rcx
  unsigned __int64 v10; // rdx
  struct CUserVault *v11; // rsi
  unsigned int UserVaultManager; // eax
  unsigned int v13; // edi
  unsigned int Vault; // eax
  unsigned int v15; // eax
  __int64 v16; // rax
  unsigned int v17; // [rsp+48h] [rbp-89h] BYREF
  HANDLE v18[2]; // [rsp+50h] [rbp-81h] BYREF
  __int64 (__fastcall *v19)(_QWORD); // [rsp+60h] [rbp-71h] BYREF
  struct CUserVault *v20; // [rsp+68h] [rbp-69h] BYREF
  int v21; // [rsp+70h] [rbp-61h]
  __int64 (__fastcall *v22)(_QWORD); // [rsp+78h] [rbp-59h] BYREF
  CUserVaultMgr *v23; // [rsp+80h] [rbp-51h] BYREF
  int v24; // [rsp+88h] [rbp-49h]
  _BYTE v25[80]; // [rsp+98h] [rbp-39h] BYREF

  v19 = AutoDereference<IVaultKeyManager>;
  v20 = 0;
  v21 = 0;
  v22 = AutoDereference<IVaultKeyManager>;
  v23 = 0;
  v24 = 0;
  v17 = 0;
  LOBYTE(v18[0]) = 0;
  v18[1] = 0;
  FnTracer::FnTracer((FnTracer *)v25, "VltDeleteItemType", &v17);
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
LABEL_5:
    v17 = 87;
    FnTracer::~FnTracer((FnTracer *)v25);
    CVaultRpcImpersonate::~CVaultRpcImpersonate(v18);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v22);
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v19);
    return 87;
  }
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF__guid__guid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, v7, (_DWORD)a3, (__int64)a2);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = *(_QWORD *)&a2->Data1;
  if ( !*(_QWORD *)&a2->Data1 )
    v10 = *(_QWORD *)a2->Data4 - _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( !v10 )
  {
    if ( (a4 & 1) == 0 )
    {
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
        WPP_SF_(v9[2], 47, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
      goto LABEL_5;
    }
    goto LABEL_18;
  }
  if ( (a4 & 1) != 0 )
  {
LABEL_18:
    v11 = (struct CUserVault *)VaultGlobals::g_GlobalSchemaMgr;
    CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v19);
    v20 = v11;
    (**(void (__fastcall ***)(struct CUserVault *))v11)(v11);
    goto LABEL_30;
  }
  UserVaultManager = CVaultMgr::GetUserVaultManager((CVaultMgr *)v9, 1u, &v23, 0, 0);
  v13 = UserVaultManager;
  v17 = UserVaultManager;
  if ( UserVaultManager )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids,
        UserVaultManager);
      v13 = v17;
    }
    goto LABEL_44;
  }
  Vault = CUserVaultMgr::GetVault(v23, a2, &v20);
  v13 = Vault;
  v17 = Vault;
  if ( Vault )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, Vault);
      v13 = v17;
    }
    goto LABEL_44;
  }
  v11 = v20;
LABEL_30:
  v15 = CVaultRpcImpersonate::Impersonate((CVaultRpcImpersonate *)v18, 1);
  v13 = v15;
  v17 = v15;
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, v15);
      v13 = v17;
    }
  }
  else
  {
    v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v11 + 1) + 216LL))(*((_QWORD *)v11 + 1));
    if ( (unsigned int)VaultAccessCheck(0, v16, 0) )
    {
      v13 = VaultDeleteSchema(v11, a3, a4);
      v17 = v13;
      if ( v13 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
        v13 = v17;
      }
    }
    else
    {
      v13 = 1168;
      v17 = 1168;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, 1168);
        v13 = v17;
      }
    }
  }
LABEL_44:
  FnTracer::~FnTracer((FnTracer *)v25);
  CVaultRpcImpersonate::~CVaultRpcImpersonate(v18);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v22);
  CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v19);
  return v13;
}

```

## disassembly

```asm
0x180046920  mov     rax, rsp
0x180046923  mov     [rax+8], rbx
0x180046927  push    rbp
0x180046928  push    rsi
0x180046929  push    rdi
0x18004692a  push    r14
0x18004692c  push    r15
0x18004692e  lea     rbp, [rax-5Fh]
0x180046932  sub     rsp, 100h
0x180046939  movaps  xmmword ptr [rax-38h], xmm6
0x18004693d  mov     rax, cs:__security_cookie
0x180046944  xor     rax, rsp
0x180046947  mov     [rbp+57h+var_40], rax
0x18004694b  mov     r14d, r9d
0x18004694e  mov     r15, r8
0x180046951  mov     rsi, rdx
0x180046954  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18004695b  mov     [rbp+57h+var_C8], rax
0x18004695f  mov     [rbp+57h+var_C0], 0
0x180046967  mov     [rbp+57h+var_B8], 0
0x18004696e  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180046975  mov     [rbp+57h+var_B0], rax
0x180046979  mov     [rbp+57h+var_A8], 0
0x180046981  mov     [rbp+57h+var_A0], 0
0x180046988  xorps   xmm6, xmm6
0x18004698b  mov     [rsp+120h+var_E0], 0
0x180046993  mov     [rsp+120h+var_D8], 0
0x180046998  mov     [rbp+57h+var_D0], 0
0x1800469a0  lea     r8, [rsp+120h+var_E0]; unsigned int *
0x1800469a5  lea     rdx, aVltdeleteitemt; "VltDeleteItemType"
0x1800469ac  lea     rcx, [rbp+57h+var_90]; this
0x1800469b0  call    ??0FnTracer@@QEAA@PEADPEAK@Z; FnTracer::FnTracer(char *,ulong *)
0x1800469b5  test    rsi, rsi
0x1800469b8  jnz     short loc_180046A1E
0x1800469ba  lea     rbx, WPP_GLOBAL_Control
0x1800469c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800469c8  cmp     rcx, rbx
0x1800469cb  jz      short loc_1800469E6
0x1800469cd  test    byte ptr [rcx+1Ch], 2
0x1800469d1  jz      short loc_1800469E6
0x1800469d3  lea     edx, [rsi+2Dh]
0x1800469d6  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x1800469dd  mov     rcx, [rcx+10h]
0x1800469e1  call    WPP_SF_
0x1800469e6  mov     ebx, 57h ; 'W'
0x1800469eb  mov     [rsp+120h+var_E0], ebx
0x1800469ef  lea     rcx, [rbp+57h+var_90]; this
0x1800469f3  call    ??1FnTracer@@QEAA@XZ; FnTracer::~FnTracer(void)
0x1800469f8  lea     rcx, [rsp+120h+var_D8]; this
0x1800469fd  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x180046a02  nop
0x180046a03  lea     rcx, [rbp+57h+var_B0]
0x180046a07  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180046a0c  nop
0x180046a0d  lea     rcx, [rbp+57h+var_C8]
0x180046a11  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180046a16  nop
0x180046a17  mov     eax, ebx
0x180046a19  jmp     loc_180046D5E
0x180046a1e  lea     rbx, WPP_GLOBAL_Control
0x180046a25  mov     rcx, cs:WPP_GLOBAL_Control
0x180046a2c  cmp     rcx, rbx
0x180046a2f  jz      short loc_180046A59
0x180046a31  test    byte ptr [rcx+1Ch], 8
0x180046a35  jz      short loc_180046A59
0x180046a37  mov     edx, 2Eh ; '.'
0x180046a3c  mov     dword ptr [rsp+120h+var_F8], r14d; unsigned int *
0x180046a41  mov     [rsp+120h+var_100], rsi
0x180046a46  mov     r9, r15
0x180046a49  mov     rcx, [rcx+10h]
0x180046a4d  call    WPP_SF__guid__guid_D
0x180046a52  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180046a59  mov     rdx, [rsi]
0x180046a5c  movq    rax, xmm6
0x180046a61  sub     rdx, rax
0x180046a64  jnz     short loc_180046A77
0x180046a66  mov     rdx, [rsi+8]
0x180046a6a  psrldq  xmm6, 8
0x180046a6f  movq    rax, xmm6
0x180046a74  sub     rdx, rax
0x180046a77  mov     eax, r14d
0x180046a7a  and     eax, 1
0x180046a7d  test    rdx, rdx
0x180046a80  jnz     short loc_180046ADA
0x180046a82  test    eax, eax
0x180046a84  jnz     short loc_180046ADE
0x180046a86  cmp     rcx, rbx
0x180046a89  jz      short loc_180046AA4
0x180046a8b  test    byte ptr [rcx+1Ch], 2
0x180046a8f  jz      short loc_180046AA4
0x180046a91  lea     edx, [rax+2Fh]
0x180046a94  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x180046a9b  mov     rcx, [rcx+10h]
0x180046a9f  call    WPP_SF_
0x180046aa4  mov     ebx, 57h ; 'W'
0x180046aa9  mov     [rsp+120h+var_E0], ebx
0x180046aad  lea     rcx, [rbp+57h+var_90]; this
0x180046ab1  call    ??1FnTracer@@QEAA@XZ; FnTracer::~FnTracer(void)
0x180046ab6  lea     rcx, [rsp+120h+var_D8]; this
0x180046abb  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x180046ac0  nop
0x180046ac1  lea     rcx, [rbp+57h+var_B0]
0x180046ac5  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180046aca  nop
0x180046acb  lea     rcx, [rbp+57h+var_C8]
0x180046acf  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180046ad4  nop
0x180046ad5  jmp     loc_180046A17
0x180046ada  test    eax, eax
0x180046adc  jz      short loc_180046B05
0x180046ade  mov     rsi, cs:?g_GlobalSchemaMgr@VaultGlobals@@3VCVaultGlobalSchemaMgr@@A; CVaultGlobalSchemaMgr VaultGlobals::g_GlobalSchemaMgr
0x180046ae5  lea     rcx, [rbp+57h+var_C8]
0x180046ae9  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180046aee  mov     [rbp+57h+var_C0], rsi
0x180046af2  mov     rax, [rsi]
0x180046af5  mov     rcx, rsi
0x180046af8  mov     rax, [rax]
0x180046afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b00  jmp     loc_180046BFA
0x180046b05  mov     [rsp+120h+var_100], 0; struct _LUID *
0x180046b0e  xor     r9d, r9d; unsigned __int8 *
0x180046b11  lea     r8, [rbp+57h+var_A8]; struct CUserVaultMgr **
0x180046b15  mov     dl, 1; unsigned __int8
0x180046b17  call    ?GetUserVaultManager@CVaultMgr@@QEAAKEPEAPEAVCUserVaultMgr@@QEAEPEAU_LUID@@PEAKPEAPEAX@Z; CVaultMgr::GetUserVaultManager(uchar,CUserVaultMgr * *,uchar * const,_LUID *,ulong *,void * *)
0x180046b1c  mov     edi, eax
0x180046b1e  mov     [rsp+120h+var_E0], eax
0x180046b22  test    eax, eax
0x180046b24  jz      short loc_180046B81
0x180046b26  mov     rcx, cs:WPP_GLOBAL_Control
0x180046b2d  cmp     rcx, rbx
0x180046b30  jz      short loc_180046B54
0x180046b32  test    byte ptr [rcx+1Ch], 2
0x180046b36  jz      short loc_180046B54
0x180046b38  mov     edx, 30h ; '0'
0x180046b3d  mov     r9d, eax
0x180046b40  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x180046b47  mov     rcx, [rcx+10h]
0x180046b4b  call    WPP_SF_d
0x180046b50  mov     edi, [rsp+120h+var_E0]
0x180046b54  lea     rcx, [rbp+57h+var_90]; this
0x180046b58  call    ??1FnTracer@@QEAA@XZ; FnTracer::~FnTracer(void)
0x180046b5d  lea     rcx, [rsp+120h+var_D8]; this
0x180046b62  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x180046b67  nop
0x180046b68  lea     rcx, [rbp+57h+var_B0]
0x180046b6c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180046b71  nop
0x180046b72  lea     rcx, [rbp+57h+var_C8]
0x180046b76  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180046b7b  nop
0x180046b7c  jmp     loc_180046D5C
0x180046b81  lea     r8, [rbp+57h+var_C0]; struct CUserVault **
0x180046b85  mov     rdx, rsi; struct _GUID *
0x180046b88  mov     rcx, [rbp+57h+var_A8]; this
0x180046b8c  call    ?GetVault@CUserVaultMgr@@QEAAKPEBU_GUID@@PEAPEAVCUserVault@@@Z; CUserVaultMgr::GetVault(_GUID const *,CUserVault * *)
0x180046b91  mov     edi, eax
0x180046b93  mov     [rsp+120h+var_E0], eax
0x180046b97  test    eax, eax
0x180046b99  jz      short loc_180046BF6
0x180046b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ba2  cmp     rcx, rbx
0x180046ba5  jz      short loc_180046BC9
0x180046ba7  test    byte ptr [rcx+1Ch], 2
0x180046bab  jz      short loc_180046BC9
0x180046bad  mov     edx, 31h ; '1'
0x180046bb2  mov     r9d, eax
0x180046bb5  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x180046bbc  mov     rcx, [rcx+10h]
0x180046bc0  call    WPP_SF_d
0x180046bc5  mov     edi, [rsp+120h+var_E0]
0x180046bc9  lea     rcx, [rbp+57h+var_90]; this
0x180046bcd  call    ??1FnTracer@@QEAA@XZ; FnTracer::~FnTracer(void)
0x180046bd2  lea     rcx, [rsp+120h+var_D8]; this
0x180046bd7  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x180046bdc  nop
0x180046bdd  lea     rcx, [rbp+57h+var_B0]
0x180046be1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180046be6  nop
0x180046be7  lea     rcx, [rbp+57h+var_C8]
0x180046beb  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180046bf0  nop
0x180046bf1  jmp     loc_180046D5C
0x180046bf6  mov     rsi, [rbp+57h+var_C0]
0x180046bfa  mov     edx, 1; int
0x180046bff  lea     rcx, [rsp+120h+var_D8]; this
0x180046c04  call    ?Impersonate@CVaultRpcImpersonate@@QEAAKH@Z; CVaultRpcImpersonate::Impersonate(int)
0x180046c09  mov     edi, eax
0x180046c0b  mov     [rsp+120h+var_E0], eax
0x180046c0f  test    eax, eax
0x180046c11  jz      short loc_180046C6E
0x180046c13  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c1a  cmp     rcx, rbx
0x180046c1d  jz      short loc_180046C41
0x180046c1f  test    byte ptr [rcx+1Ch], 2
0x180046c23  jz      short loc_180046C41
0x180046c25  mov     edx, 32h ; '2'
0x180046c2a  mov     r9d, eax
0x180046c2d  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x180046c34  mov     rcx, [rcx+10h]
0x180046c38  call    WPP_SF_d
0x180046c3d  mov     edi, [rsp+120h+var_E0]
0x180046c41  lea     rcx, [rbp+57h+var_90]; this
0x180046c45  call    ??1FnTracer@@QEAA@XZ; FnTracer::~FnTracer(void)
0x180046c4a  lea     rcx, [rsp+120h+var_D8]; this
0x180046c4f  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x180046c54  nop
0x180046c55  lea     rcx, [rbp+57h+var_B0]
0x180046c59  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180046c5e  nop
0x180046c5f  lea     rcx, [rbp+57h+var_C8]
0x180046c63  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180046c68  nop
0x180046c69  jmp     loc_180046D5C
0x180046c6e  mov     rcx, [rsi+8]
0x180046c72  mov     rax, [rcx]
0x180046c75  mov     rax, [rax+0D8h]
0x180046c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c81  xor     r8d, r8d
0x180046c84  mov     rdx, rax
0x180046c87  xor     ecx, ecx
0x180046c89  call    ?VaultAccessCheck@@YAHW4EVaultSecurableAction@@PEAVIVaultSecurable@@PEAH@Z; VaultAccessCheck(EVaultSecurableAction,IVaultSecurable *,int *)
0x180046c8e  test    eax, eax
0x180046c90  jnz     short loc_180046CF1
0x180046c92  mov     edi, 490h
0x180046c97  mov     [rsp+120h+var_E0], edi
0x180046c9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ca2  cmp     rcx, rbx
0x180046ca5  jz      short loc_180046CC7
0x180046ca7  test    byte ptr [rcx+1Ch], 2
0x180046cab  jz      short loc_180046CC7
0x180046cad  lea     edx, [rax+33h]
0x180046cb0  mov     r9d, edi
0x180046cb3  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x180046cba  mov     rcx, [rcx+10h]
0x180046cbe  call    WPP_SF_d
0x180046cc3  mov     edi, [rsp+120h+var_E0]
0x180046cc7  lea     rcx, [rbp+57h+var_90]; this
0x180046ccb  call    ??1FnTracer@@QEAA@XZ; FnTracer::~FnTracer(void)
0x180046cd0  lea     rcx, [rsp+120h+var_D8]; this
0x180046cd5  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x180046cda  nop
0x180046cdb  lea     rcx, [rbp+57h+var_B0]
0x180046cdf  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180046ce4  nop
0x180046ce5  lea     rcx, [rbp+57h+var_C8]
0x180046ce9  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180046cee  nop
0x180046cef  jmp     short loc_180046D5C
0x180046cf1  mov     r8d, r14d; unsigned int
0x180046cf4  mov     rdx, r15; struct _GUID *
0x180046cf7  mov     rcx, rsi; this
0x180046cfa  call    ?VaultDeleteSchema@@YAKPEAVCUserVault@@PEBU_GUID@@K@Z; VaultDeleteSchema(CUserVault *,_GUID const *,ulong)
0x180046cff  mov     edi, eax
0x180046d01  mov     [rsp+120h+var_E0], eax
0x180046d05  test    eax, eax
0x180046d07  jz      short loc_180046D34
0x180046d09  mov     rcx, cs:WPP_GLOBAL_Control
0x180046d10  cmp     rcx, rbx
0x180046d13  jz      short loc_180046D34
0x180046d15  test    byte ptr [rcx+1Ch], 2
0x180046d19  jz      short loc_180046D34
0x180046d1b  mov     edx, 34h ; '4'
0x180046d20  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x180046d27  mov     rcx, [rcx+10h]
0x180046d2b  call    WPP_SF_
0x180046d30  mov     edi, [rsp+120h+var_E0]
0x180046d34  lea     rcx, [rbp+57h+var_90]; this
0x180046d38  call    ??1FnTracer@@QEAA@XZ; FnTracer::~FnTracer(void)
0x180046d3d  lea     rcx, [rsp+120h+var_D8]; this
0x180046d42  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x180046d47  nop
0x180046d48  lea     rcx, [rbp+57h+var_B0]
0x180046d4c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180046d51  nop
0x180046d52  lea     rcx, [rbp+57h+var_C8]
0x180046d56  call    ?Delete@?$CVaultAutoPtr@PEAVCUserVault@@XPEAV1@$0A@@@QEAAXXZ; CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(void)
0x180046d5b  nop
0x180046d5c  mov     eax, edi
0x180046d5e  mov     rcx, [rbp+57h+var_40]
0x180046d62  xor     rcx, rsp; StackCookie
0x180046d65  call    __security_check_cookie
0x180046d6a  lea     r11, [rsp+120h+var_20]
0x180046d72  mov     rbx, [r11+30h]
0x180046d76  movaps  xmm6, xmmword ptr [r11-10h]
0x180046d7b  mov     rsp, r11
0x180046d7e  pop     r15
0x180046d80  pop     r14
0x180046d82  pop     rdi
0x180046d83  pop     rsi
0x180046d84  pop     rbp
0x180046d85  retn
```
