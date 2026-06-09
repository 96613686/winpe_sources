# CUsbFilterIoTarget::CreateInstance(WDFDEVICE__ *,WDFDEVICE__ *,CUsbFilterIoTarget * *)

- ea: `0x140006d2c`
- end: `0x140006ef3`
- name: `?CreateInstance@CUsbFilterIoTarget@@SAJPEAUWDFDEVICE__@@0PEAPEAV1@@Z`
- size: `455`
- prototype: `static int(struct WDFDEVICE__ *, struct WDFDEVICE__ *, struct CUsbFilterIoTarget **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140008d84`

## callees

- `0x140004f18`
- `0x140004f48`
- `0x140006240`
- `0x140006d2c`
- `0x140008818`
- `0x14000aa30`

## pseudocode

```c
__int64 __fastcall CUsbFilterIoTarget::CreateInstance(
        struct WDFDEVICE__ *a1,
        struct WDFDEVICE__ *a2,
        struct CUsbFilterIoTarget **a3)
{
  int v5; // ebx
  struct CUsbFilterIoTarget *v6; // rax
  struct CUsbFilterIoTarget *v7; // rdi
  _QWORD v9[3]; // [rsp+30h] [rbp-40h] BYREF
  int v10; // [rsp+48h] [rbp-28h]
  int v11; // [rsp+4Ch] [rbp-24h]
  struct WDFDEVICE__ *v12; // [rsp+50h] [rbp-20h]
  __int64 v13; // [rsp+58h] [rbp-18h]
  __int64 *v14; // [rsp+60h] [rbp-10h]
  struct WDFIOTARGET__ *v15; // [rsp+90h] [rbp+20h] BYREF

  v12 = a1;
  v10 = 1;
  v11 = 1;
  v14 = off_14000F040;
  v15 = 0;
  v9[1] = FcEvtIoTargetCleanupCallback;
  v9[0] = 56;
  v9[2] = 0;
  v13 = 0;
  v5 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *, _QWORD *, struct WDFIOTARGET__ **))WPP_MAIN_CB.Queue.ListEntry.Flink[83].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a1,
         v9,
         &v15);
  if ( v5 >= 0 )
  {
    v6 = (struct CUsbFilterIoTarget *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFIOTARGET__ *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
                                        WPP_MAIN_CB.Queue.ListEntry.Blink,
                                        v15,
                                        off_14000F040);
    v7 = v6;
    if ( v6 )
    {
      *((_QWORD *)v6 + 1) = 0;
      v5 = CUsbFilterIoTarget::Initialize(v6, v15, a2);
      if ( v5 >= 0 )
      {
        v5 = 0;
        *a3 = v7;
        v15 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            47,
            WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids,
            (unsigned int)v5);
        CUsbFilterIoTarget::~CUsbFilterIoTarget(v7);
      }
    }
    else
    {
      v5 = -1073741801;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids, (unsigned int)v5);
  }
  if ( v15 )
    ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140006d2c  mov     [rsp-18h+arg_8], rbx
0x140006d31  mov     [rsp-18h+arg_10], rsi
0x140006d36  push    rbp
0x140006d37  push    rdi
0x140006d38  push    r14
0x140006d3a  mov     rbp, rsp
0x140006d3d  sub     rsp, 70h
0x140006d41  mov     eax, 1
0x140006d46  mov     [rbp+var_20], rcx
0x140006d4a  mov     [rbp+var_28], eax
0x140006d4d  lea     r9, [rbp+arg_0]
0x140006d51  mov     [rbp+var_24], eax
0x140006d54  mov     r14, rdx
0x140006d57  mov     rax, cs:off_14000F040
0x140006d5e  mov     rsi, r8
0x140006d61  mov     [rbp+var_10], rax
0x140006d65  lea     r8, [rbp+var_40]
0x140006d69  lea     rax, FcEvtIoTargetCleanupCallback
0x140006d70  mov     [rbp+arg_0], 0
0x140006d78  mov     [rbp+var_38], rax
0x140006d7c  mov     rdx, rcx
0x140006d7f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006d86  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006d8d  mov     [rbp+var_40], 38h ; '8'
0x140006d95  mov     [rbp+var_30], 0
0x140006d9d  mov     [rbp+var_18], 0
0x140006da5  mov     rax, [rax+538h]
0x140006dac  call    _guard_dispatch_icall
0x140006db1  mov     ebx, eax
0x140006db3  test    eax, eax
0x140006db5  jns     short loc_140006DF5
0x140006db7  mov     rcx, cs:WPP_GLOBAL_Control
0x140006dbe  lea     rax, WPP_GLOBAL_Control
0x140006dc5  cmp     rcx, rax
0x140006dc8  jz      loc_140006EB8
0x140006dce  cmp     byte ptr [rcx+29h], 2
0x140006dd2  jb      loc_140006EB8
0x140006dd8  mov     rcx, [rcx+18h]
0x140006ddc  lea     r8, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x140006de3  mov     edx, 2Dh ; '-'
0x140006de8  mov     r9d, ebx
0x140006deb  call    WPP_SF_d
0x140006df0  jmp     loc_140006EB8
0x140006df5  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006dfc  mov     r8, cs:off_14000F040
0x140006e03  mov     rdx, [rbp+arg_0]
0x140006e07  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006e0e  mov     rax, [rax+650h]
0x140006e15  call    _guard_dispatch_icall
0x140006e1a  mov     rdi, rax
0x140006e1d  test    rax, rax
0x140006e20  jz      short loc_140006E85
0x140006e22  mov     qword ptr [rax+8], 0
0x140006e2a  mov     r8, r14; struct WDFDEVICE__ *
0x140006e2d  mov     rdx, [rbp+arg_0]; struct WDFIOTARGET__ *
0x140006e31  mov     rcx, rax; this
0x140006e34  call    ?Initialize@CUsbFilterIoTarget@@AEAAJPEAUWDFIOTARGET__@@PEAUWDFDEVICE__@@@Z; CUsbFilterIoTarget::Initialize(WDFIOTARGET__ *,WDFDEVICE__ *)
0x140006e39  mov     ebx, eax
0x140006e3b  test    eax, eax
0x140006e3d  jns     short loc_140006E7A
0x140006e3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e46  lea     rax, WPP_GLOBAL_Control
0x140006e4d  cmp     rcx, rax
0x140006e50  jz      short loc_140006E70
0x140006e52  cmp     byte ptr [rcx+29h], 2
0x140006e56  jb      short loc_140006E70
0x140006e58  mov     rcx, [rcx+18h]
0x140006e5c  lea     r8, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x140006e63  mov     edx, 2Fh ; '/'
0x140006e68  mov     r9d, ebx
0x140006e6b  call    WPP_SF_d
0x140006e70  mov     rcx, rdi; this
0x140006e73  call    ??1CUsbFilterIoTarget@@QEAA@XZ; CUsbFilterIoTarget::~CUsbFilterIoTarget(void)
0x140006e78  jmp     short loc_140006EB8
0x140006e7a  xor     ebx, ebx
0x140006e7c  mov     [rsi], rdi
0x140006e7f  mov     [rbp+arg_0], rbx
0x140006e83  jmp     short loc_140006EB8
0x140006e85  mov     ebx, 0C0000017h
0x140006e8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e91  lea     rax, WPP_GLOBAL_Control
0x140006e98  cmp     rcx, rax
0x140006e9b  jz      short loc_140006EB8
0x140006e9d  cmp     byte ptr [rcx+29h], 2
0x140006ea1  jb      short loc_140006EB8
0x140006ea3  mov     rcx, [rcx+18h]
0x140006ea7  lea     r8, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x140006eae  mov     edx, 2Eh ; '.'
0x140006eb3  call    WPP_SF_
0x140006eb8  mov     rdx, [rbp+arg_0]
0x140006ebc  test    rdx, rdx
0x140006ebf  jz      short loc_140006EDB
0x140006ec1  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006ec8  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006ecf  mov     rax, [rax+680h]
0x140006ed6  call    _guard_dispatch_icall
0x140006edb  lea     r11, [rsp+70h+var_s0]
0x140006ee0  mov     eax, ebx
0x140006ee2  mov     rbx, [r11+28h]
0x140006ee6  mov     rsi, [r11+30h]
0x140006eea  mov     rsp, r11
0x140006eed  pop     r14
0x140006eef  pop     rdi
0x140006ef0  pop     rbp
0x140006ef1  retn
```
