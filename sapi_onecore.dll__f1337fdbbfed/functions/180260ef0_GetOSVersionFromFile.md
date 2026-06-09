# GetOSVersionFromFile

- ea: `0x180260ef0`
- end: `0x1802610dc`
- name: `GetOSVersionFromFile`
- size: `492`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1802610e4`
- `0x18026144c`

## callees

- `0x180019660`
- `0x180079e30`
- `0x180260ef0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802610aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802610aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180260fe0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180260fe0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180260ffd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180260ffd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180260f54`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180260f9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180260f54`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180260f9b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180260f89`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180260f89`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180261022`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180261022`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180260fcf`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180260fcf`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180261047`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180261047`

## string_xrefs

- `0x180260fab`: `\ntdll.dll`
- `0x180260f67`: `\kernel32.dll`

## pseudocode

```c
__int64 __fastcall GetOSVersionFromFile(_DWORD *a1, _DWORD *a2, unsigned int *a3, _DWORD *a4, unsigned int *a5)
{
  int v8; // ebx
  DWORD FileVersionInfoSizeW; // r14d
  HANDLE ProcessHeap; // rax
  void *v11; // rsi
  void *v12; // rax
  void *v13; // rdi
  unsigned __int16 *v14; // rcx
  _DWORD *v15; // rdx
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int puLen; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpBuffer; // [rsp+28h] [rbp-D8h] BYREF
  _DWORD *v21; // [rsp+30h] [rbp-D0h]
  unsigned int *v22; // [rsp+38h] [rbp-C8h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  v21 = a2;
  v22 = a5;
  lpBuffer = 0;
  puLen = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
    return (unsigned int)-2147418113;
  v8 = StringCchCatW(Buffer, 0x104u, L"\\kernel32.dll");
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( GetFileAttributesW(Buffer) == -1 )
  {
    if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
      return (unsigned int)-2147418113;
    v8 = StringCchCatW(Buffer, 0x104u, L"\\ntdll.dll");
    if ( v8 < 0 )
      return (unsigned int)v8;
  }
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(Buffer, 0);
  if ( !FileVersionInfoSizeW )
    return (unsigned int)-2147418113;
  ProcessHeap = GetProcessHeap();
  v11 = ProcessHeap;
  if ( !ProcessHeap )
    return (unsigned int)-2147418113;
  v12 = HeapAlloc(ProcessHeap, 8u, FileVersionInfoSizeW);
  v13 = v12;
  if ( v12 )
  {
    if ( GetFileVersionInfoW(Buffer, 0, FileVersionInfoSizeW, v12) && VerQueryValueW(v13, L"\\", &lpBuffer, &puLen) )
    {
      v14 = (unsigned __int16 *)lpBuffer;
      v15 = v21;
      *a1 = *((unsigned __int16 *)lpBuffer + 5);
      *v15 = v14[4];
      v16 = v14[7];
      *v22 = v16;
      if ( v16 >= 0x23F0 )
        v17 = 0;
      else
        v17 = v16 % 0xA;
      *a3 = v17;
      *a4 = 0;
    }
    else
    {
      v8 = -2147418113;
    }
    HeapFree(v11, 0, v13);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180260ef0  push    rbp
0x180260ef2  push    rbx
0x180260ef3  push    rsi
0x180260ef4  push    rdi
0x180260ef5  push    r12
0x180260ef7  push    r13
0x180260ef9  push    r14
0x180260efb  push    r15
0x180260efd  lea     rbp, [rsp-168h]
0x180260f05  sub     rsp, 268h
0x180260f0c  mov     rax, cs:__security_cookie
0x180260f13  xor     rax, rsp
0x180260f16  mov     [rbp+1A0h+var_50], rax
0x180260f1d  mov     rax, [rbp+1A0h+arg_20]
0x180260f24  mov     r13, rcx
0x180260f27  mov     [rsp+2A0h+var_270], rdx
0x180260f2c  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180260f31  mov     edi, 104h
0x180260f36  mov     [rsp+2A0h+var_268], rax
0x180260f3b  mov     edx, edi; uSize
0x180260f3d  mov     [rsp+2A0h+lpBuffer], 0
0x180260f46  mov     r12, r9
0x180260f49  mov     [rsp+2A0h+puLen], 0
0x180260f51  mov     r15, r8
0x180260f54  call    cs:__imp_GetSystemDirectoryW
0x180260f5a  dec     eax
0x180260f5c  lea     esi, [rdi-2]
0x180260f5f  cmp     eax, esi
0x180260f61  ja      loc_1802610B2
0x180260f67  lea     r8, aKernel32Dll; "\\kernel32.dll"
0x180260f6e  mov     edx, edi; unsigned __int64
0x180260f70  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x180260f75  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180260f7a  mov     ebx, eax
0x180260f7c  test    eax, eax
0x180260f7e  js      loc_1802610B7
0x180260f84  lea     rcx, [rsp+2A0h+Buffer]; lpFileName
0x180260f89  call    cs:__imp_GetFileAttributesW
0x180260f8f  cmp     eax, 0FFFFFFFFh
0x180260f92  jnz     short loc_180260FC8
0x180260f94  mov     edx, edi; uSize
0x180260f96  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x180260f9b  call    cs:__imp_GetSystemDirectoryW
0x180260fa1  dec     eax
0x180260fa3  cmp     eax, esi
0x180260fa5  ja      loc_1802610B2
0x180260fab  lea     r8, aNtdllDll_0; "\\ntdll.dll"
0x180260fb2  mov     edx, edi; unsigned __int64
0x180260fb4  lea     rcx, [rsp+2A0h+Buffer]; unsigned __int16 *
0x180260fb9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180260fbe  mov     ebx, eax
0x180260fc0  test    eax, eax
0x180260fc2  js      loc_1802610B7
0x180260fc8  xor     edx, edx; lpdwHandle
0x180260fca  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x180260fcf  call    cs:__imp_GetFileVersionInfoSizeW
0x180260fd5  mov     r14d, eax
0x180260fd8  test    eax, eax
0x180260fda  jz      loc_1802610B2
0x180260fe0  call    cs:__imp_GetProcessHeap
0x180260fe6  mov     rsi, rax
0x180260fe9  test    rax, rax
0x180260fec  jz      loc_1802610B2
0x180260ff2  mov     r8d, r14d; dwBytes
0x180260ff5  mov     edx, 8; dwFlags
0x180260ffa  mov     rcx, rax; hHeap
0x180260ffd  call    cs:__imp_HeapAlloc
0x180261003  mov     rdi, rax
0x180261006  test    rax, rax
0x180261009  jnz     short loc_180261015
0x18026100b  mov     ebx, 8007000Eh
0x180261010  jmp     loc_1802610B7
0x180261015  mov     r9, rdi; lpData
0x180261018  lea     rcx, [rsp+2A0h+Buffer]; lptstrFilename
0x18026101d  mov     r8d, r14d; dwLen
0x180261020  xor     edx, edx; dwHandle
0x180261022  call    cs:__imp_GetFileVersionInfoW
0x180261028  test    eax, eax
0x18026102a  jnz     short loc_180261033
0x18026102c  mov     ebx, 8000FFFFh
0x180261031  jmp     short loc_1802610A2
0x180261033  lea     r9, [rsp+2A0h+puLen]; puLen
0x180261038  mov     rcx, rdi; pBlock
0x18026103b  lea     r8, [rsp+2A0h+lpBuffer]; lplpBuffer
0x180261040  lea     rdx, SubBlock; "\\"
0x180261047  call    cs:__imp_VerQueryValueW
0x18026104d  test    eax, eax
0x18026104f  jz      short loc_18026102C
0x180261051  mov     rcx, [rsp+2A0h+lpBuffer]
0x180261056  mov     rdx, [rsp+2A0h+var_270]
0x18026105b  movzx   eax, word ptr [rcx+0Ah]
0x18026105f  mov     [r13+0], eax
0x180261063  movzx   eax, word ptr [rcx+8]
0x180261067  mov     [rdx], eax
0x180261069  movzx   r8d, word ptr [rcx+0Eh]
0x18026106e  mov     rax, [rsp+2A0h+var_268]
0x180261073  mov     [rax], r8d
0x180261076  cmp     r8d, 23F0h
0x18026107d  jnb     short loc_180261094
0x18026107f  mov     eax, 0CCCCCCCDh
0x180261084  mul     r8d
0x180261087  shr     edx, 3
0x18026108a  lea     eax, [rdx+rdx*4]
0x18026108d  add     eax, eax
0x18026108f  sub     r8d, eax
0x180261092  jmp     short loc_180261097
0x180261094  xor     r8d, r8d
0x180261097  mov     [r15], r8d
0x18026109a  mov     dword ptr [r12], 0
0x1802610a2  mov     r8, rdi; lpMem
0x1802610a5  xor     edx, edx; dwFlags
0x1802610a7  mov     rcx, rsi; hHeap
0x1802610aa  call    cs:__imp_HeapFree
0x1802610b0  jmp     short loc_1802610B7
0x1802610b2  mov     ebx, 8000FFFFh
0x1802610b7  mov     eax, ebx
0x1802610b9  mov     rcx, [rbp+1A0h+var_50]
0x1802610c0  xor     rcx, rsp; StackCookie
0x1802610c3  call    __security_check_cookie
0x1802610c8  add     rsp, 268h
0x1802610cf  pop     r15
0x1802610d1  pop     r14
0x1802610d3  pop     r13
0x1802610d5  pop     r12
0x1802610d7  pop     rdi
0x1802610d8  pop     rsi
0x1802610d9  pop     rbx
0x1802610da  pop     rbp
0x1802610db  retn
```
