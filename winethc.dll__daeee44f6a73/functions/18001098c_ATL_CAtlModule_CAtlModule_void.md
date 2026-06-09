# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x18001098c`
- end: `0x180010a37`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `171`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180010a40`
- `0x180013270`

## callees

- `0x1800012c0`
- `0x18000d798`
- `0x18001098c`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180010a0c`
- `KERNEL32!DeleteCriticalSection` at `0x180010a0c`

## pseudocode

```c
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, unsigned int a2)
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
        JUMPOUT(0x180010A36LL);
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
0x18001098c  push    rbx
0x18001098e  push    rsi
0x18001098f  push    rdi
0x180010990  push    r14
0x180010992  push    r15
0x180010994  sub     rsp, 20h
0x180010998  lea     r14, [rcx+8]
0x18001099c  mov     rdi, rcx
0x18001099f  cmp     dword ptr [r14], 0
0x1800109a3  jz      short loc_180010A1F
0x1800109a5  cmp     qword ptr [rcx+10h], 0
0x1800109aa  jz      short loc_1800109F3
0x1800109ac  mov     rax, rcx
0x1800109af  neg     rax
0x1800109b2  sbb     rsi, rsi
0x1800109b5  and     rsi, r14
0x1800109b8  jz      short loc_180010A2C
0x1800109ba  mov     r15, [rsi+8]
0x1800109be  test    r15, r15
0x1800109c1  jz      short loc_1800109E3
0x1800109c3  mov     rcx, [r15+8]
0x1800109c7  mov     rax, [r15]
0x1800109ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109cf  mov     rbx, [r15+10h]
0x1800109d3  mov     rcx, r15; Block
0x1800109d6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800109db  mov     r15, rbx
0x1800109de  test    rbx, rbx
0x1800109e1  jnz     short loc_1800109C3
0x1800109e3  mov     qword ptr [rsi+8], 0
0x1800109eb  mov     qword ptr [rdi+10h], 0
0x1800109f3  mov     rcx, [rdi+40h]
0x1800109f7  test    rcx, rcx
0x1800109fa  jz      short loc_180010A08
0x1800109fc  mov     rax, [rcx]
0x1800109ff  mov     rax, [rax+10h]
0x180010a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a08  lea     rcx, [rdi+18h]; lpCriticalSection
0x180010a0c  call    cs:__imp_DeleteCriticalSection
0x180010a13  nop     dword ptr [rax+rax+00h]
0x180010a18  mov     dword ptr [r14], 0
0x180010a1f  add     rsp, 20h
0x180010a23  pop     r15
0x180010a25  pop     r14
0x180010a27  pop     rdi
0x180010a28  pop     rsi
0x180010a29  pop     rbx
0x180010a2a  retn
0x180010a2c  mov     ecx, 0C0000005h; unsigned int
0x180010a31  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
