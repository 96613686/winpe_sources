# Rootcause::get_RcReportXml(IXMLDOMDocument2 * *)

- ea: `0x18001b9c8`
- end: `0x18001bb4a`
- name: `?get_RcReportXml@Rootcause@@QEAAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `386`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY **this, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180014f7c`

## callees

- `0x180018a9c`
- `0x180019ed8`
- `0x18001a02c`
- `0x18001b9c8`
- `0x180026fa0`
- `0x180027ea4`
- `0x1800280f8`
- `0x18002a010`

## string_xrefs

- `0x18001ba03`: `Rootcause::get_RcReportXml`
- `0x18001bafd`: `Rootcause::get_RcReportXml`
- `0x18001ba25`: `<?xml version="1.0" encoding="utf-8"?><RootCauses/>`

## pseudocode

```c
__int64 __fastcall Rootcause::get_RcReportXml(struct _LIST_ENTRY **this, struct IXMLDOMDocument2 **a2)
{
  unsigned int v4; // ebx
  int FirstInstance; // eax
  struct IXMLDOMDocument2 *v6; // rdi
  int v7; // r8d
  SAFEARRAY **v8; // r14
  struct IXMLDOMDocument2 v9; // rax
  struct IXMLDOMDocument2 *v11; // [rsp+58h] [rbp+38h] BYREF
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v12; // [rsp+60h] [rbp+40h] BYREF
  struct IXMLDOMDocument2 *v13; // [rsp+68h] [rbp+48h] BYREF

  v13 = 0;
  v11 = 0;
  v12 = 0;
  if ( a2 )
  {
    FirstInstance = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><RootCauses/>", &v13);
    v6 = v13;
    v4 = FirstInstance;
    if ( FirstInstance >= 0 )
    {
      FirstInstance = Rootcause::GetFirstInstance((Rootcause *)this, this[15], &v12);
      v4 = FirstInstance;
      if ( FirstInstance >= 0 )
      {
        v8 = (SAFEARRAY **)v12;
        while ( 1 )
        {
          if ( v11 )
          {
            ((void (__fastcall *)(struct IXMLDOMDocument2 *))v11->lpVtbl->Release)(v11);
            v11 = 0;
          }
          FirstInstance = Rootcause::BuildReportXml((const unsigned __int16 **)this, v8, &v11);
          v4 = FirstInstance;
          if ( FirstInstance < 0 )
            break;
          FirstInstance = SdpXmlAppend(v6, 0, v11);
          v4 = FirstInstance;
          if ( FirstInstance < 0 )
          {
            v7 = 1771;
            goto LABEL_18;
          }
          FirstInstance = Rootcause::GetNextInstance((Rootcause *)this, this[15], &v12);
          v4 = FirstInstance;
          if ( FirstInstance < 0 )
          {
            v7 = 1774;
            goto LABEL_18;
          }
          v8 = (SAFEARRAY **)v12;
          if ( !v12 )
          {
            v9.lpVtbl = v6->lpVtbl;
            *a2 = v6;
            ((void (__fastcall *)(struct IXMLDOMDocument2 *))v9.lpVtbl->AddRef)(v6);
            goto LABEL_19;
          }
        }
        v7 = 1768;
      }
      else
      {
        v7 = 1757;
      }
    }
    else
    {
      v7 = 1754;
    }
LABEL_18:
    SdpDebugTrace(1u, L"Rootcause::get_RcReportXml", v7, FirstInstance);
LABEL_19:
    if ( v6 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v6->lpVtbl->Release)(v6);
  }
  else
  {
    v4 = -2147024809;
    SdpDebugTrace(1u, L"Rootcause::get_RcReportXml", 1751, -2147024809);
  }
  if ( v11 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v11->lpVtbl->Release)(v11);
  return v4;
}

```

## disassembly

```asm
0x18001b9c8  mov     [rsp-28h+arg_0], rbx
0x18001b9cd  push    rbp
0x18001b9ce  push    rsi
0x18001b9cf  push    rdi
0x18001b9d0  push    r14
0x18001b9d2  push    r15
0x18001b9d4  mov     rbp, rsp
0x18001b9d7  sub     rsp, 20h
0x18001b9db  mov     [rbp+arg_18], 0
0x18001b9e3  mov     r15, rdx
0x18001b9e6  mov     [rbp+arg_8], 0
0x18001b9ee  mov     rsi, rcx
0x18001b9f1  mov     [rbp+arg_10], 0
0x18001b9f9  test    rdx, rdx
0x18001b9fc  jnz     short loc_18001BA21
0x18001b9fe  mov     ebx, 80070057h
0x18001ba03  lea     rdx, aRootcauseGetRc; "Rootcause::get_RcReportXml"
0x18001ba0a  mov     r9d, ebx; int
0x18001ba0d  lea     ecx, [r15+1]; Level
0x18001ba11  mov     r8d, 6D7h; int
0x18001ba17  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001ba1c  jmp     loc_18001BB22
0x18001ba21  lea     rdx, [rbp+arg_18]; struct IXMLDOMDocument2 **
0x18001ba25  lea     rcx, aXmlVersion10En_22; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18001ba2c  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x18001ba31  mov     rdi, [rbp+arg_18]
0x18001ba35  mov     ebx, eax
0x18001ba37  test    eax, eax
0x18001ba39  jns     short loc_18001BA46
0x18001ba3b  mov     r8d, 6DAh
0x18001ba41  jmp     loc_18001BAFA
0x18001ba46  mov     rdx, [rsi+78h]; struct _LIST_ENTRY *
0x18001ba4a  lea     r8, [rbp+arg_10]; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **
0x18001ba4e  mov     rcx, rsi; this
0x18001ba51  call    ?GetFirstInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::GetFirstInstance(_LIST_ENTRY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x18001ba56  mov     ebx, eax
0x18001ba58  test    eax, eax
0x18001ba5a  jns     short loc_18001BA67
0x18001ba5c  mov     r8d, 6DDh
0x18001ba62  jmp     loc_18001BAFA
0x18001ba67  mov     r14, [rbp+arg_10]
0x18001ba6b  mov     rcx, [rbp+arg_8]
0x18001ba6f  test    rcx, rcx
0x18001ba72  jz      short loc_18001BA88
0x18001ba74  mov     rax, [rcx]
0x18001ba77  mov     rax, [rax+10h]
0x18001ba7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba80  mov     [rbp+arg_8], 0
0x18001ba88  lea     r8, [rbp+arg_8]; struct IXMLDOMDocument2 **
0x18001ba8c  mov     rdx, r14; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *
0x18001ba8f  mov     rcx, rsi; this
0x18001ba92  call    ?BuildReportXml@Rootcause@@AEAAJPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@PEAPEAUIXMLDOMDocument2@@@Z; Rootcause::BuildReportXml(Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *,IXMLDOMDocument2 * *)
0x18001ba97  mov     ebx, eax
0x18001ba99  test    eax, eax
0x18001ba9b  js      short loc_18001BAF4
0x18001ba9d  mov     r8, [rbp+arg_8]; struct IXMLDOMDocument2 *
0x18001baa1  xor     edx, edx; struct IXMLDOMElement *
0x18001baa3  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18001baa6  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x18001baab  mov     ebx, eax
0x18001baad  test    eax, eax
0x18001baaf  js      short loc_18001BAEC
0x18001bab1  mov     rdx, [rsi+78h]; struct _LIST_ENTRY *
0x18001bab5  lea     r8, [rbp+arg_10]; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **
0x18001bab9  mov     rcx, rsi; this
0x18001babc  call    ?GetNextInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::GetNextInstance(_LIST_ENTRY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x18001bac1  mov     ebx, eax
0x18001bac3  test    eax, eax
0x18001bac5  js      short loc_18001BAE4
0x18001bac7  mov     r14, [rbp+arg_10]
0x18001bacb  test    r14, r14
0x18001bace  jnz     short loc_18001BA6B
0x18001bad0  mov     rax, [rdi]
0x18001bad3  mov     rcx, rdi
0x18001bad6  mov     [r15], rdi
0x18001bad9  mov     rax, [rax+8]
0x18001badd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bae2  jmp     short loc_18001BB0E
0x18001bae4  mov     r8d, 6EEh
0x18001baea  jmp     short loc_18001BAFA
0x18001baec  mov     r8d, 6EBh
0x18001baf2  jmp     short loc_18001BAFA
0x18001baf4  mov     r8d, 6E8h; int
0x18001bafa  mov     r9d, eax; int
0x18001bafd  lea     rdx, aRootcauseGetRc; "Rootcause::get_RcReportXml"
0x18001bb04  mov     ecx, 1; Level
0x18001bb09  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001bb0e  test    rdi, rdi
0x18001bb11  jz      short loc_18001BB22
0x18001bb13  mov     rax, [rdi]
0x18001bb16  mov     rcx, rdi
0x18001bb19  mov     rax, [rax+10h]
0x18001bb1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb22  mov     rcx, [rbp+arg_8]
0x18001bb26  test    rcx, rcx
0x18001bb29  jz      short loc_18001BB37
0x18001bb2b  mov     rax, [rcx]
0x18001bb2e  mov     rax, [rax+10h]
0x18001bb32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb37  mov     eax, ebx
0x18001bb39  mov     rbx, [rsp+20h+arg_0]
0x18001bb3e  add     rsp, 20h
0x18001bb42  pop     r15
0x18001bb44  pop     r14
0x18001bb46  pop     rdi
0x18001bb47  pop     rsi
0x18001bb48  pop     rbp
0x18001bb49  retn
```
