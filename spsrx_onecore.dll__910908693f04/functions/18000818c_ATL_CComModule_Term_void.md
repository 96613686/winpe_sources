# ATL::CComModule::Term(void)

- ea: `0x18000818c`
- end: `0x180008216`
- name: `?Term@CComModule@ATL@@QEAAXXZ`
- size: `138`
- prototype: `void __fastcall(ATL::CComModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002f78`

## callees

- `0x180001fc0`
- `0x18000818c`
- `0x180010010`

## pseudocode

```c
void __fastcall ATL::CComModule::Term(ATL::CComModule *this)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rax

  v1 = qword_1800152F8;
  if ( qword_1800152F8 )
  {
    while ( *(_QWORD *)v1 )
    {
      v2 = *(_QWORD *)(v1 + 32);
      if ( v2 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
      *(_QWORD *)(v1 + 32) = 0;
      (*(void (__fastcall **)(_QWORD))(v1 + 64))(0);
      v1 += 72;
    }
  }
  v3 = qword_1800153C0;
  v4 = qword_1800153C8;
  while ( v3 < v4 )
  {
    if ( *(_QWORD *)v3 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v3 + 64LL))(0);
      v4 = qword_1800153C8;
    }
    v3 += 8LL;
  }
  ATL::CAtlModule::Term((ATL::CAtlModule *)&_Module);
}

```

## disassembly

```asm
0x18000818c  push    rbx
0x18000818e  sub     rsp, 20h
0x180008192  mov     rbx, cs:qword_1800152F8
0x180008199  test    rbx, rbx
0x18000819c  jz      short loc_1800081D2
0x18000819e  jmp     short loc_1800081CC
0x1800081a0  mov     rcx, [rbx+20h]
0x1800081a4  test    rcx, rcx
0x1800081a7  jz      short loc_1800081B5
0x1800081a9  mov     rax, [rcx]
0x1800081ac  mov     rax, [rax+10h]
0x1800081b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081b5  mov     qword ptr [rbx+20h], 0
0x1800081bd  xor     ecx, ecx
0x1800081bf  mov     rax, [rbx+40h]
0x1800081c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081c8  add     rbx, 48h ; 'H'
0x1800081cc  cmp     qword ptr [rbx], 0
0x1800081d0  jnz     short loc_1800081A0
0x1800081d2  mov     rbx, cs:qword_1800153C0
0x1800081d9  mov     rax, cs:qword_1800153C8
0x1800081e0  jmp     short loc_180008200
0x1800081e2  mov     rdx, [rbx]
0x1800081e5  test    rdx, rdx
0x1800081e8  jz      short loc_1800081FC
0x1800081ea  xor     ecx, ecx
0x1800081ec  mov     rax, [rdx+40h]
0x1800081f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081f5  mov     rax, cs:qword_1800153C8
0x1800081fc  add     rbx, 8
0x180008200  cmp     rbx, rax
0x180008203  jb      short loc_1800081E2
0x180008205  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x18000820c  add     rsp, 20h
0x180008210  pop     rbx
0x180008211  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
