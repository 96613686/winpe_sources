# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18002089c`
- end: `0x18002090c`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800298e0`

## callees

- `0x18002089c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800208f0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800208f0`

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
0x18002089c  mov     [rsp+arg_0], rbx
0x1800208a1  mov     [rsp+arg_8], rsi
0x1800208a6  push    rdi
0x1800208a7  sub     rsp, 20h
0x1800208ab  cmp     dword ptr [rcx], 0
0x1800208ae  mov     rbx, rcx
0x1800208b1  jz      short loc_1800208FC
0x1800208b3  mov     rdi, [rcx+10h]
0x1800208b7  cmp     rdi, [rcx+18h]
0x1800208bb  jnb     short loc_1800208EC
0x1800208bd  mov     rsi, [rdi]
0x1800208c0  test    rsi, rsi
0x1800208c3  jz      short loc_1800208E2
0x1800208c5  mov     rcx, [rsi+20h]
0x1800208c9  test    rcx, rcx
0x1800208cc  jz      short loc_1800208DA
0x1800208ce  mov     rax, [rcx]
0x1800208d1  mov     rax, [rax+10h]
0x1800208d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208da  mov     qword ptr [rsi+20h], 0
0x1800208e2  add     rdi, 8
0x1800208e6  cmp     rdi, [rbx+18h]
0x1800208ea  jb      short loc_1800208BD
0x1800208ec  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800208f0  call    cs:__imp_DeleteCriticalSection
0x1800208f6  mov     dword ptr [rbx], 0
0x1800208fc  mov     rbx, [rsp+28h+arg_0]
0x180020901  mov     rsi, [rsp+28h+arg_8]
0x180020906  add     rsp, 20h
0x18002090a  pop     rdi
0x18002090b  retn
```
