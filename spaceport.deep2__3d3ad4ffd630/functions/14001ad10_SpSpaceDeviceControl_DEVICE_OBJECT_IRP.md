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

- `0x140035748`

## callees

- `0x14001ad10`
- `0x14002ce90`
- `0x140033c50`
- `0x1400347d8`
- `0x140035cf4`
- `0x1400a53a0`
- `0x1400a5960`
- `0x1400a5c38`
- `0x1400a5f64`
- `0x1400a6f24`
- `0x1400a6fec`
- `0x1400a7164`
- `0x1400b44a0`
- `0x1400b5320`
- `0x1400b6bb0`
- `0x1400b6fe0`
- `0x1400b91a0`

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
0x14001ad53  jnz     loc_14006ACA4
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
0x14006aca4  cmp     ebx, 2D1190h
0x14006acaa  ja      loc_14006AD64
0x14006acb0  jz      loc_14006AD53
0x14006acb6  cmp     ebx, 7405Ch
0x14006acbc  ja      short loc_14006AD1D
0x14006acbe  jz      short loc_14006AD0C
0x14006acc0  sub     ebx, 41018h
0x14006acc6  jz      short loc_14006ACFB
0x14006acc8  sub     ebx, 0BFECh
0x14006acce  jz      short loc_14006ACEA
0x14006acd0  cmp     ebx, 10h
0x14006acd3  jnz     loc_14006ADE8
0x14006acd9  mov     rdx, rdi; struct _IRP *
0x14006acdc  mov     rcx, rsi; struct SP_DEVICE *
0x14006acdf  call    ?SpScsiPassThroughDirect@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpScsiPassThroughDirect(SP_DEVICE *,_IRP *)
0x14006ace4  nop
0x14006ace5  jmp     loc_14001AD64
0x14006acea  mov     rdx, rdi; struct _IRP *
0x14006aced  mov     rcx, rsi; struct SP_DEVICE *
0x14006acf0  call    ?SpScsiPassThrough@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpScsiPassThrough(SP_DEVICE *,_IRP *)
0x14006acf5  nop
0x14006acf6  jmp     loc_14001AD64
0x14006acfb  mov     rdx, rdi; struct _IRP *
0x14006acfe  mov     rcx, rsi; this
0x14006ad01  call    ?SpGetAddress@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpGetAddress(SP_DEVICE *,_IRP *)
0x14006ad06  nop
0x14006ad07  jmp     loc_14001AD64
0x14006ad0c  mov     rdx, rdi; struct _IRP *
0x14006ad0f  mov     rcx, rsi; struct SP_DEVICE *
0x14006ad12  call    ?SpGetLengthInfo@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpGetLengthInfo(SP_DEVICE *,_IRP *)
0x14006ad17  nop
0x14006ad18  jmp     loc_14001AD64
0x14006ad1d  cmp     ebx, 7C220h
0x14006ad23  jz      short loc_14006AD42
0x14006ad25  cmp     ebx, 2D118Ch
0x14006ad2b  jnz     loc_14006ADE8
0x14006ad31  mov     rdx, rdi; struct _IRP *
0x14006ad34  mov     rcx, rsi; struct SP_DEVICE *
0x14006ad37  call    ?SpQueryDependentDisk@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpQueryDependentDisk(SP_DEVICE *,_IRP *)
0x14006ad3c  nop
0x14006ad3d  jmp     loc_14001AD64
0x14006ad42  mov     rdx, rdi; struct _IRP *
0x14006ad45  mov     rcx, rsi; this
0x14006ad48  call    ?SpDiskVolumesAreReady@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpDiskVolumesAreReady(SP_DEVICE *,_IRP *)
0x14006ad4d  nop
0x14006ad4e  jmp     loc_14001AD64
0x14006ad53  mov     rdx, rdi; struct _IRP *
0x14006ad56  mov     rcx, rsi; struct SP_DEVICE *
0x14006ad59  call    ?SpQueryDependentDiskQos@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpQueryDependentDiskQos(SP_DEVICE *,_IRP *)
0x14006ad5e  nop
0x14006ad5f  jmp     loc_14001AD64
0x14006ad64  cmp     ebx, 2D9404h
0x14006ad6a  ja      short loc_14006ADC7
0x14006ad6c  jz      short loc_14006ADB6
0x14006ad6e  sub     ebx, 2D164Bh
0x14006ad74  jz      short loc_14006ADA5
0x14006ad76  sub     ebx, 11DDh
0x14006ad7c  jz      short loc_14006AD94
0x14006ad7e  cmp     ebx, 8
0x14006ad81  jnz     short loc_14006ADE8
0x14006ad83  mov     rdx, rdi; struct _IRP *
0x14006ad86  mov     rcx, rsi; this
0x14006ad89  call    ?SpReleaseStreamId@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpReleaseStreamId(SP_DEVICE *,_IRP *)
0x14006ad8e  nop
0x14006ad8f  jmp     loc_14001AD64
0x14006ad94  mov     rdx, rdi; struct _IRP *
0x14006ad97  mov     rcx, rsi; this
0x14006ad9a  call    ?SpGetStreamParameters@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpGetStreamParameters(SP_DEVICE *,_IRP *)
0x14006ad9f  nop
0x14006ada0  jmp     loc_14001AD64
0x14006ada5  mov     rdx, rdi; struct _IRP *
0x14006ada8  mov     rcx, rsi; struct SP_DEVICE *
0x14006adab  call    ?SpGetDumpInfo@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpGetDumpInfo(SP_DEVICE *,_IRP *)
0x14006adb0  nop
0x14006adb1  jmp     loc_14001AD64
0x14006adb6  mov     rdx, rdi; struct _IRP *
0x14006adb9  mov     rcx, rsi; struct SP_DEVICE *
0x14006adbc  call    ?SpManageDataSetAttributes@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpManageDataSetAttributes(SP_DEVICE *,_IRP *)
0x14006adc1  nop
0x14006adc2  jmp     loc_14001AD64
0x14006adc7  cmp     ebx, 0E70A04h
0x14006adcd  jz      short loc_14006ADF2
0x14006adcf  cmp     ebx, 0E7CA08h
0x14006add5  jnz     short loc_14006ADE8
0x14006add7  mov     rdx, rdi; struct _IRP *
0x14006adda  mov     rcx, rsi; this
0x14006addd  call    ?SpTrim@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpTrim(SP_DEVICE *,_IRP *)
0x14006ade2  nop
0x14006ade3  jmp     loc_14001AD64
0x14006ade8  mov     ebx, 0C00000BBh
0x14006aded  jmp     loc_14001ADAA
0x14006adf2  mov     rdx, rdi; struct _IRP *
0x14006adf5  mov     rcx, rsi; this
0x14006adf8  call    ?SpGetDataLoss@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpGetDataLoss(SP_DEVICE *,_IRP *)
0x14006adfd  nop
0x14006adfe  jmp     loc_14001AD64
```
