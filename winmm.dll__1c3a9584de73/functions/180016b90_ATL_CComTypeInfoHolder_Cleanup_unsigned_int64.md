# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x180016b90`
- end: `0x180016c07`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `119`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000c9b4`
- `0x18000c9d0`
- `0x180016b90`
- `0x18001b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CComTypeInfoHolder::Cleanup(__int64 a1)
{
  __int64 v2; // rcx
  char *v3; // rcx
  char *v4; // rbx

  if ( a1 )
  {
    v2 = *(_QWORD *)(a1 + 24);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *(_QWORD *)(a1 + 24) = 0;
    v3 = *(char **)(a1 + 40);
    if ( v3 )
    {
      v4 = v3 - 8;
      `eh vector destructor iterator'(v3, 0x10u, *((_QWORD *)v3 - 1), (void (*)(void *))ATL::CComBSTR::~CComBSTR);
      operator delete[](v4, 16LL * *(_QWORD *)v4 + 8);
    }
    *(_QWORD *)(a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x180016b90  test    rcx, rcx
0x180016b93  jz      short locret_180016C06
0x180016b95  mov     [rsp+arg_0], rbx
0x180016b9a  push    rdi
0x180016b9b  sub     rsp, 20h
0x180016b9f  mov     rdi, rcx
0x180016ba2  mov     rcx, [rcx+18h]
0x180016ba6  test    rcx, rcx
0x180016ba9  jz      short loc_180016BB7
0x180016bab  mov     rax, [rcx]
0x180016bae  mov     rax, [rax+10h]
0x180016bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bb7  mov     qword ptr [rdi+18h], 0
0x180016bbf  mov     rcx, [rdi+28h]; void *
0x180016bc3  test    rcx, rcx
0x180016bc6  jz      short loc_180016BF4
0x180016bc8  lea     rbx, [rcx-8]
0x180016bcc  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180016bd3  mov     r8, [rbx]; unsigned __int64
0x180016bd6  mov     edx, 10h; unsigned __int64
0x180016bdb  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180016be0  mov     rdx, [rbx]
0x180016be3  shl     rdx, 4
0x180016be7  add     rdx, 8; unsigned __int64
0x180016beb  mov     rcx, rbx; void *
0x180016bee  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x180016bf3  nop
0x180016bf4  mov     qword ptr [rdi+28h], 0
0x180016bfc  mov     rbx, [rsp+28h+arg_0]
0x180016c01  add     rsp, 20h
0x180016c05  pop     rdi
0x180016c06  retn
```
