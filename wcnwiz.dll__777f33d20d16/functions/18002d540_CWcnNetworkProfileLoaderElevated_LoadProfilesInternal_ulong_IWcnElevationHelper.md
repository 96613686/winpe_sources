# CWcnNetworkProfileLoaderElevated::LoadProfilesInternal(ulong,IWcnElevationHelper *)

- ea: `0x18002d540`
- end: `0x18002d77f`
- name: `?LoadProfilesInternal@CWcnNetworkProfileLoaderElevated@@EEAAXKPEAUIWcnElevationHelper@@@Z`
- size: `575`
- prototype: `void __fastcall(CWcnNetworkProfileLoaderElevated *__hidden this, unsigned int, struct IWcnElevationHelper *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003abc`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18002bf9c`
- `0x18002bfb8`
- `0x18002c708`
- `0x18002cec0`
- `0x18002d050`
- `0x18002d540`
- `0x18002de1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d5c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002d5c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWcnNetworkProfileLoaderElevated::LoadProfilesInternal(
        CWcnNetworkProfileLoaderElevated *this,
        unsigned int a2,
        struct IWcnElevationHelper *a3)
{
  int v6; // ebx
  _QWORD *v7; // r10
  const char *Indent; // rax
  __int64 v9; // r10
  HRESULT ProfileFromLastFC; // eax
  __int64 v11; // rdx
  int ProfilesFromWlan; // eax
  CWcnNetworkProfileLoader *v13; // rcx
  int WfdGoProfile; // eax
  unsigned int v15; // edx
  CWcnNetworkProfileLoaderElevated *v16; // rcx
  int HostedNetworkProfile; // eax
  CWcnNetworkProfileLoader *v18; // rcx
  unsigned int v19; // eax
  __int64 v20; // r10
  LPVOID ppv; // [rsp+80h] [rbp+18h] BYREF

  v6 = 0;
  ppv = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v9 + 16), 10, WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids, Indent);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    ProfileFromLastFC = CoCreateInstance(
                          &CLSID_WcnElevationHelper,
                          0,
                          1u,
                          &GUID_c100bebc_d33a_4a4b_bf23_bbef4663d017,
                          &ppv);
    v6 = ProfileFromLastFC;
    if ( ProfileFromLastFC < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_42;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 11;
        goto LABEL_36;
      }
      goto LABEL_38;
    }
    a3 = (struct IWcnElevationHelper *)ppv;
    v7 = WPP_GLOBAL_Control;
  }
  if ( (a2 & 1) != 0 )
  {
    ProfilesFromWlan = CWcnNetworkProfileLoaderElevated::LoadProfilesFromWlan(this, a2, a3);
    v6 = ProfilesFromWlan;
    if ( ProfilesFromWlan >= 0 )
    {
LABEL_15:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_16;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids,
        (unsigned int)ProfilesFromWlan);
      goto LABEL_15;
    }
  }
LABEL_16:
  if ( (a2 & 8) != 0 && !CWcnNetworkProfileLoader::IsOneProfileEnough(this, a2) )
  {
    WfdGoProfile = CWcnNetworkProfileLoader::LoadWfdGoProfile(v13);
    v6 = WfdGoProfile;
    if ( WfdGoProfile >= 0 )
    {
LABEL_22:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_23;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids,
        (unsigned int)WfdGoProfile);
      goto LABEL_22;
    }
  }
LABEL_23:
  if ( (a2 & 4) != 0 && !CWcnNetworkProfileLoader::IsOneProfileEnough(this, a2) )
  {
    HostedNetworkProfile = CWcnNetworkProfileLoaderElevated::LoadHostedNetworkProfile(v16, v15, a3);
    v6 = HostedNetworkProfile;
    if ( HostedNetworkProfile >= 0 )
    {
LABEL_29:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_30;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids,
        (unsigned int)HostedNetworkProfile);
      goto LABEL_29;
    }
  }
LABEL_30:
  if ( (a2 & 2) != 0 && !CWcnNetworkProfileLoader::IsOneProfileEnough(this, a2) )
  {
    ProfileFromLastFC = CWcnNetworkProfileLoader::LoadProfileFromLastFC(v18);
    v6 = ProfileFromLastFC;
    if ( ProfileFromLastFC >= 0 )
    {
LABEL_37:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_38;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_42;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      goto LABEL_38;
    v11 = 15;
LABEL_36:
    WPP_SF_d(v7[2], v11, WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids, (unsigned int)ProfileFromLastFC);
    goto LABEL_37;
  }
LABEL_38:
  if ( v7 != &WPP_GLOBAL_Control && (v6 < 0 || *((_BYTE *)v7 + 25) >= 6u) )
  {
    v19 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v20 + 16), 16, (unsigned int)WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids, v19, v6);
  }
LABEL_42:
  ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(&ppv);
}

```

## disassembly

```asm
0x18002d540  mov     rax, rsp
0x18002d543  push    rbx
0x18002d544  push    rbp
0x18002d545  push    rsi
0x18002d546  push    rdi
0x18002d547  push    r13
0x18002d549  push    r14
0x18002d54b  sub     rsp, 38h
0x18002d54f  mov     rbp, r8
0x18002d552  mov     edi, edx
0x18002d554  mov     rsi, rcx
0x18002d557  xor     ebx, ebx
0x18002d559  mov     [rax+18h], rbx
0x18002d55d  lea     r14, WPP_GLOBAL_Control
0x18002d564  lea     r13, WPP_9bfaf626458d371c1f67829d431a7c34_Traceguids
0x18002d56b  mov     r10, cs:WPP_GLOBAL_Control
0x18002d572  cmp     r10, r14
0x18002d575  jz      short loc_18002D59F
0x18002d577  cmp     byte ptr [r10+19h], 6
0x18002d57c  jb      short loc_18002D59F
0x18002d57e  lea     ecx, [rbx+1]; int
0x18002d581  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002d586  lea     edx, [rbx+0Ah]
0x18002d589  mov     r9, rax
0x18002d58c  mov     r8, r13
0x18002d58f  mov     rcx, [r10+10h]
0x18002d593  call    WPP_SF_s
0x18002d598  mov     r10, cs:WPP_GLOBAL_Control
0x18002d59f  test    rbp, rbp
0x18002d5a2  jnz     short loc_18002D603
0x18002d5a4  lea     rax, [rsp+68h+arg_10]
0x18002d5ac  mov     [rsp+68h+ppv], rax; ppv
0x18002d5b1  lea     r9, _GUID_c100bebc_d33a_4a4b_bf23_bbef4663d017; riid
0x18002d5b8  xor     edx, edx; pUnkOuter
0x18002d5ba  lea     r8d, [rbp+1]; dwClsContext
0x18002d5be  lea     rcx, CLSID_WcnElevationHelper; rclsid
0x18002d5c5  call    cs:__imp_CoCreateInstance
0x18002d5cb  mov     ebx, eax
0x18002d5cd  test    eax, eax
0x18002d5cf  jns     short loc_18002D5F4
0x18002d5d1  mov     r10, cs:WPP_GLOBAL_Control
0x18002d5d8  cmp     r10, r14
0x18002d5db  jz      loc_18002D765
0x18002d5e1  cmp     byte ptr [r10+19h], 2
0x18002d5e6  jb      loc_18002D734
0x18002d5ec  lea     edx, [rbp+0Bh]
0x18002d5ef  jmp     loc_18002D71E
0x18002d5f4  mov     rbp, [rsp+68h+arg_10]
0x18002d5fc  mov     r10, cs:WPP_GLOBAL_Control
0x18002d603  test    dil, 1
0x18002d607  jz      short loc_18002D64A
0x18002d609  mov     r8, rbp; struct IWcnElevationHelper *
0x18002d60c  mov     edx, edi; unsigned int
0x18002d60e  mov     rcx, rsi; this
0x18002d611  call    ?LoadProfilesFromWlan@CWcnNetworkProfileLoaderElevated@@AEAAJKPEAUIWcnElevationHelper@@@Z; CWcnNetworkProfileLoaderElevated::LoadProfilesFromWlan(ulong,IWcnElevationHelper *)
0x18002d616  mov     ebx, eax
0x18002d618  test    eax, eax
0x18002d61a  jns     short loc_18002D643
0x18002d61c  mov     r10, cs:WPP_GLOBAL_Control
0x18002d623  cmp     r10, r14
0x18002d626  jz      short loc_18002D64A
0x18002d628  cmp     byte ptr [r10+19h], 3
0x18002d62d  jb      short loc_18002D64A
0x18002d62f  mov     edx, 0Ch
0x18002d634  mov     r9d, eax
0x18002d637  mov     r8, r13
0x18002d63a  mov     rcx, [r10+10h]
0x18002d63e  call    WPP_SF_d
0x18002d643  mov     r10, cs:WPP_GLOBAL_Control
0x18002d64a  test    dil, 8
0x18002d64e  jz      short loc_18002D697
0x18002d650  mov     edx, edi; unsigned int
0x18002d652  mov     rcx, rsi; this
0x18002d655  call    ?IsOneProfileEnough@CWcnNetworkProfileLoader@@IEBA_NK@Z; CWcnNetworkProfileLoader::IsOneProfileEnough(ulong)
0x18002d65a  test    al, al
0x18002d65c  jnz     short loc_18002D697
0x18002d65e  call    ?LoadWfdGoProfile@CWcnNetworkProfileLoader@@IEAAJXZ; CWcnNetworkProfileLoader::LoadWfdGoProfile(void)
0x18002d663  mov     ebx, eax
0x18002d665  test    eax, eax
0x18002d667  jns     short loc_18002D690
0x18002d669  mov     r10, cs:WPP_GLOBAL_Control
0x18002d670  cmp     r10, r14
0x18002d673  jz      short loc_18002D697
0x18002d675  cmp     byte ptr [r10+19h], 3
0x18002d67a  jb      short loc_18002D697
0x18002d67c  mov     edx, 0Dh
0x18002d681  mov     r9d, eax
0x18002d684  mov     r8, r13
0x18002d687  mov     rcx, [r10+10h]
0x18002d68b  call    WPP_SF_d
0x18002d690  mov     r10, cs:WPP_GLOBAL_Control
0x18002d697  test    dil, 4
0x18002d69b  jz      short loc_18002D6E7
0x18002d69d  mov     edx, edi; unsigned int
0x18002d69f  mov     rcx, rsi; this
0x18002d6a2  call    ?IsOneProfileEnough@CWcnNetworkProfileLoader@@IEBA_NK@Z; CWcnNetworkProfileLoader::IsOneProfileEnough(ulong)
0x18002d6a7  test    al, al
0x18002d6a9  jnz     short loc_18002D6E7
0x18002d6ab  mov     r8, rbp; struct IWcnElevationHelper *
0x18002d6ae  call    ?LoadHostedNetworkProfile@CWcnNetworkProfileLoaderElevated@@AEAAJKPEAUIWcnElevationHelper@@@Z; CWcnNetworkProfileLoaderElevated::LoadHostedNetworkProfile(ulong,IWcnElevationHelper *)
0x18002d6b3  mov     ebx, eax
0x18002d6b5  test    eax, eax
0x18002d6b7  jns     short loc_18002D6E0
0x18002d6b9  mov     r10, cs:WPP_GLOBAL_Control
0x18002d6c0  cmp     r10, r14
0x18002d6c3  jz      short loc_18002D6E7
0x18002d6c5  cmp     byte ptr [r10+19h], 3
0x18002d6ca  jb      short loc_18002D6E7
0x18002d6cc  mov     edx, 0Eh
0x18002d6d1  mov     r9d, eax
0x18002d6d4  mov     r8, r13
0x18002d6d7  mov     rcx, [r10+10h]
0x18002d6db  call    WPP_SF_d
0x18002d6e0  mov     r10, cs:WPP_GLOBAL_Control
0x18002d6e7  test    dil, 2
0x18002d6eb  jz      short loc_18002D734
0x18002d6ed  mov     edx, edi; unsigned int
0x18002d6ef  mov     rcx, rsi; this
0x18002d6f2  call    ?IsOneProfileEnough@CWcnNetworkProfileLoader@@IEBA_NK@Z; CWcnNetworkProfileLoader::IsOneProfileEnough(ulong)
0x18002d6f7  test    al, al
0x18002d6f9  jnz     short loc_18002D734
0x18002d6fb  call    ?LoadProfileFromLastFC@CWcnNetworkProfileLoader@@IEAAJXZ; CWcnNetworkProfileLoader::LoadProfileFromLastFC(void)
0x18002d700  mov     ebx, eax
0x18002d702  test    eax, eax
0x18002d704  jns     short loc_18002D72D
0x18002d706  mov     r10, cs:WPP_GLOBAL_Control
0x18002d70d  cmp     r10, r14
0x18002d710  jz      short loc_18002D765
0x18002d712  cmp     byte ptr [r10+19h], 3
0x18002d717  jb      short loc_18002D734
0x18002d719  mov     edx, 0Fh
0x18002d71e  mov     r9d, eax
0x18002d721  mov     r8, r13
0x18002d724  mov     rcx, [r10+10h]
0x18002d728  call    WPP_SF_d
0x18002d72d  mov     r10, cs:WPP_GLOBAL_Control
0x18002d734  cmp     r10, r14
0x18002d737  jz      short loc_18002D765
0x18002d739  test    ebx, ebx
0x18002d73b  js      short loc_18002D744
0x18002d73d  cmp     byte ptr [r10+19h], 6
0x18002d742  jb      short loc_18002D765
0x18002d744  or      ecx, 0FFFFFFFFh; int
0x18002d747  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18002d74c  mov     edx, 10h
0x18002d751  mov     dword ptr [rsp+68h+ppv], ebx
0x18002d755  mov     r9, rax
0x18002d758  mov     r8, r13
0x18002d75b  mov     rcx, [r10+10h]
0x18002d75f  call    WPP_SF_sd
0x18002d764  nop
0x18002d765  lea     rcx, [rsp+68h+arg_10]
0x18002d76d  call    ??1?$CComPtrBase@UIWCNDevicePrivate@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(void)
0x18002d772  add     rsp, 38h
0x18002d776  pop     r14
0x18002d778  pop     r13
0x18002d77a  pop     rdi
0x18002d77b  pop     rsi
0x18002d77c  pop     rbp
0x18002d77d  pop     rbx
0x18002d77e  retn
```
