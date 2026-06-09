# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180042590`
- end: `0x180042600`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800624d0`

## callees

- `0x180042590`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800425e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800425e4`

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
0x180042590  mov     [rsp+arg_0], rbx
0x180042595  mov     [rsp+arg_8], rsi
0x18004259a  push    rdi
0x18004259b  sub     rsp, 20h
0x18004259f  cmp     dword ptr [rcx], 0
0x1800425a2  mov     rbx, rcx
0x1800425a5  jz      short loc_1800425F0
0x1800425a7  mov     rdi, [rcx+10h]
0x1800425ab  cmp     rdi, [rcx+18h]
0x1800425af  jnb     short loc_1800425E0
0x1800425b1  mov     rsi, [rdi]
0x1800425b4  test    rsi, rsi
0x1800425b7  jz      short loc_1800425D6
0x1800425b9  mov     rcx, [rsi+20h]
0x1800425bd  test    rcx, rcx
0x1800425c0  jz      short loc_1800425CE
0x1800425c2  mov     rax, [rcx]
0x1800425c5  mov     rax, [rax+10h]
0x1800425c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425ce  mov     qword ptr [rsi+20h], 0
0x1800425d6  add     rdi, 8
0x1800425da  cmp     rdi, [rbx+18h]
0x1800425de  jb      short loc_1800425B1
0x1800425e0  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800425e4  call    cs:__imp_DeleteCriticalSection
0x1800425ea  mov     dword ptr [rbx], 0
0x1800425f0  mov     rbx, [rsp+28h+arg_0]
0x1800425f5  mov     rsi, [rsp+28h+arg_8]
0x1800425fa  add     rsp, 20h
0x1800425fe  pop     rdi
0x1800425ff  retn
```
