# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180008344`
- end: `0x1800083bb`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180033d00`

## callees

- `0x180008344`
- `0x180034010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008398`
- `KERNEL32!DeleteCriticalSection` at `0x180008398`

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
0x180008344  mov     [rsp+arg_0], rbx
0x180008349  mov     [rsp+arg_8], rsi
0x18000834e  push    rdi
0x18000834f  sub     rsp, 20h
0x180008353  cmp     dword ptr [rcx], 0
0x180008356  mov     rbx, rcx
0x180008359  jz      short loc_1800083AA
0x18000835b  mov     rdi, [rcx+10h]
0x18000835f  cmp     rdi, [rcx+18h]
0x180008363  jnb     short loc_180008394
0x180008365  mov     rsi, [rdi]
0x180008368  test    rsi, rsi
0x18000836b  jz      short loc_18000838A
0x18000836d  mov     rcx, [rsi+20h]
0x180008371  test    rcx, rcx
0x180008374  jz      short loc_180008382
0x180008376  mov     rax, [rcx]
0x180008379  mov     rax, [rax+10h]
0x18000837d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008382  mov     qword ptr [rsi+20h], 0
0x18000838a  add     rdi, 8
0x18000838e  cmp     rdi, [rbx+18h]
0x180008392  jb      short loc_180008365
0x180008394  lea     rcx, [rbx+20h]; lpCriticalSection
0x180008398  call    cs:__imp_DeleteCriticalSection
0x18000839f  nop     dword ptr [rax+rax+00h]
0x1800083a4  mov     dword ptr [rbx], 0
0x1800083aa  mov     rbx, [rsp+28h+arg_0]
0x1800083af  mov     rsi, [rsp+28h+arg_8]
0x1800083b4  add     rsp, 20h
0x1800083b8  pop     rdi
0x1800083b9  retn
```
