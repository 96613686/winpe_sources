# DllGetClassObject

- ea: `0x18000ce00`
- end: `0x18000cec4`
- name: `DllGetClassObject`
- size: `196`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001ed4`
- `0x18000ce00`
- `0x18001b010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  HRESULT v7; // ebx

  *ppv = 0;
  if ( *(_OWORD *)&CLSID_RtfIFilter != *(_OWORD *)rclsid
    && (*(_QWORD *)&CLSID_RtfClass.Data1 != *(_QWORD *)&rclsid->Data1
     || *(_QWORD *)CLSID_RtfClass.Data4 != *(_QWORD *)rclsid->Data4) )
  {
    return -2147221231;
  }
  v5 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
    return -2147024882;
  *(_QWORD *)v5 = &CRtfIFilterCF::`vftable';
  _InterlockedIncrement(&g_cInstances);
  v5[2] = 1;
  v7 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v5)(v5, riid, ppv);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  return v7;
}

```

## disassembly

```asm
0x18000ce00  mov     [rsp+arg_0], rbx
0x18000ce05  mov     [rsp+arg_8], rsi
0x18000ce0a  push    rdi
0x18000ce0b  sub     rsp, 20h
0x18000ce0f  mov     qword ptr [r8], 0
0x18000ce16  mov     rbx, r8
0x18000ce19  mov     rax, qword ptr cs:?CLSID_RtfIFilter@@3U_GUID@@A.Data1; _GUID CLSID_RtfIFilter ...
0x18000ce20  mov     rsi, rdx
0x18000ce23  cmp     rax, [rcx]
0x18000ce26  jnz     short loc_18000CE35
0x18000ce28  mov     rax, qword ptr cs:?CLSID_RtfIFilter@@3U_GUID@@A.Data4; _GUID CLSID_RtfIFilter ...
0x18000ce2f  cmp     rax, [rcx+8]
0x18000ce33  jz      short loc_18000CE4E
0x18000ce35  mov     rax, qword ptr cs:?CLSID_RtfClass@@3U_GUID@@A.Data1; _GUID CLSID_RtfClass ...
0x18000ce3c  cmp     rax, [rcx]
0x18000ce3f  jnz     short loc_18000CEAD
0x18000ce41  mov     rax, qword ptr cs:?CLSID_RtfClass@@3U_GUID@@A.Data4; _GUID CLSID_RtfClass ...
0x18000ce48  cmp     rax, [rcx+8]
0x18000ce4c  jnz     short loc_18000CEAD
0x18000ce4e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ce55  mov     ecx, 10h; unsigned __int64
0x18000ce5a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ce5f  mov     rdi, rax
0x18000ce62  test    rax, rax
0x18000ce65  jz      short loc_18000CEA6
0x18000ce67  lea     rax, ??_7CRtfIFilterCF@@6B@; const CRtfIFilterCF::`vftable'
0x18000ce6e  mov     [rdi], rax
0x18000ce71  lock inc cs:?g_cInstances@@3JA; long g_cInstances
0x18000ce78  mov     dword ptr [rdi+8], 1
0x18000ce7f  mov     r8, rbx
0x18000ce82  mov     rcx, [rdi]
0x18000ce85  mov     rdx, rsi
0x18000ce88  mov     rax, [rcx]
0x18000ce8b  mov     rcx, rdi
0x18000ce8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce93  mov     rcx, [rdi]
0x18000ce96  mov     ebx, eax
0x18000ce98  mov     rax, [rcx+10h]
0x18000ce9c  mov     rcx, rdi
0x18000ce9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cea4  jmp     short loc_18000CEB2
0x18000cea6  mov     ebx, 8007000Eh
0x18000ceab  jmp     short loc_18000CEB2
0x18000cead  mov     ebx, 80040111h
0x18000ceb2  mov     rsi, [rsp+28h+arg_8]
0x18000ceb7  mov     eax, ebx
0x18000ceb9  mov     rbx, [rsp+28h+arg_0]
0x18000cebe  add     rsp, 20h
0x18000cec2  pop     rdi
0x18000cec3  retn
```
