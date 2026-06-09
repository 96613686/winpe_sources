# FilterFindConfigurableMpCtx

- ea: `0x140003854`
- end: `0x1400038e9`
- name: `FilterFindConfigurableMpCtx`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004568`

## callees

- `0x140003854`
- `0x14000d8ec`

## pseudocode

```c
__int64 __fastcall FilterFindConfigurableMpCtx(__int64 a1, unsigned int *a2)
{
  int v2; // eax
  unsigned int v3; // r8d
  unsigned int v4; // ebx

  v2 = *(_DWORD *)(a1 + 2692);
  if ( v2 == 16 )
  {
    v3 = 4;
  }
  else
  {
    if ( v2 != 9 )
    {
      v4 = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
      return v4;
    }
    v3 = 1;
  }
  v4 = -1073741823;
  while ( v3 < *(_DWORD *)(a1 + 2684) )
  {
    if ( !*(_BYTE *)(*(_QWORD *)(a1 + 3120) + 144LL * v3) )
    {
      v4 = 0;
      *a2 = v3;
      return v4;
    }
    ++v3;
  }
  return v4;
}

```

## disassembly

```asm
0x140003854  push    rbx
0x140003856  sub     rsp, 20h
0x14000385a  mov     eax, [rcx+0A84h]
0x140003860  mov     r9, rcx
0x140003863  cmp     eax, 10h
0x140003866  jnz     short loc_1400038A7
0x140003868  lea     r8d, [rax-0Ch]
0x14000386c  mov     r10d, [rcx+0A7Ch]
0x140003873  mov     ebx, 0C0000001h
0x140003878  cmp     r8d, r10d
0x14000387b  jnb     short loc_140003899
0x14000387d  mov     eax, r8d
0x140003880  lea     rcx, [rax+rax*8]
0x140003884  mov     rax, [r9+0C30h]
0x14000388b  add     rcx, rcx
0x14000388e  cmp     byte ptr [rax+rcx*8], 0
0x140003892  jnz     short loc_1400038A2
0x140003894  xor     ebx, ebx
0x140003896  mov     [rdx], r8d
0x140003899  mov     eax, ebx
0x14000389b  add     rsp, 20h
0x14000389f  pop     rbx
0x1400038a0  retn
0x1400038a2  inc     r8d
0x1400038a5  jmp     short loc_140003878
0x1400038a7  cmp     eax, 9
0x1400038aa  jnz     short loc_1400038B2
0x1400038ac  lea     r8d, [rax-8]
0x1400038b0  jmp     short loc_14000386C
0x1400038b2  mov     ebx, 0C0000001h
0x1400038b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400038be  lea     rax, WPP_GLOBAL_Control
0x1400038c5  cmp     rcx, rax
0x1400038c8  jz      short loc_140003899
0x1400038ca  mov     edx, [rcx+2Ch]
0x1400038cd  test    dl, 1
0x1400038d0  jz      short loc_140003899
0x1400038d2  mov     rcx, [rcx+18h]
0x1400038d6  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x1400038dd  mov     edx, 16h
0x1400038e2  call    WPP_SF_
0x1400038e7  jmp     short loc_140003899
```
