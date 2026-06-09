# _lambda_afd7ee1b065516bcafbe102d67bfbf3c_::operator()

- ea: `0x1800bec98`
- end: `0x1800bf06b`
- name: `_lambda_afd7ee1b065516bcafbe102d67bfbf3c_::operator()`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bea10`

## callees

- `0x1800058ec`
- `0x18000b760`
- `0x180017398`
- `0x18002d3b4`
- `0x18002f75c`
- `0x18005ee4c`
- `0x180060254`
- `0x18006963c`
- `0x1800bc144`
- `0x1800bea34`
- `0x1800bec98`
- `0x1800bf0c0`
- `0x1800bf10c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800befe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf01d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800befe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf01d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf051`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bed8b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bed8b`
- `ngckeyenum!NgcCredProvEnumLogonKeys` at `0x1800becef`
- `ngckeyenum!NgcCredProvEnumLogonKeys` at `0x1800beecc`
- `ngckeyenum!NgcCredProvEnumLogonKeys` at `0x1800becef`
- `ngckeyenum!NgcCredProvEnumLogonKeys` at `0x1800beecc`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_afd7ee1b065516bcafbe102d67bfbf3c_::operator()(_QWORD **a1)
{
  int v2; // ebx
  __int64 v3; // r9
  char *v4; // r15
  DWORD LengthSid; // eax
  __int64 v6; // r14
  PSID v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rbx
  signed int v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  signed int v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  signed int LastError; // eax
  int v23; // edx
  unsigned int v24; // r8d
  signed int v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  signed int v28; // eax
  int v29; // edx
  unsigned int v30; // r8d
  void **v31; // [rsp+30h] [rbp-49h] BYREF
  __int64 v32; // [rsp+38h] [rbp-41h] BYREF
  void **v33; // [rsp+40h] [rbp-39h] BYREF
  __int64 v34; // [rsp+48h] [rbp-31h] BYREF
  std::_Ref_count_base *v35[2]; // [rsp+50h] [rbp-29h] BYREF
  __int128 v36; // [rsp+60h] [rbp-19h] BYREF
  __int64 v37; // [rsp+70h] [rbp-9h]
  __int128 v38; // [rsp+78h] [rbp-1h] BYREF
  __int64 v39; // [rsp+88h] [rbp+Fh]
  char *v40; // [rsp+E0h] [rbp+67h] BYREF

  v33 = &Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::`vftable';
  v34 = 0;
  v36 = 0;
  v37 = 0;
  v31 = &Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::`vftable';
  v32 = 0;
  v2 = NgcCredProvEnumLogonKeys(**a1, &v32, &v34);
  if ( v2 >= 0 )
  {
    while ( 1 )
    {
      v4 = (char *)operator new(0x90u);
      v40 = v4;
      *(_OWORD *)v4 = 0;
      *((_DWORD *)v4 + 2) = 1;
      *((_DWORD *)v4 + 3) = 1;
      *(_QWORD *)v4 = &std::_Ref_count_obj2<KeyEnumInfo>::`vftable';
      *((_QWORD *)v4 + 2) = 0;
      *((_QWORD *)v4 + 3) = 0;
      *((_QWORD *)v4 + 4) = 0;
      *((_DWORD *)v4 + 10) = 0;
      *(_OWORD *)(v4 + 44) = 0;
      *((_OWORD *)v4 + 4) = 0;
      *((_QWORD *)v4 + 10) = 0;
      *((_QWORD *)v4 + 11) = 7;
      *((_WORD *)v4 + 32) = 0;
      *((_OWORD *)v4 + 6) = 0;
      *((_QWORD *)v4 + 14) = 0;
      *((_QWORD *)v4 + 15) = 7;
      *((_WORD *)v4 + 48) = 0;
      *((_DWORD *)v4 + 32) = 0;
      v4[132] = 0;
      *((_DWORD *)v4 + 34) = 0;
      v35[0] = (std::_Ref_count_base *)(v4 + 16);
      v35[1] = (std::_Ref_count_base *)v4;
      LengthSid = GetLengthSid(*(PSID *)v32);
      v6 = LengthSid;
      v38 = 0;
      v39 = 0;
      if ( LengthSid )
      {
        v7 = *(PSID *)v32;
        std::vector<unsigned char>::_Buy_nonzero(&v38, LengthSid);
        *((_QWORD *)&v38 + 1) = std::_Uninitialized_move<unsigned char *>(v7, (__int64)v7 + v6, (char *)v38);
      }
      std::vector<unsigned char>::operator=(v4 + 16, &v38);
      v8 = v32;
      v9 = *(_QWORD *)(v32 + 32);
      if ( v9 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)(v9 + 2 * v10) );
        std::wstring::_Assign<unsigned short>(v4 + 64, v9);
        v8 = v32;
      }
      v11 = *(_QWORD *)(v8 + 40);
      if ( v11 )
      {
        v12 = -1;
        do
          ++v12;
        while ( *(_WORD *)(v11 + 2 * v12) );
        std::wstring::_Assign<unsigned short>(v4 + 96, v11);
        v8 = v32;
      }
      *((_DWORD *)v4 + 10) = *(_DWORD *)(v8 + 8);
      *(_OWORD *)(v4 + 44) = *(_OWORD *)(v32 + 12);
      *((_DWORD *)v4 + 32) = *(_DWORD *)(v32 + 48);
      v4[132] = *(_BYTE *)(v32 + 52);
      *((_DWORD *)v4 + 34) = *(_DWORD *)(v32 + 56);
      v13 = *((_QWORD *)&v36 + 1);
      if ( *((_QWORD *)&v36 + 1) == v37 )
      {
        std::vector<std::shared_ptr<KeyEnumInfo>>::_Emplace_reallocate<std::shared_ptr<KeyEnumInfo>>(
          &v36,
          *((_QWORD *)&v36 + 1),
          v35);
      }
      else
      {
        **((_QWORD **)&v36 + 1) = v4 + 16;
        *(_QWORD *)(v13 + 8) = v4;
        *(_OWORD *)v35 = 0;
        *((_QWORD *)&v36 + 1) += 16LL;
      }
      std::vector<unsigned char>::_Tidy(&v38);
      if ( v35[1] )
        std::_Ref_count_base::_Decref(v35[1]);
      v31 = &Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::`vftable';
      if ( v32 )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::InternalClose(&v31) )
          break;
      }
      v31 = &Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::`vftable';
      v32 = 0;
      v2 = NgcCredProvEnumLogonKeys(**a1, &v32, &v34);
      if ( v2 < 0 )
        goto LABEL_20;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v23, v24);
    goto LABEL_45;
  }
LABEL_20:
  if ( v2 != -2146893782 )
  {
    if ( (unsigned int)dword_18010F170 > 2 )
    {
      LODWORD(v40) = v2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18010F170,
        (unsigned __int8 *)word_1800F9DEA,
        0,
        v3,
        (__int64)&v40);
    }
    v31 = &Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::`vftable';
    if ( v32 )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::InternalClose(&v31) )
        goto LABEL_48;
      v32 = 0;
    }
    std::vector<std::shared_ptr<KeyEnumInfo>>::_Tidy(&v36);
    v33 = &Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::`vftable';
    if ( !v34 || (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::InternalClose(&v33) )
      return (unsigned int)v2;
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
LABEL_39:
    v19 = GetLastError();
    if ( v19 > 0 )
      v19 = (unsigned __int16)v19 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
    __debugbreak();
  }
  v31 = &Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::`vftable';
  if ( v32 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::InternalClose(&v31) )
    goto LABEL_39;
  v14 = *a1[1];
  if ( (__int128 *)v14 != &v36 )
  {
    std::vector<std::shared_ptr<KeyEnumInfo>>::_Tidy(*a1[1]);
    *(_OWORD *)v14 = v36;
    *(_QWORD *)(v14 + 16) = v37;
    v36 = 0;
    v37 = 0;
  }
  std::vector<std::shared_ptr<KeyEnumInfo>>::_Tidy(&v36);
  v33 = &Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::`vftable';
  if ( v34 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::InternalClose(&v33) )
  {
LABEL_45:
    v25 = GetLastError();
    if ( v25 > 0 )
      v25 = (unsigned __int16)v25 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
LABEL_48:
    v28 = GetLastError();
    if ( v28 > 0 )
      v28 = (unsigned __int16)v28 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v28, v29, v30);
    JUMPOUT(0x1800BF06ALL);
  }
  return 0;
}

```

## disassembly

```asm
0x1800bec98  push    rbp
0x1800bec9a  push    rbx
0x1800bec9b  push    rsi
0x1800bec9c  push    rdi
0x1800bec9d  push    r12
0x1800bec9f  push    r13
0x1800beca1  push    r14
0x1800beca3  push    r15
0x1800beca5  lea     rbp, [rsp-1Fh]
0x1800becaa  sub     rsp, 98h
0x1800becb1  mov     rsi, rcx
0x1800becb4  xor     r12d, r12d
0x1800becb7  lea     rdi, ??_7?$HandleT@UKeyEnumStateTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::`vftable'
0x1800becbe  mov     [rbp+57h+var_90], rdi
0x1800becc2  mov     [rbp+57h+var_88], r12
0x1800becc6  xorps   xmm0, xmm0
0x1800becc9  movdqu  [rbp+57h+var_70], xmm0
0x1800becce  mov     [rbp+57h+var_60], r12
0x1800becd2  lea     r13, ??_7?$HandleT@UKeyEnumStateTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::`vftable'
0x1800becd9  mov     [rbp+57h+var_A0], r13
0x1800becdd  mov     [rbp+57h+var_98], r12
0x1800bece1  mov     rcx, [rcx]
0x1800bece4  lea     r8, [rbp+57h+var_88]
0x1800bece8  lea     rdx, [rbp+57h+var_98]
0x1800becec  mov     rcx, [rcx]
0x1800becef  call    cs:__imp_NgcCredProvEnumLogonKeys
0x1800becf5  mov     ebx, eax
0x1800becf7  test    eax, eax
0x1800becf9  js      loc_1800BEEE3
0x1800becff  mov     ecx, 90h; Size
0x1800bed04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bed09  mov     r15, rax
0x1800bed0c  mov     [rbp+57h+arg_0], rax
0x1800bed10  xorps   xmm0, xmm0
0x1800bed13  movups  xmmword ptr [rax], xmm0
0x1800bed16  mov     dword ptr [rax+8], 1
0x1800bed1d  mov     dword ptr [rax+0Ch], 1
0x1800bed24  lea     rax, ??_7?$_Ref_count_obj2@UKeyEnumInfo@@@std@@6B@; const std::_Ref_count_obj2<KeyEnumInfo>::`vftable'
0x1800bed2b  mov     [r15], rax
0x1800bed2e  lea     rdi, [r15+10h]
0x1800bed32  mov     [rdi], r12
0x1800bed35  mov     [rdi+8], r12
0x1800bed39  mov     [rdi+10h], r12
0x1800bed3d  mov     [rdi+18h], r12d
0x1800bed41  movdqu  xmmword ptr [rdi+1Ch], xmm0
0x1800bed46  movups  xmmword ptr [rdi+30h], xmm0
0x1800bed4a  mov     [rdi+40h], r12
0x1800bed4e  mov     qword ptr [rdi+48h], 7
0x1800bed56  mov     [rdi+30h], r12w
0x1800bed5b  movups  xmmword ptr [rdi+50h], xmm0
0x1800bed5f  mov     [rdi+60h], r12
0x1800bed63  mov     qword ptr [rdi+68h], 7
0x1800bed6b  mov     [rdi+50h], r12w
0x1800bed70  mov     [rdi+70h], r12d
0x1800bed74  mov     [rdi+74h], r12b
0x1800bed78  mov     [rdi+78h], r12d
0x1800bed7c  mov     [rbp+57h+var_80], rdi
0x1800bed80  mov     [rbp+57h+var_80+8], r15
0x1800bed84  mov     rcx, [rbp+57h+var_98]
0x1800bed88  mov     rcx, [rcx]; pSid
0x1800bed8b  call    cs:__imp_GetLengthSid
0x1800bed91  mov     r14d, eax
0x1800bed94  xorps   xmm0, xmm0
0x1800bed97  movdqu  [rbp+57h+var_58], xmm0
0x1800bed9c  mov     [rbp+57h+var_48], r12
0x1800beda0  test    eax, eax
0x1800beda2  jz      short loc_1800BEDCB
0x1800beda4  mov     rax, [rbp+57h+var_98]
0x1800beda8  mov     rbx, [rax]
0x1800bedab  mov     edx, r14d
0x1800bedae  lea     rcx, [rbp+57h+var_58]
0x1800bedb2  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x1800bedb7  lea     rdx, [r14+rbx]
0x1800bedbb  mov     r8, qword ptr [rbp+57h+var_58]
0x1800bedbf  mov     rcx, rbx
0x1800bedc2  call    ??$_Uninitialized_move@PEAEV?$allocator@E@std@@@std@@YAPEAEQEAE0PEAEAEAV?$allocator@E@0@@Z; std::_Uninitialized_move<uchar *>(uchar * const,uchar * const,uchar *,std::allocator<uchar> &)
0x1800bedc7  mov     qword ptr [rbp+57h+var_58+8], rax
0x1800bedcb  lea     rdx, [rbp+57h+var_58]
0x1800bedcf  mov     rcx, rdi
0x1800bedd2  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1800bedd7  mov     rax, [rbp+57h+var_98]
0x1800beddb  mov     rdx, [rax+20h]
0x1800beddf  test    rdx, rdx
0x1800bede2  jz      short loc_1800BEDFF
0x1800bede4  lea     rcx, [rdi+30h]
0x1800bede8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800bedec  inc     r8
0x1800bedef  cmp     [rdx+r8*2], r12w
0x1800bedf4  jnz     short loc_1800BEDEC
0x1800bedf6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800bedfb  mov     rax, [rbp+57h+var_98]
0x1800bedff  mov     rdx, [rax+28h]
0x1800bee03  test    rdx, rdx
0x1800bee06  jz      short loc_1800BEE23
0x1800bee08  lea     rcx, [rdi+50h]
0x1800bee0c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800bee10  inc     r8
0x1800bee13  cmp     [rdx+r8*2], r12w
0x1800bee18  jnz     short loc_1800BEE10
0x1800bee1a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800bee1f  mov     rax, [rbp+57h+var_98]
0x1800bee23  mov     eax, [rax+8]
0x1800bee26  mov     [rdi+18h], eax
0x1800bee29  mov     rax, [rbp+57h+var_98]
0x1800bee2d  movups  xmm0, xmmword ptr [rax+0Ch]
0x1800bee31  movdqu  xmmword ptr [rdi+1Ch], xmm0
0x1800bee36  mov     rax, [rbp+57h+var_98]
0x1800bee3a  mov     ecx, [rax+30h]
0x1800bee3d  mov     [rdi+70h], ecx
0x1800bee40  mov     rax, [rbp+57h+var_98]
0x1800bee44  mov     cl, [rax+34h]
0x1800bee47  mov     [rdi+74h], cl
0x1800bee4a  mov     rax, [rbp+57h+var_98]
0x1800bee4e  mov     ecx, [rax+38h]
0x1800bee51  mov     [rdi+78h], ecx
0x1800bee54  mov     rdx, qword ptr [rbp+57h+var_70+8]
0x1800bee58  cmp     rdx, [rbp+57h+var_60]
0x1800bee5c  jz      short loc_1800BEE74
0x1800bee5e  mov     [rdx], rdi
0x1800bee61  mov     [rdx+8], r15
0x1800bee65  xorps   xmm0, xmm0
0x1800bee68  movdqu  xmmword ptr [rbp+57h+var_80], xmm0
0x1800bee6d  add     qword ptr [rbp+57h+var_70+8], 10h
0x1800bee72  jmp     short loc_1800BEE82
0x1800bee74  lea     r8, [rbp+57h+var_80]
0x1800bee78  lea     rcx, [rbp+57h+var_70]
0x1800bee7c  call    ??$_Emplace_reallocate@V?$shared_ptr@UKeyEnumInfo@@@std@@@?$vector@V?$shared_ptr@UKeyEnumInfo@@@std@@V?$allocator@V?$shared_ptr@UKeyEnumInfo@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UKeyEnumInfo@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<KeyEnumInfo>>::_Emplace_reallocate<std::shared_ptr<KeyEnumInfo>>(std::shared_ptr<KeyEnumInfo> * const,std::shared_ptr<KeyEnumInfo> &&)
0x1800bee81  nop
0x1800bee82  lea     rcx, [rbp+57h+var_58]
0x1800bee86  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800bee8b  nop
0x1800bee8c  mov     rcx, [rbp+57h+var_80+8]; this
0x1800bee90  test    rcx, rcx
0x1800bee93  jz      short loc_1800BEE9B
0x1800bee95  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bee9a  nop
0x1800bee9b  mov     [rbp+57h+var_A0], r13
0x1800bee9f  cmp     [rbp+57h+var_98], r12
0x1800beea3  jz      short loc_1800BEEB6
0x1800beea5  lea     rcx, [rbp+57h+var_A0]
0x1800beea9  call    ?InternalClose@?$HandleT@UKeyEnumStateTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::InternalClose(void)
0x1800beeae  test    al, al
0x1800beeb0  jz      loc_1800BF01D
0x1800beeb6  mov     [rbp+57h+var_A0], r13
0x1800beeba  mov     [rbp+57h+var_98], r12
0x1800beebe  mov     rcx, [rsi]
0x1800beec1  lea     r8, [rbp+57h+var_88]
0x1800beec5  lea     rdx, [rbp+57h+var_98]
0x1800beec9  mov     rcx, [rcx]
0x1800beecc  call    cs:__imp_NgcCredProvEnumLogonKeys
0x1800beed2  mov     ebx, eax
0x1800beed4  test    eax, eax
0x1800beed6  jns     loc_1800BECFF
0x1800beedc  lea     rdi, ??_7?$HandleT@UKeyEnumStateTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::`vftable'
0x1800beee3  cmp     ebx, 8009002Ah
0x1800beee9  jnz     short loc_1800BEF64
0x1800beeeb  mov     [rbp+57h+var_A0], r13
0x1800beeef  cmp     [rbp+57h+var_98], r12
0x1800beef3  jz      short loc_1800BEF06
0x1800beef5  lea     rcx, [rbp+57h+var_A0]
0x1800beef9  call    ?InternalClose@?$HandleT@UKeyEnumStateTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::InternalClose(void)
0x1800beefe  test    al, al
0x1800bef00  jz      loc_1800BF002
0x1800bef06  mov     rax, [rsi+8]
0x1800bef0a  mov     rbx, [rax]
0x1800bef0d  lea     rax, [rbp+57h+var_70]
0x1800bef11  cmp     rbx, rax
0x1800bef14  jz      short loc_1800BEF3B
0x1800bef16  mov     rcx, rbx
0x1800bef19  call    ?_Tidy@?$vector@V?$shared_ptr@UKeyEnumInfo@@@std@@V?$allocator@V?$shared_ptr@UKeyEnumInfo@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<KeyEnumInfo>>::_Tidy(void)
0x1800bef1e  movups  xmm0, [rbp+57h+var_70]
0x1800bef22  movups  xmmword ptr [rbx], xmm0
0x1800bef25  movsd   xmm1, [rbp+57h+var_60]
0x1800bef2a  movsd   qword ptr [rbx+10h], xmm1
0x1800bef2f  xorps   xmm0, xmm0
0x1800bef32  movdqu  [rbp+57h+var_70], xmm0
0x1800bef37  mov     [rbp+57h+var_60], r12
0x1800bef3b  lea     rcx, [rbp+57h+var_70]
0x1800bef3f  call    ?_Tidy@?$vector@V?$shared_ptr@UKeyEnumInfo@@@std@@V?$allocator@V?$shared_ptr@UKeyEnumInfo@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<KeyEnumInfo>>::_Tidy(void)
0x1800bef44  nop
0x1800bef45  mov     [rbp+57h+var_90], rdi
0x1800bef49  cmp     [rbp+57h+var_88], r12
0x1800bef4d  jz      short loc_1800BEF60
0x1800bef4f  lea     rcx, [rbp+57h+var_90]
0x1800bef53  call    ?InternalClose@?$HandleT@UKeyEnumStateTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::InternalClose(void)
0x1800bef58  test    al, al
0x1800bef5a  jz      loc_1800BF037
0x1800bef60  xor     eax, eax
0x1800bef62  jmp     short loc_1800BEFD4
0x1800bef64  mov     eax, cs:dword_18010F170
0x1800bef6a  cmp     eax, 2
0x1800bef6d  jbe     short loc_1800BEF92
0x1800bef6f  mov     dword ptr [rbp+57h+arg_0], ebx
0x1800bef72  lea     rax, [rbp+57h+arg_0]
0x1800bef76  mov     [rsp+0D0h+var_B0], rax
0x1800bef7b  xor     r8d, r8d
0x1800bef7e  lea     rdx, word_1800F9DEA
0x1800bef85  lea     rcx, dword_18010F170
0x1800bef8c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800bef91  nop
0x1800bef92  mov     [rbp+57h+var_A0], r13
0x1800bef96  cmp     [rbp+57h+var_98], r12
0x1800bef9a  jz      short loc_1800BEFB1
0x1800bef9c  lea     rcx, [rbp+57h+var_A0]
0x1800befa0  call    ?InternalClose@?$HandleT@UKeyEnumStateTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::InternalClose(void)
0x1800befa5  test    al, al
0x1800befa7  jz      loc_1800BF051
0x1800befad  mov     [rbp+57h+var_98], r12
0x1800befb1  lea     rcx, [rbp+57h+var_70]
0x1800befb5  call    ?_Tidy@?$vector@V?$shared_ptr@UKeyEnumInfo@@@std@@V?$allocator@V?$shared_ptr@UKeyEnumInfo@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<KeyEnumInfo>>::_Tidy(void)
0x1800befba  nop
0x1800befbb  mov     [rbp+57h+var_90], rdi
0x1800befbf  cmp     [rbp+57h+var_88], r12
0x1800befc3  jz      short loc_1800BEFD2
0x1800befc5  lea     rcx, [rbp+57h+var_90]
0x1800befc9  call    ?InternalClose@?$HandleT@UKeyEnumStateTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<KeyEnumStateTraits>::InternalClose(void)
0x1800befce  test    al, al
0x1800befd0  jz      short loc_1800BEFE8
0x1800befd2  mov     eax, ebx
0x1800befd4  add     rsp, 98h
0x1800befdb  pop     r15
0x1800befdd  pop     r14
0x1800befdf  pop     r13
0x1800befe1  pop     r12
0x1800befe3  pop     rdi
0x1800befe4  pop     rsi
0x1800befe5  pop     rbx
0x1800befe6  pop     rbp
0x1800befe7  retn
0x1800befe8  call    cs:__imp_GetLastError
0x1800befee  test    eax, eax
0x1800beff0  jle     short loc_1800BEFFA
0x1800beff2  movzx   eax, ax
0x1800beff5  or      eax, 80070000h
0x1800beffa  mov     ecx, eax; this
0x1800beffc  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800bf001  nop
0x1800bf002  call    cs:__imp_GetLastError
0x1800bf008  nop
0x1800bf009  test    eax, eax
0x1800bf00b  jle     short loc_1800BF015
0x1800bf00d  movzx   eax, ax
0x1800bf010  or      eax, 80070000h
0x1800bf015  mov     ecx, eax; this
0x1800bf017  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800bf01c  int     3; Trap to Debugger
0x1800bf01d  call    cs:__imp_GetLastError
0x1800bf023  test    eax, eax
0x1800bf025  jle     short loc_1800BF02F
0x1800bf027  movzx   eax, ax
0x1800bf02a  or      eax, 80070000h
0x1800bf02f  mov     ecx, eax; this
0x1800bf031  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800bf036  nop
0x1800bf037  call    cs:__imp_GetLastError
0x1800bf03d  test    eax, eax
0x1800bf03f  jle     short loc_1800BF049
0x1800bf041  movzx   eax, ax
0x1800bf044  or      eax, 80070000h
0x1800bf049  mov     ecx, eax; this
0x1800bf04b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800bf050  nop
0x1800bf051  call    cs:__imp_GetLastError
0x1800bf057  test    eax, eax
0x1800bf059  jle     short loc_1800BF063
0x1800bf05b  movzx   eax, ax
0x1800bf05e  or      eax, 80070000h
0x1800bf063  mov     ecx, eax; this
0x1800bf065  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
