# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1800157f4`
- end: `0x180015864`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021da0`

## callees

- `0x1800157f4`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015848`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015848`

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
0x1800157f4  mov     [rsp+arg_0], rbx
0x1800157f9  mov     [rsp+arg_8], rsi
0x1800157fe  push    rdi
0x1800157ff  sub     rsp, 20h
0x180015803  cmp     dword ptr [rcx], 0
0x180015806  mov     rbx, rcx
0x180015809  jz      short loc_180015854
0x18001580b  mov     rdi, [rcx+10h]
0x18001580f  cmp     rdi, [rcx+18h]
0x180015813  jnb     short loc_180015844
0x180015815  mov     rsi, [rdi]
0x180015818  test    rsi, rsi
0x18001581b  jz      short loc_18001583A
0x18001581d  mov     rcx, [rsi+20h]
0x180015821  test    rcx, rcx
0x180015824  jz      short loc_180015832
0x180015826  mov     rax, [rcx]
0x180015829  mov     rax, [rax+10h]
0x18001582d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015832  mov     qword ptr [rsi+20h], 0
0x18001583a  add     rdi, 8
0x18001583e  cmp     rdi, [rbx+18h]
0x180015842  jb      short loc_180015815
0x180015844  lea     rcx, [rbx+20h]; lpCriticalSection
0x180015848  call    cs:__imp_DeleteCriticalSection
0x18001584e  mov     dword ptr [rbx], 0
0x180015854  mov     rbx, [rsp+28h+arg_0]
0x180015859  mov     rsi, [rsp+28h+arg_8]
0x18001585e  add     rsp, 20h
0x180015862  pop     rdi
0x180015863  retn
```
