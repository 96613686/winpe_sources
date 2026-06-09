# CDlpHelpersT<CEmptyType>::GetFileSize(ushort const *,_LARGE_INTEGER *)

- ea: `0x18001ad34`
- end: `0x18001ae25`
- name: `?GetFileSize@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBGPEAT_LARGE_INTEGER@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180017b4c`
- `0x1800190f0`
- `0x18001b484`
- `0x18002beb4`
- `0x18002ca00`
- `0x18002cd9c`
- `0x1800309dc`

## callees

- `0x18000aba4`
- `0x18001ad34`
- `0x18001fd60`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18001adc3`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18001adc3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ad87`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ad87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ad9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001adcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ae0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ae0d`

## pseudocode

```c
__int64 __fastcall CDlpHelpersT<CEmptyType>::GetFileSize(const WCHAR *a1, union _LARGE_INTEGER *a2)
{
  __int64 v2; // rbx
  int v4; // ecx
  unsigned int v5; // edi
  HANDLE FileW; // rsi
  signed int LastError; // eax
  signed int v8; // eax

  v2 = -1;
  if ( !a1 || !a2 )
  {
    v4 = -2147024809;
    v5 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_19;
  }
  FileW = CreateFileW(a1, 0, 7u, 0, 3u, 0x80u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    v4 = v5;
    goto LABEL_3;
  }
  if ( GetFileSizeEx(FileW, a2) )
  {
    v5 = 0;
  }
  else
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
  }
  v2 = (__int64)FileW;
LABEL_19:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v2);
  return v5;
}

```

## disassembly

```asm
0x18001ad34  mov     [rsp+arg_0], rbx
0x18001ad39  mov     [rsp+arg_8], rsi
0x18001ad3e  push    rdi
0x18001ad3f  sub     rsp, 40h
0x18001ad43  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ad47  mov     rdi, rdx
0x18001ad4a  test    rcx, rcx
0x18001ad4d  jnz     short loc_18001AD60
0x18001ad4f  mov     ecx, 80070057h
0x18001ad54  mov     edi, ecx
0x18001ad56  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001ad5b  jmp     loc_18001ADF9
0x18001ad60  test    rdi, rdi
0x18001ad63  jz      short loc_18001AD4F
0x18001ad65  xor     r9d, r9d; lpSecurityAttributes
0x18001ad68  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18001ad71  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001ad79  xor     edx, edx; dwDesiredAccess
0x18001ad7b  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18001ad83  lea     r8d, [r9+7]; dwShareMode
0x18001ad87  call    cs:__imp_CreateFileW
0x18001ad8d  mov     rsi, rax
0x18001ad90  inc     rax
0x18001ad93  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001ad99  jnz     short loc_18001ADBD
0x18001ad9b  call    cs:__imp_GetLastError
0x18001ada1  mov     edi, eax
0x18001ada3  test    eax, eax
0x18001ada5  jnz     short loc_18001ADAE
0x18001ada7  mov     edi, 80004005h
0x18001adac  jmp     short loc_18001ADB9
0x18001adae  jle     short loc_18001ADB9
0x18001adb0  movzx   edi, ax
0x18001adb3  or      edi, 80070000h
0x18001adb9  mov     ecx, edi
0x18001adbb  jmp     short loc_18001AD56
0x18001adbd  mov     rcx, rsi; hFile
0x18001adc0  mov     rdx, rdi; lpFileSize
0x18001adc3  call    cs:__imp_GetFileSizeEx
0x18001adc9  test    eax, eax
0x18001adcb  jnz     short loc_18001ADF4
0x18001adcd  call    cs:__imp_GetLastError
0x18001add3  mov     edi, eax
0x18001add5  test    eax, eax
0x18001add7  jnz     short loc_18001ADE0
0x18001add9  mov     edi, 80004005h
0x18001adde  jmp     short loc_18001ADEB
0x18001ade0  jle     short loc_18001ADEB
0x18001ade2  movzx   edi, ax
0x18001ade5  or      edi, 80070000h
0x18001adeb  mov     ecx, edi
0x18001aded  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001adf2  jmp     short loc_18001ADF6
0x18001adf4  xor     edi, edi
0x18001adf6  mov     rbx, rsi
0x18001adf9  mov     ecx, edi
0x18001adfb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001ae00  lea     rcx, [rbx-1]
0x18001ae04  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001ae08  ja      short loc_18001AE13
0x18001ae0a  mov     rcx, rbx; hObject
0x18001ae0d  call    cs:__imp_CloseHandle
0x18001ae13  mov     rbx, [rsp+48h+arg_0]
0x18001ae18  mov     eax, edi
0x18001ae1a  mov     rsi, [rsp+48h+arg_8]
0x18001ae1f  add     rsp, 40h
0x18001ae23  pop     rdi
0x18001ae24  retn
```
