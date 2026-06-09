# CWpnIdleTaskHandlerFactory::QueryInterface(_GUID const &,void * *)

- ea: `0x180006150`
- end: `0x1800061bb`
- name: `?QueryInterface@CWpnIdleTaskHandlerFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(CWpnIdleTaskHandlerFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180006150`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall CWpnIdleTaskHandlerFactory::QueryInterface(
        CWpnIdleTaskHandlerFactory *this,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int v3; // ebx

  if ( a3 )
  {
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000001_0000_0000_c000_000000000046.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_00000001_0000_0000_c000_000000000046.Data4
      || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
    {
      *a3 = this;
      v3 = 0;
      (*(void (__fastcall **)(CWpnIdleTaskHandlerFactory *))(*(_QWORD *)this + 8LL))(this);
    }
    else
    {
      *a3 = 0;
      return (unsigned int)-2147467262;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180006150  push    rbx
0x180006152  sub     rsp, 20h
0x180006156  test    r8, r8
0x180006159  jnz     short loc_180006162
0x18000615b  mov     ebx, 80070057h
0x180006160  jmp     short loc_1800061B3
0x180006162  mov     rax, [rdx]
0x180006165  cmp     rax, qword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data1
0x18000616c  jnz     short loc_18000617B
0x18000616e  mov     rax, [rdx+8]
0x180006172  cmp     rax, qword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data4
0x180006179  jz      short loc_180006194
0x18000617b  mov     rax, [rdx]
0x18000617e  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180006185  jnz     short loc_1800061A7
0x180006187  mov     rax, [rdx+8]
0x18000618b  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180006192  jnz     short loc_1800061A7
0x180006194  mov     [r8], rcx
0x180006197  xor     ebx, ebx
0x180006199  mov     rax, [rcx]
0x18000619c  mov     rax, [rax+8]
0x1800061a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061a5  jmp     short loc_1800061B3
0x1800061a7  mov     qword ptr [r8], 0
0x1800061ae  mov     ebx, 80004002h
0x1800061b3  mov     eax, ebx
0x1800061b5  add     rsp, 20h
0x1800061b9  pop     rbx
0x1800061ba  retn
```
