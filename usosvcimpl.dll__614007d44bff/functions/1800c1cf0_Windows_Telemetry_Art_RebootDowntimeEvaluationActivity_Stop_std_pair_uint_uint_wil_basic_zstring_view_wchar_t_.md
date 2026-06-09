# Windows::Telemetry::Art::RebootDowntimeEvaluationActivity::Stop(std::pair<uint,uint>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,std::shared_ptr<SystemInterface::Telemetry::CorrelationVector>)

- ea: `0x1800c1cf0`
- end: `0x1800c2221`
- name: `?Stop@RebootDowntimeEvaluationActivity@Art@Telemetry@Windows@@QEAAXU?$pair@II@std@@V?$basic_zstring_view@_W@wil@@1V?$shared_ptr@VCorrelationVector@Telemetry@SystemInterface@@@6@@Z`
- size: `1329`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1800c23a8`

## callees

- `0x180001350`
- `0x18000345c`
- `0x18002ea8c`
- `0x180085644`
- `0x18008c454`
- `0x1800b781c`
- `0x1800c1cf0`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1d96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1fc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1d96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1fc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c2039`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c2039`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Telemetry::Art::RebootDowntimeEvaluationActivity::Stop(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        const wchar_t *a5)
{
  int v6; // ebx
  const wchar_t *v8; // r12
  _DWORD **v9; // rdi
  __int64 v10; // r14
  int v11; // eax
  __int64 v12; // r14
  const struct _tlgProvider_t *v13; // rax
  int v14; // esi
  _QWORD *v15; // rax
  __int64 v16; // r9
  int v17; // esi
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // r13
  __int64 v20; // rax
  const wchar_t *v21; // rdi
  const OLECHAR *v22; // r14
  const OLECHAR *v23; // r12
  __int64 v24; // r8
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rsi
  volatile signed __int32 *v30; // rbx
  PSRWLOCK SRWLock; // [rsp+D0h] [rbp-80h] BYREF
  int v32; // [rsp+D8h] [rbp-78h] BYREF
  DWORD CurrentThreadId; // [rsp+DCh] [rbp-74h] BYREF
  __int64 v34; // [rsp+E0h] [rbp-70h] BYREF
  __int64 v35; // [rsp+E8h] [rbp-68h] BYREF
  int v36; // [rsp+F0h] [rbp-60h] BYREF
  int v37; // [rsp+F4h] [rbp-5Ch] BYREF
  int v38; // [rsp+F8h] [rbp-58h] BYREF
  int v39; // [rsp+FCh] [rbp-54h] BYREF
  const wchar_t *v40; // [rsp+100h] [rbp-50h] BYREF
  __int64 v41; // [rsp+108h] [rbp-48h] BYREF
  __int64 v42; // [rsp+110h] [rbp-40h] BYREF
  __int64 v43; // [rsp+118h] [rbp-38h] BYREF
  __int64 v44; // [rsp+120h] [rbp-30h] BYREF
  __int64 v45; // [rsp+128h] [rbp-28h] BYREF
  __int64 v46; // [rsp+130h] [rbp-20h] BYREF
  __int64 v47; // [rsp+138h] [rbp-18h] BYREF
  __int64 v48; // [rsp+140h] [rbp-10h] BYREF
  __int64 v49; // [rsp+148h] [rbp-8h] BYREF
  __int64 v50; // [rsp+150h] [rbp+0h] BYREF
  __int64 v51; // [rsp+158h] [rbp+8h] BYREF
  __int64 v52; // [rsp+160h] [rbp+10h] BYREF
  _BYTE v53[40]; // [rsp+168h] [rbp+18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v54; // [rsp+190h] [rbp+40h] BYREF
  __int64 *v55; // [rsp+1B0h] [rbp+60h]
  __int64 v56; // [rsp+1B8h] [rbp+68h]
  int *v57; // [rsp+1C0h] [rbp+70h]
  __int64 v58; // [rsp+1C8h] [rbp+78h]
  DWORD *p_CurrentThreadId; // [rsp+1D0h] [rbp+80h]
  __int64 v60; // [rsp+1D8h] [rbp+88h]
  __int64 *v61; // [rsp+1E0h] [rbp+90h]
  __int64 v62; // [rsp+1E8h] [rbp+98h]
  PSRWLOCK *p_SRWLock; // [rsp+1F0h] [rbp+A0h]
  __int64 v64; // [rsp+1F8h] [rbp+A8h]
  const OLECHAR *v65; // [rsp+200h] [rbp+B0h]
  int v66; // [rsp+208h] [rbp+B8h]
  int v67; // [rsp+20Ch] [rbp+BCh]
  const OLECHAR *v68; // [rsp+210h] [rbp+C0h]
  int v69; // [rsp+218h] [rbp+C8h]
  int v70; // [rsp+21Ch] [rbp+CCh]
  const wchar_t *v71; // [rsp+220h] [rbp+D0h]
  int v72; // [rsp+228h] [rbp+D8h]
  int v73; // [rsp+22Ch] [rbp+DCh]
  const char *v74; // [rsp+230h] [rbp+E0h]
  __int64 v75; // [rsp+238h] [rbp+E8h]
  int v76; // [rsp+29Ch] [rbp+14Ch]

  v76 = HIDWORD(a2);
  v42 = (__int64)a4;
  v35 = a3;
  v6 = a2;
  v8 = a5;
  v40 = a5;
  v43 = (__int64)a5;
  v9 = (_DWORD **)(a1 + 272);
  v10 = *(_QWORD *)(a1 + 272);
  v11 = *(_DWORD *)(v10 + 72);
  if ( v11 < 0 && (v12 = v10 + 80, v11 == *(_DWORD *)(v12 + 8)) && v12 )
  {
    SRWLock = 0;
    wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    **v9 = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v13 = Windows::Telemetry::Base::Provider();
    v14 = (int)v13;
    if ( *(_DWORD *)v13 > 5u
      && (*((_QWORD *)v13 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v13 + 3) & 0x400000000000LL) == *((_QWORD *)v13 + 3) )
    {
      v44 = (__int64)"1507.2603.28012.0";
      v15 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)a5 + 8LL))(*(_QWORD *)a5, v53);
      if ( v15[3] > 0xFu )
        v15 = (_QWORD *)*v15;
      v45 = (__int64)v15;
      v46 = *a4;
      v35 = *(_QWORD *)v35;
      v36 = v76;
      v37 = v6;
      v47 = *(_QWORD *)(v12 + 120);
      v48 = *(_QWORD *)(v12 + 112);
      v38 = *(_DWORD *)(v12 + 104);
      v49 = *(_QWORD *)(v12 + 96);
      v50 = *(_QWORD *)(v12 + 88);
      v39 = *(_DWORD *)(v12 + 80);
      v51 = *(_QWORD *)(v12 + 72);
      v32 = *(_DWORD *)(v12 + 32);
      v52 = *(_QWORD *)(v12 + 24);
      CurrentThreadId = *(_DWORD *)v12;
      v43 = *(_QWORD *)(v12 + 128);
      LODWORD(v34) = *(_DWORD *)(v12 + 64);
      v40 = *(const wchar_t **)(v12 + 56);
      LODWORD(SRWLock) = *(_DWORD *)(v12 + 8);
      v41 = 0x1000000;
      v42 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v14,
        (int)&byte_1801327B7,
        *(_DWORD *)v9 + 8,
        v16,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&SRWLock,
        &v40,
        (__int64)&v34,
        (const wchar_t **)&v43,
        (__int64)&CurrentThreadId,
        (const OLECHAR **)&v52,
        (__int64)&v32,
        (const wchar_t **)&v51,
        (__int64)&v39,
        (const wchar_t **)&v50,
        (const OLECHAR **)&v49,
        (__int64)&v38,
        (const wchar_t **)&v48,
        (const OLECHAR **)&v47,
        (__int64)&v37,
        (__int64)&v36,
        (const OLECHAR **)&v35,
        (const OLECHAR **)&v46,
        (const wchar_t **)&v45,
        (const wchar_t **)&v44);
      std::string::~string((__int64)v53);
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    v17 = 2;
    **v9 = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v18 = Windows::Telemetry::Base::Provider();
    v19 = (__int64)v18;
    if ( *(_DWORD *)v18 > 5u
      && (*((_QWORD *)v18 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v18 + 3) & 0x400000000000LL) == *((_QWORD *)v18 + 3) )
    {
      v20 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)a5 + 8LL))(*(_QWORD *)a5, v53);
      v21 = (const wchar_t *)v20;
      if ( *(_QWORD *)(v20 + 24) > 0xFu )
        v21 = *(const wchar_t **)v20;
      v22 = *(const OLECHAR **)v42;
      v23 = *(const OLECHAR **)v35;
      LODWORD(SRWLock) = v76;
      LODWORD(v34) = v6;
      CurrentThreadId = GetCurrentThreadId();
      v24 = *(_QWORD *)(a1 + 272);
      v32 = *(_DWORD *)(v24 + 72);
      v41 = 0x1000000;
      v74 = "1507.2603.28012.0";
      v75 = 18;
      if ( v21 )
      {
        v25 = -1;
        do
          ++v25;
        while ( *((_BYTE *)v21 + v25) );
        v26 = v25 + 1;
      }
      else
      {
        v21 = &byte_1800F555A;
        v26 = 1;
      }
      v71 = v21;
      v72 = v26;
      v73 = 0;
      if ( v22 )
      {
        v27 = -1;
        do
          ++v27;
        while ( v22[v27] );
        v28 = 2 * v27 + 2;
      }
      else
      {
        v22 = &S1;
        v28 = 2;
      }
      v68 = v22;
      v69 = v28;
      v70 = 0;
      if ( v23 )
      {
        v29 = -1;
        do
          ++v29;
        while ( v23[v29] );
        v17 = 2 * v29 + 2;
      }
      else
      {
        v23 = &S1;
      }
      v65 = v23;
      v66 = v17;
      v67 = 0;
      p_SRWLock = &SRWLock;
      v64 = 4;
      v61 = &v34;
      v62 = 4;
      p_CurrentThreadId = &CurrentThreadId;
      v60 = 4;
      v57 = &v32;
      v58 = 4;
      v55 = &v41;
      v56 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        v19,
        (unsigned __int8 *)&word_1801326F2,
        (const GUID *)(v24 + 8),
        0,
        0xBu,
        &v54);
      std::string::~string((__int64)v53);
      v8 = v40;
    }
  }
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
  v30 = (volatile signed __int32 *)*((_QWORD *)v8 + 1);
  if ( v30 && _InterlockedExchangeAdd(v30 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
    if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
  }
}

```

## disassembly

```asm
0x1800c1cf0  mov     [rsp-8+arg_10], rbx
0x1800c1cf5  mov     [rsp-8+arg_8], rdx
0x1800c1cfa  push    rbp
0x1800c1cfb  push    rsi
0x1800c1cfc  push    rdi
0x1800c1cfd  push    r12
0x1800c1cff  push    r13
0x1800c1d01  push    r14
0x1800c1d03  push    r15
0x1800c1d05  lea     rbp, [rsp-100h]
0x1800c1d0d  sub     rsp, 250h
0x1800c1d14  mov     rax, cs:__security_cookie
0x1800c1d1b  xor     rax, rsp
0x1800c1d1e  mov     [rbp+130h+var_40], rax
0x1800c1d25  mov     r13, r9
0x1800c1d28  mov     [rbp+130h+var_170], r9
0x1800c1d2c  mov     [rbp+130h+var_198], r8
0x1800c1d30  mov     rbx, rdx
0x1800c1d33  mov     r15, rcx
0x1800c1d36  mov     r12, [rbp+130h+arg_20]
0x1800c1d3d  mov     [rbp+130h+var_180], r12
0x1800c1d41  mov     [rbp+130h+var_168], r12
0x1800c1d45  lea     rdi, [rcx+110h]
0x1800c1d4c  mov     r14, [rdi]
0x1800c1d4f  mov     eax, [r14+48h]
0x1800c1d53  xor     ecx, ecx
0x1800c1d55  test    eax, eax
0x1800c1d57  jns     loc_1800C1F9F
0x1800c1d5d  add     r14, 50h ; 'P'
0x1800c1d61  cmp     eax, [r14+8]
0x1800c1d65  jnz     loc_1800C1F9F
0x1800c1d6b  test    r14, r14
0x1800c1d6e  jz      loc_1800C1F9F
0x1800c1d74  mov     [rbp+130h+SRWLock], rcx
0x1800c1d78  lea     rdx, [rbp+130h+SRWLock]
0x1800c1d7c  mov     rcx, r15
0x1800c1d7f  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800c1d84  mov     rax, [rdi]
0x1800c1d87  mov     dword ptr [rax], 2
0x1800c1d8d  mov     rcx, [rbp+130h+SRWLock]; SRWLock
0x1800c1d91  test    rcx, rcx
0x1800c1d94  jz      short loc_1800C1D9C
0x1800c1d96  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c1d9c  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800c1da1  mov     rsi, rax
0x1800c1da4  cmp     dword ptr [rax], 5
0x1800c1da7  jbe     loc_1800C21AD
0x1800c1dad  mov     rdx, 400000000000h
0x1800c1db7  test    [rax+10h], rdx
0x1800c1dbb  jz      loc_1800C21AD
0x1800c1dc1  mov     rcx, [rax+18h]
0x1800c1dc5  and     rcx, rdx
0x1800c1dc8  cmp     rcx, [rax+18h]
0x1800c1dcc  jnz     loc_1800C21AD
0x1800c1dd2  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800c1dd9  mov     [rbp+130h+var_160], rax
0x1800c1ddd  mov     rcx, [r12]
0x1800c1de1  mov     rax, [rcx]
0x1800c1de4  lea     rdx, [rbp+130h+var_118]
0x1800c1de8  mov     rax, [rax+8]
0x1800c1dec  call    _guard_dispatch_icall
0x1800c1df1  cmp     qword ptr [rax+18h], 0Fh
0x1800c1df6  jbe     short loc_1800C1DFB
0x1800c1df8  mov     rax, [rax]
0x1800c1dfb  mov     [rbp+130h+var_158], rax
0x1800c1dff  mov     rax, [r13+0]
0x1800c1e03  mov     [rbp+130h+var_150], rax
0x1800c1e07  mov     rax, [rbp+130h+var_198]
0x1800c1e0b  mov     rax, [rax]
0x1800c1e0e  mov     [rbp+130h+var_198], rax
0x1800c1e12  mov     eax, dword ptr [rbp+130h+arg_8+4]
0x1800c1e18  mov     dword ptr [rbp+130h+var_190], eax
0x1800c1e1b  mov     dword ptr [rbp+130h+var_190+4], ebx
0x1800c1e1e  mov     rax, [r14+78h]
0x1800c1e22  mov     [rbp+130h+var_148], rax
0x1800c1e26  mov     rax, [r14+70h]
0x1800c1e2a  mov     [rbp+130h+var_140], rax
0x1800c1e2e  mov     eax, [r14+68h]
0x1800c1e32  mov     dword ptr [rbp+130h+var_188], eax
0x1800c1e35  mov     rax, [r14+60h]
0x1800c1e39  mov     [rbp+130h+var_138], rax
0x1800c1e3d  mov     rax, [r14+58h]
0x1800c1e41  mov     [rbp+130h+var_130], rax
0x1800c1e45  mov     eax, [r14+50h]
0x1800c1e49  mov     dword ptr [rbp+130h+var_188+4], eax
0x1800c1e4c  mov     rax, [r14+48h]
0x1800c1e50  mov     [rbp+130h+var_128], rax
0x1800c1e54  mov     eax, [r14+20h]
0x1800c1e58  mov     dword ptr [rbp+130h+var_1A8], eax
0x1800c1e5b  mov     rax, [r14+18h]
0x1800c1e5f  mov     [rbp+130h+var_120], rax
0x1800c1e63  mov     eax, [r14]
0x1800c1e66  mov     dword ptr [rbp+130h+var_1A8+4], eax
0x1800c1e69  mov     rax, [r14+80h]
0x1800c1e70  mov     [rbp+130h+var_168], rax
0x1800c1e74  mov     eax, [r14+40h]
0x1800c1e78  mov     dword ptr [rbp+130h+var_1A0], eax
0x1800c1e7b  mov     rax, [r14+38h]
0x1800c1e7f  mov     [rbp+130h+var_180], rax
0x1800c1e83  mov     eax, [r14+8]
0x1800c1e87  mov     dword ptr [rbp+130h+SRWLock], eax
0x1800c1e8a  mov     eax, 1000000h
0x1800c1e8f  mov     [rbp+130h+var_178], rax
0x1800c1e93  mov     [rbp+130h+var_170], rax
0x1800c1e97  mov     r8, [rdi]
0x1800c1e9a  add     r8, 8; int
0x1800c1e9e  lea     rax, [rbp+130h+var_160]
0x1800c1ea2  mov     [rsp+280h+var_1B8], rax; __int64
0x1800c1eaa  lea     rax, [rbp+130h+var_158]
0x1800c1eae  mov     [rsp+280h+var_1C0], rax; __int64
0x1800c1eb6  lea     rax, [rbp+130h+var_150]
0x1800c1eba  mov     [rsp+280h+var_1C8], rax; __int64
0x1800c1ec2  lea     rax, [rbp+130h+var_198]
0x1800c1ec6  mov     [rsp+280h+var_1D0], rax; __int64
0x1800c1ece  lea     rax, [rbp+130h+var_190]
0x1800c1ed2  mov     [rsp+280h+var_1D8], rax; __int64
0x1800c1eda  lea     rax, [rbp+130h+var_190+4]
0x1800c1ede  mov     [rsp+280h+var_1E0], rax; __int64
0x1800c1ee6  lea     rax, [rbp+130h+var_148]
0x1800c1eea  mov     [rsp+280h+var_1E8], rax; __int64
0x1800c1ef2  lea     rax, [rbp+130h+var_140]
0x1800c1ef6  mov     [rsp+280h+var_1F0], rax; __int64
0x1800c1efe  lea     rax, [rbp+130h+var_188]
0x1800c1f02  mov     [rsp+280h+var_1F8], rax; __int64
0x1800c1f0a  lea     rax, [rbp+130h+var_138]
0x1800c1f0e  mov     [rsp+280h+var_200], rax; __int64
0x1800c1f16  lea     rax, [rbp+130h+var_130]
0x1800c1f1a  mov     [rsp+280h+var_208], rax; __int64
0x1800c1f1f  lea     rax, [rbp+130h+var_188+4]
0x1800c1f23  mov     [rsp+280h+var_210], rax; __int64
0x1800c1f28  lea     rax, [rbp+130h+var_128]
0x1800c1f2c  mov     [rsp+280h+var_218], rax; __int64
0x1800c1f31  lea     rax, [rbp+130h+var_1A8]
0x1800c1f35  mov     [rsp+280h+var_220], rax; __int64
0x1800c1f3a  lea     rax, [rbp+130h+var_120]
0x1800c1f3e  mov     [rsp+280h+var_228], rax; __int64
0x1800c1f43  lea     rax, [rbp+130h+var_1A8+4]
0x1800c1f47  mov     [rsp+280h+var_230], rax; __int64
0x1800c1f4c  lea     rax, [rbp+130h+var_168]
0x1800c1f50  mov     [rsp+280h+var_238], rax; __int64
0x1800c1f55  lea     rax, [rbp+130h+var_1A0]
0x1800c1f59  mov     [rsp+280h+var_240], rax; __int64
0x1800c1f5e  lea     rax, [rbp+130h+var_180]
0x1800c1f62  mov     [rsp+280h+var_248], rax; __int64
0x1800c1f67  lea     rax, [rbp+130h+SRWLock]
0x1800c1f6b  mov     [rsp+280h+var_250], rax; __int64
0x1800c1f70  lea     rax, [rbp+130h+var_178]
0x1800c1f74  mov     [rsp+280h+var_258], rax; __int64
0x1800c1f79  lea     rax, [rbp+130h+var_170]
0x1800c1f7d  mov     qword ptr [rsp+280h+var_260], rax; __int64
0x1800c1f82  lea     rdx, byte_1801327B7; int
0x1800c1f89  mov     rcx, rsi; int
0x1800c1f8c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U4@U4@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456446655@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800c1f91  lea     rcx, [rbp+130h+var_118]
0x1800c1f95  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800c1f9a  jmp     loc_1800C21AD
0x1800c1f9f  mov     [rbp+130h+SRWLock], rcx
0x1800c1fa3  lea     rdx, [rbp+130h+SRWLock]
0x1800c1fa7  mov     rcx, r15
0x1800c1faa  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800c1faf  mov     rax, [rdi]
0x1800c1fb2  mov     esi, 2
0x1800c1fb7  mov     [rax], esi
0x1800c1fb9  mov     rcx, [rbp+130h+SRWLock]; SRWLock
0x1800c1fbd  test    rcx, rcx
0x1800c1fc0  jz      short loc_1800C1FC8
0x1800c1fc2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c1fc8  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800c1fcd  mov     r13, rax
0x1800c1fd0  cmp     dword ptr [rax], 5
0x1800c1fd3  jbe     loc_1800C21AD
0x1800c1fd9  mov     rdx, 400000000000h
0x1800c1fe3  test    [rax+10h], rdx
0x1800c1fe7  jz      loc_1800C21AD
0x1800c1fed  mov     rcx, [rax+18h]
0x1800c1ff1  and     rcx, rdx
0x1800c1ff4  cmp     rcx, [rax+18h]
0x1800c1ff8  jnz     loc_1800C21AD
0x1800c1ffe  mov     rcx, [r12]
0x1800c2002  mov     rax, [rcx]
0x1800c2005  lea     rdx, [rbp+130h+var_118]
0x1800c2009  mov     rax, [rax+8]
0x1800c200d  call    _guard_dispatch_icall
0x1800c2012  mov     rdi, rax
0x1800c2015  cmp     qword ptr [rax+18h], 0Fh
0x1800c201a  jbe     short loc_1800C201F
0x1800c201c  mov     rdi, [rax]
0x1800c201f  mov     r14, [rbp+130h+var_170]
0x1800c2023  mov     r14, [r14]
0x1800c2026  mov     rax, [rbp+130h+var_198]
0x1800c202a  mov     r12, [rax]
0x1800c202d  mov     ecx, dword ptr [rbp+130h+arg_8+4]
0x1800c2033  mov     dword ptr [rbp+130h+SRWLock], ecx
0x1800c2036  mov     dword ptr [rbp+130h+var_1A0], ebx
0x1800c2039  call    cs:__imp_GetCurrentThreadId
0x1800c203f  mov     dword ptr [rbp+130h+var_1A8+4], eax
0x1800c2042  mov     r8, [r15+110h]
0x1800c2049  mov     eax, [r8+48h]
0x1800c204d  mov     dword ptr [rbp+130h+var_1A8], eax
0x1800c2050  mov     eax, 1000000h
0x1800c2055  mov     [rbp+130h+var_178], rax
0x1800c2059  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800c2060  mov     [rbp+130h+var_50], rax
0x1800c2067  mov     [rbp+130h+var_48], 12h
0x1800c2072  xor     edx, edx
0x1800c2074  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800c2078  test    rdi, rdi
0x1800c207b  jz      short loc_1800C208C
0x1800c207d  mov     rax, rcx
0x1800c2080  inc     rax
0x1800c2083  cmp     [rdi+rax], dl
0x1800c2086  jnz     short loc_1800C2080
0x1800c2088  inc     eax
0x1800c208a  jmp     short loc_1800C2098
0x1800c208c  lea     rdi, byte_1800F555A
0x1800c2093  mov     eax, 1
0x1800c2098  mov     [rbp+130h+var_60], rdi
0x1800c209f  mov     [rbp+130h+var_58], eax
0x1800c20a5  mov     [rbp+130h+var_54], edx
0x1800c20ab  test    r14, r14
0x1800c20ae  jz      short loc_1800C20C6
0x1800c20b0  mov     rax, rcx
0x1800c20b3  inc     rax
0x1800c20b6  cmp     [r14+rax*2], dx
0x1800c20bb  jnz     short loc_1800C20B3
0x1800c20bd  lea     eax, ds:2[rax*2]
0x1800c20c4  jmp     short loc_1800C20CF
0x1800c20c6  lea     r14, S1
0x1800c20cd  mov     eax, esi
0x1800c20cf  mov     [rbp+130h+var_70], r14
0x1800c20d6  mov     [rbp+130h+var_68], eax
0x1800c20dc  mov     [rbp+130h+var_64], edx
0x1800c20e2  test    r12, r12
0x1800c20e5  jz      short loc_1800C20FD
0x1800c20e7  mov     rsi, rcx
0x1800c20ea  inc     rsi
0x1800c20ed  cmp     [r12+rsi*2], dx
0x1800c20f2  jnz     short loc_1800C20EA
0x1800c20f4  lea     esi, ds:2[rsi*2]
0x1800c20fb  jmp     short loc_1800C2104
0x1800c20fd  lea     r12, S1
0x1800c2104  mov     [rbp+130h+var_80], r12
0x1800c210b  mov     [rbp+130h+var_78], esi
0x1800c2111  mov     [rbp+130h+var_74], edx
0x1800c2117  lea     rax, [rbp+130h+SRWLock]
0x1800c211b  mov     [rbp+130h+var_90], rax
0x1800c2122  mov     [rbp+130h+var_88], 4
0x1800c212d  lea     rax, [rbp+130h+var_1A0]
0x1800c2131  mov     [rbp+130h+var_A0], rax
0x1800c2138  mov     [rbp+130h+var_98], 4
0x1800c2143  lea     rax, [rbp+130h+var_1A8+4]
0x1800c2147  mov     [rbp+130h+var_B0], rax
0x1800c214e  mov     [rbp+130h+var_A8], 4
0x1800c2159  lea     rax, [rbp+130h+var_1A8]
0x1800c215d  mov     [rbp+130h+var_C0], rax
0x1800c2161  mov     [rbp+130h+var_B8], 4
0x1800c2169  lea     rax, [rbp+130h+var_178]
0x1800c216d  mov     [rbp+130h+var_D0], rax
0x1800c2171  mov     [rbp+130h+var_C8], 8
0x1800c2179  add     r8, 8; int
0x1800c217d  lea     rax, [rbp+130h+var_F0]
0x1800c2181  mov     [rsp+280h+var_258], rax; PEVENT_DATA_DESCRIPTOR
0x1800c2186  mov     [rsp+280h+var_260], 0Bh; ULONG
0x1800c218e  xor     r9d, r9d; int
0x1800c2191  lea     rdx, word_1801326F2; int
0x1800c2198  mov     rcx, r13; int
0x1800c219b  call    _tlgWriteTransfer_EventWriteTransfer
0x1800c21a0  lea     rcx, [rbp+130h+var_118]
0x1800c21a4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800c21a9  mov     r12, [rbp+130h+var_180]
0x1800c21ad  mov     rcx, r15
0x1800c21b0  call    ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800c21b5  nop
0x1800c21b6  mov     rbx, [r12+8]
0x1800c21bb  test    rbx, rbx
0x1800c21be  jz      short loc_1800C21F7
0x1800c21c0  or      eax, 0FFFFFFFFh
0x1800c21c3  lock xadd [rbx+8], eax
0x1800c21c8  cmp     eax, 1
0x1800c21cb  jnz     short loc_1800C21F7
0x1800c21cd  mov     rax, [rbx]
0x1800c21d0  mov     rcx, rbx
0x1800c21d3  mov     rax, [rax]
0x1800c21d6  call    _guard_dispatch_icall
0x1800c21db  or      eax, 0FFFFFFFFh
0x1800c21de  lock xadd [rbx+0Ch], eax
0x1800c21e3  cmp     eax, 1
0x1800c21e6  jnz     short loc_1800C21F7
0x1800c21e8  mov     rax, [rbx]
0x1800c21eb  mov     rcx, rbx
0x1800c21ee  mov     rax, [rax+8]
0x1800c21f2  call    _guard_dispatch_icall
0x1800c21f7  mov     rcx, [rbp+130h+var_40]
0x1800c21fe  xor     rcx, rsp; StackCookie
0x1800c2201  call    __security_check_cookie
0x1800c2206  mov     rbx, [rsp+280h+arg_10]
0x1800c220e  add     rsp, 250h
0x1800c2215  pop     r15
0x1800c2217  pop     r14
0x1800c2219  pop     r13
  ... truncated ...
```
