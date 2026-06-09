# ATL::CAtlModule::Term(void)

- ea: `0x18002c230`
- end: `0x18002c2e3`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800251a0`
- `0x18002c2ec`
- `0x180057340`

## callees

- `0x18002c230`
- `0x180058010`

## import_xrefs

- `msvcrt!free` at `0x18002c293`
- `msvcrt!free` at `0x18002c293`
- `KERNEL32!DeleteCriticalSection` at `0x18002c2ca`
- `KERNEL32!DeleteCriticalSection` at `0x18002c2ca`
- `KERNEL32!RaiseException` at `0x18002c270`
- `KERNEL32!RaiseException` at `0x18002c270`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v2; // r14
  __int64 v3; // rsi
  _QWORD *v4; // r15
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v3 = v2 & -(__int64)(this != 0);
      if ( !v3 )
      {
        RaiseException(0xC0000005, 1u, 0, 0);
        __debugbreak();
      }
      v4 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
      if ( v4 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v4)(v4[1]);
          v5 = (_QWORD *)v4[2];
          free(v4);
          v4 = v5;
        }
        while ( v5 );
      }
      *(_QWORD *)(v3 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v6 = *((_QWORD *)this + 8);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x18002c230  push    rbx
0x18002c232  push    rsi
0x18002c233  push    rdi
0x18002c234  push    r14
0x18002c236  push    r15
0x18002c238  sub     rsp, 20h
0x18002c23c  mov     rdi, rcx
0x18002c23f  lea     r14, [rcx+8]
0x18002c243  cmp     dword ptr [r14], 0
0x18002c247  jz      loc_18002C2D7
0x18002c24d  cmp     qword ptr [rcx+10h], 0
0x18002c252  jz      short loc_18002C2B1
0x18002c254  mov     rax, rcx
0x18002c257  neg     rax
0x18002c25a  sbb     rsi, rsi
0x18002c25d  and     rsi, r14
0x18002c260  jnz     short loc_18002C277
0x18002c262  xor     r9d, r9d; lpArguments
0x18002c265  xor     r8d, r8d; nNumberOfArguments
0x18002c268  lea     edx, [rsi+1]; dwExceptionFlags
0x18002c26b  mov     ecx, 0C0000005h; dwExceptionCode
0x18002c270  call    cs:__imp_RaiseException
0x18002c276  int     3; Trap to Debugger
0x18002c277  mov     r15, [rsi+8]
0x18002c27b  test    r15, r15
0x18002c27e  jz      short loc_18002C2A1
0x18002c280  mov     rcx, [r15+8]
0x18002c284  mov     rax, [r15]
0x18002c287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c28c  mov     rbx, [r15+10h]
0x18002c290  mov     rcx, r15; Block
0x18002c293  call    cs:__imp_free
0x18002c299  mov     r15, rbx
0x18002c29c  test    rbx, rbx
0x18002c29f  jnz     short loc_18002C280
0x18002c2a1  mov     qword ptr [rsi+8], 0
0x18002c2a9  mov     qword ptr [rdi+10h], 0
0x18002c2b1  mov     rcx, [rdi+40h]
0x18002c2b5  test    rcx, rcx
0x18002c2b8  jz      short loc_18002C2C6
0x18002c2ba  mov     rax, [rcx]
0x18002c2bd  mov     rax, [rax+10h]
0x18002c2c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2c6  lea     rcx, [rdi+18h]; lpCriticalSection
0x18002c2ca  call    cs:__imp_DeleteCriticalSection
0x18002c2d0  mov     dword ptr [r14], 0
0x18002c2d7  add     rsp, 20h
0x18002c2db  pop     r15
0x18002c2dd  pop     r14
0x18002c2df  pop     rdi
0x18002c2e0  pop     rsi
0x18002c2e1  pop     rbx
0x18002c2e2  retn
```
