# SpReleaseResourceExclusive(_ERESOURCE *)

- ea: `0x1400345a0`
- end: `0x1400347b9`
- name: `?SpReleaseResourceExclusive@@YAXPEAU_ERESOURCE@@@Z`
- size: `537`
- prototype: `void __fastcall(PERESOURCE Resource)`
- caller_count: `60`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002cfa0`
- `0x14002e088`
- `0x140033840`
- `0x1400347c0`
- `0x140039308`
- `0x14003b900`
- `0x14003c1a0`
- `0x14008d55c`
- `0x14008dd50`
- `0x140091470`
- `0x1400917e0`
- `0x1400918a4`
- `0x1400927e0`
- `0x140092fbc`
- `0x14009365c`
- `0x140093b94`
- `0x140093f68`
- `0x140094274`
- `0x1400944b8`
- `0x1400949b8`
- `0x14009665c`
- `0x1400967bc`
- `0x14009697c`
- `0x140096e90`
- `0x140097280`
- `0x140097518`
- `0x140097bdc`
- `0x140097d58`
- `0x1400985a0`
- `0x140098760`
- `0x14009882c`
- `0x140098cd8`
- `0x14009905c`
- `0x1400991dc`
- `0x1400997a8`
- `0x140099dc8`
- `0x14009a4d4`
- `0x14009aa74`
- `0x14009b578`
- `0x14009b648`
- `0x14009b874`
- `0x14009ba5c`
- `0x14009bbbc`
- `0x14009be10`
- `0x14009bf7c`
- `0x1400a219c`
- `0x1400a6288`
- `0x1400a8360`
- `0x1400a8550`
- `0x1400a8700`

## callees

- `0x14000200c`
- `0x140002ee0`
- `0x14002c3ec`
- `0x1400345a0`
- `0x140035be0`
- `0x140067fc0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003461b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003461b`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400346a3`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400346a3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003460f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003460f`
- `ntoskrnl!IoGetActivityIdThread` at `0x14003474e`
- `ntoskrnl!IoGetActivityIdThread` at `0x14003474e`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400345e6`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400345e6`

## pseudocode

```c
void __fastcall SpReleaseResourceExclusive(PERESOURCE Resource)
{
  ULONGLONG v2; // rbx
  __int64 v3; // rbx
  __int64 v4; // rcx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rsi
  int v7; // r8d
  __int64 i; // rcx
  char *v9; // rax
  char *v10; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // [rsp+50h] [rbp-19h] BYREF
  int v15; // [rsp+54h] [rbp-15h] BYREF
  int v16; // [rsp+58h] [rbp-11h] BYREF
  int v17; // [rsp+5Ch] [rbp-Dh] BYREF
  ULONGLONG v18; // [rsp+60h] [rbp-9h] BYREF
  __int64 ActivityIdThread; // [rsp+68h] [rbp-1h] BYREF
  PVOID BackTrace[2]; // [rsp+70h] [rbp+7h] BYREF
  __int128 v21; // [rsp+80h] [rbp+17h]

  v2 = 0;
  *(_OWORD *)BackTrace = 0;
  v21 = 0;
  if ( Resource == (PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96) )
  {
    v3 = *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 25);
    v2 = (KeQueryUnbiasedInterruptTime() - v3) / 0x2710;
  }
  ExReleaseResourceLite(Resource);
  KeLeaveCriticalRegion();
  if ( Resource == (PERESOURCE)((char *)WPP_MAIN_CB.DeviceExtension + 96) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids, v2);
    }
    if ( v2 > 0x7530 )
    {
      v4 = *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1);
      v5 = *(_QWORD *)(v4 + 24);
      v6 = v5 + *(unsigned int *)(v4 + 32);
      RtlCaptureStackBackTrace(1u, 4u, BackTrace, 0);
      for ( i = 0; i != 4; ++i )
      {
        v9 = (char *)BackTrace[i];
        if ( (unsigned __int64)v9 < v5 || (unsigned __int64)v9 >= v6 )
          v10 = 0;
        else
          v10 = &v9[-v5];
        BackTrace[i] = v10;
      }
      if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
        McTemplateK0xdddd_EtwWriteTransfer(
          4,
          (unsigned int)ResourceHold,
          v7,
          v2,
          (char)BackTrace[0],
          (char)BackTrace[1],
          v21,
          SBYTE8(v21));
      if ( (unsigned int)dword_14007F050 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_14007F050, 0x400000000000LL) )
        {
          v14 = DWORD2(v21);
          v15 = v21;
          v16 = (int)BackTrace[1];
          v17 = (int)BackTrace[0];
          v18 = v2;
          ActivityIdThread = IoGetActivityIdThread();
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v11,
            (unsigned int)&unk_1400758C8,
            v12,
            v13,
            (__int64)&ActivityIdThread,
            (__int64)&v18,
            (__int64)&v17,
            (__int64)&v16,
            (__int64)&v15,
            (__int64)&v14);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1400345a0  push    rbp
0x1400345a2  push    rbx
0x1400345a3  push    rsi
0x1400345a4  push    rdi
0x1400345a5  lea     rbp, [rsp-3Fh]
0x1400345aa  sub     rsp, 0A8h
0x1400345b1  mov     rax, cs:__security_cookie
0x1400345b8  xor     rax, rsp
0x1400345bb  mov     [rbp+57h+var_30], rax
0x1400345bf  mov     rdi, rcx
0x1400345c2  xorps   xmm0, xmm0
0x1400345c5  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x1400345cc  xor     ebx, ebx
0x1400345ce  movups  xmmword ptr [rbp+57h+BackTrace], xmm0
0x1400345d2  movups  [rbp+57h+var_40], xmm0
0x1400345d6  lea     rax, [rcx+60h]
0x1400345da  cmp     rdi, rax
0x1400345dd  jnz     short loc_14003460C
0x1400345df  mov     rbx, [rcx+0C8h]
0x1400345e6  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400345ed  nop     dword ptr [rax+rax+00h]
0x1400345f2  mov     rcx, rax
0x1400345f5  mov     rax, 346DC5D63886594Bh
0x1400345ff  sub     rcx, rbx
0x140034602  mul     rcx
0x140034605  mov     rbx, rdx
0x140034608  shr     rbx, 0Bh
0x14003460c  mov     rcx, rdi; Resource
0x14003460f  call    cs:__imp_ExReleaseResourceLite
0x140034616  nop     dword ptr [rax+rax+00h]
0x14003461b  call    cs:__imp_KeLeaveCriticalRegion
0x140034622  nop     dword ptr [rax+rax+00h]
0x140034627  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003462e  add     rax, 60h ; '`'
0x140034632  cmp     rdi, rax
0x140034635  jnz     loc_1400347A0
0x14003463b  mov     rcx, cs:WPP_GLOBAL_Control
0x140034642  lea     rax, WPP_GLOBAL_Control
0x140034649  cmp     rcx, rax
0x14003464c  jz      short loc_140034673
0x14003464e  mov     eax, [rcx+2Ch]
0x140034651  test    al, 1
0x140034653  jz      short loc_140034673
0x140034655  cmp     byte ptr [rcx+29h], 3
0x140034659  jb      short loc_140034673
0x14003465b  mov     rcx, [rcx+18h]
0x14003465f  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x140034666  mov     edx, 24h ; '$'
0x14003466b  mov     r9, rbx
0x14003466e  call    WPP_SF_i
0x140034673  cmp     rbx, 7530h
0x14003467a  jbe     loc_1400347A0
0x140034680  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140034687  lea     r8, [rbp+57h+BackTrace]; BackTrace
0x14003468b  xor     r9d, r9d; BackTraceHash
0x14003468e  mov     rcx, [rax+8]
0x140034692  lea     edx, [r9+4]; FramesToCapture
0x140034696  mov     rdi, [rcx+18h]
0x14003469a  mov     esi, [rcx+20h]
0x14003469d  lea     ecx, [rdx-3]; FramesToSkip
0x1400346a0  add     rsi, rdi
0x1400346a3  call    cs:__imp_RtlCaptureStackBackTrace
0x1400346aa  nop     dword ptr [rax+rax+00h]
0x1400346af  xor     ecx, ecx
0x1400346b1  mov     rax, [rbp+rcx*8+57h+BackTrace]
0x1400346b6  cmp     rax, rdi
0x1400346b9  jb      short loc_1400346C5
0x1400346bb  cmp     rax, rsi
0x1400346be  jnb     short loc_1400346C5
0x1400346c0  sub     rax, rdi
0x1400346c3  jmp     short loc_1400346C7
0x1400346c5  xor     eax, eax
0x1400346c7  mov     [rbp+rcx*8+57h+BackTrace], rax
0x1400346cc  inc     rcx
0x1400346cf  cmp     rcx, 4
0x1400346d3  jnz     short loc_1400346B1
0x1400346d5  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x1400346dc  jz      short loc_140034709
0x1400346de  mov     eax, dword ptr [rbp+57h+var_40+8]
0x1400346e1  lea     rdx, ResourceHold
0x1400346e8  mov     dword ptr [rsp+0C0h+var_88], eax
0x1400346ec  mov     r9, rbx
0x1400346ef  mov     eax, dword ptr [rbp+57h+var_40]
0x1400346f2  mov     dword ptr [rsp+0C0h+var_90], eax
0x1400346f6  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x1400346f9  mov     dword ptr [rsp+0C0h+var_98], eax
0x1400346fd  mov     eax, dword ptr [rbp+57h+BackTrace]
0x140034700  mov     dword ptr [rsp+0C0h+var_A0], eax
0x140034704  call    McTemplateK0xdddd_EtwWriteTransfer
0x140034709  mov     eax, cs:dword_14007F050
0x14003470f  cmp     eax, 5
0x140034712  jbe     loc_1400347A0
0x140034718  mov     rdx, 400000000000h
0x140034722  lea     rcx, dword_14007F050
0x140034729  call    _tlgKeywordOn
0x14003472e  test    al, al
0x140034730  jz      short loc_1400347A0
0x140034732  mov     eax, dword ptr [rbp+57h+var_40+8]
0x140034735  mov     [rbp+57h+var_70], eax
0x140034738  mov     eax, dword ptr [rbp+57h+var_40]
0x14003473b  mov     [rbp+57h+var_6C], eax
0x14003473e  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x140034741  mov     [rbp+57h+var_68], eax
0x140034744  mov     eax, dword ptr [rbp+57h+BackTrace]
0x140034747  mov     [rbp+57h+var_64], eax
0x14003474a  mov     [rbp+57h+var_60], rbx
0x14003474e  call    cs:__imp_IoGetActivityIdThread
0x140034755  nop     dword ptr [rax+rax+00h]
0x14003475a  mov     [rbp+57h+var_58], rax
0x14003475e  lea     rdx, unk_1400758C8
0x140034765  lea     rax, [rbp+57h+var_70]
0x140034769  mov     [rsp+0C0h+var_78], rax
0x14003476e  lea     rax, [rbp+57h+var_6C]
0x140034772  mov     [rsp+0C0h+var_80], rax
0x140034777  lea     rax, [rbp+57h+var_68]
0x14003477b  mov     [rsp+0C0h+var_88], rax
0x140034780  lea     rax, [rbp+57h+var_64]
0x140034784  mov     [rsp+0C0h+var_90], rax
0x140034789  lea     rax, [rbp+57h+var_60]
0x14003478d  mov     [rsp+0C0h+var_98], rax
0x140034792  lea     rax, [rbp+57h+var_58]
0x140034796  mov     [rsp+0C0h+var_A0], rax
0x14003479b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400347a0  mov     rcx, [rbp+57h+var_30]
0x1400347a4  xor     rcx, rsp; StackCookie
0x1400347a7  call    __security_check_cookie
0x1400347ac  add     rsp, 0A8h
0x1400347b3  pop     rdi
0x1400347b4  pop     rsi
0x1400347b5  pop     rbx
0x1400347b6  pop     rbp
0x1400347b7  retn
```
