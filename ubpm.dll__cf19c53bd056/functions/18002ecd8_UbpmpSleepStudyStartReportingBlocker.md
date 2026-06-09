# UbpmpSleepStudyStartReportingBlocker

- ea: `0x18002ecd8`
- end: `0x18002eee5`
- name: `UbpmpSleepStudyStartReportingBlocker`
- size: `525`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18002ea04`
- `0x18002ef50`

## callees

- `0x18000141c`
- `0x1800096e0`
- `0x18000f9a0`
- `0x180019d90`
- `0x18002990c`
- `0x18002b640`
- `0x18002ecd8`
- `0x18003d7de`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002edb9`
- `ntdll!RtlInitUnicodeString` at `0x18002edb9`
- `UMPDC!SleepstudyHelperBuildBlocker` at `0x18002edfd`
- `UMPDC!SleepstudyHelperBuildBlocker` at `0x18002edfd`
- `UMPDC!SleepstudyHelperCreateBlockerFromGuid` at `0x18002ede0`
- `UMPDC!SleepstudyHelperCreateBlockerFromGuid` at `0x18002ede0`
- `UMPDC!SleepstudyHelperBlockerActiveReference` at `0x18002ee1e`
- `UMPDC!SleepstudyHelperBlockerActiveReference` at `0x18002ee1e`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x18002ee43`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x18002ee43`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x18002ee53`
- `UMPDC!SleepstudyHelperDestroyBlockerBuilder` at `0x18002ee53`

## pseudocode

```c
__int64 __fastcall UbpmpSleepStudyStartReportingBlocker(
        __int64 a1,
        __int128 *a2,
        const WCHAR *a3,
        __int64 a4,
        _QWORD *a5)
{
  __int128 v9; // xmm0
  PCNZWCH ConsumerFriendlyName; // rbx
  unsigned __int16 *v11; // rsi
  int v12; // edi
  int v13; // ebx
  int v14; // eax
  __int64 v15; // rcx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  __int64 v20; // [rsp+40h] [rbp-A1h] BYREF
  __int64 v21; // [rsp+48h] [rbp-99h] BYREF
  int v22; // [rsp+50h] [rbp-91h] BYREF
  int v23; // [rsp+54h] [rbp-8Dh] BYREF
  __int64 v24; // [rsp+58h] [rbp-89h] BYREF
  const WCHAR *v25; // [rsp+60h] [rbp-81h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-79h] BYREF
  _DWORD v27[2]; // [rsp+78h] [rbp-69h] BYREF
  __int64 v28; // [rsp+80h] [rbp-61h]
  __int128 v29; // [rsp+88h] [rbp-59h] BYREF
  _BYTE v30[80]; // [rsp+A0h] [rbp-41h] BYREF

  v21 = 0;
  v20 = 0;
  DestinationString = 0;
  memset_0(v30, 0, 0x4Eu);
  v9 = *a2;
  v27[0] = -1428313379;
  v27[1] = 4;
  v29 = v9;
  v28 = 35;
  ConsumerFriendlyName = UbpmpGetConsumerFriendlyName(a3);
  v11 = (unsigned __int16 *)UbpmAlloc(0x1FEu);
  if ( v11 )
  {
    v14 = RtlStringCbPrintfW(v11, 0x1FEu, L"%s:%s", ConsumerFriendlyName, v30);
    if ( (int)(v14 + 0x80000000) >= 0 && v14 != -2147483643 )
      __int2c();
    RtlInitUnicodeString(&DestinationString, v11);
    v13 = SleepstudyHelperCreateBlockerFromGuid(a1, v27, &v29, &DestinationString, 4, &v21);
    if ( v13 >= 0 )
    {
      v13 = SleepstudyHelperBuildBlocker(v21, &v20);
      if ( v13 >= 0 )
      {
        v21 = 0;
        SleepstudyHelperBlockerActiveReference(v20);
        *a5 = v20;
        v12 = 0;
        v13 = 0;
        v20 = 0;
      }
      else
      {
        v12 = 30;
      }
    }
    else
    {
      v12 = 20;
    }
  }
  else
  {
    v12 = 10;
    v13 = -1073741664;
  }
  if ( v20 )
    SleepstudyHelperDestroyBlocker(v20);
  v15 = v21;
  if ( v21 )
    SleepstudyHelperDestroyBlockerBuilder();
  if ( v11 )
    UBPM_MIDL_user_free(v11);
  if ( (unsigned int)dword_18004C0F0 > 5 && (unsigned __int8)tlgKeywordOn(v15, 4) )
  {
    v22 = v13;
    v23 = v12;
    v24 = a4;
    v25 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v16,
      (unsigned int)byte_18004434B,
      v17,
      v18,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v22);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002ecd8  push    rbp
0x18002ecda  push    rbx
0x18002ecdb  push    rsi
0x18002ecdc  push    rdi
0x18002ecdd  push    r12
0x18002ecdf  push    r14
0x18002ece1  push    r15
0x18002ece3  lea     rbp, [rsp-1Fh]
0x18002ece8  sub     rsp, 100h
0x18002ecef  mov     rax, cs:__security_cookie
0x18002ecf6  xor     rax, rsp
0x18002ecf9  mov     [rbp+4Fh+var_40], rax
0x18002ecfd  mov     rdi, [rbp+4Fh+arg_20]
0x18002ed01  mov     rbx, rdx
0x18002ed04  xor     edx, edx; Val
0x18002ed06  mov     [rsp+130h+var_E8], 0
0x18002ed0f  mov     r15, r8
0x18002ed12  mov     [rsp+130h+var_F0], 0
0x18002ed1b  mov     r14, rcx
0x18002ed1e  xorps   xmm0, xmm0
0x18002ed21  lea     rcx, [rbp+4Fh+var_90]; void *
0x18002ed25  mov     r12, r9
0x18002ed28  lea     r8d, [rdx+4Eh]; Size
0x18002ed2c  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x18002ed30  call    memset_0
0x18002ed35  movups  xmm0, xmmword ptr [rbx]
0x18002ed38  mov     rcx, r15; lpString1
0x18002ed3b  mov     [rbp+4Fh+var_B8], 0AADDAADDh
0x18002ed42  mov     [rbp+4Fh+var_B4], 4
0x18002ed49  movdqu  [rbp+4Fh+var_A8], xmm0
0x18002ed4e  mov     [rbp+4Fh+var_B0], 23h ; '#'
0x18002ed56  call    ?UbpmpGetConsumerFriendlyName@@YAPEBGPEBG@Z; UbpmpGetConsumerFriendlyName(ushort const *)
0x18002ed5b  mov     ecx, 1FEh; Size
0x18002ed60  mov     rbx, rax
0x18002ed63  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002ed68  mov     rsi, rax
0x18002ed6b  test    rax, rax
0x18002ed6e  jnz     short loc_18002ED7D
0x18002ed70  lea     edi, [rax+0Ah]
0x18002ed73  mov     ebx, 0C00000A0h
0x18002ed78  jmp     loc_18002EE39
0x18002ed7d  lea     rax, [rbp+4Fh+var_90]
0x18002ed81  mov     r9, rbx
0x18002ed84  lea     r8, aSS; "%s:%s"
0x18002ed8b  mov     [rsp+130h+var_110], rax
0x18002ed90  mov     edx, 1FEh; unsigned __int64
0x18002ed95  mov     rcx, rsi; unsigned __int16 *
0x18002ed98  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ed9d  mov     edx, 80000000h
0x18002eda2  lea     ecx, [rax+rdx]
0x18002eda5  test    edx, ecx
0x18002eda7  jnz     short loc_18002EDB2
0x18002eda9  cmp     eax, 80000005h
0x18002edae  jz      short loc_18002EDB2
0x18002edb0  int     2Ch; Windows NT - assertion failure
0x18002edb2  mov     rdx, rsi; SourceString
0x18002edb5  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18002edb9  call    cs:__imp_RtlInitUnicodeString
0x18002edbf  lea     rax, [rsp+130h+var_E8]
0x18002edc4  mov     rcx, r14
0x18002edc7  mov     [rsp+130h+var_108], rax
0x18002edcc  lea     r9, [rbp+4Fh+DestinationString]
0x18002edd0  lea     r8, [rbp+4Fh+var_A8]
0x18002edd4  mov     dword ptr [rsp+130h+var_110], 4
0x18002eddc  lea     rdx, [rbp+4Fh+var_B8]
0x18002ede0  call    cs:__imp_SleepstudyHelperCreateBlockerFromGuid
0x18002ede6  mov     ebx, eax
0x18002ede8  test    eax, eax
0x18002edea  jns     short loc_18002EDF3
0x18002edec  mov     edi, 14h
0x18002edf1  jmp     short loc_18002EE39
0x18002edf3  mov     rcx, [rsp+130h+var_E8]
0x18002edf8  lea     rdx, [rsp+130h+var_F0]
0x18002edfd  call    cs:__imp_SleepstudyHelperBuildBlocker
0x18002ee03  mov     ebx, eax
0x18002ee05  test    eax, eax
0x18002ee07  jns     short loc_18002EE10
0x18002ee09  mov     edi, 1Eh
0x18002ee0e  jmp     short loc_18002EE39
0x18002ee10  mov     rcx, [rsp+130h+var_F0]
0x18002ee15  mov     [rsp+130h+var_E8], 0
0x18002ee1e  call    cs:__imp_SleepstudyHelperBlockerActiveReference
0x18002ee24  mov     rax, [rsp+130h+var_F0]
0x18002ee29  mov     [rdi], rax
0x18002ee2c  xor     edi, edi
0x18002ee2e  xor     ebx, ebx
0x18002ee30  mov     [rsp+130h+var_F0], 0
0x18002ee39  mov     rcx, [rsp+130h+var_F0]
0x18002ee3e  test    rcx, rcx
0x18002ee41  jz      short loc_18002EE49
0x18002ee43  call    cs:__imp_SleepstudyHelperDestroyBlocker
0x18002ee49  mov     rcx, [rsp+130h+var_E8]
0x18002ee4e  test    rcx, rcx
0x18002ee51  jz      short loc_18002EE59
0x18002ee53  call    cs:__imp_SleepstudyHelperDestroyBlockerBuilder
0x18002ee59  test    rsi, rsi
0x18002ee5c  jz      short loc_18002EE66
0x18002ee5e  mov     rcx, rsi
0x18002ee61  call    UBPM_MIDL_user_free
0x18002ee66  mov     eax, cs:dword_18004C0F0
0x18002ee6c  cmp     eax, 5
0x18002ee6f  jbe     short loc_18002EEC5
0x18002ee71  mov     edx, 4
0x18002ee76  call    _tlgKeywordOn
0x18002ee7b  test    al, al
0x18002ee7d  jz      short loc_18002EEC5
0x18002ee7f  lea     rax, [rsp+130h+var_E0]
0x18002ee84  mov     [rsp+130h+var_E0], ebx
0x18002ee88  mov     [rsp+130h+var_F8], rax
0x18002ee8d  lea     rdx, byte_18004434B
0x18002ee94  lea     rax, [rsp+130h+var_DC]
0x18002ee99  mov     [rsp+130h+var_DC], edi
0x18002ee9d  mov     [rsp+130h+var_100], rax
0x18002eea2  lea     rax, [rsp+130h+var_D8]
0x18002eea7  mov     [rsp+130h+var_108], rax
0x18002eeac  lea     rax, [rsp+130h+var_D0]
0x18002eeb1  mov     [rsp+130h+var_110], rax
0x18002eeb6  mov     [rsp+130h+var_D8], r12
0x18002eebb  mov     [rsp+130h+var_D0], r15
0x18002eec0  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002eec5  mov     eax, ebx
0x18002eec7  mov     rcx, [rbp+4Fh+var_40]
0x18002eecb  xor     rcx, rsp; StackCookie
0x18002eece  call    __security_check_cookie
0x18002eed3  add     rsp, 100h
0x18002eeda  pop     r15
0x18002eedc  pop     r14
0x18002eede  pop     r12
0x18002eee0  pop     rdi
0x18002eee1  pop     rsi
0x18002eee2  pop     rbx
0x18002eee3  pop     rbp
0x18002eee4  retn
```
