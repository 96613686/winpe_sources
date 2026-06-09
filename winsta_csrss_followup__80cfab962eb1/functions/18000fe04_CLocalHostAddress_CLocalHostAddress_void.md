# CLocalHostAddress::~CLocalHostAddress(void)

- ea: `0x18000fe04`
- end: `0x18000fe2f`
- name: `??1CLocalHostAddress@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(CLocalHostAddress *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fdf0`

## callees

- `0x18000fe04`
- `0x18000fe38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fe1c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fe1c`

## pseudocode

```c
void __fastcall CLocalHostAddress::~CLocalHostAddress(CLocalHostAddress *this)
{
  CLocalHostAddress::Cleanup(this);
  if ( *((_DWORD *)this + 1) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x18000fe04  push    rbx
0x18000fe06  sub     rsp, 20h
0x18000fe0a  mov     rbx, rcx
0x18000fe0d  call    ?Cleanup@CLocalHostAddress@@AEAAXXZ; CLocalHostAddress::Cleanup(void)
0x18000fe12  cmp     dword ptr [rbx+4], 0
0x18000fe16  jz      short loc_18000FE28
0x18000fe18  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000fe1c  call    cs:__imp_DeleteCriticalSection
0x18000fe23  nop     dword ptr [rax+rax+00h]
0x18000fe28  add     rsp, 20h
0x18000fe2c  pop     rbx
0x18000fe2d  retn
```
