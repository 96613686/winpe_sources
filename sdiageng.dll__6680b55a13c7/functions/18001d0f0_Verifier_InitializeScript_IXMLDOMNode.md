# Verifier::InitializeScript(IXMLDOMNode *)

- ea: `0x18001d0f0`
- end: `0x18001d204`
- name: `?InitializeScript@Verifier@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(Verifier *this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001d20c`

## callees

- `0x180001264`
- `0x18001d0f0`
- `0x18001db84`
- `0x180026fa0`

## pseudocode

```c
__int64 __fastcall Verifier::InitializeScript(Verifier *this, struct IXMLDOMNode *a2)
{
  unsigned int v4; // ebx
  int v5; // r8d
  char *v6; // rax
  int v7; // eax
  int v8; // r9d
  __int64 v9; // rax

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 262;
LABEL_17:
    v8 = v4;
    goto LABEL_18;
  }
  v6 = (char *)operator new(0x38u);
  if ( v6 )
  {
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
    *((_DWORD *)v6 + 4) = 0;
    *((_DWORD *)v6 + 10) = 0;
    *((_QWORD *)v6 + 6) = 0;
    *(_OWORD *)(v6 + 24) = 0;
  }
  *((_QWORD *)this + 1) = v6;
  if ( !v6 )
  {
    v4 = -2147024882;
    v5 = 265;
    goto LABEL_17;
  }
  if ( !*(_QWORD *)this )
  {
    v4 = -2147467261;
    v5 = 267;
    goto LABEL_17;
  }
  v7 = Script::Initialize((struct IXMLDOMDocument2 **)v6, *(struct IXMLDOMDocument2 **)this, a2);
  v4 = v7;
  if ( v7 < 0 )
  {
    v8 = v7;
    v5 = 270;
LABEL_18:
    SdpDebugTrace(1u, L"Verifier::InitializeScript", v5, v8);
    return v4;
  }
  if ( v7 == 1 || (v9 = *((_QWORD *)this + 1)) == 0 )
  {
    v4 = -2147467259;
    v5 = 271;
    goto LABEL_17;
  }
  *(_DWORD *)(*(_QWORD *)this + 56LL) |= *(_DWORD *)(v9 + 16) != 0 ? 0x8000 : 0x10000;
  if ( *(_DWORD *)(*((_QWORD *)this + 1) + 40LL) )
    *(_DWORD *)(*(_QWORD *)this + 56LL) |= 0x20u;
  return 0;
}

```

## disassembly

```asm
0x18001d0f0  mov     [rsp+arg_0], rbx
0x18001d0f5  push    rdi
0x18001d0f6  sub     rsp, 20h
0x18001d0fa  mov     rbx, rdx
0x18001d0fd  mov     rdi, rcx
0x18001d100  test    rdx, rdx
0x18001d103  jnz     short loc_18001D115
0x18001d105  mov     ebx, 80070057h
0x18001d10a  mov     r8d, 106h
0x18001d110  jmp     loc_18001D1E3
0x18001d115  mov     ecx, 38h ; '8'; Size
0x18001d11a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d11f  mov     [rsp+28h+arg_8], rax
0x18001d124  test    rax, rax
0x18001d127  jz      short loc_18001D155
0x18001d129  xorps   xmm0, xmm0
0x18001d12c  mov     qword ptr [rax], 0
0x18001d133  mov     qword ptr [rax+8], 0
0x18001d13b  mov     dword ptr [rax+10h], 0
0x18001d142  mov     dword ptr [rax+28h], 0
0x18001d149  mov     qword ptr [rax+30h], 0
0x18001d151  movups  xmmword ptr [rax+18h], xmm0
0x18001d155  mov     [rdi+8], rax
0x18001d159  test    rax, rax
0x18001d15c  jnz     short loc_18001D16B
0x18001d15e  mov     ebx, 8007000Eh
0x18001d163  mov     r8d, 109h
0x18001d169  jmp     short loc_18001D1E3
0x18001d16b  mov     rdx, [rdi]; struct Settings *
0x18001d16e  test    rdx, rdx
0x18001d171  jnz     short loc_18001D180
0x18001d173  mov     ebx, 80004003h
0x18001d178  mov     r8d, 10Bh
0x18001d17e  jmp     short loc_18001D1E3
0x18001d180  mov     r8, rbx; struct IXMLDOMNode *
0x18001d183  mov     rcx, rax; this
0x18001d186  call    ?Initialize@Script@@QEAAJPEAVSettings@@PEAUIXMLDOMNode@@@Z; Script::Initialize(Settings *,IXMLDOMNode *)
0x18001d18b  mov     ebx, eax
0x18001d18d  test    eax, eax
0x18001d18f  jns     short loc_18001D19C
0x18001d191  mov     r9d, eax
0x18001d194  mov     r8d, 10Eh
0x18001d19a  jmp     short loc_18001D1E6
0x18001d19c  cmp     eax, 1
0x18001d19f  jz      short loc_18001D1D8
0x18001d1a1  mov     rax, [rdi+8]
0x18001d1a5  test    rax, rax
0x18001d1a8  jz      short loc_18001D1D8
0x18001d1aa  mov     eax, [rax+10h]
0x18001d1ad  mov     rdx, [rdi]
0x18001d1b0  neg     eax
0x18001d1b2  sbb     ecx, ecx
0x18001d1b4  and     ecx, 0FFFF8000h
0x18001d1ba  add     ecx, 10000h
0x18001d1c0  or      [rdx+38h], ecx
0x18001d1c3  mov     rax, [rdi+8]
0x18001d1c7  cmp     dword ptr [rax+28h], 0
0x18001d1cb  jz      short loc_18001D1D4
0x18001d1cd  mov     rax, [rdi]
0x18001d1d0  or      dword ptr [rax+38h], 20h
0x18001d1d4  xor     ebx, ebx
0x18001d1d6  jmp     short loc_18001D1F7
0x18001d1d8  mov     ebx, 80004005h
0x18001d1dd  mov     r8d, 10Fh; int
0x18001d1e3  mov     r9d, ebx; int
0x18001d1e6  lea     rdx, aVerifierInitia_0; "Verifier::InitializeScript"
0x18001d1ed  mov     ecx, 1; Level
0x18001d1f2  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001d1f7  mov     eax, ebx
0x18001d1f9  mov     rbx, [rsp+28h+arg_0]
0x18001d1fe  add     rsp, 20h
0x18001d202  pop     rdi
0x18001d203  retn
```
