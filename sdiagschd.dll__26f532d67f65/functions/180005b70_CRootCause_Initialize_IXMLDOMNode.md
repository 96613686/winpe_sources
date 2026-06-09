# CRootCause::Initialize(IXMLDOMNode *)

- ea: `0x180005b70`
- end: `0x180005d70`
- name: `?Initialize@CRootCause@@QEAAJPEAUIXMLDOMNode@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(CRootCause *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180005404`

## callees

- `0x180005b70`
- `0x180005e30`
- `0x180005f60`
- `0x1800060bc`
- `0x1800066f4`
- `0x18000b13c`
- `0x18000b608`
- `0x18000d010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180005cb1`
- `KERNEL32!HeapFree` at `0x180005cb1`
- `KERNEL32!GetProcessHeap` at `0x180005bf8`
- `KERNEL32!GetProcessHeap` at `0x180005c9d`
- `KERNEL32!GetProcessHeap` at `0x180005bf8`
- `KERNEL32!GetProcessHeap` at `0x180005c9d`
- `KERNEL32!HeapAlloc` at `0x180005c0f`
- `KERNEL32!HeapAlloc` at `0x180005c0f`
- `OLEAUT32!__imp_SysAllocString` at `0x180005c6b`
- `OLEAUT32!__imp_SysAllocString` at `0x180005c6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180005cc7`
- `OLEAUT32!__imp_SysFreeString` at `0x180005cc7`

## pseudocode

```c
__int64 __fastcall CRootCause::Initialize(CRootCause *this, struct IXMLDOMDocument2 *a2)
{
  int Node; // eax
  struct IXMLDOMNode *v5; // r14
  int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v10; // rsi
  int v11; // eax
  int v12; // r9d
  int v13; // r8d
  BSTR v14; // rax
  HANDLE v15; // rax
  int v16; // r9d
  int v17; // r8d
  int v18; // eax
  BSTR bstrString; // [rsp+60h] [rbp+18h] BYREF
  struct IXMLDOMNode *v21; // [rsp+68h] [rbp+20h] BYREF

  v21 = 0;
  bstrString = 0;
  Node = SdpXmlGetNode(L"./ID", 0, a2, &v21);
  v5 = v21;
  v6 = Node;
  if ( Node < 0 )
  {
    v7 = 75;
LABEL_3:
    v8 = Node;
LABEL_4:
    SdpDebugTrace(1u, L"CRootCause::SchdpInitializeIdentification", v7, v8);
    goto LABEL_15;
  }
  Node = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v21->lpVtbl->get_text)(v21, &bstrString);
  v6 = Node;
  if ( Node < 0 )
  {
    v7 = 78;
    goto LABEL_3;
  }
  ProcessHeap = GetProcessHeap();
  v10 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( !v10 )
  {
    v8 = -2147024882;
    v7 = 80;
    v6 = -2147024882;
    goto LABEL_4;
  }
  v11 = StringCchPrintfW(v10, 0x104u, L"%s/%s", bstrString, L"DefaultInstanceId");
  v6 = v11;
  if ( v11 < 0 )
  {
    v12 = v11;
    v13 = 87;
LABEL_13:
    SdpDebugTrace(1u, L"CRootCause::SchdpInitializeIdentification", v13, v12);
    goto LABEL_14;
  }
  v14 = SysAllocString(v10);
  *(_QWORD *)this = v14;
  if ( !v14 )
  {
    v12 = -2147024882;
    v13 = 90;
    v6 = -2147024882;
    goto LABEL_13;
  }
LABEL_14:
  v15 = GetProcessHeap();
  HeapFree(v15, 0, v10);
LABEL_15:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v5->lpVtbl->Release)(v5);
  if ( v6 < 0 )
  {
    v16 = v6;
    v17 = 572;
LABEL_28:
    SdpDebugTrace(1u, L"CRootCause::Initialize", v17, v16);
    return (unsigned int)v6;
  }
  v18 = CRootCause::SchdpInitializeDisplayInformation(this, (struct IXMLDOMNode *)a2);
  v6 = v18;
  if ( v18 < 0 )
  {
    v17 = 575;
LABEL_27:
    v16 = v18;
    goto LABEL_28;
  }
  v18 = CRootCause::SchdpInitializeNotification(this, a2);
  v6 = v18;
  if ( v18 < 0 )
  {
    v17 = 578;
    goto LABEL_27;
  }
  v18 = CRootCause::SchdpInitializeResolutions(this, (struct IXMLDOMNode *)a2);
  v6 = v18;
  if ( v18 < 0 )
  {
    v17 = 581;
    goto LABEL_27;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005b70  mov     rax, rsp
0x180005b73  mov     [rax+8], rbx
0x180005b77  mov     [rax+10h], rbp
0x180005b7b  push    rsi
0x180005b7c  push    r14
0x180005b7e  push    r15
0x180005b80  sub     rsp, 30h
0x180005b84  and     qword ptr [rax+20h], 0
0x180005b89  lea     r9, [rax+20h]; struct IXMLDOMNode **
0x180005b8d  and     qword ptr [rax+18h], 0
0x180005b92  mov     rbp, rdx
0x180005b95  mov     r15, rcx
0x180005b98  mov     r8, rdx; struct IXMLDOMNode *
0x180005b9b  xor     edx, edx; struct IXMLDOMDocument2 *
0x180005b9d  lea     rcx, aId; "./ID"
0x180005ba4  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x180005ba9  mov     r14, [rsp+48h+arg_18]
0x180005bae  mov     ebx, eax
0x180005bb0  test    eax, eax
0x180005bb2  jns     short loc_180005BD3
0x180005bb4  mov     r8d, 4Bh ; 'K'; int
0x180005bba  mov     r9d, eax; int
0x180005bbd  lea     rdx, aCrootcauseSchd_1; "CRootCause::SchdpInitializeIdentificati"...
0x180005bc4  mov     ecx, 1; Level
0x180005bc9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180005bce  jmp     loc_180005CBD
0x180005bd3  mov     rax, [r14]
0x180005bd6  lea     rdx, [rsp+48h+bstrString]
0x180005bdb  mov     rcx, r14
0x180005bde  mov     rax, [rax+0D0h]
0x180005be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bea  mov     ebx, eax
0x180005bec  test    eax, eax
0x180005bee  jns     short loc_180005BF8
0x180005bf0  mov     r8d, 4Eh ; 'N'
0x180005bf6  jmp     short loc_180005BBA
0x180005bf8  call    cs:__imp_GetProcessHeap
0x180005bff  nop     dword ptr [rax+rax+00h]
0x180005c04  xor     edx, edx; dwFlags
0x180005c06  mov     r8d, 208h; dwBytes
0x180005c0c  mov     rcx, rax; hHeap
0x180005c0f  call    cs:__imp_HeapAlloc
0x180005c16  nop     dword ptr [rax+rax+00h]
0x180005c1b  mov     rsi, rax
0x180005c1e  test    rax, rax
0x180005c21  jnz     short loc_180005C32
0x180005c23  mov     r9d, 8007000Eh
0x180005c29  lea     r8d, [rax+50h]
0x180005c2d  mov     ebx, r9d
0x180005c30  jmp     short loc_180005BBD
0x180005c32  mov     r9, [rsp+48h+bstrString]
0x180005c37  lea     rax, aDefaultinstanc; "DefaultInstanceId"
0x180005c3e  lea     r8, aSS_0; "%s/%s"
0x180005c45  mov     [rsp+48h+var_28], rax
0x180005c4a  mov     edx, 104h; unsigned __int64
0x180005c4f  mov     rcx, rsi; unsigned __int16 *
0x180005c52  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005c57  mov     ebx, eax
0x180005c59  test    eax, eax
0x180005c5b  jns     short loc_180005C68
0x180005c5d  mov     r9d, eax
0x180005c60  mov     r8d, 57h ; 'W'
0x180005c66  jmp     short loc_180005C8C
0x180005c68  mov     rcx, rsi; psz
0x180005c6b  call    cs:__imp_SysAllocString
0x180005c72  nop     dword ptr [rax+rax+00h]
0x180005c77  mov     [r15], rax
0x180005c7a  test    rax, rax
0x180005c7d  jnz     short loc_180005C9D
0x180005c7f  mov     r9d, 8007000Eh; int
0x180005c85  lea     r8d, [rax+5Ah]; int
0x180005c89  mov     ebx, r9d
0x180005c8c  lea     rdx, aCrootcauseSchd_1; "CRootCause::SchdpInitializeIdentificati"...
0x180005c93  mov     ecx, 1; Level
0x180005c98  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180005c9d  call    cs:__imp_GetProcessHeap
0x180005ca4  nop     dword ptr [rax+rax+00h]
0x180005ca9  mov     r8, rsi; lpMem
0x180005cac  xor     edx, edx; dwFlags
0x180005cae  mov     rcx, rax; hHeap
0x180005cb1  call    cs:__imp_HeapFree
0x180005cb8  nop     dword ptr [rax+rax+00h]
0x180005cbd  mov     rcx, [rsp+48h+bstrString]; bstrString
0x180005cc2  test    rcx, rcx
0x180005cc5  jz      short loc_180005CD9
0x180005cc7  call    cs:__imp_SysFreeString
0x180005cce  nop     dword ptr [rax+rax+00h]
0x180005cd3  and     [rsp+48h+bstrString], 0
0x180005cd9  test    r14, r14
0x180005cdc  jz      short loc_180005CED
0x180005cde  mov     rax, [r14]
0x180005ce1  mov     rcx, r14
0x180005ce4  mov     rax, [rax+10h]
0x180005ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ced  test    ebx, ebx
0x180005cef  jns     short loc_180005CFC
0x180005cf1  mov     r9d, ebx
0x180005cf4  mov     r8d, 23Ch
0x180005cfa  jmp     short loc_180005D48
0x180005cfc  mov     rdx, rbp; struct IXMLDOMNode *
0x180005cff  mov     rcx, r15; this
0x180005d02  call    ?SchdpInitializeDisplayInformation@CRootCause@@AEAAJPEAUIXMLDOMNode@@@Z; CRootCause::SchdpInitializeDisplayInformation(IXMLDOMNode *)
0x180005d07  mov     ebx, eax
0x180005d09  test    eax, eax
0x180005d0b  jns     short loc_180005D15
0x180005d0d  mov     r8d, 23Fh
0x180005d13  jmp     short loc_180005D45
0x180005d15  mov     rdx, rbp; struct IXMLDOMNode *
0x180005d18  mov     rcx, r15; this
0x180005d1b  call    ?SchdpInitializeNotification@CRootCause@@AEAAJPEAUIXMLDOMNode@@@Z; CRootCause::SchdpInitializeNotification(IXMLDOMNode *)
0x180005d20  mov     ebx, eax
0x180005d22  test    eax, eax
0x180005d24  jns     short loc_180005D2E
0x180005d26  mov     r8d, 242h
0x180005d2c  jmp     short loc_180005D45
0x180005d2e  mov     rdx, rbp; struct IXMLDOMNode *
0x180005d31  mov     rcx, r15; this
0x180005d34  call    ?SchdpInitializeResolutions@CRootCause@@AEAAJPEAUIXMLDOMNode@@@Z; CRootCause::SchdpInitializeResolutions(IXMLDOMNode *)
0x180005d39  mov     ebx, eax
0x180005d3b  test    eax, eax
0x180005d3d  jns     short loc_180005D59
0x180005d3f  mov     r8d, 245h; int
0x180005d45  mov     r9d, eax; int
0x180005d48  lea     rdx, aCrootcauseInit; "CRootCause::Initialize"
0x180005d4f  mov     ecx, 1; Level
0x180005d54  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180005d59  mov     rbp, [rsp+48h+arg_8]
0x180005d5e  mov     eax, ebx
0x180005d60  mov     rbx, [rsp+48h+arg_0]
0x180005d65  add     rsp, 30h
0x180005d69  pop     r15
0x180005d6b  pop     r14
0x180005d6d  pop     rsi
0x180005d6e  retn
```
