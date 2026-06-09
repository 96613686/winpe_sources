# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180013a78`
- end: `0x180013ae8`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014710`

## callees

- `0x180013a78`
- `0x180015010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180013acc`
- `KERNEL32!DeleteCriticalSection` at `0x180013acc`

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
0x180013a78  mov     [rsp+arg_0], rbx
0x180013a7d  mov     [rsp+arg_8], rsi
0x180013a82  push    rdi
0x180013a83  sub     rsp, 20h
0x180013a87  cmp     dword ptr [rcx], 0
0x180013a8a  mov     rbx, rcx
0x180013a8d  jz      short loc_180013AD8
0x180013a8f  mov     rdi, [rcx+10h]
0x180013a93  cmp     rdi, [rcx+18h]
0x180013a97  jnb     short loc_180013AC8
0x180013a99  mov     rsi, [rdi]
0x180013a9c  test    rsi, rsi
0x180013a9f  jz      short loc_180013ABE
0x180013aa1  mov     rcx, [rsi+20h]
0x180013aa5  test    rcx, rcx
0x180013aa8  jz      short loc_180013AB6
0x180013aaa  mov     rax, [rcx]
0x180013aad  mov     rax, [rax+10h]
0x180013ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ab6  mov     qword ptr [rsi+20h], 0
0x180013abe  add     rdi, 8
0x180013ac2  cmp     rdi, [rbx+18h]
0x180013ac6  jb      short loc_180013A99
0x180013ac8  lea     rcx, [rbx+20h]; lpCriticalSection
0x180013acc  call    cs:__imp_DeleteCriticalSection
0x180013ad2  mov     dword ptr [rbx], 0
0x180013ad8  mov     rbx, [rsp+28h+arg_0]
0x180013add  mov     rsi, [rsp+28h+arg_8]
0x180013ae2  add     rsp, 20h
0x180013ae6  pop     rdi
0x180013ae7  retn
```
