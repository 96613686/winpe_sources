# wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>::~unique_ptr<uchar,wil::hlocal_secure_deleter>(void)

- ea: `0x18002a300`
- end: `0x18002a341`
- name: `??1?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@QEAA@XZ`
- size: `65`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003682f`

## callees

- `0x18002a300`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a335`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a335`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002a318`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002a318`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>::~unique_ptr<unsigned char,wil::hlocal_secure_deleter>(
        void **a1)
{
  void *v1; // rbx
  SIZE_T v2; // rax
  _BYTE *i; // rcx

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
  {
    v2 = LocalSize(v1);
    for ( i = v1; v2; --v2 )
      *i++ = 0;
    LocalFree(v1);
  }
}

```

## disassembly

```asm
0x18002a300  push    rbx
0x18002a302  sub     rsp, 20h
0x18002a306  mov     rbx, [rcx]
0x18002a309  mov     qword ptr [rcx], 0
0x18002a310  test    rbx, rbx
0x18002a313  jz      short loc_18002A33B
0x18002a315  mov     rcx, rbx; hMem
0x18002a318  call    cs:__imp_LocalSize
0x18002a31e  mov     rcx, rbx
0x18002a321  test    rax, rax
0x18002a324  jz      short loc_18002A332
0x18002a326  mov     byte ptr [rcx], 0
0x18002a329  inc     rcx
0x18002a32c  sub     rax, 1
0x18002a330  jnz     short loc_18002A326
0x18002a332  mov     rcx, rbx; hMem
0x18002a335  call    cs:__imp_LocalFree
0x18002a33b  add     rsp, 20h
0x18002a33f  pop     rbx
0x18002a340  retn
```
