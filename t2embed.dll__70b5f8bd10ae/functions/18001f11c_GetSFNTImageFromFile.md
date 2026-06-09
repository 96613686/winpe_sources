# GetSFNTImageFromFile

- ea: `0x18001f11c`
- end: `0x18001f3db`
- name: `GetSFNTImageFromFile`
- size: `703`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001ef44`
- `0x18001fcb0`

## callees

- `0x180017ee0`
- `0x180019dc0`
- `0x18001f11c`
- `0x18002a54e`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x18001f27d`
- `KERNEL32!UnmapViewOfFile` at `0x18001f2a4`
- `KERNEL32!UnmapViewOfFile` at `0x18001f2d2`
- `KERNEL32!UnmapViewOfFile` at `0x18001f3a7`
- `KERNEL32!UnmapViewOfFile` at `0x18001f27d`
- `KERNEL32!UnmapViewOfFile` at `0x18001f2a4`
- `KERNEL32!UnmapViewOfFile` at `0x18001f2d2`
- `KERNEL32!UnmapViewOfFile` at `0x18001f3a7`
- `KERNEL32!CreateFileA` at `0x18001f159`
- `KERNEL32!CreateFileA` at `0x18001f159`
- `KERNEL32!CloseHandle` at `0x18001f28b`
- `KERNEL32!CloseHandle` at `0x18001f294`
- `KERNEL32!CloseHandle` at `0x18001f3c1`
- `KERNEL32!CloseHandle` at `0x18001f28b`
- `KERNEL32!CloseHandle` at `0x18001f294`
- `KERNEL32!CloseHandle` at `0x18001f3c1`
- `KERNEL32!CreateFileMappingA` at `0x18001f19c`
- `KERNEL32!CreateFileMappingA` at `0x18001f19c`
- `KERNEL32!GetFileSize` at `0x18001f171`
- `KERNEL32!GetFileSize` at `0x18001f171`
- `KERNEL32!MapViewOfFile` at `0x18001f1c4`
- `KERNEL32!MapViewOfFile` at `0x18001f1c4`

## pseudocode

```c
__int64 __fastcall GetSFNTImageFromFile(const CHAR *a1, unsigned __int16 a2, unsigned __int8 **a3, unsigned int *a4)
{
  unsigned int v5; // edi
  HANDLE FileA; // rax
  void *v8; // rbp
  DWORD FileSize; // eax
  HANDLE FileMappingA; // rax
  void *v11; // r15
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // rbx
  unsigned int v14; // ebx
  unsigned int v15; // r8d
  int v16; // esi
  int v17; // ecx
  unsigned int v18; // edi
  unsigned int v20; // r8d
  unsigned __int8 *v21; // rax
  unsigned __int8 *v22; // rcx
  int v23; // r11d
  int v24; // esi
  int v25; // eax
  __int64 v26; // rax

  v5 = a2;
  FileA = CreateFileA(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v8 = FileA;
  if ( FileA != (HANDLE)-1LL )
  {
    FileSize = GetFileSize(FileA, 0);
    *a4 = FileSize;
    if ( FileSize != -1 )
    {
      FileMappingA = CreateFileMappingA(v8, 0, 2u, 0, FileSize, 0);
      v11 = FileMappingA;
      if ( FileMappingA )
      {
        v12 = (unsigned __int8 *)MapViewOfFile(FileMappingA, 4u, 0, 0, 0);
        v13 = v12;
        if ( !v12 )
        {
          v14 = 23;
LABEL_13:
          CloseHandle(v11);
          CloseHandle(v8);
          return v14;
        }
        v15 = *a4;
        if ( *a4 >= 4 )
        {
          v16 = v12[3] | ((v12[2] | ((v12[1] | (*v12 << 8)) << 8)) << 8);
          if ( v16 == 1953784678 )
          {
            if ( v15 < 0xC )
              goto LABEL_12;
            v17 = v12[11] | ((v12[10] | ((v12[9] | (v12[8] << 8)) << 8)) << 8);
            if ( v5 > v17 - 1 || v15 < 4 * v17 + 12 )
            {
              UnmapViewOfFile(v12);
              v14 = 24;
              goto LABEL_13;
            }
            v18 = v12[4 * v5 + 15] | ((v12[4 * v5 + 14] | ((v12[4 * v5 + 13] | (v12[4 * v5 + 12] << 8)) << 8)) << 8);
            if ( v15 <= v18 )
              goto LABEL_12;
          }
          else
          {
            v18 = 0;
          }
          v20 = v15 - v18;
          *a4 = v20;
          v21 = (unsigned __int8 *)T2malloc(v20);
          *a3 = v21;
          if ( !v21 )
          {
            UnmapViewOfFile(v13);
            v14 = 7;
            goto LABEL_13;
          }
          memcpy_0(v21, &v13[v18], *a4);
          if ( v16 != 1953784678 )
          {
LABEL_23:
            UnmapViewOfFile(v13);
            v14 = 0;
            goto LABEL_13;
          }
          v22 = *a3;
          if ( *a4 >= 6 )
          {
            v23 = v22[5] | (v22[4] << 8);
            if ( *a4 >= 16 * v23 + 20 )
            {
              v24 = 0;
              if ( v23 )
              {
                do
                {
                  v25 = 16 * v24++;
                  v26 = (unsigned int)(v25 + 20);
                  *(_DWORD *)&(*a3)[(unsigned int)v26] = ((((*a3)[(unsigned int)v26 + 3]
                                                          | (((*a3)[(unsigned int)v26 + 2]
                                                            | ((((*a3)[v26] << 8) | (*a3)[v26 + 1]) << 8)) << 8))
                                                         - v18) >> 24)
                                                       | (((unsigned __int8)((((*a3)[(unsigned int)v26 + 3]
                                                                             | (((*a3)[(unsigned int)v26 + 2]
                                                                               | ((((*a3)[v26] << 8) | (*a3)[v26 + 1]) << 8)) << 8))
                                                                            - v18) >> 16)
                                                         | ((((unsigned __int8)((*a3)[(unsigned int)v26 + 3] - v18) << 8)
                                                           | (unsigned __int8)((unsigned __int16)(((*a3)[(unsigned int)v26 + 3]
                                                                                                 | (unsigned __int16)(((*a3)[(unsigned int)v26 + 2] | (unsigned __int16)(_byteswap_ushort(*(_WORD *)&(*a3)[v26]) << 8)) << 8))
                                                                                                - v18) >> 8)) << 8)) << 8);
                }
                while ( v24 < v23 );
              }
              goto LABEL_23;
            }
          }
          T2free(v22);
        }
LABEL_12:
        UnmapViewOfFile(v13);
        v14 = 267;
        goto LABEL_13;
      }
    }
    CloseHandle(v8);
  }
  return 23;
}

```

## disassembly

```asm
0x18001f11c  push    rbx
0x18001f11e  push    rbp
0x18001f11f  push    rsi
0x18001f120  push    rdi
0x18001f121  push    r12
0x18001f123  push    r14
0x18001f125  push    r15
0x18001f127  sub     rsp, 40h
0x18001f12b  mov     r14, r9
0x18001f12e  movzx   edi, dx
0x18001f131  xor     r9d, r9d; lpSecurityAttributes
0x18001f134  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18001f13d  mov     r12, r8
0x18001f140  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001f148  mov     edx, 80000000h; dwDesiredAccess
0x18001f14d  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18001f155  lea     r8d, [r9+1]; dwShareMode
0x18001f159  call    cs:__imp_CreateFileA
0x18001f15f  mov     rbp, rax
0x18001f162  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f166  jz      loc_18001F3C7
0x18001f16c  xor     edx, edx; lpFileSizeHigh
0x18001f16e  mov     rcx, rax; hFile
0x18001f171  call    cs:__imp_GetFileSize
0x18001f177  mov     [r14], eax
0x18001f17a  cmp     eax, 0FFFFFFFFh
0x18001f17d  jz      loc_18001F3BE
0x18001f183  xor     r9d, r9d; dwMaximumSizeHigh
0x18001f186  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpName
0x18001f18f  xor     edx, edx; lpFileMappingAttributes
0x18001f191  mov     [rsp+78h+dwCreationDisposition], eax; dwMaximumSizeLow
0x18001f195  mov     rcx, rbp; hFile
0x18001f198  lea     r8d, [r9+2]; flProtect
0x18001f19c  call    cs:__imp_CreateFileMappingA
0x18001f1a2  mov     r15, rax
0x18001f1a5  test    rax, rax
0x18001f1a8  jz      loc_18001F3BE
0x18001f1ae  xor     r9d, r9d; dwFileOffsetLow
0x18001f1b1  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18001f1ba  xor     r8d, r8d; dwFileOffsetHigh
0x18001f1bd  mov     rcx, rax; hFileMappingObject
0x18001f1c0  lea     edx, [r9+4]; dwDesiredAccess
0x18001f1c4  call    cs:__imp_MapViewOfFile
0x18001f1ca  mov     rbx, rax
0x18001f1cd  test    rax, rax
0x18001f1d0  jnz     short loc_18001F1DA
0x18001f1d2  lea     ebx, [rax+17h]
0x18001f1d5  jmp     loc_18001F288
0x18001f1da  mov     r8d, [r14]
0x18001f1dd  cmp     r8d, 4
0x18001f1e1  jb      loc_18001F27A
0x18001f1e7  movzx   esi, byte ptr [rax]
0x18001f1ea  movzx   eax, byte ptr [rax+1]
0x18001f1ee  shl     esi, 8
0x18001f1f1  or      esi, eax
0x18001f1f3  movzx   eax, byte ptr [rbx+2]
0x18001f1f7  shl     esi, 8
0x18001f1fa  or      esi, eax
0x18001f1fc  movzx   eax, byte ptr [rbx+3]
0x18001f200  shl     esi, 8
0x18001f203  or      esi, eax
0x18001f205  cmp     esi, 74746366h
0x18001f20b  jnz     loc_18001F2B1
0x18001f211  cmp     r8d, 0Ch
0x18001f215  jb      short loc_18001F27A
0x18001f217  movzx   eax, byte ptr [rbx+9]
0x18001f21b  movzx   ecx, byte ptr [rbx+8]
0x18001f21f  shl     ecx, 8
0x18001f222  or      ecx, eax
0x18001f224  movzx   eax, byte ptr [rbx+0Ah]
0x18001f228  shl     ecx, 8
0x18001f22b  or      ecx, eax
0x18001f22d  movzx   eax, byte ptr [rbx+0Bh]
0x18001f231  shl     ecx, 8
0x18001f234  or      ecx, eax
0x18001f236  lea     eax, [rcx-1]
0x18001f239  cmp     edi, eax
0x18001f23b  ja      short loc_18001F2A1
0x18001f23d  lea     eax, ds:0Ch[rcx*4]
0x18001f244  cmp     r8d, eax
0x18001f247  jb      short loc_18001F2A1
0x18001f249  lea     eax, ds:0[rdi*4]
0x18001f250  movzx   edi, byte ptr [rax+rbx+0Ch]
0x18001f255  shl     edi, 8
0x18001f258  mov     ecx, eax
0x18001f25a  movzx   eax, byte ptr [rax+rbx+0Dh]
0x18001f25f  or      edi, eax
0x18001f261  shl     edi, 8
0x18001f264  movzx   eax, byte ptr [rcx+rbx+0Eh]
0x18001f269  or      edi, eax
0x18001f26b  movzx   eax, byte ptr [rcx+rbx+0Fh]
0x18001f270  shl     edi, 8
0x18001f273  or      edi, eax
0x18001f275  cmp     r8d, edi
0x18001f278  ja      short loc_18001F2B3
0x18001f27a  mov     rcx, rbx; lpBaseAddress
0x18001f27d  call    cs:__imp_UnmapViewOfFile
0x18001f283  mov     ebx, 10Bh
0x18001f288  mov     rcx, r15; hObject
0x18001f28b  call    cs:__imp_CloseHandle
0x18001f291  mov     rcx, rbp; hObject
0x18001f294  call    cs:__imp_CloseHandle
0x18001f29a  mov     eax, ebx
0x18001f29c  jmp     loc_18001F3CC
0x18001f2a1  mov     rcx, rbx; lpBaseAddress
0x18001f2a4  call    cs:__imp_UnmapViewOfFile
0x18001f2aa  mov     ebx, 18h
0x18001f2af  jmp     short loc_18001F288
0x18001f2b1  xor     edi, edi
0x18001f2b3  sub     r8d, edi
0x18001f2b6  mov     edx, 1
0x18001f2bb  mov     ecx, r8d; dwBytes
0x18001f2be  mov     [r14], r8d
0x18001f2c1  call    T2malloc
0x18001f2c6  mov     [r12], rax
0x18001f2ca  test    rax, rax
0x18001f2cd  jnz     short loc_18001F2DF
0x18001f2cf  mov     rcx, rbx; lpBaseAddress
0x18001f2d2  call    cs:__imp_UnmapViewOfFile
0x18001f2d8  mov     ebx, 7
0x18001f2dd  jmp     short loc_18001F288
0x18001f2df  mov     r8d, [r14]; Size
0x18001f2e2  mov     rcx, rax; void *
0x18001f2e5  mov     edx, edi
0x18001f2e7  add     rdx, rbx; Src
0x18001f2ea  call    memcpy_0
0x18001f2ef  cmp     esi, 74746366h
0x18001f2f5  jnz     loc_18001F3A4
0x18001f2fb  cmp     dword ptr [r14], 6
0x18001f2ff  mov     rcx, [r12]; lpMem
0x18001f303  jb      loc_18001F3B4
0x18001f309  movzx   eax, byte ptr [rcx+5]
0x18001f30d  movzx   r11d, byte ptr [rcx+4]
0x18001f312  shl     r11d, 8
0x18001f316  or      r11d, eax
0x18001f319  mov     eax, r11d
0x18001f31c  shl     eax, 4
0x18001f31f  add     eax, 14h
0x18001f322  cmp     [r14], eax
0x18001f325  jb      loc_18001F3B4
0x18001f32b  xor     esi, esi
0x18001f32d  test    r11d, r11d
0x18001f330  jz      short loc_18001F3A4
0x18001f332  mov     r9, [r12]
0x18001f336  mov     eax, esi
0x18001f338  shl     eax, 4
0x18001f33b  inc     esi
0x18001f33d  add     eax, 14h
0x18001f340  mov     r10d, eax
0x18001f343  movzx   r8d, byte ptr [rax+r9+1]
0x18001f349  movzx   eax, byte ptr [rax+r9]
0x18001f34e  shl     eax, 8
0x18001f351  or      r8d, eax
0x18001f354  movzx   eax, byte ptr [r10+r9+2]
0x18001f35a  shl     r8d, 8
0x18001f35e  or      r8d, eax
0x18001f361  movzx   eax, byte ptr [r10+r9+3]
0x18001f367  shl     r8d, 8
0x18001f36b  or      r8d, eax
0x18001f36e  sub     r8d, edi
0x18001f371  mov     eax, r8d
0x18001f374  shr     eax, 8
0x18001f377  movzx   edx, al
0x18001f37a  movzx   eax, r8b
0x18001f37e  shl     eax, 8
0x18001f381  or      edx, eax
0x18001f383  mov     eax, r8d
0x18001f386  shl     edx, 8
0x18001f389  shr     eax, 10h
0x18001f38c  shr     r8d, 18h
0x18001f390  movzx   ecx, al
0x18001f393  or      edx, ecx
0x18001f395  shl     edx, 8
0x18001f398  or      edx, r8d
0x18001f39b  mov     [r10+r9], edx
0x18001f39f  cmp     esi, r11d
0x18001f3a2  jl      short loc_18001F332
0x18001f3a4  mov     rcx, rbx; lpBaseAddress
0x18001f3a7  call    cs:__imp_UnmapViewOfFile
0x18001f3ad  xor     ebx, ebx
0x18001f3af  jmp     loc_18001F288
0x18001f3b4  call    T2free
0x18001f3b9  jmp     loc_18001F27A
0x18001f3be  mov     rcx, rbp; hObject
0x18001f3c1  call    cs:__imp_CloseHandle
0x18001f3c7  mov     eax, 17h
0x18001f3cc  add     rsp, 40h
0x18001f3d0  pop     r15
0x18001f3d2  pop     r14
0x18001f3d4  pop     r12
0x18001f3d6  pop     rdi
0x18001f3d7  pop     rsi
0x18001f3d8  pop     rbp
0x18001f3d9  pop     rbx
0x18001f3da  retn
```
