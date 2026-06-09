# CTransaction::DispatchReport(tagBINDSTATUS,ulong,ulong,ulong,ushort const *,ulong,long)

- ea: `0x18004aab0`
- end: `0x18004b3fa`
- name: `?DispatchReport@CTransaction@@QEAAJW4tagBINDSTATUS@@KKKPEBGKJ@Z`
- size: `2378`
- prototype: `__int64 __fastcall(CTransaction *this, unsigned int, unsigned int, unsigned int, unsigned int, WCHAR *pwzURI, unsigned int, int)`
- caller_count: `9`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180029860`
- `0x180029b70`
- `0x18002af20`
- `0x180049e90`
- `0x18004a0a0`
- `0x18004a380`
- `0x18004a690`
- `0x18004b600`
- `0x18004bec4`

## callees

- `0x18001db50`
- `0x180023130`
- `0x180028410`
- `0x180032708`
- `0x18003564c`
- `0x18003e100`
- `0x18004aab0`
- `0x180061ed8`
- `0x1800666d4`
- `0x1800668e4`
- `0x18006cba8`
- `0x180077b14`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18004aba4`
- `msvcrt!swprintf_s` at `0x18004aba4`
- `iertutil!CreateUri` at `0x18004ad0b`
- `iertutil!CreateUri` at `0x18004adef`
- `iertutil!CreateUri` at `0x18004ad0b`
- `iertutil!CreateUri` at `0x18004adef`
- `iertutil!__imp_IECompatLogEvent` at `0x18004b0d9`
- `iertutil!__imp_IECompatLogEvent` at `0x18004b0d9`
- `iertutil!__imp_?IECompatLoggingEnabledInternal@@YAHXZ` at `0x18004b06a`
- `iertutil!__imp_?IECompatLoggingEnabledInternal@@YAHXZ` at `0x18004b06a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b302`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b327`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b302`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b327`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b2e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b2e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b0e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b1a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b1f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b231`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b27c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b0e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b1a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b1f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b231`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b27c`

## string_xrefs

- `0x18004afb3`: `Class Install Handler `

## pseudocode

```c
__int64 __fastcall CTransaction::DispatchReport(
        CTransaction *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        WCHAR *pwzURI,
        unsigned int a7,
        int a8)
{
  WCHAR *v9; // r14
  int v13; // ecx
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
  WCHAR **v40; // rbx
  WCHAR *v41; // r8
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
  unsigned int v57; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v58; // [rsp+80h] [rbp-80h] BYREF
  const wchar_t *v59; // [rsp+88h] [rbp-78h] BYREF
  struct IUnknown v60; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Buffer[40]; // [rsp+A0h] [rbp-60h] BYREF

  v9 = pwzURI;
  if ( (unsigned int)dword_180166000 > 5 )
  {
    v13 = qword_180166018;
    if ( (qword_180166010 & 0x20) != 0 && (qword_180166018 & 0x20) == qword_180166018 )
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
        v17 = pwzURI;
      }
      v59 = v17;
      LODWORD(ppURI) = a2;
      v60.lpVtbl = (struct IUnknownVtbl *)this;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)byte_18015298B,
        a3,
        a4,
        (__int64)&v60,
        (__int64)&ppURI,
        (__int64)&v59,
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
          ((void (__fastcall *)(struct IInternetProtocolSink *, __int64, WCHAR *))v52->lpVtbl->ReportProgress)(
            v52,
            v21,
            pwzURI);
LABEL_21:
          MimeFilter = ((__int64 (__fastcall *)(struct IInternetProtocolSink *, _QWORD, _QWORD, _QWORD))v52->lpVtbl->ReportData)(
                         v52,
                         a3,
                         a4,
                         a5);
          break;
        case 0xDu:
          CTransaction::_TryLoadMimeFilter(this, pwzURI);
          if ( *((_QWORD *)this + 66) )
            v9 = (WCHAR *)*((_QWORD *)this + 66);
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
          if ( (v39 & 0x50) != 0x50 || (v40 = (WCHAR **)((char *)this + 512), !*((_QWORD *)this + 64)) )
          {
            v40 = (WCHAR **)((char *)this + 512);
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
            MimeFilter = ((__int64 (__fastcall *)(struct IInternetProtocolSink *, _QWORD, _QWORD, WCHAR *))v29->lpVtbl->ReportResult)(
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
          MimeFilter = (*(__int64 (__fastcall **)(CTransaction *, WCHAR *))(*(_QWORD *)this + 64LL))(this, pwzURI);
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
          MimeFilter = ((__int64 (__fastcall *)(struct IInternetProtocolSink *, __int64, WCHAR *))v52->lpVtbl->ReportProgress)(
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
0x18004aab0  push    rbp
0x18004aab2  push    rbx
0x18004aab3  push    rsi
0x18004aab4  push    rdi
0x18004aab5  push    r12
0x18004aab7  push    r13
0x18004aab9  push    r14
0x18004aabb  push    r15
0x18004aabd  lea     rbp, [rsp-8]
0x18004aac2  sub     rsp, 108h
0x18004aac9  mov     rax, cs:__security_cookie
0x18004aad0  xor     rax, rsp
0x18004aad3  mov     [rbp+40h+var_50], rax
0x18004aad7  mov     eax, cs:dword_180166000
0x18004aadd  mov     r13d, r9d
0x18004aae0  mov     r14, [rbp+40h+pwzURI]
0x18004aae4  mov     r12d, r8d
0x18004aae7  mov     r15d, [rbp+40h+arg_38]
0x18004aaee  mov     ebx, edx
0x18004aaf0  mov     rdi, rcx
0x18004aaf3  cmp     eax, 5
0x18004aaf6  jbe     loc_18004AC26
0x18004aafc  mov     rcx, cs:qword_180166018
0x18004ab03  mov     rax, cs:qword_180166010
0x18004ab0a  test    al, 20h
0x18004ab0c  jz      loc_18004AC26
0x18004ab12  mov     rax, rcx
0x18004ab15  and     eax, 20h
0x18004ab18  cmp     rax, rcx
0x18004ab1b  jnz     loc_18004AC26
0x18004ab21  mov     eax, [rbp+40h+arg_30]
0x18004ab27  mov     [rsp+140h+var_D0], eax
0x18004ab2b  mov     eax, [rbp+40h+arg_20]
0x18004ab2e  mov     [rsp+140h+var_C8], eax
0x18004ab32  mov     [rsp+140h+var_CC], r15d
0x18004ab37  mov     [rsp+140h+var_C4], r9d
0x18004ab3c  mov     [rbp+40h+var_C0], r8d
0x18004ab40  cmp     edx, 49h ; 'I'
0x18004ab43  jnz     short loc_18004ABBE
0x18004ab45  movzx   eax, word ptr [r14]
0x18004ab49  mov     r8, 0FFFEFFFEFFFEFFFEh
0x18004ab53  mov     ecx, eax
0x18004ab55  shl     rcx, 0Fh
0x18004ab59  or      rcx, rax
0x18004ab5c  mov     r9, rcx
0x18004ab5f  shl     r9, 1Eh
0x18004ab63  or      r9, rcx
0x18004ab66  movzx   ecx, word ptr [r14+0Eh]
0x18004ab6b  mov     rdx, r9
0x18004ab6e  mov     dword ptr [rsp+140h+var_118], ecx
0x18004ab72  xor     rdx, [r14+6]
0x18004ab76  lea     rcx, [rbp+40h+Buffer]; Buffer
0x18004ab7a  and     rdx, r8
0x18004ab7d  lea     r8, a0xLx0xLlx0xX; "0x%lX;0x%llX;0x%X"
0x18004ab84  xor     rdx, r9
0x18004ab87  shr     r9, 4
0x18004ab8b  xor     r9d, [r14+2]
0x18004ab8f  and     r9d, 10001h
0x18004ab96  mov     [rsp+140h+var_120], rdx
0x18004ab9b  xor     r9d, [r14+2]
0x18004ab9f  mov     edx, 25h ; '%'; BufferCount
0x18004aba4  call    cs:__imp_swprintf_s
0x18004abab  nop     dword ptr [rax+rax+00h]
0x18004abb0  xor     ecx, ecx
0x18004abb2  lea     rdx, [rbp+40h+Buffer]
0x18004abb6  test    eax, eax
0x18004abb8  cmovs   rdx, rcx
0x18004abbc  jmp     short loc_18004ABC1
0x18004abbe  mov     rdx, r14
0x18004abc1  lea     rax, [rsp+140h+var_D0]
0x18004abc6  mov     [rbp+40h+var_B8], rdx
0x18004abca  mov     [rsp+140h+var_E8], rax
0x18004abcf  lea     rdx, byte_18015298B
0x18004abd6  lea     rax, [rsp+140h+var_CC]
0x18004abdb  mov     dword ptr [rsp+140h+ppURI], ebx
0x18004abdf  mov     [rsp+140h+var_F0], rax
0x18004abe4  lea     rax, [rsp+140h+var_C8]
0x18004abe9  mov     [rsp+140h+var_F8], rax
0x18004abee  lea     rax, [rsp+140h+var_C4]
0x18004abf3  mov     [rsp+140h+var_100], rax
0x18004abf8  lea     rax, [rbp+40h+var_C0]
0x18004abfc  mov     [rsp+140h+var_108], rax
0x18004ac01  lea     rax, [rbp+40h+var_B8]
0x18004ac05  mov     [rsp+140h+var_110], rax
0x18004ac0a  lea     rax, [rsp+140h+ppURI]
0x18004ac0f  mov     [rsp+140h+var_118], rax
0x18004ac14  lea     rax, [rbp+40h+var_B0]
0x18004ac18  mov     [rsp+140h+var_120], rax; struct IUnknown *
0x18004ac1d  mov     [rbp+40h+var_B0.lpVtbl], rdi
0x18004ac21  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004ac26  movzx   eax, byte ptr [rdi+1B9h]
0x18004ac2d  xor     esi, esi
0x18004ac2f  mov     [rsp+140h+var_E0], rsi
0x18004ac34  test    al, 2
0x18004ac36  jnz     loc_18004B2DB; jumptable 000000018004AC91 case 72
0x18004ac3c  mov     rax, [rdi]
0x18004ac3f  lea     rdx, [rsp+140h+var_E0]
0x18004ac44  mov     rcx, rdi
0x18004ac47  mov     rax, [rax+0B8h]
0x18004ac4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac53  test    eax, eax
0x18004ac55  jnz     loc_18004B2AC
0x18004ac5b  cmp     dword ptr [rdi+1B0h], 2
0x18004ac62  jnz     short loc_18004AC6A
0x18004ac64  mov     [rdi+1B0h], esi
0x18004ac6a  lea     eax, [rbx-3]; switch 70 cases
0x18004ac6d  cmp     eax, 45h
0x18004ac70  ja      def_18004AC91; jumptable 000000018004AC91 default case, cases 7-12,15-21,24,25,27-32,34-55,57,59,60,62-64,66-71
0x18004ac76  lea     rdx, __ImageBase
0x18004ac7d  cdqe
0x18004ac7f  movzx   eax, ds:(byte_18004B3B4 - 180000000h)[rdx+rax]
0x18004ac87  mov     ecx, ds:(jpt_18004AC91 - 180000000h)[rdx+rax*4]
0x18004ac8e  add     rcx, rdx
0x18004ac91  jmp     rcx; switch jump
0x18004ac97  test    byte ptr [rdi+2F4h], 40h; jumptable 000000018004AC91 case 4
0x18004ac9e  jz      short loc_18004ACC8
0x18004aca0  mov     edx, ebx
0x18004aca2  jmp     short loc_18004ACB4
0x18004aca4  cmp     ebx, 6; jumptable 000000018004AC91 cases 5,6
0x18004aca7  jnz     short loc_18004ACC8
0x18004aca9  test    byte ptr [rdi+2F4h], 40h
0x18004acb0  jz      short loc_18004ACC8
0x18004acb2  mov     edx, ebx
0x18004acb4  mov     rcx, [rsp+140h+var_E0]
0x18004acb9  mov     r8, r14
0x18004acbc  mov     rax, [rcx]
0x18004acbf  mov     rax, [rax+20h]
0x18004acc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004acc8  mov     rcx, [rsp+140h+var_E0]
0x18004accd  mov     r8d, r13d
0x18004acd0  mov     r9d, [rbp+40h+arg_20]
0x18004acd4  mov     edx, r12d
0x18004acd7  mov     rax, [rcx]
0x18004acda  mov     rax, [rax+28h]
0x18004acde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ace3  mov     esi, eax
0x18004ace5  jmp     loc_18004B2DB; jumptable 000000018004AC91 case 72
0x18004acea  mov     edx, 3002B85h; jumptable 000000018004AC91 case 3
0x18004acef  mov     [rsp+140h+ppURI], rsi
0x18004acf4  mov     ecx, 3002B80h; unsigned int
0x18004acf9  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x18004acfe  mov     edx, eax; dwFlags
0x18004ad00  lea     r9, [rsp+140h+ppURI]; ppURI
0x18004ad05  mov     rcx, r14; pwzURI
0x18004ad08  xor     r8d, r8d; dwReserved
0x18004ad0b  call    cs:__imp_CreateUri
0x18004ad12  nop     dword ptr [rax+rax+00h]
0x18004ad17  mov     esi, eax
0x18004ad19  test    eax, eax
0x18004ad1b  js      short loc_18004AD5F
0x18004ad1d  mov     rdx, [rsp+140h+ppURI]; struct IUri *
0x18004ad22  mov     rcx, rdi; this
0x18004ad25  call    ?SecurityCheckOnRedirect@CTransaction@@QEAAJPEAUIUri@@@Z; CTransaction::SecurityCheckOnRedirect(IUri *)
0x18004ad2a  mov     esi, eax
0x18004ad2c  test    eax, eax
0x18004ad2e  js      short loc_18004AD5F
0x18004ad30  mov     rdx, [rsp+140h+ppURI]; struct IUri *
0x18004ad35  mov     rcx, rdi; this
0x18004ad38  call    ?SetRedirectIUri@CTransaction@@QEAAJPEAUIUri@@@Z; CTransaction::SetRedirectIUri(IUri *)
0x18004ad3d  mov     esi, eax
0x18004ad3f  test    eax, eax
0x18004ad41  js      short loc_18004AD5F
0x18004ad43  mov     rcx, [rsp+140h+var_E0]
0x18004ad48  mov     edx, ebx
0x18004ad4a  mov     r8, [rdi+0C8h]
0x18004ad51  mov     rax, [rcx]
0x18004ad54  mov     rax, [rax+20h]
0x18004ad58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad5d  mov     esi, eax
0x18004ad5f  test    esi, esi
0x18004ad61  jz      short loc_18004AD99
0x18004ad63  cmp     esi, 8000000Ah
0x18004ad69  jz      short loc_18004AD99
0x18004ad6b  movzx   eax, byte ptr [rdi+1B9h]
0x18004ad72  test    al, 1
0x18004ad74  jnz     short loc_18004AD99
0x18004ad76  mov     rcx, [rsp+140h+var_E0]
0x18004ad7b  or      al, 1
0x18004ad7d  mov     [rdi+1B9h], al
0x18004ad83  xor     r9d, r9d
0x18004ad86  xor     r8d, r8d
0x18004ad89  mov     edx, esi
0x18004ad8b  mov     rax, [rcx]
0x18004ad8e  mov     rax, [rax+30h]
0x18004ad92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad97  mov     esi, eax
0x18004ad99  mov     rcx, [rsp+140h+ppURI]
0x18004ad9e  test    rcx, rcx
0x18004ada1  jz      loc_18004B2DB; jumptable 000000018004AC91 case 72
0x18004ada7  mov     rax, [rcx]
0x18004adaa  mov     rax, [rax+10h]
0x18004adae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004adb3  jmp     loc_18004B2DB; jumptable 000000018004AC91 case 72
0x18004adb8  cmp     r15d, 800C0014h; jumptable 000000018004AC91 cases 58,61
0x18004adbf  jnz     loc_18004AEF1
0x18004adc5  test    r14, r14
0x18004adc8  jz      loc_18004AEF1
0x18004adce  mov     edx, 3002B85h; unsigned int
0x18004add3  mov     [rsp+140h+ppURI], rsi
0x18004add8  mov     ecx, 3002B80h; unsigned int
0x18004addd  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x18004ade2  mov     edx, eax; dwFlags
0x18004ade4  lea     r9, [rsp+140h+ppURI]; ppURI
0x18004ade9  mov     rcx, r14; pwzURI
0x18004adec  xor     r8d, r8d; dwReserved
0x18004adef  call    cs:__imp_CreateUri
0x18004adf6  nop     dword ptr [rax+rax+00h]
0x18004adfb  mov     esi, eax
0x18004adfd  test    eax, eax
0x18004adff  js      loc_18004AD5F
0x18004ae05  mov     rcx, [rsp+140h+ppURI]
0x18004ae0a  lea     rdx, [rsp+140h+var_D0]
0x18004ae0f  mov     [rsp+140h+var_D0], 0
0x18004ae17  mov     rax, [rcx]
0x18004ae1a  mov     rax, [rax+0C0h]
0x18004ae21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae26  mov     esi, eax
0x18004ae28  mov     eax, [rsp+140h+var_D0]
0x18004ae2c  cmp     eax, 2
0x18004ae2f  jz      short loc_18004AE36
0x18004ae31  cmp     eax, 0Bh
0x18004ae34  jnz     short loc_18004AE5F
0x18004ae36  mov     rax, [rdi]
0x18004ae39  mov     rcx, rdi
0x18004ae3c  inc     dword ptr [rdi+1BCh]
0x18004ae42  mov     ebx, [rdi+1BCh]
0x18004ae48  mov     rax, [rax+48h]
0x18004ae4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae51  cmp     ebx, eax
0x18004ae53  jbe     short loc_18004AE5F
0x18004ae55  mov     esi, 800C0014h
0x18004ae5a  jmp     loc_18004AD63
0x18004ae5f  test    esi, esi
0x18004ae61  js      loc_18004AD63
0x18004ae67  mov     rax, [rdi]
0x18004ae6a  mov     rdx, r14
0x18004ae6d  mov     rcx, rdi
0x18004ae70  mov     rax, [rax+40h]
0x18004ae74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae79  mov     esi, eax
0x18004ae7b  test    eax, eax
0x18004ae7d  js      loc_18004AD5F
0x18004ae83  mov     rdx, [rsp+140h+ppURI]; struct IUri *
0x18004ae88  mov     rcx, rdi; this
0x18004ae8b  call    ?SecurityCheckOnRedirect@CTransaction@@QEAAJPEAUIUri@@@Z; CTransaction::SecurityCheckOnRedirect(IUri *)
0x18004ae90  mov     esi, eax
0x18004ae92  test    eax, eax
0x18004ae94  js      loc_18004AD5F
0x18004ae9a  mov     rdx, [rsp+140h+ppURI]; struct IUri *
0x18004ae9f  mov     rcx, rdi; this
0x18004aea2  call    ?SetRedirectIUri@CTransaction@@QEAAJPEAUIUri@@@Z; CTransaction::SetRedirectIUri(IUri *)
0x18004aea7  mov     esi, eax
0x18004aea9  test    eax, eax
0x18004aeab  js      loc_18004AD5F
0x18004aeb1  mov     rcx, [rsp+140h+var_E0]
0x18004aeb6  mov     edx, 3
0x18004aebb  mov     r8, [rdi+0C8h]
0x18004aec2  mov     rax, [rcx]
0x18004aec5  mov     rax, [rax+20h]
0x18004aec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aece  mov     esi, eax
0x18004aed0  test    eax, eax
0x18004aed2  js      loc_18004AD5F
0x18004aed8  mov     rax, [rdi]
0x18004aedb  mov     rcx, rdi
0x18004aede  mov     rdx, [rsp+140h+ppURI]
0x18004aee3  mov     rax, [rax+60h]
0x18004aee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aeec  jmp     loc_18004AD5D
0x18004aef1  mov     rcx, [rsp+140h+var_E0]
0x18004aef6  mov     r9, r14
0x18004aef9  or      byte ptr [rdi+1B9h], 1
0x18004af00  mov     r8d, [rdi+1D0h]
0x18004af07  mov     edx, [rdi+1CCh]
0x18004af0d  mov     rax, [rcx]
0x18004af10  mov     rax, [rax+30h]
0x18004af14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af19  mov     esi, eax
0x18004af1b  jmp     loc_18004B2DB; jumptable 000000018004AC91 case 72
0x18004af20  test    r14, r14; jumptable 000000018004AC91 case 23
0x18004af23  jz      loc_18004B2DB; jumptable 000000018004AC91 case 72
0x18004af29  mov     rax, [rsp+140h+var_E0]
0x18004af2e  lea     rcx, [rdi+478h]; this
0x18004af35  mov     r9d, [rdi+2F4h]; unsigned int
0x18004af3c  mov     rdx, rdi; struct CTransaction *
0x18004af3f  mov     [rsp+140h+var_108], rsi; struct IUri *
0x18004af44  mov     [rsp+140h+var_110], rax; struct IInternetProtocolSink *
0x18004af49  mov     rax, [rdi+138h]
0x18004af50  mov     [rsp+140h+var_118], rax; struct IInternetProtocol *
0x18004af55  call    ?Initialize@COInetProt@@QEAAJPEAVCTransaction@@PEAUIServiceProvider@@KPEAUIUnknown@@PEAUIInternetProtocol@@PEAUIInternetProtocolSink@@PEAUIUri@@@Z; COInetProt::Initialize(CTransaction *,IServiceProvider *,ulong,IUnknown *,IInternetProtocol *,IInternetProtocolSink *,IUri *)
0x18004af5a  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18004af61  mov     rcx, r8
0x18004af64  inc     rcx
0x18004af67  cmp     [r14+rcx*2], si
0x18004af6c  jnz     short loc_18004AF64
0x18004af6e  mov     esi, [rdi+108h]
0x18004af74  mov     eax, 2
0x18004af79  add     esi, 18h
0x18004af7c  add     esi, ecx
0x18004af7e  mul     rsi
  ... truncated ...
```
