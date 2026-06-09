# AsrSystem::_BuildMbrPartitionXmlNode(CXMLDocument *,_ASR_DISK_INFO *,ulong,CXMLNode * *)

- ea: `0x1400790fc`
- end: `0x140079508`
- name: `?_BuildMbrPartitionXmlNode@AsrSystem@@AEAAHPEAVCXMLDocument@@PEAU_ASR_DISK_INFO@@KPEAPEAVCXMLNode@@@Z`
- size: `1036`
- prototype: `__int64 __fastcall(AsrSystem *this, struct CXMLDocument *, struct _ASR_DISK_INFO *, unsigned int, struct CXMLNode **)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x14005da78`

## callees

- `0x140021ca0`
- `0x1400235a8`
- `0x14003caec`
- `0x140058d00`
- `0x1400790fc`
- `0x14007ff70`
- `0x140091560`
- `0x1400d257c`
- `0x1400d25f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400794d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400794d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007925a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400792ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400792f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007947f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400794a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140079239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007925a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400792ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400792f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007947f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400794a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400794bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400794c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400794bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400794c5`

## string_xrefs

- `0x140079138`: `AsrSystem::_BuildMbrPartitionXmlNode`
- `0x1400794cb`: `AsrSystem::_BuildMbrPartitionXmlNode`
- `0x140079180`: `pXmlDoc`
- `0x140079420`: `NumSymbolicNames`

## pseudocode

```c
__int64 __fastcall AsrSystem::_BuildMbrPartitionXmlNode(
        AsrSystem *this,
        struct CXMLDocument *a2,
        struct _ASR_DISK_INFO *a3,
        unsigned int a4,
        struct CXMLNode **a5)
{
  struct CXMLNode *v7; // rbx
  DWORD LastError; // esi
  struct _DRIVE_LAYOUT_INFORMATION_EX *v9; // rcx
  int v10; // edx
  const char *v11; // rax
  DWORD v12; // eax
  unsigned int v13; // ecx
  __int64 v14; // r12
  unsigned __int16 *v15; // r8
  DWORD v16; // eax
  int v17; // edx
  __int64 v18; // rax
  __int64 v19; // rcx
  unsigned int v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v22; // [rsp+38h] [rbp-C8h] BYREF
  struct CXMLNode *v23; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+4Ch] [rbp-B4h] BYREF
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v30; // [rsp+70h] [rbp-90h] BYREF
  int v31; // [rsp+78h] [rbp-88h]
  unsigned int *v32; // [rsp+80h] [rbp-80h]
  const wchar_t *v33; // [rsp+88h] [rbp-78h]
  int v34; // [rsp+90h] [rbp-70h]
  int *v35; // [rsp+98h] [rbp-68h]
  const wchar_t *v36; // [rsp+A0h] [rbp-60h]
  int v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  const wchar_t *v39; // [rsp+B8h] [rbp-48h]
  int v40; // [rsp+C0h] [rbp-40h]
  int *v41; // [rsp+C8h] [rbp-38h]
  const wchar_t *v42; // [rsp+D0h] [rbp-30h]
  int v43; // [rsp+D8h] [rbp-28h]
  int *v44; // [rsp+E0h] [rbp-20h]
  const wchar_t *v45; // [rsp+E8h] [rbp-18h]
  int v46; // [rsp+F0h] [rbp-10h]
  unsigned int *v47; // [rsp+F8h] [rbp-8h]
  const wchar_t *v48; // [rsp+100h] [rbp+0h]
  int v49; // [rsp+108h] [rbp+8h]
  __int64 *v50; // [rsp+110h] [rbp+10h]
  const wchar_t *v51; // [rsp+118h] [rbp+18h]
  int v52; // [rsp+120h] [rbp+20h]
  __int64 *v53; // [rsp+128h] [rbp+28h]
  const wchar_t *v54; // [rsp+130h] [rbp+30h]
  int v55; // [rsp+138h] [rbp+38h]
  int *v56; // [rsp+140h] [rbp+40h]

  v21 = a4;
  TraceFunctionEnter(L"AsrSystem::_BuildMbrPartitionXmlNode");
  v7 = 0;
  v23 = 0;
  v22 = 0;
  if ( !a2 )
  {
    LastError = 87;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v10 = 156;
      v11 = "pXmlDoc";
LABEL_5:
      WPP_SF_Ds(
        *(_QWORD *)v9->Gpt.DiskId.Data4,
        v10,
        (unsigned int)WPP_301009c9d2f6376782984d179fa21529_Traceguids,
        87,
        (__int64)v11);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  if ( a3 )
  {
    if ( !a5 )
    {
      LODWORD(a2) = 0;
      LastError = 87;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v10 = 158;
        v11 = "ppNodeOut";
        goto LABEL_5;
      }
      goto LABEL_31;
    }
    if ( !(unsigned int)XmlDocCreateNode(a2, L"MbrPartition", &v23) )
    {
      LODWORD(a2) = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v12 = GetLastError();
        WPP_SF_DsS(
          *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
          159,
          (unsigned int)WPP_301009c9d2f6376782984d179fa21529_Traceguids,
          v12,
          (__int64)"GetLastError()",
          (__int64)L"MbrPartition");
      }
      v7 = v23;
      goto LABEL_31;
    }
    v13 = v21;
    v14 = *((_QWORD *)a3 + 5);
    v7 = v23;
    v15 = *(unsigned __int16 **)(v14 + 24LL * v21);
    if ( v15 )
    {
      if ( !(unsigned int)AsrSystem::AppendVolumeSymbolicNamesIntoXmlNode(a2, v23, v15, &v22) )
      {
        LODWORD(a2) = 0;
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
        {
          goto LABEL_31;
        }
        v16 = GetLastError();
        v17 = 160;
        goto LABEL_24;
      }
      v13 = v21;
    }
    v18 = v13;
    v19 = *((_QWORD *)a3 + 2);
    v31 = 3;
    v34 = 8;
    v37 = 7;
    v46 = 8;
    v55 = 8;
    v28 = *(_QWORD *)(144 * v18 + v19 + 56);
    v29 = *(_QWORD *)(144 * v18 + v19 + 64);
    v24 = *(unsigned __int16 *)(v14 + 24LL * v21 + 12);
    v26 = *(unsigned __int8 *)(v14 + 24LL * v21 + 14);
    v27 = *(_DWORD *)(v14 + 24LL * v21 + 16);
    v25 = *(unsigned __int8 *)(144 * v18 + v19 + 80);
    v30 = L"PartitionIndex";
    v32 = &v21;
    v33 = L"PartitionFlag";
    v35 = &v24;
    v36 = L"BootFlag";
    v38 = 144 * v18 + v19 + 81;
    v40 = 6;
    v39 = L"PartitionType";
    v41 = &v25;
    v43 = 6;
    v42 = L"FileSystemType";
    v49 = 9;
    v44 = &v26;
    v45 = L"NumSymbolicNames";
    v47 = &v22;
    v48 = L"PartitionOffset";
    v50 = &v28;
    v51 = L"PartitionLength";
    v53 = &v29;
    v54 = L"IsCritical";
    v56 = &v27;
    v52 = 9;
    if ( (unsigned int)XmlNodeInsertAttributeSet(v7, (struct _CREATE_ATTRIBUTE_SET *)&v30, 9u) )
    {
      LastError = 0;
      *a5 = v7;
      v7 = 0;
      LODWORD(a2) = 1;
      goto LABEL_31;
    }
    LODWORD(a2) = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
    {
      goto LABEL_31;
    }
    v16 = GetLastError();
    v17 = 161;
LABEL_24:
    WPP_SF_DsS(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      v17,
      (unsigned int)WPP_301009c9d2f6376782984d179fa21529_Traceguids,
      v16,
      (__int64)"GetLastError()",
      (__int64)L"MbrPartition");
    goto LABEL_31;
  }
  LODWORD(a2) = 0;
  LastError = 87;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
  {
    v10 = 157;
    v11 = "pCurrentDisk";
    goto LABEL_5;
  }
LABEL_31:
  CoTaskMemFree(0);
  CoTaskMemFree(v7);
  TraceFunctionExit(L"AsrSystem::_BuildMbrPartitionXmlNode");
  SetLastError(LastError);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x1400790fc  mov     [rsp-8+arg_0], rbx
0x140079101  push    rbp
0x140079102  push    rsi
0x140079103  push    rdi
0x140079104  push    r12
0x140079106  push    r13
0x140079108  push    r14
0x14007910a  push    r15
0x14007910c  lea     rbp, [rsp-60h]
0x140079111  sub     rsp, 160h
0x140079118  mov     rax, cs:__security_cookie
0x14007911f  xor     rax, rsp
0x140079122  mov     [rbp+90h+var_40], rax
0x140079126  mov     r14, [rbp+90h+arg_20]
0x14007912d  mov     rsi, r8
0x140079130  mov     rdi, rdx
0x140079133  mov     [rsp+190h+var_160], r9d
0x140079138  lea     rcx, aAsrsystemBuild_2; "AsrSystem::_BuildMbrPartitionXmlNode"
0x14007913f  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x140079144  xor     ebx, ebx
0x140079146  mov     [rsp+190h+var_150], rbx
0x14007914b  mov     [rsp+190h+var_158], ebx
0x14007914f  test    rdi, rdi
0x140079152  jnz     short loc_1400791A1
0x140079154  lea     r9d, [rbx+57h]
0x140079158  mov     esi, r9d
0x14007915b  mov     rcx, cs:WPP_GLOBAL_Control
0x140079162  lea     rax, WPP_GLOBAL_Control
0x140079169  cmp     rcx, rax
0x14007916c  jz      loc_1400794BA
0x140079172  test    byte ptr [rcx+1Ch], 8
0x140079176  jz      loc_1400794BA
0x14007917c  lea     edx, [r9+45h]
0x140079180  lea     rax, aPxmldoc; "pXmlDoc"
0x140079187  mov     rcx, [rcx+10h]
0x14007918b  lea     r8, WPP_301009c9d2f6376782984d179fa21529_Traceguids
0x140079192  mov     [rsp+190h+var_170], rax
0x140079197  call    WPP_SF_Ds
0x14007919c  jmp     loc_1400794BA
0x1400791a1  test    rsi, rsi
0x1400791a4  jnz     short loc_1400791DD
0x1400791a6  lea     r9d, [rsi+57h]
0x1400791aa  xor     edi, edi
0x1400791ac  mov     esi, r9d
0x1400791af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400791b6  lea     rax, WPP_GLOBAL_Control
0x1400791bd  cmp     rcx, rax
0x1400791c0  jz      loc_1400794BA
0x1400791c6  test    byte ptr [rcx+1Ch], 8
0x1400791ca  jz      loc_1400794BA
0x1400791d0  lea     edx, [r9+46h]
0x1400791d4  lea     rax, aPcurrentdisk; "pCurrentDisk"
0x1400791db  jmp     short loc_140079187
0x1400791dd  test    r14, r14
0x1400791e0  jnz     short loc_14007921C
0x1400791e2  lea     r9d, [r14+57h]
0x1400791e6  xor     edi, edi
0x1400791e8  mov     esi, r9d
0x1400791eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400791f2  lea     rax, WPP_GLOBAL_Control
0x1400791f9  cmp     rcx, rax
0x1400791fc  jz      loc_1400794BA
0x140079202  test    byte ptr [rcx+1Ch], 8
0x140079206  jz      loc_1400794BA
0x14007920c  lea     edx, [r9+47h]
0x140079210  lea     rax, aPpnodeout; "ppNodeOut"
0x140079217  jmp     loc_140079187
0x14007921c  lea     r13, aMbrpartition; "MbrPartition"
0x140079223  mov     rcx, rdi; struct CXMLDocument *
0x140079226  mov     rdx, r13; unsigned __int16 *
0x140079229  lea     r8, [rsp+190h+var_150]; struct CXMLNode **
0x14007922e  call    ?XmlDocCreateNode@@YAHPEAVCXMLDocument@@PEAGPEAPEAVCXMLNode@@@Z; XmlDocCreateNode(CXMLDocument *,ushort *,CXMLNode * *)
0x140079233  test    eax, eax
0x140079235  jnz     short loc_14007929A
0x140079237  xor     edi, edi
0x140079239  call    cs:__imp_GetLastError
0x14007923f  mov     esi, eax
0x140079241  mov     rcx, cs:WPP_GLOBAL_Control
0x140079248  lea     rax, WPP_GLOBAL_Control
0x14007924f  cmp     rcx, rax
0x140079252  jz      short loc_140079290
0x140079254  test    byte ptr [rcx+1Ch], 8
0x140079258  jz      short loc_140079290
0x14007925a  call    cs:__imp_GetLastError
0x140079260  lea     rcx, aGetlasterror_1; "GetLastError()"
0x140079267  mov     [rsp+190h+var_168], r13
0x14007926c  mov     [rsp+190h+var_170], rcx
0x140079271  lea     r8, WPP_301009c9d2f6376782984d179fa21529_Traceguids
0x140079278  mov     rcx, cs:WPP_GLOBAL_Control
0x14007927f  mov     edx, 9Fh
0x140079284  mov     r9d, eax
0x140079287  mov     rcx, [rcx+10h]
0x14007928b  call    WPP_SF_DsS
0x140079290  mov     rbx, [rsp+190h+var_150]
0x140079295  jmp     loc_1400794BA
0x14007929a  mov     ecx, [rsp+190h+var_160]
0x14007929e  mov     r12, [rsi+28h]
0x1400792a2  mov     rbx, [rsp+190h+var_150]
0x1400792a7  lea     r15, [rcx+rcx*2]
0x1400792ab  mov     r8, [r12+r15*8]; unsigned __int16 *
0x1400792af  test    r8, r8
0x1400792b2  jz      short loc_140079332
0x1400792b4  lea     r9, [rsp+190h+var_158]; unsigned int *
0x1400792b9  mov     rdx, rbx; struct CXMLNode *
0x1400792bc  mov     rcx, rdi; struct CXMLDocument *
0x1400792bf  call    ?AppendVolumeSymbolicNamesIntoXmlNode@AsrSystem@@SAHPEAVCXMLDocument@@PEAVCXMLNode@@PEAGPEAK@Z; AsrSystem::AppendVolumeSymbolicNamesIntoXmlNode(CXMLDocument *,CXMLNode *,ushort *,ulong *)
0x1400792c4  test    eax, eax
0x1400792c6  jnz     short loc_14007932E
0x1400792c8  xor     edi, edi
0x1400792ca  call    cs:__imp_GetLastError
0x1400792d0  mov     esi, eax
0x1400792d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400792d9  lea     rax, WPP_GLOBAL_Control
0x1400792e0  cmp     rcx, rax
0x1400792e3  jz      loc_1400794BA
0x1400792e9  test    byte ptr [rcx+1Ch], 8
0x1400792ed  jz      loc_1400794BA
0x1400792f3  call    cs:__imp_GetLastError
0x1400792f9  mov     edx, 0A0h
0x1400792fe  lea     rcx, aGetlasterror_1; "GetLastError()"
0x140079305  mov     [rsp+190h+var_168], r13
0x14007930a  mov     [rsp+190h+var_170], rcx
0x14007930f  lea     r8, WPP_301009c9d2f6376782984d179fa21529_Traceguids
0x140079316  mov     rcx, cs:WPP_GLOBAL_Control
0x14007931d  mov     r9d, eax
0x140079320  mov     rcx, [rcx+10h]
0x140079324  call    WPP_SF_DsS
0x140079329  jmp     loc_1400794BA
0x14007932e  mov     ecx, [rsp+190h+var_160]
0x140079332  mov     eax, ecx
0x140079334  mov     rcx, [rsi+10h]
0x140079338  mov     [rsp+190h+var_118], 3
0x140079340  mov     [rbp+90h+var_100], 8
0x140079347  lea     rdx, [rax+rax*8]
0x14007934b  mov     [rbp+90h+var_E8], 7
0x140079352  shl     rdx, 4
0x140079356  mov     [rbp+90h+var_A0], 8
0x14007935d  mov     [rbp+90h+var_58], 8
0x140079364  mov     rax, [rdx+rcx+38h]
0x140079369  mov     [rsp+190h+var_138], rax
0x14007936e  mov     rax, [rdx+rcx+40h]
0x140079373  mov     [rsp+190h+var_130], rax
0x140079378  movzx   eax, word ptr [r12+r15*8+0Ch]
0x14007937e  mov     [rsp+190h+var_148], eax
0x140079382  movzx   eax, byte ptr [r12+r15*8+0Eh]
0x140079388  mov     [rsp+190h+var_140], eax
0x14007938c  mov     eax, [r12+r15*8+10h]
0x140079391  mov     [rsp+190h+var_13C], eax
0x140079395  movzx   eax, byte ptr [rdx+rcx+50h]
0x14007939a  mov     [rsp+190h+var_144], eax
0x14007939e  lea     rax, aPartitionindex; "PartitionIndex"
0x1400793a5  mov     [rsp+190h+var_120], rax
0x1400793aa  lea     rax, [rsp+190h+var_160]
0x1400793af  mov     [rbp+90h+var_110], rax
0x1400793b3  lea     rax, aPartitionflag; "PartitionFlag"
0x1400793ba  mov     [rbp+90h+var_108], rax
0x1400793be  lea     rax, [rsp+190h+var_148]
0x1400793c3  mov     [rbp+90h+var_F8], rax
0x1400793c7  lea     rax, aBootflag; "BootFlag"
0x1400793ce  mov     [rbp+90h+var_F0], rax
0x1400793d2  lea     rax, [rcx+51h]
0x1400793d6  add     rax, rdx
0x1400793d9  mov     ecx, 6
0x1400793de  mov     [rbp+90h+var_E0], rax
0x1400793e2  lea     rdx, [rsp+190h+var_120]; struct _CREATE_ATTRIBUTE_SET *
0x1400793e7  lea     rax, aPartitiontype; "PartitionType"
0x1400793ee  mov     [rbp+90h+var_D0], ecx
0x1400793f1  mov     [rbp+90h+var_D8], rax
0x1400793f5  lea     rax, [rsp+190h+var_144]
0x1400793fa  mov     [rbp+90h+var_C8], rax
0x1400793fe  lea     r8d, [rcx+3]; unsigned int
0x140079402  lea     rax, aFilesystemtype; "FileSystemType"
0x140079409  mov     [rbp+90h+var_B8], ecx
0x14007940c  mov     [rbp+90h+var_C0], rax
0x140079410  mov     rcx, rbx; struct CXMLNode *
0x140079413  lea     rax, [rsp+190h+var_140]
0x140079418  mov     [rbp+90h+var_88], r8d
0x14007941c  mov     [rbp+90h+var_B0], rax
0x140079420  lea     rax, aNumsymbolicnam; "NumSymbolicNames"
0x140079427  mov     [rbp+90h+var_A8], rax
0x14007942b  lea     rax, [rsp+190h+var_158]
0x140079430  mov     [rbp+90h+var_98], rax
0x140079434  lea     rax, aPartitionoffse; "PartitionOffset"
0x14007943b  mov     [rbp+90h+var_90], rax
0x14007943f  lea     rax, [rsp+190h+var_138]
0x140079444  mov     [rbp+90h+var_80], rax
0x140079448  lea     rax, aPartitionlengt; "PartitionLength"
0x14007944f  mov     [rbp+90h+var_78], rax
0x140079453  lea     rax, [rsp+190h+var_130]
0x140079458  mov     [rbp+90h+var_68], rax
0x14007945c  lea     rax, aIscritical; "IsCritical"
0x140079463  mov     [rbp+90h+var_60], rax
0x140079467  lea     rax, [rsp+190h+var_13C]
0x14007946c  mov     [rbp+90h+var_50], rax
0x140079470  mov     [rbp+90h+var_70], r8d
0x140079474  call    ?XmlNodeInsertAttributeSet@@YAHPEAVCXMLNode@@PEAU_CREATE_ATTRIBUTE_SET@@K@Z; XmlNodeInsertAttributeSet(CXMLNode *,_CREATE_ATTRIBUTE_SET *,ulong)
0x140079479  test    eax, eax
0x14007947b  jnz     short loc_1400794B0
0x14007947d  xor     edi, edi
0x14007947f  call    cs:__imp_GetLastError
0x140079485  mov     esi, eax
0x140079487  mov     rcx, cs:WPP_GLOBAL_Control
0x14007948e  lea     rax, WPP_GLOBAL_Control
0x140079495  cmp     rcx, rax
0x140079498  jz      short loc_1400794BA
0x14007949a  test    byte ptr [rcx+1Ch], 8
0x14007949e  jz      short loc_1400794BA
0x1400794a0  call    cs:__imp_GetLastError
0x1400794a6  mov     edx, 0A1h
0x1400794ab  jmp     loc_1400792FE
0x1400794b0  xor     esi, esi
0x1400794b2  mov     [r14], rbx
0x1400794b5  xor     ebx, ebx
0x1400794b7  lea     edi, [rsi+1]
0x1400794ba  xor     ecx, ecx; pv
0x1400794bc  call    cs:__imp_CoTaskMemFree
0x1400794c2  mov     rcx, rbx; pv
0x1400794c5  call    cs:__imp_CoTaskMemFree
0x1400794cb  lea     rcx, aAsrsystemBuild_2; "AsrSystem::_BuildMbrPartitionXmlNode"
0x1400794d2  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x1400794d7  mov     ecx, esi; dwErrCode
0x1400794d9  call    cs:__imp_SetLastError
0x1400794df  mov     eax, edi
0x1400794e1  mov     rcx, [rbp+90h+var_40]
0x1400794e5  xor     rcx, rsp; StackCookie
0x1400794e8  call    __security_check_cookie
0x1400794ed  mov     rbx, [rsp+190h+arg_0]
0x1400794f5  add     rsp, 160h
0x1400794fc  pop     r15
0x1400794fe  pop     r14
0x140079500  pop     r13
0x140079502  pop     r12
0x140079504  pop     rdi
0x140079505  pop     rsi
0x140079506  pop     rbp
0x140079507  retn
```
