# SdpXmlGetNodes(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *)

- ea: `0x18000b750`
- end: `0x18000b87b`
- name: `?SdpXmlGetNodes@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct IXMLDOMNodeList **)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004c48`
- `0x180005404`
- `0x1800060bc`
- `0x1800062c4`

## callees

- `0x18000b13c`
- `0x18000b750`
- `0x18000d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000b7bc`
- `OLEAUT32!__imp_SysAllocString` at `0x18000b7bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b840`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b840`

## string_xrefs

- `0x18000b787`: `SdpXmlGetNodes`
- `0x18000b810`: `SdpXmlGetNodes`

## pseudocode

```c
__int64 __fastcall SdpXmlGetNodes(
        const unsigned __int16 *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMDocument2 *a3,
        struct IXMLDOMNodeList **a4)
{
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ebx
  BSTR v10; // rax
  OLECHAR *v11; // rdi
  BSTR v12; // rdx
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  struct IXMLDOMDocument2 *v14; // rcx
  int v15; // eax
  struct IXMLDOMNodeList *v16; // rcx
  struct IXMLDOMNodeList *v18; // [rsp+30h] [rbp+8h] BYREF

  v18 = 0;
  if ( !a1 )
  {
    v7 = 986;
LABEL_3:
    v8 = -2147024809;
    v9 = -2147024809;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v7 = 987;
    goto LABEL_3;
  }
  if ( !a2 && !a3 )
  {
    v7 = 991;
    goto LABEL_3;
  }
  v10 = SysAllocString(a1);
  v11 = v10;
  if ( v10 )
  {
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
    v15 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, struct IXMLDOMNodeList **))lpVtbl->selectNodes)(
            v14,
            v12,
            &v18);
    v9 = v15;
    if ( v15 >= 0 )
    {
      v16 = v18;
      *a4 = v18;
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v16->lpVtbl->AddRef)(v16);
    }
    else
    {
      SdpDebugTrace(1u, L"SdpXmlGetNodes", 1004, v15);
    }
    SysFreeString(v11);
    goto LABEL_19;
  }
  v9 = -2147024882;
  v7 = 995;
  v8 = -2147024882;
LABEL_4:
  SdpDebugTrace(1u, L"SdpXmlGetNodes", v7, v8);
LABEL_19:
  if ( v18 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v18->lpVtbl->Release)(v18);
  return v9;
}

```

## disassembly

```asm
0x18000b750  mov     rax, rsp
0x18000b753  mov     [rax+10h], rbx
0x18000b757  mov     [rax+18h], rsi
0x18000b75b  mov     [rax+20h], rdi
0x18000b75f  push    r14
0x18000b761  sub     rsp, 20h
0x18000b765  and     qword ptr [rax+8], 0
0x18000b76a  mov     r14, r9
0x18000b76d  mov     rsi, r8
0x18000b770  mov     rbx, rdx
0x18000b773  test    rcx, rcx
0x18000b776  jnz     short loc_18000B79D
0x18000b778  mov     r8d, 3DAh; int
0x18000b77e  mov     r9d, 80070057h; int
0x18000b784  mov     ebx, r9d
0x18000b787  lea     rdx, aSdpxmlgetnodes; "SdpXmlGetNodes"
0x18000b78e  mov     ecx, 1; Level
0x18000b793  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000b798  jmp     loc_18000B84C
0x18000b79d  test    r14, r14
0x18000b7a0  jnz     short loc_18000B7AA
0x18000b7a2  mov     r8d, 3DBh
0x18000b7a8  jmp     short loc_18000B77E
0x18000b7aa  test    rbx, rbx
0x18000b7ad  jnz     short loc_18000B7BC
0x18000b7af  test    rsi, rsi
0x18000b7b2  jnz     short loc_18000B7BC
0x18000b7b4  mov     r8d, 3DFh
0x18000b7ba  jmp     short loc_18000B77E
0x18000b7bc  call    cs:__imp_SysAllocString
0x18000b7c3  nop     dword ptr [rax+rax+00h]
0x18000b7c8  mov     rdi, rax
0x18000b7cb  test    rax, rax
0x18000b7ce  jnz     short loc_18000B7E0
0x18000b7d0  mov     ebx, 8007000Eh
0x18000b7d5  mov     r8d, 3E3h
0x18000b7db  mov     r9d, ebx
0x18000b7de  jmp     short loc_18000B787
0x18000b7e0  lea     r8, [rsp+28h+arg_0]
0x18000b7e5  mov     rdx, rdi
0x18000b7e8  test    rbx, rbx
0x18000b7eb  jz      short loc_18000B7F5
0x18000b7ed  mov     rax, [rbx]
0x18000b7f0  mov     rcx, rbx
0x18000b7f3  jmp     short loc_18000B7FB
0x18000b7f5  mov     rax, [rsi]
0x18000b7f8  mov     rcx, rsi
0x18000b7fb  mov     rax, [rax+120h]
0x18000b802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b807  mov     ebx, eax
0x18000b809  test    eax, eax
0x18000b80b  jns     short loc_18000B829
0x18000b80d  mov     r9d, eax; int
0x18000b810  lea     rdx, aSdpxmlgetnodes; "SdpXmlGetNodes"
0x18000b817  mov     r8d, 3ECh; int
0x18000b81d  mov     ecx, 1; Level
0x18000b822  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000b827  jmp     short loc_18000B83D
0x18000b829  mov     rcx, [rsp+28h+arg_0]
0x18000b82e  mov     [r14], rcx
0x18000b831  mov     rax, [rcx]
0x18000b834  mov     rax, [rax+8]
0x18000b838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b83d  mov     rcx, rdi; bstrString
0x18000b840  call    cs:__imp_SysFreeString
0x18000b847  nop     dword ptr [rax+rax+00h]
0x18000b84c  mov     rcx, [rsp+28h+arg_0]
0x18000b851  test    rcx, rcx
0x18000b854  jz      short loc_18000B862
0x18000b856  mov     rax, [rcx]
0x18000b859  mov     rax, [rax+10h]
0x18000b85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b862  mov     rsi, [rsp+28h+arg_10]
0x18000b867  mov     eax, ebx
0x18000b869  mov     rbx, [rsp+28h+arg_8]
0x18000b86e  mov     rdi, [rsp+28h+arg_18]
0x18000b873  add     rsp, 20h
0x18000b877  pop     r14
0x18000b879  retn
```
