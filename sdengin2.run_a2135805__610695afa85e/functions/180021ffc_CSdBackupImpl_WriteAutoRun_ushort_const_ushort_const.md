# CSdBackupImpl::_WriteAutoRun(ushort const *,ushort const *)

- ea: `0x180021ffc`
- end: `0x180022416`
- name: `?_WriteAutoRun@CSdBackupImpl@@AEAAJPEBG0@Z`
- size: `1050`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18001d464`

## callees

- `0x18001ab10`
- `0x180021ffc`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x18009e3c4`
- `0x18009e658`
- `0x18009ea34`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`
- `0x1800cf680`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800221bd`
- `KERNEL32!CreateFileW` at `0x1800222ca`
- `KERNEL32!CreateFileW` at `0x1800221bd`
- `KERNEL32!CreateFileW` at `0x1800222ca`
- `KERNEL32!GetACP` at `0x18002223c`
- `KERNEL32!GetACP` at `0x18002223c`
- `KERNEL32!GetLastError` at `0x1800221d7`
- `KERNEL32!GetLastError` at `0x1800222e4`
- `KERNEL32!GetLastError` at `0x1800221d7`
- `KERNEL32!GetLastError` at `0x1800222e4`
- `KERNEL32!CloseHandle` at `0x180022396`
- `KERNEL32!CloseHandle` at `0x1800223af`
- `KERNEL32!CloseHandle` at `0x180022396`
- `KERNEL32!CloseHandle` at `0x1800223af`
- `KERNEL32!WriteFile` at `0x180022349`
- `KERNEL32!WriteFile` at `0x180022349`
- `KERNEL32!WideCharToMultiByte` at `0x180022275`
- `KERNEL32!WideCharToMultiByte` at `0x180022275`

## string_xrefs

- `0x180022044`: `CSdBackupImpl::_WriteAutoRun`

## pseudocode

```c
__int64 __fastcall CSdBackupImpl::_WriteAutoRun(
        CSdBackupImpl *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  CSdBackupImpl *v5; // rcx
  __int64 v6; // r14
  __int64 v7; // rbx
  __int64 FileW; // rdi
  __int16 v9; // ax
  signed int StringResource; // esi
  signed int LastError; // eax
  UINT ACP; // eax
  __int64 v13; // rcx
  signed int v14; // eax
  __int16 v15; // ax
  __int64 v16; // rcx
  const unsigned __int16 *hTemplateFile; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *hTemplateFilea; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *lpUsedDefaultChar; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *lpUsedDefaultChara; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v22; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v23; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v24; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v25; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v26; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v27; // [rsp+50h] [rbp-B0h]
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v29; // [rsp+64h] [rbp-9Ch]
  __int16 v30; // [rsp+66h] [rbp-9Ah]
  DWORD NumberOfBytesWritten; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v32[2]; // [rsp+A0h] [rbp-60h] BYREF
  LPCWCH lpWideCharStr[2]; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+C0h] [rbp-40h] BYREF
  LPCWSTR v35[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v36[2]; // [rsp+E0h] [rbp-20h] BYREF
  CHAR MultiByteStr[4096]; // [rsp+F0h] [rbp-10h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v28, "CSdBackupImpl::_WriteAutoRun", 0x1114u, 1u);
  v35[0] = (LPCWSTR)qword_1800EE510;
  v35[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpFileName[1] = 0;
  v36[0] = qword_1800EE510;
  v36[1] = 0;
  lpWideCharStr[0] = (LPCWCH)qword_1800EE510;
  lpWideCharStr[1] = 0;
  memset_0(MultiByteStr, 0, sizeof(MultiByteStr));
  v6 = -1;
  v7 = -1;
  FileW = -1;
  v32[0] = qword_1800EE510;
  v32[1] = 0;
  NumberOfBytesWritten = 0;
  v9 = 4384;
  if ( !a2 || (v29 = 4384, v9 = 4385, !a3) )
  {
    StringResource = -2147024809;
    v28 = -2147024809;
    goto LABEL_3;
  }
  v28 = 0;
  v29 = 4385;
  StringResource = CSdBackupImpl::_EnsureAutoRunIcon(v5, a2, (struct CBsString *)v32);
  v28 = StringResource;
  v9 = 4387;
  if ( StringResource < 0 )
    goto LABEL_3;
  v29 = 4387;
  StringResource = CBsString::SetPath(
                     (CBsString *)v35,
                     a2,
                     L"autorun.inf",
                     0,
                     0,
                     0,
                     hTemplateFile,
                     lpUsedDefaultChar,
                     v22,
                     v24,
                     v26);
  v28 = StringResource;
  v9 = 4389;
  if ( StringResource < 0 )
    goto LABEL_3;
  v29 = 4389;
  StringResource = CBsString::SetPath(
                     (CBsString *)lpFileName,
                     a2,
                     L"autorun.wbcat",
                     0,
                     0,
                     0,
                     hTemplateFilea,
                     lpUsedDefaultChara,
                     v23,
                     v25,
                     v27);
  v28 = StringResource;
  v9 = 4391;
  if ( StringResource < 0 )
    goto LABEL_3;
  v29 = 4391;
  StringResource = CBsString::LoadStringResource((CBsString *)v36, hInstance, 0xD1u);
  v28 = StringResource;
  v9 = 4393;
  if ( StringResource < 0 )
    goto LABEL_3;
  v29 = 4393;
  FileW = (__int64)CreateFileW(lpFileName[0], 0xC0000000, 0, 0, 1u, 3u, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    StringResource = LastError;
    if ( LastError != 80 )
    {
      if ( LastError > 0 )
        StringResource = (unsigned __int16)LastError | 0x80070000;
      v28 = StringResource;
      v9 = 4415;
      if ( StringResource < 0 )
        goto LABEL_3;
      v29 = 4415;
    }
  }
  StringResource = CBsString::Format(
                     (CBsString *)lpWideCharStr,
                     L"[autorun]\r\n"
                      "label=%s\r\n"
                      "icon=%s,0\r\n"
                      "\r\n"
                      "[Content]\r\n"
                      "MusicFiles=0\r\n"
                      "PictureFiles=0\r\n"
                      "VideoFiles=0",
                     a3,
                     v32[0]);
  v28 = StringResource;
  v9 = 4428;
  if ( StringResource < 0 )
  {
LABEL_3:
    v30 = v9;
    goto LABEL_30;
  }
  v29 = 4428;
  ACP = GetACP();
  if ( !WideCharToMultiByte(ACP, 0, lpWideCharStr[0], -1, MultiByteStr, 4096, "_", 0) )
  {
    StringResource = GetLastFailureAsHRESULT(v13);
    v28 = StringResource;
    v9 = 4434;
    goto LABEL_3;
  }
  v28 = 0;
  v29 = 4434;
  v7 = (__int64)CreateFileW(v35[0], 0xC0000000, 0, 0, 1u, 0x80u, 0);
  if ( ((v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v14 = GetLastError();
    StringResource = v14;
    if ( v14 == 80 )
    {
      v28 = 1;
      v15 = 4455;
      StringResource = 1;
      goto LABEL_29;
    }
    if ( v14 > 0 )
      StringResource = (unsigned __int16)v14 | 0x80070000;
    v28 = StringResource;
    v9 = 4457;
    if ( StringResource < 0 )
      goto LABEL_3;
    v29 = 4457;
  }
  do
    ++v6;
  while ( MultiByteStr[v6] );
  if ( !WriteFile((HANDLE)v7, MultiByteStr, v6, &NumberOfBytesWritten, 0) )
  {
    StringResource = GetLastFailureAsHRESULT(v16);
    v28 = StringResource;
    v9 = 4464;
    goto LABEL_3;
  }
  v28 = 0;
  v15 = 4466;
  StringResource = 0;
LABEL_29:
  v29 = v15;
LABEL_30:
  CBsString::_Release((CBsString *)v32);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v7);
  CBsString::_Release((CBsString *)lpWideCharStr);
  CBsString::_Release((CBsString *)v36);
  CBsString::_Release((CBsString *)lpFileName);
  CBsString::_Release((CBsString *)v35);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v28);
  return (unsigned int)StringResource;
}

```

## disassembly

```asm
0x180021ffc  mov     [rsp-8+arg_0], rbx
0x180022001  push    rbp
0x180022002  push    rsi
0x180022003  push    rdi
0x180022004  push    r12
0x180022006  push    r13
0x180022008  push    r14
0x18002200a  push    r15
0x18002200c  lea     rbp, [rsp-1000h]
0x180022014  mov     eax, 1100h
0x180022019  call    _alloca_probe
0x18002201e  sub     rsp, rax
0x180022021  mov     rax, cs:__security_cookie
0x180022028  xor     rax, rsp
0x18002202b  mov     [rbp+1030h+var_40], rax
0x180022032  mov     r12, r8
0x180022035  mov     r15, rdx
0x180022038  mov     r9d, 1; unsigned __int16
0x18002203e  mov     r8d, 1114h; unsigned __int16
0x180022044  lea     rdx, aCsdbackupimplW_1; "CSdBackupImpl::_WriteAutoRun"
0x18002204b  lea     rcx, [rsp+1130h+var_10D0]; this
0x180022050  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180022055  lea     rsi, qword_1800EE510
0x18002205c  mov     [rbp+1030h+var_1060], rsi
0x180022060  xor     r13d, r13d
0x180022063  mov     [rbp+1030h+var_1058], r13
0x180022067  mov     [rbp+1030h+lpFileName], rsi
0x18002206b  mov     [rbp+1030h+var_1068], r13
0x18002206f  mov     [rbp+1030h+var_1050], rsi
0x180022073  mov     [rbp+1030h+var_1048], r13
0x180022077  mov     [rbp+1030h+lpWideCharStr], rsi
0x18002207b  mov     [rbp+1030h+var_1078], r13
0x18002207f  xor     edx, edx; Val
0x180022081  mov     r8d, 1000h; Size
0x180022087  lea     rcx, [rbp+1030h+MultiByteStr]; void *
0x18002208b  call    memset_0
0x180022090  or      r14, 0FFFFFFFFFFFFFFFFh
0x180022094  mov     rbx, r14
0x180022097  mov     rdi, r14
0x18002209a  mov     [rbp+1030h+var_1090], rsi
0x18002209e  mov     [rbp+1030h+var_1088], r13
0x1800220a2  mov     [rbp+1030h+NumberOfBytesWritten], r13d
0x1800220a6  mov     eax, 1120h
0x1800220ab  test    r15, r15
0x1800220ae  jnz     short loc_1800220C3
0x1800220b0  mov     esi, 80070057h
0x1800220b5  mov     [rsp+1130h+var_10D0], esi
0x1800220b9  mov     [rsp+1130h+var_10CA], ax
0x1800220be  jmp     loc_180022380
0x1800220c3  mov     [rsp+1130h+var_10CC], ax
0x1800220c8  mov     eax, 1121h
0x1800220cd  test    r12, r12
0x1800220d0  jz      short loc_1800220B0
0x1800220d2  mov     [rsp+1130h+var_10D0], r13d
0x1800220d7  mov     [rsp+1130h+var_10CC], ax
0x1800220dc  lea     r8, [rbp+1030h+var_1090]; struct CBsString *
0x1800220e0  mov     rdx, r15; unsigned __int16 *
0x1800220e3  call    ?_EnsureAutoRunIcon@CSdBackupImpl@@AEAAJPEBGPEAVCBsString@@@Z; CSdBackupImpl::_EnsureAutoRunIcon(ushort const *,CBsString *)
0x1800220e8  mov     esi, eax
0x1800220ea  mov     [rsp+1130h+var_10D0], eax
0x1800220ee  test    eax, eax
0x1800220f0  mov     eax, 1123h
0x1800220f5  js      short loc_1800220B9
0x1800220f7  mov     [rsp+1130h+var_10CC], ax
0x1800220fc  mov     qword ptr [rsp+1130h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x180022101  mov     qword ptr [rsp+1130h+dwCreationDisposition], r13; unsigned __int16 *
0x180022106  xor     r9d, r9d; unsigned __int16 *
0x180022109  lea     r8, aAutorunInf; "autorun.inf"
0x180022110  mov     rdx, r15; unsigned __int16 *
0x180022113  lea     rcx, [rbp+1030h+var_1060]; this
0x180022117  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18002211c  mov     esi, eax
0x18002211e  mov     [rsp+1130h+var_10D0], eax
0x180022122  test    eax, eax
0x180022124  mov     eax, 1125h
0x180022129  js      short loc_1800220B9
0x18002212b  mov     [rsp+1130h+var_10CC], ax
0x180022130  mov     qword ptr [rsp+1130h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x180022135  mov     qword ptr [rsp+1130h+dwCreationDisposition], r13; unsigned __int16 *
0x18002213a  xor     r9d, r9d; unsigned __int16 *
0x18002213d  lea     r8, aAutorunWbcat; "autorun.wbcat"
0x180022144  mov     rdx, r15; unsigned __int16 *
0x180022147  lea     rcx, [rbp+1030h+lpFileName]; this
0x18002214b  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180022150  mov     esi, eax
0x180022152  mov     [rsp+1130h+var_10D0], eax
0x180022156  test    eax, eax
0x180022158  mov     eax, 1127h
0x18002215d  js      loc_1800220B9
0x180022163  mov     [rsp+1130h+var_10CC], ax
0x180022168  mov     r8d, 0D1h; uID
0x18002216e  mov     rdx, cs:hInstance; hInstance
0x180022175  lea     rcx, [rbp+1030h+var_1050]; this
0x180022179  call    ?LoadStringResource@CBsString@@QEAAJPEAUHINSTANCE__@@I@Z; CBsString::LoadStringResource(HINSTANCE__ *,uint)
0x18002217e  mov     esi, eax
0x180022180  mov     [rsp+1130h+var_10D0], eax
0x180022184  test    eax, eax
0x180022186  mov     eax, 1129h
0x18002218b  js      loc_1800220B9
0x180022191  mov     [rsp+1130h+var_10CC], ax
0x180022196  mov     [rsp+1130h+hTemplateFile], r13; hTemplateFile
0x18002219b  mov     [rsp+1130h+dwFlagsAndAttributes], 3; dwFlagsAndAttributes
0x1800221a3  mov     r15d, 1
0x1800221a9  mov     [rsp+1130h+dwCreationDisposition], r15d; dwCreationDisposition
0x1800221ae  xor     r9d, r9d; lpSecurityAttributes
0x1800221b1  xor     r8d, r8d; dwShareMode
0x1800221b4  mov     edx, 0C0000000h; dwDesiredAccess
0x1800221b9  mov     rcx, [rbp+1030h+lpFileName]; lpFileName
0x1800221bd  call    cs:__imp_CreateFileW
0x1800221c4  nop     dword ptr [rax+rax+00h]
0x1800221c9  mov     rdi, rax
0x1800221cc  inc     rax
0x1800221cf  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800221d5  jnz     short loc_18002220D
0x1800221d7  call    cs:__imp_GetLastError
0x1800221de  nop     dword ptr [rax+rax+00h]
0x1800221e3  mov     esi, eax
0x1800221e5  cmp     eax, 50h ; 'P'
0x1800221e8  jz      short loc_18002220D
0x1800221ea  test    eax, eax
0x1800221ec  jle     short loc_1800221F7
0x1800221ee  movzx   esi, ax
0x1800221f1  or      esi, 80070000h
0x1800221f7  mov     [rsp+1130h+var_10D0], esi
0x1800221fb  mov     eax, 113Fh
0x180022200  test    esi, esi
0x180022202  js      loc_1800220B9
0x180022208  mov     [rsp+1130h+var_10CC], ax
0x18002220d  mov     r9, [rbp+1030h+var_1090]
0x180022211  mov     r8, r12
0x180022214  lea     rdx, aAutorunLabelSI; "[autorun]\r\nlabel=%s\r\nicon=%s,0\r\n"...
0x18002221b  lea     rcx, [rbp+1030h+lpWideCharStr]; this
0x18002221f  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x180022224  mov     esi, eax
0x180022226  mov     [rsp+1130h+var_10D0], eax
0x18002222a  test    eax, eax
0x18002222c  mov     eax, 114Ch
0x180022231  js      loc_1800220B9
0x180022237  mov     [rsp+1130h+var_10CC], ax
0x18002223c  call    cs:__imp_GetACP
0x180022243  nop     dword ptr [rax+rax+00h]
0x180022248  mov     [rsp+1130h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18002224d  lea     rcx, DefaultChar; "_"
0x180022254  mov     [rsp+1130h+hTemplateFile], rcx; lpDefaultChar
0x180022259  mov     [rsp+1130h+dwFlagsAndAttributes], 1000h; cbMultiByte
0x180022261  lea     rcx, [rbp+1030h+MultiByteStr]
0x180022265  mov     qword ptr [rsp+1130h+dwCreationDisposition], rcx; lpMultiByteStr
0x18002226a  mov     r9d, r14d; cchWideChar
0x18002226d  mov     r8, [rbp+1030h+lpWideCharStr]; lpWideCharStr
0x180022271  xor     edx, edx; dwFlags
0x180022273  mov     ecx, eax; CodePage
0x180022275  call    cs:__imp_WideCharToMultiByte
0x18002227c  nop     dword ptr [rax+rax+00h]
0x180022281  test    eax, eax
0x180022283  jnz     short loc_18002229A
0x180022285  call    GetLastFailureAsHRESULT
0x18002228a  mov     esi, eax
0x18002228c  mov     [rsp+1130h+var_10D0], eax
0x180022290  mov     eax, 1152h
0x180022295  jmp     loc_1800220B9
0x18002229a  mov     [rsp+1130h+var_10D0], r13d
0x18002229f  mov     eax, 1152h
0x1800222a4  mov     [rsp+1130h+var_10CC], ax
0x1800222a9  mov     [rsp+1130h+hTemplateFile], r13; hTemplateFile
0x1800222ae  mov     [rsp+1130h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800222b6  mov     [rsp+1130h+dwCreationDisposition], r15d; dwCreationDisposition
0x1800222bb  xor     r9d, r9d; lpSecurityAttributes
0x1800222be  xor     r8d, r8d; dwShareMode
0x1800222c1  mov     edx, 0C0000000h; dwDesiredAccess
0x1800222c6  mov     rcx, [rbp+1030h+var_1060]; lpFileName
0x1800222ca  call    cs:__imp_CreateFileW
0x1800222d1  nop     dword ptr [rax+rax+00h]
0x1800222d6  mov     rbx, rax
0x1800222d9  inc     rax
0x1800222dc  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800222e2  jnz     short loc_180022329
0x1800222e4  call    cs:__imp_GetLastError
0x1800222eb  nop     dword ptr [rax+rax+00h]
0x1800222f0  mov     esi, eax
0x1800222f2  cmp     eax, 50h ; 'P'
0x1800222f5  jnz     short loc_180022306
0x1800222f7  mov     [rsp+1130h+var_10D0], r15d
0x1800222fc  mov     eax, 1167h
0x180022301  mov     esi, r15d
0x180022304  jmp     short loc_18002237B
0x180022306  test    eax, eax
0x180022308  jle     short loc_180022313
0x18002230a  movzx   esi, ax
0x18002230d  or      esi, 80070000h
0x180022313  mov     [rsp+1130h+var_10D0], esi
0x180022317  mov     eax, 1169h
0x18002231c  test    esi, esi
0x18002231e  js      loc_1800220B9
0x180022324  mov     [rsp+1130h+var_10CC], ax
0x180022329  lea     rax, [rbp+1030h+MultiByteStr]
0x18002232d  inc     r14
0x180022330  cmp     [rax+r14], r13b
0x180022334  jnz     short loc_18002232D
0x180022336  mov     r8d, r14d; nNumberOfBytesToWrite
0x180022339  mov     qword ptr [rsp+1130h+dwCreationDisposition], r13; lpOverlapped
0x18002233e  lea     r9, [rbp+1030h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180022342  lea     rdx, [rbp+1030h+MultiByteStr]; lpBuffer
0x180022346  mov     rcx, rbx; hFile
0x180022349  call    cs:__imp_WriteFile
0x180022350  nop     dword ptr [rax+rax+00h]
0x180022355  test    eax, eax
0x180022357  jnz     short loc_18002236E
0x180022359  call    GetLastFailureAsHRESULT
0x18002235e  mov     esi, eax
0x180022360  mov     [rsp+1130h+var_10D0], eax
0x180022364  mov     eax, 1170h
0x180022369  jmp     loc_1800220B9
0x18002236e  mov     [rsp+1130h+var_10D0], r13d
0x180022373  mov     eax, 1172h
0x180022378  mov     esi, r13d
0x18002237b  mov     [rsp+1130h+var_10CC], ax
0x180022380  lea     rcx, [rbp+1030h+var_1090]; this
0x180022384  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180022389  lea     rax, [rdi-1]
0x18002238d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180022391  ja      short loc_1800223A2
0x180022393  mov     rcx, rdi; hObject
0x180022396  call    cs:__imp_CloseHandle
0x18002239d  nop     dword ptr [rax+rax+00h]
0x1800223a2  lea     rax, [rbx-1]
0x1800223a6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800223aa  ja      short loc_1800223BB
0x1800223ac  mov     rcx, rbx; hObject
0x1800223af  call    cs:__imp_CloseHandle
0x1800223b6  nop     dword ptr [rax+rax+00h]
0x1800223bb  lea     rcx, [rbp+1030h+lpWideCharStr]; this
0x1800223bf  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800223c4  lea     rcx, [rbp+1030h+var_1050]; this
0x1800223c8  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800223cd  lea     rcx, [rbp+1030h+lpFileName]; this
0x1800223d1  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800223d6  lea     rcx, [rbp+1030h+var_1060]; this
0x1800223da  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800223df  lea     rcx, [rsp+1130h+var_10D0]; this
0x1800223e4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800223e9  mov     eax, esi
0x1800223eb  mov     rcx, [rbp+1030h+var_40]
0x1800223f2  xor     rcx, rsp; StackCookie
0x1800223f5  call    __security_check_cookie
0x1800223fa  mov     rbx, [rsp+1130h+arg_0]
0x180022402  add     rsp, 1100h
0x180022409  pop     r15
0x18002240b  pop     r14
0x18002240d  pop     r13
0x18002240f  pop     r12
0x180022411  pop     rdi
0x180022412  pop     rsi
0x180022413  pop     rbp
0x180022414  retn
```
