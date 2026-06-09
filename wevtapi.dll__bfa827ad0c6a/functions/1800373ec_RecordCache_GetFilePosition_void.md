# RecordCache::GetFilePosition(void)

- ea: `0x1800373ec`
- end: `0x180037414`
- name: `?GetFilePosition@RecordCache@@QEAA_KXZ`
- size: `40`
- prototype: `unsigned __int64 __fastcall(RecordCache *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800384e8`
- `0x1800385dc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180037404`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180037404`

## pseudocode

```c
union _LARGE_INTEGER __fastcall RecordCache::GetFilePosition(RecordCache *this)
{
  void *v1; // rcx
  union _LARGE_INTEGER NewFilePointer; // [rsp+30h] [rbp+8h] BYREF

  v1 = (void *)*((_QWORD *)this + 7);
  NewFilePointer.QuadPart = 0;
  SetFilePointerEx(v1, 0, &NewFilePointer, 1u);
  return NewFilePointer;
}

```

## disassembly

```asm
0x1800373ec  sub     rsp, 28h
0x1800373f0  mov     rcx, [rcx+38h]; hFile
0x1800373f4  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x1800373f9  xor     edx, edx; liDistanceToMove
0x1800373fb  mov     qword ptr [rsp+28h+NewFilePointer], rdx
0x180037400  lea     r9d, [rdx+1]; dwMoveMethod
0x180037404  call    cs:__imp_SetFilePointerEx
0x18003740a  mov     rax, qword ptr [rsp+28h+NewFilePointer]
0x18003740f  add     rsp, 28h
0x180037413  retn
```
