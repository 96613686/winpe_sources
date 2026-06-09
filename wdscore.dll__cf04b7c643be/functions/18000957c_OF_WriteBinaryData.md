# OF_WriteBinaryData

- ea: `0x18000957c`
- end: `0x18000961a`
- name: `OF_WriteBinaryData`
- size: `158`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004bc4`
- `0x180007a1c`
- `0x180007c60`
- `0x180007f40`
- `0x1800080e0`
- `0x180008380`
- `0x180008bc8`
- `0x180009620`
- `0x180009b98`
- `0x18000b1f0`

## callees

- `0x18000957c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800095b2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800095ed`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800095b2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800095ed`

## pseudocode

```c
_BOOL8 __fastcall OF_WriteBinaryData(HANDLE *a1, const void *a2, DWORD a3)
{
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+50h] [rbp+18h] BYREF

  nNumberOfBytesToWrite = a3;
  NumberOfBytesWritten = 0;
  if ( !WriteFile(*a1, &nNumberOfBytesToWrite, 4u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 4 )
    return 0;
  if ( !nNumberOfBytesToWrite )
    return 1;
  return WriteFile(*a1, a2, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0)
      && NumberOfBytesWritten == nNumberOfBytesToWrite;
}

```

## disassembly

```asm
0x18000957c  mov     rax, rsp
0x18000957f  mov     [rax+10h], rbx
0x180009583  mov     [rax+18h], r8d
0x180009587  push    rdi
0x180009588  sub     rsp, 30h
0x18000958c  mov     rdi, rdx
0x18000958f  mov     dword ptr [rax+8], 0
0x180009596  mov     rbx, rcx
0x180009599  mov     qword ptr [rax-18h], 0
0x1800095a1  mov     rcx, [rcx]; hFile
0x1800095a4  lea     rdx, [rax+18h]; lpBuffer
0x1800095a8  lea     r9, [rax+8]; lpNumberOfBytesWritten
0x1800095ac  mov     r8d, 4; nNumberOfBytesToWrite
0x1800095b2  call    cs:__imp_WriteFile
0x1800095b9  nop     dword ptr [rax+rax+00h]
0x1800095be  test    eax, eax
0x1800095c0  jz      short loc_18000960C
0x1800095c2  cmp     [rsp+38h+NumberOfBytesWritten], 4
0x1800095c7  jnz     short loc_18000960C
0x1800095c9  mov     r8d, [rsp+38h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1800095ce  test    r8d, r8d
0x1800095d1  jnz     short loc_1800095D9
0x1800095d3  lea     eax, [r8+1]
0x1800095d7  jmp     short loc_18000960E
0x1800095d9  mov     rcx, [rbx]; hFile
0x1800095dc  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800095e1  mov     rdx, rdi; lpBuffer
0x1800095e4  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x1800095ed  call    cs:__imp_WriteFile
0x1800095f4  nop     dword ptr [rax+rax+00h]
0x1800095f9  test    eax, eax
0x1800095fb  jz      short loc_18000960C
0x1800095fd  mov     ecx, [rsp+38h+nNumberOfBytesToWrite]
0x180009601  xor     eax, eax
0x180009603  cmp     [rsp+38h+NumberOfBytesWritten], ecx
0x180009607  setz    al
0x18000960a  jmp     short loc_18000960E
0x18000960c  xor     eax, eax
0x18000960e  mov     rbx, [rsp+38h+arg_8]
0x180009613  add     rsp, 30h
0x180009617  pop     rdi
0x180009618  retn
```
