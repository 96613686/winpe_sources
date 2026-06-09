# MSAClientTraceTelemetry::PrimeNgcLogonCache::Stop(long,long)

- ea: `0x18002e38c`
- end: `0x18002e660`
- name: `?Stop@PrimeNgcLogonCache@MSAClientTraceTelemetry@@QEAAXJJ@Z`
- size: `724`
- prototype: `void __fastcall(MSAClientTraceTelemetry::PrimeNgcLogonCache *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180028450`
- `0x1800288bc`

## callees

- `0x180001104`
- `0x1800020d0`
- `0x180002200`
- `0x180015bc0`
- `0x18001a0d0`
- `0x18002ad6c`
- `0x18002e38c`
- `0x18002fc2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e59d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e59d`

## pseudocode

```c
void __fastcall MSAClientTraceTelemetry::PrimeNgcLogonCache::Stop(
        MSAClientTraceTelemetry::PrimeNgcLogonCache *this,
        int a2,
        int a3)
{
  __int64 v3; // rdi
  int v7; // eax
  __int64 v8; // rdi
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // r9
  __int64 v13; // r8
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  int v18; // [rsp+B0h] [rbp-80h] BYREF
  DWORD v19; // [rsp+B4h] [rbp-7Ch] BYREF
  int v20; // [rsp+B8h] [rbp-78h] BYREF
  int v21; // [rsp+BCh] [rbp-74h] BYREF
  int v22; // [rsp+C0h] [rbp-70h] BYREF
  int v23; // [rsp+C4h] [rbp-6Ch] BYREF
  int v24; // [rsp+C8h] [rbp-68h] BYREF
  int v25; // [rsp+CCh] [rbp-64h] BYREF
  __int64 v26; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v27; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v28; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v29; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v30; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v31; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v32; // [rsp+100h] [rbp-30h] BYREF
  __int64 v33; // [rsp+108h] [rbp-28h] BYREF
  __int64 v34; // [rsp+110h] [rbp-20h] BYREF
  __int64 v35; // [rsp+118h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+120h] [rbp-10h] BYREF
  __int64 *v37; // [rsp+140h] [rbp+10h]
  __int64 v38; // [rsp+148h] [rbp+18h]
  int *v39; // [rsp+150h] [rbp+20h]
  __int64 v40; // [rsp+158h] [rbp+28h]
  DWORD *v41; // [rsp+160h] [rbp+30h]
  __int64 v42; // [rsp+168h] [rbp+38h]
  int *v43; // [rsp+170h] [rbp+40h]
  __int64 v44; // [rsp+178h] [rbp+48h]
  int *v45; // [rsp+180h] [rbp+50h]
  __int64 v46; // [rsp+188h] [rbp+58h]

  v3 = *((_QWORD *)this + 34);
  v7 = *(_DWORD *)(v3 + 72);
  if ( v7 < 0 && (v8 = v3 + 80, v7 == *(_DWORD *)(v8 + 8)) && v8 )
  {
    wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = MSAClientTraceTelemetry::Provider();
    v12 = v9;
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL) )
    {
      v27 = *(_QWORD *)(v8 + 120);
      v28 = *(_QWORD *)(v8 + 112);
      v13 = *((_QWORD *)this + 34);
      v24 = *(_DWORD *)(v8 + 104);
      v29 = *(_QWORD *)(v8 + 96);
      v30 = *(_QWORD *)(v8 + 88);
      v25 = *(_DWORD *)(v8 + 80);
      v31 = *(_QWORD *)(v8 + 72);
      v18 = *(_DWORD *)(v8 + 32);
      v32 = *(_QWORD *)(v8 + 24);
      v19 = *(_DWORD *)v8;
      v33 = *(_QWORD *)(v8 + 128);
      v20 = *(_DWORD *)(v8 + 64);
      v34 = *(_QWORD *)(v8 + 56);
      v21 = *(_DWORD *)(v8 + 8);
      v35 = 0x1000000;
      v26 = 0x1000000;
      v22 = a3;
      v23 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v12,
        (unsigned int)byte_1800765E1,
        v13 + 8,
        (_DWORD)v12,
        (__int64)&v26,
        (__int64)&v35,
        (__int64)&v21,
        (__int64)&v34,
        (__int64)&v20,
        (__int64)&v33,
        (__int64)&v19,
        (__int64)&v32,
        (__int64)&v18,
        (__int64)&v31,
        (__int64)&v25,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v24,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v23,
        (__int64)&v22);
    }
  }
  else
  {
    wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = MSAClientTraceTelemetry::Provider();
    v15 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL) )
    {
      v21 = a3;
      v20 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      v19 = CurrentThreadId;
      v46 = 4;
      v44 = 4;
      v18 = *(_DWORD *)(v17 + 72);
      v26 = 0x1000000;
      v45 = &v21;
      v43 = &v20;
      v41 = &v19;
      v39 = &v18;
      v37 = &v26;
      v42 = 4;
      v40 = 4;
      v38 = 8;
      tlgWriteTransfer_EventWriteTransfer(v15, (unsigned __int8 *)&word_18007657E, (const GUID *)(v17 + 8), 0, 7u, &v36);
    }
  }
  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v10,
    v11,
    v12);
}

```

## disassembly

```asm
0x18002e38c  mov     [rsp-8+arg_8], rbx
0x18002e391  mov     [rsp-8+arg_10], rsi
0x18002e396  push    rbp
0x18002e397  push    rdi
0x18002e398  push    r14
0x18002e39a  lea     rbp, [rsp-70h]
0x18002e39f  sub     rsp, 1A0h
0x18002e3a6  mov     rax, cs:__security_cookie
0x18002e3ad  xor     rax, rsp
0x18002e3b0  mov     [rbp+80h+var_20], rax
0x18002e3b4  mov     rdi, [rcx+110h]
0x18002e3bb  mov     esi, r8d
0x18002e3be  mov     r14d, edx
0x18002e3c1  mov     rbx, rcx
0x18002e3c4  mov     eax, [rdi+48h]
0x18002e3c7  test    eax, eax
0x18002e3c9  jns     loc_18002E564
0x18002e3cf  add     rdi, 50h ; 'P'
0x18002e3d3  cmp     eax, [rdi+8]
0x18002e3d6  jnz     loc_18002E564
0x18002e3dc  test    rdi, rdi
0x18002e3df  jz      loc_18002E564
0x18002e3e5  call    ?zInternalStop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002e3ea  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18002e3ef  mov     r9, rax
0x18002e3f2  mov     ecx, [rax]
0x18002e3f4  cmp     ecx, 5
0x18002e3f7  jbe     loc_18002E634
0x18002e3fd  mov     rdx, 400000000000h
0x18002e407  mov     rcx, rax
0x18002e40a  call    _tlgKeywordOn
0x18002e40f  test    al, al
0x18002e411  jz      loc_18002E634
0x18002e417  mov     rax, [rdi+78h]
0x18002e41b  lea     rdx, byte_1800765E1
0x18002e422  mov     [rbp+80h+var_D8], rax
0x18002e426  mov     rcx, r9
0x18002e429  mov     rax, [rdi+70h]
0x18002e42d  mov     [rbp+80h+var_D0], rax
0x18002e431  mov     eax, [rdi+68h]
0x18002e434  mov     r8, [rbx+110h]
0x18002e43b  mov     [rbp+80h+var_E8], eax
0x18002e43e  add     r8, 8
0x18002e442  mov     rax, [rdi+60h]
0x18002e446  mov     [rbp+80h+var_C8], rax
0x18002e44a  mov     rax, [rdi+58h]
0x18002e44e  mov     [rbp+80h+var_C0], rax
0x18002e452  mov     eax, [rdi+50h]
0x18002e455  mov     [rbp+80h+var_E4], eax
0x18002e458  mov     rax, [rdi+48h]
0x18002e45c  mov     [rbp+80h+var_B8], rax
0x18002e460  mov     eax, [rdi+20h]
0x18002e463  mov     [rbp+80h+var_100], eax
0x18002e466  mov     rax, [rdi+18h]
0x18002e46a  mov     [rbp+80h+var_B0], rax
0x18002e46e  mov     eax, [rdi]
0x18002e470  mov     [rbp+80h+var_FC], eax
0x18002e473  mov     rax, [rdi+80h]
0x18002e47a  mov     [rbp+80h+var_A8], rax
0x18002e47e  mov     eax, [rdi+40h]
0x18002e481  mov     [rbp+80h+var_F8], eax
0x18002e484  mov     rax, [rdi+38h]
0x18002e488  mov     [rbp+80h+var_A0], rax
0x18002e48c  mov     eax, [rdi+8]
0x18002e48f  mov     [rbp+80h+var_F4], eax
0x18002e492  mov     eax, 1000000h
0x18002e497  mov     [rbp+80h+var_98], rax
0x18002e49b  mov     [rbp+80h+var_E0], rax
0x18002e49f  lea     rax, [rbp+80h+var_F0]
0x18002e4a3  mov     [rsp+1B0h+var_108], rax
0x18002e4ab  lea     rax, [rbp+80h+var_EC]
0x18002e4af  mov     [rsp+1B0h+var_110], rax
0x18002e4b7  lea     rax, [rbp+80h+var_D8]
0x18002e4bb  mov     [rsp+1B0h+var_118], rax
0x18002e4c3  lea     rax, [rbp+80h+var_D0]
0x18002e4c7  mov     [rsp+1B0h+var_120], rax
0x18002e4cf  lea     rax, [rbp+80h+var_E8]
0x18002e4d3  mov     [rsp+1B0h+var_128], rax
0x18002e4db  lea     rax, [rbp+80h+var_C8]
0x18002e4df  mov     [rsp+1B0h+var_130], rax
0x18002e4e7  lea     rax, [rbp+80h+var_C0]
0x18002e4eb  mov     [rsp+1B0h+var_138], rax
0x18002e4f0  lea     rax, [rbp+80h+var_E4]
0x18002e4f4  mov     [rsp+1B0h+var_140], rax
0x18002e4f9  lea     rax, [rbp+80h+var_B8]
0x18002e4fd  mov     [rsp+1B0h+var_148], rax
0x18002e502  lea     rax, [rbp+80h+var_100]
0x18002e506  mov     [rsp+1B0h+var_150], rax
0x18002e50b  lea     rax, [rbp+80h+var_B0]
0x18002e50f  mov     [rsp+1B0h+var_158], rax
0x18002e514  lea     rax, [rbp+80h+var_FC]
0x18002e518  mov     [rsp+1B0h+var_160], rax
0x18002e51d  lea     rax, [rbp+80h+var_A8]
0x18002e521  mov     [rsp+1B0h+var_168], rax
0x18002e526  lea     rax, [rbp+80h+var_F8]
0x18002e52a  mov     [rsp+1B0h+var_170], rax
0x18002e52f  lea     rax, [rbp+80h+var_A0]
0x18002e533  mov     [rsp+1B0h+var_178], rax
0x18002e538  lea     rax, [rbp+80h+var_F4]
0x18002e53c  mov     [rsp+1B0h+var_180], rax
0x18002e541  lea     rax, [rbp+80h+var_98]
0x18002e545  mov     [rsp+1B0h+var_188], rax
0x18002e54a  lea     rax, [rbp+80h+var_E0]
0x18002e54e  mov     [rsp+1B0h+var_190], rax
0x18002e553  mov     [rbp+80h+var_F0], esi
0x18002e556  mov     [rbp+80h+var_EC], r14d
0x18002e55a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645644@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002e55f  jmp     loc_18002E634
0x18002e564  call    ?zInternalStop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18002e569  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18002e56e  mov     rdi, rax
0x18002e571  mov     ecx, [rax]
0x18002e573  cmp     ecx, 5
0x18002e576  jbe     loc_18002E634
0x18002e57c  mov     rdx, 400000000000h
0x18002e586  mov     rcx, rax
0x18002e589  call    _tlgKeywordOn
0x18002e58e  test    al, al
0x18002e590  jz      loc_18002E634
0x18002e596  mov     [rbp+80h+var_F4], esi
0x18002e599  mov     [rbp+80h+var_F8], r14d
0x18002e59d  call    cs:__imp_GetCurrentThreadId
0x18002e5a3  mov     r8, [rbx+110h]
0x18002e5aa  lea     rdx, word_18007657E
0x18002e5b1  mov     [rbp+80h+var_FC], eax
0x18002e5b4  xor     r9d, r9d
0x18002e5b7  mov     rcx, rdi
0x18002e5ba  mov     [rbp+80h+var_28], 4
0x18002e5c2  mov     [rbp+80h+var_38], 4
0x18002e5ca  mov     eax, [r8+48h]
0x18002e5ce  add     r8, 8
0x18002e5d2  mov     [rbp+80h+var_100], eax
0x18002e5d5  mov     eax, 1000000h
0x18002e5da  mov     [rbp+80h+var_E0], rax
0x18002e5de  lea     rax, [rbp+80h+var_F4]
0x18002e5e2  mov     [rbp+80h+var_30], rax
0x18002e5e6  lea     rax, [rbp+80h+var_F8]
0x18002e5ea  mov     [rbp+80h+var_40], rax
0x18002e5ee  lea     rax, [rbp+80h+var_FC]
0x18002e5f2  mov     [rbp+80h+var_50], rax
0x18002e5f6  lea     rax, [rbp+80h+var_100]
0x18002e5fa  mov     [rbp+80h+var_60], rax
0x18002e5fe  lea     rax, [rbp+80h+var_E0]
0x18002e602  mov     [rbp+80h+var_70], rax
0x18002e606  lea     rax, [rbp+80h+var_90]
0x18002e60a  mov     [rsp+1B0h+var_188], rax
0x18002e60f  mov     dword ptr [rsp+1B0h+var_190], 7
0x18002e617  mov     [rbp+80h+var_48], 4
0x18002e61f  mov     [rbp+80h+var_58], 4
0x18002e627  mov     [rbp+80h+var_68], 8
0x18002e62f  call    _tlgWriteTransfer_EventWriteTransfer
0x18002e634  mov     rcx, rbx
0x18002e637  call    ?IgnoreCurrentThread@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18002e63c  mov     rcx, [rbp+80h+var_20]
0x18002e640  xor     rcx, rsp; StackCookie
0x18002e643  call    __security_check_cookie
0x18002e648  lea     r11, [rsp+1B0h+var_10]
0x18002e650  mov     rbx, [r11+28h]
0x18002e654  mov     rsi, [r11+30h]
0x18002e658  mov     rsp, r11
0x18002e65b  pop     r14
0x18002e65d  pop     rdi
0x18002e65e  pop     rbp
0x18002e65f  retn
```
