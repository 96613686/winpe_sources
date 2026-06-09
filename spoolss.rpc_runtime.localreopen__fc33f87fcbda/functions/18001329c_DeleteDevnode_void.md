# DeleteDevnode(void *)

- ea: `0x18001329c`
- end: `0x180013300`
- name: `?DeleteDevnode@@YAJPEAX@Z`
- size: `100`
- prototype: `__int64 __fastcall(DeviceObject *this)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18001285c`
- `0x18001346c`
- `0x180013c20`

## callees

- `0x180001d00`
- `0x180001e60`
- `0x18001329c`
- `0x18001389c`
- `0x1800139b0`
- `0x1800154bc`

## pseudocode

```c
__int64 __fastcall DeleteDevnode(DeviceObject *this)
{
  unsigned int v2; // ebx
  NCoreLibrary *v3; // rcx
  HANDLE v4; // rsi

  if ( this == (DeviceObject *)-1LL )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v4 = RevertToPrinterSelf();
    if ( !v4 )
      return (unsigned int)NCoreLibrary::GetLastErrorAsFailHR(v3);
    v2 = 0;
    DeviceObject::Uninstall(this);
    NCoreLibrary::TReferenceCount::Release(this);
    if ( !ImpersonatePrinterClient(v4) )
      return (unsigned int)NCoreLibrary::GetLastErrorAsFailHR(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x18001329c  mov     [rsp+arg_0], rbx
0x1800132a1  mov     [rsp+arg_8], rsi
0x1800132a6  push    rdi
0x1800132a7  sub     rsp, 20h
0x1800132ab  mov     rdi, rcx
0x1800132ae  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800132b2  jnz     short loc_1800132BB
0x1800132b4  mov     ebx, 80070057h
0x1800132b9  jmp     short loc_1800132ED
0x1800132bb  call    RevertToPrinterSelf
0x1800132c0  mov     rsi, rax
0x1800132c3  test    rax, rax
0x1800132c6  jz      short loc_1800132E6
0x1800132c8  mov     rcx, rdi; this
0x1800132cb  xor     ebx, ebx
0x1800132cd  call    ?Uninstall@DeviceObject@@QEAAJXZ; DeviceObject::Uninstall(void)
0x1800132d2  mov     rcx, rdi; this
0x1800132d5  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x1800132da  mov     rcx, rsi; hToken
0x1800132dd  call    ImpersonatePrinterClient
0x1800132e2  test    eax, eax
0x1800132e4  jnz     short loc_1800132ED
0x1800132e6  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800132eb  mov     ebx, eax
0x1800132ed  mov     rsi, [rsp+28h+arg_8]
0x1800132f2  mov     eax, ebx
0x1800132f4  mov     rbx, [rsp+28h+arg_0]
0x1800132f9  add     rsp, 20h
0x1800132fd  pop     rdi
0x1800132fe  retn
```
