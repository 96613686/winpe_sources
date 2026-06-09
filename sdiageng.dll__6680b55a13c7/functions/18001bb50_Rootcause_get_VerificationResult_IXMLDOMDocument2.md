# Rootcause::get_VerificationResult(IXMLDOMDocument2 *)

- ea: `0x18001bb50`
- end: `0x18001bcaf`
- name: `?get_VerificationResult@Rootcause@@AEAAJPEAUIXMLDOMDocument2@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY **this, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001b2d0`

## callees

- `0x1800199c4`
- `0x180019ed8`
- `0x18001a02c`
- `0x18001bb50`
- `0x180026fa0`
- `0x180027ea4`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Rootcause::get_VerificationResult(struct _LIST_ENTRY **this, struct IXMLDOMDocument2 *a2)
{
  struct IXMLDOMDocument2 *v2; // rdi
  unsigned int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  int FirstInstance; // eax
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v9; // rbp
  int v10; // eax
  int NextInstance; // eax
  int v12; // r8d
  struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *v14; // [rsp+48h] [rbp+10h] BYREF
  struct IXMLDOMDocument2 *v15; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  v14 = 0;
  v15 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 818;
    v7 = -2147024809;
LABEL_3:
    SdpDebugTrace(1u, L"Rootcause::get_VerificationResult", v6, v7);
    return v5;
  }
  FirstInstance = Rootcause::GetFirstInstance((Rootcause *)this, this[15], &v14);
  v5 = FirstInstance;
  if ( FirstInstance < 0 )
  {
    v7 = FirstInstance;
    v6 = 821;
    goto LABEL_3;
  }
  v9 = v14;
  if ( v14 )
  {
    while ( 1 )
    {
      if ( *((_DWORD *)v9 + 6) > 1u )
      {
        if ( v2 )
        {
          ((void (__fastcall *)(struct IXMLDOMDocument2 *))v2->lpVtbl->Release)(v2);
          v15 = 0;
        }
        v10 = Rootcause::BuildVerificationResultXml((const unsigned __int16 **)this, v9, &v15);
        v5 = v10;
        if ( v10 < 0 )
        {
          SdpDebugTrace(1u, L"Rootcause::get_VerificationResult", 829, v10);
          v2 = v15;
          goto LABEL_19;
        }
        v2 = v15;
        NextInstance = SdpXmlAppend(a2, 0, v15);
        v5 = NextInstance;
        if ( NextInstance < 0 )
        {
          v12 = 832;
          goto LABEL_18;
        }
      }
      NextInstance = Rootcause::GetNextInstance((Rootcause *)this, this[15], &v14);
      v5 = NextInstance;
      if ( NextInstance < 0 )
        break;
      v9 = v14;
      if ( !v14 )
        goto LABEL_19;
    }
    v12 = 836;
LABEL_18:
    SdpDebugTrace(1u, L"Rootcause::get_VerificationResult", v12, NextInstance);
LABEL_19:
    if ( v2 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v2->lpVtbl->Release)(v2);
  }
  return v5;
}

```

## disassembly

```asm
0x18001bb50  mov     rax, rsp
0x18001bb53  mov     [rax+8], rbx
0x18001bb57  mov     [rax+20h], rbp
0x18001bb5b  push    rdi
0x18001bb5c  push    r14
0x18001bb5e  push    r15
0x18001bb60  sub     rsp, 20h
0x18001bb64  xor     edi, edi
0x18001bb66  mov     qword ptr [rax+10h], 0
0x18001bb6e  mov     [rax+18h], rdi
0x18001bb72  mov     r15, rdx
0x18001bb75  mov     r14, rcx
0x18001bb78  test    rdx, rdx
0x18001bb7b  jnz     short loc_18001BBA1
0x18001bb7d  mov     ebx, 80070057h
0x18001bb82  mov     r8d, 332h; int
0x18001bb88  mov     r9d, ebx; int
0x18001bb8b  lea     rdx, aRootcauseGetVe; "Rootcause::get_VerificationResult"
0x18001bb92  mov     ecx, 1; Level
0x18001bb97  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001bb9c  jmp     loc_18001BC99
0x18001bba1  mov     rdx, [rcx+78h]; struct _LIST_ENTRY *
0x18001bba5  lea     r8, [rsp+38h+arg_8]; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **
0x18001bbaa  call    ?GetFirstInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::GetFirstInstance(_LIST_ENTRY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x18001bbaf  mov     ebx, eax
0x18001bbb1  test    eax, eax
0x18001bbb3  jns     short loc_18001BBC0
0x18001bbb5  mov     r9d, eax
0x18001bbb8  mov     r8d, 335h
0x18001bbbe  jmp     short loc_18001BB8B
0x18001bbc0  mov     rbp, [rsp+38h+arg_8]
0x18001bbc5  test    rbp, rbp
0x18001bbc8  jz      loc_18001BC99
0x18001bbce  cmp     dword ptr [rbp+18h], 1
0x18001bbd2  jbe     short loc_18001BC1F
0x18001bbd4  test    rdi, rdi
0x18001bbd7  jz      short loc_18001BBF1
0x18001bbd9  mov     rax, [rdi]
0x18001bbdc  mov     rcx, rdi
0x18001bbdf  mov     rax, [rax+10h]
0x18001bbe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbe8  mov     [rsp+38h+arg_10], 0
0x18001bbf1  lea     r8, [rsp+38h+arg_10]; struct IXMLDOMDocument2 **
0x18001bbf6  mov     rdx, rbp; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *
0x18001bbf9  mov     rcx, r14; this
0x18001bbfc  call    ?BuildVerificationResultXml@Rootcause@@AEAAJPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@PEAPEAUIXMLDOMDocument2@@@Z; Rootcause::BuildVerificationResultXml(Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *,IXMLDOMDocument2 * *)
0x18001bc01  mov     ebx, eax
0x18001bc03  test    eax, eax
0x18001bc05  js      short loc_18001BC4A
0x18001bc07  mov     rdi, [rsp+38h+arg_10]
0x18001bc0c  xor     edx, edx; struct IXMLDOMElement *
0x18001bc0e  mov     r8, rdi; struct IXMLDOMDocument2 *
0x18001bc11  mov     rcx, r15; struct IXMLDOMDocument2 *
0x18001bc14  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x18001bc19  mov     ebx, eax
0x18001bc1b  test    eax, eax
0x18001bc1d  js      short loc_18001BC42
0x18001bc1f  mov     rdx, [r14+78h]; struct _LIST_ENTRY *
0x18001bc23  lea     r8, [rsp+38h+arg_8]; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE **
0x18001bc28  mov     rcx, r14; this
0x18001bc2b  call    ?GetNextInstance@Rootcause@@AEAAJPEAU_LIST_ENTRY@@PEAPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@@Z; Rootcause::GetNextInstance(_LIST_ENTRY *,Rootcause::_SDIAG_ROOTCAUSE_INSTANCE * *)
0x18001bc30  mov     ebx, eax
0x18001bc32  test    eax, eax
0x18001bc34  js      short loc_18001BC6B
0x18001bc36  mov     rbp, [rsp+38h+arg_8]
0x18001bc3b  test    rbp, rbp
0x18001bc3e  jnz     short loc_18001BBCE
0x18001bc40  jmp     short loc_18001BC85
0x18001bc42  mov     r8d, 340h
0x18001bc48  jmp     short loc_18001BC71
0x18001bc4a  mov     r9d, eax; int
0x18001bc4d  lea     rdx, aRootcauseGetVe; "Rootcause::get_VerificationResult"
0x18001bc54  mov     r8d, 33Dh; int
0x18001bc5a  mov     ecx, 1; Level
0x18001bc5f  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001bc64  mov     rdi, [rsp+38h+arg_10]
0x18001bc69  jmp     short loc_18001BC85
0x18001bc6b  mov     r8d, 344h; int
0x18001bc71  mov     r9d, eax; int
0x18001bc74  lea     rdx, aRootcauseGetVe; "Rootcause::get_VerificationResult"
0x18001bc7b  mov     ecx, 1; Level
0x18001bc80  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001bc85  test    rdi, rdi
0x18001bc88  jz      short loc_18001BC99
0x18001bc8a  mov     rax, [rdi]
0x18001bc8d  mov     rcx, rdi
0x18001bc90  mov     rax, [rax+10h]
0x18001bc94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc99  mov     rbp, [rsp+38h+arg_18]
0x18001bc9e  mov     eax, ebx
0x18001bca0  mov     rbx, [rsp+38h+arg_0]
0x18001bca5  add     rsp, 20h
0x18001bca9  pop     r15
0x18001bcab  pop     r14
0x18001bcad  pop     rdi
0x18001bcae  retn
```
