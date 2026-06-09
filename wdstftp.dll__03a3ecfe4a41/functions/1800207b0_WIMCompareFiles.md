# WIMCompareFiles

- ea: `0x1800207b0`
- end: `0x180020a01`
- name: `WIMCompareFiles`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180024050`

## callees

- `0x180011cc4`
- `0x1800207b0`
- `0x180060e36`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180020911`
- `KERNEL32!GetLastError` at `0x180020964`
- `KERNEL32!GetLastError` at `0x180020911`
- `KERNEL32!GetLastError` at `0x180020964`
- `KERNEL32!ReadFile` at `0x180020901`
- `KERNEL32!ReadFile` at `0x180020954`
- `KERNEL32!ReadFile` at `0x180020901`
- `KERNEL32!ReadFile` at `0x180020954`
- `KERNEL32!GetFileSizeEx` at `0x1800207ed`
- `KERNEL32!GetFileSizeEx` at `0x180020808`
- `KERNEL32!GetFileSizeEx` at `0x1800207ed`
- `KERNEL32!GetFileSizeEx` at `0x180020808`
- `KERNEL32!GetOverlappedResult` at `0x180020989`
- `KERNEL32!GetOverlappedResult` at `0x1800209a6`
- `KERNEL32!GetOverlappedResult` at `0x180020989`
- `KERNEL32!GetOverlappedResult` at `0x1800209a6`

## pseudocode

```c
__int64 __fastcall WIMCompareFiles(__int64 a1, void *a2, void *a3)
{
  unsigned int v4; // esi
  char *v5; // rbx
  void *v7; // r13
  LONGLONG QuadPart; // rax
  DWORD v9; // edi
  DWORD v11; // [rsp+30h] [rbp-49h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+38h] [rbp-41h] BYREF
  LPVOID Buf2; // [rsp+40h] [rbp-39h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-31h] BYREF
  union _LARGE_INTEGER v15; // [rsp+50h] [rbp-29h] BYREF
  char *v16; // [rsp+58h] [rbp-21h]
  void *v17; // [rsp+60h] [rbp-19h]
  struct _OVERLAPPED lpOverlapped; // [rsp+68h] [rbp-11h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+88h] [rbp+Fh] BYREF
  DWORD NumberOfBytesRead; // [rsp+F8h] [rbp+7Fh] BYREF

  v4 = 0;
  FileSize.QuadPart = 0;
  v5 = 0;
  v15.QuadPart = 0;
  v16 = 0;
  if ( GetFileSizeEx(a2, &FileSize) )
  {
    if ( GetFileSizeEx(a3, &v15) )
    {
      if ( FileSize.QuadPart == v15.QuadPart )
      {
        v11 = 0;
        lpBuffer = 0;
        Buf2 = 0;
        memset_0(&lpOverlapped, 0, sizeof(lpOverlapped));
        if ( a1 )
        {
          v7 = *(void **)(a1 + 392);
          v17 = *(void **)(a1 + 384);
          if ( v17 )
          {
            if ( v7 )
            {
              v4 = 1;
              if ( (unsigned int)GetImageBuffers(
                                   a1,
                                   (unsigned int)&lpBuffer,
                                   (unsigned int)&v11,
                                   (unsigned int)&Buf2,
                                   (__int64)&NumberOfBytesRead) )
              {
                if ( lpBuffer && Buf2 )
                {
                  QuadPart = FileSize.QuadPart;
                  do
                  {
                    if ( !QuadPart )
                      break;
                    v9 = v11;
                    if ( v11 > QuadPart )
                      v9 = QuadPart;
                    NumberOfBytesRead = 0;
                    v4 = 0;
                    Overlapped.Internal = 0;
                    Overlapped.InternalHigh = 0;
                    Overlapped.hEvent = v17;
                    Overlapped.Pointer = v5;
                    if ( ReadFile(a2, lpBuffer, v9, &NumberOfBytesRead, &Overlapped) || GetLastError() == 997 )
                    {
                      lpOverlapped.Internal = 0;
                      lpOverlapped.InternalHigh = 0;
                      lpOverlapped.Pointer = (PVOID)__PAIR64__(HIDWORD(v16), (unsigned int)v5);
                      lpOverlapped.hEvent = v7;
                      if ( ReadFile(a3, Buf2, v9, &NumberOfBytesRead, &lpOverlapped) || GetLastError() == 997 )
                      {
                        GetOverlappedResult(a2, &Overlapped, &NumberOfBytesRead, 1);
                        GetOverlappedResult(a3, &lpOverlapped, &NumberOfBytesRead, 1);
                        if ( !memcmp_0(lpBuffer, Buf2, v9) )
                          v4 = 1;
                      }
                    }
                    v5 += v9;
                    QuadPart = FileSize.QuadPart - v9;
                    v16 = v5;
                    FileSize.QuadPart = QuadPart;
                  }
                  while ( v4 );
                }
              }
            }
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800207b0  mov     [rsp-8+arg_0], rbx
0x1800207b5  mov     [rsp-8+hFile], rdx
0x1800207ba  push    rbp
0x1800207bb  push    rsi
0x1800207bc  push    rdi
0x1800207bd  push    r12
0x1800207bf  push    r13
0x1800207c1  lea     rbp, [rsp-37h]
0x1800207c6  sub     rsp, 0B0h
0x1800207cd  mov     rax, rdx
0x1800207d0  mov     rdi, rcx
0x1800207d3  xor     esi, esi
0x1800207d5  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x1800207d9  and     qword ptr [rbp+57h+FileSize], rsi
0x1800207dd  xor     ebx, ebx
0x1800207df  and     qword ptr [rbp+57h+var_80], rsi
0x1800207e3  mov     rcx, rax; hFile
0x1800207e6  mov     r12, r8
0x1800207e9  mov     [rbp+57h+var_78], rbx
0x1800207ed  call    cs:__imp_GetFileSizeEx
0x1800207f4  nop     dword ptr [rax+rax+00h]
0x1800207f9  test    eax, eax
0x1800207fb  jz      loc_1800209E8
0x180020801  lea     rdx, [rbp+57h+var_80]; lpFileSize
0x180020805  mov     rcx, r12; hFile
0x180020808  call    cs:__imp_GetFileSizeEx
0x18002080f  nop     dword ptr [rax+rax+00h]
0x180020814  test    eax, eax
0x180020816  jz      loc_1800209E8
0x18002081c  mov     rax, qword ptr [rbp+57h+var_80]
0x180020820  cmp     qword ptr [rbp+57h+FileSize], rax
0x180020824  jnz     loc_1800209E8
0x18002082a  and     [rbp+57h+var_A0], ebx
0x18002082d  lea     r8d, [rsi+20h]; Size
0x180020831  and     [rbp+57h+lpBuffer], rbx
0x180020835  lea     rcx, [rbp+57h+var_68]; void *
0x180020839  and     [rbp+57h+Buf2], rbx
0x18002083d  xor     edx, edx; Val
0x18002083f  call    memset_0
0x180020844  test    rdi, rdi
0x180020847  jz      loc_1800209E8
0x18002084d  mov     rax, [rdi+180h]
0x180020854  mov     r13, [rdi+188h]
0x18002085b  mov     [rbp+57h+var_70], rax
0x18002085f  test    rax, rax
0x180020862  jz      loc_1800209E8
0x180020868  test    r13, r13
0x18002086b  jz      loc_1800209E8
0x180020871  lea     rax, [rbp+57h+NumberOfBytesRead]
0x180020875  mov     rcx, rdi
0x180020878  lea     r9, [rbp+57h+Buf2]
0x18002087c  mov     [rsp+0D0h+lpOverlapped], rax
0x180020881  lea     r8, [rbp+57h+var_A0]
0x180020885  lea     rdx, [rbp+57h+lpBuffer]
0x180020889  lea     esi, [rbx+1]
0x18002088c  call    GetImageBuffers
0x180020891  test    eax, eax
0x180020893  jz      loc_1800209E8
0x180020899  cmp     [rbp+57h+lpBuffer], rbx
0x18002089d  jz      loc_1800209E8
0x1800208a3  cmp     [rbp+57h+Buf2], rbx
0x1800208a7  jz      loc_1800209E8
0x1800208ad  mov     rax, qword ptr [rbp+57h+FileSize]
0x1800208b1  test    rax, rax
0x1800208b4  jz      loc_1800209E8
0x1800208ba  mov     ecx, [rbp+57h+var_A0]
0x1800208bd  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800208c1  mov     edi, [rbp+57h+var_A0]
0x1800208c4  cmp     rcx, rax
0x1800208c7  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x1800208cb  mov     rcx, [rbp+57h+hFile]; hFile
0x1800208cf  cmovg   edi, eax
0x1800208d2  and     [rbp+57h+NumberOfBytesRead], 0
0x1800208d6  xor     esi, esi
0x1800208d8  and     [rbp+57h+Overlapped.Internal], rsi
0x1800208dc  mov     rax, rbx
0x1800208df  and     [rbp+57h+Overlapped.InternalHigh], rsi
0x1800208e3  mov     r8d, edi; nNumberOfBytesToRead
0x1800208e6  shr     rax, 20h
0x1800208ea  mov     dword ptr [rbp+57h+Overlapped.10h+4], eax
0x1800208ed  mov     rax, [rbp+57h+var_70]
0x1800208f1  mov     [rbp+57h+Overlapped.hEvent], rax
0x1800208f5  lea     rax, [rbp+57h+Overlapped]
0x1800208f9  mov     [rsp+0D0h+lpOverlapped], rax; lpOverlapped
0x1800208fe  mov     dword ptr [rbp+57h+Overlapped.10h], ebx
0x180020901  call    cs:__imp_ReadFile
0x180020908  nop     dword ptr [rax+rax+00h]
0x18002090d  test    eax, eax
0x18002090f  jnz     short loc_180020928
0x180020911  call    cs:__imp_GetLastError
0x180020918  nop     dword ptr [rax+rax+00h]
0x18002091d  cmp     eax, 3E5h
0x180020922  jnz     loc_1800209CC
0x180020928  mov     eax, dword ptr [rbp+57h+var_78+4]
0x18002092b  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18002092f  mov     rdx, [rbp+57h+Buf2]; lpBuffer
0x180020933  mov     r8d, edi; nNumberOfBytesToRead
0x180020936  and     [rbp+57h+var_68.Internal], rsi
0x18002093a  mov     rcx, r12; hFile
0x18002093d  and     [rbp+57h+var_68.InternalHigh], rsi
0x180020941  mov     dword ptr [rbp+57h+var_68.10h+4], eax
0x180020944  lea     rax, [rbp+57h+var_68]
0x180020948  mov     [rsp+0D0h+lpOverlapped], rax; lpOverlapped
0x18002094d  mov     dword ptr [rbp+57h+var_68.10h], ebx
0x180020950  mov     [rbp+57h+var_68.hEvent], r13
0x180020954  call    cs:__imp_ReadFile
0x18002095b  nop     dword ptr [rax+rax+00h]
0x180020960  test    eax, eax
0x180020962  jnz     short loc_180020977
0x180020964  call    cs:__imp_GetLastError
0x18002096b  nop     dword ptr [rax+rax+00h]
0x180020970  cmp     eax, 3E5h
0x180020975  jnz     short loc_1800209CC
0x180020977  mov     rcx, [rbp+57h+hFile]; hFile
0x18002097b  lea     r8, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x18002097f  mov     r9d, 1; bWait
0x180020985  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x180020989  call    cs:__imp_GetOverlappedResult
0x180020990  nop     dword ptr [rax+rax+00h]
0x180020995  mov     r9d, 1; bWait
0x18002099b  lea     r8, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesTransferred
0x18002099f  lea     rdx, [rbp+57h+var_68]; lpOverlapped
0x1800209a3  mov     rcx, r12; hFile
0x1800209a6  call    cs:__imp_GetOverlappedResult
0x1800209ad  nop     dword ptr [rax+rax+00h]
0x1800209b2  mov     rdx, [rbp+57h+Buf2]; Buf2
0x1800209b6  mov     rcx, [rbp+57h+lpBuffer]; Buf1
0x1800209ba  mov     r8d, edi; Size
0x1800209bd  call    memcmp_0
0x1800209c2  test    eax, eax
0x1800209c4  mov     eax, 1
0x1800209c9  cmovz   esi, eax
0x1800209cc  mov     rax, qword ptr [rbp+57h+FileSize]
0x1800209d0  mov     ecx, edi
0x1800209d2  add     rbx, rcx
0x1800209d5  sub     rax, rcx
0x1800209d8  mov     [rbp+57h+var_78], rbx
0x1800209dc  mov     qword ptr [rbp+57h+FileSize], rax
0x1800209e0  test    esi, esi
0x1800209e2  jnz     loc_1800208B1
0x1800209e8  mov     rbx, [rsp+0D0h+arg_0]
0x1800209f0  mov     eax, esi
0x1800209f2  add     rsp, 0B0h
0x1800209f9  pop     r13
0x1800209fb  pop     r12
0x1800209fd  pop     rdi
0x1800209fe  pop     rsi
0x1800209ff  pop     rbp
0x180020a00  retn
```
