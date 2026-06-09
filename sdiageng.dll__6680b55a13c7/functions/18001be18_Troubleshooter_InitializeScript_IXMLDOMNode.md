# Troubleshooter::InitializeScript(IXMLDOMNode *)

- ea: `0x18001be18`
- end: `0x18001bf2c`
- name: `?InitializeScript@Troubleshooter@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(Troubleshooter *this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001bf34`

## callees

- `0x180001264`
- `0x18001be18`
- `0x18001db84`
- `0x180026fa0`

## pseudocode

```c
__int64 __fastcall Troubleshooter::InitializeScript(Troubleshooter *this, struct IXMLDOMNode *a2)
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
    v5 = 214;
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
    v5 = 217;
    goto LABEL_17;
  }
  if ( !*(_QWORD *)this )
  {
    v4 = -2147467261;
    v5 = 219;
    goto LABEL_17;
  }
  v7 = Script::Initialize((Script *)v6, *(struct Settings **)this, a2);
  v4 = v7;
  if ( v7 < 0 )
  {
    v8 = v7;
    v5 = 222;
LABEL_18:
    SdpDebugTrace(1u, L"Troubleshooter::InitializeScript", v5, v8);
    return v4;
  }
  if ( v7 == 1 || (v9 = *((_QWORD *)this + 1)) == 0 )
  {
    v4 = -2147467259;
    v5 = 223;
    goto LABEL_17;
  }
  *(_DWORD *)(*(_QWORD *)this + 56LL) |= *(_DWORD *)(v9 + 16) != 0 ? 2048 : 4096;
  if ( *(_DWORD *)(*((_QWORD *)this + 1) + 40LL) )
    *(_DWORD *)(*(_QWORD *)this + 56LL) |= 8u;
  return 0;
}

```

## disassembly

```asm
0x18001be18  mov     [rsp+arg_0], rbx
0x18001be1d  push    rdi
0x18001be1e  sub     rsp, 20h
0x18001be22  mov     rbx, rdx
0x18001be25  mov     rdi, rcx
0x18001be28  test    rdx, rdx
0x18001be2b  jnz     short loc_18001BE3D
0x18001be2d  mov     ebx, 80070057h
0x18001be32  mov     r8d, 0D6h
0x18001be38  jmp     loc_18001BF0B
0x18001be3d  mov     ecx, 38h ; '8'; Size
0x18001be42  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001be47  mov     [rsp+28h+arg_8], rax
0x18001be4c  test    rax, rax
0x18001be4f  jz      short loc_18001BE7D
0x18001be51  xorps   xmm0, xmm0
0x18001be54  mov     qword ptr [rax], 0
0x18001be5b  mov     qword ptr [rax+8], 0
0x18001be63  mov     dword ptr [rax+10h], 0
0x18001be6a  mov     dword ptr [rax+28h], 0
0x18001be71  mov     qword ptr [rax+30h], 0
0x18001be79  movups  xmmword ptr [rax+18h], xmm0
0x18001be7d  mov     [rdi+8], rax
0x18001be81  test    rax, rax
0x18001be84  jnz     short loc_18001BE93
0x18001be86  mov     ebx, 8007000Eh
0x18001be8b  mov     r8d, 0D9h
0x18001be91  jmp     short loc_18001BF0B
0x18001be93  mov     rdx, [rdi]; struct Settings *
0x18001be96  test    rdx, rdx
0x18001be99  jnz     short loc_18001BEA8
0x18001be9b  mov     ebx, 80004003h
0x18001bea0  mov     r8d, 0DBh
0x18001bea6  jmp     short loc_18001BF0B
0x18001bea8  mov     r8, rbx; struct IXMLDOMNode *
0x18001beab  mov     rcx, rax; this
0x18001beae  call    ?Initialize@Script@@QEAAJPEAVSettings@@PEAUIXMLDOMNode@@@Z; Script::Initialize(Settings *,IXMLDOMNode *)
0x18001beb3  mov     ebx, eax
0x18001beb5  test    eax, eax
0x18001beb7  jns     short loc_18001BEC4
0x18001beb9  mov     r9d, eax
0x18001bebc  mov     r8d, 0DEh
0x18001bec2  jmp     short loc_18001BF0E
0x18001bec4  cmp     eax, 1
0x18001bec7  jz      short loc_18001BF00
0x18001bec9  mov     rax, [rdi+8]
0x18001becd  test    rax, rax
0x18001bed0  jz      short loc_18001BF00
0x18001bed2  mov     rdx, [rdi]
0x18001bed5  mov     eax, [rax+10h]
0x18001bed8  neg     eax
0x18001beda  sbb     ecx, ecx
0x18001bedc  and     ecx, 0FFFFF800h
0x18001bee2  add     ecx, 1000h
0x18001bee8  or      [rdx+38h], ecx
0x18001beeb  mov     rax, [rdi+8]
0x18001beef  cmp     dword ptr [rax+28h], 0
0x18001bef3  jz      short loc_18001BEFC
0x18001bef5  mov     rax, [rdi]
0x18001bef8  or      dword ptr [rax+38h], 8
0x18001befc  xor     ebx, ebx
0x18001befe  jmp     short loc_18001BF1F
0x18001bf00  mov     ebx, 80004005h
0x18001bf05  mov     r8d, 0DFh; int
0x18001bf0b  mov     r9d, ebx; int
0x18001bf0e  lea     rdx, aTroubleshooter_4; "Troubleshooter::InitializeScript"
0x18001bf15  mov     ecx, 1; Level
0x18001bf1a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001bf1f  mov     eax, ebx
0x18001bf21  mov     rbx, [rsp+28h+arg_0]
0x18001bf26  add     rsp, 20h
0x18001bf2a  pop     rdi
0x18001bf2b  retn
```
