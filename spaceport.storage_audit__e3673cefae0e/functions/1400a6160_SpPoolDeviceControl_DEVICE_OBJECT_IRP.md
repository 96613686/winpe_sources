# SpPoolDeviceControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400a6160`
- end: `0x1400a627f`
- name: `?SpPoolDeviceControl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14002ce90`
- `0x140035cf4`
- `0x1400a6160`
- `0x1400a6288`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400a61e0`
- `ntoskrnl!IofCompleteRequest` at `0x1400a61e0`

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
0x1400a6160  push    rbx
0x1400a6162  push    rsi
0x1400a6163  push    rdi
0x1400a6164  push    r14
0x1400a6166  sub     rsp, 38h
0x1400a616a  mov     rax, [rdx+0B8h]
0x1400a6171  mov     rdi, rdx
0x1400a6174  mov     rsi, [rcx+40h]
0x1400a6178  mov     qword ptr [rdx+38h], 0
0x1400a6180  mov     ebx, [rax+18h]
0x1400a6183  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a618a  lea     r14, WPP_GLOBAL_Control
0x1400a6191  cmp     rcx, r14
0x1400a6194  jz      short loc_1400A61B4
0x1400a6196  mov     eax, [rcx+2Ch]
0x1400a6199  test    al, 1
0x1400a619b  jz      short loc_1400A61B4
0x1400a619d  cmp     byte ptr [rcx+29h], 3
0x1400a61a1  jb      short loc_1400A61B4
0x1400a61a3  mov     rcx, [rcx+18h]
0x1400a61a7  mov     edx, 1Eh
0x1400a61ac  mov     r9d, ebx
0x1400a61af  call    WPP_SF_D
0x1400a61b4  cmp     ebx, 0E7C204h
0x1400a61ba  jz      short loc_1400A61C3
0x1400a61bc  mov     ebx, 0C00000BBh
0x1400a61c1  jmp     short loc_1400A61D8
0x1400a61c3  lea     rcx, [rsi+8]; this
0x1400a61c7  mov     rdx, rdi; struct _IRP *
0x1400a61ca  call    ?SpPoolMapExtents@@YAJPEAVSP_POOL_DEVICE@@PEAU_IRP@@@Z; SpPoolMapExtents(SP_POOL_DEVICE *,_IRP *)
0x1400a61cf  mov     ebx, eax
0x1400a61d1  cmp     eax, 103h
0x1400a61d6  jz      short loc_1400A61EC
0x1400a61d8  xor     edx, edx; PriorityBoost
0x1400a61da  mov     [rdi+30h], ebx
0x1400a61dd  mov     rcx, rdi; Irp
0x1400a61e0  call    cs:__imp_IofCompleteRequest
0x1400a61e7  nop     dword ptr [rax+rax+00h]
0x1400a61ec  test    ebx, ebx
0x1400a61ee  jns     short loc_1400A621F
0x1400a61f0  cmp     ebx, 80000005h
0x1400a61f6  jz      short loc_1400A621F
0x1400a61f8  cmp     ebx, 0C0000023h
0x1400a61fe  jz      short loc_1400A621F
0x1400a6200  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a6206  cmp     ecx, 1
0x1400a6209  jz      short loc_1400A6216
0x1400a620b  mov     ecx, 1
0x1400a6210  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a6216  lea     r9, aError; "Error"
0x1400a621d  jmp     short loc_1400A623C
0x1400a621f  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1400a6225  cmp     ecx, 3
0x1400a6228  jz      short loc_1400A6235
0x1400a622a  mov     ecx, 3
0x1400a622f  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x1400a6235  lea     r9, aExit; "Exit "
0x1400a623c  mov     r10, cs:WPP_GLOBAL_Control
0x1400a6243  cmp     r10, r14
0x1400a6246  jz      short loc_1400A6272
0x1400a6248  mov     eax, [r10+2Ch]
0x1400a624c  test    al, 1
0x1400a624e  jz      short loc_1400A6272
0x1400a6250  movzx   eax, byte ptr [r10+29h]
0x1400a6255  cmp     eax, ecx
0x1400a6257  jb      short loc_1400A6272
0x1400a6259  mov     rcx, [r10+18h]
0x1400a625d  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x1400a6264  mov     edx, 1Fh
0x1400a6269  mov     [rsp+58h+var_38], ebx
0x1400a626d  call    WPP_SF_sd
0x1400a6272  mov     eax, ebx
0x1400a6274  add     rsp, 38h
0x1400a6278  pop     r14
0x1400a627a  pop     rdi
0x1400a627b  pop     rsi
0x1400a627c  pop     rbx
0x1400a627d  retn
```
