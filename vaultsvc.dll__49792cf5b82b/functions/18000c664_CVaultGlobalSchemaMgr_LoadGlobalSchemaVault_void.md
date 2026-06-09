# CVaultGlobalSchemaMgr::LoadGlobalSchemaVault(void)

- ea: `0x18000c664`
- end: `0x18000cad3`
- name: `?LoadGlobalSchemaVault@CVaultGlobalSchemaMgr@@QEAAKXZ`
- size: `1135`
- prototype: `unsigned int __fastcall(CVaultGlobalSchemaMgr *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800021e8`

## callees

- `0x180003140`
- `0x18000af40`
- `0x18000c348`
- `0x18000c664`
- `0x18000cadc`
- `0x18000d760`
- `0x180012210`
- `0x180037eb8`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18004b430`
- `0x18004d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c77a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000c77a`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000c7e4`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18000c7e4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c9f5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c9f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c718`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c718`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000c79f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000c79f`
- `profapi!__imp_ExpandEnvStringForUser` at `0x18000c741`
- `profapi!__imp_ExpandEnvStringForUser` at `0x18000c741`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVaultGlobalSchemaMgr::LoadGlobalSchemaVault(CVaultGlobalSchemaMgr *this)
{
  unsigned int v1; // esi
  const unsigned __int16 *v2; // rax
  const unsigned __int16 *v3; // rdi
  unsigned int v4; // ebx
  DWORD LastError; // eax
  PVOID *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned int GlobalSchemas; // eax
  CVaultGlobalSchemaMgr *v10; // rcx
  int v11; // r15d
  unsigned int v12; // ebx
  _QWORD *v13; // rsi
  unsigned int v14; // r14d
  CUserVault *v15; // rax
  unsigned int v16; // eax
  unsigned int i; // ebx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  unsigned int v21; // [rsp+30h] [rbp-69h] BYREF
  __int64 v22; // [rsp+38h] [rbp-61h] BYREF
  const unsigned __int16 *v23; // [rsp+40h] [rbp-59h]
  int v24; // [rsp+48h] [rbp-51h]
  HLOCAL hMem; // [rsp+50h] [rbp-49h] BYREF
  void **v26; // [rsp+58h] [rbp-41h] BYREF
  char v27; // [rsp+60h] [rbp-39h]
  int v28; // [rsp+64h] [rbp-35h]
  __int64 v29; // [rsp+68h] [rbp-31h]
  const unsigned __int16 *v30; // [rsp+70h] [rbp-29h]
  __int64 v31; // [rsp+78h] [rbp-21h] BYREF
  const unsigned __int16 *v32; // [rsp+80h] [rbp-19h]
  int v33; // [rsp+88h] [rbp-11h]
  __int128 Buf1; // [rsp+90h] [rbp-9h] BYREF

  v21 = 0;
  hMem = 0;
  v32 = 0;
  v33 = 0;
  v31 = 0;
  Buf1 = 0;
  v26 = &CVaultCall::`vftable';
  v27 = 1;
  v28 = 0;
  v29 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids);
  v23 = 0;
  v24 = 0;
  v22 = 0;
  v1 = 0;
  while ( 1 )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v22);
    v1 += 260;
    v2 = (const unsigned __int16 *)LocalAlloc(0x40u, 2LL * v1);
    v3 = v2;
    v30 = v2;
    v23 = v2;
    if ( !v2 )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v22);
      v4 = 14;
      goto LABEL_61;
    }
    v4 = ExpandEnvStringForUser(0, L"%ALLUSERSPROFILE%\\Microsoft\\Vault", v2, v1);
    if ( (v4 & 0x1FFF0000) == 0x70000 )
      v4 = (unsigned __int16)v4;
    if ( !v4 )
      break;
    if ( v4 != 122 )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v22);
LABEL_61:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_69;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_66;
      v7 = 32;
      v8 = v4;
      goto LABEL_64;
    }
  }
  if ( !(unsigned int)_o__wcsicmp(v3, L"%ALLUSERSPROFILE%\\Microsoft\\Vault") )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v22);
    v4 = 2016;
    goto LABEL_61;
  }
  v23 = 0;
  v32 = v3;
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v22);
  if ( CreateDirectoryW(v3, 0) || (LastError = GetLastError(), v4 = LastError, LastError == 183) )
  {
    if ( !ImpersonateSelf(SecurityImpersonation) )
    {
      LastError = GetLastError();
      v4 = LastError;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_69;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_66;
      v7 = 34;
LABEL_17:
      v8 = LastError;
LABEL_64:
      WPP_SF_d(v6[2], v7, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids, v8);
      goto LABEL_65;
    }
    GlobalSchemas = CVaultFactory::EnumerateVaultStore(
                      (CVaultFactory *)VaultGlobals::g_VaultFactory,
                      v3,
                      0,
                      (struct IVaultStore ***)&hMem,
                      &v21);
    v4 = GlobalSchemas;
    if ( GlobalSchemas )
    {
      if ( GlobalSchemas != 1168 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_54;
        v19 = 36;
        goto LABEL_53;
      }
    }
    else
    {
      v11 = 0;
      v12 = 0;
      v13 = hMem;
      v14 = v21;
      if ( v21 )
      {
        do
        {
          if ( !(*(unsigned int (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v13[v12] + 24LL))(v13[v12], &Buf1)
            && !memcmp_0(&Buf1, Vault_GlobalSchemaVault, 0x10u) )
          {
            v15 = (CUserVault *)CUserVault::InstantiateUserVaultObject(0, v13[v12], 0);
            VaultGlobals::g_GlobalSchemaMgr = v15;
            if ( v15 )
            {
              v27 = 0;
              v16 = CUserVault::UnlockVault(v15, (struct IVaultCall *)&v26, 0, 0);
              if ( v16 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    35,
                    WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids,
                    v16);
                (*(void (__fastcall **)(_QWORD))(*VaultGlobals::g_GlobalSchemaMgr + 8LL))(VaultGlobals::g_GlobalSchemaMgr);
                VaultGlobals::g_GlobalSchemaMgr = 0;
              }
              else
              {
                v11 = 1;
              }
            }
          }
          ++v12;
        }
        while ( v12 < v14 );
        v3 = v30;
      }
      for ( i = 0; i < v14; ++i )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[i] + 8LL))(v13[i]);
      if ( v13 )
        VaultFreeInternal(v13);
      if ( v11 )
      {
        GlobalSchemas = CVaultGlobalSchemaMgr::CreateGlobalSchemas(v10);
        v4 = GlobalSchemas;
        if ( !GlobalSchemas )
          goto LABEL_54;
        if ( GlobalSchemas == 183 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids);
          v4 = 0;
          goto LABEL_54;
        }
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        {
LABEL_54:
          RevertToSelf();
LABEL_65:
          v6 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_66;
        }
        v19 = 39;
LABEL_53:
        WPP_SF_d(v18[2], v19, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids, GlobalSchemas);
        goto LABEL_54;
      }
    }
    GlobalSchemas = CVaultGlobalSchemaMgr::CreateGlobalSchemaVault(v10, v3);
    v4 = GlobalSchemas;
    if ( !GlobalSchemas )
      goto LABEL_54;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_54;
    v19 = 37;
    goto LABEL_53;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_69;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 33;
    goto LABEL_17;
  }
LABEL_66:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_d(v6[2], 40, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids, v4);
LABEL_69:
  v26 = &CVaultCall::`vftable';
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v31);
  return v4;
}

```

## disassembly

```asm
0x18000c664  push    rbp
0x18000c666  push    rbx
0x18000c667  push    rsi
0x18000c668  push    rdi
0x18000c669  push    r12
0x18000c66b  push    r13
0x18000c66d  push    r14
0x18000c66f  push    r15
0x18000c671  lea     rbp, [rsp-1Fh]
0x18000c676  sub     rsp, 0B8h
0x18000c67d  mov     rax, cs:__security_cookie
0x18000c684  xor     rax, rsp
0x18000c687  mov     [rbp+57h+var_50], rax
0x18000c68b  xor     r13d, r13d
0x18000c68e  mov     [rbp+57h+var_C0], r13d
0x18000c692  mov     [rbp+57h+hMem], r13
0x18000c696  mov     [rbp+57h+var_70], r13
0x18000c69a  mov     [rbp+57h+var_68], r13d
0x18000c69e  mov     [rbp+57h+var_78], r13
0x18000c6a2  xorps   xmm0, xmm0
0x18000c6a5  movups  [rbp+57h+Buf1], xmm0
0x18000c6a9  lea     rax, ??_7CVaultCall@@6B@; const CVaultCall::`vftable'
0x18000c6b0  mov     [rbp+57h+var_98], rax
0x18000c6b4  mov     [rbp+57h+var_90], 1
0x18000c6b8  mov     [rbp+57h+var_8C], r13d
0x18000c6bc  mov     [rbp+57h+var_88], r13
0x18000c6c0  lea     r12, WPP_GLOBAL_Control
0x18000c6c7  lea     r14, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids
0x18000c6ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6d5  cmp     rcx, r12
0x18000c6d8  jz      short loc_18000C6F0
0x18000c6da  test    byte ptr [rcx+1Ch], 8
0x18000c6de  jz      short loc_18000C6F0
0x18000c6e0  lea     edx, [r13+1Fh]
0x18000c6e4  mov     r8, r14
0x18000c6e7  mov     rcx, [rcx+10h]
0x18000c6eb  call    WPP_SF_
0x18000c6f0  mov     [rbp+57h+var_B0], r13
0x18000c6f4  mov     [rbp+57h+var_A8], r13d
0x18000c6f8  mov     [rbp+57h+var_B8], r13
0x18000c6fc  mov     esi, r13d
0x18000c6ff  lea     rcx, [rbp+57h+var_B8]
0x18000c703  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000c708  add     esi, 104h
0x18000c70e  mov     edx, esi
0x18000c710  add     rdx, rdx; uBytes
0x18000c713  mov     ecx, 40h ; '@'; uFlags
0x18000c718  call    cs:__imp_LocalAlloc
0x18000c71e  mov     rdi, rax
0x18000c721  mov     [rbp+57h+var_80], rax
0x18000c725  mov     [rbp+57h+var_B0], rax
0x18000c729  test    rax, rax
0x18000c72c  jz      loc_18000CA3C
0x18000c732  mov     r9d, esi
0x18000c735  mov     r8, rax
0x18000c738  lea     rdx, aAllusersprofil; "%ALLUSERSPROFILE%\\Microsoft\\Vault"
0x18000c73f  xor     ecx, ecx
0x18000c741  call    cs:__imp_ExpandEnvStringForUser
0x18000c747  mov     ebx, eax
0x18000c749  and     eax, 1FFF0000h
0x18000c74e  cmp     eax, 70000h
0x18000c753  jnz     short loc_18000C758
0x18000c755  movzx   ebx, bx
0x18000c758  test    ebx, ebx
0x18000c75a  jz      short loc_18000C770
0x18000c75c  cmp     ebx, 7Ah ; 'z'
0x18000c75f  jz      short loc_18000C6FF
0x18000c761  lea     rcx, [rbp+57h+var_B8]
0x18000c765  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000c76a  nop
0x18000c76b  jmp     loc_18000CA4B
0x18000c770  lea     rdx, aAllusersprofil; "%ALLUSERSPROFILE%\\Microsoft\\Vault"
0x18000c777  mov     rcx, rdi
0x18000c77a  call    cs:__imp__o__wcsicmp
0x18000c780  test    eax, eax
0x18000c782  jz      loc_18000CA2B
0x18000c788  mov     [rbp+57h+var_B0], r13
0x18000c78c  mov     [rbp+57h+var_70], rdi
0x18000c790  lea     rcx, [rbp+57h+var_B8]
0x18000c794  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000c799  nop
0x18000c79a  xor     edx, edx; lpSecurityAttributes
0x18000c79c  mov     rcx, rdi; lpPathName
0x18000c79f  call    cs:__imp_CreateDirectoryW
0x18000c7a5  test    eax, eax
0x18000c7a7  jnz     short loc_18000C7DF
0x18000c7a9  call    cs:__imp_GetLastError
0x18000c7af  mov     ebx, eax
0x18000c7b1  cmp     eax, 0B7h
0x18000c7b6  jz      short loc_18000C7DF
0x18000c7b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7bf  cmp     rcx, r12
0x18000c7c2  jz      loc_18000CA9C
0x18000c7c8  test    byte ptr [rcx+1Ch], 1
0x18000c7cc  jz      loc_18000CA78
0x18000c7d2  mov     edx, 21h ; '!'
0x18000c7d7  mov     r9d, eax
0x18000c7da  jmp     loc_18000CA65
0x18000c7df  mov     ecx, 2; ImpersonationLevel
0x18000c7e4  call    cs:__imp_ImpersonateSelf
0x18000c7ea  test    eax, eax
0x18000c7ec  jnz     short loc_18000C817
0x18000c7ee  call    cs:__imp_GetLastError
0x18000c7f4  mov     ebx, eax
0x18000c7f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7fd  cmp     rcx, r12
0x18000c800  jz      loc_18000CA9C
0x18000c806  test    byte ptr [rcx+1Ch], 1
0x18000c80a  jz      loc_18000CA78
0x18000c810  mov     edx, 22h ; '"'
0x18000c815  jmp     short loc_18000C7D7
0x18000c817  lea     rax, [rbp+57h+var_C0]
0x18000c81b  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x18000c820  lea     r9, [rbp+57h+hMem]; struct IVaultStore ***
0x18000c824  xor     r8d, r8d; unsigned __int8
0x18000c827  mov     rdx, rdi; unsigned __int16 *
0x18000c82a  lea     rcx, ?g_VaultFactory@VaultGlobals@@3VCVaultFactory@@A; this
0x18000c831  call    ?EnumerateVaultStore@CVaultFactory@@UEAAKPEBGEPEAPEAPEAUIVaultStore@@PEAK@Z; CVaultFactory::EnumerateVaultStore(ushort const *,uchar,IVaultStore * * *,ulong *)
0x18000c836  mov     ebx, eax
0x18000c838  test    eax, eax
0x18000c83a  jnz     loc_18000C9C8
0x18000c840  mov     r15d, r13d
0x18000c843  mov     ebx, r13d
0x18000c846  mov     rsi, [rbp+57h+hMem]
0x18000c84a  mov     r14d, [rbp+57h+var_C0]
0x18000c84e  test    r14d, r14d
0x18000c851  jz      loc_18000C92F
0x18000c857  lea     rdi, WPP_GLOBAL_Control
0x18000c85e  mov     r12d, ebx
0x18000c861  mov     rcx, [rsi+r12*8]
0x18000c865  mov     rax, [rcx]
0x18000c868  lea     rdx, [rbp+57h+Buf1]
0x18000c86c  mov     rax, [rax+18h]
0x18000c870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c875  test    eax, eax
0x18000c877  jnz     loc_18000C919
0x18000c87d  lea     r8d, [rax+10h]; Size
0x18000c881  lea     rdx, Vault_GlobalSchemaVault; Buf2
0x18000c888  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18000c88c  call    memcmp_0
0x18000c891  test    eax, eax
0x18000c893  jnz     loc_18000C919
0x18000c899  xor     r8d, r8d
0x18000c89c  mov     rdx, [rsi+r12*8]
0x18000c8a0  xor     ecx, ecx
0x18000c8a2  call    ?InstantiateUserVaultObject@CUserVault@@SAPEAV1@PEAVCUserVaultMgr@@PEAUIVaultStore@@W4efVaultFlags@@@Z; CUserVault::InstantiateUserVaultObject(CUserVaultMgr *,IVaultStore *,efVaultFlags)
0x18000c8a7  mov     cs:?g_GlobalSchemaMgr@VaultGlobals@@3VCVaultGlobalSchemaMgr@@A, rax; CVaultGlobalSchemaMgr VaultGlobals::g_GlobalSchemaMgr
0x18000c8ae  test    rax, rax
0x18000c8b1  jz      short loc_18000C919
0x18000c8b3  mov     [rbp+57h+var_90], r13b
0x18000c8b7  xor     r9d, r9d; struct _LUID *
0x18000c8ba  xor     r8d, r8d; struct _GUID *
0x18000c8bd  lea     rdx, [rbp+57h+var_98]; struct IVaultCall *
0x18000c8c1  mov     rcx, rax; this
0x18000c8c4  call    ?UnlockVault@CUserVault@@QEAAKPEAUIVaultCall@@PEBU_GUID@@PEAU_LUID@@@Z; CUserVault::UnlockVault(IVaultCall *,_GUID const *,_LUID *)
0x18000c8c9  test    eax, eax
0x18000c8cb  jz      short loc_18000C913
0x18000c8cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8d4  cmp     rcx, rdi
0x18000c8d7  jz      short loc_18000C8F7
0x18000c8d9  test    byte ptr [rcx+1Ch], 2
0x18000c8dd  jz      short loc_18000C8F7
0x18000c8df  mov     edx, 23h ; '#'
0x18000c8e4  mov     r9d, eax
0x18000c8e7  lea     r8, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids
0x18000c8ee  mov     rcx, [rcx+10h]
0x18000c8f2  call    WPP_SF_d
0x18000c8f7  mov     rcx, cs:?g_GlobalSchemaMgr@VaultGlobals@@3VCVaultGlobalSchemaMgr@@A; CVaultGlobalSchemaMgr VaultGlobals::g_GlobalSchemaMgr
0x18000c8fe  mov     rax, [rcx]
0x18000c901  mov     rax, [rax+8]
0x18000c905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c90a  mov     cs:?g_GlobalSchemaMgr@VaultGlobals@@3VCVaultGlobalSchemaMgr@@A, r13; CVaultGlobalSchemaMgr VaultGlobals::g_GlobalSchemaMgr
0x18000c911  jmp     short loc_18000C919
0x18000c913  mov     r15d, 1
0x18000c919  inc     ebx
0x18000c91b  cmp     ebx, r14d
0x18000c91e  jb      loc_18000C85E
0x18000c924  mov     rdi, [rbp+57h+var_80]
0x18000c928  lea     r12, WPP_GLOBAL_Control
0x18000c92f  mov     ebx, r13d
0x18000c932  test    r14d, r14d
0x18000c935  jz      short loc_18000C950
0x18000c937  mov     eax, ebx
0x18000c939  mov     rcx, [rsi+rax*8]
0x18000c93d  mov     rax, [rcx]
0x18000c940  mov     rax, [rax+8]
0x18000c944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c949  inc     ebx
0x18000c94b  cmp     ebx, r14d
0x18000c94e  jb      short loc_18000C937
0x18000c950  test    rsi, rsi
0x18000c953  jz      short loc_18000C95D
0x18000c955  mov     rcx, rsi; hMem
0x18000c958  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x18000c95d  test    r15d, r15d
0x18000c960  jz      loc_18000C9FD
0x18000c966  call    ?CreateGlobalSchemas@CVaultGlobalSchemaMgr@@AEAAKXZ; CVaultGlobalSchemaMgr::CreateGlobalSchemas(void)
0x18000c96b  mov     ebx, eax
0x18000c96d  test    eax, eax
0x18000c96f  jz      loc_18000C9F5
0x18000c975  cmp     eax, 0B7h
0x18000c97a  jz      short loc_18000C99C
0x18000c97c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c983  cmp     rcx, r12
0x18000c986  jz      short loc_18000C9F5
0x18000c988  test    byte ptr [rcx+1Ch], 2
0x18000c98c  jz      short loc_18000C9F5
0x18000c98e  mov     edx, 27h ; '''
0x18000c993  lea     r8, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids
0x18000c99a  jmp     short loc_18000C9E9
0x18000c99c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9a3  cmp     rcx, r12
0x18000c9a6  jz      short loc_18000C9C3
0x18000c9a8  test    byte ptr [rcx+1Ch], 8
0x18000c9ac  jz      short loc_18000C9C3
0x18000c9ae  mov     edx, 26h ; '&'
0x18000c9b3  lea     r8, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids
0x18000c9ba  mov     rcx, [rcx+10h]
0x18000c9be  call    WPP_SF_
0x18000c9c3  mov     ebx, r13d
0x18000c9c6  jmp     short loc_18000C9F5
0x18000c9c8  cmp     eax, 490h
0x18000c9cd  jz      short loc_18000CA04
0x18000c9cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9d6  cmp     rcx, r12
0x18000c9d9  jz      short loc_18000C9F5
0x18000c9db  test    byte ptr [rcx+1Ch], 2
0x18000c9df  jz      short loc_18000C9F5
0x18000c9e1  mov     edx, 24h ; '$'
0x18000c9e6  mov     r8, r14
0x18000c9e9  mov     r9d, eax
0x18000c9ec  mov     rcx, [rcx+10h]
0x18000c9f0  call    WPP_SF_d
0x18000c9f5  call    cs:__imp_RevertToSelf
0x18000c9fb  jmp     short loc_18000CA71
0x18000c9fd  lea     r14, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids
0x18000ca04  mov     rdx, rdi; unsigned __int16 *
0x18000ca07  call    ?CreateGlobalSchemaVault@CVaultGlobalSchemaMgr@@AEAAKPEBG@Z; CVaultGlobalSchemaMgr::CreateGlobalSchemaVault(ushort const *)
0x18000ca0c  mov     ebx, eax
0x18000ca0e  test    eax, eax
0x18000ca10  jz      short loc_18000C9F5
0x18000ca12  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca19  cmp     rcx, r12
0x18000ca1c  jz      short loc_18000C9F5
0x18000ca1e  test    byte ptr [rcx+1Ch], 1
0x18000ca22  jz      short loc_18000C9F5
0x18000ca24  mov     edx, 25h ; '%'
0x18000ca29  jmp     short loc_18000C9E6
0x18000ca2b  lea     rcx, [rbp+57h+var_B8]
0x18000ca2f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000ca34  nop
0x18000ca35  mov     ebx, 7E0h
0x18000ca3a  jmp     short loc_18000CA4B
0x18000ca3c  lea     rcx, [rbp+57h+var_B8]
0x18000ca40  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000ca45  nop
0x18000ca46  mov     ebx, 0Eh
0x18000ca4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca52  cmp     rcx, r12
0x18000ca55  jz      short loc_18000CA9C
0x18000ca57  test    byte ptr [rcx+1Ch], 1
0x18000ca5b  jz      short loc_18000CA78
0x18000ca5d  mov     edx, 20h ; ' '
0x18000ca62  mov     r9d, ebx
0x18000ca65  mov     r8, r14
0x18000ca68  mov     rcx, [rcx+10h]
0x18000ca6c  call    WPP_SF_d
0x18000ca71  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca78  cmp     rcx, r12
0x18000ca7b  jz      short loc_18000CA9C
0x18000ca7d  test    byte ptr [rcx+1Ch], 8
0x18000ca81  jz      short loc_18000CA9C
0x18000ca83  mov     edx, 28h ; '('
0x18000ca88  mov     r9d, ebx
0x18000ca8b  lea     r8, WPP_74c7e70425c233ec77b6ce648993cd63_Traceguids
0x18000ca92  mov     rcx, [rcx+10h]
0x18000ca96  call    WPP_SF_d
0x18000ca9b  nop
0x18000ca9c  lea     rax, ??_7CVaultCall@@6B@; const CVaultCall::`vftable'
0x18000caa3  mov     [rbp+57h+var_98], rax
0x18000caa7  lea     rcx, [rbp+57h+var_78]
0x18000caab  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18000cab0  nop
0x18000cab1  mov     eax, ebx
0x18000cab3  mov     rcx, [rbp+57h+var_50]
0x18000cab7  xor     rcx, rsp; StackCookie
0x18000caba  call    __security_check_cookie
0x18000cabf  add     rsp, 0B8h
0x18000cac6  pop     r15
0x18000cac8  pop     r14
0x18000caca  pop     r13
0x18000cacc  pop     r12
0x18000cace  pop     rdi
0x18000cacf  pop     rsi
0x18000cad0  pop     rbx
0x18000cad1  pop     rbp
0x18000cad2  retn
```
