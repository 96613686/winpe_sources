# FindVirtualDiskShimForFile

- ea: `0x180003d30`
- end: `0x180004050`
- name: `FindVirtualDiskShimForFile`
- size: `800`
- prototype: `__int64 __fastcall(_WORD *Src, int, void **, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180003930`
- `0x1800073d0`

## callees

- `0x180003d30`
- `0x180004110`
- `0x18000aba0`
- `0x18000ba11`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003df6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003df6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003faf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ff4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003faf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ff4`
- `ntdll!RtlFreeHeap` at `0x180003ec3`
- `ntdll!RtlFreeHeap` at `0x18000401e`
- `ntdll!RtlFreeHeap` at `0x180003ec3`
- `ntdll!RtlFreeHeap` at `0x18000401e`
- `ntdll!RtlAllocateHeap` at `0x180003d97`
- `ntdll!RtlAllocateHeap` at `0x180003f27`
- `ntdll!RtlAllocateHeap` at `0x180003d97`
- `ntdll!RtlAllocateHeap` at `0x180003f27`

## pseudocode

```c
__int64 __fastcall FindVirtualDiskShimForFile(_WORD *Src, int a2, void **a3, __int64 a4, __int64 *a5)
{
  __int64 v9; // rbx
  _DWORD *Heap; // r14
  DWORD v11; // ebp
  __int64 FileW; // r12
  int v13; // eax
  void *v14; // r8
  int v15; // eax
  __int64 v16; // r13
  unsigned int v17; // ecx
  PVOID v18; // r15
  _WORD *v19; // rax
  char *Srca; // [rsp+40h] [rbp-48h]
  DWORD NumberOfBytesTransferred; // [rsp+90h] [rbp+8h] BYREF
  void **v23; // [rsp+A0h] [rbp+18h]

  v23 = a3;
  if ( Src )
  {
    v9 = -1;
    do
      ++v9;
    while ( Src[v9] );
  }
  else
  {
    v9 = 0;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v9 + 558);
  if ( Heap )
  {
    NumberOfBytesTransferred = 0;
    FileW = (__int64)CreateFileW(L"\\\\.\\VDRVROOT", 0x80000000, 3u, 0, 3u, 0x40000000u, 0);
    if ( FileW != -1 )
    {
      v13 = *(_DWORD *)(a4 + 16);
      *Heap = 2;
      Heap[8] = a2;
      *(_OWORD *)(Heap + 1) = *(_OWORD *)a4;
      Heap[5] = v13;
      if ( v9 )
      {
        Heap[7] = 2 * v9 + 2;
        Heap[6] = 36;
        memcpy_0(Heap + 9, Src, (unsigned int)(2 * v9 + 2));
      }
      else
      {
        *((_QWORD *)Heap + 3) = 0;
      }
      v11 = IssueSynchronousDeviceIoControl(
              (HANDLE)FileW,
              0x2D592Cu,
              Heap,
              2 * v9 + 558,
              Heap,
              2 * v9 + 558,
              &NumberOfBytesTransferred);
      if ( !v11 && NumberOfBytesTransferred >= 0x1C )
      {
        v14 = *a3;
        v15 = Heap[4];
        *(_OWORD *)a4 = *(_OWORD *)Heap;
        *(_DWORD *)(a4 + 16) = v15;
        if ( v14 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
          *a3 = 0;
        }
        v16 = 0;
        v17 = Heap[6] >> 1;
        Srca = (char *)Heap + (unsigned int)Heap[5];
        if ( v17 )
        {
          do
          {
            if ( !*(_WORD *)((char *)Heap + 2 * v16 + (unsigned int)Heap[5]) )
              break;
            v16 = (unsigned int)(v16 + 1);
          }
          while ( (unsigned int)v16 < v17 );
        }
        v18 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * (v9 + v16) + 4);
        *v23 = v18;
        if ( v18 )
        {
          memcpy_0(v18, Srca, 2LL * (unsigned int)v16);
          *((_WORD *)v18 + (unsigned int)v16) = 92;
          *((_WORD *)v18 + (unsigned int)(v16 + 1)) = 0;
          if ( v9 && StringCchCatW((STRSAFE_LPWSTR)v18, (unsigned __int64)(2 * (v9 + v16) + 4) >> 1, Src) )
          {
            v11 = -1069940716;
            CloseHandle((HANDLE)FileW);
            FileW = -1;
          }
          v19 = *v23;
          if ( *(_WORD *)*v23 == 92 && v19[1] == 92 && v19[2] == 46 && v19[3] == 92 )
            *(_DWORD *)(v19 + 1) = 4128831;
        }
        else
        {
          v11 = 14;
          CloseHandle((HANDLE)FileW);
          FileW = -1;
        }
        goto LABEL_30;
      }
      CloseHandle((HANDLE)FileW);
      FileW = -1;
    }
    v11 = -1069940716;
LABEL_30:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    *a5 = FileW;
    return v11;
  }
  v11 = 14;
  *a5 = -1;
  return v11;
}

```

## disassembly

```asm
0x180003d30  mov     [rsp+arg_8], rbx
0x180003d35  mov     [rsp+arg_10], r8
0x180003d3a  push    rbp
0x180003d3b  push    rsi
0x180003d3c  push    rdi
0x180003d3d  push    r12
0x180003d3f  push    r13
0x180003d41  push    r14
0x180003d43  push    r15
0x180003d45  sub     rsp, 50h
0x180003d49  xor     r12d, r12d
0x180003d4c  mov     r15, r9
0x180003d4f  mov     r13, r8
0x180003d52  mov     ebp, edx
0x180003d54  mov     rsi, rcx
0x180003d57  test    rcx, rcx
0x180003d5a  jnz     short loc_180003D61
0x180003d5c  mov     ebx, r12d
0x180003d5f  jmp     short loc_180003D7A
0x180003d61  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180003d68  nop     dword ptr [rax+rax+00000000h]
0x180003d70  inc     rbx
0x180003d73  cmp     [rcx+rbx*2], r12w
0x180003d78  jnz     short loc_180003D70
0x180003d7a  mov     rcx, gs:60h
0x180003d83  lea     rdi, ds:22Eh[rbx*2]
0x180003d8b  mov     r8, rdi; Size
0x180003d8e  mov     edx, 8; Flags
0x180003d93  mov     rcx, [rcx+30h]; HeapHandle
0x180003d97  call    cs:__imp_RtlAllocateHeap
0x180003d9e  nop     dword ptr [rax+rax+00h]
0x180003da3  mov     r14, rax
0x180003da6  test    rax, rax
0x180003da9  jnz     short loc_180003DC4
0x180003dab  mov     rax, [rsp+88h+arg_20]
0x180003db3  mov     ebp, 0Eh
0x180003db8  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x180003dbf  jmp     loc_180004035
0x180003dc4  mov     [rsp+88h+hTemplateFile], r12; hTemplateFile
0x180003dc9  lea     rcx, FileName; "\\\\.\\VDRVROOT"
0x180003dd0  mov     [rsp+88h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180003dd8  xor     r9d, r9d; lpSecurityAttributes
0x180003ddb  mov     edx, 80000000h; dwDesiredAccess
0x180003de0  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x180003de8  mov     r8d, 3; dwShareMode
0x180003dee  mov     [rsp+88h+NumberOfBytesTransferred], r12d
0x180003df6  call    cs:__imp_CreateFileW
0x180003dfd  nop     dword ptr [rax+rax+00h]
0x180003e02  mov     r12, rax
0x180003e05  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003e09  jz      loc_180004007
0x180003e0f  mov     eax, [r15+10h]
0x180003e13  mov     dword ptr [r14], 2
0x180003e1a  mov     [r14+20h], ebp
0x180003e1e  movups  xmm0, xmmword ptr [r15]
0x180003e22  movups  xmmword ptr [r14+4], xmm0
0x180003e27  mov     [r14+14h], eax
0x180003e2b  test    rbx, rbx
0x180003e2e  jz      short loc_180003E54
0x180003e30  lea     eax, ds:2[rbx*2]
0x180003e37  mov     rdx, rsi; Src
0x180003e3a  mov     [r14+1Ch], eax
0x180003e3e  lea     rcx, [r14+24h]; void *
0x180003e42  mov     r8d, eax; Size
0x180003e45  mov     dword ptr [r14+18h], 24h ; '$'
0x180003e4d  call    memcpy_0
0x180003e52  jmp     short loc_180003E5A
0x180003e54  xor     eax, eax
0x180003e56  mov     [r14+18h], rax
0x180003e5a  lea     rax, [rsp+88h+NumberOfBytesTransferred]
0x180003e62  mov     r9d, edi; nInBufferSize
0x180003e65  mov     [rsp+88h+hTemplateFile], rax; lpNumberOfBytesTransferred
0x180003e6a  mov     r8, r14; lpInBuffer
0x180003e6d  mov     [rsp+88h+dwFlagsAndAttributes], edi; DWORD
0x180003e71  mov     edx, 2D592Ch; dwIoControlCode
0x180003e76  mov     rcx, r12; hFile
0x180003e79  mov     qword ptr [rsp+88h+dwCreationDisposition], r14; LPVOID
0x180003e7e  call    IssueSynchronousDeviceIoControl
0x180003e83  mov     ebp, eax
0x180003e85  test    eax, eax
0x180003e87  jnz     loc_180003FF1
0x180003e8d  cmp     [rsp+88h+NumberOfBytesTransferred], 1Ch
0x180003e95  jb      loc_180003FF1
0x180003e9b  movups  xmm0, xmmword ptr [r14]
0x180003e9f  mov     r8, [r13+0]; P
0x180003ea3  mov     eax, [r14+10h]
0x180003ea7  movups  xmmword ptr [r15], xmm0
0x180003eab  mov     [r15+10h], eax
0x180003eaf  test    r8, r8
0x180003eb2  jz      short loc_180003ED7
0x180003eb4  mov     rcx, gs:60h
0x180003ebd  xor     edx, edx; Flags
0x180003ebf  mov     rcx, [rcx+30h]; HeapHandle
0x180003ec3  call    cs:__imp_RtlFreeHeap
0x180003eca  nop     dword ptr [rax+rax+00h]
0x180003ecf  mov     qword ptr [r13+0], 0
0x180003ed7  mov     edx, [r14+14h]
0x180003edb  xor     r13d, r13d
0x180003ede  mov     ecx, [r14+18h]
0x180003ee2  add     rdx, r14
0x180003ee5  shr     ecx, 1
0x180003ee7  mov     [rsp+88h+Src], rdx
0x180003eec  jz      short loc_180003EFE
0x180003eee  cmp     word ptr [rdx+r13*2], 0
0x180003ef4  jz      short loc_180003EFE
0x180003ef6  inc     r13d
0x180003ef9  cmp     r13d, ecx
0x180003efc  jb      short loc_180003EEE
0x180003efe  mov     rcx, gs:60h
0x180003f07  lea     rax, [rbx+r13]
0x180003f0b  lea     rax, ds:4[rax*2]
0x180003f13  mov     edi, r13d
0x180003f16  mov     r8, rax; Size
0x180003f19  mov     [rsp+88h+var_40], rax
0x180003f1e  mov     edx, 8; Flags
0x180003f23  mov     rcx, [rcx+30h]; HeapHandle
0x180003f27  call    cs:__imp_RtlAllocateHeap
0x180003f2e  nop     dword ptr [rax+rax+00h]
0x180003f33  mov     r15, rax
0x180003f36  mov     rax, [rsp+88h+arg_10]
0x180003f3e  mov     [rax], r15
0x180003f41  test    r15, r15
0x180003f44  jnz     short loc_180003F66
0x180003f46  mov     rcx, r12; hObject
0x180003f49  mov     ebp, 0Eh
0x180003f4e  call    cs:__imp_CloseHandle
0x180003f55  nop     dword ptr [rax+rax+00h]
0x180003f5a  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180003f61  jmp     loc_18000400C
0x180003f66  mov     rdx, [rsp+88h+Src]; Src
0x180003f6b  add     rdi, rdi
0x180003f6e  mov     r8, rdi; Size
0x180003f71  mov     rcx, r15; void *
0x180003f74  call    memcpy_0
0x180003f79  xor     eax, eax
0x180003f7b  mov     word ptr [rdi+r15], 5Ch ; '\'
0x180003f82  lea     ecx, [r13+1]
0x180003f86  mov     [r15+rcx*2], ax
0x180003f8b  test    rbx, rbx
0x180003f8e  jz      short loc_180003FC2
0x180003f90  mov     rdx, [rsp+88h+var_40]
0x180003f95  mov     r8, rsi; pszSrc
0x180003f98  shr     rdx, 1; cchDest
0x180003f9b  mov     rcx, r15; pszDest
0x180003f9e  call    StringCchCatW
0x180003fa3  test    eax, eax
0x180003fa5  jz      short loc_180003FC2
0x180003fa7  mov     rcx, r12; hObject
0x180003faa  mov     ebp, 0C03A0014h
0x180003faf  call    cs:__imp_CloseHandle
0x180003fb6  nop     dword ptr [rax+rax+00h]
0x180003fbb  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180003fc2  mov     rax, [rsp+88h+arg_10]
0x180003fca  mov     rax, [rax]
0x180003fcd  cmp     word ptr [rax], 5Ch ; '\'
0x180003fd1  jnz     short loc_18000400C
0x180003fd3  cmp     word ptr [rax+2], 5Ch ; '\'
0x180003fd8  jnz     short loc_18000400C
0x180003fda  cmp     word ptr [rax+4], 2Eh ; '.'
0x180003fdf  jnz     short loc_18000400C
0x180003fe1  cmp     word ptr [rax+6], 5Ch ; '\'
0x180003fe6  jnz     short loc_18000400C
0x180003fe8  mov     dword ptr [rax+2], 3F003Fh
0x180003fef  jmp     short loc_18000400C
0x180003ff1  mov     rcx, r12; hObject
0x180003ff4  call    cs:__imp_CloseHandle
0x180003ffb  nop     dword ptr [rax+rax+00h]
0x180004000  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180004007  mov     ebp, 0C03A0014h
0x18000400c  mov     rcx, gs:60h
0x180004015  mov     r8, r14; P
0x180004018  xor     edx, edx; Flags
0x18000401a  mov     rcx, [rcx+30h]; HeapHandle
0x18000401e  call    cs:__imp_RtlFreeHeap
0x180004025  nop     dword ptr [rax+rax+00h]
0x18000402a  mov     rax, [rsp+88h+arg_20]
0x180004032  mov     [rax], r12
0x180004035  mov     rbx, [rsp+88h+arg_8]
0x18000403d  mov     eax, ebp
0x18000403f  add     rsp, 50h
0x180004043  pop     r15
0x180004045  pop     r14
0x180004047  pop     r13
0x180004049  pop     r12
0x18000404b  pop     rdi
0x18000404c  pop     rsi
0x18000404d  pop     rbp
0x18000404e  retn
```
