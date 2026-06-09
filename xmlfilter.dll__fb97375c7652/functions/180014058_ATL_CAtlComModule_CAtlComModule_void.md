# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180014058`
- end: `0x1800140c8`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016250`

## callees

- `0x180014058`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800140ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800140ac`

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
0x180014058  mov     [rsp+arg_0], rbx
0x18001405d  mov     [rsp+arg_8], rsi
0x180014062  push    rdi
0x180014063  sub     rsp, 20h
0x180014067  cmp     dword ptr [rcx], 0
0x18001406a  mov     rbx, rcx
0x18001406d  jz      short loc_1800140B8
0x18001406f  mov     rdi, [rcx+10h]
0x180014073  cmp     rdi, [rcx+18h]
0x180014077  jnb     short loc_1800140A8
0x180014079  mov     rsi, [rdi]
0x18001407c  test    rsi, rsi
0x18001407f  jz      short loc_18001409E
0x180014081  mov     rcx, [rsi+20h]
0x180014085  test    rcx, rcx
0x180014088  jz      short loc_180014096
0x18001408a  mov     rax, [rcx]
0x18001408d  mov     rax, [rax+10h]
0x180014091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014096  mov     qword ptr [rsi+20h], 0
0x18001409e  add     rdi, 8
0x1800140a2  cmp     rdi, [rbx+18h]
0x1800140a6  jb      short loc_180014079
0x1800140a8  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800140ac  call    cs:__imp_DeleteCriticalSection
0x1800140b2  mov     dword ptr [rbx], 0
0x1800140b8  mov     rbx, [rsp+28h+arg_0]
0x1800140bd  mov     rsi, [rsp+28h+arg_8]
0x1800140c2  add     rsp, 20h
0x1800140c6  pop     rdi
0x1800140c7  retn
```
