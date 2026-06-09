# SpSpaceFileSystemControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140035430`
- end: `0x140035546`
- name: `?SpSpaceFileSystemControl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `278`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14002ce90`
- `0x140035430`
- `0x1400355dc`
- `0x140035cf4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140035499`
- `ntoskrnl!IofCompleteRequest` at `0x140035499`

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
0x140035430  push    rbx
0x140035432  push    rsi
0x140035433  push    rdi
0x140035434  push    r14
0x140035436  sub     rsp, 38h
0x14003543a  mov     rax, [rdx+0B8h]
0x140035441  mov     rdi, rdx
0x140035444  mov     rsi, [rcx+40h]
0x140035448  mov     qword ptr [rdx+38h], 0
0x140035450  mov     ebx, [rax+18h]
0x140035453  mov     rcx, cs:WPP_GLOBAL_Control
0x14003545a  lea     r14, WPP_GLOBAL_Control
0x140035461  cmp     rcx, r14
0x140035464  jz      short loc_140035484
0x140035466  mov     eax, [rcx+2Ch]
0x140035469  test    al, 1
0x14003546b  jz      short loc_140035484
0x14003546d  cmp     byte ptr [rcx+29h], 3
0x140035471  jb      short loc_140035484
0x140035473  mov     rcx, [rcx+18h]
0x140035477  mov     edx, 25h ; '%'
0x14003547c  mov     r9d, ebx
0x14003547f  call    WPP_SF_D
0x140035484  cmp     ebx, 903A0h
0x14003548a  jz      short loc_1400354A7
0x14003548c  mov     ebx, 0C00000BBh
0x140035491  xor     edx, edx; PriorityBoost
0x140035493  mov     rcx, rdi; Irp
0x140035496  mov     [rdi+30h], ebx
0x140035499  call    cs:__imp_IofCompleteRequest
0x1400354a0  nop     dword ptr [rax+rax+00h]
0x1400354a5  jmp     short loc_1400354C7
0x1400354a7  lea     rcx, [rsi+8]; struct SP_DEVICE *
0x1400354ab  mov     rdx, rdi; struct _IRP *
0x1400354ae  call    ?SpSsdiStorageRequest@@YAJPEAVSP_DEVICE@@PEAU_IRP@@@Z; SpSsdiStorageRequest(SP_DEVICE *,_IRP *)
0x1400354b3  mov     ebx, eax
0x1400354b5  test    eax, eax
0x1400354b7  jns     short loc_1400354E6
0x1400354b9  cmp     eax, 80000005h
0x1400354be  jz      short loc_1400354E6
0x1400354c0  cmp     eax, 0C0000023h
0x1400354c5  jz      short loc_1400354E6
0x1400354c7  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400354cd  cmp     ecx, 1
0x1400354d0  jz      short loc_1400354DD
0x1400354d2  mov     ecx, 1
0x1400354d7  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400354dd  lea     r9, aError; "Error"
0x1400354e4  jmp     short loc_140035503
0x1400354e6  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400354ec  cmp     ecx, 3
0x1400354ef  jz      short loc_1400354FC
0x1400354f1  mov     ecx, 3
0x1400354f6  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400354fc  lea     r9, aExit; "Exit "
0x140035503  mov     r10, cs:WPP_GLOBAL_Control
0x14003550a  cmp     r10, r14
0x14003550d  jz      short loc_140035539
0x14003550f  mov     eax, [r10+2Ch]
0x140035513  test    al, 1
0x140035515  jz      short loc_140035539
0x140035517  movzx   eax, byte ptr [r10+29h]
0x14003551c  cmp     eax, ecx
0x14003551e  jb      short loc_140035539
0x140035520  mov     rcx, [r10+18h]
0x140035524  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x14003552b  mov     edx, 26h ; '&'
0x140035530  mov     [rsp+58h+var_38], ebx
0x140035534  call    WPP_SF_sd
0x140035539  mov     eax, ebx
0x14003553b  add     rsp, 38h
0x14003553f  pop     r14
0x140035541  pop     rdi
0x140035542  pop     rsi
0x140035543  pop     rbx
0x140035544  retn
```
