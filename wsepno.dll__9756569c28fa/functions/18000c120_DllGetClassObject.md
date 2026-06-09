# DllGetClassObject

- ea: `0x18000c120`
- end: `0x18000c1d0`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001b78`
- `0x18000c120`
- `0x18000f010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  _DWORD *v7; // rax
  _DWORD *v8; // rdi

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  v6 = -2147221231;
  if ( *(_OWORD *)rclsid == *(_OWORD *)&CLSID_ProfileNotifyHandler )
  {
    v6 = -2147024882;
    v7 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( v7 )
    {
      ++g_cRefDll;
      *(_QWORD *)v7 = &CClassFactory::`vftable';
      v7[2] = 1;
      *((_QWORD *)v7 + 2) = CProfileNotifyHandler_CreateInstance;
      v6 = ((__int64 (__fastcall *)(_DWORD *, const IID *const, LPVOID *))CClassFactory::`vftable')(v7, riid, ppv);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000c120  push    rbx
0x18000c122  push    rbp
0x18000c123  push    rsi
0x18000c124  push    rdi
0x18000c125  sub     rsp, 28h
0x18000c129  mov     rsi, r8
0x18000c12c  mov     rbp, rdx
0x18000c12f  test    r8, r8
0x18000c132  jnz     short loc_18000C13E
0x18000c134  mov     eax, 80070057h
0x18000c139  jmp     loc_18000C1C7
0x18000c13e  mov     qword ptr [r8], 0
0x18000c145  mov     ebx, 80040111h
0x18000c14a  mov     rax, [rcx]
0x18000c14d  cmp     rax, qword ptr cs:CLSID_ProfileNotifyHandler.Data1
0x18000c154  jnz     short loc_18000C1C5
0x18000c156  mov     rax, [rcx+8]
0x18000c15a  cmp     rax, qword ptr cs:CLSID_ProfileNotifyHandler.Data4
0x18000c161  jnz     short loc_18000C1C5
0x18000c163  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c16a  mov     ecx, 18h; unsigned __int64
0x18000c16f  mov     ebx, 8007000Eh
0x18000c174  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c179  mov     rdi, rax
0x18000c17c  test    rax, rax
0x18000c17f  jz      short loc_18000C1C5
0x18000c181  inc     cs:?g_cRefDll@@3JA; long g_cRefDll
0x18000c187  lea     r9, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x18000c18e  mov     [rax], r9
0x18000c191  mov     r8, rsi
0x18000c194  mov     dword ptr [rax+8], 1
0x18000c19b  mov     rdx, rbp
0x18000c19e  lea     rax, ?CProfileNotifyHandler_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CProfileNotifyHandler_CreateInstance(_GUID const &,void * *)
0x18000c1a5  mov     rcx, rdi
0x18000c1a8  mov     [rdi+10h], rax
0x18000c1ac  mov     rax, [r9]
0x18000c1af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1b4  mov     rcx, [rdi]
0x18000c1b7  mov     ebx, eax
0x18000c1b9  mov     rax, [rcx+10h]
0x18000c1bd  mov     rcx, rdi
0x18000c1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1c5  mov     eax, ebx
0x18000c1c7  add     rsp, 28h
0x18000c1cb  pop     rdi
0x18000c1cc  pop     rsi
0x18000c1cd  pop     rbp
0x18000c1ce  pop     rbx
0x18000c1cf  retn
```
