# CXMLDocument::LoadXML(ATL::CComBSTR const &,IXMLDOMParseError * *)

- ea: `0x18002b1d4`
- end: `0x18002b319`
- name: `?LoadXML@CXMLDocument@@QEAAJAEBVCComBSTR@ATL@@PEAPEAUIXMLDOMParseError@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(LPVOID *ppv, const struct ATL::CComBSTR *, struct IXMLDOMParseError **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c8a8`

## callees

- `0x180003458`
- `0x18002a510`
- `0x18002b1d4`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b20c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b20c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXMLDocument::LoadXML(LPVOID *ppv, struct IXMLDOMNode **a2, struct IXMLDOMParseError **a3)
{
  unsigned int Instance; // ebx
  struct IXMLDOMNode **v6; // rdx
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  struct IXMLDOMParseError **v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = a3;
  CXMLDocumentNode::Detach((CXMLDocumentNode *)ppv, a2);
  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               1u,
               &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
               ppv);
  if ( !Instance )
  {
    if ( *ppv )
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 504LL))(*ppv, 0);
      if ( !Instance )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 560LL))(*ppv, 0);
        if ( !Instance )
          Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 544LL))(*ppv, 0);
      }
      if ( !Instance )
      {
        LOWORD(v9) = 0;
        Instance = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMNode *, struct IXMLDOMParseError ***))(*(_QWORD *)*ppv + 520LL))(
                     *ppv,
                     *a2,
                     &v9);
        if ( Instance == 1 || !(_WORD)v9 )
        {
          v8 = 0;
          (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*ppv + 480LL))(*ppv, &v8);
          Instance = -2147287038;
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v8);
        }
        else if ( !Instance )
        {
          CXMLDocumentNode::Detach((CXMLDocumentNode *)(ppv + 1), v6);
          return (**(unsigned int (__fastcall ***)(_QWORD, GUID *, LPVOID *))*ppv)(*ppv, &IID_IXMLDOMNode, ppv + 1);
        }
      }
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  return Instance;
}

```

## disassembly

```asm
0x18002b1d4  mov     [rsp+arg_8], rbx
0x18002b1d9  mov     [rsp+arg_18], rsi
0x18002b1de  mov     [rsp+arg_10], r8
0x18002b1e3  push    rdi
0x18002b1e4  sub     rsp, 30h
0x18002b1e8  mov     rsi, rdx
0x18002b1eb  mov     rdi, rcx
0x18002b1ee  call    ?Detach@CXMLDocumentNode@@QEAAJPEAPEAUIXMLDOMNode@@@Z; CXMLDocumentNode::Detach(IXMLDOMNode * *)
0x18002b1f3  mov     [rsp+38h+ppv], rdi; ppv
0x18002b1f8  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18002b1ff  xor     edx, edx; pUnkOuter
0x18002b201  lea     r8d, [rdx+1]; dwClsContext
0x18002b205  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18002b20c  call    cs:__imp_CoCreateInstance
0x18002b212  mov     ebx, eax
0x18002b214  test    eax, eax
0x18002b216  jnz     loc_18002B307
0x18002b21c  mov     rcx, [rdi]
0x18002b21f  test    rcx, rcx
0x18002b222  jnz     short loc_18002B22E
0x18002b224  mov     ebx, 8000FFFFh
0x18002b229  jmp     loc_18002B307
0x18002b22e  mov     rax, [rcx]
0x18002b231  xor     edx, edx
0x18002b233  mov     rax, [rax+1F8h]
0x18002b23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b23f  mov     ebx, eax
0x18002b241  test    eax, eax
0x18002b243  jnz     short loc_18002B275
0x18002b245  mov     rcx, [rdi]
0x18002b248  mov     rax, [rcx]
0x18002b24b  xor     edx, edx
0x18002b24d  mov     rax, [rax+230h]
0x18002b254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b259  mov     ebx, eax
0x18002b25b  test    eax, eax
0x18002b25d  jnz     short loc_18002B275
0x18002b25f  mov     rcx, [rdi]
0x18002b262  mov     rax, [rcx]
0x18002b265  xor     edx, edx
0x18002b267  mov     rax, [rax+220h]
0x18002b26e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b273  mov     ebx, eax
0x18002b275  test    ebx, ebx
0x18002b277  jnz     loc_18002B307
0x18002b27d  xor     eax, eax
0x18002b27f  mov     word ptr [rsp+38h+arg_10], ax
0x18002b284  mov     rcx, [rdi]
0x18002b287  mov     rax, [rcx]
0x18002b28a  lea     r8, [rsp+38h+arg_10]
0x18002b28f  mov     rdx, [rsi]
0x18002b292  mov     rax, [rax+208h]
0x18002b299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b29e  mov     ebx, eax
0x18002b2a0  cmp     eax, 1
0x18002b2a3  jz      short loc_18002B2D8
0x18002b2a5  xor     eax, eax
0x18002b2a7  cmp     ax, word ptr [rsp+38h+arg_10]
0x18002b2ac  jz      short loc_18002B2D8
0x18002b2ae  test    ebx, ebx
0x18002b2b0  jnz     short loc_18002B307
0x18002b2b2  lea     rcx, [rdi+8]; this
0x18002b2b6  call    ?Detach@CXMLDocumentNode@@QEAAJPEAPEAUIXMLDOMNode@@@Z; CXMLDocumentNode::Detach(IXMLDOMNode * *)
0x18002b2bb  mov     rcx, [rdi]
0x18002b2be  mov     rax, [rcx]
0x18002b2c1  lea     r8, [rdi+8]
0x18002b2c5  lea     rdx, IID_IXMLDOMNode
0x18002b2cc  mov     rax, [rax]
0x18002b2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2d4  mov     ebx, eax
0x18002b2d6  jmp     short loc_18002B307
0x18002b2d8  mov     [rsp+38h+arg_0], 0
0x18002b2e1  mov     rcx, [rdi]
0x18002b2e4  mov     rax, [rcx]
0x18002b2e7  lea     rdx, [rsp+38h+arg_0]
0x18002b2ec  mov     rax, [rax+1E0h]
0x18002b2f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2f8  mov     ebx, 80030002h
0x18002b2fd  lea     rcx, [rsp+38h+arg_0]
0x18002b302  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002b307  mov     eax, ebx
0x18002b309  mov     rbx, [rsp+38h+arg_8]
0x18002b30e  mov     rsi, [rsp+38h+arg_18]
0x18002b313  add     rsp, 30h
0x18002b317  pop     rdi
0x18002b318  retn
```
