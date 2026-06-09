# CSetupLogging::CreateLogFile(void)

- ea: `0x180037c08`
- end: `0x180037def`
- name: `?CreateLogFile@CSetupLogging@@AEAAXXZ`
- size: `487`
- prototype: `void __fastcall(CSetupLogging *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x180036e6c`

## callees

- `0x180007824`
- `0x18000dd78`
- `0x1800363c0`
- `0x180037c08`
- `0x180043118`
- `0x18004d030`
- `0x18004d350`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180037d45`
- `KERNEL32!GetLastError` at `0x180037d45`
- `KERNEL32!CreateFileW` at `0x180037da3`
- `KERNEL32!CreateFileW` at `0x180037da3`
- `KERNEL32!FindClose` at `0x180037dc2`
- `KERNEL32!FindClose` at `0x180037dc2`
- `KERNEL32!FindFirstFileW` at `0x180037cf7`
- `KERNEL32!FindFirstFileW` at `0x180037cf7`
- `KERNEL32!FindNextFileW` at `0x180037d3b`
- `KERNEL32!FindNextFileW` at `0x180037d3b`

## pseudocode

```c
void __fastcall CSetupLogging::CreateLogFile(CSetupLogging *this)
{
  char *FirstFileW; // rbx
  signed int v3; // esi
  __int64 v4; // r8
  WCHAR *v5; // rcx
  WCHAR v6; // ax
  WCHAR *v7; // rax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  signed int v9; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR FileName[520]; // [rsp+4B0h] [rbp+3B0h] BYREF

  *(_QWORD *)this = 0;
  FirstFileW = 0;
  v3 = 0;
  memset_0(Buffer, 0, 0x20Au);
  if ( !SecureGetTempPath(0x104u, Buffer) )
  {
LABEL_2:
    GetLastWin32Error();
    goto LABEL_20;
  }
  v4 = 520;
  v5 = FileName;
  do
  {
    if ( v4 == -2147483126 )
      break;
    v6 = *(v5 - 264);
    if ( !v6 )
      break;
    *v5++ = v6;
    --v4;
  }
  while ( v4 );
  v7 = v5 - 1;
  if ( v4 )
    v7 = v5;
  *v7 = 0;
  if ( v4 && !(unsigned int)StringCchCatW(FileName, 0x208u, L"\\ASPNETSetup_*.log") )
  {
    FirstFileW = (char *)FindFirstFileW(FileName, &FindFileData);
    if ( FirstFileW != (char *)-1LL )
    {
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0
          && swscanf_s(FindFileData.cFileName, L"ASPNETSetup_%d.log", &v9) == 1
          && v9 >= v3 )
        {
          v3 = v9 + 1;
        }
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      if ( GetLastError() != 18 )
        goto LABEL_2;
    }
    dwCreationDisposition = v3;
    if ( !(unsigned int)StringCchPrintfW(
                          &CSetupLogging::m_szFileName,
                          0x11Au,
                          L"%sASPNETSetup_%05d.log",
                          Buffer,
                          dwCreationDisposition) )
      *(_QWORD *)this = CreateFileW(&CSetupLogging::m_szFileName, 0x40000000u, 3u, 0, 2u, 0x80000080, 0);
  }
LABEL_20:
  if ( *(_QWORD *)this == -1 )
    *(_QWORD *)this = 0;
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose(FirstFileW);
}

```

## disassembly

```asm
0x180037c08  mov     [rsp-8+arg_8], rbx
0x180037c0d  mov     [rsp-8+arg_10], rsi
0x180037c12  push    rbp
0x180037c13  push    rdi
0x180037c14  push    r14
0x180037c16  lea     rbp, [rsp-7D0h]
0x180037c1e  sub     rsp, 8D0h
0x180037c25  mov     rax, cs:__security_cookie
0x180037c2c  xor     rax, rsp
0x180037c2f  mov     [rbp+7E0h+var_20], rax
0x180037c36  xor     r14d, r14d
0x180037c39  mov     rdi, rcx
0x180037c3c  mov     [rcx], r14
0x180037c3f  xor     edx, edx; Val
0x180037c41  lea     rcx, [rbp+7E0h+Buffer]; void *
0x180037c48  mov     r8d, 20Ah; Size
0x180037c4e  mov     ebx, r14d
0x180037c51  mov     esi, r14d
0x180037c54  call    memset_0
0x180037c59  lea     rdx, [rbp+7E0h+Buffer]; lpBuffer
0x180037c60  mov     ecx, 104h; nBufferLength
0x180037c65  call    ?SecureGetTempPath@@YAKKPEAG@Z; SecureGetTempPath(ulong,ushort *)
0x180037c6a  test    eax, eax
0x180037c6c  jnz     short loc_180037C78
0x180037c6e  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180037c73  jmp     loc_180037DAC
0x180037c78  mov     edx, 208h; unsigned __int64
0x180037c7d  lea     r9, [rbp+7E0h+Buffer]
0x180037c84  lea     rax, [rbp+7E0h+FileName]
0x180037c8b  mov     r8d, edx
0x180037c8e  sub     r9, rax
0x180037c91  lea     rcx, [rbp+7E0h+FileName]
0x180037c98  lea     rax, [r8+7FFFFDF6h]
0x180037c9f  test    rax, rax
0x180037ca2  jz      short loc_180037CBB
0x180037ca4  movzx   eax, word ptr [r9+rcx]
0x180037ca9  test    ax, ax
0x180037cac  jz      short loc_180037CBB
0x180037cae  mov     [rcx], ax
0x180037cb1  add     rcx, 2
0x180037cb5  sub     r8, 1
0x180037cb9  jnz     short loc_180037C98
0x180037cbb  test    r8, r8
0x180037cbe  lea     rax, [rcx-2]
0x180037cc2  cmovnz  rax, rcx
0x180037cc6  mov     [rax], r14w
0x180037cca  jz      loc_180037DAC
0x180037cd0  lea     r8, aAspnetsetupLog; "\\ASPNETSetup_*.log"
0x180037cd7  lea     rcx, [rbp+7E0h+FileName]; unsigned __int16 *
0x180037cde  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037ce3  test    eax, eax
0x180037ce5  jnz     loc_180037DAC
0x180037ceb  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x180037cf0  lea     rcx, [rbp+7E0h+FileName]; lpFileName
0x180037cf7  call    cs:__imp_FindFirstFileW
0x180037cfd  mov     rbx, rax
0x180037d00  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037d04  jz      short loc_180037D54
0x180037d06  test    byte ptr [rsp+8E0h+FindFileData.dwFileAttributes], 10h
0x180037d0b  jnz     short loc_180037D33
0x180037d0d  lea     r8, [rsp+8E0h+var_8A0]
0x180037d12  lea     rdx, aAspnetsetupDLo; "ASPNETSetup_%d.log"
0x180037d19  lea     rcx, [rsp+8E0h+FindFileData.cFileName]; Buffer
0x180037d1e  call    swscanf_s
0x180037d23  cmp     eax, 1
0x180037d26  jnz     short loc_180037D33
0x180037d28  mov     eax, [rsp+8E0h+var_8A0]
0x180037d2c  cmp     eax, esi
0x180037d2e  jl      short loc_180037D33
0x180037d30  lea     esi, [rax+1]
0x180037d33  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x180037d38  mov     rcx, rbx; hFindFile
0x180037d3b  call    cs:__imp_FindNextFileW
0x180037d41  test    eax, eax
0x180037d43  jnz     short loc_180037D06
0x180037d45  call    cs:__imp_GetLastError
0x180037d4b  cmp     eax, 12h
0x180037d4e  jnz     loc_180037C6E
0x180037d54  lea     r9, [rbp+7E0h+Buffer]
0x180037d5b  mov     [rsp+8E0h+dwCreationDisposition], esi
0x180037d5f  lea     r8, aSaspnetsetup05; "%sASPNETSetup_%05d.log"
0x180037d66  mov     edx, 11Ah; unsigned __int64
0x180037d6b  lea     rcx, ?m_szFileName@CSetupLogging@@0PAGA; Buffer
0x180037d72  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037d77  test    eax, eax
0x180037d79  jnz     short loc_180037DAC
0x180037d7b  mov     [rsp+8E0h+hTemplateFile], r14; hTemplateFile
0x180037d80  lea     r8d, [rax+3]; dwShareMode
0x180037d84  mov     [rsp+8E0h+dwFlagsAndAttributes], 80000080h; dwFlagsAndAttributes
0x180037d8c  lea     rcx, ?m_szFileName@CSetupLogging@@0PAGA; lpFileName
0x180037d93  xor     r9d, r9d; lpSecurityAttributes
0x180037d96  mov     [rsp+8E0h+dwCreationDisposition], 2; dwCreationDisposition
0x180037d9e  mov     edx, 40000000h; dwDesiredAccess
0x180037da3  call    cs:__imp_CreateFileW
0x180037da9  mov     [rdi], rax
0x180037dac  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180037db0  jnz     short loc_180037DB5
0x180037db2  mov     [rdi], r14
0x180037db5  lea     rax, [rbx-1]
0x180037db9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180037dbd  ja      short loc_180037DC8
0x180037dbf  mov     rcx, rbx; hFindFile
0x180037dc2  call    cs:__imp_FindClose
0x180037dc8  mov     rcx, [rbp+7E0h+var_20]
0x180037dcf  xor     rcx, rsp; StackCookie
0x180037dd2  call    __security_check_cookie
0x180037dd7  lea     r11, [rsp+8E0h+var_10]
0x180037ddf  mov     rbx, [r11+28h]
0x180037de3  mov     rsi, [r11+30h]
0x180037de7  mov     rsp, r11
0x180037dea  pop     r14
0x180037dec  pop     rdi
0x180037ded  pop     rbp
0x180037dee  retn
```
