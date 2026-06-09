# _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::CreateInstance(_GUID const &,IUnknown *,ulong)

- ea: `0x18004c55c`
- end: `0x18004c608`
- name: `?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z`
- size: `172`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004d4c8`
- `0x18004d900`

## callees

- `0x180024cac`
- `0x18004c55c`
- `0x180058010`

## import_xrefs

- `ole32!OleRun` at `0x18004c5ac`
- `ole32!OleRun` at `0x18004c5ac`
- `ole32!CoCreateInstance` at `0x18004c59d`
- `ole32!CoCreateInstance` at `0x18004c5f3`
- `ole32!CoCreateInstance` at `0x18004c59d`
- `ole32!CoCreateInstance` at `0x18004c5f3`

## pseudocode

```c
int __fastcall _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>>::CreateInstance(
        LPVOID *ppv,
        __int64 a2,
        IUnknown *a3,
        DWORD a4)
{
  int result; // eax
  HRESULT v7; // ebx
  LPUNKNOWN pUnknown; // [rsp+50h] [rbp+18h] BYREF

  pUnknown = a3;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppv);
  if ( (a4 & 0x14) == 0 )
    return CoCreateInstance(
             &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
             0,
             a4,
             &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
             ppv);
  pUnknown = 0;
  result = CoCreateInstance(
             &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
             0,
             a4,
             &GUID_00000000_0000_0000_c000_000000000046,
             (LPVOID *)&pUnknown);
  if ( result < 0 )
    return result;
  v7 = OleRun(pUnknown);
  if ( v7 >= 0 )
    v7 = ((__int64 (__fastcall *)(LPUNKNOWN, GUID *, LPVOID *))pUnknown->lpVtbl->QueryInterface)(
           pUnknown,
           &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
           ppv);
  ((void (__fastcall *)(LPUNKNOWN))pUnknown->lpVtbl->Release)(pUnknown);
  return v7;
}

```

## disassembly

```asm
0x18004c55c  mov     [rsp+arg_0], rbx
0x18004c561  mov     [rsp+pUnknown], r8
0x18004c566  push    rdi
0x18004c567  sub     rsp, 30h
0x18004c56b  mov     ebx, r9d
0x18004c56e  mov     rdi, rcx
0x18004c571  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c576  mov     r8d, ebx; dwClsContext
0x18004c579  xor     edx, edx; pUnkOuter
0x18004c57b  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18004c582  test    bl, 14h
0x18004c585  jz      short loc_18004C5E7
0x18004c587  mov     [rsp+38h+pUnknown], rdx
0x18004c58c  lea     rax, [rsp+38h+pUnknown]
0x18004c591  mov     [rsp+38h+ppv], rax; ppv
0x18004c596  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18004c59d  call    cs:__imp_CoCreateInstance
0x18004c5a3  test    eax, eax
0x18004c5a5  js      short loc_18004C5FD
0x18004c5a7  mov     rcx, [rsp+38h+pUnknown]; pUnknown
0x18004c5ac  call    cs:__imp_OleRun
0x18004c5b2  mov     ebx, eax
0x18004c5b4  test    eax, eax
0x18004c5b6  js      short loc_18004C5D4
0x18004c5b8  mov     rcx, [rsp+38h+pUnknown]
0x18004c5bd  mov     rax, [rcx]
0x18004c5c0  mov     r8, rdi
0x18004c5c3  lea     rdx, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60
0x18004c5ca  mov     rax, [rax]
0x18004c5cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c5d2  mov     ebx, eax
0x18004c5d4  mov     rcx, [rsp+38h+pUnknown]
0x18004c5d9  mov     rax, [rcx]
0x18004c5dc  mov     rax, [rax+10h]
0x18004c5e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c5e5  jmp     short loc_18004C5FB
0x18004c5e7  mov     [rsp+38h+ppv], rdi; ppv
0x18004c5ec  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18004c5f3  call    cs:__imp_CoCreateInstance
0x18004c5f9  mov     ebx, eax
0x18004c5fb  mov     eax, ebx
0x18004c5fd  mov     rbx, [rsp+38h+arg_0]
0x18004c602  add     rsp, 30h
0x18004c606  pop     rdi
0x18004c607  retn
```
