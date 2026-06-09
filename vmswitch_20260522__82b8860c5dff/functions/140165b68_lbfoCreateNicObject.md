# lbfoCreateNicObject

- ea: `0x140165b68`
- end: `0x140165e4a`
- name: `lbfoCreateNicObject`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140164cd0`

## callees

- `0x14002e0f0`
- `0x140095e88`
- `0x1400dabf0`
- `0x14015b288`
- `0x140164bf4`
- `0x14016531c`
- `0x1401654d0`
- `0x140165b68`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140165cd5`
- `ntoskrnl!KeInitializeEvent` at `0x140165cd5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140165dc4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140165dc4`
- `ntoskrnl!RtlStringFromGUID` at `0x140165d13`
- `ntoskrnl!RtlStringFromGUID` at `0x140165d13`
- `ntoskrnl!ExAllocatePool3` at `0x140165bc6`
- `ntoskrnl!ExAllocatePool3` at `0x140165bc6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140165d65`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140165d65`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x140165d21`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x140165d21`

## pseudocode

```c
__int64 __fastcall lbfoCreateNicObject(__int64 a1, _OWORD *a2, __int64 a3, __int64 a4, int a5, __int16 a6, __int64 *a7)
{
  __int64 *v7; // r15
  __int64 Pool3; // rax
  int v12; // edx
  __int64 v13; // rbx
  unsigned int Timer; // edi
  int v15; // edx
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // r8
  int v18; // r9d
  unsigned __int8 v19; // cl
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v22; // edx
  int v23; // r8d
  int v25; // [rsp+20h] [rbp-A8h]
  int v26; // [rsp+40h] [rbp-88h]
  int v27; // [rsp+48h] [rbp-80h]
  struct _UNICODE_STRING GuidString; // [rsp+68h] [rbp-60h] BYREF
  _QWORD v29[10]; // [rsp+78h] [rbp-50h] BYREF

  v7 = a7;
  v29[1] = 16;
  v29[0] = 1;
  GuidString = 0;
  Pool3 = ExAllocatePool3(64, 912, 1415801166, v29, 1);
  v13 = Pool3;
  if ( Pool3 )
  {
    Timer = VmsTmAllocateTimer(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 304LL), &lbfoSoftFailTimer, Pool3 + 688);
    if ( !Timer )
    {
      *(_QWORD *)(v13 + 696) = a1;
      v19 = 1;
      *(_DWORD *)(v13 + 704) = 6;
      *(_DWORD *)(v13 + 160) = 0;
      do
      {
        if ( !*(_QWORD *)(a1 + 8LL * v19 + 1696) )
          break;
        ++v19;
      }
      while ( v19 <= 0x40u );
      *(_BYTE *)(v13 + 680) = v19;
      *(_QWORD *)(v13 + 744) = 10000000000LL;
      *(_QWORD *)(v13 + 752) = 10000000000LL;
      *(_WORD *)(v13 + 170) = 1;
      *(_DWORD *)(v13 + 760) = -1;
      *(_DWORD *)(v13 + 764) = -1;
      *(_QWORD *)(v13 + 72) = v13 + 80;
      *(_DWORD *)(v13 + 736) = 0;
      *(_WORD *)(v13 + 66) = 78;
      *(_QWORD *)(v13 + 720) = v13 + 712;
      *(_QWORD *)(v13 + 712) = v13 + 712;
      KeInitializeEvent((PRKEVENT)(v13 + 176), NotificationEvent, 0);
      *(_WORD *)(v13 + 164) = a6;
      *(_DWORD *)(v13 + 40) = *(_DWORD *)a3;
      *(_WORD *)(v13 + 44) = *(_WORD *)(a3 + 4);
      *(_OWORD *)(v13 + 48) = *a2;
      v20 = RtlStringFromGUID((const GUID *const)(v13 + 48), &GuidString);
      v21 = NdisConvertNtStatusToNdisStatus(v20);
      Timer = v21;
      if ( v21 )
      {
        WPP_RECORDER_SF__guid_d(
          VmsIfrLog,
          v22,
          v23,
          41,
          (__int64)WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids,
          v13 + 48,
          v21);
      }
      else
      {
        RtlCopyUnicodeString((PUNICODE_STRING)(v13 + 64), &GuidString);
        v16 = WPP_GLOBAL_Control;
        if ( (unsigned __int8)(BYTE1(WPP_GLOBAL_Control->Timer) - 1) > 2u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_qqd_guid__MAC_(
            WPP_GLOBAL_Control->DeviceExtension,
            v15,
            v17,
            v18,
            v25,
            a1,
            v13,
            *(_BYTE *)(v13 + 680),
            v13 + 48,
            v13 + 40);
      }
      v7 = a7;
    }
  }
  else
  {
    Timer = -1073741670;
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_ld(VmsIfrLog, v12, 20, 40, (__int64)WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids, 144, 154);
  }
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  if ( Timer )
  {
    if ( v13 )
    {
      lbfoDestroyNicObject(a1, v13);
      v13 = 0;
    }
    WPP_RECORDER_SF_q_guid__MAC_IIHd((_DWORD)v16, v15, v17, v18, v25, a1, (__int64)a2, a3, v26, v27, a6, Timer);
  }
  else if ( v13 && (Microsoft_Windows_Hyper_V_VmSwitchEnableBits & 0x200000) != 0 )
  {
    McTemplateK0jd_EtwWriteTransfer(v16, MemberCreatedInfo, v17, v13 + 48, 0);
  }
  *v7 = v13;
  return Timer;
}

```

## disassembly

```asm
0x140165b68  mov     r11, rsp
0x140165b6b  mov     [r11+20h], rbx
0x140165b6f  push    rbp
0x140165b70  push    rsi
0x140165b71  push    rdi
0x140165b72  push    r12
0x140165b74  push    r13
0x140165b76  push    r14
0x140165b78  push    r15
0x140165b7a  sub     rsp, 90h
0x140165b81  mov     r15, [rsp+0C8h+arg_30]
0x140165b89  lea     r9, [r11-50h]
0x140165b8d  xor     ebp, ebp
0x140165b8f  mov     [rsp+0C8h+var_68], r15
0x140165b94  mov     r14, r8
0x140165b97  mov     qword ptr [r11-48h], 10h
0x140165b9f  mov     r12, rdx
0x140165ba2  mov     rsi, rcx
0x140165ba5  xorps   xmm0, xmm0
0x140165ba8  mov     edx, 390h
0x140165bad  lea     eax, [rbp+1]
0x140165bb0  mov     r8d, 5463694Eh
0x140165bb6  lea     ecx, [rbp+40h]
0x140165bb9  mov     [r11-50h], rax
0x140165bbd  mov     dword ptr [rsp+0C8h+var_A8], eax
0x140165bc1  movups  xmmword ptr [rsp+0C8h+GuidString.Length], xmm0
0x140165bc6  call    cs:__imp_ExAllocatePool3
0x140165bcd  nop     dword ptr [rax+rax+00h]
0x140165bd2  movzx   r13d, [rsp+0C8h+arg_28]
0x140165bdb  mov     rbx, rax
0x140165bde  test    rax, rax
0x140165be1  jnz     short loc_140165C1B
0x140165be3  mov     edi, 0C000009Ah
0x140165be8  mov     rcx, cs:VmsIfrLog
0x140165bef  lea     rax, WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids
0x140165bf6  mov     dword ptr [rsp+0C8h+var_98], edi
0x140165bfa  lea     r9d, [rbp+28h]
0x140165bfe  mov     dword ptr [rsp+0C8h+var_A0], 390h
0x140165c06  lea     r8d, [rbp+14h]
0x140165c0a  mov     dl, 2
0x140165c0c  mov     [rsp+0C8h+var_A8], rax
0x140165c11  call    WPP_RECORDER_SF_ld
0x140165c16  jmp     loc_140165DB8
0x140165c1b  mov     rcx, [rsi+8]
0x140165c1f  lea     r8, [rax+2B0h]
0x140165c26  lea     rdx, lbfoSoftFailTimer
0x140165c2d  mov     rcx, [rcx+130h]
0x140165c34  call    VmsTmAllocateTimer
0x140165c39  mov     edi, eax
0x140165c3b  test    eax, eax
0x140165c3d  jnz     loc_140165DB8
0x140165c43  lea     edx, [rax+1]
0x140165c46  mov     [rbx+2B8h], rsi
0x140165c4d  mov     cl, dl
0x140165c4f  mov     dword ptr [rbx+2C0h], 6
0x140165c59  mov     [rbx+0A0h], ebp
0x140165c5f  movzx   eax, cl
0x140165c62  cmp     [rsi+rax*8+6A0h], rbp
0x140165c6a  jz      short loc_140165C73
0x140165c6c  add     cl, dl
0x140165c6e  cmp     cl, 40h ; '@'
0x140165c71  jbe     short loc_140165C5F
0x140165c73  mov     rax, 2540BE400h
0x140165c7d  mov     [rbx+2A8h], cl
0x140165c83  mov     [rbx+2E8h], rax
0x140165c8a  lea     rcx, [rbx+0B0h]; Event
0x140165c91  mov     [rbx+2F0h], rax
0x140165c98  xor     r8d, r8d; State
0x140165c9b  or      eax, 0FFFFFFFFh
0x140165c9e  mov     [rbx+0AAh], dx
0x140165ca5  mov     [rbx+2F8h], eax
0x140165cab  xor     edx, edx; Type
0x140165cad  mov     [rbx+2FCh], eax
0x140165cb3  lea     rax, [rbx+50h]
0x140165cb7  mov     [rbx+48h], rax
0x140165cbb  lea     rax, [rbx+2C8h]
0x140165cc2  mov     [rbx+2E0h], ebp
0x140165cc8  mov     word ptr [rbx+42h], 4Eh ; 'N'
0x140165cce  mov     [rax+8], rax
0x140165cd2  mov     [rax], rax
0x140165cd5  call    cs:__imp_KeInitializeEvent
0x140165cdc  nop     dword ptr [rax+rax+00h]
0x140165ce1  mov     [rbx+0A4h], r13w
0x140165ce9  lea     r15, [rbx+28h]
0x140165ced  mov     eax, [r14]
0x140165cf0  lea     rbp, [rbx+30h]
0x140165cf4  mov     [r15], eax
0x140165cf7  lea     rdx, [rsp+0C8h+GuidString]; GuidString
0x140165cfc  movzx   eax, word ptr [r14+4]
0x140165d01  mov     rcx, rbp; Guid
0x140165d04  mov     [r15+4], ax
0x140165d09  movaps  xmm0, xmmword ptr [r12]
0x140165d0e  movdqu  xmmword ptr [rbp+0], xmm0
0x140165d13  call    cs:__imp_RtlStringFromGUID
0x140165d1a  nop     dword ptr [rax+rax+00h]
0x140165d1f  mov     ecx, eax
0x140165d21  call    cs:__imp_NdisConvertNtStatusToNdisStatus
0x140165d28  nop     dword ptr [rax+rax+00h]
0x140165d2d  mov     edi, eax
0x140165d2f  test    eax, eax
0x140165d31  jz      short loc_140165D5C
0x140165d33  mov     rcx, cs:VmsIfrLog
0x140165d3a  mov     r9d, 29h ; ')'
0x140165d40  mov     dword ptr [rsp+0C8h+var_98], eax
0x140165d44  lea     rax, WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids
0x140165d4b  mov     [rsp+0C8h+var_A0], rbp
0x140165d50  mov     [rsp+0C8h+var_A8], rax
0x140165d55  call    WPP_RECORDER_SF__guid_d
0x140165d5a  jmp     short loc_140165DB1
0x140165d5c  lea     rcx, [rbx+40h]; DestinationString
0x140165d60  lea     rdx, [rsp+0C8h+GuidString]; SourceString
0x140165d65  call    cs:__imp_RtlCopyUnicodeString
0x140165d6c  nop     dword ptr [rax+rax+00h]
0x140165d71  mov     rcx, cs:WPP_GLOBAL_Control
0x140165d78  mov     al, [rcx+29h]
0x140165d7b  dec     al
0x140165d7d  cmp     al, 2
0x140165d7f  ja      short loc_140165D89
0x140165d81  xor     eax, eax
0x140165d83  cmp     [rcx+48h], ax
0x140165d87  jz      short loc_140165DB1
0x140165d89  movzx   eax, byte ptr [rbx+2A8h]
0x140165d90  mov     rcx, [rcx+40h]
0x140165d94  mov     [rsp+0C8h+var_80], r15
0x140165d99  mov     [rsp+0C8h+var_88], rbp
0x140165d9e  mov     dword ptr [rsp+0C8h+var_90], eax
0x140165da2  mov     [rsp+0C8h+var_98], rbx
0x140165da7  mov     [rsp+0C8h+var_A0], rsi
0x140165dac  call    WPP_RECORDER_SF_qqd_guid__MAC_
0x140165db1  mov     r15, [rsp+0C8h+var_68]
0x140165db6  xor     ebp, ebp
0x140165db8  cmp     [rsp+0C8h+GuidString.Buffer], rbp
0x140165dbd  jz      short loc_140165DD0
0x140165dbf  lea     rcx, [rsp+0C8h+GuidString]; UnicodeString
0x140165dc4  call    cs:__imp_RtlFreeUnicodeString
0x140165dcb  nop     dword ptr [rax+rax+00h]
0x140165dd0  test    edi, edi
0x140165dd2  jz      short loc_140165E07
0x140165dd4  test    rbx, rbx
0x140165dd7  jz      short loc_140165DE7
0x140165dd9  mov     rdx, rbx
0x140165ddc  mov     rcx, rsi
0x140165ddf  call    lbfoDestroyNicObject
0x140165de4  mov     rbx, rbp
0x140165de7  mov     [rsp+0C8h+var_70], edi
0x140165deb  mov     [rsp+0C8h+var_78], r13w
0x140165df1  mov     [rsp+0C8h+var_90], r14
0x140165df6  mov     [rsp+0C8h+var_98], r12
0x140165dfb  mov     [rsp+0C8h+var_A0], rsi
0x140165e00  call    WPP_RECORDER_SF_q_guid__MAC_IIHd
0x140165e05  jmp     short loc_140165E29
0x140165e07  test    rbx, rbx
0x140165e0a  jz      short loc_140165E29
0x140165e0c  test    byte ptr cs:Microsoft_Windows_Hyper_V_VmSwitchEnableBits+2, 20h
0x140165e13  jz      short loc_140165E29
0x140165e15  lea     r9, [rbx+30h]
0x140165e19  mov     dword ptr [rsp+0C8h+var_A8], ebp
0x140165e1d  lea     rdx, MemberCreatedInfo
0x140165e24  call    McTemplateK0jd_EtwWriteTransfer
0x140165e29  mov     [r15], rbx
0x140165e2c  mov     eax, edi
0x140165e2e  mov     rbx, [rsp+0C8h+arg_18]
0x140165e36  add     rsp, 90h
0x140165e3d  pop     r15
0x140165e3f  pop     r14
0x140165e41  pop     r13
0x140165e43  pop     r12
0x140165e45  pop     rdi
0x140165e46  pop     rsi
0x140165e47  pop     rbp
0x140165e48  retn
```
