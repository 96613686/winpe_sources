# CContainer::KillThread(void *,uchar)

- ea: `0x140006340`
- end: `0x14000634e`
- name: `?KillThread@CContainer@@CAXPEAXE@Z`
- size: `14`
- prototype: `void __fastcall __noreturn(PVOID)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140006347`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140006347`

## pseudocode

```c
void __fastcall __noreturn CContainer::KillThread(PVOID a1)
{
  ExitProcess(0xFFFFFFFF);
}

```

## disassembly

```asm
0x140006340  sub     rsp, 28h
0x140006344  or      ecx, 0FFFFFFFFh; uExitCode
0x140006347  call    cs:__imp_ExitProcess
```
