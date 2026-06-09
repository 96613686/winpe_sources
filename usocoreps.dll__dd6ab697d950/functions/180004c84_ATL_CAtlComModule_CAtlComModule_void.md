# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180004c84`
- end: `0x180004cf4`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005110`

## callees

- `0x180004c84`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004cd8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004cd8`

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
0x180004c84  mov     [rsp+arg_0], rbx
0x180004c89  mov     [rsp+arg_8], rsi
0x180004c8e  push    rdi
0x180004c8f  sub     rsp, 20h
0x180004c93  cmp     dword ptr [rcx], 0
0x180004c96  mov     rbx, rcx
0x180004c99  jz      short loc_180004CE4
0x180004c9b  mov     rdi, [rcx+10h]
0x180004c9f  cmp     rdi, [rcx+18h]
0x180004ca3  jnb     short loc_180004CD4
0x180004ca5  mov     rsi, [rdi]
0x180004ca8  test    rsi, rsi
0x180004cab  jz      short loc_180004CCA
0x180004cad  mov     rcx, [rsi+20h]
0x180004cb1  test    rcx, rcx
0x180004cb4  jz      short loc_180004CC2
0x180004cb6  mov     rax, [rcx]
0x180004cb9  mov     rax, [rax+10h]
0x180004cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc2  mov     qword ptr [rsi+20h], 0
0x180004cca  add     rdi, 8
0x180004cce  cmp     rdi, [rbx+18h]
0x180004cd2  jb      short loc_180004CA5
0x180004cd4  lea     rcx, [rbx+20h]; lpCriticalSection
0x180004cd8  call    cs:__imp_DeleteCriticalSection
0x180004cde  mov     dword ptr [rbx], 0
0x180004ce4  mov     rbx, [rsp+28h+arg_0]
0x180004ce9  mov     rsi, [rsp+28h+arg_8]
0x180004cee  add     rsp, 20h
0x180004cf2  pop     rdi
0x180004cf3  retn
```
