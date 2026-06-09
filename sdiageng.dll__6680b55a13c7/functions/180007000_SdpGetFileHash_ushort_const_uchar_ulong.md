# SdpGetFileHash(ushort const *,uchar * *,ulong &)

- ea: `0x180007000`
- end: `0x18000717c`
- name: `?SdpGetFileHash@@YAJPEBGPEAPEAEAEAK@Z`
- size: `380`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000698c`
- `0x18000787c`
- `0x180007f0c`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x180007000`
- `0x180026fa0`
- `0x180029882`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800070fa`
- `KERNEL32!GetLastError` at `0x18000711b`
- `KERNEL32!GetLastError` at `0x1800070fa`
- `KERNEL32!GetLastError` at `0x18000711b`
- `KERNEL32!CreateFileW` at `0x1800070b1`
- `KERNEL32!CreateFileW` at `0x1800070b1`
- `KERNEL32!CloseHandle` at `0x180007167`
- `KERNEL32!CloseHandle` at `0x180007167`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1800070d4`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1800070d4`

## pseudocode

```c
__int64 __fastcall SdpGetFileHash(LPCWSTR lpFileName, unsigned __int8 **a2, unsigned int *a3)
{
  unsigned int v6; // r8d
  int v7; // r9d
  signed int v8; // ebx
  unsigned __int8 *v9; // rax
  unsigned __int8 *v10; // rbp
  char *FileW; // rsi
  signed int v12; // eax
  unsigned int v13; // r8d
  signed int LastError; // eax
  size_t Size; // [rsp+80h] [rbp+8h] BYREF

  LODWORD(Size) = 128;
  if ( !lpFileName )
  {
    v6 = 682;
LABEL_3:
    v7 = -2147024809;
    v8 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpGetFileHash", v6, v7);
    return (unsigned int)v8;
  }
  if ( !a2 )
  {
    v6 = 683;
    goto LABEL_3;
  }
  v9 = (unsigned __int8 *)operator new[](0x80u);
  v10 = v9;
  if ( !v9 )
  {
    v8 = -2147024882;
    v6 = 686;
    v7 = -2147024882;
    goto LABEL_4;
  }
  memset_0(v9, 0, (unsigned int)Size);
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v13 = 697;
    if ( v8 >= 0 )
      v8 = -2147467259;
  }
  else
  {
    if ( CryptCATAdminCalcHashFromFileHandle(FileW, (DWORD *)&Size, v10, 0) )
    {
      v8 = 0;
LABEL_12:
      *a3 = Size;
      LODWORD(Size) = 0;
      *a2 = v10;
LABEL_23:
      CloseHandle(FileW);
      return (unsigned int)v8;
    }
    v12 = GetLastError();
    v8 = v12;
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    if ( v8 >= 0 )
      goto LABEL_12;
    v13 = 703;
  }
  SdpDebugTrace(1u, L"SdpGetFileHash", v13, v8);
  operator delete(v10);
  if ( FileW && FileW != (char *)-1LL )
    goto LABEL_23;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007000  mov     rax, rsp
0x180007003  push    rbx
0x180007004  push    rbp
0x180007005  push    rsi
0x180007006  push    rdi
0x180007007  push    r14
0x180007009  push    r15
0x18000700b  sub     rsp, 48h
0x18000700f  mov     rbx, rcx
0x180007012  mov     r15, r8
0x180007015  mov     ecx, 80h; unsigned __int64
0x18000701a  mov     r14, rdx
0x18000701d  mov     [rax+8], ecx
0x180007020  test    rbx, rbx
0x180007023  jnz     short loc_18000704A
0x180007025  mov     r8d, 2AAh; int
0x18000702b  mov     r9d, 80070057h; int
0x180007031  mov     ebx, r9d
0x180007034  lea     rdx, aSdpgetfilehash; "SdpGetFileHash"
0x18000703b  mov     ecx, 1; Level
0x180007040  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007045  jmp     loc_18000716D
0x18000704a  test    r14, r14
0x18000704d  jnz     short loc_180007057
0x18000704f  mov     r8d, 2ABh
0x180007055  jmp     short loc_18000702B
0x180007057  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000705c  mov     rbp, rax
0x18000705f  test    rax, rax
0x180007062  jnz     short loc_180007074
0x180007064  mov     ebx, 8007000Eh
0x180007069  mov     r8d, 2AEh
0x18000706f  mov     r9d, ebx
0x180007072  jmp     short loc_180007034
0x180007074  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x18000707c  xor     edx, edx; Val
0x18000707e  mov     rcx, rbp; void *
0x180007081  call    memset_0
0x180007086  xor     r9d, r9d; lpSecurityAttributes
0x180007089  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180007092  mov     [rsp+78h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000709a  mov     edx, 80000000h; dwDesiredAccess
0x18000709f  mov     rcx, rbx; lpFileName
0x1800070a2  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x1800070aa  lea     edi, [r9+1]
0x1800070ae  mov     r8d, edi; dwShareMode
0x1800070b1  call    cs:__imp_CreateFileW
0x1800070b7  mov     rsi, rax
0x1800070ba  dec     rax
0x1800070bd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800070c1  ja      short loc_18000711B
0x1800070c3  xor     r9d, r9d; dwFlags
0x1800070c6  lea     rdx, [rsp+78h+Size]; pcbHash
0x1800070ce  mov     r8, rbp; pbHash
0x1800070d1  mov     rcx, rsi; hFile
0x1800070d4  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x1800070da  test    eax, eax
0x1800070dc  jz      short loc_1800070FA
0x1800070de  xor     ebx, ebx
0x1800070e0  mov     eax, dword ptr [rsp+78h+Size]
0x1800070e7  mov     [r15], eax
0x1800070ea  mov     dword ptr [rsp+78h+Size], 0
0x1800070f5  mov     [r14], rbp
0x1800070f8  jmp     short loc_180007164
0x1800070fa  call    cs:__imp_GetLastError
0x180007100  mov     ebx, eax
0x180007102  test    eax, eax
0x180007104  jle     short loc_18000710F
0x180007106  movzx   ebx, ax
0x180007109  or      ebx, 80070000h
0x18000710f  test    ebx, ebx
0x180007111  jns     short loc_1800070E0
0x180007113  mov     r8d, 2BFh
0x180007119  jmp     short loc_180007140
0x18000711b  call    cs:__imp_GetLastError
0x180007121  mov     ebx, eax
0x180007123  test    eax, eax
0x180007125  jle     short loc_180007130
0x180007127  movzx   ebx, ax
0x18000712a  or      ebx, 80070000h
0x180007130  test    ebx, ebx
0x180007132  mov     eax, 80004005h
0x180007137  mov     r8d, 2B9h; int
0x18000713d  cmovns  ebx, eax
0x180007140  mov     r9d, ebx; int
0x180007143  lea     rdx, aSdpgetfilehash; "SdpGetFileHash"
0x18000714a  mov     ecx, edi; Level
0x18000714c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007151  mov     rcx, rbp; Block
0x180007154  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007159  test    rsi, rsi
0x18000715c  jz      short loc_18000716D
0x18000715e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180007162  jz      short loc_18000716D
0x180007164  mov     rcx, rsi; hObject
0x180007167  call    cs:__imp_CloseHandle
0x18000716d  mov     eax, ebx
0x18000716f  add     rsp, 48h
0x180007173  pop     r15
0x180007175  pop     r14
0x180007177  pop     rdi
0x180007178  pop     rsi
0x180007179  pop     rbp
0x18000717a  pop     rbx
0x18000717b  retn
```
