# ATL::CRegObject::~CRegObject(void)

- ea: `0x140009c24`
- end: `0x140009c8e`
- name: `??1CRegObject@ATL@@QEAA@XZ`
- size: `106`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x14000c860`

## callees

- `0x140001008`
- `0x140009c24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140009c87`
- `ole32!CoTaskMemFree` at `0x140009c4b`
- `ole32!CoTaskMemFree` at `0x140009c54`
- `ole32!CoTaskMemFree` at `0x140009c4b`
- `ole32!CoTaskMemFree` at `0x140009c54`

## pseudocode

```c
void __fastcall ATL::CRegObject::~CRegObject(ATL::CRegObject *this)
{
  int i; // esi
  LPVOID *v3; // rbx

  for ( i = 0; i < *((_DWORD *)this + 2); ++i )
  {
    v3 = *(LPVOID **)(*(_QWORD *)this + 8LL * i);
    CoTaskMemFree(v3[1]);
    CoTaskMemFree(*v3);
    operator delete(v3, 0x10u);
  }
  *((_DWORD *)this + 2) = 0;
  free(*(void **)this);
}

```

## disassembly

```asm
0x140009c24  mov     [rsp+arg_0], rbx
0x140009c29  mov     [rsp+arg_8], rsi
0x140009c2e  push    rdi
0x140009c2f  sub     rsp, 20h
0x140009c33  xor     esi, esi
0x140009c35  mov     rdi, rcx
0x140009c38  cmp     [rcx+8], esi
0x140009c3b  jle     short loc_140009C6E
0x140009c3d  mov     rax, [rdi]
0x140009c40  movsxd  rdx, esi
0x140009c43  mov     rbx, [rax+rdx*8]
0x140009c47  mov     rcx, [rbx+8]; pv
0x140009c4b  call    cs:__imp_CoTaskMemFree
0x140009c51  mov     rcx, [rbx]; pv
0x140009c54  call    cs:__imp_CoTaskMemFree
0x140009c5a  mov     edx, 10h; unsigned __int64
0x140009c5f  mov     rcx, rbx; void *
0x140009c62  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009c67  inc     esi
0x140009c69  cmp     esi, [rdi+8]
0x140009c6c  jl      short loc_140009C3D
0x140009c6e  mov     dword ptr [rdi+8], 0
0x140009c75  mov     rcx, [rdi]
0x140009c78  mov     rbx, [rsp+28h+arg_0]
0x140009c7d  mov     rsi, [rsp+28h+arg_8]
0x140009c82  add     rsp, 20h
0x140009c86  pop     rdi
0x140009c87  jmp     cs:__imp_free
```
