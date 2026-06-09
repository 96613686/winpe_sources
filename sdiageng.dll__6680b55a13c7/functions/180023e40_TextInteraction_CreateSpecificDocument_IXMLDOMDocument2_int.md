# TextInteraction::CreateSpecificDocument(IXMLDOMDocument2 * *,int)

- ea: `0x180023e40`
- end: `0x180023f97`
- name: `?CreateSpecificDocument@TextInteraction@@EEAAJPEAPEAUIXMLDOMDocument2@@H@Z`
- size: `343`
- prototype: `__int64 __fastcall(TextInteraction *this, struct IXMLDOMDocument2 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180023e40`
- `0x180026fa0`
- `0x1800280f8`
- `0x18002827c`
- `0x18002a010`

## string_xrefs

- `0x180023e71`: `TextInteraction::CreateSpecificDocument`
- `0x180023ea8`: `TextInteraction::CreateSpecificDocument`
- `0x180023ef5`: `TextInteraction::CreateSpecificDocument`
- `0x180023f3c`: `TextInteraction::CreateSpecificDocument`
- `0x180023e93`: `<?xml version="1.0" encoding="utf-8"?><TextInteraction/>`

## pseudocode

```c
__int64 __fastcall TextInteraction::CreateSpecificDocument(TextInteraction *this, struct IXMLDOMDocument2 **a2)
{
  struct IXMLDOMElement *v2; // rdi
  unsigned int v5; // ebx
  int v6; // eax
  struct IXMLDOMDocument2 *v7; // rsi
  int v8; // eax
  int v9; // eax
  struct IXMLDOMDocument2 *v11; // [rsp+58h] [rbp+10h] BYREF
  struct IXMLDOMElement *v12; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  v11 = 0;
  v12 = 0;
  if ( a2 )
  {
    v6 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><TextInteraction/>", &v11);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v7 = v11;
      v8 = SdpXmlCreateNode(v11, 0, L"RegularExpression", 0, &v12);
      v5 = v8;
      if ( v8 >= 0 )
      {
        v2 = v12;
        if ( *((_QWORD *)this + 12)
          && (v9 = ((__int64 (__fastcall *)(struct IXMLDOMElement *))v12->lpVtbl->put_text)(v12), v5 = v9, v9 < 0) )
        {
          SdpDebugTrace(1u, L"TextInteraction::CreateSpecificDocument", 181, v9);
        }
        else
        {
          *a2 = v7;
          v7 = 0;
        }
      }
      else
      {
        SdpDebugTrace(1u, L"TextInteraction::CreateSpecificDocument", 177, v8);
        v2 = v12;
      }
    }
    else
    {
      SdpDebugTrace(1u, L"TextInteraction::CreateSpecificDocument", 169, v6);
      v7 = v11;
    }
    if ( v7 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
    if ( v2 )
      ((void (__fastcall *)(struct IXMLDOMElement *))v2->lpVtbl->Release)(v2);
  }
  else
  {
    v5 = -2147024809;
    SdpDebugTrace(1u, L"TextInteraction::CreateSpecificDocument", 166, -2147024809);
  }
  return v5;
}

```

## disassembly

```asm
0x180023e40  mov     rax, rsp
0x180023e43  mov     [rax+8], rbx
0x180023e47  mov     [rax+18h], rbp
0x180023e4b  push    rsi
0x180023e4c  push    rdi
0x180023e4d  push    r14
0x180023e4f  sub     rsp, 30h
0x180023e53  xor     edi, edi
0x180023e55  mov     qword ptr [rax+10h], 0
0x180023e5d  mov     [rax+20h], rdi
0x180023e61  mov     r14, rdx
0x180023e64  mov     rbp, rcx
0x180023e67  test    rdx, rdx
0x180023e6a  jnz     short loc_180023E8E
0x180023e6c  mov     ebx, 80070057h
0x180023e71  lea     rdx, aTextinteractio_2; "TextInteraction::CreateSpecificDocument"
0x180023e78  mov     r9d, ebx; int
0x180023e7b  lea     ecx, [rdi+1]; Level
0x180023e7e  mov     r8d, 0A6h; int
0x180023e84  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180023e89  jmp     loc_180023F82
0x180023e8e  lea     rdx, [rsp+48h+arg_8]; struct IXMLDOMDocument2 **
0x180023e93  lea     rcx, aXmlVersion10En_13; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180023e9a  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180023e9f  mov     ebx, eax
0x180023ea1  test    eax, eax
0x180023ea3  jns     short loc_180023EC9
0x180023ea5  mov     r9d, eax; int
0x180023ea8  lea     rdx, aTextinteractio_2; "TextInteraction::CreateSpecificDocument"
0x180023eaf  mov     r8d, 0A9h; int
0x180023eb5  mov     ecx, 1; Level
0x180023eba  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180023ebf  mov     rsi, [rsp+48h+arg_8]
0x180023ec4  jmp     loc_180023F5A
0x180023ec9  mov     rsi, [rsp+48h+arg_8]
0x180023ece  lea     rax, [rsp+48h+arg_18]
0x180023ed3  mov     rcx, rsi; struct IXMLDOMDocument2 *
0x180023ed6  mov     [rsp+48h+var_28], rax; struct IXMLDOMElement **
0x180023edb  xor     r9d, r9d; unsigned __int16 *
0x180023ede  lea     r8, aRegularexpress; "RegularExpression"
0x180023ee5  xor     edx, edx; struct IXMLDOMElement *
0x180023ee7  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180023eec  mov     ebx, eax
0x180023eee  test    eax, eax
0x180023ef0  jns     short loc_180023F13
0x180023ef2  mov     r9d, eax; int
0x180023ef5  lea     rdx, aTextinteractio_2; "TextInteraction::CreateSpecificDocument"
0x180023efc  mov     r8d, 0B1h; int
0x180023f02  mov     ecx, 1; Level
0x180023f07  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180023f0c  mov     rdi, [rsp+48h+arg_18]
0x180023f11  jmp     short loc_180023F5A
0x180023f13  mov     rdx, [rbp+60h]
0x180023f17  mov     rdi, [rsp+48h+arg_18]
0x180023f1c  test    rdx, rdx
0x180023f1f  jz      short loc_180023F55
0x180023f21  mov     rax, [rdi]
0x180023f24  mov     rcx, rdi
0x180023f27  mov     rax, [rax+0D8h]
0x180023f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f33  mov     ebx, eax
0x180023f35  test    eax, eax
0x180023f37  jns     short loc_180023F55
0x180023f39  mov     r9d, eax; int
0x180023f3c  lea     rdx, aTextinteractio_2; "TextInteraction::CreateSpecificDocument"
0x180023f43  mov     r8d, 0B5h; int
0x180023f49  mov     ecx, 1; Level
0x180023f4e  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180023f53  jmp     short loc_180023F5A
0x180023f55  mov     [r14], rsi
0x180023f58  xor     esi, esi
0x180023f5a  test    rsi, rsi
0x180023f5d  jz      short loc_180023F6E
0x180023f5f  mov     rax, [rsi]
0x180023f62  mov     rcx, rsi
0x180023f65  mov     rax, [rax+10h]
0x180023f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f6e  test    rdi, rdi
0x180023f71  jz      short loc_180023F82
0x180023f73  mov     rax, [rdi]
0x180023f76  mov     rcx, rdi
0x180023f79  mov     rax, [rax+10h]
0x180023f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f82  mov     rbp, [rsp+48h+arg_10]
0x180023f87  mov     eax, ebx
0x180023f89  mov     rbx, [rsp+48h+arg_0]
0x180023f8e  add     rsp, 30h
0x180023f92  pop     r14
0x180023f94  pop     rdi
0x180023f95  pop     rsi
0x180023f96  retn
```
