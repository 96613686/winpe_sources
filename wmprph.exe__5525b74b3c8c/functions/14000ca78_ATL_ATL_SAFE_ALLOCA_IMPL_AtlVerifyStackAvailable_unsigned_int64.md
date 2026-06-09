# ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)

- ea: `0x14000ca78`
- end: `0x14000cae8`
- name: `?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z`
- size: `112`
- prototype: `bool __fastcall(ATL::_ATL_SAFE_ALLOCA_IMPL *__hidden this, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140009ec8`
- `0x14000b9a0`
- `0x14000bbf0`

## callees

- `0x140001390`
- `0x14000ca78`
- `0x14000caf0`
- `0x14000e380`

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
0x14000ca78  push    rbp
0x14000ca7a  sub     rsp, 30h
0x14000ca7e  lea     rbp, [rsp+20h]
0x14000ca83  mov     [rbp+10h+arg_0], rbx
0x14000ca87  mov     rax, cs:__security_cookie
0x14000ca8e  xor     rax, rbp
0x14000ca91  mov     [rbp+10h+var_10], rax
0x14000ca95  mov     bl, 1
0x14000ca97  lea     rdx, [rcx+2000h]
0x14000ca9e  cmp     rdx, rcx
0x14000caa1  jnb     short loc_14000CAA7
0x14000caa3  xor     al, al
0x14000caa5  jmp     short loc_14000CAD2
0x14000caa7  lea     rax, [rdx+0Fh]
0x14000caab  cmp     rax, rdx
0x14000caae  ja      short loc_14000CABA
0x14000cab0  mov     rax, 0FFFFFFFFFFFFFF0h
0x14000caba  and     rax, 0FFFFFFFFFFFFFFF0h
0x14000cabe  call    _alloca_probe
0x14000cac3  sub     rsp, rax
0x14000cac6  jmp     short loc_14000CAD0
0x14000cac8  xor     bl, bl
0x14000caca  call    ?_Atlresetstkoflw@_ATL_SAFE_ALLOCA_IMPL@ATL@@YAHXZ; ATL::_ATL_SAFE_ALLOCA_IMPL::_Atlresetstkoflw(void)
0x14000cacf  nop
0x14000cad0  mov     al, bl
0x14000cad2  mov     rcx, [rbp+10h+var_10]
0x14000cad6  xor     rcx, rbp; StackCookie
0x14000cad9  call    __security_check_cookie
0x14000cade  mov     rbx, [rbp+10h+arg_0]
0x14000cae2  lea     rsp, [rbp+10h]
0x14000cae6  pop     rbp
0x14000cae7  retn
0x14000e527  push    rbp
0x14000e529  sub     rsp, 20h
0x14000e52d  lea     rbp, [rdx+20h]
0x14000e531  mov     rax, [rcx]
0x14000e534  xor     ecx, ecx
0x14000e536  cmp     dword ptr [rax], 0C00000FDh
0x14000e53c  setz    cl
0x14000e53f  mov     eax, ecx
0x14000e541  add     rsp, 20h
0x14000e545  pop     rbp
0x14000e546  retn
```
