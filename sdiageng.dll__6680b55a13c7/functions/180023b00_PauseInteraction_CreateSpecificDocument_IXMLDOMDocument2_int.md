# PauseInteraction::CreateSpecificDocument(IXMLDOMDocument2 * *,int)

- ea: `0x180023b00`
- end: `0x180023b97`
- name: `?CreateSpecificDocument@PauseInteraction@@MEAAJPEAPEAUIXMLDOMDocument2@@H@Z`
- size: `151`
- prototype: `__int64 __fastcall(PauseInteraction *this, struct IXMLDOMDocument2 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180023b00`
- `0x180026fa0`
- `0x1800280f8`
- `0x18002a010`

## string_xrefs

- `0x180023b27`: `PauseInteraction::CreateSpecificDocument`
- `0x180023b55`: `PauseInteraction::CreateSpecificDocument`
- `0x180023b3d`: `<?xml version="1.0" encoding="utf-8"?><PauseInteraction/>`

## pseudocode

```c
__int64 __fastcall PauseInteraction::CreateSpecificDocument(PauseInteraction *this, struct IXMLDOMDocument2 **a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  struct IXMLDOMDocument2 *v5; // rcx
  struct IXMLDOMDocument2 *v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  if ( a2 )
  {
    v4 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><PauseInteraction/>", &v7);
    v3 = v4;
    if ( v4 >= 0 )
    {
      v5 = 0;
      *a2 = v7;
    }
    else
    {
      SdpDebugTrace(1u, L"PauseInteraction::CreateSpecificDocument", 82, v4);
      v5 = v7;
    }
    if ( v5 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v5->lpVtbl->Release)(v5);
  }
  else
  {
    v3 = -2147024809;
    SdpDebugTrace(1u, L"PauseInteraction::CreateSpecificDocument", 79, -2147024809);
  }
  return v3;
}

```

## disassembly

```asm
0x180023b00  mov     [rsp+arg_0], rbx
0x180023b05  push    rdi
0x180023b06  sub     rsp, 20h
0x180023b0a  mov     [rsp+28h+arg_8], 0
0x180023b13  mov     rdi, rdx
0x180023b16  test    rdx, rdx
0x180023b19  jnz     short loc_180023B38
0x180023b1b  lea     r8d, [rdx+4Fh]; int
0x180023b1f  mov     ebx, 80070057h
0x180023b24  mov     r9d, ebx; int
0x180023b27  lea     rdx, aPauseinteracti; "PauseInteraction::CreateSpecificDocumen"...
0x180023b2e  lea     ecx, [rdi+1]; Level
0x180023b31  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180023b36  jmp     short loc_180023B8A
0x180023b38  lea     rdx, [rsp+28h+arg_8]; struct IXMLDOMDocument2 **
0x180023b3d  lea     rcx, aXmlVersion10En_11; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180023b44  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180023b49  mov     ebx, eax
0x180023b4b  test    eax, eax
0x180023b4d  jns     short loc_180023B6F
0x180023b4f  mov     r8d, 52h ; 'R'; int
0x180023b55  lea     rdx, aPauseinteracti; "PauseInteraction::CreateSpecificDocumen"...
0x180023b5c  mov     r9d, eax; int
0x180023b5f  lea     ecx, [r8-51h]; Level
0x180023b63  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180023b68  mov     rcx, [rsp+28h+arg_8]
0x180023b6d  jmp     short loc_180023B79
0x180023b6f  mov     rax, [rsp+28h+arg_8]
0x180023b74  xor     ecx, ecx
0x180023b76  mov     [rdi], rax
0x180023b79  test    rcx, rcx
0x180023b7c  jz      short loc_180023B8A
0x180023b7e  mov     rax, [rcx]
0x180023b81  mov     rax, [rax+10h]
0x180023b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b8a  mov     eax, ebx
0x180023b8c  mov     rbx, [rsp+28h+arg_0]
0x180023b91  add     rsp, 20h
0x180023b95  pop     rdi
0x180023b96  retn
```
