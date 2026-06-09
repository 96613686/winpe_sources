# SpSpaceFileSystemControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400354f0`
- end: `0x140035606`
- name: `?SpSpaceFileSystemControl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `278`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14002ce90`
- `0x1400354f0`
- `0x14003569c`
- `0x140035db4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140035559`
- `ntoskrnl!IofCompleteRequest` at `0x140035559`

## pseudocode

```c
__int64 __fastcall SpSpaceFileSystemControl(struct _DEVICE_OBJECT *a1, struct _IRP *a2, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  char *DeviceExtension; // rsi
  DWORD LowPart; // ebx
  unsigned int v7; // ebx
  int v8; // eax
  ULONG DeviceType; // ecx
  const char *v10; // r9

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  DeviceExtension = (char *)a1->DeviceExtension;
  a2->IoStatus.Information = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 37, a3, LowPart);
  }
  if ( LowPart != 590752 )
  {
    v7 = -1073741637;
    a2->IoStatus.Status = -1073741637;
    IofCompleteRequest(a2, 0);
LABEL_10:
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v10 = "Error";
    goto LABEL_16;
  }
  v8 = SpSsdiStorageRequest((struct SP_DEVICE *)(DeviceExtension + 8), a2);
  v7 = v8;
  if ( v8 < 0 && v8 != -2147483643 && v8 != -1073741789 )
    goto LABEL_10;
  DeviceType = WPP_MAIN_CB.DeviceType;
  if ( WPP_MAIN_CB.DeviceType != 3 )
  {
    DeviceType = 3;
    WPP_MAIN_CB.DeviceType = 3;
  }
  v10 = "Exit ";
LABEL_16:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      38,
      (unsigned int)WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids,
      (_DWORD)v10,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x1400354f0  push    rbx
0x1400354f2  push    rsi
0x1400354f3  push    rdi
0x1400354f4  push    r14
0x1400354f6  sub     rsp, 38h
0x1400354fa  mov     rax, [rdx+0B8h]
0x140035501  mov     rdi, rdx
0x140035504  mov     rsi, [rcx+40h]
0x140035508  mov     qword ptr [rdx+38h], 0
0x140035510  mov     ebx, [rax+18h]
0x140035513  mov     rcx, cs:WPP_GLOBAL_Control
0x14003551a  lea     r14, WPP_GLOBAL_Control
0x140035521  cmp     rcx, r14
0x140035524  jz      short loc_140035544
0x140035526  mov     eax, [rcx+2Ch]
0x140035529  test    al, 1
0x14003552b  jz      short loc_140035544
0x14003552d  cmp     byte ptr [rcx+29h], 3
0x140035531  jb      short loc_140035544
0x140035533  mov     rcx, [rcx+18h]
0x140035537  mov     edx, 25h ; '%'
0x14003553c  mov     r9d, ebx
0x14003553f  call    WPP_SF_D
0x140035544  cmp     ebx, 903A0h
0x14003554a  jz      short loc_140035567
0x14003554c  mov     ebx, 0C00000BBh
0x140035551  xor     edx, edx; PriorityBoost
0x140035553  mov     rcx, rdi; Irp
0x140035556  mov     [rdi+30h], ebx
0x140035559  call    cs:__imp_IofCompleteRequest
0x140035560  nop     dword ptr [rax+rax+00h]
0x140035565  jmp     short loc_140035587
0x140035567  lea     rcx, [rsi+8]; struct SP_DEVICE *
0x14003556b  mov     rdx, rdi; struct _IRP *
0x14003556e  call    ?SpSsdiStorageRequest@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpSsdiStorageRequest(SP_DEVICE *,_IRP *)
0x140035573  mov     ebx, eax
0x140035575  test    eax, eax
0x140035577  jns     short loc_1400355A6
0x140035579  cmp     eax, 80000005h
0x14003557e  jz      short loc_1400355A6
0x140035580  cmp     eax, 0C0000023h
0x140035585  jz      short loc_1400355A6
0x140035587  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x14003558d  cmp     ecx, 1
0x140035590  jz      short loc_14003559D
0x140035592  mov     ecx, 1
0x140035597  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x14003559d  lea     r9, aError; "Error"
0x1400355a4  jmp     short loc_1400355C3
0x1400355a6  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400355ac  cmp     ecx, 3
0x1400355af  jz      short loc_1400355BC
0x1400355b1  mov     ecx, 3
0x1400355b6  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400355bc  lea     r9, aExit; "Exit "
0x1400355c3  mov     r10, cs:WPP_GLOBAL_Control
0x1400355ca  cmp     r10, r14
0x1400355cd  jz      short loc_1400355F9
0x1400355cf  mov     eax, [r10+2Ch]
0x1400355d3  test    al, 1
0x1400355d5  jz      short loc_1400355F9
0x1400355d7  movzx   eax, byte ptr [r10+29h]
0x1400355dc  cmp     eax, ecx
0x1400355de  jb      short loc_1400355F9
0x1400355e0  mov     rcx, [r10+18h]
0x1400355e4  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x1400355eb  mov     edx, 26h ; '&'
0x1400355f0  mov     [rsp+58h+var_38], ebx
0x1400355f4  call    WPP_SF_sd
0x1400355f9  mov     eax, ebx
0x1400355fb  add     rsp, 38h
0x1400355ff  pop     r14
0x140035601  pop     rdi
0x140035602  pop     rsi
0x140035603  pop     rbx
0x140035604  retn
```
