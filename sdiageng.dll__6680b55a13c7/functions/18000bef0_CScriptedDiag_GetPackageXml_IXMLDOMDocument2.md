# CScriptedDiag::GetPackageXml(IXMLDOMDocument2 * *)

- ea: `0x18000bef0`
- end: `0x18000c13c`
- name: `?GetPackageXml@CScriptedDiag@@AEAAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `588`
- prototype: `__int64 __fastcall(CScriptedDiag *__hidden this, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18000cf00`

## callees

- `0x1800012a4`
- `0x1800020f8`
- `0x18000bef0`
- `0x18001e808`
- `0x180026fa0`
- `0x180028988`
- `0x180029882`
- `0x1800298c0`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c0a7`
- `KERNEL32!GetLastError` at `0x18000c0a7`
- `KERNEL32!FindFirstFileW` at `0x18000c004`
- `KERNEL32!FindFirstFileW` at `0x18000c004`
- `KERNEL32!FindClose` at `0x18000c01b`
- `KERNEL32!FindClose` at `0x18000c01b`

## string_xrefs

- `0x18000bf5c`: `CScriptedDiag::GetPackageXml`
- `0x18000bf9b`: `CScriptedDiag::GetPackageXml`
- `0x18000bfdc`: `CScriptedDiag::GetPackageXml`
- `0x18000c070`: `CScriptedDiag::GetPackageXml`
- `0x18000c0be`: `CScriptedDiag::GetPackageXml`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::GetPackageXml(CScriptedDiag *this, struct IXMLDOMDocument2 **a2)
{
  struct IXMLDOMDocument2 *v4; // rsi
  WCHAR *v5; // rdi
  unsigned int v6; // ebx
  int v7; // r8d
  Settings *v8; // rcx
  int PackagePath; // eax
  int v10; // eax
  int v11; // r8d
  char *FirstFileW; // rax
  int v13; // eax
  signed int LastError; // eax
  LPCWSTR lpFileName; // [rsp+20h] [rbp-E0h] BYREF
  void *Block; // [rsp+28h] [rbp-D8h] BYREF
  struct IXMLDOMDocument2 *v18; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF

  v4 = 0;
  v5 = 0;
  v18 = 0;
  Block = 0;
  lpFileName = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 850;
LABEL_3:
    SdpDebugTrace(1u, L"CScriptedDiag::GetPackageXml", v7, v6);
    return v6;
  }
  v8 = (Settings *)*((_QWORD *)this + 3);
  if ( !v8 )
  {
    v6 = -2147467261;
    v7 = 852;
    goto LABEL_3;
  }
  PackagePath = Settings::get_PackagePath(v8, (unsigned __int16 **)&Block);
  v6 = PackagePath;
  if ( PackagePath >= 0 )
  {
    v10 = SdpBuildPath((const unsigned __int16 *)Block, L"*.diagpkg", (unsigned __int16 **)&lpFileName);
    v6 = v10;
    if ( v10 < 0 )
    {
      v11 = 860;
LABEL_10:
      SdpDebugTrace(1u, L"CScriptedDiag::GetPackageXml", v11, v10);
      v5 = (WCHAR *)lpFileName;
      goto LABEL_26;
    }
    v5 = (WCHAR *)lpFileName;
    FirstFileW = (char *)FindFirstFileW(lpFileName, &FindFileData);
    if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( (v6 & 0x80000000) == 0 )
        v6 = -2147467259;
      SdpDebugTrace(1u, L"CScriptedDiag::GetPackageXml", 863, v6);
    }
    else
    {
      FindClose(FirstFileW);
      if ( v5 )
      {
        operator delete(v5);
        lpFileName = 0;
      }
      v10 = SdpBuildPath((const unsigned __int16 *)Block, FindFileData.cFileName, (unsigned __int16 **)&lpFileName);
      v6 = v10;
      if ( v10 < 0 )
      {
        v11 = 871;
        goto LABEL_10;
      }
      v5 = (WCHAR *)lpFileName;
      v13 = SdpXmlLoad((OLECHAR *)lpFileName, &v18);
      v6 = v13;
      if ( v13 >= 0 )
      {
        v4 = v18;
        *a2 = v18;
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v4->lpVtbl->AddRef)(v4);
      }
      else
      {
        SdpDebugTrace(1u, L"CScriptedDiag::GetPackageXml", 874, v13);
        v4 = v18;
      }
    }
    if ( v4 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v4->lpVtbl->Release)(v4);
    goto LABEL_26;
  }
  SdpDebugTrace(1u, L"CScriptedDiag::GetPackageXml", 855, PackagePath);
LABEL_26:
  if ( Block )
    operator delete(Block);
  if ( v5 )
    operator delete(v5);
  return v6;
}

```

## disassembly

```asm
0x18000bef0  mov     [rsp-8+arg_10], rbx
0x18000bef5  mov     [rsp-8+arg_18], rsi
0x18000befa  push    rbp
0x18000befb  push    rdi
0x18000befc  push    r15
0x18000befe  lea     rbp, [rsp-1A0h]
0x18000bf06  sub     rsp, 2A0h
0x18000bf0d  mov     rax, cs:__security_cookie
0x18000bf14  xor     rax, rsp
0x18000bf17  mov     [rbp+1B0h+var_20], rax
0x18000bf1e  mov     r15, rdx
0x18000bf21  mov     rbx, rcx
0x18000bf24  xor     esi, esi
0x18000bf26  lea     rcx, [rsp+2B0h+FindFileData]; void *
0x18000bf2b  xor     edi, edi
0x18000bf2d  mov     [rsp+2B0h+var_280], rsi
0x18000bf32  xor     edx, edx; Val
0x18000bf34  mov     [rsp+2B0h+Block], rsi
0x18000bf39  mov     r8d, 250h; Size
0x18000bf3f  mov     [rsp+2B0h+lpFileName], rdi
0x18000bf44  call    memset_0
0x18000bf49  test    r15, r15
0x18000bf4c  jnz     short loc_18000BF72
0x18000bf4e  mov     ebx, 80070057h
0x18000bf53  mov     r8d, 352h; int
0x18000bf59  mov     r9d, ebx; int
0x18000bf5c  lea     rdx, aCscripteddiagG_14; "CScriptedDiag::GetPackageXml"
0x18000bf63  mov     ecx, 1; Level
0x18000bf68  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000bf6d  jmp     loc_18000C113
0x18000bf72  mov     rcx, [rbx+18h]; this
0x18000bf76  test    rcx, rcx
0x18000bf79  jnz     short loc_18000BF88
0x18000bf7b  mov     ebx, 80004003h
0x18000bf80  mov     r8d, 354h
0x18000bf86  jmp     short loc_18000BF59
0x18000bf88  lea     rdx, [rsp+2B0h+Block]; unsigned __int16 **
0x18000bf8d  call    ?get_PackagePath@Settings@@QEAAJPEAPEAG@Z; Settings::get_PackagePath(ushort * *)
0x18000bf92  mov     ebx, eax
0x18000bf94  test    eax, eax
0x18000bf96  jns     short loc_18000BFB7
0x18000bf98  mov     r9d, eax; int
0x18000bf9b  lea     rdx, aCscripteddiagG_14; "CScriptedDiag::GetPackageXml"
0x18000bfa2  mov     r8d, 357h; int
0x18000bfa8  mov     ecx, 1; Level
0x18000bfad  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000bfb2  jmp     loc_18000C0F4
0x18000bfb7  mov     rcx, [rsp+2B0h+Block]; unsigned __int16 *
0x18000bfbc  lea     r8, [rsp+2B0h+lpFileName]; unsigned __int16 **
0x18000bfc1  lea     rdx, aDiagpkg; "*.diagpkg"
0x18000bfc8  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x18000bfcd  mov     ebx, eax
0x18000bfcf  test    eax, eax
0x18000bfd1  jns     short loc_18000BFF7
0x18000bfd3  mov     r8d, 35Ch; int
0x18000bfd9  mov     r9d, eax; int
0x18000bfdc  lea     rdx, aCscripteddiagG_14; "CScriptedDiag::GetPackageXml"
0x18000bfe3  mov     ecx, 1; Level
0x18000bfe8  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000bfed  mov     rdi, [rsp+2B0h+lpFileName]
0x18000bff2  jmp     loc_18000C0F4
0x18000bff7  mov     rdi, [rsp+2B0h+lpFileName]
0x18000bffc  lea     rdx, [rsp+2B0h+FindFileData]; lpFindFileData
0x18000c001  mov     rcx, rdi; lpFileName
0x18000c004  call    cs:__imp_FindFirstFileW
0x18000c00a  lea     rdx, [rax-1]
0x18000c00e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000c012  ja      loc_18000C0A7
0x18000c018  mov     rcx, rax; hFindFile
0x18000c01b  call    cs:__imp_FindClose
0x18000c021  test    rdi, rdi
0x18000c024  jz      short loc_18000C033
0x18000c026  mov     rcx, rdi; Block
0x18000c029  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c02e  mov     [rsp+2B0h+lpFileName], rsi
0x18000c033  mov     rcx, [rsp+2B0h+Block]; unsigned __int16 *
0x18000c038  lea     r8, [rsp+2B0h+lpFileName]; unsigned __int16 **
0x18000c03d  lea     rdx, [rsp+2B0h+FindFileData.cFileName]; unsigned __int16 *
0x18000c042  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x18000c047  mov     ebx, eax
0x18000c049  test    eax, eax
0x18000c04b  jns     short loc_18000C055
0x18000c04d  mov     r8d, 367h
0x18000c053  jmp     short loc_18000BFD9
0x18000c055  mov     rdi, [rsp+2B0h+lpFileName]
0x18000c05a  lea     rdx, [rsp+2B0h+var_280]; struct IXMLDOMDocument2 **
0x18000c05f  mov     rcx, rdi; psz
0x18000c062  call    ?SdpXmlLoad@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlLoad(ushort const *,IXMLDOMDocument2 * *)
0x18000c067  mov     ebx, eax
0x18000c069  test    eax, eax
0x18000c06b  jns     short loc_18000C08E
0x18000c06d  mov     r9d, eax; int
0x18000c070  lea     rdx, aCscripteddiagG_14; "CScriptedDiag::GetPackageXml"
0x18000c077  mov     r8d, 36Ah; int
0x18000c07d  mov     ecx, 1; Level
0x18000c082  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000c087  mov     rsi, [rsp+2B0h+var_280]
0x18000c08c  jmp     short loc_18000C0E0
0x18000c08e  mov     rsi, [rsp+2B0h+var_280]
0x18000c093  mov     [r15], rsi
0x18000c096  mov     rcx, rsi
0x18000c099  mov     rax, [rsi]
0x18000c09c  mov     rax, [rax+8]
0x18000c0a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0a5  jmp     short loc_18000C0E0
0x18000c0a7  call    cs:__imp_GetLastError
0x18000c0ad  mov     ebx, eax
0x18000c0af  test    eax, eax
0x18000c0b1  jle     short loc_18000C0BC
0x18000c0b3  movzx   ebx, ax
0x18000c0b6  or      ebx, 80070000h
0x18000c0bc  test    ebx, ebx
0x18000c0be  lea     rdx, aCscripteddiagG_14; "CScriptedDiag::GetPackageXml"
0x18000c0c5  mov     eax, 80004005h
0x18000c0ca  mov     r8d, 35Fh; int
0x18000c0d0  cmovns  ebx, eax
0x18000c0d3  mov     ecx, 1; Level
0x18000c0d8  mov     r9d, ebx; int
0x18000c0db  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000c0e0  test    rsi, rsi
0x18000c0e3  jz      short loc_18000C0F4
0x18000c0e5  mov     rax, [rsi]
0x18000c0e8  mov     rcx, rsi
0x18000c0eb  mov     rax, [rax+10h]
0x18000c0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0f4  cmp     [rsp+2B0h+Block], 0
0x18000c0fa  jz      short loc_18000C106
0x18000c0fc  mov     rcx, [rsp+2B0h+Block]; Block
0x18000c101  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c106  test    rdi, rdi
0x18000c109  jz      short loc_18000C113
0x18000c10b  mov     rcx, rdi; Block
0x18000c10e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c113  mov     eax, ebx
0x18000c115  mov     rcx, [rbp+1B0h+var_20]
0x18000c11c  xor     rcx, rsp; StackCookie
0x18000c11f  call    __security_check_cookie
0x18000c124  lea     r11, [rsp+2B0h+var_10]
0x18000c12c  mov     rbx, [r11+30h]
0x18000c130  mov     rsi, [r11+38h]
0x18000c134  mov     rsp, r11
0x18000c137  pop     r15
0x18000c139  pop     rdi
0x18000c13a  pop     rbp
0x18000c13b  retn
```
