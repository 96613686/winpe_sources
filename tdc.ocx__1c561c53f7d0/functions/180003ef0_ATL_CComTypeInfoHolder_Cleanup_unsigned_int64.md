# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x180003ef0`
- end: `0x180003f69`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `121`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800011a0`
- `0x180001fe8`
- `0x180003ef0`
- `0x180015010`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::Cleanup(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  void *v4; // r14
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
      v4 = (void *)(v3 - 8);
      v5 = *(_QWORD *)(v3 - 8);
      for ( i = (ATL::CComTypeInfoHolder::stringdispid *)(v3 + 16 * v5); v5; --v5 )
      {
        i = (ATL::CComTypeInfoHolder::stringdispid *)((char *)i - 16);
        ATL::CComTypeInfoHolder::stringdispid::~stringdispid(i);
      }
      operator delete[](v4);
    }
    *(_QWORD *)(a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x180003ef0  test    rcx, rcx
0x180003ef3  jz      short locret_180003F68
0x180003ef5  push    rbx
0x180003ef6  push    rsi
0x180003ef7  push    rdi
0x180003ef8  push    r14
0x180003efa  sub     rsp, 28h
0x180003efe  mov     rbx, rcx
0x180003f01  mov     rcx, [rcx+18h]
0x180003f05  test    rcx, rcx
0x180003f08  jz      short loc_180003F16
0x180003f0a  mov     rax, [rcx]
0x180003f0d  mov     rax, [rax+10h]
0x180003f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f16  mov     rax, [rbx+28h]
0x180003f1a  mov     qword ptr [rbx+18h], 0
0x180003f22  test    rax, rax
0x180003f25  jz      short loc_180003F57
0x180003f27  lea     r14, [rax-8]
0x180003f2b  mov     rsi, [r14]
0x180003f2e  mov     rdi, rsi
0x180003f31  shl     rdi, 4
0x180003f35  add     rdi, rax
0x180003f38  test    rsi, rsi
0x180003f3b  jz      short loc_180003F4F
0x180003f3d  sub     rdi, 10h
0x180003f41  mov     rcx, rdi; this
0x180003f44  call    ??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)
0x180003f49  sub     rsi, 1
0x180003f4d  jnz     short loc_180003F3D
0x180003f4f  mov     rcx, r14; Block
0x180003f52  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180003f57  mov     qword ptr [rbx+28h], 0
0x180003f5f  add     rsp, 28h
0x180003f63  pop     r14
0x180003f65  pop     rdi
0x180003f66  pop     rsi
0x180003f67  pop     rbx
0x180003f68  retn
```
