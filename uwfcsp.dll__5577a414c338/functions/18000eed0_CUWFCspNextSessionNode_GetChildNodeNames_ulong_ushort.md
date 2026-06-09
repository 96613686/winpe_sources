# CUWFCspNextSessionNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x18000eed0`
- end: `0x18000f32c`
- name: `?GetChildNodeNames@CUWFCspNextSessionNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `1116`
- prototype: `__int64 __fastcall(CUWFCspNextSessionNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800068f4`
- `0x18000c1d4`
- `0x18000d0d8`
- `0x18000eed0`
- `0x18001b010`

## import_xrefs

- `msvcrt!free` at `0x18000f1b2`
- `msvcrt!free` at `0x18000f205`
- `msvcrt!free` at `0x18000f25a`
- `msvcrt!free` at `0x18000f2bc`
- `msvcrt!free` at `0x18000f2d6`
- `msvcrt!free` at `0x18000f2ef`
- `msvcrt!free` at `0x18000f1b2`
- `msvcrt!free` at `0x18000f205`
- `msvcrt!free` at `0x18000f25a`
- `msvcrt!free` at `0x18000f2bc`
- `msvcrt!free` at `0x18000f2d6`
- `msvcrt!free` at `0x18000f2ef`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f01c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f147`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f01c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f147`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f19b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f1ed`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f242`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f295`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f19b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f1ed`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f242`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f2a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f2a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000eff3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f11b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000eff3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f11b`
- `uwfcfgmgmt!UwfCfgGetFileExclusions` at `0x18000ef99`
- `uwfcfgmgmt!UwfCfgGetFileExclusions` at `0x18000ef99`
- `uwfcfgmgmt!UwfCfgGetVolumes` at `0x18000f061`
- `uwfcfgmgmt!UwfCfgGetVolumes` at `0x18000f061`
- `uwfcfgmgmt!UwfCfgGetRegExclusions` at `0x18000f081`
- `uwfcfgmgmt!UwfCfgGetRegExclusions` at `0x18000f081`

## string_xrefs

- `0x18000f0d9`: `MaximumOverlaySize`
- `0x18000f0fa`: `RegistryExclusions`
- `0x18000f03d`: `onecore\base\uwf\uwfcsp\precomp.h`

## pseudocode

```c
__int64 __fastcall CUWFCspNextSessionNode::GetChildNodeNames(
        CUWFCspNextSessionNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3)
{
  CUWFCspNextSessionNode *v5; // rdx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int RegExclusions; // ebx
  void **p_Block; // r8
  __int64 v12; // rbx
  unsigned __int16 **v13; // rax
  unsigned __int16 **v14; // r15
  unsigned int v15; // r14d
  BSTR v16; // rax
  __int64 v17; // rbx
  unsigned __int16 **v18; // rax
  BSTR v19; // rax
  unsigned int v20; // r15d
  int i; // r14d
  unsigned int v22; // r15d
  int v23; // r14d
  unsigned int v24; // r15d
  int v25; // r14d
  BSTR *v26; // r15
  unsigned int v27; // r12d
  unsigned int m; // r14d
  void *v30; // [rsp+20h] [rbp-99h] BYREF
  __int64 k; // [rsp+28h] [rbp-91h]
  void *v32; // [rsp+30h] [rbp-89h] BYREF
  __int64 v33; // [rsp+38h] [rbp-81h]
  void *Block; // [rsp+40h] [rbp-79h] BYREF
  __int64 j; // [rsp+48h] [rbp-71h]
  OLECHAR *psz[4]; // [rsp+50h] [rbp-69h]
  OLECHAR *v37[20]; // [rsp+70h] [rbp-49h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  __int64 v39; // [rsp+128h] [rbp+6Fh] BYREF

  v39 = 0;
  Block = 0;
  v5 = this;
  j = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  k = 0;
  if ( !a2 || !a3 )
  {
    RegExclusions = -2147024809;
    goto LABEL_32;
  }
  *a2 = 0;
  *a3 = 0;
  v6 = *((_DWORD *)this + 11) - 29;
  if ( !v6 )
  {
    v17 = 88;
    v37[0] = L"FilterEnabled";
    v37[1] = L"ResetPersistentState";
    v37[2] = L"ResetPersistentStateSavedMode";
    v37[3] = L"OverlayType";
    v37[4] = L"OverlayFlags";
    v37[5] = L"MaximumOverlaySize";
    v37[6] = L"PersistDomainSecretKey";
    v37[7] = L"PersistTSCAL";
    v37[8] = L"RegistryExclusions";
    v37[9] = L"ServicingEnabled";
    v37[10] = L"Volume";
    v18 = (unsigned __int16 **)CoTaskMemAlloc(0x58u);
    v14 = v18;
    if ( v18 )
    {
      v15 = 0;
      do
      {
        *(_BYTE *)v18 = 0;
        v18 = (unsigned __int16 **)((char *)v18 + 1);
        --v17;
      }
      while ( v17 );
      while ( 1 )
      {
        v19 = SysAllocString(v37[v15]);
        v14[v15] = v19;
        if ( !v19 )
          goto LABEL_19;
        if ( ++v15 >= 0xB )
        {
LABEL_30:
          *a3 = v14;
          RegExclusions = 0;
          *a2 = v15;
          goto LABEL_32;
        }
      }
    }
LABEL_25:
    RegExclusions = -2147024882;
    goto LABEL_32;
  }
  v7 = v6 - 8;
  if ( !v7 )
  {
    RegExclusions = UwfCfgGetRegExclusions(0, &v30);
    if ( RegExclusions >= 0 )
    {
      p_Block = &v30;
      goto LABEL_12;
    }
    goto LABEL_32;
  }
  v8 = v7 - 5;
  if ( v8 )
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
                        &v39);
      if ( RegExclusions >= 0 )
      {
        RegExclusions = UwfCfgGetFileExclusions(0, v39, &v32);
        if ( RegExclusions >= 0 )
        {
          p_Block = &v32;
LABEL_12:
          RegExclusions = ConstructBSTRArray(a3, a2, (__int64)p_Block);
          goto LABEL_32;
        }
      }
      goto LABEL_32;
    }
    v12 = 32;
    psz[0] = L"Protected";
    psz[1] = L"BindByDriveLetter";
    psz[2] = L"DriveLetter";
    psz[3] = L"Exclusions";
    v13 = (unsigned __int16 **)CoTaskMemAlloc(0x20u);
    v14 = v13;
    if ( v13 )
    {
      v15 = 0;
      do
      {
        *(_BYTE *)v13 = 0;
        v13 = (unsigned __int16 **)((char *)v13 + 1);
        --v12;
      }
      while ( v12 );
      while ( 1 )
      {
        v16 = SysAllocString(psz[v15]);
        v14[v15] = v16;
        if ( !v16 )
          break;
        if ( ++v15 >= 4 )
          goto LABEL_30;
      }
LABEL_19:
      RegExclusions = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecore\\base\\uwf\\uwfcsp\\precomp.h",
        (const char *)0x8007000ELL,
        (int)v30);
      goto LABEL_32;
    }
    goto LABEL_25;
  }
  RegExclusions = UwfCfgGetVolumes(0, &Block);
  if ( RegExclusions >= 0 )
  {
    p_Block = &Block;
    goto LABEL_12;
  }
LABEL_32:
  v20 = j;
  for ( i = 0; i < v20; ++i )
  {
    if ( i < 0 || i >= (int)j )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, (int)v5, (unsigned int)a3);
      JUMPOUT(0x18000F32BLL);
    }
    SysFreeString(*((BSTR *)Block + i));
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  v22 = k;
  v23 = 0;
  for ( j = 0; v23 < v22; ++v23 )
  {
    if ( v23 < 0 || v23 >= (int)k )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, (int)v5, (unsigned int)a3);
      __debugbreak();
    }
    SysFreeString(*((BSTR *)v30 + v23));
  }
  if ( v30 )
  {
    free(v30);
    v30 = 0;
  }
  v24 = v33;
  v25 = 0;
  for ( k = 0; v25 < v24; ++v25 )
  {
    if ( v25 < 0 || v25 >= (int)v33 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, (int)v5, (unsigned int)a3);
      __debugbreak();
    }
    SysFreeString(*((BSTR *)v32 + v25));
  }
  if ( v32 )
  {
    free(v32);
    v32 = 0;
  }
  v33 = 0;
  if ( (int)(RegExclusions + 0x80000000) >= 0 && RegExclusions != -2147024809 )
  {
    v26 = *a3;
    if ( *a3 )
    {
      v27 = *a2;
      for ( m = 0; m < v27; ++m )
        SysFreeString(v26[m]);
      CoTaskMemFree(v26);
    }
    *a3 = 0;
    *a2 = 0;
  }
  if ( v30 )
  {
    free(v30);
    v30 = 0;
  }
  k = 0;
  if ( v32 )
  {
    free(v32);
    v32 = 0;
  }
  v33 = 0;
  if ( Block )
    free(Block);
  return (unsigned int)RegExclusions;
}

```

## disassembly

```asm
0x18000eed0  push    rbp
0x18000eed2  push    rbx
0x18000eed3  push    rsi
0x18000eed4  push    rdi
0x18000eed5  push    r12
0x18000eed7  push    r13
0x18000eed9  push    r14
0x18000eedb  push    r15
0x18000eedd  lea     rbp, [rsp-1Fh]
0x18000eee2  sub     rsp, 0D8h
0x18000eee9  xor     r13d, r13d
0x18000eeec  mov     rsi, rdx
0x18000eeef  mov     [rbp+57h+arg_8], r13
0x18000eef3  mov     rdi, r8
0x18000eef6  mov     [rbp+57h+Block], r13
0x18000eefa  mov     rdx, rcx; int
0x18000eefd  mov     [rbp+57h+var_C8], r13
0x18000ef01  mov     r12d, 80070057h
0x18000ef07  mov     [rsp+110h+var_E0], r13
0x18000ef0c  mov     [rsp+110h+var_D8], r13
0x18000ef11  mov     [rsp+110h+var_F0], r13; int
0x18000ef16  mov     [rsp+110h+var_E8], r13
0x18000ef1b  test    rsi, rsi
0x18000ef1e  jz      loc_18000F16E
0x18000ef24  test    r8, r8
0x18000ef27  jz      loc_18000F16E
0x18000ef2d  mov     [rsi], r13d
0x18000ef30  mov     [r8], r13
0x18000ef33  mov     ecx, [rcx+2Ch]
0x18000ef36  sub     ecx, 1Dh
0x18000ef39  jz      loc_18000F09B
0x18000ef3f  sub     ecx, 8
0x18000ef42  jz      loc_18000F07A
0x18000ef48  sub     ecx, 5
0x18000ef4b  jz      loc_18000F05B
0x18000ef51  sub     ecx, 1
0x18000ef54  jz      short loc_18000EFC0
0x18000ef56  cmp     ecx, 5
0x18000ef59  jz      short loc_18000EF6B
0x18000ef5b  mov     [rsi], r13d
0x18000ef5e  mov     [r8], r13
0x18000ef61  mov     ebx, 86000011h
0x18000ef66  jmp     loc_18000F171
0x18000ef6b  mov     rcx, [rdx+18h]
0x18000ef6f  lea     r8, [rbp+57h+arg_8]
0x18000ef73  mov     edx, 3
0x18000ef78  mov     rax, [rcx]
0x18000ef7b  mov     rax, [rax+58h]
0x18000ef7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef84  mov     ebx, eax
0x18000ef86  test    eax, eax
0x18000ef88  js      loc_18000F171
0x18000ef8e  mov     rdx, [rbp+57h+arg_8]
0x18000ef92  lea     r8, [rsp+110h+var_E0]
0x18000ef97  xor     ecx, ecx
0x18000ef99  call    cs:__imp_?UwfCfgGetFileExclusions@@YAJ_NPEBGPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; UwfCfgGetFileExclusions(bool,ushort const *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x18000ef9f  mov     ebx, eax
0x18000efa1  test    eax, eax
0x18000efa3  js      loc_18000F171
0x18000efa9  lea     r8, [rsp+110h+var_E0]
0x18000efae  mov     rdx, rsi
0x18000efb1  mov     rcx, rdi
0x18000efb4  call    ?ConstructBSTRArray@@YAJPEAPEAPEAGPEAKAEBV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; ConstructBSTRArray(ushort * * *,ulong *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> const &)
0x18000efb9  mov     ebx, eax
0x18000efbb  jmp     loc_18000F171
0x18000efc0  lea     rax, aProtected; "Protected"
0x18000efc7  mov     ebx, 20h ; ' '
0x18000efcc  mov     [rbp+57h+psz], rax
0x18000efd0  mov     ecx, ebx; cb
0x18000efd2  lea     rax, aBindbydrivelet; "BindByDriveLetter"
0x18000efd9  mov     [rbp+57h+var_B8], rax
0x18000efdd  lea     rax, aDriveletter; "DriveLetter"
0x18000efe4  mov     [rbp+57h+var_B0], rax
0x18000efe8  lea     rax, aExclusions; "Exclusions"
0x18000efef  mov     [rbp+57h+var_A8], rax
0x18000eff3  call    cs:__imp_CoTaskMemAlloc
0x18000eff9  mov     r15, rax
0x18000effc  test    rax, rax
0x18000efff  jz      loc_18000F129
0x18000f005  mov     r14d, r13d
0x18000f008  mov     [rax], r13b
0x18000f00b  inc     rax
0x18000f00e  sub     rbx, 1
0x18000f012  jnz     short loc_18000F008
0x18000f014  mov     ebx, r14d
0x18000f017  mov     rcx, [rbp+rbx*8+57h+psz]; psz
0x18000f01c  call    cs:__imp_SysAllocString
0x18000f022  mov     [r15+rbx*8], rax
0x18000f026  test    rax, rax
0x18000f029  jz      short loc_18000F039
0x18000f02b  inc     r14d
0x18000f02e  cmp     r14d, 4
0x18000f032  jb      short loc_18000F014
0x18000f034  jmp     loc_18000F163
0x18000f039  mov     rcx, [rbp+5Fh]; this
0x18000f03d  lea     r8, aOnecoreBaseUwf; "onecore\\base\\uwf\\uwfcsp\\precomp.h"
0x18000f044  mov     ebx, 8007000Eh
0x18000f049  mov     edx, 9Eh; void *
0x18000f04e  mov     r9d, ebx; char *
0x18000f051  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f056  jmp     loc_18000F171
0x18000f05b  lea     rdx, [rbp+57h+Block]
0x18000f05f  xor     ecx, ecx
0x18000f061  call    cs:__imp_?UwfCfgGetVolumes@@YAJ_NPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; UwfCfgGetVolumes(bool,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x18000f067  mov     ebx, eax
0x18000f069  test    eax, eax
0x18000f06b  js      loc_18000F171
0x18000f071  lea     r8, [rbp+57h+Block]
0x18000f075  jmp     loc_18000EFAE
0x18000f07a  lea     rdx, [rsp+110h+var_F0]
0x18000f07f  xor     ecx, ecx
0x18000f081  call    cs:__imp_?UwfCfgGetRegExclusions@@YAJ_NPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; UwfCfgGetRegExclusions(bool,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x18000f087  mov     ebx, eax
0x18000f089  test    eax, eax
0x18000f08b  js      loc_18000F171
0x18000f091  lea     r8, [rsp+110h+var_F0]
0x18000f096  jmp     loc_18000EFAE
0x18000f09b  lea     rax, aFilterenabled; "FilterEnabled"
0x18000f0a2  mov     ebx, 58h ; 'X'
0x18000f0a7  mov     [rbp+57h+var_A0], rax
0x18000f0ab  mov     ecx, ebx; cb
0x18000f0ad  lea     rax, aResetpersisten_0; "ResetPersistentState"
0x18000f0b4  mov     [rbp+57h+var_98], rax
0x18000f0b8  lea     rax, aResetpersisten; "ResetPersistentStateSavedMode"
0x18000f0bf  mov     [rbp+57h+var_90], rax
0x18000f0c3  lea     rax, aOverlaytype; "OverlayType"
0x18000f0ca  mov     [rbp+57h+var_88], rax
0x18000f0ce  lea     rax, aOverlayflags; "OverlayFlags"
0x18000f0d5  mov     [rbp+57h+var_80], rax
0x18000f0d9  lea     rax, aMaximumoverlay; "MaximumOverlaySize"
0x18000f0e0  mov     [rbp+57h+var_78], rax
0x18000f0e4  lea     rax, aPersistdomains; "PersistDomainSecretKey"
0x18000f0eb  mov     [rbp+57h+var_70], rax
0x18000f0ef  lea     rax, aPersisttscal; "PersistTSCAL"
0x18000f0f6  mov     [rbp+57h+var_68], rax
0x18000f0fa  lea     rax, aRegistryexclus; "RegistryExclusions"
0x18000f101  mov     [rbp+57h+var_60], rax
0x18000f105  lea     rax, aServicingenabl; "ServicingEnabled"
0x18000f10c  mov     [rbp+57h+var_58], rax
0x18000f110  lea     rax, aVolume; "Volume"
0x18000f117  mov     [rbp+57h+var_50], rax
0x18000f11b  call    cs:__imp_CoTaskMemAlloc
0x18000f121  mov     r15, rax
0x18000f124  test    rax, rax
0x18000f127  jnz     short loc_18000F130
0x18000f129  mov     ebx, 8007000Eh
0x18000f12e  jmp     short loc_18000F171
0x18000f130  mov     r14d, r13d
0x18000f133  mov     [rax], r13b
0x18000f136  inc     rax
0x18000f139  sub     rbx, 1
0x18000f13d  jnz     short loc_18000F133
0x18000f13f  mov     ebx, r14d
0x18000f142  mov     rcx, [rbp+rbx*8+57h+var_A0]; psz
0x18000f147  call    cs:__imp_SysAllocString
0x18000f14d  mov     [r15+rbx*8], rax
0x18000f151  test    rax, rax
0x18000f154  jz      loc_18000F039
0x18000f15a  inc     r14d
0x18000f15d  cmp     r14d, 0Bh
0x18000f161  jb      short loc_18000F13F
0x18000f163  mov     [rdi], r15
0x18000f166  mov     ebx, r13d
0x18000f169  mov     [rsi], r14d
0x18000f16c  jmp     short loc_18000F171
0x18000f16e  mov     ebx, r12d
0x18000f171  mov     r15d, dword ptr [rbp+57h+var_C8]
0x18000f175  mov     r14d, r13d
0x18000f178  test    r15d, r15d
0x18000f17b  jz      short loc_18000F1A9
0x18000f17d  test    r14d, r14d
0x18000f180  js      loc_18000F321
0x18000f186  cmp     r14d, dword ptr [rbp+57h+var_C8]
0x18000f18a  jge     loc_18000F321
0x18000f190  mov     rcx, [rbp+57h+Block]
0x18000f194  movsxd  rax, r14d
0x18000f197  mov     rcx, [rcx+rax*8]; bstrString
0x18000f19b  call    cs:__imp_SysFreeString
0x18000f1a1  inc     r14d
0x18000f1a4  cmp     r14d, r15d
0x18000f1a7  jb      short loc_18000F17D
0x18000f1a9  mov     rcx, [rbp+57h+Block]; Block
0x18000f1ad  test    rcx, rcx
0x18000f1b0  jz      short loc_18000F1BC
0x18000f1b2  call    cs:__imp_free
0x18000f1b8  mov     [rbp+57h+Block], r13
0x18000f1bc  mov     r15d, dword ptr [rsp+110h+var_E8]
0x18000f1c1  mov     r14d, r13d
0x18000f1c4  mov     [rbp+57h+var_C8], r13
0x18000f1c8  test    r15d, r15d
0x18000f1cb  jz      short loc_18000F1FB
0x18000f1cd  test    r14d, r14d
0x18000f1d0  js      loc_18000F30B
0x18000f1d6  cmp     r14d, dword ptr [rsp+110h+var_E8]
0x18000f1db  jge     loc_18000F30B
0x18000f1e1  mov     rcx, [rsp+110h+var_F0]
0x18000f1e6  movsxd  rax, r14d
0x18000f1e9  mov     rcx, [rcx+rax*8]; bstrString
0x18000f1ed  call    cs:__imp_SysFreeString
0x18000f1f3  inc     r14d
0x18000f1f6  cmp     r14d, r15d
0x18000f1f9  jb      short loc_18000F1CD
0x18000f1fb  mov     rcx, [rsp+110h+var_F0]; Block
0x18000f200  test    rcx, rcx
0x18000f203  jz      short loc_18000F210
0x18000f205  call    cs:__imp_free
0x18000f20b  mov     [rsp+110h+var_F0], r13
0x18000f210  mov     r15d, dword ptr [rsp+110h+var_D8]
0x18000f215  mov     r14d, r13d
0x18000f218  mov     [rsp+110h+var_E8], r13
0x18000f21d  test    r15d, r15d
0x18000f220  jz      short loc_18000F250
0x18000f222  test    r14d, r14d
0x18000f225  js      loc_18000F316
0x18000f22b  cmp     r14d, dword ptr [rsp+110h+var_D8]
0x18000f230  jge     loc_18000F316
0x18000f236  mov     rcx, [rsp+110h+var_E0]
0x18000f23b  movsxd  rax, r14d
0x18000f23e  mov     rcx, [rcx+rax*8]; bstrString
0x18000f242  call    cs:__imp_SysFreeString
0x18000f248  inc     r14d
0x18000f24b  cmp     r14d, r15d
0x18000f24e  jb      short loc_18000F222
0x18000f250  mov     rcx, [rsp+110h+var_E0]; Block
0x18000f255  test    rcx, rcx
0x18000f258  jz      short loc_18000F265
0x18000f25a  call    cs:__imp_free
0x18000f260  mov     [rsp+110h+var_E0], r13
0x18000f265  mov     ecx, 80000000h
0x18000f26a  mov     [rsp+110h+var_D8], r13
0x18000f26f  lea     eax, [rbx+rcx]
0x18000f272  test    ecx, eax
0x18000f274  jnz     short loc_18000F2B2
0x18000f276  cmp     ebx, r12d
0x18000f279  jz      short loc_18000F2B2
0x18000f27b  mov     r15, [rdi]
0x18000f27e  test    r15, r15
0x18000f281  jz      short loc_18000F2AC
0x18000f283  mov     r12d, [rsi]
0x18000f286  mov     r14d, r13d
0x18000f289  test    r12d, r12d
0x18000f28c  jz      short loc_18000F2A3
0x18000f28e  mov     ecx, r14d
0x18000f291  mov     rcx, [r15+rcx*8]; bstrString
0x18000f295  call    cs:__imp_SysFreeString
0x18000f29b  inc     r14d
0x18000f29e  cmp     r14d, r12d
0x18000f2a1  jb      short loc_18000F28E
0x18000f2a3  mov     rcx, r15; pv
0x18000f2a6  call    cs:__imp_CoTaskMemFree
0x18000f2ac  mov     [rdi], r13
0x18000f2af  mov     [rsi], r13d
0x18000f2b2  mov     rcx, [rsp+110h+var_F0]; Block
0x18000f2b7  test    rcx, rcx
0x18000f2ba  jz      short loc_18000F2C7
0x18000f2bc  call    cs:__imp_free
0x18000f2c2  mov     [rsp+110h+var_F0], r13
0x18000f2c7  mov     rcx, [rsp+110h+var_E0]; Block
0x18000f2cc  mov     [rsp+110h+var_E8], r13
0x18000f2d1  test    rcx, rcx
0x18000f2d4  jz      short loc_18000F2E1
0x18000f2d6  call    cs:__imp_free
0x18000f2dc  mov     [rsp+110h+var_E0], r13
0x18000f2e1  mov     rcx, [rbp+57h+Block]; Block
0x18000f2e5  mov     [rsp+110h+var_D8], r13
0x18000f2ea  test    rcx, rcx
0x18000f2ed  jz      short loc_18000F2F5
0x18000f2ef  call    cs:__imp_free
0x18000f2f5  mov     eax, ebx
0x18000f2f7  add     rsp, 0D8h
0x18000f2fe  pop     r15
0x18000f300  pop     r14
0x18000f302  pop     r13
0x18000f304  pop     r12
0x18000f306  pop     rdi
0x18000f307  pop     rsi
0x18000f308  pop     rbx
0x18000f309  pop     rbp
0x18000f30a  retn
0x18000f30b  mov     ecx, 0C000008Ch; this
0x18000f310  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000f315  int     3; Trap to Debugger
0x18000f316  mov     ecx, 0C000008Ch; this
0x18000f31b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000f320  int     3; Trap to Debugger
0x18000f321  mov     ecx, 0C000008Ch; this
0x18000f326  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
