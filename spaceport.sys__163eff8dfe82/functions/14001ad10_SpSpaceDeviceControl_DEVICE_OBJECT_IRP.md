# SpSpaceDeviceControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x14001ad10`
- end: `0x14001ae54`
- name: `?SpSpaceDeviceControl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `324`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140035808`

## callees

- `0x14001ad10`
- `0x14002ce90`
- `0x140033d00`
- `0x140034898`
- `0x140035db4`
- `0x1400a54d0`
- `0x1400a5a90`
- `0x1400a5d68`
- `0x1400a6094`
- `0x1400a7054`
- `0x1400a711c`
- `0x1400a7294`
- `0x1400b4640`
- `0x1400b54c0`
- `0x1400b6d50`
- `0x1400b7180`
- `0x1400b9340`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001adb2`
- `ntoskrnl!IofCompleteRequest` at `0x14001adb2`

## pseudocode

```c
__int64 __fastcall SpSpaceDeviceControl(struct _DEVICE_OBJECT *a1, struct _IRP *a2, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct SP_DEVICE *v5; // rsi
  unsigned int LowPart; // ebx
  int Property; // eax
  int v8; // ebx
  ULONG DeviceType; // edx
  const char *v10; // r9
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  unsigned int v15; // ebx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = (struct SP_DEVICE *)((char *)a1->DeviceExtension + 8);
  a2->IoStatus.Information = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 39, a3, LowPart);
  }
  if ( LowPart == 2954240 )
  {
    Property = SpQueryProperty(v5, a2);
    goto LABEL_4;
  }
  if ( LowPart > 0x2D1190 )
  {
    if ( LowPart > 0x2D9404 )
    {
      if ( LowPart == 15141380 )
      {
        Property = SpGetDataLoss(v5, a2);
      }
      else
      {
        if ( LowPart != 15190536 )
          goto LABEL_51;
        Property = SpTrim(v5, a2);
      }
    }
    else if ( LowPart == 2987012 )
    {
      Property = SpManageDataSetAttributes(v5, a2);
    }
    else
    {
      v14 = LowPart - 2954827;
      if ( v14 )
      {
        v15 = v14 - 4573;
        if ( v15 )
        {
          if ( v15 != 8 )
            goto LABEL_51;
          Property = SpReleaseStreamId(v5, a2);
        }
        else
        {
          Property = SpGetStreamParameters(v5, a2);
        }
      }
      else
      {
        Property = SpGetDumpInfo(v5, a2);
      }
    }
  }
  else if ( LowPart == 2953616 )
  {
    Property = SpQueryDependentDiskQos(v5, a2);
  }
  else if ( LowPart > 0x7405C )
  {
    if ( LowPart == 508448 )
    {
      Property = SpDiskVolumesAreReady(v5, a2);
    }
    else
    {
      if ( LowPart != 2953612 )
        goto LABEL_51;
      Property = SpQueryDependentDisk(v5, a2);
    }
  }
  else if ( LowPart == 475228 )
  {
    Property = SpGetLengthInfo(v5, a2);
  }
  else
  {
    v12 = LowPart - 266264;
    if ( v12 )
    {
      v13 = v12 - 49132;
      if ( v13 )
      {
        if ( v13 == 16 )
        {
          Property = SpScsiPassThroughDirect(v5, a2);
          goto LABEL_4;
        }
LABEL_51:
        v8 = -1073741637;
        goto LABEL_12;
      }
      Property = SpScsiPassThrough(v5, a2);
    }
    else
    {
      Property = SpGetAddress(v5, a2);
    }
  }
LABEL_4:
  v8 = Property;
  if ( Property != 259 )
  {
LABEL_12:
    a2->IoStatus.Status = v8;
    IofCompleteRequest(a2, 0);
  }
  if ( v8 >= 0 || v8 == -2147483643 || v8 == -1073741789 )
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 3 )
    {
      DeviceType = 3;
      WPP_MAIN_CB.DeviceType = 3;
    }
    v10 = "Exit ";
  }
  else
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v10 = "Error";
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      40,
      (unsigned int)WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids,
      (_DWORD)v10,
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001ad10  push    rbx
0x14001ad12  push    rbp
0x14001ad13  push    rsi
0x14001ad14  push    rdi
0x14001ad15  sub     rsp, 38h
0x14001ad19  mov     rsi, [rcx+40h]
0x14001ad1d  mov     rdi, rdx
0x14001ad20  mov     rax, [rdx+0B8h]
0x14001ad27  add     rsi, 8
0x14001ad2b  mov     qword ptr [rdx+38h], 0
0x14001ad33  mov     ebx, [rax+18h]
0x14001ad36  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ad3d  lea     rbp, WPP_GLOBAL_Control
0x14001ad44  cmp     rcx, rbp
0x14001ad47  jnz     loc_14001ADEF
0x14001ad4d  cmp     ebx, 2D1400h
0x14001ad53  jnz     loc_14006ADE4
0x14001ad59  mov     rdx, rdi; struct _IRP *
0x14001ad5c  mov     rcx, rsi; struct SP_DEVICE *
0x14001ad5f  call    ?SpQueryProperty@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpQueryProperty(SP_DEVICE *,_IRP *)
0x14001ad64  mov     ebx, eax
0x14001ad66  cmp     eax, 103h
0x14001ad6b  jnz     short loc_14001ADAA
0x14001ad6d  test    ebx, ebx
0x14001ad6f  js      short loc_14001ADC0
0x14001ad71  mov     edx, cs:WPP_MAIN_CB.DeviceType
0x14001ad77  cmp     edx, 3
0x14001ad7a  jnz     loc_14001AE1A
0x14001ad80  lea     r9, aExit; "Exit "
0x14001ad87  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ad8e  cmp     rcx, rbp
0x14001ad91  jz      short loc_14001AD9E
0x14001ad93  mov     eax, [rcx+2Ch]
0x14001ad96  test    al, 1
0x14001ad98  jnz     loc_14001AE2A
0x14001ad9e  mov     eax, ebx
0x14001ada0  add     rsp, 38h
0x14001ada4  pop     rdi
0x14001ada5  pop     rsi
0x14001ada6  pop     rbp
0x14001ada7  pop     rbx
0x14001ada8  retn
0x14001adaa  xor     edx, edx; PriorityBoost
0x14001adac  mov     [rdi+30h], ebx
0x14001adaf  mov     rcx, rdi; Irp
0x14001adb2  call    cs:__imp_IofCompleteRequest
0x14001adb9  nop     dword ptr [rax+rax+00h]
0x14001adbe  jmp     short loc_14001AD6D
0x14001adc0  cmp     ebx, 80000005h
0x14001adc6  jz      short loc_14001AD71
0x14001adc8  cmp     ebx, 0C0000023h
0x14001adce  jz      short loc_14001AD71
0x14001add0  mov     edx, cs:WPP_MAIN_CB.DeviceType
0x14001add6  cmp     edx, 1
0x14001add9  jz      short loc_14001ADE6
0x14001addb  mov     edx, 1
0x14001ade0  mov     cs:WPP_MAIN_CB.DeviceType, edx
0x14001ade6  lea     r9, aError; "Error"
0x14001aded  jmp     short loc_14001AD87
0x14001adef  mov     eax, [rcx+2Ch]
0x14001adf2  test    al, 1
0x14001adf4  jz      loc_14001AD4D
0x14001adfa  cmp     byte ptr [rcx+29h], 3
0x14001adfe  jb      loc_14001AD4D
0x14001ae04  mov     rcx, [rcx+18h]
0x14001ae08  mov     edx, 27h ; '''
0x14001ae0d  mov     r9d, ebx
0x14001ae10  call    WPP_SF_D
0x14001ae15  jmp     loc_14001AD4D
0x14001ae1a  mov     edx, 3
0x14001ae1f  mov     cs:WPP_MAIN_CB.DeviceType, edx
0x14001ae25  jmp     loc_14001AD80
0x14001ae2a  movzx   eax, byte ptr [rcx+29h]
0x14001ae2e  cmp     eax, edx
0x14001ae30  jb      loc_14001AD9E
0x14001ae36  mov     rcx, [rcx+18h]
0x14001ae3a  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x14001ae41  mov     edx, 28h ; '('
0x14001ae46  mov     [rsp+58h+var_38], ebx
0x14001ae4a  call    WPP_SF_sd
0x14001ae4f  jmp     loc_14001AD9E
0x14006ade4  cmp     ebx, 2D1190h
0x14006adea  ja      loc_14006AEA4
0x14006adf0  jz      loc_14006AE93
0x14006adf6  cmp     ebx, 7405Ch
0x14006adfc  ja      short loc_14006AE5D
0x14006adfe  jz      short loc_14006AE4C
0x14006ae00  sub     ebx, 41018h
0x14006ae06  jz      short loc_14006AE3B
0x14006ae08  sub     ebx, 0BFECh
0x14006ae0e  jz      short loc_14006AE2A
0x14006ae10  cmp     ebx, 10h
0x14006ae13  jnz     loc_14006AF28
0x14006ae19  mov     rdx, rdi; struct _IRP *
0x14006ae1c  mov     rcx, rsi; struct SP_DEVICE *
0x14006ae1f  call    ?SpScsiPassThroughDirect@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpScsiPassThroughDirect(SP_DEVICE *,_IRP *)
0x14006ae24  nop
0x14006ae25  jmp     loc_14001AD64
0x14006ae2a  mov     rdx, rdi; struct _IRP *
0x14006ae2d  mov     rcx, rsi; struct SP_DEVICE *
0x14006ae30  call    ?SpScsiPassThrough@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpScsiPassThrough(SP_DEVICE *,_IRP *)
0x14006ae35  nop
0x14006ae36  jmp     loc_14001AD64
0x14006ae3b  mov     rdx, rdi; struct _IRP *
0x14006ae3e  mov     rcx, rsi; this
0x14006ae41  call    ?SpGetAddress@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpGetAddress(SP_DEVICE *,_IRP *)
0x14006ae46  nop
0x14006ae47  jmp     loc_14001AD64
0x14006ae4c  mov     rdx, rdi; struct _IRP *
0x14006ae4f  mov     rcx, rsi; struct SP_DEVICE *
0x14006ae52  call    ?SpGetLengthInfo@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpGetLengthInfo(SP_DEVICE *,_IRP *)
0x14006ae57  nop
0x14006ae58  jmp     loc_14001AD64
0x14006ae5d  cmp     ebx, 7C220h
0x14006ae63  jz      short loc_14006AE82
0x14006ae65  cmp     ebx, 2D118Ch
0x14006ae6b  jnz     loc_14006AF28
0x14006ae71  mov     rdx, rdi; struct _IRP *
0x14006ae74  mov     rcx, rsi; struct SP_DEVICE *
0x14006ae77  call    ?SpQueryDependentDisk@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpQueryDependentDisk(SP_DEVICE *,_IRP *)
0x14006ae7c  nop
0x14006ae7d  jmp     loc_14001AD64
0x14006ae82  mov     rdx, rdi; struct _IRP *
0x14006ae85  mov     rcx, rsi; this
0x14006ae88  call    ?SpDiskVolumesAreReady@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpDiskVolumesAreReady(SP_DEVICE *,_IRP *)
0x14006ae8d  nop
0x14006ae8e  jmp     loc_14001AD64
0x14006ae93  mov     rdx, rdi; struct _IRP *
0x14006ae96  mov     rcx, rsi; struct SP_DEVICE *
0x14006ae99  call    ?SpQueryDependentDiskQos@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpQueryDependentDiskQos(SP_DEVICE *,_IRP *)
0x14006ae9e  nop
0x14006ae9f  jmp     loc_14001AD64
0x14006aea4  cmp     ebx, 2D9404h
0x14006aeaa  ja      short loc_14006AF07
0x14006aeac  jz      short loc_14006AEF6
0x14006aeae  sub     ebx, 2D164Bh
0x14006aeb4  jz      short loc_14006AEE5
0x14006aeb6  sub     ebx, 11DDh
0x14006aebc  jz      short loc_14006AED4
0x14006aebe  cmp     ebx, 8
0x14006aec1  jnz     short loc_14006AF28
0x14006aec3  mov     rdx, rdi; struct _IRP *
0x14006aec6  mov     rcx, rsi; this
0x14006aec9  call    ?SpReleaseStreamId@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpReleaseStreamId(SP_DEVICE *,_IRP *)
0x14006aece  nop
0x14006aecf  jmp     loc_14001AD64
0x14006aed4  mov     rdx, rdi; struct _IRP *
0x14006aed7  mov     rcx, rsi; this
0x14006aeda  call    ?SpGetStreamParameters@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpGetStreamParameters(SP_DEVICE *,_IRP *)
0x14006aedf  nop
0x14006aee0  jmp     loc_14001AD64
0x14006aee5  mov     rdx, rdi; struct _IRP *
0x14006aee8  mov     rcx, rsi; struct SP_DEVICE *
0x14006aeeb  call    ?SpGetDumpInfo@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpGetDumpInfo(SP_DEVICE *,_IRP *)
0x14006aef0  nop
0x14006aef1  jmp     loc_14001AD64
0x14006aef6  mov     rdx, rdi; struct _IRP *
0x14006aef9  mov     rcx, rsi; struct SP_DEVICE *
0x14006aefc  call    ?SpManageDataSetAttributes@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpManageDataSetAttributes(SP_DEVICE *,_IRP *)
0x14006af01  nop
0x14006af02  jmp     loc_14001AD64
0x14006af07  cmp     ebx, 0E70A04h
0x14006af0d  jz      short loc_14006AF32
0x14006af0f  cmp     ebx, 0E7CA08h
0x14006af15  jnz     short loc_14006AF28
0x14006af17  mov     rdx, rdi; struct _IRP *
0x14006af1a  mov     rcx, rsi; this
0x14006af1d  call    ?SpTrim@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpTrim(SP_DEVICE *,_IRP *)
0x14006af22  nop
0x14006af23  jmp     loc_14001AD64
0x14006af28  mov     ebx, 0C00000BBh
0x14006af2d  jmp     loc_14001ADAA
0x14006af32  mov     rdx, rdi; struct _IRP *
0x14006af35  mov     rcx, rsi; this
0x14006af38  call    ?SpGetDataLoss@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpGetDataLoss(SP_DEVICE *,_IRP *)
0x14006af3d  nop
0x14006af3e  jmp     loc_14001AD64
```
