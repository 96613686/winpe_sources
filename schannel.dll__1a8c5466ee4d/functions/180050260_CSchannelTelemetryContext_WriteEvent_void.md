# CSchannelTelemetryContext::WriteEvent(void)

- ea: `0x180050260`
- end: `0x18005094f`
- name: `?WriteEvent@CSchannelTelemetryContext@@MEAAXXZ`
- size: `1775`
- prototype: `void __fastcall(CSchannelTelemetryContext *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001c84`
- `0x18002ec34`
- `0x180050260`
- `0x180050960`
- `0x18006fe8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180050289`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800502a2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180050289`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800502a2`

## string_xrefs

- `0x18005027f`: `.data.microsoft.com`
- `0x180050298`: `.telemetry.microsoft.com`

## pseudocode

```c
void __fastcall CSchannelTelemetryContext::WriteEvent(CSchannelTelemetryContext *this, __int64 a2, __int64 a3)
{
  const wchar_t *v3; // rdi
  int v5; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rcx
  _WORD v15[2]; // [rsp+100h] [rbp-80h] BYREF
  int v16; // [rsp+104h] [rbp-7Ch] BYREF
  int v17; // [rsp+108h] [rbp-78h] BYREF
  int v18; // [rsp+10Ch] [rbp-74h] BYREF
  int v19; // [rsp+110h] [rbp-70h] BYREF
  int v20; // [rsp+114h] [rbp-6Ch] BYREF
  int v21; // [rsp+118h] [rbp-68h] BYREF
  int v22; // [rsp+11Ch] [rbp-64h] BYREF
  int v23; // [rsp+120h] [rbp-60h] BYREF
  int v24; // [rsp+124h] [rbp-5Ch] BYREF
  int v25; // [rsp+128h] [rbp-58h] BYREF
  int v26; // [rsp+12Ch] [rbp-54h] BYREF
  int v27; // [rsp+130h] [rbp-50h] BYREF
  int v28; // [rsp+134h] [rbp-4Ch] BYREF
  __int64 v29; // [rsp+138h] [rbp-48h] BYREF
  const wchar_t *v30; // [rsp+140h] [rbp-40h] BYREF
  char *v31; // [rsp+148h] [rbp-38h] BYREF
  const wchar_t *v32; // [rsp+150h] [rbp-30h] BYREF
  __int64 v33; // [rsp+158h] [rbp-28h] BYREF
  char *v34; // [rsp+160h] [rbp-20h] BYREF
  __int16 v35; // [rsp+168h] [rbp-18h]
  __int64 v36; // [rsp+170h] [rbp-10h] BYREF
  const wchar_t *v37; // [rsp+178h] [rbp-8h] BYREF
  const wchar_t *v38; // [rsp+180h] [rbp+0h] BYREF
  const wchar_t *v39; // [rsp+188h] [rbp+8h] BYREF
  __int16 v40; // [rsp+190h] [rbp+10h]
  char v41; // [rsp+1C0h] [rbp+40h] BYREF
  char v42; // [rsp+1C8h] [rbp+48h] BYREF
  __int16 v43; // [rsp+1D0h] [rbp+50h] BYREF
  __int16 v44; // [rsp+1D8h] [rbp+58h] BYREF

  v3 = (const wchar_t *)((char *)this + 160);
  if ( this == (CSchannelTelemetryContext *)-160LL
    || !wcsstr((const wchar_t *)this + 80, L".data.microsoft.com") && !wcsstr(v3, L".telemetry.microsoft.com") )
  {
    v5 = *((_DWORD *)this + 5);
    if ( *((_BYTE *)this + 25) )
    {
      if ( v5 == 1 )
      {
        if ( (unsigned int)dword_1800AD4B8 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_1800AD4B8, 0x400000000000LL, a3, 1) )
          {
            v16 = *((_DWORD *)this + 30);
            v41 = *((_BYTE *)this + 116);
            v17 = *((_DWORD *)this + 28);
            v18 = *((_DWORD *)this + 18);
            v19 = *((_DWORD *)this + 17);
            v8 = *((unsigned __int16 *)this + 846);
            v20 = *((_DWORD *)this + 16);
            v21 = *((_DWORD *)this + 15);
            v22 = *((_DWORD *)this + 14);
            v23 = *((_DWORD *)this + 12);
            v24 = *((_DWORD *)this + 11);
            v34 = (char *)this + 1592;
            v25 = *((_DWORD *)this + 21);
            v26 = *((_DWORD *)this + 20);
            v44 = *((_WORD *)this + 39);
            v15[0] = *((_WORD *)this + 38);
            v36 = *((_QWORD *)this + 17);
            v37 = (const wchar_t *)*((_QWORD *)this + 16);
            v42 = *((_BYTE *)this + 32);
            v38 = (const wchar_t *)((char *)this + 672);
            v27 = *((_DWORD *)this + 10);
            v28 = bDomainJoined;
            v29 = *((unsigned __int8 *)this + 1696);
            v30 = (const wchar_t *)*((_QWORD *)this + 13);
            v31 = (char *)v30;
            v32 = v30;
            v43 = v8;
            v35 = v8;
            v39 = v3;
            v33 = v7;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
              v8,
              byte_18009D883,
              v6,
              &v33,
              &v32,
              &v31,
              &v30,
              &v29,
              &v39,
              &v28,
              &v27,
              &v38,
              &v42,
              &v37,
              &v36,
              v15,
              &v44,
              &v26,
              &v25,
              &v34,
              &v43,
              &v24,
              &v23,
              &v22,
              &v21,
              &v20,
              &v19,
              &v18,
              &v17,
              &v41,
              &v16);
          }
        }
      }
      else if ( v5 == 2
             && (unsigned int)dword_1800AD4B8 > 5
             && (unsigned __int8)tlgKeywordOn(&dword_1800AD4B8, 0x400000000000LL, a3, 1) )
      {
        v28 = *((_DWORD *)this + 397);
        v34 = (char *)this + 1184;
        v35 = *((_WORD *)this + 792);
        v27 = *((_DWORD *)this + 13);
        v26 = *((_DWORD *)this + 30);
        v41 = *((_BYTE *)this + 116);
        v25 = *((_DWORD *)this + 28);
        v11 = *((unsigned __int16 *)this + 846);
        v24 = *((_DWORD *)this + 18);
        v23 = *((_DWORD *)this + 17);
        v22 = *((_DWORD *)this + 16);
        v21 = *((_DWORD *)this + 15);
        v20 = *((_DWORD *)this + 14);
        v19 = *((_DWORD *)this + 12);
        v18 = *((_DWORD *)this + 11);
        v39 = (const wchar_t *)((char *)this + 1592);
        v17 = *((_DWORD *)this + 21);
        v16 = *((_DWORD *)this + 20);
        v44 = *((_WORD *)this + 39);
        v15[0] = *((_WORD *)this + 38);
        v33 = *((_QWORD *)this + 17);
        v32 = (const wchar_t *)*((_QWORD *)this + 16);
        v42 = *((_BYTE *)this + 32);
        v31 = (char *)this + 672;
        v30 = (const wchar_t *)*((unsigned __int8 *)this + 1696);
        v43 = v11;
        v40 = v11;
        v29 = v10;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<4>,_tlgWrapperByVal<4>>(
          v11,
          byte_18009DD31,
          v9,
          &v29,
          &v30,
          &v31,
          &v42,
          &v32,
          &v33,
          v15,
          &v44,
          &v16,
          &v17,
          &v39,
          &v43,
          &v18,
          &v19,
          &v20,
          &v21,
          &v22,
          &v23,
          &v24,
          &v25,
          &v41,
          &v26,
          &v27,
          &v34,
          &v28);
      }
    }
    else if ( v5 == 1 )
    {
      if ( (unsigned int)dword_1800AD4B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800AD4B8, 0x400000000000LL, a3, 1) )
      {
        v28 = *((_DWORD *)this + 30);
        v41 = *((_BYTE *)this + 116);
        v27 = *((_DWORD *)this + 28);
        v26 = *((_DWORD *)this + 18);
        v25 = *((_DWORD *)this + 17);
        v14 = *((unsigned __int16 *)this + 846);
        v24 = *((_DWORD *)this + 16);
        v23 = *((_DWORD *)this + 15);
        v22 = *((_DWORD *)this + 14);
        v21 = *((_DWORD *)this + 12);
        v20 = *((_DWORD *)this + 11);
        v34 = (char *)this + 1592;
        v19 = *((_DWORD *)this + 21);
        v18 = *((_DWORD *)this + 20);
        v44 = *((_WORD *)this + 39);
        v15[0] = *((_WORD *)this + 38);
        v33 = *((_QWORD *)this + 17);
        v32 = (const wchar_t *)*((_QWORD *)this + 16);
        v42 = *((_BYTE *)this + 32);
        v31 = (char *)this + 672;
        v17 = *((_DWORD *)this + 10);
        v16 = bDomainJoined;
        v29 = *((unsigned __int8 *)this + 1696);
        v39 = (const wchar_t *)*((_QWORD *)this + 13);
        v38 = v39;
        v37 = v39;
        v43 = v14;
        v35 = v14;
        v30 = v3;
        v36 = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
          v14,
          &unk_18009DA98,
          v12,
          &v36,
          &v37,
          &v38,
          &v39,
          &v29,
          &v30,
          &v16,
          &v17,
          &v31,
          &v42,
          &v32,
          &v33,
          v15,
          &v44,
          &v18,
          &v19,
          &v34,
          &v43,
          &v20,
          &v21,
          &v22,
          &v23,
          &v24,
          &v25,
          &v26,
          &v27,
          &v41,
          &v28);
      }
    }
    else if ( v5 == 2 )
    {
      CSchannelTelemetryContext::WriteServerEvent(this);
    }
  }
}

```

## disassembly

```asm
0x180050260  push    rbp
0x180050262  push    rbx
0x180050263  push    rdi
0x180050264  lea     rbp, [rsp-20h]
0x180050269  sub     rsp, 1A0h
0x180050270  lea     rdi, [rcx+0A0h]
0x180050277  mov     rbx, rcx
0x18005027a  test    rdi, rdi
0x18005027d  jz      short loc_1800502B1
0x18005027f  lea     rdx, aDataMicrosoftC; ".data.microsoft.com"
0x180050286  mov     rcx, rdi; Str
0x180050289  call    cs:__imp_wcsstr
0x18005028f  test    rax, rax
0x180050292  jnz     loc_180050944
0x180050298  lea     rdx, aTelemetryMicro; ".telemetry.microsoft.com"
0x18005029f  mov     rcx, rdi; Str
0x1800502a2  call    cs:__imp_wcsstr
0x1800502a8  test    rax, rax
0x1800502ab  jnz     loc_180050944
0x1800502b1  cmp     byte ptr [rbx+19h], 0
0x1800502b5  mov     r9d, 1
0x1800502bb  mov     eax, [rbx+14h]
0x1800502be  jz      loc_180050704
0x1800502c4  cmp     eax, r9d
0x1800502c7  jnz     loc_1800504F0
0x1800502cd  mov     eax, cs:dword_1800AD4B8
0x1800502d3  cmp     eax, 5
0x1800502d6  jbe     loc_180050944
0x1800502dc  mov     rdx, 400000000000h
0x1800502e6  lea     rcx, dword_1800AD4B8
0x1800502ed  call    _tlgKeywordOn
0x1800502f2  test    al, al
0x1800502f4  jz      loc_180050944
0x1800502fa  mov     eax, [rbx+78h]
0x1800502fd  mov     [rbp+30h+var_AC], eax
0x180050300  mov     al, [rbx+74h]
0x180050303  mov     [rbp+30h+arg_0], al
0x180050306  mov     eax, [rbx+70h]
0x180050309  mov     [rbp+30h+var_A8], eax
0x18005030c  mov     eax, [rbx+48h]
0x18005030f  mov     [rbp+30h+var_A4], eax
0x180050312  mov     eax, [rbx+44h]
0x180050315  mov     [rbp+30h+var_A0], eax
0x180050318  mov     eax, [rbx+40h]
0x18005031b  movzx   ecx, word ptr [rbx+69Ch]
0x180050322  mov     [rbp+30h+var_9C], eax
0x180050325  mov     eax, [rbx+3Ch]
0x180050328  mov     [rbp+30h+var_98], eax
0x18005032b  mov     eax, [rbx+38h]
0x18005032e  mov     [rbp+30h+var_94], eax
0x180050331  mov     eax, [rbx+30h]
0x180050334  mov     [rbp+30h+var_90], eax
0x180050337  mov     eax, [rbx+2Ch]
0x18005033a  mov     [rbp+30h+var_8C], eax
0x18005033d  lea     rax, [rbx+638h]
0x180050344  mov     [rbp+30h+var_50], rax
0x180050348  mov     eax, [rbx+54h]
0x18005034b  mov     [rbp+30h+var_88], eax
0x18005034e  mov     eax, [rbx+50h]
0x180050351  mov     [rbp+30h+var_84], eax
0x180050354  movzx   eax, word ptr [rbx+4Eh]
0x180050358  mov     [rbp+30h+arg_18], ax
0x18005035c  movzx   eax, word ptr [rbx+4Ch]
0x180050360  mov     [rbp+30h+var_B0], ax
0x180050364  mov     rax, [rbx+88h]
0x18005036b  mov     [rbp+30h+var_40], rax
0x18005036f  mov     rax, [rbx+80h]
0x180050376  mov     [rbp+30h+var_38], rax
0x18005037a  mov     al, [rbx+20h]
0x18005037d  mov     [rbp+30h+arg_8], al
0x180050380  lea     rax, [rbx+2A0h]
0x180050387  mov     [rbp+30h+var_30], rax
0x18005038b  mov     eax, [rbx+28h]
0x18005038e  mov     [rbp+30h+var_80], eax
0x180050391  mov     eax, cs:?bDomainJoined@@3HA; int bDomainJoined
0x180050397  mov     [rbp+30h+var_7C], eax
0x18005039a  movzx   eax, byte ptr [rbx+6A0h]
0x1800503a1  mov     [rbp+30h+var_78], rax
0x1800503a5  mov     rax, [rbx+68h]
0x1800503a9  mov     [rbp+30h+var_70], rax
0x1800503ad  mov     [rbp+30h+var_68], rax
0x1800503b1  mov     [rbp+30h+var_60], rax
0x1800503b5  lea     rax, [rbp+30h+var_AC]
0x1800503b9  mov     [rsp+1B0h+var_C0], rax
0x1800503c1  lea     rax, [rbp+30h+arg_0]
0x1800503c5  mov     [rsp+1B0h+var_C8], rax
0x1800503cd  lea     rax, [rbp+30h+var_A8]
0x1800503d1  mov     [rsp+1B0h+var_D0], rax
0x1800503d9  lea     rax, [rbp+30h+var_A4]
0x1800503dd  mov     [rsp+1B0h+var_D8], rax
0x1800503e5  lea     rax, [rbp+30h+var_A0]
0x1800503e9  mov     [rsp+1B0h+var_E0], rax
0x1800503f1  lea     rax, [rbp+30h+var_9C]
0x1800503f5  mov     [rsp+1B0h+var_E8], rax
0x1800503fd  lea     rax, [rbp+30h+var_98]
0x180050401  mov     [rsp+1B0h+var_F0], rax
0x180050409  lea     rax, [rbp+30h+var_94]
0x18005040d  mov     [rsp+1B0h+var_F8], rax
0x180050415  lea     rax, [rbp+30h+var_90]
0x180050419  mov     [rsp+1B0h+var_100], rax
0x180050421  lea     rax, [rbp+30h+var_8C]
0x180050425  mov     [rsp+1B0h+var_108], rax
0x18005042d  lea     rax, [rbp+30h+arg_10]
0x180050431  mov     [rsp+1B0h+var_110], rax
0x180050439  lea     rax, [rbp+30h+var_50]
0x18005043d  mov     [rsp+1B0h+var_118], rax
0x180050445  lea     rax, [rbp+30h+var_88]
0x180050449  mov     [rsp+1B0h+var_120], rax
0x180050451  lea     rax, [rbp+30h+var_84]
0x180050455  mov     [rsp+1B0h+var_128], rax
0x18005045d  mov     [rbp+30h+arg_10], cx
0x180050461  mov     [rbp+30h+var_48], cx
0x180050465  mov     [rbp+30h+var_28], rdi
0x180050469  mov     [rbp+30h+var_58], r9
0x18005046d  lea     rax, [rbp+30h+arg_18]
0x180050471  mov     [rsp+1B0h+var_130], rax
0x180050479  lea     r9, [rbp+30h+var_58]
0x18005047d  lea     rax, [rbp+30h+var_B0]
0x180050481  mov     [rsp+1B0h+var_138], rax
0x180050486  lea     rdx, byte_18009D883
0x18005048d  lea     rax, [rbp+30h+var_40]
0x180050491  mov     [rsp+1B0h+var_140], rax
0x180050496  lea     rax, [rbp+30h+var_38]
0x18005049a  mov     [rsp+1B0h+var_148], rax
0x18005049f  lea     rax, [rbp+30h+arg_8]
0x1800504a3  mov     [rsp+1B0h+var_150], rax
0x1800504a8  lea     rax, [rbp+30h+var_30]
0x1800504ac  mov     [rsp+1B0h+var_158], rax
0x1800504b1  lea     rax, [rbp+30h+var_80]
0x1800504b5  mov     [rsp+1B0h+var_160], rax
0x1800504ba  lea     rax, [rbp+30h+var_7C]
0x1800504be  mov     [rsp+1B0h+var_168], rax
0x1800504c3  lea     rax, [rbp+30h+var_28]
0x1800504c7  mov     [rsp+1B0h+var_170], rax
0x1800504cc  lea     rax, [rbp+30h+var_78]
0x1800504d0  mov     [rsp+1B0h+var_178], rax
0x1800504d5  lea     rax, [rbp+30h+var_70]
0x1800504d9  mov     [rsp+1B0h+var_180], rax
0x1800504de  lea     rax, [rbp+30h+var_68]
0x1800504e2  mov     [rsp+1B0h+var_188], rax
0x1800504e7  lea     rax, [rbp+30h+var_60]
0x1800504eb  jmp     loc_18005092B
0x1800504f0  cmp     eax, 2
0x1800504f3  jnz     loc_180050944
0x1800504f9  mov     eax, cs:dword_1800AD4B8
0x1800504ff  cmp     eax, 5
0x180050502  jbe     loc_180050944
0x180050508  mov     rdx, 400000000000h
0x180050512  lea     rcx, dword_1800AD4B8
0x180050519  call    _tlgKeywordOn
0x18005051e  test    al, al
0x180050520  jz      loc_180050944
0x180050526  mov     eax, [rbx+634h]
0x18005052c  mov     [rbp+30h+var_7C], eax
0x18005052f  lea     rax, [rbx+4A0h]
0x180050536  mov     [rbp+30h+var_50], rax
0x18005053a  movzx   eax, word ptr [rbx+630h]
0x180050541  mov     [rbp+30h+var_48], ax
0x180050545  mov     eax, [rbx+34h]
0x180050548  mov     [rbp+30h+var_80], eax
0x18005054b  mov     eax, [rbx+78h]
0x18005054e  mov     [rbp+30h+var_84], eax
0x180050551  mov     al, [rbx+74h]
0x180050554  mov     [rbp+30h+arg_0], al
0x180050557  mov     eax, [rbx+70h]
0x18005055a  mov     [rbp+30h+var_88], eax
0x18005055d  mov     eax, [rbx+48h]
0x180050560  movzx   ecx, word ptr [rbx+69Ch]
0x180050567  mov     [rbp+30h+var_8C], eax
0x18005056a  mov     eax, [rbx+44h]
0x18005056d  mov     [rbp+30h+var_90], eax
0x180050570  mov     eax, [rbx+40h]
0x180050573  mov     [rbp+30h+var_94], eax
0x180050576  mov     eax, [rbx+3Ch]
0x180050579  mov     [rbp+30h+var_98], eax
0x18005057c  mov     eax, [rbx+38h]
0x18005057f  mov     [rbp+30h+var_9C], eax
0x180050582  mov     eax, [rbx+30h]
0x180050585  mov     [rbp+30h+var_A0], eax
0x180050588  mov     eax, [rbx+2Ch]
0x18005058b  mov     [rbp+30h+var_A4], eax
0x18005058e  lea     rax, [rbx+638h]
0x180050595  mov     [rbp+30h+var_28], rax
0x180050599  mov     eax, [rbx+54h]
0x18005059c  mov     [rbp+30h+var_A8], eax
0x18005059f  mov     eax, [rbx+50h]
0x1800505a2  mov     [rbp+30h+var_AC], eax
0x1800505a5  movzx   eax, word ptr [rbx+4Eh]
0x1800505a9  mov     [rbp+30h+arg_18], ax
0x1800505ad  movzx   eax, word ptr [rbx+4Ch]
0x1800505b1  mov     [rbp+30h+var_B0], ax
0x1800505b5  mov     rax, [rbx+88h]
0x1800505bc  mov     [rbp+30h+var_58], rax
0x1800505c0  mov     rax, [rbx+80h]
0x1800505c7  mov     [rbp+30h+var_60], rax
0x1800505cb  mov     al, [rbx+20h]
0x1800505ce  mov     [rbp+30h+arg_8], al
0x1800505d1  lea     rax, [rbx+2A0h]
0x1800505d8  mov     [rbp+30h+var_68], rax
0x1800505dc  movzx   eax, byte ptr [rbx+6A0h]
0x1800505e3  mov     [rbp+30h+var_70], rax
0x1800505e7  lea     rax, [rbp+30h+var_7C]
0x1800505eb  mov     [rsp+1B0h+var_D8], rax
0x1800505f3  lea     rax, [rbp+30h+var_50]
0x1800505f7  mov     [rsp+1B0h+var_E0], rax
0x1800505ff  lea     rax, [rbp+30h+var_80]
0x180050603  mov     [rsp+1B0h+var_E8], rax
0x18005060b  lea     rax, [rbp+30h+var_84]
0x18005060f  mov     [rsp+1B0h+var_F0], rax
0x180050617  lea     rax, [rbp+30h+arg_0]
0x18005061b  mov     [rsp+1B0h+var_F8], rax
0x180050623  lea     rax, [rbp+30h+var_88]
0x180050627  mov     [rsp+1B0h+var_100], rax
0x18005062f  lea     rax, [rbp+30h+var_8C]
0x180050633  mov     [rsp+1B0h+var_108], rax
0x18005063b  lea     rax, [rbp+30h+var_90]
0x18005063f  mov     [rsp+1B0h+var_110], rax
0x180050647  lea     rax, [rbp+30h+var_94]
0x18005064b  mov     [rsp+1B0h+var_118], rax
0x180050653  lea     rax, [rbp+30h+var_98]
0x180050657  mov     [rsp+1B0h+var_120], rax
0x18005065f  lea     rax, [rbp+30h+var_9C]
0x180050663  mov     [rsp+1B0h+var_128], rax
0x18005066b  lea     rax, [rbp+30h+var_A0]
0x18005066f  mov     [rsp+1B0h+var_130], rax
0x180050677  lea     rax, [rbp+30h+var_A4]
0x18005067b  mov     [rsp+1B0h+var_138], rax
0x180050680  lea     rax, [rbp+30h+arg_10]
0x180050684  mov     [rsp+1B0h+var_140], rax
0x180050689  lea     rax, [rbp+30h+var_28]
0x18005068d  mov     [rbp+30h+arg_10], cx
0x180050691  mov     [rbp+30h+var_20], cx
0x180050695  mov     [rbp+30h+var_78], r9
0x180050699  mov     [rsp+1B0h+var_148], rax
0x18005069e  lea     r9, [rbp+30h+var_78]
0x1800506a2  lea     rax, [rbp+30h+var_A8]
0x1800506a6  mov     [rsp+1B0h+var_150], rax
0x1800506ab  lea     rdx, byte_18009DD31
0x1800506b2  lea     rax, [rbp+30h+var_AC]
0x1800506b6  mov     [rsp+1B0h+var_158], rax
0x1800506bb  lea     rax, [rbp+30h+arg_18]
0x1800506bf  mov     [rsp+1B0h+var_160], rax
0x1800506c4  lea     rax, [rbp+30h+var_B0]
0x1800506c8  mov     [rsp+1B0h+var_168], rax
0x1800506cd  lea     rax, [rbp+30h+var_58]
0x1800506d1  mov     [rsp+1B0h+var_170], rax
0x1800506d6  lea     rax, [rbp+30h+var_60]
0x1800506da  mov     [rsp+1B0h+var_178], rax
0x1800506df  lea     rax, [rbp+30h+arg_8]
0x1800506e3  mov     [rsp+1B0h+var_180], rax
0x1800506e8  lea     rax, [rbp+30h+var_68]
0x1800506ec  mov     [rsp+1B0h+var_188], rax
0x1800506f1  lea     rax, [rbp+30h+var_70]
0x1800506f5  mov     [rsp+1B0h+var_190], rax
0x1800506fa  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U1@U1@U?$_tlgWrapperByVal@$01@@U4@U?$_tlgWrapperByVal@$03@@U5@U?$_tlgWrapperArray@$01@@U4@U5@U5@U5@U5@U5@U5@U5@U5@U3@U5@U5@U?$_tlgWrapperArray@$03@@U5@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@22AEBU?$_tlgWrapperByVal@$01@@5AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperArray@$01@@566666666466AEBU?$_tlgWrapperArray@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperArray<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperArray<4> const &,_tlgWrapperByVal<4> const &)
0x1800506ff  jmp     loc_180050944
0x180050704  cmp     eax, r9d
0x180050707  jnz     loc_180050937
0x18005070d  mov     eax, cs:dword_1800AD4B8
0x180050713  cmp     eax, 5
0x180050716  jbe     loc_180050944
0x18005071c  mov     rdx, 400000000000h
0x180050726  lea     rcx, dword_1800AD4B8
0x18005072d  call    _tlgKeywordOn
0x180050732  test    al, al
0x180050734  jz      loc_180050944
0x18005073a  mov     eax, [rbx+78h]
0x18005073d  mov     [rbp+30h+var_7C], eax
0x180050740  mov     al, [rbx+74h]
0x180050743  mov     [rbp+30h+arg_0], al
0x180050746  mov     eax, [rbx+70h]
0x180050749  mov     [rbp+30h+var_80], eax
0x18005074c  mov     eax, [rbx+48h]
0x18005074f  mov     [rbp+30h+var_84], eax
0x180050752  mov     eax, [rbx+44h]
0x180050755  mov     [rbp+30h+var_88], eax
0x180050758  mov     eax, [rbx+40h]
0x18005075b  movzx   ecx, word ptr [rbx+69Ch]
0x180050762  mov     [rbp+30h+var_8C], eax
0x180050765  mov     eax, [rbx+3Ch]
0x180050768  mov     [rbp+30h+var_90], eax
0x18005076b  mov     eax, [rbx+38h]
0x18005076e  mov     [rbp+30h+var_94], eax
0x180050771  mov     eax, [rbx+30h]
0x180050774  mov     [rbp+30h+var_98], eax
0x180050777  mov     eax, [rbx+2Ch]
0x18005077a  mov     [rbp+30h+var_9C], eax
0x18005077d  lea     rax, [rbx+638h]
0x180050784  mov     [rbp+30h+var_50], rax
0x180050788  mov     eax, [rbx+54h]
0x18005078b  mov     [rbp+30h+var_A0], eax
0x18005078e  mov     eax, [rbx+50h]
0x180050791  mov     [rbp+30h+var_A4], eax
0x180050794  movzx   eax, word ptr [rbx+4Eh]
0x180050798  mov     [rbp+30h+arg_18], ax
0x18005079c  movzx   eax, word ptr [rbx+4Ch]
0x1800507a0  mov     [rbp+30h+var_B0], ax
0x1800507a4  mov     rax, [rbx+88h]
0x1800507ab  mov     [rbp+30h+var_58], rax
0x1800507af  mov     rax, [rbx+80h]
  ... truncated ...
```
