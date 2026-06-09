# PtAddDevice

- ea: `0x140009010`
- end: `0x1400092df`
- name: `PtAddDevice`
- size: `719`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callees

- `0x14000173c`
- `0x1400017e8`
- `0x140003500`
- `0x140009010`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140009289`
- `ntoskrnl!IoDeleteDevice` at `0x140009289`
- `ntoskrnl!IoDetachDevice` at `0x140009274`
- `ntoskrnl!IoDetachDevice` at `0x140009274`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x140009218`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x140009218`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1400091b5`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1400091b5`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000913b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000913b`
- `ntoskrnl!IoCreateDevice` at `0x1400090f8`
- `ntoskrnl!IoCreateDevice` at `0x1400090f8`
- `ntoskrnl!IoGetDeviceProperty` at `0x140009054`
- `ntoskrnl!IoGetDeviceProperty` at `0x140009166`
- `ntoskrnl!IoGetDeviceProperty` at `0x140009054`
- `ntoskrnl!IoGetDeviceProperty` at `0x140009166`

## pseudocode

```c
__int64 __fastcall PtAddDevice(PDRIVER_OBJECT DriverObject, PDEVICE_OBJECT TargetDevice)
{
  NTSTATUS DeviceProperty; // eax
  int v5; // edx
  int v6; // r8d
  NTSTATUS v7; // ebx
  int v8; // r9d
  ULONG v9; // esi
  _QWORD *DeviceExtension; // rdi
  PDEVICE_OBJECT v11; // rax
  ULONG BufferLength; // [rsp+80h] [rbp+40h] BYREF
  PDEVICE_OBJECT SourceDevice; // [rsp+88h] [rbp+48h] BYREF

  SourceDevice = 0;
  BufferLength = 0;
  DeviceProperty = IoGetDeviceProperty(TargetDevice, DevicePropertyPhysicalDeviceObjectName, 0, 0, &BufferLength);
  v7 = 0;
  if ( DeviceProperty != -1073741789 )
    v7 = DeviceProperty;
  if ( v7 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_26;
    v8 = 10;
    goto LABEL_9;
  }
  v9 = BufferLength + 240;
  if ( BufferLength >= 0xFFFFFF10 )
  {
    v7 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_26;
    v8 = 11;
    goto LABEL_9;
  }
  v7 = IoCreateDevice(DriverObject, v9, 0, 0x27u, 0x100u, 0, &SourceDevice);
  if ( v7 >= 0 )
  {
    DeviceExtension = SourceDevice->DeviceExtension;
    memset(DeviceExtension, 0, v9);
    KeInitializeSpinLock(DeviceExtension + 29);
    v7 = IoGetDeviceProperty(
           TargetDevice,
           DevicePropertyPhysicalDeviceObjectName,
           BufferLength,
           DeviceExtension + 30,
           &BufferLength);
    if ( v7 >= 0 )
    {
      if ( BufferLength <= 0xFFFF )
      {
        DeviceExtension[22] = DeviceExtension + 30;
        *((_WORD *)DeviceExtension + 84) = BufferLength - 2;
        *((_WORD *)DeviceExtension + 85) = BufferLength - 2;
        v11 = IoAttachDeviceToDeviceStack(SourceDevice, TargetDevice);
        DeviceExtension[1] = v11;
        if ( v11 )
        {
          *DeviceExtension = SourceDevice;
          DeviceExtension[2] = TargetDevice;
          IoInitializeRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 3), 0x69547354u, 0, 0x14u, 0x20u);
          SourceDevice->Flags |= 4u;
          SourceDevice->Flags &= ~0x80u;
          goto LABEL_28;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_s(
            WPP_GLOBAL_Control->DeviceExtension,
            v5,
            v6,
            14,
            (__int64)WPP_75fd79d40e58354b8c24f648881272a9_Traceguids);
        v7 = -1073741810;
        goto LABEL_23;
      }
      v7 = -1073741436;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_s(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        v6,
        13,
        (__int64)WPP_75fd79d40e58354b8c24f648881272a9_Traceguids);
LABEL_23:
    if ( DeviceExtension && DeviceExtension[1] )
      IoDetachDevice(SourceDevice);
    goto LABEL_26;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v8 = 12;
LABEL_9:
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      v6,
      v8,
      (__int64)WPP_75fd79d40e58354b8c24f648881272a9_Traceguids);
  }
LABEL_26:
  if ( SourceDevice )
  {
    IoDeleteDevice(SourceDevice);
    SourceDevice = 0;
  }
LABEL_28:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      v6,
      15,
      (__int64)WPP_75fd79d40e58354b8c24f648881272a9_Traceguids);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140009010  mov     [rsp-28h+arg_0], rbx
0x140009015  mov     [rsp-28h+arg_8], rsi
0x14000901a  push    rbp
0x14000901b  push    rdi
0x14000901c  push    r12
0x14000901e  push    r13
0x140009020  push    r14
0x140009022  mov     rbp, rsp
0x140009025  sub     rsp, 40h
0x140009029  mov     r14, rdx
0x14000902c  mov     [rbp+SourceDevice], 0
0x140009034  xor     r9d, r9d; PropertyBuffer
0x140009037  mov     [rbp+BufferLength], 0
0x14000903e  mov     rdi, rcx
0x140009041  lea     rax, [rbp+BufferLength]
0x140009045  xor     r8d, r8d; BufferLength
0x140009048  mov     [rsp+40h+ResultLength], rax; ResultLength
0x14000904d  mov     rcx, r14; DeviceObject
0x140009050  lea     edx, [r9+0Bh]; DeviceProperty
0x140009054  call    cs:__imp_IoGetDeviceProperty
0x14000905b  nop     dword ptr [rax+rax+00h]
0x140009060  xor     ebx, ebx
0x140009062  lea     r12, WPP_RECORDER_INITIALIZED
0x140009069  cmp     eax, 0C0000023h
0x14000906e  lea     r13, WPP_75fd79d40e58354b8c24f648881272a9_Traceguids
0x140009075  cmovnz  ebx, eax
0x140009078  test    ebx, ebx
0x14000907a  jns     short loc_140009091
0x14000907c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140009083  jz      loc_140009280
0x140009089  mov     r9d, 0Ah
0x14000908f  jmp     short loc_1400090BA
0x140009091  mov     esi, [rbp+BufferLength]
0x140009094  add     esi, 0F0h
0x14000909a  cmp     esi, 0F0h
0x1400090a0  jnb     short loc_1400090D4
0x1400090a2  mov     ebx, 0C000000Dh
0x1400090a7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400090ae  jz      loc_140009280
0x1400090b4  mov     r9d, 0Bh
0x1400090ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400090c1  mov     [rsp+40h+ResultLength], r13
0x1400090c6  mov     rcx, [rcx+40h]
0x1400090ca  call    WPP_RECORDER_SF_s
0x1400090cf  jmp     loc_140009280
0x1400090d4  lea     rax, [rbp+SourceDevice]
0x1400090d8  mov     r9d, 27h ; '''; DeviceType
0x1400090de  mov     [rsp+40h+DeviceObject], rax; DeviceObject
0x1400090e3  xor     r8d, r8d; DeviceName
0x1400090e6  mov     [rsp+40h+Exclusive], 0; Exclusive
0x1400090eb  mov     edx, esi; DeviceExtensionSize
0x1400090ed  mov     rcx, rdi; DriverObject
0x1400090f0  mov     dword ptr [rsp+40h+ResultLength], 100h; DeviceCharacteristics
0x1400090f8  call    cs:__imp_IoCreateDevice
0x1400090ff  nop     dword ptr [rax+rax+00h]
0x140009104  mov     ebx, eax
0x140009106  test    eax, eax
0x140009108  jns     short loc_14000911F
0x14000910a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140009111  jz      loc_140009280
0x140009117  mov     r9d, 0Ch
0x14000911d  jmp     short loc_1400090BA
0x14000911f  mov     rax, [rbp+SourceDevice]
0x140009123  xor     edx, edx; Val
0x140009125  mov     r8d, esi; Size
0x140009128  mov     rdi, [rax+40h]
0x14000912c  mov     rcx, rdi; void *
0x14000912f  call    memset
0x140009134  lea     rcx, [rdi+0E8h]; SpinLock
0x14000913b  call    cs:__imp_KeInitializeSpinLock
0x140009142  nop     dword ptr [rax+rax+00h]
0x140009147  mov     r8d, [rbp+BufferLength]; BufferLength
0x14000914b  lea     rax, [rbp+BufferLength]
0x14000914f  lea     rsi, [rdi+0F0h]
0x140009156  mov     [rsp+40h+ResultLength], rax; ResultLength
0x14000915b  mov     r9, rsi; PropertyBuffer
0x14000915e  mov     edx, 0Bh; DeviceProperty
0x140009163  mov     rcx, r14; DeviceObject
0x140009166  call    cs:__imp_IoGetDeviceProperty
0x14000916d  nop     dword ptr [rax+rax+00h]
0x140009172  mov     ebx, eax
0x140009174  test    eax, eax
0x140009176  js      loc_14000923C
0x14000917c  cmp     [rbp+BufferLength], 0FFFFh
0x140009183  ja      loc_140009237
0x140009189  mov     [rdi+0B0h], rsi
0x140009190  mov     rdx, r14; TargetDevice
0x140009193  movzx   eax, word ptr [rbp+BufferLength]
0x140009197  sub     ax, 2
0x14000919b  mov     [rdi+0A8h], ax
0x1400091a2  movzx   eax, word ptr [rbp+BufferLength]
0x1400091a6  sub     ax, 2
0x1400091aa  mov     [rdi+0AAh], ax
0x1400091b1  mov     rcx, [rbp+SourceDevice]; SourceDevice
0x1400091b5  call    cs:__imp_IoAttachDeviceToDeviceStack
0x1400091bc  nop     dword ptr [rax+rax+00h]
0x1400091c1  mov     [rdi+8], rax
0x1400091c5  test    rax, rax
0x1400091c8  jnz     short loc_1400091F3
0x1400091ca  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400091d1  jz      short loc_1400091EC
0x1400091d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400091da  lea     r9d, [rax+0Eh]
0x1400091de  mov     [rsp+40h+ResultLength], r13
0x1400091e3  mov     rcx, [rcx+40h]
0x1400091e7  call    WPP_RECORDER_SF_s
0x1400091ec  mov     ebx, 0C000000Eh
0x1400091f1  jmp     short loc_140009264
0x1400091f3  mov     rax, [rbp+SourceDevice]
0x1400091f7  lea     rcx, [rdi+18h]; Lock
0x1400091fb  mov     r9d, 14h; HighWatermark
0x140009201  mov     [rdi], rax
0x140009204  xor     r8d, r8d; MaxLockedMinutes
0x140009207  mov     [rdi+10h], r14
0x14000920b  mov     edx, 69547354h; AllocateTag
0x140009210  mov     dword ptr [rsp+40h+ResultLength], 20h ; ' '; RemlockSize
0x140009218  call    cs:__imp_IoInitializeRemoveLockEx
0x14000921f  nop     dword ptr [rax+rax+00h]
0x140009224  mov     rax, [rbp+SourceDevice]
0x140009228  or      dword ptr [rax+30h], 4
0x14000922c  mov     rax, [rbp+SourceDevice]
0x140009230  btr     dword ptr [rax+30h], 7
0x140009235  jmp     short loc_14000929D
0x140009237  mov     ebx, 0C0000184h
0x14000923c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140009243  jz      short loc_140009264
0x140009245  mov     rcx, cs:WPP_GLOBAL_Control
0x14000924c  mov     r9d, 0Dh
0x140009252  mov     [rsp+40h+ResultLength], r13
0x140009257  mov     rcx, [rcx+40h]
0x14000925b  call    WPP_RECORDER_SF_s
0x140009260  test    ebx, ebx
0x140009262  jns     short loc_14000929D
0x140009264  test    rdi, rdi
0x140009267  jz      short loc_140009280
0x140009269  cmp     qword ptr [rdi+8], 0
0x14000926e  jz      short loc_140009280
0x140009270  mov     rcx, [rbp+SourceDevice]; TargetDevice
0x140009274  call    cs:__imp_IoDetachDevice
0x14000927b  nop     dword ptr [rax+rax+00h]
0x140009280  mov     rcx, [rbp+SourceDevice]; DeviceObject
0x140009284  test    rcx, rcx
0x140009287  jz      short loc_14000929D
0x140009289  call    cs:__imp_IoDeleteDevice
0x140009290  nop     dword ptr [rax+rax+00h]
0x140009295  mov     [rbp+SourceDevice], 0
0x14000929d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400092a4  jz      short loc_1400092C5
0x1400092a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400092ad  mov     r9d, 0Fh
0x1400092b3  mov     dword ptr [rsp+40h+DeviceObject], ebx
0x1400092b7  mov     [rsp+40h+ResultLength], r13
0x1400092bc  mov     rcx, [rcx+40h]
0x1400092c0  call    WPP_RECORDER_SF_sD
0x1400092c5  mov     rsi, [rsp+40h+arg_8]
0x1400092ca  mov     eax, ebx
0x1400092cc  mov     rbx, [rsp+40h+arg_0]
0x1400092d1  add     rsp, 40h
0x1400092d5  pop     r14
0x1400092d7  pop     r13
0x1400092d9  pop     r12
0x1400092db  pop     rdi
0x1400092dc  pop     rbp
0x1400092dd  retn
```
