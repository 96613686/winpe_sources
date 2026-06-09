# PrintMessage(uint,...)

- ea: `0x140006238`
- end: `0x1400063d3`
- name: `?PrintMessage@@YAXIZZ`
- size: `411`
- prototype: `void(UINT, ...)`
- caller_count: `10`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1400037e0`
- `0x140003c88`
- `0x1400045e0`
- `0x1400046f4`
- `0x140004df8`
- `0x140005988`
- `0x140006480`
- `0x1400075a8`
- `0x14000792c`
- `0x140008500`

## callees

- `0x140006238`
- `0x14002e420`
- `0x14002e4e0`

## import_xrefs

- `KERNEL32!GetConsoleMode` at `0x140006322`
- `KERNEL32!GetConsoleMode` at `0x140006322`
- `KERNEL32!WriteConsoleW` at `0x140006343`
- `KERNEL32!WriteConsoleW` at `0x140006343`
- `KERNEL32!LocalFree` at `0x1400063b2`
- `KERNEL32!LocalFree` at `0x1400063b2`
- `KERNEL32!WideCharToMultiByte` at `0x140006388`
- `KERNEL32!WideCharToMultiByte` at `0x140006388`
- `KERNEL32!GetFileType` at `0x14000630b`
- `KERNEL32!GetFileType` at `0x14000630b`
- `KERNEL32!WriteFile` at `0x1400063a9`
- `KERNEL32!WriteFile` at `0x1400063a9`
- `KERNEL32!GetStdHandle` at `0x1400062dc`
- `KERNEL32!GetStdHandle` at `0x1400062dc`
- `KERNEL32!LocalAlloc` at `0x140006354`
- `KERNEL32!LocalAlloc` at `0x140006354`
- `msvcrt!_vsnwprintf` at `0x1400062b8`
- `msvcrt!_vsnwprintf` at `0x1400062b8`
- `USER32!LoadStringW` at `0x140006290`
- `USER32!LoadStringW` at `0x140006290`

## pseudocode

```c
void PrintMessage(UINT a1, ...)
{
  unsigned int v1; // eax
  HANDLE StdHandle; // rbx
  __int64 v3; // rax
  CHAR *v4; // rax
  CHAR *v5; // rdi
  DWORD v6; // eax
  DWORD NumberOfCharsWritten[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 Mode; // [rsp+50h] [rbp-B8h] BYREF
  wchar_t WideCharStr[1024]; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR Buffer[1024]; // [rsp+858h] [rbp+750h] BYREF
  va_list Args; // [rsp+10A0h] [rbp+F98h] BYREF

  va_start(Args, a1);
  Mode = 0;
  if ( LoadStringW(g_hInst, a1, Buffer, 1024) )
  {
    v1 = _vsnwprintf(WideCharStr, 0x3FFu, Buffer, Args);
    if ( v1 < 0x400 )
    {
      if ( v1 == 1023 )
        WideCharStr[1023] = 0;
      StdHandle = GetStdHandle(0xFFFFFFF5);
      v3 = -1;
      do
        ++v3;
      while ( WideCharStr[v3] );
      NumberOfCharsWritten[0] = v3;
      if ( StdHandle )
      {
        LODWORD(Mode) = 0;
        if ( (GetFileType(StdHandle) & 0xFFFF7FFF) == 2 && GetConsoleMode(StdHandle, (LPDWORD)&Mode) )
        {
          WriteConsoleW(StdHandle, WideCharStr, NumberOfCharsWritten[0], NumberOfCharsWritten, 0);
        }
        else
        {
          v4 = (CHAR *)LocalAlloc(0, 2LL * NumberOfCharsWritten[0]);
          v5 = v4;
          if ( v4 )
          {
            v6 = WideCharToMultiByte(1u, 0, WideCharStr, NumberOfCharsWritten[0], v4, 2 * NumberOfCharsWritten[0], 0, 0);
            NumberOfCharsWritten[0] = v6;
            if ( v6 )
              WriteFile(StdHandle, v5, v6, NumberOfCharsWritten, 0);
            LocalFree(v5);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140006238  mov     rax, rsp
0x14000623b  mov     [rax+8], ecx
0x14000623e  mov     [rax+10h], rdx
0x140006242  mov     [rax+18h], r8
0x140006246  mov     [rax+20h], r9
0x14000624a  push    rbp
0x14000624b  push    rbx
0x14000624c  push    rsi
0x14000624d  push    rdi
0x14000624e  lea     rbp, [rax-0F88h]
0x140006255  mov     eax, 1068h
0x14000625a  call    _alloca_probe
0x14000625f  sub     rsp, rax
0x140006262  mov     rax, cs:__security_cookie
0x140006269  xor     rax, rsp
0x14000626c  mov     [rbp+0F80h+var_30], rax
0x140006273  mov     edx, ecx; uID
0x140006275  lea     r8, [rbp+0F80h+Buffer]; lpBuffer
0x14000627c  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x140006283  xor     esi, esi
0x140006285  mov     r9d, 400h; cchBufferMax
0x14000628b  mov     [rsp+1080h+Mode], rsi
0x140006290  call    cs:__imp_LoadStringW
0x140006296  test    eax, eax
0x140006298  jz      loc_1400063B8
0x14000629e  mov     ebx, 3FFh
0x1400062a3  lea     r9, [rbp+0F80h+Args]; Args
0x1400062aa  mov     edx, ebx; BufferCount
0x1400062ac  lea     r8, [rbp+0F80h+Buffer]; Format
0x1400062b3  lea     rcx, [rsp+1080h+WideCharStr]; Buffer
0x1400062b8  call    cs:__imp__vsnwprintf
0x1400062be  test    eax, eax
0x1400062c0  js      loc_1400063B8
0x1400062c6  cmp     eax, ebx
0x1400062c8  ja      loc_1400063B8
0x1400062ce  jnz     short loc_1400062D7
0x1400062d0  mov     [rbp+0F80h+var_832], si
0x1400062d7  mov     ecx, 0FFFFFFF5h; nStdHandle
0x1400062dc  call    cs:__imp_GetStdHandle
0x1400062e2  mov     rbx, rax
0x1400062e5  lea     rcx, [rsp+1080h+WideCharStr]
0x1400062ea  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400062ee  inc     rax
0x1400062f1  cmp     [rcx+rax*2], si
0x1400062f5  jnz     short loc_1400062EE
0x1400062f7  mov     [rsp+1080h+NumberOfCharsWritten], eax
0x1400062fb  test    rbx, rbx
0x1400062fe  jz      loc_1400063B8
0x140006304  mov     rcx, rbx; hFile
0x140006307  mov     dword ptr [rsp+1080h+Mode], esi
0x14000630b  call    cs:__imp_GetFileType
0x140006311  btr     eax, 0Fh
0x140006315  cmp     eax, 2
0x140006318  jnz     short loc_14000634B
0x14000631a  lea     rdx, [rsp+1080h+Mode]; lpMode
0x14000631f  mov     rcx, rbx; hConsoleHandle
0x140006322  call    cs:__imp_GetConsoleMode
0x140006328  test    eax, eax
0x14000632a  jz      short loc_14000634B
0x14000632c  mov     r8d, [rsp+1080h+NumberOfCharsWritten]; nNumberOfCharsToWrite
0x140006331  lea     r9, [rsp+1080h+NumberOfCharsWritten]; lpNumberOfCharsWritten
0x140006336  lea     rdx, [rsp+1080h+WideCharStr]; lpBuffer
0x14000633b  mov     [rsp+1080h+lpReserved], rsi; lpReserved
0x140006340  mov     rcx, rbx; hConsoleOutput
0x140006343  call    cs:__imp_WriteConsoleW
0x140006349  jmp     short loc_1400063B8
0x14000634b  mov     edx, [rsp+1080h+NumberOfCharsWritten]
0x14000634f  xor     ecx, ecx; uFlags
0x140006351  add     rdx, rdx; uBytes
0x140006354  call    cs:__imp_LocalAlloc
0x14000635a  mov     rdi, rax
0x14000635d  test    rax, rax
0x140006360  jz      short loc_1400063B8
0x140006362  mov     r9d, [rsp+1080h+NumberOfCharsWritten]; cchWideChar
0x140006367  lea     r8, [rsp+1080h+WideCharStr]; lpWideCharStr
0x14000636c  mov     [rsp+1080h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x140006371  xor     edx, edx; dwFlags
0x140006373  mov     [rsp+1080h+lpDefaultChar], rsi; lpDefaultChar
0x140006378  lea     ecx, [r9+r9]
0x14000637c  mov     [rsp+1080h+cbMultiByte], ecx; cbMultiByte
0x140006380  lea     ecx, [rdx+1]; CodePage
0x140006383  mov     [rsp+1080h+lpReserved], rax; lpMultiByteStr
0x140006388  call    cs:__imp_WideCharToMultiByte
0x14000638e  mov     [rsp+1080h+NumberOfCharsWritten], eax
0x140006392  test    eax, eax
0x140006394  jz      short loc_1400063AF
0x140006396  lea     r9, [rsp+1080h+NumberOfCharsWritten]; lpNumberOfBytesWritten
0x14000639b  mov     [rsp+1080h+lpReserved], rsi; lpOverlapped
0x1400063a0  mov     r8d, eax; nNumberOfBytesToWrite
0x1400063a3  mov     rdx, rdi; lpBuffer
0x1400063a6  mov     rcx, rbx; hFile
0x1400063a9  call    cs:__imp_WriteFile
0x1400063af  mov     rcx, rdi; hMem
0x1400063b2  call    cs:__imp_LocalFree
0x1400063b8  mov     rcx, [rbp+0F80h+var_30]
0x1400063bf  xor     rcx, rsp; StackCookie
0x1400063c2  call    __security_check_cookie
0x1400063c7  add     rsp, 1068h
0x1400063ce  pop     rdi
0x1400063cf  pop     rsi
0x1400063d0  pop     rbx
0x1400063d1  pop     rbp
0x1400063d2  retn
```
