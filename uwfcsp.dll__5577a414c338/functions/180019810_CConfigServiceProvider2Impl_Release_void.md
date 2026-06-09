# CConfigServiceProvider2Impl::Release(void)

- ea: `0x180019810`
- end: `0x18001983f`
- name: `?Release@CConfigServiceProvider2Impl@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CConfigServiceProvider2Impl *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800073f0`

## callees

- `0x180019810`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::Release(CConfigServiceProvider2Impl *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 10);
  if ( !v1 && this )
    (*(void (__fastcall **)(CConfigServiceProvider2Impl *, __int64))(*(_QWORD *)this + 40LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x180019810  push    rbx
0x180019812  sub     rsp, 20h
0x180019816  or      ebx, 0FFFFFFFFh
0x180019819  lock xadd [rcx+28h], ebx
0x18001981e  sub     ebx, 1
0x180019821  jnz     short loc_180019837
0x180019823  test    rcx, rcx
0x180019826  jz      short loc_180019837
0x180019828  mov     rdx, [rcx]
0x18001982b  mov     rax, [rdx+28h]
0x18001982f  lea     edx, [rbx+1]
0x180019832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019837  mov     eax, ebx
0x180019839  add     rsp, 20h
0x18001983d  pop     rbx
0x18001983e  retn
```
