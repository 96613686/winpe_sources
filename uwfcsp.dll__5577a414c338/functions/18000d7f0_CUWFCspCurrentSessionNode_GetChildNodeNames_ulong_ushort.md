# CUWFCspCurrentSessionNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x18000d7f0`
- end: `0x18000dcaa`
- name: `?GetChildNodeNames@CUWFCspCurrentSessionNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `1210`
- prototype: `__int64 __fastcall(CUWFCspCurrentSessionNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800068f4`
- `0x18000c1d4`
- `0x18000d0d8`
- `0x18000d7f0`
- `0x18001b010`

## import_xrefs

- `msvcrt!free` at `0x18000db2d`
- `msvcrt!free` at `0x18000db82`
- `msvcrt!free` at `0x18000dbd7`
- `msvcrt!free` at `0x18000dc39`
- `msvcrt!free` at `0x18000dc53`
- `msvcrt!free` at `0x18000dc6d`
- `msvcrt!free` at `0x18000db2d`
- `msvcrt!free` at `0x18000db82`
- `msvcrt!free` at `0x18000dbd7`
- `msvcrt!free` at `0x18000dc39`
- `msvcrt!free` at `0x18000dc53`
- `msvcrt!free` at `0x18000dc6d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d95a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dabe`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d95a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dabe`
- `OLEAUT32!__imp_SysFreeString` at `0x18000db15`
- `OLEAUT32!__imp_SysFreeString` at `0x18000db6a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dbbf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc12`
- `OLEAUT32!__imp_SysFreeString` at `0x18000db15`
- `OLEAUT32!__imp_SysFreeString` at `0x18000db6a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dbbf`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d931`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000da92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d931`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000da92`
- `uwfcfgmgmt!UwfCfgGetFileExclusions` at `0x18000d8bb`
- `uwfcfgmgmt!UwfCfgGetFileExclusions` at `0x18000d8bb`
- `uwfcfgmgmt!UwfCfgGetVolumes` at `0x18000d9a0`
- `uwfcfgmgmt!UwfCfgGetVolumes` at `0x18000d9a0`
- `uwfcfgmgmt!UwfCfgGetRegExclusions` at `0x18000d9c1`
- `uwfcfgmgmt!UwfCfgGetRegExclusions` at `0x18000d9c1`

## string_xrefs

- `0x18000da2f`: `MaximumOverlaySize`
- `0x18000da50`: `RegistryExclusions`
- `0x18000d919`: `CommitFile`
- `0x18000d925`: `CommitFileDeletion`
- `0x18000da7c`: `CommitRegistry`
- `0x18000da87`: `CommitRegistryDeletion`
- `0x18000d97b`: `onecore\base\uwf\uwfcsp\precomp.h`

## pseudocode

```c
__int64 __fastcall CUWFCspCurrentSessionNode::GetChildNodeNames(
        CUWFCspCurrentSessionNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3)
{
  CUWFCspCurrentSessionNode *v5; // rdx
  int v6; // ecx
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // ecx
  int RegExclusions; // ebx
  __int64 v11; // rcx
  void **p_Block; // r8
  __int64 v13; // rbx
  unsigned __int16 **v14; // rax
  unsigned __int16 **v15; // r15
  unsigned int v16; // r14d
  BSTR v17; // rax
  __int64 v18; // rbx
  unsigned __int16 **v19; // rax
  BSTR v20; // rax
  unsigned int v21; // r15d
  int i; // r14d
  unsigned int v23; // r15d
  int v24; // r14d
  unsigned int v25; // r15d
  int v26; // r14d
  BSTR *v27; // r15
  unsigned int v28; // r12d
  unsigned int m; // r14d
  void *v31; // [rsp+20h] [rbp-E0h] BYREF
  __int64 k; // [rsp+28h] [rbp-D8h]
  void *v33; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v34; // [rsp+38h] [rbp-C8h]
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  __int64 j; // [rsp+48h] [rbp-B8h]
  OLECHAR *psz[6]; // [rsp+50h] [rbp-B0h]
  OLECHAR *v38[24]; // [rsp+80h] [rbp-80h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]
  __int64 v40; // [rsp+158h] [rbp+58h] BYREF

  v40 = 0;
  Block = 0;
  v5 = this;
  j = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  k = 0;
  if ( !a2 || !a3 )
  {
    RegExclusions = -2147024809;
    goto LABEL_32;
  }
  *a2 = 0;
  *a3 = 0;
  v6 = *((_DWORD *)this + 11) - 1;
  if ( !v6 )
  {
    v18 = 128;
    v38[0] = L"FilterEnabled";
    v38[1] = L"OverlayConsumption";
    v38[2] = L"AvailableOverlaySpace";
    v38[3] = L"CriticalOverlayThreshold";
    v38[4] = L"WarningOverlayThreshold";
    v38[5] = L"OverlayType";
    v38[6] = L"OverlayFlags";
    v38[7] = L"MaximumOverlaySize";
    v38[8] = L"PersistDomainSecretKey";
    v38[9] = L"PersistTSCAL";
    v38[10] = L"RegistryExclusions";
    v38[11] = L"ServicingEnabled";
    v38[12] = L"Volume";
    v38[13] = L"ShutdownPending";
    v38[14] = L"CommitRegistry";
    v38[15] = L"CommitRegistryDeletion";
    v19 = (unsigned __int16 **)CoTaskMemAlloc(0x80u);
    v15 = v19;
    if ( v19 )
    {
      v16 = 0;
      do
      {
        *(_BYTE *)v19 = 0;
        v19 = (unsigned __int16 **)((char *)v19 + 1);
        --v18;
      }
      while ( v18 );
      while ( 1 )
      {
        v20 = SysAllocString(v38[v16]);
        v15[v16] = v20;
        if ( !v20 )
          goto LABEL_19;
        if ( ++v16 >= 0x10 )
        {
LABEL_30:
          *a3 = v15;
          RegExclusions = 0;
          *a2 = v16;
          goto LABEL_32;
        }
      }
    }
LABEL_25:
    RegExclusions = -2147024882;
    goto LABEL_32;
  }
  v7 = (unsigned int)(v6 - 12);
  if ( !(_DWORD)v7 )
  {
    LODWORD(v7) = 1;
    RegExclusions = UwfCfgGetRegExclusions(v7, &v31);
    if ( RegExclusions >= 0 )
    {
      p_Block = &v31;
      goto LABEL_12;
    }
    goto LABEL_32;
  }
  v8 = (unsigned int)(v7 - 4);
  if ( (_DWORD)v8 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      if ( v9 != 5 )
      {
        *a2 = 0;
        *a3 = 0;
        RegExclusions = -2046820335;
        goto LABEL_32;
      }
      RegExclusions = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(**((_QWORD **)v5 + 3) + 88LL))(
                        *((_QWORD *)v5 + 3),
                        3,
                        &v40);
      if ( RegExclusions >= 0 )
      {
        LOBYTE(v11) = 1;
        RegExclusions = UwfCfgGetFileExclusions(v11, v40, &v33);
        if ( RegExclusions >= 0 )
        {
          p_Block = &v33;
LABEL_12:
          RegExclusions = ConstructBSTRArray(a3, a2, (__int64)p_Block);
          goto LABEL_32;
        }
      }
      goto LABEL_32;
    }
    v13 = 48;
    psz[0] = L"Protected";
    psz[1] = L"BindByDriveLetter";
    psz[2] = L"DriveLetter";
    psz[3] = L"Exclusions";
    psz[4] = L"CommitFile";
    psz[5] = L"CommitFileDeletion";
    v14 = (unsigned __int16 **)CoTaskMemAlloc(0x30u);
    v15 = v14;
    if ( v14 )
    {
      v16 = 0;
      do
      {
        *(_BYTE *)v14 = 0;
        v14 = (unsigned __int16 **)((char *)v14 + 1);
        --v13;
      }
      while ( v13 );
      while ( 1 )
      {
        v17 = SysAllocString(psz[v16]);
        v15[v16] = v17;
        if ( !v17 )
          break;
        if ( ++v16 >= 6 )
          goto LABEL_30;
      }
LABEL_19:
      RegExclusions = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecore\\base\\uwf\\uwfcsp\\precomp.h",
        (const char *)0x8007000ELL,
        (int)v31);
      goto LABEL_32;
    }
    goto LABEL_25;
  }
  LODWORD(v8) = 1;
  RegExclusions = UwfCfgGetVolumes(v8, &Block);
  if ( RegExclusions >= 0 )
  {
    p_Block = &Block;
    goto LABEL_12;
  }
LABEL_32:
  v21 = j;
  for ( i = 0; i < v21; ++i )
  {
    if ( i < 0 || i >= (int)j )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, (int)v5, (unsigned int)a3);
      JUMPOUT(0x18000DCA9LL);
    }
    SysFreeString(*((BSTR *)Block + i));
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  v23 = k;
  v24 = 0;
  for ( j = 0; v24 < v23; ++v24 )
  {
    if ( v24 < 0 || v24 >= (int)k )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, (int)v5, (unsigned int)a3);
      __debugbreak();
    }
    SysFreeString(*((BSTR *)v31 + v24));
  }
  if ( v31 )
  {
    free(v31);
    v31 = 0;
  }
  v25 = v34;
  v26 = 0;
  for ( k = 0; v26 < v25; ++v26 )
  {
    if ( v26 < 0 || v26 >= (int)v34 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, (int)v5, (unsigned int)a3);
      __debugbreak();
    }
    SysFreeString(*((BSTR *)v33 + v26));
  }
  if ( v33 )
  {
    free(v33);
    v33 = 0;
  }
  v34 = 0;
  if ( (int)(RegExclusions + 0x80000000) >= 0 && RegExclusions != -2147024809 )
  {
    v27 = *a3;
    if ( *a3 )
    {
      v28 = *a2;
      for ( m = 0; m < v28; ++m )
        SysFreeString(v27[m]);
      CoTaskMemFree(v27);
    }
    *a3 = 0;
    *a2 = 0;
  }
  if ( v31 )
  {
    free(v31);
    v31 = 0;
  }
  k = 0;
  if ( v33 )
  {
    free(v33);
    v33 = 0;
  }
  v34 = 0;
  if ( Block )
    free(Block);
  return (unsigned int)RegExclusions;
}

```

## disassembly

```asm
0x18000d7f0  push    rbp
0x18000d7f2  push    rbx
0x18000d7f3  push    rsi
0x18000d7f4  push    rdi
0x18000d7f5  push    r12
0x18000d7f7  push    r13
0x18000d7f9  push    r14
0x18000d7fb  push    r15
0x18000d7fd  lea     rbp, [rsp-8]
0x18000d802  sub     rsp, 108h
0x18000d809  xor     r13d, r13d
0x18000d80c  mov     rsi, rdx
0x18000d80f  mov     [rbp+40h+arg_8], r13
0x18000d813  mov     rdi, r8
0x18000d816  mov     [rsp+140h+Block], r13
0x18000d81b  mov     rdx, rcx; int
0x18000d81e  mov     [rsp+140h+var_F8], r13
0x18000d823  mov     r12d, 80070057h
0x18000d829  mov     [rsp+140h+var_110], r13
0x18000d82e  mov     [rsp+140h+var_108], r13
0x18000d833  mov     [rsp+140h+var_120], r13; int
0x18000d838  mov     [rsp+140h+var_118], r13
0x18000d83d  test    rsi, rsi
0x18000d840  jz      loc_18000DAE5
0x18000d846  test    r8, r8
0x18000d849  jz      loc_18000DAE5
0x18000d84f  mov     [rsi], r13d
0x18000d852  mov     [r8], r13
0x18000d855  mov     ecx, [rcx+2Ch]
0x18000d858  sub     ecx, 1
0x18000d85b  jz      loc_18000D9DB
0x18000d861  sub     ecx, 0Ch
0x18000d864  jz      loc_18000D9BA
0x18000d86a  sub     ecx, 4
0x18000d86d  jz      loc_18000D999
0x18000d873  sub     ecx, 1
0x18000d876  jz      short loc_18000D8E2
0x18000d878  cmp     ecx, 5
0x18000d87b  jz      short loc_18000D88D
0x18000d87d  mov     [rsi], r13d
0x18000d880  mov     [r8], r13
0x18000d883  mov     ebx, 86000011h
0x18000d888  jmp     loc_18000DAE8
0x18000d88d  mov     rcx, [rdx+18h]
0x18000d891  lea     r8, [rbp+40h+arg_8]
0x18000d895  mov     edx, 3
0x18000d89a  mov     rax, [rcx]
0x18000d89d  mov     rax, [rax+58h]
0x18000d8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8a6  mov     ebx, eax
0x18000d8a8  test    eax, eax
0x18000d8aa  js      loc_18000DAE8
0x18000d8b0  mov     rdx, [rbp+40h+arg_8]
0x18000d8b4  lea     r8, [rsp+140h+var_110]
0x18000d8b9  mov     cl, 1
0x18000d8bb  call    cs:__imp_?UwfCfgGetFileExclusions@@YAJ_NPEBGPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; UwfCfgGetFileExclusions(bool,ushort const *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x18000d8c1  mov     ebx, eax
0x18000d8c3  test    eax, eax
0x18000d8c5  js      loc_18000DAE8
0x18000d8cb  lea     r8, [rsp+140h+var_110]
0x18000d8d0  mov     rdx, rsi
0x18000d8d3  mov     rcx, rdi
0x18000d8d6  call    ?ConstructBSTRArray@@YAJPEAPEAPEAGPEAKAEBV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; ConstructBSTRArray(ushort * * *,ulong *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> const &)
0x18000d8db  mov     ebx, eax
0x18000d8dd  jmp     loc_18000DAE8
0x18000d8e2  lea     rax, aProtected; "Protected"
0x18000d8e9  mov     ebx, 30h ; '0'
0x18000d8ee  mov     [rsp+140h+psz], rax
0x18000d8f3  mov     ecx, ebx; cb
0x18000d8f5  lea     rax, aBindbydrivelet; "BindByDriveLetter"
0x18000d8fc  mov     [rsp+140h+var_E8], rax
0x18000d901  lea     rax, aDriveletter; "DriveLetter"
0x18000d908  mov     [rsp+140h+var_E0], rax
0x18000d90d  lea     rax, aExclusions; "Exclusions"
0x18000d914  mov     [rsp+140h+var_D8], rax
0x18000d919  lea     rax, aCommitfile; "CommitFile"
0x18000d920  mov     [rsp+140h+var_D0], rax
0x18000d925  lea     rax, aCommitfiledele; "CommitFileDeletion"
0x18000d92c  mov     [rsp+140h+var_C8], rax
0x18000d931  call    cs:__imp_CoTaskMemAlloc
0x18000d937  mov     r15, rax
0x18000d93a  test    rax, rax
0x18000d93d  jz      loc_18000DAA0
0x18000d943  mov     r14d, r13d
0x18000d946  mov     [rax], r13b
0x18000d949  inc     rax
0x18000d94c  sub     rbx, 1
0x18000d950  jnz     short loc_18000D946
0x18000d952  mov     ebx, r14d
0x18000d955  mov     rcx, [rsp+rbx*8+140h+psz]; psz
0x18000d95a  call    cs:__imp_SysAllocString
0x18000d960  mov     [r15+rbx*8], rax
0x18000d964  test    rax, rax
0x18000d967  jz      short loc_18000D977
0x18000d969  inc     r14d
0x18000d96c  cmp     r14d, 6
0x18000d970  jb      short loc_18000D952
0x18000d972  jmp     loc_18000DADA
0x18000d977  mov     rcx, [rbp+48h]; this
0x18000d97b  lea     r8, aOnecoreBaseUwf; "onecore\\base\\uwf\\uwfcsp\\precomp.h"
0x18000d982  mov     ebx, 8007000Eh
0x18000d987  mov     edx, 9Eh; void *
0x18000d98c  mov     r9d, ebx; char *
0x18000d98f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d994  jmp     loc_18000DAE8
0x18000d999  lea     rdx, [rsp+140h+Block]
0x18000d99e  mov     cl, 1
0x18000d9a0  call    cs:__imp_?UwfCfgGetVolumes@@YAJ_NPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; UwfCfgGetVolumes(bool,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x18000d9a6  mov     ebx, eax
0x18000d9a8  test    eax, eax
0x18000d9aa  js      loc_18000DAE8
0x18000d9b0  lea     r8, [rsp+140h+Block]
0x18000d9b5  jmp     loc_18000D8D0
0x18000d9ba  lea     rdx, [rsp+140h+var_120]
0x18000d9bf  mov     cl, 1
0x18000d9c1  call    cs:__imp_?UwfCfgGetRegExclusions@@YAJ_NPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; UwfCfgGetRegExclusions(bool,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x18000d9c7  mov     ebx, eax
0x18000d9c9  test    eax, eax
0x18000d9cb  js      loc_18000DAE8
0x18000d9d1  lea     r8, [rsp+140h+var_120]
0x18000d9d6  jmp     loc_18000D8D0
0x18000d9db  lea     rax, aFilterenabled; "FilterEnabled"
0x18000d9e2  mov     ebx, 80h
0x18000d9e7  mov     [rbp+40h+var_C0], rax
0x18000d9eb  mov     ecx, ebx; cb
0x18000d9ed  lea     rax, aOverlayconsump; "OverlayConsumption"
0x18000d9f4  mov     [rbp+40h+var_B8], rax
0x18000d9f8  lea     rax, aAvailableoverl; "AvailableOverlaySpace"
0x18000d9ff  mov     [rbp+40h+var_B0], rax
0x18000da03  lea     rax, aCriticaloverla; "CriticalOverlayThreshold"
0x18000da0a  mov     [rbp+40h+var_A8], rax
0x18000da0e  lea     rax, aWarningoverlay; "WarningOverlayThreshold"
0x18000da15  mov     [rbp+40h+var_A0], rax
0x18000da19  lea     rax, aOverlaytype; "OverlayType"
0x18000da20  mov     [rbp+40h+var_98], rax
0x18000da24  lea     rax, aOverlayflags; "OverlayFlags"
0x18000da2b  mov     [rbp+40h+var_90], rax
0x18000da2f  lea     rax, aMaximumoverlay; "MaximumOverlaySize"
0x18000da36  mov     [rbp+40h+var_88], rax
0x18000da3a  lea     rax, aPersistdomains; "PersistDomainSecretKey"
0x18000da41  mov     [rbp+40h+var_80], rax
0x18000da45  lea     rax, aPersisttscal; "PersistTSCAL"
0x18000da4c  mov     [rbp+40h+var_78], rax
0x18000da50  lea     rax, aRegistryexclus; "RegistryExclusions"
0x18000da57  mov     [rbp+40h+var_70], rax
0x18000da5b  lea     rax, aServicingenabl; "ServicingEnabled"
0x18000da62  mov     [rbp+40h+var_68], rax
0x18000da66  lea     rax, aVolume; "Volume"
0x18000da6d  mov     [rbp+40h+var_60], rax
0x18000da71  lea     rax, aShutdownpendin; "ShutdownPending"
0x18000da78  mov     [rbp+40h+var_58], rax
0x18000da7c  lea     rax, aCommitregistry_0; "CommitRegistry"
0x18000da83  mov     [rbp+40h+var_50], rax
0x18000da87  lea     rax, aCommitregistry; "CommitRegistryDeletion"
0x18000da8e  mov     [rbp+40h+var_48], rax
0x18000da92  call    cs:__imp_CoTaskMemAlloc
0x18000da98  mov     r15, rax
0x18000da9b  test    rax, rax
0x18000da9e  jnz     short loc_18000DAA7
0x18000daa0  mov     ebx, 8007000Eh
0x18000daa5  jmp     short loc_18000DAE8
0x18000daa7  mov     r14d, r13d
0x18000daaa  mov     [rax], r13b
0x18000daad  inc     rax
0x18000dab0  sub     rbx, 1
0x18000dab4  jnz     short loc_18000DAAA
0x18000dab6  mov     ebx, r14d
0x18000dab9  mov     rcx, [rbp+rbx*8+40h+var_C0]; psz
0x18000dabe  call    cs:__imp_SysAllocString
0x18000dac4  mov     [r15+rbx*8], rax
0x18000dac8  test    rax, rax
0x18000dacb  jz      loc_18000D977
0x18000dad1  inc     r14d
0x18000dad4  cmp     r14d, 10h
0x18000dad8  jb      short loc_18000DAB6
0x18000dada  mov     [rdi], r15
0x18000dadd  mov     ebx, r13d
0x18000dae0  mov     [rsi], r14d
0x18000dae3  jmp     short loc_18000DAE8
0x18000dae5  mov     ebx, r12d
0x18000dae8  mov     r15d, dword ptr [rsp+140h+var_F8]
0x18000daed  mov     r14d, r13d
0x18000daf0  test    r15d, r15d
0x18000daf3  jz      short loc_18000DB23
0x18000daf5  test    r14d, r14d
0x18000daf8  js      loc_18000DC9F
0x18000dafe  cmp     r14d, dword ptr [rsp+140h+var_F8]
0x18000db03  jge     loc_18000DC9F
0x18000db09  mov     rcx, [rsp+140h+Block]
0x18000db0e  movsxd  rax, r14d
0x18000db11  mov     rcx, [rcx+rax*8]; bstrString
0x18000db15  call    cs:__imp_SysFreeString
0x18000db1b  inc     r14d
0x18000db1e  cmp     r14d, r15d
0x18000db21  jb      short loc_18000DAF5
0x18000db23  mov     rcx, [rsp+140h+Block]; Block
0x18000db28  test    rcx, rcx
0x18000db2b  jz      short loc_18000DB38
0x18000db2d  call    cs:__imp_free
0x18000db33  mov     [rsp+140h+Block], r13
0x18000db38  mov     r15d, dword ptr [rsp+140h+var_118]
0x18000db3d  mov     r14d, r13d
0x18000db40  mov     [rsp+140h+var_F8], r13
0x18000db45  test    r15d, r15d
0x18000db48  jz      short loc_18000DB78
0x18000db4a  test    r14d, r14d
0x18000db4d  js      loc_18000DC89
0x18000db53  cmp     r14d, dword ptr [rsp+140h+var_118]
0x18000db58  jge     loc_18000DC89
0x18000db5e  mov     rcx, [rsp+140h+var_120]
0x18000db63  movsxd  rax, r14d
0x18000db66  mov     rcx, [rcx+rax*8]; bstrString
0x18000db6a  call    cs:__imp_SysFreeString
0x18000db70  inc     r14d
0x18000db73  cmp     r14d, r15d
0x18000db76  jb      short loc_18000DB4A
0x18000db78  mov     rcx, [rsp+140h+var_120]; Block
0x18000db7d  test    rcx, rcx
0x18000db80  jz      short loc_18000DB8D
0x18000db82  call    cs:__imp_free
0x18000db88  mov     [rsp+140h+var_120], r13
0x18000db8d  mov     r15d, dword ptr [rsp+140h+var_108]
0x18000db92  mov     r14d, r13d
0x18000db95  mov     [rsp+140h+var_118], r13
0x18000db9a  test    r15d, r15d
0x18000db9d  jz      short loc_18000DBCD
0x18000db9f  test    r14d, r14d
0x18000dba2  js      loc_18000DC94
0x18000dba8  cmp     r14d, dword ptr [rsp+140h+var_108]
0x18000dbad  jge     loc_18000DC94
0x18000dbb3  mov     rcx, [rsp+140h+var_110]
0x18000dbb8  movsxd  rax, r14d
0x18000dbbb  mov     rcx, [rcx+rax*8]; bstrString
0x18000dbbf  call    cs:__imp_SysFreeString
0x18000dbc5  inc     r14d
0x18000dbc8  cmp     r14d, r15d
0x18000dbcb  jb      short loc_18000DB9F
0x18000dbcd  mov     rcx, [rsp+140h+var_110]; Block
0x18000dbd2  test    rcx, rcx
0x18000dbd5  jz      short loc_18000DBE2
0x18000dbd7  call    cs:__imp_free
0x18000dbdd  mov     [rsp+140h+var_110], r13
0x18000dbe2  mov     ecx, 80000000h
0x18000dbe7  mov     [rsp+140h+var_108], r13
0x18000dbec  lea     eax, [rbx+rcx]
0x18000dbef  test    ecx, eax
0x18000dbf1  jnz     short loc_18000DC2F
0x18000dbf3  cmp     ebx, r12d
0x18000dbf6  jz      short loc_18000DC2F
0x18000dbf8  mov     r15, [rdi]
0x18000dbfb  test    r15, r15
0x18000dbfe  jz      short loc_18000DC29
0x18000dc00  mov     r12d, [rsi]
0x18000dc03  mov     r14d, r13d
0x18000dc06  test    r12d, r12d
0x18000dc09  jz      short loc_18000DC20
0x18000dc0b  mov     ecx, r14d
0x18000dc0e  mov     rcx, [r15+rcx*8]; bstrString
0x18000dc12  call    cs:__imp_SysFreeString
0x18000dc18  inc     r14d
0x18000dc1b  cmp     r14d, r12d
0x18000dc1e  jb      short loc_18000DC0B
0x18000dc20  mov     rcx, r15; pv
0x18000dc23  call    cs:__imp_CoTaskMemFree
0x18000dc29  mov     [rdi], r13
0x18000dc2c  mov     [rsi], r13d
0x18000dc2f  mov     rcx, [rsp+140h+var_120]; Block
0x18000dc34  test    rcx, rcx
0x18000dc37  jz      short loc_18000DC44
0x18000dc39  call    cs:__imp_free
0x18000dc3f  mov     [rsp+140h+var_120], r13
0x18000dc44  mov     rcx, [rsp+140h+var_110]; Block
0x18000dc49  mov     [rsp+140h+var_118], r13
0x18000dc4e  test    rcx, rcx
0x18000dc51  jz      short loc_18000DC5E
0x18000dc53  call    cs:__imp_free
0x18000dc59  mov     [rsp+140h+var_110], r13
0x18000dc5e  mov     rcx, [rsp+140h+Block]; Block
0x18000dc63  mov     [rsp+140h+var_108], r13
0x18000dc68  test    rcx, rcx
0x18000dc6b  jz      short loc_18000DC73
0x18000dc6d  call    cs:__imp_free
0x18000dc73  mov     eax, ebx
0x18000dc75  add     rsp, 108h
0x18000dc7c  pop     r15
0x18000dc7e  pop     r14
0x18000dc80  pop     r13
0x18000dc82  pop     r12
0x18000dc84  pop     rdi
0x18000dc85  pop     rsi
0x18000dc86  pop     rbx
0x18000dc87  pop     rbp
0x18000dc88  retn
0x18000dc89  mov     ecx, 0C000008Ch; this
0x18000dc8e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000dc93  int     3; Trap to Debugger
0x18000dc94  mov     ecx, 0C000008Ch; this
0x18000dc99  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000dc9e  int     3; Trap to Debugger
0x18000dc9f  mov     ecx, 0C000008Ch; this
  ... truncated ...
```
