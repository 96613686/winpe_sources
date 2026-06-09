# TpmTransportCommandResponseHsp::TpmEvtDevicePrepareHardware(WDFDEVICE__ *,WDFCMRESLIST__ *,WDFCMRESLIST__ *)

- ea: `0x140028ab0`
- end: `0x140028cdc`
- name: `?TpmEvtDevicePrepareHardware@TpmTransportCommandResponseHsp@@UEAAJPEAUWDFDEVICE__@@PEAUWDFCMRESLIST__@@1@Z`
- size: `556`
- prototype: `__int64 __fastcall(TpmTransportCommandResponseHsp *__hidden this, struct WDFDEVICE__ *, struct WDFCMRESLIST__ *, struct WDFCMRESLIST__ *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400078b8`
- `0x140022934`
- `0x1400239b0`
- `0x140028ab0`
- `0x140028d34`
- `0x140039740`

## import_xrefs

- `ntoskrnl!MmMapIoSpaceEx` at `0x140028b7f`
- `ntoskrnl!MmMapIoSpaceEx` at `0x140028be4`
- `ntoskrnl!MmMapIoSpaceEx` at `0x140028c45`
- `ntoskrnl!MmMapIoSpaceEx` at `0x140028b7f`
- `ntoskrnl!MmMapIoSpaceEx` at `0x140028be4`
- `ntoskrnl!MmMapIoSpaceEx` at `0x140028c45`

## pseudocode

```c
__int64 __fastcall TpmTransportCommandResponseHsp::TpmEvtDevicePrepareHardware(
        TpmTransportCommandResponseHsp *this,
        struct WDFDEVICE__ *a2,
        struct WDFCMRESLIST__ *a3,
        struct WDFCMRESLIST__ *a4)
{
  int AcpiTablePlatformParameters; // ebx
  unsigned int v6; // r14d
  unsigned int v7; // esi
  __int64 v8; // rax
  __int64 v9; // rcx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v16[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v17; // [rsp+28h] [rbp-50h]
  __int64 v18; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v19; // [rsp+38h] [rbp-40h]
  unsigned int v20; // [rsp+3Ch] [rbp-3Ch]

  v16[0] = 4;
  AcpiTablePlatformParameters = TpmTransportMemBase::TpmEvtDevicePrepareHardware(this, a2, a3, a4);
  if ( AcpiTablePlatformParameters < 0 )
    goto LABEL_27;
  AcpiTablePlatformParameters = TpmTransportType::GetAcpiTablePlatformParameters(4u, (unsigned int *)&v18, v16);
  if ( AcpiTablePlatformParameters < 0 )
    goto LABEL_27;
  if ( v16[0] < 4 )
  {
    AcpiTablePlatformParameters = -1073741811;
LABEL_27:
    TpmTransportCommandResponseHsp::UnmapMailboxAddresses(this);
    return (unsigned int)AcpiTablePlatformParameters;
  }
  v17 = v18;
  v16[0] = v19;
  v16[1] = v20;
  if ( !v18 || !*(_QWORD *)v16 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
      goto LABEL_26;
    v11 = 10;
    goto LABEL_25;
  }
  v6 = v18 & 0xFFF;
  v16[0] = v19 & 0xFFFFF000;
  v7 = v19 & 0xFFF;
  LODWORD(v17) = v18 & 0xFFFFF000;
  if ( v17 == *(_QWORD *)v16 )
  {
    v8 = MmMapIoSpaceEx(v17, 4096, 516);
    *((_QWORD *)this + 67) = v8;
    v9 = v8;
    if ( !v8 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_26;
      v11 = 11;
LABEL_25:
      WPP_SF_(v10->AttachedDevice, v11, WPP_424eb819144b3da1c0fd8eea13590484_Traceguids);
LABEL_26:
      AcpiTablePlatformParameters = -1073741823;
      goto LABEL_27;
    }
    *((_QWORD *)this + 68) = v8 + v6;
  }
  else
  {
    v12 = MmMapIoSpaceEx(v17, 4096, 516);
    *((_QWORD *)this + 68) = v12;
    if ( !v12 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_26;
      v11 = 12;
      goto LABEL_25;
    }
    v13 = *(_QWORD *)v16;
    *((_QWORD *)this + 68) = v12 + v6;
    v14 = MmMapIoSpaceEx(v13, 4096, 516);
    *((_QWORD *)this + 69) = v14;
    v9 = v14;
    if ( !v14 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_26;
      v11 = 13;
      goto LABEL_25;
    }
  }
  *((_QWORD *)this + 69) = v9 + v7;
  return (unsigned int)AcpiTablePlatformParameters;
}

```

## disassembly

```asm
0x140028ab0  push    rbx
0x140028ab2  push    rsi
0x140028ab3  push    rdi
0x140028ab4  push    r14
0x140028ab6  sub     rsp, 58h
0x140028aba  mov     rax, cs:__security_cookie
0x140028ac1  xor     rax, rsp
0x140028ac4  mov     [rsp+78h+var_38], rax
0x140028ac9  mov     esi, 4
0x140028ace  mov     rdi, rcx
0x140028ad1  mov     [rsp+78h+var_58], esi
0x140028ad5  call    ?TpmEvtDevicePrepareHardware@TpmTransportMemBase@@UEAAJPEAUWDFDEVICE__@@PEAUWDFCMRESLIST__@@1@Z; TpmTransportMemBase::TpmEvtDevicePrepareHardware(WDFDEVICE__ *,WDFCMRESLIST__ *,WDFCMRESLIST__ *)
0x140028ada  mov     ebx, eax
0x140028adc  test    eax, eax
0x140028ade  js      loc_140028CBA
0x140028ae4  lea     r8, [rsp+78h+var_58]; unsigned int *
0x140028ae9  mov     ecx, esi; unsigned int
0x140028aeb  lea     rdx, [rsp+78h+var_48]; unsigned int *
0x140028af0  call    ?GetAcpiTablePlatformParameters@TpmTransportType@@SAJIPEAI0@Z; TpmTransportType::GetAcpiTablePlatformParameters(uint,uint *,uint *)
0x140028af5  mov     ebx, eax
0x140028af7  test    eax, eax
0x140028af9  js      loc_140028CBA
0x140028aff  cmp     [rsp+78h+var_58], esi
0x140028b03  jnb     short loc_140028B0F
0x140028b05  mov     ebx, 0C000000Dh
0x140028b0a  jmp     loc_140028CBA
0x140028b0f  mov     eax, dword ptr [rsp+78h+var_48+4]
0x140028b13  mov     ecx, dword ptr [rsp+78h+var_48]
0x140028b17  mov     edx, [rsp+78h+var_40]
0x140028b1b  mov     dword ptr [rsp+78h+var_50+4], eax
0x140028b1f  mov     eax, [rsp+78h+var_3C]
0x140028b23  mov     dword ptr [rsp+78h+var_50], ecx
0x140028b27  cmp     [rsp+78h+var_50], 0
0x140028b2d  mov     [rsp+78h+var_58], edx
0x140028b31  mov     [rsp+78h+var_58+4], eax
0x140028b35  jz      loc_140028C85
0x140028b3b  cmp     qword ptr [rsp+78h+var_58], 0
0x140028b41  jz      loc_140028C85
0x140028b47  mov     r8d, 0FFFh
0x140028b4d  mov     r14d, ecx
0x140028b50  mov     esi, edx
0x140028b52  mov     eax, 0FFFFF000h
0x140028b57  and     ecx, eax
0x140028b59  and     edx, eax
0x140028b5b  and     r14d, r8d
0x140028b5e  mov     [rsp+78h+var_58], edx
0x140028b62  and     esi, r8d
0x140028b65  mov     dword ptr [rsp+78h+var_50], ecx
0x140028b69  mov     rcx, [rsp+78h+var_50]
0x140028b6e  lea     edx, [r8+1]
0x140028b72  mov     r8d, 204h
0x140028b78  cmp     rcx, qword ptr [rsp+78h+var_58]
0x140028b7d  jnz     short loc_140028BE4
0x140028b7f  call    cs:__imp_MmMapIoSpaceEx
0x140028b86  nop     dword ptr [rax+rax+00h]
0x140028b8b  mov     [rdi+218h], rax
0x140028b92  mov     rcx, rax
0x140028b95  test    rax, rax
0x140028b98  jnz     short loc_140028BC6
0x140028b9a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028ba1  lea     rax, WPP_GLOBAL_Control
0x140028ba8  cmp     rcx, rax
0x140028bab  jz      loc_140028CB5
0x140028bb1  mov     eax, [rcx+2Ch]
0x140028bb4  test    al, 1
0x140028bb6  jz      loc_140028CB5
0x140028bbc  mov     edx, 0Bh
0x140028bc1  jmp     loc_140028CA5
0x140028bc6  mov     eax, r14d
0x140028bc9  add     rax, rcx
0x140028bcc  mov     [rdi+220h], rax
0x140028bd3  mov     eax, esi
0x140028bd5  add     rax, rcx
0x140028bd8  mov     [rdi+228h], rax
0x140028bdf  jmp     loc_140028CC2
0x140028be4  call    cs:__imp_MmMapIoSpaceEx
0x140028beb  nop     dword ptr [rax+rax+00h]
0x140028bf0  mov     [rdi+220h], rax
0x140028bf7  mov     rcx, rax
0x140028bfa  test    rax, rax
0x140028bfd  jnz     short loc_140028C28
0x140028bff  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028c06  lea     rax, WPP_GLOBAL_Control
0x140028c0d  cmp     rcx, rax
0x140028c10  jz      loc_140028CB5
0x140028c16  mov     eax, [rcx+2Ch]
0x140028c19  test    al, 1
0x140028c1b  jz      loc_140028CB5
0x140028c21  mov     edx, 0Ch
0x140028c26  jmp     short loc_140028CA5
0x140028c28  mov     eax, r14d
0x140028c2b  mov     edx, 1000h
0x140028c30  add     rax, rcx
0x140028c33  mov     r8d, 204h
0x140028c39  mov     rcx, qword ptr [rsp+78h+var_58]
0x140028c3e  mov     [rdi+220h], rax
0x140028c45  call    cs:__imp_MmMapIoSpaceEx
0x140028c4c  nop     dword ptr [rax+rax+00h]
0x140028c51  mov     [rdi+228h], rax
0x140028c58  mov     rcx, rax
0x140028c5b  test    rax, rax
0x140028c5e  jnz     loc_140028BD3
0x140028c64  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028c6b  lea     rax, WPP_GLOBAL_Control
0x140028c72  cmp     rcx, rax
0x140028c75  jz      short loc_140028CB5
0x140028c77  mov     eax, [rcx+2Ch]
0x140028c7a  test    al, 1
0x140028c7c  jz      short loc_140028CB5
0x140028c7e  mov     edx, 0Dh
0x140028c83  jmp     short loc_140028CA5
0x140028c85  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028c8c  lea     rax, WPP_GLOBAL_Control
0x140028c93  cmp     rcx, rax
0x140028c96  jz      short loc_140028CB5
0x140028c98  mov     eax, [rcx+2Ch]
0x140028c9b  test    sil, al
0x140028c9e  jz      short loc_140028CB5
0x140028ca0  mov     edx, 0Ah
0x140028ca5  mov     rcx, [rcx+18h]
0x140028ca9  lea     r8, WPP_424eb819144b3da1c0fd8eea13590484_Traceguids
0x140028cb0  call    WPP_SF_
0x140028cb5  mov     ebx, 0C0000001h
0x140028cba  mov     rcx, rdi; this
0x140028cbd  call    ?UnmapMailboxAddresses@TpmTransportCommandResponseHsp@@IEAAXXZ; TpmTransportCommandResponseHsp::UnmapMailboxAddresses(void)
0x140028cc2  mov     eax, ebx
0x140028cc4  mov     rcx, [rsp+78h+var_38]
0x140028cc9  xor     rcx, rsp; StackCookie
0x140028ccc  call    __security_check_cookie
0x140028cd1  add     rsp, 58h
0x140028cd5  pop     r14
0x140028cd7  pop     rdi
0x140028cd8  pop     rsi
0x140028cd9  pop     rbx
0x140028cda  retn
```
