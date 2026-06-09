# FileStream::DeleteExistingContent(void)

- ea: `0x1800119a8`
- end: `0x180011a0c`
- name: `?DeleteExistingContent@FileStream@@QEAAJXZ`
- size: `100`
- prototype: `__int64 __fastcall(FileStream *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014900`
- `0x180015500`

## callees

- `0x1800119a8`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119e9`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800119d9`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800119d9`

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
0x1800119a8  push    rbx
0x1800119aa  sub     rsp, 30h
0x1800119ae  mov     rax, [rcx]
0x1800119b1  xor     r9d, r9d
0x1800119b4  mov     [rsp+38h+arg_0], 0
0x1800119bd  xor     r8d, r8d
0x1800119c0  mov     rdx, [rsp+38h+arg_0]
0x1800119c5  mov     rbx, rcx
0x1800119c8  mov     rax, [rax+28h]
0x1800119cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119d1  test    eax, eax
0x1800119d3  jnz     short loc_180011A05
0x1800119d5  mov     rcx, [rbx+8]; hFile
0x1800119d9  call    cs:__imp_SetEndOfFile
0x1800119e0  nop     dword ptr [rax+rax+00h]
0x1800119e5  test    eax, eax
0x1800119e7  jnz     short loc_180011A03
0x1800119e9  call    cs:__imp_GetLastError
0x1800119f0  nop     dword ptr [rax+rax+00h]
0x1800119f5  test    eax, eax
0x1800119f7  jle     short loc_180011A05
0x1800119f9  movzx   eax, ax
0x1800119fc  or      eax, 80070000h
0x180011a01  jmp     short loc_180011A05
0x180011a03  xor     eax, eax
0x180011a05  add     rsp, 30h
0x180011a09  pop     rbx
0x180011a0a  retn
```
