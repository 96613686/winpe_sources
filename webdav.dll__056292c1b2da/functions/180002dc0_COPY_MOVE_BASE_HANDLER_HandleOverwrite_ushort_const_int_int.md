# COPY_MOVE_BASE_HANDLER::HandleOverwrite(ushort const *,int,int *)

- ea: `0x180002dc0`
- end: `0x180002e57`
- name: `?HandleOverwrite@COPY_MOVE_BASE_HANDLER@@QEAAJPEBGHPEAH@Z`
- size: `151`
- prototype: `__int64 __fastcall(struct IBaseFileSystem **this, const unsigned __int16 *, int, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180002fbc`
- `0x18000dfb4`

## callees

- `0x180002dc0`
- `0x18001af58`
- `0x18001b018`
- `0x180023010`

## string_xrefs

- `0x180002e31`: `Overwrite of Existing File Not Allowed Due To Overwrite: Header`

## pseudocode

```c
__int64 __fastcall COPY_MOVE_BASE_HANDLER::HandleOverwrite(
        struct IBaseFileSystem **this,
        const unsigned __int16 *a2,
        int a3,
        int *a4)
{
  int v5; // ebx
  __int64 v9; // rax

  v5 = 0;
  *a4 = 0;
  if ( (unsigned int)DoesFileOrDirExist(this[30], a2) )
  {
    if ( a3 )
    {
      v5 = DeleteFileOrDirectoryTree(this[30], a2);
      if ( v5 >= 0 )
        *a4 = 1;
    }
    else
    {
      v5 = -2147024713;
      v9 = (*(__int64 (__fastcall **)(struct IBaseFileSystem *))(*(_QWORD *)this[1] + 272LL))(this[1]);
      (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, char))(*(_QWORD *)v9 + 32LL))(
        v9,
        L"Overwrite of Existing File Not Allowed Due To Overwrite: Header",
        0,
        0,
        3);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002dc0  push    rbx
0x180002dc2  push    rbp
0x180002dc3  push    rsi
0x180002dc4  push    rdi
0x180002dc5  push    r14
0x180002dc7  sub     rsp, 30h
0x180002dcb  mov     rsi, rcx
0x180002dce  xor     ebx, ebx
0x180002dd0  mov     [r9], ebx
0x180002dd3  mov     rdi, r9
0x180002dd6  mov     rcx, [rcx+0F0h]; struct IBaseFileSystem *
0x180002ddd  mov     r14d, r8d
0x180002de0  mov     rbp, rdx
0x180002de3  call    ?DoesFileOrDirExist@@YAHPEAVIBaseFileSystem@@PEBG@Z; DoesFileOrDirExist(IBaseFileSystem *,ushort const *)
0x180002de8  test    eax, eax
0x180002dea  jz      short loc_180002E4A
0x180002dec  test    r14d, r14d
0x180002def  jz      short loc_180002E0E
0x180002df1  mov     rcx, [rsi+0F0h]; struct IBaseFileSystem *
0x180002df8  mov     rdx, rbp; unsigned __int16 *
0x180002dfb  call    ?DeleteFileOrDirectoryTree@@YAJPEAVIBaseFileSystem@@PEBG@Z; DeleteFileOrDirectoryTree(IBaseFileSystem *,ushort const *)
0x180002e00  mov     ebx, eax
0x180002e02  test    eax, eax
0x180002e04  js      short loc_180002E4A
0x180002e06  mov     dword ptr [rdi], 1
0x180002e0c  jmp     short loc_180002E4A
0x180002e0e  mov     rcx, [rsi+8]
0x180002e12  mov     ebx, 800700B7h
0x180002e17  mov     rax, [rcx]
0x180002e1a  mov     rax, [rax+110h]
0x180002e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e26  mov     r10, rax
0x180002e29  mov     [rsp+58h+var_38], 3
0x180002e2e  xor     r9d, r9d
0x180002e31  lea     rdx, aOverwriteOfExi; "Overwrite of Existing File Not Allowed "...
0x180002e38  xor     r8d, r8d
0x180002e3b  mov     rcx, [rax]
0x180002e3e  mov     rax, [rcx+20h]
0x180002e42  mov     rcx, r10
0x180002e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e4a  mov     eax, ebx
0x180002e4c  add     rsp, 30h
0x180002e50  pop     r14
0x180002e52  pop     rdi
0x180002e53  pop     rsi
0x180002e54  pop     rbp
0x180002e55  pop     rbx
0x180002e56  retn
```
