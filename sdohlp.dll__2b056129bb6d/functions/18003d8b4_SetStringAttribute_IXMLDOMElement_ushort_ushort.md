# SetStringAttribute(IXMLDOMElement *,ushort *,ushort *)

- ea: `0x18003d8b4`
- end: `0x18003d9a9`
- name: `?SetStringAttribute@@YAJPEAUIXMLDOMElement@@PEAG1@Z`
- size: `245`
- prototype: `int(struct IXMLDOMElement *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003a880`

## callees

- `0x18002cd00`
- `0x18003d8b4`
- `0x180042a80`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003d8f2`
- `OLEAUT32!__imp_SysAllocString` at `0x18003d8f2`
- `OLEAUT32!__imp_VariantInit` at `0x18003d8df`
- `OLEAUT32!__imp_VariantInit` at `0x18003d8df`
- `OLEAUT32!__imp_VariantClear` at `0x18003d98f`
- `OLEAUT32!__imp_VariantClear` at `0x18003d98f`

## pseudocode

```c
__int64 __fastcall SetStringAttribute(struct IXMLDOMElement *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  HRESULT (__stdcall *setAttribute)(IXMLDOMElement *, BSTR, VARIANT); // rax
  int v8; // ebx
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF
  __int128 v11; // [rsp+50h] [rbp-28h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-18h]

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(a3);
  lpVtbl = a1->lpVtbl;
  pRecInfo = pvarg.pRecInfo;
  setAttribute = lpVtbl->setAttribute;
  v11 = *(_OWORD *)&pvarg.vt;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, unsigned __int16 *, __int128 *))setAttribute)(a1, a2, &v11);
  if ( v8 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("pElement->setAttribute failed with 0x%x", v8);
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
      (unsigned int)"NPSSDO",
      v8);
  }
  VariantClear(&pvarg);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003d8b4  mov     r11, rsp
0x18003d8b7  mov     [r11+8], rbx
0x18003d8bb  mov     [r11+10h], rsi
0x18003d8bf  push    rdi
0x18003d8c0  sub     rsp, 70h
0x18003d8c4  xorps   xmm0, xmm0
0x18003d8c7  mov     rsi, rcx
0x18003d8ca  xor     eax, eax
0x18003d8cc  lea     rcx, [r11-48h]; pvarg
0x18003d8d0  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x18003d8d5  mov     [r11-38h], rax
0x18003d8d9  mov     rbx, r8
0x18003d8dc  mov     rdi, rdx
0x18003d8df  call    cs:__imp_VariantInit
0x18003d8e5  mov     eax, 8
0x18003d8ea  mov     rcx, rbx; psz
0x18003d8ed  mov     word ptr [rsp+78h+pvarg], ax
0x18003d8f2  call    cs:__imp_SysAllocString
0x18003d8f8  movsd   xmm1, qword ptr [rsp+78h+pvarg+10h]
0x18003d8fe  lea     r8, [rsp+78h+var_28]
0x18003d903  mov     qword ptr [rsp+78h+pvarg+8], rax
0x18003d908  mov     rdx, rdi
0x18003d90b  mov     rax, [rsi]
0x18003d90e  mov     rcx, rsi
0x18003d911  movups  xmm0, xmmword ptr [rsp+78h+pvarg]
0x18003d916  movsd   [rsp+78h+var_18], xmm1
0x18003d91c  mov     rax, [rax+168h]
0x18003d923  movaps  [rsp+78h+var_28], xmm0
0x18003d928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d92d  mov     ebx, eax
0x18003d92f  test    eax, eax
0x18003d931  jns     short loc_18003D98A
0x18003d933  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d93a  lea     rax, WPP_GLOBAL_Control
0x18003d941  cmp     rcx, rax
0x18003d944  jz      short loc_18003D98A
0x18003d946  cmp     byte ptr [rcx+19h], 2
0x18003d94a  jb      short loc_18003D98A
0x18003d94c  test    dword ptr [rcx+1Ch], 400h
0x18003d953  jz      short loc_18003D98A
0x18003d955  mov     edx, ebx
0x18003d957  lea     rcx, aPelementSetatt; "pElement->setAttribute failed with 0x%x"
0x18003d95e  call    WppDbgPrint
0x18003d963  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d96a  lea     r9, aNpssdo; "NPSSDO"
0x18003d971  mov     edx, 16h
0x18003d976  mov     [rsp+78h+var_58], ebx
0x18003d97a  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003d981  mov     rcx, [rcx+10h]
0x18003d985  call    WPP_SF_sd
0x18003d98a  lea     rcx, [rsp+78h+pvarg]; pvarg
0x18003d98f  call    cs:__imp_VariantClear
0x18003d995  lea     r11, [rsp+78h+var_8]
0x18003d99a  mov     eax, ebx
0x18003d99c  mov     rbx, [r11+10h]
0x18003d9a0  mov     rsi, [r11+18h]
0x18003d9a4  mov     rsp, r11
0x18003d9a7  pop     rdi
0x18003d9a8  retn
```
