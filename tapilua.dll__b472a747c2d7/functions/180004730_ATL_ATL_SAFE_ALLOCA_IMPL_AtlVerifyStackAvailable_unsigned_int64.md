# ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)

- ea: `0x180004730`
- end: `0x1800047a0`
- name: `?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z`
- size: `112`
- prototype: `char __fastcall(ATL::_ATL_SAFE_ALLOCA_IMPL *this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002164`
- `0x180003688`
- `0x1800038f0`

## callees

- `0x180001470`
- `0x180004730`
- `0x1800047a8`
- `0x180004ee0`

## pseudocode

```c
char __fastcall ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(ATL::_ATL_SAFE_ALLOCA_IMPL *this)
{
  __int64 v2; // rax
  void *v3; // rsp

  if ( (ATL::_ATL_SAFE_ALLOCA_IMPL *)((char *)this + 0x2000) < this )
    return 0;
  v2 = (__int64)this + 8207;
  if ( (char *)this + 8207 < (char *)this + 0x2000 )
    v2 = 0xFFFFFFFFFFFFFF0LL;
  v3 = alloca(v2 & 0xFFFFFFFFFFFFFFF0uLL);
  return 1;
}

```

## disassembly

```asm
0x180004730  push    rbp
0x180004732  sub     rsp, 30h
0x180004736  lea     rbp, [rsp+20h]
0x18000473b  mov     [rbp+10h+arg_0], rbx
0x18000473f  mov     rax, cs:__security_cookie
0x180004746  xor     rax, rbp
0x180004749  mov     [rbp+10h+var_10], rax
0x18000474d  mov     bl, 1
0x18000474f  lea     rdx, [rcx+2000h]
0x180004756  cmp     rdx, rcx
0x180004759  jnb     short loc_18000475F
0x18000475b  xor     al, al
0x18000475d  jmp     short loc_18000478A
0x18000475f  lea     rax, [rdx+0Fh]
0x180004763  cmp     rax, rdx
0x180004766  ja      short loc_180004772
0x180004768  mov     rax, 0FFFFFFFFFFFFFF0h
0x180004772  and     rax, 0FFFFFFFFFFFFFFF0h
0x180004776  call    _alloca_probe
0x18000477b  sub     rsp, rax
0x18000477e  jmp     short loc_180004788
0x180004780  xor     bl, bl
0x180004782  call    ?_Atlresetstkoflw@_ATL_SAFE_ALLOCA_IMPL@ATL@@YAHXZ; ATL::_ATL_SAFE_ALLOCA_IMPL::_Atlresetstkoflw(void)
0x180004787  nop
0x180004788  mov     al, bl
0x18000478a  mov     rcx, [rbp+10h+var_10]
0x18000478e  xor     rcx, rbp; StackCookie
0x180004791  call    __security_check_cookie
0x180004796  mov     rbx, [rbp+10h+arg_0]
0x18000479a  lea     rsp, [rbp+10h]
0x18000479e  pop     rbp
0x18000479f  retn
0x18000518f  push    rbp
0x180005191  sub     rsp, 20h
0x180005195  lea     rbp, [rdx+20h]
0x180005199  mov     rax, [rcx]
0x18000519c  xor     ecx, ecx
0x18000519e  cmp     dword ptr [rax], 0C00000FDh
0x1800051a4  setz    cl
0x1800051a7  mov     eax, ecx
0x1800051a9  add     rsp, 20h
0x1800051ad  pop     rbp
0x1800051ae  retn
```
