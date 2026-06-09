# Resolver::InitializeScript(IXMLDOMNode *)

- ea: `0x18001c5ac`
- end: `0x18001c6df`
- name: `?InitializeScript@Resolver@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(Resolver *this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18001c6e8`

## callees

- `0x180001264`
- `0x1800012a4`
- `0x18001c5ac`
- `0x18001d420`
- `0x18001db84`
- `0x180026fa0`

## pseudocode

```c
__int64 __fastcall Resolver::InitializeScript(Resolver *this, struct IXMLDOMNode *a2)
{
  unsigned int v4; // ebx
  int v5; // r8d
  int v6; // r9d
  char *v7; // rax
  int v8; // eax
  void *v9; // rsi

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 438;
LABEL_3:
    v6 = v4;
LABEL_4:
    SdpDebugTrace(1u, L"Resolver::InitializeScript", v5, v6);
    return v4;
  }
  v7 = (char *)operator new(0x38u);
  if ( v7 )
  {
    *(_QWORD *)v7 = 0;
    *((_QWORD *)v7 + 1) = 0;
    *((_DWORD *)v7 + 4) = 0;
    *((_DWORD *)v7 + 10) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *(_OWORD *)(v7 + 24) = 0;
  }
  *((_QWORD *)this + 1) = v7;
  if ( !v7 )
  {
    v4 = -2147024882;
    v5 = 441;
    goto LABEL_3;
  }
  if ( !*(_QWORD *)this )
  {
    v4 = -2147467261;
    v5 = 443;
    goto LABEL_3;
  }
  v8 = Script::Initialize((struct IXMLDOMDocument2 **)v7, *(struct IXMLDOMDocument2 **)this, a2);
  v4 = v8;
  if ( v8 < 0 )
  {
    v6 = v8;
    v5 = 446;
    goto LABEL_4;
  }
  if ( v8 == 1 )
  {
    v9 = (void *)*((_QWORD *)this + 1);
    if ( v9 )
    {
      Script::~Script(*((Script **)this + 1));
      operator delete(v9);
      *((_QWORD *)this + 1) = 0;
    }
  }
  else
  {
    *(_DWORD *)(*(_QWORD *)this + 56LL) |= *(_DWORD *)(*((_QWORD *)this + 1) + 16LL) != 0 ? 0x2000 : 0x4000;
    if ( *(_DWORD *)(*((_QWORD *)this + 1) + 40LL) )
      *(_DWORD *)(*(_QWORD *)this + 56LL) |= 0x10u;
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18001c5ac  mov     [rsp+arg_0], rbx
0x18001c5b1  mov     [rsp+arg_10], rsi
0x18001c5b6  push    rdi
0x18001c5b7  sub     rsp, 20h
0x18001c5bb  mov     rbx, rdx
0x18001c5be  mov     rdi, rcx
0x18001c5c1  test    rdx, rdx
0x18001c5c4  jnz     short loc_18001C5EA
0x18001c5c6  mov     ebx, 80070057h
0x18001c5cb  mov     r8d, 1B6h; int
0x18001c5d1  mov     r9d, ebx; int
0x18001c5d4  lea     rdx, aResolverInitia; "Resolver::InitializeScript"
0x18001c5db  mov     ecx, 1; Level
0x18001c5e0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001c5e5  jmp     loc_18001C6CD
0x18001c5ea  mov     ecx, 38h ; '8'; Size
0x18001c5ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c5f4  mov     [rsp+28h+arg_8], rax
0x18001c5f9  test    rax, rax
0x18001c5fc  jz      short loc_18001C62A
0x18001c5fe  xorps   xmm0, xmm0
0x18001c601  mov     qword ptr [rax], 0
0x18001c608  mov     qword ptr [rax+8], 0
0x18001c610  mov     dword ptr [rax+10h], 0
0x18001c617  mov     dword ptr [rax+28h], 0
0x18001c61e  mov     qword ptr [rax+30h], 0
0x18001c626  movups  xmmword ptr [rax+18h], xmm0
0x18001c62a  mov     [rdi+8], rax
0x18001c62e  test    rax, rax
0x18001c631  jnz     short loc_18001C640
0x18001c633  mov     ebx, 8007000Eh
0x18001c638  mov     r8d, 1B9h
0x18001c63e  jmp     short loc_18001C5D1
0x18001c640  mov     rdx, [rdi]; struct Settings *
0x18001c643  test    rdx, rdx
0x18001c646  jnz     short loc_18001C658
0x18001c648  mov     ebx, 80004003h
0x18001c64d  mov     r8d, 1BBh
0x18001c653  jmp     loc_18001C5D1
0x18001c658  mov     r8, rbx; struct IXMLDOMNode *
0x18001c65b  mov     rcx, rax; this
0x18001c65e  call    ?Initialize@Script@@QEAAJPEAVSettings@@PEAUIXMLDOMNode@@@Z; Script::Initialize(Settings *,IXMLDOMNode *)
0x18001c663  mov     ebx, eax
0x18001c665  test    eax, eax
0x18001c667  jns     short loc_18001C677
0x18001c669  mov     r9d, eax
0x18001c66c  mov     r8d, 1BEh
0x18001c672  jmp     loc_18001C5D4
0x18001c677  cmp     eax, 1
0x18001c67a  jnz     short loc_18001C69F
0x18001c67c  mov     rsi, [rdi+8]
0x18001c680  test    rsi, rsi
0x18001c683  jz      short loc_18001C6CD
0x18001c685  mov     rcx, rsi; this
0x18001c688  call    ??1Script@@QEAA@XZ; Script::~Script(void)
0x18001c68d  mov     rcx, rsi; Block
0x18001c690  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c695  mov     qword ptr [rdi+8], 0
0x18001c69d  jmp     short loc_18001C6CD
0x18001c69f  mov     rax, [rdi+8]
0x18001c6a3  mov     rdx, [rdi]
0x18001c6a6  mov     ecx, [rax+10h]
0x18001c6a9  neg     ecx
0x18001c6ab  sbb     eax, eax
0x18001c6ad  and     eax, 0FFFFE000h
0x18001c6b2  add     eax, 4000h
0x18001c6b7  or      [rdx+38h], eax
0x18001c6ba  mov     rax, [rdi+8]
0x18001c6be  cmp     dword ptr [rax+28h], 0
0x18001c6c2  jz      short loc_18001C6CB
0x18001c6c4  mov     rax, [rdi]
0x18001c6c7  or      dword ptr [rax+38h], 10h
0x18001c6cb  xor     ebx, ebx
0x18001c6cd  mov     rsi, [rsp+28h+arg_10]
0x18001c6d2  mov     eax, ebx
0x18001c6d4  mov     rbx, [rsp+28h+arg_0]
0x18001c6d9  add     rsp, 20h
0x18001c6dd  pop     rdi
0x18001c6de  retn
```
