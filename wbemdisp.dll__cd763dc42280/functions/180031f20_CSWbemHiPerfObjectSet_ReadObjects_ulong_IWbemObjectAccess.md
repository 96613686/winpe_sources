# CSWbemHiPerfObjectSet::ReadObjects(ulong &,IWbemObjectAccess * * *)

- ea: `0x180031f20`
- end: `0x180032004`
- name: `?ReadObjects@CSWbemHiPerfObjectSet@@QEAAJAEAKPEAPEAPEAUIWbemObjectAccess@@@Z`
- size: `228`
- prototype: `__int64 __fastcall(CSWbemHiPerfObjectSet *__hidden this, unsigned int *, struct IWbemObjectAccess ***)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003073c`
- `0x1800317c0`
- `0x180031a30`
- `0x1800327e0`

## callees

- `0x180031f20`
- `0x18003405f`
- `0x180036010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180031f90`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180031f90`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180031fde`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180031fde`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemHiPerfObjectSet::ReadObjects(
        CSWbemHiPerfObjectSet *this,
        unsigned int *a2,
        struct IWbemObjectAccess ***a3)
{
  int v6; // ebx
  __int64 v7; // rcx
  struct IWbemObjectAccess **v8; // rax
  int v10; // [rsp+60h] [rbp+8h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = -2147217407;
  v7 = *((_QWORD *)this + 15);
  if ( v7 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v7 + 40LL))(
           v7,
           0,
           0,
           0,
           a2);
    if ( v6 == -2147217348 )
    {
      v6 = 0;
      if ( *a2 )
      {
        v8 = (struct IWbemObjectAccess **)CWin32DefaultArena::WbemMemAlloc(saturated_mul(*a2, 8u));
        *a3 = v8;
        if ( v8 )
        {
          memset_0(v8, 0, 8LL * *a2);
          v10 = 0;
          v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, int *))(**((_QWORD **)this + 15) + 40LL))(
                 *((_QWORD *)this + 15),
                 0,
                 *a2,
                 *a3,
                 &v10);
          if ( v6 < 0 )
          {
            CWin32DefaultArena::WbemMemFree(*a3);
            *a3 = 0;
            *a2 = 0;
          }
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180031f20  push    rbx
0x180031f22  push    rbp
0x180031f23  push    rsi
0x180031f24  push    rdi
0x180031f25  sub     rsp, 38h
0x180031f29  mov     rsi, r8
0x180031f2c  mov     rdi, rdx
0x180031f2f  mov     rbp, rcx
0x180031f32  mov     qword ptr [r8], 0
0x180031f39  mov     dword ptr [rdx], 0
0x180031f3f  mov     ebx, 80041001h
0x180031f44  mov     rcx, [rcx+78h]
0x180031f48  test    rcx, rcx
0x180031f4b  jz      loc_180031FF9
0x180031f51  mov     rax, [rcx]
0x180031f54  mov     [rsp+58h+var_38], rdx
0x180031f59  xor     r9d, r9d
0x180031f5c  xor     r8d, r8d
0x180031f5f  xor     edx, edx
0x180031f61  mov     rax, [rax+28h]
0x180031f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031f6a  mov     ebx, eax
0x180031f6c  cmp     eax, 8004103Ch
0x180031f71  jnz     loc_180031FF9
0x180031f77  xor     ebx, ebx
0x180031f79  cmp     [rdi], ebx
0x180031f7b  jbe     short loc_180031FF9
0x180031f7d  mov     ecx, [rdi]
0x180031f7f  lea     eax, [rbx+8]
0x180031f82  mul     rcx
0x180031f85  lea     rcx, [rbx-1]
0x180031f89  cmovb   rax, rcx
0x180031f8d  mov     rcx, rax
0x180031f90  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180031f96  mov     [rsi], rax
0x180031f99  test    rax, rax
0x180031f9c  jz      short loc_180031FF4
0x180031f9e  mov     r8d, [rdi]
0x180031fa1  shl     r8, 3; Size
0x180031fa5  xor     edx, edx; Val
0x180031fa7  mov     rcx, rax; void *
0x180031faa  call    memset_0
0x180031faf  mov     [rsp+58h+arg_0], ebx
0x180031fb3  mov     rcx, [rbp+78h]
0x180031fb7  mov     rax, [rcx]
0x180031fba  lea     rdx, [rsp+58h+arg_0]
0x180031fbf  mov     [rsp+58h+var_38], rdx
0x180031fc4  mov     r9, [rsi]
0x180031fc7  mov     r8d, [rdi]
0x180031fca  xor     edx, edx
0x180031fcc  mov     rax, [rax+28h]
0x180031fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031fd5  mov     ebx, eax
0x180031fd7  test    eax, eax
0x180031fd9  jns     short loc_180031FF9
0x180031fdb  mov     rcx, [rsi]
0x180031fde  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180031fe4  nop
0x180031fe5  mov     qword ptr [rsi], 0
0x180031fec  mov     dword ptr [rdi], 0
0x180031ff2  jmp     short loc_180031FF9
0x180031ff4  mov     ebx, 8007000Eh
0x180031ff9  mov     eax, ebx
0x180031ffb  add     rsp, 38h
0x180031fff  pop     rdi
0x180032000  pop     rsi
0x180032001  pop     rbp
0x180032002  pop     rbx
0x180032003  retn
```
