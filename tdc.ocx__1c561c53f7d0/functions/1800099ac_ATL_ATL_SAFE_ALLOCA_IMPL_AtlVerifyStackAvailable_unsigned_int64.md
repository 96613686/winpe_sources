# ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)

- ea: `0x1800099ac`
- end: `0x180009a2f`
- name: `?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z`
- size: `131`
- prototype: `bool __fastcall(ATL::_ATL_SAFE_ALLOCA_IMPL *__hidden this, unsigned __int64)`
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x180002fd8`
- `0x180004fd0`
- `0x180005e28`
- `0x18000f500`
- `0x18000f68c`
- `0x18000f804`
- `0x18001008c`
- `0x180010440`
- `0x180011800`
- `0x1800124b4`
- `0x1800125c4`
- `0x1800127d8`
- `0x1800128e8`
- `0x180012cac`
- `0x180013070`

## callees

- `0x1800099ac`
- `0x180014270`
- `0x180014300`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x180009a10`
- `msvcrt!_resetstkoflw` at `0x180009a10`

## pseudocode

```c
char __fastcall ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64 this)
{
  char v1; // bl
  char *v2; // rax
  unsigned __int64 v3; // rcx
  void *v4; // rsp
  void *v5; // rsp

  v1 = 1;
  if ( ~this < 0x4000 )
    return 0;
  v2 = (char *)(this + 0x4000);
  v3 = this + 16399;
  if ( v3 <= (unsigned __int64)v2 )
    v3 = 0xFFFFFFFFFFFFFF0LL;
  v4 = alloca(v3 & 0xFFFFFFFFFFFFFFF0uLL);
  v5 = alloca(v3 & 0xFFFFFFFFFFFFFFF0uLL);
  return v1;
}

```

## disassembly

```asm
0x1800099ac  push    rbp
0x1800099ae  sub     rsp, 30h
0x1800099b2  lea     rbp, [rsp+20h]
0x1800099b7  mov     [rbp+10h+arg_0], rbx
0x1800099bb  mov     rax, cs:__security_cookie
0x1800099c2  xor     rax, rbp
0x1800099c5  mov     [rbp+10h+var_8], rax
0x1800099c9  mov     bl, 1
0x1800099cb  mov     rax, rcx
0x1800099ce  not     rax
0x1800099d1  cmp     rax, 4000h
0x1800099d7  jb      short loc_180009A04
0x1800099d9  lea     rax, [rcx+4000h]
0x1800099e0  lea     rcx, [rax+0Fh]
0x1800099e4  cmp     rcx, rax
0x1800099e7  ja      short loc_1800099F3
0x1800099e9  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800099f3  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800099f7  mov     rax, rcx
0x1800099fa  call    _alloca_probe
0x1800099ff  sub     rsp, rcx
0x180009a02  jmp     short loc_180009A09
0x180009a04  xor     bl, bl
0x180009a06  mov     [rbp+10h+var_10], bl
0x180009a09  jmp     short loc_180009A17
0x180009a0b  xor     bl, bl
0x180009a0d  mov     [rbp+10h+var_10], bl
0x180009a10  call    cs:__imp__resetstkoflw
0x180009a16  nop
0x180009a17  mov     al, bl
0x180009a19  mov     rcx, [rbp+10h+var_8]
0x180009a1d  xor     rcx, rbp; StackCookie
0x180009a20  call    __security_check_cookie
0x180009a25  mov     rbx, [rbp+10h+arg_0]
0x180009a29  lea     rsp, [rbp+10h]
0x180009a2d  pop     rbp
0x180009a2e  retn
0x180014656  push    rbp
0x180014658  sub     rsp, 20h
0x18001465c  lea     rbp, [rdx+20h]
0x180014660  mov     rax, [rcx]
0x180014663  xor     ecx, ecx
0x180014665  cmp     dword ptr [rax], 0C00000FDh
0x18001466b  setz    cl
0x18001466e  mov     eax, ecx
0x180014670  add     rsp, 20h
0x180014674  pop     rbp
0x180014675  retn
```
