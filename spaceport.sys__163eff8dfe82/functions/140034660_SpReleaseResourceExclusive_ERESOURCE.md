# SpReleaseResourceExclusive(_ERESOURCE *)

- ea: `0x140034660`
- end: `0x140034879`
- name: `?SpReleaseResourceExclusive@@YAXPEAU_ERESOURCE@@@Z`
- size: `537`
- prototype: `void __fastcall(PERESOURCE Resource)`
- caller_count: `60`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002cfa0`
- `0x14002e088`
- `0x1400338f0`
- `0x140034880`
- `0x1400393c8`
- `0x14003b9c0`
- `0x14003c260`
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
- `0x1400a22cc`
- `0x1400a63b8`
- `0x1400a84f0`
- `0x1400a86e0`
- `0x1400a8890`

## callees

- `0x14000200c`
- `0x140002ee0`
- `0x14002c3ec`
- `0x140034660`
- `0x140035ca0`
- `0x140068110`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400346db`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400346db`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140034763`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140034763`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400346cf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400346cf`
- `ntoskrnl!IoGetActivityIdThread` at `0x14003480e`
- `ntoskrnl!IoGetActivityIdThread` at `0x14003480e`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400346a6`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400346a6`

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
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // [rsp+50h] [rbp-19h] BYREF
  int v16; // [rsp+54h] [rbp-15h] BYREF
  int v17; // [rsp+58h] [rbp-11h] BYREF
  int v18; // [rsp+5Ch] [rbp-Dh] BYREF
  ULONGLONG v19; // [rsp+60h] [rbp-9h] BYREF
  __int64 ActivityIdThread; // [rsp+68h] [rbp-1h] BYREF
  PVOID BackTrace[2]; // [rsp+70h] [rbp+7h] BYREF
  __int128 v22; // [rsp+80h] [rbp+17h]

  v2 = 0;
  *(_OWORD *)BackTrace = 0;
  v22 = 0;
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
          v22,
          SBYTE8(v22));
      if ( (unsigned int)dword_14007F050 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_14007F050, 0x400000000000LL) )
        {
          v15 = DWORD2(v22);
          v16 = v22;
          v17 = (int)BackTrace[1];
          v18 = (int)BackTrace[0];
          v19 = v2;
          ActivityIdThread = IoGetActivityIdThread(v11);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v12,
            (unsigned int)&unk_1400758C8,
            v13,
            v14,
            (__int64)&ActivityIdThread,
            (__int64)&v19,
            (__int64)&v18,
            (__int64)&v17,
            (__int64)&v16,
            (__int64)&v15);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140034660  push    rbp
0x140034662  push    rbx
0x140034663  push    rsi
0x140034664  push    rdi
0x140034665  lea     rbp, [rsp-3Fh]
0x14003466a  sub     rsp, 0A8h
0x140034671  mov     rax, cs:__security_cookie
0x140034678  xor     rax, rsp
0x14003467b  mov     [rbp+57h+var_30], rax
0x14003467f  mov     rdi, rcx
0x140034682  xorps   xmm0, xmm0
0x140034685  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003468c  xor     ebx, ebx
0x14003468e  movups  xmmword ptr [rbp+57h+BackTrace], xmm0
0x140034692  movups  [rbp+57h+var_40], xmm0
0x140034696  lea     rax, [rcx+60h]
0x14003469a  cmp     rdi, rax
0x14003469d  jnz     short loc_1400346CC
0x14003469f  mov     rbx, [rcx+0C8h]
0x1400346a6  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400346ad  nop     dword ptr [rax+rax+00h]
0x1400346b2  mov     rcx, rax
0x1400346b5  mov     rax, 346DC5D63886594Bh
0x1400346bf  sub     rcx, rbx
0x1400346c2  mul     rcx
0x1400346c5  mov     rbx, rdx
0x1400346c8  shr     rbx, 0Bh
0x1400346cc  mov     rcx, rdi; Resource
0x1400346cf  call    cs:__imp_ExReleaseResourceLite
0x1400346d6  nop     dword ptr [rax+rax+00h]
0x1400346db  call    cs:__imp_KeLeaveCriticalRegion
0x1400346e2  nop     dword ptr [rax+rax+00h]
0x1400346e7  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400346ee  add     rax, 60h ; '`'
0x1400346f2  cmp     rdi, rax
0x1400346f5  jnz     loc_140034860
0x1400346fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140034702  lea     rax, WPP_GLOBAL_Control
0x140034709  cmp     rcx, rax
0x14003470c  jz      short loc_140034733
0x14003470e  mov     eax, [rcx+2Ch]
0x140034711  test    al, 1
0x140034713  jz      short loc_140034733
0x140034715  cmp     byte ptr [rcx+29h], 3
0x140034719  jb      short loc_140034733
0x14003471b  mov     rcx, [rcx+18h]
0x14003471f  lea     r8, WPP_11a2794c3c7f381fe7bc9d8a5fd7594c_Traceguids
0x140034726  mov     edx, 24h ; '$'
0x14003472b  mov     r9, rbx
0x14003472e  call    WPP_SF_i
0x140034733  cmp     rbx, 7530h
0x14003473a  jbe     loc_140034860
0x140034740  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140034747  lea     r8, [rbp+57h+BackTrace]; BackTrace
0x14003474b  xor     r9d, r9d; BackTraceHash
0x14003474e  mov     rcx, [rax+8]
0x140034752  lea     edx, [r9+4]; FramesToCapture
0x140034756  mov     rdi, [rcx+18h]
0x14003475a  mov     esi, [rcx+20h]
0x14003475d  lea     ecx, [rdx-3]; FramesToSkip
0x140034760  add     rsi, rdi
0x140034763  call    cs:__imp_RtlCaptureStackBackTrace
0x14003476a  nop     dword ptr [rax+rax+00h]
0x14003476f  xor     ecx, ecx
0x140034771  mov     rax, [rbp+rcx*8+57h+BackTrace]
0x140034776  cmp     rax, rdi
0x140034779  jb      short loc_140034785
0x14003477b  cmp     rax, rsi
0x14003477e  jnb     short loc_140034785
0x140034780  sub     rax, rdi
0x140034783  jmp     short loc_140034787
0x140034785  xor     eax, eax
0x140034787  mov     [rbp+rcx*8+57h+BackTrace], rax
0x14003478c  inc     rcx
0x14003478f  cmp     rcx, 4
0x140034793  jnz     short loc_140034771
0x140034795  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x14003479c  jz      short loc_1400347C9
0x14003479e  mov     eax, dword ptr [rbp+57h+var_40+8]
0x1400347a1  lea     rdx, ResourceHold
0x1400347a8  mov     dword ptr [rsp+0C0h+var_88], eax
0x1400347ac  mov     r9, rbx
0x1400347af  mov     eax, dword ptr [rbp+57h+var_40]
0x1400347b2  mov     dword ptr [rsp+0C0h+var_90], eax
0x1400347b6  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x1400347b9  mov     dword ptr [rsp+0C0h+var_98], eax
0x1400347bd  mov     eax, dword ptr [rbp+57h+BackTrace]
0x1400347c0  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1400347c4  call    McTemplateK0xdddd_EtwWriteTransfer
0x1400347c9  mov     eax, cs:dword_14007F050
0x1400347cf  cmp     eax, 5
0x1400347d2  jbe     loc_140034860
0x1400347d8  mov     rdx, 400000000000h
0x1400347e2  lea     rcx, dword_14007F050
0x1400347e9  call    _tlgKeywordOn
0x1400347ee  test    al, al
0x1400347f0  jz      short loc_140034860
0x1400347f2  mov     eax, dword ptr [rbp+57h+var_40+8]
0x1400347f5  mov     [rbp+57h+var_70], eax
0x1400347f8  mov     eax, dword ptr [rbp+57h+var_40]
0x1400347fb  mov     [rbp+57h+var_6C], eax
0x1400347fe  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x140034801  mov     [rbp+57h+var_68], eax
0x140034804  mov     eax, dword ptr [rbp+57h+BackTrace]
0x140034807  mov     [rbp+57h+var_64], eax
0x14003480a  mov     [rbp+57h+var_60], rbx
0x14003480e  call    cs:__imp_IoGetActivityIdThread
0x140034815  nop     dword ptr [rax+rax+00h]
0x14003481a  mov     [rbp+57h+var_58], rax
0x14003481e  lea     rdx, unk_1400758C8
0x140034825  lea     rax, [rbp+57h+var_70]
0x140034829  mov     [rsp+0C0h+var_78], rax
0x14003482e  lea     rax, [rbp+57h+var_6C]
0x140034832  mov     [rsp+0C0h+var_80], rax
0x140034837  lea     rax, [rbp+57h+var_68]
0x14003483b  mov     [rsp+0C0h+var_88], rax
0x140034840  lea     rax, [rbp+57h+var_64]
0x140034844  mov     [rsp+0C0h+var_90], rax
0x140034849  lea     rax, [rbp+57h+var_60]
0x14003484d  mov     [rsp+0C0h+var_98], rax
0x140034852  lea     rax, [rbp+57h+var_58]
0x140034856  mov     [rsp+0C0h+var_A0], rax
0x14003485b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140034860  mov     rcx, [rbp+57h+var_30]
0x140034864  xor     rcx, rsp; StackCookie
0x140034867  call    __security_check_cookie
0x14003486c  add     rsp, 0A8h
0x140034873  pop     rdi
0x140034874  pop     rsi
0x140034875  pop     rbx
0x140034876  pop     rbp
0x140034877  retn
```
