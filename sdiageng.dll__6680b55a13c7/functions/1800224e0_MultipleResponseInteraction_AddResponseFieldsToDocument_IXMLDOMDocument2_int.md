# MultipleResponseInteraction::AddResponseFieldsToDocument(IXMLDOMDocument2 *,int)

- ea: `0x1800224e0`
- end: `0x180022567`
- name: `?AddResponseFieldsToDocument@MultipleResponseInteraction@@MEAAJPEAUIXMLDOMDocument2@@H@Z`
- size: `135`
- prototype: `__int64 __fastcall(MultipleResponseInteraction *this, struct IXMLDOMDocument2 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800224e0`
- `0x180026fa0`
- `0x180027ea4`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall MultipleResponseInteraction::AddResponseFieldsToDocument(
        MultipleResponseInteraction *this,
        struct IXMLDOMDocument2 *a2)
{
  __int64 v2; // rax
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // r8d
  struct IXMLDOMDocument2 *v8; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_QWORD *)this;
  v8 = 0;
  v4 = (*(__int64 (__fastcall **)(MultipleResponseInteraction *, struct IXMLDOMDocument2 **))(v2 + 96))(this, &v8);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v4 = SdpXmlAppend(a2, 0, v8);
    v5 = v4;
    if ( v4 >= 0 )
      goto LABEL_6;
    v6 = 727;
  }
  else
  {
    v6 = 724;
  }
  SdpDebugTrace(1u, L"MultipleResponseInteraction::AddResponseFieldsToDocument", v6, v4);
LABEL_6:
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v8->lpVtbl->Release)(v8);
  return v5;
}

```

## disassembly

```asm
0x1800224e0  mov     [rsp+arg_8], rbx
0x1800224e5  push    rdi
0x1800224e6  sub     rsp, 20h
0x1800224ea  mov     rax, [rcx]
0x1800224ed  mov     rdi, rdx
0x1800224f0  lea     rdx, [rsp+28h+arg_0]
0x1800224f5  mov     [rsp+28h+arg_0], 0
0x1800224fe  mov     rax, [rax+60h]
0x180022502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022507  mov     ebx, eax
0x180022509  test    eax, eax
0x18002250b  jns     short loc_180022515
0x18002250d  mov     r8d, 2D4h
0x180022513  jmp     short loc_180022530
0x180022515  mov     r8, [rsp+28h+arg_0]; struct IXMLDOMDocument2 *
0x18002251a  xor     edx, edx; struct IXMLDOMElement *
0x18002251c  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x18002251f  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x180022524  mov     ebx, eax
0x180022526  test    eax, eax
0x180022528  jns     short loc_180022544
0x18002252a  mov     r8d, 2D7h; int
0x180022530  mov     r9d, eax; int
0x180022533  lea     rdx, aMultiplerespon_0; "MultipleResponseInteraction::AddRespons"...
0x18002253a  mov     ecx, 1; Level
0x18002253f  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180022544  mov     rcx, [rsp+28h+arg_0]
0x180022549  test    rcx, rcx
0x18002254c  jz      short loc_18002255A
0x18002254e  mov     rax, [rcx]
0x180022551  mov     rax, [rax+10h]
0x180022555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002255a  mov     eax, ebx
0x18002255c  mov     rbx, [rsp+28h+arg_8]
0x180022561  add     rsp, 20h
0x180022565  pop     rdi
0x180022566  retn
```
