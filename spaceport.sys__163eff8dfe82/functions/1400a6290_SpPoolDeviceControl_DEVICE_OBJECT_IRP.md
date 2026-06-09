# SpPoolDeviceControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400a6290`
- end: `0x1400a63af`
- name: `?SpPoolDeviceControl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `287`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14002ce90`
- `0x140035db4`
- `0x1400a6290`
- `0x1400a63b8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400a6310`
- `ntoskrnl!IofCompleteRequest` at `0x1400a6310`

## pseudocode

```c
__int64 __fastcall SpPoolDeviceControl(struct _DEVICE_OBJECT *a1, struct _IRP *a2, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  char *DeviceExtension; // rsi
  DWORD LowPart; // ebx
  int v7; // ebx
  ULONG DeviceType; // ecx
  const char *v9; // r9

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  DeviceExtension = (char *)a1->DeviceExtension;
  a2->IoStatus.Information = 0;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 30, a3, LowPart);
  }
  if ( LowPart != 15188484 )
  {
    v7 = -1073741637;
LABEL_8:
    a2->IoStatus.Status = v7;
    IofCompleteRequest(a2, 0);
    goto LABEL_9;
  }
  v7 = SpPoolMapExtents((struct SP_POOL_DEVICE *)(DeviceExtension + 8), a2);
  if ( v7 != 259 )
    goto LABEL_8;
LABEL_9:
  if ( v7 >= 0 || v7 == -2147483643 || v7 == -1073741789 )
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 3 )
    {
      DeviceType = 3;
      WPP_MAIN_CB.DeviceType = 3;
    }
    v9 = "Exit ";
  }
  else
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v9 = "Error";
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      31,
      (unsigned int)WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids,
      (_DWORD)v9,
      v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400a6290  push    rbx
0x1400a6292  push    rsi
0x1400a6293  push    rdi
0x1400a6294  push    r14
0x1400a6296  sub     rsp, 38h
0x1400a629a  mov     rax, [rdx+0B8h]
0x1400a62a1  mov     rdi, rdx
0x1400a62a4  mov     rsi, [rcx+40h]
0x1400a62a8  mov     qword ptr [rdx+38h], 0
0x1400a62b0  mov     ebx, [rax+18h]
0x1400a62b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a62ba  lea     r14, WPP_GLOBAL_Control
0x1400a62c1  cmp     rcx, r14
0x1400a62c4  jz      short loc_1400A62E4
0x1400a62c6  mov     eax, [rcx+2Ch]
0x1400a62c9  test    al, 1
0x1400a62cb  jz      short loc_1400A62E4
0x1400a62cd  cmp     byte ptr [rcx+29h], 3
0x1400a62d1  jb      short loc_1400A62E4
0x1400a62d3  mov     rcx, [rcx+18h]
0x1400a62d7  mov     edx, 1Eh
0x1400a62dc  mov     r9d, ebx
0x1400a62df  call    WPP_SF_D
0x1400a62e4  cmp     ebx, 0E7C204h
0x1400a62ea  jz      short loc_1400A62F3
0x1400a62ec  mov     ebx, 0C00000BBh
0x1400a62f1  jmp     short loc_1400A6308
0x1400a62f3  lea     rcx, [rsi+8]; this
0x1400a62f7  mov     rdx, rdi; struct _IRP *
0x1400a62fa  call    ?SpPoolMapExtents@@YAJPEAVSP_POOL_DEVICE@@PEAU_IRP@@@Z; SpPoolMapExtents(SP_POOL_DEVICE *,_IRP *)
0x1400a62ff  mov     ebx, eax
0x1400a6301  cmp     eax, 103h
0x1400a6306  jz      short loc_1400A631C
0x1400a6308  xor     edx, edx; PriorityBoost
0x1400a630a  mov     [rdi+30h], ebx
0x1400a630d  mov     rcx, rdi; Irp
0x1400a6310  call    cs:__imp_IofCompleteRequest
0x1400a6317  nop     dword ptr [rax+rax+00h]
0x1400a631c  test    ebx, ebx
0x1400a631e  jns     short loc_1400A634F
0x1400a6320  cmp     ebx, 80000005h
0x1400a6326  jz      short loc_1400A634F
0x1400a6328  cmp     ebx, 0C0000023h
0x1400a632e  jz      short loc_1400A634F
0x1400a6330  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a6336  cmp     ecx, 1
0x1400a6339  jz      short loc_1400A6346
0x1400a633b  mov     ecx, 1
0x1400a6340  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a6346  lea     r9, aError; "Error"
0x1400a634d  jmp     short loc_1400A636C
0x1400a634f  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a6355  cmp     ecx, 3
0x1400a6358  jz      short loc_1400A6365
0x1400a635a  mov     ecx, 3
0x1400a635f  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a6365  lea     r9, aExit; "Exit "
0x1400a636c  mov     r10, cs:WPP_GLOBAL_Control
0x1400a6373  cmp     r10, r14
0x1400a6376  jz      short loc_1400A63A2
0x1400a6378  mov     eax, [r10+2Ch]
0x1400a637c  test    al, 1
0x1400a637e  jz      short loc_1400A63A2
0x1400a6380  movzx   eax, byte ptr [r10+29h]
0x1400a6385  cmp     eax, ecx
0x1400a6387  jb      short loc_1400A63A2
0x1400a6389  mov     rcx, [r10+18h]
0x1400a638d  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x1400a6394  mov     edx, 1Fh
0x1400a6399  mov     [rsp+58h+var_38], ebx
0x1400a639d  call    WPP_SF_sd
0x1400a63a2  mov     eax, ebx
0x1400a63a4  add     rsp, 38h
0x1400a63a8  pop     r14
0x1400a63aa  pop     rdi
0x1400a63ab  pop     rsi
0x1400a63ac  pop     rbx
0x1400a63ad  retn
```
