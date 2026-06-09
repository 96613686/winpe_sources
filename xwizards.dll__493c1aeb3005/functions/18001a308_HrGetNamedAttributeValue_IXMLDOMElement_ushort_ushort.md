# HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)

- ea: `0x18001a308`
- end: `0x18001a4ac`
- name: `?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z`
- size: `420`
- prototype: `int(struct IXMLDOMElement *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180012a64`
- `0x180013994`
- `0x180014248`
- `0x180014724`
- `0x180014c80`
- `0x180014f08`

## callees

- `0x18000ae04`
- `0x18001a308`
- `0x180034010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001a332`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a332`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a3a4`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a3a4`
- `OLEAUT32!__imp_VariantInit` at `0x18001a40b`
- `OLEAUT32!__imp_VariantInit` at `0x18001a40b`

## pseudocode

```c
__int64 __fastcall HrGetNamedAttributeValue(struct IXMLDOMElement *a1, unsigned __int16 *a2, unsigned __int16 **a3)
{
  OLECHAR *v5; // rdi
  struct IXMLDOMElementVtbl *lpVtbl; // rax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  pvarg.pRecInfo = 0;
  *a3 = 0;
  *(_OWORD *)&pvarg.vt = 0;
  v5 = SysAllocString(a2);
  if ( v5 )
  {
    lpVtbl = a1->lpVtbl;
    v12 = 0;
    v8 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, OLECHAR *, __int64 *))lpVtbl->getAttributeNode)(a1, v5, &v12);
    SysFreeString(v5);
    if ( v8 )
    {
      if ( (v8 & 0x80000000) == 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          return v8;
        v10 = 12;
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          return v8;
        v10 = 11;
      }
    }
    else
    {
      VariantInit(&pvarg);
      v8 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v12 + 352LL))(v12, &pvarg);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      if ( (v8 & 0x80000000) == 0 )
      {
        *a3 = pvarg.bstrVal;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          return v8;
        v10 = 14;
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          return v8;
        v10 = 13;
      }
    }
    WPP_SF_d(v9[2], v10, WPP_0fce6e367d1735e30e776fb70888306d_Traceguids, v8);
    return v8;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0fce6e367d1735e30e776fb70888306d_Traceguids, 2147942414LL);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001a308  mov     [rsp+arg_0], rbx
0x18001a30d  mov     [rsp+arg_8], rsi
0x18001a312  push    rdi
0x18001a313  sub     rsp, 40h
0x18001a317  xor     eax, eax
0x18001a319  mov     rbx, rcx
0x18001a31c  xorps   xmm0, xmm0
0x18001a31f  mov     qword ptr [rsp+48h+pvarg+10h], rax
0x18001a324  mov     rcx, rdx; psz
0x18001a327  mov     [r8], rax
0x18001a32a  movups  xmmword ptr [rsp+48h+pvarg], xmm0
0x18001a32f  mov     rsi, r8
0x18001a332  call    cs:__imp_SysAllocString
0x18001a338  mov     rdi, rax
0x18001a33b  test    rax, rax
0x18001a33e  jnz     short loc_18001A37C
0x18001a340  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a347  lea     rax, WPP_GLOBAL_Control
0x18001a34e  cmp     rcx, rax
0x18001a351  jz      short loc_18001A372
0x18001a353  test    byte ptr [rcx+1Ch], 4
0x18001a357  jz      short loc_18001A372
0x18001a359  mov     rcx, [rcx+10h]
0x18001a35d  lea     edx, [rdi+0Ah]
0x18001a360  mov     r9d, 8007000Eh
0x18001a366  lea     r8, WPP_0fce6e367d1735e30e776fb70888306d_Traceguids
0x18001a36d  call    WPP_SF_d
0x18001a372  mov     eax, 8007000Eh
0x18001a377  jmp     loc_18001A49C
0x18001a37c  mov     rax, [rbx]
0x18001a37f  lea     r8, [rsp+48h+arg_10]
0x18001a384  mov     rdx, rdi
0x18001a387  mov     [rsp+48h+arg_10], 0
0x18001a390  mov     rcx, rbx
0x18001a393  mov     rax, [rax+178h]
0x18001a39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a39f  mov     rcx, rdi; bstrString
0x18001a3a2  mov     ebx, eax
0x18001a3a4  call    cs:__imp_SysFreeString
0x18001a3aa  test    ebx, ebx
0x18001a3ac  jz      short loc_18001A406
0x18001a3ae  jns     short loc_18001A3DB
0x18001a3b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a3b7  lea     rax, WPP_GLOBAL_Control
0x18001a3be  cmp     rcx, rax
0x18001a3c1  jz      loc_18001A49A
0x18001a3c7  test    byte ptr [rcx+1Ch], 4
0x18001a3cb  jz      loc_18001A49A
0x18001a3d1  mov     edx, 0Bh
0x18001a3d6  jmp     loc_18001A487
0x18001a3db  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a3e2  lea     rax, WPP_GLOBAL_Control
0x18001a3e9  cmp     rcx, rax
0x18001a3ec  jz      loc_18001A49A
0x18001a3f2  test    byte ptr [rcx+1Ch], 10h
0x18001a3f6  jz      loc_18001A49A
0x18001a3fc  mov     edx, 0Ch
0x18001a401  jmp     loc_18001A487
0x18001a406  lea     rcx, [rsp+48h+pvarg]; pvarg
0x18001a40b  call    cs:__imp_VariantInit
0x18001a411  mov     rcx, [rsp+48h+arg_10]
0x18001a416  lea     rdx, [rsp+48h+pvarg]
0x18001a41b  mov     rax, [rcx]
0x18001a41e  mov     rax, [rax+160h]
0x18001a425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a42a  mov     rcx, [rsp+48h+arg_10]
0x18001a42f  mov     ebx, eax
0x18001a431  mov     rdx, [rcx]
0x18001a434  mov     rax, [rdx+10h]
0x18001a438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a43d  test    ebx, ebx
0x18001a43f  jns     short loc_18001A461
0x18001a441  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a448  lea     rax, WPP_GLOBAL_Control
0x18001a44f  cmp     rcx, rax
0x18001a452  jz      short loc_18001A49A
0x18001a454  test    byte ptr [rcx+1Ch], 4
0x18001a458  jz      short loc_18001A49A
0x18001a45a  mov     edx, 0Dh
0x18001a45f  jmp     short loc_18001A487
0x18001a461  mov     rax, qword ptr [rsp+48h+pvarg+8]
0x18001a466  mov     [rsi], rax
0x18001a469  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a470  lea     rax, WPP_GLOBAL_Control
0x18001a477  cmp     rcx, rax
0x18001a47a  jz      short loc_18001A49A
0x18001a47c  test    byte ptr [rcx+1Ch], 10h
0x18001a480  jz      short loc_18001A49A
0x18001a482  mov     edx, 0Eh
0x18001a487  mov     rcx, [rcx+10h]
0x18001a48b  lea     r8, WPP_0fce6e367d1735e30e776fb70888306d_Traceguids
0x18001a492  mov     r9d, ebx
0x18001a495  call    WPP_SF_d
0x18001a49a  mov     eax, ebx
0x18001a49c  mov     rbx, [rsp+48h+arg_0]
0x18001a4a1  mov     rsi, [rsp+48h+arg_8]
0x18001a4a6  add     rsp, 40h
0x18001a4aa  pop     rdi
0x18001a4ab  retn
```
