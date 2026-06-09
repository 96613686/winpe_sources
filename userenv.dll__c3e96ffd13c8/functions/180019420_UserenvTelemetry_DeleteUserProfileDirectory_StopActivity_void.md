# UserenvTelemetry::DeleteUserProfileDirectory::StopActivity(void)

- ea: `0x180019420`
- end: `0x18001969e`
- name: `?StopActivity@DeleteUserProfileDirectory@UserenvTelemetry@@MEAAXXZ`
- size: `638`
- prototype: `void __fastcall(UserenvTelemetry::DeleteUserProfileDirectory *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001d58`
- `0x180001ed0`
- `0x180002184`
- `0x18000cc14`
- `0x18000d9b0`
- `0x180012c48`
- `0x180013b7c`
- `0x180019420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800195fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800195fe`

## pseudocode

```c
void __fastcall UserenvTelemetry::DeleteUserProfileDirectory::StopActivity(
        UserenvTelemetry::DeleteUserProfileDirectory *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  const size_t *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  const struct _tlgProvider_t *v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  int v17; // [rsp+A0h] [rbp-80h] BYREF
  DWORD v18; // [rsp+A4h] [rbp-7Ch] BYREF
  int v19; // [rsp+A8h] [rbp-78h] BYREF
  int v20; // [rsp+ACh] [rbp-74h] BYREF
  int v21; // [rsp+B0h] [rbp-70h] BYREF
  int v22; // [rsp+B4h] [rbp-6Ch] BYREF
  __int64 v23; // [rsp+B8h] [rbp-68h] BYREF
  const size_t *v24; // [rsp+C0h] [rbp-60h] BYREF
  const unsigned __int16 *v25; // [rsp+C8h] [rbp-58h] BYREF
  const size_t *v26; // [rsp+D0h] [rbp-50h] BYREF
  const unsigned __int16 *v27; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v28; // [rsp+E0h] [rbp-40h] BYREF
  const size_t *v29; // [rsp+E8h] [rbp-38h] BYREF
  const unsigned __int16 *v30; // [rsp+F0h] [rbp-30h] BYREF
  const unsigned __int16 *v31; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v32; // [rsp+100h] [rbp-20h] BYREF
  char v33[32]; // [rsp+110h] [rbp-10h] BYREF
  __int64 *v34; // [rsp+130h] [rbp+10h]
  __int64 v35; // [rsp+138h] [rbp+18h]
  int *v36; // [rsp+140h] [rbp+20h]
  __int64 v37; // [rsp+148h] [rbp+28h]
  DWORD *v38; // [rsp+150h] [rbp+30h]
  __int64 v39; // [rsp+158h] [rbp+38h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = ProfileAPILogging::Provider(v5);
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7) )
    {
      v9 = (const size_t *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v19 = v4[26];
      v26 = (const size_t *)*((_QWORD *)v4 + 12);
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v20 = v4[20];
      v28 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v21 = v4[8];
      v29 = (const size_t *)*((_QWORD *)v4 + 3);
      v22 = *v4;
      v30 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v17 = v4[16];
      v31 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v18 = v4[2];
      v32 = 0x1000000;
      v23 = 0x1000000;
      v24 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)byte_1800214C5,
        v10 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v18,
        &v31,
        (__int64)&v17,
        &v30,
        (__int64)&v22,
        &v29,
        (__int64)&v21,
        &v28,
        (__int64)&v20,
        &v27,
        &v26,
        (__int64)&v19,
        &v25,
        &v24);
    }
  }
  else
  {
    wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = ProfileAPILogging::Provider(v11);
    v14 = v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      v18 = CurrentThreadId;
      v39 = 4;
      v37 = 4;
      v17 = *(_DWORD *)(v16 + 72);
      v23 = 0x1000000;
      v38 = &v18;
      v36 = &v17;
      v34 = &v23;
      v35 = 8;
      tlgWriteTransfer_EventWriteTransfer(v14, word_18002146A, v16 + 8, 0, 5, v33);
    }
  }
  wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180019420  mov     [rsp-8+arg_8], rbx
0x180019425  mov     [rsp-8+arg_10], rdi
0x18001942a  push    rbp
0x18001942b  lea     rbp, [rsp-50h]
0x180019430  sub     rsp, 170h
0x180019437  mov     rax, cs:__security_cookie
0x18001943e  xor     rax, rsp
0x180019441  mov     [rbp+50h+var_10], rax
0x180019445  mov     rdi, [rcx+110h]
0x18001944c  mov     rbx, rcx
0x18001944f  mov     eax, [rdi+48h]
0x180019452  test    eax, eax
0x180019454  jns     loc_1800195D0
0x18001945a  add     rdi, 50h ; 'P'
0x18001945e  cmp     eax, [rdi+8]
0x180019461  jnz     loc_1800195D0
0x180019467  test    rdi, rdi
0x18001946a  jz      loc_1800195D0
0x180019470  call    ?zInternalStop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180019475  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x18001947a  mov     r9, rax
0x18001947d  mov     ecx, [rax]
0x18001947f  cmp     ecx, 5
0x180019482  jbe     loc_180019675
0x180019488  mov     rdx, 400000000000h
0x180019492  mov     rcx, rax
0x180019495  call    _tlgKeywordOn
0x18001949a  test    al, al
0x18001949c  jz      loc_180019675
0x1800194a2  mov     rax, [rdi+70h]
0x1800194a6  lea     rdx, byte_1800214C5
0x1800194ad  mov     rcx, [rdi+78h]
0x1800194b1  mov     r8, [rbx+110h]
0x1800194b8  mov     [rbp+50h+var_A8], rax
0x1800194bc  add     r8, 8
0x1800194c0  mov     eax, [rdi+68h]
0x1800194c3  mov     [rbp+50h+var_C8], eax
0x1800194c6  mov     rax, [rdi+60h]
0x1800194ca  mov     [rbp+50h+var_A0], rax
0x1800194ce  mov     rax, [rdi+58h]
0x1800194d2  mov     [rbp+50h+var_98], rax
0x1800194d6  mov     eax, [rdi+50h]
0x1800194d9  mov     [rbp+50h+var_C4], eax
0x1800194dc  mov     rax, [rdi+48h]
0x1800194e0  mov     [rbp+50h+var_90], rax
0x1800194e4  mov     eax, [rdi+20h]
0x1800194e7  mov     [rbp+50h+var_C0], eax
0x1800194ea  mov     rax, [rdi+18h]
0x1800194ee  mov     [rbp+50h+var_88], rax
0x1800194f2  mov     eax, [rdi]
0x1800194f4  mov     [rbp+50h+var_BC], eax
0x1800194f7  mov     rax, [rdi+80h]
0x1800194fe  mov     [rbp+50h+var_80], rax
0x180019502  mov     eax, [rdi+40h]
0x180019505  mov     [rbp+50h+var_D0], eax
0x180019508  mov     rax, [rdi+38h]
0x18001950c  mov     [rbp+50h+var_78], rax
0x180019510  mov     eax, [rdi+8]
0x180019513  mov     [rbp+50h+var_CC], eax
0x180019516  mov     eax, 1000000h
0x18001951b  mov     [rbp+50h+var_70], rax
0x18001951f  mov     [rbp+50h+var_B8], rax
0x180019523  lea     rax, [rbp+50h+var_B0]
0x180019527  mov     [rsp+170h+var_D8], rax
0x18001952f  lea     rax, [rbp+50h+var_A8]
0x180019533  mov     [rsp+170h+var_E0], rax
0x18001953b  lea     rax, [rbp+50h+var_C8]
0x18001953f  mov     [rsp+170h+var_E8], rax
0x180019547  lea     rax, [rbp+50h+var_A0]
0x18001954b  mov     [rsp+170h+var_F0], rax
0x180019553  lea     rax, [rbp+50h+var_98]
0x180019557  mov     [rsp+170h+var_F8], rax
0x18001955c  lea     rax, [rbp+50h+var_C4]
0x180019560  mov     [rsp+170h+var_100], rax
0x180019565  lea     rax, [rbp+50h+var_90]
0x180019569  mov     [rsp+170h+var_108], rax
0x18001956e  lea     rax, [rbp+50h+var_C0]
0x180019572  mov     [rsp+170h+var_110], rax
0x180019577  lea     rax, [rbp+50h+var_88]
0x18001957b  mov     [rsp+170h+var_118], rax
0x180019580  lea     rax, [rbp+50h+var_BC]
0x180019584  mov     [rsp+170h+var_120], rax
0x180019589  lea     rax, [rbp+50h+var_80]
0x18001958d  mov     [rsp+170h+var_128], rax
0x180019592  lea     rax, [rbp+50h+var_D0]
0x180019596  mov     [rsp+170h+var_130], rax
0x18001959b  lea     rax, [rbp+50h+var_78]
0x18001959f  mov     [rsp+170h+var_138], rax
0x1800195a4  lea     rax, [rbp+50h+var_CC]
0x1800195a8  mov     [rsp+170h+var_140], rax
0x1800195ad  lea     rax, [rbp+50h+var_70]
0x1800195b1  mov     [rsp+170h+var_148], rax
0x1800195b6  lea     rax, [rbp+50h+var_B8]
0x1800195ba  mov     [rbp+50h+var_B0], rcx
0x1800195be  mov     rcx, r9
0x1800195c1  mov     [rsp+170h+var_150], rax
0x1800195c6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800195cb  jmp     loc_180019675
0x1800195d0  call    ?zInternalStop@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800195d5  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x1800195da  mov     rdi, rax
0x1800195dd  mov     ecx, [rax]
0x1800195df  cmp     ecx, 5
0x1800195e2  jbe     loc_180019675
0x1800195e8  mov     rdx, 400000000000h
0x1800195f2  mov     rcx, rax
0x1800195f5  call    _tlgKeywordOn
0x1800195fa  test    al, al
0x1800195fc  jz      short loc_180019675
0x1800195fe  call    cs:__imp_GetCurrentThreadId
0x180019604  mov     r8, [rbx+110h]
0x18001960b  lea     rdx, word_18002146A
0x180019612  mov     [rbp+50h+var_CC], eax
0x180019615  xor     r9d, r9d
0x180019618  mov     rcx, rdi
0x18001961b  mov     [rbp+50h+var_18], 4
0x180019623  mov     [rbp+50h+var_28], 4
0x18001962b  mov     eax, [r8+48h]
0x18001962f  add     r8, 8
0x180019633  mov     [rbp+50h+var_D0], eax
0x180019636  mov     eax, 1000000h
0x18001963b  mov     [rbp+50h+var_B8], rax
0x18001963f  lea     rax, [rbp+50h+var_CC]
0x180019643  mov     [rbp+50h+var_20], rax
0x180019647  lea     rax, [rbp+50h+var_D0]
0x18001964b  mov     [rbp+50h+var_30], rax
0x18001964f  lea     rax, [rbp+50h+var_B8]
0x180019653  mov     [rbp+50h+var_40], rax
0x180019657  lea     rax, [rbp+50h+var_60]
0x18001965b  mov     [rsp+170h+var_148], rax
0x180019660  mov     dword ptr [rsp+170h+var_150], 5
0x180019668  mov     [rbp+50h+var_38], 8
0x180019670  call    _tlgWriteTransfer_EventWriteTransfer
0x180019675  mov     rcx, rbx
0x180019678  call    ?IgnoreCurrentThread@?$ActivityBase@VProfileAPILogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ProfileAPILogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001967d  mov     rcx, [rbp+50h+var_10]
0x180019681  xor     rcx, rsp; StackCookie
0x180019684  call    __security_check_cookie
0x180019689  lea     r11, [rsp+170h+var_s0]
0x180019691  mov     rbx, [r11+18h]
0x180019695  mov     rdi, [r11+20h]
0x180019699  mov     rsp, r11
0x18001969c  pop     rbp
0x18001969d  retn
```
