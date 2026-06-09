# CSpp::CleanupSnapshotsWithCorruptMetadata(void)

- ea: `0x180005360`
- end: `0x1800057d2`
- name: `?CleanupSnapshotsWithCorruptMetadata@CSpp@@UEAAJXZ`
- size: `1138`
- prototype: `__int64 __fastcall(CSpp *__hidden this)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800021f8`
- `0x18000232c`
- `0x180005360`
- `0x180007344`
- `0x180008ed0`
- `0x18000907c`
- `0x18000e208`
- `0x18000e248`
- `0x18001a830`
- `0x18001b70c`
- `0x180020710`
- `0x180020968`
- `0x1800211e0`
- `0x1800220d8`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002a778`
- `0x180035390`
- `0x180035b00`
- `0x180035b9a`
- `0x180035bd0`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800055d1`
- `KERNEL32!GetLastError` at `0x1800055d1`
- `KERNEL32!CreateFileW` at `0x1800055ad`
- `KERNEL32!CreateFileW` at `0x1800055ad`
- `KERNEL32!CloseHandle` at `0x180005711`
- `KERNEL32!CloseHandle` at `0x18000577a`
- `KERNEL32!CloseHandle` at `0x180005711`
- `KERNEL32!CloseHandle` at `0x18000577a`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x180005471`
- `VSSAPI!CreateVssBackupComponentsInternal` at `0x180005471`

## pseudocode

```c
__int64 __fastcall CSpp::CleanupSnapshotsWithCorruptMetadata(CSpp *this)
{
  struct CSxVolumeInfoArray *v2; // rdi
  CSpp *v3; // rcx
  int IsServerSku; // ecx
  __int16 v5; // ax
  int v6; // eax
  bool v7; // sf
  __int64 v8; // rdx
  __int64 FileW; // rsi
  unsigned int i; // r14d
  __int16 v11; // r10
  struct CSxVolumeInfoArray *v12; // rbx
  const unsigned __int16 *v13; // rdx
  char LastError; // al
  int v15; // r15d
  __int64 v16; // r8
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // r8
  CSppStringMapEntry *v20; // rcx
  unsigned int v21; // ebx
  __int64 v22; // rdx
  __int64 v23; // r8
  const unsigned __int16 *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v27; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v28; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v29; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v30; // [rsp+50h] [rbp-B0h]
  struct CSxVolumeInfoArray *v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v32; // [rsp+68h] [rbp-98h] BYREF
  int SnapshotVolumeList; // [rsp+70h] [rbp-90h] BYREF
  __int16 v34; // [rsp+74h] [rbp-8Ch]
  __int16 v35; // [rsp+76h] [rbp-8Ah]
  LPCWSTR lpFileName[3]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v37; // [rsp+C0h] [rbp-40h] BYREF
  GUID v38; // [rsp+D0h] [rbp-30h] BYREF
  int v39; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v40[156]; // [rsp+E4h] [rbp-1Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&SnapshotVolumeList,
    "CSpp::CleanupSnapshotsWithCorruptMetadata",
    12511,
    1);
  v2 = 0;
  v31 = 0;
  ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(&v32);
  IsServerSku = CSpp::_IsServerSku(v3);
  SnapshotVolumeList = IsServerSku;
  v5 = 12517;
  if ( IsServerSku < 0 )
    goto LABEL_5;
  v34 = 12517;
  if ( IsServerSku )
  {
    v6 = CSxVolumeInfoArray::CreateInstance(&v31);
    v2 = v31;
    v7 = v6 < 0;
    SnapshotVolumeList = v6;
    v5 = 12524;
    if ( v7 )
      goto LABEL_5;
    v34 = 12524;
    SnapshotVolumeList = CSpp::_GetSnapshotVolumeList(this, v31);
    v5 = 12525;
    if ( SnapshotVolumeList < 0 )
      goto LABEL_5;
    v34 = 12525;
    SnapshotVolumeList = CreateVssBackupComponentsInternal(&v32, v8);
    v5 = 12527;
    if ( SnapshotVolumeList < 0
      || (v34 = 12527,
          SnapshotVolumeList = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v32 + 40))(v32, 0),
          v5 = 12528,
          SnapshotVolumeList < 0)
      || (v34 = 12528,
          SnapshotVolumeList = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v32 + 280))(v32, 13),
          v5 = 12531,
          SnapshotVolumeList < 0) )
    {
LABEL_5:
      v35 = v5;
      goto LABEL_43;
    }
    FileW = -1;
    v34 = 12531;
    for ( i = 0; i < *((_DWORD *)v2 + 2); ++i )
    {
      v31 = 0;
      SnapshotVolumeList = CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(v2, i, &v31);
      if ( SnapshotVolumeList < 0 )
      {
        v20 = v31;
        v35 = v11;
        if ( !v31 )
          break;
        goto LABEL_40;
      }
      v12 = v31;
      v34 = v11;
      if ( !(unsigned int)SxIsBootVolume(*((const unsigned __int16 **)v31 + 1)) )
      {
        v13 = (const unsigned __int16 *)*((_QWORD *)v12 + 3);
        lpFileName[0] = &FileName;
        lpFileName[1] = 0;
        SnapshotVolumeList = CBsString::SetPath(
                               (CBsString *)lpFileName,
                               v13,
                               L"System Volume Information\\SPP",
                               L"snapshot-2",
                               0,
                               dwFlagsAndAttributes,
                               hTemplateFile,
                               v27,
                               v28,
                               v29,
                               v30);
        if ( SnapshotVolumeList < 0 )
        {
          v35 = 12544;
          CBsString::_Release((unsigned __int16 **)lpFileName);
          if ( !v12 )
            break;
          v20 = v12;
LABEL_40:
          CSppStringMapEntry::Release(v20);
          break;
        }
        v34 = 12544;
        FileW = (__int64)CreateFileW(lpFileName[0], 1u, 1u, 0, 3u, 0, 0);
        if ( FileW == -1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
          {
            LastError = GetLastError();
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              215,
              (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
              lpFileName[0],
              LastError);
          }
        }
        else
        {
          v39 = 0;
          memset_0(v40, 0, 0x94u);
          v15 = DeserializeFromFile<_SPP_ONDISK_SNAPSHOT_PROP>(
                  (HANDLE)FileW,
                  (__int64)&SPP_ONDISK_SNAPSHOT_PROP_Decode,
                  (__int64)&stru_18003C2F0,
                  &v39);
          Free_SPP_ONDISK_SNAPSHOT_PROP((struct _SPP_ONDISK_SNAPSHOT_PROP *)&v39);
          if ( v15 < 0 )
          {
            LODWORD(v31) = 0;
            v38 = GUID_NULL;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
              WPP_SF__guid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 216, v16, (char *)v12 + 56, v15);
            dwFlagsAndAttributes = (const unsigned __int16 *)&v38;
            v17 = *v32;
            v37 = *(_OWORD *)((char *)v12 + 56);
            v18 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64))(v17 + 312))(v32, &v37, 3);
            if ( v18 < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
            {
              WPP_SF__guid_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, v19, (char *)v12 + 56, v18);
            }
          }
          if ( FileW )
          {
            CloseHandle((HANDLE)FileW);
            FileW = -1;
          }
        }
        CBsString::_Release((unsigned __int16 **)lpFileName);
      }
      if ( v12 )
        CSppStringMapEntry::Release(v12);
    }
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle((HANDLE)FileW);
  }
  else
  {
    SnapshotVolumeList = 0;
    v34 = 12521;
  }
LABEL_43:
  v21 = SnapshotVolumeList;
  ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>();
  if ( v2 )
    CSnapshotEntryArray::Release(v2);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&SnapshotVolumeList, v22, v23);
  return v21;
}

```

## disassembly

```asm
0x180005360  mov     [rsp-8+arg_8], rbx
0x180005365  mov     [rsp-8+arg_10], rsi
0x18000536a  push    rbp
0x18000536b  push    rdi
0x18000536c  push    r13
0x18000536e  push    r14
0x180005370  push    r15
0x180005372  lea     rbp, [rsp-90h]
0x18000537a  sub     rsp, 190h
0x180005381  mov     rax, cs:__security_cookie
0x180005388  xor     rax, rsp
0x18000538b  mov     [rbp+0B0h+var_30], rax
0x180005392  mov     rbx, rcx
0x180005395  mov     rcx, cs:WPP_GLOBAL_Control
0x18000539c  lea     r13, WPP_GLOBAL_Control
0x1800053a3  cmp     rcx, r13
0x1800053a6  jz      short loc_1800053C6
0x1800053a8  test    dword ptr [rcx+1Ch], 20000000h
0x1800053af  jz      short loc_1800053C6
0x1800053b1  mov     rcx, [rcx+10h]
0x1800053b5  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800053bc  mov     edx, 0D6h
0x1800053c1  call    WPP_SF_
0x1800053c6  mov     r9d, 1; unsigned __int16
0x1800053cc  lea     rdx, aCsppCleanupsna_0; "CSpp::CleanupSnapshotsWithCorruptMetada"...
0x1800053d3  mov     r8d, 30DFh; unsigned __int16
0x1800053d9  lea     rcx, [rsp+1B0h+var_140]; this
0x1800053de  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800053e3  xor     edi, edi
0x1800053e5  lea     rcx, [rsp+1B0h+var_148]
0x1800053ea  mov     [rsp+1B0h+var_150], rdi
0x1800053ef  call    ??0?$CComPtr@VIVssBackupComponents@@@ATL@@QEAA@H@Z; ATL::CComPtr<IVssBackupComponents>::CComPtr<IVssBackupComponents>(int)
0x1800053f4  call    ?_IsServerSku@CSpp@@AEAAJXZ; CSpp::_IsServerSku(void)
0x1800053f9  mov     ecx, eax
0x1800053fb  mov     [rsp+1B0h+var_140], eax
0x1800053ff  test    eax, eax
0x180005401  mov     eax, 30E5h
0x180005406  jns     short loc_180005412
0x180005408  mov     [rsp+1B0h+var_13A], ax
0x18000540d  jmp     loc_180005780
0x180005412  mov     [rsp+1B0h+var_13C], ax
0x180005417  test    ecx, ecx
0x180005419  jnz     short loc_18000542E
0x18000541b  mov     eax, 30E9h
0x180005420  mov     [rsp+1B0h+var_140], edi
0x180005424  mov     [rsp+1B0h+var_13C], ax
0x180005429  jmp     loc_180005780
0x18000542e  lea     rcx, [rsp+1B0h+var_150]; struct CSxVolumeInfoArray **
0x180005433  call    ?CreateInstance@CSxVolumeInfoArray@@SAJPEAPEAV1@@Z; CSxVolumeInfoArray::CreateInstance(CSxVolumeInfoArray * *)
0x180005438  mov     rdi, [rsp+1B0h+var_150]
0x18000543d  test    eax, eax
0x18000543f  mov     [rsp+1B0h+var_140], eax
0x180005443  mov     eax, 30ECh
0x180005448  js      short loc_180005408
0x18000544a  mov     rdx, rdi; struct CSnapshotEntryArray *
0x18000544d  mov     [rsp+1B0h+var_13C], ax
0x180005452  mov     rcx, rbx; this
0x180005455  call    ?_GetSnapshotVolumeList@CSpp@@AEAAJPEAVCSnapshotEntryArray@@@Z; CSpp::_GetSnapshotVolumeList(CSnapshotEntryArray *)
0x18000545a  mov     [rsp+1B0h+var_140], eax
0x18000545e  test    eax, eax
0x180005460  mov     eax, 30EDh
0x180005465  js      short loc_180005408
0x180005467  lea     rcx, [rsp+1B0h+var_148]
0x18000546c  mov     [rsp+1B0h+var_13C], ax
0x180005471  call    cs:__imp_CreateVssBackupComponentsInternal
0x180005477  mov     [rsp+1B0h+var_140], eax
0x18000547b  test    eax, eax
0x18000547d  mov     eax, 30EFh
0x180005482  js      short loc_180005408
0x180005484  mov     rcx, [rsp+1B0h+var_148]
0x180005489  xor     edx, edx
0x18000548b  mov     [rsp+1B0h+var_13C], ax
0x180005490  mov     rax, [rcx]
0x180005493  mov     rax, [rax+28h]
0x180005497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000549c  mov     [rsp+1B0h+var_140], eax
0x1800054a0  test    eax, eax
0x1800054a2  mov     eax, 30F0h
0x1800054a7  js      loc_180005408
0x1800054ad  mov     rcx, [rsp+1B0h+var_148]
0x1800054b2  mov     edx, 0Dh
0x1800054b7  mov     [rsp+1B0h+var_13C], ax
0x1800054bc  mov     rax, [rcx]
0x1800054bf  mov     rax, [rax+118h]
0x1800054c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054cb  mov     [rsp+1B0h+var_140], eax
0x1800054cf  test    eax, eax
0x1800054d1  mov     eax, 30F3h
0x1800054d6  js      loc_180005408
0x1800054dc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800054e0  mov     [rsp+1B0h+var_13C], ax
0x1800054e5  xor     r14d, r14d
0x1800054e8  lea     r15d, [rax+0Dh]
0x1800054ec  mov     r10d, 30F8h
0x1800054f2  cmp     r14d, [rdi+8]
0x1800054f6  jnb     loc_18000576D
0x1800054fc  lea     r8, [rsp+1B0h+var_150]
0x180005501  mov     [rsp+1B0h+var_150], 0
0x18000550a  mov     edx, r14d
0x18000550d  mov     rcx, rdi
0x180005510  call    ?Get@?$CSxRefArray@VCWriterEntryArray@@VCWriterEntry@@@@QEAAJKPEAPEAVCWriterEntry@@@Z; CSxRefArray<CWriterEntryArray,CWriterEntry>::Get(ulong,CWriterEntry * *)
0x180005515  mov     [rsp+1B0h+var_140], eax
0x180005519  test    eax, eax
0x18000551b  js      loc_180005758
0x180005521  mov     rbx, [rsp+1B0h+var_150]
0x180005526  mov     [rsp+1B0h+var_13C], r10w
0x18000552c  mov     rcx, [rbx+8]; unsigned __int16 *
0x180005530  call    ?SxIsBootVolume@@YAJPEBG@Z; SxIsBootVolume(ushort const *)
0x180005535  test    eax, eax
0x180005537  jnz     loc_18000572A
0x18000553d  mov     rdx, [rbx+18h]; unsigned __int16 *
0x180005541  lea     rax, FileName
0x180005548  lea     r9, aSnapshot2; "snapshot-2"
0x18000554f  mov     [rbp+0B0h+lpFileName], rax
0x180005553  lea     r8, aSystemVolumeIn_0; "System Volume Information\\SPP"
0x18000555a  mov     [rbp+0B0h+var_100], 0
0x180005562  lea     rcx, [rbp+0B0h+lpFileName]; this
0x180005566  mov     qword ptr [rsp+1B0h+dwCreationDisposition], 0; unsigned __int16 *
0x18000556f  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180005574  mov     [rsp+1B0h+var_140], eax
0x180005578  test    eax, eax
0x18000557a  js      loc_18000573F
0x180005580  mov     rcx, [rbp+0B0h+lpFileName]; lpFileName
0x180005584  xor     r9d, r9d; lpSecurityAttributes
0x180005587  mov     [rsp+1B0h+hTemplateFile], 0; hTemplateFile
0x180005590  mov     [rsp+1B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180005598  mov     [rsp+1B0h+var_13C], r15w
0x18000559e  lea     edx, [r9+1]; dwDesiredAccess
0x1800055a2  mov     [rsp+1B0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800055aa  mov     r8d, edx; dwShareMode
0x1800055ad  call    cs:__imp_CreateFileW
0x1800055b3  mov     rsi, rax
0x1800055b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800055ba  jnz     short loc_180005615
0x1800055bc  mov     rax, cs:WPP_GLOBAL_Control
0x1800055c3  cmp     rax, r13
0x1800055c6  jz      short loc_180005607
0x1800055c8  test    dword ptr [rax+1Ch], 4000000h
0x1800055cf  jz      short loc_180005607
0x1800055d1  call    cs:__imp_GetLastError
0x1800055d7  test    eax, eax
0x1800055d9  jle     short loc_1800055E3
0x1800055db  movzx   eax, ax
0x1800055de  or      eax, 80070000h
0x1800055e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055ea  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800055f1  mov     r9, [rbp+0B0h+lpFileName]
0x1800055f5  mov     edx, 0D7h
0x1800055fa  mov     [rsp+1B0h+dwCreationDisposition], eax
0x1800055fe  mov     rcx, [rcx+10h]
0x180005602  call    WPP_SF_Sd
0x180005607  lea     rcx, [rbp+0B0h+lpFileName]; this
0x18000560b  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180005610  jmp     loc_18000572A
0x180005615  xor     edx, edx; Val
0x180005617  mov     [rbp+0B0h+var_D0], 0
0x18000561e  mov     r8d, 94h; Size
0x180005624  lea     rcx, [rbp+0B0h+var_CC]; void *
0x180005628  call    memset_0
0x18000562d  lea     r9, [rbp+0B0h+var_D0]
0x180005631  mov     rcx, rsi; hFile
0x180005634  lea     r8, stru_18003C2F0
0x18000563b  lea     rdx, SPP_ONDISK_SNAPSHOT_PROP_Decode
0x180005642  call    ??$DeserializeFromFile@U_SPP_ONDISK_SNAPSHOT_PROP@@@@YAJPEAXP6AX0PEAU_SPP_ONDISK_SNAPSHOT_PROP@@@ZPEBU_GUID@@1@Z; DeserializeFromFile<_SPP_ONDISK_SNAPSHOT_PROP>(void *,void (*)(void *,_SPP_ONDISK_SNAPSHOT_PROP *),_GUID const *,_SPP_ONDISK_SNAPSHOT_PROP *)
0x180005647  lea     rcx, [rbp+0B0h+var_D0]; struct _SPP_ONDISK_SNAPSHOT_PROP *
0x18000564b  mov     r15d, eax
0x18000564e  call    ?Free_SPP_ONDISK_SNAPSHOT_PROP@@YAXPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z; Free_SPP_ONDISK_SNAPSHOT_PROP(_SPP_ONDISK_SNAPSHOT_PROP *)
0x180005653  test    r15d, r15d
0x180005656  jns     loc_180005709
0x18000565c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180005663  mov     dword ptr [rsp+1B0h+var_150], 0
0x18000566b  movdqu  [rbp+0B0h+var_E0], xmm0
0x180005670  mov     rcx, cs:WPP_GLOBAL_Control
0x180005677  cmp     rcx, r13
0x18000567a  jz      short loc_18000569C
0x18000567c  test    dword ptr [rcx+1Ch], 8000000h
0x180005683  jz      short loc_18000569C
0x180005685  mov     rcx, [rcx+10h]
0x180005689  lea     r9, [rbx+38h]
0x18000568d  mov     edx, 0D8h
0x180005692  mov     [rsp+1B0h+dwCreationDisposition], r15d
0x180005697  call    WPP_SF__guid_D
0x18000569c  mov     rcx, [rsp+1B0h+var_148]
0x1800056a1  lea     rdx, [rbp+0B0h+var_E0]
0x1800056a5  movups  xmm0, xmmword ptr [rbx+38h]
0x1800056a9  mov     qword ptr [rsp+1B0h+dwFlagsAndAttributes], rdx
0x1800056ae  mov     r9d, 1
0x1800056b4  lea     rdx, [rsp+1B0h+var_150]
0x1800056b9  mov     rax, [rcx]
0x1800056bc  mov     qword ptr [rsp+1B0h+dwCreationDisposition], rdx
0x1800056c1  lea     rdx, [rbp+0B0h+var_F0]
0x1800056c5  lea     r8d, [r9+2]
0x1800056c9  movdqu  [rbp+0B0h+var_F0], xmm0
0x1800056ce  mov     rax, [rax+138h]
0x1800056d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056da  test    eax, eax
0x1800056dc  jns     short loc_180005709
0x1800056de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056e5  cmp     rcx, r13
0x1800056e8  jz      short loc_180005709
0x1800056ea  test    dword ptr [rcx+1Ch], 8000000h
0x1800056f1  jz      short loc_180005709
0x1800056f3  mov     rcx, [rcx+10h]
0x1800056f7  lea     r9, [rbx+38h]
0x1800056fb  mov     edx, 0D9h
0x180005700  mov     [rsp+1B0h+dwCreationDisposition], eax
0x180005704  call    WPP_SF__guid_D
0x180005709  test    rsi, rsi
0x18000570c  jz      short loc_18000571B
0x18000570e  mov     rcx, rsi; hObject
0x180005711  call    cs:__imp_CloseHandle
0x180005717  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000571b  lea     rcx, [rbp+0B0h+lpFileName]; this
0x18000571f  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180005724  mov     r15d, 3100h
0x18000572a  test    rbx, rbx
0x18000572d  jz      short loc_180005737
0x18000572f  mov     rcx, rbx; this
0x180005732  call    ?Release@CSppStringMapEntry@@QEAAKXZ; CSppStringMapEntry::Release(void)
0x180005737  inc     r14d
0x18000573a  jmp     loc_1800054EC
0x18000573f  lea     rcx, [rbp+0B0h+lpFileName]; this
0x180005743  mov     [rsp+1B0h+var_13A], r15w
0x180005749  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000574e  test    rbx, rbx
0x180005751  jz      short loc_18000576D
0x180005753  mov     rcx, rbx
0x180005756  jmp     short loc_180005768
0x180005758  mov     rcx, [rsp+1B0h+var_150]; this
0x18000575d  mov     [rsp+1B0h+var_13A], r10w
0x180005763  test    rcx, rcx
0x180005766  jz      short loc_18000576D
0x180005768  call    ?Release@CSppStringMapEntry@@QEAAKXZ; CSppStringMapEntry::Release(void)
0x18000576d  lea     rax, [rsi-1]
0x180005771  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005775  ja      short loc_180005780
0x180005777  mov     rcx, rsi; hObject
0x18000577a  call    cs:__imp_CloseHandle
0x180005780  mov     ebx, [rsp+1B0h+var_140]
0x180005784  lea     rcx, [rsp+1B0h+var_148]
0x180005789  call    ??1?$CComPtr@VIVssExamineWriterMetadata@@@ATL@@QEAA@XZ; ATL::CComPtr<IVssExamineWriterMetadata>::~CComPtr<IVssExamineWriterMetadata>(void)
0x18000578e  test    rdi, rdi
0x180005791  jz      short loc_18000579B
0x180005793  mov     rcx, rdi; this
0x180005796  call    ?Release@CSnapshotEntryArray@@QEAAKXZ; CSnapshotEntryArray::Release(void)
0x18000579b  lea     rcx, [rsp+1B0h+var_140]; this
0x1800057a0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800057a5  mov     eax, ebx
0x1800057a7  mov     rcx, [rbp+0B0h+var_30]
0x1800057ae  xor     rcx, rsp; StackCookie
0x1800057b1  call    __security_check_cookie
0x1800057b6  lea     r11, [rsp+1B0h+var_20]
0x1800057be  mov     rbx, [r11+38h]
0x1800057c2  mov     rsi, [r11+40h]
0x1800057c6  mov     rsp, r11
0x1800057c9  pop     r15
0x1800057cb  pop     r14
0x1800057cd  pop     r13
0x1800057cf  pop     rdi
0x1800057d0  pop     rbp
0x1800057d1  retn
```
