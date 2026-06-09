# Telemetry4UpdateCli::RunCmd::StopActivity(void)

- ea: `0x18000cbb0`
- end: `0x18000cee4`
- name: `?StopActivity@RunCmd@Telemetry4UpdateCli@@MEAAXXZ`
- size: `820`
- prototype: `void __fastcall(Telemetry4UpdateCli::RunCmd *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x18000109c`
- `0x180001350`
- `0x180004158`
- `0x18000cbb0`
- `0x18000cf08`
- `0x18000d038`
- `0x180010310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cdba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cdba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cdf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cdf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ce76`

## pseudocode

```c
void __fastcall Telemetry4UpdateCli::RunCmd::StopActivity(Telemetry4UpdateCli::RunCmd *this)
{
  _DWORD **v1; // rsi
  __int64 v3; // rdi
  int v4; // eax
  __int64 v5; // rdi
  _DWORD **v6; // r14
  RTL_SRWLOCK *v7; // rcx
  __int64 v8; // r9
  _DWORD *v9; // r8
  RTL_SRWLOCK *v10; // rcx
  __int64 v11; // rdi
  DWORD CurrentThreadId; // eax
  _DWORD *v13; // r8
  char *v14; // rbx
  void *v15; // rdx
  __int64 v16; // r8
  __int64 *v17; // rcx
  __int64 v18; // rax
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp-80h] BYREF
  int v20; // [rsp+A8h] [rbp-78h] BYREF
  int v21; // [rsp+ACh] [rbp-74h] BYREF
  int v22; // [rsp+B0h] [rbp-70h] BYREF
  int v23; // [rsp+B4h] [rbp-6Ch] BYREF
  __int64 v24; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v25; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v27; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v28; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v29; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v30; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v31; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v32; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v33; // [rsp+100h] [rbp-20h] BYREF
  __int64 v34; // [rsp+108h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+110h] [rbp-10h] BYREF
  __int64 *v36; // [rsp+130h] [rbp+10h]
  __int64 v37; // [rsp+138h] [rbp+18h]
  int *v38; // [rsp+140h] [rbp+20h]
  __int64 v39; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v41; // [rsp+158h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+68h]

  v1 = (_DWORD **)((char *)this + 272);
  v3 = *((_QWORD *)this + 34);
  v4 = *(_DWORD *)(v3 + 72);
  if ( v4 < 0 && (v5 = v3 + 80, v4 == *(_DWORD *)(v5 + 8)) )
  {
    v6 = (_DWORD **)((char *)this + 272);
    if ( v5 )
    {
      SRWLock = 0;
      wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        (__int64)this,
        &SRWLock);
      v7 = SRWLock;
      **v1 = 2;
      if ( v7 )
        ReleaseSRWLockExclusive(v7);
      v8 = *((_QWORD *)Telemetry4UpdateCli::Instance() + 1);
      if ( *(_DWORD *)v8 > 5u
        && (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0
        && (*(_QWORD *)(v8 + 24) & 0x400000000000LL) == *(_QWORD *)(v8 + 24) )
      {
        v9 = *v1;
        v26 = *(_QWORD *)(v5 + 120);
        v27 = *(_QWORD *)(v5 + 112);
        v21 = *(_DWORD *)(v5 + 104);
        v28 = *(_QWORD *)(v5 + 96);
        v29 = *(_QWORD *)(v5 + 88);
        v22 = *(_DWORD *)(v5 + 80);
        v30 = *(_QWORD *)(v5 + 72);
        v23 = *(_DWORD *)(v5 + 32);
        v31 = *(_QWORD *)(v5 + 24);
        LODWORD(v24) = *(_DWORD *)v5;
        v32 = *(_QWORD *)(v5 + 128);
        v20 = *(_DWORD *)(v5 + 64);
        v33 = *(_QWORD *)(v5 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v5 + 8);
        v34 = 0x1000000;
        v25 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
          v8,
          (int)&byte_18001AE31,
          (_DWORD)v9 + 8,
          v8,
          (__int64)&v25,
          (__int64)&v34,
          (__int64)&SRWLock,
          (const wchar_t **)&v33,
          (__int64)&v20,
          (const wchar_t **)&v32,
          (__int64)&v24,
          (char **)&v31,
          (__int64)&v23,
          (const wchar_t **)&v30,
          (__int64)&v22,
          (const wchar_t **)&v29,
          (char **)&v28,
          (__int64)&v21,
          (const wchar_t **)&v27,
          (char **)&v26);
      }
      goto LABEL_17;
    }
  }
  else
  {
    v6 = (_DWORD **)((char *)this + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &SRWLock);
  v10 = SRWLock;
  **v6 = 2;
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  v11 = *((_QWORD *)Telemetry4UpdateCli::Instance() + 1);
  if ( *(_DWORD *)v11 > 5u
    && (*(_QWORD *)(v11 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v11 + 24) & 0x400000000000LL) == *(_QWORD *)(v11 + 24) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v13 = *v1;
    LODWORD(SRWLock) = CurrentThreadId;
    v41 = 4;
    v39 = 4;
    v20 = v13[18];
    v25 = 0x1000000;
    p_SRWLock = &SRWLock;
    v38 = &v20;
    v36 = &v25;
    v37 = 8;
    tlgWriteTransfer_EventWriteTransfer(v11, (int)&byte_18001AF4F, (_DWORD)v13 + 8, 0, 5u, &v35);
  }
LABEL_17:
  if ( *((_DWORD *)this + 78) )
  {
    v14 = (char *)this + 288;
    if ( *((_DWORD *)v14 + 6) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v15, v16, (const char *)0x8007029CLL);
    v17 = *(__int64 **)v14;
    *((_DWORD *)v14 + 6) = 0;
    while ( 1 )
    {
      v18 = *v17;
      if ( !*v17 )
        break;
      if ( (char *)v18 == v14 )
      {
        *v17 = *((_QWORD *)v14 + 2);
        break;
      }
      v17 = (__int64 *)(v18 + 16);
      *(_QWORD *)v14 = v18 + 16;
    }
    *(_QWORD *)v14 = 0;
  }
}

```

## disassembly

```asm
0x18000cbb0  mov     [rsp-8+arg_8], rbx
0x18000cbb5  mov     [rsp-8+arg_10], rsi
0x18000cbba  push    rbp
0x18000cbbb  push    rdi
0x18000cbbc  push    r14
0x18000cbbe  lea     rbp, [rsp-50h]
0x18000cbc3  sub     rsp, 170h
0x18000cbca  mov     rax, cs:__security_cookie
0x18000cbd1  xor     rax, rsp
0x18000cbd4  mov     [rbp+60h+var_20], rax
0x18000cbd8  lea     rsi, [rcx+110h]
0x18000cbdf  mov     rbx, rcx
0x18000cbe2  mov     rdi, [rsi]
0x18000cbe5  mov     eax, [rdi+48h]
0x18000cbe8  test    eax, eax
0x18000cbea  jns     loc_18000CD94
0x18000cbf0  add     rdi, 50h ; 'P'
0x18000cbf4  cmp     eax, [rdi+8]
0x18000cbf7  jnz     loc_18000CD94
0x18000cbfd  mov     r14, rsi
0x18000cc00  test    rdi, rdi
0x18000cc03  jz      loc_18000CD97
0x18000cc09  lea     rdx, [rbp+60h+SRWLock]
0x18000cc0d  mov     [rbp+60h+SRWLock], 0
0x18000cc15  call    ?LockExclusive@?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000cc1a  mov     rax, [rsi]
0x18000cc1d  mov     rcx, [rbp+60h+SRWLock]; SRWLock
0x18000cc21  mov     dword ptr [rax], 2
0x18000cc27  test    rcx, rcx
0x18000cc2a  jz      short loc_18000CC32
0x18000cc2c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cc32  call    ?Instance@Telemetry4UpdateCli@@KAPEAV1@XZ; Telemetry4UpdateCli::Instance(void)
0x18000cc37  mov     r9, [rax+8]
0x18000cc3b  cmp     dword ptr [r9], 5
0x18000cc3f  jbe     loc_18000CE66
0x18000cc45  mov     rcx, 400000000000h
0x18000cc4f  test    [r9+10h], rcx
0x18000cc53  jz      loc_18000CE66
0x18000cc59  mov     rax, [r9+18h]
0x18000cc5d  and     rax, rcx
0x18000cc60  cmp     rax, [r9+18h]
0x18000cc64  jnz     loc_18000CE66
0x18000cc6a  mov     rax, [rdi+78h]
0x18000cc6e  lea     rdx, byte_18001AE31; int
0x18000cc75  mov     r8, [rsi]
0x18000cc78  mov     rcx, r9; int
0x18000cc7b  mov     [rbp+60h+var_B8], rax
0x18000cc7f  add     r8, 8; int
0x18000cc83  mov     rax, [rdi+70h]
0x18000cc87  mov     [rbp+60h+var_B0], rax
0x18000cc8b  mov     eax, [rdi+68h]
0x18000cc8e  mov     dword ptr [rbp+60h+var_D8+4], eax
0x18000cc91  mov     rax, [rdi+60h]
0x18000cc95  mov     [rbp+60h+var_A8], rax
0x18000cc99  mov     rax, [rdi+58h]
0x18000cc9d  mov     [rbp+60h+var_A0], rax
0x18000cca1  mov     eax, [rdi+50h]
0x18000cca4  mov     dword ptr [rbp+60h+var_D0], eax
0x18000cca7  mov     rax, [rdi+48h]
0x18000ccab  mov     [rbp+60h+var_98], rax
0x18000ccaf  mov     eax, [rdi+20h]
0x18000ccb2  mov     dword ptr [rbp+60h+var_D0+4], eax
0x18000ccb5  mov     rax, [rdi+18h]
0x18000ccb9  mov     [rbp+60h+var_90], rax
0x18000ccbd  mov     eax, [rdi]
0x18000ccbf  mov     dword ptr [rbp+60h+var_C8], eax
0x18000ccc2  mov     rax, [rdi+80h]
0x18000ccc9  mov     [rbp+60h+var_88], rax
0x18000cccd  mov     eax, [rdi+40h]
0x18000ccd0  mov     dword ptr [rbp+60h+var_D8], eax
0x18000ccd3  mov     rax, [rdi+38h]
0x18000ccd7  mov     [rbp+60h+var_80], rax
0x18000ccdb  mov     eax, [rdi+8]
0x18000ccde  mov     dword ptr [rbp+60h+SRWLock], eax
0x18000cce1  mov     eax, 1000000h
0x18000cce6  mov     [rbp+60h+var_78], rax
0x18000ccea  mov     [rbp+60h+var_C0], rax
0x18000ccee  lea     rax, [rbp+60h+var_B8]
0x18000ccf2  mov     [rsp+180h+var_E8], rax; __int64
0x18000ccfa  lea     rax, [rbp+60h+var_B0]
0x18000ccfe  mov     [rsp+180h+var_F0], rax; __int64
0x18000cd06  lea     rax, [rbp+60h+var_D8+4]
0x18000cd0a  mov     [rsp+180h+var_F8], rax; __int64
0x18000cd12  lea     rax, [rbp+60h+var_A8]
0x18000cd16  mov     [rsp+180h+var_100], rax; __int64
0x18000cd1e  lea     rax, [rbp+60h+var_A0]
0x18000cd22  mov     [rsp+180h+var_108], rax; __int64
0x18000cd27  lea     rax, [rbp+60h+var_D0]
0x18000cd2b  mov     [rsp+180h+var_110], rax; __int64
0x18000cd30  lea     rax, [rbp+60h+var_98]
0x18000cd34  mov     [rsp+180h+var_118], rax; __int64
0x18000cd39  lea     rax, [rbp+60h+var_D0+4]
0x18000cd3d  mov     [rsp+180h+var_120], rax; __int64
0x18000cd42  lea     rax, [rbp+60h+var_90]
0x18000cd46  mov     [rsp+180h+var_128], rax; __int64
0x18000cd4b  lea     rax, [rbp+60h+var_C8]
0x18000cd4f  mov     [rsp+180h+var_130], rax; __int64
0x18000cd54  lea     rax, [rbp+60h+var_88]
0x18000cd58  mov     [rsp+180h+var_138], rax; __int64
0x18000cd5d  lea     rax, [rbp+60h+var_D8]
0x18000cd61  mov     [rsp+180h+var_140], rax; __int64
0x18000cd66  lea     rax, [rbp+60h+var_80]
0x18000cd6a  mov     [rsp+180h+var_148], rax; __int64
0x18000cd6f  lea     rax, [rbp+60h+SRWLock]
0x18000cd73  mov     [rsp+180h+var_150], rax; __int64
0x18000cd78  lea     rax, [rbp+60h+var_78]
0x18000cd7c  mov     [rsp+180h+var_158], rax; __int64
0x18000cd81  lea     rax, [rbp+60h+var_C0]
0x18000cd85  mov     qword ptr [rsp+180h+var_160], rax; __int64
0x18000cd8a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x18000cd8f  jmp     loc_18000CE66
0x18000cd94  mov     r14, rsi
0x18000cd97  lea     rdx, [rbp+60h+SRWLock]
0x18000cd9b  mov     [rbp+60h+SRWLock], 0
0x18000cda3  call    ?LockExclusive@?$ActivityBase@VTelemetry4UpdateCli@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Telemetry4UpdateCli,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000cda8  mov     rax, [r14]
0x18000cdab  mov     rcx, [rbp+60h+SRWLock]; SRWLock
0x18000cdaf  mov     dword ptr [rax], 2
0x18000cdb5  test    rcx, rcx
0x18000cdb8  jz      short loc_18000CDC0
0x18000cdba  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cdc0  call    ?Instance@Telemetry4UpdateCli@@KAPEAV1@XZ; Telemetry4UpdateCli::Instance(void)
0x18000cdc5  mov     rdi, [rax+8]
0x18000cdc9  cmp     dword ptr [rdi], 5
0x18000cdcc  jbe     loc_18000CE66
0x18000cdd2  mov     rcx, 400000000000h
0x18000cddc  test    [rdi+10h], rcx
0x18000cde0  jz      loc_18000CE66
0x18000cde6  mov     rax, [rdi+18h]
0x18000cdea  and     rax, rcx
0x18000cded  cmp     rax, [rdi+18h]
0x18000cdf1  jnz     short loc_18000CE66
0x18000cdf3  call    cs:__imp_GetCurrentThreadId
0x18000cdf9  mov     r8, [rsi]
0x18000cdfc  lea     rdx, byte_18001AF4F; int
0x18000ce03  mov     dword ptr [rbp+60h+SRWLock], eax
0x18000ce06  xor     r9d, r9d; int
0x18000ce09  mov     rcx, rdi; int
0x18000ce0c  mov     [rbp+60h+var_28], 4
0x18000ce14  mov     [rbp+60h+var_38], 4
0x18000ce1c  mov     eax, [r8+48h]
0x18000ce20  add     r8, 8; int
0x18000ce24  mov     dword ptr [rbp+60h+var_D8], eax
0x18000ce27  mov     eax, 1000000h
0x18000ce2c  mov     [rbp+60h+var_C0], rax
0x18000ce30  lea     rax, [rbp+60h+SRWLock]
0x18000ce34  mov     [rbp+60h+var_30], rax
0x18000ce38  lea     rax, [rbp+60h+var_D8]
0x18000ce3c  mov     [rbp+60h+var_40], rax
0x18000ce40  lea     rax, [rbp+60h+var_C0]
0x18000ce44  mov     [rbp+60h+var_50], rax
0x18000ce48  lea     rax, [rbp+60h+var_70]
0x18000ce4c  mov     [rsp+180h+var_158], rax; PEVENT_DATA_DESCRIPTOR
0x18000ce51  mov     [rsp+180h+var_160], 5; int
0x18000ce59  mov     [rbp+60h+var_48], 8
0x18000ce61  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ce66  cmp     dword ptr [rbx+138h], 0
0x18000ce6d  jz      short loc_18000CEC0
0x18000ce6f  add     rbx, 120h
0x18000ce76  call    cs:__imp_GetCurrentThreadId
0x18000ce7c  cmp     [rbx+18h], eax
0x18000ce7f  jz      short loc_18000CE90
0x18000ce81  mov     rcx, [rbp+68h]; this
0x18000ce85  mov     r9d, 8007029Ch; char *
0x18000ce8b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000ce90  mov     rcx, [rbx]
0x18000ce93  mov     dword ptr [rbx+18h], 0
0x18000ce9a  jmp     short loc_18000CEA8
0x18000ce9c  cmp     rax, rbx
0x18000ce9f  jz      short loc_18000CEB2
0x18000cea1  lea     rcx, [rax+10h]
0x18000cea5  mov     [rbx], rcx
0x18000cea8  mov     rax, [rcx]
0x18000ceab  test    rax, rax
0x18000ceae  jnz     short loc_18000CE9C
0x18000ceb0  jmp     short loc_18000CEB9
0x18000ceb2  mov     rax, [rbx+10h]
0x18000ceb6  mov     [rcx], rax
0x18000ceb9  mov     qword ptr [rbx], 0
0x18000cec0  mov     rcx, [rbp+60h+var_20]
0x18000cec4  xor     rcx, rsp; StackCookie
0x18000cec7  call    __security_check_cookie
0x18000cecc  lea     r11, [rsp+180h+var_10]
0x18000ced4  mov     rbx, [r11+28h]
0x18000ced8  mov     rsi, [r11+30h]
0x18000cedc  mov     rsp, r11
0x18000cedf  pop     r14
0x18000cee1  pop     rdi
0x18000cee2  pop     rbp
0x18000cee3  retn
```
