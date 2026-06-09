# Rootcause::BuildVerificationResultXml(Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *,IXMLDOMDocument2 * *)

- ea: `0x1800199c4`
- end: `0x180019b81`
- name: `?BuildVerificationResultXml@Rootcause@@AEAAJPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18001bb50`

## callees

- `0x1800012a4`
- `0x180002280`
- `0x1800199c4`
- `0x18001b070`
- `0x180026fa0`
- `0x1800280f8`
- `0x18002827c`
- `0x18002a010`

## string_xrefs

- `0x180019a34`: `<?xml version="1.0" encoding="utf-8"?><Rootcause/>`
- `0x180019a06`: `Rootcause::BuildVerificationResultXml`
- `0x180019a57`: `Rootcause::BuildVerificationResultXml`
- `0x180019a9d`: `Rootcause::BuildVerificationResultXml`

## pseudocode

```c
__int64 __fastcall Rootcause::BuildVerificationResultXml(
        const unsigned __int16 **this,
        struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *a2,
        struct IXMLDOMDocument2 **a3)
{
  unsigned __int16 *v3; // rsi
  int v7; // r8d
  unsigned int v8; // ebx
  int Node; // eax
  struct IXMLDOMDocument2 *v10; // rdi
  int v11; // r8d
  int v12; // r9d
  const unsigned __int16 *v13; // rdx
  int v14; // eax
  __int64 v15; // rcx
  struct IXMLDOMDocument2 v16; // rax
  unsigned __int16 *v18; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v19; // [rsp+78h] [rbp+10h] BYREF
  struct IXMLDOMDocument2 *v20; // [rsp+88h] [rbp+20h] BYREF

  v3 = 0;
  v20 = 0;
  v18 = 0;
  v19 = 0;
  if ( !a2 )
  {
    v7 = 1496;
LABEL_3:
    v8 = -2147024809;
    SdpDebugTrace(1u, L"Rootcause::BuildVerificationResultXml", v7, -2147024809);
    return v8;
  }
  if ( !a3 )
  {
    v7 = 1497;
    goto LABEL_3;
  }
  Node = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Rootcause/>", &v20);
  v10 = v20;
  v8 = Node;
  if ( Node >= 0 )
  {
    v13 = (const unsigned __int16 *)*((_QWORD *)a2 + 2);
    if ( !v13 )
    {
      v8 = -2147467261;
      v11 = 1506;
      v12 = -2147467261;
      goto LABEL_9;
    }
    v14 = SdpCatId(this[5], v13, &v19);
    v8 = v14;
    if ( v14 < 0 )
    {
      SdpDebugTrace(1u, L"Rootcause::BuildVerificationResultXml", 1509, v14);
      v3 = v19;
      goto LABEL_21;
    }
    v3 = v19;
    Node = SdpXmlCreateNode(v10, 0, L"ID", v19, 0);
    v8 = Node;
    if ( Node >= 0 )
    {
      Node = Rootcause::StatusToString(v15, *((unsigned int *)a2 + 6), &v18);
      v8 = Node;
      if ( Node >= 0 )
      {
        Node = SdpXmlCreateNode(v10, 0, L"Status", v18, 0);
        v8 = Node;
        if ( Node >= 0 )
        {
          v16.lpVtbl = v10->lpVtbl;
          *a3 = v10;
          ((void (__fastcall *)(struct IXMLDOMDocument2 *))v16.lpVtbl->AddRef)(v10);
          goto LABEL_21;
        }
        v11 = 1522;
      }
      else
      {
        v11 = 1519;
      }
    }
    else
    {
      v11 = 1512;
    }
  }
  else
  {
    v11 = 1500;
  }
  v12 = Node;
LABEL_9:
  SdpDebugTrace(1u, L"Rootcause::BuildVerificationResultXml", v11, v12);
LABEL_21:
  if ( v10 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v10->lpVtbl->Release)(v10);
  if ( v3 )
    operator delete(v3);
  return v8;
}

```

## disassembly

```asm
0x1800199c4  mov     rax, rsp
0x1800199c7  mov     [rax+8], rbx
0x1800199cb  push    rbp
0x1800199cc  push    rsi
0x1800199cd  push    rdi
0x1800199ce  push    r14
0x1800199d0  push    r15
0x1800199d2  sub     rsp, 40h
0x1800199d6  xor     esi, esi
0x1800199d8  mov     qword ptr [rax+20h], 0
0x1800199e0  mov     qword ptr [rax-38h], 0
0x1800199e8  mov     r14, r8
0x1800199eb  mov     [rax+10h], rsi
0x1800199ef  mov     rbp, rdx
0x1800199f2  mov     r15, rcx
0x1800199f5  test    rdx, rdx
0x1800199f8  jnz     short loc_180019A1F
0x1800199fa  mov     r8d, 5D8h; int
0x180019a00  mov     r9d, 80070057h; int
0x180019a06  lea     rdx, aRootcauseBuild_0; "Rootcause::BuildVerificationResultXml"
0x180019a0d  mov     ecx, 1; Level
0x180019a12  mov     ebx, r9d
0x180019a15  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180019a1a  jmp     loc_180019B6E
0x180019a1f  test    r14, r14
0x180019a22  jnz     short loc_180019A2C
0x180019a24  mov     r8d, 5D9h
0x180019a2a  jmp     short loc_180019A00
0x180019a2c  lea     rdx, [rsp+68h+arg_18]; struct IXMLDOMDocument2 **
0x180019a34  lea     rcx, aXmlVersion10En_9; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180019a3b  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180019a40  mov     rdi, [rsp+68h+arg_18]
0x180019a48  mov     ebx, eax
0x180019a4a  test    eax, eax
0x180019a4c  jns     short loc_180019A6D
0x180019a4e  mov     r8d, 5DCh; int
0x180019a54  mov     r9d, eax; int
0x180019a57  lea     rdx, aRootcauseBuild_0; "Rootcause::BuildVerificationResultXml"
0x180019a5e  mov     ecx, 1; Level
0x180019a63  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180019a68  jmp     loc_180019B4D
0x180019a6d  mov     rdx, [rbp+10h]; unsigned __int16 *
0x180019a71  test    rdx, rdx
0x180019a74  jnz     short loc_180019A86
0x180019a76  mov     ebx, 80004003h
0x180019a7b  mov     r8d, 5E2h
0x180019a81  mov     r9d, ebx
0x180019a84  jmp     short loc_180019A57
0x180019a86  mov     rcx, [r15+28h]; unsigned __int16 *
0x180019a8a  lea     r8, [rsp+68h+arg_8]; unsigned __int16 **
0x180019a8f  call    ?SdpCatId@@YAJPEBG0PEAPEAG@Z; SdpCatId(ushort const *,ushort const *,ushort * *)
0x180019a94  mov     ebx, eax
0x180019a96  test    eax, eax
0x180019a98  jns     short loc_180019ABE
0x180019a9a  mov     r9d, eax; int
0x180019a9d  lea     rdx, aRootcauseBuild_0; "Rootcause::BuildVerificationResultXml"
0x180019aa4  mov     r8d, 5E5h; int
0x180019aaa  mov     ecx, 1; Level
0x180019aaf  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180019ab4  mov     rsi, [rsp+68h+arg_8]
0x180019ab9  jmp     loc_180019B4D
0x180019abe  mov     [rsp+68h+var_48], rsi; struct IXMLDOMElement **
0x180019ac3  lea     r8, aId; "ID"
0x180019aca  mov     rsi, [rsp+68h+arg_8]
0x180019acf  xor     edx, edx; struct IXMLDOMElement *
0x180019ad1  mov     r9, rsi; unsigned __int16 *
0x180019ad4  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x180019ad7  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180019adc  mov     ebx, eax
0x180019ade  test    eax, eax
0x180019ae0  jns     short loc_180019AED
0x180019ae2  mov     r8d, 5E8h
0x180019ae8  jmp     loc_180019A54
0x180019aed  mov     edx, [rbp+18h]
0x180019af0  lea     r8, [rsp+68h+var_38]
0x180019af5  call    ?StatusToString@Rootcause@@AEAAJW4SDIAG_ROOTCAUSE_STATUS@1@PEAPEAG@Z; Rootcause::StatusToString(Rootcause::SDIAG_ROOTCAUSE_STATUS,ushort * *)
0x180019afa  mov     ebx, eax
0x180019afc  test    eax, eax
0x180019afe  jns     short loc_180019B0B
0x180019b00  mov     r8d, 5EFh
0x180019b06  jmp     loc_180019A54
0x180019b0b  mov     r9, [rsp+68h+var_38]; unsigned __int16 *
0x180019b10  lea     r8, aStatus; "Status"
0x180019b17  xor     edx, edx; struct IXMLDOMElement *
0x180019b19  mov     [rsp+68h+var_48], 0; struct IXMLDOMElement **
0x180019b22  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x180019b25  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180019b2a  mov     ebx, eax
0x180019b2c  test    eax, eax
0x180019b2e  jns     short loc_180019B3B
0x180019b30  mov     r8d, 5F2h
0x180019b36  jmp     loc_180019A54
0x180019b3b  mov     rax, [rdi]
0x180019b3e  mov     rcx, rdi
0x180019b41  mov     [r14], rdi
0x180019b44  mov     rax, [rax+8]
0x180019b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b4d  test    rdi, rdi
0x180019b50  jz      short loc_180019B61
0x180019b52  mov     rax, [rdi]
0x180019b55  mov     rcx, rdi
0x180019b58  mov     rax, [rax+10h]
0x180019b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b61  test    rsi, rsi
0x180019b64  jz      short loc_180019B6E
0x180019b66  mov     rcx, rsi; Block
0x180019b69  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019b6e  mov     eax, ebx
0x180019b70  mov     rbx, [rsp+68h+arg_0]
0x180019b75  add     rsp, 40h
0x180019b79  pop     r15
0x180019b7b  pop     r14
0x180019b7d  pop     rdi
0x180019b7e  pop     rsi
0x180019b7f  pop     rbp
0x180019b80  retn
```
