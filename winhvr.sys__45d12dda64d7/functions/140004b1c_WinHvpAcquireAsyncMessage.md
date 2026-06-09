# WinHvpAcquireAsyncMessage

- ea: `0x140004b1c`
- end: `0x140004b47`
- name: `WinHvpAcquireAsyncMessage`
- size: `43`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140001ef0`
- `0x140004a00`
- `0x140008420`
- `0x140009750`
- `0x14001c8e0`
- `0x14001f990`
- `0x140024020`
- `0x140024110`

## callees

- `0x140004b1c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140004b35`
- `ntoskrnl!ExAcquireFastMutex` at `0x140004b35`

## pseudocode

```c
void __fastcall WinHvpAcquireAsyncMessage(__int64 a1)
{
  struct _FAST_MUTEX *v1; // rcx

  if ( a1 )
    v1 = (struct _FAST_MUTEX *)(a1 + 184);
  else
    v1 = &WinHvpGlobalAsyncMutex;
  ExAcquireFastMutex(v1);
}

```

## disassembly

```asm
0x140004b1c  sub     rsp, 28h
0x140004b20  test    rcx, rcx
0x140004b23  jz      short loc_140004B2E
0x140004b25  add     rcx, 0B8h
0x140004b2c  jmp     short loc_140004B35
0x140004b2e  lea     rcx, WinHvpGlobalAsyncMutex; FastMutex
0x140004b35  call    cs:__imp_ExAcquireFastMutex
0x140004b3c  nop     dword ptr [rax+rax+00h]
0x140004b41  add     rsp, 28h
0x140004b45  retn
```
