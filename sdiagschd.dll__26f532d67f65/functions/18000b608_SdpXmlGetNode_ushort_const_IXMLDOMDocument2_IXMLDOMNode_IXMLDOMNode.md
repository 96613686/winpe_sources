# SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)

- ea: `0x18000b608`
- end: `0x18000b74a`
- name: `?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z`
- size: `322`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct IXMLDOMNode **)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004c48`
- `0x1800050c0`
- `0x180005260`
- `0x180005b70`
- `0x180005e30`
- `0x180005f60`
- `0x1800062c4`
- `0x180006770`
- `0x180006ba8`

## callees

- `0x18000b13c`
- `0x18000b608`
- `0x18000d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000b674`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b674`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b70f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b70f`

## string_xrefs

- `0x18000b63f`: `SdpXmlGetNode`
- `0x18000b6fb`: `SdpXmlGetNode`

## pseudocode

```c
__int64 __fastcall SdpXmlGetNode(
        const unsigned __int16 *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMDocument2 *a3,
        struct IXMLDOMNode **a4)
{
  int v7; // r8d
  int v8; // r9d
  int v9; // ebx
  BSTR v10; // rax
  OLECHAR *v11; // rdi
  BSTR v12; // rdx
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  struct IXMLDOMDocument2 *v14; // rcx
  int v15; // r8d
  struct IXMLDOMNode v16; // rax
  struct IXMLDOMNode *v18; // [rsp+30h] [rbp+8h] BYREF

  v18 = 0;
  if ( !a1 )
  {
    v7 = 917;
LABEL_3:
    v8 = -2147024809;
    v9 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"SdpXmlGetNode", v7, v8);
    goto LABEL_23;
  }
  if ( !a4 )
  {
    v7 = 918;
    goto LABEL_3;
  }
  if ( !a2 && !a3 )
  {
    v7 = 921;
    goto LABEL_3;
  }
  v10 = SysAllocString(a1);
  v11 = v10;
  if ( !v10 )
  {
    v9 = -2147024882;
    v7 = 925;
    v8 = -2147024882;
    goto LABEL_4;
  }
  v12 = v10;
  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    v14 = a2;
  }
  else
  {
    lpVtbl = a3->lpVtbl;
    v14 = a3;
  }
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, struct IXMLDOMNode **))lpVtbl->selectSingleNode)(
         v14,
         v12,
         &v18);
  if ( v9 < 0 )
  {
    v15 = 934;
LABEL_21:
    SdpDebugTrace(1u, L"SdpXmlGetNode", v15, v9);
    goto LABEL_22;
  }
  if ( v9 == 1 || !v18 )
  {
    v9 = -2147467259;
    v15 = 935;
    goto LABEL_21;
  }
  v16.lpVtbl = v18->lpVtbl;
  *a4 = v18;
  ((void (*)(void))v16.lpVtbl->AddRef)();
LABEL_22:
  SysFreeString(v11);
LABEL_23:
  if ( v18 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v18->lpVtbl->Release)(v18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b608  mov     rax, rsp
0x18000b60b  mov     [rax+10h], rbx
0x18000b60f  mov     [rax+18h], rsi
0x18000b613  mov     [rax+20h], rdi
0x18000b617  push    r14
0x18000b619  sub     rsp, 20h
0x18000b61d  and     qword ptr [rax+8], 0
0x18000b622  mov     r14, r9
0x18000b625  mov     rsi, r8
0x18000b628  mov     rbx, rdx
0x18000b62b  test    rcx, rcx
0x18000b62e  jnz     short loc_18000B655
0x18000b630  mov     r8d, 395h; int
0x18000b636  mov     r9d, 80070057h; int
0x18000b63c  mov     ebx, r9d
0x18000b63f  lea     rdx, aSdpxmlgetnode; "SdpXmlGetNode"
0x18000b646  mov     ecx, 1; Level
0x18000b64b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000b650  jmp     loc_18000B71B
0x18000b655  test    r14, r14
0x18000b658  jnz     short loc_18000B662
0x18000b65a  mov     r8d, 396h
0x18000b660  jmp     short loc_18000B636
0x18000b662  test    rbx, rbx
0x18000b665  jnz     short loc_18000B674
0x18000b667  test    rsi, rsi
0x18000b66a  jnz     short loc_18000B674
0x18000b66c  mov     r8d, 399h
0x18000b672  jmp     short loc_18000B636
0x18000b674  call    cs:__imp_SysAllocString
0x18000b67b  nop     dword ptr [rax+rax+00h]
0x18000b680  mov     rdi, rax
0x18000b683  test    rax, rax
0x18000b686  jnz     short loc_18000B698
0x18000b688  mov     ebx, 8007000Eh
0x18000b68d  mov     r8d, 39Dh
0x18000b693  mov     r9d, ebx
0x18000b696  jmp     short loc_18000B63F
0x18000b698  lea     r8, [rsp+28h+arg_0]
0x18000b69d  mov     rdx, rdi
0x18000b6a0  test    rbx, rbx
0x18000b6a3  jz      short loc_18000B6AD
0x18000b6a5  mov     rax, [rbx]
0x18000b6a8  mov     rcx, rbx
0x18000b6ab  jmp     short loc_18000B6B3
0x18000b6ad  mov     rax, [rsi]
0x18000b6b0  mov     rcx, rsi
0x18000b6b3  mov     rax, [rax+128h]
0x18000b6ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6bf  mov     ebx, eax
0x18000b6c1  test    eax, eax
0x18000b6c3  jns     short loc_18000B6CD
0x18000b6c5  mov     r8d, 3A6h
0x18000b6cb  jmp     short loc_18000B6F8
0x18000b6cd  cmp     ebx, 1
0x18000b6d0  jz      short loc_18000B6ED
0x18000b6d2  mov     rcx, [rsp+28h+arg_0]
0x18000b6d7  test    rcx, rcx
0x18000b6da  jz      short loc_18000B6ED
0x18000b6dc  mov     rax, [rcx]
0x18000b6df  mov     [r14], rcx
0x18000b6e2  mov     rax, [rax+8]
0x18000b6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6eb  jmp     short loc_18000B70C
0x18000b6ed  mov     ebx, 80004005h
0x18000b6f2  mov     r8d, 3A7h; int
0x18000b6f8  mov     r9d, ebx; int
0x18000b6fb  lea     rdx, aSdpxmlgetnode; "SdpXmlGetNode"
0x18000b702  mov     ecx, 1; Level
0x18000b707  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000b70c  mov     rcx, rdi; bstrString
0x18000b70f  call    cs:__imp_SysFreeString
0x18000b716  nop     dword ptr [rax+rax+00h]
0x18000b71b  mov     rcx, [rsp+28h+arg_0]
0x18000b720  test    rcx, rcx
0x18000b723  jz      short loc_18000B731
0x18000b725  mov     rax, [rcx]
0x18000b728  mov     rax, [rax+10h]
0x18000b72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b731  mov     rsi, [rsp+28h+arg_10]
0x18000b736  mov     eax, ebx
0x18000b738  mov     rbx, [rsp+28h+arg_8]
0x18000b73d  mov     rdi, [rsp+28h+arg_18]
0x18000b742  add     rsp, 20h
0x18000b746  pop     r14
0x18000b748  retn
```
