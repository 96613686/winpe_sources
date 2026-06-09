# ItSpSubmitThreadpoolWork(_TP_WORK * *,_ITSRV_GLOBAL_CONTEXT *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *))

- ea: `0x180073bd0`
- end: `0x180073c39`
- name: `?ItSpSubmitThreadpoolWork@@YAKPEAPEAU_TP_WORK@@PEAU_ITSRV_GLOBAL_CONTEXT@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU1@@Z@Z`
- size: `105`
- prototype: `unsigned int(struct _TP_WORK **, struct _ITSRV_GLOBAL_CONTEXT *, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *))`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180039ad0`
- `0x180042610`
- `0x180072430`
- `0x180072810`
- `0x180072900`
- `0x180072ad0`

## callees

- `0x180073bd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073c12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073c12`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180073be7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180073be7`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180073c0c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180073c26`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180073c0c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180073c26`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180073bfe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180073bfe`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180073c1d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180073c1d`

## pseudocode

```c
DWORD __fastcall ItSpSubmitThreadpoolWork(
        struct _TP_WORK **a1,
        struct _ITSRV_GLOBAL_CONTEXT *a2,
        void (*a3)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *))
{
  char *v3; // rdi
  struct _TP_WORK *ThreadpoolWork; // rax

  v3 = (char *)a2 + 312;
  RtlAcquireSRWLockExclusive((char *)a2 + 312);
  ThreadpoolWork = CreateThreadpoolWork(ItSpPowerNotificationWorker, a2, (PTP_CALLBACK_ENVIRON)((char *)a2 + 232));
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
    RtlReleaseSRWLockExclusive(v3);
    return 0;
  }
  else
  {
    RtlReleaseSRWLockExclusive(v3);
    return GetLastError();
  }
}

```

## disassembly

```asm
0x180073bd0  mov     [rsp+arg_0], rbx
0x180073bd5  push    rdi
0x180073bd6  sub     rsp, 20h
0x180073bda  lea     rdi, [rdx+138h]
0x180073be1  mov     rbx, rdx
0x180073be4  mov     rcx, rdi
0x180073be7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180073bed  lea     r8, [rbx+0E8h]; pcbe
0x180073bf4  mov     rdx, rbx; pv
0x180073bf7  lea     rcx, ?ItSpPowerNotificationWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180073bfe  call    cs:__imp_CreateThreadpoolWork
0x180073c04  test    rax, rax
0x180073c07  jnz     short loc_180073C1A
0x180073c09  mov     rcx, rdi
0x180073c0c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180073c12  call    cs:__imp_GetLastError
0x180073c18  jmp     short loc_180073C2E
0x180073c1a  mov     rcx, rax; pwk
0x180073c1d  call    cs:__imp_SubmitThreadpoolWork
0x180073c23  mov     rcx, rdi
0x180073c26  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180073c2c  xor     eax, eax
0x180073c2e  mov     rbx, [rsp+28h+arg_0]
0x180073c33  add     rsp, 20h
0x180073c37  pop     rdi
0x180073c38  retn
```
