# MultipleResponseInteraction::CreateSpecificDocument(IXMLDOMDocument2 * *,int)

- ea: `0x180022a30`
- end: `0x180022b0c`
- name: `?CreateSpecificDocument@MultipleResponseInteraction@@MEAAJPEAPEAUIXMLDOMDocument2@@H@Z`
- size: `220`
- prototype: `__int64 __fastcall(MultipleResponseInteraction *this, struct IXMLDOMDocument2 **, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180022a30`
- `0x180026fa0`
- `0x1800280f8`
- `0x18002a010`

## string_xrefs

- `0x180022a56`: `MultipleResponseInteraction::CreateSpecificDocument`
- `0x180022a8d`: `MultipleResponseInteraction::CreateSpecificDocument`
- `0x180022ace`: `MultipleResponseInteraction::CreateSpecificDocument`
- `0x180022a78`: `<?xml version="1.0" encoding="utf-8"?><MultipleResponseInteraction/>`

## pseudocode

```c
__int64 __fastcall MultipleResponseInteraction::CreateSpecificDocument(
        MultipleResponseInteraction *this,
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
    v7 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><MultipleResponseInteraction/>", &v12);
    v6 = v7;
    if ( v7 >= 0 )
    {
      v9 = a3;
      v8 = v12;
      v10 = (*(__int64 (__fastcall **)(MultipleResponseInteraction *, struct IXMLDOMDocument2 *, __int64))(*(_QWORD *)this + 64LL))(
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
        SdpDebugTrace(1u, L"MultipleResponseInteraction::CreateSpecificDocument", 754, v10);
      }
    }
    else
    {
      SdpDebugTrace(1u, L"MultipleResponseInteraction::CreateSpecificDocument", 751, v7);
      v8 = v12;
    }
    if ( v8 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v8->lpVtbl->Release)(v8);
  }
  else
  {
    v6 = -2147024809;
    SdpDebugTrace(1u, L"MultipleResponseInteraction::CreateSpecificDocument", 748, -2147024809);
  }
  return v6;
}

```

## disassembly

```asm
0x180022a30  push    rbx
0x180022a32  push    rsi
0x180022a33  push    rdi
0x180022a34  push    r14
0x180022a36  sub     rsp, 28h
0x180022a3a  mov     [rsp+48h+arg_8], 0
0x180022a43  mov     edi, r8d
0x180022a46  mov     rsi, rdx
0x180022a49  mov     r14, rcx
0x180022a4c  test    rdx, rdx
0x180022a4f  jnz     short loc_180022A73
0x180022a51  mov     ebx, 80070057h
0x180022a56  lea     rdx, aMultiplerespon_14; "MultipleResponseInteraction::CreateSpec"...
0x180022a5d  mov     r9d, ebx; int
0x180022a60  lea     ecx, [rsi+1]; Level
0x180022a63  mov     r8d, 2ECh; int
0x180022a69  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180022a6e  jmp     loc_180022B00
0x180022a73  lea     rdx, [rsp+48h+arg_8]; struct IXMLDOMDocument2 **
0x180022a78  lea     rcx, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180022a7f  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180022a84  mov     ebx, eax
0x180022a86  test    eax, eax
0x180022a88  jns     short loc_180022AAB
0x180022a8a  mov     r9d, eax; int
0x180022a8d  lea     rdx, aMultiplerespon_14; "MultipleResponseInteraction::CreateSpec"...
0x180022a94  mov     r8d, 2EFh; int
0x180022a9a  mov     ecx, 1; Level
0x180022a9f  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180022aa4  mov     rdi, [rsp+48h+arg_8]
0x180022aa9  jmp     short loc_180022AEC
0x180022aab  mov     rax, [r14]
0x180022aae  mov     r8d, edi
0x180022ab1  mov     rdi, [rsp+48h+arg_8]
0x180022ab6  mov     rcx, r14
0x180022ab9  mov     rdx, rdi
0x180022abc  mov     rax, [rax+40h]
0x180022ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ac5  mov     ebx, eax
0x180022ac7  test    eax, eax
0x180022ac9  jns     short loc_180022AE7
0x180022acb  mov     r9d, eax; int
0x180022ace  lea     rdx, aMultiplerespon_14; "MultipleResponseInteraction::CreateSpec"...
0x180022ad5  mov     r8d, 2F2h; int
0x180022adb  mov     ecx, 1; Level
0x180022ae0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180022ae5  jmp     short loc_180022AEC
0x180022ae7  mov     [rsi], rdi
0x180022aea  xor     edi, edi
0x180022aec  test    rdi, rdi
0x180022aef  jz      short loc_180022B00
0x180022af1  mov     rax, [rdi]
0x180022af4  mov     rcx, rdi
0x180022af7  mov     rax, [rax+10h]
0x180022afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b00  mov     eax, ebx
0x180022b02  add     rsp, 28h
0x180022b06  pop     r14
0x180022b08  pop     rdi
0x180022b09  pop     rsi
0x180022b0a  pop     rbx
0x180022b0b  retn
```
