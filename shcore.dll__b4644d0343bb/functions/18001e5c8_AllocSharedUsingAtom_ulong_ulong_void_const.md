# _AllocSharedUsingAtom(ulong,ulong,void const *)

- ea: `0x18001e5c8`
- end: `0x18001e6ad`
- name: `?_AllocSharedUsingAtom@@YAPEAXKKPEBX@Z`
- size: `229`
- prototype: `void *__fastcall(size_t Size, unsigned int, const void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18001e530`

## callees

- `0x18001e5c8`
- `0x18001fe5c`
- `0x18009341c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e694`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e694`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e62d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e62d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e679`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e679`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001e600`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001e600`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001e670`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001e670`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001e61f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001e61f`

## pseudocode

```c
__int64 __fastcall _AllocSharedUsingAtom(size_t Size, unsigned int a2, const void *Src)
{
  size_t v3; // rdi
  __int64 v4; // rsi
  HANDLE FileMappingW; // rax
  void *v8; // rbp
  _DWORD *v9; // rbx
  DWORD CurrentProcessId; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned __int16 v14; // [rsp+70h] [rbp+8h] BYREF

  v3 = (unsigned int)Size;
  v4 = 0;
  if ( (int)Size + 16 < (unsigned int)Size )
  {
    SetLastError(8u);
  }
  else
  {
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, (int)Size + 16, 0);
    v8 = FileMappingW;
    if ( FileMappingW )
    {
      v9 = MapViewOfFile(FileMappingW, 6u, 0, 0, 0);
      if ( v9 )
      {
        CurrentProcessId = GetCurrentProcessId();
        *v9 = v3;
        v9[2] = CurrentProcessId;
        v9[1] = -1157686529;
        v9[3] = a2;
        if ( Src )
          memcpy_0(v9 + 4, Src, v3);
        v14 = 0;
        if ( (int)CreateTransferAtom(v8, a2, v11, v12, &v14) >= 0 )
          v4 = v14;
        UnmapViewOfFile(v9);
      }
      CloseHandle(v8);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001e5c8  push    rbx
0x18001e5ca  push    rbp
0x18001e5cb  push    rsi
0x18001e5cc  push    rdi
0x18001e5cd  push    r14
0x18001e5cf  push    r15
0x18001e5d1  sub     rsp, 38h
0x18001e5d5  mov     edi, ecx
0x18001e5d7  xor     esi, esi
0x18001e5d9  mov     r14, r8
0x18001e5dc  mov     r15d, edx
0x18001e5df  lea     eax, [rdi+10h]
0x18001e5e2  cmp     eax, ecx
0x18001e5e4  jb      loc_18001E68F
0x18001e5ea  mov     [rsp+68h+lpName], rsi; lpName
0x18001e5ef  lea     r8d, [rsi+4]; flProtect
0x18001e5f3  xor     r9d, r9d; dwMaximumSizeHigh
0x18001e5f6  mov     [rsp+68h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x18001e5fa  xor     edx, edx; lpFileMappingAttributes
0x18001e5fc  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001e600  call    cs:__imp_CreateFileMappingW
0x18001e606  mov     rbp, rax
0x18001e609  test    rax, rax
0x18001e60c  jz      short loc_18001E67F
0x18001e60e  xor     r9d, r9d; dwFileOffsetLow
0x18001e611  mov     qword ptr [rsp+68h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x18001e616  xor     r8d, r8d; dwFileOffsetHigh
0x18001e619  lea     edx, [rsi+6]; dwDesiredAccess
0x18001e61c  mov     rcx, rax; hFileMappingObject
0x18001e61f  call    cs:__imp_MapViewOfFile
0x18001e625  mov     rbx, rax
0x18001e628  test    rax, rax
0x18001e62b  jz      short loc_18001E676
0x18001e62d  call    cs:__imp_GetCurrentProcessId
0x18001e633  mov     [rbx], edi
0x18001e635  mov     [rbx+8], eax
0x18001e638  mov     dword ptr [rbx+4], 0BAFF1AFFh
0x18001e63f  mov     [rbx+0Ch], r15d
0x18001e643  test    r14, r14
0x18001e646  jnz     short loc_18001E69C
0x18001e648  xor     eax, eax
0x18001e64a  mov     edx, r15d; unsigned int
0x18001e64d  mov     [rsp+68h+arg_0], ax
0x18001e652  mov     rcx, rbp; hSourceHandle
0x18001e655  lea     rax, [rsp+68h+arg_0]
0x18001e65a  mov     qword ptr [rsp+68h+dwMaximumSizeLow], rax; unsigned __int16 *
0x18001e65f  call    ?CreateTransferAtom@@YAJPEAXKKKPEAG@Z; CreateTransferAtom(void *,ulong,ulong,ulong,ushort *)
0x18001e664  test    eax, eax
0x18001e666  js      short loc_18001E66D
0x18001e668  movzx   esi, [rsp+68h+arg_0]
0x18001e66d  mov     rcx, rbx; lpBaseAddress
0x18001e670  call    cs:__imp_UnmapViewOfFile
0x18001e676  mov     rcx, rbp; hObject
0x18001e679  call    cs:__imp_CloseHandle
0x18001e67f  mov     rax, rsi
0x18001e682  add     rsp, 38h
0x18001e686  pop     r15
0x18001e688  pop     r14
0x18001e68a  pop     rdi
0x18001e68b  pop     rsi
0x18001e68c  pop     rbp
0x18001e68d  pop     rbx
0x18001e68e  retn
0x18001e68f  mov     ecx, 8; dwErrCode
0x18001e694  call    cs:__imp_SetLastError
0x18001e69a  jmp     short loc_18001E67F
0x18001e69c  mov     r8, rdi; Size
0x18001e69f  lea     rcx, [rbx+10h]; void *
0x18001e6a3  mov     rdx, r14; Src
0x18001e6a6  call    memcpy_0
0x18001e6ab  jmp     short loc_18001E648
```
