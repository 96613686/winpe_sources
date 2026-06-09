# CWwanPinSM::maybeUnlockPin(_WWAN_PIN_INFO *)

- ea: `0x18001ff9c`
- end: `0x180020538`
- name: `?maybeUnlockPin@CWwanPinSM@@AEAAKPEAU_WWAN_PIN_INFO@@@Z`
- size: `1436`
- prototype: `unsigned int __fastcall(CWwanPinSM *__hidden this, struct _WWAN_PIN_INFO *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task`

## callers

- `0x180020bd4`

## callees

- `0x18000153c`
- `0x180001818`
- `0x1800085d0`
- `0x1800094f4`
- `0x18001077c`
- `0x180012300`
- `0x180014f1c`
- `0x180018abc`
- `0x18001f380`
- `0x18001ff9c`
- `0x180073684`
- `0x1800769a4`
- `0x180076a5c`
- `0x18008aa84`
- `0x1800b6a40`
- `0x1800c858c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020257`
- `CRYPT32!CryptUnprotectMemory` at `0x180020249`
- `CRYPT32!CryptUnprotectMemory` at `0x180020249`

## string_xrefs

- `0x180020029`: ` Unexpected: We're processing a PIN response, but the device readyObject status is: (0x%08x)`
- `0x18002004d`: ` Not attempting auto-PIN-unlock.  Device is not locked.`
- `0x180020077`: ` Not attempting auto-PIN-unlock.  AttemptsRemaining is below threshold: %u < %u`
- `0x1800200d8`: ` Not attempting auto-PIN-unlock.  PIN types don't match.`
- `0x1800201da`: ` Attempting auto-PIN-unlock.`
- `0x180020327`: `Attempt to auto-unlock PIN failed: %u`
- `0x18002038c`: `Attempt to auto-unlock PIN succeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWwanPinSM::maybeUnlockPin(CWwanPinSM *this, struct _WWAN_PIN_INFO *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r9
  struct CWwanManager *Instance; // rax
  std::_Ref_count_base *v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rcx
  const WCHAR *v12; // r8
  __int64 v13; // r9
  const wchar_t *v14; // rsi
  char *v15; // r15
  int v16; // eax
  const struct _GUID *v17; // rdx
  CWwanManager *v18; // rax
  _BYTE *v19; // rax
  _BYTE *v20; // rsi
  rsize_t v22; // r14
  __int64 LastError; // rdi
  __int64 v24; // rcx
  const WCHAR *v25; // r8
  __int64 v26; // r9
  const WCHAR *v27; // rax
  char *v28; // rdx
  unsigned int v29; // eax
  __int64 v30; // rcx
  _BYTE *v31; // rax
  __int64 v32; // rcx
  const WCHAR *v33; // r8
  __int64 v34; // r9
  const WCHAR *v35; // [rsp+40h] [rbp-59h] BYREF
  __int64 v36; // [rsp+48h] [rbp-51h] BYREF
  const WCHAR *v37; // [rsp+50h] [rbp-49h] BYREF
  std::_Ref_count_base *v38[2]; // [rsp+58h] [rbp-41h] BYREF
  _DWORD v39[2]; // [rsp+70h] [rbp-29h] BYREF
  _OWORD v40[2]; // [rsp+78h] [rbp-21h] BYREF
  __int16 v41; // [rsp+98h] [rbp-1h]

  *(_OWORD *)v38 = 0;
  if ( !CWwanInterface::IsVersionBlueOrHigher((CWwanPinSM *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8)) )
  {
    WwanLog::Info(
      "CWwanPinSM::maybeUnlockPin",
      (const struct _GUID *)v5,
      L" Automatic PIN unlock is not supported for pre-WinBlue drivers. Version: %d.%d",
      *(unsigned int *)((char *)this + v6 + 24),
      *(_DWORD *)(v5 + 20));
    return 0;
  }
  if ( *(_DWORD *)((char *)this + v6 + 152) )
  {
    WwanLog::Info(
      "CWwanPinSM::maybeUnlockPin",
      (const struct _GUID *)v5,
      L" Unexpected: We're processing a PIN response, but the device readyObject status is: (0x%08x)",
      *(unsigned int *)((char *)this + v6 + 152));
    return 0;
  }
  if ( *(_DWORD *)(v4 + 4) != 1 )
  {
    WwanLog::Info(
      "CWwanPinSM::maybeUnlockPin",
      (const struct _GUID *)v5,
      L" Not attempting auto-PIN-unlock.  Device is not locked.");
    return 0;
  }
  v7 = *(unsigned int *)(v4 + 8);
  if ( (unsigned int)v7 < 2 )
  {
    WwanLog::Info(
      "CWwanPinSM::maybeUnlockPin",
      (const struct _GUID *)v5,
      L" Not attempting auto-PIN-unlock.  AttemptsRemaining is below threshold: %u < %u",
      v7,
      2);
    return 0;
  }
  Instance = CWwanManager::GetInstance();
  if ( (unsigned int)CWwanManager::GetInterfacePinInfo(
                       Instance,
                       (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8,
                       v38)
    || (v9 = v38[0]) == 0
    || !*((_DWORD *)v38[0] + 14) )
  {
    WwanLog::Info(
      "CWwanPinSM::maybeUnlockPin",
      (const struct _GUID *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8),
      L" There is no stored PIN for this interface");
    if ( CServiceHandler::s_lLoggingRegistered >= 0 )
    {
      _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
      if ( (unsigned int)dword_180151040 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x400000000000LL) )
        {
          v37 = L"NoStoredPin";
          v36 = (__int64)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8;
          v35 = v33;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
            v32,
            (__int64)&byte_18013E23F,
            (__int64)v33,
            v34,
            (__int64)&v35,
            &v36,
            &v37);
        }
      }
    }
    goto LABEL_51;
  }
  v10 = *(int *)(*((_QWORD *)this + 1) + 4LL);
  if ( *(_DWORD *)a2 != *((_DWORD *)v38[0] + 1) )
  {
    WwanLog::Info(
      "CWwanPinSM::maybeUnlockPin",
      (const struct _GUID *)((char *)this + v10 + 8),
      L" Not attempting auto-PIN-unlock.  PIN types don't match.");
    if ( CServiceHandler::s_lLoggingRegistered >= 0 )
    {
      _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
      if ( (unsigned int)dword_180151040 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_180151040, 0x400000000000LL) )
        {
          v35 = L"PinTypesMismatch";
          v36 = (__int64)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8;
          v37 = v12;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
            v11,
            (__int64)word_18013E202,
            (__int64)v12,
            v13,
            (__int64)&v37,
            &v36,
            &v35);
        }
      }
    }
    goto LABEL_51;
  }
  v14 = (const wchar_t *)((char *)this + v10 + 80);
  v15 = (char *)this + v10;
  v16 = wcsncmp_0((const wchar_t *)v38[0] + 4, v14, 0x15u);
  v17 = (const struct _GUID *)(v15 + 8);
  if ( v16 )
  {
    WwanLog::Info(
      "CWwanPinSM::maybeUnlockPin",
      v17,
      L" The ICCID associated with this interface has changed. \"%ws\" --> \"%ws\"",
      (char *)v9 + 8,
      v14);
    v18 = CWwanManager::GetInstance();
    CWwanManager::ClearInterfacePinInfo(
      v18,
      (const struct _GUID *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8));
LABEL_51:
    if ( v38[1] )
      std::_Ref_count_base::_Decref(v38[1]);
    return 0;
  }
  WwanLog::Info("CWwanPinSM::maybeUnlockPin", v17, L" Attempting auto-PIN-unlock.");
  memset_0(v39, 0, 0x50u);
  v39[0] = *((_DWORD *)v9 + 1);
  v39[1] = 0;
  v19 = (_BYTE *)WwanMemAlloc(*((unsigned int *)v9 + 14));
  v20 = v19;
  if ( !v19 )
  {
    if ( v38[1] )
      std::_Ref_count_base::_Decref(v38[1]);
    return 8;
  }
  v22 = *((unsigned int *)v9 + 14);
  memcpy_s(v19, v22, *((const void *const *)v9 + 8), (unsigned int)v22);
  if ( CryptUnprotectMemory(v20, v22, 0)
    || (LastError = GetLastError(),
        WwanLog::Error(
          "CWwanPinSM::decryptPin",
          0,
          L"Could not unencrypt PIN - CryptUnprotectMemory failed: %u",
          LastError),
        !(_DWORD)LastError) )
  {
    v40[0] = *(_OWORD *)v20;
    v40[1] = *((_OWORD *)v20 + 1);
    v41 = *((_WORD *)v20 + 16);
    v29 = CWwanPinSM::DoSimPinAction(this, (struct _WWAN_PIN_ACTION *)v39, 0);
    LODWORD(LastError) = v29;
    if ( v29 )
    {
      WwanLog::Error("CWwanPinSM::maybeUnlockPin", 0, L"Attempt to auto-unlock PIN failed: %u", v29);
      if ( CServiceHandler::s_lLoggingRegistered < 0 )
        goto LABEL_40;
      _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
      if ( (unsigned int)dword_180151040 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_180151040, 0x400000000000LL) )
        goto LABEL_40;
      v27 = L"AutoUnlockFailed";
      v28 = (char *)&unk_18013E188;
    }
    else
    {
      WwanLog::Info("CWwanPinSM::maybeUnlockPin", 0, L"Attempt to auto-unlock PIN succeeded");
      if ( CServiceHandler::s_lLoggingRegistered < 0 )
        goto LABEL_40;
      _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
      if ( (unsigned int)dword_180151040 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_180151040, 0x400000000000LL) )
        goto LABEL_40;
      v27 = L"Succeeded";
      v28 = byte_18013E14B;
    }
  }
  else
  {
    WwanLog::Error("CWwanPinSM::maybeUnlockPin", 0, L"PIN decryption failed: %u", (unsigned int)LastError);
    if ( CServiceHandler::s_lLoggingRegistered < 0 )
      goto LABEL_40;
    _InterlockedIncrement64((volatile signed __int64 *)&g_TelemetrySequenceNumber);
    if ( (unsigned int)dword_180151040 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_180151040, 0x400000000000LL) )
      goto LABEL_40;
    v27 = L"PinDecryptionError";
    v28 = byte_18013E1C5;
  }
  v37 = v27;
  v36 = (__int64)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8;
  v35 = v25;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
    v24,
    (__int64)v28,
    (__int64)v25,
    v26,
    (__int64)&v35,
    &v36,
    &v37);
LABEL_40:
  while ( v22 )
  {
    *v20++ = 0;
    --v22;
  }
  v30 = 34;
  v31 = v40;
  do
  {
    *v31++ = 0;
    --v30;
  }
  while ( v30 );
  if ( v38[1] )
    std::_Ref_count_base::_Decref(v38[1]);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001ff9c  mov     [rsp-8+arg_10], rbx
0x18001ffa1  mov     [rsp-8+arg_18], rsi
0x18001ffa6  push    rbp
0x18001ffa7  push    rdi
0x18001ffa8  push    r13
0x18001ffaa  push    r14
0x18001ffac  push    r15
0x18001ffae  lea     rbp, [rsp-37h]
0x18001ffb3  sub     rsp, 0D0h
0x18001ffba  mov     rax, cs:__security_cookie
0x18001ffc1  xor     rax, rsp
0x18001ffc4  mov     [rbp+57h+var_30], rax
0x18001ffc8  mov     rsi, rdx
0x18001ffcb  mov     rbx, rcx
0x18001ffce  xorps   xmm0, xmm0
0x18001ffd1  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x18001ffd6  mov     rax, [rcx+8]
0x18001ffda  movsxd  r9, dword ptr [rax+4]
0x18001ffde  add     rcx, 8
0x18001ffe2  add     rcx, r9; this
0x18001ffe5  call    ?IsVersionBlueOrHigher@CWwanInterface@@QEBA_NXZ; CWwanInterface::IsVersionBlueOrHigher(void)
0x18001ffea  test    al, al
0x18001ffec  jnz     short loc_180020016
0x18001ffee  mov     eax, [rcx+14h]
0x18001fff1  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18001fff5  mov     r9d, [rbx+r9+18h]
0x18001fffa  lea     r8, aAutomaticPinUn; " Automatic PIN unlock is not supported "...
0x180020001  mov     rdx, rcx; struct _GUID *
0x180020004  lea     rcx, aCwwanpinsmMayb; "CWwanPinSM::maybeUnlockPin"
0x18002000b  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180020010  nop
0x180020011  jmp     loc_18002050E
0x180020016  cmp     dword ptr [rbx+r9+98h], 0
0x18002001f  jz      short loc_180020041
0x180020021  mov     r9d, [r9+rbx+98h]
0x180020029  lea     r8, aUnexpectedWeRe; " Unexpected: We're processing a PIN res"...
0x180020030  mov     rdx, rcx; struct _GUID *
0x180020033  lea     rcx, aCwwanpinsmMayb; "CWwanPinSM::maybeUnlockPin"
0x18002003a  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18002003f  jmp     short loc_180020011
0x180020041  mov     r13d, 1
0x180020047  cmp     [rdx+4], r13d
0x18002004b  jz      short loc_180020065
0x18002004d  lea     r8, aNotAttemptingA_0; " Not attempting auto-PIN-unlock.  Devic"...
0x180020054  mov     rdx, rcx; struct _GUID *
0x180020057  lea     rcx, aCwwanpinsmMayb; "CWwanPinSM::maybeUnlockPin"
0x18002005e  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180020063  jmp     short loc_180020011
0x180020065  mov     r9d, [rdx+8]
0x180020069  cmp     r9d, 2
0x18002006d  jnb     short loc_180020080
0x18002006f  mov     dword ptr [rsp+0F0h+var_D0], 2
0x180020077  lea     r8, aNotAttemptingA; " Not attempting auto-PIN-unlock.  Attem"...
0x18002007e  jmp     short loc_180020001
0x180020080  call    ?GetInstance@CWwanManager@@SAPEAV1@XZ; CWwanManager::GetInstance(void)
0x180020085  mov     rcx, [rbx+8]
0x180020089  movsxd  rdx, dword ptr [rcx+4]
0x18002008d  add     rdx, 8
0x180020091  add     rdx, rbx
0x180020094  lea     r8, [rbp+57h+var_98]
0x180020098  mov     rcx, rax
0x18002009b  call    ?GetInterfacePinInfo@CWwanManager@@QEAAKAEBU_GUID@@PEAV?$shared_ptr@U_WWAN_STORED_PIN_INFO@@@std@@@Z; CWwanManager::GetInterfacePinInfo(_GUID const &,std::shared_ptr<_WWAN_STORED_PIN_INFO> *)
0x1800200a0  test    eax, eax
0x1800200a2  jnz     loc_180020457
0x1800200a8  mov     rdi, [rbp+57h+var_98]
0x1800200ac  test    rdi, rdi
0x1800200af  jz      loc_180020457
0x1800200b5  cmp     [rdi+38h], eax
0x1800200b8  jz      loc_180020457
0x1800200be  mov     rax, [rbx+8]
0x1800200c2  movsxd  rcx, dword ptr [rax+4]
0x1800200c6  mov     eax, [rdi+4]
0x1800200c9  cmp     [rsi], eax
0x1800200cb  jz      loc_180020178
0x1800200d1  lea     rdx, [rbx+8]
0x1800200d5  add     rdx, rcx; struct _GUID *
0x1800200d8  lea     r8, aNotAttemptingA_1; " Not attempting auto-PIN-unlock.  PIN t"...
0x1800200df  lea     rcx, aCwwanpinsmMayb; "CWwanPinSM::maybeUnlockPin"
0x1800200e6  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800200eb  cmp     cs:?s_lLoggingRegistered@CServiceHandler@@0JA, 0; long CServiceHandler::s_lLoggingRegistered
0x1800200f2  jl      loc_180020500
0x1800200f8  mov     r8, r13
0x1800200fb  lock xadd cs:?g_TelemetrySequenceNumber@@3_KA, r8; unsigned __int64 g_TelemetrySequenceNumber
0x180020104  add     r8, r13
0x180020107  mov     eax, cs:dword_180151040
0x18002010d  cmp     eax, 5
0x180020110  jbe     loc_180020500
0x180020116  mov     rdx, 400000000000h
0x180020120  lea     rcx, dword_180151040
0x180020127  call    _tlgKeywordOn
0x18002012c  test    al, al
0x18002012e  jz      loc_180020500
0x180020134  lea     rax, aPintypesmismat; "PinTypesMismatch"
0x18002013b  mov     [rbp+57h+var_B0], rax
0x18002013f  mov     rax, [rbx+8]
0x180020143  movsxd  rax, dword ptr [rax+4]
0x180020147  add     rax, 8
0x18002014b  add     rax, rbx
0x18002014e  mov     [rbp+57h+var_A8], rax
0x180020152  mov     [rbp+57h+var_A0], r8
0x180020156  lea     rax, [rbp+57h+var_B0]
0x18002015a  mov     [rsp+0F0h+var_C0], rax
0x18002015f  lea     rax, [rbp+57h+var_A8]
0x180020163  mov     [rsp+0F0h+var_C8], rax
0x180020168  lea     rax, [rbp+57h+var_A0]
0x18002016c  lea     rdx, word_18013E202
0x180020173  jmp     loc_1800204F5
0x180020178  lea     rsi, [rbx+50h]
0x18002017c  add     rsi, rcx
0x18002017f  lea     r15, [rcx+rbx]
0x180020183  mov     r8d, 15h; MaxCount
0x180020189  mov     rdx, rsi; String2
0x18002018c  lea     rcx, [rdi+8]; String1
0x180020190  call    wcsncmp_0
0x180020195  lea     rdx, [r15+8]; struct _GUID *
0x180020199  lea     rcx, aCwwanpinsmMayb; "CWwanPinSM::maybeUnlockPin"
0x1800201a0  test    eax, eax
0x1800201a2  jz      short loc_1800201DA
0x1800201a4  mov     [rsp+0F0h+var_D0], rsi
0x1800201a9  lea     r9, [rdi+8]
0x1800201ad  lea     r8, aTheIccidAssoci; " The ICCID associated with this interfa"...
0x1800201b4  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800201b9  call    ?GetInstance@CWwanManager@@SAPEAV1@XZ; CWwanManager::GetInstance(void)
0x1800201be  mov     rcx, [rbx+8]
0x1800201c2  movsxd  rdx, dword ptr [rcx+4]
0x1800201c6  add     rdx, 8
0x1800201ca  add     rdx, rbx; struct _GUID *
0x1800201cd  mov     rcx, rax; this
0x1800201d0  call    ?ClearInterfacePinInfo@CWwanManager@@QEAAXAEBU_GUID@@@Z; CWwanManager::ClearInterfacePinInfo(_GUID const &)
0x1800201d5  jmp     loc_180020500
0x1800201da  lea     r8, aAttemptingAuto; " Attempting auto-PIN-unlock."
0x1800201e1  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800201e6  xor     edx, edx; Val
0x1800201e8  lea     r8d, [rdx+50h]; Size
0x1800201ec  lea     rcx, [rbp+57h+var_80]; void *
0x1800201f0  call    memset_0
0x1800201f5  mov     eax, [rdi+4]
0x1800201f8  mov     [rbp+57h+var_80], eax
0x1800201fb  mov     [rbp+57h+var_7C], 0
0x180020202  mov     ecx, [rdi+38h]; Size
0x180020205  call    WwanMemAlloc
0x18002020a  mov     rsi, rax
0x18002020d  test    rax, rax
0x180020210  jnz     short loc_18002022A
0x180020212  mov     rcx, [rbp+57h+var_98+8]; this
0x180020216  test    rcx, rcx
0x180020219  jz      short loc_180020220
0x18002021b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180020220  mov     eax, 8
0x180020225  jmp     loc_180020510
0x18002022a  mov     r14d, [rdi+38h]
0x18002022e  mov     r9d, r14d; SourceSize
0x180020231  mov     r8, [rdi+40h]; Source
0x180020235  mov     edx, r14d; DestinationSize
0x180020238  mov     rcx, rsi; Destination
0x18002023b  call    memcpy_s
0x180020240  xor     r8d, r8d; dwFlags
0x180020243  mov     edx, r14d; cbDataIn
0x180020246  mov     rcx, rsi; pDataIn
0x180020249  call    cs:__imp_CryptUnprotectMemory
0x18002024f  test    eax, eax
0x180020251  jnz     loc_1800202EF
0x180020257  call    cs:__imp_GetLastError
0x18002025d  mov     edi, eax
0x18002025f  mov     r9d, eax
0x180020262  lea     r8, aCouldNotUnencr; "Could not unencrypt PIN - CryptUnprotec"...
0x180020269  xor     edx, edx; struct _GUID *
0x18002026b  lea     rcx, aCwwanpinsmDecr; "CWwanPinSM::decryptPin"
0x180020272  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180020277  test    edi, edi
0x180020279  jz      short loc_1800202EF
0x18002027b  mov     r9d, edi
0x18002027e  lea     r8, aPinDecryptionF; "PIN decryption failed: %u"
0x180020285  xor     edx, edx; struct _GUID *
0x180020287  lea     rcx, aCwwanpinsmMayb; "CWwanPinSM::maybeUnlockPin"
0x18002028e  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180020293  cmp     cs:?s_lLoggingRegistered@CServiceHandler@@0JA, 0; long CServiceHandler::s_lLoggingRegistered
0x18002029a  jl      loc_18002041E
0x1800202a0  mov     r8, r13
0x1800202a3  lock xadd cs:?g_TelemetrySequenceNumber@@3_KA, r8; unsigned __int64 g_TelemetrySequenceNumber
0x1800202ac  add     r8, r13
0x1800202af  mov     eax, cs:dword_180151040
0x1800202b5  cmp     eax, 5
0x1800202b8  jbe     loc_18002041E
0x1800202be  mov     rdx, 400000000000h
0x1800202c8  lea     rcx, dword_180151040
0x1800202cf  call    _tlgKeywordOn
0x1800202d4  test    al, al
0x1800202d6  jz      loc_18002041E
0x1800202dc  lea     rax, aPindecryptione; "PinDecryptionError"
0x1800202e3  lea     rdx, byte_18013E1C5
0x1800202ea  jmp     loc_1800203E3
0x1800202ef  movups  xmm0, xmmword ptr [rsi]
0x1800202f2  movups  [rbp+57h+var_78], xmm0
0x1800202f6  movups  xmm1, xmmword ptr [rsi+10h]
0x1800202fa  movups  [rbp+57h+var_68], xmm1
0x1800202fe  movzx   eax, word ptr [rsi+20h]
0x180020302  mov     [rbp+57h+var_58], ax
0x180020306  xor     r8d, r8d; unsigned int *
0x180020309  lea     rdx, [rbp+57h+var_80]; struct _WWAN_PIN_ACTION *
0x18002030d  mov     rcx, rbx; this
0x180020310  call    ?DoSimPinAction@CWwanPinSM@@QEAAKPEAU_WWAN_PIN_ACTION@@PEAK@Z; CWwanPinSM::DoSimPinAction(_WWAN_PIN_ACTION *,ulong *)
0x180020315  mov     edi, eax
0x180020317  xor     edx, edx; struct _GUID *
0x180020319  lea     rcx, aCwwanpinsmMayb; "CWwanPinSM::maybeUnlockPin"
0x180020320  test    eax, eax
0x180020322  jz      short loc_18002038C
0x180020324  mov     r9d, eax
0x180020327  lea     r8, aAttemptToAutoU_0; "Attempt to auto-unlock PIN failed: %u"
0x18002032e  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180020333  cmp     cs:?s_lLoggingRegistered@CServiceHandler@@0JA, 0; long CServiceHandler::s_lLoggingRegistered
0x18002033a  jl      loc_18002041E
0x180020340  mov     r8, r13
0x180020343  lock xadd cs:?g_TelemetrySequenceNumber@@3_KA, r8; unsigned __int64 g_TelemetrySequenceNumber
0x18002034c  add     r8, r13
0x18002034f  mov     eax, cs:dword_180151040
0x180020355  cmp     eax, 5
0x180020358  jbe     loc_18002041E
0x18002035e  mov     rdx, 400000000000h
0x180020368  lea     rcx, dword_180151040
0x18002036f  call    _tlgKeywordOn
0x180020374  test    al, al
0x180020376  jz      loc_18002041E
0x18002037c  lea     rax, aAutounlockfail; "AutoUnlockFailed"
0x180020383  lea     rdx, unk_18013E188
0x18002038a  jmp     short loc_1800203E3
0x18002038c  lea     r8, aAttemptToAutoU; "Attempt to auto-unlock PIN succeeded"
0x180020393  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180020398  cmp     cs:?s_lLoggingRegistered@CServiceHandler@@0JA, 0; long CServiceHandler::s_lLoggingRegistered
0x18002039f  jl      short loc_18002041E
0x1800203a1  mov     r8, r13
0x1800203a4  lock xadd cs:?g_TelemetrySequenceNumber@@3_KA, r8; unsigned __int64 g_TelemetrySequenceNumber
0x1800203ad  add     r8, r13
0x1800203b0  mov     eax, cs:dword_180151040
0x1800203b6  cmp     eax, 5
0x1800203b9  jbe     short loc_18002041E
0x1800203bb  mov     rdx, 400000000000h
0x1800203c5  lea     rcx, dword_180151040
0x1800203cc  call    _tlgKeywordOn
0x1800203d1  test    al, al
0x1800203d3  jz      short loc_18002041E
0x1800203d5  lea     rax, aSucceeded; "Succeeded"
0x1800203dc  lea     rdx, byte_18013E14B
0x1800203e3  mov     [rbp+57h+var_A0], rax
0x1800203e7  mov     rax, [rbx+8]
0x1800203eb  movsxd  rax, dword ptr [rax+4]
0x1800203ef  add     rax, 8
0x1800203f3  add     rax, rbx
0x1800203f6  mov     [rbp+57h+var_A8], rax
0x1800203fa  lea     rax, [rbp+57h+var_A0]
0x1800203fe  mov     [rsp+0F0h+var_C0], rax
0x180020403  lea     rax, [rbp+57h+var_A8]
0x180020407  mov     [rsp+0F0h+var_C8], rax
0x18002040c  lea     rax, [rbp+57h+var_B0]
0x180020410  mov     [rsp+0F0h+var_D0], rax
0x180020415  mov     [rbp+57h+var_B0], r8
0x180020419  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &)
0x18002041e  test    r14, r14
0x180020421  jz      short loc_18002042E
0x180020423  mov     byte ptr [rsi], 0
0x180020426  add     rsi, r13
0x180020429  sub     r14, r13
0x18002042c  jnz     short loc_180020423
0x18002042e  mov     ecx, 22h ; '"'
0x180020433  lea     rax, [rbp+57h+var_78]
0x180020437  mov     byte ptr [rax], 0
0x18002043a  add     rax, r13
0x18002043d  sub     rcx, r13
0x180020440  jnz     short loc_180020437
0x180020442  mov     rcx, [rbp+57h+var_98+8]; this
0x180020446  test    rcx, rcx
0x180020449  jz      short loc_180020450
0x18002044b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180020450  mov     eax, edi
0x180020452  jmp     loc_180020510
0x180020457  mov     rax, [rbx+8]
0x18002045b  movsxd  rdx, dword ptr [rax+4]
0x18002045f  add     rdx, 8
0x180020463  add     rdx, rbx; struct _GUID *
0x180020466  lea     r8, aThereIsNoStore; " There is no stored PIN for this interf"...
0x18002046d  lea     rcx, aCwwanpinsmMayb; "CWwanPinSM::maybeUnlockPin"
0x180020474  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180020479  cmp     cs:?s_lLoggingRegistered@CServiceHandler@@0JA, 0; long CServiceHandler::s_lLoggingRegistered
0x180020480  jl      short loc_180020500
0x180020482  mov     r8, r13
0x180020485  lock xadd cs:?g_TelemetrySequenceNumber@@3_KA, r8; unsigned __int64 g_TelemetrySequenceNumber
0x18002048e  add     r8, r13
0x180020491  mov     eax, cs:dword_180151040
0x180020497  cmp     eax, 5
0x18002049a  jbe     short loc_180020500
0x18002049c  mov     rdx, 400000000000h
0x1800204a6  lea     rcx, dword_180151040
0x1800204ad  call    _tlgKeywordOn
0x1800204b2  test    al, al
0x1800204b4  jz      short loc_180020500
0x1800204b6  lea     rax, aNostoredpin; "NoStoredPin"
0x1800204bd  mov     [rbp+57h+var_A0], rax
0x1800204c1  mov     rax, [rbx+8]
0x1800204c5  movsxd  rax, dword ptr [rax+4]
0x1800204c9  add     rax, 8
  ... truncated ...
```
