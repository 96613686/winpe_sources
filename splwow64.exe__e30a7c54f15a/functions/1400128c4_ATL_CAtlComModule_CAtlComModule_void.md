# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1400128c4`
- end: `0x140012934`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140015840`

## callees

- `0x1400128c4`
- `0x140016010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140012918`
- `KERNEL32!DeleteCriticalSection` at `0x140012918`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::~CAtlComModule(ATL::CAtlComModule *this)
{
  __int64 *i; // rdi
  __int64 v3; // rsi
  __int64 v4; // rcx

  if ( *(_DWORD *)this )
  {
    for ( i = (__int64 *)*((_QWORD *)this + 2); (unsigned __int64)i < *((_QWORD *)this + 3); ++i )
    {
      v3 = *i;
      if ( *i )
      {
        v4 = *(_QWORD *)(v3 + 32);
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        *(_QWORD *)(v3 + 32) = 0;
      }
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1400128c4  mov     [rsp+arg_0], rbx
0x1400128c9  mov     [rsp+arg_8], rsi
0x1400128ce  push    rdi
0x1400128cf  sub     rsp, 20h
0x1400128d3  cmp     dword ptr [rcx], 0
0x1400128d6  mov     rbx, rcx
0x1400128d9  jz      short loc_140012924
0x1400128db  mov     rdi, [rcx+10h]
0x1400128df  cmp     rdi, [rcx+18h]
0x1400128e3  jnb     short loc_140012914
0x1400128e5  mov     rsi, [rdi]
0x1400128e8  test    rsi, rsi
0x1400128eb  jz      short loc_14001290A
0x1400128ed  mov     rcx, [rsi+20h]
0x1400128f1  test    rcx, rcx
0x1400128f4  jz      short loc_140012902
0x1400128f6  mov     rax, [rcx]
0x1400128f9  mov     rax, [rax+10h]
0x1400128fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012902  mov     qword ptr [rsi+20h], 0
0x14001290a  add     rdi, 8
0x14001290e  cmp     rdi, [rbx+18h]
0x140012912  jb      short loc_1400128E5
0x140012914  lea     rcx, [rbx+20h]; lpCriticalSection
0x140012918  call    cs:__imp_DeleteCriticalSection
0x14001291e  mov     dword ptr [rbx], 0
0x140012924  mov     rbx, [rsp+28h+arg_0]
0x140012929  mov     rsi, [rsp+28h+arg_8]
0x14001292e  add     rsp, 20h
0x140012932  pop     rdi
0x140012933  retn
```
