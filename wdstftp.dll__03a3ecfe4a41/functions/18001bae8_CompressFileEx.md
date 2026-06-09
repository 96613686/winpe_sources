# CompressFileEx

- ea: `0x18001bae8`
- end: `0x18001bd15`
- name: `CompressFileEx`
- size: `557`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023f00`

## callees

- `0x1800119e8`
- `0x180018e94`
- `0x180019188`
- `0x18001b6a0`
- `0x18001bae8`
- `0x18001bf60`
- `0x180022d7c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001bcc8`
- `KERNEL32!HeapFree` at `0x18001bcc8`
- `KERNEL32!GetLastError` at `0x18001bc93`
- `KERNEL32!GetLastError` at `0x18001bc93`
- `KERNEL32!CreateFileW` at `0x18001bbbc`
- `KERNEL32!CreateFileW` at `0x18001bbbc`
- `KERNEL32!SetLastError` at `0x18001bcda`
- `KERNEL32!SetLastError` at `0x18001bcef`
- `KERNEL32!SetLastError` at `0x18001bcda`
- `KERNEL32!SetLastError` at `0x18001bcef`
- `KERNEL32!GetProcessHeap` at `0x18001bcb4`
- `KERNEL32!GetProcessHeap` at `0x18001bcb4`

## pseudocode

```c
__int64 __fastcall CompressFileEx(
        __int64 a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        int a5,
        unsigned int a6,
        __int64 *a7,
        unsigned __int16 **a8,
        _QWORD *a9,
        unsigned int a10)
{
  __int64 FileW; // r15
  unsigned int v13; // ebx
  unsigned __int16 *v14; // rdi
  DWORD LastError; // ebp
  __int64 *v16; // r13
  _QWORD *v17; // r14
  unsigned int CompressionSize; // eax
  bool v19; // cc
  const WCHAR *TempFile; // rax
  __int64 v21; // rdx
  __int64 inited; // rax
  __int64 v23; // rax
  unsigned __int16 **v24; // rax
  HANDLE ProcessHeap; // rax
  __int64 v27; // [rsp+90h] [rbp+8h] BYREF
  __int64 v28; // [rsp+A8h] [rbp+20h]

  v28 = a4;
  FileW = -1;
  v27 = 0;
  v13 = 0;
  v14 = 0;
  LastError = 0;
  if ( a1 && a2 && a3 != (void *)-1LL && (v16 = a7) != 0 && (v17 = a9) != 0 )
  {
    CompressionSize = GetCompressionSize();
    v19 = *v17 <= 64LL;
    a6 = CompressionSize;
    if ( v19 )
      goto LABEL_21;
    if ( (unsigned int)DiamondIsCabinet(a3) )
      goto LABEL_21;
    TempFile = (const WCHAR *)GetTempFile(a1);
    v14 = (unsigned __int16 *)TempFile;
    if ( !TempFile )
      goto LABEL_21;
    if ( !*TempFile )
      goto LABEL_21;
    FileW = (__int64)CreateFileW(TempFile, 0xC0010000, 7u, 0, 2u, 0x48000100u, 0);
    if ( FileW == -1 )
      goto LABEL_21;
    v21 = *(_QWORD *)(a1 + 272);
    if ( !v21 )
    {
      inited = InitCompressionContext(a10, a6);
      *(_QWORD *)(a1 + 272) = inited;
      v21 = inited;
      if ( !inited )
        goto LABEL_21;
    }
    v13 = CompressFileDataToFile(a1, v21, a3, FileW, a6, v28, a5, &v27);
    if ( v13 && ((v13 = 0, v27 >= *v17) ? (v23 = 0) : (v23 = 100 * (*v17 - v27) / *v17), v23 >= 3) )
    {
      v24 = a8;
      *v17 = v27;
      *v16 = FileW;
      if ( v24 )
      {
        *v24 = v14;
        v14 = 0;
      }
      v13 = 1;
    }
    else
    {
LABEL_21:
      LastError = GetLastError();
      ReclaimTempFile(a1, FileW, v14);
    }
    if ( v14 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
    }
    if ( LastError )
      SetLastError(LastError);
    return v13;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18001bae8  mov     r11, rsp
0x18001baeb  mov     [r11+10h], rbx
0x18001baef  mov     [r11+20h], r9
0x18001baf3  push    rbp
0x18001baf4  push    rsi
0x18001baf5  push    rdi
0x18001baf6  push    r12
0x18001baf8  push    r13
0x18001bafa  push    r14
0x18001bafc  push    r15
0x18001bafe  sub     rsp, 50h
0x18001bb02  xor     eax, eax
0x18001bb04  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001bb08  mov     [r11+8], rax
0x18001bb0c  mov     r12, r8
0x18001bb0f  mov     rsi, rcx
0x18001bb12  mov     ebx, eax
0x18001bb14  mov     edi, eax
0x18001bb16  mov     ebp, eax
0x18001bb18  test    rcx, rcx
0x18001bb1b  jz      loc_18001BCEA
0x18001bb21  test    rdx, rdx
0x18001bb24  jz      loc_18001BCEA
0x18001bb2a  cmp     r8, r15
0x18001bb2d  jz      loc_18001BCEA
0x18001bb33  mov     r13, [rsp+88h+arg_30]
0x18001bb3b  test    r13, r13
0x18001bb3e  jz      loc_18001BCEA
0x18001bb44  mov     r14, [rsp+88h+arg_40]
0x18001bb4c  test    r14, r14
0x18001bb4f  jz      loc_18001BCEA
0x18001bb55  call    GetCompressionSize
0x18001bb5a  cmp     qword ptr [r14], 40h ; '@'
0x18001bb5e  mov     [rsp+88h+arg_28], eax
0x18001bb65  jle     loc_18001BC93
0x18001bb6b  mov     rcx, r12; hFile
0x18001bb6e  call    DiamondIsCabinet
0x18001bb73  test    eax, eax
0x18001bb75  jnz     loc_18001BC93
0x18001bb7b  mov     rcx, rsi
0x18001bb7e  call    GetTempFile
0x18001bb83  mov     rdi, rax
0x18001bb86  test    rax, rax
0x18001bb89  jz      loc_18001BC93
0x18001bb8f  cmp     [rax], bx
0x18001bb92  jz      loc_18001BC93
0x18001bb98  mov     [rsp+88h+hTemplateFile], rbx; hTemplateFile
0x18001bb9d  lea     r8d, [r15+8]; dwShareMode
0x18001bba1  mov     [rsp+88h+dwFlagsAndAttributes], 48000100h; dwFlagsAndAttributes
0x18001bba9  xor     r9d, r9d; lpSecurityAttributes
0x18001bbac  mov     edx, 0C0010000h; dwDesiredAccess
0x18001bbb1  mov     [rsp+88h+dwCreationDisposition], 2; dwCreationDisposition
0x18001bbb9  mov     rcx, rax; lpFileName
0x18001bbbc  call    cs:__imp_CreateFileW
0x18001bbc3  nop     dword ptr [rax+rax+00h]
0x18001bbc8  mov     r15, rax
0x18001bbcb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bbcf  jz      loc_18001BC93
0x18001bbd5  mov     rdx, [rsi+110h]
0x18001bbdc  test    rdx, rdx
0x18001bbdf  jnz     short loc_18001BC07
0x18001bbe1  mov     edx, [rsp+88h+arg_28]
0x18001bbe8  mov     ecx, [rsp+88h+arg_48]
0x18001bbef  call    InitCompressionContext
0x18001bbf4  mov     [rsi+110h], rax
0x18001bbfb  mov     rdx, rax
0x18001bbfe  test    rax, rax
0x18001bc01  jz      loc_18001BC93
0x18001bc07  lea     rax, [rsp+88h+arg_0]
0x18001bc0f  mov     r9, r15
0x18001bc12  mov     [rsp+88h+var_50], rax
0x18001bc17  mov     r8, r12
0x18001bc1a  mov     eax, [rsp+88h+arg_20]
0x18001bc21  mov     rcx, rsi
0x18001bc24  mov     dword ptr [rsp+88h+hTemplateFile], eax
0x18001bc28  mov     rax, [rsp+88h+arg_18]
0x18001bc30  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rax
0x18001bc35  mov     eax, [rsp+88h+arg_28]
0x18001bc3c  mov     [rsp+88h+dwCreationDisposition], eax
0x18001bc40  call    CompressFileDataToFile
0x18001bc45  mov     ebx, eax
0x18001bc47  test    eax, eax
0x18001bc49  jz      short loc_18001BC93
0x18001bc4b  mov     rcx, [rsp+88h+arg_0]
0x18001bc53  xor     ebx, ebx
0x18001bc55  cmp     rcx, [r14]
0x18001bc58  jge     short loc_18001BC6B
0x18001bc5a  mov     rax, [r14]
0x18001bc5d  sub     rax, rcx
0x18001bc60  imul    rax, 64h ; 'd'
0x18001bc64  cqo
0x18001bc66  idiv    qword ptr [r14]
0x18001bc69  jmp     short loc_18001BC6D
0x18001bc6b  xor     eax, eax
0x18001bc6d  cmp     rax, 3
0x18001bc71  jl      short loc_18001BC93
0x18001bc73  mov     rax, [rsp+88h+arg_38]
0x18001bc7b  mov     [r14], rcx
0x18001bc7e  mov     [r13+0], r15
0x18001bc82  test    rax, rax
0x18001bc85  jz      short loc_18001BC8C
0x18001bc87  mov     [rax], rdi
0x18001bc8a  xor     edi, edi
0x18001bc8c  mov     ebx, 1
0x18001bc91  jmp     short loc_18001BCAF
0x18001bc93  call    cs:__imp_GetLastError
0x18001bc9a  nop     dword ptr [rax+rax+00h]
0x18001bc9f  mov     r8, rdi
0x18001bca2  mov     rdx, r15
0x18001bca5  mov     rcx, rsi
0x18001bca8  mov     ebp, eax
0x18001bcaa  call    ReclaimTempFile
0x18001bcaf  test    rdi, rdi
0x18001bcb2  jz      short loc_18001BCD4
0x18001bcb4  call    cs:__imp_GetProcessHeap
0x18001bcbb  nop     dword ptr [rax+rax+00h]
0x18001bcc0  mov     r8, rdi; lpMem
0x18001bcc3  xor     edx, edx; dwFlags
0x18001bcc5  mov     rcx, rax; hHeap
0x18001bcc8  call    cs:__imp_HeapFree
0x18001bccf  nop     dword ptr [rax+rax+00h]
0x18001bcd4  test    ebp, ebp
0x18001bcd6  jz      short loc_18001BCE6
0x18001bcd8  mov     ecx, ebp; dwErrCode
0x18001bcda  call    cs:__imp_SetLastError
0x18001bce1  nop     dword ptr [rax+rax+00h]
0x18001bce6  mov     eax, ebx
0x18001bce8  jmp     short loc_18001BCFD
0x18001bcea  mov     ecx, 57h ; 'W'; dwErrCode
0x18001bcef  call    cs:__imp_SetLastError
0x18001bcf6  nop     dword ptr [rax+rax+00h]
0x18001bcfb  xor     eax, eax
0x18001bcfd  mov     rbx, [rsp+88h+arg_8]
0x18001bd05  add     rsp, 50h
0x18001bd09  pop     r15
0x18001bd0b  pop     r14
0x18001bd0d  pop     r13
0x18001bd0f  pop     r12
0x18001bd11  pop     rdi
0x18001bd12  pop     rsi
0x18001bd13  pop     rbp
0x18001bd14  retn
```
