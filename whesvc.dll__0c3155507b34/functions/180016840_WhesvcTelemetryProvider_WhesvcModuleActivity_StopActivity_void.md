# WhesvcTelemetryProvider::WhesvcModuleActivity::StopActivity(void)

- ea: `0x180016840`
- end: `0x180016b20`
- name: `?StopActivity@WhesvcModuleActivity@WhesvcTelemetryProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(WhesvcTelemetryProvider::WhesvcModuleActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001008`
- `0x1800018dc`
- `0x1800032e0`
- `0x18000a920`
- `0x18000a9ac`
- `0x18000ae4c`
- `0x180016840`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016a81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016a81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800168af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016a42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800168af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016a42`

## pseudocode

```c
void __fastcall WhesvcTelemetryProvider::WhesvcModuleActivity::StopActivity(
        WhesvcTelemetryProvider::WhesvcModuleActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  __int64 v13; // rax
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // [rsp+A0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  PSRWLOCK v18; // [rsp+B0h] [rbp-70h] BYREF
  int v19; // [rsp+B8h] [rbp-68h] BYREF
  int v20; // [rsp+BCh] [rbp-64h] BYREF
  int v21; // [rsp+C0h] [rbp-60h] BYREF
  int v22; // [rsp+C4h] [rbp-5Ch] BYREF
  const wchar_t *v23; // [rsp+C8h] [rbp-58h] BYREF
  const unsigned __int16 *v24; // [rsp+D0h] [rbp-50h] BYREF
  const wchar_t *v25; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v26; // [rsp+E0h] [rbp-40h] BYREF
  const unsigned __int16 *v27; // [rsp+E8h] [rbp-38h] BYREF
  const wchar_t *v28; // [rsp+F0h] [rbp-30h] BYREF
  const unsigned __int16 *v29; // [rsp+F8h] [rbp-28h] BYREF
  const unsigned __int16 *v30; // [rsp+100h] [rbp-20h] BYREF
  __int64 v31; // [rsp+108h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v33; // [rsp+130h] [rbp+10h]
  __int64 v34; // [rsp+138h] [rbp+18h]
  int *v35; // [rsp+140h] [rbp+20h]
  __int64 v36; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v38; // [rsp+158h] [rbp+38h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = WhesvcTelemetryProvider::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 0x200000000000LL) != 0 && (v8 & 0x200000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v23 = (const wchar_t *)*((_QWORD *)v4 + 15);
        v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v19 = v4[26];
        v25 = (const wchar_t *)*((_QWORD *)v4 + 12);
        v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v20 = v4[20];
        v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v21 = v4[8];
        v28 = (const wchar_t *)*((_QWORD *)v4 + 3);
        v22 = *v4;
        v29 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v16 = v4[16];
        v30 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v31 = 0x1000000;
        v18 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)&word_18002D896,
          v9 + 8,
          v7,
          (__int64)&v18,
          (__int64)&v31,
          (__int64)&SRWLock,
          &v30,
          (__int64)&v16,
          &v29,
          (__int64)&v22,
          &v28,
          (__int64)&v21,
          &v27,
          (__int64)&v20,
          &v26,
          &v25,
          (__int64)&v19,
          &v24,
          &v23);
      }
    }
  }
  else
  {
    wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v18);
    v10 = v18;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = WhesvcTelemetryProvider::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*(_QWORD *)(v12 + 16) & 0x200000000000LL) != 0 && (v13 & 0x200000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v38 = 4;
        v36 = 4;
        v16 = *(_DWORD *)(v15 + 72);
        p_SRWLock = &SRWLock;
        v35 = &v16;
        v33 = &v18;
        v18 = 0;
        v34 = 8;
        tlgWriteTransfer_EventWriteTransfer(
          v12,
          (unsigned __int8 *)word_18002D9C2,
          (const GUID *)(v15 + 8),
          0,
          5u,
          &v32);
      }
    }
  }
  wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180016840  mov     [rsp-8+arg_8], rbx
0x180016845  mov     [rsp-8+arg_10], rdi
0x18001684a  push    rbp
0x18001684b  lea     rbp, [rsp-50h]
0x180016850  sub     rsp, 170h
0x180016857  mov     rax, cs:__security_cookie
0x18001685e  xor     rax, rsp
0x180016861  mov     [rbp+50h+var_10], rax
0x180016865  mov     rdi, [rcx+110h]
0x18001686c  mov     rbx, rcx
0x18001686f  mov     eax, [rdi+48h]
0x180016872  test    eax, eax
0x180016874  jns     loc_180016A23
0x18001687a  add     rdi, 50h ; 'P'
0x18001687e  cmp     eax, [rdi+8]
0x180016881  jnz     loc_180016A23
0x180016887  test    rdi, rdi
0x18001688a  jz      loc_180016A23
0x180016890  lea     rdx, [rbp+50h+SRWLock]
0x180016894  call    ?LockExclusive@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180016899  mov     rax, [rbx+110h]
0x1800168a0  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x1800168a4  mov     dword ptr [rax], 2
0x1800168aa  test    rcx, rcx
0x1800168ad  jz      short loc_1800168B5
0x1800168af  call    cs:__imp_ReleaseSRWLockExclusive
0x1800168b5  call    ?Provider@WhesvcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; WhesvcTelemetryProvider::Provider(void)
0x1800168ba  mov     r9, rax
0x1800168bd  mov     ecx, [rax]
0x1800168bf  cmp     ecx, 5
0x1800168c2  jbe     loc_180016AF7
0x1800168c8  mov     rax, [rax+18h]
0x1800168cc  mov     rdx, 200000000000h
0x1800168d6  mov     rcx, [r9+10h]
0x1800168da  test    rdx, rcx
0x1800168dd  jz      loc_180016AF7
0x1800168e3  mov     rcx, rax
0x1800168e6  and     rcx, rdx
0x1800168e9  cmp     rcx, rax
0x1800168ec  jnz     loc_180016AF7
0x1800168f2  mov     rax, [rdi+78h]
0x1800168f6  lea     rdx, word_18002D896
0x1800168fd  mov     r8, [rbx+110h]
0x180016904  mov     rcx, r9
0x180016907  mov     [rbp+50h+var_A8], rax
0x18001690b  add     r8, 8
0x18001690f  mov     rax, [rdi+70h]
0x180016913  mov     [rbp+50h+var_A0], rax
0x180016917  mov     eax, [rdi+68h]
0x18001691a  mov     [rbp+50h+var_B8], eax
0x18001691d  mov     rax, [rdi+60h]
0x180016921  mov     [rbp+50h+var_98], rax
0x180016925  mov     rax, [rdi+58h]
0x180016929  mov     [rbp+50h+var_90], rax
0x18001692d  mov     eax, [rdi+50h]
0x180016930  mov     [rbp+50h+var_B4], eax
0x180016933  mov     rax, [rdi+48h]
0x180016937  mov     [rbp+50h+var_88], rax
0x18001693b  mov     eax, [rdi+20h]
0x18001693e  mov     [rbp+50h+var_B0], eax
0x180016941  mov     rax, [rdi+18h]
0x180016945  mov     [rbp+50h+var_80], rax
0x180016949  mov     eax, [rdi]
0x18001694b  mov     [rbp+50h+var_AC], eax
0x18001694e  mov     rax, [rdi+80h]
0x180016955  mov     [rbp+50h+var_78], rax
0x180016959  mov     eax, [rdi+40h]
0x18001695c  mov     [rbp+50h+var_D0], eax
0x18001695f  mov     rax, [rdi+38h]
0x180016963  mov     [rbp+50h+var_70], rax
0x180016967  mov     eax, [rdi+8]
0x18001696a  mov     dword ptr [rbp+50h+SRWLock], eax
0x18001696d  lea     rax, [rbp+50h+var_A8]
0x180016971  mov     [rsp+170h+var_D8], rax
0x180016979  lea     rax, [rbp+50h+var_A0]
0x18001697d  mov     [rsp+170h+var_E0], rax
0x180016985  lea     rax, [rbp+50h+var_B8]
0x180016989  mov     [rsp+170h+var_E8], rax
0x180016991  lea     rax, [rbp+50h+var_98]
0x180016995  mov     [rsp+170h+var_F0], rax
0x18001699d  lea     rax, [rbp+50h+var_90]
0x1800169a1  mov     [rsp+170h+var_F8], rax
0x1800169a6  lea     rax, [rbp+50h+var_B4]
0x1800169aa  mov     [rsp+170h+var_100], rax
0x1800169af  lea     rax, [rbp+50h+var_88]
0x1800169b3  mov     [rsp+170h+var_108], rax
0x1800169b8  lea     rax, [rbp+50h+var_B0]
0x1800169bc  mov     [rsp+170h+var_110], rax
0x1800169c1  lea     rax, [rbp+50h+var_80]
0x1800169c5  mov     [rsp+170h+var_118], rax
0x1800169ca  lea     rax, [rbp+50h+var_AC]
0x1800169ce  mov     [rsp+170h+var_120], rax
0x1800169d3  lea     rax, [rbp+50h+var_78]
0x1800169d7  mov     [rsp+170h+var_128], rax
0x1800169dc  lea     rax, [rbp+50h+var_D0]
0x1800169e0  mov     [rsp+170h+var_130], rax
0x1800169e5  lea     rax, [rbp+50h+var_70]
0x1800169e9  mov     [rsp+170h+var_138], rax
0x1800169ee  lea     rax, [rbp+50h+SRWLock]
0x1800169f2  mov     [rsp+170h+var_140], rax
0x1800169f7  lea     rax, [rbp+50h+var_68]
0x1800169fb  mov     [rsp+170h+var_148], rax
0x180016a00  lea     rax, [rbp+50h+var_C0]
0x180016a04  mov     [rsp+170h+var_150], rax
0x180016a09  mov     [rbp+50h+var_68], 1000000h
0x180016a11  mov     [rbp+50h+var_C0], 0
0x180016a19  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180016a1e  jmp     loc_180016AF7
0x180016a23  lea     rdx, [rbp+50h+var_C0]
0x180016a27  call    ?LockExclusive@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180016a2c  mov     rax, [rbx+110h]
0x180016a33  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x180016a37  mov     dword ptr [rax], 2
0x180016a3d  test    rcx, rcx
0x180016a40  jz      short loc_180016A48
0x180016a42  call    cs:__imp_ReleaseSRWLockExclusive
0x180016a48  call    ?Provider@WhesvcTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; WhesvcTelemetryProvider::Provider(void)
0x180016a4d  mov     rdi, rax
0x180016a50  mov     ecx, [rax]
0x180016a52  cmp     ecx, 5
0x180016a55  jbe     loc_180016AF7
0x180016a5b  mov     rax, [rax+18h]
0x180016a5f  mov     rdx, 200000000000h
0x180016a69  mov     rcx, [rdi+10h]
0x180016a6d  test    rdx, rcx
0x180016a70  jz      loc_180016AF7
0x180016a76  mov     rcx, rax
0x180016a79  and     rcx, rdx
0x180016a7c  cmp     rcx, rax
0x180016a7f  jnz     short loc_180016AF7
0x180016a81  call    cs:__imp_GetCurrentThreadId
0x180016a87  mov     r8, [rbx+110h]
0x180016a8e  lea     rdx, word_18002D9C2
0x180016a95  mov     dword ptr [rbp+50h+SRWLock], eax
0x180016a98  xor     r9d, r9d
0x180016a9b  mov     rcx, rdi
0x180016a9e  mov     [rbp+50h+var_18], 4
0x180016aa6  mov     [rbp+50h+var_28], 4
0x180016aae  mov     eax, [r8+48h]
0x180016ab2  add     r8, 8
0x180016ab6  mov     [rbp+50h+var_D0], eax
0x180016ab9  lea     rax, [rbp+50h+SRWLock]
0x180016abd  mov     [rbp+50h+var_20], rax
0x180016ac1  lea     rax, [rbp+50h+var_D0]
0x180016ac5  mov     [rbp+50h+var_30], rax
0x180016ac9  lea     rax, [rbp+50h+var_C0]
0x180016acd  mov     [rbp+50h+var_40], rax
0x180016ad1  lea     rax, [rbp+50h+var_60]
0x180016ad5  mov     [rsp+170h+var_148], rax
0x180016ada  mov     dword ptr [rsp+170h+var_150], 5
0x180016ae2  mov     [rbp+50h+var_C0], 0
0x180016aea  mov     [rbp+50h+var_38], 8
0x180016af2  call    _tlgWriteTransfer_EventWriteTransfer
0x180016af7  mov     rcx, rbx
0x180016afa  call    ?IgnoreCurrentThread@?$ActivityBase@VWhesvcTelemetryProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WhesvcTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180016aff  mov     rcx, [rbp+50h+var_10]
0x180016b03  xor     rcx, rsp; StackCookie
0x180016b06  call    __security_check_cookie
0x180016b0b  lea     r11, [rsp+170h+var_s0]
0x180016b13  mov     rbx, [r11+18h]
0x180016b17  mov     rdi, [r11+20h]
0x180016b1b  mov     rsp, r11
0x180016b1e  pop     rbp
0x180016b1f  retn
```
