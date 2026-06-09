# WTL::CString::AllocCopy(WTL::CString &,int,int,int)

- ea: `0x18000d500`
- end: `0x18000d570`
- name: `?AllocCopy@CString@WTL@@IEBAHAEAV12@HHH@Z`
- size: `112`
- prototype: `int(WTL::CString *__hidden this, struct WTL::CString *, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800103d4`
- `0x180013e50`

## callees

- `0x1800048d4`
- `0x180004c00`
- `0x18000d500`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000d551`
- `msvcrt!memcpy_s` at `0x18000d551`

## pseudocode

```c
__int64 __fastcall WTL::CString::AllocCopy(WTL::CString *this, void **a2, int a3, int a4)
{
  __int64 v4; // rbp
  __int64 v6; // rsi
  unsigned int v8; // ebx
  errno_t v9; // eax

  v4 = a4;
  v6 = a3;
  if ( !a3 )
  {
    *a2 = (void *)WTL::_atltmpPchNil;
    return 1;
  }
  v8 = 0;
  if ( (unsigned int)WTL::CString::AllocBuffer((WTL::CString *)a2, a3) )
  {
    v9 = memcpy_s(*a2, 2LL * ((int)v6 + 1), (const void *const)(*(_QWORD *)this + 2 * v4), 2 * v6);
    ATL::AtlCrtErrorCheck(v9);
    return 1;
  }
  return v8;
}

```

## disassembly

```asm
0x18000d500  push    rbx
0x18000d502  push    rbp
0x18000d503  push    rsi
0x18000d504  push    rdi
0x18000d505  push    r14
0x18000d507  sub     rsp, 20h
0x18000d50b  movsxd  rbp, r9d
0x18000d50e  mov     rdi, rdx
0x18000d511  movsxd  rsi, r8d
0x18000d514  mov     r14, rcx
0x18000d517  test    r8d, r8d
0x18000d51a  jnz     short loc_18000D528
0x18000d51c  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x18000d523  mov     [rdx], rax
0x18000d526  jmp     short loc_18000D55E
0x18000d528  mov     edx, esi; int
0x18000d52a  mov     rcx, rdi; this
0x18000d52d  xor     ebx, ebx
0x18000d52f  call    ?AllocBuffer@CString@WTL@@IEAAHH@Z; WTL::CString::AllocBuffer(int)
0x18000d534  test    eax, eax
0x18000d536  jz      short loc_18000D563
0x18000d538  mov     rax, [r14]
0x18000d53b  mov     r9, rsi
0x18000d53e  mov     rcx, [rdi]; Destination
0x18000d541  add     r9, r9; SourceSize
0x18000d544  lea     r8, [rax+rbp*2]; Source
0x18000d548  lea     eax, [rsi+1]
0x18000d54b  movsxd  rdx, eax
0x18000d54e  add     rdx, rdx; DestinationSize
0x18000d551  call    cs:__imp_memcpy_s
0x18000d557  mov     ecx, eax; int
0x18000d559  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000d55e  mov     ebx, 1
0x18000d563  mov     eax, ebx
0x18000d565  add     rsp, 20h
0x18000d569  pop     r14
0x18000d56b  pop     rdi
0x18000d56c  pop     rsi
0x18000d56d  pop     rbp
0x18000d56e  pop     rbx
0x18000d56f  retn
```
