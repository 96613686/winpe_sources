# Interaction::Initialize(Settings *,IXMLDOMNode *,IXMLDOMDocument2 *)

- ea: `0x18002021c`
- end: `0x1800202b9`
- name: `?Initialize@Interaction@@QEAAJPEAVSettings@@PEAUIXMLDOMNode@@PEAUIXMLDOMDocument2@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(Interaction *__hidden this, struct Settings *, struct IXMLDOMNode *, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001f010`

## callees

- `0x18002021c`
- `0x180020648`
- `0x1800208f4`
- `0x180026fa0`

## pseudocode

```c
__int64 __fastcall Interaction::Initialize(
        Interaction *this,
        struct Settings *a2,
        struct IXMLDOMNode *a3,
        struct IXMLDOMDocument2 *a4)
{
  int v6; // r9d
  int v7; // r8d
  unsigned int v8; // ebx
  int v9; // eax

  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 352;
    v8 = -2147024809;
LABEL_11:
    SdpDebugTrace(1u, L"Interaction::Initialize", v7, v6);
    return v8;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    v7 = 353;
    v8 = -2147024809;
    goto LABEL_11;
  }
  *((_QWORD *)this + 1) = a2;
  v9 = Interaction::ParseInteractionXml(this, a3);
  v8 = v9;
  if ( v9 < 0 )
  {
    v7 = 358;
LABEL_10:
    v6 = v9;
    goto LABEL_11;
  }
  if ( a4 )
  {
    v9 = Interaction::ParseAnswerXml(this, a4);
    v8 = v9;
    if ( v9 < 0 )
    {
      v7 = 362;
      goto LABEL_10;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18002021c  mov     [rsp+arg_0], rbx
0x180020221  mov     [rsp+arg_8], rsi
0x180020226  push    rdi
0x180020227  sub     rsp, 20h
0x18002022b  mov     rdi, r9
0x18002022e  mov     rsi, rcx
0x180020231  test    rdx, rdx
0x180020234  jnz     short loc_180020247
0x180020236  mov     r9d, 80070057h
0x18002023c  mov     r8d, 160h
0x180020242  mov     ebx, r9d
0x180020245  jmp     short loc_180020296
0x180020247  test    r8, r8
0x18002024a  jnz     short loc_18002025D
0x18002024c  mov     r9d, 80070057h
0x180020252  mov     r8d, 161h
0x180020258  mov     ebx, r9d
0x18002025b  jmp     short loc_180020296
0x18002025d  mov     [rcx+8], rdx
0x180020261  mov     rdx, r8; struct IXMLDOMNode *
0x180020264  call    ?ParseInteractionXml@Interaction@@IEAAJPEAUIXMLDOMNode@@@Z; Interaction::ParseInteractionXml(IXMLDOMNode *)
0x180020269  mov     ebx, eax
0x18002026b  test    eax, eax
0x18002026d  jns     short loc_180020277
0x18002026f  mov     r8d, 166h
0x180020275  jmp     short loc_180020293
0x180020277  test    rdi, rdi
0x18002027a  jz      short loc_1800202A7
0x18002027c  mov     rdx, rdi; struct IXMLDOMDocument2 *
0x18002027f  mov     rcx, rsi; this
0x180020282  call    ?ParseAnswerXml@Interaction@@IEAAJPEAUIXMLDOMDocument2@@@Z; Interaction::ParseAnswerXml(IXMLDOMDocument2 *)
0x180020287  mov     ebx, eax
0x180020289  test    eax, eax
0x18002028b  jns     short loc_1800202A7
0x18002028d  mov     r8d, 16Ah; int
0x180020293  mov     r9d, eax; int
0x180020296  lea     rdx, aInteractionIni_0; "Interaction::Initialize"
0x18002029d  mov     ecx, 1; Level
0x1800202a2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800202a7  mov     rsi, [rsp+28h+arg_8]
0x1800202ac  mov     eax, ebx
0x1800202ae  mov     rbx, [rsp+28h+arg_0]
0x1800202b3  add     rsp, 20h
0x1800202b7  pop     rdi
0x1800202b8  retn
```
