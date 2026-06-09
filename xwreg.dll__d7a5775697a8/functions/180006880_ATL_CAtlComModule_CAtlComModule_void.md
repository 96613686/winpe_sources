# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180006880`
- end: `0x1800068f0`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012f20`

## callees

- `0x180006880`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800068d4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800068d4`

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
0x180006880  mov     [rsp+arg_0], rbx
0x180006885  mov     [rsp+arg_8], rsi
0x18000688a  push    rdi
0x18000688b  sub     rsp, 20h
0x18000688f  cmp     dword ptr [rcx], 0
0x180006892  mov     rbx, rcx
0x180006895  jz      short loc_1800068E0
0x180006897  mov     rdi, [rcx+10h]
0x18000689b  cmp     rdi, [rcx+18h]
0x18000689f  jnb     short loc_1800068D0
0x1800068a1  mov     rsi, [rdi]
0x1800068a4  test    rsi, rsi
0x1800068a7  jz      short loc_1800068C6
0x1800068a9  mov     rcx, [rsi+20h]
0x1800068ad  test    rcx, rcx
0x1800068b0  jz      short loc_1800068BE
0x1800068b2  mov     rax, [rcx]
0x1800068b5  mov     rax, [rax+10h]
0x1800068b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068be  mov     qword ptr [rsi+20h], 0
0x1800068c6  add     rdi, 8
0x1800068ca  cmp     rdi, [rbx+18h]
0x1800068ce  jb      short loc_1800068A1
0x1800068d0  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800068d4  call    cs:__imp_DeleteCriticalSection
0x1800068da  mov     dword ptr [rbx], 0
0x1800068e0  mov     rbx, [rsp+28h+arg_0]
0x1800068e5  mov     rsi, [rsp+28h+arg_8]
0x1800068ea  add     rsp, 20h
0x1800068ee  pop     rdi
0x1800068ef  retn
```
