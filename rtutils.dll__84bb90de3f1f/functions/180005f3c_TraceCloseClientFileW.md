# TraceCloseClientFileW

- ea: `0x180005f3c`
- end: `0x180005f6a`
- name: `TraceCloseClientFileW`
- size: `46`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180001100`
- `0x180001c20`
- `0x180001fa0`
- `0x180002ae0`
- `0x180002c80`
- `0x180006514`
- `0x180006fc4`
- `0x1800074e8`

## callees

- `0x180005f3c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f51`

## pseudocode

```c
__int64 __fastcall TraceCloseClientFileW(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)(a1 + 256);
  if ( v2 )
  {
    CloseHandle(v2);
    *(_QWORD *)(a1 + 256) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180005f3c  push    rbx
0x180005f3e  sub     rsp, 20h
0x180005f42  mov     rbx, rcx
0x180005f45  mov     rcx, [rcx+100h]; hObject
0x180005f4c  test    rcx, rcx
0x180005f4f  jz      short loc_180005F62
0x180005f51  call    cs:__imp_CloseHandle
0x180005f57  mov     qword ptr [rbx+100h], 0
0x180005f62  xor     eax, eax
0x180005f64  add     rsp, 20h
0x180005f68  pop     rbx
0x180005f69  retn
```
