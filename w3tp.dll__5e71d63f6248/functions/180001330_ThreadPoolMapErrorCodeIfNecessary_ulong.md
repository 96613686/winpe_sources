# ThreadPoolMapErrorCodeIfNecessary(ulong)

- ea: `0x180001330`
- end: `0x18000134d`
- name: `?ThreadPoolMapErrorCodeIfNecessary@@YAKK@Z`
- size: `29`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001330`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180001345`
- `ntdll!RtlNtStatusToDosError` at `0x180001345`

## pseudocode

```c
ULONG __fastcall ThreadPoolMapErrorCodeIfNecessary(NTSTATUS a1)
{
  if ( g_pThreadPool )
    return a1;
  else
    return RtlNtStatusToDosError(a1);
}

```

## disassembly

```asm
0x180001330  sub     rsp, 28h
0x180001334  cmp     cs:?g_pThreadPool@@3PEAVTHREAD_POOL@@EA, 0; THREAD_POOL * g_pThreadPool
0x18000133c  jz      short loc_180001345
0x18000133e  mov     eax, ecx
0x180001340  add     rsp, 28h
0x180001344  retn
0x180001345  call    cs:__imp_RtlNtStatusToDosError
0x18000134b  jmp     short loc_180001340
```
