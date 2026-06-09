# TpmTransportTis::TpmEvtDevicePrepareHardware(WDFDEVICE__ *,WDFCMRESLIST__ *,WDFCMRESLIST__ *)

- ea: `0x140018a30`
- end: `0x140018fc2`
- name: `?TpmEvtDevicePrepareHardware@TpmTransportTis@@UEAAJPEAUWDFDEVICE__@@PEAUWDFCMRESLIST__@@1@Z`
- size: `1426`
- prototype: `__int64 __fastcall(TpmTransportTis *__hidden this, struct WDFDEVICE__ *, struct WDFCMRESLIST__ *, struct WDFCMRESLIST__ *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config`

## callees

- `0x140001620`
- `0x1400052b0`
- `0x1400078b8`
- `0x140009278`
- `0x140009fc8`
- `0x14000b6c8`
- `0x14000ff70`
- `0x140014a34`
- `0x140018a30`
- `0x1400193c8`
- `0x14001cfdc`
- `0x140022a90`
- `0x140024fd4`
- `0x140025090`
- `0x140029560`
- `0x140039780`
- `0x140039b40`

## import_xrefs

- `ntoskrnl!MmMapIoSpaceEx` at `0x140018bb4`
- `ntoskrnl!MmMapIoSpaceEx` at `0x140018bb4`

## string_xrefs

- `0x140018c99`: `TPMDriverReadAfterWriteCount`
- `0x140018cd7`: `TPMDriverReadAfterWriteConfig`
- `0x140018d1d`: `TPMDriverReadAfterWriteConfig`

## pseudocode

```c
__int64 __fastcall TpmTransportTis::TpmEvtDevicePrepareHardware(
        TpmTransportTis *this,
        struct WDFDEVICE__ *a2,
        struct WDFCMRESLIST__ *a3,
        struct WDFCMRESLIST__ *a4)
{
  __int64 v6; // rsi
  struct WDFCMRESLIST__ *v7; // rbx
  __int64 v8; // r13
  unsigned __int64 v9; // r12
  __int64 v10; // r14
  unsigned int i; // r15d
  __int64 v12; // rax
  int v13; // r8d
  _DWORD *v14; // rbx
  int v15; // ecx
  __int64 (__fastcall *v16)(PKDPC, struct WDFCMRESLIST__ *, _QWORD); // rax
  __int64 v17; // rax
  int Value; // ebx
  int DeviceRoutine; // eax
  int v20; // esi
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // esi
  __int64 v24; // rdx
  _DWORD *v25; // rsi
  int v27; // [rsp+30h] [rbp-B1h]
  int v28; // [rsp+58h] [rbp-89h] BYREF
  int v29; // [rsp+60h] [rbp-81h]
  _DWORD *v30; // [rsp+68h] [rbp-79h]
  TpmDevice *v31; // [rsp+70h] [rbp-71h]
  __int128 v32; // [rsp+78h] [rbp-69h] BYREF
  int v33; // [rsp+88h] [rbp-59h]
  _QWORD v34[20]; // [rsp+98h] [rbp-49h] BYREF

  v33 = 0;
  v6 = 0;
  v30 = 0;
  v7 = a4;
  v8 = 0;
  v32 = 0;
  memset(v34, 0, 0x68u);
  v9 = 0;
  v10 = 0;
  v29 = 0;
  v31 = (TpmDevice *)(*((__int64 (__fastcall **)(PKDPC, struct WDFDEVICE__ *, void *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                      + 202))(
                       WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                       a2,
                       off_140047040);
  for ( i = 0;
        i < (*((unsigned int (__fastcall **)(PKDPC, struct WDFCMRESLIST__ *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 304))(
              WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
              v7);
        ++i )
  {
    v12 = (*((__int64 (__fastcall **)(PKDPC, struct WDFCMRESLIST__ *, _QWORD))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 305))(
            WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
            v7,
            i);
    v14 = (_DWORD *)v12;
    if ( !v12 )
      return (unsigned int)-1073741438;
    if ( *(_BYTE *)v12 == 1 )
    {
      v17 = *(_QWORD *)(v12 + 4);
      if ( v17 )
        v6 = v17;
    }
    else if ( *(_BYTE *)v12 == 2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids);
      v29 = 1;
      v16 = (__int64 (__fastcall *)(PKDPC, struct WDFCMRESLIST__ *, _QWORD))*((_QWORD *)WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                                                                            + 305);
      v30 = v14;
      v8 = v16(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc, a3, i);
    }
    else if ( *(_BYTE *)v12 == 3 && *(_DWORD *)(v12 + 12) >= 0x400u )
    {
      if ( *(_DWORD *)(v12 + 8) || *(_DWORD *)(v12 + 4) != -19660800 )
      {
        v15 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids);
        if ( (TPMEnableBits & 2) != 0 )
          McTemplateK0dqqq_EtwWriteTransfer(v15, (unsigned int)TPM_NON_STD_BASE_REG, v13, 44, 205, v14[2], v14[1]);
      }
      v10 = MmMapIoSpaceEx(*(_QWORD *)(v14 + 1), (unsigned int)v14[3], 516);
      if ( !v10 )
        return (unsigned int)-1073741670;
      v9 = (unsigned int)v14[3];
    }
    v7 = a4;
  }
  if ( v10 )
  {
    *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = v10;
    LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) = 1;
    WPP_MAIN_CB.Queue.Wcb.DeviceContext = (PVOID)v9;
    if ( (unsigned int)Feature_TPMDriverMemoryTISWriteFix__private_IsEnabledDeviceUsageNoInline() )
    {
      Value = TpmRegistry::QueryValue(
                24,
                L"TPMDriverReadAfterWriteCount",
                4,
                &WPP_MAIN_CB.Queue.Wcb.DeviceRoutine,
                4,
                0);
      if ( Value == -1073741772 || (DeviceRoutine = (int)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) == 0 )
      {
        v28 = 0;
        Value = TpmRegistry::AssignValue(1, L"TPMDriverReadAfterWriteConfig", 4, &v28, 4);
        if ( Value < 0 )
          return (unsigned int)Value;
        DeviceRoutine = 0;
        *(_QWORD *)((char *)&WPP_MAIN_CB.Queue.Wcb.1 + 20) = 0;
      }
      else if ( Value < 0 )
      {
        return (unsigned int)Value;
      }
      if ( DeviceRoutine && !*((_DWORD *)&WPP_MAIN_CB.Queue.Wcb.1 + 5) )
      {
        v28 = 1;
        Value = TpmRegistry::AssignValue(1, L"TPMDriverReadAfterWriteConfig", 4, &v28, 4);
        if ( Value < 0 )
          return (unsigned int)Value;
        *((_DWORD *)&WPP_MAIN_CB.Queue.Wcb.1 + 5) = 1;
      }
    }
  }
  else
  {
    if ( !v6 )
      return (unsigned int)-1073741438;
    LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) = 0;
    *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = v6;
    WPP_MAIN_CB.Queue.Wcb.DeviceContext = 0;
  }
  Value = TpmDevice::Initialize(v31);
  if ( Value < 0 )
    return (unsigned int)Value;
  v20 = v29;
  *((_DWORD *)this + 76) = v29 != 0;
  *((_DWORD *)this + 76) = *((_DWORD *)this + 76) & 0xFFFFFFFD
                         | ((unsigned int)TpmTransportType::IsInterruptSupportEnabled() != 0 ? 2 : 0);
  if ( v20 && (unsigned int)TpmTransportType::IsInterruptSupportEnabled() )
  {
    if ( (TpmRegister<unsigned char>::Read((char *)this + 320) & 0x20) == 0 )
    {
      LOBYTE(v22) = 2;
      TpmRegister<unsigned char>::Write((char *)this + 320, v21, v22);
      Value = TpmTransportTis::WaitForBitSet<unsigned char>(this, 32, v27, TpmTransport::m_DefaultTimeouts, 0, 0, 1);
      if ( Value < 0 )
        return (unsigned int)Value;
    }
    if ( v8 )
    {
      v23 = *(_DWORD *)(v8 + 8);
      if ( v23 - 1 <= 0xE )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids, v23);
        LOBYTE(v22) = v23;
        TpmRegister<unsigned char>::Write((char *)this + 348, v21, v22);
      }
    }
    if ( (unsigned int)TpmTransportTis::SetIntRegisterEnable(this, 0) )
    {
      v25 = v30;
      if ( v30 )
      {
        if ( v8 )
        {
          TpmTransportTis::ClearIntRegDataAvail(this);
          memset(v34, 0, 0x68u);
          v34[3] = TpmInterruptIsr;
          LODWORD(v34[0]) = 104;
          v34[4] = TpmInterruptDpc;
          LODWORD(v34[2]) = 2;
          v34[5] = TpmInterruptEnable;
          HIDWORD(v34[11]) = 2;
          v34[6] = TpmInterruptDisable;
          v34[8] = v8;
          v34[9] = v25;
          Value = (*((__int64 (__fastcall **)(PKDPC, struct WDFDEVICE__ *, _QWORD *, _QWORD, char *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp
                   + 141))(
                    WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
                    a2,
                    v34,
                    0,
                    (char *)this + 296);
          if ( Value >= 0 )
          {
            *((_DWORD *)this + 76) |= 4u;
            *((_DWORD *)this + 66) = 1;
          }
        }
      }
    }
    if ( !*((_DWORD *)this + 66) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids);
      TpmRegister<unsigned char>::Write((char *)this + 348, v24, 0);
    }
  }
  if ( TpmTransportType::m_Version == 2 )
  {
    Value = Tpm20CmdGetSizes(this, (struct _TPM20CMD_SIZES *)&v32);
    if ( Value >= 0 )
      *((_DWORD *)this + 90) = v32;
  }
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x140018a30  mov     rax, rsp
0x140018a33  mov     [rax+8], rbx
0x140018a37  mov     [rax+20h], r9
0x140018a3b  mov     [rax+18h], r8
0x140018a3f  mov     [rax+10h], rdx
0x140018a43  push    rbp
0x140018a44  push    rsi
0x140018a45  push    rdi
0x140018a46  push    r12
0x140018a48  push    r13
0x140018a4a  push    r14
0x140018a4c  push    r15
0x140018a4e  lea     rbp, [rax-5Fh]
0x140018a52  sub     rsp, 100h
0x140018a59  xor     eax, eax
0x140018a5b  mov     r15, rdx
0x140018a5e  mov     rdi, rcx
0x140018a61  mov     [rbp+57h+var_B0], eax
0x140018a64  xorps   xmm0, xmm0
0x140018a67  lea     rcx, [rbp+57h+var_A0]; void *
0x140018a6b  xor     esi, esi
0x140018a6d  xor     edx, edx; Val
0x140018a6f  lea     r8d, [rax+68h]; Size
0x140018a73  mov     [rbp+57h+var_D0], rsi
0x140018a77  mov     rbx, r9
0x140018a7a  xor     r13d, r13d
0x140018a7d  movups  [rbp+57h+var_C0], xmm0
0x140018a81  call    memset
0x140018a86  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140018a8d  mov     rdx, r15
0x140018a90  mov     r8, cs:off_140047040
0x140018a97  xor     r12d, r12d
0x140018a9a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140018aa1  xor     r14d, r14d
0x140018aa4  mov     [rsp+130h+var_D8], esi
0x140018aa8  mov     rax, [rax+650h]
0x140018aaf  call    _guard_dispatch_icall
0x140018ab4  mov     [rbp+57h+var_C8], rax
0x140018ab8  xor     r15d, r15d
0x140018abb  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140018ac2  mov     rdx, rbx
0x140018ac5  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140018acc  mov     rax, [rax+980h]
0x140018ad3  call    _guard_dispatch_icall
0x140018ad8  cmp     r15d, eax
0x140018adb  jnb     loc_140018C50
0x140018ae1  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140018ae8  mov     r8d, r15d
0x140018aeb  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140018af2  mov     rdx, rbx
0x140018af5  mov     rax, [rax+988h]
0x140018afc  call    _guard_dispatch_icall
0x140018b01  mov     rbx, rax
0x140018b04  test    rax, rax
0x140018b07  jz      loc_140018F9F
0x140018b0d  movzx   ecx, byte ptr [rax]
0x140018b10  sub     ecx, 1
0x140018b13  jz      loc_140018C2F
0x140018b19  sub     ecx, 1
0x140018b1c  jz      loc_140018BCE
0x140018b22  cmp     ecx, 1
0x140018b25  jnz     loc_140018C3A
0x140018b2b  cmp     dword ptr [rax+0Ch], 400h
0x140018b32  jb      loc_140018C3A
0x140018b38  cmp     dword ptr [rax+8], 0
0x140018b3c  jnz     short loc_140018B47
0x140018b3e  cmp     dword ptr [rax+4], 0FED40000h
0x140018b45  jz      short loc_140018BA7
0x140018b47  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140018b4e  lea     rax, WPP_GLOBAL_Control
0x140018b55  cmp     rcx, rax
0x140018b58  jz      short loc_140018B76
0x140018b5a  mov     eax, [rcx+2Ch]
0x140018b5d  test    al, 2
0x140018b5f  jz      short loc_140018B76
0x140018b61  mov     rcx, [rcx+18h]
0x140018b65  lea     r8, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids
0x140018b6c  mov     edx, 0Ah
0x140018b71  call    WPP_SF_
0x140018b76  test    cs:TPMEnableBits, 2
0x140018b7d  jz      short loc_140018BA7
0x140018b7f  mov     eax, [rbx+4]
0x140018b82  lea     rdx, TPM_NON_STD_BASE_REG
0x140018b89  mov     [rsp+130h+var_100], eax
0x140018b8d  mov     r9d, 2Ch ; ','
0x140018b93  mov     eax, [rbx+8]
0x140018b96  mov     [rsp+130h+var_108], eax
0x140018b9a  mov     dword ptr [rsp+130h+var_110], 0CDh
0x140018ba2  call    McTemplateK0dqqq_EtwWriteTransfer
0x140018ba7  mov     edx, [rbx+0Ch]
0x140018baa  mov     r8d, 204h
0x140018bb0  mov     rcx, [rbx+4]
0x140018bb4  call    cs:__imp_MmMapIoSpaceEx
0x140018bbb  nop     dword ptr [rax+rax+00h]
0x140018bc0  mov     r14, rax
0x140018bc3  test    rax, rax
0x140018bc6  jz      short loc_140018C46
0x140018bc8  mov     r12d, [rbx+0Ch]
0x140018bcc  jmp     short loc_140018C3A
0x140018bce  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140018bd5  lea     rax, WPP_GLOBAL_Control
0x140018bdc  cmp     rcx, rax
0x140018bdf  jz      short loc_140018BFD
0x140018be1  mov     eax, [rcx+2Ch]
0x140018be4  test    al, 4
0x140018be6  jz      short loc_140018BFD
0x140018be8  mov     rcx, [rcx+18h]
0x140018bec  lea     r8, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids
0x140018bf3  mov     edx, 0Bh
0x140018bf8  call    WPP_SF_
0x140018bfd  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140018c04  mov     r8d, r15d
0x140018c07  mov     rdx, [rbp+57h+arg_10]
0x140018c0b  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140018c12  mov     [rsp+130h+var_D8], 1
0x140018c1a  mov     rax, [rax+988h]
0x140018c21  mov     [rbp+57h+var_D0], rbx
0x140018c25  call    _guard_dispatch_icall
0x140018c2a  mov     r13, rax
0x140018c2d  jmp     short loc_140018C3A
0x140018c2f  mov     rax, [rax+4]
0x140018c33  test    rax, rax
0x140018c36  cmovnz  rsi, rax
0x140018c3a  mov     rbx, [rbp+57h+arg_18]
0x140018c3e  inc     r15d
0x140018c41  jmp     loc_140018ABB
0x140018c46  mov     ebx, 0C000009Ah
0x140018c4b  jmp     loc_140018FA4
0x140018c50  xor     r15d, r15d
0x140018c53  test    r14, r14
0x140018c56  jz      loc_140018D3D
0x140018c5c  lea     esi, [r15+1]
0x140018c60  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, r14
0x140018c67  mov     dword ptr cs:WPP_MAIN_CB.Queue+30h, esi
0x140018c6d  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, r12
0x140018c74  call    Feature_TPMDriverMemoryTISWriteFix__private_IsEnabledDeviceUsageNoInline
0x140018c79  lea     r14d, [r15+4]
0x140018c7d  test    eax, eax
0x140018c7f  jz      loc_140018D61
0x140018c85  mov     qword ptr [rsp+130h+var_108], r15
0x140018c8a  lea     r9, WPP_MAIN_CB.Queue+18h
0x140018c91  mov     r8d, r14d
0x140018c94  mov     dword ptr [rsp+130h+var_110], r14d
0x140018c99  lea     rdx, aTpmdriverreada_0; "TPMDriverReadAfterWriteCount"
0x140018ca0  lea     ecx, [rsi+17h]
0x140018ca3  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x140018ca8  mov     ebx, eax
0x140018caa  cmp     eax, 0C0000034h
0x140018caf  jz      short loc_140018CC5
0x140018cb1  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+18h
0x140018cb7  test    eax, eax
0x140018cb9  jz      short loc_140018CC5
0x140018cbb  test    ebx, ebx
0x140018cbd  js      loc_140018FA4
0x140018cc3  jmp     short loc_140018CFF
0x140018cc5  lea     r9, [rsp+130h+var_E0]
0x140018cca  mov     [rsp+130h+var_E0], r15d
0x140018ccf  mov     r8d, r14d
0x140018cd2  mov     dword ptr [rsp+130h+var_110], r14d
0x140018cd7  lea     rdx, aTpmdriverreada; "TPMDriverReadAfterWriteConfig"
0x140018cde  mov     ecx, esi
0x140018ce0  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x140018ce5  mov     ebx, eax
0x140018ce7  test    eax, eax
0x140018ce9  js      loc_140018FA4
0x140018cef  mov     eax, r15d
0x140018cf2  mov     dword ptr cs:WPP_MAIN_CB.Queue+14h, r15d
0x140018cf9  mov     dword ptr cs:WPP_MAIN_CB.Queue+18h, eax
0x140018cff  test    eax, eax
0x140018d01  jz      short loc_140018D61
0x140018d03  cmp     dword ptr cs:WPP_MAIN_CB.Queue+14h, r15d
0x140018d0a  jnz     short loc_140018D61
0x140018d0c  lea     r9, [rsp+130h+var_E0]
0x140018d11  mov     [rsp+130h+var_E0], esi
0x140018d15  mov     r8d, r14d
0x140018d18  mov     dword ptr [rsp+130h+var_110], r14d
0x140018d1d  lea     rdx, aTpmdriverreada; "TPMDriverReadAfterWriteConfig"
0x140018d24  mov     ecx, esi
0x140018d26  call    ?AssignValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXK@Z; TpmRegistry::AssignValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong)
0x140018d2b  mov     ebx, eax
0x140018d2d  test    eax, eax
0x140018d2f  js      loc_140018FA4
0x140018d35  mov     dword ptr cs:WPP_MAIN_CB.Queue+14h, esi
0x140018d3b  jmp     short loc_140018D61
0x140018d3d  test    rsi, rsi
0x140018d40  jz      loc_140018F9F
0x140018d46  mov     dword ptr cs:WPP_MAIN_CB.Queue+30h, r15d
0x140018d4d  mov     r14d, 4
0x140018d53  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, rsi
0x140018d5a  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, r15
0x140018d61  mov     rcx, [rbp+57h+var_C8]; this
0x140018d65  call    ?Initialize@TpmDevice@@QEAAJXZ; TpmDevice::Initialize(void)
0x140018d6a  mov     ebx, eax
0x140018d6c  test    eax, eax
0x140018d6e  js      loc_140018FA4
0x140018d74  mov     esi, [rsp+130h+var_D8]
0x140018d78  mov     eax, r15d
0x140018d7b  test    esi, esi
0x140018d7d  setnz   al
0x140018d80  mov     [rdi+130h], eax
0x140018d86  call    ?IsInterruptSupportEnabled@TpmTransportType@@SAHXZ; TpmTransportType::IsInterruptSupportEnabled(void)
0x140018d8b  neg     eax
0x140018d8d  mov     r12d, 2
0x140018d93  mov     eax, [rdi+130h]
0x140018d99  sbb     ecx, ecx
0x140018d9b  and     eax, 0FFFFFFFDh
0x140018d9e  and     ecx, r12d
0x140018da1  or      ecx, eax
0x140018da3  mov     [rdi+130h], ecx
0x140018da9  test    esi, esi
0x140018dab  jz      loc_140018F79
0x140018db1  call    ?IsInterruptSupportEnabled@TpmTransportType@@SAHXZ; TpmTransportType::IsInterruptSupportEnabled(void)
0x140018db6  test    eax, eax
0x140018db8  jz      loc_140018F79
0x140018dbe  lea     rsi, [rdi+140h]
0x140018dc5  mov     rcx, rsi
0x140018dc8  call    ?Read@?$TpmRegister@E@@QEAAEI@Z; TpmRegister<uchar>::Read(uint)
0x140018dcd  test    al, 20h
0x140018dcf  jnz     short loc_140018E14
0x140018dd1  mov     r8b, r12b
0x140018dd4  mov     rcx, rsi
0x140018dd7  call    ?Write@?$TpmRegister@E@@QEAAXIE@Z; TpmRegister<uchar>::Write(uint,uchar)
0x140018ddc  mov     eax, cs:?m_DefaultTimeouts@TpmTransport@@1VTpmTimeouts@1@A; TpmTransport::TpmTimeouts TpmTransport::m_DefaultTimeouts
0x140018de2  mov     r8, rsi
0x140018de5  mov     [rsp+130h+var_E8], 1; char
0x140018dea  mov     edx, 165h
0x140018def  mov     [rsp+130h+var_F0], r15; __int64
0x140018df4  mov     rcx, rdi; this
0x140018df7  mov     [rsp+130h+var_F8], r15b; char
0x140018dfc  mov     [rsp+130h+var_100], eax; int
0x140018e00  mov     [rsp+130h+var_110], 20h ; ' '; char
0x140018e05  call    ??$WaitForBitSet@E@TpmTransportTis@@AEAAJIAEAV?$TpmRegister@E@@IE_NI1PEAE1@Z; TpmTransportTis::WaitForBitSet<uchar>(uint,TpmRegister<uchar> &,uint,uchar,bool,uint,bool,uchar *,bool)
0x140018e0a  mov     ebx, eax
0x140018e0c  test    eax, eax
0x140018e0e  js      loc_140018FA4
0x140018e14  test    r13, r13
0x140018e17  jz      short loc_140018E67
0x140018e19  mov     esi, [r13+8]
0x140018e1d  lea     eax, [rsi-1]
0x140018e20  cmp     eax, 0Eh
0x140018e23  ja      short loc_140018E67
0x140018e25  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140018e2c  lea     rax, WPP_GLOBAL_Control
0x140018e33  cmp     rcx, rax
0x140018e36  jz      short loc_140018E58
0x140018e38  mov     eax, [rcx+2Ch]
0x140018e3b  test    r14b, al
0x140018e3e  jz      short loc_140018E58
0x140018e40  mov     rcx, [rcx+18h]
0x140018e44  lea     r8, WPP_180f891eace83e5bd5ec0d2a96c28cc7_Traceguids
0x140018e4b  mov     edx, 0Ch
0x140018e50  mov     r9d, esi
0x140018e53  call    WPP_SF_d
0x140018e58  mov     r8b, sil
0x140018e5b  lea     rcx, [rdi+15Ch]
0x140018e62  call    ?Write@?$TpmRegister@E@@QEAAXIE@Z; TpmRegister<uchar>::Write(uint,uchar)
0x140018e67  xor     edx, edx; unsigned int
0x140018e69  mov     rcx, rdi; this
0x140018e6c  call    ?SetIntRegisterEnable@TpmTransportTis@@AEAAHI@Z; TpmTransportTis::SetIntRegisterEnable(uint)
0x140018e71  test    eax, eax
0x140018e73  jz      loc_140018F31
0x140018e79  mov     rsi, [rbp+57h+var_D0]
0x140018e7d  test    rsi, rsi
0x140018e80  jz      loc_140018F31
0x140018e86  test    r13, r13
0x140018e89  jz      loc_140018F31
0x140018e8f  mov     rcx, rdi; this
0x140018e92  call    ?ClearIntRegDataAvail@TpmTransportTis@@AEAAXXZ; TpmTransportTis::ClearIntRegDataAvail(void)
0x140018e97  mov     ebx, 68h ; 'h'
0x140018e9c  lea     rcx, [rbp+57h+var_A0]; void *
0x140018ea0  mov     r8d, ebx; Size
0x140018ea3  xor     edx, edx; Val
0x140018ea5  call    memset
0x140018eaa  mov     rdx, [rbp+57h+arg_8]
0x140018eae  lea     rax, TpmInterruptIsr
0x140018eb5  mov     [rbp+57h+var_88], rax
0x140018eb9  lea     rcx, [rdi+128h]
0x140018ec0  lea     rax, TpmInterruptDpc
0x140018ec7  mov     [rbp+57h+var_A0], ebx
0x140018eca  mov     [rbp+57h+var_80], rax
0x140018ece  lea     r8, [rbp+57h+var_A0]
0x140018ed2  lea     rax, TpmInterruptEnable
0x140018ed9  mov     [rbp+57h+var_90], r12d
0x140018edd  mov     [rbp+57h+var_78], rax
0x140018ee1  xor     r9d, r9d
0x140018ee4  lea     rax, TpmInterruptDisable
0x140018eeb  mov     [rbp+57h+var_44], r12d
0x140018eef  mov     [rbp+57h+var_70], rax
0x140018ef3  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140018efa  mov     [rbp+57h+var_60], r13
0x140018efe  mov     [rbp+57h+var_58], rsi
0x140018f02  mov     qword ptr [rsp+130h+var_110], rcx
0x140018f07  mov     rax, [rax+468h]
0x140018f0e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x140018f15  call    _guard_dispatch_icall
0x140018f1a  mov     ebx, eax
0x140018f1c  test    eax, eax
0x140018f1e  js      short loc_140018F31
0x140018f20  or      [rdi+130h], r14d
0x140018f27  mov     dword ptr [rdi+108h], 1
  ... truncated ...
```
