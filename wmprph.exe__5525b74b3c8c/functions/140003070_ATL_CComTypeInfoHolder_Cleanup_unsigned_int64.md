# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x140003070`
- end: `0x1400030f4`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `132`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400013b4`
- `0x140002410`
- `0x140003070`
- `0x14000f010`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::Cleanup(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  _QWORD *v4; // r14
  __int64 v5; // rsi
  ATL::CComTypeInfoHolder::stringdispid *i; // rdi

  if ( a1 )
  {
    v2 = *(_QWORD *)(a1 + 24);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    v3 = *(_QWORD *)(a1 + 40);
    *(_QWORD *)(a1 + 24) = 0;
    if ( v3 )
    {
      v4 = (_QWORD *)(v3 - 8);
      v5 = *(_QWORD *)(v3 - 8);
      for ( i = (ATL::CComTypeInfoHolder::stringdispid *)(v3 + 16 * v5); v5; --v5 )
      {
        i = (ATL::CComTypeInfoHolder::stringdispid *)((char *)i - 16);
        ATL::CComTypeInfoHolder::stringdispid::~stringdispid(i);
      }
      operator delete[](v4, 16LL * *v4 + 8);
    }
    *(_QWORD *)(a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x140003070  test    rcx, rcx
0x140003073  jz      short locret_1400030F3
0x140003075  push    rbx
0x140003076  push    rsi
0x140003077  push    rdi
0x140003078  push    r14
0x14000307a  sub     rsp, 28h
0x14000307e  mov     rbx, rcx
0x140003081  mov     rcx, [rcx+18h]
0x140003085  test    rcx, rcx
0x140003088  jz      short loc_140003096
0x14000308a  mov     rax, [rcx]
0x14000308d  mov     rax, [rax+10h]
0x140003091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003096  mov     rax, [rbx+28h]
0x14000309a  mov     qword ptr [rbx+18h], 0
0x1400030a2  test    rax, rax
0x1400030a5  jz      short loc_1400030E2
0x1400030a7  lea     r14, [rax-8]
0x1400030ab  mov     rsi, [r14]
0x1400030ae  mov     rdi, rsi
0x1400030b1  shl     rdi, 4
0x1400030b5  add     rdi, rax
0x1400030b8  test    rsi, rsi
0x1400030bb  jz      short loc_1400030CF
0x1400030bd  sub     rdi, 10h
0x1400030c1  mov     rcx, rdi; this
0x1400030c4  call    ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)
0x1400030c9  sub     rsi, 1
0x1400030cd  jnz     short loc_1400030BD
0x1400030cf  mov     rdx, [r14]
0x1400030d2  mov     rcx, r14; void *
0x1400030d5  shl     rdx, 4
0x1400030d9  add     rdx, 8; unsigned __int64
0x1400030dd  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x1400030e2  mov     qword ptr [rbx+28h], 0
0x1400030ea  add     rsp, 28h
0x1400030ee  pop     r14
0x1400030f0  pop     rdi
0x1400030f1  pop     rsi
0x1400030f2  pop     rbx
0x1400030f3  retn
```
