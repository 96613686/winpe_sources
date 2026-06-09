# Rootcause::InitializeVerifier(IXMLDOMNode *)

- ea: `0x18001a424`
- end: `0x18001a528`
- name: `?InitializeVerifier@Rootcause@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `260`
- prototype: `__int64 __fastcall(Rootcause *this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18001a530`

## callees

- `0x180001264`
- `0x1800012a4`
- `0x18001a424`
- `0x18001d094`
- `0x18001d20c`
- `0x180026fa0`

## pseudocode

```c
__int64 __fastcall Rootcause::InitializeVerifier(Rootcause *this, struct IXMLDOMNode *a2)
{
  unsigned int v4; // ebx
  int v5; // r8d
  Verifier *v6; // rax
  int v7; // eax
  void *v8; // rsi

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 1189;
LABEL_3:
    SdpDebugTrace(1u, L"Rootcause::InitializeVerifier", v5, v4);
    return v4;
  }
  v6 = (Verifier *)operator new(0x18u);
  if ( v6 )
  {
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
    *((_QWORD *)v6 + 2) = 0;
  }
  *((_QWORD *)this + 3) = v6;
  if ( !v6 )
  {
    v4 = -2147024882;
    v5 = 1192;
    goto LABEL_3;
  }
  if ( !*(_QWORD *)this )
  {
    v4 = -2147467261;
    v5 = 1194;
    goto LABEL_3;
  }
  *(_QWORD *)v6 = *(_QWORD *)this;
  v7 = Verifier::ParseVerifierXml(v6, a2);
  v4 = v7;
  if ( v7 < 0 )
  {
    SdpDebugTrace(1u, L"Verifier::Initialize", 75, v7);
    v5 = 1197;
    goto LABEL_3;
  }
  if ( v7 == 1 )
  {
    v8 = (void *)*((_QWORD *)this + 3);
    if ( v8 )
    {
      Verifier::~Verifier(*((Verifier **)this + 3));
      operator delete(v8);
      *((_QWORD *)this + 3) = 0;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001a424  mov     [rsp+arg_0], rbx
0x18001a429  mov     [rsp+arg_10], rsi
0x18001a42e  push    rdi
0x18001a42f  sub     rsp, 20h
0x18001a433  mov     rbx, rdx
0x18001a436  mov     rdi, rcx
0x18001a439  test    rdx, rdx
0x18001a43c  jnz     short loc_18001A462
0x18001a43e  mov     ebx, 80070057h
0x18001a443  mov     r8d, 4A5h; int
0x18001a449  mov     r9d, ebx; int
0x18001a44c  lea     rdx, aRootcauseIniti_1; "Rootcause::InitializeVerifier"
0x18001a453  mov     ecx, 1; Level
0x18001a458  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001a45d  jmp     loc_18001A516
0x18001a462  mov     ecx, 18h; Size
0x18001a467  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a46c  mov     [rsp+28h+arg_8], rax
0x18001a471  test    rax, rax
0x18001a474  jz      short loc_18001A48D
0x18001a476  mov     qword ptr [rax], 0
0x18001a47d  mov     qword ptr [rax+8], 0
0x18001a485  mov     qword ptr [rax+10h], 0
0x18001a48d  mov     [rdi+18h], rax
0x18001a491  test    rax, rax
0x18001a494  jnz     short loc_18001A4A3
0x18001a496  mov     ebx, 8007000Eh
0x18001a49b  mov     r8d, 4A8h
0x18001a4a1  jmp     short loc_18001A449
0x18001a4a3  mov     rcx, [rdi]
0x18001a4a6  test    rcx, rcx
0x18001a4a9  jnz     short loc_18001A4B8
0x18001a4ab  mov     ebx, 80004003h
0x18001a4b0  mov     r8d, 4AAh
0x18001a4b6  jmp     short loc_18001A449
0x18001a4b8  mov     [rax], rcx
0x18001a4bb  mov     rdx, rbx; struct IXMLDOMNode *
0x18001a4be  mov     rcx, rax; this
0x18001a4c1  call    ?ParseVerifierXml@Verifier@@AEAAJPEAUIXMLDOMNode@@@Z; Verifier::ParseVerifierXml(IXMLDOMNode *)
0x18001a4c6  mov     ebx, eax
0x18001a4c8  test    eax, eax
0x18001a4ca  jns     short loc_18001A4F0
0x18001a4cc  mov     r8d, 4Bh ; 'K'; int
0x18001a4d2  lea     rdx, aVerifierInitia; "Verifier::Initialize"
0x18001a4d9  mov     r9d, eax; int
0x18001a4dc  lea     ecx, [r8-4Ah]; Level
0x18001a4e0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001a4e5  mov     r8d, 4ADh
0x18001a4eb  jmp     loc_18001A449
0x18001a4f0  cmp     ebx, 1
0x18001a4f3  jnz     short loc_18001A516
0x18001a4f5  mov     rsi, [rdi+18h]
0x18001a4f9  test    rsi, rsi
0x18001a4fc  jz      short loc_18001A516
0x18001a4fe  mov     rcx, rsi; this
0x18001a501  call    ??1Verifier@@QEAA@XZ; Verifier::~Verifier(void)
0x18001a506  mov     rcx, rsi; Block
0x18001a509  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a50e  mov     qword ptr [rdi+18h], 0
0x18001a516  mov     rsi, [rsp+28h+arg_10]
0x18001a51b  mov     eax, ebx
0x18001a51d  mov     rbx, [rsp+28h+arg_0]
0x18001a522  add     rsp, 20h
0x18001a526  pop     rdi
0x18001a527  retn
```
