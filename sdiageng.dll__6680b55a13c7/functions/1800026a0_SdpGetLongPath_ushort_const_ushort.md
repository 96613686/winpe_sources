# SdpGetLongPath(ushort const *,ushort * *)

- ea: `0x1800026a0`
- end: `0x180002792`
- name: `?SdpGetLongPath@@YAJPEBGPEAPEAG@Z`
- size: `242`
- prototype: `__int64 __fastcall(LPCWSTR lpszShortPath, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000cf00`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x1800026a0`
- `0x180026fa0`

## import_xrefs

- `KERNEL32!GetLongPathNameW` at `0x18000271a`
- `KERNEL32!GetLongPathNameW` at `0x18000271a`
- `KERNEL32!GetLastError` at `0x180002724`
- `KERNEL32!GetLastError` at `0x180002724`

## string_xrefs

- `0x1800026c9`: `SdpGetLongPath`
- `0x180002760`: `SdpGetLongPath`

## pseudocode

```c
__int64 __fastcall SdpGetLongPath(LPCWSTR lpszShortPath, unsigned __int16 **a2)
{
  unsigned int v4; // r8d
  int v5; // r9d
  unsigned int v6; // ebx
  WCHAR *v7; // rax
  unsigned __int16 *v8; // rdi
  DWORD LongPathNameW; // eax
  signed int LastError; // eax
  unsigned int v11; // r8d

  if ( !lpszShortPath )
  {
    v4 = 363;
LABEL_3:
    v5 = -2147024809;
    v6 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpGetLongPath", v4, v5);
    return v6;
  }
  if ( !a2 )
  {
    v4 = 364;
    goto LABEL_3;
  }
  v7 = (WCHAR *)operator new[](0x208u);
  v8 = v7;
  if ( !v7 )
  {
    v6 = -2147024882;
    v4 = 367;
    v5 = -2147024882;
    goto LABEL_4;
  }
  LongPathNameW = GetLongPathNameW(lpszShortPath, v7, 0x104u);
  if ( LongPathNameW )
  {
    if ( LongPathNameW <= 0x104 )
    {
      v6 = 0;
      *a2 = v8;
      return v6;
    }
    v6 = -2147024785;
    v11 = 374;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v11 = 370;
    if ( (v6 & 0x80000000) == 0 )
      v6 = -2147467259;
  }
  SdpDebugTrace(1u, L"SdpGetLongPath", v11, v6);
  operator delete(v8);
  return v6;
}

```

## disassembly

```asm
0x1800026a0  mov     [rsp+arg_0], rbx
0x1800026a5  mov     [rsp+arg_8], rsi
0x1800026aa  push    rdi
0x1800026ab  sub     rsp, 20h
0x1800026af  mov     rsi, rdx
0x1800026b2  mov     rbx, rcx
0x1800026b5  test    rcx, rcx
0x1800026b8  jnz     short loc_1800026DF
0x1800026ba  mov     r8d, 16Bh; int
0x1800026c0  mov     r9d, 80070057h; int
0x1800026c6  mov     ebx, r9d
0x1800026c9  lea     rdx, aSdpgetlongpath; "SdpGetLongPath"
0x1800026d0  mov     ecx, 1; Level
0x1800026d5  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800026da  jmp     loc_180002780
0x1800026df  test    rsi, rsi
0x1800026e2  jnz     short loc_1800026EC
0x1800026e4  mov     r8d, 16Ch
0x1800026ea  jmp     short loc_1800026C0
0x1800026ec  mov     ecx, 208h; unsigned __int64
0x1800026f1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800026f6  mov     rdi, rax
0x1800026f9  test    rax, rax
0x1800026fc  jnz     short loc_18000270E
0x1800026fe  mov     ebx, 8007000Eh
0x180002703  mov     r8d, 16Fh
0x180002709  mov     r9d, ebx
0x18000270c  jmp     short loc_1800026C9
0x18000270e  mov     r8d, 104h; cchBuffer
0x180002714  mov     rdx, rdi; lpszLongPath
0x180002717  mov     rcx, rbx; lpszShortPath
0x18000271a  call    cs:__imp_GetLongPathNameW
0x180002720  test    eax, eax
0x180002722  jnz     short loc_18000274B
0x180002724  call    cs:__imp_GetLastError
0x18000272a  mov     ebx, eax
0x18000272c  test    eax, eax
0x18000272e  jle     short loc_180002739
0x180002730  movzx   ebx, ax
0x180002733  or      ebx, 80070000h
0x180002739  test    ebx, ebx
0x18000273b  mov     eax, 80004005h
0x180002740  mov     r8d, 172h
0x180002746  cmovns  ebx, eax
0x180002749  jmp     short loc_18000275D
0x18000274b  cmp     eax, 104h
0x180002750  jbe     short loc_18000277B
0x180002752  mov     ebx, 8007006Fh
0x180002757  mov     r8d, 176h; int
0x18000275d  mov     r9d, ebx; int
0x180002760  lea     rdx, aSdpgetlongpath; "SdpGetLongPath"
0x180002767  mov     ecx, 1; Level
0x18000276c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002771  mov     rcx, rdi; Block
0x180002774  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002779  jmp     short loc_180002780
0x18000277b  xor     ebx, ebx
0x18000277d  mov     [rsi], rdi
0x180002780  mov     rsi, [rsp+28h+arg_8]
0x180002785  mov     eax, ebx
0x180002787  mov     rbx, [rsp+28h+arg_0]
0x18000278c  add     rsp, 20h
0x180002790  pop     rdi
0x180002791  retn
```
