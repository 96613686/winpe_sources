# CScriptedDiag::GetTempDirPath(ushort * *)

- ea: `0x18000c31c`
- end: `0x18000c3f5`
- name: `?GetTempDirPath@CScriptedDiag@@AEAAJPEAPEAG@Z`
- size: `217`
- prototype: `__int64 __fastcall(CScriptedDiag *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000c3fc`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x18000c31c`
- `0x180026fa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c38a`
- `KERNEL32!GetLastError` at `0x18000c38a`
- `KERNEL32!GetTempPath2W` at `0x18000c380`
- `KERNEL32!GetTempPath2W` at `0x18000c380`

## string_xrefs

- `0x18000c341`: `CScriptedDiag::GetTempDirPath`
- `0x18000c3c3`: `CScriptedDiag::GetTempDirPath`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::GetTempDirPath(CScriptedDiag *this, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  int v4; // r8d
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rdi
  unsigned int TempPath2W; // eax
  signed int LastError; // eax
  int v9; // r8d

  if ( !a2 )
  {
    v3 = -2147024809;
    v4 = 1872;
LABEL_3:
    SdpDebugTrace(1u, L"CScriptedDiag::GetTempDirPath", v4, v3);
    return v3;
  }
  v5 = (unsigned __int16 *)operator new[](0x208u);
  v6 = v5;
  if ( !v5 )
  {
    v3 = -2147024882;
    v4 = 1875;
    goto LABEL_3;
  }
  TempPath2W = GetTempPath2W(260, v5);
  if ( TempPath2W )
  {
    if ( TempPath2W <= 0x104 )
    {
      v3 = 0;
      *a2 = v6;
      return v3;
    }
    v3 = -2147024785;
    v9 = 1882;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v9 = 1878;
    if ( (v3 & 0x80000000) == 0 )
      v3 = -2147467259;
  }
  SdpDebugTrace(1u, L"CScriptedDiag::GetTempDirPath", v9, v3);
  operator delete(v6);
  return v3;
}

```

## disassembly

```asm
0x18000c31c  mov     [rsp+arg_0], rbx
0x18000c321  mov     [rsp+arg_8], rsi
0x18000c326  push    rdi
0x18000c327  sub     rsp, 20h
0x18000c32b  mov     rsi, rdx
0x18000c32e  test    rdx, rdx
0x18000c331  jnz     short loc_18000C357
0x18000c333  mov     ebx, 80070057h
0x18000c338  mov     r8d, 750h; int
0x18000c33e  mov     r9d, ebx; int
0x18000c341  lea     rdx, aCscripteddiagG_16; "CScriptedDiag::GetTempDirPath"
0x18000c348  mov     ecx, 1; Level
0x18000c34d  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000c352  jmp     loc_18000C3E3
0x18000c357  mov     ecx, 208h; unsigned __int64
0x18000c35c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000c361  mov     rdi, rax
0x18000c364  test    rax, rax
0x18000c367  jnz     short loc_18000C376
0x18000c369  mov     ebx, 8007000Eh
0x18000c36e  mov     r8d, 753h
0x18000c374  jmp     short loc_18000C33E
0x18000c376  mov     ebx, 104h
0x18000c37b  mov     rdx, rdi
0x18000c37e  mov     ecx, ebx
0x18000c380  call    cs:__imp_GetTempPath2W
0x18000c386  test    eax, eax
0x18000c388  jnz     short loc_18000C3B1
0x18000c38a  call    cs:__imp_GetLastError
0x18000c390  mov     ebx, eax
0x18000c392  test    eax, eax
0x18000c394  jle     short loc_18000C39F
0x18000c396  movzx   ebx, ax
0x18000c399  or      ebx, 80070000h
0x18000c39f  test    ebx, ebx
0x18000c3a1  mov     eax, 80004005h
0x18000c3a6  mov     r8d, 756h
0x18000c3ac  cmovns  ebx, eax
0x18000c3af  jmp     short loc_18000C3C0
0x18000c3b1  cmp     eax, ebx
0x18000c3b3  jbe     short loc_18000C3DE
0x18000c3b5  mov     ebx, 8007006Fh
0x18000c3ba  mov     r8d, 75Ah; int
0x18000c3c0  mov     r9d, ebx; int
0x18000c3c3  lea     rdx, aCscripteddiagG_16; "CScriptedDiag::GetTempDirPath"
0x18000c3ca  mov     ecx, 1; Level
0x18000c3cf  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000c3d4  mov     rcx, rdi; Block
0x18000c3d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c3dc  jmp     short loc_18000C3E3
0x18000c3de  xor     ebx, ebx
0x18000c3e0  mov     [rsi], rdi
0x18000c3e3  mov     rsi, [rsp+28h+arg_8]
0x18000c3e8  mov     eax, ebx
0x18000c3ea  mov     rbx, [rsp+28h+arg_0]
0x18000c3ef  add     rsp, 20h
0x18000c3f3  pop     rdi
0x18000c3f4  retn
```
