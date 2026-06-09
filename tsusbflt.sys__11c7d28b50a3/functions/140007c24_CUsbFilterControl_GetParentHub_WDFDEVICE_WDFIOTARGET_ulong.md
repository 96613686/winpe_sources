# CUsbFilterControl::GetParentHub(WDFDEVICE__ *,WDFIOTARGET__ * *,ulong *)

- ea: `0x140007c24`
- end: `0x140008183`
- name: `?GetParentHub@CUsbFilterControl@@QEAAJPEAUWDFDEVICE__@@PEAPEAUWDFIOTARGET__@@PEAK@Z`
- size: `1375`
- prototype: `__int64 __fastcall(CUsbFilterControl *__hidden this, struct WDFDEVICE__ *, struct WDFIOTARGET__ **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x1400031b0`

## callees

- `0x140004f18`
- `0x140004f48`
- `0x140007c24`
- `0x14000a9f0`
- `0x14000aa30`

## import_xrefs

- `ntoskrnl!IoGetDeviceProperty` at `0x140007ce1`
- `ntoskrnl!IoGetDeviceProperty` at `0x140007dc3`
- `ntoskrnl!IoGetDeviceProperty` at `0x140007ce1`
- `ntoskrnl!IoGetDeviceProperty` at `0x140007dc3`

## pseudocode

```c
__int64 __fastcall CUsbFilterControl::GetParentHub(
        CUsbFilterControl *this,
        struct WDFDEVICE__ *a2,
        struct WDFIOTARGET__ **a3,
        unsigned int *a4)
{
  struct _LIST_ENTRY *Blink; // rax
  struct _DEVICE_OBJECT *v7; // rdi
  NTSTATUS DeviceProperty; // ebx
  PDEVICE_OBJECT v9; // rcx
  unsigned __int16 v10; // dx
  struct WDFIOTARGET__ *v11; // r14
  unsigned int v12; // esi
  unsigned int v13; // r12d
  struct WDFIOTARGET__ *v14; // rdi
  __int64 v15; // rax
  unsigned __int16 *v16; // rcx
  __int64 v17; // r8
  int v18; // eax
  int v19; // edx
  unsigned int *v20; // rax
  ULONG BufferLength; // [rsp+50h] [rbp-39h] BYREF
  __int64 v23; // [rsp+58h] [rbp-31h] BYREF
  PVOID PropertyBuffer; // [rsp+60h] [rbp-29h]
  __int64 v25; // [rsp+68h] [rbp-21h]
  __int64 v26; // [rsp+70h] [rbp-19h] BYREF
  unsigned int *v27; // [rsp+78h] [rbp-11h] BYREF
  unsigned int *v28; // [rsp+80h] [rbp-9h]
  __int128 v29; // [rsp+88h] [rbp-1h] BYREF

  PropertyBuffer = 0;
  BufferLength = 0;
  v23 = 0;
  v25 = 0;
  v29 = 0;
  v27 = 0;
  v26 = 0;
  Blink = WPP_MAIN_CB.Queue.ListEntry.Flink[16].Blink;
  v28 = a4;
  v7 = (struct _DEVICE_OBJECT *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *))Blink)(
                                  WPP_MAIN_CB.Queue.ListEntry.Blink,
                                  a2);
  PropertyBuffer = 0;
  v23 = 0;
  v25 = 0;
  v26 = 0;
  DeviceProperty = IoGetDeviceProperty(v7, DevicePropertyPhysicalDeviceObjectName, 0, 0, &BufferLength);
  if ( DeviceProperty != -1073741789 )
  {
    if ( DeviceProperty >= 0 )
      DeviceProperty = -1073741595;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v10 = 13;
      goto LABEL_7;
    }
    goto LABEL_43;
  }
  DeviceProperty = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[96].Flink)(
                     WPP_MAIN_CB.Queue.ListEntry.Blink,
                     0,
                     1);
  if ( DeviceProperty < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v10 = 14;
      goto LABEL_7;
    }
    goto LABEL_43;
  }
  DeviceProperty = IoGetDeviceProperty(
                     v7,
                     DevicePropertyPhysicalDeviceObjectName,
                     BufferLength,
                     PropertyBuffer,
                     &BufferLength);
  if ( DeviceProperty < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v10 = 15;
      goto LABEL_7;
    }
    goto LABEL_43;
  }
  DeviceProperty = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, __int64, _QWORD, __int64, __int64 *, unsigned int **))WPP_MAIN_CB.Queue.ListEntry.Flink[96].Flink)(
                     WPP_MAIN_CB.Queue.ListEntry.Blink,
                     0,
                     1,
                     0,
                     4,
                     &v26,
                     &v27);
  if ( DeviceProperty < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v10 = 16;
      goto LABEL_7;
    }
    goto LABEL_43;
  }
  DeviceProperty = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, _QWORD, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[123].Blink)(
                     WPP_MAIN_CB.Queue.ListEntry.Blink,
                     0,
                     0,
                     &v23);
  if ( DeviceProperty < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v10 = 17;
      goto LABEL_7;
    }
    goto LABEL_43;
  }
  v11 = 0;
  ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    *(_QWORD *)this);
  v12 = 0;
  v13 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[7].Flink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          *((_QWORD *)this + 1));
  if ( !v13 )
  {
LABEL_33:
    ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[155].Blink)(
      WPP_MAIN_CB.Queue.ListEntry.Blink,
      *(_QWORD *)this);
    if ( v11 )
    {
      DeviceProperty = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x13u,
          (__int64)WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids);
      DeviceProperty = -1073741275;
    }
    goto LABEL_43;
  }
  while ( 1 )
  {
    v14 = (struct WDFIOTARGET__ *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[9].Flink)(
                                    WPP_MAIN_CB.Queue.ListEntry.Blink,
                                    *((_QWORD *)this + 1),
                                    v12);
    v15 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFIOTARGET__ *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
            WPP_MAIN_CB.Queue.ListEntry.Blink,
            v14,
            off_14000F040);
    v16 = (unsigned __int16 *)PropertyBuffer;
    v17 = *(_QWORD *)(v15 + 8) - (_QWORD)PropertyBuffer;
    do
    {
      v18 = *(unsigned __int16 *)((char *)v16 + v17);
      v19 = *v16 - v18;
      if ( v19 )
        break;
      ++v16;
    }
    while ( v18 );
    if ( !v19 )
      goto LABEL_32;
    DeviceProperty = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFIOTARGET__ *, __int64, __int64, __int64, _QWORD, __int64, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[94].Blink)(
                       WPP_MAIN_CB.Queue.ListEntry.Blink,
                       v14,
                       v23,
                       2245652,
                       v25,
                       0,
                       v26,
                       0);
    if ( DeviceProperty < 0 )
      break;
    v29 = 0x200000010uLL;
    if ( ((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *, __int64, struct WDFIOTARGET__ *, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Blink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           v23,
           v14,
           &v29)
      && ((int (__fastcall *)(struct _LIST_ENTRY *, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[127].Flink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           v23) >= 0 )
    {
      v11 = v14;
      ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFIOTARGET__ *, _QWORD, __int64, const char *))WPP_MAIN_CB.Queue.ListEntry.Flink[102].Blink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        v14,
        0,
        419,
        "clientcore\\termsrv\\devices\\urbdr\\busfilter\\control.cpp");
      v20 = v27;
      *a3 = v14;
      *v28 = *v20;
      goto LABEL_33;
    }
LABEL_32:
    if ( ++v12 >= v13 )
      goto LABEL_33;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v10 = 18;
LABEL_7:
    WPP_SF_d((__int64)v9->AttachedDevice, v10, (__int64)WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids, DeviceProperty);
  }
LABEL_43:
  if ( v23 )
    ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
  if ( v25 )
    ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
  if ( v26 )
    ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
  return (unsigned int)DeviceProperty;
}

```

## disassembly

```asm
0x140007c24  push    rbp
0x140007c26  push    rbx
0x140007c27  push    rsi
0x140007c28  push    rdi
0x140007c29  push    r12
0x140007c2b  push    r13
0x140007c2d  push    r14
0x140007c2f  push    r15
0x140007c31  lea     rbp, [rsp-1Fh]
0x140007c36  sub     rsp, 0A8h
0x140007c3d  mov     rax, cs:__security_cookie
0x140007c44  xor     rax, rsp
0x140007c47  mov     [rbp+57h+var_48], rax
0x140007c4b  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140007c52  xorps   xmm0, xmm0
0x140007c55  mov     r15, rcx
0x140007c58  mov     [rbp+57h+PropertyBuffer], 0
0x140007c60  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140007c67  mov     r13, r8
0x140007c6a  mov     [rbp+57h+BufferLength], 0
0x140007c71  mov     [rbp+57h+var_88], 0
0x140007c79  mov     [rbp+57h+var_78], 0
0x140007c81  movups  [rbp+57h+var_58], xmm0
0x140007c85  mov     [rbp+57h+var_68], 0
0x140007c8d  mov     [rbp+57h+var_70], 0
0x140007c95  mov     rax, [rax+108h]
0x140007c9c  mov     [rbp+57h+var_60], r9
0x140007ca0  call    _guard_dispatch_icall
0x140007ca5  mov     rdi, rax
0x140007ca8  mov     [rbp+57h+PropertyBuffer], 0
0x140007cb0  xor     r9d, r9d; PropertyBuffer
0x140007cb3  mov     [rbp+57h+var_88], 0
0x140007cbb  lea     rax, [rbp+57h+BufferLength]
0x140007cbf  mov     [rbp+57h+var_78], 0
0x140007cc7  xor     r8d, r8d; BufferLength
0x140007cca  mov     [rbp+57h+var_70], 0
0x140007cd2  mov     rcx, rdi; DeviceObject
0x140007cd5  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x140007cda  lea     r14d, [r9+0Bh]
0x140007cde  mov     edx, r14d; DeviceProperty
0x140007ce1  call    cs:__imp_IoGetDeviceProperty
0x140007ce8  nop     dword ptr [rax+rax+00h]
0x140007ced  mov     ebx, eax
0x140007cef  cmp     eax, 0C0000023h
0x140007cf4  jz      short loc_140007D3D
0x140007cf6  test    ebx, ebx
0x140007cf8  mov     eax, 0C00000E5h
0x140007cfd  cmovns  ebx, eax
0x140007d00  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d07  lea     rax, WPP_GLOBAL_Control
0x140007d0e  cmp     rcx, rax
0x140007d11  jz      loc_1400080F7
0x140007d17  cmp     byte ptr [rcx+29h], 2
0x140007d1b  jb      loc_1400080F7
0x140007d21  lea     edx, [r14+2]
0x140007d25  mov     rcx, [rcx+18h]
0x140007d29  lea     r8, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x140007d30  mov     r9d, ebx
0x140007d33  call    WPP_SF_d
0x140007d38  jmp     loc_1400080F7
0x140007d3d  mov     ecx, [rbp+57h+BufferLength]
0x140007d40  lea     rdx, [rbp+57h+PropertyBuffer]
0x140007d44  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140007d4b  xor     r9d, r9d
0x140007d4e  mov     [rsp+0E0h+var_B0], rdx
0x140007d53  lea     rdx, [rbp+57h+var_78]
0x140007d57  mov     [rsp+0E0h+var_B8], rdx
0x140007d5c  xor     edx, edx
0x140007d5e  mov     [rsp+0E0h+ResultLength], rcx
0x140007d63  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140007d6a  lea     esi, [r9+1]
0x140007d6e  mov     rax, [rax+600h]
0x140007d75  mov     r8d, esi
0x140007d78  call    _guard_dispatch_icall
0x140007d7d  mov     ebx, eax
0x140007d7f  test    eax, eax
0x140007d81  jns     short loc_140007DAC
0x140007d83  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d8a  lea     rax, WPP_GLOBAL_Control
0x140007d91  cmp     rcx, rax
0x140007d94  jz      loc_1400080F7
0x140007d9a  cmp     byte ptr [rcx+29h], 2
0x140007d9e  jb      loc_1400080F7
0x140007da4  lea     edx, [rsi+0Dh]
0x140007da7  jmp     loc_140007D25
0x140007dac  mov     r9, [rbp+57h+PropertyBuffer]; PropertyBuffer
0x140007db0  lea     rax, [rbp+57h+BufferLength]
0x140007db4  mov     r8d, [rbp+57h+BufferLength]; BufferLength
0x140007db8  mov     edx, r14d; DeviceProperty
0x140007dbb  mov     rcx, rdi; DeviceObject
0x140007dbe  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x140007dc3  call    cs:__imp_IoGetDeviceProperty
0x140007dca  nop     dword ptr [rax+rax+00h]
0x140007dcf  mov     ebx, eax
0x140007dd1  test    eax, eax
0x140007dd3  jns     short loc_140007E00
0x140007dd5  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ddc  lea     rax, WPP_GLOBAL_Control
0x140007de3  cmp     rcx, rax
0x140007de6  jz      loc_1400080F7
0x140007dec  cmp     byte ptr [rcx+29h], 2
0x140007df0  jb      loc_1400080F7
0x140007df6  mov     edx, 0Fh
0x140007dfb  jmp     loc_140007D25
0x140007e00  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140007e07  lea     rcx, [rbp+57h+var_68]
0x140007e0b  mov     [rsp+0E0h+var_B0], rcx
0x140007e10  xor     r9d, r9d
0x140007e13  lea     rcx, [rbp+57h+var_70]
0x140007e17  mov     r8d, esi
0x140007e1a  mov     [rsp+0E0h+var_B8], rcx
0x140007e1f  xor     edx, edx
0x140007e21  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140007e28  mov     rax, [rax+600h]
0x140007e2f  mov     [rsp+0E0h+ResultLength], 4
0x140007e38  call    _guard_dispatch_icall
0x140007e3d  mov     ebx, eax
0x140007e3f  test    eax, eax
0x140007e41  jns     short loc_140007E6E
0x140007e43  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e4a  lea     rax, WPP_GLOBAL_Control
0x140007e51  cmp     rcx, rax
0x140007e54  jz      loc_1400080F7
0x140007e5a  cmp     byte ptr [rcx+29h], 2
0x140007e5e  jb      loc_1400080F7
0x140007e64  mov     edx, 10h
0x140007e69  jmp     loc_140007D25
0x140007e6e  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140007e75  lea     r9, [rbp+57h+var_88]
0x140007e79  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140007e80  xor     r8d, r8d
0x140007e83  xor     edx, edx
0x140007e85  mov     rax, [rax+7B8h]
0x140007e8c  call    _guard_dispatch_icall
0x140007e91  mov     ebx, eax
0x140007e93  test    eax, eax
0x140007e95  jns     short loc_140007EC2
0x140007e97  mov     rcx, cs:WPP_GLOBAL_Control
0x140007e9e  lea     rax, WPP_GLOBAL_Control
0x140007ea5  cmp     rcx, rax
0x140007ea8  jz      loc_1400080F7
0x140007eae  cmp     byte ptr [rcx+29h], 2
0x140007eb2  jb      loc_1400080F7
0x140007eb8  mov     edx, 11h
0x140007ebd  jmp     loc_140007D25
0x140007ec2  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140007ec9  xor     r14d, r14d
0x140007ecc  mov     rdx, [r15]
0x140007ecf  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140007ed6  mov     rax, [rax+9B0h]
0x140007edd  call    _guard_dispatch_icall
0x140007ee2  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140007ee9  mov     rdx, [r15+8]
0x140007eed  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140007ef4  mov     rax, [rax+70h]
0x140007ef8  call    _guard_dispatch_icall
0x140007efd  xor     esi, esi
0x140007eff  mov     r12d, eax
0x140007f02  test    eax, eax
0x140007f04  jz      loc_14000802E
0x140007f0a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140007f11  mov     r8d, esi
0x140007f14  mov     rdx, [r15+8]
0x140007f18  mov     rax, [rcx+90h]
0x140007f1f  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140007f26  call    _guard_dispatch_icall
0x140007f2b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue
0x140007f32  mov     rdi, rax
0x140007f35  mov     r8, cs:off_14000F040
0x140007f3c  mov     rdx, rdi
0x140007f3f  mov     rax, [rcx+650h]
0x140007f46  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140007f4d  call    _guard_dispatch_icall
0x140007f52  mov     rcx, [rbp+57h+PropertyBuffer]
0x140007f56  mov     r8, [rax+8]
0x140007f5a  sub     r8, rcx
0x140007f5d  movzx   edx, word ptr [rcx]
0x140007f60  movzx   eax, word ptr [rcx+r8]
0x140007f65  sub     edx, eax
0x140007f67  jnz     short loc_140007F71
0x140007f69  add     rcx, 2
0x140007f6d  test    eax, eax
0x140007f6f  jnz     short loc_140007F5D
0x140007f71  test    edx, edx
0x140007f73  jz      loc_140008023
0x140007f79  mov     rcx, [rbp+57h+var_70]
0x140007f7d  mov     r9d, 224414h
0x140007f83  mov     rdx, [rbp+57h+var_78]
0x140007f87  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140007f8e  mov     r8, [rbp+57h+var_88]
0x140007f92  mov     [rsp+0E0h+var_A8], r14
0x140007f97  mov     [rsp+0E0h+var_B0], rcx
0x140007f9c  mov     rax, [rax+5E8h]
0x140007fa3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140007faa  mov     [rsp+0E0h+var_B8], r14
0x140007faf  mov     [rsp+0E0h+ResultLength], rdx
0x140007fb4  mov     rdx, rdi
0x140007fb7  call    _guard_dispatch_icall
0x140007fbc  mov     ebx, eax
0x140007fbe  test    eax, eax
0x140007fc0  js      loc_1400080D2
0x140007fc6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140007fcd  lea     r9, [rbp+57h+var_58]
0x140007fd1  mov     rdx, [rbp+57h+var_88]
0x140007fd5  mov     r8, rdi
0x140007fd8  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140007fdf  mov     qword ptr [rbp+57h+var_58+8], r14
0x140007fe3  mov     dword ptr [rbp+57h+var_58], 10h
0x140007fea  mov     dword ptr [rbp+57h+var_58+4], 2
0x140007ff1  mov     rax, [rax+7E8h]
0x140007ff8  call    _guard_dispatch_icall
0x140007ffd  test    al, al
0x140007fff  jz      short loc_140008023
0x140008001  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140008008  mov     rdx, [rbp+57h+var_88]
0x14000800c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140008013  mov     rax, [rax+7F0h]
0x14000801a  call    _guard_dispatch_icall
0x14000801f  test    eax, eax
0x140008021  jns     short loc_140008088
0x140008023  inc     esi
0x140008025  cmp     esi, r12d
0x140008028  jb      loc_140007F0A
0x14000802e  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140008035  mov     rdx, [r15]
0x140008038  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000803f  mov     rax, [rax+9B8h]
0x140008046  call    _guard_dispatch_icall
0x14000804b  test    r14, r14
0x14000804e  jnz     loc_1400080F5
0x140008054  mov     rcx, cs:WPP_GLOBAL_Control
0x14000805b  lea     rax, WPP_GLOBAL_Control
0x140008062  cmp     rcx, rax
0x140008065  jz      short loc_140008081
0x140008067  cmp     byte ptr [rcx+29h], 2
0x14000806b  jb      short loc_140008081
0x14000806d  mov     rcx, [rcx+18h]
0x140008071  lea     edx, [r14+13h]
0x140008075  lea     r8, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x14000807c  call    WPP_SF_
0x140008081  mov     ebx, 0C0000225h
0x140008086  jmp     short loc_1400080F7
0x140008088  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000808f  lea     rcx, aClientcoreTerm_0; "clientcore\\termsrv\\devices\\urbdr\\bu"...
0x140008096  mov     [rsp+0E0h+ResultLength], rcx
0x14000809b  mov     r9d, 1A3h
0x1400080a1  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400080a8  xor     r8d, r8d
0x1400080ab  mov     rdx, rdi
0x1400080ae  mov     r14, rdi
0x1400080b1  mov     rax, [rax+668h]
0x1400080b8  call    _guard_dispatch_icall
0x1400080bd  mov     rax, [rbp+57h+var_68]
0x1400080c1  mov     [r13+0], rdi
0x1400080c5  mov     ecx, [rax]
0x1400080c7  mov     rax, [rbp+57h+var_60]
0x1400080cb  mov     [rax], ecx
0x1400080cd  jmp     loc_14000802E
0x1400080d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400080d9  lea     rax, WPP_GLOBAL_Control
0x1400080e0  cmp     rcx, rax
0x1400080e3  jz      short loc_1400080F7
0x1400080e5  cmp     byte ptr [rcx+29h], 2
0x1400080e9  jb      short loc_1400080F7
0x1400080eb  mov     edx, 12h
0x1400080f0  jmp     loc_140007D25
0x1400080f5  xor     ebx, ebx
0x1400080f7  mov     rdx, [rbp+57h+var_88]
0x1400080fb  test    rdx, rdx
0x1400080fe  jz      short loc_14000811A
0x140008100  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140008107  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000810e  mov     rax, [rax+680h]
0x140008115  call    _guard_dispatch_icall
0x14000811a  mov     rdx, [rbp+57h+var_78]
0x14000811e  test    rdx, rdx
0x140008121  jz      short loc_14000813D
0x140008123  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000812a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140008131  mov     rax, [rax+680h]
0x140008138  call    _guard_dispatch_icall
0x14000813d  mov     rdx, [rbp+57h+var_70]
0x140008141  test    rdx, rdx
0x140008144  jz      short loc_140008160
0x140008146  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000814d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140008154  mov     rax, [rax+680h]
0x14000815b  call    _guard_dispatch_icall
0x140008160  mov     eax, ebx
0x140008162  mov     rcx, [rbp+57h+var_48]
0x140008166  xor     rcx, rsp; StackCookie
0x140008169  call    __security_check_cookie
0x14000816e  add     rsp, 0A8h
0x140008175  pop     r15
0x140008177  pop     r14
0x140008179  pop     r13
0x14000817b  pop     r12
0x14000817d  pop     rdi
0x14000817e  pop     rsi
0x14000817f  pop     rbx
  ... truncated ...
```
