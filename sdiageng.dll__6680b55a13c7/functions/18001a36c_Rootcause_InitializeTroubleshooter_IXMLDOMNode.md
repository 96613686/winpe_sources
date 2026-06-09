# Rootcause::InitializeTroubleshooter(IXMLDOMNode *)

- ea: `0x18001a36c`
- end: `0x18001a41d`
- name: `?InitializeTroubleshooter@Rootcause@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(Rootcause *this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001a530`

## callees

- `0x180001264`
- `0x18001a36c`
- `0x18001bdac`
- `0x180026fa0`

## pseudocode

```c
__int64 __fastcall Rootcause::InitializeTroubleshooter(Rootcause *this, struct IXMLDOMNode *a2)
{
  unsigned int v4; // ebx
  int v5; // r8d
  int v6; // r9d
  Troubleshooter *v7; // rax
  int v8; // eax

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 1077;
    v6 = -2147024809;
LABEL_11:
    SdpDebugTrace(1u, L"Rootcause::InitializeTroubleshooter", v5, v6);
    return v4;
  }
  v7 = (Troubleshooter *)operator new(0x10u);
  if ( v7 )
  {
    *(_QWORD *)v7 = 0;
    *((_QWORD *)v7 + 1) = 0;
  }
  *((_QWORD *)this + 1) = v7;
  if ( !v7 )
  {
    v4 = -2147024882;
    v5 = 1080;
    v6 = -2147024882;
    goto LABEL_11;
  }
  if ( !*(_QWORD *)this )
  {
    v4 = -2147467261;
    v5 = 1082;
    v6 = -2147467261;
    goto LABEL_11;
  }
  v8 = Troubleshooter::Initialize(v7, *(struct Settings **)this, a2);
  v4 = v8;
  if ( v8 < 0 )
  {
    v6 = v8;
    v5 = 1085;
    goto LABEL_11;
  }
  return v4;
}

```

## disassembly

```asm
0x18001a36c  mov     [rsp+arg_0], rbx
0x18001a371  push    rdi
0x18001a372  sub     rsp, 20h
0x18001a376  mov     rdi, rdx
0x18001a379  mov     rbx, rcx
0x18001a37c  test    rdx, rdx
0x18001a37f  jnz     short loc_18001A391
0x18001a381  mov     ebx, 80070057h
0x18001a386  mov     r8d, 435h
0x18001a38c  mov     r9d, ebx
0x18001a38f  jmp     short loc_18001A3FF
0x18001a391  mov     ecx, 10h; Size
0x18001a396  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a39b  mov     [rsp+28h+arg_8], rax
0x18001a3a0  test    rax, rax
0x18001a3a3  jz      short loc_18001A3B4
0x18001a3a5  mov     qword ptr [rax], 0
0x18001a3ac  mov     qword ptr [rax+8], 0
0x18001a3b4  mov     [rbx+8], rax
0x18001a3b8  test    rax, rax
0x18001a3bb  jnz     short loc_18001A3CD
0x18001a3bd  mov     ebx, 8007000Eh
0x18001a3c2  mov     r8d, 438h
0x18001a3c8  mov     r9d, ebx
0x18001a3cb  jmp     short loc_18001A3FF
0x18001a3cd  mov     rdx, [rbx]; struct Settings *
0x18001a3d0  test    rdx, rdx
0x18001a3d3  jnz     short loc_18001A3E5
0x18001a3d5  mov     ebx, 80004003h
0x18001a3da  mov     r8d, 43Ah
0x18001a3e0  mov     r9d, ebx
0x18001a3e3  jmp     short loc_18001A3FF
0x18001a3e5  mov     r8, rdi; struct IXMLDOMNode *
0x18001a3e8  mov     rcx, rax; this
0x18001a3eb  call    ?Initialize@Troubleshooter@@QEAAJPEAVSettings@@PEAUIXMLDOMNode@@@Z; Troubleshooter::Initialize(Settings *,IXMLDOMNode *)
0x18001a3f0  mov     ebx, eax
0x18001a3f2  test    eax, eax
0x18001a3f4  jns     short loc_18001A410
0x18001a3f6  mov     r9d, eax; int
0x18001a3f9  mov     r8d, 43Dh; int
0x18001a3ff  lea     rdx, aRootcauseIniti_0; "Rootcause::InitializeTroubleshooter"
0x18001a406  mov     ecx, 1; Level
0x18001a40b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001a410  mov     eax, ebx
0x18001a412  mov     rbx, [rsp+28h+arg_0]
0x18001a417  add     rsp, 20h
0x18001a41b  pop     rdi
0x18001a41c  retn
```
