# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1800147f4`
- end: `0x180014864`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c580`

## callees

- `0x1800147f4`
- `0x18001d010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180014848`
- `KERNEL32!DeleteCriticalSection` at `0x180014848`

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
0x1800147f4  mov     [rsp+arg_0], rbx
0x1800147f9  mov     [rsp+arg_8], rsi
0x1800147fe  push    rdi
0x1800147ff  sub     rsp, 20h
0x180014803  cmp     dword ptr [rcx], 0
0x180014806  mov     rbx, rcx
0x180014809  jz      short loc_180014854
0x18001480b  mov     rdi, [rcx+10h]
0x18001480f  cmp     rdi, [rcx+18h]
0x180014813  jnb     short loc_180014844
0x180014815  mov     rsi, [rdi]
0x180014818  test    rsi, rsi
0x18001481b  jz      short loc_18001483A
0x18001481d  mov     rcx, [rsi+20h]
0x180014821  test    rcx, rcx
0x180014824  jz      short loc_180014832
0x180014826  mov     rax, [rcx]
0x180014829  mov     rax, [rax+10h]
0x18001482d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014832  mov     qword ptr [rsi+20h], 0
0x18001483a  add     rdi, 8
0x18001483e  cmp     rdi, [rbx+18h]
0x180014842  jb      short loc_180014815
0x180014844  lea     rcx, [rbx+20h]; lpCriticalSection
0x180014848  call    cs:__imp_DeleteCriticalSection
0x18001484e  mov     dword ptr [rbx], 0
0x180014854  mov     rbx, [rsp+28h+arg_0]
0x180014859  mov     rsi, [rsp+28h+arg_8]
0x18001485e  add     rsp, 20h
0x180014862  pop     rdi
0x180014863  retn
```
