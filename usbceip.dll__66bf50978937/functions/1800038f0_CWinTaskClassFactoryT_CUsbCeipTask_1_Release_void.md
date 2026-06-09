# CWinTaskClassFactoryT<CUsbCeipTask,1>::Release(void)

- ea: `0x1800038f0`
- end: `0x18000391f`
- name: `?Release@?$CWinTaskClassFactoryT@VCUsbCeipTask@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800038f0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CUsbCeipTask,1>::Release(volatile signed __int32 *a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(a1 + 2);
  if ( !v1 && a1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
  return v1;
}

```

## disassembly

```asm
0x1800038f0  push    rbx
0x1800038f2  sub     rsp, 20h
0x1800038f6  or      ebx, 0FFFFFFFFh
0x1800038f9  lock xadd [rcx+8], ebx
0x1800038fe  sub     ebx, 1
0x180003901  jnz     short loc_180003917
0x180003903  test    rcx, rcx
0x180003906  jz      short loc_180003917
0x180003908  mov     rdx, [rcx]
0x18000390b  mov     rax, [rdx+28h]
0x18000390f  lea     edx, [rbx+1]
0x180003912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003917  mov     eax, ebx
0x180003919  add     rsp, 20h
0x18000391d  pop     rbx
0x18000391e  retn
```
