# CSpp::CreateExternalGroupDataBlob(_SPP_GROUP_PROP const *,ulong,ushort * *,ulong,ushort * *,_SPP_BLOB *)

- ea: `0x180006110`
- end: `0x18000653d`
- name: `?CreateExternalGroupDataBlob@CSpp@@UEAAJPEBU_SPP_GROUP_PROP@@KPEAPEAGK1PEAU_SPP_BLOB@@@Z`
- size: `1069`
- prototype: `__int64 __fastcall(CSpp *this, const struct _SPP_GROUP_PROP *, int, unsigned __int16 **, unsigned int, unsigned __int16 **, LPVOID *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180006110`
- `0x180008ed0`
- `0x180020710`
- `0x180020968`
- `0x1800220d8`
- `0x1800225a0`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x180035390`
- `0x180035b00`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800062d7`
- `KERNEL32!CreateFileW` at `0x1800062d7`
- `KERNEL32!CloseHandle` at `0x180006501`
- `KERNEL32!CloseHandle` at `0x180006501`
- `KERNEL32!GetFileSizeEx` at `0x180006306`
- `KERNEL32!GetFileSizeEx` at `0x180006306`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800064d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800064d5`

## string_xrefs

- `0x180006192`: `CSpp::CreateExternalGroupDataBlob`

## pseudocode

```c
__int64 __fastcall CSpp::CreateExternalGroupDataBlob(
        CSpp *this,
        const struct _SPP_GROUP_PROP *a2,
        int a3,
        unsigned __int16 **a4,
        unsigned int a5,
        unsigned __int16 **a6,
        LPVOID *a7)
{
  const WCHAR *v10; // r15
  __int64 FileW; // rbx
  __int64 v12; // r14
  LPVOID *v13; // rax
  __int64 v14; // rcx
  __int16 v15; // ax
  __int64 v16; // rcx
  LPVOID *v17; // rax
  unsigned int i; // edx
  const unsigned __int16 *v19; // r10
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // edi
  LPVOID *v23; // rax
  unsigned int v24; // edi
  __int64 v25; // rdx
  __int64 v26; // r8
  const unsigned __int16 *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v30; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v31; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v32; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v33; // [rsp+50h] [rbp-B0h]
  int LastFailureAsHRESULT; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v35; // [rsp+64h] [rbp-9Ch]
  __int16 v36; // [rsp+66h] [rbp-9Ah]
  union _LARGE_INTEGER FileSize; // [rsp+98h] [rbp-68h] BYREF
  LPVOID pv[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v39[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 **v40; // [rsp+C0h] [rbp-40h]
  __int128 v41; // [rsp+C8h] [rbp-38h]
  __int128 v42; // [rsp+D8h] [rbp-28h]
  _OWORD v43[9]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v44; // [rsp+180h] [rbp+80h]
  int v45; // [rsp+188h] [rbp+88h]
  int v46; // [rsp+18Ch] [rbp+8Ch]
  unsigned __int16 **v47; // [rsp+190h] [rbp+90h]
  unsigned int v48; // [rsp+198h] [rbp+98h]
  int v49; // [rsp+19Ch] [rbp+9Ch]
  unsigned __int16 **v50; // [rsp+1A0h] [rbp+A0h]
  _OWORD v51[9]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v52; // [rsp+240h] [rbp+140h]

  v40 = a6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 204, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSpp::CreateExternalGroupDataBlob",
    11976,
    1);
  v10 = &FileName;
  v39[0] = (unsigned __int16 *)&FileName;
  v39[1] = 0;
  FileSize.QuadPart = 0;
  LODWORD(v51[0]) = 0;
  FileW = -1;
  memset_0((char *)v51 + 4, 0, 0x94u);
  LODWORD(v43[0]) = 0;
  memset_0((char *)v43 + 4, 0, 0xB4u);
  v12 = 16;
  v13 = pv;
  v41 = 0;
  v14 = 16;
  v42 = 0;
  *(_OWORD *)pv = 0;
  do
  {
    *(_BYTE *)v13 = 0;
    v13 = (LPVOID *)((char *)v13 + 1);
    --v14;
  }
  while ( v14 );
  v15 = 11992;
  if ( !a2 || (v35 = 11992, v15 = 11993, !a7) )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_32;
  }
  v35 = 11993;
  v16 = 16;
  v17 = a7;
  LastFailureAsHRESULT = 0;
  do
  {
    *(_BYTE *)v17 = 0;
    v17 = (LPVOID *)((char *)v17 + 1);
    --v16;
  }
  while ( v16 );
  for ( i = 0; i < *((_DWORD *)a2 + 20); ++i )
  {
    v19 = *(const unsigned __int16 **)(56LL * i + *((_QWORD *)a2 + 11) + 24);
    if ( v19 )
    {
      LastFailureAsHRESULT = CBsString::SetPath(
                               (CBsString *)v39,
                               v19,
                               L"System Volume Information\\SPP",
                               L"snapshot-2",
                               0,
                               dwFlagsAndAttributes,
                               hTemplateFile,
                               v30,
                               v31,
                               v32,
                               v33);
      v15 = 12008;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_32;
      v10 = v39[0];
      v35 = 12008;
      break;
    }
  }
  FileW = (__int64)CreateFileW(v10, 1u, 1u, 0, 3u, 0, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v20);
    v15 = 12026;
    goto LABEL_32;
  }
  LastFailureAsHRESULT = 0;
  v35 = 12026;
  if ( !GetFileSizeEx((HANDLE)FileW, &FileSize) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v21);
    v15 = 12031;
    goto LABEL_32;
  }
  v35 = 12031;
  v15 = 12032;
  if ( (unsigned __int64)(FileSize.QuadPart - 1) > 0xFFFFF )
  {
    LastFailureAsHRESULT = -2130706173;
    goto LABEL_32;
  }
  LastFailureAsHRESULT = 0;
  v35 = 12032;
  v22 = DeserializeFromFile<_SPP_ONDISK_SNAPSHOT_PROP>(
          (HANDLE)FileW,
          (__int64)&SPP_ONDISK_SNAPSHOT_PROP_Decode,
          (__int64)&stru_18003C2F0,
          v51);
  if ( v22 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        205,
        (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
        (_DWORD)v10,
        v22);
    LastFailureAsHRESULT = v22;
    v15 = 12038;
    goto LABEL_32;
  }
  v44 = v52;
  v43[0] = v51[0];
  v46 = DWORD1(v41);
  v43[2] = v51[2];
  v48 = a5;
  v43[1] = v51[1];
  v49 = DWORD1(v42);
  v43[4] = v51[4];
  v50 = v40;
  v43[3] = v51[3];
  v43[6] = v51[6];
  v45 = a3;
  v43[5] = v51[5];
  v47 = a4;
  v43[8] = v51[8];
  v43[7] = v51[7];
  LastFailureAsHRESULT = SerializeToBuffer<_SPP_EXTERNAL_SNAPSHOT_PROP>(pv, &pv[1]);
  v15 = 12051;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_32:
    v36 = v15;
    goto LABEL_33;
  }
  v35 = 12051;
  a7[1] = pv[1];
  *(_DWORD *)a7 = pv[0];
  v23 = pv;
  do
  {
    *(_BYTE *)v23 = 0;
    v23 = (LPVOID *)((char *)v23 + 1);
    --v12;
  }
  while ( v12 );
LABEL_33:
  CoTaskMemFree(pv[1]);
  Free_SPP_ONDISK_SNAPSHOT_PROP((struct _SPP_ONDISK_SNAPSHOT_PROP *)v51);
  v24 = LastFailureAsHRESULT;
  CBsString::_Release(v39);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, v25, v26);
  return v24;
}

```

## disassembly

```asm
0x180006110  mov     [rsp-8+arg_0], rbx
0x180006115  push    rbp
0x180006116  push    rsi
0x180006117  push    rdi
0x180006118  push    r12
0x18000611a  push    r13
0x18000611c  push    r14
0x18000611e  push    r15
0x180006120  lea     rbp, [rsp-160h]
0x180006128  sub     rsp, 260h
0x18000612f  mov     rax, cs:__security_cookie
0x180006136  xor     rax, rsp
0x180006139  mov     [rbp+190h+var_40], rax
0x180006140  mov     rax, [rbp+190h+arg_28]
0x180006147  mov     r13, r9
0x18000614a  mov     rsi, [rbp+190h+arg_30]
0x180006151  mov     r12d, r8d
0x180006154  mov     [rbp+190h+var_1D0], rax
0x180006158  mov     rdi, rdx
0x18000615b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006162  lea     rax, WPP_GLOBAL_Control
0x180006169  cmp     rcx, rax
0x18000616c  jz      short loc_18000618C
0x18000616e  test    dword ptr [rcx+1Ch], 20000000h
0x180006175  jz      short loc_18000618C
0x180006177  mov     rcx, [rcx+10h]
0x18000617b  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180006182  mov     edx, 0CCh
0x180006187  call    WPP_SF_
0x18000618c  mov     r9d, 1; unsigned __int16
0x180006192  lea     rdx, aCsppCreateexte; "CSpp::CreateExternalGroupDataBlob"
0x180006199  mov     r8d, 2EC8h; unsigned __int16
0x18000619f  lea     rcx, [rsp+290h+var_230]; this
0x1800061a4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800061a9  xor     r14d, r14d
0x1800061ac  lea     r15, FileName
0x1800061b3  xor     edx, edx; Val
0x1800061b5  mov     [rbp+190h+var_1E0], r15
0x1800061b9  mov     r8d, 94h; Size
0x1800061bf  mov     [rbp+190h+var_1D8], r14
0x1800061c3  lea     rcx, [rbp+190h+var_E0+4]; void *
0x1800061ca  mov     qword ptr [rbp+190h+FileSize], r14
0x1800061ce  mov     dword ptr [rbp+190h+var_E0], r14d
0x1800061d5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800061d9  call    memset_0
0x1800061de  xor     edx, edx; Val
0x1800061e0  mov     dword ptr [rbp+190h+var_1A0], r14d
0x1800061e4  mov     r8d, 0B4h; Size
0x1800061ea  lea     rcx, [rbp+190h+var_1A0+4]; void *
0x1800061ee  call    memset_0
0x1800061f3  xorps   xmm0, xmm0
0x1800061f6  lea     r14d, [rbx+11h]
0x1800061fa  xorps   xmm1, xmm1
0x1800061fd  lea     rax, [rbp+190h+pv]
0x180006201  movups  [rbp+190h+var_1C8], xmm0
0x180006205  mov     ecx, r14d
0x180006208  xor     r8d, r8d
0x18000620b  movups  [rbp+190h+var_1B8], xmm1
0x18000620f  movups  xmmword ptr [rbp+190h+pv], xmm0
0x180006213  mov     [rax], r8b
0x180006216  inc     rax
0x180006219  sub     rcx, 1
0x18000621d  jnz     short loc_180006213
0x18000621f  mov     eax, 2ED8h
0x180006224  test    rdi, rdi
0x180006227  jz      loc_1800064C4
0x18000622d  mov     [rsp+290h+var_22C], ax
0x180006232  mov     eax, 2ED9h
0x180006237  test    rsi, rsi
0x18000623a  jz      loc_1800064C4
0x180006240  mov     [rsp+290h+var_22C], ax
0x180006245  mov     rcx, r14
0x180006248  mov     rax, rsi
0x18000624b  mov     [rsp+290h+var_230], r8d
0x180006250  mov     [rax], r8b
0x180006253  inc     rax
0x180006256  sub     rcx, 1
0x18000625a  jnz     short loc_180006250
0x18000625c  mov     edx, r8d
0x18000625f  cmp     edx, [rdi+50h]
0x180006262  jnb     short loc_1800062B8
0x180006264  mov     eax, edx
0x180006266  imul    rcx, rax, 38h ; '8'
0x18000626a  mov     rax, [rdi+58h]
0x18000626e  mov     r10, [rcx+rax+18h]
0x180006273  test    r10, r10
0x180006276  jnz     short loc_18000627C
0x180006278  inc     edx
0x18000627a  jmp     short loc_18000625F
0x18000627c  mov     qword ptr [rsp+290h+dwCreationDisposition], r8; unsigned __int16 *
0x180006281  lea     r9, aSnapshot2; "snapshot-2"
0x180006288  lea     r8, aSystemVolumeIn_0; "System Volume Information\\SPP"
0x18000628f  mov     rdx, r10; unsigned __int16 *
0x180006292  lea     rcx, [rbp+190h+var_1E0]; this
0x180006296  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000629b  xor     r8d, r8d
0x18000629e  mov     [rsp+290h+var_230], eax
0x1800062a2  test    eax, eax
0x1800062a4  mov     eax, 2EE8h
0x1800062a9  js      loc_1800064CC
0x1800062af  mov     r15, [rbp+190h+var_1E0]
0x1800062b3  mov     [rsp+290h+var_22C], ax
0x1800062b8  mov     [rsp+290h+hTemplateFile], r8; hTemplateFile
0x1800062bd  xor     r9d, r9d; lpSecurityAttributes
0x1800062c0  mov     dword ptr [rsp+290h+dwFlagsAndAttributes], r8d; dwFlagsAndAttributes
0x1800062c5  mov     rcx, r15; lpFileName
0x1800062c8  mov     [rsp+290h+dwCreationDisposition], 3; dwCreationDisposition
0x1800062d0  lea     edx, [r9+1]; dwDesiredAccess
0x1800062d4  mov     r8d, edx; dwShareMode
0x1800062d7  call    cs:__imp_CreateFileW
0x1800062dd  mov     rbx, rax
0x1800062e0  dec     rax
0x1800062e3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800062e7  ja      loc_1800064B4
0x1800062ed  mov     eax, 2EFAh
0x1800062f2  mov     [rsp+290h+var_230], 0
0x1800062fa  lea     rdx, [rbp+190h+FileSize]; lpFileSize
0x1800062fe  mov     [rsp+290h+var_22C], ax
0x180006303  mov     rcx, rbx; hFile
0x180006306  call    cs:__imp_GetFileSizeEx
0x18000630c  test    eax, eax
0x18000630e  jnz     short loc_180006323
0x180006310  call    GetLastFailureAsHRESULT
0x180006315  mov     [rsp+290h+var_230], eax
0x180006319  mov     eax, 2EFFh
0x18000631e  jmp     loc_1800064CC
0x180006323  mov     eax, 2EFFh
0x180006328  mov     [rsp+290h+var_22C], ax
0x18000632d  mov     rax, qword ptr [rbp+190h+FileSize]
0x180006331  dec     rax
0x180006334  cmp     rax, 0FFFFFh
0x18000633a  mov     eax, 2F00h
0x18000633f  ja      loc_1800064AA
0x180006345  lea     r9, [rbp+190h+var_E0]
0x18000634c  mov     [rsp+290h+var_230], 0
0x180006354  lea     r8, stru_18003C2F0
0x18000635b  mov     [rsp+290h+var_22C], ax
0x180006360  lea     rdx, SPP_ONDISK_SNAPSHOT_PROP_Decode
0x180006367  mov     rcx, rbx; hFile
0x18000636a  call    ??$DeserializeFromFile@U_SPP_ONDISK_SNAPSHOT_PROP@@@@YAJPEAXP6AX0PEAU_SPP_ONDISK_SNAPSHOT_PROP@@@ZPEBU_GUID@@1@Z; DeserializeFromFile<_SPP_ONDISK_SNAPSHOT_PROP>(void *,void (*)(void *,_SPP_ONDISK_SNAPSHOT_PROP *),_GUID const *,_SPP_ONDISK_SNAPSHOT_PROP *)
0x18000636f  mov     edi, eax
0x180006371  test    eax, eax
0x180006373  jns     short loc_1800063BB
0x180006375  mov     rcx, cs:WPP_GLOBAL_Control
0x18000637c  lea     rax, WPP_GLOBAL_Control
0x180006383  cmp     rcx, rax
0x180006386  jz      short loc_1800063AD
0x180006388  test    dword ptr [rcx+1Ch], 2000000h
0x18000638f  jz      short loc_1800063AD
0x180006391  mov     rcx, [rcx+10h]
0x180006395  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18000639c  mov     edx, 0CDh
0x1800063a1  mov     [rsp+290h+dwCreationDisposition], edi
0x1800063a5  mov     r9, r15
0x1800063a8  call    WPP_SF_Sd
0x1800063ad  mov     [rsp+290h+var_230], edi
0x1800063b1  mov     eax, 2F06h
0x1800063b6  jmp     loc_1800064CC
0x1800063bb  mov     rax, [rbp+190h+var_50]
0x1800063c2  lea     rdx, [rbp+190h+pv+8]
0x1800063c6  movaps  xmm0, [rbp+190h+var_E0]
0x1800063cd  lea     rcx, [rbp+190h+pv]
0x1800063d1  movaps  xmm1, [rbp+190h+var_D0]
0x1800063d8  mov     [rbp+190h+var_110], rax
0x1800063df  mov     eax, dword ptr [rbp+190h+var_1C8+4]
0x1800063e2  movups  [rbp+190h+var_1A0], xmm0
0x1800063e6  mov     [rbp+190h+var_104], eax
0x1800063ec  movaps  xmm0, [rbp+190h+var_C0]
0x1800063f3  mov     eax, [rbp+190h+arg_20]
0x1800063f9  movups  [rbp+190h+var_180], xmm0
0x1800063fd  mov     [rbp+190h+var_F8], eax
0x180006403  movaps  xmm0, [rbp+190h+var_A0]
0x18000640a  mov     eax, dword ptr [rbp+190h+var_1B8+4]
0x18000640d  movups  [rbp+190h+var_190], xmm1
0x180006411  mov     [rbp+190h+var_F4], eax
0x180006417  movaps  xmm1, [rbp+190h+var_B0]
0x18000641e  mov     rax, [rbp+190h+var_1D0]
0x180006422  movups  [rbp+190h+var_160], xmm0
0x180006426  mov     [rbp+190h+var_F0], rax
0x18000642d  lea     rax, [rbp+190h+var_1A0]
0x180006431  movaps  xmm0, [rbp+190h+var_80]
0x180006438  movups  [rbp+190h+var_170], xmm1
0x18000643c  mov     qword ptr [rsp+290h+dwCreationDisposition], rax
0x180006441  movaps  xmm1, [rbp+190h+var_90]
0x180006448  movups  [rbp+190h+var_140], xmm0
0x18000644c  mov     [rbp+190h+var_108], r12d
0x180006453  movaps  xmm0, [rbp+190h+var_60]
0x18000645a  movups  [rbp+190h+var_150], xmm1
0x18000645e  mov     [rbp+190h+var_100], r13
0x180006465  movaps  xmm1, [rbp+190h+var_70]
0x18000646c  movups  [rbp+190h+var_120], xmm0
0x180006470  movups  [rbp+190h+var_130], xmm1
0x180006474  call    ??$SerializeToBuffer@U_SPP_EXTERNAL_SNAPSHOT_PROP@@@@YAJPEAKPEAPEAEP6AXPEAXPEAU_SPP_EXTERNAL_SNAPSHOT_PROP@@@ZPEBU_GUID@@3@Z; SerializeToBuffer<_SPP_EXTERNAL_SNAPSHOT_PROP>(ulong *,uchar * *,void (*)(void *,_SPP_EXTERNAL_SNAPSHOT_PROP *),_GUID const *,_SPP_EXTERNAL_SNAPSHOT_PROP *)
0x180006479  mov     [rsp+290h+var_230], eax
0x18000647d  test    eax, eax
0x18000647f  mov     eax, 2F13h
0x180006484  js      short loc_1800064CC
0x180006486  mov     [rsp+290h+var_22C], ax
0x18000648b  mov     rax, [rbp+190h+pv+8]
0x18000648f  mov     [rsi+8], rax
0x180006493  mov     eax, dword ptr [rbp+190h+pv]
0x180006496  mov     [rsi], eax
0x180006498  lea     rax, [rbp+190h+pv]
0x18000649c  mov     byte ptr [rax], 0
0x18000649f  inc     rax
0x1800064a2  sub     r14, 1
0x1800064a6  jnz     short loc_18000649C
0x1800064a8  jmp     short loc_1800064D1
0x1800064aa  mov     [rsp+290h+var_230], 81000103h
0x1800064b2  jmp     short loc_1800064CC
0x1800064b4  call    GetLastFailureAsHRESULT
0x1800064b9  mov     [rsp+290h+var_230], eax
0x1800064bd  mov     eax, 2EFAh
0x1800064c2  jmp     short loc_1800064CC
0x1800064c4  mov     [rsp+290h+var_230], 80070057h
0x1800064cc  mov     [rsp+290h+var_22A], ax
0x1800064d1  mov     rcx, [rbp+190h+pv+8]; pv
0x1800064d5  call    cs:__imp_CoTaskMemFree
0x1800064db  lea     rcx, [rbp+190h+var_E0]; struct _SPP_ONDISK_SNAPSHOT_PROP *
0x1800064e2  call    ?Free_SPP_ONDISK_SNAPSHOT_PROP@@YAXPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z; Free_SPP_ONDISK_SNAPSHOT_PROP(_SPP_ONDISK_SNAPSHOT_PROP *)
0x1800064e7  mov     edi, [rsp+290h+var_230]
0x1800064eb  lea     rcx, [rbp+190h+var_1E0]; this
0x1800064ef  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800064f4  lea     rcx, [rbx-1]
0x1800064f8  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800064fc  ja      short loc_180006507
0x1800064fe  mov     rcx, rbx; hObject
0x180006501  call    cs:__imp_CloseHandle
0x180006507  lea     rcx, [rsp+290h+var_230]; this
0x18000650c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180006511  mov     eax, edi
0x180006513  mov     rcx, [rbp+190h+var_40]
0x18000651a  xor     rcx, rsp; StackCookie
0x18000651d  call    __security_check_cookie
0x180006522  mov     rbx, [rsp+290h+arg_0]
0x18000652a  add     rsp, 260h
0x180006531  pop     r15
0x180006533  pop     r14
0x180006535  pop     r13
0x180006537  pop     r12
0x180006539  pop     rdi
0x18000653a  pop     rsi
0x18000653b  pop     rbp
0x18000653c  retn
```
