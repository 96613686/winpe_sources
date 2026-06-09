# ParsedObjectPath::AddKeyRef(KeyRef *)

- ea: `0x1800145d8`
- end: `0x18001465a`
- name: `?AddKeyRef@ParsedObjectPath@@QEAAHPEAUKeyRef@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(ParsedObjectPath *__hidden this, struct KeyRef *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014ef4`
- `0x180015220`

## callees

- `0x1800145d8`
- `0x180015646`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180014631`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180014631`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001460b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001460b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ParsedObjectPath::AddKeyRef(ParsedObjectPath *this, struct KeyRef *a2)
{
  int v2; // eax
  int v5; // ebp
  __int64 result; // rax
  __int64 v7; // rsi

  v2 = *((_DWORD *)this + 9);
  if ( *((_DWORD *)this + 8) == v2 )
  {
    v5 = 2 * v2;
    result = (__int64)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(2 * v2), 8u));
    v7 = result;
    if ( !result )
      return result;
    memcpy_0((void *)result, *((const void **)this + 5), 8LL * *((unsigned int *)this + 9));
    CWin32DefaultArena::WbemMemFree(*((void **)this + 5));
    *((_QWORD *)this + 5) = v7;
    *((_DWORD *)this + 9) = v5;
  }
  *(_QWORD *)(*((_QWORD *)this + 5) + 8LL * *((unsigned int *)this + 8)) = a2;
  result = 1;
  ++*((_DWORD *)this + 8);
  return result;
}

```

## disassembly

```asm
0x1800145d8  push    rbx
0x1800145da  push    rbp
0x1800145db  push    rsi
0x1800145dc  push    rdi
0x1800145dd  sub     rsp, 28h
0x1800145e1  mov     eax, [rcx+24h]
0x1800145e4  mov     rdi, rdx
0x1800145e7  mov     rbx, rcx
0x1800145ea  cmp     [rcx+20h], eax
0x1800145ed  jnz     short loc_18001463E
0x1800145ef  lea     ebp, [rax+rax]
0x1800145f2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800145f9  mov     r8d, ebp
0x1800145fc  mov     eax, 8
0x180014601  mul     r8
0x180014604  cmovb   rax, rcx
0x180014608  mov     rcx, rax
0x18001460b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180014611  mov     rsi, rax
0x180014614  test    rax, rax
0x180014617  jz      short loc_180014651
0x180014619  mov     r8d, [rbx+24h]
0x18001461d  mov     rcx, rsi; void *
0x180014620  mov     rdx, [rbx+28h]; Src
0x180014624  shl     r8, 3; Size
0x180014628  call    memcpy_0
0x18001462d  mov     rcx, [rbx+28h]
0x180014631  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180014637  mov     [rbx+28h], rsi
0x18001463b  mov     [rbx+24h], ebp
0x18001463e  mov     ecx, [rbx+20h]
0x180014641  mov     rax, [rbx+28h]
0x180014645  mov     [rax+rcx*8], rdi
0x180014649  mov     eax, 1
0x18001464e  add     [rbx+20h], eax
0x180014651  add     rsp, 28h
0x180014655  pop     rdi
0x180014656  pop     rsi
0x180014657  pop     rbp
0x180014658  pop     rbx
0x180014659  retn
```
