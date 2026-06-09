# CMPEG2TSFormatPlugin::PinSetDataFormat(_KSPIN *,KSDATAFORMAT *,KSDATAFORMAT *,ulong *,ulong *)

- ea: `0x14003ebd0`
- end: `0x14003ec6e`
- name: `?PinSetDataFormat@CMPEG2TSFormatPlugin@@UEAAJPEAU_KSPIN@@PEATKSDATAFORMAT@@1PEAK2@Z`
- size: `158`
- prototype: `__int64 __fastcall(CMPEG2TSFormatPlugin *__hidden this, struct _KSPIN *, union KSDATAFORMAT *, union KSDATAFORMAT *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x14001b118`
- `0x14003ebd0`
- `0x140040a70`

## pseudocode

```c
__int64 __fastcall CMPEG2TSFormatPlugin::PinSetDataFormat(
        CMPEG2TSFormatPlugin *this,
        struct _KSPIN *a2,
        union KSDATAFORMAT *a3,
        union KSDATAFORMAT *a4)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_76389ff8e0f43d9eb559368648028ddd_Traceguids, a2->Id);
  if ( a3 && a2->DeviceState )
    return 3221225860LL;
  else
    return (*(__int64 (__fastcall **)(CMPEG2TSFormatPlugin *, _QWORD, PKSDATAFORMAT, const PKSDATARANGE *, ULONG))(*(_QWORD *)this + 88LL))(
             this,
             (unsigned int)a2->DataFlow,
             a2->ConnectionFormat,
             a2->Descriptor->PinDescriptor.DataRanges,
             a2->Descriptor->PinDescriptor.DataRangesCount) == 0
         ? 0xC0000272
         : 0;
}

```

## disassembly

```asm
0x14003ebd0  mov     [rsp+arg_0], rbx
0x14003ebd5  mov     [rsp+arg_8], rsi
0x14003ebda  push    rdi
0x14003ebdb  sub     rsp, 30h
0x14003ebdf  mov     rdi, r8
0x14003ebe2  mov     rbx, rdx
0x14003ebe5  mov     rsi, rcx
0x14003ebe8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ebef  lea     rax, WPP_GLOBAL_Control
0x14003ebf6  cmp     rcx, rax
0x14003ebf9  jz      short loc_14003EC1A
0x14003ebfb  cmp     byte ptr [rcx+29h], 5
0x14003ebff  jb      short loc_14003EC1A
0x14003ec01  mov     r9d, [rbx+18h]
0x14003ec05  lea     r8, WPP_76389ff8e0f43d9eb559368648028ddd_Traceguids
0x14003ec0c  mov     rcx, [rcx+18h]
0x14003ec10  mov     edx, 0Dh
0x14003ec15  call    WPP_SF_d
0x14003ec1a  test    rdi, rdi
0x14003ec1d  jz      short loc_14003EC2C
0x14003ec1f  cmp     dword ptr [rbx+78h], 0
0x14003ec23  jz      short loc_14003EC2C
0x14003ec25  mov     eax, 0C0000184h
0x14003ec2a  jmp     short loc_14003EC5D
0x14003ec2c  mov     r9, [rbx]
0x14003ec2f  mov     rax, [rsi]
0x14003ec32  mov     r8, [rbx+60h]
0x14003ec36  mov     edx, [rbx+74h]
0x14003ec39  mov     ecx, [r9+30h]
0x14003ec3d  mov     r9, [r9+38h]
0x14003ec41  mov     rax, [rax+58h]
0x14003ec45  mov     [rsp+38h+var_18], ecx
0x14003ec49  mov     rcx, rsi
0x14003ec4c  call    _guard_dispatch_icall
0x14003ec51  neg     rax
0x14003ec54  sbb     eax, eax
0x14003ec56  not     eax
0x14003ec58  and     eax, 0C0000272h
0x14003ec5d  mov     rbx, [rsp+38h+arg_0]
0x14003ec62  mov     rsi, [rsp+38h+arg_8]
0x14003ec67  add     rsp, 30h
0x14003ec6b  pop     rdi
0x14003ec6c  retn
```
