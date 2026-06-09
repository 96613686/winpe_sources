# HUBMISC_ReportPnPFailureProblem

- ea: `0x140084e28`
- end: `0x140085151`
- name: `HUBMISC_ReportPnPFailureProblem`
- size: `809`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140009820`
- `0x140016160`

## callees

- `0x1400024b8`
- `0x14001cc5c`
- `0x140045530`
- `0x140045570`
- `0x140084e28`

## import_xrefs

- `ntoskrnl!RtlFindMessage` at `0x140084eb6`
- `ntoskrnl!RtlFindMessage` at `0x140084eb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008511c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008511c`
- `ntoskrnl!ExAllocatePool2` at `0x140084f54`
- `ntoskrnl!ExAllocatePool2` at `0x140084f54`
- `ntoskrnl!IoSetDevicePropertyData` at `0x140085035`
- `ntoskrnl!IoSetDevicePropertyData` at `0x140085035`

## string_xrefs

- `0x140084e4e`: `@System32\drivers\usbhub3.sys`

## pseudocode

```c
void __fastcall HUBMISC_ReportPnPFailureProblem(__int64 a1, ULONG a2)
{
  wchar_t *Data; // r14
  NTSTATUS Message; // eax
  unsigned int v6; // ebx
  unsigned __int64 v7; // rcx
  BYTE *Text; // rax
  unsigned __int64 v9; // rcx
  unsigned __int64 i; // rdi
  unsigned __int64 v11; // rdi
  size_t v12; // rdi
  NTSTATUS v13; // eax
  unsigned __int64 v14; // rdi
  wchar_t *v15; // rax
  int j; // ebp
  int v17; // ebp
  struct _DEVICE_OBJECT *v18; // rax
  NTSTATUS v19; // eax
  char v20; // bl
  __int64 v21; // rax
  int v22; // edx
  __int64 v23; // rax
  int v24; // edx
  PMESSAGE_RESOURCE_ENTRY *MessageResourceEntry; // [rsp+20h] [rbp-98h]
  PMESSAGE_RESOURCE_ENTRY v26; // [rsp+40h] [rbp-78h] BYREF
  _OWORD v27[2]; // [rsp+48h] [rbp-70h] BYREF
  _OWORD v28[2]; // [rsp+68h] [rbp-50h]

  v26 = 0;
  Data = 0;
  v27[0] = *(_OWORD *)L"@System32\\drivers\\usbhub3.sys";
  v27[1] = *(_OWORD *)L"2\\drivers\\usbhub3.sys";
  v28[0] = *(_OWORD *)L"s\\usbhub3.sys";
  *(_OWORD *)((char *)v28 + 12) = *(_OWORD *)L"ub3.sys";
  if ( !a2 )
  {
    LOBYTE(v6) = -27;
    goto LABEL_28;
  }
  Message = RtlFindMessage(*(PVOID *)(g_Usbhub3DriverObject + 24), 0xBu, 0, a2, &v26);
  LOBYTE(v6) = Message;
  if ( Message >= 0 )
  {
    v7 = v26->Length - 4LL;
    if ( v7 <= 0xFFFFFFFE )
    {
      Text = v26->Text;
      if ( v26 == (PMESSAGE_RESOURCE_ENTRY)-4LL )
        goto LABEL_26;
      v9 = v7 >> 1;
      if ( v9 > 0x7FFFFFFF )
        goto LABEL_26;
      for ( i = v9; v9; --v9 )
      {
        if ( !*(_WORD *)Text )
          break;
        Text += 2;
      }
      v6 = v9 == 0 ? 0xC000000D : 0;
      if ( v9 )
        v11 = i - v9;
      else
        v11 = 0;
      if ( !v9 )
        goto LABEL_28;
      v12 = 2 * v11 + 88;
      Data = (wchar_t *)ExAllocatePool2(64, v12, 1748191317);
      if ( !Data )
        goto LABEL_28;
      LODWORD(MessageResourceEntry) = a2;
      v13 = RtlStringCbPrintfW(Data, v12, L"%s,#%d;%s", v27, MessageResourceEntry, v26->Text);
      LOBYTE(v6) = v13;
      if ( v13 < 0 )
        goto LABEL_28;
      v14 = v12 >> 1;
      if ( v14 > 0x7FFFFFFF )
      {
LABEL_26:
        LOBYTE(v6) = 13;
        goto LABEL_28;
      }
      v15 = Data;
      for ( j = v14; v14; --v14 )
      {
        if ( !*v15 )
          break;
        ++v15;
      }
      v6 = v14 == 0 ? 0xC000000D : 0;
      if ( v14 )
        v17 = j - v14;
      else
        v17 = 0;
      if ( v14 )
      {
        v18 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 264))(
                                         WdfDriverGlobals,
                                         a1);
        v19 = IoSetDevicePropertyData(v18, &DEVPKEY_Device_DriverProblemDesc, 0, 0, 0x19u, 2 * v17 + 2, Data);
        v20 = v19;
        if ( v19 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v21 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                  WdfDriverGlobals,
                  WdfDriverGlobals->Driver,
                  off_14006B2C0);
          LOBYTE(v22) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(v21 + 64),
            v22,
            5,
            121,
            (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids,
            v20);
        }
LABEL_31:
        ExFreePoolWithTag(Data, 0x68334855u);
        return;
      }
    }
  }
LABEL_28:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v23 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
            WdfDriverGlobals,
            WdfDriverGlobals->Driver,
            off_14006B2C0);
    LOBYTE(v24) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(v23 + 64), v24, 5, 122, (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids, v6);
  }
  if ( Data )
    goto LABEL_31;
}

```

## disassembly

```asm
0x140084e28  mov     [rsp+arg_10], rbx
0x140084e2d  push    rbp
0x140084e2e  push    rdi
0x140084e2f  push    r12
0x140084e31  push    r14
0x140084e33  push    r15
0x140084e35  sub     rsp, 90h
0x140084e3c  mov     rax, cs:__security_cookie
0x140084e43  xor     rax, rsp
0x140084e46  mov     [rsp+0B8h+var_30], rax
0x140084e4e  movups  xmm0, xmmword ptr cs:aSystem32Driver; "@System32\\drivers\\usbhub3.sys"
0x140084e55  xor     r12d, r12d
0x140084e58  mov     ebp, edx
0x140084e5a  mov     [rsp+0B8h+var_78], r12
0x140084e5f  mov     r15, rcx
0x140084e62  mov     r14d, r12d
0x140084e65  movups  xmm1, xmmword ptr cs:aSystem32Driver+10h; "2\\drivers\\usbhub3.sys"
0x140084e6c  movups  [rsp+0B8h+var_70], xmm0
0x140084e71  movups  xmm0, xmmword ptr cs:aSystem32Driver+20h; "s\\usbhub3.sys"
0x140084e78  movups  [rsp+0B8h+var_60], xmm1
0x140084e7d  movups  xmm1, xmmword ptr cs:aSystem32Driver+2Ch; "ub3.sys"
0x140084e84  movups  xmmword ptr [rsp+0B8h+var_50], xmm0
0x140084e89  movups  xmmword ptr [rsp+0B8h+var_50+0Ch], xmm1
0x140084e8e  test    edx, edx
0x140084e90  jz      loc_1400850B1
0x140084e96  mov     rcx, cs:g_Usbhub3DriverObject
0x140084e9d  lea     rax, [rsp+0B8h+var_78]
0x140084ea2  mov     r9d, edx; MessageId
0x140084ea5  mov     [rsp+0B8h+MessageResourceEntry], rax; MessageResourceEntry
0x140084eaa  xor     r8d, r8d; Language
0x140084ead  lea     edx, [r12+0Bh]; Type
0x140084eb2  mov     rcx, [rcx+18h]; BaseAddress
0x140084eb6  call    cs:__imp_RtlFindMessage
0x140084ebd  nop     dword ptr [rax+rax+00h]
0x140084ec2  mov     ebx, eax
0x140084ec4  test    eax, eax
0x140084ec6  js      loc_1400850B6
0x140084ecc  mov     rax, [rsp+0B8h+var_78]
0x140084ed1  mov     edx, 0FFFFFFFEh
0x140084ed6  movzx   ecx, word ptr [rax]
0x140084ed9  add     rcx, 0FFFFFFFFFFFFFFFCh
0x140084edd  cmp     rcx, rdx
0x140084ee0  ja      loc_1400850B6
0x140084ee6  add     rax, 4
0x140084eea  jz      loc_1400850AA
0x140084ef0  shr     rcx, 1
0x140084ef3  cmp     rcx, 7FFFFFFFh
0x140084efa  ja      loc_1400850AA
0x140084f00  mov     rdi, rcx
0x140084f03  test    rcx, rcx
0x140084f06  jz      short loc_140084F18
0x140084f08  cmp     [rax], r12w
0x140084f0c  jz      short loc_140084F18
0x140084f0e  add     rax, 2
0x140084f12  sub     rcx, 1
0x140084f16  jnz     short loc_140084F08
0x140084f18  mov     rax, rcx
0x140084f1b  neg     rax
0x140084f1e  sbb     ebx, ebx
0x140084f20  not     ebx
0x140084f22  and     ebx, 0C000000Dh
0x140084f28  test    rcx, rcx
0x140084f2b  jz      short loc_140084F32
0x140084f2d  sub     rdi, rcx
0x140084f30  jmp     short loc_140084F35
0x140084f32  mov     rdi, r12
0x140084f35  test    rcx, rcx
0x140084f38  jz      loc_1400850B6
0x140084f3e  lea     rdi, ds:58h[rdi*2]
0x140084f46  mov     r8d, 68334855h
0x140084f4c  mov     rdx, rdi
0x140084f4f  mov     ecx, 40h ; '@'
0x140084f54  call    cs:__imp_ExAllocatePool2
0x140084f5b  nop     dword ptr [rax+rax+00h]
0x140084f60  mov     r14, rax
0x140084f63  test    rax, rax
0x140084f66  jz      loc_1400850B6
0x140084f6c  mov     rax, [rsp+0B8h+var_78]
0x140084f71  lea     r9, [rsp+0B8h+var_70]
0x140084f76  add     rax, 4
0x140084f7a  lea     r8, aSDS; "%s,#%d;%s"
0x140084f81  mov     qword ptr [rsp+0B8h+Size], rax
0x140084f86  mov     rdx, rdi; cbDest
0x140084f89  mov     rcx, r14; pszDest
0x140084f8c  mov     dword ptr [rsp+0B8h+MessageResourceEntry], ebp
0x140084f90  call    RtlStringCbPrintfW
0x140084f95  mov     ebx, eax
0x140084f97  test    eax, eax
0x140084f99  js      loc_1400850B6
0x140084f9f  shr     rdi, 1
0x140084fa2  cmp     rdi, 7FFFFFFFh
0x140084fa9  ja      loc_1400850AA
0x140084faf  mov     rax, r14
0x140084fb2  mov     rbp, rdi
0x140084fb5  test    rdi, rdi
0x140084fb8  jz      short loc_140084FCA
0x140084fba  cmp     [rax], r12w
0x140084fbe  jz      short loc_140084FCA
0x140084fc0  add     rax, 2
0x140084fc4  sub     rdi, 1
0x140084fc8  jnz     short loc_140084FBA
0x140084fca  mov     rax, rdi
0x140084fcd  neg     rax
0x140084fd0  sbb     ebx, ebx
0x140084fd2  not     ebx
0x140084fd4  and     ebx, 0C000000Dh
0x140084fda  test    rdi, rdi
0x140084fdd  jz      short loc_140084FE4
0x140084fdf  sub     rbp, rdi
0x140084fe2  jmp     short loc_140084FE7
0x140084fe4  mov     rbp, r12
0x140084fe7  test    rdi, rdi
0x140084fea  jz      loc_1400850B6
0x140084ff0  mov     rax, cs:WdfFunctions_01015
0x140084ff7  mov     rdx, r15
0x140084ffa  mov     rcx, cs:WdfDriverGlobals
0x140085001  mov     rax, [rax+108h]
0x140085008  call    _guard_dispatch_icall
0x14008500d  lea     ecx, ds:2[rbp*2]
0x140085014  mov     [rsp+0B8h+Data], r14; Data
0x140085019  mov     [rsp+0B8h+Size], ecx; Size
0x14008501d  lea     rdx, DEVPKEY_Device_DriverProblemDesc; PropertyKey
0x140085024  mov     rcx, rax; Pdo
0x140085027  mov     dword ptr [rsp+0B8h+MessageResourceEntry], 19h; Type
0x14008502f  xor     r9d, r9d; Flags
0x140085032  xor     r8d, r8d; Lcid
0x140085035  call    cs:__imp_IoSetDevicePropertyData
0x14008503c  nop     dword ptr [rax+rax+00h]
0x140085041  mov     ebx, eax
0x140085043  test    eax, eax
0x140085045  jns     loc_140085114
0x14008504b  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140085052  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140085059  jz      loc_140085114
0x14008505f  mov     rcx, cs:WdfFunctions_01015
0x140085066  mov     r8, cs:off_14006B2C0
0x14008506d  mov     rax, [rcx+650h]
0x140085074  mov     rcx, cs:WdfDriverGlobals
0x14008507b  mov     rdx, [rcx]
0x14008507e  call    _guard_dispatch_icall
0x140085083  mov     r9d, 79h ; 'y'
0x140085089  mov     [rsp+0B8h+Size], ebx
0x14008508d  lea     rcx, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x140085094  mov     dl, 2
0x140085096  mov     [rsp+0B8h+MessageResourceEntry], rcx
0x14008509b  mov     rcx, [rax+40h]
0x14008509f  lea     r8d, [r9-74h]
0x1400850a3  call    WPP_RECORDER_SF_d
0x1400850a8  jmp     short loc_140085114
0x1400850aa  mov     ebx, 0C000000Dh
0x1400850af  jmp     short loc_1400850B6
0x1400850b1  mov     ebx, 0C00000E5h
0x1400850b6  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400850bd  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400850c4  jz      short loc_14008510F
0x1400850c6  mov     rax, cs:WdfFunctions_01015
0x1400850cd  mov     rcx, cs:WdfDriverGlobals
0x1400850d4  mov     r8, cs:off_14006B2C0
0x1400850db  mov     rax, [rax+650h]
0x1400850e2  mov     rdx, [rcx]
0x1400850e5  call    _guard_dispatch_icall
0x1400850ea  mov     r9d, 7Ah ; 'z'
0x1400850f0  mov     [rsp+0B8h+Size], ebx
0x1400850f4  lea     rcx, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x1400850fb  mov     dl, 2
0x1400850fd  mov     [rsp+0B8h+MessageResourceEntry], rcx
0x140085102  mov     rcx, [rax+40h]
0x140085106  lea     r8d, [r9-75h]
0x14008510a  call    WPP_RECORDER_SF_d
0x14008510f  test    r14, r14
0x140085112  jz      short loc_140085128
0x140085114  mov     edx, 68334855h; Tag
0x140085119  mov     rcx, r14; P
0x14008511c  call    cs:__imp_ExFreePoolWithTag
0x140085123  nop     dword ptr [rax+rax+00h]
0x140085128  mov     rcx, [rsp+0B8h+var_30]
0x140085130  xor     rcx, rsp; StackCookie
0x140085133  call    __security_check_cookie
0x140085138  mov     rbx, [rsp+0B8h+arg_10]
0x140085140  add     rsp, 90h
0x140085147  pop     r15
0x140085149  pop     r14
0x14008514b  pop     r12
0x14008514d  pop     rdi
0x14008514e  pop     rbp
0x14008514f  retn
```
