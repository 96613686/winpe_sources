# CScrubbingClient::DeleteSingleFile(ushort const *)

- ea: `0x1800593c8`
- end: `0x18005961a`
- name: `?DeleteSingleFile@CScrubbingClient@@AEAAJPEBG@Z`
- size: `594`
- prototype: `int(CScrubbingClient *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18005a140`

## callees

- `0x180003604`
- `0x180007e10`
- `0x180011314`
- `0x180058d88`
- `0x1800593c8`
- `0x180061990`
- `0x180062448`
- `0x1800bb748`

## import_xrefs

- `KERNEL32!SetFileInformationByHandle` at `0x180059585`
- `KERNEL32!SetFileInformationByHandle` at `0x180059585`
- `KERNEL32!GetLastError` at `0x18005958f`
- `KERNEL32!GetLastError` at `0x18005958f`
- `ntdll!NtClose` at `0x1800595e8`
- `ntdll!NtClose` at `0x1800595e8`

## string_xrefs

- `0x18005943e`: `CScrubbingClient::DeleteSingleFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CScrubbingClient::DeleteSingleFile(CScrubbingClient *this, const unsigned __int16 *a2)
{
  _BYTE *v3; // rax
  char v4; // al
  int NormalizedNtPath; // eax
  unsigned int v6; // edx
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  int v9; // eax
  int Only; // eax
  signed int LastError; // eax
  unsigned int v12; // ebx
  unsigned int v14; // [rsp+20h] [rbp-78h]
  unsigned int v15; // [rsp+28h] [rbp-70h]
  unsigned int v16; // [rsp+30h] [rbp-68h]
  int v17; // [rsp+40h] [rbp-58h] BYREF
  int v18; // [rsp+44h] [rbp-54h]
  char v19; // [rsp+48h] [rbp-50h]
  const char *v20; // [rsp+50h] [rbp-48h]
  __int64 v21; // [rsp+58h] [rbp-40h]
  int pExceptionObject; // [rsp+60h] [rbp-38h] BYREF
  int v23; // [rsp+64h] [rbp-34h] BYREF
  int v24; // [rsp+68h] [rbp-30h] BYREF
  int v25; // [rsp+6Ch] [rbp-2Ch] BYREF
  signed int v26; // [rsp+70h] [rbp-28h] BYREF
  PCWSTR SourceString; // [rsp+78h] [rbp-20h] BYREF
  int v28; // [rsp+80h] [rbp-18h] BYREF
  const ATL::CAtlException *v29; // [rsp+88h] [rbp-10h] BYREF
  CScrubbingClient *FileInformation; // [rsp+A0h] [rbp+8h] BYREF
  HANDLE hFile; // [rsp+A8h] [rbp+10h] BYREF

  FileInformation = this;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_ec18d6b144853d7d3b8a6094779b898d_Traceguids);
      v3 = WPP_GLOBAL_Control;
    }
  }
  if ( (v3[68] & 8) != 0 && v3[65] >= 6u )
  {
    v4 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v4 = 0;
LABEL_9:
  v17 = 0;
  v18 = 383;
  v19 = v4;
  v20 = "CScrubbingClient::DeleteSingleFile";
  v21 = 0;
  hFile = 0;
  SourceString = 0;
  if ( !a2 )
  {
    v17 = -2147024809;
    HIWORD(v18) = 389;
    pExceptionObject = -2147024809;
    throw (long *)&pExceptionObject;
  }
  v17 = 0;
  LOWORD(v18) = 389;
  try
  {
    NormalizedNtPath = CPathUtilities::GetNormalizedNtPath(a2, (unsigned __int16 **)&SourceString);
    v17 = NormalizedNtPath;
    if ( NormalizedNtPath < 0 )
    {
      HIWORD(v18) = 394;
      v23 = NormalizedNtPath;
      throw (long *)&v23;
    }
    LOWORD(v18) = 394;
    v9 = CEcsPath::CreateFileW(SourceString, v6, v7, v8, v14, v15, v16, &hFile);
    v17 = v9;
    if ( v9 < 0 )
    {
      HIWORD(v18) = 407;
      v24 = v9;
      throw (long *)&v24;
    }
    LOWORD(v18) = 407;
    Only = CEcsPath::ClearReadOnly(hFile);
    v17 = Only;
    if ( Only < 0 )
    {
      HIWORD(v18) = 410;
      v25 = Only;
      throw (long *)&v25;
    }
    LOWORD(v18) = 410;
    LOBYTE(FileInformation) = 1;
    if ( !SetFileInformationByHandle(hFile, FileDispositionInfo, &FileInformation, 1u) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v17 = LastError;
        HIWORD(v18) = 416;
        v26 = LastError;
        throw (long *)&v26;
      }
    }
  }
  catch ( long v28 )
  {
    v17 = v28;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v18) = 419;
    v17 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v18) = 419;
    v17 = -2147418113;
  }
  catch ( const ATL::CAtlException *v29 )
  {
    HIWORD(v18) = 419;
    v17 = *(_DWORD *)v29;
  }
  if ( hFile )
    NtClose(hFile);
  v12 = v17;
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&SourceString);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v17);
  return v12;
}

```

## disassembly

```asm
0x1800593c8  mov     [rsp+arg_10], rbx
0x1800593cd  mov     [rsp+FileInformation], rcx
0x1800593d2  push    rdi
0x1800593d3  sub     rsp, 90h
0x1800593da  mov     rdi, rdx
0x1800593dd  lea     rcx, WPP_GLOBAL_Control
0x1800593e4  mov     rax, cs:WPP_GLOBAL_Control
0x1800593eb  cmp     rax, rcx
0x1800593ee  jz      short loc_180059418
0x1800593f0  test    byte ptr [rax+44h], 8
0x1800593f4  jz      short loc_18005942A
0x1800593f6  cmp     byte ptr [rax+41h], 6
0x1800593fa  jb      short loc_180059418
0x1800593fc  mov     edx, 15h
0x180059401  lea     r8, WPP_ec18d6b144853d7d3b8a6094779b898d_Traceguids
0x180059408  mov     rcx, [rax+38h]
0x18005940c  call    WPP_SF_
0x180059411  mov     rax, cs:WPP_GLOBAL_Control
0x180059418  test    byte ptr [rax+44h], 8
0x18005941c  jz      short loc_18005942A
0x18005941e  cmp     byte ptr [rax+41h], 6
0x180059422  jb      short loc_18005942A
0x180059424  mov     al, 1
0x180059426  xor     ebx, ebx
0x180059428  jmp     short loc_18005942E
0x18005942a  xor     ebx, ebx
0x18005942c  mov     al, bl
0x18005942e  mov     [rsp+98h+var_58], ebx
0x180059432  mov     [rsp+98h+var_54], 17Fh
0x18005943a  mov     [rsp+98h+var_50], al
0x18005943e  lea     rax, aCscrubbingclie; "CScrubbingClient::DeleteSingleFile"
0x180059445  mov     [rsp+98h+var_48], rax
0x18005944a  mov     [rsp+98h+var_40], rbx
0x18005944f  mov     [rsp+98h+hFile], rbx
0x180059457  mov     [rsp+98h+SourceString], rbx
0x18005945c  mov     eax, [rsp+98h+var_58]
0x180059460  mov     [rsp+98h+var_58], eax
0x180059464  mov     eax, 185h
0x180059469  test    rdi, rdi
0x18005946c  jnz     short loc_180059492
0x18005946e  mov     ecx, 80070057h
0x180059473  mov     [rsp+98h+var_58], ecx
0x180059477  mov     word ptr [rsp+98h+var_54+2], ax
0x18005947c  mov     [rsp+98h+pExceptionObject], ecx
0x180059480  lea     rdx, _TI1J; pThrowInfo
0x180059487  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18005948c  call    _CxxThrowException_0
0x180059492  mov     [rsp+98h+var_58], ebx
0x180059496  mov     word ptr [rsp+98h+var_54], ax
0x18005949b  lea     rdx, [rsp+98h+SourceString]; unsigned __int16 **
0x1800594a0  mov     rcx, rdi; unsigned __int16 *
0x1800594a3  call    ?GetNormalizedNtPath@CPathUtilities@@SAJPEBGPEAPEAG@Z; CPathUtilities::GetNormalizedNtPath(ushort const *,ushort * *)
0x1800594a8  mov     [rsp+98h+var_58], eax
0x1800594ac  mov     [rsp+98h+var_58], eax
0x1800594b0  mov     ecx, 18Ah
0x1800594b5  test    eax, eax
0x1800594b7  jns     short loc_1800594D3
0x1800594b9  mov     word ptr [rsp+98h+var_54+2], cx
0x1800594be  mov     [rsp+98h+var_34], eax
0x1800594c2  lea     rdx, _TI1J; pThrowInfo
0x1800594c9  lea     rcx, [rsp+98h+var_34]; pExceptionObject
0x1800594ce  call    _CxxThrowException_0
0x1800594d3  mov     word ptr [rsp+98h+var_54], cx
0x1800594d8  lea     rax, [rsp+98h+hFile]
0x1800594e0  mov     [rsp+98h+var_60], rax; void **
0x1800594e5  mov     rcx, [rsp+98h+SourceString]; SourceString
0x1800594ea  call    ?CreateFileW@CEcsPath@@SAJPEBGKKKKKKPEAPEAX@Z; CEcsPath::CreateFileW(ushort const *,ulong,ulong,ulong,ulong,ulong,ulong,void * *)
0x1800594ef  mov     [rsp+98h+var_58], eax
0x1800594f3  mov     [rsp+98h+var_58], eax
0x1800594f7  mov     ecx, 197h
0x1800594fc  test    eax, eax
0x1800594fe  jns     short loc_18005951A
0x180059500  mov     word ptr [rsp+98h+var_54+2], cx
0x180059505  mov     [rsp+98h+var_30], eax
0x180059509  lea     rdx, _TI1J; pThrowInfo
0x180059510  lea     rcx, [rsp+98h+var_30]; pExceptionObject
0x180059515  call    _CxxThrowException_0
0x18005951a  mov     word ptr [rsp+98h+var_54], cx
0x18005951f  mov     rcx, [rsp+98h+hFile]; FileHandle
0x180059527  call    ?ClearReadOnly@CEcsPath@@SAJPEAX@Z; CEcsPath::ClearReadOnly(void *)
0x18005952c  mov     [rsp+98h+var_58], eax
0x180059530  mov     [rsp+98h+var_58], eax
0x180059534  mov     ecx, 19Ah
0x180059539  test    eax, eax
0x18005953b  jns     short loc_180059557
0x18005953d  mov     word ptr [rsp+98h+var_54+2], cx
0x180059542  mov     [rsp+98h+var_2C], eax
0x180059546  lea     rdx, _TI1J; pThrowInfo
0x18005954d  lea     rcx, [rsp+98h+var_2C]; pExceptionObject
0x180059552  call    _CxxThrowException_0
0x180059557  mov     word ptr [rsp+98h+var_54], cx
0x18005955c  mov     byte ptr [rsp+98h+FileInformation], bl
0x180059563  mov     byte ptr [rsp+98h+FileInformation], 1
0x18005956b  mov     r9d, 1; dwBufferSize
0x180059571  lea     r8, [rsp+98h+FileInformation]; lpFileInformation
0x180059579  lea     edx, [r9+3]; FileInformationClass
0x18005957d  mov     rcx, [rsp+98h+hFile]; hFile
0x180059585  call    cs:__imp_SetFileInformationByHandle
0x18005958b  test    eax, eax
0x18005958d  jnz     short loc_1800595D3
0x18005958f  call    cs:__imp_GetLastError
0x180059595  test    eax, eax
0x180059597  jz      short loc_1800595D3
0x180059599  jle     short loc_1800595A3
0x18005959b  movzx   eax, ax
0x18005959e  or      eax, 80070000h
0x1800595a3  mov     [rsp+98h+var_58], eax
0x1800595a7  mov     [rsp+98h+var_58], eax
0x1800595ab  mov     ecx, 1A0h
0x1800595b0  test    eax, eax
0x1800595b2  jns     short loc_1800595CE
0x1800595b4  mov     word ptr [rsp+98h+var_54+2], cx
0x1800595b9  mov     [rsp+98h+var_28], eax
0x1800595bd  lea     rdx, _TI1J; pThrowInfo
0x1800595c4  lea     rcx, [rsp+98h+var_28]; pExceptionObject
0x1800595c9  call    _CxxThrowException_0
0x1800595ce  mov     word ptr [rsp+98h+var_54], cx
0x1800595d3  jmp     short loc_1800595DB
0x1800595d5  jmp     short loc_1800595DB
0x1800595d7  jmp     short loc_1800595DB
0x1800595d9  jmp     short $+2
0x1800595db  mov     rcx, [rsp+98h+hFile]; Handle
0x1800595e3  test    rcx, rcx
0x1800595e6  jz      short loc_1800595EE
0x1800595e8  call    cs:__imp_NtClose
0x1800595ee  mov     ebx, [rsp+98h+var_58]
0x1800595f2  lea     rcx, [rsp+98h+SourceString]
0x1800595f7  call    ??1?$CEcsMemPtr@G$0A@@@QEAA@XZ; CEcsMemPtr<ushort,0>::~CEcsMemPtr<ushort,0>(void)
0x1800595fc  nop
0x1800595fd  lea     rcx, [rsp+98h+var_58]; this
0x180059602  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180059607  mov     eax, ebx
0x180059609  mov     rbx, [rsp+98h+arg_10]
0x180059611  add     rsp, 90h
0x180059618  pop     rdi
0x180059619  retn
```
