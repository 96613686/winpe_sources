# CResolution::Initialize(ushort *,IXMLDOMNode *)

- ea: `0x180006ba8`
- end: `0x180006f1a`
- name: `?Initialize@CResolution@@QEAAJPEAGPEAUIXMLDOMNode@@@Z`
- size: `882`
- prototype: `int(CResolution *__hidden this, unsigned __int16 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800060bc`

## callees

- `0x1800066f4`
- `0x180006ba8`
- `0x18000b13c`
- `0x18000b608`
- `0x18000d010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180006e03`
- `msvcrt!_wcsicmp` at `0x180006e23`
- `msvcrt!_wcsicmp` at `0x180006e03`
- `msvcrt!_wcsicmp` at `0x180006e23`
- `KERNEL32!HeapFree` at `0x180006ef3`
- `KERNEL32!HeapFree` at `0x180006ef3`
- `KERNEL32!GetProcessHeap` at `0x180006c50`
- `KERNEL32!GetProcessHeap` at `0x180006edf`
- `KERNEL32!GetProcessHeap` at `0x180006c50`
- `KERNEL32!GetProcessHeap` at `0x180006edf`
- `KERNEL32!HeapAlloc` at `0x180006c67`
- `KERNEL32!HeapAlloc` at `0x180006c67`
- `OLEAUT32!__imp_SysAllocString` at `0x180006cbf`
- `OLEAUT32!__imp_SysAllocString` at `0x180006cbf`
- `OLEAUT32!__imp_SysFreeString` at `0x180006e98`
- `OLEAUT32!__imp_SysFreeString` at `0x180006eb1`
- `OLEAUT32!__imp_SysFreeString` at `0x180006eca`
- `OLEAUT32!__imp_SysFreeString` at `0x180006e98`
- `OLEAUT32!__imp_SysFreeString` at `0x180006eb1`
- `OLEAUT32!__imp_SysFreeString` at `0x180006eca`

## pseudocode

```c
__int64 __fastcall CResolution::Initialize(CResolution *this, unsigned __int16 *a2, struct IXMLDOMDocument2 *a3)
{
  struct IXMLDOMNode *v3; // r15
  struct IXMLDOMNode *v4; // rsi
  struct IXMLDOMNode *v5; // r14
  int v6; // edi
  unsigned __int16 *v7; // r12
  int Node; // eax
  unsigned int v10; // ebx
  int v11; // r8d
  int v12; // r9d
  HANDLE ProcessHeap; // rax
  BSTR v14; // rax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // r13d
  HANDLE v19; // rax
  wchar_t *String1; // [rsp+30h] [rbp-30h] BYREF
  BSTR v22; // [rsp+38h] [rbp-28h] BYREF
  struct IXMLDOMNode *v23; // [rsp+40h] [rbp-20h] BYREF
  struct IXMLDOMNode *v24; // [rsp+48h] [rbp-18h] BYREF
  struct IXMLDOMNode *v25; // [rsp+50h] [rbp-10h] BYREF
  struct IXMLDOMNode *v26; // [rsp+58h] [rbp-8h] BYREF
  BSTR bstrString; // [rsp+B8h] [rbp+58h] BYREF

  v25 = 0;
  v3 = 0;
  v23 = 0;
  v4 = 0;
  v26 = 0;
  v5 = 0;
  v6 = 1;
  v24 = 0;
  bstrString = 0;
  v7 = 0;
  String1 = 0;
  v22 = 0;
  Node = SdpXmlGetNode(L"./ID", 0, a3, &v25);
  v10 = Node;
  if ( Node < 0 )
  {
    v11 = 76;
LABEL_3:
    v12 = Node;
LABEL_4:
    SdpDebugTrace(1u, L"CResolution::Initialize", v11, v12);
    goto LABEL_30;
  }
  Node = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v25->lpVtbl->get_text)(v25, &bstrString);
  v10 = Node;
  if ( Node < 0 )
  {
    v11 = 79;
    goto LABEL_3;
  }
  ProcessHeap = GetProcessHeap();
  v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( !v7 )
  {
    v12 = -2147024882;
    v11 = 81;
    v10 = -2147024882;
    goto LABEL_4;
  }
  Node = StringCchPrintfW(v7, 0x104u, L"%s/%s", a2, bstrString);
  v10 = Node;
  if ( Node < 0 )
  {
    v11 = 89;
    goto LABEL_3;
  }
  v14 = SysAllocString(v7);
  *(_QWORD *)this = v14;
  if ( !v14 )
  {
    v12 = -2147024882;
    v11 = 92;
    v10 = -2147024882;
    goto LABEL_4;
  }
  v15 = SdpXmlGetNode(L"./RequiresConsent", 0, a3, &v23);
  v10 = v15;
  if ( v15 >= 0 )
  {
    v3 = v23;
    Node = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))v23->lpVtbl->get_text)(v23, &String1);
    v10 = Node;
    if ( Node < 0 )
    {
      v11 = 101;
      goto LABEL_3;
    }
    v16 = SdpXmlGetNode(L"./Script", 0, a3, &v24);
    v10 = v16;
    if ( v16 >= 0 )
    {
      v5 = v24;
      v17 = SdpXmlGetNode(L"./RequiresInteractivity", 0, (struct IXMLDOMDocument2 *)v24, &v26);
      v10 = v17;
      if ( v17 < 0 )
      {
        SdpDebugTrace(2u, L"CResolution::Initialize", 113, v17);
        v10 = 0;
      }
      v4 = v26;
      if ( v26 )
      {
        v18 = 0;
        Node = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v26->lpVtbl->get_text)(v26, &v22);
        v10 = Node;
        if ( Node < 0 )
        {
          v11 = 123;
          goto LABEL_3;
        }
      }
      else
      {
        v18 = 1;
      }
      if ( _wcsicmp(String1, L"FALSE") || v18 || _wcsicmp(v22, L"FALSE") )
        v6 = 0;
      *((_DWORD *)this + 2) = v6;
    }
    else
    {
      SdpDebugTrace(1u, L"CResolution::Initialize", 107, v16);
      v5 = v24;
    }
  }
  else
  {
    SdpDebugTrace(1u, L"CResolution::Initialize", 98, v15);
    v3 = v23;
  }
LABEL_30:
  if ( v25 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v25->lpVtbl->Release)(v25);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v3->lpVtbl->Release)(v3);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v5->lpVtbl->Release)(v5);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( String1 )
  {
    SysFreeString(String1);
    String1 = 0;
  }
  if ( v22 )
  {
    SysFreeString(v22);
    v22 = 0;
  }
  if ( v7 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v7);
  }
  return v10;
}

```

## disassembly

```asm
0x180006ba8  mov     [rsp-38h+arg_10], rbx
0x180006bad  mov     [rsp-38h+arg_8], rdx
0x180006bb2  mov     [rsp-38h+arg_0], rcx
0x180006bb7  push    rbp
0x180006bb8  push    rsi
0x180006bb9  push    rdi
0x180006bba  push    r12
0x180006bbc  push    r13
0x180006bbe  push    r14
0x180006bc0  push    r15
0x180006bc2  mov     rbp, rsp
0x180006bc5  sub     rsp, 60h
0x180006bc9  xor     ecx, ecx
0x180006bcb  lea     r9, [rbp+var_10]; struct IXMLDOMNode **
0x180006bcf  mov     [rbp+var_10], rcx
0x180006bd3  mov     r15d, ecx
0x180006bd6  mov     [rbp+var_20], rcx
0x180006bda  mov     esi, ecx
0x180006bdc  mov     [rbp+var_8], rcx
0x180006be0  mov     r14d, ecx
0x180006be3  lea     edi, [rcx+1]
0x180006be6  mov     [rbp+var_18], rcx
0x180006bea  mov     [rbp+bstrString], rcx
0x180006bee  mov     r12d, ecx
0x180006bf1  mov     [rbp+String1], rcx
0x180006bf5  xor     edx, edx; struct IXMLDOMDocument2 *
0x180006bf7  mov     [rbp+var_28], rcx
0x180006bfb  mov     r13, r8
0x180006bfe  lea     rcx, aId; "./ID"
0x180006c05  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x180006c0a  mov     ebx, eax
0x180006c0c  test    eax, eax
0x180006c0e  jns     short loc_180006C2B
0x180006c10  lea     r8d, [r12+4Ch]; int
0x180006c15  mov     r9d, eax; int
0x180006c18  lea     rdx, aCresolutionIni; "CResolution::Initialize"
0x180006c1f  mov     ecx, edi; Level
0x180006c21  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006c26  jmp     loc_180006E3C
0x180006c2b  mov     rcx, [rbp+var_10]
0x180006c2f  lea     rdx, [rbp+bstrString]
0x180006c33  mov     rax, [rcx]
0x180006c36  mov     rax, [rax+0D0h]
0x180006c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c42  mov     ebx, eax
0x180006c44  test    eax, eax
0x180006c46  jns     short loc_180006C50
0x180006c48  mov     r8d, 4Fh ; 'O'
0x180006c4e  jmp     short loc_180006C15
0x180006c50  call    cs:__imp_GetProcessHeap
0x180006c57  nop     dword ptr [rax+rax+00h]
0x180006c5c  xor     edx, edx; dwFlags
0x180006c5e  mov     r8d, 208h; dwBytes
0x180006c64  mov     rcx, rax; hHeap
0x180006c67  call    cs:__imp_HeapAlloc
0x180006c6e  nop     dword ptr [rax+rax+00h]
0x180006c73  mov     r12, rax
0x180006c76  test    rax, rax
0x180006c79  jnz     short loc_180006C8A
0x180006c7b  mov     r9d, 8007000Eh
0x180006c81  lea     r8d, [rax+51h]
0x180006c85  mov     ebx, r9d
0x180006c88  jmp     short loc_180006C18
0x180006c8a  mov     rax, [rbp+bstrString]
0x180006c8e  lea     r8, aSS_0; "%s/%s"
0x180006c95  mov     r9, [rbp+arg_8]
0x180006c99  mov     edx, 104h; unsigned __int64
0x180006c9e  mov     rcx, r12; unsigned __int16 *
0x180006ca1  mov     [rsp+60h+var_40], rax
0x180006ca6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006cab  mov     ebx, eax
0x180006cad  test    eax, eax
0x180006caf  jns     short loc_180006CBC
0x180006cb1  mov     r8d, 59h ; 'Y'
0x180006cb7  jmp     loc_180006C15
0x180006cbc  mov     rcx, r12; psz
0x180006cbf  call    cs:__imp_SysAllocString
0x180006cc6  nop     dword ptr [rax+rax+00h]
0x180006ccb  mov     rcx, [rbp+arg_0]
0x180006ccf  mov     [rcx], rax
0x180006cd2  test    rax, rax
0x180006cd5  jnz     short loc_180006CE9
0x180006cd7  mov     r9d, 8007000Eh
0x180006cdd  lea     r8d, [rax+5Ch]
0x180006ce1  mov     ebx, r9d
0x180006ce4  jmp     loc_180006C18
0x180006ce9  lea     r9, [rbp+var_20]; struct IXMLDOMNode **
0x180006ced  mov     r8, r13; struct IXMLDOMNode *
0x180006cf0  xor     edx, edx; struct IXMLDOMDocument2 *
0x180006cf2  lea     rcx, aRequiresconsen; "./RequiresConsent"
0x180006cf9  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x180006cfe  mov     ebx, eax
0x180006d00  test    eax, eax
0x180006d02  jns     short loc_180006D24
0x180006d04  mov     r9d, eax; int
0x180006d07  lea     rdx, aCresolutionIni; "CResolution::Initialize"
0x180006d0e  mov     r8d, 62h ; 'b'; int
0x180006d14  mov     ecx, edi; Level
0x180006d16  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006d1b  mov     r15, [rbp+var_20]
0x180006d1f  jmp     loc_180006E3C
0x180006d24  mov     r15, [rbp+var_20]
0x180006d28  lea     rdx, [rbp+String1]
0x180006d2c  mov     rcx, r15
0x180006d2f  mov     rax, [r15]
0x180006d32  mov     rax, [rax+0D0h]
0x180006d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d3e  mov     ebx, eax
0x180006d40  test    eax, eax
0x180006d42  jns     short loc_180006D4F
0x180006d44  mov     r8d, 65h ; 'e'
0x180006d4a  jmp     loc_180006C15
0x180006d4f  lea     r9, [rbp+var_18]; struct IXMLDOMNode **
0x180006d53  mov     r8, r13; struct IXMLDOMNode *
0x180006d56  xor     edx, edx; struct IXMLDOMDocument2 *
0x180006d58  lea     rcx, aScript; "./Script"
0x180006d5f  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x180006d64  mov     ebx, eax
0x180006d66  test    eax, eax
0x180006d68  jns     short loc_180006D8A
0x180006d6a  mov     r9d, eax; int
0x180006d6d  lea     rdx, aCresolutionIni; "CResolution::Initialize"
0x180006d74  mov     r8d, 6Bh ; 'k'; int
0x180006d7a  mov     ecx, edi; Level
0x180006d7c  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006d81  mov     r14, [rbp+var_18]
0x180006d85  jmp     loc_180006E3C
0x180006d8a  mov     r14, [rbp+var_18]
0x180006d8e  lea     r9, [rbp+var_8]; struct IXMLDOMNode **
0x180006d92  mov     r8, r14; struct IXMLDOMNode *
0x180006d95  lea     rcx, aRequiresintera; "./RequiresInteractivity"
0x180006d9c  xor     edx, edx; struct IXMLDOMDocument2 *
0x180006d9e  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x180006da3  mov     ebx, eax
0x180006da5  test    eax, eax
0x180006da7  jns     short loc_180006DC4
0x180006da9  mov     r8d, 71h ; 'q'; int
0x180006daf  lea     rdx, aCresolutionIni; "CResolution::Initialize"
0x180006db6  mov     r9d, eax; int
0x180006db9  lea     ecx, [r8-6Fh]; Level
0x180006dbd  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006dc2  xor     ebx, ebx
0x180006dc4  mov     rsi, [rbp+var_8]
0x180006dc8  test    rsi, rsi
0x180006dcb  jz      short loc_180006DF5
0x180006dcd  mov     rax, [rsi]
0x180006dd0  lea     rdx, [rbp+var_28]
0x180006dd4  mov     rcx, rsi
0x180006dd7  xor     r13d, r13d
0x180006dda  mov     rax, [rax+0D0h]
0x180006de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006de6  mov     ebx, eax
0x180006de8  test    eax, eax
0x180006dea  jns     short loc_180006DF8
0x180006dec  lea     r8d, [r13+7Bh]
0x180006df0  jmp     loc_180006C15
0x180006df5  mov     r13d, edi
0x180006df8  mov     rcx, [rbp+String1]; String1
0x180006dfc  lea     rdx, aFalse; "FALSE"
0x180006e03  call    cs:__imp__wcsicmp
0x180006e0a  nop     dword ptr [rax+rax+00h]
0x180006e0f  test    eax, eax
0x180006e11  jnz     short loc_180006E33
0x180006e13  test    r13d, r13d
0x180006e16  jnz     short loc_180006E33
0x180006e18  mov     rcx, [rbp+var_28]; String1
0x180006e1c  lea     rdx, aFalse; "FALSE"
0x180006e23  call    cs:__imp__wcsicmp
0x180006e2a  nop     dword ptr [rax+rax+00h]
0x180006e2f  test    eax, eax
0x180006e31  jz      short loc_180006E35
0x180006e33  xor     edi, edi
0x180006e35  mov     rax, [rbp+arg_0]
0x180006e39  mov     [rax+8], edi
0x180006e3c  mov     rcx, [rbp+var_10]
0x180006e40  xor     edi, edi
0x180006e42  test    rcx, rcx
0x180006e45  jz      short loc_180006E53
0x180006e47  mov     rax, [rcx]
0x180006e4a  mov     rax, [rax+10h]
0x180006e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e53  test    r15, r15
0x180006e56  jz      short loc_180006E67
0x180006e58  mov     rax, [r15]
0x180006e5b  mov     rcx, r15
0x180006e5e  mov     rax, [rax+10h]
0x180006e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e67  test    rsi, rsi
0x180006e6a  jz      short loc_180006E7B
0x180006e6c  mov     rax, [rsi]
0x180006e6f  mov     rcx, rsi
0x180006e72  mov     rax, [rax+10h]
0x180006e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e7b  test    r14, r14
0x180006e7e  jz      short loc_180006E8F
0x180006e80  mov     rax, [r14]
0x180006e83  mov     rcx, r14
0x180006e86  mov     rax, [rax+10h]
0x180006e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e8f  mov     rcx, [rbp+bstrString]; bstrString
0x180006e93  test    rcx, rcx
0x180006e96  jz      short loc_180006EA8
0x180006e98  call    cs:__imp_SysFreeString
0x180006e9f  nop     dword ptr [rax+rax+00h]
0x180006ea4  mov     [rbp+bstrString], rdi
0x180006ea8  mov     rcx, [rbp+String1]; bstrString
0x180006eac  test    rcx, rcx
0x180006eaf  jz      short loc_180006EC1
0x180006eb1  call    cs:__imp_SysFreeString
0x180006eb8  nop     dword ptr [rax+rax+00h]
0x180006ebd  mov     [rbp+String1], rdi
0x180006ec1  mov     rcx, [rbp+var_28]; bstrString
0x180006ec5  test    rcx, rcx
0x180006ec8  jz      short loc_180006EDA
0x180006eca  call    cs:__imp_SysFreeString
0x180006ed1  nop     dword ptr [rax+rax+00h]
0x180006ed6  mov     [rbp+var_28], rdi
0x180006eda  test    r12, r12
0x180006edd  jz      short loc_180006EFF
0x180006edf  call    cs:__imp_GetProcessHeap
0x180006ee6  nop     dword ptr [rax+rax+00h]
0x180006eeb  mov     r8, r12; lpMem
0x180006eee  xor     edx, edx; dwFlags
0x180006ef0  mov     rcx, rax; hHeap
0x180006ef3  call    cs:__imp_HeapFree
0x180006efa  nop     dword ptr [rax+rax+00h]
0x180006eff  mov     eax, ebx
0x180006f01  mov     rbx, [rsp+60h+arg_10]
0x180006f09  add     rsp, 60h
0x180006f0d  pop     r15
0x180006f0f  pop     r14
0x180006f11  pop     r13
0x180006f13  pop     r12
0x180006f15  pop     rdi
0x180006f16  pop     rsi
0x180006f17  pop     rbp
0x180006f18  retn
```
