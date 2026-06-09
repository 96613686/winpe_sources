# mmStartTask(void *)

- ea: `0x18001d0c0`
- end: `0x18001d10d`
- name: `?mmStartTask@@YAKPEAX@Z`
- size: `77`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18001d0c0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d0da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d0da`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d0f5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d0f5`

## pseudocode

```c
__int64 __fastcall mmStartTask(void **Parameter)
{
  void *v1; // rsi
  void *v2; // rbx
  __int64 (__fastcall *v3)(void *); // rdi
  unsigned int v4; // ebx

  v1 = *Parameter;
  v2 = Parameter[1];
  v3 = (__int64 (__fastcall *)(void *))Parameter[2];
  LocalFree(Parameter);
  v4 = v3(v2);
  if ( v1 )
    SetEvent(v1);
  return v4;
}

```

## disassembly

```asm
0x18001d0c0  mov     [rsp+arg_0], rbx
0x18001d0c5  mov     [rsp+arg_8], rsi
0x18001d0ca  push    rdi
0x18001d0cb  sub     rsp, 20h
0x18001d0cf  mov     rsi, [rcx]
0x18001d0d2  mov     rbx, [rcx+8]
0x18001d0d6  mov     rdi, [rcx+10h]
0x18001d0da  call    cs:__imp_LocalFree
0x18001d0e0  mov     rcx, rbx
0x18001d0e3  mov     rax, rdi
0x18001d0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0eb  mov     ebx, eax
0x18001d0ed  test    rsi, rsi
0x18001d0f0  jz      short loc_18001D0FB
0x18001d0f2  mov     rcx, rsi; hEvent
0x18001d0f5  call    cs:__imp_SetEvent
0x18001d0fb  mov     rsi, [rsp+28h+arg_8]
0x18001d100  mov     eax, ebx
0x18001d102  mov     rbx, [rsp+28h+arg_0]
0x18001d107  add     rsp, 20h
0x18001d10b  pop     rdi
0x18001d10c  retn
```
