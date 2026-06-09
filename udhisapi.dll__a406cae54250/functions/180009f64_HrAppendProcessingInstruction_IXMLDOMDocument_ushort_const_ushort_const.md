# HrAppendProcessingInstruction(IXMLDOMDocument *,ushort const *,ushort const *)

- ea: `0x180009f64`
- end: `0x18000a06a`
- name: `?HrAppendProcessingInstruction@@YAJPEAUIXMLDOMDocument@@PEBG1@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800063e0`

## callees

- `0x180009f64`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180009f8d`
- `OLEAUT32!__imp_SysAllocString` at `0x180009f9d`
- `OLEAUT32!__imp_SysAllocString` at `0x180009f8d`
- `OLEAUT32!__imp_SysAllocString` at `0x180009f9d`
- `OLEAUT32!__imp_SysFreeString` at `0x180009fd9`
- `OLEAUT32!__imp_SysFreeString` at `0x180009fe2`
- `OLEAUT32!__imp_SysFreeString` at `0x180009fd9`
- `OLEAUT32!__imp_SysFreeString` at `0x180009fe2`

## pseudocode

```c
__int64 __fastcall HrAppendProcessingInstruction(
        struct IXMLDOMDocument *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  OLECHAR *v4; // rsi
  BSTR v5; // rax
  OLECHAR *v6; // rdi
  int v7; // ebx
  __int64 v9; // [rsp+58h] [rbp+10h] BYREF
  const unsigned __int16 *v10; // [rsp+60h] [rbp+18h] BYREF

  v10 = a3;
  v9 = 0;
  v4 = SysAllocString(L"xml");
  v5 = SysAllocString(L"version=\"1.0\"");
  v6 = v5;
  if ( v4 && v5 )
    v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, OLECHAR *, BSTR, __int64 *))a1->lpVtbl->createProcessingInstruction)(
           a1,
           v4,
           v5,
           &v9);
  else
    v7 = -2147024882;
  SysFreeString(v4);
  SysFreeString(v6);
  if ( v7 >= 0 )
  {
    v10 = 0;
    v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, const unsigned __int16 **))v9)(v9, &IID_IXMLDOMNode, &v10);
    if ( v7 >= 0 )
    {
      v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, const unsigned __int16 *, _QWORD))a1->lpVtbl->appendChild)(
             a1,
             v10,
             0);
      (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009f64  mov     rax, rsp
0x180009f67  mov     [rax+8], rbx
0x180009f6b  mov     [rax+18h], r8
0x180009f6f  mov     [rax+10h], rdx
0x180009f73  push    rsi
0x180009f74  push    rdi
0x180009f75  push    r14
0x180009f77  sub     rsp, 30h
0x180009f7b  mov     r14, rcx
0x180009f7e  mov     qword ptr [rax+10h], 0
0x180009f86  lea     rcx, aXml; "xml"
0x180009f8d  call    cs:__imp_SysAllocString
0x180009f93  lea     rcx, aVersion10; "version=\"1.0\""
0x180009f9a  mov     rsi, rax
0x180009f9d  call    cs:__imp_SysAllocString
0x180009fa3  mov     rdi, rax
0x180009fa6  test    rsi, rsi
0x180009fa9  jz      short loc_180009FD1
0x180009fab  test    rax, rax
0x180009fae  jz      short loc_180009FD1
0x180009fb0  mov     rcx, [r14]
0x180009fb3  lea     r9, [rsp+48h+arg_8]
0x180009fb8  mov     r8, rdi
0x180009fbb  mov     rdx, rsi
0x180009fbe  mov     rax, [rcx+1A0h]
0x180009fc5  mov     rcx, r14
0x180009fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fcd  mov     ebx, eax
0x180009fcf  jmp     short loc_180009FD6
0x180009fd1  mov     ebx, 8007000Eh
0x180009fd6  mov     rcx, rsi; bstrString
0x180009fd9  call    cs:__imp_SysFreeString
0x180009fdf  mov     rcx, rdi; bstrString
0x180009fe2  call    cs:__imp_SysFreeString
0x180009fe8  test    ebx, ebx
0x180009fea  js      short loc_18000A044
0x180009fec  mov     rcx, [rsp+48h+arg_8]
0x180009ff1  lea     r8, [rsp+48h+arg_10]
0x180009ff6  mov     [rsp+48h+arg_10], 0
0x180009fff  lea     rdx, IID_IXMLDOMNode
0x18000a006  mov     rax, [rcx]
0x18000a009  mov     rax, [rax]
0x18000a00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a011  mov     ebx, eax
0x18000a013  test    eax, eax
0x18000a015  js      short loc_18000A044
0x18000a017  mov     rax, [r14]
0x18000a01a  xor     r8d, r8d
0x18000a01d  mov     rdx, [rsp+48h+arg_10]
0x18000a022  mov     rcx, r14
0x18000a025  mov     rax, [rax+0A8h]
0x18000a02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a031  mov     rcx, [rsp+48h+arg_10]
0x18000a036  mov     ebx, eax
0x18000a038  mov     rax, [rcx]
0x18000a03b  mov     rax, [rax+10h]
0x18000a03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a044  mov     rcx, [rsp+48h+arg_8]
0x18000a049  test    rcx, rcx
0x18000a04c  jz      short loc_18000A05A
0x18000a04e  mov     rax, [rcx]
0x18000a051  mov     rax, [rax+10h]
0x18000a055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a05a  mov     eax, ebx
0x18000a05c  mov     rbx, [rsp+48h+arg_0]
0x18000a061  add     rsp, 30h
0x18000a065  pop     r14
0x18000a067  pop     rdi
0x18000a068  pop     rsi
0x18000a069  retn
```
