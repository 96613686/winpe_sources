# ParsedObjectPath::AddNamespace(ushort const *)

- ea: `0x180014660`
- end: `0x1800146f3`
- name: `?AddNamespace@ParsedObjectPath@@QEAAHPEBG@Z`
- size: `147`
- prototype: `__int64 __fastcall(ParsedObjectPath *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014ce8`
- `0x180015084`

## callees

- `0x180014660`
- `0x18001474c`
- `0x180015646`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800146b9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800146b9`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014693`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014693`

## pseudocode

```c
__int64 __fastcall ParsedObjectPath::AddNamespace(ParsedObjectPath *this, const unsigned __int16 *a2)
{
  int v2; // eax
  int v5; // ebp
  void *v6; // rax
  void *v7; // rdi
  unsigned __int16 *v8; // rax
  __int64 result; // rax

  v2 = *((_DWORD *)this + 3);
  if ( *((_DWORD *)this + 2) == v2 )
  {
    v5 = 2 * v2;
    v6 = CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(2 * v2), 8u));
    v7 = v6;
    if ( !v6 )
      return 0;
    memcpy_0(v6, *((const void **)this + 2), 8LL * *((unsigned int *)this + 3));
    CWin32DefaultArena::WbemMemFree(*((void **)this + 2));
    *((_QWORD *)this + 2) = v7;
    *((_DWORD *)this + 3) = v5;
  }
  v8 = Macro_CloneLPWSTR(a2);
  if ( v8 )
  {
    *(_QWORD *)(*((_QWORD *)this + 2) + 8LL * *((unsigned int *)this + 2)) = v8;
    result = 1;
    ++*((_DWORD *)this + 2);
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x180014660  push    rbx
0x180014662  push    rbp
0x180014663  push    rsi
0x180014664  push    rdi
0x180014665  sub     rsp, 28h
0x180014669  mov     eax, [rcx+0Ch]
0x18001466c  mov     rsi, rdx
0x18001466f  mov     rbx, rcx
0x180014672  cmp     [rcx+8], eax
0x180014675  jnz     short loc_1800146C6
0x180014677  lea     ebp, [rax+rax]
0x18001467a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180014681  mov     r8d, ebp
0x180014684  mov     eax, 8
0x180014689  mul     r8
0x18001468c  cmovb   rax, rcx
0x180014690  mov     rcx, rax
0x180014693  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180014699  mov     rdi, rax
0x18001469c  test    rax, rax
0x18001469f  jz      short loc_1800146E8
0x1800146a1  mov     r8d, [rbx+0Ch]
0x1800146a5  mov     rcx, rax; void *
0x1800146a8  mov     rdx, [rbx+10h]; Src
0x1800146ac  shl     r8, 3; Size
0x1800146b0  call    memcpy_0
0x1800146b5  mov     rcx, [rbx+10h]
0x1800146b9  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800146bf  mov     [rbx+10h], rdi
0x1800146c3  mov     [rbx+0Ch], ebp
0x1800146c6  mov     rcx, rsi; Src
0x1800146c9  call    ?Macro_CloneLPWSTR@@YAPEAGPEBG@Z; Macro_CloneLPWSTR(ushort const *)
0x1800146ce  test    rax, rax
0x1800146d1  jz      short loc_1800146E8
0x1800146d3  mov     edx, [rbx+8]
0x1800146d6  mov     rcx, [rbx+10h]
0x1800146da  mov     [rcx+rdx*8], rax
0x1800146de  mov     eax, 1
0x1800146e3  add     [rbx+8], eax
0x1800146e6  jmp     short loc_1800146EA
0x1800146e8  xor     eax, eax
0x1800146ea  add     rsp, 28h
0x1800146ee  pop     rdi
0x1800146ef  pop     rsi
0x1800146f0  pop     rbp
0x1800146f1  pop     rbx
0x1800146f2  retn
```
