# T2OSSvcCreateFontFile

- ea: `0x18001a1a4`
- end: `0x18001a2a9`
- name: `T2OSSvcCreateFontFile`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800190a4`

## callees

- `0x180019dc0`
- `0x18001a1a4`
- `0x18001c87c`
- `0x18001ca94`
- `0x180021ed4`
- `0x18002252c`

## pseudocode

```c
__int64 __fastcall T2OSSvcCreateFontFile(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // ebx
  __int64 v5; // rsi
  int v9; // r14d
  void *v11; // rbx
  int UniqueFileNames; // esi
  void *v13; // rcx
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF
  __int16 v15; // [rsp+70h] [rbp+18h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp+20h] BYREF

  v4 = *(_DWORD *)(a1 + 4);
  v5 = *(_QWORD *)(a1 + 200);
  lpMem = 0;
  v15 = 0;
  v14 = 0;
  v9 = a3;
  if ( (unsigned int)TTGetOffsetToTable(v5, v4, a3, &v14) && v14 && v5 && v4 > v14 && v4 - v14 >= 4 )
    *(_DWORD *)(v14 + v5) = 1212764996;
  if ( !v9 && a2 )
  {
    if ( !(unsigned int)AllocConvertToMultiByte(&lpMem, &v15, *(_QWORD *)(a1 + 88)) )
      return 0;
    v11 = lpMem;
    UniqueFileNames = MakeUniqueFileNames((__int64)lpMem, (const CHAR *)(a4 + 260), (const CHAR *)a4, a2, 0);
    if ( UniqueFileNames )
    {
      v13 = v11;
LABEL_13:
      T2free(v13);
      *(_DWORD *)(a4 + 944) = UniqueFileNames;
      return 0;
    }
    UniqueFileNames = CopyEmbeddedFontDataToFile(*(LPCVOID *)(a1 + 200), *(_DWORD *)(a1 + 4), (LPCSTR)(a4 + 260), 0);
    v13 = v11;
    if ( UniqueFileNames )
      goto LABEL_13;
    T2free(v11);
  }
  return 1;
}

```

## disassembly

```asm
0x18001a1a4  mov     [rsp+arg_8], rbx
0x18001a1a9  push    rbp
0x18001a1aa  push    rsi
0x18001a1ab  push    rdi
0x18001a1ac  push    r14
0x18001a1ae  push    r15
0x18001a1b0  sub     rsp, 30h
0x18001a1b4  mov     ebx, [rcx+4]
0x18001a1b7  xor     eax, eax
0x18001a1b9  mov     rsi, [rcx+0C8h]
0x18001a1c0  mov     rdi, r9
0x18001a1c3  mov     r15d, edx
0x18001a1c6  mov     [rsp+58h+lpMem], 0
0x18001a1cf  mov     rbp, rcx
0x18001a1d2  mov     [rsp+58h+arg_10], ax
0x18001a1d7  mov     rcx, rsi
0x18001a1da  mov     [rsp+58h+arg_0], eax
0x18001a1de  lea     r9, [rsp+58h+arg_0]
0x18001a1e3  mov     edx, ebx
0x18001a1e5  mov     r14d, r8d
0x18001a1e8  call    TTGetOffsetToTable
0x18001a1ed  test    eax, eax
0x18001a1ef  jz      short loc_18001A210
0x18001a1f1  mov     eax, [rsp+58h+arg_0]
0x18001a1f5  test    eax, eax
0x18001a1f7  jz      short loc_18001A210
0x18001a1f9  test    rsi, rsi
0x18001a1fc  jz      short loc_18001A210
0x18001a1fe  cmp     ebx, eax
0x18001a200  jbe     short loc_18001A210
0x18001a202  sub     ebx, eax
0x18001a204  cmp     ebx, 4
0x18001a207  jb      short loc_18001A210
0x18001a209  mov     dword ptr [rax+rsi], 48495344h
0x18001a210  test    r14d, r14d
0x18001a213  jnz     short loc_18001A293
0x18001a215  test    r15d, r15d
0x18001a218  jz      short loc_18001A293
0x18001a21a  mov     r8, [rbp+58h]
0x18001a21e  lea     rdx, [rsp+58h+arg_10]
0x18001a223  lea     rcx, [rsp+58h+lpMem]
0x18001a228  call    AllocConvertToMultiByte
0x18001a22d  test    eax, eax
0x18001a22f  jnz     short loc_18001A235
0x18001a231  xor     eax, eax
0x18001a233  jmp     short loc_18001A298
0x18001a235  mov     rbx, [rsp+58h+lpMem]
0x18001a23a  lea     r14, [rdi+104h]
0x18001a241  mov     rdx, r14
0x18001a244  mov     [rsp+58h+var_38], 0
0x18001a24c  mov     rcx, rbx
0x18001a24f  mov     r9d, r15d
0x18001a252  mov     r8, rdi
0x18001a255  call    MakeUniqueFileNames
0x18001a25a  mov     esi, eax
0x18001a25c  test    eax, eax
0x18001a25e  jz      short loc_18001A270
0x18001a260  mov     rcx, rbx; lpMem
0x18001a263  call    T2free
0x18001a268  mov     [rdi+3B0h], esi
0x18001a26e  jmp     short loc_18001A231
0x18001a270  mov     edx, [rbp+4]; nNumberOfBytesToWrite
0x18001a273  xor     r9d, r9d
0x18001a276  mov     rcx, [rbp+0C8h]; lpBuffer
0x18001a27d  mov     r8, r14; lpFileName
0x18001a280  call    CopyEmbeddedFontDataToFile
0x18001a285  mov     esi, eax
0x18001a287  mov     rcx, rbx; lpMem
0x18001a28a  test    eax, eax
0x18001a28c  jnz     short loc_18001A263
0x18001a28e  call    T2free
0x18001a293  mov     eax, 1
0x18001a298  mov     rbx, [rsp+58h+arg_8]
0x18001a29d  add     rsp, 30h
0x18001a2a1  pop     r15
0x18001a2a3  pop     r14
0x18001a2a5  pop     rdi
0x18001a2a6  pop     rsi
0x18001a2a7  pop     rbp
0x18001a2a8  retn
```
