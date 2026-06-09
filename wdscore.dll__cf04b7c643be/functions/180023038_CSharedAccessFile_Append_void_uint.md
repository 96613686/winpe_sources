# CSharedAccessFile::Append(void *,uint)

- ea: `0x180023038`
- end: `0x180023095`
- name: `?Append@CSharedAccessFile@@QEAAHPEAXI@Z`
- size: `93`
- prototype: `int(CSharedAccessFile *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180024600`

## callees

- `0x180023038`
- `0x180023494`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180023078`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180023078`

## pseudocode

```c
int __fastcall CSharedAccessFile::Append(HANDLE *this, void *a2, DWORD a3)
{
  int result; // eax
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+20h] BYREF

  NumberOfBytesWritten = 0;
  result = CSharedAccessFile::SetFilePosition(this, (__int64)a2, a3);
  if ( result )
    return WriteFile(*this, a2, a3, &NumberOfBytesWritten, 0);
  return result;
}

```

## disassembly

```asm
0x180023038  mov     [rsp+arg_0], rbx
0x18002303d  mov     [rsp+arg_8], rsi
0x180023042  push    rdi
0x180023043  sub     rsp, 30h
0x180023047  mov     edi, r8d
0x18002304a  mov     [rsp+38h+NumberOfBytesWritten], 0
0x180023052  mov     rsi, rdx
0x180023055  mov     rbx, rcx
0x180023058  call    ?SetFilePosition@CSharedAccessFile@@QEAAH_JK@Z; CSharedAccessFile::SetFilePosition(__int64,ulong)
0x18002305d  test    eax, eax
0x18002305f  jz      short loc_180023084
0x180023061  mov     rcx, [rbx]; hFile
0x180023064  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180023069  mov     r8d, edi; nNumberOfBytesToWrite
0x18002306c  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180023075  mov     rdx, rsi; lpBuffer
0x180023078  call    cs:__imp_WriteFile
0x18002307f  nop     dword ptr [rax+rax+00h]
0x180023084  mov     rbx, [rsp+38h+arg_0]
0x180023089  mov     rsi, [rsp+38h+arg_8]
0x18002308e  add     rsp, 30h
0x180023092  pop     rdi
0x180023093  retn
```
