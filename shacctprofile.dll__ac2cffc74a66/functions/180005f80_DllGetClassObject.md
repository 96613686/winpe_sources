# DllGetClassObject

- ea: `0x180005f80`
- end: `0x18000602f`
- name: `DllGetClassObject`
- size: `175`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001e00`
- `0x180005f80`
- `0x18000a010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  _DWORD *v5; // rax
  _DWORD *v6; // rbx
  HRESULT v7; // edi

  *ppv = 0;
  if ( *(_OWORD *)rclsid != *(_OWORD *)&CLSID_ProfileNotificationHandler )
    return -2147221231;
  v5 = operator new(0x18u);
  v6 = v5;
  if ( !v5 )
    return -2147024882;
  v5[2] = 1;
  *(_QWORD *)v5 = &CClassFactory::`vftable';
  *((_QWORD *)v5 + 2) = CProfileNotificationHandler_CreateInstance;
  _InterlockedIncrement(&g_cRefCount);
  v7 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v5)(v5, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  return v7;
}

```

## disassembly

```asm
0x180005f80  mov     [rsp+arg_0], rbx
0x180005f85  mov     [rsp+arg_8], rsi
0x180005f8a  push    rdi
0x180005f8b  sub     rsp, 20h
0x180005f8f  mov     qword ptr [r8], 0
0x180005f96  mov     rdi, r8
0x180005f99  mov     rax, [rcx]
0x180005f9c  mov     rsi, rdx
0x180005f9f  cmp     rax, qword ptr cs:CLSID_ProfileNotificationHandler.Data1
0x180005fa6  jnz     short loc_18000601A
0x180005fa8  mov     rax, [rcx+8]
0x180005fac  cmp     rax, qword ptr cs:CLSID_ProfileNotificationHandler.Data4
0x180005fb3  jnz     short loc_18000601A
0x180005fb5  mov     ecx, 18h; Size
0x180005fba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005fbf  mov     rbx, rax
0x180005fc2  test    rax, rax
0x180005fc5  jz      short loc_180006011
0x180005fc7  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x180005fce  mov     dword ptr [rbx+8], 1
0x180005fd5  mov     [rbx], rax
0x180005fd8  lea     rax, ?CProfileNotificationHandler_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CProfileNotificationHandler_CreateInstance(_GUID const &,void * *)
0x180005fdf  mov     [rbx+10h], rax
0x180005fe3  lock inc cs:?g_cRefCount@@3JA; long g_cRefCount
0x180005fea  mov     rcx, [rbx]
0x180005fed  mov     r8, rdi
0x180005ff0  mov     rdx, rsi
0x180005ff3  mov     rax, [rcx]
0x180005ff6  mov     rcx, rbx
0x180005ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ffe  mov     rcx, [rbx]
0x180006001  mov     edi, eax
0x180006003  mov     rax, [rcx+10h]
0x180006007  mov     rcx, rbx
0x18000600a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000600f  jmp     short loc_180006016
0x180006011  mov     edi, 8007000Eh
0x180006016  mov     eax, edi
0x180006018  jmp     short loc_18000601F
0x18000601a  mov     eax, 80040111h
0x18000601f  mov     rbx, [rsp+28h+arg_0]
0x180006024  mov     rsi, [rsp+28h+arg_8]
0x180006029  add     rsp, 20h
0x18000602d  pop     rdi
0x18000602e  retn
```
