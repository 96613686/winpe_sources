# ATL::CRegObject::~CRegObject(void)

- ea: `0x180001f38`
- end: `0x180001fa2`
- name: `??1CRegObject@ATL@@QEAA@XZ`
- size: `106`
- prototype: `void __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x1800045a0`
- `0x18000516b`

## callees

- `0x180001494`
- `0x180001f38`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001f9b`
- `ole32!CoTaskMemFree` at `0x180001f5f`
- `ole32!CoTaskMemFree` at `0x180001f68`
- `ole32!CoTaskMemFree` at `0x180001f5f`
- `ole32!CoTaskMemFree` at `0x180001f68`

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
0x180001f38  mov     [rsp+arg_0], rbx
0x180001f3d  mov     [rsp+arg_8], rsi
0x180001f42  push    rdi
0x180001f43  sub     rsp, 20h
0x180001f47  xor     esi, esi
0x180001f49  mov     rdi, rcx
0x180001f4c  cmp     [rcx+8], esi
0x180001f4f  jle     short loc_180001F82
0x180001f51  mov     rax, [rdi]
0x180001f54  movsxd  rdx, esi
0x180001f57  mov     rbx, [rax+rdx*8]
0x180001f5b  mov     rcx, [rbx+8]; pv
0x180001f5f  call    cs:__imp_CoTaskMemFree
0x180001f65  mov     rcx, [rbx]; pv
0x180001f68  call    cs:__imp_CoTaskMemFree
0x180001f6e  mov     edx, 10h; unsigned __int64
0x180001f73  mov     rcx, rbx; void *
0x180001f76  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180001f7b  inc     esi
0x180001f7d  cmp     esi, [rdi+8]
0x180001f80  jl      short loc_180001F51
0x180001f82  mov     dword ptr [rdi+8], 0
0x180001f89  mov     rcx, [rdi]
0x180001f8c  mov     rbx, [rsp+28h+arg_0]
0x180001f91  mov     rsi, [rsp+28h+arg_8]
0x180001f96  add     rsp, 20h
0x180001f9a  pop     rdi
0x180001f9b  jmp     cs:__imp_free
```
