# lbfoCreateNicObject

- ea: `0x140165bd8`
- end: `0x140165eba`
- name: `lbfoCreateNicObject`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140164d40`

## callees

- `0x14002e0f0`
- `0x140095e88`
- `0x1400dac60`
- `0x14015b2f8`
- `0x140164c64`
- `0x14016538c`
- `0x140165540`
- `0x140165bd8`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140165d45`
- `ntoskrnl!KeInitializeEvent` at `0x140165d45`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140165e34`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140165e34`
- `ntoskrnl!RtlStringFromGUID` at `0x140165d83`
- `ntoskrnl!RtlStringFromGUID` at `0x140165d83`
- `ntoskrnl!ExAllocatePool3` at `0x140165c36`
- `ntoskrnl!ExAllocatePool3` at `0x140165c36`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140165dd5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140165dd5`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x140165d91`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x140165d91`

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
0x140165bd8  mov     r11, rsp
0x140165bdb  mov     [r11+20h], rbx
0x140165bdf  push    rbp
0x140165be0  push    rsi
0x140165be1  push    rdi
0x140165be2  push    r12
0x140165be4  push    r13
0x140165be6  push    r14
0x140165be8  push    r15
0x140165bea  sub     rsp, 90h
0x140165bf1  mov     r15, [rsp+0C8h+arg_30]
0x140165bf9  lea     r9, [r11-50h]
0x140165bfd  xor     ebp, ebp
0x140165bff  mov     [rsp+0C8h+var_68], r15
0x140165c04  mov     r14, r8
0x140165c07  mov     qword ptr [r11-48h], 10h
0x140165c0f  mov     r12, rdx
0x140165c12  mov     rsi, rcx
0x140165c15  xorps   xmm0, xmm0
0x140165c18  mov     edx, 390h
0x140165c1d  lea     eax, [rbp+1]
0x140165c20  mov     r8d, 5463694Eh
0x140165c26  lea     ecx, [rbp+40h]
0x140165c29  mov     [r11-50h], rax
0x140165c2d  mov     dword ptr [rsp+0C8h+var_A8], eax
0x140165c31  movups  xmmword ptr [rsp+0C8h+GuidString.Length], xmm0
0x140165c36  call    cs:__imp_ExAllocatePool3
0x140165c3d  nop     dword ptr [rax+rax+00h]
0x140165c42  movzx   r13d, [rsp+0C8h+arg_28]
0x140165c4b  mov     rbx, rax
0x140165c4e  test    rax, rax
0x140165c51  jnz     short loc_140165C8B
0x140165c53  mov     edi, 0C000009Ah
0x140165c58  mov     rcx, cs:VmsIfrLog
0x140165c5f  lea     rax, WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids
0x140165c66  mov     dword ptr [rsp+0C8h+var_98], edi
0x140165c6a  lea     r9d, [rbp+28h]
0x140165c6e  mov     dword ptr [rsp+0C8h+var_A0], 390h
0x140165c76  lea     r8d, [rbp+14h]
0x140165c7a  mov     dl, 2
0x140165c7c  mov     [rsp+0C8h+var_A8], rax
0x140165c81  call    WPP_RECORDER_SF_ld
0x140165c86  jmp     loc_140165E28
0x140165c8b  mov     rcx, [rsi+8]
0x140165c8f  lea     r8, [rax+2B0h]
0x140165c96  lea     rdx, lbfoSoftFailTimer
0x140165c9d  mov     rcx, [rcx+130h]
0x140165ca4  call    VmsTmAllocateTimer
0x140165ca9  mov     edi, eax
0x140165cab  test    eax, eax
0x140165cad  jnz     loc_140165E28
0x140165cb3  lea     edx, [rax+1]
0x140165cb6  mov     [rbx+2B8h], rsi
0x140165cbd  mov     cl, dl
0x140165cbf  mov     dword ptr [rbx+2C0h], 6
0x140165cc9  mov     [rbx+0A0h], ebp
0x140165ccf  movzx   eax, cl
0x140165cd2  cmp     [rsi+rax*8+6A0h], rbp
0x140165cda  jz      short loc_140165CE3
0x140165cdc  add     cl, dl
0x140165cde  cmp     cl, 40h ; '@'
0x140165ce1  jbe     short loc_140165CCF
0x140165ce3  mov     rax, 2540BE400h
0x140165ced  mov     [rbx+2A8h], cl
0x140165cf3  mov     [rbx+2E8h], rax
0x140165cfa  lea     rcx, [rbx+0B0h]; Event
0x140165d01  mov     [rbx+2F0h], rax
0x140165d08  xor     r8d, r8d; State
0x140165d0b  or      eax, 0FFFFFFFFh
0x140165d0e  mov     [rbx+0AAh], dx
0x140165d15  mov     [rbx+2F8h], eax
0x140165d1b  xor     edx, edx; Type
0x140165d1d  mov     [rbx+2FCh], eax
0x140165d23  lea     rax, [rbx+50h]
0x140165d27  mov     [rbx+48h], rax
0x140165d2b  lea     rax, [rbx+2C8h]
0x140165d32  mov     [rbx+2E0h], ebp
0x140165d38  mov     word ptr [rbx+42h], 4Eh ; 'N'
0x140165d3e  mov     [rax+8], rax
0x140165d42  mov     [rax], rax
0x140165d45  call    cs:__imp_KeInitializeEvent
0x140165d4c  nop     dword ptr [rax+rax+00h]
0x140165d51  mov     [rbx+0A4h], r13w
0x140165d59  lea     r15, [rbx+28h]
0x140165d5d  mov     eax, [r14]
0x140165d60  lea     rbp, [rbx+30h]
0x140165d64  mov     [r15], eax
0x140165d67  lea     rdx, [rsp+0C8h+GuidString]; GuidString
0x140165d6c  movzx   eax, word ptr [r14+4]
0x140165d71  mov     rcx, rbp; Guid
0x140165d74  mov     [r15+4], ax
0x140165d79  movaps  xmm0, xmmword ptr [r12]
0x140165d7e  movdqu  xmmword ptr [rbp+0], xmm0
0x140165d83  call    cs:__imp_RtlStringFromGUID
0x140165d8a  nop     dword ptr [rax+rax+00h]
0x140165d8f  mov     ecx, eax
0x140165d91  call    cs:__imp_NdisConvertNtStatusToNdisStatus
0x140165d98  nop     dword ptr [rax+rax+00h]
0x140165d9d  mov     edi, eax
0x140165d9f  test    eax, eax
0x140165da1  jz      short loc_140165DCC
0x140165da3  mov     rcx, cs:VmsIfrLog
0x140165daa  mov     r9d, 29h ; ')'
0x140165db0  mov     dword ptr [rsp+0C8h+var_98], eax
0x140165db4  lea     rax, WPP_a2c0a6227fb63d778eade1329930ec3e_Traceguids
0x140165dbb  mov     [rsp+0C8h+var_A0], rbp
0x140165dc0  mov     [rsp+0C8h+var_A8], rax
0x140165dc5  call    WPP_RECORDER_SF__guid_d
0x140165dca  jmp     short loc_140165E21
0x140165dcc  lea     rcx, [rbx+40h]; DestinationString
0x140165dd0  lea     rdx, [rsp+0C8h+GuidString]; SourceString
0x140165dd5  call    cs:__imp_RtlCopyUnicodeString
0x140165ddc  nop     dword ptr [rax+rax+00h]
0x140165de1  mov     rcx, cs:WPP_GLOBAL_Control
0x140165de8  mov     al, [rcx+29h]
0x140165deb  dec     al
0x140165ded  cmp     al, 2
0x140165def  ja      short loc_140165DF9
0x140165df1  xor     eax, eax
0x140165df3  cmp     [rcx+48h], ax
0x140165df7  jz      short loc_140165E21
0x140165df9  movzx   eax, byte ptr [rbx+2A8h]
0x140165e00  mov     rcx, [rcx+40h]
0x140165e04  mov     [rsp+0C8h+var_80], r15
0x140165e09  mov     [rsp+0C8h+var_88], rbp
0x140165e0e  mov     dword ptr [rsp+0C8h+var_90], eax
0x140165e12  mov     [rsp+0C8h+var_98], rbx
0x140165e17  mov     [rsp+0C8h+var_A0], rsi
0x140165e1c  call    WPP_RECORDER_SF_qqd_guid__MAC_
0x140165e21  mov     r15, [rsp+0C8h+var_68]
0x140165e26  xor     ebp, ebp
0x140165e28  cmp     [rsp+0C8h+GuidString.Buffer], rbp
0x140165e2d  jz      short loc_140165E40
0x140165e2f  lea     rcx, [rsp+0C8h+GuidString]; UnicodeString
0x140165e34  call    cs:__imp_RtlFreeUnicodeString
0x140165e3b  nop     dword ptr [rax+rax+00h]
0x140165e40  test    edi, edi
0x140165e42  jz      short loc_140165E77
0x140165e44  test    rbx, rbx
0x140165e47  jz      short loc_140165E57
0x140165e49  mov     rdx, rbx
0x140165e4c  mov     rcx, rsi
0x140165e4f  call    lbfoDestroyNicObject
0x140165e54  mov     rbx, rbp
0x140165e57  mov     [rsp+0C8h+var_70], edi
0x140165e5b  mov     [rsp+0C8h+var_78], r13w
0x140165e61  mov     [rsp+0C8h+var_90], r14
0x140165e66  mov     [rsp+0C8h+var_98], r12
0x140165e6b  mov     [rsp+0C8h+var_A0], rsi
0x140165e70  call    WPP_RECORDER_SF_q_guid__MAC_IIHd
0x140165e75  jmp     short loc_140165E99
0x140165e77  test    rbx, rbx
0x140165e7a  jz      short loc_140165E99
0x140165e7c  test    byte ptr cs:Microsoft_Windows_Hyper_V_VmSwitchEnableBits+2, 20h
0x140165e83  jz      short loc_140165E99
0x140165e85  lea     r9, [rbx+30h]
0x140165e89  mov     dword ptr [rsp+0C8h+var_A8], ebp
0x140165e8d  lea     rdx, MemberCreatedInfo
0x140165e94  call    McTemplateK0jd_EtwWriteTransfer
0x140165e99  mov     [r15], rbx
0x140165e9c  mov     eax, edi
0x140165e9e  mov     rbx, [rsp+0C8h+arg_18]
0x140165ea6  add     rsp, 90h
0x140165ead  pop     r15
0x140165eaf  pop     r14
0x140165eb1  pop     r13
0x140165eb3  pop     r12
0x140165eb5  pop     rdi
0x140165eb6  pop     rsi
0x140165eb7  pop     rbp
0x140165eb8  retn
```
