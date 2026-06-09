# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x1800079d4`
- end: `0x180007aa8`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `212`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007ab0`
- `0x18000cdb0`

## callees

- `0x1800015d4`
- `0x180005404`
- `0x1800079d4`
- `0x18000d010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007a6e`
- `KERNEL32!DeleteCriticalSection` at `0x180007a6e`

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
        JUMPOUT(0x180007AA7LL);
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
0x1800079d4  mov     rax, rsp
0x1800079d7  mov     [rax+8], rbx
0x1800079db  mov     [rax+10h], rsi
0x1800079df  mov     [rax+18h], rdi
0x1800079e3  mov     [rax+20h], r14
0x1800079e7  push    r15
0x1800079e9  sub     rsp, 20h
0x1800079ed  lea     r14, [rcx+8]
0x1800079f1  mov     rdi, rcx
0x1800079f4  cmp     dword ptr [r14], 0
0x1800079f8  jz      loc_180007A81
0x1800079fe  cmp     qword ptr [rcx+10h], 0
0x180007a03  jz      short loc_180007A55
0x180007a05  mov     rax, rcx
0x180007a08  neg     rax
0x180007a0b  sbb     rsi, rsi
0x180007a0e  and     rsi, r14
0x180007a11  jz      loc_180007A9D
0x180007a17  mov     r15, [rsi+8]
0x180007a1b  test    r15, r15
0x180007a1e  jz      short loc_180007A45
0x180007a20  mov     rcx, [r15+8]
0x180007a24  mov     rax, [r15]
0x180007a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a2c  mov     rbx, [r15+10h]
0x180007a30  mov     edx, 18h
0x180007a35  mov     rcx, r15; Block
0x180007a38  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007a3d  mov     r15, rbx
0x180007a40  test    rbx, rbx
0x180007a43  jnz     short loc_180007A20
0x180007a45  mov     qword ptr [rsi+8], 0
0x180007a4d  mov     qword ptr [rdi+10h], 0
0x180007a55  mov     rcx, [rdi+40h]
0x180007a59  test    rcx, rcx
0x180007a5c  jz      short loc_180007A6A
0x180007a5e  mov     rax, [rcx]
0x180007a61  mov     rax, [rax+10h]
0x180007a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a6a  lea     rcx, [rdi+18h]; lpCriticalSection
0x180007a6e  call    cs:__imp_DeleteCriticalSection
0x180007a75  nop     dword ptr [rax+rax+00h]
0x180007a7a  mov     dword ptr [r14], 0
0x180007a81  mov     rbx, [rsp+28h+arg_0]
0x180007a86  mov     rsi, [rsp+28h+arg_8]
0x180007a8b  mov     rdi, [rsp+28h+arg_10]
0x180007a90  mov     r14, [rsp+28h+arg_18]
0x180007a95  add     rsp, 20h
0x180007a99  pop     r15
0x180007a9b  retn
0x180007a9d  mov     ecx, 0C0000005h; unsigned int
0x180007aa2  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
