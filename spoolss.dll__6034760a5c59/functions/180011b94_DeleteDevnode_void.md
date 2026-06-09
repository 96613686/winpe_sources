# DeleteDevnode(void *)

- ea: `0x180011b94`
- end: `0x180011bf7`
- name: `?DeleteDevnode@@YAJPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(DeviceObject *this)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800111f0`
- `0x180011d48`
- `0x180012500`

## callees

- `0x180001cd0`
- `0x180001e00`
- `0x180011b94`
- `0x180012130`
- `0x180012234`
- `0x180013c58`

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
0x180011b94  mov     [rsp+arg_0], rbx
0x180011b99  mov     [rsp+arg_8], rsi
0x180011b9e  push    rdi
0x180011b9f  sub     rsp, 20h
0x180011ba3  mov     rdi, rcx
0x180011ba6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011baa  jnz     short loc_180011BB3
0x180011bac  mov     ebx, 80070057h
0x180011bb1  jmp     short loc_180011BE5
0x180011bb3  call    RevertToPrinterSelf
0x180011bb8  mov     rsi, rax
0x180011bbb  test    rax, rax
0x180011bbe  jz      short loc_180011BDE
0x180011bc0  mov     rcx, rdi; this
0x180011bc3  xor     ebx, ebx
0x180011bc5  call    ?Uninstall@DeviceObject@@QEAAJXZ; DeviceObject::Uninstall(void)
0x180011bca  mov     rcx, rdi; this
0x180011bcd  call    ?Release@TReferenceCount@NCoreLibrary@@QEBAJXZ; NCoreLibrary::TReferenceCount::Release(void)
0x180011bd2  mov     rcx, rsi; hToken
0x180011bd5  call    ImpersonatePrinterClient
0x180011bda  test    eax, eax
0x180011bdc  jnz     short loc_180011BE5
0x180011bde  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180011be3  mov     ebx, eax
0x180011be5  mov     rsi, [rsp+28h+arg_8]
0x180011bea  mov     eax, ebx
0x180011bec  mov     rbx, [rsp+28h+arg_0]
0x180011bf1  add     rsp, 20h
0x180011bf5  pop     rdi
0x180011bf6  retn
```
