# CDVRSource::SeekToLocked(_LARGE_INTEGER *,ulong,_LARGE_INTEGER *)

- ea: `0x1800074b8`
- end: `0x18000750e`
- name: `?SeekToLocked@CDVRSource@@IEAAJPEAT_LARGE_INTEGER@@K0@Z`
- size: `86`
- prototype: `int(CDVRSource *__hidden this, union _LARGE_INTEGER *, unsigned int, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800072f0`

## callees

- `0x1800074b8`
- `0x18002b010`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x1800074e9`
- `KERNEL32!SetFilePointerEx` at `0x1800074e9`
- `KERNEL32!GetLastError` at `0x1800074f7`
- `KERNEL32!GetLastError` at `0x1800074f7`

## pseudocode

```c
int __fastcall CDVRSource::SeekToLocked(CDVRSource *this, union _LARGE_INTEGER *a2, DWORD a3, union _LARGE_INTEGER *a4)
{
  __int64 v5; // rcx
  int result; // eax

  v5 = *((_QWORD *)this + 18);
  if ( v5 )
    return (*(__int64 (__fastcall **)(__int64, union _LARGE_INTEGER *))(*(_QWORD *)v5 + 48LL))(v5, a2);
  if ( SetFilePointerEx(*((HANDLE *)this + 10), *a2, a4, a3) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800074b8  sub     rsp, 38h
0x1800074bc  mov     rax, rcx
0x1800074bf  mov     r10, r9
0x1800074c2  mov     rcx, [rcx+90h]
0x1800074c9  test    rcx, rcx
0x1800074cc  jz      short loc_1800074DC
0x1800074ce  mov     rax, [rcx]
0x1800074d1  mov     rax, [rax+30h]
0x1800074d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074da  jmp     short loc_180007509
0x1800074dc  mov     rdx, [rdx]; liDistanceToMove
0x1800074df  mov     r9d, r8d; dwMoveMethod
0x1800074e2  mov     rcx, [rax+50h]; hFile
0x1800074e6  mov     r8, r10; lpNewFilePointer
0x1800074e9  call    cs:__imp_SetFilePointerEx
0x1800074ef  test    eax, eax
0x1800074f1  jz      short loc_1800074F7
0x1800074f3  xor     eax, eax
0x1800074f5  jmp     short loc_180007509
0x1800074f7  call    cs:__imp_GetLastError
0x1800074fd  test    eax, eax
0x1800074ff  jle     short loc_180007509
0x180007501  movzx   eax, ax
0x180007504  or      eax, 80070000h
0x180007509  add     rsp, 38h
0x18000750d  retn
```
