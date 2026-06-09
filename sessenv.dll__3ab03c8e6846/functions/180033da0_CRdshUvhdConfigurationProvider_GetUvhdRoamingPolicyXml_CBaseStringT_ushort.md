# CRdshUvhdConfigurationProvider::GetUvhdRoamingPolicyXml(CBaseStringT<ushort> *)

- ea: `0x180033da0`
- end: `0x180034058`
- name: `?GetUvhdRoamingPolicyXml@CRdshUvhdConfigurationProvider@@UEBAJPEAV?$CBaseStringT@G@@@Z`
- size: `696`
- prototype: `__int64 __fastcall(CRdshUvhdConfigurationProvider *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180003f30`
- `0x180004db0`
- `0x180019b38`
- `0x180031204`
- `0x180031448`
- `0x18003146c`
- `0x1800327c8`
- `0x180033c04`
- `0x180033da0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034010`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034010`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033e74`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033e74`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180033edc`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180033edc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180033f7b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180033f7b`

## string_xrefs

- `0x180033dee`: `CRdshUvhdConfigurationProvider::GetUvhdRoamingPolicyXml`
- `0x180034026`: `CRdshUvhdConfigurationProvider::GetUvhdRoamingPolicyXml`
- `0x180033df5`: `pstrUvhdRoamingPolicyXml`
- `0x180033e28`: `GetUvhdPolicyFilePath() failed: 0x%x in %s`
- `0x18003401f`: `ReadUvhdPolicyFromPolicyFile() failed: 0x%x in %s`
- `0x180033eb3`: `CRdshUvhdConfigurationProvider::ReadUvhdPolicyFromPolicyFile`
- `0x180033ff6`: `CRdshUvhdConfigurationProvider::ReadUvhdPolicyFromPolicyFile`
- `0x180033ebd`: `Failed to open the Policy File failed: 0x%x in %s`
- `0x180033fb8`: `Failed to read the Policy File contents failed: 0x%x in %s`
- `0x180033fd0`: `Policy File was not read completely. failed: 0x%x in %s`
- `0x180033fef`: `pstrUvhdRoamingPolicyXml->SetLength() failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CRdshUvhdConfigurationProvider::GetUvhdRoamingPolicyXml(
        CRdshUvhdConfigurationProvider *a1,
        __int64 a2)
{
  signed int v3; // edi
  int UvhdPolicyFilePath; // eax
  const WCHAR *v5; // rax
  HANDLE FileW; // r14
  signed int LastError; // eax
  signed int v8; // ebx
  signed int v9; // eax
  void *Buffer; // rax
  DWORD v11; // r10d
  signed int v12; // eax
  int v13; // eax
  void **v15; // [rsp+40h] [rbp-30h] BYREF
  int v16; // [rsp+48h] [rbp-28h]
  __int64 v17; // [rsp+4Ch] [rbp-24h]
  int v18; // [rsp+54h] [rbp-1Ch]
  __int64 v19; // [rsp+58h] [rbp-18h]
  int v20; // [rsp+60h] [rbp-10h]
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+28h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+A0h] [rbp+30h] BYREF

  v17 = 128;
  v15 = &CPathString::`vftable';
  v19 = 0;
  v18 = 0;
  v20 = 0x8000000;
  v16 = 0;
  if ( !a2 )
  {
    _DbgPrintMessage(
      8,
      "Missing paramter %s in %s",
      "pstrUvhdRoamingPolicyXml",
      "CRdshUvhdConfigurationProvider::GetUvhdRoamingPolicyXml");
    v3 = -2147024809;
    goto LABEL_39;
  }
  UvhdPolicyFilePath = CRdshUvhdConfigurationProvider::GetUvhdPolicyFilePath(a1, (struct CPathString *)&v15);
  v3 = UvhdPolicyFilePath;
  if ( UvhdPolicyFilePath < 0 )
  {
    _DbgPrintMessage(
      8,
      "GetUvhdPolicyFilePath() failed: 0x%x in %s",
      (unsigned int)UvhdPolicyFilePath,
      "CRdshUvhdConfigurationProvider::GetUvhdRoamingPolicyXml");
    goto LABEL_39;
  }
  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  v5 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v15);
  FileW = CreateFileW(v5, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      v3 = v3 & 0x8000FFFF | 0x50610000;
    }
    if ( v3 < 0 )
    {
      v8 = v3;
      _DbgPrintMessage(
        8,
        "Failed to open the Policy File failed: 0x%x in %s",
        v3,
        "CRdshUvhdConfigurationProvider::ReadUvhdPolicyFromPolicyFile");
LABEL_38:
      _DbgPrintMessage(
        8,
        "ReadUvhdPolicyFromPolicyFile() failed: 0x%x in %s",
        (unsigned int)v8,
        "CRdshUvhdConfigurationProvider::GetUvhdRoamingPolicyXml");
      goto LABEL_39;
    }
  }
  if ( GetFileSizeEx(FileW, &FileSize) )
    goto LABEL_21;
  v9 = GetLastError();
  v8 = v9;
  if ( v9 && (v9 & 0xFFFF0000) == 0 )
  {
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    v8 = v8 & 0x8000FFFF | 0x50620000;
  }
  if ( v8 >= 0 )
  {
LABEL_21:
    if ( FileSize.QuadPart <= 0x100000 )
    {
      CBaseStringT<unsigned short>::EnsureSpace(a2, (unsigned __int64)FileSize.QuadPart >> 1);
      CBaseStringT<unsigned short>::GetBufferLength(a2);
      Buffer = (void *)CBaseStringT<unsigned short>::GetBuffer();
      if ( ReadFile(FileW, Buffer, v11, &NumberOfBytesRead, 0) )
        goto LABEL_31;
      v12 = GetLastError();
      v8 = v12;
      if ( v12 && (v12 & 0xFFFF0000) == 0 )
      {
        if ( v12 > 0 )
          v8 = (unsigned __int16)v12 | 0x80070000;
        v8 = v8 & 0x8000FFFF | 0x50630000;
      }
      if ( v8 >= 0 )
      {
LABEL_31:
        if ( NumberOfBytesRead == FileSize.QuadPart )
        {
          v13 = CBaseStringT<unsigned short>::SetLength(a2, NumberOfBytesRead >> 1);
          v8 = v13;
          if ( v13 < 0 )
            _DbgPrintMessage(
              8,
              "pstrUvhdRoamingPolicyXml->SetLength() failed: 0x%x in %s",
              (unsigned int)v13,
              "CRdshUvhdConfigurationProvider::ReadUvhdPolicyFromPolicyFile");
        }
        else
        {
          v8 = -2147467259;
          _DbgPrintMessage(
            8,
            "Policy File was not read completely. failed: 0x%x in %s",
            2147500037LL,
            "CRdshUvhdConfigurationProvider::ReadUvhdPolicyFromPolicyFile");
        }
      }
      else
      {
        _DbgPrintMessage(
          8,
          "Failed to read the Policy File contents failed: 0x%x in %s",
          (unsigned int)v8,
          "CRdshUvhdConfigurationProvider::ReadUvhdPolicyFromPolicyFile");
      }
    }
    else
    {
      v8 = -2147467259;
      _DbgPrintMessage(
        8,
        "Policy File is too big. failed: 0x%x in %s",
        2147500037LL,
        "CRdshUvhdConfigurationProvider::ReadUvhdPolicyFromPolicyFile");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "Failed to obtain Policy File size failed: 0x%x in %s",
      (unsigned int)v8,
      "CRdshUvhdConfigurationProvider::ReadUvhdPolicyFromPolicyFile");
  }
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  v3 = v8;
  if ( v8 < 0 )
    goto LABEL_38;
LABEL_39:
  CPathString::~CPathString((CPathString *)&v15);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180033da0  mov     [rsp-18h+arg_0], rbx
0x180033da5  mov     [rsp-18h+arg_18], rdi
0x180033daa  push    rbp
0x180033dab  push    r14
0x180033dad  push    r15
0x180033daf  mov     rbp, rsp
0x180033db2  sub     rsp, 70h
0x180033db6  mov     [rbp+var_24], 80h
0x180033dbe  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180033dc5  mov     [rbp+var_30], rax
0x180033dc9  mov     r15, rdx
0x180033dcc  mov     [rbp+var_18], 0
0x180033dd4  mov     [rbp+var_1C], 0
0x180033ddb  mov     [rbp+var_10], 8000000h
0x180033de2  mov     [rbp+var_28], 0
0x180033de9  test    rdx, rdx
0x180033dec  jnz     short loc_180033E16
0x180033dee  lea     r9, aCrdshuvhdconfi_7; "CRdshUvhdConfigurationProvider::GetUvhd"...
0x180033df5  lea     r8, aPstruvhdroamin; "pstrUvhdRoamingPolicyXml"
0x180033dfc  lea     rdx, aMissingParamte; "Missing paramter %s in %s"
0x180033e03  lea     ecx, [r15+8]; int
0x180033e07  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180033e0c  mov     edi, 80070057h
0x180033e11  jmp     loc_180034037
0x180033e16  lea     rdx, [rbp+var_30]; struct CPathString *
0x180033e1a  call    ?GetUvhdPolicyFilePath@CRdshUvhdConfigurationProvider@@AEBAJPEAVCPathString@@@Z; CRdshUvhdConfigurationProvider::GetUvhdPolicyFilePath(CPathString *)
0x180033e1f  mov     edi, eax
0x180033e21  test    eax, eax
0x180033e23  jns     short loc_180033E34
0x180033e25  mov     r8d, eax
0x180033e28  lea     rdx, aGetuvhdpolicyf; "GetUvhdPolicyFilePath() failed: 0x%x in"...
0x180033e2f  jmp     loc_180034026
0x180033e34  lea     rcx, [rbp+var_30]
0x180033e38  mov     qword ptr [rbp+FileSize], 0
0x180033e40  mov     [rbp+NumberOfBytesRead], 0
0x180033e47  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180033e4c  xor     r9d, r9d; lpSecurityAttributes
0x180033e4f  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x180033e58  mov     rcx, rax; lpFileName
0x180033e5b  mov     [rsp+70h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180033e63  mov     edx, 80000000h; dwDesiredAccess
0x180033e68  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x180033e70  lea     r8d, [r9+1]; dwShareMode
0x180033e74  call    cs:__imp_CreateFileW
0x180033e7a  mov     r14, rax
0x180033e7d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180033e81  jnz     short loc_180033ED5
0x180033e83  call    cs:__imp_GetLastError
0x180033e89  mov     edi, eax
0x180033e8b  test    eax, eax
0x180033e8d  jz      short loc_180033EAF
0x180033e8f  test    eax, 0FFFF0000h
0x180033e94  jnz     short loc_180033EAF
0x180033e96  test    eax, eax
0x180033e98  jle     short loc_180033EA3
0x180033e9a  movzx   edi, ax
0x180033e9d  or      edi, 80070000h
0x180033ea3  and     edi, 0D061FFFFh
0x180033ea9  or      edi, 50610000h
0x180033eaf  test    edi, edi
0x180033eb1  jns     short loc_180033ED5
0x180033eb3  lea     r9, aCrdshuvhdconfi_4; "CRdshUvhdConfigurationProvider::ReadUvh"...
0x180033eba  mov     r8d, edi
0x180033ebd  lea     rdx, aFailedToOpenTh; "Failed to open the Policy File failed: "...
0x180033ec4  mov     ecx, 8; int
0x180033ec9  mov     ebx, edi
0x180033ecb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180033ed0  jmp     loc_18003401C
0x180033ed5  lea     rdx, [rbp+FileSize]; lpFileSize
0x180033ed9  mov     rcx, r14; hFile
0x180033edc  call    cs:__imp_GetFileSizeEx
0x180033ee2  test    eax, eax
0x180033ee4  jnz     short loc_180033F25
0x180033ee6  call    cs:__imp_GetLastError
0x180033eec  mov     ebx, eax
0x180033eee  test    eax, eax
0x180033ef0  jz      short loc_180033F12
0x180033ef2  test    eax, 0FFFF0000h
0x180033ef7  jnz     short loc_180033F12
0x180033ef9  test    eax, eax
0x180033efb  jle     short loc_180033F06
0x180033efd  movzx   ebx, ax
0x180033f00  or      ebx, 80070000h
0x180033f06  and     ebx, 0D062FFFFh
0x180033f0c  or      ebx, 50620000h
0x180033f12  test    ebx, ebx
0x180033f14  jns     short loc_180033F25
0x180033f16  mov     r8d, ebx
0x180033f19  lea     rdx, aFailedToObtain_1; "Failed to obtain Policy File size faile"...
0x180033f20  jmp     loc_180033FF6
0x180033f25  mov     rdx, qword ptr [rbp+FileSize]
0x180033f29  cmp     rdx, 100000h
0x180033f30  jle     short loc_180033F47
0x180033f32  mov     r8d, 80004005h
0x180033f38  lea     rdx, aPolicyFileIsTo; "Policy File is too big. failed: 0x%x in"...
0x180033f3f  mov     ebx, r8d
0x180033f42  jmp     loc_180033FF6
0x180033f47  shr     rdx, 1
0x180033f4a  mov     rcx, r15
0x180033f4d  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x180033f52  mov     rcx, r15
0x180033f55  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x180033f5a  mov     r10d, eax
0x180033f5d  add     r10d, r10d
0x180033f60  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x180033f65  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180033f69  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180033f72  mov     r8d, r10d; nNumberOfBytesToRead
0x180033f75  mov     rdx, rax; lpBuffer
0x180033f78  mov     rcx, r14; hFile
0x180033f7b  call    cs:__imp_ReadFile
0x180033f81  test    eax, eax
0x180033f83  jnz     short loc_180033FC1
0x180033f85  call    cs:__imp_GetLastError
0x180033f8b  mov     ebx, eax
0x180033f8d  test    eax, eax
0x180033f8f  jz      short loc_180033FB1
0x180033f91  test    eax, 0FFFF0000h
0x180033f96  jnz     short loc_180033FB1
0x180033f98  test    eax, eax
0x180033f9a  jle     short loc_180033FA5
0x180033f9c  movzx   ebx, ax
0x180033f9f  or      ebx, 80070000h
0x180033fa5  and     ebx, 0D063FFFFh
0x180033fab  or      ebx, 50630000h
0x180033fb1  test    ebx, ebx
0x180033fb3  jns     short loc_180033FC1
0x180033fb5  mov     r8d, ebx
0x180033fb8  lea     rdx, aFailedToReadTh; "Failed to read the Policy File contents"...
0x180033fbf  jmp     short loc_180033FF6
0x180033fc1  mov     edx, [rbp+NumberOfBytesRead]
0x180033fc4  cmp     rdx, qword ptr [rbp+FileSize]
0x180033fc8  jz      short loc_180033FDC
0x180033fca  mov     r8d, 80004005h
0x180033fd0  lea     rdx, aPolicyFileWasN; "Policy File was not read completely. fa"...
0x180033fd7  mov     ebx, r8d
0x180033fda  jmp     short loc_180033FF6
0x180033fdc  shr     edx, 1
0x180033fde  mov     rcx, r15
0x180033fe1  call    ?SetLength@?$CBaseStringT@G@@QEAAJK@Z; CBaseStringT<ushort>::SetLength(ulong)
0x180033fe6  mov     ebx, eax
0x180033fe8  test    eax, eax
0x180033fea  jns     short loc_180034007
0x180033fec  mov     r8d, eax
0x180033fef  lea     rdx, aPstruvhdroamin_0; "pstrUvhdRoamingPolicyXml->SetLength() f"...
0x180033ff6  lea     r9, aCrdshuvhdconfi_4; "CRdshUvhdConfigurationProvider::ReadUvh"...
0x180033ffd  mov     ecx, 8; int
0x180034002  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180034007  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18003400b  jz      short loc_180034016
0x18003400d  mov     rcx, r14; hObject
0x180034010  call    cs:__imp_CloseHandle
0x180034016  mov     edi, ebx
0x180034018  test    ebx, ebx
0x18003401a  jns     short loc_180034037
0x18003401c  mov     r8d, ebx
0x18003401f  lea     rdx, aReaduvhdpolicy; "ReadUvhdPolicyFromPolicyFile() failed: "...
0x180034026  lea     r9, aCrdshuvhdconfi_7; "CRdshUvhdConfigurationProvider::GetUvhd"...
0x18003402d  mov     ecx, 8; int
0x180034032  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180034037  lea     rcx, [rbp+var_30]; this
0x18003403b  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180034040  lea     r11, [rsp+70h+var_s0]
0x180034045  mov     eax, edi
0x180034047  mov     rbx, [r11+20h]
0x18003404b  mov     rdi, [r11+38h]
0x18003404f  mov     rsp, r11
0x180034052  pop     r15
0x180034054  pop     r14
0x180034056  pop     rbp
0x180034057  retn
```
