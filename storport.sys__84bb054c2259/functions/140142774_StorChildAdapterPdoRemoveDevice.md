# StorChildAdapterPdoRemoveDevice

- ea: `0x140142774`
- end: `0x14014284d`
- name: `StorChildAdapterPdoRemoveDevice`
- size: `217`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2, PIRP Irp)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1401421e8`

## callees

- `0x14009d8dc`
- `0x140142774`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140142833`
- `ntoskrnl!IoDeleteDevice` at `0x140142833`
- `ntoskrnl!IofCompleteRequest` at `0x14014280b`
- `ntoskrnl!IofCompleteRequest` at `0x14014280b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140142790`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140142790`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14014281b`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14014281b`
- `ntoskrnl!KeBugCheckEx` at `0x1401427cd`
- `ntoskrnl!KeBugCheckEx` at `0x1401427cd`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401427a0`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1401427a0`

## pseudocode

```c
__int64 __fastcall StorChildAdapterPdoRemoveDevice(ULONG_PTR BugCheckParameter2, PIRP Irp)
{
  __int64 CommonAdapterMiniport; // rax
  ULONG_PTR v5; // rcx
  struct _DEVICE_OBJECT *v6; // rcx
  signed __int32 v8[8]; // [rsp+0h] [rbp-38h] BYREF

  _InterlockedExchange((volatile __int32 *)(BugCheckParameter2 + 60), 6);
  ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(BugCheckParameter2 + 64));
  ExWaitForRundownProtectionReleaseCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(BugCheckParameter2 + 64));
  CommonAdapterMiniport = StorGetCommonAdapterMiniport(*(_QWORD *)(BugCheckParameter2 + 72));
  if ( !CommonAdapterMiniport )
    KeBugCheckEx(0x176u, 5u, BugCheckParameter2, v5, 0);
  *(_DWORD *)(CommonAdapterMiniport + 248) &= 0xFFFFFE7F;
  _InterlockedOr(v8, 0);
  *(_QWORD *)(CommonAdapterMiniport + 384) = 0;
  *(_QWORD *)(CommonAdapterMiniport + 376) = 0;
  Irp->IoStatus.Status = 0;
  IofCompleteRequest(Irp, 0);
  ExFreeCacheAwareRundownProtection(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(BugCheckParameter2 + 64));
  v6 = *(struct _DEVICE_OBJECT **)(BugCheckParameter2 + 32);
  *(_QWORD *)(BugCheckParameter2 + 64) = 0;
  IoDeleteDevice(v6);
  return 0;
}

```

## disassembly

```asm
0x140142774  mov     [rsp+arg_0], rbx
0x140142779  push    rdi
0x14014277a  sub     rsp, 30h
0x14014277e  mov     eax, 6
0x140142783  mov     rbx, rcx
0x140142786  xchg    eax, [rcx+3Ch]
0x140142789  mov     rcx, [rcx+40h]; RunRefCacheAware
0x14014278d  mov     rdi, rdx
0x140142790  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140142797  nop     dword ptr [rax+rax+00h]
0x14014279c  mov     rcx, [rbx+40h]; RunRef
0x1401427a0  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1401427a7  nop     dword ptr [rax+rax+00h]
0x1401427ac  mov     rcx, [rbx+48h]
0x1401427b0  call    StorGetCommonAdapterMiniport
0x1401427b5  test    rax, rax
0x1401427b8  jnz     short loc_1401427DA
0x1401427ba  mov     r9, rcx; BugCheckParameter3
0x1401427bd  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x1401427c2  mov     ecx, 176h; BugCheckCode
0x1401427c7  lea     edx, [rax+5]; BugCheckParameter1
0x1401427ca  mov     r8, rbx; BugCheckParameter2
0x1401427cd  call    cs:__imp_KeBugCheckEx
0x1401427da  and     dword ptr [rax+0F8h], 0FFFFFE7Fh
0x1401427e4  lock or [rsp+38h+var_38], 0
0x1401427e9  mov     qword ptr [rax+180h], 0
0x1401427f4  xor     edx, edx; PriorityBoost
0x1401427f6  mov     qword ptr [rax+178h], 0
0x140142801  mov     rcx, rdi; Irp
0x140142804  mov     dword ptr [rdi+30h], 0
0x14014280b  call    cs:__imp_IofCompleteRequest
0x140142812  nop     dword ptr [rax+rax+00h]
0x140142817  mov     rcx, [rbx+40h]; RunRefCacheAware
0x14014281b  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140142822  nop     dword ptr [rax+rax+00h]
0x140142827  mov     rcx, [rbx+20h]; DeviceObject
0x14014282b  mov     qword ptr [rbx+40h], 0
0x140142833  call    cs:__imp_IoDeleteDevice
0x14014283a  nop     dword ptr [rax+rax+00h]
0x14014283f  mov     rbx, [rsp+38h+arg_0]
0x140142844  xor     eax, eax
0x140142846  add     rsp, 30h
0x14014284a  pop     rdi
0x14014284b  retn
```
