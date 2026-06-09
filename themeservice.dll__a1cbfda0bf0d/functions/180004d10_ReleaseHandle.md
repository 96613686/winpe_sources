# ReleaseHandle

- ea: `0x180004d10`
- end: `0x180004d34`
- name: `ReleaseHandle`
- size: `36`
- prototype: `BOOL __fastcall(void **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020fc`
- `0x180002940`
- `0x180004178`
- `0x180006580`
- `0x18000697c`

## callees

- `0x180004d10`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d21`

## pseudocode

```c
BOOL __fastcall ReleaseHandle(void **a1)
{
  void *v2; // rcx
  BOOL result; // eax

  v2 = *a1;
  if ( v2 )
  {
    result = CloseHandle(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004d10  push    rbx
0x180004d12  sub     rsp, 20h
0x180004d16  mov     rbx, rcx
0x180004d19  mov     rcx, [rcx]; hObject
0x180004d1c  test    rcx, rcx
0x180004d1f  jz      short loc_180004D2E
0x180004d21  call    cs:__imp_CloseHandle
0x180004d27  mov     qword ptr [rbx], 0
0x180004d2e  add     rsp, 20h
0x180004d32  pop     rbx
0x180004d33  retn
```
