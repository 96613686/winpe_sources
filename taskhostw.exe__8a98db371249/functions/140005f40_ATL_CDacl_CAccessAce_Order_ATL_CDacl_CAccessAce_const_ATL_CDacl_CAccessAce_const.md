# ATL::CDacl::CAccessAce::Order(ATL::CDacl::CAccessAce const &,ATL::CDacl::CAccessAce const &)

- ea: `0x140005f40`
- end: `0x140006014`
- name: `?Order@CAccessAce@CDacl@ATL@@SAHAEBV123@0@Z`
- size: `212`
- prototype: `__int64 __fastcall(const struct ATL::CDacl::CAccessAce *, const struct ATL::CDacl::CAccessAce *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140005d50`

## callees

- `0x140005f40`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall ATL::CDacl::CAccessAce::Order(
        const struct ATL::CDacl::CAccessAce *a1,
        const struct ATL::CDacl::CAccessAce *a2)
{
  if ( (*((_BYTE *)a1 + 132) & 0x10) != 0 )
  {
    if ( (*((_BYTE *)a2 + 132) & 0x10) == 0 )
      return 0xFFFFFFFFLL;
  }
  else if ( (*((_BYTE *)a2 + 132) & 0x10) != 0 )
  {
    return 1;
  }
  if ( *((_BYTE *)a1 + 144) )
  {
    if ( !*((_BYTE *)a2 + 144) )
      return 0xFFFFFFFFLL;
    goto LABEL_9;
  }
  if ( *((_BYTE *)a2 + 144) )
    return 1;
LABEL_9:
  if ( (*(unsigned __int8 (__fastcall **)(const struct ATL::CDacl::CAccessAce *))(*(_QWORD *)a1 + 32LL))(a1)
    && !(*(unsigned __int8 (__fastcall **)(const struct ATL::CDacl::CAccessAce *))(*(_QWORD *)a2 + 32LL))(a2) )
  {
    return 0xFFFFFFFFLL;
  }
  return !(*(unsigned __int8 (__fastcall **)(const struct ATL::CDacl::CAccessAce *))(*(_QWORD *)a1 + 32LL))(a1)
      && (*(unsigned __int8 (__fastcall **)(const struct ATL::CDacl::CAccessAce *))(*(_QWORD *)a2 + 32LL))(a2) != 0;
}

```

## disassembly

```asm
0x140005f40  mov     [rsp+arg_0], rbx
0x140005f45  push    rdi
0x140005f46  sub     rsp, 20h
0x140005f4a  test    byte ptr [rcx+84h], 10h
0x140005f51  mov     rdi, rdx
0x140005f54  mov     rbx, rcx
0x140005f57  jz      short loc_140005F64
0x140005f59  test    byte ptr [rdx+84h], 10h
0x140005f60  jnz     short loc_140005F71
0x140005f62  jmp     short loc_140005FB1
0x140005f64  test    byte ptr [rdx+84h], 10h
0x140005f6b  jnz     loc_140006004
0x140005f71  cmp     byte ptr [rcx+90h], 0
0x140005f78  jz      short loc_140005F85
0x140005f7a  cmp     byte ptr [rdx+90h], 0
0x140005f81  jnz     short loc_140005F8E
0x140005f83  jmp     short loc_140005FB1
0x140005f85  cmp     byte ptr [rdx+90h], 0
0x140005f8c  jnz     short loc_140006004
0x140005f8e  mov     rax, [rcx]
0x140005f91  mov     rax, [rax+20h]
0x140005f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f9a  test    al, al
0x140005f9c  jz      short loc_140005FC1
0x140005f9e  mov     rax, [rdi]
0x140005fa1  mov     rcx, rdi
0x140005fa4  mov     rax, [rax+20h]
0x140005fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fad  test    al, al
0x140005faf  jnz     short loc_140005FC1
0x140005fb1  mov     eax, 0FFFFFFFFh
0x140005fb6  mov     rbx, [rsp+28h+arg_0]
0x140005fbb  add     rsp, 20h
0x140005fbf  pop     rdi
0x140005fc0  retn
0x140005fc1  mov     rax, [rbx]
0x140005fc4  mov     rcx, rbx
0x140005fc7  mov     rax, [rax+20h]
0x140005fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fd0  test    al, al
0x140005fd2  jnz     short loc_140005FF7
0x140005fd4  mov     rax, [rdi]
0x140005fd7  mov     rcx, rdi
0x140005fda  mov     rax, [rax+20h]
0x140005fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fe3  xor     ecx, ecx
0x140005fe5  test    al, al
0x140005fe7  setnz   cl
0x140005fea  mov     eax, ecx
0x140005fec  mov     rbx, [rsp+28h+arg_0]
0x140005ff1  add     rsp, 20h
0x140005ff5  pop     rdi
0x140005ff6  retn
0x140005ff7  xor     eax, eax
0x140005ff9  mov     rbx, [rsp+28h+arg_0]
0x140005ffe  add     rsp, 20h
0x140006002  pop     rdi
0x140006003  retn
0x140006004  mov     rbx, [rsp+28h+arg_0]
0x140006009  mov     eax, 1
0x14000600e  add     rsp, 20h
0x140006012  pop     rdi
0x140006013  retn
```
