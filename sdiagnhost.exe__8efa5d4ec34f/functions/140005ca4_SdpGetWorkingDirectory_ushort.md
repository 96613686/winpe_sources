# SdpGetWorkingDirectory(ushort * *)

- ea: `0x140005ca4`
- end: `0x140005d74`
- name: `?SdpGetWorkingDirectory@@YAJPEAPEAG@Z`
- size: `208`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140002af0`

## callees

- `0x140001ed8`
- `0x140005964`
- `0x140005ca4`

## import_xrefs

- `KERNEL32!GetCurrentDirectoryW` at `0x140005d03`
- `KERNEL32!GetCurrentDirectoryW` at `0x140005d03`
- `KERNEL32!GetLastError` at `0x140005d0d`
- `KERNEL32!GetLastError` at `0x140005d0d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140005d55`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140005d55`

## string_xrefs

- `0x140005cc9`: `SdpGetWorkingDirectory`
- `0x140005d46`: `SdpGetWorkingDirectory`

## pseudocode

```c
__int64 __fastcall SdpGetWorkingDirectory(unsigned __int16 **a1)
{
  unsigned int v2; // ebx
  unsigned int v3; // r8d
  WCHAR *v4; // rax
  unsigned __int16 *v5; // rdi
  DWORD CurrentDirectoryW; // eax
  __int64 v7; // rcx
  signed int LastError; // eax
  unsigned int v9; // r8d

  if ( !a1 )
  {
    v2 = -2147024809;
    v3 = 2507;
LABEL_3:
    SdpDebugTrace((__int64)a1, (const char *)L"SdpGetWorkingDirectory", v3, v2);
    return v2;
  }
  v4 = (WCHAR *)operator new[](0x208u);
  v5 = v4;
  if ( !v4 )
  {
    v2 = -2147024882;
    v3 = 2510;
    goto LABEL_3;
  }
  CurrentDirectoryW = GetCurrentDirectoryW(0x104u, v4);
  if ( CurrentDirectoryW )
  {
    if ( CurrentDirectoryW <= 0x104 )
    {
      v2 = 0;
      *a1 = v5;
      return v2;
    }
    v2 = -2147024785;
    v9 = 2517;
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    v9 = 2513;
    if ( (v2 & 0x80000000) == 0 )
      v2 = -2147467259;
  }
  SdpDebugTrace(v7, (const char *)L"SdpGetWorkingDirectory", v9, v2);
  operator delete[](v5);
  return v2;
}

```

## disassembly

```asm
0x140005ca4  mov     [rsp+arg_0], rbx
0x140005ca9  mov     [rsp+arg_8], rsi
0x140005cae  push    rdi
0x140005caf  sub     rsp, 20h
0x140005cb3  mov     rsi, rcx
0x140005cb6  test    rcx, rcx
0x140005cb9  jnz     short loc_140005CDA
0x140005cbb  mov     ebx, 80070057h
0x140005cc0  mov     r8d, 9CBh; int
0x140005cc6  mov     r9d, ebx; int
0x140005cc9  lea     rdx, aSdpgetworkingd; "SdpGetWorkingDirectory"
0x140005cd0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140005cd5  jmp     loc_140005D62
0x140005cda  mov     ecx, 208h; unsigned __int64
0x140005cdf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140005ce4  mov     rdi, rax
0x140005ce7  test    rax, rax
0x140005cea  jnz     short loc_140005CF9
0x140005cec  mov     ebx, 8007000Eh
0x140005cf1  mov     r8d, 9CEh
0x140005cf7  jmp     short loc_140005CC6
0x140005cf9  mov     ebx, 104h
0x140005cfe  mov     rdx, rdi; lpBuffer
0x140005d01  mov     ecx, ebx; nBufferLength
0x140005d03  call    cs:__imp_GetCurrentDirectoryW
0x140005d09  test    eax, eax
0x140005d0b  jnz     short loc_140005D34
0x140005d0d  call    cs:__imp_GetLastError
0x140005d13  mov     ebx, eax
0x140005d15  test    eax, eax
0x140005d17  jle     short loc_140005D22
0x140005d19  movzx   ebx, ax
0x140005d1c  or      ebx, 80070000h
0x140005d22  test    ebx, ebx
0x140005d24  mov     eax, 80004005h
0x140005d29  mov     r8d, 9D1h
0x140005d2f  cmovns  ebx, eax
0x140005d32  jmp     short loc_140005D43
0x140005d34  cmp     eax, ebx
0x140005d36  jbe     short loc_140005D5D
0x140005d38  mov     ebx, 8007006Fh
0x140005d3d  mov     r8d, 9D5h; int
0x140005d43  mov     r9d, ebx; int
0x140005d46  lea     rdx, aSdpgetworkingd; "SdpGetWorkingDirectory"
0x140005d4d  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x140005d52  mov     rcx, rdi
0x140005d55  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140005d5b  jmp     short loc_140005D62
0x140005d5d  xor     ebx, ebx
0x140005d5f  mov     [rsi], rdi
0x140005d62  mov     rsi, [rsp+28h+arg_8]
0x140005d67  mov     eax, ebx
0x140005d69  mov     rbx, [rsp+28h+arg_0]
0x140005d6e  add     rsp, 20h
0x140005d72  pop     rdi
0x140005d73  retn
```
