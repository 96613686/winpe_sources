# CSslLookaside::Allocate(void)

- ea: `0x18003c8e0`
- end: `0x18003c95b`
- name: `?Allocate@CSslLookaside@@UEAAPEAXXZ`
- size: `123`
- prototype: `void *__fastcall(CSslLookaside *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180077e80`

## callees

- `0x180021eb0`
- `0x18003c8e0`
- `0x18005a160`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003c91f`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18003c92f`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18003c92f`

## pseudocode

```c
struct _SLIST_ENTRY *__fastcall CSslLookaside::Allocate(CSslLookaside *this)
{
  SIZE_T v2; // rcx
  struct _SLIST_ENTRY *result; // rax
  PSLIST_ENTRY v4; // rax
  unsigned int v5; // ecx
  PSLIST_ENTRY v6; // rdi

  if ( *((_BYTE *)this + 32) )
  {
    v4 = InterlockedPopEntrySList((PSLIST_HEADER)this + 1);
    v5 = *((_DWORD *)this + 9);
    v6 = v4;
    if ( v4 )
    {
      memset_0(&v4[1], 0, v5);
      _InterlockedDecrement((volatile signed __int32 *)this + 13);
    }
    else
    {
      result = (struct _SLIST_ENTRY *)SPExternalAlloc(v5 + 16);
      v6 = result;
      if ( !result )
        return result;
      _InterlockedIncrement((volatile signed __int32 *)this + 17);
    }
    _InterlockedIncrement((volatile signed __int32 *)this + 15);
    return v6 + 1;
  }
  else
  {
    v2 = *((unsigned int *)this + 9);
    if ( LsaTable )
      return (struct _SLIST_ENTRY *)(*(__int64 (__fastcall **)(SIZE_T))(LsaTable + 40))(v2);
    else
      return (struct _SLIST_ENTRY *)LocalAlloc(0x40u, v2);
  }
}

```

## disassembly

```asm
0x18003c8e0  push    rbx
0x18003c8e2  sub     rsp, 20h
0x18003c8e6  cmp     byte ptr [rcx+20h], 0
0x18003c8ea  mov     rbx, rcx
0x18003c8ed  jnz     short loc_18003C926
0x18003c8ef  mov     rax, cs:LsaTable
0x18003c8f6  mov     ecx, [rcx+24h]
0x18003c8f9  test    rax, rax
0x18003c8fc  jz      short loc_18003C912
0x18003c8fe  mov     rax, [rax+28h]
0x18003c902  add     rsp, 20h
0x18003c906  pop     rbx
0x18003c907  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18003c90c  add     rsp, 20h
0x18003c910  pop     rbx
0x18003c911  retn
0x18003c912  mov     rdx, rcx
0x18003c915  mov     ecx, 40h ; '@'
0x18003c91a  add     rsp, 20h
0x18003c91e  pop     rbx
0x18003c91f  jmp     cs:__imp_LocalAlloc
0x18003c926  add     rcx, 10h; ListHead
0x18003c92a  mov     [rsp+28h+arg_0], rdi
0x18003c92f  call    cs:__imp_InterlockedPopEntrySList
0x18003c935  mov     ecx, [rbx+24h]
0x18003c938  mov     rdi, rax
0x18003c93b  test    rax, rax
0x18003c93e  jz      loc_18008EF2C
0x18003c944  mov     r8d, ecx; Size
0x18003c947  xor     edx, edx; Val
0x18003c949  lea     rcx, [rax+10h]; void *
0x18003c94d  call    memset_0
0x18003c952  lock dec dword ptr [rbx+34h]
0x18003c956  jmp     loc_18008EF40
0x18008ef2c  add     ecx, 10h; uBytes
0x18008ef2f  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18008ef34  mov     rdi, rax
0x18008ef37  test    rax, rax
0x18008ef3a  jz      short loc_18008EF48
0x18008ef3c  lock inc dword ptr [rbx+44h]
0x18008ef40  lock inc dword ptr [rbx+3Ch]
0x18008ef44  lea     rax, [rdi+10h]
0x18008ef48  mov     rdi, [rsp+28h+arg_0]
0x18008ef4d  jmp     loc_18003C90C
```
