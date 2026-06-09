# CConsistentMapping::AcquireReadWriteAccess(void)

- ea: `0x18000f924`
- end: `0x18000f9b0`
- name: `?AcquireReadWriteAccess@CConsistentMapping@@IEAAHXZ`
- size: `140`
- prototype: `__int64 __fastcall(CConsistentMapping *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800166d0`
- `0x180016780`

## callees

- `0x18000f73c`
- `0x18000f924`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall CConsistentMapping::AcquireReadWriteAccess(CConsistentMapping *this)
{
  __int64 v2; // rbx
  __int64 result; // rax

  if ( *(_DWORD *)(*((_QWORD *)this + 1) + 8LL) == -1
    && (v2 = *((_QWORD *)this + 1),
        *(_DWORD *)(v2 + 16) == (*(unsigned int (__fastcall **)(struct IKernel32Interface *))(*(_QWORD *)g_Kernel32
                                                                                            + 624LL))(g_Kernel32)) )
  {
    if ( *(_DWORD *)(*((_QWORD *)this + 1) + 12LL) )
    {
      result = 1;
      ++*(_DWORD *)(*((_QWORD *)this + 1) + 12LL);
    }
    else
    {
      return 0;
    }
  }
  else
  {
    AcquireReadAccess((volatile int *)(*((_QWORD *)this + 1) + 8LL));
    return (**(__int64 (__fastcall ***)(CConsistentMapping *, _QWORD))this)(this, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18000f924  mov     [rsp+arg_0], rbx
0x18000f929  push    rdi
0x18000f92a  sub     rsp, 20h
0x18000f92e  mov     rax, [rcx+8]
0x18000f932  mov     rdi, rcx
0x18000f935  mov     edx, [rax+8]
0x18000f938  cmp     edx, 0FFFFFFFFh
0x18000f93b  jnz     short loc_18000F987
0x18000f93d  mov     rax, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000f944  mov     rbx, [rcx+8]
0x18000f948  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18000f94f  mov     rdx, [rax]
0x18000f952  mov     rax, [rdx+270h]
0x18000f959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f95e  mov     ecx, [rbx+10h]
0x18000f961  cmp     ecx, eax
0x18000f963  jnz     short loc_18000F987
0x18000f965  mov     rax, [rdi+8]
0x18000f969  mov     ecx, [rax+0Ch]
0x18000f96c  test    ecx, ecx
0x18000f96e  jnz     short loc_18000F974
0x18000f970  xor     eax, eax
0x18000f972  jmp     short loc_18000F9A4
0x18000f974  mov     rdx, [rdi+8]
0x18000f978  mov     eax, 1
0x18000f97d  mov     ecx, [rdx+0Ch]
0x18000f980  add     ecx, eax
0x18000f982  mov     [rdx+0Ch], ecx
0x18000f985  jmp     short loc_18000F9A4
0x18000f987  mov     rcx, [rdi+8]
0x18000f98b  add     rcx, 8; volatile int *
0x18000f98f  call    ?AcquireReadAccess@@YAXPECJ@Z; AcquireReadAccess(long volatile *)
0x18000f994  mov     rax, [rdi]
0x18000f997  xor     edx, edx
0x18000f999  mov     rcx, rdi
0x18000f99c  mov     rax, [rax]
0x18000f99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9a4  mov     rbx, [rsp+28h+arg_0]
0x18000f9a9  add     rsp, 20h
0x18000f9ad  pop     rdi
0x18000f9ae  retn
```
