# CUsbFilterControl::CreateInstance(WDFDRIVER__ *,CUsbFilterControl * *)

- ea: `0x1400068dc`
- end: `0x140006d26`
- name: `?CreateInstance@CUsbFilterControl@@CAJPEAUWDFDRIVER__@@PEAPEAV1@@Z`
- size: `1098`
- prototype: `__int64 __fastcall(struct WDFDRIVER__ *, struct CUsbFilterControl **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140008b54`

## callees

- `0x140004f18`
- `0x140004f48`
- `0x1400068dc`
- `0x14000818c`
- `0x14000a9f0`
- `0x14000aa30`

## string_xrefs

- `0x14000696b`: `\Device\TerminalServicesUSBFilterDriverControlObject`

## pseudocode

```c
__int64 __fastcall CUsbFilterControl::CreateInstance(struct WDFDRIVER__ *a1, struct CUsbFilterControl **a2)
{
  int v3; // ebx
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax
  struct CUsbFilterControl *v10; // rdi
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  struct WDFDEVICE__ *v13; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v14; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h]
  __int128 v16; // [rsp+60h] [rbp-A0h]
  __int64 *v17; // [rsp+70h] [rbp-90h]
  _QWORD v18[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v19; // [rsp+88h] [rbp-78h] BYREF
  __int128 v20; // [rsp+98h] [rbp-68h]
  __int64 v21; // [rsp+A8h] [rbp-58h]
  _OWORD v22[5]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v23[2]; // [rsp+100h] [rbp+0h]

  v22[1] = *(_OWORD *)L"TerminalServicesUSBFilterDriverControlObject";
  v14 = 0;
  v17 = 0;
  v15 = 0;
  v21 = 0;
  v16 = 0;
  v18[1] = v22;
  v19 = 0;
  v12 = 0;
  v20 = 0;
  v18[0] = 6946920;
  v22[0] = *(_OWORD *)L"\\Device\\TerminalServicesUSBFilterDriverControlObject";
  v22[2] = *(_OWORD *)L"ServicesUSBFilterDriverControlObject";
  v22[4] = *(_OWORD *)L"rDriverControlObject";
  v13 = 0;
  v22[3] = *(_OWORD *)L"USBFilterDriverControlObject";
  v23[0] = *(_OWORD *)L"ontrolObject";
  *(_OWORD *)((char *)v23 + 10) = *(_OWORD *)L"lObject";
  v12 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDRIVER__ *, const wchar_t *))WPP_MAIN_CB.Queue.ListEntry.Flink[12].Blink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          a1,
          L"VX");
  if ( !v12 )
  {
    v3 = -1073741670;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v5 = 20;
LABEL_23:
      WPP_SF_(v4->AttachedDevice, v5, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids);
      goto LABEL_24;
    }
    goto LABEL_24;
  }
  ((void (__fastcall *)(struct _LIST_ENTRY *, __int64, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[31].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    v12,
    0);
  ((void (__fastcall *)(struct _LIST_ENTRY *, __int64, __int64))WPP_MAIN_CB.Queue.ListEntry.Flink[30].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    v12,
    2);
  v3 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64, _QWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[33].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         v12,
         v18);
  if ( v3 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_24;
    v7 = 21;
    goto LABEL_9;
  }
  *((_QWORD *)&v19 + 1) = &FcEvtDeviceFileCreate;
  LODWORD(v19) = 40;
  *(_QWORD *)&v15 = 0;
  *(_QWORD *)&v20 = FcEvtFileClose;
  v17 = off_14000F178;
  v14 = 0;
  *((_QWORD *)&v20 + 1) = 0;
  v21 = 0x400000002LL;
  v16 = 0;
  LODWORD(v14) = 56;
  *((_QWORD *)&v15 + 1) = 0x100000001LL;
  ((void (__fastcall *)(struct _LIST_ENTRY *, __int64, __int128 *, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[35].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    v12,
    &v19,
    &v14);
  v17 = off_14000F068;
  *(_QWORD *)&v14 = 56;
  *((_QWORD *)&v14 + 1) = FcEvtControlCleanupCallback;
  *(_QWORD *)&v15 = 0;
  v16 = 0;
  *((_QWORD *)&v15 + 1) = 0x200000002LL;
  v3 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64 *, __int128 *, struct WDFDEVICE__ **))WPP_MAIN_CB.Queue.ListEntry.Flink[37].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         &v12,
         &v14,
         &v13);
  if ( v3 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_24;
    v7 = 22;
    goto LABEL_9;
  }
  v8 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[15].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         v13);
  ++*(_BYTE *)(v8 + 76);
  v9 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         v13,
         off_14000F068);
  v10 = (struct CUsbFilterControl *)v9;
  if ( v9 )
  {
    *(_QWORD *)v9 = 0;
    *(_QWORD *)(v9 + 8) = 0;
    *(_QWORD *)(v9 + 16) = 0;
    *(_DWORD *)(v9 + 24) = 0;
    *(_QWORD *)(v9 + 32) = 0;
    *(_DWORD *)(v9 + 40) = 3;
    v3 = CUsbFilterControl::Initialize((CUsbFilterControl *)v9, v13);
    if ( v3 >= 0 )
    {
      v3 = 0;
      *a2 = v10;
      v13 = 0;
      goto LABEL_24;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_24;
    v7 = 24;
LABEL_9:
    WPP_SF_d(v6->AttachedDevice, v7, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids, (unsigned int)v3);
    goto LABEL_24;
  }
  v3 = -1073741801;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v5 = 23;
    goto LABEL_23;
  }
LABEL_24:
  if ( v12 )
    ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[27].Flink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
  if ( v13 )
    ((void (__fastcall *)(struct _LIST_ENTRY *))WPP_MAIN_CB.Queue.ListEntry.Flink[104].Flink)(WPP_MAIN_CB.Queue.ListEntry.Blink);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400068dc  mov     [rsp-8+arg_10], rbx
0x1400068e1  push    rbp
0x1400068e2  push    rdi
0x1400068e3  push    r14
0x1400068e5  lea     rbp, [rsp-30h]
0x1400068ea  sub     rsp, 130h
0x1400068f1  mov     rax, cs:__security_cookie
0x1400068f8  xor     rax, rsp
0x1400068fb  mov     [rbp+40h+var_20], rax
0x1400068ff  movaps  xmm1, xmmword ptr cs:aDeviceTerminal+10h; "TerminalServicesUSBFilterDriverControlO"...
0x140006906  lea     r8, aVx; "VX"
0x14000690d  xorps   xmm0, xmm0
0x140006910  movaps  [rbp+40h+var_80], xmm1
0x140006914  movaps  xmm1, xmmword ptr cs:aDeviceTerminal+30h; "USBFilterDriverControlObject"
0x14000691b  xor     eax, eax
0x14000691d  movups  [rsp+140h+var_100], xmm0
0x140006922  mov     [rsp+140h+var_D0], rax
0x140006927  mov     r14, rdx
0x14000692a  movups  [rsp+140h+var_F0], xmm0
0x14000692f  mov     [rbp+40h+var_98], rax
0x140006933  lea     rax, [rbp+40h+var_90]
0x140006937  movups  [rsp+140h+var_E0], xmm0
0x14000693c  mov     [rbp+40h+var_C0], rax
0x140006940  mov     rdx, rcx
0x140006943  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x14000694a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006951  movups  [rbp+40h+var_B8], xmm0
0x140006955  mov     [rsp+140h+var_110], 0
0x14000695e  movups  [rbp+40h+var_A8], xmm0
0x140006962  mov     [rsp+140h+var_C8], 6A0068h
0x14000696b  movaps  xmm0, xmmword ptr cs:aDeviceTerminal; "\\Device\\TerminalServicesUSBFilterDriv"...
0x140006972  movaps  [rbp+40h+var_90], xmm0
0x140006976  movaps  xmm0, xmmword ptr cs:aDeviceTerminal+20h; "ServicesUSBFilterDriverControlObject"
0x14000697d  movaps  [rbp+40h+var_70], xmm0
0x140006981  movaps  xmm0, xmmword ptr cs:aDeviceTerminal+40h; "rDriverControlObject"
0x140006988  movaps  [rbp+40h+var_50], xmm0
0x14000698c  movups  xmm0, xmmword ptr cs:aDeviceTerminal+5Ah; "lObject"
0x140006993  mov     [rsp+140h+var_108], 0
0x14000699c  movaps  [rbp+40h+var_60], xmm1
0x1400069a0  movaps  xmm1, xmmword ptr cs:aDeviceTerminal+50h; "ontrolObject"
0x1400069a7  movaps  xmmword ptr [rbp+40h+var_40], xmm1
0x1400069ab  movups  xmmword ptr [rbp+40h+var_40+0Ah], xmm0
0x1400069af  mov     rax, [rax+0C8h]
0x1400069b6  call    _guard_dispatch_icall
0x1400069bb  mov     [rsp+140h+var_110], rax
0x1400069c0  test    rax, rax
0x1400069c3  jnz     short loc_1400069F5
0x1400069c5  mov     ebx, 0C000009Ah
0x1400069ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400069d1  lea     rax, WPP_GLOBAL_Control
0x1400069d8  cmp     rcx, rax
0x1400069db  jz      loc_140006CBB
0x1400069e1  cmp     byte ptr [rcx+29h], 2
0x1400069e5  jb      loc_140006CBB
0x1400069eb  mov     edx, 14h
0x1400069f0  jmp     loc_140006CAB
0x1400069f5  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400069fc  xor     r8d, r8d
0x1400069ff  mov     rdx, [rsp+140h+var_110]
0x140006a04  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006a0b  mov     rax, [rax+1F0h]
0x140006a12  call    _guard_dispatch_icall
0x140006a17  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006a1e  mov     r8d, 2
0x140006a24  mov     rdx, [rsp+140h+var_110]
0x140006a29  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006a30  mov     rax, [rax+1E8h]
0x140006a37  call    _guard_dispatch_icall
0x140006a3c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006a43  lea     r8, [rsp+140h+var_C8]
0x140006a48  mov     rdx, [rsp+140h+var_110]
0x140006a4d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006a54  mov     rax, [rax+218h]
0x140006a5b  call    _guard_dispatch_icall
0x140006a60  mov     ebx, eax
0x140006a62  test    eax, eax
0x140006a64  jns     short loc_140006AA4
0x140006a66  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a6d  lea     rax, WPP_GLOBAL_Control
0x140006a74  cmp     rcx, rax
0x140006a77  jz      loc_140006CBB
0x140006a7d  cmp     byte ptr [rcx+29h], 2
0x140006a81  jb      loc_140006CBB
0x140006a87  mov     edx, 15h
0x140006a8c  mov     rcx, [rcx+18h]
0x140006a90  lea     r8, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x140006a97  mov     r9d, ebx
0x140006a9a  call    WPP_SF_d
0x140006a9f  jmp     loc_140006CBB
0x140006aa4  mov     rdx, [rsp+140h+var_110]
0x140006aa9  lea     rax, FcEvtDeviceFileCreate
0x140006ab0  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006ab7  lea     r9, [rsp+140h+var_100]
0x140006abc  mov     qword ptr [rbp+40h+var_B8+8], rax
0x140006ac0  lea     r8, [rbp+40h+var_B8]
0x140006ac4  xorps   xmm0, xmm0
0x140006ac7  mov     dword ptr [rbp+40h+var_B8], 28h ; '('
0x140006ace  movups  [rsp+140h+var_F0], xmm0
0x140006ad3  lea     rax, FcEvtFileClose
0x140006ada  mov     ebx, 38h ; '8'
0x140006adf  mov     qword ptr [rbp+40h+var_A8], rax
0x140006ae3  mov     rax, cs:off_14000F178
0x140006aea  mov     [rsp+140h+var_D0], rax
0x140006aef  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006af6  lea     edi, [rbx-37h]
0x140006af9  movups  [rsp+140h+var_100], xmm0
0x140006afe  mov     qword ptr [rbp+40h+var_A8+8], 0
0x140006b06  mov     dword ptr [rbp+40h+var_98+4], 4
0x140006b0d  mov     dword ptr [rbp+40h+var_98], 2
0x140006b14  movups  [rsp+140h+var_E0], xmm0
0x140006b19  mov     dword ptr [rsp+140h+var_100], ebx
0x140006b1d  mov     dword ptr [rsp+140h+var_F0+8], edi
0x140006b21  mov     dword ptr [rsp+140h+var_F0+0Ch], edi
0x140006b25  mov     rax, [rax+238h]
0x140006b2c  call    _guard_dispatch_icall
0x140006b31  mov     rax, cs:off_14000F068
0x140006b38  lea     r9, [rsp+140h+var_108]
0x140006b3d  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006b44  lea     r8, [rsp+140h+var_100]
0x140006b49  mov     [rsp+140h+var_D0], rax
0x140006b4e  lea     rdx, [rsp+140h+var_110]
0x140006b53  lea     rax, FcEvtControlCleanupCallback
0x140006b5a  mov     qword ptr [rsp+140h+var_100], rbx
0x140006b5f  mov     qword ptr [rsp+140h+var_100+8], rax
0x140006b64  xorps   xmm0, xmm0
0x140006b67  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006b6e  mov     qword ptr [rsp+140h+var_F0], 0
0x140006b77  movdqu  [rsp+140h+var_E0], xmm0
0x140006b7d  mov     dword ptr [rsp+140h+var_F0+8], 2
0x140006b85  mov     dword ptr [rsp+140h+var_F0+0Ch], 2
0x140006b8d  mov     rax, [rax+258h]
0x140006b94  call    _guard_dispatch_icall
0x140006b99  mov     ebx, eax
0x140006b9b  test    eax, eax
0x140006b9d  jns     short loc_140006BC8
0x140006b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ba6  lea     rax, WPP_GLOBAL_Control
0x140006bad  cmp     rcx, rax
0x140006bb0  jz      loc_140006CBB
0x140006bb6  cmp     byte ptr [rcx+29h], 2
0x140006bba  jb      loc_140006CBB
0x140006bc0  lea     edx, [rdi+15h]
0x140006bc3  jmp     loc_140006A8C
0x140006bc8  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006bcf  mov     rdx, [rsp+140h+var_108]
0x140006bd4  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006bdb  mov     rax, [rax+0F8h]
0x140006be2  call    _guard_dispatch_icall
0x140006be7  add     [rax+4Ch], dil
0x140006beb  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006bf2  mov     r8, cs:off_14000F068
0x140006bf9  mov     rdx, [rsp+140h+var_108]
0x140006bfe  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006c05  mov     rax, [rax+650h]
0x140006c0c  call    _guard_dispatch_icall
0x140006c11  mov     rdi, rax
0x140006c14  test    rax, rax
0x140006c17  jz      short loc_140006C88
0x140006c19  mov     qword ptr [rax], 0
0x140006c20  mov     rcx, rax; this
0x140006c23  mov     qword ptr [rax+8], 0
0x140006c2b  mov     qword ptr [rax+10h], 0
0x140006c33  mov     dword ptr [rax+18h], 0
0x140006c3a  mov     qword ptr [rax+20h], 0
0x140006c42  mov     dword ptr [rax+28h], 3
0x140006c49  mov     rdx, [rsp+140h+var_108]; struct WDFDEVICE__ *
0x140006c4e  call    ?Initialize@CUsbFilterControl@@AEAAJPEAUWDFDEVICE__@@@Z; CUsbFilterControl::Initialize(WDFDEVICE__ *)
0x140006c53  mov     ebx, eax
0x140006c55  test    eax, eax
0x140006c57  jns     short loc_140006C7C
0x140006c59  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c60  lea     rax, WPP_GLOBAL_Control
0x140006c67  cmp     rcx, rax
0x140006c6a  jz      short loc_140006CBB
0x140006c6c  cmp     byte ptr [rcx+29h], 2
0x140006c70  jb      short loc_140006CBB
0x140006c72  mov     edx, 18h
0x140006c77  jmp     loc_140006A8C
0x140006c7c  xor     ebx, ebx
0x140006c7e  mov     [r14], rdi
0x140006c81  mov     [rsp+140h+var_108], rbx
0x140006c86  jmp     short loc_140006CBB
0x140006c88  mov     ebx, 0C0000017h
0x140006c8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006c94  lea     rax, WPP_GLOBAL_Control
0x140006c9b  cmp     rcx, rax
0x140006c9e  jz      short loc_140006CBB
0x140006ca0  cmp     byte ptr [rcx+29h], 2
0x140006ca4  jb      short loc_140006CBB
0x140006ca6  mov     edx, 17h
0x140006cab  mov     rcx, [rcx+18h]
0x140006caf  lea     r8, WPP_02dd943b345c3ce3db307cc1c0a3a28d_Traceguids
0x140006cb6  call    WPP_SF_
0x140006cbb  mov     rdx, [rsp+140h+var_110]
0x140006cc0  test    rdx, rdx
0x140006cc3  jz      short loc_140006CDF
0x140006cc5  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006ccc  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006cd3  mov     rax, [rax+1B0h]
0x140006cda  call    _guard_dispatch_icall
0x140006cdf  mov     rdx, [rsp+140h+var_108]
0x140006ce4  test    rdx, rdx
0x140006ce7  jz      short loc_140006D03
0x140006ce9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140006cf0  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140006cf7  mov     rax, [rax+680h]
0x140006cfe  call    _guard_dispatch_icall
0x140006d03  mov     eax, ebx
0x140006d05  mov     rcx, [rbp+40h+var_20]
0x140006d09  xor     rcx, rsp; StackCookie
0x140006d0c  call    __security_check_cookie
0x140006d11  mov     rbx, [rsp+140h+arg_10]
0x140006d19  add     rsp, 130h
0x140006d20  pop     r14
0x140006d22  pop     rdi
0x140006d23  pop     rbp
0x140006d24  retn
```
