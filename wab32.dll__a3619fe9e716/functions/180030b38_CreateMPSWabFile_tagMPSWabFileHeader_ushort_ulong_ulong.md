# CreateMPSWabFile(_tagMPSWabFileHeader *,ushort *,ulong,ulong)

- ea: `0x180030b38`
- end: `0x180030d1d`
- name: `?CreateMPSWabFile@@YAHPEAU_tagMPSWabFileHeader@@PEAGKK@Z`
- size: `485`
- prototype: `__int64 __fastcall(LPCVOID lpBuffer, LPCWSTR lpFileName, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180030300`
- `0x1800323b8`

## callees

- `0x180030b38`
- `0x180033ae0`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180030c7d`
- `KERNEL32!LocalAlloc` at `0x180030c7d`
- `KERNEL32!CreateFileW` at `0x180030b86`
- `KERNEL32!CreateFileW` at `0x180030b86`
- `KERNEL32!WriteFile` at `0x180030c67`
- `KERNEL32!WriteFile` at `0x180030cae`
- `KERNEL32!WriteFile` at `0x180030cdb`
- `KERNEL32!WriteFile` at `0x180030c67`
- `KERNEL32!WriteFile` at `0x180030cae`
- `KERNEL32!WriteFile` at `0x180030cdb`
- `KERNEL32!CloseHandle` at `0x180030cf6`
- `KERNEL32!CloseHandle` at `0x180030cf6`

## pseudocode

```c
_BOOL8 __fastcall CreateMPSWabFile(char *lpBuffer, LPCWSTR lpFileName, int a3, int a4)
{
  int v7; // edi
  HANDLE FileW; // r14
  int v9; // r9d
  __int64 v10; // r8
  __int64 v11; // rdx
  int v12; // ecx
  int v13; // eax
  HLOCAL v14; // rax
  const void *v15; // rbp
  int i; // esi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-48h] BYREF
  void *v19[8]; // [rsp+48h] [rbp-40h] BYREF

  NumberOfBytesWritten = 0;
  v19[0] = 0;
  v7 = -2147467259;
  FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    *((_DWORD *)lpBuffer + 4) = 0;
    *((_DWORD *)lpBuffer + 30) = 0;
    v9 = 0;
    *((_DWORD *)lpBuffer + 31) = a3;
    v10 = 0;
    *(_OWORD *)lpBuffer = xmmword_18009B828;
    *((_DWORD *)lpBuffer + 32) = 0;
    *(_QWORD *)(lpBuffer + 148) = 0;
    *(_QWORD *)(lpBuffer + 156) = 0;
    *((_DWORD *)lpBuffer + 5) = 1;
    *((_DWORD *)lpBuffer + 35) = 164;
    *((_DWORD *)lpBuffer + 34) = 0;
    *((_DWORD *)lpBuffer + 36) = 0;
    *((_DWORD *)lpBuffer + 33) = a4;
    do
    {
      v11 = 2 * v10;
      *(_DWORD *)&lpBuffer[8 * v11 + 28] = 0;
      *(_DWORD *)&lpBuffer[8 * v11 + 36] = 0;
      if ( v9 )
      {
        v13 = *(_DWORD *)&lpBuffer[16 * v10 + 8] + *(_DWORD *)&lpBuffer[16 * v10 + 16];
        v12 = 68;
      }
      else
      {
        v12 = 8;
        v13 = *((_DWORD *)lpBuffer + 35) + *((_DWORD *)lpBuffer + 33);
      }
      *(_DWORD *)&lpBuffer[16 * v10 + 32] = v13;
      ++v9;
      ++v10;
      *(_DWORD *)&lpBuffer[8 * v11 + 24] = v12 * a3;
    }
    while ( v9 < 6 );
    if ( WriteFile(FileW, lpBuffer, 0xA4u, &NumberOfBytesWritten, 0) )
    {
      v14 = LocalAlloc(0x40u, *((unsigned int *)lpBuffer + 10));
      v19[0] = v14;
      v15 = v14;
      if ( v14 )
      {
        if ( WriteFile(FileW, v14, *((_DWORD *)lpBuffer + 33), &NumberOfBytesWritten, 0) )
        {
          for ( i = 0; i < 6; ++i )
          {
            if ( !WriteFile(FileW, v15, *(_DWORD *)&lpBuffer[16 * i + 24], &NumberOfBytesWritten, 0) )
              goto LABEL_16;
          }
          LocalFreeAndNull(v19);
          CloseHandle(FileW);
          v7 = 0;
        }
      }
      else
      {
        v7 = -2147024882;
      }
    }
  }
LABEL_16:
  LocalFreeAndNull(v19);
  return v7 >= 0;
}

```

## disassembly

```asm
0x180030b38  push    rbx
0x180030b3a  push    rbp
0x180030b3b  push    rsi
0x180030b3c  push    rdi
0x180030b3d  push    r14
0x180030b3f  push    r15
0x180030b41  sub     rsp, 58h
0x180030b45  xor     r15d, r15d
0x180030b48  mov     rax, rdx
0x180030b4b  mov     [rsp+88h+hTemplateFile], r15; hTemplateFile
0x180030b50  mov     esi, r9d
0x180030b53  mov     ebp, r8d
0x180030b56  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180030b5e  mov     rbx, rcx
0x180030b61  mov     [rsp+88h+dwCreationDisposition], 2; dwCreationDisposition
0x180030b69  xor     r9d, r9d; lpSecurityAttributes
0x180030b6c  mov     [rsp+88h+NumberOfBytesWritten], r15d
0x180030b71  xor     r8d, r8d; dwShareMode
0x180030b74  mov     [rsp+88h+var_40], r15
0x180030b79  mov     edx, 40000000h; dwDesiredAccess
0x180030b7e  mov     rcx, rax; lpFileName
0x180030b81  mov     edi, 80004005h
0x180030b86  call    cs:__imp_CreateFileW
0x180030b8c  mov     r14, rax
0x180030b8f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030b93  jz      loc_180030CFF
0x180030b99  mov     [rbx+10h], r15d
0x180030b9d  mov     r11d, 0A4h
0x180030ba3  movups  xmm0, cs:xmmword_18009B828
0x180030baa  mov     [rbx+78h], r15d
0x180030bae  mov     r9d, r15d
0x180030bb1  mov     [rbx+7Ch], ebp
0x180030bb4  mov     r8d, r15d
0x180030bb7  movdqu  xmmword ptr [rbx], xmm0
0x180030bbb  mov     [rbx+80h], r15d
0x180030bc2  mov     [rbx+94h], r15
0x180030bc9  mov     [rbx+9Ch], r15
0x180030bd0  mov     dword ptr [rbx+14h], 1
0x180030bd7  mov     [rbx+8Ch], r11d
0x180030bde  mov     [rbx+88h], r15d
0x180030be5  mov     [rbx+90h], r15d
0x180030bec  mov     [rbx+84h], esi
0x180030bf2  mov     rdx, r8
0x180030bf5  lea     r10, [r8+2]
0x180030bf9  add     rdx, rdx
0x180030bfc  add     r10, r10
0x180030bff  mov     [rbx+rdx*8+1Ch], r15d
0x180030c04  mov     [rbx+rdx*8+24h], r15d
0x180030c09  test    r9d, r9d
0x180030c0c  jnz     short loc_180030C20
0x180030c0e  mov     eax, [rbx+84h]
0x180030c14  lea     ecx, [r9+8]
0x180030c18  add     eax, [rbx+8Ch]
0x180030c1e  jmp     short loc_180030C3B
0x180030c20  lea     rcx, [r8-1]
0x180030c24  lea     rax, [rcx+2]
0x180030c28  shl     rcx, 4
0x180030c2c  add     rax, rax
0x180030c2f  mov     eax, [rbx+rax*8]
0x180030c32  add     eax, [rcx+rbx+18h]
0x180030c36  mov     ecx, 44h ; 'D'
0x180030c3b  mov     [rbx+r10*8], eax
0x180030c3f  inc     r9d
0x180030c42  mov     eax, ebp
0x180030c44  inc     r8
0x180030c47  imul    eax, ecx
0x180030c4a  mov     [rbx+rdx*8+18h], eax
0x180030c4e  cmp     r9d, 6
0x180030c52  jl      short loc_180030BF2
0x180030c54  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180030c59  mov     qword ptr [rsp+88h+dwCreationDisposition], r15; lpOverlapped
0x180030c5e  mov     r8d, r11d; nNumberOfBytesToWrite
0x180030c61  mov     rdx, rbx; lpBuffer
0x180030c64  mov     rcx, r14; hFile
0x180030c67  call    cs:__imp_WriteFile
0x180030c6d  test    eax, eax
0x180030c6f  jz      loc_180030CFF
0x180030c75  mov     edx, [rbx+28h]; uBytes
0x180030c78  mov     ecx, 40h ; '@'; uFlags
0x180030c7d  call    cs:__imp_LocalAlloc
0x180030c83  mov     [rsp+88h+var_40], rax
0x180030c88  mov     rbp, rax
0x180030c8b  test    rax, rax
0x180030c8e  jnz     short loc_180030C97
0x180030c90  mov     edi, 8007000Eh
0x180030c95  jmp     short loc_180030CFF
0x180030c97  mov     r8d, [rbx+84h]; nNumberOfBytesToWrite
0x180030c9e  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180030ca3  mov     rdx, rbp; lpBuffer
0x180030ca6  mov     qword ptr [rsp+88h+dwCreationDisposition], r15; lpOverlapped
0x180030cab  mov     rcx, r14; hFile
0x180030cae  call    cs:__imp_WriteFile
0x180030cb4  test    eax, eax
0x180030cb6  jz      short loc_180030CFF
0x180030cb8  mov     esi, r15d
0x180030cbb  cmp     esi, 6
0x180030cbe  jge     short loc_180030CE9
0x180030cc0  movsxd  r8, esi
0x180030cc3  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180030cc8  add     r8, r8
0x180030ccb  mov     qword ptr [rsp+88h+dwCreationDisposition], r15; lpOverlapped
0x180030cd0  mov     rdx, rbp; lpBuffer
0x180030cd3  mov     rcx, r14; hFile
0x180030cd6  mov     r8d, [rbx+r8*8+18h]; nNumberOfBytesToWrite
0x180030cdb  call    cs:__imp_WriteFile
0x180030ce1  test    eax, eax
0x180030ce3  jz      short loc_180030CFF
0x180030ce5  inc     esi
0x180030ce7  jmp     short loc_180030CBB
0x180030ce9  lea     rcx, [rsp+88h+var_40]; void **
0x180030cee  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z
0x180030cf3  mov     rcx, r14; hObject
0x180030cf6  call    cs:__imp_CloseHandle
0x180030cfc  mov     edi, r15d
0x180030cff  lea     rcx, [rsp+88h+var_40]; void **
0x180030d04  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z
0x180030d09  not     edi
0x180030d0b  shr     edi, 1Fh
0x180030d0e  mov     eax, edi
0x180030d10  add     rsp, 58h
0x180030d14  pop     r15
0x180030d16  pop     r14
0x180030d18  pop     rdi
0x180030d19  pop     rsi
0x180030d1a  pop     rbp
0x180030d1b  pop     rbx
0x180030d1c  retn
```
