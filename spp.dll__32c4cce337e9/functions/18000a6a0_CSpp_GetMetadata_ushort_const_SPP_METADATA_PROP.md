# CSpp::GetMetadata(ushort const *,_SPP_METADATA_PROP *)

- ea: `0x18000a6a0`
- end: `0x18000a90e`
- name: `?GetMetadata@CSpp@@UEAAJPEBGPEAU_SPP_METADATA_PROP@@@Z`
- size: `622`
- prototype: `int(CSpp *__hidden this, const unsigned __int16 *, struct _SPP_METADATA_PROP *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callees

- `0x18000a6a0`
- `0x180020908`
- `0x180020968`
- `0x180021cb0`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x180034afc`
- `0x180034cd8`
- `0x18003532c`
- `0x1800353c4`
- `0x180035b00`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18000a7eb`
- `KERNEL32!CreateFileW` at `0x18000a7eb`
- `KERNEL32!CloseHandle` at `0x18000a8c9`
- `KERNEL32!CloseHandle` at `0x18000a8c9`

## pseudocode

```c
__int64 __fastcall CSpp::GetMetadata(CSpp *this, const unsigned __int16 *a2, struct _SPP_METADATA_PROP *a3)
{
  __int64 v5; // rcx
  struct _SPP_METADATA_PROP *v6; // rax
  unsigned __int16 v7; // dx
  __int16 v8; // ax
  __int64 v9; // rcx
  HANDLE FileW; // rbx
  int v11; // eax
  __int128 v12; // xmm1
  __int64 v13; // xmm0_8
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-39h] BYREF
  __int128 v19; // [rsp+50h] [rbp-29h] BYREF
  __int128 v20; // [rsp+60h] [rbp-19h]
  __int64 v21; // [rsp+70h] [rbp-9h]
  int LastFailureAsHRESULT; // [rsp+78h] [rbp-1h] BYREF
  __int16 v23; // [rsp+7Ch] [rbp+3h]
  __int16 v24; // [rsp+7Eh] [rbp+5h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, a2);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "CSpp::GetMetadata", 10052, 1);
  lpFileName[1] = 0;
  v21 = 0;
  lpFileName[0] = &FileName;
  v19 = 0;
  v20 = 0;
  if ( !a3 )
  {
    LastFailureAsHRESULT = -2147024809;
    v8 = 10061;
    goto LABEL_23;
  }
  v5 = 40;
  v6 = a3;
  do
  {
    *(_BYTE *)v6 = 0;
    v6 = (struct _SPP_METADATA_PROP *)((char *)v6 + 1);
    --v5;
  }
  while ( v5 );
  LastFailureAsHRESULT = 0;
  v23 = 10061;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)lpFileName, a2);
  v8 = 10066;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_23;
  v23 = 10066;
  LastFailureAsHRESULT = CBsString::Trailing((CBsString *)lpFileName, v7);
  v8 = 10068;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_23;
  v23 = 10068;
  LastFailureAsHRESULT = CBsString::Append(
                           (CBsString *)lpFileName,
                           L"System Volume Information\\SPP",
                           L"\\",
                           L"metadata-2");
  v8 = 10070;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_23;
  v23 = 10070;
  FileW = CreateFileW(lpFileName[0], 1u, 0, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
    v8 = 10079;
LABEL_23:
    v24 = v8;
    goto LABEL_24;
  }
  LastFailureAsHRESULT = 0;
  v23 = 10079;
  v11 = DeserializeFromFile<_SPP_METADATA_PROP>(
          FileW,
          (__int64)&SPP_METADATA_PROP_Decode,
          (__int64)&stru_18003C2E0,
          &v19);
  if ( v11 == -2147023113 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        175,
        (unsigned int)&WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids,
        lpFileName[0],
        247);
    LastFailureAsHRESULT = -2130706173;
    goto LABEL_18;
  }
  LastFailureAsHRESULT = v11;
  if ( v11 < 0 )
  {
LABEL_18:
    v24 = 10087;
    goto LABEL_20;
  }
  v12 = v20;
  v23 = 10087;
  *(_OWORD *)a3 = v19;
  v13 = v21;
  *((_OWORD *)a3 + 1) = v12;
  v21 = 0;
  *((_QWORD *)a3 + 4) = v13;
  v19 = 0;
  v20 = 0;
LABEL_20:
  if ( FileW )
    CloseHandle(FileW);
LABEL_24:
  Free_SPP_METADATA_PROP((struct _SPP_METADATA_PROP *)&v19);
  v14 = LastFailureAsHRESULT;
  CBsString::_Release((unsigned __int16 **)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, v15, v16);
  return v14;
}

```

## disassembly

```asm
0x18000a6a0  push    rbp
0x18000a6a2  push    rbx
0x18000a6a3  push    rdi
0x18000a6a4  push    r14
0x18000a6a6  lea     rbp, [rsp-3Fh]
0x18000a6ab  sub     rsp, 0B8h
0x18000a6b2  mov     rdi, r8
0x18000a6b5  mov     rbx, rdx
0x18000a6b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6bf  lea     r14, WPP_GLOBAL_Control
0x18000a6c6  cmp     rcx, r14
0x18000a6c9  jz      short loc_18000A6EC
0x18000a6cb  test    dword ptr [rcx+1Ch], 20000000h
0x18000a6d2  jz      short loc_18000A6EC
0x18000a6d4  mov     rcx, [rcx+10h]
0x18000a6d8  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18000a6df  mov     edx, 0AEh
0x18000a6e4  mov     r9, rbx
0x18000a6e7  call    WPP_SF_S
0x18000a6ec  mov     r9d, 1; unsigned __int16
0x18000a6f2  lea     rdx, aCsppGetmetadat; "CSpp::GetMetadata"
0x18000a6f9  mov     r8d, 2744h; unsigned __int16
0x18000a6ff  lea     rcx, [rbp+57h+var_58]; this
0x18000a703  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000a708  xor     eax, eax
0x18000a70a  mov     [rbp+57h+var_88], 0
0x18000a712  mov     [rbp+57h+var_60], rax
0x18000a716  xorps   xmm0, xmm0
0x18000a719  lea     rax, FileName
0x18000a720  mov     [rbp+57h+lpFileName], rax
0x18000a724  movups  [rbp+57h+var_80], xmm0
0x18000a728  movups  [rbp+57h+var_70], xmm0
0x18000a72c  test    rdi, rdi
0x18000a72f  jz      loc_18000A8D1
0x18000a735  mov     ecx, 28h ; '('
0x18000a73a  mov     rax, rdi
0x18000a73d  mov     byte ptr [rax], 0
0x18000a740  inc     rax
0x18000a743  sub     rcx, 1
0x18000a747  jnz     short loc_18000A73D
0x18000a749  mov     [rbp+57h+var_58], ecx
0x18000a74c  mov     eax, 274Dh
0x18000a751  lea     rcx, [rbp+57h+lpFileName]; this
0x18000a755  mov     [rbp+57h+var_54], ax
0x18000a759  mov     rdx, rbx; unsigned __int16 *
0x18000a75c  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000a761  mov     [rbp+57h+var_58], eax
0x18000a764  test    eax, eax
0x18000a766  mov     eax, 2752h
0x18000a76b  js      loc_18000A8DD
0x18000a771  lea     rcx, [rbp+57h+lpFileName]; this
0x18000a775  mov     [rbp+57h+var_54], ax
0x18000a779  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18000a77e  mov     [rbp+57h+var_58], eax
0x18000a781  test    eax, eax
0x18000a783  mov     eax, 2754h
0x18000a788  js      loc_18000A8DD
0x18000a78e  lea     r9, aMetadata2; "metadata-2"
0x18000a795  mov     [rbp+57h+var_54], ax
0x18000a799  lea     r8, asc_18003A0A0; "\\"
0x18000a7a0  lea     rdx, aSystemVolumeIn_0; "System Volume Information\\SPP"
0x18000a7a7  lea     rcx, [rbp+57h+lpFileName]; this
0x18000a7ab  call    ?Append@CBsString@@QEAAJPEBG00@Z; CBsString::Append(ushort const *,ushort const *,ushort const *)
0x18000a7b0  mov     [rbp+57h+var_58], eax
0x18000a7b3  test    eax, eax
0x18000a7b5  mov     eax, 2756h
0x18000a7ba  js      loc_18000A8DD
0x18000a7c0  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18000a7c4  xor     r9d, r9d; lpSecurityAttributes
0x18000a7c7  mov     [rsp+0D0h+hTemplateFile], 0; hTemplateFile
0x18000a7d0  xor     r8d, r8d; dwShareMode
0x18000a7d3  mov     [rsp+0D0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000a7db  mov     [rbp+57h+var_54], ax
0x18000a7df  lea     edx, [r9+1]; dwDesiredAccess
0x18000a7e3  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000a7eb  call    cs:__imp_CreateFileW
0x18000a7f1  mov     rbx, rax
0x18000a7f4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a7f8  jnz     short loc_18000A80C
0x18000a7fa  call    GetLastFailureAsHRESULT
0x18000a7ff  mov     [rbp+57h+var_58], eax
0x18000a802  mov     eax, 275Fh
0x18000a807  jmp     loc_18000A8DD
0x18000a80c  mov     eax, 275Fh
0x18000a811  mov     [rbp+57h+var_58], 0
0x18000a818  lea     r9, [rbp+57h+var_80]
0x18000a81c  mov     [rbp+57h+var_54], ax
0x18000a820  lea     r8, stru_18003C2E0
0x18000a827  mov     rcx, rbx; hFile
0x18000a82a  lea     rdx, SPP_METADATA_PROP_Decode
0x18000a831  call    ??$DeserializeFromFile@U_SPP_METADATA_PROP@@@@YAJPEAXP6AX0PEAU_SPP_METADATA_PROP@@@ZPEBU_GUID@@1@Z; DeserializeFromFile<_SPP_METADATA_PROP>(void *,void (*)(void *,_SPP_METADATA_PROP *),_GUID const *,_SPP_METADATA_PROP *)
0x18000a836  cmp     eax, 800706F7h
0x18000a83b  jnz     short loc_18000A87C
0x18000a83d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a844  cmp     rcx, r14
0x18000a847  jz      short loc_18000A873
0x18000a849  test    dword ptr [rcx+1Ch], 4000000h
0x18000a850  jz      short loc_18000A873
0x18000a852  mov     r9, [rbp+57h+lpFileName]
0x18000a856  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18000a85d  mov     rcx, [rcx+10h]
0x18000a861  mov     edx, 0AFh
0x18000a866  mov     [rsp+0D0h+dwCreationDisposition], 800706F7h
0x18000a86e  call    WPP_SF_Sd
0x18000a873  mov     [rbp+57h+var_58], 81000103h
0x18000a87a  jmp     short loc_18000A883
0x18000a87c  mov     [rbp+57h+var_58], eax
0x18000a87f  test    eax, eax
0x18000a881  jns     short loc_18000A88E
0x18000a883  mov     eax, 2767h
0x18000a888  mov     [rbp+57h+var_52], ax
0x18000a88c  jmp     short loc_18000A8C1
0x18000a88e  movups  xmm0, [rbp+57h+var_80]
0x18000a892  mov     eax, 2767h
0x18000a897  movups  xmm1, [rbp+57h+var_70]
0x18000a89b  mov     [rbp+57h+var_54], ax
0x18000a89f  xor     eax, eax
0x18000a8a1  movups  xmmword ptr [rdi], xmm0
0x18000a8a4  movsd   xmm0, [rbp+57h+var_60]
0x18000a8a9  movups  xmmword ptr [rdi+10h], xmm1
0x18000a8ad  mov     [rbp+57h+var_60], rax
0x18000a8b1  xorps   xmm1, xmm1
0x18000a8b4  movsd   qword ptr [rdi+20h], xmm0
0x18000a8b9  movups  [rbp+57h+var_80], xmm1
0x18000a8bd  movups  [rbp+57h+var_70], xmm1
0x18000a8c1  test    rbx, rbx
0x18000a8c4  jz      short loc_18000A8E1
0x18000a8c6  mov     rcx, rbx; hObject
0x18000a8c9  call    cs:__imp_CloseHandle
0x18000a8cf  jmp     short loc_18000A8E1
0x18000a8d1  mov     [rbp+57h+var_58], 80070057h
0x18000a8d8  mov     eax, 274Dh
0x18000a8dd  mov     [rbp+57h+var_52], ax
0x18000a8e1  lea     rcx, [rbp+57h+var_80]; struct _SPP_METADATA_PROP *
0x18000a8e5  call    ?Free_SPP_METADATA_PROP@@YAXPEAU_SPP_METADATA_PROP@@@Z; Free_SPP_METADATA_PROP(_SPP_METADATA_PROP *)
0x18000a8ea  mov     ebx, [rbp+57h+var_58]
0x18000a8ed  lea     rcx, [rbp+57h+lpFileName]; this
0x18000a8f1  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000a8f6  lea     rcx, [rbp+57h+var_58]; this
0x18000a8fa  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000a8ff  mov     eax, ebx
0x18000a901  add     rsp, 0B8h
0x18000a908  pop     r14
0x18000a90a  pop     rdi
0x18000a90b  pop     rbx
0x18000a90c  pop     rbp
0x18000a90d  retn
```
