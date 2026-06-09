# CExcludedExtsPolicy::~CExcludedExtsPolicy(void)

- ea: `0x180012470`
- end: `0x1800124dc`
- name: `??1CExcludedExtsPolicy@@UEAA@XZ`
- size: `108`
- prototype: `void __fastcall(CExcludedExtsPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012720`

## callees

- `0x180012470`
- `0x18001ac7c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001249c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800124bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001249c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800124bc`

## pseudocode

```c
void __fastcall CExcludedExtsPolicy::~CExcludedExtsPolicy(CExcludedExtsPolicy *this)
{
  __int64 i; // rbx
  LPVOID *v3; // rsi

  *(_QWORD *)this = &CExcludedExtsPolicy::`vftable';
  for ( i = 0; i != 4; ++i )
  {
    v3 = (LPVOID *)*((_QWORD *)this + i + 2);
    if ( v3 )
    {
      CoTaskMemFree(v3[4]);
      operator delete(v3, 0x28u);
    }
  }
  CoTaskMemFree(*((LPVOID *)this + 10));
  *(_QWORD *)this = &CPolicyHandlerBase::`vftable';
}

```

## disassembly

```asm
0x180012470  mov     [rsp+arg_0], rbx
0x180012475  mov     [rsp+arg_8], rsi
0x18001247a  push    rdi
0x18001247b  sub     rsp, 20h
0x18001247f  lea     rax, ??_7CExcludedExtsPolicy@@6B@; const CExcludedExtsPolicy::`vftable'
0x180012486  mov     rdi, rcx
0x180012489  mov     [rcx], rax
0x18001248c  xor     ebx, ebx
0x18001248e  mov     rsi, [rdi+rbx*8+10h]
0x180012493  test    rsi, rsi
0x180012496  jz      short loc_1800124AF
0x180012498  mov     rcx, [rsi+20h]; pv
0x18001249c  call    cs:__imp_CoTaskMemFree
0x1800124a2  mov     edx, 28h ; '('; unsigned __int64
0x1800124a7  mov     rcx, rsi; void *
0x1800124aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800124af  inc     rbx
0x1800124b2  cmp     rbx, 4
0x1800124b6  jnz     short loc_18001248E
0x1800124b8  mov     rcx, [rdi+50h]; pv
0x1800124bc  call    cs:__imp_CoTaskMemFree
0x1800124c2  mov     rbx, [rsp+28h+arg_0]
0x1800124c7  lea     rax, ??_7CPolicyHandlerBase@@6B@; const CPolicyHandlerBase::`vftable'
0x1800124ce  mov     rsi, [rsp+28h+arg_8]
0x1800124d3  mov     [rdi], rax
0x1800124d6  add     rsp, 20h
0x1800124da  pop     rdi
0x1800124db  retn
```
