# mlib::MCreateFile(ushort const *,ulong,void * &)

- ea: `0x140056f94`
- end: `0x1400570c2`
- name: `?MCreateFile@mlib@@YAKPEBGKAEAPEAX@Z`
- size: `302`
- prototype: `DWORD __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, _QWORD *, void **)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001fea4`
- `0x14005ccd0`
- `0x1400719f0`
- `0x1400796f8`

## callees

- `0x140056f94`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14005709d`
- `KERNEL32!CreateFileW` at `0x14005709d`
- `KERNEL32!GetLastError` at `0x1400570b0`
- `KERNEL32!GetLastError` at `0x1400570b0`

## pseudocode

```c
DWORD __fastcall mlib::MCreateFile(LPCWSTR lpFileName, const unsigned __int16 *a2, _QWORD *a3, void **a4)
{
  unsigned int v4; // r11d
  DWORD v7; // ebx
  DWORD v8; // r10d
  unsigned int v9; // ecx
  int v10; // edx
  DWORD dwCreationDisposition; // r9d
  int v12; // edx
  int v13; // r8d
  int v14; // ecx
  int v15; // edx
  int v16; // ecx
  int v17; // edx
  DWORD dwFlagsAndAttributes; // eax
  HANDLE FileW; // rax

  v4 = (unsigned int)a2;
  v7 = ((_DWORD)a2 << 31) | 0x40000000;
  if ( ((unsigned __int8)a2 & 2) == 0 )
    v7 = (_DWORD)a2 << 31;
  v8 = ((unsigned int)a2 >> 2) & 1 | 2;
  if ( ((unsigned __int8)a2 & 8) == 0 )
    v8 = ((unsigned int)a2 >> 2) & 1;
  v9 = ((unsigned int)a2 >> 4) & 1;
  v10 = v9 | 2;
  if ( (v4 & 0x20) == 0 )
    v10 = v9;
  if ( (v4 & 0x40) != 0 )
    v10 = 3;
  dwCreationDisposition = v10 | 5;
  if ( (v4 & 0x80) == 0 )
    dwCreationDisposition = v10;
  v12 = (v4 >> 8) & 1 | 2;
  if ( (v4 & 0x200) == 0 )
    v12 = (v4 >> 8) & 1;
  v13 = v12 | 4;
  if ( (v4 & 0x400) == 0 )
    v13 = v12;
  v14 = v13 | 0x10;
  if ( (v4 & 0x800) == 0 )
    v14 = v13;
  v15 = v14 | 0x20;
  if ( (v4 & 0x1000) == 0 )
    v15 = v14;
  v16 = v15 | 0x80;
  if ( (v4 & 0x2000) == 0 )
    v16 = v15;
  v17 = v16 | 0x100;
  if ( (v4 & 0x4000) == 0 )
    v17 = v16;
  dwFlagsAndAttributes = v17 | 0x800;
  if ( (v4 & 0x8000) == 0 )
    dwFlagsAndAttributes = v17;
  if ( !dwCreationDisposition )
    dwCreationDisposition = 3;
  if ( !dwFlagsAndAttributes )
    dwFlagsAndAttributes = 128;
  FileW = CreateFileW(lpFileName, v7, v8, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  *a3 = FileW;
  return 0;
}

```

## disassembly

```asm
0x140056f94  push    rbx
0x140056f96  push    rsi
0x140056f97  push    rdi
0x140056f98  push    r14
0x140056f9a  push    r15
0x140056f9c  sub     rsp, 40h
0x140056fa0  mov     r11d, edx
0x140056fa3  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x140056fac  mov     r9d, edx
0x140056faf  mov     rdi, rcx
0x140056fb2  shl     r9d, 1Fh
0x140056fb6  mov     ecx, edx
0x140056fb8  mov     ebx, r9d
0x140056fbb  mov     rsi, r8
0x140056fbe  bts     ebx, 1Eh
0x140056fc2  mov     r14d, 3
0x140056fc8  test    dl, 2
0x140056fcb  cmovz   ebx, r9d
0x140056fcf  shr     ecx, 2
0x140056fd2  and     ecx, 1
0x140056fd5  lea     r15d, [r14+7Dh]
0x140056fd9  mov     r10d, ecx
0x140056fdc  or      r10d, 2
0x140056fe0  test    dl, 8
0x140056fe3  cmovz   r10d, ecx
0x140056fe7  mov     ecx, edx
0x140056fe9  shr     ecx, 4
0x140056fec  and     ecx, 1
0x140056fef  mov     edx, ecx
0x140056ff1  or      edx, 2
0x140056ff4  test    r11b, 20h
0x140056ff8  cmovz   edx, ecx
0x140056ffb  test    r11b, 40h
0x140056fff  mov     ecx, r11d
0x140057002  cmovnz  edx, r14d
0x140057006  mov     r9d, edx
0x140057009  or      r9d, 5
0x14005700d  test    r15b, r11b
0x140057010  cmovz   r9d, edx
0x140057014  shr     ecx, 8
0x140057017  and     ecx, 1
0x14005701a  mov     edx, ecx
0x14005701c  or      edx, 2
0x14005701f  bt      r11d, 9
0x140057024  cmovnb  edx, ecx
0x140057027  mov     r8d, edx
0x14005702a  or      r8d, 4
0x14005702e  bt      r11d, 0Ah
0x140057033  cmovnb  r8d, edx
0x140057037  mov     ecx, r8d
0x14005703a  or      ecx, 10h
0x14005703d  bt      r11d, 0Bh
0x140057042  cmovnb  ecx, r8d
0x140057046  mov     r8d, r10d; dwShareMode
0x140057049  mov     edx, ecx
0x14005704b  or      edx, 20h
0x14005704e  bt      r11d, 0Ch
0x140057053  cmovnb  edx, ecx
0x140057056  mov     ecx, edx
0x140057058  or      ecx, r15d
0x14005705b  bt      r11d, 0Dh
0x140057060  cmovnb  ecx, edx
0x140057063  mov     edx, ecx
0x140057065  bts     edx, 8
0x140057069  bt      r11d, 0Eh
0x14005706e  cmovnb  edx, ecx
0x140057071  mov     rcx, rdi; lpFileName
0x140057074  mov     eax, edx
0x140057076  bts     eax, 0Bh
0x14005707a  bt      r11d, 0Fh
0x14005707f  cmovnb  eax, edx
0x140057082  test    r9d, r9d
0x140057085  mov     edx, ebx; dwDesiredAccess
0x140057087  cmovz   r9d, r14d
0x14005708b  test    eax, eax
0x14005708d  cmovz   eax, r15d
0x140057091  mov     [rsp+68h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x140057095  mov     [rsp+68h+dwCreationDisposition], r9d; dwCreationDisposition
0x14005709a  xor     r9d, r9d; lpSecurityAttributes
0x14005709d  call    cs:__imp_CreateFileW
0x1400570a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400570a7  jz      short loc_1400570B0
0x1400570a9  mov     [rsi], rax
0x1400570ac  xor     eax, eax
0x1400570ae  jmp     short loc_1400570B6
0x1400570b0  call    cs:__imp_GetLastError
0x1400570b6  add     rsp, 40h
0x1400570ba  pop     r15
0x1400570bc  pop     r14
0x1400570be  pop     rdi
0x1400570bf  pop     rsi
0x1400570c0  pop     rbx
0x1400570c1  retn
```
