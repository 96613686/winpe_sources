# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180002248`
- end: `0x1800022f1`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `169`
- prototype: `void __fastcall(ATL::CAtlModule *this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800023e0`
- `0x1800050f0`

## callees

- `0x180001534`
- `0x180002248`
- `0x180004a7c`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800022cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800022cd`

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
        JUMPOUT(0x1800022F0LL);
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
0x180002248  push    rbx
0x18000224a  push    rsi
0x18000224b  push    rdi
0x18000224c  push    r14
0x18000224e  push    r15
0x180002250  sub     rsp, 20h
0x180002254  mov     rdi, rcx
0x180002257  lea     r14, [rcx+8]
0x18000225b  cmp     dword ptr [r14], 0
0x18000225f  jz      short loc_1800022DA
0x180002261  cmp     qword ptr [rcx+10h], 0
0x180002266  jz      short loc_1800022B4
0x180002268  mov     rax, rcx
0x18000226b  neg     rax
0x18000226e  sbb     rsi, rsi
0x180002271  and     rsi, r14
0x180002274  jz      short loc_1800022E6
0x180002276  mov     r15, [rsi+8]
0x18000227a  test    r15, r15
0x18000227d  jz      short loc_1800022A4
0x18000227f  mov     rcx, [r15+8]
0x180002283  mov     rax, [r15]
0x180002286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000228b  mov     rbx, [r15+10h]
0x18000228f  mov     edx, 18h
0x180002294  mov     rcx, r15; Block
0x180002297  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000229c  mov     r15, rbx
0x18000229f  test    rbx, rbx
0x1800022a2  jnz     short loc_18000227F
0x1800022a4  mov     qword ptr [rsi+8], 0
0x1800022ac  mov     qword ptr [rdi+10h], 0
0x1800022b4  mov     rcx, [rdi+40h]
0x1800022b8  test    rcx, rcx
0x1800022bb  jz      short loc_1800022C9
0x1800022bd  mov     rax, [rcx]
0x1800022c0  mov     rax, [rax+10h]
0x1800022c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022c9  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800022cd  call    cs:__imp_DeleteCriticalSection
0x1800022d3  mov     dword ptr [r14], 0
0x1800022da  add     rsp, 20h
0x1800022de  pop     r15
0x1800022e0  pop     r14
0x1800022e2  pop     rdi
0x1800022e3  pop     rsi
0x1800022e4  pop     rbx
0x1800022e5  retn
0x1800022e6  mov     ecx, 0C0000005h; unsigned int
0x1800022eb  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
