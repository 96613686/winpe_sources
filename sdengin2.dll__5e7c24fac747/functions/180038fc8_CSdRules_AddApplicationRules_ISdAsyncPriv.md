# CSdRules::AddApplicationRules(ISdAsyncPriv *)

- ea: `0x180038fc8`
- end: `0x1800394cf`
- name: `?AddApplicationRules@CSdRules@@QEAAJPEAUISdAsyncPriv@@@Z`
- size: `1287`
- prototype: `__int64 __fastcall(CSdRules *__hidden this, struct ISdAsyncPriv *)`
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x180041b90`

## callees

- `0x1800081d8`
- `0x180008240`
- `0x1800083cc`
- `0x180014394`
- `0x180038fc8`
- `0x180043670`
- `0x180043794`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180071784`
- `0x18008f8ac`
- `0x18009063c`
- `0x180091678`
- `0x180099bdc`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180039095`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800390e2`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180039437`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180039095`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800390e2`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180039437`
- `msi!__imp_MsiEnumClientsW` at `0x1800390cf`
- `msi!__imp_MsiEnumClientsW` at `0x1800390cf`
- `msi!__imp_MsiEnumComponentsW` at `0x1800390b1`
- `msi!__imp_MsiEnumComponentsW` at `0x180039397`
- `msi!__imp_MsiEnumComponentsW` at `0x1800390b1`
- `msi!__imp_MsiEnumComponentsW` at `0x180039397`
- `msi!__imp_MsiSetInternalUI` at `0x1800390a5`
- `msi!__imp_MsiSetInternalUI` at `0x1800390a5`
- `msi!__imp_MsiGetComponentPathW` at `0x180039154`
- `msi!__imp_MsiGetComponentPathW` at `0x180039154`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v27, "CSdRules::AddApplicationRules", 617, 0);
  v4 = 0;
  memset_0(ComponentBuf, 0, 0x4Eu);
  memset_0(ProductBuf, 0, 0x4Eu);
  memset_0(PathBuf, 0, 0x20Au);
  memset_0(v33, 0, 0x20Au);
  pcchBuf = 261;
  SystemTimeAsFileTime = 0;
  v24 = 0;
  v23 = 0;
  v26[0] = qword_1800E8530;
  v26[1] = 0;
  lpszVolumeName[0] = (LPCWSTR)qword_1800E8530;
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
0x180038fc8  mov     [rsp-8+arg_10], rbx
0x180038fcd  mov     [rsp-8+arg_18], rsi
0x180038fd2  push    rbp
0x180038fd3  push    rdi
0x180038fd4  push    r12
0x180038fd6  push    r14
0x180038fd8  push    r15
0x180038fda  lea     rbp, [rsp-490h]
0x180038fe2  sub     rsp, 590h
0x180038fe9  mov     rax, cs:__security_cookie
0x180038ff0  xor     rax, rsp
0x180038ff3  mov     [rbp+4B0h+var_30], rax
0x180038ffa  mov     r14, rdx
0x180038ffd  mov     r15, rcx
0x180039000  xor     r9d, r9d; unsigned __int16
0x180039003  mov     r8d, 269h; unsigned __int16
0x180039009  lea     rdx, aCsdrulesAddapp; "CSdRules::AddApplicationRules"
0x180039010  lea     rcx, [rbp+4B0h+var_530]; this
0x180039014  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180039019  xor     esi, esi
0x18003901b  lea     ebx, [rsi+4Eh]
0x18003901e  mov     r8d, ebx; Size
0x180039021  xor     edx, edx; Val
0x180039023  lea     rcx, [rbp+4B0h+ComponentBuf]; void *
0x180039027  call    memset_0
0x18003902c  mov     r8d, ebx; Size
0x18003902f  xor     edx, edx; Val
0x180039031  lea     rcx, [rbp+4B0h+ProductBuf]; void *
0x180039035  call    memset_0
0x18003903a  mov     ebx, 20Ah
0x18003903f  mov     r8d, ebx; Size
0x180039042  xor     edx, edx; Val
0x180039044  lea     rcx, [rbp+4B0h+PathBuf]; void *
0x180039048  call    memset_0
0x18003904d  mov     r8d, ebx; Size
0x180039050  xor     edx, edx; Val
0x180039052  lea     rcx, [rbp+4B0h+var_240]; void *
0x180039059  call    memset_0
0x18003905e  mov     [rsp+5B0h+pcchBuf], 105h
0x180039066  mov     qword ptr [rsp+5B0h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x18003906b  mov     qword ptr [rsp+5B0h+var_558.dwLowDateTime], rsi
0x180039070  mov     qword ptr [rsp+5B0h+var_560.dwLowDateTime], rsi
0x180039075  lea     rax, qword_1800E8530
0x18003907c  mov     [rsp+5B0h+var_540], rax
0x180039081  mov     [rsp+5B0h+var_538], rsi
0x180039086  mov     [rsp+5B0h+lpszVolumeName], rax
0x18003908b  mov     [rsp+5B0h+var_548], rsi
0x180039090  lea     rcx, [rsp+5B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180039095  call    cs:__imp_GetSystemTimeAsFileTime
0x18003909b  mov     rbx, qword ptr [rsp+5B0h+SystemTimeAsFileTime.dwLowDateTime]
0x1800390a0  xor     edx, edx; phWnd
0x1800390a2  lea     ecx, [rsi+2]; dwUILevel
0x1800390a5  call    cs:__imp_MsiSetInternalUI
0x1800390ab  lea     rdx, [rbp+4B0h+ComponentBuf]; lpComponentBuf
0x1800390af  xor     ecx, ecx; iComponentIndex
0x1800390b1  call    cs:__imp_MsiEnumComponentsW
0x1800390b7  lea     r12d, [rsi+1]
0x1800390bb  test    eax, eax
0x1800390bd  jnz     loc_1800393F0
0x1800390c3  xor     edi, edi
0x1800390c5  xor     edx, edx; iProductIndex
0x1800390c7  lea     r8, [rbp+4B0h+ProductBuf]; lpProductBuf
0x1800390cb  lea     rcx, [rbp+4B0h+ComponentBuf]; szComponent
0x1800390cf  call    cs:__imp_MsiEnumClientsW
0x1800390d5  test    eax, eax
0x1800390d7  jnz     loc_180039350
0x1800390dd  lea     rcx, [rsp+5B0h+var_560]; lpSystemTimeAsFileTime
0x1800390e2  call    cs:__imp_GetSystemTimeAsFileTime
0x1800390e8  mov     rax, qword ptr [rsp+5B0h+var_560.dwLowDateTime]
0x1800390ed  mov     rcx, rax
0x1800390f0  sub     rcx, qword ptr [rsp+5B0h+SystemTimeAsFileTime.dwLowDateTime]
0x1800390f5  mov     rdx, 165A0E310h
0x1800390ff  cmp     rcx, rdx
0x180039102  jnb     loc_1800393B0
0x180039108  sub     rax, rbx
0x18003910b  cmp     rax, 8F0F890h
0x180039111  jb      short loc_18003913B
0x180039113  mov     rax, [r14]
0x180039116  mov     rcx, r14
0x180039119  mov     rax, [rax+78h]
0x18003911d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039122  mov     [rbp+4B0h+var_530], eax
0x180039125  test    eax, eax
0x180039127  mov     eax, 29Fh
0x18003912c  js      loc_1800393A7
0x180039132  mov     [rbp+4B0h+var_52C], ax
0x180039136  mov     rbx, qword ptr [rsp+5B0h+var_560.dwLowDateTime]
0x18003913b  mov     [rsp+5B0h+pcchBuf], 105h
0x180039143  lea     r9, [rsp+5B0h+pcchBuf]; pcchBuf
0x180039148  lea     r8, [rbp+4B0h+PathBuf]; lpPathBuf
0x18003914c  lea     rdx, [rbp+4B0h+ComponentBuf]; szComponent
0x180039150  lea     rcx, [rbp+4B0h+ProductBuf]; szProduct
0x180039154  call    cs:__imp_MsiGetComponentPathW
0x18003915a  mov     edx, [rsp+5B0h+pcchBuf]
0x18003915e  test    edx, edx
0x180039160  jz      loc_180039346
0x180039166  lea     ecx, [rax-3]
0x180039169  cmp     ecx, r12d
0x18003916c  ja      loc_18003930C
0x180039172  movzx   eax, [rbp+4B0h+PathBuf]
0x180039176  sub     ax, 30h ; '0'
0x18003917a  mov     ecx, 0FFFDh
0x18003917f  test    cx, ax
0x180039182  jnz     short loc_1800391C1
0x180039184  movzx   eax, [rbp+4B0h+var_44E]
0x180039188  sub     ax, 30h ; '0'
0x18003918c  cmp     ax, 3
0x180039190  ja      short loc_1800391C1
0x180039192  cmp     [rbp+4B0h+var_44C], 3Ah ; ':'
0x180039197  jnz     short loc_1800391C1
0x180039199  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391a0  lea     rax, WPP_GLOBAL_Control
0x1800391a7  cmp     rcx, rax
0x1800391aa  jz      loc_180039346
0x1800391b0  test    [rcx+1Ch], r12b
0x1800391b4  jz      loc_180039346
0x1800391ba  mov     edx, 12h
0x1800391bf  jmp     short loc_180039227
0x1800391c1  lea     eax, [rdx-1]
0x1800391c4  cmp     [rbp+rax*2+4B0h+PathBuf], 5Ch ; '\'
0x1800391ca  jnz     short loc_1800391F4
0x1800391cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800391d3  lea     rax, WPP_GLOBAL_Control
0x1800391da  cmp     rcx, rax
0x1800391dd  jz      loc_180039346
0x1800391e3  test    [rcx+1Ch], r12b
0x1800391e7  jz      loc_180039346
0x1800391ed  mov     edx, 13h
0x1800391f2  jmp     short loc_180039227
0x1800391f4  lea     rcx, [rbp+4B0h+PathBuf]; unsigned __int16 *
0x1800391f8  call    ?SxCheckWildCards@@YAHPEBG@Z; SxCheckWildCards(ushort const *)
0x1800391fd  test    eax, eax
0x1800391ff  jz      short loc_180039240
0x180039201  mov     rcx, cs:WPP_GLOBAL_Control
0x180039208  lea     rax, WPP_GLOBAL_Control
0x18003920f  cmp     rcx, rax
0x180039212  jz      loc_180039346
0x180039218  test    [rcx+1Ch], r12b
0x18003921c  jz      loc_180039346
0x180039222  mov     edx, 14h
0x180039227  lea     r9, [rbp+4B0h+PathBuf]
0x18003922b  lea     r8, WPP_05c116ddfb383e8206a27640713afc74_Traceguids
0x180039232  mov     rcx, [rcx+10h]
0x180039236  call    WPP_SF_S
0x18003923b  jmp     loc_180039346
0x180039240  mov     rcx, cs:WPP_GLOBAL_Control
0x180039247  lea     rax, WPP_GLOBAL_Control
0x18003924e  cmp     rcx, rax
0x180039251  jz      short loc_180039272
0x180039253  test    [rcx+1Ch], r12b
0x180039257  jz      short loc_180039272
0x180039259  mov     edx, 15h
0x18003925e  lea     r9, [rbp+4B0h+PathBuf]
0x180039262  lea     r8, WPP_05c116ddfb383e8206a27640713afc74_Traceguids
0x180039269  mov     rcx, [rcx+10h]
0x18003926d  call    WPP_SF_S
0x180039272  lea     rcx, [rsp+5B0h+var_540]; this
0x180039277  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x18003927c  lea     rcx, [rsp+5B0h+lpszVolumeName]; this
0x180039281  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180039286  lea     r8, [rsp+5B0h+var_540]; struct CBsString *
0x18003928b  lea     rdx, [rsp+5B0h+lpszVolumeName]; this
0x180039290  lea     rcx, [rbp+4B0h+PathBuf]; lpSrc
0x180039294  call    ?SxCrackPath@@YAJPEBGPEAVCBsString@@1@Z; SxCrackPath(ushort const *,CBsString *,CBsString *)
0x180039299  test    eax, eax
0x18003929b  js      loc_180039346
0x1800392a1  lea     rdx, [rbp+4B0h+var_240]; unsigned __int16 *
0x1800392a8  mov     rcx, [rsp+5B0h+lpszVolumeName]; lpszVolumeName
0x1800392ad  call    ?SxGetDosVolumeName@@YAJPEBGPEAGK@Z; SxGetDosVolumeName(ushort const *,ushort *,ulong)
0x1800392b2  mov     [rbp+4B0h+var_530], eax
0x1800392b5  test    eax, eax
0x1800392b7  js      loc_1800393A2
0x1800392bd  mov     ecx, 2DCh
0x1800392c2  mov     [rbp+4B0h+var_52C], cx
0x1800392c6  jnz     short loc_180039346
0x1800392c8  mov     [rsp+5B0h+var_580], 0
0x1800392d1  mov     dword ptr [rsp+5B0h+var_588], 2
0x1800392d9  mov     dword ptr [rsp+5B0h+var_590], r12d
0x1800392de  mov     r9d, r12d
0x1800392e1  mov     r8, [rsp+5B0h+var_540]
0x1800392e6  lea     rdx, [rbp+4B0h+var_240]
0x1800392ed  mov     rcx, [r15+8]
0x1800392f1  call    ?AddRule@CSxRuleForest@@QEAAJPEBG0HHW4_SxRuleAction@@PEAVCSxExtensionSetList@@@Z; CSxRuleForest::AddRule(ushort const *,ushort const *,int,int,_SxRuleAction,CSxExtensionSetList *)
0x1800392f6  mov     [rbp+4B0h+var_530], eax
0x1800392f9  test    eax, eax
0x1800392fb  mov     eax, 2E5h
0x180039300  js      loc_1800393A7
0x180039306  mov     [rbp+4B0h+var_52C], ax
0x18003930a  jmp     short loc_180039346
0x18003930c  test    edx, edx
0x18003930e  jz      short loc_180039346
0x180039310  mov     rcx, cs:WPP_GLOBAL_Control
0x180039317  lea     rdx, WPP_GLOBAL_Control
0x18003931e  cmp     rcx, rdx
0x180039321  jz      short loc_180039346
0x180039323  test    [rcx+1Ch], r12b
0x180039327  jz      short loc_180039346
0x180039329  mov     edx, 11h
0x18003932e  mov     dword ptr [rsp+5B0h+var_590], eax
0x180039332  lea     r9, [rbp+4B0h+PathBuf]
0x180039336  lea     r8, WPP_05c116ddfb383e8206a27640713afc74_Traceguids
0x18003933d  mov     rcx, [rcx+10h]
0x180039341  call    WPP_SF_Sd
0x180039346  add     edi, r12d
0x180039349  mov     edx, edi
0x18003934b  jmp     loc_1800390C7
0x180039350  cmp     eax, 103h
0x180039355  jz      short loc_18003938E
0x180039357  mov     rcx, cs:WPP_GLOBAL_Control
0x18003935e  lea     rdx, WPP_GLOBAL_Control
0x180039365  cmp     rcx, rdx
0x180039368  jz      short loc_18003938E
0x18003936a  test    [rcx+1Ch], r12b
0x18003936e  jz      short loc_18003938E
0x180039370  mov     dword ptr [rsp+5B0h+var_580], eax
0x180039374  lea     rax, [rbp+4B0h+ProductBuf]
0x180039378  mov     [rsp+5B0h+var_588], rax
0x18003937d  mov     dword ptr [rsp+5B0h+var_590], edi
0x180039381  lea     r9, [rbp+4B0h+ComponentBuf]
0x180039385  mov     rcx, [rcx+10h]
0x180039389  call    WPP_SF_SdqD
0x18003938e  add     esi, r12d
0x180039391  lea     rdx, [rbp+4B0h+ComponentBuf]; lpComponentBuf
0x180039395  mov     ecx, esi; iComponentIndex
0x180039397  call    cs:__imp_MsiEnumComponentsW
0x18003939d  jmp     loc_1800390BB
0x1800393a2  mov     eax, 2DCh
0x1800393a7  mov     [rbp+4B0h+var_52A], ax
0x1800393ab  jmp     loc_180039482
0x1800393b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800393b7  lea     rax, WPP_GLOBAL_Control
0x1800393be  cmp     rcx, rax
0x1800393c1  jz      short loc_1800393DE
0x1800393c3  test    byte ptr [rcx+1Ch], 40h
0x1800393c7  jz      short loc_1800393DE
0x1800393c9  mov     edx, 10h
0x1800393ce  lea     r8, WPP_05c116ddfb383e8206a27640713afc74_Traceguids
0x1800393d5  mov     rcx, [rcx+10h]
0x1800393d9  call    WPP_SF_
0x1800393de  mov     [rbp+4B0h+var_530], r12d
0x1800393e2  mov     eax, 29Ah
0x1800393e7  mov     [rbp+4B0h+var_52C], ax
0x1800393eb  jmp     loc_180039482
0x1800393f0  cmp     eax, 103h
0x1800393f5  jz      short loc_18003942B
0x1800393f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800393fe  lea     rdi, WPP_GLOBAL_Control
0x180039405  cmp     rcx, rdi
0x180039408  jz      short loc_180039432
0x18003940a  test    [rcx+1Ch], r12b
0x18003940e  jz      short loc_180039432
0x180039410  mov     dword ptr [rsp+5B0h+var_588], eax
0x180039414  lea     rax, [rbp+4B0h+ComponentBuf]
0x180039418  mov     [rsp+5B0h+var_590], rax
0x18003941d  mov     r9d, esi
0x180039420  mov     rcx, [rcx+10h]
0x180039424  call    WPP_SF_dqD
0x180039429  jmp     short loc_180039432
0x18003942b  lea     rdi, WPP_GLOBAL_Control
0x180039432  lea     rcx, [rsp+5B0h+var_558]; lpSystemTimeAsFileTime
0x180039437  call    cs:__imp_GetSystemTimeAsFileTime
0x18003943d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039444  cmp     rcx, rdi
0x180039447  jz      short loc_180039482
0x180039449  test    byte ptr [rcx+1Ch], 40h
0x18003944d  jz      short loc_180039482
0x18003944f  mov     rdx, qword ptr [rsp+5B0h+var_558.dwLowDateTime]
0x180039454  sub     rdx, qword ptr [rsp+5B0h+SystemTimeAsFileTime.dwLowDateTime]
0x180039459  mov     rax, 346DC5D63886594Bh
0x180039463  mul     rdx
0x180039466  mov     r9, rdx
0x180039469  shr     r9, 0Bh
0x18003946d  mov     edx, 18h
0x180039472  lea     r8, WPP_05c116ddfb383e8206a27640713afc74_Traceguids
0x180039479  mov     rcx, [rcx+10h]
0x18003947d  call    WPP_SF_q
0x180039482  mov     ebx, [rbp+4B0h+var_530]
0x180039485  lea     rcx, [rsp+5B0h+lpszVolumeName]; this
0x18003948a  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18003948f  lea     rcx, [rsp+5B0h+var_540]; this
0x180039494  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180039499  lea     rcx, [rbp+4B0h+var_530]; this
0x18003949d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800394a2  mov     eax, ebx
0x1800394a4  mov     rcx, [rbp+4B0h+var_30]
0x1800394ab  xor     rcx, rsp; StackCookie
0x1800394ae  call    __security_check_cookie
0x1800394b3  lea     r11, [rsp+5B0h+var_20]
0x1800394bb  mov     rbx, [r11+40h]
0x1800394bf  mov     rsi, [r11+48h]
0x1800394c3  mov     rsp, r11
0x1800394c6  pop     r15
0x1800394c8  pop     r14
0x1800394ca  pop     r12
0x1800394cc  pop     rdi
0x1800394cd  pop     rbp
0x1800394ce  retn
```
