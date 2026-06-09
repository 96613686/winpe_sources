# PrepareRdvFolder(ushort const *,ushort const *)

- ea: `0x180036ae0`
- end: `0x180036dcc`
- name: `?PrepareRdvFolder@@YAJPEBG0@Z`
- size: `748`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180018650`

## callees

- `0x180003f30`
- `0x180004db0`
- `0x1800136ac`
- `0x180019b38`
- `0x180035db4`
- `0x180035fdc`
- `0x1800365a4`
- `0x180036ae0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036c6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036cb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036c6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036cb0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180036ca6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180036ca6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180036c64`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180036c64`

## string_xrefs

- `0x180036ccc`: `CreateDirectory failed: 0x%x in %s`
- `0x180036c8a`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed: 0x%x in %s`
- `0x180036c38`: `DeleteFolder failed: 0x%x in %s`
- `0x180036d68`: `CopyFolder failed: 0x%x in %s`
- `0x180036b5f`: `szVhdVolumeRootPath`
- `0x180036b8d`: `szVmRootPath`
- `0x180036baf`: `Failed to build VHD Folder Root path failed: 0x%x in %s`
- `0x180036c15`: `rdvFolderOnVhdPath.BuildPath failed: 0x%x in %s`
- `0x180036cf1`: `rdvFolderOnHostPath.BuildPath failed: 0x%x in %s`
- `0x180036d2e`: `RDV: SessEnvRpc found rdv folder on host (%ws), copy it to vhd. rdvFolderOnVhdPath: %ws,rdvFolderOnHostPath: %ws.`
- `0x180036d88`: `DeleteFolder rdvFolderOnHostPath failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall PrepareRdvFolder(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  const char *v3; // r8
  signed int v4; // ebx
  int v5; // eax
  const char *v6; // rdx
  const unsigned __int16 *v7; // rax
  __int64 v8; // rax
  const unsigned __int16 *v9; // rax
  const unsigned __int16 *v10; // rax
  signed int LastError; // eax
  const WCHAR *v12; // rax
  signed int v13; // eax
  const unsigned __int16 *v14; // rax
  __int64 v15; // rax
  __int64 v16; // r10
  const unsigned __int16 *v17; // rax
  const unsigned __int16 *v18; // r10
  const unsigned __int16 *v19; // rax
  void **v21; // [rsp+20h] [rbp-59h] BYREF
  __int128 v22; // [rsp+28h] [rbp-51h]
  __int64 v23; // [rsp+38h] [rbp-41h]
  __int64 v24; // [rsp+40h] [rbp-39h]
  void **v25; // [rsp+48h] [rbp-31h] BYREF
  __int128 v26; // [rsp+50h] [rbp-29h]
  __int64 v27; // [rsp+60h] [rbp-19h]
  __int64 v28; // [rsp+68h] [rbp-11h]
  void **v29; // [rsp+70h] [rbp-9h] BYREF
  __int128 v30; // [rsp+78h] [rbp-1h]
  __int64 v31; // [rsp+88h] [rbp+Fh]
  __int64 v32; // [rsp+90h] [rbp+17h]
  struct _SECURITY_ATTRIBUTES SecurityDescriptor[2]; // [rsp+98h] [rbp+1Fh] BYREF

  *(_QWORD *)((char *)&v30 + 4) = 128;
  v31 = 0;
  v29 = &CPathString::`vftable';
  v25 = &CPathString::`vftable';
  v21 = &CPathString::`vftable';
  HIDWORD(v30) = 0;
  LODWORD(v32) = 0x8000000;
  LODWORD(v30) = 0;
  *(_QWORD *)((char *)&v26 + 4) = 128;
  v27 = 0;
  HIDWORD(v26) = 0;
  LODWORD(v28) = 0x8000000;
  LODWORD(v26) = 0;
  *(_QWORD *)((char *)&v22 + 4) = 128;
  v23 = 0;
  HIDWORD(v22) = 0;
  LODWORD(v24) = 0x8000000;
  LODWORD(v22) = 0;
  memset(SecurityDescriptor, 0, 24);
  if ( a1 )
  {
    if ( a2 )
    {
      v5 = CPathString::BuildPath((CPathString *)&v29, a1, L"Windows");
      v4 = v5;
      if ( v5 >= 0 )
      {
        v7 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v29);
        if ( !(unsigned int)FolderExists(v7) )
        {
          v4 = -2147024894;
          v8 = CBaseStringT<unsigned short>::PContents(&v29);
          _DbgPrintMessage(4, "RDV Folder Root [%ws] not found", v8);
          goto LABEL_32;
        }
        v9 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v29);
        v5 = CPathString::BuildPath((CPathString *)&v21, v9, L"rdvdata");
        v4 = v5;
        if ( v5 >= 0 )
        {
          v10 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v21);
          v5 = DeleteFolder(v10);
          v4 = v5;
          if ( v5 >= 0 )
          {
            SecurityDescriptor[0].nLength = 24;
            SecurityDescriptor[0].bInheritHandle = 0;
            SecurityDescriptor[0].lpSecurityDescriptor = 0;
            if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
                    L"D:(A;OICI;FAGA;;;SY)",
                    1u,
                    &SecurityDescriptor[0].lpSecurityDescriptor,
                    0) )
            {
              LastError = GetLastError();
              v4 = LastError;
              if ( LastError > 0 )
                v4 = (unsigned __int16)LastError | 0x80070000;
              if ( v4 < 0 )
              {
                _DbgPrintMessage(
                  8,
                  "ConvertStringSecurityDescriptorToSecurityDescriptor failed: 0x%x in %s",
                  (unsigned int)v4,
                  "PrepareRdvFolder");
                goto LABEL_32;
              }
            }
            v12 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v21);
            if ( !CreateDirectoryW(v12, SecurityDescriptor) )
            {
              v13 = GetLastError();
              v4 = v13;
              if ( v13 > 0 )
                v4 = (unsigned __int16)v13 | 0x80070000;
              if ( v4 < 0 )
              {
                _DbgPrintMessage(8, "CreateDirectory failed: 0x%x in %s", (unsigned int)v4, "PrepareRdvFolder");
                goto LABEL_32;
              }
            }
            v5 = CPathString::BuildPath((CPathString *)&v25, a2, L"rdvdata");
            v4 = v5;
            if ( v5 >= 0 )
            {
              v14 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v25);
              if ( !(unsigned int)FolderExists(v14) )
                goto LABEL_32;
              CBaseStringT<unsigned short>::PContents(&v25);
              v15 = CBaseStringT<unsigned short>::PContents(&v21);
              _DbgPrintMessage(
                8,
                "RDV: SessEnvRpc found rdv folder on host (%ws), copy it to vhd. rdvFolderOnVhdPath: %ws,rdvFolderOnHostPath: %ws.",
                v15,
                v16,
                v21,
                v22,
                v23,
                v24,
                v25,
                v26,
                v27,
                v28,
                v29,
                v30,
                v31,
                v32);
              CBaseStringT<unsigned short>::PContents(&v21);
              v17 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v25);
              v5 = CopyFolder(v17, v18);
              v4 = v5;
              if ( v5 >= 0 )
              {
                v19 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v25);
                v5 = DeleteFolder(v19);
                v4 = v5;
                if ( v5 >= 0 )
                  goto LABEL_32;
                v6 = "DeleteFolder rdvFolderOnHostPath failed: 0x%x in %s";
              }
              else
              {
                v6 = "CopyFolder failed: 0x%x in %s";
              }
            }
            else
            {
              v6 = "rdvFolderOnHostPath.BuildPath failed: 0x%x in %s";
            }
          }
          else
          {
            v6 = "DeleteFolder failed: 0x%x in %s";
          }
        }
        else
        {
          v6 = "rdvFolderOnVhdPath.BuildPath failed: 0x%x in %s";
        }
      }
      else
      {
        v6 = "Failed to build VHD Folder Root path failed: 0x%x in %s";
      }
      _DbgPrintMessage(8, v6, (unsigned int)v5, "PrepareRdvFolder", v21, v22, v23, v24);
      goto LABEL_32;
    }
    v3 = "szVmRootPath";
  }
  else
  {
    v3 = "szVhdVolumeRootPath";
  }
  _DbgPrintMessage(8, "Missing paramter %s in %s", v3, "PrepareRdvFolder");
  v4 = -2147024809;
LABEL_32:
  CPathString::~CPathString((CPathString *)&v21);
  CPathString::~CPathString((CPathString *)&v25);
  CPathString::~CPathString((CPathString *)&v29);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180036ae0  push    rbp
0x180036ae2  push    rbx
0x180036ae3  push    rsi
0x180036ae4  push    rdi
0x180036ae5  lea     rbp, [rsp-3Fh]
0x180036aea  sub     rsp, 0B8h
0x180036af1  xor     esi, esi
0x180036af3  mov     qword ptr [rbp+57h+var_58+4], 80h
0x180036afb  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180036b02  mov     [rbp+57h+var_48], rsi
0x180036b06  mov     [rbp+57h+var_60], rax
0x180036b0a  mov     rdi, rdx
0x180036b0d  mov     edx, 8000000h
0x180036b12  mov     [rbp+57h+var_88], rax
0x180036b16  mov     [rbp+57h+var_B0], rax
0x180036b1a  xorps   xmm0, xmm0
0x180036b1d  xor     eax, eax
0x180036b1f  mov     dword ptr [rbp+57h+var_58+0Ch], esi
0x180036b22  mov     dword ptr [rbp+57h+var_40], edx
0x180036b25  mov     dword ptr [rbp+57h+var_58], esi
0x180036b28  mov     qword ptr [rbp+57h+var_80+4], 80h
0x180036b30  mov     [rbp+57h+var_70], rsi
0x180036b34  mov     dword ptr [rbp+57h+var_80+0Ch], esi
0x180036b37  mov     dword ptr [rbp+57h+var_68], edx
0x180036b3a  mov     dword ptr [rbp+57h+var_80], esi
0x180036b3d  mov     qword ptr [rbp+57h+var_A8+4], 80h
0x180036b45  mov     [rbp+57h+var_98], rsi
0x180036b49  mov     dword ptr [rbp+57h+var_A8+0Ch], esi
0x180036b4c  mov     dword ptr [rbp+57h+var_90], edx
0x180036b4f  mov     dword ptr [rbp+57h+var_A8], esi
0x180036b52  mov     [rbp+57h+var_28], rax
0x180036b56  movups  xmmword ptr [rbp+57h+SecurityDescriptor], xmm0
0x180036b5a  test    rcx, rcx
0x180036b5d  jnz     short loc_180036B88
0x180036b5f  lea     r8, aSzvhdvolumeroo; "szVhdVolumeRootPath"
0x180036b66  lea     r9, aPreparerdvfold; "PrepareRdvFolder"
0x180036b6d  mov     ecx, 8; int
0x180036b72  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180036b79  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180036b7e  mov     ebx, 80070057h
0x180036b83  jmp     loc_180036DA3
0x180036b88  test    rdi, rdi
0x180036b8b  jnz     short loc_180036B96
0x180036b8d  lea     r8, aSzvmrootpath; "szVmRootPath"
0x180036b94  jmp     short loc_180036B66
0x180036b96  mov     rdx, rcx; unsigned __int16 *
0x180036b99  lea     r8, aWindows; "Windows"
0x180036ba0  lea     rcx, [rbp+57h+var_60]; this
0x180036ba4  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x180036ba9  mov     ebx, eax
0x180036bab  test    eax, eax
0x180036bad  jns     short loc_180036BBB
0x180036baf  lea     rdx, aFailedToBuildV; "Failed to build VHD Folder Root path fa"...
0x180036bb6  jmp     loc_180036D8F
0x180036bbb  lea     rcx, [rbp+57h+var_60]
0x180036bbf  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180036bc4  mov     rcx, rax; unsigned __int16 *
0x180036bc7  call    ?FolderExists@@YAHPEBG@Z; FolderExists(ushort const *)
0x180036bcc  lea     rcx, [rbp+57h+var_60]
0x180036bd0  test    eax, eax
0x180036bd2  jnz     short loc_180036BF7
0x180036bd4  mov     ebx, 80070002h
0x180036bd9  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180036bde  mov     r8, rax
0x180036be1  lea     rdx, aRdvFolderRootW; "RDV Folder Root [%ws] not found"
0x180036be8  mov     ecx, 4; int
0x180036bed  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180036bf2  jmp     loc_180036DA3
0x180036bf7  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180036bfc  lea     r8, aRdvdata; "rdvdata"
0x180036c03  mov     rdx, rax; unsigned __int16 *
0x180036c06  lea     rcx, [rbp+57h+var_B0]; this
0x180036c0a  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x180036c0f  mov     ebx, eax
0x180036c11  test    eax, eax
0x180036c13  jns     short loc_180036C21
0x180036c15  lea     rdx, aRdvfolderonvhd; "rdvFolderOnVhdPath.BuildPath failed: 0x"...
0x180036c1c  jmp     loc_180036D8F
0x180036c21  lea     rcx, [rbp+57h+var_B0]
0x180036c25  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180036c2a  mov     rcx, rax; unsigned __int16 *
0x180036c2d  call    ?DeleteFolder@@YAJPEBG@Z; DeleteFolder(ushort const *)
0x180036c32  mov     ebx, eax
0x180036c34  test    eax, eax
0x180036c36  jns     short loc_180036C44
0x180036c38  lea     rdx, aDeletefolderFa; "DeleteFolder failed: 0x%x in %s"
0x180036c3f  jmp     loc_180036D8F
0x180036c44  xor     r9d, r9d; SecurityDescriptorSize
0x180036c47  mov     dword ptr [rbp+57h+SecurityDescriptor], 18h
0x180036c4e  lea     r8, [rbp+57h+SecurityDescriptor+8]; SecurityDescriptor
0x180036c52  mov     dword ptr [rbp+57h+var_28], esi
0x180036c55  lea     rcx, aDAOiciFagaSy; "D:(A;OICI;FAGA;;;SY)"
0x180036c5c  mov     [rbp+57h+SecurityDescriptor+8], rsi
0x180036c60  lea     edx, [r9+1]; StringSDRevision
0x180036c64  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180036c6a  test    eax, eax
0x180036c6c  jnz     short loc_180036C96
0x180036c6e  call    cs:__imp_GetLastError
0x180036c74  mov     ebx, eax
0x180036c76  test    eax, eax
0x180036c78  jle     short loc_180036C83
0x180036c7a  movzx   ebx, ax
0x180036c7d  or      ebx, 80070000h
0x180036c83  test    ebx, ebx
0x180036c85  jns     short loc_180036C96
0x180036c87  mov     r8d, ebx
0x180036c8a  lea     rdx, aConvertstrings_6; "ConvertStringSecurityDescriptorToSecuri"...
0x180036c91  jmp     loc_180036D92
0x180036c96  lea     rcx, [rbp+57h+var_B0]
0x180036c9a  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180036c9f  mov     rcx, rax; lpPathName
0x180036ca2  lea     rdx, [rbp+57h+SecurityDescriptor]; lpSecurityAttributes
0x180036ca6  call    cs:__imp_CreateDirectoryW
0x180036cac  test    eax, eax
0x180036cae  jnz     short loc_180036CD8
0x180036cb0  call    cs:__imp_GetLastError
0x180036cb6  mov     ebx, eax
0x180036cb8  test    eax, eax
0x180036cba  jle     short loc_180036CC5
0x180036cbc  movzx   ebx, ax
0x180036cbf  or      ebx, 80070000h
0x180036cc5  test    ebx, ebx
0x180036cc7  jns     short loc_180036CD8
0x180036cc9  mov     r8d, ebx
0x180036ccc  lea     rdx, aCreatedirector_0; "CreateDirectory failed: 0x%x in %s"
0x180036cd3  jmp     loc_180036D92
0x180036cd8  lea     r8, aRdvdata; "rdvdata"
0x180036cdf  mov     rdx, rdi; unsigned __int16 *
0x180036ce2  lea     rcx, [rbp+57h+var_88]; this
0x180036ce6  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x180036ceb  mov     ebx, eax
0x180036ced  test    eax, eax
0x180036cef  jns     short loc_180036CFD
0x180036cf1  lea     rdx, aRdvfolderonhos; "rdvFolderOnHostPath.BuildPath failed: 0"...
0x180036cf8  jmp     loc_180036D8F
0x180036cfd  lea     rcx, [rbp+57h+var_88]
0x180036d01  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180036d06  mov     rcx, rax; unsigned __int16 *
0x180036d09  call    ?FolderExists@@YAHPEBG@Z; FolderExists(ushort const *)
0x180036d0e  test    eax, eax
0x180036d10  jz      loc_180036DA3
0x180036d16  lea     rcx, [rbp+57h+var_88]
0x180036d1a  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180036d1f  lea     rcx, [rbp+57h+var_B0]
0x180036d23  mov     r10, rax
0x180036d26  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180036d2b  mov     r9, r10
0x180036d2e  lea     rdx, aRdvSessenvrpcF; "RDV: SessEnvRpc found rdv folder on hos"...
0x180036d35  mov     r8, rax
0x180036d38  mov     ecx, 8; int
0x180036d3d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180036d42  lea     rcx, [rbp+57h+var_B0]
0x180036d46  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180036d4b  lea     rcx, [rbp+57h+var_88]
0x180036d4f  mov     r10, rax
0x180036d52  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180036d57  mov     rdx, r10; unsigned __int16 *
0x180036d5a  mov     rcx, rax; unsigned __int16 *
0x180036d5d  call    ?CopyFolder@@YAJPEBG0@Z; CopyFolder(ushort const *,ushort const *)
0x180036d62  mov     ebx, eax
0x180036d64  test    eax, eax
0x180036d66  jns     short loc_180036D71
0x180036d68  lea     rdx, aCopyfolderFail; "CopyFolder failed: 0x%x in %s"
0x180036d6f  jmp     short loc_180036D8F
0x180036d71  lea     rcx, [rbp+57h+var_88]
0x180036d75  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180036d7a  mov     rcx, rax; unsigned __int16 *
0x180036d7d  call    ?DeleteFolder@@YAJPEBG@Z; DeleteFolder(ushort const *)
0x180036d82  mov     ebx, eax
0x180036d84  test    eax, eax
0x180036d86  jns     short loc_180036DA3
0x180036d88  lea     rdx, aDeletefolderRd; "DeleteFolder rdvFolderOnHostPath failed"...
0x180036d8f  mov     r8d, eax
0x180036d92  lea     r9, aPreparerdvfold; "PrepareRdvFolder"
0x180036d99  mov     ecx, 8; int
0x180036d9e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180036da3  lea     rcx, [rbp+57h+var_B0]; this
0x180036da7  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180036dac  lea     rcx, [rbp+57h+var_88]; this
0x180036db0  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180036db5  lea     rcx, [rbp+57h+var_60]; this
0x180036db9  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180036dbe  mov     eax, ebx
0x180036dc0  add     rsp, 0B8h
0x180036dc7  pop     rdi
0x180036dc8  pop     rsi
0x180036dc9  pop     rbx
0x180036dca  pop     rbp
0x180036dcb  retn
```
