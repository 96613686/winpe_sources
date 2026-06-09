# CWMIndexEntryArchiver::ResetIteration(void)

- ea: `0x180010430`
- end: `0x180010471`
- name: `?ResetIteration@CWMIndexEntryArchiver@@UEAAJXZ`
- size: `65`
- prototype: `__int64 __fastcall(CWMIndexEntryArchiver *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180010430`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x18001044e`
- `KERNEL32!SetFilePointer` at `0x18001044e`

## pseudocode

```c
__int64 __fastcall CWMIndexEntryArchiver::ResetIteration(CWMIndexEntryArchiver *this)
{
  void *v2; // rcx
  __int64 result; // rax

  v2 = (void *)*((_QWORD *)this + 1233);
  if ( v2 != (void *)-1LL )
    SetFilePointer(v2, 0, 0, 0);
  *((_DWORD *)this + 2599) = 0;
  result = 0;
  *((_QWORD *)this + 1300) = 0;
  return result;
}

```

## disassembly

```asm
0x180010430  push    rbx
0x180010432  sub     rsp, 20h
0x180010436  mov     rbx, rcx
0x180010439  mov     rcx, [rcx+2688h]; hFile
0x180010440  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180010444  jz      short loc_180010454
0x180010446  xor     r9d, r9d; dwMoveMethod
0x180010449  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001044c  xor     edx, edx; lDistanceToMove
0x18001044e  call    cs:__imp_SetFilePointer
0x180010454  mov     dword ptr [rbx+289Ch], 0
0x18001045e  xor     eax, eax
0x180010460  mov     qword ptr [rbx+28A0h], 0
0x18001046b  add     rsp, 20h
0x18001046f  pop     rbx
0x180010470  retn
```
