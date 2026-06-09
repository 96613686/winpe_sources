# CreateAndAppendNode(IXMLDOMDocument2 *,IXMLDOMNode *,ushort *,IXMLDOMNode * *)

- ea: `0x18003a560`
- end: `0x18003a6f4`
- name: `?CreateAndAppendNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAGPEAPEAU2@@Z`
- size: `404`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, unsigned __int16 *, struct IXMLDOMNode **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18003a880`
- `0x18003b31c`

## callees

- `0x18002cd00`
- `0x18003a560`
- `0x18003d9b0`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003a59a`
- `OLEAUT32!__imp_VariantInit` at `0x18003a59a`

## string_xrefs

- `0x18003a615`: `pXMLDomNode->createNode failed with 0x%x`
- `0x18003a695`: `pXMLParentNode->appendChild failed with 0x%x`

## pseudocode

```c
__int64 __fastcall CreateAndAppendNode(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        unsigned __int16 *a3,
        struct IXMLDOMNode **a4)
{
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  HRESULT (__stdcall *createNode)(IXMLDOMDocument2 *, VARIANT, BSTR, BSTR, IXMLDOMNode **); // rax
  int v10; // ebx
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  __int128 v13; // [rsp+50h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-10h]
  __int64 v15; // [rsp+90h] [rbp+20h] BYREF

  v15 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.lVal = 1;
  pvarg.vt = 3;
  lpVtbl = a1->lpVtbl;
  pRecInfo = pvarg.pRecInfo;
  createNode = lpVtbl->createNode;
  v13 = *(_OWORD *)&pvarg.vt;
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int128 *, unsigned __int16 *, __int64 *, __int64 *))createNode)(
          a1,
          &v13,
          a3,
          &qword_180061188,
          &v15);
  if ( v10 >= 0 )
  {
    v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, struct IXMLDOMNode **))a2->lpVtbl->appendChild)(
            a2,
            v15,
            a4);
    if ( v10 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pXMLParentNode->appendChild failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
        (unsigned int)"NPSSDO",
        v10);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pXMLDomNode->createNode failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
        (unsigned int)"NPSSDO",
        v10);
    }
    TraceXMLFailure(a1);
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003a560  mov     [rsp-18h+arg_8], rbx
0x18003a565  mov     [rsp-18h+arg_10], rsi
0x18003a56a  push    rbp
0x18003a56b  push    rdi
0x18003a56c  push    r14
0x18003a56e  mov     rbp, rsp
0x18003a571  sub     rsp, 70h
0x18003a575  mov     rsi, rcx
0x18003a578  mov     [rbp+arg_0], 0
0x18003a580  xorps   xmm0, xmm0
0x18003a583  lea     rcx, [rbp+pvarg]; pvarg
0x18003a587  xor     eax, eax
0x18003a589  mov     r14, r9
0x18003a58c  movups  xmmword ptr [rbp+pvarg], xmm0
0x18003a590  mov     qword ptr [rbp+pvarg+10h], rax
0x18003a594  mov     rbx, r8
0x18003a597  mov     rdi, rdx
0x18003a59a  call    cs:__imp_VariantInit
0x18003a5a0  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18003a5a5  lea     rcx, [rbp+arg_0]
0x18003a5a9  mov     eax, 3
0x18003a5ae  mov     dword ptr [rbp+pvarg+8], 1
0x18003a5b5  mov     word ptr [rbp+pvarg], ax
0x18003a5b9  lea     r9, qword_180061188
0x18003a5c0  mov     rax, [rsi]
0x18003a5c3  lea     rdx, [rbp+var_20]
0x18003a5c7  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18003a5cb  mov     [rsp+70h+var_50], rcx
0x18003a5d0  mov     r8, rbx
0x18003a5d3  mov     rcx, rsi
0x18003a5d6  movsd   [rbp+var_10], xmm1
0x18003a5db  mov     rax, [rax+1C0h]
0x18003a5e2  movaps  [rbp+var_20], xmm0
0x18003a5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a5eb  mov     ebx, eax
0x18003a5ed  test    eax, eax
0x18003a5ef  jns     short loc_18003A652
0x18003a5f1  mov     rax, cs:WPP_GLOBAL_Control
0x18003a5f8  lea     rcx, WPP_GLOBAL_Control
0x18003a5ff  cmp     rax, rcx
0x18003a602  jz      short loc_18003A648
0x18003a604  cmp     byte ptr [rax+19h], 2
0x18003a608  jb      short loc_18003A648
0x18003a60a  test    dword ptr [rax+1Ch], 400h
0x18003a611  jz      short loc_18003A648
0x18003a613  mov     edx, ebx
0x18003a615  lea     rcx, aPxmldomnodeCre; "pXMLDomNode->createNode failed with 0x%"...
0x18003a61c  call    WppDbgPrint
0x18003a621  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a628  lea     r9, aNpssdo; "NPSSDO"
0x18003a62f  mov     edx, 14h
0x18003a634  mov     dword ptr [rsp+70h+var_50], ebx
0x18003a638  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003a63f  mov     rcx, [rcx+10h]
0x18003a643  call    WPP_SF_sd
0x18003a648  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x18003a64b  call    ?TraceXMLFailure@@YAXPEAUIXMLDOMDocument2@@@Z; TraceXMLFailure(IXMLDOMDocument2 *)
0x18003a650  jmp     short loc_18003A6C8
0x18003a652  mov     rax, [rdi]
0x18003a655  mov     r8, r14
0x18003a658  mov     rdx, [rbp+arg_0]
0x18003a65c  mov     rcx, rdi
0x18003a65f  mov     rax, [rax+0A8h]
0x18003a666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a66b  mov     ebx, eax
0x18003a66d  test    eax, eax
0x18003a66f  jns     short loc_18003A6C8
0x18003a671  mov     rax, cs:WPP_GLOBAL_Control
0x18003a678  lea     rcx, WPP_GLOBAL_Control
0x18003a67f  cmp     rax, rcx
0x18003a682  jz      short loc_18003A6C8
0x18003a684  cmp     byte ptr [rax+19h], 2
0x18003a688  jb      short loc_18003A6C8
0x18003a68a  test    dword ptr [rax+1Ch], 400h
0x18003a691  jz      short loc_18003A6C8
0x18003a693  mov     edx, ebx
0x18003a695  lea     rcx, aPxmlparentnode; "pXMLParentNode->appendChild failed with"...
0x18003a69c  call    WppDbgPrint
0x18003a6a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a6a8  lea     r9, aNpssdo; "NPSSDO"
0x18003a6af  mov     edx, 15h
0x18003a6b4  mov     dword ptr [rsp+70h+var_50], ebx
0x18003a6b8  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003a6bf  mov     rcx, [rcx+10h]
0x18003a6c3  call    WPP_SF_sd
0x18003a6c8  mov     rcx, [rbp+arg_0]
0x18003a6cc  test    rcx, rcx
0x18003a6cf  jz      short loc_18003A6DD
0x18003a6d1  mov     rax, [rcx]
0x18003a6d4  mov     rax, [rax+10h]
0x18003a6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6dd  lea     r11, [rsp+70h+var_s0]
0x18003a6e2  mov     eax, ebx
0x18003a6e4  mov     rbx, [r11+28h]
0x18003a6e8  mov     rsi, [r11+30h]
0x18003a6ec  mov     rsp, r11
0x18003a6ef  pop     r14
0x18003a6f1  pop     rdi
0x18003a6f2  pop     rbp
0x18003a6f3  retn
```
