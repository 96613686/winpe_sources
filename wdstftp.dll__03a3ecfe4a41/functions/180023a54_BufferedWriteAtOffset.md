# BufferedWriteAtOffset

- ea: `0x180023a54`
- end: `0x180023bac`
- name: `BufferedWriteAtOffset`
- size: `344`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800195a0`
- `0x1800199c0`

## callees

- `0x180023a54`
- `0x180060e42`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180023b44`
- `KERNEL32!WriteFile` at `0x180023b44`
- `KERNEL32!SetLastError` at `0x180023b8b`
- `KERNEL32!SetLastError` at `0x180023b8b`
- `KERNEL32!SetFilePointerEx` at `0x180023b01`
- `KERNEL32!SetFilePointerEx` at `0x180023b21`
- `KERNEL32!SetFilePointerEx` at `0x180023b62`
- `KERNEL32!SetFilePointerEx` at `0x180023b01`
- `KERNEL32!SetFilePointerEx` at `0x180023b21`
- `KERNEL32!SetFilePointerEx` at `0x180023b62`

## pseudocode

```c
__int64 __fastcall BufferedWriteAtOffset(__int64 a1, LARGE_INTEGER a2, char *a3, DWORD a4)
{
  DWORD v5; // edi
  LARGE_INTEGER v7; // rcx
  unsigned __int64 v8; // rdx
  __int64 v10; // rax
  LARGE_INTEGER v11; // r9
  DWORD LowPart; // r8d
  LARGE_INTEGER v13; // rax
  int v14; // ebp
  DWORD v15; // ebp
  HANDLE v16; // rcx
  DWORD v17; // ecx
  union _LARGE_INTEGER NewFilePointer; // [rsp+50h] [rbp+8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  v7 = *(LARGE_INTEGER *)(a1 + 16);
  v8 = a2.QuadPart + a4;
  v10 = *(unsigned int *)(a1 + 8);
  v11.QuadPart = v7.QuadPart - v10;
  if ( a2.QuadPart > (unsigned __int64)v7.QuadPart || v8 > v7.QuadPart )
  {
    v17 = 87;
  }
  else
  {
    LowPart = a2.LowPart;
    v13.QuadPart = v7.QuadPart - v10;
    v14 = v8;
    if ( v11.QuadPart <= (unsigned __int64)a2.QuadPart )
      v13 = a2;
    else
      LowPart = v11.LowPart;
    if ( v7.QuadPart >= v8 )
      v7.QuadPart = v8;
    else
      v14 = v7.LowPart;
    if ( v13.QuadPart < (unsigned __int64)v7.QuadPart )
    {
      v15 = v14 - LowPart;
      memcpy_0((void *)(v13.QuadPart - v11.QuadPart + a1 + 24), &a3[v13.QuadPart - a2.QuadPart], v15);
      v5 -= v15;
    }
    if ( !v5 )
      return 1;
    v16 = *(HANDLE *)a1;
    NewFilePointer.QuadPart = 0;
    NumberOfBytesWritten = 0;
    if ( !SetFilePointerEx(v16, g_liZero, &NewFilePointer, 1u)
      || !SetFilePointerEx(*(HANDLE *)a1, a2, 0, 0)
      || !WriteFile(*(HANDLE *)a1, a3, v5, &NumberOfBytesWritten, 0)
      || !SetFilePointerEx(*(HANDLE *)a1, NewFilePointer, 0, 0) )
    {
      return 0;
    }
    if ( NumberOfBytesWritten == v5 )
      return 1;
    v17 = 234;
  }
  SetLastError(v17);
  return 0;
}

```

## disassembly

```asm
0x180023a54  mov     [rsp+arg_8], rbx
0x180023a59  mov     [rsp+arg_10], rbp
0x180023a5e  push    rsi
0x180023a5f  push    rdi
0x180023a60  push    r14
0x180023a62  sub     rsp, 30h
0x180023a66  mov     rsi, rdx
0x180023a69  mov     edi, r9d
0x180023a6c  mov     edx, r9d
0x180023a6f  mov     rbx, rcx
0x180023a72  mov     rcx, [rcx+10h]
0x180023a76  add     rdx, rsi
0x180023a79  mov     r9, rcx
0x180023a7c  mov     r14, r8
0x180023a7f  mov     eax, [rbx+8]
0x180023a82  sub     r9, rax
0x180023a85  cmp     rsi, rcx
0x180023a88  ja      loc_180023B86
0x180023a8e  cmp     rdx, rcx
0x180023a91  ja      loc_180023B86
0x180023a97  cmp     r9, rsi
0x180023a9a  mov     r8, rsi
0x180023a9d  mov     rax, r9
0x180023aa0  mov     rbp, rdx
0x180023aa3  cmova   r8, r9
0x180023aa7  cmovbe  rax, rsi
0x180023aab  cmp     rcx, rdx
0x180023aae  cmovb   rbp, rcx
0x180023ab2  cmovnb  rcx, rdx
0x180023ab6  cmp     rax, rcx
0x180023ab9  jnb     short loc_180023ADB
0x180023abb  mov     rdx, rax
0x180023abe  lea     rcx, [rbx+18h]
0x180023ac2  sub     rdx, rsi
0x180023ac5  sub     ebp, r8d
0x180023ac8  sub     rax, r9
0x180023acb  mov     r8d, ebp; Size
0x180023ace  add     rdx, r14; Src
0x180023ad1  add     rcx, rax; void *
0x180023ad4  call    memcpy_0
0x180023ad9  sub     edi, ebp
0x180023adb  xor     ebp, ebp
0x180023add  test    edi, edi
0x180023adf  jz      loc_180023B7F
0x180023ae5  mov     rdx, qword ptr cs:g_liZero; liDistanceToMove
0x180023aec  lea     r9d, [rbp+1]; dwMoveMethod
0x180023af0  mov     rcx, [rbx]; hFile
0x180023af3  lea     r8, [rsp+48h+NewFilePointer]; lpNewFilePointer
0x180023af8  mov     qword ptr [rsp+48h+NewFilePointer], rbp
0x180023afd  mov     [rsp+48h+NumberOfBytesWritten], ebp
0x180023b01  call    cs:__imp_SetFilePointerEx
0x180023b08  nop     dword ptr [rax+rax+00h]
0x180023b0d  test    eax, eax
0x180023b0f  jz      loc_180023B97
0x180023b15  mov     rcx, [rbx]; hFile
0x180023b18  xor     r9d, r9d; dwMoveMethod
0x180023b1b  xor     r8d, r8d; lpNewFilePointer
0x180023b1e  mov     rdx, rsi; liDistanceToMove
0x180023b21  call    cs:__imp_SetFilePointerEx
0x180023b28  nop     dword ptr [rax+rax+00h]
0x180023b2d  test    eax, eax
0x180023b2f  jz      short loc_180023B97
0x180023b31  mov     rcx, [rbx]; hFile
0x180023b34  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180023b39  mov     r8d, edi; nNumberOfBytesToWrite
0x180023b3c  mov     [rsp+48h+lpOverlapped], rbp; lpOverlapped
0x180023b41  mov     rdx, r14; lpBuffer
0x180023b44  call    cs:__imp_WriteFile
0x180023b4b  nop     dword ptr [rax+rax+00h]
0x180023b50  test    eax, eax
0x180023b52  jz      short loc_180023B97
0x180023b54  mov     rdx, qword ptr [rsp+48h+NewFilePointer]; liDistanceToMove
0x180023b59  xor     r9d, r9d; dwMoveMethod
0x180023b5c  mov     rcx, [rbx]; hFile
0x180023b5f  xor     r8d, r8d; lpNewFilePointer
0x180023b62  call    cs:__imp_SetFilePointerEx
0x180023b69  nop     dword ptr [rax+rax+00h]
0x180023b6e  test    eax, eax
0x180023b70  jz      short loc_180023B97
0x180023b72  cmp     [rsp+48h+NumberOfBytesWritten], edi
0x180023b76  jz      short loc_180023B7F
0x180023b78  mov     ecx, 0EAh
0x180023b7d  jmp     short loc_180023B8B
0x180023b7f  mov     eax, 1
0x180023b84  jmp     short loc_180023B99
0x180023b86  mov     ecx, 57h ; 'W'; dwErrCode
0x180023b8b  call    cs:__imp_SetLastError
0x180023b92  nop     dword ptr [rax+rax+00h]
0x180023b97  xor     eax, eax
0x180023b99  mov     rbx, [rsp+48h+arg_8]
0x180023b9e  mov     rbp, [rsp+48h+arg_10]
0x180023ba3  add     rsp, 30h
0x180023ba7  pop     r14
0x180023ba9  pop     rdi
0x180023baa  pop     rsi
0x180023bab  retn
```
