# TpmTransportSpb::TpmEvtDevicePrepareHardware(WDFDEVICE__ *,WDFCMRESLIST__ *,WDFCMRESLIST__ *)

- ea: `0x140027bc0`
- end: `0x1400281dc`
- name: `?TpmEvtDevicePrepareHardware@TpmTransportSpb@@UEAAJPEAUWDFDEVICE__@@PEAUWDFCMRESLIST__@@1@Z`
- size: `1564`
- prototype: `__int64 __fastcall(TpmTransportSpb *__hidden this, struct WDFDEVICE__ *, struct WDFCMRESLIST__ *, struct WDFCMRESLIST__ *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1400104b4`
- `0x140016358`
- `0x14001cfdc`
- `0x140025480`
- `0x140027bc0`
- `0x14002827c`
- `0x1400282b4`
- `0x140029560`
- `0x140039740`
- `0x140039780`
- `0x140039b40`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140027e65`
- `ntoskrnl!KeWaitForSingleObject` at `0x140027e65`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140027f39`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002802d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140028079`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140027f39`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002802d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140028079`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027f09`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027f21`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027fe7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027ffe`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028015`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027f09`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027f21`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027fe7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027ffe`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028015`
- `ntoskrnl!KeInitializeEvent` at `0x140027e0e`
- `ntoskrnl!KeInitializeEvent` at `0x140027e0e`

## pseudocode

```c
__int64 __fastcall TpmTransportSpb::TpmEvtDevicePrepareHardware(
        void **this,
        struct WDFDEVICE__ *a2,
        struct WDFCMRESLIST__ *a3,
        struct WDFCMRESLIST__ *a4)
{
  struct WDFCMRESLIST__ *v5; // r14
  int Sizes; // edi
  __int64 (__fastcall *v7)(PKDPC, struct WDFDEVICE__ *, void *); // rax
  unsigned int v8; // r15d
  unsigned int i; // ebx
  __int16 v10; // r12
  __int16 v11; // r13
  _BYTE *v12; // rax
  _BYTE *v13; // rbx
  char v14; // r14
  int v15; // edi
  int v16; // ebx
  const WCHAR *v17; // rax
  void ***v18; // rax
  void ***v19; // rcx
  void **v20; // rax
  void ***v21; // rax
  const WCHAR *v22; // rax
  void ***v23; // rax
  void **v24; // rax
  void ***v25; // rax
  TpmTransportSpbI2CDevice *v26; // rax
  _QWORD *v27; // rbx
  unsigned __int16 v28; // dx
  struct WDFIOTARGET__ *v30; // [rsp+40h] [rbp-C0h] BYREF
  struct WDFCMRESLIST__ *v31; // [rsp+48h] [rbp-B8h]
  unsigned int v32; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING String2; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+70h] [rbp-90h] BYREF
  int v36; // [rsp+74h] [rbp-8Ch]
  char *v37; // [rsp+78h] [rbp-88h]
  __int64 v38; // [rsp+80h] [rbp-80h]
  union _LARGE_INTEGER Timeout; // [rsp+88h] [rbp-78h] BYREF
  struct WDFDEVICE__ *v40; // [rsp+90h] [rbp-70h]
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  TpmDevice *v42; // [rsp+A8h] [rbp-58h]
  __int128 v43; // [rsp+B0h] [rbp-50h] BYREF
  int v44; // [rsp+C0h] [rbp-40h]
  UNICODE_STRING v45; // [rsp+C8h] [rbp-38h] BYREF
  struct _KEVENT Event; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v47[18]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v48[48]; // [rsp+180h] [rbp+80h] BYREF
  char v49; // [rsp+1B0h] [rbp+B0h] BYREF

  v44 = 0;
  v5 = a4;
  v31 = a4;
  Sizes = 0;
  v40 = a2;
  v7 = (__int64 (__fastcall *)(PKDPC, struct WDFDEVICE__ *, void *))*((_QWORD *)WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 202);
  v43 = 0;
  v42 = (TpmDevice *)v7(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc, a2, off_140047040);
  v33 = 0;
  memset(v47, 0, 0x88u);
  Timeout.QuadPart = 0;
  memset(&Event, 0, sizeof(Event));
  v30 = 0;
  if ( TpmTransportType::m_Version != 2 )
    return (unsigned int)Sizes;
  v8 = 0;
  for ( i = 0; ; i = v32 + 1 )
  {
    v32 = i;
    if ( i >= (*((unsigned int (__fastcall **)(PKDPC, struct WDFCMRESLIST__ *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 304))(
                WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                v5) )
      break;
    *(_QWORD *)&String2.Length = 0;
    v36 = 0;
    v35 = 9961472;
    v37 = &v49;
    v10 = 0;
    v11 = 152;
    v12 = (_BYTE *)(*((__int64 (__fastcall **)(PKDPC, struct WDFCMRESLIST__ *, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                    + 305))(
                     WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                     v5,
                     i);
    v13 = v12;
    if ( !v12 )
    {
      Sizes = -1073741438;
      v27 = this + 42;
      goto LABEL_47;
    }
    if ( *v12 == 0x84 && v12[4] == 2 )
    {
      v14 = v12[5];
      if ( (unsigned __int8)(v14 - 1) <= 1u )
      {
        v15 = (*((__int64 (__fastcall **)(PKDPC, struct WDFDEVICE__ *, _QWORD, struct WDFIOTARGET__ **))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
               + 167))(
                WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                v40,
                0,
                &v30);
        if ( v15 < 0 )
          break;
        v38 = *((_QWORD *)v13 + 1);
        if ( (int)RESOURCE_HUB_STRING_PRINTF(v48, 34, L"%0*I64x", 16, v38) < 0 )
        {
          v16 = *(_DWORD *)&String2.Length;
        }
        else
        {
          RESOURCE_HUB_UNICODE_STRING_PRINTF(&v35, L"%s%s", L"\\Device\\RESOURCE_HUB\\", v48);
          v16 = v36;
          v11 = HIWORD(v35);
          v10 = v35;
        }
        memset(v47, 0, 0x88u);
        HIDWORD(v47[6]) = v16;
        v47[7] = v37;
        v47[0] = 0x200000088LL;
        LOWORD(v47[6]) = v10;
        WORD1(v47[6]) = v11;
        v47[8] = 3221225472LL;
        LODWORD(v47[10]) = 64;
        v47[9] = 0x100000080LL;
        KeInitializeEvent(&Event, NotificationEvent, 0);
        while ( v8 < 0x100 )
        {
          ++v8;
          v15 = (*((__int64 (__fastcall **)(PKDPC, struct WDFIOTARGET__ *, _QWORD *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                 + 168))(
                  WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                  v30,
                  v47);
          if ( v15 >= 0 )
            goto LABEL_18;
          Timeout.QuadPart = -100000;
          KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout);
        }
        if ( v15 < 0 )
          break;
        ++v8;
LABEL_18:
        if ( (*((int (__fastcall **)(PKDPC, struct WDFDEVICE__ *, __int64, __int64, _QWORD, __int64 *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
              + 82))(
               WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
               v40,
               1,
               512,
               0,
               &v33) < 0 )
          break;
        if ( v14 == 2 )
        {
          DestinationString = 0;
          String2 = 0;
          v17 = (const WCHAR *)(*((__int64 (__fastcall **)(PKDPC, __int64, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 194))(
                                 WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                                 v33,
                                 0);
          RtlInitUnicodeString(&DestinationString, v17);
          RtlInitUnicodeString(&String2, L"ACPI\\VEN_NATZ&DEV_0101");
          if ( RtlCompareUnicodeString(&DestinationString, &String2, 1u) )
          {
            v21 = (void ***)AllocatorBaseNonPaged::operator new(0x18u);
            v19 = v21;
            if ( !v21 )
              goto LABEL_26;
            v21[1] = (void **)v30;
            v20 = &TpmTransportSpbSPIDevice::`vftable';
LABEL_25:
            *v19 = v20;
            v19[2] = this;
          }
          else
          {
            v18 = (void ***)AllocatorBaseNonPaged::operator new(0x18u);
            v19 = v18;
            if ( v18 )
            {
              v18[1] = (void **)v30;
              v20 = &TpmTransportSpbSPINTZDevice::`vftable';
              goto LABEL_25;
            }
LABEL_26:
            v19 = 0;
          }
LABEL_27:
          this[42] = v19;
        }
        else if ( v14 == 1 )
        {
          String2 = 0;
          DestinationString = 0;
          v45 = 0;
          v22 = (const WCHAR *)(*((__int64 (__fastcall **)(PKDPC, __int64, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 194))(
                                 WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                                 v33,
                                 0);
          RtlInitUnicodeString(&String2, v22);
          RtlInitUnicodeString(&DestinationString, L"ACPI\\VEN_NATZ&DEV_0101");
          RtlInitUnicodeString(&v45, L"ACPI\\VEN_NVTN&DEV_0101");
          if ( RtlCompareUnicodeString(&String2, &DestinationString, 1u) )
          {
            if ( RtlCompareUnicodeString(&String2, &v45, 1u) )
            {
              v26 = (TpmTransportSpbI2CDevice *)AllocatorBaseNonPaged::operator new(0x38u);
              if ( v26 )
                v26 = TpmTransportSpbI2CDevice::TpmTransportSpbI2CDevice(v26, v30, (struct TpmTransportSpb *)this);
              this[42] = v26;
              goto LABEL_39;
            }
            v25 = (void ***)AllocatorBaseNonPaged::operator new(0x18u);
            v19 = v25;
            if ( !v25 )
              goto LABEL_26;
            v25[1] = (void **)v30;
            v24 = &TpmTransportSpbI2CNTCDevice::`vftable';
          }
          else
          {
            v23 = (void ***)AllocatorBaseNonPaged::operator new(0x18u);
            v19 = v23;
            if ( !v23 )
              goto LABEL_26;
            v23[1] = (void **)v30;
            v24 = &TpmTransportSpbI2CNTZDevice::`vftable';
          }
          v19[2] = this;
          *v19 = v24;
          goto LABEL_27;
        }
      }
LABEL_39:
      v5 = v31;
      continue;
    }
  }
  v27 = this + 42;
  if ( this[42] )
  {
    Sizes = TpmDevice::Initialize(v42);
    if ( Sizes >= 0 )
    {
      Tpm20CmdTpmStartup((struct TpmTransport *)this, v28);
      Sizes = Tpm20CmdGetSizes((struct TpmTransport *)this, (struct _TPM20CMD_SIZES *)&v43);
      if ( Sizes >= 0 )
        *((_DWORD *)this + 78) = v43;
    }
  }
  else
  {
    Sizes = -1073741438;
  }
LABEL_47:
  if ( v33 )
  {
    (*((void (__fastcall **)(PKDPC))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 208))(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc);
    v33 = 0;
  }
  if ( Sizes < 0 )
  {
    if ( *v27 )
    {
      (**(void (__fastcall ***)(_QWORD, __int64))*v27)(*v27, 1);
      *v27 = 0;
    }
    else if ( v30 )
    {
      (*((void (__fastcall **)(PKDPC))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 170))(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc);
    }
  }
  return (unsigned int)Sizes;
}

```

## disassembly

```asm
0x140027bc0  mov     [rsp-8+arg_10], rbx
0x140027bc5  push    rbp
0x140027bc6  push    rsi
0x140027bc7  push    rdi
0x140027bc8  push    r12
0x140027bca  push    r13
0x140027bcc  push    r14
0x140027bce  push    r15
0x140027bd0  lea     rbp, [rsp-160h]
0x140027bd8  sub     rsp, 260h
0x140027bdf  mov     rax, cs:__security_cookie
0x140027be6  xor     rax, rsp
0x140027be9  mov     [rbp+190h+var_40], rax
0x140027bf0  mov     r8, cs:off_140047040
0x140027bf7  xor     eax, eax
0x140027bf9  mov     [rbp+190h+var_1D0], eax
0x140027bfc  mov     rsi, rcx
0x140027bff  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140027c06  xorps   xmm0, xmm0
0x140027c09  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140027c10  mov     r14, r9
0x140027c13  mov     [rsp+290h+var_248], r9
0x140027c18  xor     edi, edi
0x140027c1a  mov     [rbp+190h+var_200], rdx
0x140027c1e  mov     rax, [rax+650h]
0x140027c25  movups  [rbp+190h+var_1E0], xmm0
0x140027c29  call    _guard_dispatch_icall
0x140027c2e  xor     edx, edx; Val
0x140027c30  mov     [rbp+190h+var_1E8], rax
0x140027c34  mov     r8d, 88h; Size
0x140027c3a  mov     [rsp+290h+var_238], rdi
0x140027c3f  lea     rcx, [rbp+190h+var_1A0]; void *
0x140027c43  call    memset
0x140027c48  xor     eax, eax
0x140027c4a  mov     qword ptr [rbp+190h+var_208], rdi
0x140027c4e  cmp     cs:?m_Version@TpmTransportType@@0W4VERSION@1@A, 2; TpmTransportType::VERSION TpmTransportType::m_Version
0x140027c55  xorps   xmm0, xmm0
0x140027c58  movups  xmmword ptr [rbp+190h+Event.Header], xmm0
0x140027c5c  mov     [rbp+190h+Event.Header.WaitListHead.Blink], rax
0x140027c60  mov     [rsp+290h+var_250], rax
0x140027c65  jnz     loc_1400281AF
0x140027c6b  xor     r15d, r15d
0x140027c6e  xor     ebx, ebx
0x140027c70  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140027c77  mov     rdx, r14
0x140027c7a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140027c81  mov     [rsp+290h+var_240], ebx
0x140027c85  mov     rax, [rax+980h]
0x140027c8c  call    _guard_dispatch_icall
0x140027c91  cmp     ebx, eax
0x140027c93  jnb     loc_1400280F3
0x140027c99  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140027ca0  xor     eax, eax
0x140027ca2  mov     qword ptr [rsp+290h+String2.Length], rax
0x140027ca7  mov     r8d, ebx
0x140027caa  mov     [rsp+290h+var_21C], eax
0x140027cae  mov     rdx, r14
0x140027cb1  lea     rax, [rbp+190h+var_E0]
0x140027cb8  mov     [rsp+290h+var_220], 980000h
0x140027cc0  mov     [rsp+290h+var_218], rax
0x140027cc5  xor     r12d, r12d
0x140027cc8  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140027ccf  mov     r13d, 98h
0x140027cd5  mov     rax, [rax+988h]
0x140027cdc  call    _guard_dispatch_icall
0x140027ce1  mov     rbx, rax
0x140027ce4  test    rax, rax
0x140027ce7  jz      loc_1400280E5
0x140027ced  cmp     byte ptr [rax], 84h
0x140027cf0  jnz     loc_1400280DA
0x140027cf6  cmp     byte ptr [rax+4], 2
0x140027cfa  jnz     loc_1400280DA
0x140027d00  mov     r14b, [rax+5]
0x140027d04  lea     eax, [r14-1]
0x140027d08  cmp     al, 1
0x140027d0a  ja      loc_1400280D5
0x140027d10  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140027d17  lea     r9, [rsp+290h+var_250]
0x140027d1c  mov     rdx, [rbp+190h+var_200]
0x140027d20  xor     r8d, r8d
0x140027d23  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140027d2a  mov     rax, [rax+538h]
0x140027d31  call    _guard_dispatch_icall
0x140027d36  mov     edi, eax
0x140027d38  test    eax, eax
0x140027d3a  js      loc_1400280F3
0x140027d40  mov     eax, [rbx+8]
0x140027d43  lea     r9d, [r12+10h]
0x140027d48  mov     dword ptr [rbp+190h+var_210], eax
0x140027d4b  lea     r8, a0I64x; "%0*I64x"
0x140027d52  mov     eax, [rbx+0Ch]
0x140027d55  lea     edx, [r12+22h]
0x140027d5a  mov     dword ptr [rbp+190h+var_210+4], eax
0x140027d5d  lea     rcx, [rbp+190h+var_110]
0x140027d64  mov     rax, [rbp+190h+var_210]
0x140027d68  mov     [rsp+290h+Timeout], rax
0x140027d6d  call    RESOURCE_HUB_STRING_PRINTF
0x140027d72  test    eax, eax
0x140027d74  js      short loc_140027DA7
0x140027d76  lea     r9, [rbp+190h+var_110]
0x140027d7d  lea     r8, aDeviceResource; "\\Device\\RESOURCE_HUB\\"
0x140027d84  lea     rdx, aSS_0; "%s%s"
0x140027d8b  lea     rcx, [rsp+290h+var_220]
0x140027d90  call    RESOURCE_HUB_UNICODE_STRING_PRINTF
0x140027d95  mov     ebx, [rsp+290h+var_21C]
0x140027d99  movzx   r13d, word ptr [rsp+290h+var_220+2]
0x140027d9f  movzx   r12d, word ptr [rsp+290h+var_220]
0x140027da5  jmp     short loc_140027DAC
0x140027da7  mov     rbx, qword ptr [rsp+290h+String2.Length]
0x140027dac  xor     edx, edx; Val
0x140027dae  lea     rcx, [rbp+190h+var_1A0]; void *
0x140027db2  mov     r8d, 88h; Size
0x140027db8  call    memset
0x140027dbd  mov     rax, [rsp+290h+var_218]
0x140027dc2  lea     rcx, [rbp+190h+Event]; Event
0x140027dc6  mov     [rbp+190h+var_16C], ebx
0x140027dc9  xor     r8d, r8d; State
0x140027dcc  mov     ebx, 1
0x140027dd1  mov     [rbp+190h+var_168], rax
0x140027dd5  xor     edx, edx; Type
0x140027dd7  mov     [rbp+190h+var_154], ebx
0x140027dda  mov     [rbp+190h+var_1A0], 88h
0x140027de1  mov     [rbp+190h+var_19C], 2
0x140027de8  mov     [rbp+190h+var_170], r12w
0x140027ded  mov     [rbp+190h+var_16E], r13w
0x140027df2  mov     [rbp+190h+var_160], 0C0000000h
0x140027df9  mov     [rbp+190h+var_150], 40h ; '@'
0x140027e00  mov     [rbp+190h+var_15C], 0
0x140027e07  mov     [rbp+190h+var_158], 80h
0x140027e0e  call    cs:__imp_KeInitializeEvent
0x140027e15  nop     dword ptr [rax+rax+00h]
0x140027e1a  jmp     short loc_140027E71
0x140027e1c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140027e23  lea     r8, [rbp+190h+var_1A0]
0x140027e27  mov     rdx, [rsp+290h+var_250]
0x140027e2c  add     r15d, ebx
0x140027e2f  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140027e36  mov     rax, [rax+540h]
0x140027e3d  call    _guard_dispatch_icall
0x140027e42  mov     edi, eax
0x140027e44  test    eax, eax
0x140027e46  jns     short loc_140027E85
0x140027e48  lea     rax, [rbp+190h+var_208]
0x140027e4c  mov     qword ptr [rbp+190h+var_208], 0FFFFFFFFFFFE7960h
0x140027e54  xor     r9d, r9d; Alertable
0x140027e57  mov     [rsp+290h+Timeout], rax; Timeout
0x140027e5c  xor     r8d, r8d; WaitMode
0x140027e5f  lea     rcx, [rbp+190h+Event]; Object
0x140027e63  xor     edx, edx; WaitReason
0x140027e65  call    cs:__imp_KeWaitForSingleObject
0x140027e6c  nop     dword ptr [rax+rax+00h]
0x140027e71  cmp     r15d, 100h
0x140027e78  jb      short loc_140027E1C
0x140027e7a  test    edi, edi
0x140027e7c  js      loc_1400280F3
0x140027e82  add     r15d, ebx
0x140027e85  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140027e8c  lea     rcx, [rsp+290h+var_238]
0x140027e91  mov     rdx, [rbp+190h+var_200]
0x140027e95  mov     r9d, 200h
0x140027e9b  mov     [rsp+290h+var_268], rcx
0x140027ea0  mov     r8d, ebx
0x140027ea3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140027eaa  mov     rax, [rax+290h]
0x140027eb1  mov     [rsp+290h+Timeout], 0
0x140027eba  call    _guard_dispatch_icall
0x140027ebf  test    eax, eax
0x140027ec1  js      loc_1400280F3
0x140027ec7  cmp     r14b, 2
0x140027ecb  jnz     loc_140027FA1
0x140027ed1  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140027ed8  xorps   xmm0, xmm0
0x140027edb  mov     rdx, [rsp+290h+var_238]
0x140027ee0  xorps   xmm1, xmm1
0x140027ee3  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140027eea  xor     r8d, r8d
0x140027eed  movups  xmmword ptr [rbp+190h+DestinationString.Length], xmm0
0x140027ef1  movups  xmmword ptr [rsp+290h+String2.Length], xmm1
0x140027ef6  mov     rax, [rax+610h]
0x140027efd  call    _guard_dispatch_icall
0x140027f02  mov     rdx, rax; SourceString
0x140027f05  lea     rcx, [rbp+190h+DestinationString]; DestinationString
0x140027f09  call    cs:__imp_RtlInitUnicodeString
0x140027f10  nop     dword ptr [rax+rax+00h]
0x140027f15  lea     rdx, aAcpiVenNatzDev; "ACPI\\VEN_NATZ&DEV_0101"
0x140027f1c  lea     rcx, [rsp+290h+String2]; DestinationString
0x140027f21  call    cs:__imp_RtlInitUnicodeString
0x140027f28  nop     dword ptr [rax+rax+00h]
0x140027f2d  mov     r8b, bl; CaseInSensitive
0x140027f30  lea     rdx, [rsp+290h+String2]; String2
0x140027f35  lea     rcx, [rbp+190h+DestinationString]; String1
0x140027f39  call    cs:__imp_RtlCompareUnicodeString
0x140027f40  nop     dword ptr [rax+rax+00h]
0x140027f45  mov     ecx, 18h; Size
0x140027f4a  test    eax, eax
0x140027f4c  jnz     short loc_140027F6D
0x140027f4e  call    ??2AllocatorBaseNonPaged@@SAPEAX_K@Z; AllocatorBaseNonPaged::operator new(unsigned __int64)
0x140027f53  mov     rcx, rax
0x140027f56  test    rax, rax
0x140027f59  jz      short loc_140027F93
0x140027f5b  mov     rax, [rsp+290h+var_250]
0x140027f60  mov     [rcx+8], rax
0x140027f64  lea     rax, ??_7TpmTransportSpbSPINTZDevice@@6B@; const TpmTransportSpbSPINTZDevice::`vftable'
0x140027f6b  jmp     short loc_140027F8A
0x140027f6d  call    ??2AllocatorBaseNonPaged@@SAPEAX_K@Z; AllocatorBaseNonPaged::operator new(unsigned __int64)
0x140027f72  mov     rcx, rax
0x140027f75  test    rax, rax
0x140027f78  jz      short loc_140027F93
0x140027f7a  mov     rax, [rsp+290h+var_250]
0x140027f7f  mov     [rcx+8], rax
0x140027f83  lea     rax, ??_7TpmTransportSpbSPIDevice@@6B@; const TpmTransportSpbSPIDevice::`vftable'
0x140027f8a  mov     [rcx], rax
0x140027f8d  mov     [rcx+10h], rsi
0x140027f91  jmp     short loc_140027F95
0x140027f93  xor     ecx, ecx
0x140027f95  mov     [rsi+150h], rcx
0x140027f9c  jmp     loc_1400280D5
0x140027fa1  cmp     r14b, bl
0x140027fa4  jnz     loc_1400280D5
0x140027faa  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140027fb1  xorps   xmm0, xmm0
0x140027fb4  mov     rdx, [rsp+290h+var_238]
0x140027fb9  xorps   xmm1, xmm1
0x140027fbc  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140027fc3  xor     r8d, r8d
0x140027fc6  movups  xmmword ptr [rsp+290h+String2.Length], xmm0
0x140027fcb  movups  xmmword ptr [rbp+190h+DestinationString.Length], xmm1
0x140027fcf  movups  xmmword ptr [rbp+190h+var_1C8.Length], xmm0
0x140027fd3  mov     rax, [rax+610h]
0x140027fda  call    _guard_dispatch_icall
0x140027fdf  mov     rdx, rax; SourceString
0x140027fe2  lea     rcx, [rsp+290h+String2]; DestinationString
0x140027fe7  call    cs:__imp_RtlInitUnicodeString
0x140027fee  nop     dword ptr [rax+rax+00h]
0x140027ff3  lea     rdx, aAcpiVenNatzDev; "ACPI\\VEN_NATZ&DEV_0101"
0x140027ffa  lea     rcx, [rbp+190h+DestinationString]; DestinationString
0x140027ffe  call    cs:__imp_RtlInitUnicodeString
0x140028005  nop     dword ptr [rax+rax+00h]
0x14002800a  lea     rdx, aAcpiVenNvtnDev; "ACPI\\VEN_NVTN&DEV_0101"
0x140028011  lea     rcx, [rbp+190h+var_1C8]; DestinationString
0x140028015  call    cs:__imp_RtlInitUnicodeString
0x14002801c  nop     dword ptr [rax+rax+00h]
0x140028021  mov     r8b, bl; CaseInSensitive
0x140028024  lea     rdx, [rbp+190h+DestinationString]; String2
0x140028028  lea     rcx, [rsp+290h+String2]; String1
0x14002802d  call    cs:__imp_RtlCompareUnicodeString
0x140028034  nop     dword ptr [rax+rax+00h]
0x140028039  test    eax, eax
0x14002803b  jnz     short loc_14002806D
0x14002803d  lea     ecx, [rax+18h]; Size
0x140028040  call    ??2AllocatorBaseNonPaged@@SAPEAX_K@Z; AllocatorBaseNonPaged::operator new(unsigned __int64)
0x140028045  mov     rcx, rax
0x140028048  test    rax, rax
0x14002804b  jz      loc_140027F93
0x140028051  mov     rax, [rsp+290h+var_250]
0x140028056  mov     [rcx+8], rax
0x14002805a  lea     rax, ??_7TpmTransportSpbI2CNTZDevice@@6B@; const TpmTransportSpbI2CNTZDevice::`vftable'
0x140028061  mov     [rcx+10h], rsi
0x140028065  mov     [rcx], rax
0x140028068  jmp     loc_140027F95
0x14002806d  mov     r8b, bl; CaseInSensitive
0x140028070  lea     rdx, [rbp+190h+var_1C8]; String2
0x140028074  lea     rcx, [rsp+290h+String2]; String1
0x140028079  call    cs:__imp_RtlCompareUnicodeString
0x140028080  nop     dword ptr [rax+rax+00h]
0x140028085  test    eax, eax
0x140028087  jnz     short loc_1400280AF
0x140028089  lea     ecx, [rax+18h]; Size
0x14002808c  call    ??2AllocatorBaseNonPaged@@SAPEAX_K@Z; AllocatorBaseNonPaged::operator new(unsigned __int64)
0x140028091  mov     rcx, rax
0x140028094  test    rax, rax
0x140028097  jz      loc_140027F93
0x14002809d  mov     rax, [rsp+290h+var_250]
0x1400280a2  mov     [rcx+8], rax
0x1400280a6  lea     rax, ??_7TpmTransportSpbI2CNTCDevice@@6B@; const TpmTransportSpbI2CNTCDevice::`vftable'
0x1400280ad  jmp     short loc_140028061
0x1400280af  mov     ecx, 38h ; '8'; Size
0x1400280b4  call    ??2AllocatorBaseNonPaged@@SAPEAX_K@Z; AllocatorBaseNonPaged::operator new(unsigned __int64)
0x1400280b9  test    rax, rax
0x1400280bc  jz      short loc_1400280CE
0x1400280be  mov     rdx, [rsp+290h+var_250]; struct WDFIOTARGET__ *
0x1400280c3  mov     r8, rsi; struct TpmTransportSpb *
0x1400280c6  mov     rcx, rax; this
0x1400280c9  call    ??0TpmTransportSpbI2CDevice@@QEAA@PEAUWDFIOTARGET__@@PEAVTpmTransportSpb@@@Z; TpmTransportSpbI2CDevice::TpmTransportSpbI2CDevice(WDFIOTARGET__ *,TpmTransportSpb *)
0x1400280ce  mov     [rsi+150h], rax
0x1400280d5  mov     r14, [rsp+290h+var_248]
0x1400280da  mov     ebx, [rsp+290h+var_240]
0x1400280de  inc     ebx
0x1400280e0  jmp     loc_140027C70
0x1400280e5  mov     edi, 0C0000182h
0x1400280ea  lea     rbx, [rsi+150h]
0x1400280f1  jmp     short loc_140028139
0x1400280f3  lea     rbx, [rsi+150h]
0x1400280fa  cmp     qword ptr [rbx], 0
0x1400280fe  jnz     short loc_140028107
0x140028100  mov     edi, 0C0000182h
0x140028105  jmp     short loc_140028139
0x140028107  mov     rcx, [rbp+190h+var_1E8]; this
0x14002810b  call    ?Initialize@TpmDevice@@QEAAJXZ; TpmDevice::Initialize(void)
0x140028110  mov     edi, eax
  ... truncated ...
```
