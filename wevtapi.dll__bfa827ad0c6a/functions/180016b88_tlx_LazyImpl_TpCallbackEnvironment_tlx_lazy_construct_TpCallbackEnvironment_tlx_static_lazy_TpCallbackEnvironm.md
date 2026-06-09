# tlx::_LazyImpl<TpCallbackEnvironment,tlx::lazy_construct<TpCallbackEnvironment>,tlx::static_lazy<TpCallbackEnvironment,0,tlx::lazy_construct<TpCallbackEnvironment>>>::_Initializer::_Construct(void)

- ea: `0x180016b88`
- end: `0x180016bdd`
- name: `?_Construct@_Initializer@?$_LazyImpl@UTpCallbackEnvironment@@V?$lazy_construct@UTpCallbackEnvironment@@@tlx@@V?$static_lazy@UTpCallbackEnvironment@@$0A@V?$lazy_construct@UTpCallbackEnvironment@@@tlx@@@3@@tlx@@QEAAPEAXXZ`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180015084`
- `0x180016be4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016bce`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016bce`

## pseudocode

```c
union _RTL_RUN_ONCE *__fastcall tlx::_LazyImpl<TpCallbackEnvironment,tlx::lazy_construct<TpCallbackEnvironment>,tlx::static_lazy<TpCallbackEnvironment,0,tlx::lazy_construct<TpCallbackEnvironment>>>::_Initializer::_Construct(
        union _RTL_RUN_ONCE **a1)
{
  union _RTL_RUN_ONCE *v1; // r9
  union _RTL_RUN_ONCE *v2; // rbx

  v1 = *a1;
  v2 = *a1 + 1;
  LODWORD(v2->Ptr) = 3;
  v2[1].Ptr = 0;
  v2[2].Ptr = 0;
  v2[3].Ptr = 0;
  v2[4].Ptr = 0;
  v2[5].Ptr = 0;
  v2[6].Ptr = 0;
  HIDWORD(v2[7].Ptr) = 1;
  LODWORD(v2[8].Ptr) = 72;
  LODWORD(v2[7].Ptr) = 1;
  *a1 = 0;
  InitOnceComplete(v1, 0, v2);
  return v2;
}

```

## disassembly

```asm
0x180016b88  push    rbx
0x180016b8a  sub     rsp, 20h
0x180016b8e  mov     r9, [rcx]
0x180016b91  xor     edx, edx; dwFlags
0x180016b93  lea     rbx, [r9+8]
0x180016b97  lea     eax, [rdx+1]
0x180016b9a  mov     dword ptr [rbx], 3
0x180016ba0  mov     [rbx+8], rdx
0x180016ba4  mov     r8, rbx; lpContext
0x180016ba7  mov     [rbx+10h], rdx
0x180016bab  mov     [rbx+18h], rdx
0x180016baf  mov     [rbx+20h], rdx
0x180016bb3  mov     [rbx+28h], rdx
0x180016bb7  mov     [rbx+30h], rdx
0x180016bbb  mov     [rbx+3Ch], eax
0x180016bbe  mov     dword ptr [rbx+40h], 48h ; 'H'
0x180016bc5  mov     [rbx+38h], eax
0x180016bc8  mov     [rcx], rdx
0x180016bcb  mov     rcx, r9; lpInitOnce
0x180016bce  call    cs:__imp_InitOnceComplete
0x180016bd4  mov     rax, rbx
0x180016bd7  add     rsp, 20h
0x180016bdb  pop     rbx
0x180016bdc  retn
```
