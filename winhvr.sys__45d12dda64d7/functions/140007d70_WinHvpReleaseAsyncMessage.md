# WinHvpReleaseAsyncMessage

- ea: `0x140007d70`
- end: `0x140007d9b`
- name: `WinHvpReleaseAsyncMessage`
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

- `0x140007d70`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140007d89`
- `ntoskrnl!ExReleaseFastMutex` at `0x140007d89`

## pseudocode

```c
void __fastcall WinHvpReleaseAsyncMessage(__int64 a1)
{
  struct _FAST_MUTEX *v1; // rcx

  if ( a1 )
    v1 = (struct _FAST_MUTEX *)(a1 + 184);
  else
    v1 = &WinHvpGlobalAsyncMutex;
  ExReleaseFastMutex(v1);
}

```

## disassembly

```asm
0x140007d70  sub     rsp, 28h
0x140007d74  test    rcx, rcx
0x140007d77  jz      short loc_140007D82
0x140007d79  add     rcx, 0B8h
0x140007d80  jmp     short loc_140007D89
0x140007d82  lea     rcx, WinHvpGlobalAsyncMutex; FastMutex
0x140007d89  call    cs:__imp_ExReleaseFastMutex
0x140007d90  nop     dword ptr [rax+rax+00h]
0x140007d95  add     rsp, 28h
0x140007d99  retn
```
