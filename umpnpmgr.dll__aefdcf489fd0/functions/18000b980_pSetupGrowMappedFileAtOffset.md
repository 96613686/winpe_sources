# pSetupGrowMappedFileAtOffset

- ea: `0x18000b980`
- end: `0x18000b9f8`
- name: `pSetupGrowMappedFileAtOffset`
- size: `120`
- prototype: `__int64 __fastcall(HANDLE hFile, unsigned int, __int64, unsigned int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x18000c9d0`
- `0x180010a58`

## callees

- `0x18000b980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9ee`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000b9cf`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000b9cf`

## pseudocode

```c
__int64 __fastcall pSetupGrowMappedFileAtOffset(HANDLE hFile, unsigned int a2, __int64 a3, unsigned int a4, int a5)
{
  unsigned int v7; // eax
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 i; // rax
  char v11; // cl
  __int64 v12; // rdx

  if ( a4 > a2 )
    return 87;
  v7 = a2 - a4;
  v8 = a3 + a4;
  v9 = 0;
  for ( i = v7 - 1; (int)i >= 0; *(_BYTE *)(v12 + v8) = v11 )
  {
    v11 = *(_BYTE *)(i + v8);
    v12 = (unsigned int)(i + a5);
    i = (unsigned int)(i - 1);
  }
  if ( SetFilePointer(hFile, a2 + a5, 0, 0) == -1 )
    return GetLastError();
  return v9;
}

```

## disassembly

```asm
0x18000b980  push    rdi
0x18000b982  sub     rsp, 20h
0x18000b986  mov     r10d, r9d
0x18000b989  mov     r11d, edx
0x18000b98c  mov     rdi, rcx
0x18000b98f  cmp     r9d, edx
0x18000b992  ja      short loc_18000B9E7
0x18000b994  mov     eax, edx
0x18000b996  mov     [rsp+28h+arg_0], rbx
0x18000b99b  sub     eax, r10d
0x18000b99e  lea     r9, [r8+r10]
0x18000b9a2  mov     r10d, [rsp+28h+arg_20]
0x18000b9a7  xor     ebx, ebx
0x18000b9a9  sub     eax, 1
0x18000b9ac  js      short loc_18000B9C2
0x18000b9ae  xchg    ax, ax
0x18000b9b0  movzx   ecx, byte ptr [rax+r9]
0x18000b9b5  lea     edx, [rax+r10]
0x18000b9b9  sub     eax, 1
0x18000b9bc  mov     [rdx+r9], cl
0x18000b9c0  jns     short loc_18000B9B0
0x18000b9c2  lea     edx, [r11+r10]; lDistanceToMove
0x18000b9c6  xor     r9d, r9d; dwMoveMethod
0x18000b9c9  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000b9cc  mov     rcx, rdi; hFile
0x18000b9cf  call    cs:__imp_SetFilePointer
0x18000b9d5  cmp     eax, 0FFFFFFFFh
0x18000b9d8  jz      short loc_18000B9EE
0x18000b9da  mov     eax, ebx
0x18000b9dc  mov     rbx, [rsp+28h+arg_0]
0x18000b9e1  add     rsp, 20h
0x18000b9e5  pop     rdi
0x18000b9e6  retn
0x18000b9e7  mov     eax, 57h ; 'W'
0x18000b9ec  jmp     short loc_18000B9E1
0x18000b9ee  call    cs:__imp_GetLastError
0x18000b9f4  mov     ebx, eax
0x18000b9f6  jmp     short loc_18000B9DA
```
