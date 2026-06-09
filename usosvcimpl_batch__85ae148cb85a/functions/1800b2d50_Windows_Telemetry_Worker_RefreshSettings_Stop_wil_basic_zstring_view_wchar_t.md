# Windows::Telemetry::Worker::RefreshSettings::Stop(wil::basic_zstring_view<wchar_t>)

- ea: `0x1800b2d50`
- end: `0x1800b30e5`
- name: `?Stop@RefreshSettings@Worker@Telemetry@Windows@@QEAAXV?$basic_zstring_view@_W@wil@@@Z`
- size: `917`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800b3550`

## callees

- `0x180001350`
- `0x180001fa0`
- `0x180085644`
- `0x18008c454`
- `0x1800b2d50`
- `0x1800b781c`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b2dd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b2fa0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b2dd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b2fa0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2fe8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b2fe8`

## pseudocode

```c
void __fastcall Windows::Telemetry::Worker::RefreshSettings::Stop(__int64 a1, __int64 *a2)
{
  _DWORD **v2; // r14
  __int64 v3; // rsi
  int v6; // eax
  __int64 v7; // rsi
  _DWORD **v8; // rbx
  RTL_SRWLOCK *v9; // rcx
  const struct _tlgProvider_t *v10; // rax
  _DWORD *v11; // r8
  _DWORD *v12; // rax
  int v13; // ebx
  RTL_SRWLOCK *v14; // rcx
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // rsi
  const OLECHAR *v17; // r15
  DWORD CurrentThreadId; // eax
  _DWORD *v19; // r8
  __int64 v20; // rbx
  __int64 v21; // [rsp+C0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-78h] BYREF
  int v23; // [rsp+D0h] [rbp-70h] BYREF
  int v24; // [rsp+D4h] [rbp-6Ch] BYREF
  int v25; // [rsp+D8h] [rbp-68h] BYREF
  int v26; // [rsp+DCh] [rbp-64h] BYREF
  __int64 v27; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v28; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v29; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v30; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v31; // [rsp+100h] [rbp-40h] BYREF
  __int64 v32; // [rsp+108h] [rbp-38h] BYREF
  __int64 v33; // [rsp+110h] [rbp-30h] BYREF
  __int64 v34; // [rsp+118h] [rbp-28h] BYREF
  __int64 v35; // [rsp+120h] [rbp-20h] BYREF
  __int64 v36; // [rsp+128h] [rbp-18h] BYREF
  __int64 v37; // [rsp+130h] [rbp-10h] BYREF
  __int64 v38; // [rsp+138h] [rbp-8h] BYREF
  __int64 v39; // [rsp+140h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v40; // [rsp+150h] [rbp+10h] BYREF
  __int64 *v41; // [rsp+170h] [rbp+30h]
  __int64 v42; // [rsp+178h] [rbp+38h]
  int *v43; // [rsp+180h] [rbp+40h]
  __int64 v44; // [rsp+188h] [rbp+48h]
  PSRWLOCK *p_SRWLock; // [rsp+190h] [rbp+50h]
  __int64 v46; // [rsp+198h] [rbp+58h]
  const OLECHAR *v47; // [rsp+1A0h] [rbp+60h]
  int v48; // [rsp+1A8h] [rbp+68h]
  int v49; // [rsp+1ACh] [rbp+6Ch]
  __int64 *v50; // [rsp+1B0h] [rbp+70h]
  __int64 v51; // [rsp+1B8h] [rbp+78h]
  const char *v52; // [rsp+1C0h] [rbp+80h]
  __int64 v53; // [rsp+1C8h] [rbp+88h]

  v2 = (_DWORD **)(a1 + 272);
  v3 = *(_QWORD *)(a1 + 272);
  v6 = *(_DWORD *)(v3 + 72);
  if ( v6 < 0 && (v7 = v3 + 80, v6 == *(_DWORD *)(v7 + 8)) )
  {
    v8 = (_DWORD **)(a1 + 272);
    if ( v7 )
    {
      SRWLock = 0;
      wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        a1,
        &SRWLock);
      v9 = SRWLock;
      **v2 = 2;
      if ( v9 )
        ReleaseSRWLockExclusive(v9);
      v10 = Windows::Telemetry::Base::Provider();
      if ( *(_DWORD *)v10 > 5u
        && (*((_QWORD *)v10 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v10 + 3) & 0x400000000000LL) == *((_QWORD *)v10 + 3) )
      {
        v11 = *v2;
        v29 = (__int64)"1507.2603.28012.0";
        LOBYTE(v21) = *(_BYTE *)(a1 + 328);
        v30 = *a2;
        v31 = *(_QWORD *)(v7 + 120);
        v32 = *(_QWORD *)(v7 + 112);
        v24 = *(_DWORD *)(v7 + 104);
        v33 = *(_QWORD *)(v7 + 96);
        v34 = *(_QWORD *)(v7 + 88);
        v25 = *(_DWORD *)(v7 + 80);
        v35 = *(_QWORD *)(v7 + 72);
        v26 = *(_DWORD *)(v7 + 32);
        v36 = *(_QWORD *)(v7 + 24);
        LODWORD(v27) = *(_DWORD *)v7;
        v37 = *(_QWORD *)(v7 + 128);
        v23 = *(_DWORD *)(v7 + 64);
        v38 = *(_QWORD *)(v7 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v7 + 8);
        v39 = 0x1000000;
        v28 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<char>>(
          (int)v10,
          (int)&qword_180131790,
          (_DWORD)v11 + 8,
          (__int64)&v28,
          (__int64)&v39,
          (__int64)&SRWLock,
          (__int64)&v38,
          (__int64)&v23,
          (__int64)&v37,
          (__int64)&v27,
          (__int64)&v36,
          (__int64)&v26,
          (__int64)&v35,
          (__int64)&v25,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v24,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v21,
          (__int64)&v29);
      }
      goto LABEL_22;
    }
  }
  else
  {
    v8 = (_DWORD **)(a1 + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v12 = *v8;
  v13 = 2;
  v14 = SRWLock;
  *v12 = 2;
  if ( v14 )
    ReleaseSRWLockExclusive(v14);
  v15 = Windows::Telemetry::Base::Provider();
  v16 = (__int64)v15;
  if ( *(_DWORD *)v15 > 5u
    && (*((_QWORD *)v15 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v15 + 3) & 0x400000000000LL) == *((_QWORD *)v15 + 3) )
  {
    v17 = (const OLECHAR *)*a2;
    LOBYTE(v21) = *(_BYTE *)(a1 + 328);
    CurrentThreadId = GetCurrentThreadId();
    v19 = *v2;
    LODWORD(SRWLock) = CurrentThreadId;
    v53 = 18;
    v51 = 1;
    v23 = v19[18];
    v28 = 0x1000000;
    v52 = "1507.2603.28012.0";
    v50 = &v21;
    if ( v17 )
    {
      v20 = -1;
      do
        ++v20;
      while ( v17[v20] );
      v13 = 2 * v20 + 2;
    }
    else
    {
      v17 = &S1;
    }
    v47 = v17;
    p_SRWLock = &SRWLock;
    v48 = v13;
    v43 = &v23;
    v49 = 0;
    v41 = &v28;
    v46 = 4;
    v44 = 4;
    v42 = 8;
    tlgWriteTransfer_EventWriteTransfer(v16, (unsigned __int8 *)&byte_1801315A7, (const GUID *)(v19 + 2), 0, 8u, &v40);
  }
LABEL_22:
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x1800b2d50  mov     [rsp-8+arg_8], rbx
0x1800b2d55  mov     [rsp-8+arg_10], rsi
0x1800b2d5a  push    rbp
0x1800b2d5b  push    rdi
0x1800b2d5c  push    r12
0x1800b2d5e  push    r14
0x1800b2d60  push    r15
0x1800b2d62  lea     rbp, [rsp-0A0h]
0x1800b2d6a  sub     rsp, 1E0h
0x1800b2d71  mov     rax, cs:__security_cookie
0x1800b2d78  xor     rax, rsp
0x1800b2d7b  mov     [rbp+0C0h+var_30], rax
0x1800b2d82  lea     r14, [rcx+110h]
0x1800b2d89  xor     r12d, r12d
0x1800b2d8c  mov     rsi, [r14]
0x1800b2d8f  mov     r15, rdx
0x1800b2d92  mov     rdi, rcx
0x1800b2d95  mov     eax, [rsi+48h]
0x1800b2d98  test    eax, eax
0x1800b2d9a  jns     loc_1800B2F7D
0x1800b2da0  add     rsi, 50h ; 'P'
0x1800b2da4  cmp     eax, [rsi+8]
0x1800b2da7  jnz     loc_1800B2F7D
0x1800b2dad  mov     rbx, r14
0x1800b2db0  test    rsi, rsi
0x1800b2db3  jz      loc_1800B2F80
0x1800b2db9  lea     rdx, [rbp+0C0h+SRWLock]
0x1800b2dbd  mov     [rbp+0C0h+SRWLock], r12
0x1800b2dc1  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800b2dc6  mov     rax, [r14]
0x1800b2dc9  mov     rcx, [rbp+0C0h+SRWLock]; SRWLock
0x1800b2dcd  mov     dword ptr [rax], 2
0x1800b2dd3  test    rcx, rcx
0x1800b2dd6  jz      short loc_1800B2DDE
0x1800b2dd8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b2dde  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800b2de3  mov     r9, rax
0x1800b2de6  cmp     dword ptr [rax], 5
0x1800b2de9  jbe     loc_1800B30B2
0x1800b2def  mov     rdx, 400000000000h
0x1800b2df9  test    [rax+10h], rdx
0x1800b2dfd  jz      loc_1800B30B2
0x1800b2e03  mov     rcx, [rax+18h]
0x1800b2e07  and     rcx, rdx
0x1800b2e0a  cmp     rcx, [rax+18h]
0x1800b2e0e  jnz     loc_1800B30B2
0x1800b2e14  mov     r8, [r14]
0x1800b2e17  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800b2e1e  mov     [rbp+0C0h+var_110], rax
0x1800b2e22  lea     rdx, qword_180131790; int
0x1800b2e29  mov     al, [rdi+148h]
0x1800b2e2f  add     r8, 8; int
0x1800b2e33  mov     byte ptr [rbp+0C0h+var_140], al
0x1800b2e36  mov     rcx, r9; int
0x1800b2e39  mov     rax, [r15]
0x1800b2e3c  mov     [rbp+0C0h+var_108], rax
0x1800b2e40  mov     rax, [rsi+78h]
0x1800b2e44  mov     [rbp+0C0h+var_100], rax
0x1800b2e48  mov     rax, [rsi+70h]
0x1800b2e4c  mov     [rbp+0C0h+var_F8], rax
0x1800b2e50  mov     eax, [rsi+68h]
0x1800b2e53  mov     dword ptr [rbp+0C0h+var_130+4], eax
0x1800b2e56  mov     rax, [rsi+60h]
0x1800b2e5a  mov     [rbp+0C0h+var_F0], rax
0x1800b2e5e  mov     rax, [rsi+58h]
0x1800b2e62  mov     [rbp+0C0h+var_E8], rax
0x1800b2e66  mov     eax, [rsi+50h]
0x1800b2e69  mov     dword ptr [rbp+0C0h+var_128], eax
0x1800b2e6c  mov     rax, [rsi+48h]
0x1800b2e70  mov     [rbp+0C0h+var_E0], rax
0x1800b2e74  mov     eax, [rsi+20h]
0x1800b2e77  mov     dword ptr [rbp+0C0h+var_128+4], eax
0x1800b2e7a  mov     rax, [rsi+18h]
0x1800b2e7e  mov     [rbp+0C0h+var_D8], rax
0x1800b2e82  mov     eax, [rsi]
0x1800b2e84  mov     dword ptr [rbp+0C0h+var_120], eax
0x1800b2e87  mov     rax, [rsi+80h]
0x1800b2e8e  mov     [rbp+0C0h+var_D0], rax
0x1800b2e92  mov     eax, [rsi+40h]
0x1800b2e95  mov     dword ptr [rbp+0C0h+var_130], eax
0x1800b2e98  mov     rax, [rsi+38h]
0x1800b2e9c  mov     [rbp+0C0h+var_C8], rax
0x1800b2ea0  mov     eax, [rsi+8]
0x1800b2ea3  mov     dword ptr [rbp+0C0h+SRWLock], eax
0x1800b2ea6  mov     eax, 1000000h
0x1800b2eab  mov     [rbp+0C0h+var_C0], rax
0x1800b2eaf  mov     [rbp+0C0h+var_118], rax
0x1800b2eb3  lea     rax, [rbp+0C0h+var_110]
0x1800b2eb7  mov     [rsp+200h+var_150], rax; __int64
0x1800b2ebf  lea     rax, [rbp+0C0h+var_140]
0x1800b2ec3  mov     [rsp+200h+var_158], rax; __int64
0x1800b2ecb  lea     rax, [rbp+0C0h+var_108]
0x1800b2ecf  mov     [rsp+200h+var_160], rax; __int64
0x1800b2ed7  lea     rax, [rbp+0C0h+var_100]
0x1800b2edb  mov     [rsp+200h+var_168], rax; __int64
0x1800b2ee3  lea     rax, [rbp+0C0h+var_F8]
0x1800b2ee7  mov     [rsp+200h+var_170], rax; __int64
0x1800b2eef  lea     rax, [rbp+0C0h+var_130+4]
0x1800b2ef3  mov     [rsp+200h+var_178], rax; __int64
0x1800b2efb  lea     rax, [rbp+0C0h+var_F0]
0x1800b2eff  mov     [rsp+200h+var_180], rax; __int64
0x1800b2f07  lea     rax, [rbp+0C0h+var_E8]
0x1800b2f0b  mov     [rsp+200h+var_188], rax; __int64
0x1800b2f10  lea     rax, [rbp+0C0h+var_128]
0x1800b2f14  mov     [rsp+200h+var_190], rax; __int64
0x1800b2f19  lea     rax, [rbp+0C0h+var_E0]
0x1800b2f1d  mov     [rsp+200h+var_198], rax; __int64
0x1800b2f22  lea     rax, [rbp+0C0h+var_128+4]
0x1800b2f26  mov     [rsp+200h+var_1A0], rax; __int64
0x1800b2f2b  lea     rax, [rbp+0C0h+var_D8]
0x1800b2f2f  mov     [rsp+200h+var_1A8], rax; __int64
0x1800b2f34  lea     rax, [rbp+0C0h+var_120]
0x1800b2f38  mov     [rsp+200h+var_1B0], rax; __int64
0x1800b2f3d  lea     rax, [rbp+0C0h+var_D0]
0x1800b2f41  mov     [rsp+200h+var_1B8], rax; __int64
0x1800b2f46  lea     rax, [rbp+0C0h+var_130]
0x1800b2f4a  mov     [rsp+200h+var_1C0], rax; __int64
0x1800b2f4f  lea     rax, [rbp+0C0h+var_C8]
0x1800b2f53  mov     [rsp+200h+var_1C8], rax; __int64
0x1800b2f58  lea     rax, [rbp+0C0h+SRWLock]
0x1800b2f5c  mov     [rsp+200h+var_1D0], rax; __int64
0x1800b2f61  lea     rax, [rbp+0C0h+var_C0]
0x1800b2f65  mov     [rsp+200h+var_1D8], rax; __int64
0x1800b2f6a  lea     rax, [rbp+0C0h+var_118]
0x1800b2f6e  mov     qword ptr [rsp+200h+var_1E0], rax; __int64
0x1800b2f73  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U?$_tlgWrapperByVal@$00@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564566AEBU?$_tlgWrapperByVal@$00@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<char> const &)
0x1800b2f78  jmp     loc_1800B30B2
0x1800b2f7d  mov     rbx, r14
0x1800b2f80  lea     rdx, [rbp+0C0h+SRWLock]
0x1800b2f84  mov     [rbp+0C0h+SRWLock], r12
0x1800b2f88  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800b2f8d  mov     rax, [rbx]
0x1800b2f90  mov     ebx, 2
0x1800b2f95  mov     rcx, [rbp+0C0h+SRWLock]; SRWLock
0x1800b2f99  mov     [rax], ebx
0x1800b2f9b  test    rcx, rcx
0x1800b2f9e  jz      short loc_1800B2FA6
0x1800b2fa0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b2fa6  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800b2fab  mov     rsi, rax
0x1800b2fae  cmp     dword ptr [rax], 5
0x1800b2fb1  jbe     loc_1800B30B2
0x1800b2fb7  mov     rdx, 400000000000h
0x1800b2fc1  test    [rax+10h], rdx
0x1800b2fc5  jz      loc_1800B30B2
0x1800b2fcb  mov     rcx, [rax+18h]
0x1800b2fcf  and     rcx, rdx
0x1800b2fd2  cmp     rcx, [rax+18h]
0x1800b2fd6  jnz     loc_1800B30B2
0x1800b2fdc  mov     al, [rdi+148h]
0x1800b2fe2  mov     r15, [r15]
0x1800b2fe5  mov     byte ptr [rbp+0C0h+var_140], al
0x1800b2fe8  call    cs:__imp_GetCurrentThreadId
0x1800b2fee  mov     r8, [r14]
0x1800b2ff1  mov     dword ptr [rbp+0C0h+SRWLock], eax
0x1800b2ff4  mov     [rbp+0C0h+var_38], 12h
0x1800b2fff  mov     [rbp+0C0h+var_48], 1
0x1800b3007  mov     eax, [r8+48h]
0x1800b300b  mov     dword ptr [rbp+0C0h+var_130], eax
0x1800b300e  mov     eax, 1000000h
0x1800b3013  mov     [rbp+0C0h+var_118], rax
0x1800b3017  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800b301e  mov     [rbp+0C0h+var_40], rax
0x1800b3025  lea     rax, [rbp+0C0h+var_140]
0x1800b3029  mov     [rbp+0C0h+var_50], rax
0x1800b302d  test    r15, r15
0x1800b3030  jz      short loc_1800B3049
0x1800b3032  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b3036  inc     rbx
0x1800b3039  cmp     [r15+rbx*2], r12w
0x1800b303e  jnz     short loc_1800B3036
0x1800b3040  lea     ebx, ds:2[rbx*2]
0x1800b3047  jmp     short loc_1800B3050
0x1800b3049  lea     r15, S1
0x1800b3050  lea     rax, [rbp+0C0h+SRWLock]
0x1800b3054  mov     [rbp+0C0h+var_60], r15
0x1800b3058  mov     [rbp+0C0h+var_70], rax
0x1800b305c  lea     rdx, byte_1801315A7; int
0x1800b3063  lea     rax, [rbp+0C0h+var_130]
0x1800b3067  mov     [rbp+0C0h+var_58], ebx
0x1800b306a  mov     [rbp+0C0h+var_80], rax
0x1800b306e  add     r8, 8; int
0x1800b3072  lea     rax, [rbp+0C0h+var_118]
0x1800b3076  mov     [rbp+0C0h+var_54], r12d
0x1800b307a  mov     [rbp+0C0h+var_90], rax
0x1800b307e  xor     r9d, r9d; int
0x1800b3081  lea     rax, [rbp+0C0h+var_B0]
0x1800b3085  mov     [rbp+0C0h+var_68], 4
0x1800b308d  mov     [rsp+200h+var_1D8], rax; PEVENT_DATA_DESCRIPTOR
0x1800b3092  mov     rcx, rsi; int
0x1800b3095  mov     [rsp+200h+var_1E0], 8; ULONG
0x1800b309d  mov     [rbp+0C0h+var_78], 4
0x1800b30a5  mov     [rbp+0C0h+var_88], 8
0x1800b30ad  call    _tlgWriteTransfer_EventWriteTransfer
0x1800b30b2  mov     rcx, rdi
0x1800b30b5  call    ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800b30ba  mov     rcx, [rbp+0C0h+var_30]
0x1800b30c1  xor     rcx, rsp; StackCookie
0x1800b30c4  call    __security_check_cookie
0x1800b30c9  lea     r11, [rsp+200h+var_20]
0x1800b30d1  mov     rbx, [r11+38h]
0x1800b30d5  mov     rsi, [r11+40h]
0x1800b30d9  mov     rsp, r11
0x1800b30dc  pop     r15
0x1800b30de  pop     r14
0x1800b30e0  pop     r12
0x1800b30e2  pop     rdi
0x1800b30e3  pop     rbp
0x1800b30e4  retn
```
