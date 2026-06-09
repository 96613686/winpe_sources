# UpdateFilterMpAttributesWithPMCapabilities

- ea: `0x140001008`
- end: `0x14000116d`
- name: `UpdateFilterMpAttributesWithPMCapabilities`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1400027d0`

## callees

- `0x140001008`
- `0x140001174`
- `0x14000cd98`
- `0x14000d8ec`
- `0x14000d91c`

## pseudocode

```c
__int64 __fastcall UpdateFilterMpAttributesWithPMCapabilities(__int64 a1, __int64 a2)
{
  unsigned int MpPowerCaps; // edi
  int v5; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 118, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  MpPowerCaps = FilterGetMpPowerCaps(a1, a2);
  if ( MpPowerCaps )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return MpPowerCaps;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 119, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  }
  else
  {
    *(_BYTE *)(a2 + 2296) = -97;
    *(_WORD *)(a2 + 2298) = 224;
    v5 = *(_DWORD *)(a2 + 2692);
    if ( v5 == 16 )
    {
      *(_BYTE *)(a2 + 2297) = 1;
      if ( !*(_QWORD *)(a2 + 2696) )
        TraceAssert("pFilter->pnpCapabilities != NULL", "onecoreuap\\net\\vwifi\\filter\\filter.c", 1959);
      *(_QWORD *)(a2 + 2368) = *(_QWORD *)(a2 + 2696);
    }
    else if ( v5 == 9 )
    {
      *(_BYTE *)(a2 + 2297) = 2;
      if ( !*(_QWORD *)(a2 + 2704) )
        TraceAssert("pFilter->pmCapabilities != NULL", "onecoreuap\\net\\vwifi\\filter\\filter.c", 1968);
      *(_QWORD *)(a2 + 2512) = *(_QWORD *)(a2 + 2704);
    }
    else
    {
      MpPowerCaps = -1073741823;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 120, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  return MpPowerCaps;
}

```

## disassembly

```asm
0x140001008  mov     [rsp+arg_0], rbx
0x14000100d  mov     [rsp+arg_8], rsi
0x140001012  push    rdi
0x140001013  sub     rsp, 20h
0x140001017  mov     rbx, rdx
0x14000101a  mov     rdi, rcx
0x14000101d  mov     rcx, cs:WPP_GLOBAL_Control
0x140001024  lea     rsi, WPP_GLOBAL_Control
0x14000102b  cmp     rcx, rsi
0x14000102e  jz      short loc_14000104C
0x140001030  mov     eax, [rcx+2Ch]
0x140001033  test    al, 20h
0x140001035  jz      short loc_14000104C
0x140001037  mov     rcx, [rcx+18h]
0x14000103b  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140001042  mov     edx, 76h ; 'v'
0x140001047  call    WPP_SF_
0x14000104c  mov     rdx, rbx
0x14000104f  mov     rcx, rdi
0x140001052  call    FilterGetMpPowerCaps
0x140001057  mov     edi, eax
0x140001059  test    eax, eax
0x14000105b  jz      short loc_140001096
0x14000105d  mov     rcx, cs:WPP_GLOBAL_Control
0x140001064  cmp     rcx, rsi
0x140001067  jz      loc_14000115A
0x14000106d  mov     edx, [rcx+2Ch]
0x140001070  test    dl, 1
0x140001073  jz      loc_14000112F
0x140001079  mov     rcx, [rcx+18h]
0x14000107d  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140001084  mov     edx, 77h ; 'w'
0x140001089  mov     r9d, eax
0x14000108c  call    WPP_SF_d
0x140001091  jmp     loc_14000112F
0x140001096  mov     byte ptr [rbx+8F8h], 9Fh
0x14000109d  mov     word ptr [rbx+8FAh], 0E0h
0x1400010a6  mov     eax, [rbx+0A84h]
0x1400010ac  cmp     eax, 10h
0x1400010af  jnz     short loc_1400010EB
0x1400010b1  mov     byte ptr [rbx+8F9h], 1
0x1400010b8  cmp     qword ptr [rbx+0A88h], 0
0x1400010c0  jnz     short loc_1400010DB
0x1400010c2  mov     r8d, 7A7h
0x1400010c8  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x1400010cf  lea     rcx, aPfilterPnpcapa; "pFilter->pnpCapabilities != NULL"
0x1400010d6  call    TraceAssert
0x1400010db  mov     rax, [rbx+0A88h]
0x1400010e2  mov     [rbx+940h], rax
0x1400010e9  jmp     short loc_14000112F
0x1400010eb  cmp     eax, 9
0x1400010ee  jnz     short loc_14000112A
0x1400010f0  mov     byte ptr [rbx+8F9h], 2
0x1400010f7  cmp     qword ptr [rbx+0A90h], 0
0x1400010ff  jnz     short loc_14000111A
0x140001101  mov     r8d, 7B0h
0x140001107  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000110e  lea     rcx, aPfilterPmcapab; "pFilter->pmCapabilities != NULL"
0x140001115  call    TraceAssert
0x14000111a  mov     rax, [rbx+0A90h]
0x140001121  mov     [rbx+9D0h], rax
0x140001128  jmp     short loc_14000112F
0x14000112a  mov     edi, 0C0000001h
0x14000112f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001136  cmp     rcx, rsi
0x140001139  jz      short loc_14000115A
0x14000113b  mov     eax, [rcx+2Ch]
0x14000113e  test    al, 20h
0x140001140  jz      short loc_14000115A
0x140001142  mov     rcx, [rcx+18h]
0x140001146  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000114d  mov     edx, 78h ; 'x'
0x140001152  mov     r9d, edi
0x140001155  call    WPP_SF_d
0x14000115a  mov     rbx, [rsp+28h+arg_0]
0x14000115f  mov     eax, edi
0x140001161  mov     rsi, [rsp+28h+arg_8]
0x140001166  add     rsp, 20h
0x14000116a  pop     rdi
0x14000116b  retn
```
