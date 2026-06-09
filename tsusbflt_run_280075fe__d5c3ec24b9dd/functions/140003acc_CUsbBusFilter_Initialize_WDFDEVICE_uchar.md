# CUsbBusFilter::Initialize(WDFDEVICE__ *,uchar)

- ea: `0x140003acc`
- end: `0x140003f87`
- name: `?Initialize@CUsbBusFilter@@AEAAJPEAUWDFDEVICE__@@E@Z`
- size: `1211`
- prototype: `__int64 __fastcall(CUsbBusFilter *__hidden this, struct WDFDEVICE__ *, unsigned __int8)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400029e4`

## callees

- `0x140003acc`
- `0x1400048d4`
- `0x140004edc`
- `0x140004f18`
- `0x140004f48`
- `0x140005000`
- `0x14000a9f0`
- `0x14000aa30`
- `0x14000ab00`

## import_xrefs

- `ntoskrnl!RtlVerifyVersionInfo` at `0x140003c5d`
- `ntoskrnl!RtlVerifyVersionInfo` at `0x140003c5d`
- `ntoskrnl!VerSetConditionMask` at `0x140003c47`
- `ntoskrnl!VerSetConditionMask` at `0x140003c47`

## string_xrefs

- `0x140003e36`: `\REGISTRY\MACHINE\System\CurrentControlSet\Services\usbhub\hubg`

## pseudocode

```c
__int64 __fastcall CUsbBusFilter::Initialize(CUsbBusFilter *this, struct WDFDEVICE__ *a2, char a3)
{
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  ULONGLONG v10; // rax
  char v11; // al
  unsigned int v12; // ebx
  PDEVICE_OBJECT v13; // rcx
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v16[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v17; // [rsp+58h] [rbp-A8h]
  __int64 *v18; // [rsp+68h] [rbp-98h]
  __int64 v19; // [rsp+70h] [rbp-90h] BYREF
  __int128 v20; // [rsp+78h] [rbp-88h] BYREF
  __int64 v21; // [rsp+88h] [rbp-78h]
  __int64 v22; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v23[12]; // [rsp+A0h] [rbp-60h] BYREF
  _OSVERSIONINFOEXW VersionInfo; // [rsp+100h] [rbp+0h] BYREF

  memset(v23, 0, sizeof(v23));
  v22 = 0;
  memset(&VersionInfo, 0, sizeof(VersionInfo));
  *(_QWORD *)this = a2;
  *((_BYTE *)this + 41) = a3;
  v18 = 0;
  v21 = 0;
  v19 = 0;
  v15 = 0;
  memset(v16, 0, sizeof(v16));
  v17 = 0;
  v20 = 0;
  *((_QWORD *)this + 1) = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[21].Flink)(
                            WPP_MAIN_CB.Queue.ListEntry.Blink,
                            a2);
  memset(v23, 0, sizeof(v23));
  v23[0] = 0x200000060LL;
  v23[5] = &FdEvtIoDeviceControl;
  BYTE5(v23[1]) = 1;
  v23[6] = &FdEvtIoInternalDeviceControl;
  LODWORD(v23[1]) = 2;
  LODWORD(v23[10]) = -1;
  v6 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *, _QWORD *, _QWORD, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[76].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         v23,
         0,
         &v22);
  v7 = v6;
  if ( v6 >= 0 )
  {
    memset(&VersionInfo.dwMinorVersion, 0, 0x114u);
    VersionInfo.dwOSVersionInfoSize = 284;
    VersionInfo.dwMajorVersion = 6;
    v10 = VerSetConditionMask(0, 2u, 3u);
    v6 = RtlVerifyVersionInfo(&VersionInfo, 2u, v10);
    v7 = v6;
    if ( v6 )
    {
      if ( v6 != -1073741735 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v9 = 13;
          goto LABEL_43;
        }
        return v7;
      }
      v11 = 0;
    }
    else
    {
      v11 = 1;
    }
    *((_BYTE *)this + 40) = v11;
    v6 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFDEVICE__ *, GUID *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[38].Blink)(
           WPP_MAIN_CB.Queue.ListEntry.Blink,
           a2,
           &GUID_DEVINTERFACE_TSUSBBUS_FILTER,
           0);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v18 = off_14000F0E0;
      *(_QWORD *)((char *)&v16[1] + 4) = 0x100000000LL;
      v21 = 0;
      *((_QWORD *)&v20 + 1) = FdQueryBusRelationsCompletionWorkItemCallback;
      *(_OWORD *)((char *)v16 + 4) = 0;
      LODWORD(v16[0]) = 56;
      v17 = (unsigned __int64)a2;
      HIDWORD(v16[1]) = 4;
      *(_QWORD *)&v20 = 24;
      v6 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int128 *, _OWORD *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[189].Blink)(
             WPP_MAIN_CB.Queue.ListEntry.Blink,
             &v20,
             v16,
             &v19);
      v7 = v6;
      if ( v6 >= 0 )
      {
        *((_QWORD *)this + 2) = v19;
        v18 = 0;
        *((_QWORD *)&v16[1] + 1) = 0x100000001LL;
        memset(v16, 0, 24);
        LODWORD(v16[0]) = 56;
        v17 = (unsigned __int64)a2;
        v6 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, _OWORD *, char *))WPP_MAIN_CB.Queue.ListEntry.Flink[6].Blink)(
               WPP_MAIN_CB.Queue.ListEntry.Blink,
               v16,
               (char *)this + 24);
        v7 = v6;
        if ( v6 >= 0 )
        {
          v6 = CUsbBusFilter::QueryRegistryData(
                 L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Services\\usbhub\\hubg",
                 L"EnableDiagnosticMode",
                 &v15);
          v7 = v6;
          if ( v6 >= 0 )
          {
            v12 = v15;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_SD(
                WPP_GLOBAL_Control->AttachedDevice,
                18,
                (unsigned int)WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids,
                (unsigned int)L"EnableDiagnosticMode",
                v15);
            if ( v12 )
            {
              if ( (v12 & 0x7FFFFFFF) != 0 )
              {
                *((_BYTE *)this + 60) = 1;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids);
              }
              return 0;
            }
            else
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids);
              if ( (Microsoft_Windows_TerminalServices_ClientUSBDevicesEnableBits & 0x10) != 0 )
                McTemplateK0_EtwWriteTransfer(v13, EVENT_USB_DIAGNOSTIC_MODE_NOT_SET);
              return (unsigned int)-1073741637;
            }
          }
          else
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v9 = 17;
              goto LABEL_43;
            }
          }
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v9 = 16;
            goto LABEL_43;
          }
        }
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v9 = 15;
          goto LABEL_43;
        }
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v9 = 14;
        goto LABEL_43;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v9 = 12;
LABEL_43:
      WPP_SF_d(v8->AttachedDevice, v9, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids, (unsigned int)v6);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140003acc  mov     [rsp-8+arg_10], rbx
0x140003ad1  mov     [rsp-8+arg_18], rsi
0x140003ad6  push    rbp
0x140003ad7  push    rdi
0x140003ad8  push    r14
0x140003ada  lea     rbp, [rsp-130h]
0x140003ae2  sub     rsp, 230h
0x140003ae9  mov     rax, cs:__security_cookie
0x140003af0  xor     rax, rsp
0x140003af3  mov     [rbp+140h+var_20], rax
0x140003afa  mov     bl, r8b
0x140003afd  mov     rdi, rdx
0x140003b00  mov     rsi, rcx
0x140003b03  mov     r14d, 60h ; '`'
0x140003b09  mov     r8d, r14d; Size
0x140003b0c  lea     rcx, [rbp+140h+var_1A0]; void *
0x140003b10  xor     edx, edx; Val
0x140003b12  call    memset
0x140003b17  xor     edx, edx; Val
0x140003b19  mov     [rbp+140h+var_1B0], 0
0x140003b21  mov     r8d, 11Ch; Size
0x140003b27  lea     rcx, [rbp+140h+VersionInfo]; void *
0x140003b2b  call    memset
0x140003b30  xor     eax, eax
0x140003b32  mov     [rsi], rdi
0x140003b35  xorps   xmm0, xmm0
0x140003b38  mov     [rsi+29h], bl
0x140003b3b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003b42  mov     rdx, rdi
0x140003b45  mov     [rsp+240h+var_1D8], rax
0x140003b4a  mov     [rbp+140h+var_1B8], rax
0x140003b4e  mov     [rsp+240h+var_1D0], rax
0x140003b53  mov     [rsp+240h+var_210], eax
0x140003b57  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003b5e  movups  [rsp+240h+var_208], xmm0
0x140003b63  movups  [rsp+240h+var_1F8], xmm0
0x140003b68  movups  [rsp+240h+var_1E8], xmm0
0x140003b6d  movups  [rsp+240h+var_1C8], xmm0
0x140003b72  mov     rax, [rax+150h]
0x140003b79  call    _guard_dispatch_icall
0x140003b7e  mov     r8d, r14d; Size
0x140003b81  mov     [rsi+8], rax
0x140003b85  xor     edx, edx; Val
0x140003b87  lea     rcx, [rbp+140h+var_1A0]; void *
0x140003b8b  call    memset
0x140003b90  mov     [rbp+140h+var_1A0], r14d
0x140003b94  lea     rax, FdEvtIoDeviceControl
0x140003b9b  mov     [rbp+140h+var_178], rax
0x140003b9f  lea     rcx, [rbp+140h+var_1B0]
0x140003ba3  lea     rax, FdEvtIoInternalDeviceControl
0x140003baa  mov     [rbp+140h+var_193], 1
0x140003bae  mov     [rbp+140h+var_170], rax
0x140003bb2  lea     r8, [rbp+140h+var_1A0]
0x140003bb6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003bbd  mov     r14d, 2
0x140003bc3  mov     [rbp+140h+var_198], r14d
0x140003bc7  xor     r9d, r9d
0x140003bca  mov     [rbp+140h+var_19C], r14d
0x140003bce  mov     rdx, rdi
0x140003bd1  mov     [rbp+140h+var_150], 0FFFFFFFFh
0x140003bd8  mov     rax, [rax+4C0h]
0x140003bdf  mov     [rsp+240h+var_220], rcx
0x140003be4  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003beb  call    _guard_dispatch_icall
0x140003bf0  mov     ebx, eax
0x140003bf2  test    eax, eax
0x140003bf4  jns     short loc_140003C20
0x140003bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x140003bfd  lea     rdi, WPP_GLOBAL_Control
0x140003c04  cmp     rcx, rdi
0x140003c07  jz      loc_140003F5D
0x140003c0d  cmp     [rcx+29h], r14b
0x140003c11  jb      loc_140003F5D
0x140003c17  lea     edx, [r14+0Ah]
0x140003c1b  jmp     loc_140003F4A
0x140003c20  xor     edx, edx; Val
0x140003c22  lea     rcx, [rbp+140h+VersionInfo.dwMinorVersion]; void *
0x140003c26  mov     r8d, 114h; Size
0x140003c2c  call    memset
0x140003c31  mov     r8b, 3; Condition
0x140003c34  mov     [rbp+140h+VersionInfo.dwOSVersionInfoSize], 11Ch
0x140003c3b  mov     edx, r14d; TypeMask
0x140003c3e  mov     [rbp+140h+VersionInfo.dwMajorVersion], 6
0x140003c45  xor     ecx, ecx; ConditionMask
0x140003c47  call    cs:__imp_VerSetConditionMask
0x140003c4e  nop     dword ptr [rax+rax+00h]
0x140003c53  mov     edx, r14d; TypeMask
0x140003c56  lea     rcx, [rbp+140h+VersionInfo]; VersionInfo
0x140003c5a  mov     r8, rax; ConditionMask
0x140003c5d  call    cs:__imp_RtlVerifyVersionInfo
0x140003c64  nop     dword ptr [rax+rax+00h]
0x140003c69  mov     ebx, eax
0x140003c6b  test    eax, eax
0x140003c6d  jnz     short loc_140003C73
0x140003c6f  mov     al, 1
0x140003c71  jmp     short loc_140003C80
0x140003c73  cmp     eax, 0C0000059h
0x140003c78  jnz     loc_140003F2C
0x140003c7e  xor     al, al
0x140003c80  mov     [rsi+28h], al
0x140003c83  lea     r8, GUID_DEVINTERFACE_TSUSBBUS_FILTER
0x140003c8a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003c91  xor     r9d, r9d
0x140003c94  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003c9b  mov     rdx, rdi
0x140003c9e  mov     rax, [rax+268h]
0x140003ca5  call    _guard_dispatch_icall
0x140003caa  mov     ebx, eax
0x140003cac  test    eax, eax
0x140003cae  jns     short loc_140003CDB
0x140003cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140003cb7  lea     rdi, WPP_GLOBAL_Control
0x140003cbe  cmp     rcx, rdi
0x140003cc1  jz      loc_140003F5D
0x140003cc7  cmp     [rcx+29h], r14b
0x140003ccb  jb      loc_140003F5D
0x140003cd1  mov     edx, 0Eh
0x140003cd6  jmp     loc_140003F4A
0x140003cdb  mov     rax, cs:off_14000F0E0
0x140003ce2  lea     r9, [rsp+240h+var_1D0]
0x140003ce7  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003cee  lea     r8, [rsp+240h+var_208]
0x140003cf3  mov     [rsp+240h+var_1D8], rax
0x140003cf8  lea     rdx, [rsp+240h+var_1C8]
0x140003cfd  xor     eax, eax
0x140003cff  mov     dword ptr [rsp+240h+var_1F8+4], 0
0x140003d07  mov     [rbp+140h+var_1B8], rax
0x140003d0b  xorps   xmm0, xmm0
0x140003d0e  movups  [rsp+240h+var_1C8], xmm0
0x140003d13  lea     rax, FdQueryBusRelationsCompletionWorkItemCallback
0x140003d1a  mov     qword ptr [rsp+240h+var_1E8+8], 0
0x140003d23  mov     qword ptr [rbp+140h+var_1C8+8], rax
0x140003d27  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003d2e  movdqu  [rsp+240h+var_208+4], xmm0
0x140003d34  mov     dword ptr [rsp+240h+var_208], 38h ; '8'
0x140003d3c  mov     dword ptr [rsp+240h+var_1F8+8], 1
0x140003d44  mov     qword ptr [rsp+240h+var_1E8], rdi
0x140003d49  mov     dword ptr [rsp+240h+var_1F8+0Ch], 4
0x140003d51  mov     dword ptr [rsp+240h+var_1C8], 18h
0x140003d59  mov     byte ptr [rbp+140h+var_1B8], 0
0x140003d5d  mov     rax, [rax+0BD8h]
0x140003d64  call    _guard_dispatch_icall
0x140003d69  mov     ebx, eax
0x140003d6b  test    eax, eax
0x140003d6d  jns     short loc_140003D9A
0x140003d6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d76  lea     rdi, WPP_GLOBAL_Control
0x140003d7d  cmp     rcx, rdi
0x140003d80  jz      loc_140003F5D
0x140003d86  cmp     [rcx+29h], r14b
0x140003d8a  jb      loc_140003F5D
0x140003d90  mov     edx, 0Fh
0x140003d95  jmp     loc_140003F4A
0x140003d9a  mov     rax, [rsp+240h+var_1D0]
0x140003d9f  lea     r8, [rsi+18h]
0x140003da3  mov     [rsi+10h], rax
0x140003da7  lea     rdx, [rsp+240h+var_208]
0x140003dac  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140003db3  xor     eax, eax
0x140003db5  xorps   xmm0, xmm0
0x140003db8  mov     [rsp+240h+var_1D8], rax
0x140003dbd  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140003dc4  movups  [rsp+240h+var_1F8], xmm0
0x140003dc9  mov     dword ptr [rsp+240h+var_1F8+8], 1
0x140003dd1  movups  [rsp+240h+var_208], xmm0
0x140003dd6  mov     dword ptr [rsp+240h+var_208], 38h ; '8'
0x140003dde  movups  [rsp+240h+var_1E8], xmm0
0x140003de3  mov     dword ptr [rsp+240h+var_1F8+0Ch], 1
0x140003deb  mov     qword ptr [rsp+240h+var_1E8], rdi
0x140003df0  mov     rax, [rax+68h]
0x140003df4  call    _guard_dispatch_icall
0x140003df9  mov     ebx, eax
0x140003dfb  test    eax, eax
0x140003dfd  jns     short loc_140003E2A
0x140003dff  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e06  lea     rdi, WPP_GLOBAL_Control
0x140003e0d  cmp     rcx, rdi
0x140003e10  jz      loc_140003F5D
0x140003e16  cmp     [rcx+29h], r14b
0x140003e1a  jb      loc_140003F5D
0x140003e20  mov     edx, 10h
0x140003e25  jmp     loc_140003F4A
0x140003e2a  lea     r8, [rsp+240h+var_210]; unsigned int *
0x140003e2f  lea     rdx, aEnablediagnost; "EnableDiagnosticMode"
0x140003e36  lea     rcx, aRegistryMachin_1; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x140003e3d  call    ?QueryRegistryData@CUsbBusFilter@@SAJPEBG0PEAK@Z; CUsbBusFilter::QueryRegistryData(ushort const *,ushort const *,ulong *)
0x140003e42  mov     ebx, eax
0x140003e44  test    eax, eax
0x140003e46  jns     short loc_140003E73
0x140003e48  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e4f  lea     rdi, WPP_GLOBAL_Control
0x140003e56  cmp     rcx, rdi
0x140003e59  jz      loc_140003F5D
0x140003e5f  cmp     [rcx+29h], r14b
0x140003e63  jb      loc_140003F5D
0x140003e69  mov     edx, 11h
0x140003e6e  jmp     loc_140003F4A
0x140003e73  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e7a  lea     rdi, WPP_GLOBAL_Control
0x140003e81  mov     ebx, [rsp+240h+var_210]
0x140003e85  cmp     rcx, rdi
0x140003e88  jz      short loc_140003EB0
0x140003e8a  cmp     byte ptr [rcx+29h], 5
0x140003e8e  jb      short loc_140003EB0
0x140003e90  mov     rcx, [rcx+18h]
0x140003e94  lea     r9, aEnablediagnost; "EnableDiagnosticMode"
0x140003e9b  mov     edx, 12h
0x140003ea0  mov     dword ptr [rsp+240h+var_220], ebx
0x140003ea4  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140003eab  call    WPP_SF_SD
0x140003eb0  test    ebx, ebx
0x140003eb2  jnz     short loc_140003EF5
0x140003eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ebb  cmp     rcx, rdi
0x140003ebe  jz      short loc_140003ED9
0x140003ec0  cmp     [rcx+29h], r14b
0x140003ec4  jb      short loc_140003ED9
0x140003ec6  mov     rcx, [rcx+18h]
0x140003eca  lea     edx, [rbx+13h]
0x140003ecd  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140003ed4  call    WPP_SF_
0x140003ed9  test    cs:Microsoft_Windows_TerminalServices_ClientUSBDevicesEnableBits, 10h
0x140003ee0  jz      short loc_140003EEE
0x140003ee2  lea     rdx, EVENT_USB_DIAGNOSTIC_MODE_NOT_SET
0x140003ee9  call    McTemplateK0_EtwWriteTransfer
0x140003eee  mov     ebx, 0C00000BBh
0x140003ef3  jmp     short loc_140003F5D
0x140003ef5  test    ebx, 7FFFFFFFh
0x140003efb  jz      short loc_140003F28
0x140003efd  mov     byte ptr [rsi+3Ch], 1
0x140003f01  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f08  cmp     rcx, rdi
0x140003f0b  jz      short loc_140003F28
0x140003f0d  cmp     byte ptr [rcx+29h], 5
0x140003f11  jb      short loc_140003F28
0x140003f13  mov     rcx, [rcx+18h]
0x140003f17  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140003f1e  mov     edx, 14h
0x140003f23  call    WPP_SF_
0x140003f28  xor     ebx, ebx
0x140003f2a  jmp     short loc_140003F5D
0x140003f2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f33  lea     rdi, WPP_GLOBAL_Control
0x140003f3a  cmp     rcx, rdi
0x140003f3d  jz      short loc_140003F5D
0x140003f3f  cmp     [rcx+29h], r14b
0x140003f43  jb      short loc_140003F5D
0x140003f45  mov     edx, 0Dh
0x140003f4a  mov     rcx, [rcx+18h]
0x140003f4e  lea     r8, WPP_b486fa217bde37cd2eb5d2f2271ffb01_Traceguids
0x140003f55  mov     r9d, eax
0x140003f58  call    WPP_SF_d
0x140003f5d  mov     eax, ebx
0x140003f5f  mov     rcx, [rbp+140h+var_20]
0x140003f66  xor     rcx, rsp; StackCookie
0x140003f69  call    __security_check_cookie
0x140003f6e  lea     r11, [rsp+240h+var_10]
0x140003f76  mov     rbx, [r11+30h]
0x140003f7a  mov     rsi, [r11+38h]
0x140003f7e  mov     rsp, r11
0x140003f81  pop     r14
0x140003f83  pop     rdi
0x140003f84  pop     rbp
0x140003f85  retn
```
