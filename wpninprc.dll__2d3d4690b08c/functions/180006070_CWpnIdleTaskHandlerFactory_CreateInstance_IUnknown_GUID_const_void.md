# CWpnIdleTaskHandlerFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180006070`
- end: `0x18000611d`
- name: `?CreateInstance@CWpnIdleTaskHandlerFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `173`
- prototype: `__int64 __fastcall(CWpnIdleTaskHandlerFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180001918`
- `0x180006070`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall CWpnIdleTaskHandlerFactory::CreateInstance(
        CWpnIdleTaskHandlerFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // edi
  _DWORD *v7; // rbx

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v7 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v7 )
      {
        v7[2] = 1;
        *(_QWORD *)v7 = &CWpnIdleTaskHandler::`vftable';
        _InterlockedIncrement(&g_Count);
        v6 = (**(__int64 (__fastcall ***)(_DWORD *, const struct _GUID *, void **))v7)(v7, a3, a4);
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180006070  mov     [rsp+arg_0], rbx
0x180006075  mov     [rsp+arg_8], rsi
0x18000607a  push    rdi
0x18000607b  sub     rsp, 20h
0x18000607f  mov     rdi, r9
0x180006082  mov     rsi, r8
0x180006085  test    r9, r9
0x180006088  jnz     short loc_180006091
0x18000608a  mov     edi, 80070057h
0x18000608f  jmp     short loc_18000610B
0x180006091  mov     qword ptr [r9], 0
0x180006098  test    rdx, rdx
0x18000609b  jz      short loc_1800060A4
0x18000609d  mov     edi, 80040110h
0x1800060a2  jmp     short loc_18000610B
0x1800060a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800060ab  mov     ecx, 10h; unsigned __int64
0x1800060b0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800060b5  mov     [rsp+28h+arg_18], rax
0x1800060ba  mov     rbx, rax
0x1800060bd  test    rax, rax
0x1800060c0  jz      short loc_180006106
0x1800060c2  lea     rax, ??_7CWpnIdleTaskHandler@@6B@; const CWpnIdleTaskHandler::`vftable'
0x1800060c9  mov     dword ptr [rbx+8], 1
0x1800060d0  mov     [rbx], rax
0x1800060d3  lock inc cs:?g_Count@@3JA; long g_Count
0x1800060da  test    rbx, rbx
0x1800060dd  jz      short loc_180006106
0x1800060df  mov     rax, [rbx]
0x1800060e2  mov     r8, rdi
0x1800060e5  mov     rdx, rsi
0x1800060e8  mov     rcx, rbx
0x1800060eb  mov     rax, [rax]
0x1800060ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060f3  mov     rdx, [rbx]
0x1800060f6  mov     edi, eax
0x1800060f8  mov     rcx, rbx
0x1800060fb  mov     rax, [rdx+10h]
0x1800060ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006104  jmp     short loc_18000610B
0x180006106  mov     edi, 8007000Eh
0x18000610b  mov     rbx, [rsp+28h+arg_0]
0x180006110  mov     eax, edi
0x180006112  mov     rsi, [rsp+28h+arg_8]
0x180006117  add     rsp, 20h
0x18000611b  pop     rdi
0x18000611c  retn
```
