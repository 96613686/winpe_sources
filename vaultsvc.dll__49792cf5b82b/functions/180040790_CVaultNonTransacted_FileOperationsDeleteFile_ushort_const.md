# CVaultNonTransacted::FileOperationsDeleteFile(ushort const *)

- ea: `0x180040790`
- end: `0x1800407b3`
- name: `?FileOperationsDeleteFile@CVaultNonTransacted@@UEAAKPEBG@Z`
- size: `35`
- prototype: `unsigned int(CVaultNonTransacted *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180040790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800407a5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180040797`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180040797`

## pseudocode

```c
DWORD __fastcall CVaultNonTransacted::FileOperationsDeleteFile(CVaultNonTransacted *this, const unsigned __int16 *a2)
{
  if ( DeleteFileW(a2) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180040790  sub     rsp, 28h
0x180040794  mov     rcx, rdx; lpFileName
0x180040797  call    cs:__imp_DeleteFileW
0x18004079d  test    eax, eax
0x18004079f  jnz     short loc_1800407AC
0x1800407a1  add     rsp, 28h
0x1800407a5  jmp     cs:__imp_GetLastError
0x1800407ac  xor     eax, eax
0x1800407ae  add     rsp, 28h
0x1800407b2  retn
```
