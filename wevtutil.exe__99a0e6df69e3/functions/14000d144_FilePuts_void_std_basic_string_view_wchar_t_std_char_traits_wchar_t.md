# FilePuts(void *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x14000d144`
- end: `0x14000d2e6`
- name: `?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `21`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000116c`
- `0x140008db0`
- `0x14000b8e8`
- `0x14000bbd0`
- `0x14000be14`
- `0x14000cafc`
- `0x14000cc80`
- `0x14000ce74`
- `0x14000dac4`
- `0x14000e8c4`
- `0x14000e924`
- `0x14000fc50`
- `0x140011f60`
- `0x140023994`
- `0x140024b44`
- `0x140029664`
- `0x14002987c`
- `0x140029b20`
- `0x14003222b`
- `0x140032fbd`
- `0x14003316b`

## callees

- `0x14000d144`
- `0x14000da84`
- `0x140021b00`
- `0x1400286f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d1ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d26f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d1ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d26f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000d265`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000d2b5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000d265`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14000d2b5`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x14000d186`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x14000d186`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14000d1db`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x14000d1db`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x14000d198`
- `api-ms-win-core-console-l1-1-0!GetConsoleMode` at `0x14000d198`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall FilePuts(HANDLE hFile, _QWORD *a2)
{
  __int64 i; // rsi
  DWORD v5; // r8d
  signed int result; // eax
  int v7; // ebx
  LPCVOID *v8; // rdx
  signed int LastError; // eax
  DWORD NumberOfCharsWritten; // [rsp+30h] [rbp-30h] BYREF
  DWORD Mode; // [rsp+34h] [rbp-2Ch] BYREF
  LPCVOID lpBuffer[2]; // [rsp+38h] [rbp-28h] BYREF
  DWORD nNumberOfBytesToWrite[2]; // [rsp+48h] [rbp-18h]
  unsigned __int64 v14; // [rsp+50h] [rbp-10h]

  Mode = 0;
  NumberOfCharsWritten = 0;
  if ( !a2[1] )
    return 0;
  if ( GetFileType(hFile) == 2 && GetConsoleMode(hFile, &Mode) )
  {
    for ( i = 0; (unsigned __int64)(unsigned int)i < a2[1]; i = NumberOfCharsWritten + (unsigned int)i )
    {
      v5 = *((_DWORD *)a2 + 2) - i;
      if ( v5 > 0x1000 )
        v5 = 4096;
      if ( !WriteConsoleW(hFile, (const void *)(*a2 + 2 * i), v5, &NumberOfCharsWritten, 0) )
        goto LABEL_10;
    }
    return 0;
  }
  if ( !g_outputUnicode )
  {
    *(_OWORD *)lpBuffer = 0;
    v14 = 15;
    *(_QWORD *)nNumberOfBytesToWrite = 0;
    LOBYTE(lpBuffer[0]) = 0;
    v7 = tlx::_AppendWideImpl<std::string,wchar_t>(lpBuffer, *a2, a2[1]);
    if ( v7 < 0 )
    {
LABEL_20:
      std::string::~string(lpBuffer);
      return v7;
    }
    v8 = lpBuffer;
    if ( v14 > 0xF )
      v8 = (LPCVOID *)lpBuffer[0];
    if ( !WriteFile(hFile, v8, nNumberOfBytesToWrite[0], &NumberOfCharsWritten, 0) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v7 = LastError;
      goto LABEL_20;
    }
    std::string::~string(lpBuffer);
    return 0;
  }
  if ( WriteFile(hFile, (LPCVOID)*a2, 2 * *((_DWORD *)a2 + 2), &NumberOfCharsWritten, 0) )
    return 0;
LABEL_10:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14000d144  mov     [rsp-18h+arg_10], rbx
0x14000d149  mov     [rsp-18h+arg_18], rsi
0x14000d14e  push    rbp
0x14000d14f  push    rdi
0x14000d150  push    r12
0x14000d152  mov     rbp, rsp
0x14000d155  sub     rsp, 60h
0x14000d159  mov     rax, cs:__security_cookie
0x14000d160  xor     rax, rsp
0x14000d163  mov     [rbp+var_8], rax
0x14000d167  mov     rbx, rdx
0x14000d16a  mov     rdi, rcx
0x14000d16d  mov     [rbp+Mode], 0
0x14000d174  mov     [rbp+NumberOfCharsWritten], 0
0x14000d17b  cmp     qword ptr [rdx+8], 0
0x14000d180  jz      loc_14000D2C3
0x14000d186  call    cs:__imp_GetFileType
0x14000d18c  cmp     eax, 2
0x14000d18f  jnz     short loc_14000D205
0x14000d191  lea     rdx, [rbp+Mode]; lpMode
0x14000d195  mov     rcx, rdi; hConsoleHandle
0x14000d198  call    cs:__imp_GetConsoleMode
0x14000d19e  test    eax, eax
0x14000d1a0  jz      short loc_14000D205
0x14000d1a2  xor     esi, esi
0x14000d1a4  mov     r12d, 1000h
0x14000d1aa  mov     ecx, esi
0x14000d1ac  cmp     rcx, [rbx+8]
0x14000d1b0  jnb     loc_14000D2C3
0x14000d1b6  mov     rax, [rbx]
0x14000d1b9  lea     rdx, [rax+rsi*2]; lpBuffer
0x14000d1bd  mov     r8d, [rbx+8]
0x14000d1c1  sub     r8d, esi
0x14000d1c4  cmp     r8d, r12d
0x14000d1c7  cmova   r8d, r12d; nNumberOfCharsToWrite
0x14000d1cb  mov     [rsp+60h+lpReserved], 0; lpReserved
0x14000d1d4  lea     r9, [rbp+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x14000d1d8  mov     rcx, rdi; hConsoleOutput
0x14000d1db  call    cs:__imp_WriteConsoleW
0x14000d1e1  test    eax, eax
0x14000d1e3  jz      short loc_14000D1EA
0x14000d1e5  add     esi, [rbp+NumberOfCharsWritten]
0x14000d1e8  jmp     short loc_14000D1AA
0x14000d1ea  call    cs:__imp_GetLastError
0x14000d1f0  test    eax, eax
0x14000d1f2  jle     loc_14000D2C5
0x14000d1f8  movzx   eax, ax
0x14000d1fb  or      eax, 80070000h
0x14000d200  jmp     loc_14000D2C5
0x14000d205  cmp     cs:?g_outputUnicode@@3_NA, 0; bool g_outputUnicode
0x14000d20c  jnz     loc_14000D29B
0x14000d212  xorps   xmm0, xmm0
0x14000d215  movups  xmmword ptr [rbp+lpBuffer], xmm0
0x14000d219  mov     [rbp+var_10], 0Fh
0x14000d221  mov     qword ptr [rbp+nNumberOfBytesToWrite], 0
0x14000d229  mov     byte ptr [rbp+lpBuffer], 0
0x14000d22d  mov     r8, [rbx+8]
0x14000d231  mov     rdx, [rbx]
0x14000d234  lea     rcx, [rbp+lpBuffer]
0x14000d238  call    ??$_AppendWideImpl@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_W@tlx@@YAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEB_W_KII@Z; tlx::_AppendWideImpl<std::string,wchar_t>(std::string &,wchar_t const *,unsigned __int64,uint,uint)
0x14000d23d  mov     ebx, eax
0x14000d23f  test    eax, eax
0x14000d241  js      short loc_14000D283
0x14000d243  lea     rdx, [rbp+lpBuffer]
0x14000d247  cmp     [rbp+var_10], 0Fh
0x14000d24c  cmova   rdx, [rbp+lpBuffer]; lpBuffer
0x14000d251  mov     [rsp+60h+lpReserved], 0; lpOverlapped
0x14000d25a  lea     r9, [rbp+NumberOfCharsWritten]; lpNumberOfBytesWritten
0x14000d25e  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x14000d262  mov     rcx, rdi; hFile
0x14000d265  call    cs:__imp_WriteFile
0x14000d26b  test    eax, eax
0x14000d26d  jnz     short loc_14000D290
0x14000d26f  call    cs:__imp_GetLastError
0x14000d275  test    eax, eax
0x14000d277  jle     short loc_14000D281
0x14000d279  movzx   eax, ax
0x14000d27c  or      eax, 80070000h
0x14000d281  mov     ebx, eax
0x14000d283  lea     rcx, [rbp+lpBuffer]
0x14000d287  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000d28c  mov     eax, ebx
0x14000d28e  jmp     short loc_14000D2C5
0x14000d290  lea     rcx, [rbp+lpBuffer]
0x14000d294  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000d299  jmp     short loc_14000D2C3
0x14000d29b  mov     r8d, [rbx+8]
0x14000d29f  add     r8d, r8d; nNumberOfBytesToWrite
0x14000d2a2  mov     [rsp+60h+lpReserved], 0; lpOverlapped
0x14000d2ab  lea     r9, [rbp+NumberOfCharsWritten]; lpNumberOfBytesWritten
0x14000d2af  mov     rdx, [rbx]; lpBuffer
0x14000d2b2  mov     rcx, rdi; hFile
0x14000d2b5  call    cs:__imp_WriteFile
0x14000d2bb  test    eax, eax
0x14000d2bd  jz      loc_14000D1EA
0x14000d2c3  xor     eax, eax
0x14000d2c5  mov     rcx, [rbp+var_8]
0x14000d2c9  xor     rcx, rsp; StackCookie
0x14000d2cc  call    __security_check_cookie
0x14000d2d1  lea     r11, [rsp+60h+var_s0]
0x14000d2d6  mov     rbx, [r11+30h]
0x14000d2da  mov     rsi, [r11+38h]
0x14000d2de  mov     rsp, r11
0x14000d2e1  pop     r12
0x14000d2e3  pop     rdi
0x14000d2e4  pop     rbp
0x14000d2e5  retn
```
