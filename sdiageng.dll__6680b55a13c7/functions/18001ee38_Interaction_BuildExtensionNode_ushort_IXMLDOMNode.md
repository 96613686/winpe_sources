# Interaction::BuildExtensionNode(ushort *,IXMLDOMNode * *)

- ea: `0x18001ee38`
- end: `0x18001f00a`
- name: `?BuildExtensionNode@Interaction@@IEAAJPEAGPEAPEAUIXMLDOMNode@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(Interaction *this, unsigned __int16 *, struct IXMLDOMNode **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180023260`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x18000551c`
- `0x180010e70`
- `0x18001ee38`
- `0x180026fa0`
- `0x1800280f8`
- `0x1800288b8`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001ee67`
- `OLEAUT32!__imp_SysStringLen` at `0x18001ee67`

## string_xrefs

- `0x18001ee97`: `Interaction::BuildExtensionNode`
- `0x18001ef2f`: `Interaction::BuildExtensionNode`
- `0x18001ef68`: `Interaction::BuildExtensionNode`
- `0x18001efb2`: `Interaction::BuildExtensionNode`
- `0x18001eeb4`: `<?xml version="1.0" encoding="utf-8"?><ExtensionPoint>`
- `0x18001eef6`: `</ExtensionPoint>`

## pseudocode

```c
__int64 __fastcall Interaction::BuildExtensionNode(Interaction *this, unsigned __int16 *a2, struct IXMLDOMNode **a3)
{
  struct IXMLDOMDocument2 *v3; // rsi
  struct IXMLDOMElement *v4; // rdi
  unsigned __int64 v7; // r14
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbp
  unsigned int v10; // ebx
  int v11; // eax
  int v12; // r8d
  int v13; // eax
  int RootNode; // eax
  struct IXMLDOMDocument2 *v16; // [rsp+60h] [rbp+8h] BYREF
  struct IXMLDOMElement *v17; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  v4 = 0;
  v16 = 0;
  v17 = 0;
  v7 = SysStringLen(a2) + 72LL;
  v8 = (unsigned __int16 *)operator new[](saturated_mul(v7, 2u));
  v9 = v8;
  if ( !v8 )
  {
    v10 = -2147024882;
    SdpDebugTrace(1u, L"Interaction::BuildExtensionNode", 843, -2147024882);
    return v10;
  }
  v11 = StringCchCopyW(v8, v7, L"<?xml version=\"1.0\" encoding=\"utf-8\"?><ExtensionPoint>");
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 851;
LABEL_15:
    SdpDebugTrace(1u, L"Interaction::BuildExtensionNode", v12, v11);
    goto LABEL_16;
  }
  v11 = StringCchCatW(v9, v7, a2);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 856;
    goto LABEL_15;
  }
  v11 = StringCchCatW(v9, v7, L"</ExtensionPoint>");
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 861;
    goto LABEL_15;
  }
  v13 = SdpXmlCreate(v9, &v16);
  v10 = v13;
  if ( v13 >= 0 )
  {
    v3 = v16;
    RootNode = SdpXmlGetRootNode(v16, &v17);
    v10 = RootNode;
    if ( RootNode >= 0 )
    {
      v4 = v17;
      v11 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, __int64, struct IXMLDOMNode **))v17->lpVtbl->cloneNode)(
              v17,
              0xFFFFFFFFLL,
              a3);
      v10 = v11;
      if ( v11 < 0 )
      {
        v12 = 870;
        goto LABEL_15;
      }
    }
    else
    {
      SdpDebugTrace(1u, L"Interaction::BuildExtensionNode", 867, RootNode);
      v4 = v17;
    }
  }
  else
  {
    SdpDebugTrace(1u, L"Interaction::BuildExtensionNode", 864, v13);
    v3 = v16;
  }
LABEL_16:
  operator delete(v9);
  if ( v3 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v3->lpVtbl->Release)(v3);
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v4->lpVtbl->Release)(v4);
  return v10;
}

```

## disassembly

```asm
0x18001ee38  mov     rax, rsp
0x18001ee3b  mov     [rax+10h], rbx
0x18001ee3f  mov     [rax+8], rcx
0x18001ee43  push    rbp
0x18001ee44  push    rsi
0x18001ee45  push    rdi
0x18001ee46  push    r12
0x18001ee48  push    r13
0x18001ee4a  push    r14
0x18001ee4c  push    r15
0x18001ee4e  sub     rsp, 20h
0x18001ee52  xor     esi, esi
0x18001ee54  xor     edi, edi
0x18001ee56  mov     rcx, rdx; pbstr
0x18001ee59  mov     [rax+8], rsi
0x18001ee5d  mov     [rax+20h], rdi
0x18001ee61  mov     r12, r8
0x18001ee64  mov     r15, rdx
0x18001ee67  call    cs:__imp_SysStringLen
0x18001ee6d  mov     r14d, eax
0x18001ee70  lea     r13, [rsi-1]
0x18001ee74  add     r14, 48h ; 'H'
0x18001ee78  lea     eax, [rsi+2]
0x18001ee7b  mul     r14
0x18001ee7e  cmovb   rax, r13
0x18001ee82  mov     rcx, rax; unsigned __int64
0x18001ee85  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001ee8a  mov     rbp, rax
0x18001ee8d  test    rax, rax
0x18001ee90  jnz     short loc_18001EEB4
0x18001ee92  mov     ebx, 8007000Eh
0x18001ee97  lea     rdx, aInteractionBui_1; "Interaction::BuildExtensionNode"
0x18001ee9e  mov     r9d, ebx; int
0x18001eea1  lea     ecx, [rsi+1]; Level
0x18001eea4  mov     r8d, 34Bh; int
0x18001eeaa  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001eeaf  jmp     loc_18001EFF3
0x18001eeb4  lea     r8, aXmlVersion10En_6; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18001eebb  mov     rdx, r14; unsigned __int64
0x18001eebe  mov     rcx, rbp; unsigned __int16 *
0x18001eec1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001eec6  mov     ebx, eax
0x18001eec8  test    eax, eax
0x18001eeca  jns     short loc_18001EED7
0x18001eecc  mov     r8d, 353h
0x18001eed2  jmp     loc_18001EFAF
0x18001eed7  mov     r8, r15; unsigned __int16 *
0x18001eeda  mov     rdx, r14; unsigned __int64
0x18001eedd  mov     rcx, rbp; unsigned __int16 *
0x18001eee0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001eee5  mov     ebx, eax
0x18001eee7  test    eax, eax
0x18001eee9  jns     short loc_18001EEF6
0x18001eeeb  mov     r8d, 358h
0x18001eef1  jmp     loc_18001EFAF
0x18001eef6  lea     r8, aExtensionpoint; "</ExtensionPoint>"
0x18001eefd  mov     rdx, r14; unsigned __int64
0x18001ef00  mov     rcx, rbp; unsigned __int16 *
0x18001ef03  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001ef08  mov     ebx, eax
0x18001ef0a  test    eax, eax
0x18001ef0c  jns     short loc_18001EF19
0x18001ef0e  mov     r8d, 35Dh
0x18001ef14  jmp     loc_18001EFAF
0x18001ef19  lea     rdx, [rsp+58h+arg_0]; struct IXMLDOMDocument2 **
0x18001ef1e  mov     rcx, rbp; psz
0x18001ef21  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x18001ef26  mov     ebx, eax
0x18001ef28  test    eax, eax
0x18001ef2a  jns     short loc_18001EF4D
0x18001ef2c  mov     r9d, eax; int
0x18001ef2f  lea     rdx, aInteractionBui_1; "Interaction::BuildExtensionNode"
0x18001ef36  mov     r8d, 360h; int
0x18001ef3c  mov     ecx, 1; Level
0x18001ef41  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001ef46  mov     rsi, [rsp+58h+arg_0]
0x18001ef4b  jmp     short loc_18001EFC3
0x18001ef4d  mov     rsi, [rsp+58h+arg_0]
0x18001ef52  lea     rdx, [rsp+58h+arg_18]; struct IXMLDOMElement **
0x18001ef57  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x18001ef5a  call    ?SdpXmlGetRootNode@@YAJPEAUIXMLDOMDocument2@@PEAPEAUIXMLDOMElement@@@Z; SdpXmlGetRootNode(IXMLDOMDocument2 *,IXMLDOMElement * *)
0x18001ef5f  mov     ebx, eax
0x18001ef61  test    eax, eax
0x18001ef63  jns     short loc_18001EF86
0x18001ef65  mov     r9d, eax; int
0x18001ef68  lea     rdx, aInteractionBui_1; "Interaction::BuildExtensionNode"
0x18001ef6f  mov     r8d, 363h; int
0x18001ef75  mov     ecx, 1; Level
0x18001ef7a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001ef7f  mov     rdi, [rsp+58h+arg_18]
0x18001ef84  jmp     short loc_18001EFC3
0x18001ef86  mov     rdi, [rsp+58h+arg_18]
0x18001ef8b  mov     edx, r13d
0x18001ef8e  mov     r8, r12
0x18001ef91  mov     rcx, rdi
0x18001ef94  mov     rax, [rdi]
0x18001ef97  mov     rax, [rax+0C0h]
0x18001ef9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efa3  mov     ebx, eax
0x18001efa5  test    eax, eax
0x18001efa7  jns     short loc_18001EFC3
0x18001efa9  mov     r8d, 366h; int
0x18001efaf  mov     r9d, eax; int
0x18001efb2  lea     rdx, aInteractionBui_1; "Interaction::BuildExtensionNode"
0x18001efb9  mov     ecx, 1; Level
0x18001efbe  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001efc3  mov     rcx, rbp; Block
0x18001efc6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001efcb  test    rsi, rsi
0x18001efce  jz      short loc_18001EFDF
0x18001efd0  mov     rax, [rsi]
0x18001efd3  mov     rcx, rsi
0x18001efd6  mov     rax, [rax+10h]
0x18001efda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efdf  test    rdi, rdi
0x18001efe2  jz      short loc_18001EFF3
0x18001efe4  mov     rax, [rdi]
0x18001efe7  mov     rcx, rdi
0x18001efea  mov     rax, [rax+10h]
0x18001efee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eff3  mov     eax, ebx
0x18001eff5  mov     rbx, [rsp+58h+arg_8]
0x18001effa  add     rsp, 20h
0x18001effe  pop     r15
0x18001f000  pop     r14
0x18001f002  pop     r13
0x18001f004  pop     r12
0x18001f006  pop     rdi
0x18001f007  pop     rsi
0x18001f008  pop     rbp
0x18001f009  retn
```
