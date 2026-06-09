# ItSpSubmitThreadpoolWork(_TP_WORK * *,_ITSRV_GLOBAL_CONTEXT *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *))

- ea: `0x180077880`
- end: `0x18007790e`
- name: `?ItSpSubmitThreadpoolWork@@YAKPEAPEAU_TP_WORK@@PEAU_ITSRV_GLOBAL_CONTEXT@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU1@@Z@Z`
- size: `142`
- prototype: `unsigned int(struct _TP_WORK **, struct _ITSRV_GLOBAL_CONTEXT *, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *))`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002f770`
- `0x1800449f0`
- `0x180075de0`
- `0x180076250`
- `0x180076360`
- `0x180076570`

## callees

- `0x180077880`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800778d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800778d4`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180077897`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180077897`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800778c8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800778f4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800778c8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800778f4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800778b4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800778b4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800778e5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800778e5`

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
0x180077880  mov     [rsp+arg_0], rbx
0x180077885  push    rdi
0x180077886  sub     rsp, 20h
0x18007788a  lea     rdi, [rdx+138h]
0x180077891  mov     rbx, rdx
0x180077894  mov     rcx, rdi
0x180077897  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18007789e  nop     dword ptr [rax+rax+00h]
0x1800778a3  lea     r8, [rbx+0E8h]; pcbe
0x1800778aa  mov     rdx, rbx; pv
0x1800778ad  lea     rcx, ?ItSpPowerNotificationWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800778b4  call    cs:__imp_CreateThreadpoolWork
0x1800778bb  nop     dword ptr [rax+rax+00h]
0x1800778c0  test    rax, rax
0x1800778c3  jnz     short loc_1800778E2
0x1800778c5  mov     rcx, rdi
0x1800778c8  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800778cf  nop     dword ptr [rax+rax+00h]
0x1800778d4  call    cs:__imp_GetLastError
0x1800778db  nop     dword ptr [rax+rax+00h]
0x1800778e0  jmp     short loc_180077902
0x1800778e2  mov     rcx, rax; pwk
0x1800778e5  call    cs:__imp_SubmitThreadpoolWork
0x1800778ec  nop     dword ptr [rax+rax+00h]
0x1800778f1  mov     rcx, rdi
0x1800778f4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800778fb  nop     dword ptr [rax+rax+00h]
0x180077900  xor     eax, eax
0x180077902  mov     rbx, [rsp+28h+arg_0]
0x180077907  add     rsp, 20h
0x18007790b  pop     rdi
0x18007790c  retn
```
