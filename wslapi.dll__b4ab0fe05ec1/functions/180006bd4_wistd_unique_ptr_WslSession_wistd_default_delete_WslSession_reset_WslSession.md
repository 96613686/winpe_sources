# wistd::unique_ptr<WslSession,wistd::default_delete<WslSession>>::reset(WslSession *)

- ea: `0x180006bd4`
- end: `0x180006c00`
- name: `?reset@?$unique_ptr@VWslSession@@U?$default_delete@VWslSession@@@wistd@@@wistd@@QEAAXPEAVWslSession@@@Z`
- size: `44`
- prototype: `void __fastcall(WslSession **, WslSession *)`
- caller_count: `9`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006958`
- `0x1800069e4`
- `0x180006aa0`
- `0x180006f80`
- `0x18000710c`
- `0x1800071b0`
- `0x1800079cc`
- `0x180007a80`
- `0x180009190`

## callees

- `0x180002190`
- `0x1800069ac`
- `0x180006bd4`

## pseudocode

```c
void __fastcall wistd::unique_ptr<WslSession,wistd::default_delete<WslSession>>::reset(WslSession **a1, WslSession *a2)
{
  WslSession *v2; // rbx

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
  {
    WslSession::~WslSession(v2);
    operator delete(v2, (const struct std::nothrow_t *)0x18);
  }
}

```

## disassembly

```asm
0x180006bd4  push    rbx
0x180006bd6  sub     rsp, 20h
0x180006bda  mov     rbx, [rcx]
0x180006bdd  mov     [rcx], rdx
0x180006be0  test    rbx, rbx
0x180006be3  jz      short loc_180006BFA
0x180006be5  mov     rcx, rbx; this
0x180006be8  call    ??1WslSession@@QEAA@XZ; WslSession::~WslSession(void)
0x180006bed  mov     edx, 18h; struct std::nothrow_t *
0x180006bf2  mov     rcx, rbx; void *
0x180006bf5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006bfa  add     rsp, 20h
0x180006bfe  pop     rbx
0x180006bff  retn
```
