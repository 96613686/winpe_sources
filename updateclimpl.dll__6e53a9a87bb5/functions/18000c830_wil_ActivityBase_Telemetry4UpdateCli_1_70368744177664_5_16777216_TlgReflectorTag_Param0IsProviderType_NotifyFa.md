# wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x18000c830`
- end: `0x18000cba1`
- name: `?NotifyFailure@?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `881`
- prototype: `char __fastcall(_QWORD *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x18000140c`
- `0x180001a7c`
- `0x180004158`
- `0x180004fdc`
- `0x18000c830`
- `0x18000d038`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cb84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cb84`

## pseudocode

```c
char __fastcall wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r9
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // r9
  __int64 v9; // r8
  _DWORD *v10; // rax
  int v11; // edx
  int v13; // [rsp+B0h] [rbp-80h] BYREF
  int v14; // [rsp+B4h] [rbp-7Ch] BYREF
  int v15; // [rsp+B8h] [rbp-78h] BYREF
  int v16; // [rsp+BCh] [rbp-74h] BYREF
  int v17; // [rsp+C0h] [rbp-70h] BYREF
  int v18; // [rsp+C4h] [rbp-6Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v26; // [rsp+100h] [rbp-30h] BYREF
  __int64 v27; // [rsp+108h] [rbp-28h] BYREF
  __int64 v28; // [rsp+110h] [rbp-20h] BYREF
  __int64 v29; // [rsp+118h] [rbp-18h] BYREF
  __int64 v30; // [rsp+120h] [rbp-10h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v7 = *((_QWORD *)Telemetry4UpdateCli::Instance() + 1);
      if ( *(_DWORD *)v7 > 2u
        && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
        && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
      {
        v27 = *((_QWORD *)a2 + 6);
        v18 = a2[17];
        v17 = a2[4];
        v26 = *((_QWORD *)a2 + 15);
        v9 = a1[34];
        v25 = *((_QWORD *)a2 + 14);
        v16 = a2[26];
        v24 = *((_QWORD *)a2 + 12);
        v23 = *((_QWORD *)a2 + 11);
        v15 = a2[20];
        v22 = *((_QWORD *)a2 + 9);
        v14 = a2[8];
        v21 = *((_QWORD *)a2 + 3);
        v13 = *a2;
        v28 = *((_QWORD *)a2 + 16);
        LODWORD(v20) = a2[16];
        v29 = *((_QWORD *)a2 + 7);
        LODWORD(SRWLock) = a2[2];
        v30 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v7,
          (int)&byte_18001ACF9,
          v9 + 8,
          v8,
          (__int64)&v30,
          (__int64)&SRWLock,
          (const wchar_t **)&v29,
          (__int64)&v20,
          (const wchar_t **)&v28,
          (__int64)&v13,
          (char **)&v21,
          (__int64)&v14,
          (const wchar_t **)&v22,
          (__int64)&v15,
          (const wchar_t **)&v23,
          (char **)&v24,
          (__int64)&v16,
          (const wchar_t **)&v25,
          (char **)&v26,
          (__int64)&v17,
          (__int64)&v18,
          (const wchar_t **)&v27);
      }
    }
    else
    {
      v4 = *((_QWORD *)Telemetry4UpdateCli::Instance() + 1);
      if ( *(_DWORD *)v4 > 2u
        && (*(_QWORD *)(v4 + 16) & 0x600000000000LL) != 0
        && (*(_QWORD *)(v4 + 24) & 0x600000000000LL) == *(_QWORD *)(v4 + 24) )
      {
        v6 = a1[34];
        SRWLock = (PSRWLOCK)*((_QWORD *)a2 + 15);
        v20 = *((_QWORD *)a2 + 14);
        v13 = a2[26];
        v21 = *((_QWORD *)a2 + 12);
        v22 = *((_QWORD *)a2 + 11);
        v14 = a2[20];
        v23 = *((_QWORD *)a2 + 9);
        v15 = a2[8];
        v24 = *((_QWORD *)a2 + 3);
        v16 = *a2;
        v25 = *((_QWORD *)a2 + 16);
        v17 = a2[16];
        v26 = *((_QWORD *)a2 + 7);
        v18 = a2[2];
        v27 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
          v4,
          (int)&dword_18001ABE4,
          v6 + 8,
          v5,
          (__int64)&v27,
          (__int64)&v18,
          (const wchar_t **)&v26,
          (__int64)&v17,
          (const wchar_t **)&v25,
          (__int64)&v16,
          (char **)&v24,
          (__int64)&v15,
          (const wchar_t **)&v23,
          (__int64)&v14,
          (const wchar_t **)&v22,
          (char **)&v21,
          (__int64)&v13,
          (const wchar_t **)&v20,
          (char **)&SRWLock);
      }
    }
  }
  SRWLock = 0;
  wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &SRWLock);
  v10 = (_DWORD *)a1[34];
  v11 = a2[2];
  if ( v11 != v10[22] && (v11 != v10[18] || (int)v10[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v10 + 20), (const struct wil::FailureInfo *)a2);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return 1;
}

```

## disassembly

```asm
0x18000c830  mov     [rsp-8+arg_10], rbx
0x18000c835  mov     [rsp-8+arg_18], rdi
0x18000c83a  push    rbp
0x18000c83b  mov     rbp, rsp
0x18000c83e  sub     rsp, 130h
0x18000c845  test    byte ptr [rdx+4], 2
0x18000c849  mov     rbx, rdx
0x18000c84c  mov     rdi, rcx
0x18000c84f  jnz     loc_18000CB41
0x18000c855  mov     rax, [rcx]
0x18000c858  mov     edx, [rdx+10h]
0x18000c85b  mov     rax, [rax+10h]
0x18000c85f  call    _guard_dispatch_icall
0x18000c864  test    al, al
0x18000c866  jnz     loc_18000C9BD
0x18000c86c  call    ?Instance@Telemetry4UpdateCli@@KAPEAV1@XZ; Telemetry4UpdateCli::Instance(void)
0x18000c871  mov     rcx, [rax+8]; int
0x18000c875  cmp     dword ptr [rcx], 2
0x18000c878  jbe     loc_18000CB41
0x18000c87e  mov     rdx, 600000000000h
0x18000c888  test    [rcx+10h], rdx
0x18000c88c  jz      loc_18000CB41
0x18000c892  mov     rax, [rcx+18h]
0x18000c896  and     rax, rdx
0x18000c899  cmp     rax, [rcx+18h]
0x18000c89d  jnz     loc_18000CB41
0x18000c8a3  mov     rax, [rbx+78h]
0x18000c8a7  lea     rdx, dword_18001ABE4; int
0x18000c8ae  mov     r8, [rdi+110h]
0x18000c8b5  mov     [rbp+SRWLock], rax
0x18000c8b9  add     r8, 8; int
0x18000c8bd  mov     rax, [rbx+70h]
0x18000c8c1  mov     [rbp+var_60], rax
0x18000c8c5  mov     eax, [rbx+68h]
0x18000c8c8  mov     dword ptr [rbp+var_80], eax
0x18000c8cb  mov     rax, [rbx+60h]
0x18000c8cf  mov     [rbp+var_58], rax
0x18000c8d3  mov     rax, [rbx+58h]
0x18000c8d7  mov     [rbp+var_50], rax
0x18000c8db  mov     eax, [rbx+50h]
0x18000c8de  mov     dword ptr [rbp+var_80+4], eax
0x18000c8e1  mov     rax, [rbx+48h]
0x18000c8e5  mov     [rbp+var_48], rax
0x18000c8e9  mov     eax, [rbx+20h]
0x18000c8ec  mov     dword ptr [rbp+var_78], eax
0x18000c8ef  mov     rax, [rbx+18h]
0x18000c8f3  mov     [rbp+var_40], rax
0x18000c8f7  mov     eax, [rbx]
0x18000c8f9  mov     dword ptr [rbp+var_78+4], eax
0x18000c8fc  mov     rax, [rbx+80h]
0x18000c903  mov     [rbp+var_38], rax
0x18000c907  mov     eax, [rbx+40h]
0x18000c90a  mov     dword ptr [rbp+var_70], eax
0x18000c90d  mov     rax, [rbx+38h]
0x18000c911  mov     [rbp+var_30], rax
0x18000c915  mov     eax, [rbx+8]
0x18000c918  mov     dword ptr [rbp+var_70+4], eax
0x18000c91b  lea     rax, [rbp+SRWLock]
0x18000c91f  mov     [rsp+130h+var_A0], rax; __int64
0x18000c927  lea     rax, [rbp+var_60]
0x18000c92b  mov     [rsp+130h+var_A8], rax; __int64
0x18000c933  lea     rax, [rbp+var_80]
0x18000c937  mov     [rsp+130h+var_B0], rax; __int64
0x18000c93f  lea     rax, [rbp+var_58]
0x18000c943  mov     [rsp+130h+var_B8], rax; __int64
0x18000c948  lea     rax, [rbp+var_50]
0x18000c94c  mov     [rsp+130h+var_C0], rax; __int64
0x18000c951  lea     rax, [rbp+var_80+4]
0x18000c955  mov     [rsp+130h+var_C8], rax; __int64
0x18000c95a  lea     rax, [rbp+var_48]
0x18000c95e  mov     [rsp+130h+var_D0], rax; __int64
0x18000c963  lea     rax, [rbp+var_78]
0x18000c967  mov     [rsp+130h+var_D8], rax; __int64
0x18000c96c  lea     rax, [rbp+var_40]
0x18000c970  mov     [rsp+130h+var_E0], rax; __int64
0x18000c975  lea     rax, [rbp+var_78+4]
0x18000c979  mov     [rsp+130h+var_E8], rax; __int64
0x18000c97e  lea     rax, [rbp+var_38]
0x18000c982  mov     [rsp+130h+var_F0], rax; __int64
0x18000c987  lea     rax, [rbp+var_70]
0x18000c98b  mov     [rsp+130h+var_F8], rax; __int64
0x18000c990  lea     rax, [rbp+var_30]
0x18000c994  mov     [rsp+130h+var_100], rax; __int64
0x18000c999  lea     rax, [rbp+var_70+4]
0x18000c99d  mov     [rsp+130h+var_108], rax; __int64
0x18000c9a2  lea     rax, [rbp+var_28]
0x18000c9a6  mov     [rsp+130h+var_110], rax; __int64
0x18000c9ab  mov     [rbp+var_28], 1000000h
0x18000c9b3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x18000c9b8  jmp     loc_18000CB41
0x18000c9bd  call    ?Instance@Telemetry4UpdateCli@@KAPEAV1@XZ; Telemetry4UpdateCli::Instance(void)
0x18000c9c2  mov     rcx, [rax+8]; int
0x18000c9c6  cmp     dword ptr [rcx], 2
0x18000c9c9  jbe     loc_18000CB41
0x18000c9cf  mov     rdx, 400000000000h
0x18000c9d9  test    [rcx+10h], rdx
0x18000c9dd  jz      loc_18000CB41
0x18000c9e3  mov     rax, [rcx+18h]
0x18000c9e7  and     rax, rdx
0x18000c9ea  cmp     rax, [rcx+18h]
0x18000c9ee  jnz     loc_18000CB41
0x18000c9f4  mov     rax, [rbx+30h]
0x18000c9f8  lea     rdx, byte_18001ACF9; int
0x18000c9ff  mov     [rbp+var_28], rax
0x18000ca03  mov     eax, [rbx+44h]
0x18000ca06  mov     dword ptr [rbp+var_70+4], eax
0x18000ca09  mov     eax, [rbx+10h]
0x18000ca0c  mov     dword ptr [rbp+var_70], eax
0x18000ca0f  mov     rax, [rbx+78h]
0x18000ca13  mov     [rbp+var_30], rax
0x18000ca17  mov     rax, [rbx+70h]
0x18000ca1b  mov     r8, [rdi+110h]
0x18000ca22  mov     [rbp+var_38], rax
0x18000ca26  add     r8, 8; int
0x18000ca2a  mov     eax, [rbx+68h]
0x18000ca2d  mov     dword ptr [rbp+var_78+4], eax
0x18000ca30  mov     rax, [rbx+60h]
0x18000ca34  mov     [rbp+var_40], rax
0x18000ca38  mov     rax, [rbx+58h]
0x18000ca3c  mov     [rbp+var_48], rax
0x18000ca40  mov     eax, [rbx+50h]
0x18000ca43  mov     dword ptr [rbp+var_78], eax
0x18000ca46  mov     rax, [rbx+48h]
0x18000ca4a  mov     [rbp+var_50], rax
0x18000ca4e  mov     eax, [rbx+20h]
0x18000ca51  mov     dword ptr [rbp+var_80+4], eax
0x18000ca54  mov     rax, [rbx+18h]
0x18000ca58  mov     [rbp+var_58], rax
0x18000ca5c  mov     eax, [rbx]
0x18000ca5e  mov     dword ptr [rbp+var_80], eax
0x18000ca61  mov     rax, [rbx+80h]
0x18000ca68  mov     [rbp+var_20], rax
0x18000ca6c  mov     eax, [rbx+40h]
0x18000ca6f  mov     dword ptr [rbp+var_60], eax
0x18000ca72  mov     rax, [rbx+38h]
0x18000ca76  mov     [rbp+var_18], rax
0x18000ca7a  mov     eax, [rbx+8]
0x18000ca7d  mov     dword ptr [rbp+SRWLock], eax
0x18000ca80  lea     rax, [rbp+var_28]
0x18000ca84  mov     [rsp+130h+var_88], rax; __int64
0x18000ca8c  lea     rax, [rbp+var_70+4]
0x18000ca90  mov     [rsp+130h+var_90], rax; __int64
0x18000ca98  lea     rax, [rbp+var_70]
0x18000ca9c  mov     [rsp+130h+var_98], rax; __int64
0x18000caa4  lea     rax, [rbp+var_30]
0x18000caa8  mov     [rsp+130h+var_A0], rax; __int64
0x18000cab0  lea     rax, [rbp+var_38]
0x18000cab4  mov     [rsp+130h+var_A8], rax; __int64
0x18000cabc  lea     rax, [rbp+var_78+4]
0x18000cac0  mov     [rsp+130h+var_B0], rax; __int64
0x18000cac8  lea     rax, [rbp+var_40]
0x18000cacc  mov     [rsp+130h+var_B8], rax; __int64
0x18000cad1  lea     rax, [rbp+var_48]
0x18000cad5  mov     [rsp+130h+var_C0], rax; __int64
0x18000cada  lea     rax, [rbp+var_78]
0x18000cade  mov     [rsp+130h+var_C8], rax; __int64
0x18000cae3  lea     rax, [rbp+var_50]
0x18000cae7  mov     [rsp+130h+var_D0], rax; __int64
0x18000caec  lea     rax, [rbp+var_80+4]
0x18000caf0  mov     [rsp+130h+var_D8], rax; __int64
0x18000caf5  lea     rax, [rbp+var_58]
0x18000caf9  mov     [rsp+130h+var_E0], rax; __int64
0x18000cafe  lea     rax, [rbp+var_80]
0x18000cb02  mov     [rsp+130h+var_E8], rax; __int64
0x18000cb07  lea     rax, [rbp+var_20]
0x18000cb0b  mov     [rsp+130h+var_F0], rax; __int64
0x18000cb10  lea     rax, [rbp+var_60]
0x18000cb14  mov     [rsp+130h+var_F8], rax; __int64
0x18000cb19  lea     rax, [rbp+var_18]
0x18000cb1d  mov     [rsp+130h+var_100], rax; __int64
0x18000cb22  lea     rax, [rbp+SRWLock]
0x18000cb26  mov     [rsp+130h+var_108], rax; __int64
0x18000cb2b  lea     rax, [rbp+var_10]
0x18000cb2f  mov     [rsp+130h+var_110], rax; __int64
0x18000cb34  mov     [rbp+var_10], 1000000h
0x18000cb3c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000cb41  lea     rdx, [rbp+SRWLock]
0x18000cb45  mov     [rbp+SRWLock], 0
0x18000cb4d  mov     rcx, rdi
0x18000cb50  call    ?LockExclusive@?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000cb55  mov     rax, [rdi+110h]
0x18000cb5c  mov     edx, [rbx+8]
0x18000cb5f  lea     rcx, [rax+50h]; this
0x18000cb63  cmp     edx, [rcx+8]
0x18000cb66  jz      short loc_18000CB7B
0x18000cb68  cmp     edx, [rax+48h]
0x18000cb6b  jnz     short loc_18000CB73
0x18000cb6d  cmp     dword ptr [rax+48h], 0
0x18000cb71  jl      short loc_18000CB7B
0x18000cb73  mov     rdx, rbx; struct wil::FailureInfo *
0x18000cb76  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x18000cb7b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000cb7f  test    rcx, rcx
0x18000cb82  jz      short loc_18000CB8A
0x18000cb84  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cb8a  lea     r11, [rsp+130h+var_s0]
0x18000cb92  mov     al, 1
0x18000cb94  mov     rbx, [r11+20h]
0x18000cb98  mov     rdi, [r11+28h]
0x18000cb9c  mov     rsp, r11
0x18000cb9f  pop     rbp
0x18000cba0  retn
```
