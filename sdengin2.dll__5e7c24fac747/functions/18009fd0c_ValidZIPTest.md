# ValidZIPTest

- ea: `0x18009fd0c`
- end: `0x18009ffbc`
- name: `ValidZIPTest`
- size: `688`
- prototype: `__int64 __fastcall(LPCSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800a0f48`

## callees

- `0x18009da0c`
- `0x18009e540`
- `0x18009fd0c`
- `0x1800a359c`
- `0x1800a3608`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x18009ff91`
- `KERNEL32!GlobalUnlock` at `0x18009ff91`
- `KERNEL32!lstrcmpA` at `0x18009fd4b`
- `KERNEL32!lstrcmpA` at `0x18009fd4b`
- `KERNEL32!GlobalLock` at `0x18009fe2d`
- `KERNEL32!GlobalLock` at `0x18009fe2d`
- `KERNEL32!ReadFile` at `0x18009fe55`
- `KERNEL32!ReadFile` at `0x18009fe55`
- `KERNEL32!CloseHandle` at `0x18009fdca`
- `KERNEL32!CloseHandle` at `0x18009ff56`
- `KERNEL32!CloseHandle` at `0x18009fdca`
- `KERNEL32!CloseHandle` at `0x18009ff56`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18009fd7d`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18009fd7d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18009fe1c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18009fe1c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009ff9f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009ff9f`

## pseudocode

```c
__int64 __fastcall ValidZIPTest(LPCSTR lpFileName, __int64 a2)
{
  int v4; // r13d
  HANDLE FileA; // rax
  void *v6; // r15
  __int64 v7; // rbp
  unsigned int v8; // esi
  _BYTE *v10; // r14
  __int64 v11; // rdi
  void *v12; // rdi
  unsigned int v13; // ebx
  DWORD v14; // r13d
  HGLOBAL v15; // rax
  void *v16; // rax
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rdx
  char v20; // r9
  __int64 v21; // rax
  char v22; // bp
  int v23; // r10d
  char v24; // r11
  unsigned int v25; // eax
  DWORD NumberOfBytesRead; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v29; // [rsp+A8h] [rbp+20h]

  NumberOfBytesRead = 0;
  if ( lpFileName
    && *lpFileName
    && lstrcmpA(lpFileName, "-")
    && (v4 = 3, FileA = CreateFileA(lpFileName, 0x80000000, 0, 0, 3u, 0x80u, 0), v6 = FileA, FileA != (HANDLE)-1LL) )
  {
    v7 = DZGetFileSize(FileA);
    if ( (!*(_DWORD *)(a2 + 624) || *(_DWORD *)(a2 + 628)) && v7 >= 0xFFFFFFFFLL )
    {
      v8 = 8;
LABEL_11:
      CloseHandle(v6);
      return v8;
    }
    if ( v7 < 22 )
    {
      v8 = 11;
      goto LABEL_11;
    }
    v10 = 0;
    v11 = 65579;
    if ( v7 < 65579 )
      v11 = v7;
    v29 = v11;
    if ( DZSetFilePointer(v6, v7 - v11, 0) == v7 - v11 )
    {
      v14 = v11;
      v15 = GlobalAlloc(2u, (unsigned int)v11);
      v12 = v15;
      if ( v15 && (v16 = GlobalLock(v15), (v10 = v16) != 0) )
      {
        if ( !ReadFile(v6, v16, v14, &NumberOfBytesRead, 0) || (v13 = 0, NumberOfBytesRead != v14) )
          v13 = 11;
      }
      else
      {
        v13 = 4;
      }
      v4 = 3;
    }
    else
    {
      v12 = 0;
      v13 = 11;
    }
    v17 = v29;
    v18 = 22;
    if ( v7 != 22 )
      v18 = 18;
    v19 = v29 - v18;
    LODWORD(v29) = 0;
    do
    {
      if ( v13 || v19 < 0 || v18 > v17 )
        break;
      v20 = v10[v19];
      v21 = v19 + 2;
      v22 = v10[v19 + 1];
      v23 = 18 - v4;
      do
      {
        v24 = v10[v21++];
        if ( v20 == 80 && v22 == 75 && v24 == 5 && v10[v21] == 6 )
        {
          if ( v10[v21 + 1] || v10[v21 + 2] )
          {
            v13 = 21;
          }
          else
          {
            v13 = 0;
            LODWORD(v29) = 1;
          }
        }
        --v23;
        v20 = v22;
        v22 = v24;
      }
      while ( v23 > 0 );
      if ( !(_DWORD)v29 && v19 <= 0 )
        v13 = 11;
      v18 += 18;
      v19 = 0;
      v4 = 0;
      if ( v17 - v18 >= 0 )
        v19 = v17 - v18;
    }
    while ( !(_DWORD)v29 );
    CloseHandle(v6);
    if ( v13 == 11 )
    {
      v25 = dzDriveFromPath(lpFileName);
      if ( (unsigned int)dzIsMediaRemovable(v25, a2) )
        v13 = 21;
    }
    if ( v10 )
      GlobalUnlock(v12);
    if ( v12 )
      GlobalFree(v12);
  }
  else
  {
    return 0;
  }
  return v13;
}

```

## disassembly

```asm
0x18009fd0c  mov     rax, rsp
0x18009fd0f  mov     [rax+10h], rdx
0x18009fd13  mov     [rax+8], rcx
0x18009fd17  push    rbx
0x18009fd18  push    rbp
0x18009fd19  push    rsi
0x18009fd1a  push    rdi
0x18009fd1b  push    r12
0x18009fd1d  push    r13
0x18009fd1f  push    r14
0x18009fd21  push    r15
0x18009fd23  sub     rsp, 48h
0x18009fd27  xor     edi, edi
0x18009fd29  mov     rbx, rdx
0x18009fd2c  mov     [rax+18h], edi
0x18009fd2f  mov     r12, rcx
0x18009fd32  test    rcx, rcx
0x18009fd35  jz      loc_18009FFA7
0x18009fd3b  cmp     [rcx], dil
0x18009fd3e  jz      loc_18009FFA7
0x18009fd44  lea     rdx, asc_1800E85DC; "-"
0x18009fd4b  call    cs:__imp_lstrcmpA
0x18009fd51  test    eax, eax
0x18009fd53  jz      loc_18009FFA7
0x18009fd59  mov     [rsp+88h+hTemplateFile], rdi; hTemplateFile
0x18009fd5e  lea     r13d, [rdi+3]
0x18009fd62  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009fd6a  xor     r9d, r9d; lpSecurityAttributes
0x18009fd6d  xor     r8d, r8d; dwShareMode
0x18009fd70  mov     [rsp+88h+dwCreationDisposition], r13d; dwCreationDisposition
0x18009fd75  mov     edx, 80000000h; dwDesiredAccess
0x18009fd7a  mov     rcx, r12; lpFileName
0x18009fd7d  call    cs:__imp_CreateFileA
0x18009fd83  mov     r15, rax
0x18009fd86  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009fd8a  jz      loc_18009FFA7
0x18009fd90  mov     rcx, rax
0x18009fd93  call    DZGetFileSize
0x18009fd98  mov     rbp, rax
0x18009fd9b  cmp     [rbx+270h], edi
0x18009fda1  jz      short loc_18009FDAB
0x18009fda3  cmp     [rbx+274h], edi
0x18009fda9  jz      short loc_18009FDBC
0x18009fdab  mov     eax, 0FFFFFFFFh
0x18009fdb0  cmp     rbp, rax
0x18009fdb3  jl      short loc_18009FDBC
0x18009fdb5  mov     esi, 8
0x18009fdba  jmp     short loc_18009FDC7
0x18009fdbc  cmp     rbp, 16h
0x18009fdc0  jge     short loc_18009FDD7
0x18009fdc2  mov     esi, 0Bh
0x18009fdc7  mov     rcx, r15; hObject
0x18009fdca  call    cs:__imp_CloseHandle
0x18009fdd0  mov     eax, esi
0x18009fdd2  jmp     loc_18009FFAB
0x18009fdd7  mov     r14, rdi
0x18009fdda  mov     rbx, rbp
0x18009fddd  mov     edi, 1002Bh
0x18009fde2  mov     rcx, r15
0x18009fde5  cmp     rbp, rdi
0x18009fde8  cmovl   rdi, rbp
0x18009fdec  xor     r8d, r8d
0x18009fdef  sub     rbx, rdi
0x18009fdf2  mov     [rsp+88h+arg_18], rdi
0x18009fdfa  mov     rdx, rbx
0x18009fdfd  call    DZSetFilePointer
0x18009fe02  mov     esi, 0Bh
0x18009fe07  cmp     rax, rbx
0x18009fe0a  jz      short loc_18009FE12
0x18009fe0c  xor     edi, edi
0x18009fe0e  mov     ebx, esi
0x18009fe10  jmp     short loc_18009FE7A
0x18009fe12  mov     edx, edi; dwBytes
0x18009fe14  mov     ecx, 2; uFlags
0x18009fe19  mov     r13d, edi
0x18009fe1c  call    cs:__imp_GlobalAlloc
0x18009fe22  mov     rdi, rax
0x18009fe25  test    rax, rax
0x18009fe28  jz      short loc_18009FE6F
0x18009fe2a  mov     rcx, rax; hMem
0x18009fe2d  call    cs:__imp_GlobalLock
0x18009fe33  mov     r14, rax
0x18009fe36  test    rax, rax
0x18009fe39  jz      short loc_18009FE6F
0x18009fe3b  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009fe43  mov     qword ptr [rsp+88h+dwCreationDisposition], 0; lpOverlapped
0x18009fe4c  mov     r8d, r13d; nNumberOfBytesToRead
0x18009fe4f  mov     rdx, rax; lpBuffer
0x18009fe52  mov     rcx, r15; hFile
0x18009fe55  call    cs:__imp_ReadFile
0x18009fe5b  test    eax, eax
0x18009fe5d  jz      short loc_18009FE6B
0x18009fe5f  xor     ebx, ebx
0x18009fe61  cmp     [rsp+88h+NumberOfBytesRead], r13d
0x18009fe69  jz      short loc_18009FE74
0x18009fe6b  mov     ebx, esi
0x18009fe6d  jmp     short loc_18009FE74
0x18009fe6f  mov     ebx, 4
0x18009fe74  mov     r13d, 3
0x18009fe7a  mov     r8, [rsp+88h+arg_18]
0x18009fe82  mov     ecx, 16h
0x18009fe87  cmp     rbp, rcx
0x18009fe8a  mov     rdx, r8
0x18009fe8d  lea     r12d, [rcx-4]
0x18009fe91  cmovnz  ecx, r12d
0x18009fe95  sub     rdx, rcx
0x18009fe98  xor     r9d, r9d
0x18009fe9b  mov     dword ptr [rsp+88h+arg_18], r9d
0x18009fea3  test    ebx, ebx
0x18009fea5  jnz     loc_18009FF53
0x18009feab  test    rdx, rdx
0x18009feae  js      loc_18009FF53
0x18009feb4  cmp     rcx, r8
0x18009feb7  jg      loc_18009FF53
0x18009febd  mov     r9b, [r14+rdx]
0x18009fec1  lea     rax, [rdx+2]
0x18009fec5  mov     bpl, [r14+rdx+1]
0x18009feca  mov     r10d, r12d
0x18009fecd  sub     r10d, r13d
0x18009fed0  mov     r11b, [r14+rax]
0x18009fed4  inc     rax
0x18009fed7  cmp     r9b, 50h ; 'P'
0x18009fedb  jnz     short loc_18009FF14
0x18009fedd  cmp     bpl, 4Bh ; 'K'
0x18009fee1  jnz     short loc_18009FF14
0x18009fee3  cmp     r11b, 5
0x18009fee7  jnz     short loc_18009FF14
0x18009fee9  cmp     byte ptr [r14+rax], 6
0x18009feee  jnz     short loc_18009FF14
0x18009fef0  cmp     byte ptr [r14+rax+1], 0
0x18009fef6  jnz     short loc_18009FF0F
0x18009fef8  cmp     byte ptr [r14+rax+2], 0
0x18009fefe  jnz     short loc_18009FF0F
0x18009ff00  xor     ebx, ebx
0x18009ff02  mov     dword ptr [rsp+88h+arg_18], 1
0x18009ff0d  jmp     short loc_18009FF14
0x18009ff0f  mov     ebx, 15h
0x18009ff14  dec     r10d
0x18009ff17  mov     r9b, bpl
0x18009ff1a  mov     bpl, r11b
0x18009ff1d  test    r10d, r10d
0x18009ff20  jg      short loc_18009FED0
0x18009ff22  mov     r9d, dword ptr [rsp+88h+arg_18]
0x18009ff2a  test    r9d, r9d
0x18009ff2d  jnz     short loc_18009FF35
0x18009ff2f  test    rdx, rdx
0x18009ff32  cmovle  ebx, esi
0x18009ff35  add     rcx, r12
0x18009ff38  mov     edx, 0
0x18009ff3d  mov     rax, r8
0x18009ff40  mov     r13d, edx
0x18009ff43  sub     rax, rcx
0x18009ff46  cmovns  rdx, rax
0x18009ff4a  test    r9d, r9d
0x18009ff4d  jz      loc_18009FEA3
0x18009ff53  mov     rcx, r15; hObject
0x18009ff56  call    cs:__imp_CloseHandle
0x18009ff5c  mov     r12, [rsp+88h+lpszStart]
0x18009ff64  cmp     ebx, esi
0x18009ff66  jnz     short loc_18009FF89
0x18009ff68  mov     rcx, r12; lpszStart
0x18009ff6b  call    dzDriveFromPath
0x18009ff70  mov     rdx, [rsp+88h+arg_8]
0x18009ff78  mov     ecx, eax
0x18009ff7a  call    dzIsMediaRemovable
0x18009ff7f  test    eax, eax
0x18009ff81  mov     eax, 15h
0x18009ff86  cmovnz  ebx, eax
0x18009ff89  test    r14, r14
0x18009ff8c  jz      short loc_18009FF97
0x18009ff8e  mov     rcx, rdi; hMem
0x18009ff91  call    cs:__imp_GlobalUnlock
0x18009ff97  test    rdi, rdi
0x18009ff9a  jz      short loc_18009FFA9
0x18009ff9c  mov     rcx, rdi; hMem
0x18009ff9f  call    cs:__imp_GlobalFree
0x18009ffa5  jmp     short loc_18009FFA9
0x18009ffa7  mov     ebx, edi
0x18009ffa9  mov     eax, ebx
0x18009ffab  add     rsp, 48h
0x18009ffaf  pop     r15
0x18009ffb1  pop     r14
0x18009ffb3  pop     r13
0x18009ffb5  pop     r12
0x18009ffb7  pop     rdi
0x18009ffb8  pop     rsi
0x18009ffb9  pop     rbp
0x18009ffba  pop     rbx
0x18009ffbb  retn
```
