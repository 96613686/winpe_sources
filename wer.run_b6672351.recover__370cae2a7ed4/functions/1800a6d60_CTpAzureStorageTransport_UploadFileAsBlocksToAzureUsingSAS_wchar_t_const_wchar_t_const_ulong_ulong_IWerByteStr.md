# CTpAzureStorageTransport::UploadFileAsBlocksToAzureUsingSAS(wchar_t const *,wchar_t const *,ulong,ulong,IWerByteStream *,unsigned __int64,void *,ulong &,unsigned __int64 &,ITpCallbacks *)

- ea: `0x1800a6d60`
- end: `0x1800a744d`
- name: `?UploadFileAsBlocksToAzureUsingSAS@CTpAzureStorageTransport@@CAJPEB_W0KKPEAUIWerByteStream@@_KPEAXAEAKAEA_KPEAUITpCallbacks@@@Z`
- size: `1773`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, unsigned int, unsigned int, struct IWerByteStream *, unsigned __int64, void *, unsigned int *, unsigned __int64 *, struct ITpCallbacks *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a7454`

## callees

- `0x18000cf50`
- `0x18000db80`
- `0x18000e31c`
- `0x180010280`
- `0x1800172c0`
- `0x180020680`
- `0x180026650`
- `0x18002d180`
- `0x180031944`
- `0x18003b62c`
- `0x18003e17c`
- `0x1800490c0`
- `0x18004c428`
- `0x180053300`
- `0x180053d3c`
- `0x180054568`
- `0x18009eb20`
- `0x18009ec90`
- `0x1800a663c`
- `0x1800a6670`
- `0x1800a6934`
- `0x1800a6d60`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a6ee5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a7207`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a6ee5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800a7207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a70d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a70d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7227`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpUpload` at `0x1800a7052`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpUpload` at `0x1800a737d`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpUpload` at `0x1800a7052`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpUpload` at `0x1800a737d`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpCompleteUpload` at `0x1800a7067`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpCompleteUpload` at `0x1800a7392`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpCompleteUpload` at `0x1800a7067`
- `ext-ms-win-wer-xbox-l1-1-0!XerTpCompleteUpload` at `0x1800a7392`

## string_xrefs

- `0x1800a6e80`: `%ls&comp=blocklist`
- `0x1800a6f8b`: `%ls&comp=block&blockid=%ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CTpAzureStorageTransport::UploadFileAsBlocksToAzureUsingSAS(
        const wchar_t *a1,
        const wchar_t *a2,
        int a3,
        unsigned int a4,
        struct IWerByteStream *a5,
        unsigned __int64 a6,
        void *a7,
        unsigned int *a8,
        unsigned __int64 *a9,
        struct ITpCallbacks *a10)
{
  __int128 v12; // xmm0
  __int64 v14; // rdi
  signed int PutBlockListXml; // ebx
  wchar_t *v16; // rcx
  __int64 v17; // rdx
  unsigned int v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v20[4]; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v21; // [rsp+58h] [rbp-A8h]
  struct ITpCallbacks *v22; // [rsp+60h] [rbp-A0h]
  void *v23; // [rsp+68h] [rbp-98h]
  __int128 v24; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+80h] [rbp-80h]
  void **v26; // [rsp+88h] [rbp-78h] BYREF
  __int128 v27; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+A0h] [rbp-60h]
  int v29; // [rsp+A8h] [rbp-58h]
  const wchar_t *v30; // [rsp+B0h] [rbp-50h]
  void *v31; // [rsp+B8h] [rbp-48h] BYREF
  void *v32; // [rsp+D8h] [rbp-28h] BYREF
  int v33; // [rsp+E0h] [rbp-20h]
  _QWORD v34[4]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v35[4]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v36[4]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v37[5]; // [rsp+158h] [rbp+58h] BYREF
  _QWORD v38[3]; // [rsp+180h] [rbp+80h] BYREF
  __int16 v39; // [rsp+198h] [rbp+98h]
  __int128 *v40; // [rsp+1A0h] [rbp+A0h]
  int v41; // [rsp+1A8h] [rbp+A8h]
  BOOL v42; // [rsp+1B0h] [rbp+B0h]
  unsigned __int64 v43; // [rsp+1B8h] [rbp+B8h]
  __int64 v44; // [rsp+1C0h] [rbp+C0h]
  int v45; // [rsp+1C8h] [rbp+C8h]
  __int64 v46; // [rsp+1D0h] [rbp+D0h]
  void *v47; // [rsp+1D8h] [rbp+D8h]
  struct ITpCallbacks *v48; // [rsp+1E8h] [rbp+E8h]
  _QWORD v49[3]; // [rsp+230h] [rbp+130h] BYREF
  __int16 v50; // [rsp+248h] [rbp+148h]
  __int128 *v51; // [rsp+250h] [rbp+150h]
  int v52; // [rsp+258h] [rbp+158h]
  BOOL v53; // [rsp+260h] [rbp+160h]
  int v54; // [rsp+278h] [rbp+178h]
  __int64 v55; // [rsp+280h] [rbp+180h]
  void *v56; // [rsp+288h] [rbp+188h]
  struct ITpCallbacks *v57; // [rsp+298h] [rbp+198h]
  struct _SYSTEMTIME SystemTime; // [rsp+2E0h] [rbp+1E0h] BYREF

  v19 = a4;
  v30 = a2;
  v21 = a1;
  v23 = a7;
  v22 = a10;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v20);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v31);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v37);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v34);
  v12 = 0;
  SystemTime = 0;
  *(double *)&v12 = utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::basic_string<char,utl::char_traits<char>,utl::allocator<char>>(&v32);
  v26 = &CMemoryByteStream::`vftable';
  v27 = v12;
  v28 = 0;
  v29 = 0;
  memset_0(v38, 0, 0xB0u);
  memset_0(v49, 0, 0xB0u);
  v24 = 0;
  v25 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v36);
  *a9 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v35);
  tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v35, L"%ls&comp=blocklist", a2);
  *(_QWORD *)&v24 = a10;
  while ( 1 )
  {
    if ( a6 >= (*(__int64 (__fastcall **)(struct IWerByteStream *))(*(_QWORD *)a5 + 32LL))(a5) )
    {
      PutBlockListXml = CTpAzureStorageTransport::GetPutBlockListXml(*a8, v34);
      if ( PutBlockListXml >= 0 )
      {
        PutBlockListXml = tlx::_AppendWideImpl<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,wchar_t>(
                            &v32,
                            v34[0],
                            (__int64)(v34[1] - v34[0]) >> 1);
        if ( PutBlockListXml >= 0 )
        {
          CMemoryByteStream::OpenForReadWrite((CMemoryByteStream *)&v26);
          PutBlockListXml = CMemoryByteStream::Write((CMemoryByteStream *)&v26, v32, v33 - (_DWORD)v32, &v19, 0);
          if ( PutBlockListXml >= 0 )
          {
            GetSystemTime(&SystemTime);
            if ( (int)CTpAzureStorageTransport::GetInternetTime(&SystemTime, &v31) >= 0 )
            {
              *((_QWORD *)&v24 + 1) = (unsigned int)v28;
              LOBYTE(v25) = 0;
              v20[1] = v20[0];
              *(_WORD *)v20[0] = 0;
              tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                v20,
                L"Content-Length: %llu\n",
                (unsigned int)v28);
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                v20,
                L"x-ms-version: 2017-04-17\n");
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v20, L"x-ms-date: ");
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v20, v31);
              utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(v20, 10);
              v49[0] = v21;
              v49[1] = v35[0];
              v49[2] = &v26;
              v50 = 0;
              v51 = &v24;
              v52 = 1;
              v53 = (a3 & 1) == 0;
              v54 = a3;
              v55 = v20[0];
              v57 = v22;
              v56 = v23;
              if ( (unsigned __int8)IsXerGetMachineIdPresent() )
              {
                PutBlockListXml = XerTpUpload(v49);
                XerTpCompleteUpload(v38);
              }
              else
              {
                PutBlockListXml = TpUpload((struct _WER_TP_UPLOAD_STATE *)v49, 0);
                TpCompleteUpload((struct _WER_TP_UPLOAD_STATE *)v38);
              }
              if ( PutBlockListXml >= 0 )
              {
                PutBlockListXml = 0;
              }
              else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  24,
                  WPP_2630288230103b96da97e4a7a3753ae6_Traceguids,
                  (unsigned int)PutBlockListXml);
              }
            }
            else
            {
              PutBlockListXml = GetLastError();
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                v17 = 23;
                goto LABEL_21;
              }
            }
          }
          else
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v17 = 22;
              goto LABEL_21;
            }
          }
        }
        else
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v17 = 21;
            goto LABEL_21;
          }
        }
      }
      else
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v17 = 20;
          goto LABEL_21;
        }
      }
      goto LABEL_46;
    }
    v14 = v19;
    if ( v19 + a6 >= (*(__int64 (__fastcall **)(struct IWerByteStream *))(*(_QWORD *)a5 + 32LL))(a5) )
      v14 = (*(__int64 (__fastcall **)(struct IWerByteStream *))(*(_QWORD *)a5 + 32LL))(a5) - a6;
    GetSystemTime(&SystemTime);
    if ( (int)CTpAzureStorageTransport::GetInternetTime(&SystemTime, &v31) < 0 )
      break;
    tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v20, L"Content-Length: %llu\n", v14);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
      v20,
      L"x-ms-version: 2017-04-17\n");
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v20, L"x-ms-date: ");
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(v20, v31);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(v20, 10);
    PutBlockListXml = CTpAzureStorageTransport::GetBlockId(*a8 + 1, 1, v36);
    if ( PutBlockListXml < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_46;
      v17 = 18;
LABEL_21:
      WPP_SF_d(
        *((_QWORD *)v16 + 2),
        v17,
        WPP_2630288230103b96da97e4a7a3753ae6_Traceguids,
        (unsigned int)PutBlockListXml);
      goto LABEL_46;
    }
    tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
      v37,
      L"%ls&comp=block&blockid=%ls",
      v30,
      v36[0]);
    *((_QWORD *)&v24 + 1) = v14;
    LOBYTE(v25) = 0;
    v38[0] = v21;
    v38[1] = v37[0];
    v38[2] = a5;
    v39 = 0;
    v40 = &v24;
    v41 = 1;
    v42 = (a3 & 1) == 0;
    v45 = a3;
    v46 = v20[0];
    v43 = a6;
    v44 = v14;
    v48 = v22;
    v47 = v23;
    if ( (unsigned __int8)IsXerGetMachineIdPresent() )
    {
      PutBlockListXml = XerTpUpload(v38);
      XerTpCompleteUpload(v38);
    }
    else
    {
      PutBlockListXml = TpUpload((struct _WER_TP_UPLOAD_STATE *)v38, 0);
      TpCompleteUpload((struct _WER_TP_UPLOAD_STATE *)v38);
    }
    if ( PutBlockListXml < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_46;
      v17 = 19;
      goto LABEL_21;
    }
    ++*a8;
    *a9 += v14;
    a6 += v14;
  }
  PutBlockListXml = GetLastError();
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v17 = 17;
    goto LABEL_21;
  }
LABEL_46:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v35);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v36);
  CMemoryByteStream::~CMemoryByteStream((CMemoryByteStream *)&v26);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v32);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v34);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v37);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v31);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v20);
  return (unsigned int)PutBlockListXml;
}

```

## disassembly

```asm
0x1800a6d60  push    rbp
0x1800a6d62  push    rbx
0x1800a6d63  push    rsi
0x1800a6d64  push    rdi
0x1800a6d65  push    r12
0x1800a6d67  push    r13
0x1800a6d69  push    r14
0x1800a6d6b  push    r15
0x1800a6d6d  lea     rbp, [rsp-208h]
0x1800a6d75  sub     rsp, 308h
0x1800a6d7c  mov     rax, cs:__security_cookie
0x1800a6d83  xor     rax, rsp
0x1800a6d86  mov     [rbp+240h+var_50], rax
0x1800a6d8d  mov     [rsp+340h+var_310], r9d
0x1800a6d92  mov     r13d, r8d
0x1800a6d95  mov     rbx, rdx
0x1800a6d98  mov     [rbp+240h+var_290], rdx
0x1800a6d9c  mov     [rsp+340h+var_2E8], rcx
0x1800a6da1  mov     rsi, [rbp+240h+arg_20]
0x1800a6da8  mov     rax, [rbp+240h+arg_30]
0x1800a6daf  mov     [rsp+340h+var_2D8], rax
0x1800a6db4  mov     r15, [rbp+240h+arg_38]
0x1800a6dbb  mov     r12, [rbp+240h+arg_40]
0x1800a6dc2  mov     rdi, [rbp+240h+arg_48]
0x1800a6dc9  mov     [rsp+340h+var_2E0], rdi
0x1800a6dce  lea     rcx, [rsp+340h+var_308]; void *
0x1800a6dd3  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a6dd8  nop
0x1800a6dd9  lea     rcx, [rbp+240h+var_288]; void *
0x1800a6ddd  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a6de2  nop
0x1800a6de3  lea     rcx, [rbp+240h+var_1E8]; void *
0x1800a6de7  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a6dec  nop
0x1800a6ded  lea     rcx, [rbp+240h+var_248]; void *
0x1800a6df1  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a6df6  nop
0x1800a6df7  xorps   xmm0, xmm0
0x1800a6dfa  movups  xmmword ptr [rbp+240h+SystemTime.wYear], xmm0
0x1800a6e01  lea     rcx, [rbp+240h+var_268]
0x1800a6e05  call    ??0?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@QEAA@XZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::basic_string<char,utl::char_traits<char>,utl::allocator<char>>(void)
0x1800a6e0a  nop
0x1800a6e0b  lea     rax, ??_7CMemoryByteStream@@6B@; const CMemoryByteStream::`vftable'
0x1800a6e12  mov     [rbp+240h+var_2B8], rax
0x1800a6e16  movdqu  [rbp+240h+var_2B0], xmm0
0x1800a6e1b  xor     eax, eax
0x1800a6e1d  mov     [rbp+240h+var_2A0], rax
0x1800a6e21  mov     [rbp+240h+var_298], eax
0x1800a6e24  mov     r14d, 0B0h
0x1800a6e2a  mov     r8d, r14d; Size
0x1800a6e2d  xor     edx, edx; Val
0x1800a6e2f  lea     rcx, [rbp+240h+var_1C0]; void *
0x1800a6e36  call    memset_0
0x1800a6e3b  mov     r8d, r14d; Size
0x1800a6e3e  xor     edx, edx; Val
0x1800a6e40  lea     rcx, [rbp+240h+var_110]; void *
0x1800a6e47  call    memset_0
0x1800a6e4c  xorps   xmm0, xmm0
0x1800a6e4f  xor     eax, eax
0x1800a6e51  movups  [rsp+340h+var_2D0], xmm0
0x1800a6e56  mov     [rbp+240h+var_2C0], rax
0x1800a6e5a  mov     r14, [rbp+240h+arg_28]
0x1800a6e61  lea     rcx, [rbp+240h+var_208]; void *
0x1800a6e65  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a6e6a  nop
0x1800a6e6b  mov     qword ptr [r12], 0
0x1800a6e73  lea     rcx, [rbp+240h+var_228]; void *
0x1800a6e77  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800a6e7c  nop
0x1800a6e7d  mov     r8, rbx
0x1800a6e80  lea     rdx, aLsCompBlocklis; "%ls&comp=blocklist"
0x1800a6e87  lea     rcx, [rbp+240h+var_228]
0x1800a6e8b  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800a6e90  mov     qword ptr [rsp+340h+var_2D0], rdi
0x1800a6e95  mov     rax, [rsi]
0x1800a6e98  mov     rcx, rsi
0x1800a6e9b  mov     rax, [rax+20h]
0x1800a6e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6ea4  cmp     r14, rax
0x1800a6ea7  jnb     loc_1800A7122
0x1800a6ead  mov     edi, [rsp+340h+var_310]
0x1800a6eb1  mov     rax, [rsi]
0x1800a6eb4  mov     rcx, rsi
0x1800a6eb7  mov     rax, [rax+20h]
0x1800a6ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6ec0  lea     rcx, [rdi+r14]
0x1800a6ec4  cmp     rcx, rax
0x1800a6ec7  jb      short loc_1800A6EDE
0x1800a6ec9  mov     rax, [rsi]
0x1800a6ecc  mov     rcx, rsi
0x1800a6ecf  mov     rax, [rax+20h]
0x1800a6ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6ed8  mov     rdi, rax
0x1800a6edb  sub     rdi, r14
0x1800a6ede  lea     rcx, [rbp+240h+SystemTime]; lpSystemTime
0x1800a6ee5  call    cs:__imp_GetSystemTime
0x1800a6eec  nop     dword ptr [rax+rax+00h]
0x1800a6ef1  lea     rdx, [rbp+240h+var_288]
0x1800a6ef5  lea     rcx, [rbp+240h+SystemTime]
0x1800a6efc  call    ?GetInternetTime@CTpAzureStorageTransport@@CAJAEBU_SYSTEMTIME@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpAzureStorageTransport::GetInternetTime(_SYSTEMTIME const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800a6f01  test    eax, eax
0x1800a6f03  js      loc_1800A70D6
0x1800a6f09  mov     r8, rdi
0x1800a6f0c  lea     rdx, aContentLengthL; "Content-Length: %llu\n"
0x1800a6f13  lea     rcx, [rsp+340h+var_308]
0x1800a6f18  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800a6f1d  lea     rdx, aXMsVersion2017; "x-ms-version: 2017-04-17\n"
0x1800a6f24  lea     rcx, [rsp+340h+var_308]
0x1800a6f29  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a6f2e  lea     rdx, aXMsDate; "x-ms-date: "
0x1800a6f35  lea     rcx, [rsp+340h+var_308]
0x1800a6f3a  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a6f3f  mov     r8, [rbp+240h+var_280]
0x1800a6f43  mov     rdx, [rbp+240h+var_288]
0x1800a6f47  sub     r8, rdx
0x1800a6f4a  sar     r8, 1
0x1800a6f4d  lea     rcx, [rsp+340h+var_308]
0x1800a6f52  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1800a6f57  mov     edx, 0Ah
0x1800a6f5c  lea     rcx, [rsp+340h+var_308]
0x1800a6f61  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x1800a6f66  mov     ecx, [r15]
0x1800a6f69  inc     ecx
0x1800a6f6b  lea     r8, [rbp+240h+var_208]
0x1800a6f6f  mov     edx, 1
0x1800a6f74  call    ?GetBlockId@CTpAzureStorageTransport@@CAJKHPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpAzureStorageTransport::GetBlockId(ulong,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800a6f79  mov     ebx, eax
0x1800a6f7b  test    eax, eax
0x1800a6f7d  js      loc_1800A70AE
0x1800a6f83  mov     r9, [rbp+240h+var_208]
0x1800a6f87  mov     r8, [rbp+240h+var_290]
0x1800a6f8b  lea     rdx, aLsCompBlockBlo; "%ls&comp=block&blockid=%ls"
0x1800a6f92  lea     rcx, [rbp+240h+var_1E8]
0x1800a6f96  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800a6f9b  mov     qword ptr [rsp+340h+var_2D0+8], rdi
0x1800a6fa0  mov     byte ptr [rbp+240h+var_2C0], 0
0x1800a6fa4  mov     rax, [rsp+340h+var_2E8]
0x1800a6fa9  mov     [rbp+240h+var_1C0], rax
0x1800a6fb0  mov     rax, [rbp+240h+var_1E8]
0x1800a6fb4  mov     [rbp+240h+var_1B8], rax
0x1800a6fbb  mov     [rbp+240h+var_1B0], rsi
0x1800a6fc2  xor     eax, eax
0x1800a6fc4  mov     [rbp+240h+var_1A8], ax
0x1800a6fcb  lea     rax, [rsp+340h+var_2D0]
0x1800a6fd0  mov     [rbp+240h+var_1A0], rax
0x1800a6fd7  mov     [rbp+240h+var_198], 1
0x1800a6fe1  mov     al, r13b
0x1800a6fe4  not     al
0x1800a6fe6  movzx   ecx, al
0x1800a6fe9  and     ecx, 1
0x1800a6fec  mov     [rbp+240h+var_190], ecx
0x1800a6ff2  mov     [rbp+240h+var_178], r13d
0x1800a6ff9  mov     rax, [rsp+340h+var_308]
0x1800a6ffe  mov     [rbp+240h+var_170], rax
0x1800a7005  mov     [rbp+240h+var_188], r14
0x1800a700c  mov     [rbp+240h+var_180], rdi
0x1800a7013  mov     rax, [rsp+340h+var_2E0]
0x1800a7018  mov     [rbp+240h+var_158], rax
0x1800a701f  mov     rax, [rsp+340h+var_2D8]
0x1800a7024  mov     [rbp+240h+var_168], rax
0x1800a702b  call    IsXerGetMachineIdPresent
0x1800a7030  lea     rcx, [rbp+240h+var_1C0]; struct _WER_TP_UPLOAD_STATE *
0x1800a7037  test    al, al
0x1800a7039  jnz     short loc_1800A7052
0x1800a703b  xor     edx, edx; struct WINHTTP_TIMEOUTS *
0x1800a703d  call    ?TpUpload@@YAJPEAU_WER_TP_UPLOAD_STATE@@PEAUWINHTTP_TIMEOUTS@@@Z; TpUpload(_WER_TP_UPLOAD_STATE *,WINHTTP_TIMEOUTS *)
0x1800a7042  mov     ebx, eax
0x1800a7044  lea     rcx, [rbp+240h+var_1C0]; struct _WER_TP_UPLOAD_STATE *
0x1800a704b  call    ?TpCompleteUpload@@YAXPEAU_WER_TP_UPLOAD_STATE@@@Z; TpCompleteUpload(_WER_TP_UPLOAD_STATE *)
0x1800a7050  jmp     short loc_1800A7073
0x1800a7052  call    cs:__imp_XerTpUpload
0x1800a7059  nop     dword ptr [rax+rax+00h]
0x1800a705e  mov     ebx, eax
0x1800a7060  lea     rcx, [rbp+240h+var_1C0]
0x1800a7067  call    cs:__imp_XerTpCompleteUpload
0x1800a706e  nop     dword ptr [rax+rax+00h]
0x1800a7073  test    ebx, ebx
0x1800a7075  js      short loc_1800A7086
0x1800a7077  inc     dword ptr [r15]
0x1800a707a  add     [r12], rdi
0x1800a707e  add     r14, rdi
0x1800a7081  jmp     loc_1800A6E95
0x1800a7086  lea     rax, WPP_GLOBAL_Control
0x1800a708d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7094  cmp     rcx, rax
0x1800a7097  jz      loc_1800A73D7
0x1800a709d  test    byte ptr [rcx+1Ch], 4
0x1800a70a1  jz      loc_1800A73D7
0x1800a70a7  mov     edx, 13h
0x1800a70ac  jmp     short loc_1800A710A
0x1800a70ae  lea     rax, WPP_GLOBAL_Control
0x1800a70b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a70bc  cmp     rcx, rax
0x1800a70bf  jz      loc_1800A73D7
0x1800a70c5  test    byte ptr [rcx+1Ch], 1
0x1800a70c9  jz      loc_1800A73D7
0x1800a70cf  mov     edx, 12h
0x1800a70d4  jmp     short loc_1800A710A
0x1800a70d6  call    cs:__imp_GetLastError
0x1800a70dd  nop     dword ptr [rax+rax+00h]
0x1800a70e2  mov     ebx, eax
0x1800a70e4  lea     rax, WPP_GLOBAL_Control
0x1800a70eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a70f2  cmp     rcx, rax
0x1800a70f5  jz      loc_1800A73D7
0x1800a70fb  test    byte ptr [rcx+1Ch], 1
0x1800a70ff  jz      loc_1800A73D7
0x1800a7105  mov     edx, 11h
0x1800a710a  mov     r9d, ebx
0x1800a710d  lea     r8, WPP_2630288230103b96da97e4a7a3753ae6_Traceguids
0x1800a7114  mov     rcx, [rcx+10h]
0x1800a7118  call    WPP_SF_d
0x1800a711d  jmp     loc_1800A73D7
0x1800a7122  lea     rdx, [rbp+240h+var_248]
0x1800a7126  mov     ecx, [r15]
0x1800a7129  call    ?GetPutBlockListXml@CTpAzureStorageTransport@@CAJKPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpAzureStorageTransport::GetPutBlockListXml(ulong,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800a712e  mov     ebx, eax
0x1800a7130  test    eax, eax
0x1800a7132  jns     short loc_1800A715C
0x1800a7134  lea     rax, WPP_GLOBAL_Control
0x1800a713b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7142  cmp     rcx, rax
0x1800a7145  jz      loc_1800A73D7
0x1800a714b  test    byte ptr [rcx+1Ch], 1
0x1800a714f  jz      loc_1800A73D7
0x1800a7155  mov     edx, 14h
0x1800a715a  jmp     short loc_1800A710A
0x1800a715c  mov     rdx, [rbp+240h+var_248]
0x1800a7160  mov     r8, [rbp+240h+var_240]
0x1800a7164  sub     r8, rdx
0x1800a7167  sar     r8, 1
0x1800a716a  lea     rcx, [rbp+240h+var_268]
0x1800a716e  call    ??$_AppendWideImpl@V?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@_W@tlx@@YAJAEAV?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@PEB_W_KII@Z; tlx::_AppendWideImpl<utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>,wchar_t>(utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>> &,wchar_t const *,unsigned __int64,uint,uint)
0x1800a7173  mov     ebx, eax
0x1800a7175  test    eax, eax
0x1800a7177  jns     short loc_1800A71A4
0x1800a7179  lea     rax, WPP_GLOBAL_Control
0x1800a7180  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7187  cmp     rcx, rax
0x1800a718a  jz      loc_1800A73D7
0x1800a7190  test    byte ptr [rcx+1Ch], 1
0x1800a7194  jz      loc_1800A73D7
0x1800a719a  mov     edx, 15h
0x1800a719f  jmp     loc_1800A710A
0x1800a71a4  lea     rcx, [rbp+240h+var_2B8]; this
0x1800a71a8  call    ?OpenForReadWrite@CMemoryByteStream@@QEAAXXZ; CMemoryByteStream::OpenForReadWrite(void)
0x1800a71ad  mov     rdx, [rbp+240h+var_268]; void *
0x1800a71b1  mov     r8d, [rbp+240h+var_260]
0x1800a71b5  sub     r8d, edx; unsigned int
0x1800a71b8  mov     [rsp+340h+var_320], 0; void *
0x1800a71c1  lea     r9, [rsp+340h+var_310]; unsigned int *
0x1800a71c6  lea     rcx, [rbp+240h+var_2B8]; this
0x1800a71ca  call    ?Write@CMemoryByteStream@@UEAAJPEAXKPEAK0@Z; CMemoryByteStream::Write(void *,ulong,ulong *,void *)
0x1800a71cf  mov     ebx, eax
0x1800a71d1  test    eax, eax
0x1800a71d3  jns     short loc_1800A7200
0x1800a71d5  lea     rax, WPP_GLOBAL_Control
0x1800a71dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a71e3  cmp     rcx, rax
0x1800a71e6  jz      loc_1800A73D7
0x1800a71ec  test    byte ptr [rcx+1Ch], 1
0x1800a71f0  jz      loc_1800A73D7
0x1800a71f6  mov     edx, 16h
0x1800a71fb  jmp     loc_1800A710A
0x1800a7200  lea     rcx, [rbp+240h+SystemTime]; lpSystemTime
0x1800a7207  call    cs:__imp_GetSystemTime
0x1800a720e  nop     dword ptr [rax+rax+00h]
0x1800a7213  lea     rdx, [rbp+240h+var_288]
0x1800a7217  lea     rcx, [rbp+240h+SystemTime]
0x1800a721e  call    ?GetInternetTime@CTpAzureStorageTransport@@CAJAEBU_SYSTEMTIME@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpAzureStorageTransport::GetInternetTime(_SYSTEMTIME const &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800a7223  test    eax, eax
0x1800a7225  jns     short loc_1800A7260
0x1800a7227  call    cs:__imp_GetLastError
0x1800a722e  nop     dword ptr [rax+rax+00h]
0x1800a7233  mov     ebx, eax
0x1800a7235  lea     rax, WPP_GLOBAL_Control
0x1800a723c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7243  cmp     rcx, rax
0x1800a7246  jz      loc_1800A73D7
0x1800a724c  test    byte ptr [rcx+1Ch], 1
0x1800a7250  jz      loc_1800A73D7
0x1800a7256  mov     edx, 17h
0x1800a725b  jmp     loc_1800A710A
0x1800a7260  mov     eax, dword ptr [rbp+240h+var_2A0]
0x1800a7263  mov     qword ptr [rsp+340h+var_2D0+8], rax
0x1800a7268  mov     byte ptr [rbp+240h+var_2C0], 0
0x1800a726c  mov     rcx, [rsp+340h+var_308]
0x1800a7271  mov     [rsp+340h+var_300], rcx
0x1800a7276  xor     eax, eax
0x1800a7278  mov     [rcx], ax
0x1800a727b  mov     r8d, dword ptr [rbp+240h+var_2A0]
0x1800a727f  lea     rdx, aContentLengthL; "Content-Length: %llu\n"
0x1800a7286  lea     rcx, [rsp+340h+var_308]
0x1800a728b  call    ??$append_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::append_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800a7290  lea     rdx, aXMsVersion2017; "x-ms-version: 2017-04-17\n"
0x1800a7297  lea     rcx, [rsp+340h+var_308]
0x1800a729c  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
0x1800a72a1  lea     rdx, aXMsDate; "x-ms-date: "
0x1800a72a8  lea     rcx, [rsp+340h+var_308]
0x1800a72ad  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *)
  ... truncated ...
```
