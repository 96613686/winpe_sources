# FilterAllocateMpCtxs

- ea: `0x140002710`
- end: `0x1400027c1`
- name: `FilterAllocateMpCtxs`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140002c90`

## callees

- `0x14000253c`
- `0x140002710`
- `0x14000d0a4`
- `0x14000d8ec`
- `0x14000d91c`

## pseudocode

```c
__int64 __fastcall FilterAllocateMpCtxs(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // eax
  unsigned int VWifiMpCtxs; // eax
  unsigned int v8; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  v6 = *(_DWORD *)(a3 + 2692);
  if ( v6 == 16 )
  {
    VWifiMpCtxs = FilterAllocateVWifiMpCtxs(a1, *(_QWORD *)(*(_QWORD *)(a2 + 80) + 40LL), a3);
  }
  else
  {
    if ( v6 != 9 )
    {
      v8 = -1073741823;
      goto LABEL_10;
    }
    VWifiMpCtxs = FilterAllocateWWANMpCtxs(a1, a3);
  }
  v8 = VWifiMpCtxs;
LABEL_10:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  return v8;
}

```

## disassembly

```asm
0x140002710  push    rbx
0x140002712  push    rbp
0x140002713  push    rsi
0x140002714  push    rdi
0x140002715  sub     rsp, 28h
0x140002719  mov     rbx, r8
0x14000271c  mov     rsi, rdx
0x14000271f  mov     rdi, rcx
0x140002722  mov     rcx, cs:WPP_GLOBAL_Control
0x140002729  lea     rbp, WPP_GLOBAL_Control
0x140002730  cmp     rcx, rbp
0x140002733  jz      short loc_140002751
0x140002735  mov     eax, [rcx+2Ch]
0x140002738  test    al, 20h
0x14000273a  jz      short loc_140002751
0x14000273c  mov     rcx, [rcx+18h]
0x140002740  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140002747  mov     edx, 6Bh ; 'k'
0x14000274c  call    WPP_SF_
0x140002751  mov     eax, [rbx+0A84h]
0x140002757  cmp     eax, 10h
0x14000275a  jnz     short loc_140002771
0x14000275c  mov     rdx, [rsi+50h]
0x140002760  mov     r8, rbx
0x140002763  mov     rcx, rdi
0x140002766  mov     rdx, [rdx+28h]
0x14000276a  call    FilterAllocateVWifiMpCtxs
0x14000276f  jmp     short loc_140002781
0x140002771  cmp     eax, 9
0x140002774  jnz     short loc_140002785
0x140002776  mov     rdx, rbx
0x140002779  mov     rcx, rdi
0x14000277c  call    FilterAllocateWWANMpCtxs
0x140002781  mov     ebx, eax
0x140002783  jmp     short loc_14000278A
0x140002785  mov     ebx, 0C0000001h
0x14000278a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002791  cmp     rcx, rbp
0x140002794  jz      short loc_1400027B5
0x140002796  mov     eax, [rcx+2Ch]
0x140002799  test    al, 20h
0x14000279b  jz      short loc_1400027B5
0x14000279d  mov     rcx, [rcx+18h]
0x1400027a1  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x1400027a8  mov     edx, 6Ch ; 'l'
0x1400027ad  mov     r9d, ebx
0x1400027b0  call    WPP_SF_d
0x1400027b5  mov     eax, ebx
0x1400027b7  add     rsp, 28h
0x1400027bb  pop     rdi
0x1400027bc  pop     rsi
0x1400027bd  pop     rbp
0x1400027be  pop     rbx
0x1400027bf  retn
```
