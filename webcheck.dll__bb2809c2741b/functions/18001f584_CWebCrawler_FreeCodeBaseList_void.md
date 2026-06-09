# CWebCrawler::FreeCodeBaseList(void)

- ea: `0x18001f584`
- end: `0x18001f631`
- name: `?FreeCodeBaseList@CWebCrawler@@IEAAXXZ`
- size: `173`
- prototype: `void __fastcall(CWebCrawler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x1800225d8`

## callees

- `0x18001ba40`
- `0x18001f584`
- `0x18002a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001f5ce`
- `ole32!CoTaskMemFree` at `0x18001f5ce`

## pseudocode

```c
void __fastcall CWebCrawler::FreeCodeBaseList(CWebCrawler *this)
{
  __int64 v1; // rax
  int v3; // ebp
  unsigned int i; // ebx
  LPVOID *v5; // rax
  LPVOID *v6; // rsi
  void (__fastcall ***v7)(_QWORD, __int64); // rcx

  v1 = *((_QWORD *)this + 24);
  if ( v1 )
  {
    v3 = *(_DWORD *)(v1 + 12);
    for ( i = 0; (int)i < v3; ++i )
    {
      v5 = (LPVOID *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 24) + 24LL))(
                       *((_QWORD *)this + 24),
                       i);
      v6 = v5;
      if ( v5 )
      {
        if ( *v5 )
        {
          CoTaskMemFree(*v5);
          *v6 = 0;
        }
        operator delete(v6);
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 24) + 32LL))(*((_QWORD *)this + 24), i, 0);
      }
    }
    v7 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 24);
    if ( v7 )
    {
      (**v7)(v7, 1);
      *((_QWORD *)this + 24) = 0;
    }
  }
}

```

## disassembly

```asm
0x18001f584  push    rbx
0x18001f586  push    rbp
0x18001f587  push    rsi
0x18001f588  push    rdi
0x18001f589  sub     rsp, 28h
0x18001f58d  mov     rax, [rcx+0C0h]
0x18001f594  mov     rdi, rcx
0x18001f597  test    rax, rax
0x18001f59a  jz      loc_18001F628
0x18001f5a0  mov     ebp, [rax+0Ch]
0x18001f5a3  xor     ebx, ebx
0x18001f5a5  test    ebp, ebp
0x18001f5a7  jle     short loc_18001F601
0x18001f5a9  mov     rcx, [rdi+0C0h]
0x18001f5b0  mov     edx, ebx
0x18001f5b2  mov     rax, [rcx]
0x18001f5b5  mov     rax, [rax+18h]
0x18001f5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5be  mov     rsi, rax
0x18001f5c1  test    rax, rax
0x18001f5c4  jz      short loc_18001F5FB
0x18001f5c6  mov     rcx, [rax]; pv
0x18001f5c9  test    rcx, rcx
0x18001f5cc  jz      short loc_18001F5DB
0x18001f5ce  call    cs:__imp_CoTaskMemFree
0x18001f5d4  mov     qword ptr [rsi], 0
0x18001f5db  mov     rcx, rsi; lpMem
0x18001f5de  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f5e3  mov     rcx, [rdi+0C0h]
0x18001f5ea  xor     r8d, r8d
0x18001f5ed  mov     edx, ebx
0x18001f5ef  mov     rax, [rcx]
0x18001f5f2  mov     rax, [rax+20h]
0x18001f5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5fb  inc     ebx
0x18001f5fd  cmp     ebx, ebp
0x18001f5ff  jl      short loc_18001F5A9
0x18001f601  mov     rcx, [rdi+0C0h]
0x18001f608  test    rcx, rcx
0x18001f60b  jz      short loc_18001F628
0x18001f60d  mov     rax, [rcx]
0x18001f610  mov     edx, 1
0x18001f615  mov     rax, [rax]
0x18001f618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f61d  mov     qword ptr [rdi+0C0h], 0
0x18001f628  add     rsp, 28h
0x18001f62c  pop     rdi
0x18001f62d  pop     rsi
0x18001f62e  pop     rbp
0x18001f62f  pop     rbx
0x18001f630  retn
```
