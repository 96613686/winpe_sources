# CSpp::_WriteVolumeMetadata(ulong,_SPP_ONDISK_SNAPSHOT_PROP *,_SPP_METADATA_PROP *)

- ea: `0x18001ff4c`
- end: `0x180020440`
- name: `?_WriteVolumeMetadata@CSpp@@AEAAJKPEAU_SPP_ONDISK_SNAPSHOT_PROP@@PEAU_SPP_METADATA_PROP@@@Z`
- size: `1268`
- prototype: `__int64 __fastcall(CSpp *__hidden this, unsigned int, struct _SPP_ONDISK_SNAPSHOT_PROP *, struct _SPP_METADATA_PROP *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001f8f4`

## callees

- `0x18001a4f0`
- `0x18001b70c`
- `0x18001d97c`
- `0x18001ff4c`
- `0x180020738`
- `0x180020870`
- `0x180020968`
- `0x180020a70`
- `0x18002182c`
- `0x18002279c`
- `0x180022a74`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002ad80`
- `0x18002d6e8`
- `0x1800352cc`
- `0x180035b00`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800200a1`
- `KERNEL32!CreateFileW` at `0x1800201ae`
- `KERNEL32!CreateFileW` at `0x180020378`
- `KERNEL32!CreateFileW` at `0x1800200a1`
- `KERNEL32!CreateFileW` at `0x1800201ae`
- `KERNEL32!CreateFileW` at `0x180020378`
- `KERNEL32!CloseHandle` at `0x180020149`
- `KERNEL32!CloseHandle` at `0x18002024b`
- `KERNEL32!CloseHandle` at `0x1800203ff`
- `KERNEL32!CloseHandle` at `0x180020149`
- `KERNEL32!CloseHandle` at `0x18002024b`
- `KERNEL32!CloseHandle` at `0x1800203ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020408`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020408`

## string_xrefs

- `0x18001ffb5`: `CSpp::_WriteVolumeMetadata`

## pseudocode

```c
__int64 __fastcall CSpp::_WriteVolumeMetadata(
        CSpp *this,
        unsigned int a2,
        struct _SPP_ONDISK_SNAPSHOT_PROP *a3,
        struct _SPP_METADATA_PROP *a4)
{
  __int64 v5; // rbx
  unsigned __int64 v8; // r13
  __int16 v9; // ax
  WCHAR *v10; // r14
  CSpp *v11; // rcx
  const unsigned __int16 *v12; // r12
  int IsServerSku; // esi
  const unsigned __int16 *v14; // r8
  const unsigned __int16 *v15; // r9
  struct _SECURITY_ATTRIBUTES *v16; // rax
  LPCWSTR v17; // r15
  HANDLE FileW; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rbx
  int LastFailureAsHRESULT; // eax
  CSpp *v24; // rcx
  __int16 v25; // ax
  int SnapshotOnDiskPropCacheFilePath; // eax
  bool v27; // sf
  struct _SECURITY_ATTRIBUTES *v28; // rsi
  HANDLE v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  int v32; // eax
  unsigned __int64 *v33; // rdx
  __int64 v34; // r8
  unsigned __int64 *v35; // r9
  int v36; // eax
  int v37; // edx
  const unsigned __int16 *v38; // r8
  const unsigned __int16 *v39; // r9
  PVOID *v40; // rcx
  LPCWSTR v41; // rdi
  HANDLE v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  int v46; // eax
  unsigned int v47; // ebx
  __int64 v48; // rdx
  __int64 v49; // r8
  int v51; // [rsp+40h] [rbp-59h] BYREF
  __int16 v52; // [rsp+44h] [rbp-55h]
  __int16 v53; // [rsp+46h] [rbp-53h]
  LPCWSTR v54; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int64 v55; // [rsp+80h] [rbp-19h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+88h] [rbp-11h] BYREF
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+98h] [rbp-1h]
  unsigned __int64 v58; // [rsp+A0h] [rbp+7h] BYREF
  struct _GUID v59; // [rsp+B0h] [rbp+17h] BYREF
  int v60; // [rsp+110h] [rbp+77h]

  v5 = a2;
  v8 = 0x20000000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, a2);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v51, "CSpp::_WriteVolumeMetadata", 5239, 1);
  lpFileName[0] = &FileName;
  v9 = 5251;
  lpFileName[1] = 0;
  v10 = 0;
  v54 = 0;
  v58 = 0;
  v55 = 0;
  if ( !a3 || (v52 = 5251, v9 = 5252, !a4) )
  {
    v51 = -2147024809;
LABEL_6:
    v53 = v9;
    goto LABEL_57;
  }
  v51 = 0;
  v52 = 5252;
  v11 = *(CSpp **)(*((_QWORD *)a3 + 12) + 48 * v5 + 40);
  v12 = *(const unsigned __int16 **)v11;
  IsServerSku = CSpp::_IsServerSku(v11);
  v51 = IsServerSku;
  v9 = 5261;
  if ( IsServerSku < 0 )
    goto LABEL_6;
  v52 = 5261;
  *((_DWORD *)a3 + 22) = v5;
  v60 = CBsString::Set((CBsString *)lpFileName, v12, v14, v15, L"snapshot-2");
  v51 = v60;
  v9 = 5273;
  if ( v60 < 0 )
    goto LABEL_6;
  v52 = 5273;
  v16 = (struct _SECURITY_ATTRIBUTES *)((char *)this + 56);
  v17 = lpFileName[0];
  lpSecurityAttributes = v16;
  FileW = CreateFileW(lpFileName[0], 0x40000000u, 0, v16, 2u, 6u, 0);
  v22 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v20);
    v51 = LastFailureAsHRESULT;
    v53 = 5282;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        83,
        (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
        (unsigned int)"hFile != INVALID_HANDLE_VALUE",
        (__int64)v17,
        LastFailureAsHRESULT);
    goto LABEL_57;
  }
  v52 = 5282;
  v51 = 0;
  v51 = SerializeToFile<_SPP_ONDISK_SNAPSHOT_PROP>(FileW, v19, v21, (__int64)a3);
  v25 = 5284;
  if ( v51 < 0 )
    goto LABEL_16;
  v52 = 5284;
  if ( v22 )
  {
    CloseHandle((HANDLE)v22);
    v22 = -1;
  }
  if ( IsServerSku )
  {
    v59 = *(struct _GUID *)a3;
    SnapshotOnDiskPropCacheFilePath = CSpp::_GetSnapshotOnDiskPropCacheFilePath(
                                        v24,
                                        &v59,
                                        v12,
                                        (unsigned __int16 **)&v54);
    v10 = (WCHAR *)v54;
    v27 = SnapshotOnDiskPropCacheFilePath < 0;
    v51 = SnapshotOnDiskPropCacheFilePath;
    v25 = 5293;
    if ( v27 )
      goto LABEL_16;
    v28 = lpSecurityAttributes;
    v52 = 5293;
    v29 = CreateFileW(v54, 0x40000000u, 0, lpSecurityAttributes, 2u, 6u, 0);
    v22 = (__int64)v29;
    if ( v29 == (HANDLE)-1LL )
    {
      v24 = (CSpp *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          84,
          (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
          (_DWORD)v10,
          v60);
    }
    else
    {
      v32 = SerializeToFile<_SPP_ONDISK_SNAPSHOT_PROP>(v29, v30, v31, (__int64)a3);
      if ( v32 < 0 )
      {
        v24 = (CSpp *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            85,
            (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
            (_DWORD)v10,
            v32);
      }
      if ( v22 )
      {
        CloseHandle((HANDLE)v22);
        v22 = -1;
      }
    }
  }
  else
  {
    v28 = lpSecurityAttributes;
  }
  if ( (int)CSpp::_RegQueryMinSizeForExtraMetadataFile(v24, &v55) >= 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
    {
      v8 = v55;
    }
    else
    {
      v8 = v55;
      WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, v34, v55);
    }
  }
  v36 = SxQueryVolumeSpace(v12, v33, &v58, v35);
  if ( v36 >= 0 )
    goto LABEL_41;
  v40 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      87,
      (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
      (_DWORD)v12,
      v36);
LABEL_41:
    v40 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v58 && v58 < v8 )
  {
    if ( v40 != &WPP_GLOBAL_Control && (*((_DWORD *)v40 + 7) & 0x2000000) != 0 )
      WPP_SF_SI((unsigned int)v40[2], v37, (_DWORD)v38, (_DWORD)v12, v58);
    v51 = -2130706160;
    v25 = 5360;
    goto LABEL_16;
  }
  v51 = CBsString::Set((CBsString *)lpFileName, v12, v38, v39, L"metadata-2");
  v25 = 5367;
  if ( v51 < 0 )
  {
LABEL_16:
    v53 = v25;
    goto LABEL_55;
  }
  v41 = lpFileName[0];
  v52 = 5367;
  v42 = CreateFileW(lpFileName[0], 0x40000000u, 0, v28, 2u, 6u, 0);
  v22 = (__int64)v42;
  if ( v42 != (HANDLE)-1LL )
  {
    v52 = 5376;
    v51 = 0;
    v51 = SerializeToFile<_SPP_METADATA_PROP>(v42, v43, v45, (__int64)a4);
    v25 = 5378;
    if ( v51 >= 0 )
    {
      v52 = 5378;
LABEL_55:
      if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle((HANDLE)v22);
      goto LABEL_57;
    }
    goto LABEL_16;
  }
  v46 = GetLastFailureAsHRESULT(v44);
  v51 = v46;
  v53 = 5376;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      89,
      (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
      (unsigned int)"hFile != INVALID_HANDLE_VALUE",
      (__int64)v41,
      v46);
LABEL_57:
  CoTaskMemFree(v10);
  v47 = v51;
  CBsString::_Release((unsigned __int16 **)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v51, v48, v49);
  return v47;
}

```

## disassembly

```asm
0x18001ff4c  mov     [rsp-8+arg_0], rbx
0x18001ff51  mov     [rsp-8+arg_18], r9
0x18001ff56  push    rbp
0x18001ff57  push    rsi
0x18001ff58  push    rdi
0x18001ff59  push    r12
0x18001ff5b  push    r13
0x18001ff5d  push    r14
0x18001ff5f  push    r15
0x18001ff61  lea     rbp, [rsp-27h]
0x18001ff66  sub     rsp, 0C0h
0x18001ff6d  mov     rsi, r9
0x18001ff70  mov     ebx, edx
0x18001ff72  mov     rdi, r8
0x18001ff75  mov     r15, rcx
0x18001ff78  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff7f  lea     rax, WPP_GLOBAL_Control
0x18001ff86  mov     r13d, 20000000h
0x18001ff8c  cmp     rcx, rax
0x18001ff8f  jz      short loc_18001FFAF
0x18001ff91  test    [rcx+1Ch], r13d
0x18001ff95  jz      short loc_18001FFAF
0x18001ff97  mov     rcx, [rcx+10h]
0x18001ff9b  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001ffa2  mov     edx, 52h ; 'R'
0x18001ffa7  mov     r9d, ebx
0x18001ffaa  call    WPP_SF_D
0x18001ffaf  mov     r9d, 1; unsigned __int16
0x18001ffb5  lea     rdx, aCsppWritevolum; "CSpp::_WriteVolumeMetadata"
0x18001ffbc  mov     r8d, 1477h; unsigned __int16
0x18001ffc2  lea     rcx, [rbp+57h+var_B0]; this
0x18001ffc6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001ffcb  xor     ecx, ecx
0x18001ffcd  lea     rax, FileName
0x18001ffd4  mov     [rbp+57h+lpFileName], rax
0x18001ffd8  mov     eax, 1483h
0x18001ffdd  mov     [rbp+57h+var_60], rcx
0x18001ffe1  mov     r14d, ecx
0x18001ffe4  mov     [rbp+57h+var_78], rcx
0x18001ffe8  mov     [rbp+57h+var_50], rcx
0x18001ffec  mov     [rbp+57h+var_70], rcx
0x18001fff0  test    rdi, rdi
0x18001fff3  jnz     short loc_180020005
0x18001fff5  mov     [rbp+57h+var_B0], 80070057h
0x18001fffc  mov     [rbp+57h+var_AA], ax
0x180020000  jmp     loc_180020405
0x180020005  mov     [rbp+57h+var_AC], ax
0x180020009  mov     eax, 1484h
0x18002000e  test    rsi, rsi
0x180020011  jz      short loc_18001FFF5
0x180020013  mov     [rbp+57h+var_B0], ecx
0x180020016  lea     rcx, [rbx+rbx*2]
0x18002001a  mov     [rbp+57h+var_AC], ax
0x18002001e  add     rcx, rcx
0x180020021  mov     rax, [rdi+60h]
0x180020025  mov     rcx, [rax+rcx*8+28h]; this
0x18002002a  mov     r12, [rcx]
0x18002002d  call    ?_IsServerSku@CSpp@@AEAAJXZ; CSpp::_IsServerSku(void)
0x180020032  mov     esi, eax
0x180020034  mov     [rbp+57h+var_B0], eax
0x180020037  test    eax, eax
0x180020039  mov     eax, 148Dh
0x18002003e  js      short loc_18001FFFC
0x180020040  mov     [rbp+57h+var_AC], ax
0x180020044  lea     rcx, [rbp+57h+lpFileName]; this
0x180020048  lea     rax, aSnapshot2; "snapshot-2"
0x18002004f  mov     [rdi+58h], ebx
0x180020052  mov     rdx, r12; unsigned __int16 *
0x180020055  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax; unsigned __int16 *
0x18002005a  call    ?Set@CBsString@@QEAAJPEBG000@Z; CBsString::Set(ushort const *,ushort const *,ushort const *,ushort const *)
0x18002005f  mov     [rbp+57h+arg_10], eax
0x180020062  test    eax, eax
0x180020064  mov     [rbp+57h+var_B0], eax
0x180020067  mov     eax, 1499h
0x18002006c  js      short loc_18001FFFC
0x18002006e  mov     [rbp+57h+var_AC], ax
0x180020072  xor     r8d, r8d; dwShareMode
0x180020075  lea     rax, [r15+38h]
0x180020079  mov     [rsp+0F0h+hTemplateFile], r14; hTemplateFile
0x18002007e  mov     r15, [rbp+57h+lpFileName]
0x180020082  mov     r9, rax; lpSecurityAttributes
0x180020085  mov     rcx, r15; lpFileName
0x180020088  mov     [rsp+0F0h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x180020090  mov     edx, 40000000h; dwDesiredAccess
0x180020095  mov     [rbp+57h+lpSecurityAttributes], rax
0x180020099  mov     [rsp+0F0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800200a1  call    cs:__imp_CreateFileW
0x1800200a7  mov     rbx, rax
0x1800200aa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800200ae  jnz     short loc_18002010D
0x1800200b0  call    GetLastFailureAsHRESULT
0x1800200b5  mov     ecx, 14A2h
0x1800200ba  mov     [rbp+57h+var_B0], eax
0x1800200bd  mov     [rbp+57h+var_AA], cx
0x1800200c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200c8  lea     rdx, WPP_GLOBAL_Control
0x1800200cf  cmp     rcx, rdx
0x1800200d2  jz      loc_180020405
0x1800200d8  test    dword ptr [rcx+1Ch], 2000000h
0x1800200df  jz      loc_180020405
0x1800200e5  mov     [rsp+0F0h+dwFlagsAndAttributes], eax
0x1800200e9  lea     edx, [rbx+54h]
0x1800200ec  mov     qword ptr [rsp+0F0h+dwCreationDisposition], r15
0x1800200f1  mov     rcx, [rcx+10h]
0x1800200f5  lea     r9, aHfileInvalidHa; "hFile != INVALID_HANDLE_VALUE"
0x1800200fc  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180020103  call    WPP_SF_sSd
0x180020108  jmp     loc_180020405
0x18002010d  mov     ecx, 14A2h
0x180020112  xor     r15d, r15d
0x180020115  mov     [rbp+57h+var_AC], cx
0x180020119  mov     r9, rdi
0x18002011c  mov     rcx, rbx; hFile
0x18002011f  mov     [rbp+57h+var_B0], r15d
0x180020123  call    ??$SerializeToFile@U_SPP_ONDISK_SNAPSHOT_PROP@@@@YAJPEAXP6AX0PEAU_SPP_ONDISK_SNAPSHOT_PROP@@@ZPEBU_GUID@@1@Z; SerializeToFile<_SPP_ONDISK_SNAPSHOT_PROP>(void *,void (*)(void *,_SPP_ONDISK_SNAPSHOT_PROP *),_GUID const *,_SPP_ONDISK_SNAPSHOT_PROP *)
0x180020128  mov     [rbp+57h+var_B0], eax
0x18002012b  test    eax, eax
0x18002012d  mov     eax, 14A4h
0x180020132  jns     short loc_18002013D
0x180020134  mov     [rbp+57h+var_AA], ax
0x180020138  jmp     loc_1800203F2
0x18002013d  mov     [rbp+57h+var_AC], ax
0x180020141  test    rbx, rbx
0x180020144  jz      short loc_180020153
0x180020146  mov     rcx, rbx; hObject
0x180020149  call    cs:__imp_CloseHandle
0x18002014f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180020153  test    esi, esi
0x180020155  jz      loc_180020257
0x18002015b  movups  xmm0, xmmword ptr [rdi]
0x18002015e  lea     r9, [rbp+57h+var_78]; unsigned __int16 **
0x180020162  mov     r8, r12; unsigned __int16 *
0x180020165  lea     rdx, [rbp+57h+var_40]; struct _GUID
0x180020169  movdqu  xmmword ptr [rbp+57h+var_40.Data1], xmm0
0x18002016e  call    ?_GetSnapshotOnDiskPropCacheFilePath@CSpp@@AEAAJU_GUID@@PEBGPEAPEAG@Z; CSpp::_GetSnapshotOnDiskPropCacheFilePath(_GUID,ushort const *,ushort * *)
0x180020173  mov     r14, [rbp+57h+var_78]
0x180020177  test    eax, eax
0x180020179  mov     [rbp+57h+var_B0], eax
0x18002017c  mov     eax, 14ADh
0x180020181  js      short loc_180020134
0x180020183  mov     rsi, [rbp+57h+lpSecurityAttributes]
0x180020187  xor     r8d, r8d; dwShareMode
0x18002018a  mov     [rsp+0F0h+hTemplateFile], r15; hTemplateFile
0x18002018f  mov     r9, rsi; lpSecurityAttributes
0x180020192  mov     [rsp+0F0h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x18002019a  mov     edx, 40000000h; dwDesiredAccess
0x18002019f  mov     rcx, r14; lpFileName
0x1800201a2  mov     [rbp+57h+var_AC], ax
0x1800201a6  mov     [rsp+0F0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800201ae  call    cs:__imp_CreateFileW
0x1800201b4  mov     rbx, rax
0x1800201b7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800201bb  jnz     short loc_1800201FC
0x1800201bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201c4  lea     rdx, WPP_GLOBAL_Control
0x1800201cb  cmp     rcx, rdx
0x1800201ce  jz      loc_18002025B
0x1800201d4  test    dword ptr [rcx+1Ch], 4000000h
0x1800201db  jz      short loc_18002025B
0x1800201dd  mov     rcx, [rcx+10h]
0x1800201e1  lea     edx, [rax+55h]
0x1800201e4  mov     eax, [rbp+57h+arg_10]
0x1800201e7  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800201ee  mov     r9, r14
0x1800201f1  mov     [rsp+0F0h+dwCreationDisposition], eax
0x1800201f5  call    WPP_SF_Sd
0x1800201fa  jmp     short loc_18002025B
0x1800201fc  mov     r9, rdi
0x1800201ff  mov     rcx, rbx; hFile
0x180020202  call    ??$SerializeToFile@U_SPP_ONDISK_SNAPSHOT_PROP@@@@YAJPEAXP6AX0PEAU_SPP_ONDISK_SNAPSHOT_PROP@@@ZPEBU_GUID@@1@Z; SerializeToFile<_SPP_ONDISK_SNAPSHOT_PROP>(void *,void (*)(void *,_SPP_ONDISK_SNAPSHOT_PROP *),_GUID const *,_SPP_ONDISK_SNAPSHOT_PROP *)
0x180020207  test    eax, eax
0x180020209  jns     short loc_180020243
0x18002020b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020212  lea     rdx, WPP_GLOBAL_Control
0x180020219  cmp     rcx, rdx
0x18002021c  jz      short loc_180020243
0x18002021e  test    dword ptr [rcx+1Ch], 4000000h
0x180020225  jz      short loc_180020243
0x180020227  mov     rcx, [rcx+10h]
0x18002022b  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180020232  mov     edx, 55h ; 'U'
0x180020237  mov     [rsp+0F0h+dwCreationDisposition], eax
0x18002023b  mov     r9, r14
0x18002023e  call    WPP_SF_Sd
0x180020243  test    rbx, rbx
0x180020246  jz      short loc_18002025B
0x180020248  mov     rcx, rbx; hObject
0x18002024b  call    cs:__imp_CloseHandle
0x180020251  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180020255  jmp     short loc_18002025B
0x180020257  mov     rsi, [rbp+57h+lpSecurityAttributes]
0x18002025b  lea     rdx, [rbp+57h+var_70]; unsigned __int64 *
0x18002025f  call    ?_RegQueryMinSizeForExtraMetadataFile@CSpp@@AEAAJPEA_K@Z; CSpp::_RegQueryMinSizeForExtraMetadataFile(unsigned __int64 *)
0x180020264  lea     rdi, WPP_GLOBAL_Control
0x18002026b  test    eax, eax
0x18002026d  js      short loc_18002029F
0x18002026f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020276  cmp     rcx, rdi
0x180020279  jz      short loc_18002029B
0x18002027b  test    dword ptr [rcx+1Ch], 8000000h
0x180020282  jz      short loc_18002029B
0x180020284  mov     r13, [rbp+57h+var_70]
0x180020288  mov     edx, 56h ; 'V'
0x18002028d  mov     rcx, [rcx+10h]
0x180020291  mov     r9, r13
0x180020294  call    WPP_SF_I
0x180020299  jmp     short loc_18002029F
0x18002029b  mov     r13, [rbp+57h+var_70]
0x18002029f  lea     r8, [rbp+57h+var_50]; unsigned __int64 *
0x1800202a3  mov     rcx, r12; unsigned __int16 *
0x1800202a6  call    ?SxQueryVolumeSpace@@YAJPEBGPEA_K11@Z; SxQueryVolumeSpace(ushort const *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x1800202ab  test    eax, eax
0x1800202ad  jns     short loc_1800202E0
0x1800202af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800202b6  cmp     rcx, rdi
0x1800202b9  jz      short loc_1800202E7
0x1800202bb  test    dword ptr [rcx+1Ch], 4000000h
0x1800202c2  jz      short loc_1800202E7
0x1800202c4  mov     rcx, [rcx+10h]
0x1800202c8  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800202cf  mov     edx, 57h ; 'W'
0x1800202d4  mov     [rsp+0F0h+dwCreationDisposition], eax
0x1800202d8  mov     r9, r12
0x1800202db  call    WPP_SF_Sd
0x1800202e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800202e7  mov     rax, [rbp+57h+var_50]
0x1800202eb  test    rax, rax
0x1800202ee  jz      short loc_180020325
0x1800202f0  cmp     rax, r13
0x1800202f3  jnb     short loc_180020325
0x1800202f5  cmp     rcx, rdi
0x1800202f8  jz      short loc_180020314
0x1800202fa  test    dword ptr [rcx+1Ch], 2000000h
0x180020301  jz      short loc_180020314
0x180020303  mov     rcx, [rcx+10h]
0x180020307  mov     r9, r12
0x18002030a  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax
0x18002030f  call    WPP_SF_SI
0x180020314  mov     [rbp+57h+var_B0], 81000110h
0x18002031b  mov     eax, 14F0h
0x180020320  jmp     loc_180020134
0x180020325  lea     rax, aMetadata2; "metadata-2"
0x18002032c  mov     rdx, r12; unsigned __int16 *
0x18002032f  lea     rcx, [rbp+57h+lpFileName]; this
0x180020333  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rax; unsigned __int16 *
0x180020338  call    ?Set@CBsString@@QEAAJPEBG000@Z; CBsString::Set(ushort const *,ushort const *,ushort const *,ushort const *)
0x18002033d  mov     [rbp+57h+var_B0], eax
0x180020340  test    eax, eax
0x180020342  mov     eax, 14F7h
0x180020347  js      loc_180020134
0x18002034d  mov     rdi, [rbp+57h+lpFileName]
0x180020351  mov     r9, rsi; lpSecurityAttributes
0x180020354  mov     [rsp+0F0h+hTemplateFile], r15; hTemplateFile
0x180020359  mov     rcx, rdi; lpFileName
0x18002035c  mov     [rsp+0F0h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x180020364  xor     r8d, r8d; dwShareMode
0x180020367  mov     edx, 40000000h; dwDesiredAccess
0x18002036c  mov     [rbp+57h+var_AC], ax
0x180020370  mov     [rsp+0F0h+dwCreationDisposition], 2; dwCreationDisposition
0x180020378  call    cs:__imp_CreateFileW
0x18002037e  mov     rbx, rax
0x180020381  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020385  jnz     short loc_1800203C5
0x180020387  call    GetLastFailureAsHRESULT
0x18002038c  mov     ecx, 1500h
0x180020391  mov     [rbp+57h+var_B0], eax
0x180020394  mov     [rbp+57h+var_AA], cx
0x180020398  mov     rcx, cs:WPP_GLOBAL_Control
0x18002039f  lea     rdx, WPP_GLOBAL_Control
0x1800203a6  cmp     rcx, rdx
0x1800203a9  jz      short loc_180020405
0x1800203ab  test    dword ptr [rcx+1Ch], 2000000h
0x1800203b2  jz      short loc_180020405
0x1800203b4  mov     [rsp+0F0h+dwFlagsAndAttributes], eax
0x1800203b8  lea     edx, [rbx+5Ah]
0x1800203bb  mov     qword ptr [rsp+0F0h+dwCreationDisposition], rdi
0x1800203c0  jmp     loc_1800200F1
0x1800203c5  mov     r9, [rbp+57h+arg_18]
0x1800203c9  mov     ecx, 1500h
0x1800203ce  mov     [rbp+57h+var_AC], cx
0x1800203d2  mov     rcx, rax; hFile
0x1800203d5  mov     [rbp+57h+var_B0], r15d
0x1800203d9  call    ??$SerializeToFile@U_SPP_METADATA_PROP@@@@YAJPEAXP6AX0PEAU_SPP_METADATA_PROP@@@ZPEBU_GUID@@1@Z; SerializeToFile<_SPP_METADATA_PROP>(void *,void (*)(void *,_SPP_METADATA_PROP *),_GUID const *,_SPP_METADATA_PROP *)
0x1800203de  mov     [rbp+57h+var_B0], eax
0x1800203e1  test    eax, eax
0x1800203e3  mov     eax, 1502h
0x1800203e8  js      loc_180020134
0x1800203ee  mov     [rbp+57h+var_AC], ax
0x1800203f2  lea     rax, [rbx-1]
0x1800203f6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800203fa  ja      short loc_180020405
0x1800203fc  mov     rcx, rbx; hObject
0x1800203ff  call    cs:__imp_CloseHandle
0x180020405  mov     rcx, r14; pv
0x180020408  call    cs:__imp_CoTaskMemFree
0x18002040e  mov     ebx, [rbp+57h+var_B0]
0x180020411  lea     rcx, [rbp+57h+lpFileName]; this
0x180020415  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18002041a  lea     rcx, [rbp+57h+var_B0]; this
0x18002041e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
  ... truncated ...
```
