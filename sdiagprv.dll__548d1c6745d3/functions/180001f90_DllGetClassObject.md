# DllGetClassObject

- ea: `0x180001f90`
- end: `0x18000201b`
- name: `DllGetClassObject`
- size: `139`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001074`
- `0x180001f90`
- `0x1800021f0`
- `0x180019010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  CClassFactory *v7; // rax
  CClassFactory *v8; // rax
  CClassFactory *v9; // rdi
  HRESULT v10; // ebx

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  v7 = (CClassFactory *)operator new(0x20u);
  if ( !v7 )
    return -2147024882;
  v8 = CClassFactory::CClassFactory(v7, rclsid);
  v9 = v8;
  if ( !v8 )
    return -2147024882;
  v10 = (**(__int64 (__fastcall ***)(CClassFactory *, const IID *const, LPVOID *))v8)(v8, riid, ppv);
  (*(void (__fastcall **)(CClassFactory *))(*(_QWORD *)v9 + 16LL))(v9);
  return v10;
}

```

## disassembly

```asm
0x180001f90  mov     [rsp+arg_0], rbx
0x180001f95  mov     [rsp+arg_8], rsi
0x180001f9a  push    rdi
0x180001f9b  sub     rsp, 20h
0x180001f9f  mov     rbx, r8
0x180001fa2  mov     rsi, rdx
0x180001fa5  mov     rdi, rcx
0x180001fa8  test    r8, r8
0x180001fab  jnz     short loc_180001FB4
0x180001fad  mov     eax, 80070057h
0x180001fb2  jmp     short loc_18000200B
0x180001fb4  mov     ecx, 20h ; ' '; Size
0x180001fb9  mov     qword ptr [r8], 0
0x180001fc0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001fc5  test    rax, rax
0x180001fc8  jz      short loc_180002004
0x180001fca  mov     rdx, rdi; struct _GUID *
0x180001fcd  mov     rcx, rax; this
0x180001fd0  call    ??0CClassFactory@@QEAA@AEBU_GUID@@@Z; CClassFactory::CClassFactory(_GUID const &)
0x180001fd5  mov     rdi, rax
0x180001fd8  test    rax, rax
0x180001fdb  jz      short loc_180002004
0x180001fdd  mov     rcx, [rax]
0x180001fe0  mov     r8, rbx
0x180001fe3  mov     rdx, rsi
0x180001fe6  mov     rax, [rcx]
0x180001fe9  mov     rcx, rdi
0x180001fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ff1  mov     ebx, eax
0x180001ff3  mov     rcx, [rdi]
0x180001ff6  mov     rax, [rcx+10h]
0x180001ffa  mov     rcx, rdi
0x180001ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002002  jmp     short loc_180002009
0x180002004  mov     ebx, 8007000Eh
0x180002009  mov     eax, ebx
0x18000200b  mov     rbx, [rsp+28h+arg_0]
0x180002010  mov     rsi, [rsp+28h+arg_8]
0x180002015  add     rsp, 20h
0x180002019  pop     rdi
0x18000201a  retn
```
