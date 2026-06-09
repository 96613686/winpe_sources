# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000f820`
- end: `0x18000f890`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180030b40`

## callees

- `0x18000f820`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f874`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f874`

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
0x18000f820  mov     [rsp+arg_0], rbx
0x18000f825  mov     [rsp+arg_8], rsi
0x18000f82a  push    rdi
0x18000f82b  sub     rsp, 20h
0x18000f82f  cmp     dword ptr [rcx], 0
0x18000f832  mov     rbx, rcx
0x18000f835  jz      short loc_18000F880
0x18000f837  mov     rdi, [rcx+10h]
0x18000f83b  cmp     rdi, [rcx+18h]
0x18000f83f  jnb     short loc_18000F870
0x18000f841  mov     rsi, [rdi]
0x18000f844  test    rsi, rsi
0x18000f847  jz      short loc_18000F866
0x18000f849  mov     rcx, [rsi+20h]
0x18000f84d  test    rcx, rcx
0x18000f850  jz      short loc_18000F85E
0x18000f852  mov     rax, [rcx]
0x18000f855  mov     rax, [rax+10h]
0x18000f859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f85e  mov     qword ptr [rsi+20h], 0
0x18000f866  add     rdi, 8
0x18000f86a  cmp     rdi, [rbx+18h]
0x18000f86e  jb      short loc_18000F841
0x18000f870  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000f874  call    cs:__imp_DeleteCriticalSection
0x18000f87a  mov     dword ptr [rbx], 0
0x18000f880  mov     rbx, [rsp+28h+arg_0]
0x18000f885  mov     rsi, [rsp+28h+arg_8]
0x18000f88a  add     rsp, 20h
0x18000f88e  pop     rdi
0x18000f88f  retn
```
