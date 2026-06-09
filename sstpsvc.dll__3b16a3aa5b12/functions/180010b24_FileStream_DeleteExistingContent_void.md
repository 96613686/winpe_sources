# FileStream::DeleteExistingContent(void)

- ea: `0x180010b24`
- end: `0x180010b7b`
- name: `?DeleteExistingContent@FileStream@@QEAAJXZ`
- size: `87`
- prototype: `__int64 __fastcall(FileStream *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800138c0`
- `0x180014490`

## callees

- `0x180010b24`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b5f`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180010b55`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180010b55`

## pseudocode

```c
signed int __fastcall FileStream::DeleteExistingContent(HANDLE *this)
{
  signed int result; // eax

  result = (*((__int64 (__fastcall **)(HANDLE *, _QWORD, _QWORD, _QWORD))*this + 5))(this, 0, 0, 0);
  if ( !result )
  {
    if ( SetEndOfFile(this[1]) )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010b24  push    rbx
0x180010b26  sub     rsp, 30h
0x180010b2a  mov     rax, [rcx]
0x180010b2d  xor     r9d, r9d
0x180010b30  mov     [rsp+38h+arg_0], 0
0x180010b39  xor     r8d, r8d
0x180010b3c  mov     rdx, [rsp+38h+arg_0]
0x180010b41  mov     rbx, rcx
0x180010b44  mov     rax, [rax+28h]
0x180010b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b4d  test    eax, eax
0x180010b4f  jnz     short loc_180010B75
0x180010b51  mov     rcx, [rbx+8]; hFile
0x180010b55  call    cs:__imp_SetEndOfFile
0x180010b5b  test    eax, eax
0x180010b5d  jnz     short loc_180010B73
0x180010b5f  call    cs:__imp_GetLastError
0x180010b65  test    eax, eax
0x180010b67  jle     short loc_180010B75
0x180010b69  movzx   eax, ax
0x180010b6c  or      eax, 80070000h
0x180010b71  jmp     short loc_180010B75
0x180010b73  xor     eax, eax
0x180010b75  add     rsp, 30h
0x180010b79  pop     rbx
0x180010b7a  retn
```
