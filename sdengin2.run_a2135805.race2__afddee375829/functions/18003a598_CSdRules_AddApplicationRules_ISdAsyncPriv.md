# CSdRules::AddApplicationRules(ISdAsyncPriv *)

- ea: `0x18003a598`
- end: `0x18003aad0`
- name: `?AddApplicationRules@CSdRules@@QEAAJPEAUISdAsyncPriv@@@Z`
- size: `1336`
- prototype: `__int64 __fastcall(CSdRules *__hidden this, struct ISdAsyncPriv *)`
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x1800433d8`

## callees

- `0x180008370`
- `0x1800083e4`
- `0x180008588`
- `0x180014c30`
- `0x18003a598`
- `0x180044f60`
- `0x180045090`
- `0x180072e08`
- `0x180072f14`
- `0x180074804`
- `0x1800939a0`
- `0x180094730`
- `0x180095808`
- `0x18009e234`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003a665`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003a6ca`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003aa31`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003a665`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003a6ca`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003aa31`
- `msi!__imp_MsiEnumClientsW` at `0x18003a6b1`
- `msi!__imp_MsiEnumClientsW` at `0x18003a6b1`
- `msi!__imp_MsiEnumComponentsW` at `0x18003a68d`
- `msi!__imp_MsiEnumComponentsW` at `0x18003a98b`
- `msi!__imp_MsiEnumComponentsW` at `0x18003a68d`
- `msi!__imp_MsiEnumComponentsW` at `0x18003a98b`
- `msi!__imp_MsiSetInternalUI` at `0x18003a67b`
- `msi!__imp_MsiSetInternalUI` at `0x18003a67b`
- `msi!__imp_MsiGetComponentPathW` at `0x18003a742`
- `msi!__imp_MsiGetComponentPathW` at `0x18003a742`

## pseudocode

```c
__int64 __fastcall CSdRules::AddApplicationRules(CSdRules *this, struct ISdAsyncPriv *a2)
{
  DWORD v4; // esi
  struct _FILETIME v5; // rbx
  UINT i; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  DWORD v9; // edi
  DWORD j; // edx
  UINT v11; // eax
  int v12; // r8d
  __int16 v13; // ax
  INSTALLSTATE ComponentPathW; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // r8d
  int DosVolumeName; // eax
  unsigned int v19; // ebx
  DWORD pcchBuf; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME v23; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME v24; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpszVolumeName[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v26[2]; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+80h] [rbp-80h] BYREF
  __int16 v28; // [rsp+84h] [rbp-7Ch]
  __int16 v29; // [rsp+86h] [rbp-7Ah]
  WCHAR ComponentBuf[40]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR ProductBuf[40]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR PathBuf[264]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v33[264]; // [rsp+370h] [rbp+270h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v27, "CSdRules::AddApplicationRules", 0x269u, 0);
  v4 = 0;
  memset_0(ComponentBuf, 0, 0x4Eu);
  memset_0(ProductBuf, 0, 0x4Eu);
  memset_0(PathBuf, 0, 0x20Au);
  memset_0(v33, 0, 0x20Au);
  pcchBuf = 261;
  SystemTimeAsFileTime = 0;
  v24 = 0;
  v23 = 0;
  v26[0] = qword_1800EE510;
  v26[1] = 0;
  lpszVolumeName[0] = (LPCWSTR)qword_1800EE510;
  lpszVolumeName[1] = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v5 = SystemTimeAsFileTime;
  MsiSetInternalUI(INSTALLUILEVEL_NONE, 0);
  for ( i = MsiEnumComponentsW(0, ComponentBuf); !i; i = MsiEnumComponentsW(v4, ComponentBuf) )
  {
    v9 = 0;
    for ( j = 0; ; j = v9 )
    {
      v11 = MsiEnumClientsW(ComponentBuf, j, ProductBuf);
      if ( v11 )
        break;
      GetSystemTimeAsFileTime(&v23);
      if ( *(_QWORD *)&v23 - *(_QWORD *)&SystemTimeAsFileTime >= 0x165A0E310uLL )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_05c116ddfb383e8206a27640713afc74_Traceguids);
        v27 = 1;
        v28 = 666;
        goto LABEL_56;
      }
      if ( *(_QWORD *)&v23 - *(_QWORD *)&v5 >= 0x8F0F890u )
      {
        v27 = (*(__int64 (__fastcall **)(struct ISdAsyncPriv *))(*(_QWORD *)a2 + 120LL))(a2);
        v13 = 671;
        if ( v27 < 0 )
          goto LABEL_44;
        v28 = 671;
        v5 = v23;
      }
      pcchBuf = 261;
      ComponentPathW = MsiGetComponentPathW(ProductBuf, ComponentBuf, PathBuf, &pcchBuf);
      if ( pcchBuf )
      {
        if ( (unsigned int)(ComponentPathW - 3) > 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              (unsigned int)&WPP_05c116ddfb383e8206a27640713afc74_Traceguids,
              (unsigned int)PathBuf,
              ComponentPathW);
        }
        else if ( ((PathBuf[0] - 48) & 0xFFFD) != 0 || (unsigned __int16)(PathBuf[1] - 48) > 3u || PathBuf[2] != 58 )
        {
          if ( PathBuf[pcchBuf - 1] == 92 )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v16 = 19;
              goto LABEL_25;
            }
          }
          else if ( (unsigned int)SxCheckWildCards(PathBuf) )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v16 = 20;
              goto LABEL_25;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                21,
                &WPP_05c116ddfb383e8206a27640713afc74_Traceguids,
                PathBuf);
            CBsString::Empty((CBsString *)v26);
            CBsString::Empty((CBsString *)lpszVolumeName);
            if ( (int)SxCrackPath(PathBuf, (struct CBsString *)lpszVolumeName, (struct CBsString *)v26) >= 0 )
            {
              DosVolumeName = SxGetDosVolumeName(lpszVolumeName[0], v33, v17);
              v27 = DosVolumeName;
              if ( DosVolumeName < 0 )
              {
                v13 = 732;
LABEL_44:
                v29 = v13;
                goto LABEL_56;
              }
              v28 = 732;
              if ( !DosVolumeName )
              {
                v27 = CSxRuleForest::AddRule(*((_QWORD *)this + 1), v33, v26[0], 1, 1, 2, 0);
                v13 = 741;
                if ( v27 < 0 )
                  goto LABEL_44;
                v28 = 741;
              }
            }
          }
        }
        else
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v16 = 18;
LABEL_25:
            WPP_SF_S(v15[2], v16, &WPP_05c116ddfb383e8206a27640713afc74_Traceguids, PathBuf);
          }
        }
      }
      ++v9;
    }
    if ( v11 != 259 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SdqD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        v12,
        (unsigned int)ComponentBuf,
        v9,
        (char)ProductBuf,
        v11);
    ++v4;
  }
  if ( i != 259 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, v4, ComponentBuf, i);
  GetSystemTimeAsFileTime(&v24);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_05c116ddfb383e8206a27640713afc74_Traceguids,
      (*(_QWORD *)&v24 - *(_QWORD *)&SystemTimeAsFileTime) / 0x2710uLL);
LABEL_56:
  v19 = v27;
  CBsString::_Release((CBsString *)lpszVolumeName);
  CBsString::_Release((CBsString *)v26);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v27);
  return v19;
}

```

## disassembly

```asm
0x18003a598  mov     [rsp-8+arg_10], rbx
0x18003a59d  mov     [rsp-8+arg_18], rsi
0x18003a5a2  push    rbp
0x18003a5a3  push    rdi
0x18003a5a4  push    r12
0x18003a5a6  push    r14
0x18003a5a8  push    r15
0x18003a5aa  lea     rbp, [rsp-490h]
0x18003a5b2  sub     rsp, 590h
0x18003a5b9  mov     rax, cs:__security_cookie
0x18003a5c0  xor     rax, rsp
0x18003a5c3  mov     [rbp+4B0h+var_30], rax
0x18003a5ca  mov     r14, rdx
0x18003a5cd  mov     r15, rcx
0x18003a5d0  xor     r9d, r9d; unsigned __int16
0x18003a5d3  mov     r8d, 269h; unsigned __int16
0x18003a5d9  lea     rdx, aCsdrulesAddapp; "CSdRules::AddApplicationRules"
0x18003a5e0  lea     rcx, [rbp+4B0h+var_530]; this
0x18003a5e4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003a5e9  xor     esi, esi
0x18003a5eb  lea     ebx, [rsi+4Eh]
0x18003a5ee  mov     r8d, ebx; Size
0x18003a5f1  xor     edx, edx; Val
0x18003a5f3  lea     rcx, [rbp+4B0h+ComponentBuf]; void *
0x18003a5f7  call    memset_0
0x18003a5fc  mov     r8d, ebx; Size
0x18003a5ff  xor     edx, edx; Val
0x18003a601  lea     rcx, [rbp+4B0h+ProductBuf]; void *
0x18003a605  call    memset_0
0x18003a60a  mov     ebx, 20Ah
0x18003a60f  mov     r8d, ebx; Size
0x18003a612  xor     edx, edx; Val
0x18003a614  lea     rcx, [rbp+4B0h+PathBuf]; void *
0x18003a618  call    memset_0
0x18003a61d  mov     r8d, ebx; Size
0x18003a620  xor     edx, edx; Val
0x18003a622  lea     rcx, [rbp+4B0h+var_240]; void *
0x18003a629  call    memset_0
0x18003a62e  mov     [rsp+5B0h+pcchBuf], 105h
0x18003a636  mov     qword ptr [rsp+5B0h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x18003a63b  mov     qword ptr [rsp+5B0h+var_558.dwLowDateTime], rsi
0x18003a640  mov     qword ptr [rsp+5B0h+var_560.dwLowDateTime], rsi
0x18003a645  lea     rax, qword_1800EE510
0x18003a64c  mov     [rsp+5B0h+var_540], rax
0x18003a651  mov     [rsp+5B0h+var_538], rsi
0x18003a656  mov     [rsp+5B0h+lpszVolumeName], rax
0x18003a65b  mov     [rsp+5B0h+var_548], rsi
0x18003a660  lea     rcx, [rsp+5B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003a665  call    cs:__imp_GetSystemTimeAsFileTime
0x18003a66c  nop     dword ptr [rax+rax+00h]
0x18003a671  mov     rbx, qword ptr [rsp+5B0h+SystemTimeAsFileTime.dwLowDateTime]
0x18003a676  xor     edx, edx; phWnd
0x18003a678  lea     ecx, [rsi+2]; dwUILevel
0x18003a67b  call    cs:__imp_MsiSetInternalUI
0x18003a682  nop     dword ptr [rax+rax+00h]
0x18003a687  lea     rdx, [rbp+4B0h+ComponentBuf]; lpComponentBuf
0x18003a68b  xor     ecx, ecx; iComponentIndex
0x18003a68d  call    cs:__imp_MsiEnumComponentsW
0x18003a694  nop     dword ptr [rax+rax+00h]
0x18003a699  lea     r12d, [rsi+1]
0x18003a69d  test    eax, eax
0x18003a69f  jnz     loc_18003A9EA
0x18003a6a5  xor     edi, edi
0x18003a6a7  xor     edx, edx; iProductIndex
0x18003a6a9  lea     r8, [rbp+4B0h+ProductBuf]; lpProductBuf
0x18003a6ad  lea     rcx, [rbp+4B0h+ComponentBuf]; szComponent
0x18003a6b1  call    cs:__imp_MsiEnumClientsW
0x18003a6b8  nop     dword ptr [rax+rax+00h]
0x18003a6bd  test    eax, eax
0x18003a6bf  jnz     loc_18003A944
0x18003a6c5  lea     rcx, [rsp+5B0h+var_560]; lpSystemTimeAsFileTime
0x18003a6ca  call    cs:__imp_GetSystemTimeAsFileTime
0x18003a6d1  nop     dword ptr [rax+rax+00h]
0x18003a6d6  mov     rax, qword ptr [rsp+5B0h+var_560.dwLowDateTime]
0x18003a6db  mov     rcx, rax
0x18003a6de  sub     rcx, qword ptr [rsp+5B0h+SystemTimeAsFileTime.dwLowDateTime]
0x18003a6e3  mov     rdx, 165A0E310h
0x18003a6ed  cmp     rcx, rdx
0x18003a6f0  jnb     loc_18003A9AA
0x18003a6f6  sub     rax, rbx
0x18003a6f9  cmp     rax, 8F0F890h
0x18003a6ff  jb      short loc_18003A729
0x18003a701  mov     rax, [r14]
0x18003a704  mov     rcx, r14
0x18003a707  mov     rax, [rax+78h]
0x18003a70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a710  mov     [rbp+4B0h+var_530], eax
0x18003a713  test    eax, eax
0x18003a715  mov     eax, 29Fh
0x18003a71a  js      loc_18003A9A1
0x18003a720  mov     [rbp+4B0h+var_52C], ax
0x18003a724  mov     rbx, qword ptr [rsp+5B0h+var_560.dwLowDateTime]
0x18003a729  mov     [rsp+5B0h+pcchBuf], 105h
0x18003a731  lea     r9, [rsp+5B0h+pcchBuf]; pcchBuf
0x18003a736  lea     r8, [rbp+4B0h+PathBuf]; lpPathBuf
0x18003a73a  lea     rdx, [rbp+4B0h+ComponentBuf]; szComponent
0x18003a73e  lea     rcx, [rbp+4B0h+ProductBuf]; szProduct
0x18003a742  call    cs:__imp_MsiGetComponentPathW
0x18003a749  nop     dword ptr [rax+rax+00h]
0x18003a74e  mov     edx, [rsp+5B0h+pcchBuf]
0x18003a752  test    edx, edx
0x18003a754  jz      loc_18003A93A
0x18003a75a  lea     ecx, [rax-3]
0x18003a75d  cmp     ecx, r12d
0x18003a760  ja      loc_18003A900
0x18003a766  movzx   eax, [rbp+4B0h+PathBuf]
0x18003a76a  sub     ax, 30h ; '0'
0x18003a76e  mov     ecx, 0FFFDh
0x18003a773  test    cx, ax
0x18003a776  jnz     short loc_18003A7B5
0x18003a778  movzx   eax, [rbp+4B0h+var_44E]
0x18003a77c  sub     ax, 30h ; '0'
0x18003a780  cmp     ax, 3
0x18003a784  ja      short loc_18003A7B5
0x18003a786  cmp     [rbp+4B0h+var_44C], 3Ah ; ':'
0x18003a78b  jnz     short loc_18003A7B5
0x18003a78d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a794  lea     rax, WPP_GLOBAL_Control
0x18003a79b  cmp     rcx, rax
0x18003a79e  jz      loc_18003A93A
0x18003a7a4  test    [rcx+1Ch], r12b
0x18003a7a8  jz      loc_18003A93A
0x18003a7ae  mov     edx, 12h
0x18003a7b3  jmp     short loc_18003A81B
0x18003a7b5  lea     eax, [rdx-1]
0x18003a7b8  cmp     [rbp+rax*2+4B0h+PathBuf], 5Ch ; '\'
0x18003a7be  jnz     short loc_18003A7E8
0x18003a7c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a7c7  lea     rax, WPP_GLOBAL_Control
0x18003a7ce  cmp     rcx, rax
0x18003a7d1  jz      loc_18003A93A
0x18003a7d7  test    [rcx+1Ch], r12b
0x18003a7db  jz      loc_18003A93A
0x18003a7e1  mov     edx, 13h
0x18003a7e6  jmp     short loc_18003A81B
0x18003a7e8  lea     rcx, [rbp+4B0h+PathBuf]; unsigned __int16 *
0x18003a7ec  call    ?SxCheckWildCards@@YAHPEBG@Z; SxCheckWildCards(ushort const *)
0x18003a7f1  test    eax, eax
0x18003a7f3  jz      short loc_18003A834
0x18003a7f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a7fc  lea     rax, WPP_GLOBAL_Control
0x18003a803  cmp     rcx, rax
0x18003a806  jz      loc_18003A93A
0x18003a80c  test    [rcx+1Ch], r12b
0x18003a810  jz      loc_18003A93A
0x18003a816  mov     edx, 14h
0x18003a81b  lea     r9, [rbp+4B0h+PathBuf]
0x18003a81f  lea     r8, WPP_05c116ddfb383e8206a27640713afc74_Traceguids
0x18003a826  mov     rcx, [rcx+10h]
0x18003a82a  call    WPP_SF_S
0x18003a82f  jmp     loc_18003A93A
0x18003a834  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a83b  lea     rax, WPP_GLOBAL_Control
0x18003a842  cmp     rcx, rax
0x18003a845  jz      short loc_18003A866
0x18003a847  test    [rcx+1Ch], r12b
0x18003a84b  jz      short loc_18003A866
0x18003a84d  mov     edx, 15h
0x18003a852  lea     r9, [rbp+4B0h+PathBuf]
0x18003a856  lea     r8, WPP_05c116ddfb383e8206a27640713afc74_Traceguids
0x18003a85d  mov     rcx, [rcx+10h]
0x18003a861  call    WPP_SF_S
0x18003a866  lea     rcx, [rsp+5B0h+var_540]; this
0x18003a86b  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x18003a870  lea     rcx, [rsp+5B0h+lpszVolumeName]; this
0x18003a875  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x18003a87a  lea     r8, [rsp+5B0h+var_540]; struct CBsString *
0x18003a87f  lea     rdx, [rsp+5B0h+lpszVolumeName]; this
0x18003a884  lea     rcx, [rbp+4B0h+PathBuf]; lpSrc
0x18003a888  call    ?SxCrackPath@@YAJPEBGPEAVCBsString@@1@Z; SxCrackPath(ushort const *,CBsString *,CBsString *)
0x18003a88d  test    eax, eax
0x18003a88f  js      loc_18003A93A
0x18003a895  lea     rdx, [rbp+4B0h+var_240]; unsigned __int16 *
0x18003a89c  mov     rcx, [rsp+5B0h+lpszVolumeName]; lpszVolumeName
0x18003a8a1  call    ?SxGetDosVolumeName@@YAJPEBGPEAGK@Z; SxGetDosVolumeName(ushort const *,ushort *,ulong)
0x18003a8a6  mov     [rbp+4B0h+var_530], eax
0x18003a8a9  test    eax, eax
0x18003a8ab  js      loc_18003A99C
0x18003a8b1  mov     ecx, 2DCh
0x18003a8b6  mov     [rbp+4B0h+var_52C], cx
0x18003a8ba  jnz     short loc_18003A93A
0x18003a8bc  mov     [rsp+5B0h+var_580], 0
0x18003a8c5  mov     dword ptr [rsp+5B0h+var_588], 2
0x18003a8cd  mov     dword ptr [rsp+5B0h+var_590], r12d
0x18003a8d2  mov     r9d, r12d
0x18003a8d5  mov     r8, [rsp+5B0h+var_540]
0x18003a8da  lea     rdx, [rbp+4B0h+var_240]
0x18003a8e1  mov     rcx, [r15+8]
0x18003a8e5  call    ?AddRule@CSxRuleForest@@QEAAJPEBG0HHW4_SxRuleAction@@PEAVCSxExtensionSetList@@@Z; CSxRuleForest::AddRule(ushort const *,ushort const *,int,int,_SxRuleAction,CSxExtensionSetList *)
0x18003a8ea  mov     [rbp+4B0h+var_530], eax
0x18003a8ed  test    eax, eax
0x18003a8ef  mov     eax, 2E5h
0x18003a8f4  js      loc_18003A9A1
0x18003a8fa  mov     [rbp+4B0h+var_52C], ax
0x18003a8fe  jmp     short loc_18003A93A
0x18003a900  test    edx, edx
0x18003a902  jz      short loc_18003A93A
0x18003a904  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a90b  lea     rdx, WPP_GLOBAL_Control
0x18003a912  cmp     rcx, rdx
0x18003a915  jz      short loc_18003A93A
0x18003a917  test    [rcx+1Ch], r12b
0x18003a91b  jz      short loc_18003A93A
0x18003a91d  mov     edx, 11h
0x18003a922  mov     dword ptr [rsp+5B0h+var_590], eax
0x18003a926  lea     r9, [rbp+4B0h+PathBuf]
0x18003a92a  lea     r8, WPP_05c116ddfb383e8206a27640713afc74_Traceguids
0x18003a931  mov     rcx, [rcx+10h]
0x18003a935  call    WPP_SF_Sd
0x18003a93a  add     edi, r12d
0x18003a93d  mov     edx, edi
0x18003a93f  jmp     loc_18003A6A9
0x18003a944  cmp     eax, 103h
0x18003a949  jz      short loc_18003A982
0x18003a94b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a952  lea     rdx, WPP_GLOBAL_Control
0x18003a959  cmp     rcx, rdx
0x18003a95c  jz      short loc_18003A982
0x18003a95e  test    [rcx+1Ch], r12b
0x18003a962  jz      short loc_18003A982
0x18003a964  mov     dword ptr [rsp+5B0h+var_580], eax
0x18003a968  lea     rax, [rbp+4B0h+ProductBuf]
0x18003a96c  mov     [rsp+5B0h+var_588], rax
0x18003a971  mov     dword ptr [rsp+5B0h+var_590], edi
0x18003a975  lea     r9, [rbp+4B0h+ComponentBuf]
0x18003a979  mov     rcx, [rcx+10h]
0x18003a97d  call    WPP_SF_SdqD
0x18003a982  add     esi, r12d
0x18003a985  lea     rdx, [rbp+4B0h+ComponentBuf]; lpComponentBuf
0x18003a989  mov     ecx, esi; iComponentIndex
0x18003a98b  call    cs:__imp_MsiEnumComponentsW
0x18003a992  nop     dword ptr [rax+rax+00h]
0x18003a997  jmp     loc_18003A69D
0x18003a99c  mov     eax, 2DCh
0x18003a9a1  mov     [rbp+4B0h+var_52A], ax
0x18003a9a5  jmp     loc_18003AA82
0x18003a9aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a9b1  lea     rax, WPP_GLOBAL_Control
0x18003a9b8  cmp     rcx, rax
0x18003a9bb  jz      short loc_18003A9D8
0x18003a9bd  test    byte ptr [rcx+1Ch], 40h
0x18003a9c1  jz      short loc_18003A9D8
0x18003a9c3  mov     edx, 10h
0x18003a9c8  lea     r8, WPP_05c116ddfb383e8206a27640713afc74_Traceguids
0x18003a9cf  mov     rcx, [rcx+10h]
0x18003a9d3  call    WPP_SF_
0x18003a9d8  mov     [rbp+4B0h+var_530], r12d
0x18003a9dc  mov     eax, 29Ah
0x18003a9e1  mov     [rbp+4B0h+var_52C], ax
0x18003a9e5  jmp     loc_18003AA82
0x18003a9ea  cmp     eax, 103h
0x18003a9ef  jz      short loc_18003AA25
0x18003a9f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a9f8  lea     rdi, WPP_GLOBAL_Control
0x18003a9ff  cmp     rcx, rdi
0x18003aa02  jz      short loc_18003AA2C
0x18003aa04  test    [rcx+1Ch], r12b
0x18003aa08  jz      short loc_18003AA2C
0x18003aa0a  mov     dword ptr [rsp+5B0h+var_588], eax
0x18003aa0e  lea     rax, [rbp+4B0h+ComponentBuf]
0x18003aa12  mov     [rsp+5B0h+var_590], rax
0x18003aa17  mov     r9d, esi
0x18003aa1a  mov     rcx, [rcx+10h]
0x18003aa1e  call    WPP_SF_dqD
0x18003aa23  jmp     short loc_18003AA2C
0x18003aa25  lea     rdi, WPP_GLOBAL_Control
0x18003aa2c  lea     rcx, [rsp+5B0h+var_558]; lpSystemTimeAsFileTime
0x18003aa31  call    cs:__imp_GetSystemTimeAsFileTime
0x18003aa38  nop     dword ptr [rax+rax+00h]
0x18003aa3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aa44  cmp     rcx, rdi
0x18003aa47  jz      short loc_18003AA82
0x18003aa49  test    byte ptr [rcx+1Ch], 40h
0x18003aa4d  jz      short loc_18003AA82
0x18003aa4f  mov     rdx, qword ptr [rsp+5B0h+var_558.dwLowDateTime]
0x18003aa54  sub     rdx, qword ptr [rsp+5B0h+SystemTimeAsFileTime.dwLowDateTime]
0x18003aa59  mov     rax, 346DC5D63886594Bh
0x18003aa63  mul     rdx
0x18003aa66  mov     r9, rdx
0x18003aa69  shr     r9, 0Bh
0x18003aa6d  mov     edx, 18h
0x18003aa72  lea     r8, WPP_05c116ddfb383e8206a27640713afc74_Traceguids
0x18003aa79  mov     rcx, [rcx+10h]
0x18003aa7d  call    WPP_SF_q
0x18003aa82  mov     ebx, [rbp+4B0h+var_530]
0x18003aa85  lea     rcx, [rsp+5B0h+lpszVolumeName]; this
0x18003aa8a  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18003aa8f  lea     rcx, [rsp+5B0h+var_540]; this
0x18003aa94  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18003aa99  lea     rcx, [rbp+4B0h+var_530]; this
0x18003aa9d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003aaa2  mov     eax, ebx
0x18003aaa4  mov     rcx, [rbp+4B0h+var_30]
0x18003aaab  xor     rcx, rsp; StackCookie
0x18003aaae  call    __security_check_cookie
0x18003aab3  lea     r11, [rsp+5B0h+var_20]
0x18003aabb  mov     rbx, [r11+40h]
0x18003aabf  mov     rsi, [r11+48h]
0x18003aac3  mov     rsp, r11
0x18003aac6  pop     r15
  ... truncated ...
```
