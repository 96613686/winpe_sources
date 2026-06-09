# SingleResponseInteraction::CreateSpecificDocument(IXMLDOMDocument2 * *,int)

- ea: `0x180022350`
- end: `0x180022428`
- name: `?CreateSpecificDocument@SingleResponseInteraction@@EEAAJPEAPEAUIXMLDOMDocument2@@H@Z`
- size: `216`
- prototype: `__int64 __fastcall(SingleResponseInteraction *this, struct IXMLDOMDocument2 **, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180022350`
- `0x180026fa0`
- `0x1800280f8`
- `0x18002a010`

## string_xrefs

- `0x18002237d`: `SingleResponseInteraction::CreateSpecificDocument`
- `0x1800223ae`: `SingleResponseInteraction::CreateSpecificDocument`
- `0x1800223ee`: `SingleResponseInteraction::CreateSpecificDocument`
- `0x180022396`: `<?xml version="1.0" encoding="utf-8"?><SingleResponseInteraction/>`

## pseudocode

```c
__int64 __fastcall SingleResponseInteraction::CreateSpecificDocument(
        SingleResponseInteraction *this,
        struct IXMLDOMDocument2 **a2,
        unsigned int a3)
{
  unsigned int v6; // ebx
  int v7; // eax
  struct IXMLDOMDocument2 *v8; // rdi
  __int64 v9; // r8
  int v10; // eax
  struct IXMLDOMDocument2 *v12; // [rsp+58h] [rbp+10h] BYREF

  v12 = 0;
  if ( a2 )
  {
    v7 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><SingleResponseInteraction/>", &v12);
    v6 = v7;
    if ( v7 >= 0 )
    {
      v9 = a3;
      v8 = v12;
      v10 = (*(__int64 (__fastcall **)(SingleResponseInteraction *, struct IXMLDOMDocument2 *, __int64))(*(_QWORD *)this + 64LL))(
              this,
              v12,
              v9);
      v6 = v10;
      if ( v10 >= 0 )
      {
        *a2 = v8;
        v8 = 0;
      }
      else
      {
        SdpDebugTrace(1u, L"SingleResponseInteraction::CreateSpecificDocument", 79, v10);
      }
    }
    else
    {
      SdpDebugTrace(1u, L"SingleResponseInteraction::CreateSpecificDocument", 76, v7);
      v8 = v12;
    }
    if ( v8 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v8->lpVtbl->Release)(v8);
  }
  else
  {
    v6 = -2147024809;
    SdpDebugTrace(1u, L"SingleResponseInteraction::CreateSpecificDocument", 73, -2147024809);
  }
  return v6;
}

```

## disassembly

```asm
0x180022350  push    rbx
0x180022352  push    rsi
0x180022353  push    rdi
0x180022354  push    r14
0x180022356  sub     rsp, 28h
0x18002235a  mov     [rsp+48h+arg_8], 0
0x180022363  mov     edi, r8d
0x180022366  mov     rsi, rdx
0x180022369  mov     r14, rcx
0x18002236c  test    rdx, rdx
0x18002236f  jnz     short loc_180022391
0x180022371  lea     r8d, [rdx+49h]; int
0x180022375  mov     ebx, 80070057h
0x18002237a  mov     r9d, ebx; int
0x18002237d  lea     rdx, aSingleresponse_1; "SingleResponseInteraction::CreateSpecif"...
0x180022384  lea     ecx, [rsi+1]; Level
0x180022387  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18002238c  jmp     loc_18002241C
0x180022391  lea     rdx, [rsp+48h+arg_8]; struct IXMLDOMDocument2 **
0x180022396  lea     rcx, aXmlVersion10En_5; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18002239d  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x1800223a2  mov     ebx, eax
0x1800223a4  test    eax, eax
0x1800223a6  jns     short loc_1800223C8
0x1800223a8  mov     r8d, 4Ch ; 'L'; int
0x1800223ae  lea     rdx, aSingleresponse_1; "SingleResponseInteraction::CreateSpecif"...
0x1800223b5  mov     r9d, eax; int
0x1800223b8  lea     ecx, [r8-4Bh]; Level
0x1800223bc  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800223c1  mov     rdi, [rsp+48h+arg_8]
0x1800223c6  jmp     short loc_180022408
0x1800223c8  mov     rax, [r14]
0x1800223cb  mov     r8d, edi
0x1800223ce  mov     rdi, [rsp+48h+arg_8]
0x1800223d3  mov     rcx, r14
0x1800223d6  mov     rdx, rdi
0x1800223d9  mov     rax, [rax+40h]
0x1800223dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223e2  mov     ebx, eax
0x1800223e4  test    eax, eax
0x1800223e6  jns     short loc_180022403
0x1800223e8  mov     r8d, 4Fh ; 'O'; int
0x1800223ee  lea     rdx, aSingleresponse_1; "SingleResponseInteraction::CreateSpecif"...
0x1800223f5  mov     r9d, eax; int
0x1800223f8  lea     ecx, [r8-4Eh]; Level
0x1800223fc  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180022401  jmp     short loc_180022408
0x180022403  mov     [rsi], rdi
0x180022406  xor     edi, edi
0x180022408  test    rdi, rdi
0x18002240b  jz      short loc_18002241C
0x18002240d  mov     rax, [rdi]
0x180022410  mov     rcx, rdi
0x180022413  mov     rax, [rax+10h]
0x180022417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002241c  mov     eax, ebx
0x18002241e  add     rsp, 28h
0x180022422  pop     r14
0x180022424  pop     rdi
0x180022425  pop     rsi
0x180022426  pop     rbx
0x180022427  retn
```
