# CCSPNodeImpl::Initialize(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *)

- ea: `0x180019b70`
- end: `0x180019be4`
- name: `?Initialize@CCSPNodeImpl@@UEAAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@@Z`
- size: `116`
- prototype: `__int64 __fastcall(CCSPNodeImpl *this, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180019b70`
- `0x18001b010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180019bc5`
- `msvcrt!memcpy_s` at `0x180019bc5`

## pseudocode

```c
__int64 __fastcall CCSPNodeImpl::Initialize(
        CCSPNodeImpl *this,
        struct CConfigServiceProvider2Impl *a2,
        struct IConfigManager2URI *a3,
        const struct CSP_NODE_DATA *a4)
{
  unsigned int v6; // edi

  if ( *((_OWORD *)this + 1) == 0 )
  {
    v6 = 0;
    *((_QWORD *)this + 2) = a2;
    if ( a3 )
    {
      *((_QWORD *)this + 3) = a3;
      (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)a3 + 8LL))(a3);
    }
    if ( a4 )
      memcpy_s((char *)this + 32, 0x20u, a4, 0x20u);
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return v6;
}

```

## disassembly

```asm
0x180019b70  mov     [rsp+arg_0], rbx
0x180019b75  mov     [rsp+arg_8], rsi
0x180019b7a  push    rdi
0x180019b7b  sub     rsp, 20h
0x180019b7f  cmp     qword ptr [rcx+10h], 0
0x180019b84  mov     rsi, r9
0x180019b87  mov     rbx, rcx
0x180019b8a  jnz     short loc_180019BCD
0x180019b8c  cmp     qword ptr [rcx+18h], 0
0x180019b91  jnz     short loc_180019BCD
0x180019b93  xor     edi, edi
0x180019b95  mov     [rcx+10h], rdx
0x180019b99  test    r8, r8
0x180019b9c  jz      short loc_180019BB1
0x180019b9e  mov     [rcx+18h], r8
0x180019ba2  mov     rcx, r8
0x180019ba5  mov     rax, [r8]
0x180019ba8  mov     rax, [rax+8]
0x180019bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bb1  test    rsi, rsi
0x180019bb4  jz      short loc_180019BD2
0x180019bb6  mov     edx, 20h ; ' '; DestinationSize
0x180019bbb  lea     rcx, [rbx+20h]; Destination
0x180019bbf  mov     r9d, edx; SourceSize
0x180019bc2  mov     r8, rsi; Source
0x180019bc5  call    cs:__imp_memcpy_s
0x180019bcb  jmp     short loc_180019BD2
0x180019bcd  mov     edi, 8000FFFFh
0x180019bd2  mov     rbx, [rsp+28h+arg_0]
0x180019bd7  mov     eax, edi
0x180019bd9  mov     rsi, [rsp+28h+arg_8]
0x180019bde  add     rsp, 20h
0x180019be2  pop     rdi
0x180019be3  retn
```
