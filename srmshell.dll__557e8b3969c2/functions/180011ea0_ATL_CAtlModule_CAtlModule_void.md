# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180011ea0`
- end: `0x180011f45`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `165`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180011d1c`
- `0x180011d7c`
- `0x180012250`
- `0x18001e52a`
- `0x18001e5ea`
- `0x18001f2d0`

## callees

- `0x180011ea0`
- `0x180015ac8`
- `0x180020010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011eea`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011eea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011f21`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011f21`

## pseudocode

```c
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
        JUMPOUT(0x180011F44LL);
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
0x180011ea0  push    rbx
0x180011ea2  push    rsi
0x180011ea3  push    rdi
0x180011ea4  push    r14
0x180011ea6  push    r15
0x180011ea8  sub     rsp, 20h
0x180011eac  mov     rdi, rcx
0x180011eaf  lea     r14, [rcx+8]
0x180011eb3  cmp     dword ptr [r14], 0
0x180011eb7  jz      short loc_180011F2E
0x180011eb9  cmp     qword ptr [rcx+10h], 0
0x180011ebe  jz      short loc_180011F08
0x180011ec0  mov     rax, rcx
0x180011ec3  neg     rax
0x180011ec6  sbb     rsi, rsi
0x180011ec9  and     rsi, r14
0x180011ecc  jz      short loc_180011F3A
0x180011ece  mov     r15, [rsi+8]
0x180011ed2  test    r15, r15
0x180011ed5  jz      short loc_180011EF8
0x180011ed7  mov     rcx, [r15+8]
0x180011edb  mov     rax, [r15]
0x180011ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ee3  mov     rbx, [r15+10h]
0x180011ee7  mov     rcx, r15
0x180011eea  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011ef0  mov     r15, rbx
0x180011ef3  test    rbx, rbx
0x180011ef6  jnz     short loc_180011ED7
0x180011ef8  mov     qword ptr [rsi+8], 0
0x180011f00  mov     qword ptr [rdi+10h], 0
0x180011f08  mov     rcx, [rdi+40h]
0x180011f0c  test    rcx, rcx
0x180011f0f  jz      short loc_180011F1D
0x180011f11  mov     rax, [rcx]
0x180011f14  mov     rax, [rax+10h]
0x180011f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f1d  lea     rcx, [rdi+18h]; lpCriticalSection
0x180011f21  call    cs:__imp_DeleteCriticalSection
0x180011f27  mov     dword ptr [r14], 0
0x180011f2e  add     rsp, 20h
0x180011f32  pop     r15
0x180011f34  pop     r14
0x180011f36  pop     rdi
0x180011f37  pop     rsi
0x180011f38  pop     rbx
0x180011f39  retn
0x180011f3a  mov     ecx, 0C0000005h; unsigned int
0x180011f3f  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
