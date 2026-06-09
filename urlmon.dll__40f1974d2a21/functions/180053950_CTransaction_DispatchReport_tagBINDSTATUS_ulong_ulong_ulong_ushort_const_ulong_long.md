# CTransaction::DispatchReport(tagBINDSTATUS,ulong,ulong,ulong,ushort const *,ulong,long)

- ea: `0x180053950`
- end: `0x180054246`
- name: `?DispatchReport@CTransaction@@QEAAJW4tagBINDSTATUS@@KKKPEBGKJ@Z`
- size: `2294`
- prototype: `__int64 __usercall@<rax>(CTransaction *__hidden this@<rcx>, enum tagBINDSTATUS@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, const unsigned __int16 *, unsigned int, int)`
- caller_count: `9`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800229a0`
- `0x180022c80`
- `0x180023f30`
- `0x180052e20`
- `0x180053090`
- `0x1800532c0`
- `0x180053590`
- `0x180054430`
- `0x180054ad8`

## callees

- `0x1800150e0`
- `0x18001c470`
- `0x1800214d0`
- `0x18002c524`
- `0x18002f214`
- `0x18003b010`
- `0x180053950`
- `0x18005c564`
- `0x180061ccc`
- `0x180061ea0`
- `0x180068238`
- `0x180072f80`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180053a44`
- `msvcrt!swprintf_s` at `0x180053a44`
- `iertutil!CreateUri` at `0x180053ba1`
- `iertutil!CreateUri` at `0x180053c7f`
- `iertutil!CreateUri` at `0x180053ba1`
- `iertutil!CreateUri` at `0x180053c7f`
- `iertutil!__imp_IECompatLogEvent` at `0x180053f5f`
- `iertutil!__imp_IECompatLogEvent` at `0x180053f5f`
- `iertutil!__imp_?IECompatLoggingEnabledInternal@@YAHXZ` at `0x180053ef6`
- `iertutil!__imp_?IECompatLoggingEnabledInternal@@YAHXZ` at `0x180053ef6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005415b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005417a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005415b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005417a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054141`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054141`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053f68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005401d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054062`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005409c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800540e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053f68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005401d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054062`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005409c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800540e1`

## string_xrefs

- `0x180053e3f`: `Class Install Handler `

## pseudocode

```c
__int64 __fastcall CTransaction::DispatchReport(
        CTransaction *this,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        LPCWSTR pwzURI,
        unsigned int a7,
        int a8)
{
  unsigned int v8; // r13d
  LPCWSTR v9; // r14
  unsigned int v10; // r12d
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned __int64 v15; // r9
  int v16; // eax
  wchar_t *v17; // rdx
  char v18; // al
  HRESULT MimeFilter; // esi
  struct IServiceProvider *v20; // r8
  __int64 v21; // rdx
  DWORD v22; // eax
  HRESULT v23; // eax
  char v24; // al
  struct IInternetProtocolSink *v25; // rcx
  DWORD v26; // eax
  __int64 v27; // rax
  unsigned int v28; // ebx
  struct IInternetProtocolSink *v29; // rcx
  __int64 v30; // rcx
  unsigned __int64 v31; // rsi
  unsigned __int16 *v32; // rax
  unsigned __int16 *v33; // rbx
  __int64 v34; // rcx
  const wchar_t *v35; // r8
  unsigned __int64 v36; // rdx
  unsigned __int16 *v37; // rcx
  unsigned int v38; // r9d
  char v39; // al
  LPCWSTR *v40; // rbx
  LPCWSTR v41; // r8
  __int64 v42; // rdx
  void *v43; // rcx
  void *v44; // rcx
  void *v45; // rcx
  void *v46; // rcx
  char v47; // al
  struct _RTL_CRITICAL_SECTION *v48; // rcx
  struct IInternetProtocolSink *v49; // rcx
  struct IUnknown *v51; // [rsp+20h] [rbp-E0h]
  struct IInternetProtocolSink *v52; // [rsp+60h] [rbp-A0h] BYREF
  IUri *ppURI; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v54; // [rsp+70h] [rbp-90h] BYREF
  int v55; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v56; // [rsp+78h] [rbp-88h] BYREF
  int v57; // [rsp+7Ch] [rbp-84h] BYREF
  int v58; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v59; // [rsp+88h] [rbp-78h] BYREF
  struct IUnknown v60; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Buffer[40]; // [rsp+A0h] [rbp-60h] BYREF

  v8 = a4;
  v9 = pwzURI;
  v10 = a3;
  if ( (unsigned int)dword_180159000 > 5 )
  {
    v13 = qword_180159018;
    if ( (qword_180159010 & 0x20) != 0 && (qword_180159018 & 0x20) == qword_180159018 )
    {
      v54 = a7;
      v56 = a5;
      v55 = a8;
      v57 = a4;
      v58 = a3;
      if ( a2 == 73 )
      {
        v14 = *pwzURI;
        v15 = v14 | (v14 << 15) | ((v14 | (v14 << 15)) << 30);
        v16 = swprintf_s(
                Buffer,
                0x25u,
                L"0x%lX;0x%llX;0x%X",
                *(_DWORD *)(pwzURI + 1) ^ (*(_DWORD *)(pwzURI + 1) ^ (unsigned int)(v15 >> 4)) & 0x10001,
                v15 ^ (*(_QWORD *)(pwzURI + 3) ^ v15) & 0xFFFEFFFEFFFEFFFEuLL,
                pwzURI[7]);
        v13 = 0;
        v17 = Buffer;
        if ( v16 < 0 )
          v17 = 0;
      }
      else
      {
        v17 = (wchar_t *)pwzURI;
      }
      v59 = v17;
      LODWORD(ppURI) = a2;
      v60.lpVtbl = (struct IUnknownVtbl *)this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned __int8 *)byte_1801459C3,
        a3,
        a4,
        (__int64)&v60,
        (__int64)&ppURI,
        (const OLECHAR **)&v59,
        (__int64)&v58,
        (__int64)&v57,
        (__int64)&v56,
        (__int64)&v55,
        (__int64)&v54);
    }
  }
  v18 = *((_BYTE *)this + 441);
  MimeFilter = 0;
  v52 = 0;
  if ( (v18 & 2) == 0 )
  {
    if ( (*(unsigned int (__fastcall **)(CTransaction *, struct IInternetProtocolSink **))(*(_QWORD *)this + 184LL))(
           this,
           &v52) )
    {
      v47 = *((_BYTE *)this + 441);
      if ( (v47 & 2) == 0 && (a2 == 61 || a2 == 58) )
      {
        *((_BYTE *)this + 441) = v47 | 1;
        (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 6) + 48LL))((char *)this + 48, 0);
      }
    }
    else
    {
      if ( *((_DWORD *)this + 108) == 2 )
        *((_DWORD *)this + 108) = 0;
      switch ( a2 )
      {
        case 3u:
          ppURI = 0;
          v22 = HelperAddUriDefaultFlags(0x3002B80u, 0x3002B85u);
          MimeFilter = CreateUri(pwzURI, v22, 0, &ppURI);
          if ( MimeFilter < 0 )
            goto LABEL_27;
          MimeFilter = CTransaction::SecurityCheckOnRedirect(this, ppURI);
          if ( MimeFilter < 0 )
            goto LABEL_27;
          MimeFilter = CTransaction::SetRedirectIUri(this, ppURI);
          if ( MimeFilter < 0 )
            goto LABEL_27;
          v23 = ((__int64 (__fastcall *)(struct IInternetProtocolSink *, _QWORD, _QWORD))v52->lpVtbl->ReportProgress)(
                  v52,
                  a2,
                  *((_QWORD *)this + 25));
          goto LABEL_26;
        case 4u:
          if ( (*((_BYTE *)this + 756) & 0x40) == 0 )
            goto LABEL_21;
          v21 = a2;
          goto LABEL_20;
        case 5u:
        case 6u:
          if ( a2 != 6 || (*((_BYTE *)this + 756) & 0x40) == 0 )
            goto LABEL_21;
          v21 = 6;
LABEL_20:
          ((void (__fastcall *)(struct IInternetProtocolSink *, __int64, LPCWSTR))v52->lpVtbl->ReportProgress)(
            v52,
            v21,
            pwzURI);
LABEL_21:
          MimeFilter = ((__int64 (__fastcall *)(struct IInternetProtocolSink *, _QWORD, _QWORD, _QWORD))v52->lpVtbl->ReportData)(
                         v52,
                         v10,
                         v8,
                         a5);
          break;
        case 0xDu:
          CTransaction::_TryLoadMimeFilter(this, pwzURI);
          if ( *((_QWORD *)this + 66) )
            v9 = (LPCWSTR)*((_QWORD *)this + 66);
          goto LABEL_83;
        case 0xEu:
          v43 = (void *)*((_QWORD *)this + 60);
          if ( v43 )
            CoTaskMemFree(v43);
          *((_QWORD *)this + 60) = OLESTRDuplicate(pwzURI);
          goto LABEL_83;
        case 0x16u:
          CTransaction::_TryLoadMimeFilter(this, pwzURI);
          *((_DWORD *)this + 242) |= 0x1000u;
          v39 = *((_BYTE *)this + 441);
          *((_DWORD *)this + 233) &= 0xFFFFFDCF;
          if ( (v39 & 0x50) != 0x50 || (v40 = (LPCWSTR *)((char *)this + 512), !*((_QWORD *)this + 64)) )
          {
            v40 = (LPCWSTR *)((char *)this + 512);
            FastMimeType::SetType((CTransaction *)((char *)this + 512), pwzURI);
            *((_BYTE *)this + 441) |= 0x10u;
          }
          v41 = *v40;
          v42 = 13;
          goto LABEL_84;
        case 0x17u:
          if ( !pwzURI )
            break;
          COInetProt::Initialize(
            (CTransaction *)((char *)this + 1144),
            this,
            v20,
            *((_DWORD *)this + 189),
            v51,
            *((struct IInternetProtocol **)this + 39),
            v52,
            0);
          v30 = -1;
          do
            ++v30;
          while ( pwzURI[v30] );
          v31 = (unsigned int)(v30 + *((_DWORD *)this + 66) + 24);
          v32 = (unsigned __int16 *)operator new(saturated_mul(v31, 2u));
          v33 = v32;
          if ( !v32 )
          {
            MimeFilter = -2147024882;
            goto LABEL_72;
          }
          if ( v31 )
          {
            if ( v31 <= 0x7FFFFFFF )
            {
              v34 = 2147483646;
              v35 = L"Class Install Handler ";
              v36 = v31;
              do
              {
                if ( !v34 )
                  break;
                if ( !*v35 )
                  break;
                *v32++ = *v35++;
                --v34;
                --v36;
              }
              while ( v36 );
              v37 = v32 - 1;
              if ( v36 )
                v37 = v32;
              *v37 = 0;
            }
            else
            {
              *v32 = 0;
            }
          }
          StringCchCatW(v33, v31, *((const unsigned __int16 **)this + 32));
          StringCchCatW(v33, v31, L" ");
          StringCchCatW(v33, v31, pwzURI);
          v33[21] = 0;
          v33[*((unsigned int *)this + 66) + 22] = 0;
          MimeFilter = CTransaction::LoadMimeFilter(this, v33, (CTransaction *)((char *)this + 1144), v38, 1);
          if ( MimeFilter >= 0 || g_cmptlgs == 1 )
            goto LABEL_69;
          if ( g_cmptlgs )
          {
            if ( g_cmptlgs != 2 )
              goto LABEL_69;
          }
          else
          {
            if ( !IECompatLoggingEnabledInternal() )
            {
              g_cmptlgs = 1;
              goto LABEL_69;
            }
            g_cmptlgs = 2;
          }
          v59 = L"Scenario";
          v60.lpVtbl = (struct IUnknownVtbl *)L"DocFile";
          IECompatLogEvent(3221226516LL, L"CDLRestricted", 0, 0, 1, &v59, &v60);
LABEL_69:
          CoTaskMemFree(v33);
          if ( MimeFilter >= 0 )
            break;
LABEL_72:
          ((void (__fastcall *)(struct IInternetProtocolSink *, __int64, _QWORD))v52->lpVtbl->ReportProgress)(v52, 9, 0);
          break;
        case 0x1Au:
          *((_BYTE *)this + 440) |= 0x10u;
          v44 = (void *)*((_QWORD *)this + 63);
          if ( v44 )
            CoTaskMemFree(v44);
          if ( pwzURI )
            *((_QWORD *)this + 63) = OLESTRDuplicate(pwzURI);
          else
            *((_QWORD *)this + 63) = 0;
          goto LABEL_83;
        case 0x21u:
          *((_BYTE *)this + 440) |= 0x20u;
          goto LABEL_83;
        case 0x38u:
          v46 = (void *)*((_QWORD *)this + 61);
          if ( v46 )
            CoTaskMemFree(v46);
          *((_QWORD *)this + 61) = 0;
          if ( pwzURI )
            *((_QWORD *)this + 61) = OLESTRDuplicate(pwzURI);
          goto LABEL_83;
        case 0x3Au:
        case 0x3Du:
          if ( a8 != -2146697196 || !pwzURI )
          {
            v29 = v52;
            *((_BYTE *)this + 441) |= 1u;
            MimeFilter = ((__int64 (__fastcall *)(struct IInternetProtocolSink *, _QWORD, _QWORD, LPCWSTR))v29->lpVtbl->ReportResult)(
                           v29,
                           *((unsigned int *)this + 115),
                           *((unsigned int *)this + 116),
                           pwzURI);
            break;
          }
          ppURI = 0;
          v26 = HelperAddUriDefaultFlags(0x3002B80u, 0x3002B85u);
          MimeFilter = CreateUri(pwzURI, v26, 0, &ppURI);
          if ( MimeFilter < 0 )
            goto LABEL_27;
          v54 = 0;
          MimeFilter = ((__int64 (__fastcall *)(IUri *, unsigned int *))ppURI->lpVtbl->GetScheme)(ppURI, &v54);
          if ( v54 == 2 || v54 == 11 )
          {
            v27 = *(_QWORD *)this;
            v28 = ++*((_DWORD *)this + 111);
            if ( v28 > (*(unsigned int (__fastcall **)(CTransaction *))(v27 + 72))(this) )
            {
              MimeFilter = -2146697196;
LABEL_28:
              if ( MimeFilter != -2147483638 )
              {
                v24 = *((_BYTE *)this + 441);
                if ( (v24 & 1) == 0 )
                {
                  v25 = v52;
                  *((_BYTE *)this + 441) = v24 | 1;
                  MimeFilter = ((__int64 (__fastcall *)(struct IInternetProtocolSink *, _QWORD, _QWORD, _QWORD))v25->lpVtbl->ReportResult)(
                                 v25,
                                 (unsigned int)MimeFilter,
                                 0,
                                 0);
                }
              }
              goto LABEL_31;
            }
          }
          if ( MimeFilter < 0 )
            goto LABEL_28;
          MimeFilter = (*(__int64 (__fastcall **)(CTransaction *, LPCWSTR))(*(_QWORD *)this + 64LL))(this, pwzURI);
          if ( MimeFilter >= 0 )
          {
            MimeFilter = CTransaction::SecurityCheckOnRedirect(this, ppURI);
            if ( MimeFilter >= 0 )
            {
              MimeFilter = CTransaction::SetRedirectIUri(this, ppURI);
              if ( MimeFilter >= 0 )
              {
                MimeFilter = ((__int64 (__fastcall *)(struct IInternetProtocolSink *, __int64, _QWORD))v52->lpVtbl->ReportProgress)(
                               v52,
                               3,
                               *((_QWORD *)this + 25));
                if ( MimeFilter >= 0 )
                {
                  v23 = (*(__int64 (__fastcall **)(CTransaction *, IUri *))(*(_QWORD *)this + 96LL))(this, ppURI);
LABEL_26:
                  MimeFilter = v23;
                }
              }
            }
          }
LABEL_27:
          if ( MimeFilter )
            goto LABEL_28;
LABEL_31:
          if ( ppURI )
            ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
          break;
        case 0x41u:
          *((_BYTE *)this + 440) |= 0x40u;
          v45 = (void *)*((_QWORD *)this + 62);
          if ( v45 )
            CoTaskMemFree(v45);
          if ( pwzURI )
            *((_QWORD *)this + 62) = OLESTRDuplicate(pwzURI);
          else
            *((_QWORD *)this + 62) = 0;
          goto LABEL_83;
        case 0x48u:
          break;
        default:
LABEL_83:
          v41 = v9;
          v42 = a2;
LABEL_84:
          MimeFilter = ((__int64 (__fastcall *)(struct IInternetProtocolSink *, __int64, LPCWSTR))v52->lpVtbl->ReportProgress)(
                         v52,
                         v42,
                         v41);
          break;
      }
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
  v48 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 624);
  if ( (*((_BYTE *)this + 441) & 0xA) == 8 )
  {
    LeaveCriticalSection(v48);
    (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 6) + 48LL))(
      (char *)this + 48,
      *((unsigned int *)this + 114));
  }
  else
  {
    LeaveCriticalSection(v48);
  }
  v49 = v52;
  if ( v52 )
  {
    v52 = 0;
    ((void (__fastcall *)(struct IInternetProtocolSink *))v49->lpVtbl->Release)(v49);
  }
  return (unsigned int)MimeFilter;
}

```

## disassembly

```asm
0x180053950  push    rbp
0x180053952  push    rbx
0x180053953  push    rsi
0x180053954  push    rdi
0x180053955  push    r12
0x180053957  push    r13
0x180053959  push    r14
0x18005395b  push    r15
0x18005395d  lea     rbp, [rsp-8]
0x180053962  sub     rsp, 108h
0x180053969  mov     rax, cs:__security_cookie
0x180053970  xor     rax, rsp
0x180053973  mov     [rbp+40h+var_50], rax
0x180053977  mov     eax, cs:dword_180159000
0x18005397d  mov     r13d, r9d
0x180053980  mov     r14, [rbp+40h+pwzURI]
0x180053984  mov     r12d, r8d
0x180053987  mov     r15d, [rbp+40h+arg_38]
0x18005398e  mov     ebx, edx
0x180053990  mov     rdi, rcx
0x180053993  cmp     eax, 5
0x180053996  jbe     loc_180053AC0
0x18005399c  mov     rcx, cs:qword_180159018
0x1800539a3  mov     rax, cs:qword_180159010
0x1800539aa  test    al, 20h
0x1800539ac  jz      loc_180053AC0
0x1800539b2  mov     rax, rcx
0x1800539b5  and     eax, 20h
0x1800539b8  cmp     rax, rcx
0x1800539bb  jnz     loc_180053AC0
0x1800539c1  mov     eax, [rbp+40h+arg_30]
0x1800539c7  mov     [rsp+140h+var_D0], eax
0x1800539cb  mov     eax, [rbp+40h+arg_20]
0x1800539ce  mov     [rsp+140h+var_C8], eax
0x1800539d2  mov     [rsp+140h+var_CC], r15d
0x1800539d7  mov     [rsp+140h+var_C4], r9d
0x1800539dc  mov     [rbp+40h+var_C0], r8d
0x1800539e0  cmp     edx, 49h ; 'I'
0x1800539e3  jnz     short loc_180053A58
0x1800539e5  movzx   eax, word ptr [r14]
0x1800539e9  mov     r8, 0FFFEFFFEFFFEFFFEh
0x1800539f3  mov     ecx, eax
0x1800539f5  shl     rcx, 0Fh
0x1800539f9  or      rcx, rax
0x1800539fc  mov     r9, rcx
0x1800539ff  shl     r9, 1Eh
0x180053a03  or      r9, rcx
0x180053a06  movzx   ecx, word ptr [r14+0Eh]
0x180053a0b  mov     rdx, r9
0x180053a0e  mov     dword ptr [rsp+140h+var_118], ecx
0x180053a12  xor     rdx, [r14+6]
0x180053a16  lea     rcx, [rbp+40h+Buffer]; Buffer
0x180053a1a  and     rdx, r8
0x180053a1d  lea     r8, a0xLx0xLlx0xX; "0x%lX;0x%llX;0x%X"
0x180053a24  xor     rdx, r9
0x180053a27  shr     r9, 4
0x180053a2b  xor     r9d, [r14+2]
0x180053a2f  and     r9d, 10001h
0x180053a36  mov     [rsp+140h+var_120], rdx
0x180053a3b  xor     r9d, [r14+2]
0x180053a3f  mov     edx, 25h ; '%'; BufferCount
0x180053a44  call    cs:__imp_swprintf_s
0x180053a4a  xor     ecx, ecx
0x180053a4c  lea     rdx, [rbp+40h+Buffer]
0x180053a50  test    eax, eax
0x180053a52  cmovs   rdx, rcx
0x180053a56  jmp     short loc_180053A5B
0x180053a58  mov     rdx, r14
0x180053a5b  lea     rax, [rsp+140h+var_D0]
0x180053a60  mov     [rbp+40h+var_B8], rdx
0x180053a64  mov     [rsp+140h+var_E8], rax
0x180053a69  lea     rdx, byte_1801459C3
0x180053a70  lea     rax, [rsp+140h+var_CC]
0x180053a75  mov     dword ptr [rsp+140h+ppURI], ebx
0x180053a79  mov     [rsp+140h+var_F0], rax
0x180053a7e  lea     rax, [rsp+140h+var_C8]
0x180053a83  mov     [rsp+140h+var_F8], rax
0x180053a88  lea     rax, [rsp+140h+var_C4]
0x180053a8d  mov     [rsp+140h+var_100], rax
0x180053a92  lea     rax, [rbp+40h+var_C0]
0x180053a96  mov     [rsp+140h+var_108], rax
0x180053a9b  lea     rax, [rbp+40h+var_B8]
0x180053a9f  mov     [rsp+140h+var_110], rax
0x180053aa4  lea     rax, [rsp+140h+ppURI]
0x180053aa9  mov     [rsp+140h+var_118], rax
0x180053aae  lea     rax, [rbp+40h+var_B0]
0x180053ab2  mov     [rsp+140h+var_120], rax; struct IUnknown *
0x180053ab7  mov     [rbp+40h+var_B0.lpVtbl], rdi
0x180053abb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180053ac0  movzx   eax, byte ptr [rdi+1B9h]
0x180053ac7  xor     esi, esi
0x180053ac9  mov     [rsp+140h+var_E0], rsi
0x180053ace  test    al, 2
0x180053ad0  jnz     loc_18005413A; jumptable 0000000180053B2B case 72
0x180053ad6  mov     rax, [rdi]
0x180053ad9  lea     rdx, [rsp+140h+var_E0]
0x180053ade  mov     rcx, rdi
0x180053ae1  mov     rax, [rax+0B8h]
0x180053ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053aed  test    eax, eax
0x180053aef  jnz     loc_18005410B
0x180053af5  cmp     dword ptr [rdi+1B0h], 2
0x180053afc  jnz     short loc_180053B04
0x180053afe  mov     [rdi+1B0h], esi
0x180053b04  lea     eax, [rbx-3]; switch 70 cases
0x180053b07  cmp     eax, 45h
0x180053b0a  ja      def_180053B2B; jumptable 0000000180053B2B default case, cases 7-12,15-21,24,25,27-32,34-55,57,59,60,62-64,66-71
0x180053b10  lea     rdx, __ImageBase
0x180053b17  cdqe
0x180053b19  movzx   eax, ds:(byte_180054200 - 180000000h)[rdx+rax]
0x180053b21  mov     ecx, ds:(jpt_180053B2B - 180000000h)[rdx+rax*4]
0x180053b28  add     rcx, rdx
0x180053b2b  jmp     rcx; switch jump
0x180053b2d  test    byte ptr [rdi+2F4h], 40h; jumptable 0000000180053B2B case 4
0x180053b34  jz      short loc_180053B5E
0x180053b36  mov     edx, ebx
0x180053b38  jmp     short loc_180053B4A
0x180053b3a  cmp     ebx, 6; jumptable 0000000180053B2B cases 5,6
0x180053b3d  jnz     short loc_180053B5E
0x180053b3f  test    byte ptr [rdi+2F4h], 40h
0x180053b46  jz      short loc_180053B5E
0x180053b48  mov     edx, ebx
0x180053b4a  mov     rcx, [rsp+140h+var_E0]
0x180053b4f  mov     r8, r14
0x180053b52  mov     rax, [rcx]
0x180053b55  mov     rax, [rax+20h]
0x180053b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b5e  mov     rcx, [rsp+140h+var_E0]
0x180053b63  mov     r8d, r13d
0x180053b66  mov     r9d, [rbp+40h+arg_20]
0x180053b6a  mov     edx, r12d
0x180053b6d  mov     rax, [rcx]
0x180053b70  mov     rax, [rax+28h]
0x180053b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b79  mov     esi, eax
0x180053b7b  jmp     loc_18005413A; jumptable 0000000180053B2B case 72
0x180053b80  mov     edx, 3002B85h; jumptable 0000000180053B2B case 3
0x180053b85  mov     [rsp+140h+ppURI], rsi
0x180053b8a  mov     ecx, 3002B80h; unsigned int
0x180053b8f  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x180053b94  mov     edx, eax; dwFlags
0x180053b96  lea     r9, [rsp+140h+ppURI]; ppURI
0x180053b9b  mov     rcx, r14; pwzURI
0x180053b9e  xor     r8d, r8d; dwReserved
0x180053ba1  call    cs:__imp_CreateUri
0x180053ba7  mov     esi, eax
0x180053ba9  test    eax, eax
0x180053bab  js      short loc_180053BEF
0x180053bad  mov     rdx, [rsp+140h+ppURI]; struct IUri *
0x180053bb2  mov     rcx, rdi; this
0x180053bb5  call    ?SecurityCheckOnRedirect@CTransaction@@QEAAJPEAUIUri@@@Z; CTransaction::SecurityCheckOnRedirect(IUri *)
0x180053bba  mov     esi, eax
0x180053bbc  test    eax, eax
0x180053bbe  js      short loc_180053BEF
0x180053bc0  mov     rdx, [rsp+140h+ppURI]; struct IUri *
0x180053bc5  mov     rcx, rdi; this
0x180053bc8  call    ?SetRedirectIUri@CTransaction@@QEAAJPEAUIUri@@@Z; CTransaction::SetRedirectIUri(IUri *)
0x180053bcd  mov     esi, eax
0x180053bcf  test    eax, eax
0x180053bd1  js      short loc_180053BEF
0x180053bd3  mov     rcx, [rsp+140h+var_E0]
0x180053bd8  mov     edx, ebx
0x180053bda  mov     r8, [rdi+0C8h]
0x180053be1  mov     rax, [rcx]
0x180053be4  mov     rax, [rax+20h]
0x180053be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053bed  mov     esi, eax
0x180053bef  test    esi, esi
0x180053bf1  jz      short loc_180053C29
0x180053bf3  cmp     esi, 8000000Ah
0x180053bf9  jz      short loc_180053C29
0x180053bfb  movzx   eax, byte ptr [rdi+1B9h]
0x180053c02  test    al, 1
0x180053c04  jnz     short loc_180053C29
0x180053c06  mov     rcx, [rsp+140h+var_E0]
0x180053c0b  or      al, 1
0x180053c0d  mov     [rdi+1B9h], al
0x180053c13  xor     r9d, r9d
0x180053c16  xor     r8d, r8d
0x180053c19  mov     edx, esi
0x180053c1b  mov     rax, [rcx]
0x180053c1e  mov     rax, [rax+30h]
0x180053c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c27  mov     esi, eax
0x180053c29  mov     rcx, [rsp+140h+ppURI]
0x180053c2e  test    rcx, rcx
0x180053c31  jz      loc_18005413A; jumptable 0000000180053B2B case 72
0x180053c37  mov     rax, [rcx]
0x180053c3a  mov     rax, [rax+10h]
0x180053c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c43  jmp     loc_18005413A; jumptable 0000000180053B2B case 72
0x180053c48  cmp     r15d, 800C0014h; jumptable 0000000180053B2B cases 58,61
0x180053c4f  jnz     loc_180053D7B
0x180053c55  test    r14, r14
0x180053c58  jz      loc_180053D7B
0x180053c5e  mov     edx, 3002B85h; unsigned int
0x180053c63  mov     [rsp+140h+ppURI], rsi
0x180053c68  mov     ecx, 3002B80h; unsigned int
0x180053c6d  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x180053c72  mov     edx, eax; dwFlags
0x180053c74  lea     r9, [rsp+140h+ppURI]; ppURI
0x180053c79  mov     rcx, r14; pwzURI
0x180053c7c  xor     r8d, r8d; dwReserved
0x180053c7f  call    cs:__imp_CreateUri
0x180053c85  mov     esi, eax
0x180053c87  test    eax, eax
0x180053c89  js      loc_180053BEF
0x180053c8f  mov     rcx, [rsp+140h+ppURI]
0x180053c94  lea     rdx, [rsp+140h+var_D0]
0x180053c99  mov     [rsp+140h+var_D0], 0
0x180053ca1  mov     rax, [rcx]
0x180053ca4  mov     rax, [rax+0C0h]
0x180053cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053cb0  mov     esi, eax
0x180053cb2  mov     eax, [rsp+140h+var_D0]
0x180053cb6  cmp     eax, 2
0x180053cb9  jz      short loc_180053CC0
0x180053cbb  cmp     eax, 0Bh
0x180053cbe  jnz     short loc_180053CE9
0x180053cc0  mov     rax, [rdi]
0x180053cc3  mov     rcx, rdi
0x180053cc6  inc     dword ptr [rdi+1BCh]
0x180053ccc  mov     ebx, [rdi+1BCh]
0x180053cd2  mov     rax, [rax+48h]
0x180053cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053cdb  cmp     ebx, eax
0x180053cdd  jbe     short loc_180053CE9
0x180053cdf  mov     esi, 800C0014h
0x180053ce4  jmp     loc_180053BF3
0x180053ce9  test    esi, esi
0x180053ceb  js      loc_180053BF3
0x180053cf1  mov     rax, [rdi]
0x180053cf4  mov     rdx, r14
0x180053cf7  mov     rcx, rdi
0x180053cfa  mov     rax, [rax+40h]
0x180053cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d03  mov     esi, eax
0x180053d05  test    eax, eax
0x180053d07  js      loc_180053BEF
0x180053d0d  mov     rdx, [rsp+140h+ppURI]; struct IUri *
0x180053d12  mov     rcx, rdi; this
0x180053d15  call    ?SecurityCheckOnRedirect@CTransaction@@QEAAJPEAUIUri@@@Z; CTransaction::SecurityCheckOnRedirect(IUri *)
0x180053d1a  mov     esi, eax
0x180053d1c  test    eax, eax
0x180053d1e  js      loc_180053BEF
0x180053d24  mov     rdx, [rsp+140h+ppURI]; struct IUri *
0x180053d29  mov     rcx, rdi; this
0x180053d2c  call    ?SetRedirectIUri@CTransaction@@QEAAJPEAUIUri@@@Z; CTransaction::SetRedirectIUri(IUri *)
0x180053d31  mov     esi, eax
0x180053d33  test    eax, eax
0x180053d35  js      loc_180053BEF
0x180053d3b  mov     rcx, [rsp+140h+var_E0]
0x180053d40  mov     edx, 3
0x180053d45  mov     r8, [rdi+0C8h]
0x180053d4c  mov     rax, [rcx]
0x180053d4f  mov     rax, [rax+20h]
0x180053d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d58  mov     esi, eax
0x180053d5a  test    eax, eax
0x180053d5c  js      loc_180053BEF
0x180053d62  mov     rax, [rdi]
0x180053d65  mov     rcx, rdi
0x180053d68  mov     rdx, [rsp+140h+ppURI]
0x180053d6d  mov     rax, [rax+60h]
0x180053d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d76  jmp     loc_180053BED
0x180053d7b  mov     rcx, [rsp+140h+var_E0]
0x180053d80  mov     r9, r14
0x180053d83  or      byte ptr [rdi+1B9h], 1
0x180053d8a  mov     r8d, [rdi+1D0h]
0x180053d91  mov     edx, [rdi+1CCh]
0x180053d97  mov     rax, [rcx]
0x180053d9a  mov     rax, [rax+30h]
0x180053d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053da3  mov     esi, eax
0x180053da5  jmp     loc_18005413A; jumptable 0000000180053B2B case 72
0x180053daa  test    r14, r14; jumptable 0000000180053B2B case 23
0x180053dad  jz      loc_18005413A; jumptable 0000000180053B2B case 72
0x180053db3  mov     rax, [rsp+140h+var_E0]
0x180053db8  lea     rcx, [rdi+478h]; this
0x180053dbf  mov     r9d, [rdi+2F4h]; unsigned int
0x180053dc6  mov     rdx, rdi; struct CTransaction *
0x180053dc9  mov     [rsp+140h+var_108], rsi; struct IUri *
0x180053dce  mov     [rsp+140h+var_110], rax; struct IInternetProtocolSink *
0x180053dd3  mov     rax, [rdi+138h]
0x180053dda  mov     [rsp+140h+var_118], rax; struct IInternetProtocol *
0x180053ddf  call    ?Initialize@COInetProt@@QEAAJPEAVCTransaction@@PEAUIServiceProvider@@KPEAUIUnknown@@PEAUIInternetProtocol@@PEAUIInternetProtocolSink@@PEAUIUri@@@Z; COInetProt::Initialize(CTransaction *,IServiceProvider *,ulong,IUnknown *,IInternetProtocol *,IInternetProtocolSink *,IUri *)
0x180053de4  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180053deb  mov     rcx, r8
0x180053dee  xchg    ax, ax
0x180053df0  inc     rcx
0x180053df3  cmp     [r14+rcx*2], si
0x180053df8  jnz     short loc_180053DF0
0x180053dfa  mov     esi, [rdi+108h]
0x180053e00  mov     eax, 2
0x180053e05  add     esi, 18h
0x180053e08  add     esi, ecx
0x180053e0a  mul     rsi
0x180053e0d  cmovb   rax, r8
0x180053e11  mov     rcx, rax; Size
  ... truncated ...
```
