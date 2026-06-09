# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000bbc0`
- end: `0x18000bc30`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800336d0`

## callees

- `0x18000bbc0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bc14`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bc14`

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
0x18000bbc0  mov     [rsp+arg_0], rbx
0x18000bbc5  mov     [rsp+arg_8], rsi
0x18000bbca  push    rdi
0x18000bbcb  sub     rsp, 20h
0x18000bbcf  cmp     dword ptr [rcx], 0
0x18000bbd2  mov     rbx, rcx
0x18000bbd5  jz      short loc_18000BC20
0x18000bbd7  mov     rdi, [rcx+10h]
0x18000bbdb  cmp     rdi, [rcx+18h]
0x18000bbdf  jnb     short loc_18000BC10
0x18000bbe1  mov     rsi, [rdi]
0x18000bbe4  test    rsi, rsi
0x18000bbe7  jz      short loc_18000BC06
0x18000bbe9  mov     rcx, [rsi+20h]
0x18000bbed  test    rcx, rcx
0x18000bbf0  jz      short loc_18000BBFE
0x18000bbf2  mov     rax, [rcx]
0x18000bbf5  mov     rax, [rax+10h]
0x18000bbf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbfe  mov     qword ptr [rsi+20h], 0
0x18000bc06  add     rdi, 8
0x18000bc0a  cmp     rdi, [rbx+18h]
0x18000bc0e  jb      short loc_18000BBE1
0x18000bc10  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000bc14  call    cs:__imp_DeleteCriticalSection
0x18000bc1a  mov     dword ptr [rbx], 0
0x18000bc20  mov     rbx, [rsp+28h+arg_0]
0x18000bc25  mov     rsi, [rsp+28h+arg_8]
0x18000bc2a  add     rsp, 20h
0x18000bc2e  pop     rdi
0x18000bc2f  retn
```
