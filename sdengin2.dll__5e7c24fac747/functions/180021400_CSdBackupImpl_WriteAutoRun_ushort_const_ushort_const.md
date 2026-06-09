# CSdBackupImpl::_WriteAutoRun(ushort const *,ushort const *)

- ea: `0x180021400`
- end: `0x1800217e3`
- name: `?_WriteAutoRun@CSdBackupImpl@@AEAAJPEBG0@Z`
- size: `995`
- prototype: `__int64 __fastcall(CSdBackupImpl *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18001c978`

## callees

- `0x18001a0bc`
- `0x180021400`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x180099d58`
- `0x180099fd8`
- `0x18009a378`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`
- `0x1800c98f0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800215c1`
- `KERNEL32!CreateFileW` at `0x1800216b6`
- `KERNEL32!CreateFileW` at `0x1800215c1`
- `KERNEL32!CreateFileW` at `0x1800216b6`
- `KERNEL32!GetACP` at `0x180021634`
- `KERNEL32!GetACP` at `0x180021634`
- `KERNEL32!GetLastError` at `0x1800215d5`
- `KERNEL32!GetLastError` at `0x1800216ca`
- `KERNEL32!GetLastError` at `0x1800215d5`
- `KERNEL32!GetLastError` at `0x1800216ca`
- `KERNEL32!CloseHandle` at `0x180021770`
- `KERNEL32!CloseHandle` at `0x180021783`
- `KERNEL32!CloseHandle` at `0x180021770`
- `KERNEL32!CloseHandle` at `0x180021783`
- `KERNEL32!WriteFile` at `0x180021729`
- `KERNEL32!WriteFile` at `0x180021729`
- `KERNEL32!WideCharToMultiByte` at `0x180021667`
- `KERNEL32!WideCharToMultiByte` at `0x180021667`

## string_xrefs

- `0x180021448`: `CSdBackupImpl::_WriteAutoRun`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v28, "CSdBackupImpl::_WriteAutoRun", 4372, 1);
  v35[0] = (LPCWSTR)qword_1800E8530;
  v35[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  v36[0] = qword_1800E8530;
  v36[1] = 0;
  lpWideCharStr[0] = (LPCWCH)qword_1800E8530;
  lpWideCharStr[1] = 0;
  memset_0(MultiByteStr, 0, sizeof(MultiByteStr));
  v6 = -1;
  v7 = -1;
  FileW = -1;
  v32[0] = qword_1800E8530;
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
0x180021400  mov     [rsp-8+arg_0], rbx
0x180021405  push    rbp
0x180021406  push    rsi
0x180021407  push    rdi
0x180021408  push    r12
0x18002140a  push    r13
0x18002140c  push    r14
0x18002140e  push    r15
0x180021410  lea     rbp, [rsp-1000h]
0x180021418  mov     eax, 1100h
0x18002141d  call    _alloca_probe
0x180021422  sub     rsp, rax
0x180021425  mov     rax, cs:__security_cookie
0x18002142c  xor     rax, rsp
0x18002142f  mov     [rbp+1030h+var_40], rax
0x180021436  mov     r12, r8
0x180021439  mov     r15, rdx
0x18002143c  mov     r9d, 1; unsigned __int16
0x180021442  mov     r8d, 1114h; unsigned __int16
0x180021448  lea     rdx, aCsdbackupimplW_1; "CSdBackupImpl::_WriteAutoRun"
0x18002144f  lea     rcx, [rsp+1130h+var_10D0]; this
0x180021454  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180021459  lea     rsi, qword_1800E8530
0x180021460  mov     [rbp+1030h+var_1060], rsi
0x180021464  xor     r13d, r13d
0x180021467  mov     [rbp+1030h+var_1058], r13
0x18002146b  mov     [rbp+1030h+lpFileName], rsi
0x18002146f  mov     [rbp+1030h+var_1068], r13
0x180021473  mov     [rbp+1030h+var_1050], rsi
0x180021477  mov     [rbp+1030h+var_1048], r13
0x18002147b  mov     [rbp+1030h+lpWideCharStr], rsi
0x18002147f  mov     [rbp+1030h+var_1078], r13
0x180021483  xor     edx, edx; Val
0x180021485  mov     r8d, 1000h; Size
0x18002148b  lea     rcx, [rbp+1030h+MultiByteStr]; void *
0x18002148f  call    memset_0
0x180021494  or      r14, 0FFFFFFFFFFFFFFFFh
0x180021498  mov     rbx, r14
0x18002149b  mov     rdi, r14
0x18002149e  mov     [rbp+1030h+var_1090], rsi
0x1800214a2  mov     [rbp+1030h+var_1088], r13
0x1800214a6  mov     [rbp+1030h+NumberOfBytesWritten], r13d
0x1800214aa  mov     eax, 1120h
0x1800214af  test    r15, r15
0x1800214b2  jnz     short loc_1800214C7
0x1800214b4  mov     esi, 80070057h
0x1800214b9  mov     [rsp+1130h+var_10D0], esi
0x1800214bd  mov     [rsp+1130h+var_10CA], ax
0x1800214c2  jmp     loc_18002175A
0x1800214c7  mov     [rsp+1130h+var_10CC], ax
0x1800214cc  mov     eax, 1121h
0x1800214d1  test    r12, r12
0x1800214d4  jz      short loc_1800214B4
0x1800214d6  mov     [rsp+1130h+var_10D0], r13d
0x1800214db  mov     [rsp+1130h+var_10CC], ax
0x1800214e0  lea     r8, [rbp+1030h+var_1090]; struct CBsString *
0x1800214e4  mov     rdx, r15; unsigned __int16 *
0x1800214e7  call    ?_EnsureAutoRunIcon@CSdBackupImpl@@AEAAJPEBGPEAVCBsString@@@Z; CSdBackupImpl::_EnsureAutoRunIcon(ushort const *,CBsString *)
0x1800214ec  mov     esi, eax
0x1800214ee  mov     [rsp+1130h+var_10D0], eax
0x1800214f2  test    eax, eax
0x1800214f4  mov     eax, 1123h
0x1800214f9  js      short loc_1800214BD
0x1800214fb  mov     [rsp+1130h+var_10CC], ax
0x180021500  mov     qword ptr [rsp+1130h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x180021505  mov     qword ptr [rsp+1130h+dwCreationDisposition], r13; unsigned __int16 *
0x18002150a  xor     r9d, r9d; unsigned __int16 *
0x18002150d  lea     r8, aAutorunInf; "autorun.inf"
0x180021514  mov     rdx, r15; unsigned __int16 *
0x180021517  lea     rcx, [rbp+1030h+var_1060]; this
0x18002151b  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180021520  mov     esi, eax
0x180021522  mov     [rsp+1130h+var_10D0], eax
0x180021526  test    eax, eax
0x180021528  mov     eax, 1125h
0x18002152d  js      short loc_1800214BD
0x18002152f  mov     [rsp+1130h+var_10CC], ax
0x180021534  mov     qword ptr [rsp+1130h+dwFlagsAndAttributes], r13; unsigned __int16 *
0x180021539  mov     qword ptr [rsp+1130h+dwCreationDisposition], r13; unsigned __int16 *
0x18002153e  xor     r9d, r9d; unsigned __int16 *
0x180021541  lea     r8, aAutorunWbcat; "autorun.wbcat"
0x180021548  mov     rdx, r15; unsigned __int16 *
0x18002154b  lea     rcx, [rbp+1030h+lpFileName]; this
0x18002154f  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180021554  mov     esi, eax
0x180021556  mov     [rsp+1130h+var_10D0], eax
0x18002155a  test    eax, eax
0x18002155c  mov     eax, 1127h
0x180021561  js      loc_1800214BD
0x180021567  mov     [rsp+1130h+var_10CC], ax
0x18002156c  mov     r8d, 0D1h; uID
0x180021572  mov     rdx, cs:hInstance; hInstance
0x180021579  lea     rcx, [rbp+1030h+var_1050]; this
0x18002157d  call    ?LoadStringResource@CBsString@@QEAAJPEAUHINSTANCE__@@I@Z; CBsString::LoadStringResource(HINSTANCE__ *,uint)
0x180021582  mov     esi, eax
0x180021584  mov     [rsp+1130h+var_10D0], eax
0x180021588  test    eax, eax
0x18002158a  mov     eax, 1129h
0x18002158f  js      loc_1800214BD
0x180021595  mov     [rsp+1130h+var_10CC], ax
0x18002159a  mov     [rsp+1130h+hTemplateFile], r13; hTemplateFile
0x18002159f  mov     [rsp+1130h+dwFlagsAndAttributes], 3; dwFlagsAndAttributes
0x1800215a7  mov     r15d, 1
0x1800215ad  mov     [rsp+1130h+dwCreationDisposition], r15d; dwCreationDisposition
0x1800215b2  xor     r9d, r9d; lpSecurityAttributes
0x1800215b5  xor     r8d, r8d; dwShareMode
0x1800215b8  mov     edx, 0C0000000h; dwDesiredAccess
0x1800215bd  mov     rcx, [rbp+1030h+lpFileName]; lpFileName
0x1800215c1  call    cs:__imp_CreateFileW
0x1800215c7  mov     rdi, rax
0x1800215ca  inc     rax
0x1800215cd  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800215d3  jnz     short loc_180021605
0x1800215d5  call    cs:__imp_GetLastError
0x1800215db  mov     esi, eax
0x1800215dd  cmp     eax, 50h ; 'P'
0x1800215e0  jz      short loc_180021605
0x1800215e2  test    eax, eax
0x1800215e4  jle     short loc_1800215EF
0x1800215e6  movzx   esi, ax
0x1800215e9  or      esi, 80070000h
0x1800215ef  mov     [rsp+1130h+var_10D0], esi
0x1800215f3  mov     eax, 113Fh
0x1800215f8  test    esi, esi
0x1800215fa  js      loc_1800214BD
0x180021600  mov     [rsp+1130h+var_10CC], ax
0x180021605  mov     r9, [rbp+1030h+var_1090]
0x180021609  mov     r8, r12
0x18002160c  lea     rdx, aAutorunLabelSI; "[autorun]\r\nlabel=%s\r\nicon=%s,0\r\n"...
0x180021613  lea     rcx, [rbp+1030h+lpWideCharStr]; this
0x180021617  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x18002161c  mov     esi, eax
0x18002161e  mov     [rsp+1130h+var_10D0], eax
0x180021622  test    eax, eax
0x180021624  mov     eax, 114Ch
0x180021629  js      loc_1800214BD
0x18002162f  mov     [rsp+1130h+var_10CC], ax
0x180021634  call    cs:__imp_GetACP
0x18002163a  mov     [rsp+1130h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18002163f  lea     rcx, DefaultChar; "_"
0x180021646  mov     [rsp+1130h+hTemplateFile], rcx; lpDefaultChar
0x18002164b  mov     [rsp+1130h+dwFlagsAndAttributes], 1000h; cbMultiByte
0x180021653  lea     rcx, [rbp+1030h+MultiByteStr]
0x180021657  mov     qword ptr [rsp+1130h+dwCreationDisposition], rcx; lpMultiByteStr
0x18002165c  mov     r9d, r14d; cchWideChar
0x18002165f  mov     r8, [rbp+1030h+lpWideCharStr]; lpWideCharStr
0x180021663  xor     edx, edx; dwFlags
0x180021665  mov     ecx, eax; CodePage
0x180021667  call    cs:__imp_WideCharToMultiByte
0x18002166d  test    eax, eax
0x18002166f  jnz     short loc_180021686
0x180021671  call    GetLastFailureAsHRESULT
0x180021676  mov     esi, eax
0x180021678  mov     [rsp+1130h+var_10D0], eax
0x18002167c  mov     eax, 1152h
0x180021681  jmp     loc_1800214BD
0x180021686  mov     [rsp+1130h+var_10D0], r13d
0x18002168b  mov     eax, 1152h
0x180021690  mov     [rsp+1130h+var_10CC], ax
0x180021695  mov     [rsp+1130h+hTemplateFile], r13; hTemplateFile
0x18002169a  mov     [rsp+1130h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800216a2  mov     [rsp+1130h+dwCreationDisposition], r15d; dwCreationDisposition
0x1800216a7  xor     r9d, r9d; lpSecurityAttributes
0x1800216aa  xor     r8d, r8d; dwShareMode
0x1800216ad  mov     edx, 0C0000000h; dwDesiredAccess
0x1800216b2  mov     rcx, [rbp+1030h+var_1060]; lpFileName
0x1800216b6  call    cs:__imp_CreateFileW
0x1800216bc  mov     rbx, rax
0x1800216bf  inc     rax
0x1800216c2  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800216c8  jnz     short loc_180021709
0x1800216ca  call    cs:__imp_GetLastError
0x1800216d0  mov     esi, eax
0x1800216d2  cmp     eax, 50h ; 'P'
0x1800216d5  jnz     short loc_1800216E6
0x1800216d7  mov     [rsp+1130h+var_10D0], r15d
0x1800216dc  mov     eax, 1167h
0x1800216e1  mov     esi, r15d
0x1800216e4  jmp     short loc_180021755
0x1800216e6  test    eax, eax
0x1800216e8  jle     short loc_1800216F3
0x1800216ea  movzx   esi, ax
0x1800216ed  or      esi, 80070000h
0x1800216f3  mov     [rsp+1130h+var_10D0], esi
0x1800216f7  mov     eax, 1169h
0x1800216fc  test    esi, esi
0x1800216fe  js      loc_1800214BD
0x180021704  mov     [rsp+1130h+var_10CC], ax
0x180021709  lea     rax, [rbp+1030h+MultiByteStr]
0x18002170d  inc     r14
0x180021710  cmp     [rax+r14], r13b
0x180021714  jnz     short loc_18002170D
0x180021716  mov     r8d, r14d; nNumberOfBytesToWrite
0x180021719  mov     qword ptr [rsp+1130h+dwCreationDisposition], r13; lpOverlapped
0x18002171e  lea     r9, [rbp+1030h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180021722  lea     rdx, [rbp+1030h+MultiByteStr]; lpBuffer
0x180021726  mov     rcx, rbx; hFile
0x180021729  call    cs:__imp_WriteFile
0x18002172f  test    eax, eax
0x180021731  jnz     short loc_180021748
0x180021733  call    GetLastFailureAsHRESULT
0x180021738  mov     esi, eax
0x18002173a  mov     [rsp+1130h+var_10D0], eax
0x18002173e  mov     eax, 1170h
0x180021743  jmp     loc_1800214BD
0x180021748  mov     [rsp+1130h+var_10D0], r13d
0x18002174d  mov     eax, 1172h
0x180021752  mov     esi, r13d
0x180021755  mov     [rsp+1130h+var_10CC], ax
0x18002175a  lea     rcx, [rbp+1030h+var_1090]; this
0x18002175e  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180021763  lea     rax, [rdi-1]
0x180021767  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002176b  ja      short loc_180021776
0x18002176d  mov     rcx, rdi; hObject
0x180021770  call    cs:__imp_CloseHandle
0x180021776  lea     rax, [rbx-1]
0x18002177a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002177e  ja      short loc_180021789
0x180021780  mov     rcx, rbx; hObject
0x180021783  call    cs:__imp_CloseHandle
0x180021789  lea     rcx, [rbp+1030h+lpWideCharStr]; this
0x18002178d  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180021792  lea     rcx, [rbp+1030h+var_1050]; this
0x180021796  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18002179b  lea     rcx, [rbp+1030h+lpFileName]; this
0x18002179f  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800217a4  lea     rcx, [rbp+1030h+var_1060]; this
0x1800217a8  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800217ad  lea     rcx, [rsp+1130h+var_10D0]; this
0x1800217b2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800217b7  mov     eax, esi
0x1800217b9  mov     rcx, [rbp+1030h+var_40]
0x1800217c0  xor     rcx, rsp; StackCookie
0x1800217c3  call    __security_check_cookie
0x1800217c8  mov     rbx, [rsp+1130h+arg_0]
0x1800217d0  add     rsp, 1100h
0x1800217d7  pop     r15
0x1800217d9  pop     r14
0x1800217db  pop     r13
0x1800217dd  pop     r12
0x1800217df  pop     rdi
0x1800217e0  pop     rsi
0x1800217e1  pop     rbp
0x1800217e2  retn
```
