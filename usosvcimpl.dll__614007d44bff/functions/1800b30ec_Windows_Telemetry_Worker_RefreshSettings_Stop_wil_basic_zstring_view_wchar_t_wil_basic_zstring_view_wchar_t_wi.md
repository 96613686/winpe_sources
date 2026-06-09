# Windows::Telemetry::Worker::RefreshSettings::Stop(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x1800b30ec`
- end: `0x1800b3546`
- name: `?Stop@RefreshSettings@Worker@Telemetry@Windows@@QEAAXV?$basic_zstring_view@_W@wil@@00@Z`
- size: `1114`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800b3550`

## callees

- `0x180001350`
- `0x1800022d4`
- `0x180085644`
- `0x18008c454`
- `0x1800b30ec`
- `0x1800b781c`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b3186`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b3380`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b3186`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b3380`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b33d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800b33d4`

## pseudocode

```c
void __fastcall Windows::Telemetry::Worker::RefreshSettings::Stop(__int64 a1, __int64 *a2, __int64 *a3, __int64 *a4)
{
  _DWORD **v4; // rsi
  __int64 v5; // r14
  int v10; // eax
  int *v11; // r14
  _DWORD **v12; // rbx
  RTL_SRWLOCK *v13; // rcx
  const struct _tlgProvider_t *v14; // rax
  _DWORD *v15; // r8
  _DWORD *v16; // rax
  int v17; // ebx
  RTL_SRWLOCK *v18; // rcx
  const struct _tlgProvider_t *v19; // rax
  __int64 v20; // r13
  const OLECHAR *v21; // r14
  const OLECHAR *v22; // r15
  const OLECHAR *v23; // r12
  DWORD CurrentThreadId; // eax
  _DWORD *v25; // r8
  __int64 v26; // rax
  __int64 v27; // rcx
  int v28; // ecx
  __int64 v29; // rcx
  int v30; // ecx
  __int64 v31; // [rsp+D8h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+E0h] [rbp-78h] BYREF
  __int64 v33; // [rsp+E8h] [rbp-70h] BYREF
  __int64 v34; // [rsp+F0h] [rbp-68h] BYREF
  int v35; // [rsp+F8h] [rbp-60h] BYREF
  int v36; // [rsp+FCh] [rbp-5Ch] BYREF
  int v37; // [rsp+100h] [rbp-58h] BYREF
  int v38; // [rsp+104h] [rbp-54h] BYREF
  __int64 v39; // [rsp+108h] [rbp-50h] BYREF
  __int64 v40; // [rsp+110h] [rbp-48h] BYREF
  __int64 v41; // [rsp+118h] [rbp-40h] BYREF
  __int64 v42; // [rsp+120h] [rbp-38h] BYREF
  __int64 v43; // [rsp+128h] [rbp-30h] BYREF
  __int64 v44; // [rsp+130h] [rbp-28h] BYREF
  __int64 v45; // [rsp+138h] [rbp-20h] BYREF
  __int64 v46; // [rsp+140h] [rbp-18h] BYREF
  __int64 v47; // [rsp+148h] [rbp-10h] BYREF
  __int64 v48; // [rsp+150h] [rbp-8h] BYREF
  __int64 v49; // [rsp+158h] [rbp+0h] BYREF
  __int64 v50; // [rsp+160h] [rbp+8h] BYREF
  __int64 v51; // [rsp+168h] [rbp+10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+178h] [rbp+20h] BYREF
  __int64 *v53; // [rsp+198h] [rbp+40h]
  __int64 v54; // [rsp+1A0h] [rbp+48h]
  __int64 *v55; // [rsp+1A8h] [rbp+50h]
  __int64 v56; // [rsp+1B0h] [rbp+58h]
  PSRWLOCK *p_SRWLock; // [rsp+1B8h] [rbp+60h]
  __int64 v58; // [rsp+1C0h] [rbp+68h]
  const OLECHAR *v59; // [rsp+1C8h] [rbp+70h]
  int v60; // [rsp+1D0h] [rbp+78h]
  int v61; // [rsp+1D4h] [rbp+7Ch]
  __int64 *v62; // [rsp+1D8h] [rbp+80h]
  __int64 v63; // [rsp+1E0h] [rbp+88h]
  const OLECHAR *v64; // [rsp+1E8h] [rbp+90h]
  int v65; // [rsp+1F0h] [rbp+98h]
  int v66; // [rsp+1F4h] [rbp+9Ch]
  const OLECHAR *v67; // [rsp+1F8h] [rbp+A0h]
  int v68; // [rsp+200h] [rbp+A8h]
  int v69; // [rsp+204h] [rbp+ACh]
  const char *v70; // [rsp+208h] [rbp+B0h]
  __int64 v71; // [rsp+210h] [rbp+B8h]

  v4 = (_DWORD **)(a1 + 272);
  v34 = (__int64)a2;
  v5 = *(_QWORD *)(a1 + 272);
  v10 = *(_DWORD *)(v5 + 72);
  if ( v10 < 0 && (v11 = (int *)(v5 + 80), v10 == v11[2]) )
  {
    v12 = (_DWORD **)(a1 + 272);
    if ( v11 )
    {
      SRWLock = 0;
      wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        a1,
        &SRWLock);
      v13 = SRWLock;
      **v4 = 2;
      if ( v13 )
        ReleaseSRWLockExclusive(v13);
      v14 = Windows::Telemetry::Base::Provider();
      if ( *(_DWORD *)v14 > 5u
        && (*((_QWORD *)v14 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v14 + 3) & 0x400000000000LL) == *((_QWORD *)v14 + 3) )
      {
        v15 = *v4;
        v39 = (__int64)"1507.2603.28012.0";
        v40 = *a4;
        v41 = *a3;
        LOBYTE(v31) = *(_BYTE *)(a1 + 328);
        v42 = *a2;
        v43 = *((_QWORD *)v11 + 15);
        v44 = *((_QWORD *)v11 + 14);
        v35 = v11[26];
        v45 = *((_QWORD *)v11 + 12);
        v46 = *((_QWORD *)v11 + 11);
        v36 = v11[20];
        v47 = *((_QWORD *)v11 + 9);
        v37 = v11[8];
        v48 = *((_QWORD *)v11 + 3);
        v38 = *v11;
        v49 = *((_QWORD *)v11 + 16);
        LODWORD(v33) = v11[16];
        v50 = *((_QWORD *)v11 + 7);
        LODWORD(SRWLock) = v11[2];
        v51 = 0x1000000;
        v34 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          (int)v14,
          (int)&dword_180131624,
          (_DWORD)v15 + 8,
          (__int64)v14,
          (__int64)&v34,
          (__int64)&v51,
          (__int64)&SRWLock,
          (const wchar_t **)&v50,
          (__int64)&v33,
          (const wchar_t **)&v49,
          (__int64)&v38,
          (const OLECHAR **)&v48,
          (__int64)&v37,
          (const wchar_t **)&v47,
          (__int64)&v36,
          (const wchar_t **)&v46,
          (const OLECHAR **)&v45,
          (__int64)&v35,
          (const wchar_t **)&v44,
          (const OLECHAR **)&v43,
          (const OLECHAR **)&v42,
          (__int64)&v31,
          (const OLECHAR **)&v41,
          (const OLECHAR **)&v40,
          (const wchar_t **)&v39);
      }
      goto LABEL_31;
    }
  }
  else
  {
    v12 = (_DWORD **)(a1 + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v16 = *v12;
  v17 = 2;
  v18 = SRWLock;
  *v16 = 2;
  if ( v18 )
    ReleaseSRWLockExclusive(v18);
  v19 = Windows::Telemetry::Base::Provider();
  v20 = (__int64)v19;
  if ( *(_DWORD *)v19 > 5u
    && (*((_QWORD *)v19 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v19 + 3) & 0x400000000000LL) == *((_QWORD *)v19 + 3) )
  {
    v21 = (const OLECHAR *)*a3;
    v22 = (const OLECHAR *)*a4;
    LOBYTE(v31) = *(_BYTE *)(a1 + 328);
    v23 = *(const OLECHAR **)v34;
    CurrentThreadId = GetCurrentThreadId();
    v25 = *v4;
    LODWORD(SRWLock) = CurrentThreadId;
    v71 = 18;
    LODWORD(v33) = v25[18];
    v34 = 0x1000000;
    v70 = "1507.2603.28012.0";
    v26 = -1;
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
    v67 = v22;
    v68 = v28;
    v69 = 0;
    if ( v21 )
    {
      v29 = -1;
      do
        ++v29;
      while ( v21[v29] );
      v30 = 2 * v29 + 2;
    }
    else
    {
      v21 = &S1;
      v30 = 2;
    }
    v65 = v30;
    v62 = &v31;
    v64 = v21;
    v66 = 0;
    v63 = 1;
    if ( v23 )
    {
      do
        ++v26;
      while ( v23[v26] );
      v17 = 2 * v26 + 2;
    }
    else
    {
      v23 = &S1;
    }
    v61 = 0;
    p_SRWLock = &SRWLock;
    v59 = v23;
    v55 = &v33;
    v60 = v17;
    v53 = &v34;
    v58 = 4;
    v56 = 4;
    v54 = 8;
    tlgWriteTransfer_EventWriteTransfer(v20, (unsigned __int8 *)&word_180131512, (const GUID *)(v25 + 2), 0, 0xAu, &v52);
  }
LABEL_31:
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x1800b30ec  mov     rax, rsp
0x1800b30ef  mov     [rax+10h], rbx
0x1800b30f3  mov     [rax+18h], rsi
0x1800b30f7  mov     [rax+20h], rdi
0x1800b30fb  push    rbp
0x1800b30fc  push    r12
0x1800b30fe  push    r13
0x1800b3100  push    r14
0x1800b3102  push    r15
0x1800b3104  lea     rbp, [rax-0F8h]
0x1800b310b  sub     rsp, 220h
0x1800b3112  mov     rax, cs:__security_cookie
0x1800b3119  xor     rax, rsp
0x1800b311c  mov     [rbp+0F0h+var_30], rax
0x1800b3123  lea     rsi, [rcx+110h]
0x1800b312a  mov     [rbp+0F0h+var_158], rdx
0x1800b312e  mov     r14, [rsi]
0x1800b3131  mov     r15, r9
0x1800b3134  mov     r12, r8
0x1800b3137  mov     r13, rdx
0x1800b313a  mov     rdi, rcx
0x1800b313d  mov     eax, [r14+48h]
0x1800b3141  test    eax, eax
0x1800b3143  jns     loc_1800B3359
0x1800b3149  add     r14, 50h ; 'P'
0x1800b314d  cmp     eax, [r14+8]
0x1800b3151  jnz     loc_1800B3359
0x1800b3157  mov     rbx, rsi
0x1800b315a  test    r14, r14
0x1800b315d  jz      loc_1800B335C
0x1800b3163  lea     rdx, [rbp+0F0h+SRWLock]
0x1800b3167  mov     [rbp+0F0h+SRWLock], 0
0x1800b316f  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800b3174  mov     rax, [rsi]
0x1800b3177  mov     rcx, [rbp+0F0h+SRWLock]; SRWLock
0x1800b317b  mov     dword ptr [rax], 2
0x1800b3181  test    rcx, rcx
0x1800b3184  jz      short loc_1800B318C
0x1800b3186  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b318c  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800b3191  mov     r9, rax
0x1800b3194  cmp     dword ptr [rax], 5
0x1800b3197  jbe     loc_1800B350E
0x1800b319d  mov     rdx, 400000000000h
0x1800b31a7  test    [rax+10h], rdx
0x1800b31ab  jz      loc_1800B350E
0x1800b31b1  mov     rcx, [rax+18h]
0x1800b31b5  and     rcx, rdx
0x1800b31b8  cmp     rcx, [rax+18h]
0x1800b31bc  jnz     loc_1800B350E
0x1800b31c2  mov     r8, [rsi]
0x1800b31c5  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800b31cc  mov     [rbp+0F0h+var_140], rax
0x1800b31d0  add     r8, 8; int
0x1800b31d4  mov     rax, [r15]
0x1800b31d7  mov     [rbp+0F0h+var_138], rax
0x1800b31db  mov     rax, [r12]
0x1800b31df  mov     [rbp+0F0h+var_130], rax
0x1800b31e3  mov     al, [rdi+148h]
0x1800b31e9  mov     byte ptr [rbp+0F0h+var_170], al
0x1800b31ec  mov     rax, [r13+0]
0x1800b31f0  mov     [rbp+0F0h+var_128], rax
0x1800b31f4  mov     rax, [r14+78h]
0x1800b31f8  mov     [rbp+0F0h+var_120], rax
0x1800b31fc  mov     rax, [r14+70h]
0x1800b3200  mov     [rbp+0F0h+var_118], rax
0x1800b3204  mov     eax, [r14+68h]
0x1800b3208  mov     dword ptr [rbp+0F0h+var_150], eax
0x1800b320b  mov     rax, [r14+60h]
0x1800b320f  mov     [rbp+0F0h+var_110], rax
0x1800b3213  mov     rax, [r14+58h]
0x1800b3217  mov     [rbp+0F0h+var_108], rax
0x1800b321b  mov     eax, [r14+50h]
0x1800b321f  mov     dword ptr [rbp+0F0h+var_150+4], eax
0x1800b3222  mov     rax, [r14+48h]
0x1800b3226  mov     [rbp+0F0h+var_100], rax
0x1800b322a  mov     eax, [r14+20h]
0x1800b322e  mov     dword ptr [rbp+0F0h+var_148], eax
0x1800b3231  mov     rax, [r14+18h]
0x1800b3235  mov     [rbp+0F0h+var_F8], rax
0x1800b3239  mov     eax, [r14]
0x1800b323c  mov     dword ptr [rbp+0F0h+var_148+4], eax
0x1800b323f  mov     rax, [r14+80h]
0x1800b3246  mov     [rbp+0F0h+var_F0], rax
0x1800b324a  mov     eax, [r14+40h]
0x1800b324e  mov     dword ptr [rbp+0F0h+var_160], eax
0x1800b3251  mov     rax, [r14+38h]
0x1800b3255  mov     [rbp+0F0h+var_E8], rax
0x1800b3259  mov     eax, [r14+8]
0x1800b325d  mov     dword ptr [rbp+0F0h+SRWLock], eax
0x1800b3260  mov     eax, 1000000h
0x1800b3265  mov     [rbp+0F0h+var_E0], rax
0x1800b3269  mov     [rbp+0F0h+var_158], rax
0x1800b326d  lea     rax, [rbp+0F0h+var_140]
0x1800b3271  mov     [rsp+240h+var_180], rax; __int64
0x1800b3279  lea     rax, [rbp+0F0h+var_138]
0x1800b327d  mov     [rsp+240h+var_188], rax; __int64
0x1800b3285  lea     rax, [rbp+0F0h+var_130]
0x1800b3289  mov     [rsp+240h+var_190], rax; __int64
0x1800b3291  lea     rax, [rbp+0F0h+var_170]
0x1800b3295  mov     [rsp+240h+var_198], rax; __int64
0x1800b329d  lea     rax, [rbp+0F0h+var_128]
0x1800b32a1  mov     [rsp+240h+var_1A0], rax; __int64
0x1800b32a9  lea     rax, [rbp+0F0h+var_120]
0x1800b32ad  mov     [rsp+240h+var_1A8], rax; __int64
0x1800b32b5  lea     rax, [rbp+0F0h+var_118]
0x1800b32b9  mov     [rsp+240h+var_1B0], rax; __int64
0x1800b32c1  lea     rax, [rbp+0F0h+var_150]
0x1800b32c5  mov     [rsp+240h+var_1B8], rax; __int64
0x1800b32cd  lea     rax, [rbp+0F0h+var_110]
0x1800b32d1  mov     [rsp+240h+var_1C0], rax; __int64
0x1800b32d9  lea     rax, [rbp+0F0h+var_108]
0x1800b32dd  mov     [rsp+240h+var_1C8], rax; __int64
0x1800b32e2  lea     rax, [rbp+0F0h+var_150+4]
0x1800b32e6  mov     [rsp+240h+var_1D0], rax; __int64
0x1800b32eb  lea     rax, [rbp+0F0h+var_100]
0x1800b32ef  mov     [rsp+240h+var_1D8], rax; __int64
0x1800b32f4  lea     rax, [rbp+0F0h+var_148]
0x1800b32f8  mov     [rsp+240h+var_1E0], rax; __int64
0x1800b32fd  lea     rax, [rbp+0F0h+var_F8]
0x1800b3301  mov     [rsp+240h+var_1E8], rax; __int64
0x1800b3306  lea     rax, [rbp+0F0h+var_148+4]
0x1800b330a  mov     [rsp+240h+var_1F0], rax; __int64
0x1800b330f  lea     rax, [rbp+0F0h+var_F0]
0x1800b3313  mov     [rsp+240h+var_1F8], rax; __int64
0x1800b3318  lea     rax, [rbp+0F0h+var_160]
0x1800b331c  mov     [rsp+240h+var_200], rax; __int64
0x1800b3321  lea     rax, [rbp+0F0h+var_E8]
0x1800b3325  mov     [rsp+240h+var_208], rax; __int64
0x1800b332a  lea     rax, [rbp+0F0h+SRWLock]
0x1800b332e  mov     [rsp+240h+var_210], rax; __int64
0x1800b3333  lea     rax, [rbp+0F0h+var_E0]
0x1800b3337  mov     rcx, r9; int
0x1800b333a  mov     [rsp+240h+var_218], rax; __int64
0x1800b333f  lea     rdx, dword_180131624; int
0x1800b3346  lea     rax, [rbp+0F0h+var_158]
0x1800b334a  mov     qword ptr [rsp+240h+var_220], rax; __int64
0x1800b334f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U?$_tlgWrapperByVal@$00@@U4@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564566AEBU?$_tlgWrapperByVal@$00@@665@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &)
0x1800b3354  jmp     loc_1800B350E
0x1800b3359  mov     rbx, rsi
0x1800b335c  lea     rdx, [rbp+0F0h+SRWLock]
0x1800b3360  mov     [rbp+0F0h+SRWLock], 0
0x1800b3368  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800b336d  mov     rax, [rbx]
0x1800b3370  mov     ebx, 2
0x1800b3375  mov     rcx, [rbp+0F0h+SRWLock]; SRWLock
0x1800b3379  mov     [rax], ebx
0x1800b337b  test    rcx, rcx
0x1800b337e  jz      short loc_1800B3386
0x1800b3380  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b3386  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800b338b  mov     r13, rax
0x1800b338e  cmp     dword ptr [rax], 5
0x1800b3391  jbe     loc_1800B350E
0x1800b3397  mov     rdx, 400000000000h
0x1800b33a1  test    [rax+10h], rdx
0x1800b33a5  jz      loc_1800B350E
0x1800b33ab  mov     rcx, [rax+18h]
0x1800b33af  and     rcx, rdx
0x1800b33b2  cmp     rcx, [rax+18h]
0x1800b33b6  jnz     loc_1800B350E
0x1800b33bc  mov     r14, [r12]
0x1800b33c0  mov     r12, [rbp+0F0h+var_158]
0x1800b33c4  mov     al, [rdi+148h]
0x1800b33ca  mov     r15, [r15]
0x1800b33cd  mov     byte ptr [rbp+0F0h+var_170], al
0x1800b33d0  mov     r12, [r12]
0x1800b33d4  call    cs:__imp_GetCurrentThreadId
0x1800b33da  mov     r8, [rsi]
0x1800b33dd  lea     r9, S1
0x1800b33e4  mov     dword ptr [rbp+0F0h+SRWLock], eax
0x1800b33e7  xor     edx, edx
0x1800b33e9  mov     [rbp+0F0h+var_38], 12h
0x1800b33f4  mov     eax, [r8+48h]
0x1800b33f8  mov     dword ptr [rbp+0F0h+var_160], eax
0x1800b33fb  mov     eax, 1000000h
0x1800b3400  mov     [rbp+0F0h+var_158], rax
0x1800b3404  lea     rax, a15072603280120; "1507.2603.28012.0"
0x1800b340b  mov     [rbp+0F0h+var_40], rax
0x1800b3412  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b3416  test    r15, r15
0x1800b3419  jz      short loc_1800B3431
0x1800b341b  mov     rcx, rax
0x1800b341e  inc     rcx
0x1800b3421  cmp     [r15+rcx*2], dx
0x1800b3426  jnz     short loc_1800B341E
0x1800b3428  lea     ecx, ds:2[rcx*2]
0x1800b342f  jmp     short loc_1800B3436
0x1800b3431  mov     r15, r9
0x1800b3434  mov     ecx, ebx
0x1800b3436  mov     [rbp+0F0h+var_50], r15
0x1800b343d  mov     [rbp+0F0h+var_48], ecx
0x1800b3443  mov     [rbp+0F0h+var_44], edx
0x1800b3449  test    r14, r14
0x1800b344c  jz      short loc_1800B3464
0x1800b344e  mov     rcx, rax
0x1800b3451  inc     rcx
0x1800b3454  cmp     [r14+rcx*2], dx
0x1800b3459  jnz     short loc_1800B3451
0x1800b345b  lea     ecx, ds:2[rcx*2]
0x1800b3462  jmp     short loc_1800B3469
0x1800b3464  mov     r14, r9
0x1800b3467  mov     ecx, ebx
0x1800b3469  mov     [rbp+0F0h+var_58], ecx
0x1800b346f  lea     rcx, [rbp+0F0h+var_170]
0x1800b3473  mov     [rbp+0F0h+var_70], rcx
0x1800b347a  mov     [rbp+0F0h+var_60], r14
0x1800b3481  mov     [rbp+0F0h+var_54], edx
0x1800b3487  mov     [rbp+0F0h+var_68], 1
0x1800b3492  test    r12, r12
0x1800b3495  jz      short loc_1800B34AA
0x1800b3497  inc     rax
0x1800b349a  cmp     [r12+rax*2], dx
0x1800b349f  jnz     short loc_1800B3497
0x1800b34a1  lea     ebx, ds:2[rax*2]
0x1800b34a8  jmp     short loc_1800B34AD
0x1800b34aa  mov     r12, r9
0x1800b34ad  lea     rax, [rbp+0F0h+SRWLock]
0x1800b34b1  mov     [rbp+0F0h+var_74], edx
0x1800b34b4  mov     [rbp+0F0h+var_90], rax
0x1800b34b8  lea     rdx, word_180131512; int
0x1800b34bf  lea     rax, [rbp+0F0h+var_160]
0x1800b34c3  mov     [rbp+0F0h+var_80], r12
0x1800b34c7  mov     [rbp+0F0h+var_A0], rax
0x1800b34cb  add     r8, 8; int
0x1800b34cf  lea     rax, [rbp+0F0h+var_158]
0x1800b34d3  mov     [rbp+0F0h+var_78], ebx
0x1800b34d6  mov     [rbp+0F0h+var_B0], rax
0x1800b34da  xor     r9d, r9d; int
0x1800b34dd  lea     rax, [rbp+0F0h+var_D0]
0x1800b34e1  mov     [rbp+0F0h+var_88], 4
0x1800b34e9  mov     [rsp+240h+var_218], rax; PEVENT_DATA_DESCRIPTOR
0x1800b34ee  mov     rcx, r13; int
0x1800b34f1  mov     [rsp+240h+var_220], 0Ah; ULONG
0x1800b34f9  mov     [rbp+0F0h+var_98], 4
0x1800b3501  mov     [rbp+0F0h+var_A8], 8
0x1800b3509  call    _tlgWriteTransfer_EventWriteTransfer
0x1800b350e  mov     rcx, rdi
0x1800b3511  call    ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800b3516  mov     rcx, [rbp+0F0h+var_30]
0x1800b351d  xor     rcx, rsp; StackCookie
0x1800b3520  call    __security_check_cookie
0x1800b3525  lea     r11, [rsp+240h+var_20]
0x1800b352d  mov     rbx, [r11+38h]
0x1800b3531  mov     rsi, [r11+40h]
0x1800b3535  mov     rdi, [r11+48h]
0x1800b3539  mov     rsp, r11
0x1800b353c  pop     r15
0x1800b353e  pop     r14
0x1800b3540  pop     r13
0x1800b3542  pop     r12
0x1800b3544  pop     rbp
0x1800b3545  retn
```
