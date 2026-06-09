# _ResourceStringAllocCopyExCoAlloc

- ea: `0x180018bec`
- end: `0x180018c15`
- name: `_ResourceStringAllocCopyExCoAlloc`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018aec`

## callees

- `0x180018bec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018bf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018bf8`

## pseudocode

```c
__int64 __fastcall ResourceStringAllocCopyExCoAlloc(__int64 a1, SIZE_T a2, _QWORD *a3)
{
  LPVOID v4; // rax

  v4 = CoTaskMemAlloc(a2);
  if ( !v4 )
    return 2147942414LL;
  *a3 = v4;
  return 0;
}

```

## disassembly

```asm
0x180018bec  push    rbx
0x180018bee  sub     rsp, 20h
0x180018bf2  mov     rcx, rdx; cb
0x180018bf5  mov     rbx, r8
0x180018bf8  call    cs:__imp_CoTaskMemAlloc
0x180018bfe  test    rax, rax
0x180018c01  jz      short loc_180018C0A
0x180018c03  mov     [rbx], rax
0x180018c06  xor     eax, eax
0x180018c08  jmp     short loc_180018C0F
0x180018c0a  mov     eax, 8007000Eh
0x180018c0f  add     rsp, 20h
0x180018c13  pop     rbx
0x180018c14  retn
```
