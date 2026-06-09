# ATL::CComModule::Term(void)

- ea: `0x180006038`
- end: `0x1800060c2`
- name: `?Term@CComModule@ATL@@QEAAXXZ`
- size: `138`
- prototype: `void __fastcall(ATL::CComModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001160`

## callees

- `0x180005f7c`
- `0x180006038`
- `0x180013010`

## pseudocode

```c
void __fastcall ATL::CComModule::Term(ATL::CComModule *this)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 *v3; // rbx
  __int64 *v4; // rax

  v1 = qword_18001E3A8;
  if ( qword_18001E3A8 )
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
  v3 = off_18001D330[0];
  v4 = off_18001D338;
  while ( v3 < v4 )
  {
    if ( *v3 )
    {
      (*(void (__fastcall **)(_QWORD))(*v3 + 64))(0);
      v4 = off_18001D338;
    }
    ++v3;
  }
  ATL::CAtlModule::Term((ATL::CAtlModule *)&_Module);
}

```

## disassembly

```asm
0x180006038  push    rbx
0x18000603a  sub     rsp, 20h
0x18000603e  mov     rbx, cs:qword_18001E3A8
0x180006045  test    rbx, rbx
0x180006048  jz      short loc_18000607E
0x18000604a  jmp     short loc_180006078
0x18000604c  mov     rcx, [rbx+20h]
0x180006050  test    rcx, rcx
0x180006053  jz      short loc_180006061
0x180006055  mov     rax, [rcx]
0x180006058  mov     rax, [rax+10h]
0x18000605c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006061  mov     qword ptr [rbx+20h], 0
0x180006069  xor     ecx, ecx
0x18000606b  mov     rax, [rbx+40h]
0x18000606f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006074  add     rbx, 48h ; 'H'
0x180006078  cmp     qword ptr [rbx], 0
0x18000607c  jnz     short loc_18000604C
0x18000607e  mov     rbx, cs:off_18001D330
0x180006085  mov     rax, cs:off_18001D338
0x18000608c  jmp     short loc_1800060AC
0x18000608e  mov     rdx, [rbx]
0x180006091  test    rdx, rdx
0x180006094  jz      short loc_1800060A8
0x180006096  xor     ecx, ecx
0x180006098  mov     rax, [rdx+40h]
0x18000609c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060a1  mov     rax, cs:off_18001D338
0x1800060a8  add     rbx, 8
0x1800060ac  cmp     rbx, rax
0x1800060af  jb      short loc_18000608E
0x1800060b1  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x1800060b8  add     rsp, 20h
0x1800060bc  pop     rbx
0x1800060bd  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
