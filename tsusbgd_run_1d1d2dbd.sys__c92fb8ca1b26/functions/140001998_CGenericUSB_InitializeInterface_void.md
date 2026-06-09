# CGenericUSB::InitializeInterface(void)

- ea: `0x140001998`
- end: `0x140001aba`
- name: `?InitializeInterface@CGenericUSB@@AEAAJXZ`
- size: `290`
- prototype: `__int64 __fastcall(CGenericUSB *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001464`

## callees

- `0x140001998`
- `0x140001ac0`
- `0x140006370`

## pseudocode

```c
__int64 __fastcall CGenericUSB::InitializeInterface(CGenericUSB *this)
{
  char *v1; // rsi
  int v3; // ebx
  __int16 v5; // [rsp+20h] [rbp-48h]
  int v6; // [rsp+20h] [rbp-48h]
  int v7; // [rsp+20h] [rbp-48h]
  __int16 v8; // [rsp+28h] [rbp-40h]
  int v9; // [rsp+28h] [rbp-40h]
  int v10; // [rsp+28h] [rbp-40h]

  v1 = (char *)this + 88;
  v8 = 2;
  v5 = 80;
  v3 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, const GUID *, char *, __int16, __int16, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[88].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         *((_QWORD *)this + 4),
         &USB_BUS_INTERFACE_USBDI_GUID,
         (char *)this + 88,
         v5,
         v8,
         0);
  if ( v3 < 0 )
  {
    LOWORD(v9) = 1;
    LOWORD(v6) = 72;
    v3 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, const GUID *, char *, int, int, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[88].Blink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           *((_QWORD *)this + 4),
           &USB_BUS_INTERFACE_USBDI_GUID,
           v1,
           v6,
           v9,
           0);
    if ( v3 < 0 )
    {
      LOWORD(v10) = 0;
      LOWORD(v7) = 64;
      v3 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _QWORD, const GUID *, char *, int, int, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[88].Blink)(
             WPP_MAIN_CB.Queue.ListEntry.Blink,
             *((_QWORD *)this + 4),
             &USB_BUS_INTERFACE_USBDI_GUID,
             v1,
             v7,
             v10,
             0);
      if ( v3 < 0 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x15u,
          (__int64)&WPP_e22684400aa030ec2c531d4dcef4cab4_Traceguids,
          v3);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140001998  push    rbx
0x14000199a  push    rsi
0x14000199b  push    rdi
0x14000199c  push    r14
0x14000199e  sub     rsp, 48h
0x1400019a2  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400019a9  lea     rsi, [rcx+58h]
0x1400019ad  mov     rdx, [rcx+20h]
0x1400019b1  lea     r8, USB_BUS_INTERFACE_USBDI_GUID
0x1400019b8  mov     rdi, rcx
0x1400019bb  mov     [rsp+68h+var_38], 0
0x1400019c4  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400019cb  mov     r14d, 2
0x1400019d1  mov     rax, [rax+588h]
0x1400019d8  mov     r9, rsi
0x1400019db  mov     [rsp+68h+var_40], r14w
0x1400019e1  mov     [rsp+68h+var_48], 50h ; 'P'
0x1400019e8  call    _guard_dispatch_icall
0x1400019ed  mov     ebx, eax
0x1400019ef  test    eax, eax
0x1400019f1  jns     loc_140001AAD
0x1400019f7  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400019fe  lea     r8, USB_BUS_INTERFACE_USBDI_GUID
0x140001a05  mov     rdx, [rdi+20h]
0x140001a09  mov     r9, rsi
0x140001a0c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001a13  mov     [rsp+68h+var_38], 0
0x140001a1c  mov     rax, [rax+588h]
0x140001a23  mov     [rsp+68h+var_40], 1
0x140001a2a  mov     [rsp+68h+var_48], 48h ; 'H'
0x140001a31  call    _guard_dispatch_icall
0x140001a36  mov     ebx, eax
0x140001a38  test    eax, eax
0x140001a3a  jns     short loc_140001AAD
0x140001a3c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140001a43  lea     r8, USB_BUS_INTERFACE_USBDI_GUID
0x140001a4a  mov     rdx, [rdi+20h]
0x140001a4e  xor     ecx, ecx
0x140001a50  mov     [rsp+68h+var_38], rcx
0x140001a55  mov     r9, rsi
0x140001a58  mov     [rsp+68h+var_40], cx
0x140001a5d  mov     rax, [rax+588h]
0x140001a64  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001a6b  mov     [rsp+68h+var_48], 40h ; '@'
0x140001a72  call    _guard_dispatch_icall
0x140001a77  mov     ebx, eax
0x140001a79  test    eax, eax
0x140001a7b  jns     short loc_140001AAD
0x140001a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140001a84  lea     rax, WPP_GLOBAL_Control
0x140001a8b  cmp     rcx, rax
0x140001a8e  jz      short loc_140001AAD
0x140001a90  cmp     [rcx+29h], r14b
0x140001a94  jb      short loc_140001AAD
0x140001a96  mov     rcx, [rcx+18h]
0x140001a9a  lea     edx, [r14+13h]
0x140001a9e  mov     r9d, ebx
0x140001aa1  lea     r8, WPP_e22684400aa030ec2c531d4dcef4cab4_Traceguids
0x140001aa8  call    WPP_SF_d
0x140001aad  mov     eax, ebx
0x140001aaf  add     rsp, 48h
0x140001ab3  pop     r14
0x140001ab5  pop     rdi
0x140001ab6  pop     rsi
0x140001ab7  pop     rbx
0x140001ab8  retn
```
