# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180007f48`
- end: `0x180008007`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `191`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180008030`
- `0x180033ca0`

## callees

- `0x180007f48`
- `0x180008204`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007f9f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007f9f`
- `KERNEL32!DeleteCriticalSection` at `0x180007fdc`
- `KERNEL32!DeleteCriticalSection` at `0x180007fdc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, unsigned int a2)
{
  unsigned __int64 v3; // r14
  __int64 v4; // rsi
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  v3 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = v3 & -(__int64)(this != 0);
      if ( !v4 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x180008006LL);
      }
      v5 = *(_QWORD **)((v3 & -(__int64)(this != 0)) + 8);
      if ( v5 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v5)(v5[1]);
          v6 = (_QWORD *)v5[2];
          operator delete(v5);
          v5 = v6;
        }
        while ( v6 );
      }
      *(_QWORD *)(v4 + 8) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v7 = *((_QWORD *)this + 8);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v3 = 0;
  }
}

```

## disassembly

```asm
0x180007f48  push    rbx
0x180007f4a  push    rsi
0x180007f4b  push    rdi
0x180007f4c  push    r14
0x180007f4e  push    r15
0x180007f50  sub     rsp, 30h
0x180007f54  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x180007f5d  mov     rdi, rcx
0x180007f60  lea     r14, [rcx+8]
0x180007f64  cmp     dword ptr [r14], 0
0x180007f68  jz      loc_180007FEF
0x180007f6e  cmp     qword ptr [rcx+10h], 0
0x180007f73  jz      short loc_180007FC3
0x180007f75  mov     rax, rcx
0x180007f78  neg     rax
0x180007f7b  sbb     rsi, rsi
0x180007f7e  and     rsi, r14
0x180007f81  jz      short loc_180007FFC
0x180007f83  mov     r15, [rsi+8]
0x180007f87  test    r15, r15
0x180007f8a  jz      short loc_180007FB3
0x180007f8c  mov     rcx, [r15+8]
0x180007f90  mov     rax, [r15]
0x180007f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f98  mov     rbx, [r15+10h]
0x180007f9c  mov     rcx, r15
0x180007f9f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007fa6  nop     dword ptr [rax+rax+00h]
0x180007fab  mov     r15, rbx
0x180007fae  test    rbx, rbx
0x180007fb1  jnz     short loc_180007F8C
0x180007fb3  mov     qword ptr [rsi+8], 0
0x180007fbb  mov     qword ptr [rdi+10h], 0
0x180007fc3  mov     rcx, [rdi+40h]
0x180007fc7  test    rcx, rcx
0x180007fca  jz      short loc_180007FD8
0x180007fcc  mov     rax, [rcx]
0x180007fcf  mov     rax, [rax+10h]
0x180007fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fd8  lea     rcx, [rdi+18h]; lpCriticalSection
0x180007fdc  call    cs:__imp_DeleteCriticalSection
0x180007fe3  nop     dword ptr [rax+rax+00h]
0x180007fe8  mov     dword ptr [r14], 0
0x180007fef  add     rsp, 30h
0x180007ff3  pop     r15
0x180007ff5  pop     r14
0x180007ff7  pop     rdi
0x180007ff8  pop     rsi
0x180007ff9  pop     rbx
0x180007ffa  retn
0x180007ffc  mov     ecx, 0C0000005h; unsigned int
0x180008001  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
