# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000202c`
- end: `0x18000209c`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800036a0`

## callees

- `0x18000202c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002080`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002080`

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
0x18000202c  mov     [rsp+arg_0], rbx
0x180002031  mov     [rsp+arg_8], rsi
0x180002036  push    rdi
0x180002037  sub     rsp, 20h
0x18000203b  cmp     dword ptr [rcx], 0
0x18000203e  mov     rbx, rcx
0x180002041  jz      short loc_18000208C
0x180002043  mov     rdi, [rcx+10h]
0x180002047  cmp     rdi, [rcx+18h]
0x18000204b  jnb     short loc_18000207C
0x18000204d  mov     rsi, [rdi]
0x180002050  test    rsi, rsi
0x180002053  jz      short loc_180002072
0x180002055  mov     rcx, [rsi+20h]
0x180002059  test    rcx, rcx
0x18000205c  jz      short loc_18000206A
0x18000205e  mov     rax, [rcx]
0x180002061  mov     rax, [rax+10h]
0x180002065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000206a  mov     qword ptr [rsi+20h], 0
0x180002072  add     rdi, 8
0x180002076  cmp     rdi, [rbx+18h]
0x18000207a  jb      short loc_18000204D
0x18000207c  lea     rcx, [rbx+20h]; lpCriticalSection
0x180002080  call    cs:__imp_DeleteCriticalSection
0x180002086  mov     dword ptr [rbx], 0
0x18000208c  mov     rbx, [rsp+28h+arg_0]
0x180002091  mov     rsi, [rsp+28h+arg_8]
0x180002096  add     rsp, 20h
0x18000209a  pop     rdi
0x18000209b  retn
```
