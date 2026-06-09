# VerInstallFileA

- ea: `0x180001a40`
- end: `0x180001d58`
- name: `VerInstallFileA`
- size: `792`
- prototype: `DWORD __stdcall(DWORD uFlags, LPCSTR szSrcFileName, LPCSTR szDestFileName, LPCSTR szSrcDir, LPCSTR szDestDir, LPCSTR szCurDir, LPSTR szTmpFile, PUINT puTmpFileLen)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x180001a40`
- `0x180002b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001abd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001abd`
- `ntdll!RtlAllocateHeap` at `0x180001bea`
- `ntdll!RtlAllocateHeap` at `0x180001bea`
- `ntdll!RtlFreeUnicodeString` at `0x180001af5`
- `ntdll!RtlFreeUnicodeString` at `0x180001b27`
- `ntdll!RtlFreeUnicodeString` at `0x180001b5c`
- `ntdll!RtlFreeUnicodeString` at `0x180001b66`
- `ntdll!RtlFreeUnicodeString` at `0x180001b9b`
- `ntdll!RtlFreeUnicodeString` at `0x180001ba5`
- `ntdll!RtlFreeUnicodeString` at `0x180001baf`
- `ntdll!RtlFreeUnicodeString` at `0x180001bfd`
- `ntdll!RtlFreeUnicodeString` at `0x180001c07`
- `ntdll!RtlFreeUnicodeString` at `0x180001c11`
- `ntdll!RtlFreeUnicodeString` at `0x180001c1b`
- `ntdll!RtlFreeUnicodeString` at `0x180001c25`
- `ntdll!RtlFreeUnicodeString` at `0x180001c50`
- `ntdll!RtlFreeUnicodeString` at `0x180001c5a`
- `ntdll!RtlFreeUnicodeString` at `0x180001c64`
- `ntdll!RtlFreeUnicodeString` at `0x180001c6e`
- `ntdll!RtlFreeUnicodeString` at `0x180001c78`
- `ntdll!RtlFreeUnicodeString` at `0x180001c82`
- `ntdll!RtlFreeUnicodeString` at `0x180001d0e`
- `ntdll!RtlFreeUnicodeString` at `0x180001d18`
- `ntdll!RtlFreeUnicodeString` at `0x180001d22`
- `ntdll!RtlFreeUnicodeString` at `0x180001d2c`
- `ntdll!RtlFreeUnicodeString` at `0x180001d36`
- `ntdll!RtlFreeUnicodeString` at `0x180001d40`
- `ntdll!RtlFreeUnicodeString` at `0x180001af5`
- `ntdll!RtlFreeUnicodeString` at `0x180001b27`
- `ntdll!RtlFreeUnicodeString` at `0x180001b5c`
- `ntdll!RtlFreeUnicodeString` at `0x180001b66`
- `ntdll!RtlFreeUnicodeString` at `0x180001b9b`
- `ntdll!RtlFreeUnicodeString` at `0x180001ba5`
- `ntdll!RtlFreeUnicodeString` at `0x180001baf`
- `ntdll!RtlFreeUnicodeString` at `0x180001bfd`
- `ntdll!RtlFreeUnicodeString` at `0x180001c07`
- `ntdll!RtlFreeUnicodeString` at `0x180001c11`
- `ntdll!RtlFreeUnicodeString` at `0x180001c1b`
- `ntdll!RtlFreeUnicodeString` at `0x180001c25`
- `ntdll!RtlFreeUnicodeString` at `0x180001c50`
- `ntdll!RtlFreeUnicodeString` at `0x180001c5a`
- `ntdll!RtlFreeUnicodeString` at `0x180001c64`
- `ntdll!RtlFreeUnicodeString` at `0x180001c6e`
- `ntdll!RtlFreeUnicodeString` at `0x180001c78`
- `ntdll!RtlFreeUnicodeString` at `0x180001c82`
- `ntdll!RtlFreeUnicodeString` at `0x180001d0e`
- `ntdll!RtlFreeUnicodeString` at `0x180001d18`
- `ntdll!RtlFreeUnicodeString` at `0x180001d22`
- `ntdll!RtlFreeUnicodeString` at `0x180001d2c`
- `ntdll!RtlFreeUnicodeString` at `0x180001d36`
- `ntdll!RtlFreeUnicodeString` at `0x180001d40`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001ab1`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001ae5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001b17`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001b4c`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001b8b`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001c40`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001ab1`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001ae5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001b17`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001b4c`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001b8b`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001c40`
- `ntdll!RtlInitAnsiString` at `0x180001aa0`
- `ntdll!RtlInitAnsiString` at `0x180001ad4`
- `ntdll!RtlInitAnsiString` at `0x180001b06`
- `ntdll!RtlInitAnsiString` at `0x180001b3b`
- `ntdll!RtlInitAnsiString` at `0x180001b7a`
- `ntdll!RtlInitAnsiString` at `0x180001bc9`
- `ntdll!RtlInitAnsiString` at `0x180001aa0`
- `ntdll!RtlInitAnsiString` at `0x180001ad4`
- `ntdll!RtlInitAnsiString` at `0x180001b06`
- `ntdll!RtlInitAnsiString` at `0x180001b3b`
- `ntdll!RtlInitAnsiString` at `0x180001b7a`
- `ntdll!RtlInitAnsiString` at `0x180001bc9`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180001cfe`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180001cfe`

## pseudocode

```c
DWORD __stdcall VerInstallFileA(
        DWORD uFlags,
        LPCSTR szSrcFileName,
        LPCSTR szDestFileName,
        LPCSTR szSrcDir,
        LPCSTR szDestDir,
        LPCSTR szCurDir,
        LPSTR szTmpFile,
        PUINT puTmpFileLen)
{
  USHORT *v8; // rsi
  unsigned int v10; // edi
  bool v12; // zf
  NTSTATUS v14; // eax
  DWORD v15; // ecx
  NTSTATUS v17; // ebx
  struct _UNICODE_STRING *p_UnicodeString; // rcx
  NTSTATUS v19; // edi
  DWORD v20; // edi
  int v21; // ecx
  _STRING DestinationString; // [rsp+40h] [rbp-69h] BYREF
  _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-59h] BYREF
  UNICODE_STRING SourceString; // [rsp+60h] [rbp-49h] BYREF
  struct _UNICODE_STRING v25; // [rsp+70h] [rbp-39h] BYREF
  struct _UNICODE_STRING v26; // [rsp+80h] [rbp-29h] BYREF
  struct _UNICODE_STRING v27; // [rsp+90h] [rbp-19h] BYREF
  struct _UNICODE_STRING v28; // [rsp+A0h] [rbp-9h] BYREF

  v8 = (USHORT *)puTmpFileLen;
  v10 = 1;
  v12 = *puTmpFileLen == 0;
  UnicodeString = 0;
  if ( !v12 )
    v10 = *puTmpFileLen;
  v25 = 0;
  if ( v10 > 0x104 )
    v10 = 260;
  LODWORD(puTmpFileLen) = v10;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  SourceString = 0;
  DestinationString = 0;
  RtlInitAnsiString(&DestinationString, szSrcFileName);
  v14 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
  if ( v14 < 0 )
  {
    v15 = v14;
LABEL_7:
    SetLastError(v15);
    return 0x8000;
  }
  RtlInitAnsiString(&DestinationString, szDestFileName);
  v17 = RtlAnsiStringToUnicodeString(&v25, &DestinationString, 1u);
  if ( v17 < 0 )
  {
    p_UnicodeString = &UnicodeString;
LABEL_10:
    RtlFreeUnicodeString(p_UnicodeString);
    v15 = v17;
    goto LABEL_7;
  }
  RtlInitAnsiString(&DestinationString, szSrcDir);
  v17 = RtlAnsiStringToUnicodeString(&v26, &DestinationString, 1u);
  if ( v17 < 0 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    p_UnicodeString = &v25;
    goto LABEL_10;
  }
  RtlInitAnsiString(&DestinationString, szCurDir);
  v17 = RtlAnsiStringToUnicodeString(&v27, &DestinationString, 1u);
  if ( v17 < 0 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    RtlFreeUnicodeString(&v25);
    p_UnicodeString = &v26;
    goto LABEL_10;
  }
  RtlInitAnsiString(&DestinationString, szDestDir);
  v17 = RtlAnsiStringToUnicodeString(&v28, &DestinationString, 1u);
  if ( v17 < 0 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    RtlFreeUnicodeString(&v25);
    RtlFreeUnicodeString(&v26);
    p_UnicodeString = &v27;
    goto LABEL_10;
  }
  RtlInitAnsiString(&DestinationString, szTmpFile);
  SourceString.MaximumLength = 2 * v10;
  SourceString.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned __int16)(2 * v10));
  if ( !SourceString.Buffer )
  {
    RtlFreeUnicodeString(&UnicodeString);
    RtlFreeUnicodeString(&v25);
    RtlFreeUnicodeString(&v26);
    RtlFreeUnicodeString(&v27);
    RtlFreeUnicodeString(&v28);
    v15 = 8;
    goto LABEL_7;
  }
  v19 = RtlAnsiStringToUnicodeString(&SourceString, &DestinationString, 0);
  if ( v19 < 0 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    RtlFreeUnicodeString(&v25);
    RtlFreeUnicodeString(&v26);
    RtlFreeUnicodeString(&v27);
    RtlFreeUnicodeString(&v28);
    RtlFreeUnicodeString(&SourceString);
    v15 = v19;
    goto LABEL_7;
  }
  v20 = VerInstallFileW(
          uFlags,
          UnicodeString.Buffer,
          v25.Buffer,
          v26.Buffer,
          v28.Buffer,
          v27.Buffer,
          SourceString.Buffer,
          (PUINT)&puTmpFileLen);
  if ( (v20 & 0x40000) != 0 )
  {
    v21 = (int)puTmpFileLen;
    *szTmpFile = 0;
    *(_DWORD *)v8 = v21;
  }
  else
  {
    DestinationString.Buffer = szTmpFile;
    SourceString.MaximumLength = 2 * (_WORD)puTmpFileLen;
    SourceString.Length = 2 * (_WORD)puTmpFileLen;
    DestinationString.MaximumLength = *v8;
    RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 0);
    *(_DWORD *)v8 = DestinationString.Length;
  }
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v25);
  RtlFreeUnicodeString(&v26);
  RtlFreeUnicodeString(&v28);
  RtlFreeUnicodeString(&v27);
  RtlFreeUnicodeString(&SourceString);
  return v20;
}

```

## disassembly

```asm
0x180001a40  push    rbp
0x180001a42  push    rbx
0x180001a43  push    rsi
0x180001a44  push    rdi
0x180001a45  push    r14
0x180001a47  push    r15
0x180001a49  lea     rbp, [rsp-0Fh]
0x180001a4e  sub     rsp, 0B8h
0x180001a55  mov     rsi, [rbp+37h+puTmpFileLen]
0x180001a59  xorps   xmm0, xmm0
0x180001a5c  xorps   xmm1, xmm1
0x180001a5f  mov     eax, 104h
0x180001a64  mov     r15d, ecx
0x180001a67  mov     edi, 1
0x180001a6c  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x180001a70  mov     r14, r9
0x180001a73  cmp     dword ptr [rsi], 0
0x180001a76  mov     rbx, r8
0x180001a79  movups  xmmword ptr [rbp+37h+UnicodeString.Length], xmm0
0x180001a7d  cmovnz  edi, [rsi]
0x180001a80  cmp     edi, eax
0x180001a82  movups  xmmword ptr [rbp+37h+var_70.Length], xmm1
0x180001a86  cmova   edi, eax
0x180001a89  mov     dword ptr [rbp+37h+puTmpFileLen], edi
0x180001a8c  movups  xmmword ptr [rbp+37h+var_60.Length], xmm0
0x180001a90  movups  xmmword ptr [rbp+37h+var_50.Length], xmm1
0x180001a94  movups  xmmword ptr [rbp+37h+var_40.Length], xmm0
0x180001a98  movups  xmmword ptr [rbp+37h+SourceString.Length], xmm1
0x180001a9c  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x180001aa0  call    cs:__imp_RtlInitAnsiString
0x180001aa6  mov     r8b, 1; AllocateDestinationString
0x180001aa9  lea     rdx, [rbp+37h+DestinationString]; SourceString
0x180001aad  lea     rcx, [rbp+37h+UnicodeString]; DestinationString
0x180001ab1  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180001ab7  test    eax, eax
0x180001ab9  jns     short loc_180001ACD
0x180001abb  mov     ecx, eax; dwErrCode
0x180001abd  call    cs:__imp_SetLastError
0x180001ac3  mov     eax, 8000h
0x180001ac8  jmp     loc_180001D48
0x180001acd  mov     rdx, rbx; SourceString
0x180001ad0  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x180001ad4  call    cs:__imp_RtlInitAnsiString
0x180001ada  mov     r8b, 1; AllocateDestinationString
0x180001add  lea     rdx, [rbp+37h+DestinationString]; SourceString
0x180001ae1  lea     rcx, [rbp+37h+var_70]; DestinationString
0x180001ae5  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180001aeb  mov     ebx, eax
0x180001aed  test    eax, eax
0x180001aef  jns     short loc_180001AFF
0x180001af1  lea     rcx, [rbp+37h+UnicodeString]; UnicodeString
0x180001af5  call    cs:__imp_RtlFreeUnicodeString
0x180001afb  mov     ecx, ebx
0x180001afd  jmp     short loc_180001ABD
0x180001aff  mov     rdx, r14; SourceString
0x180001b02  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x180001b06  call    cs:__imp_RtlInitAnsiString
0x180001b0c  mov     r8b, 1; AllocateDestinationString
0x180001b0f  lea     rdx, [rbp+37h+DestinationString]; SourceString
0x180001b13  lea     rcx, [rbp+37h+var_60]; DestinationString
0x180001b17  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180001b1d  mov     ebx, eax
0x180001b1f  test    eax, eax
0x180001b21  jns     short loc_180001B33
0x180001b23  lea     rcx, [rbp+37h+UnicodeString]; UnicodeString
0x180001b27  call    cs:__imp_RtlFreeUnicodeString
0x180001b2d  lea     rcx, [rbp+37h+var_70]
0x180001b31  jmp     short loc_180001AF5
0x180001b33  mov     rdx, [rbp+37h+szCurDir]; SourceString
0x180001b37  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x180001b3b  call    cs:__imp_RtlInitAnsiString
0x180001b41  mov     r8b, 1; AllocateDestinationString
0x180001b44  lea     rdx, [rbp+37h+DestinationString]; SourceString
0x180001b48  lea     rcx, [rbp+37h+var_50]; DestinationString
0x180001b4c  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180001b52  mov     ebx, eax
0x180001b54  test    eax, eax
0x180001b56  jns     short loc_180001B72
0x180001b58  lea     rcx, [rbp+37h+UnicodeString]; UnicodeString
0x180001b5c  call    cs:__imp_RtlFreeUnicodeString
0x180001b62  lea     rcx, [rbp+37h+var_70]; UnicodeString
0x180001b66  call    cs:__imp_RtlFreeUnicodeString
0x180001b6c  lea     rcx, [rbp+37h+var_60]
0x180001b70  jmp     short loc_180001AF5
0x180001b72  mov     rdx, [rbp+37h+szDestDir]; SourceString
0x180001b76  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x180001b7a  call    cs:__imp_RtlInitAnsiString
0x180001b80  mov     r8b, 1; AllocateDestinationString
0x180001b83  lea     rdx, [rbp+37h+DestinationString]; SourceString
0x180001b87  lea     rcx, [rbp+37h+var_40]; DestinationString
0x180001b8b  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180001b91  mov     ebx, eax
0x180001b93  test    eax, eax
0x180001b95  jns     short loc_180001BBE
0x180001b97  lea     rcx, [rbp+37h+UnicodeString]; UnicodeString
0x180001b9b  call    cs:__imp_RtlFreeUnicodeString
0x180001ba1  lea     rcx, [rbp+37h+var_70]; UnicodeString
0x180001ba5  call    cs:__imp_RtlFreeUnicodeString
0x180001bab  lea     rcx, [rbp+37h+var_60]; UnicodeString
0x180001baf  call    cs:__imp_RtlFreeUnicodeString
0x180001bb5  lea     rcx, [rbp+37h+var_50]
0x180001bb9  jmp     loc_180001AF5
0x180001bbe  mov     rbx, [rbp+37h+szTmpFile]
0x180001bc2  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x180001bc6  mov     rdx, rbx; SourceString
0x180001bc9  call    cs:__imp_RtlInitAnsiString
0x180001bcf  add     di, di
0x180001bd2  xor     edx, edx; Flags
0x180001bd4  movzx   r8d, di; Size
0x180001bd8  mov     [rbp+37h+SourceString.MaximumLength], r8w
0x180001bdd  mov     rcx, gs:60h
0x180001be6  mov     rcx, [rcx+30h]; HeapHandle
0x180001bea  call    cs:__imp_RtlAllocateHeap
0x180001bf0  mov     [rbp+37h+SourceString.Buffer], rax
0x180001bf4  test    rax, rax
0x180001bf7  jnz     short loc_180001C35
0x180001bf9  lea     rcx, [rbp+37h+UnicodeString]; UnicodeString
0x180001bfd  call    cs:__imp_RtlFreeUnicodeString
0x180001c03  lea     rcx, [rbp+37h+var_70]; UnicodeString
0x180001c07  call    cs:__imp_RtlFreeUnicodeString
0x180001c0d  lea     rcx, [rbp+37h+var_60]; UnicodeString
0x180001c11  call    cs:__imp_RtlFreeUnicodeString
0x180001c17  lea     rcx, [rbp+37h+var_50]; UnicodeString
0x180001c1b  call    cs:__imp_RtlFreeUnicodeString
0x180001c21  lea     rcx, [rbp+37h+var_40]; UnicodeString
0x180001c25  call    cs:__imp_RtlFreeUnicodeString
0x180001c2b  mov     ecx, 8
0x180001c30  jmp     loc_180001ABD
0x180001c35  xor     r8d, r8d; AllocateDestinationString
0x180001c38  lea     rdx, [rbp+37h+DestinationString]; SourceString
0x180001c3c  lea     rcx, [rbp+37h+SourceString]; DestinationString
0x180001c40  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180001c46  mov     edi, eax
0x180001c48  test    eax, eax
0x180001c4a  jns     short loc_180001C8F
0x180001c4c  lea     rcx, [rbp+37h+UnicodeString]; UnicodeString
0x180001c50  call    cs:__imp_RtlFreeUnicodeString
0x180001c56  lea     rcx, [rbp+37h+var_70]; UnicodeString
0x180001c5a  call    cs:__imp_RtlFreeUnicodeString
0x180001c60  lea     rcx, [rbp+37h+var_60]; UnicodeString
0x180001c64  call    cs:__imp_RtlFreeUnicodeString
0x180001c6a  lea     rcx, [rbp+37h+var_50]; UnicodeString
0x180001c6e  call    cs:__imp_RtlFreeUnicodeString
0x180001c74  lea     rcx, [rbp+37h+var_40]; UnicodeString
0x180001c78  call    cs:__imp_RtlFreeUnicodeString
0x180001c7e  lea     rcx, [rbp+37h+SourceString]; UnicodeString
0x180001c82  call    cs:__imp_RtlFreeUnicodeString
0x180001c88  mov     ecx, edi
0x180001c8a  jmp     loc_180001ABD
0x180001c8f  mov     r9, [rbp+37h+var_60.Buffer]; szSrcDir
0x180001c93  lea     rax, [rbp+37h+puTmpFileLen]
0x180001c97  mov     r8, [rbp+37h+var_70.Buffer]; szDestFileName
0x180001c9b  mov     ecx, r15d; uFlags
0x180001c9e  mov     rdx, [rbp+37h+UnicodeString.Buffer]; szSrcFileName
0x180001ca2  mov     [rsp+0E0h+var_A8], rax; puTmpFileLen
0x180001ca7  mov     rax, [rbp+37h+SourceString.Buffer]
0x180001cab  mov     [rsp+0E0h+var_B0], rax; szTmpFile
0x180001cb0  mov     rax, [rbp+37h+var_50.Buffer]
0x180001cb4  mov     [rsp+0E0h+var_B8], rax; szCurDir
0x180001cb9  mov     rax, [rbp+37h+var_40.Buffer]
0x180001cbd  mov     [rsp+0E0h+var_C0], rax; szDestDir
0x180001cc2  call    VerInstallFileW
0x180001cc7  mov     edi, eax
0x180001cc9  bt      eax, 12h
0x180001ccd  jnb     short loc_180001CD9
0x180001ccf  mov     ecx, dword ptr [rbp+37h+puTmpFileLen]
0x180001cd2  mov     byte ptr [rbx], 0
0x180001cd5  mov     [rsi], ecx
0x180001cd7  jmp     short loc_180001D0A
0x180001cd9  movzx   eax, word ptr [rbp+37h+puTmpFileLen]
0x180001cdd  lea     rdx, [rbp+37h+SourceString]; SourceString
0x180001ce1  add     ax, ax
0x180001ce4  mov     [rbp+37h+DestinationString.Buffer], rbx
0x180001ce8  mov     [rbp+37h+SourceString.MaximumLength], ax
0x180001cec  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x180001cf0  mov     [rbp+37h+SourceString.Length], ax
0x180001cf4  xor     r8d, r8d; AllocateDestinationString
0x180001cf7  movzx   eax, word ptr [rsi]
0x180001cfa  mov     [rbp+37h+DestinationString.MaximumLength], ax
0x180001cfe  call    cs:__imp_RtlUnicodeStringToAnsiString
0x180001d04  movzx   eax, [rbp+37h+DestinationString.Length]
0x180001d08  mov     [rsi], eax
0x180001d0a  lea     rcx, [rbp+37h+UnicodeString]; UnicodeString
0x180001d0e  call    cs:__imp_RtlFreeUnicodeString
0x180001d14  lea     rcx, [rbp+37h+var_70]; UnicodeString
0x180001d18  call    cs:__imp_RtlFreeUnicodeString
0x180001d1e  lea     rcx, [rbp+37h+var_60]; UnicodeString
0x180001d22  call    cs:__imp_RtlFreeUnicodeString
0x180001d28  lea     rcx, [rbp+37h+var_40]; UnicodeString
0x180001d2c  call    cs:__imp_RtlFreeUnicodeString
0x180001d32  lea     rcx, [rbp+37h+var_50]; UnicodeString
0x180001d36  call    cs:__imp_RtlFreeUnicodeString
0x180001d3c  lea     rcx, [rbp+37h+SourceString]; UnicodeString
0x180001d40  call    cs:__imp_RtlFreeUnicodeString
0x180001d46  mov     eax, edi
0x180001d48  add     rsp, 0B8h
0x180001d4f  pop     r15
0x180001d51  pop     r14
0x180001d53  pop     rdi
0x180001d54  pop     rsi
0x180001d55  pop     rbx
0x180001d56  pop     rbp
0x180001d57  retn
```
