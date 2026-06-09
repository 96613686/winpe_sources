# InitializeProbeCommitControl

- ea: `0x14002af70`
- end: `0x14002b067`
- name: `InitializeProbeCommitControl`
- size: `247`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002b690`
- `0x14002b8e0`
- `0x14002bb20`
- `0x14002bd60`

## callees

- `0x140009dc8`
- `0x14001b15c`
- `0x14002af70`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x14002af84`
- `ks!KsGetFilterFromIrp` at `0x14002af84`
- `ks!KsGetDevice` at `0x14002aff2`
- `ks!KsGetDevice` at `0x14002aff2`

## pseudocode

```c
__int64 __fastcall InitializeProbeCommitControl(
        IRP *a1,
        unsigned int a2,
        _QWORD *a3,
        _QWORD *a4,
        PKSDEVICE *a5,
        _QWORD *a6)
{
  __int64 v7; // rbx
  PKSFILTER FilterFromIrp; // rax
  _QWORD *Context; // r9
  __int64 v11; // rbx
  __int64 result; // rax
  PKSDEVICE Device; // rdi
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rsi
  int v17; // edx
  SIZE_T NumberOfBytes; // [rsp+28h] [rbp-30h]

  v7 = a2;
  FilterFromIrp = KsGetFilterFromIrp(a1);
  if ( !FilterFromIrp || (unsigned int)v7 >= FilterFromIrp->Descriptor->PinDescriptorsCount )
    return 3221225473LL;
  Context = FilterFromIrp->Context;
  _mm_lfence();
  v11 = *(_QWORD *)(Context[8] + 8 * v7);
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_d768fed4ca1d3d5df3e949c91ce185dd_Traceguids, Context);
    return 3221225473LL;
  }
  Device = KsGetDevice(FilterFromIrp);
  if ( !Device )
    return 3221225473LL;
  v16 = *(_QWORD *)(v11 + 16);
  result = 0;
  if ( !*(_DWORD *)(v11 + 104)
    || (v17 = v11 + 184,
        LOBYTE(v15) = *(_BYTE *)(v11 + 177),
        LOBYTE(v14) = 2,
        LODWORD(NumberOfBytes) = *(_DWORD *)(v11 + 180),
        LOBYTE(v17) = -127,
        result = GetSetInterfaceControl((int)Device, v17, v14, v15, (void *)(v11 + 184), NumberOfBytes),
        (int)result >= 0) )
  {
    *a4 = v16;
    *a3 = v11 + 184;
    *a5 = Device;
    *a6 = v11;
  }
  return result;
}

```

## disassembly

```asm
0x14002af70  push    rbx
0x14002af72  push    rsi
0x14002af73  push    rdi
0x14002af74  push    r14
0x14002af76  push    r15
0x14002af78  sub     rsp, 30h
0x14002af7c  mov     r14, r9
0x14002af7f  mov     ebx, edx
0x14002af81  mov     r15, r8
0x14002af84  call    cs:__imp_KsGetFilterFromIrp
0x14002af8b  nop     dword ptr [rax+rax+00h]
0x14002af90  test    rax, rax
0x14002af93  jz      short loc_14002AFDD
0x14002af95  mov     rcx, [rax]
0x14002af98  cmp     ebx, [rcx+20h]
0x14002af9b  jnb     short loc_14002AFDD
0x14002af9d  mov     r9, [rax+10h]
0x14002afa1  lfence
0x14002afa4  mov     rcx, [r9+40h]
0x14002afa8  mov     rbx, [rcx+rbx*8]
0x14002afac  test    rbx, rbx
0x14002afaf  jnz     short loc_14002AFEF
0x14002afb1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002afb8  lea     rax, WPP_GLOBAL_Control
0x14002afbf  cmp     rcx, rax
0x14002afc2  jz      short loc_14002AFDD
0x14002afc4  cmp     byte ptr [rcx+29h], 5
0x14002afc8  jb      short loc_14002AFDD
0x14002afca  mov     rcx, [rcx+18h]
0x14002afce  lea     edx, [rbx+12h]
0x14002afd1  lea     r8, WPP_d768fed4ca1d3d5df3e949c91ce185dd_Traceguids
0x14002afd8  call    WPP_SF_q
0x14002afdd  mov     eax, 0C0000001h
0x14002afe2  add     rsp, 30h
0x14002afe6  pop     r15
0x14002afe8  pop     r14
0x14002afea  pop     rdi
0x14002afeb  pop     rsi
0x14002afec  pop     rbx
0x14002afed  retn
0x14002afef  mov     rcx, rax; Object
0x14002aff2  call    cs:__imp_KsGetDevice
0x14002aff9  nop     dword ptr [rax+rax+00h]
0x14002affe  mov     rdi, rax
0x14002b001  test    rax, rax
0x14002b004  jz      short loc_14002AFDD
0x14002b006  mov     rsi, [rbx+10h]
0x14002b00a  xor     eax, eax
0x14002b00c  cmp     [rbx+68h], eax
0x14002b00f  jz      short loc_14002B03F
0x14002b011  mov     ecx, [rbx+0B4h]
0x14002b017  lea     rdx, [rbx+0B8h]
0x14002b01e  mov     r9b, [rbx+0B1h]; int
0x14002b025  mov     r8b, 2; int
0x14002b028  mov     dword ptr [rsp+58h+NumberOfBytes], ecx; NumberOfBytes
0x14002b02c  mov     rcx, rdi; int
0x14002b02f  mov     [rsp+58h+Src], rdx; Src
0x14002b034  mov     dl, 81h; int
0x14002b036  call    GetSetInterfaceControl
0x14002b03b  test    eax, eax
0x14002b03d  js      short loc_14002AFE2
0x14002b03f  lea     rcx, [rbx+0B8h]
0x14002b046  mov     [r14], rsi
0x14002b049  mov     [r15], rcx
0x14002b04c  mov     rcx, [rsp+58h+arg_20]
0x14002b054  mov     [rcx], rdi
0x14002b057  mov     rcx, [rsp+58h+arg_28]
0x14002b05f  mov     [rcx], rbx
0x14002b062  jmp     loc_14002AFE2
```
