# FilterRemoveMpLink

- ea: `0x140003fe8`
- end: `0x1400040d2`
- name: `FilterRemoveMpLink`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400038f0`
- `0x14000d690`

## callees

- `0x140003fe8`
- `0x14000443c`
- `0x1400057f8`
- `0x14000cd98`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000dd28`

## pseudocode

```c
__int64 __fastcall FilterRemoveMpLink(__int64 a1)
{
  __int64 result; // rax
  void *v3; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x20) != 0 )
      result = WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids);
  }
  if ( *(_BYTE *)(a1 + 1) )
  {
    if ( *(_DWORD *)(a1 + 124) )
      TraceAssert("0 == pFilterMpCtx->OutstandingSends", "onecoreuap\\net\\vwifi\\filter\\fltintf.c", 45);
    FilterWaitForVariable(a1 + 128);
    FilterWaitForVariable(a1 + 140);
    v3 = *(void **)(a1 + 8);
    *(_BYTE *)(a1 + 1) = 0;
    result = FilterDeRef(v3);
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return result;
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 4) != 0 )
      result = WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids, a1);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x20) != 0 )
      return WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140003fe8  mov     [rsp+arg_0], rbx
0x140003fed  push    rsi
0x140003fee  sub     rsp, 20h
0x140003ff2  mov     rbx, rcx
0x140003ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ffc  lea     rsi, WPP_GLOBAL_Control
0x140004003  cmp     rcx, rsi
0x140004006  jz      short loc_140004024
0x140004008  mov     eax, [rcx+2Ch]
0x14000400b  test    al, 20h
0x14000400d  jz      short loc_140004024
0x14000400f  mov     rcx, [rcx+18h]
0x140004013  lea     r8, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids
0x14000401a  mov     edx, 0Ah
0x14000401f  call    WPP_SF_
0x140004024  cmp     byte ptr [rbx+1], 0
0x140004028  jz      short loc_140004070
0x14000402a  cmp     dword ptr [rbx+7Ch], 0
0x14000402e  jz      short loc_140004049
0x140004030  mov     r8d, 2Dh ; '-'
0x140004036  lea     rdx, aOnecoreuapNetV_2; "onecoreuap\\net\\vwifi\\filter\\fltintf"...
0x14000403d  lea     rcx, a0PfiltermpctxO; "0 == pFilterMpCtx->OutstandingSends"
0x140004044  call    TraceAssert
0x140004049  lea     rcx, [rbx+80h]
0x140004050  call    FilterWaitForVariable
0x140004055  lea     rcx, [rbx+8Ch]
0x14000405c  call    FilterWaitForVariable
0x140004061  mov     rcx, [rbx+8]; VirtualAddress
0x140004065  mov     byte ptr [rbx+1], 0
0x140004069  call    FilterDeRef
0x14000406e  jmp     short loc_14000409B
0x140004070  mov     rcx, cs:WPP_GLOBAL_Control
0x140004077  cmp     rcx, rsi
0x14000407a  jz      short loc_1400040C6
0x14000407c  mov     eax, [rcx+2Ch]
0x14000407f  test    al, 4
0x140004081  jz      short loc_14000409B
0x140004083  mov     rcx, [rcx+18h]
0x140004087  lea     r8, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids
0x14000408e  mov     edx, 0Bh
0x140004093  mov     r9, rbx
0x140004096  call    WPP_SF_q
0x14000409b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400040a2  cmp     rcx, rsi
0x1400040a5  jz      short loc_1400040C6
0x1400040a7  mov     eax, [rcx+2Ch]
0x1400040aa  test    al, 20h
0x1400040ac  jz      short loc_1400040C6
0x1400040ae  mov     rcx, [rcx+18h]
0x1400040b2  lea     r8, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids
0x1400040b9  mov     edx, 0Ch
0x1400040be  xor     r9d, r9d
0x1400040c1  call    WPP_SF_d
0x1400040c6  mov     rbx, [rsp+28h+arg_0]
0x1400040cb  add     rsp, 20h
0x1400040cf  pop     rsi
0x1400040d0  retn
```
