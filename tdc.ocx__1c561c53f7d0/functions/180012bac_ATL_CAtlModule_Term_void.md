# ATL::CAtlModule::Term(void)

- ea: `0x180012bac`
- end: `0x180012c50`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000f170`
- `0x180013670`
- `0x1800146b0`

## callees

- `0x180001194`
- `0x180009994`
- `0x180012bac`
- `0x180015010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180012c2c`
- `KERNEL32!DeleteCriticalSection` at `0x180012c2c`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this, unsigned int a2)
{
  unsigned __int64 v2; // r14
  __int64 v4; // rsi
  _QWORD *v5; // r15
  _QWORD *v6; // rbx
  __int64 v7; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v4 = v2 & -(__int64)(this != 0);
      if ( !v4 )
      {
        ATL::_AtlRaiseException(0xC0000005, a2);
        JUMPOUT(0x180012C4FLL);
      }
      v5 = *(_QWORD **)((v2 & -(__int64)(this != 0)) + 8);
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
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x180012bac  push    rbx
0x180012bae  push    rsi
0x180012baf  push    rdi
0x180012bb0  push    r14
0x180012bb2  push    r15
0x180012bb4  sub     rsp, 20h
0x180012bb8  lea     r14, [rcx+8]
0x180012bbc  mov     rdi, rcx
0x180012bbf  cmp     dword ptr [r14], 0
0x180012bc3  jz      short loc_180012C39
0x180012bc5  cmp     qword ptr [rcx+10h], 0
0x180012bca  jz      short loc_180012C13
0x180012bcc  mov     rax, rcx
0x180012bcf  neg     rax
0x180012bd2  sbb     rsi, rsi
0x180012bd5  and     rsi, r14
0x180012bd8  jz      short loc_180012C45
0x180012bda  mov     r15, [rsi+8]
0x180012bde  test    r15, r15
0x180012be1  jz      short loc_180012C03
0x180012be3  mov     rcx, [r15+8]
0x180012be7  mov     rax, [r15]
0x180012bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bef  mov     rbx, [r15+10h]
0x180012bf3  mov     rcx, r15; Block
0x180012bf6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012bfb  mov     r15, rbx
0x180012bfe  test    rbx, rbx
0x180012c01  jnz     short loc_180012BE3
0x180012c03  mov     qword ptr [rsi+8], 0
0x180012c0b  mov     qword ptr [rdi+10h], 0
0x180012c13  mov     rcx, [rdi+40h]
0x180012c17  test    rcx, rcx
0x180012c1a  jz      short loc_180012C28
0x180012c1c  mov     rax, [rcx]
0x180012c1f  mov     rax, [rax+10h]
0x180012c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c28  lea     rcx, [rdi+18h]; lpCriticalSection
0x180012c2c  call    cs:__imp_DeleteCriticalSection
0x180012c32  mov     dword ptr [r14], 0
0x180012c39  add     rsp, 20h
0x180012c3d  pop     r15
0x180012c3f  pop     r14
0x180012c41  pop     rdi
0x180012c42  pop     rsi
0x180012c43  pop     rbx
0x180012c44  retn
0x180012c45  mov     ecx, 0C0000005h; unsigned int
0x180012c4a  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
