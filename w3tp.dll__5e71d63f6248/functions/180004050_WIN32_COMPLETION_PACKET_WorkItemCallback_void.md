# WIN32_COMPLETION_PACKET::WorkItemCallback(void *)

- ea: `0x180004050`
- end: `0x18000409a`
- name: `?WorkItemCallback@WIN32_COMPLETION_PACKET@@CAKPEAX@Z`
- size: `74`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005010`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180004073`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180004073`

## pseudocode

```c
__int64 __fastcall WIN32_COMPLETION_PACKET::WorkItemCallback(_QWORD *Parameter)
{
  void (__fastcall *v1)(_QWORD, _QWORD, __int64); // rsi
  __int64 v2; // rbx
  unsigned int v3; // edi

  v1 = (void (__fastcall *)(_QWORD, _QWORD, __int64))*Parameter;
  v2 = Parameter[1];
  v3 = *((_DWORD *)Parameter + 4);
  ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)WIN32_COMPLETION_PACKET::sm_Allocator, Parameter);
  v1(0, v3, v2);
  return 0;
}

```

## disassembly

```asm
0x180004050  mov     [rsp+arg_0], rbx
0x180004055  mov     [rsp+arg_8], rsi
0x18000405a  push    rdi
0x18000405b  sub     rsp, 20h
0x18000405f  mov     rsi, [rcx]
0x180004062  mov     rdx, rcx
0x180004065  mov     rbx, [rcx+8]
0x180004069  mov     edi, [rcx+10h]
0x18000406c  mov     rcx, cs:?sm_Allocator@WIN32_COMPLETION_PACKET@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * WIN32_COMPLETION_PACKET::sm_Allocator
0x180004073  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180004079  mov     r8, rbx
0x18000407c  mov     edx, edi
0x18000407e  xor     ecx, ecx
0x180004080  mov     rax, rsi
0x180004083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004088  mov     rbx, [rsp+28h+arg_0]
0x18000408d  xor     eax, eax
0x18000408f  mov     rsi, [rsp+28h+arg_8]
0x180004094  add     rsp, 20h
0x180004098  pop     rdi
0x180004099  retn
```
