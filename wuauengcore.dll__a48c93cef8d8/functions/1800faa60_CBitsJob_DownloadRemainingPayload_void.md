# CBitsJob::DownloadRemainingPayload(void)

- ea: `0x1800faa60`
- end: `0x1800fb258`
- name: `?DownloadRemainingPayload@CBitsJob@@UEAAJXZ`
- size: `2040`
- prototype: `__int64 __fastcall(CBitsJob *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x18000def4`
- `0x18003bab0`
- `0x180052114`
- `0x180052fb0`
- `0x1800788b8`
- `0x180078900`
- `0x1800d34d0`
- `0x1800e73a4`
- `0x1800e7870`
- `0x1800f8464`
- `0x1800faa60`
- `0x180102e14`
- `0x180102f48`
- `0x180113ae8`
- `0x18012b618`
- `0x18012bed4`
- `0x180238960`
- `0x180238984`
- `0x180239110`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fab5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fab9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800facd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800faceb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fad1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fad34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fad66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fad7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fadaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fadc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fab5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fab9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800facd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800faceb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fad1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fad34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fad66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fad7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fadaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fadc6`

## string_xrefs

- `0x1800fb216`: `C:\__w\1\s\src\Client\Engine\Agent\BitsJobBlockTable.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CBitsJob::DownloadRemainingPayload(CBitsJob *this)
{
  struct IBackgroundCopyFile **v2; // rdi
  signed int Files; // esi
  unsigned int v4; // r12d
  __int64 v5; // r14
  __int64 v6; // rbx
  __int64 (__fastcall *v7)(__int64, LPVOID *); // rsi
  struct IBackgroundCopyFile *v8; // rbx
  HRESULT (__stdcall *GetLocalName)(IBackgroundCopyFile *, LPWSTR *); // rsi
  unsigned int v10; // ecx
  unsigned int v11; // eax
  unsigned int v12; // r8d
  char *v13; // rbx
  __int64 v14; // rdx
  __m128i v15; // xmm6
  __int64 v16; // r12
  BitsJobBlockTable::CBlockInfoProvider *v17; // rax
  BitsJobBlockTable::CBlockInfoProvider *v18; // r14
  __int64 v19; // r13
  unsigned int IndexOf; // eax
  const wchar_t *v21; // r8
  __int64 v22; // r12
  unsigned int v23; // esi
  unsigned int v24; // ebx
  unsigned int v25; // esi
  unsigned int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // r8
  __int64 v30; // rdx
  unsigned int v31; // ecx
  void *v32; // rbx
  __int64 v33; // rax
  int v35; // [rsp+28h] [rbp-E0h]
  unsigned int v36[2]; // [rsp+58h] [rbp-B0h] BYREF
  char *v37; // [rsp+60h] [rbp-A8h] BYREF
  struct IBackgroundCopyFile **v38; // [rsp+68h] [rbp-A0h] BYREF
  struct _GUID v39; // [rsp+70h] [rbp-98h] BYREF
  BitsJobBlockTable::CBlockInfoProvider *v40; // [rsp+80h] [rbp-88h]
  unsigned int v41[2]; // [rsp+88h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+90h] [rbp-78h] BYREF
  LPVOID v43; // [rsp+98h] [rbp-70h] BYREF
  void *lpMem[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v45; // [rsp+B0h] [rbp-58h]
  _QWORD v46[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int128 v47; // [rsp+C8h] [rbp-40h]
  __int128 v48; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v49; // [rsp+E8h] [rbp-20h]
  __int64 v50; // [rsp+F0h] [rbp-18h]
  char *v51; // [rsp+F8h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+170h] [rbp+68h]

  v2 = 0;
  v38 = 0;
  v41[0] = 0;
  if ( *((_BYTE *)this + 8) )
  {
    Files = (*(__int64 (__fastcall **)(CBitsJob *))(*(_QWORD *)this + 176LL))(this);
    if ( Files >= 0 )
    {
      *((_BYTE *)this + 8) = 0;
      Files = CBitsJob::GetFiles(this, &v38, v41);
      v2 = v38;
      if ( Files >= 0 )
      {
        v4 = v41[0];
        if ( v41[0] )
        {
          v5 = 0;
          do
          {
            *(_QWORD *)v41 = 0;
            pv = 0;
            v43 = 0;
            Files = ((__int64 (__fastcall *)(struct IBackgroundCopyFile *, GUID *, unsigned int *))v2[v5]->lpVtbl->QueryInterface)(
                      v2[v5],
                      &GUID_659cdeaa_489e_11d9_a9cd_000d56965251,
                      v41);
            if ( Files < 0 )
            {
              if ( v43 )
              {
                CoTaskMemFree(v43);
                v43 = 0;
              }
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              if ( *(_QWORD *)v41 )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
              goto LABEL_83;
            }
            v6 = *(_QWORD *)v41;
            v7 = *(__int64 (__fastcall **)(__int64, LPVOID *))(**(_QWORD **)v41 + 64LL);
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            Files = v7(v6, &pv);
            if ( Files < 0 )
            {
              if ( v43 )
              {
                CoTaskMemFree(v43);
                v43 = 0;
              }
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              if ( *(_QWORD *)v41 )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
              goto LABEL_83;
            }
            v8 = v2[v5];
            GetLocalName = v8->lpVtbl->GetLocalName;
            if ( v43 )
            {
              CoTaskMemFree(v43);
              v43 = 0;
            }
            Files = ((__int64 (__fastcall *)(struct IBackgroundCopyFile *, LPVOID *))GetLocalName)(v8, &v43);
            if ( Files < 0 )
            {
              if ( v43 )
              {
                CoTaskMemFree(v43);
                v43 = 0;
              }
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              if ( *(_QWORD *)v41 )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
              goto LABEL_83;
            }
            v37 = (char *)pv;
            *(_QWORD *)v36 = v43;
            Files = CSusMap<wchar_t *,CBitsJob::CStreamingInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsDelete<CBitsJob::CStreamingInfo *>>::Add(
                      (char *)this + 48,
                      v36,
                      &v37);
            if ( Files < 0 )
            {
              if ( v43 )
              {
                CoTaskMemFree(v43);
                v43 = 0;
              }
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              if ( *(_QWORD *)v41 )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
              goto LABEL_83;
            }
            v43 = 0;
            pv = 0;
            if ( *(_QWORD *)v41 )
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
            v5 = (unsigned int)(v5 + 1);
          }
          while ( (unsigned int)v5 < v4 );
          v10 = 0;
          LODWORD(pv) = 0;
          v11 = *((_DWORD *)this + 25);
          if ( v11 )
          {
            v12 = *((_DWORD *)this + 25);
            while ( 1 )
            {
              lpMem[0] = &CSusArrayList<RequestJobRange,CSusArrayListItemOpNoop<RequestJobRange>>::`vftable';
              v13 = 0;
              lpMem[1] = 0;
              v45 = 0;
              v41[0] = 0;
              v46[1] = 0;
              v47 = 0u;
              v46[0] = &CSusSortedArrayList<unsigned long,CSusSortedArrayListItemOpsBasic<unsigned long>>::`vftable';
              if ( v10 >= v12 )
                break;
              v14 = *((_QWORD *)this + 11);
              v15 = *(__m128i *)(v14 + 16LL * v10);
              if ( v10 >= v11 )
                break;
              v16 = *(_QWORD *)(v14 + 16LL * v10);
              v17 = (BitsJobBlockTable::CBlockInfoProvider *)operator new(
                                                               0x18u,
                                                               (const struct std::nothrow_t *)&std::nothrow);
              v18 = v17;
              if ( v17 )
              {
                *((_QWORD *)v17 + 1) = 0;
                *((_QWORD *)v17 + 2) = 0;
                *(_QWORD *)v17 = &CSusArray<CAppxBlockTableBase *,CSusArrayListItemOpDelete<CAppxBlockTableBase *>>::`vftable';
              }
              else
              {
                v18 = 0;
              }
              v40 = v18;
              Files = v18 == 0 ? 0x8007000E : 0;
              if ( !v18 )
                goto LABEL_93;
              v19 = v16;
              if ( (unsigned int)BitsJobBlockTable::CBlockInfoProvider::Init(
                                   v18,
                                   *(const wchar_t **)(v16 + 40),
                                   *(const wchar_t **)(v16 + 56),
                                   *(_DWORD *)(v16 + 32),
                                   *(const unsigned __int8 **)(v16 + 24),
                                   *(const wchar_t **)(v16 + 16)) == -2147024894 )
              {
                v37 = *(char **)(v16 + 56);
                IndexOf = CSusMap<wchar_t *,CBitsJob::CStreamingInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsDelete<CBitsJob::CStreamingInfo *>>::GetIndexOf(
                            (char *)this + 48,
                            &v37);
                if ( IndexOf >= *((_DWORD *)this + 17) )
                {
LABEL_86:
                  Files = -2145124345;
                  goto LABEL_87;
                }
                v21 = *(const wchar_t **)(*((_QWORD *)this + 7) + 16LL * IndexOf);
                Files = 0;
                if ( !v21 )
                  goto LABEL_87;
                Files = BitsJobBlockTable::CBlockInfoProvider::Init(
                          v18,
                          *(const wchar_t **)(v16 + 40),
                          v21,
                          *(_DWORD *)(v16 + 32),
                          *(const unsigned __int8 **)(v16 + 24),
                          *(const wchar_t **)(v16 + 16));
                if ( Files < 0 )
                  goto LABEL_87;
              }
              v37 = 0;
              LODWORD(v43) = *(_DWORD *)(v16 + 84);
              v22 = 0;
              if ( (_DWORD)v43 )
              {
                do
                {
                  if ( (unsigned int)v22 >= *(_DWORD *)(v19 + 84) )
                    goto LABEL_86;
                  v36[0] = 0;
                  v41[0] = 0;
                  Files = BitsJobBlockTable::CBlockInfoProvider::GetBlockInfos(
                            v18,
                            (const struct _BG_FILE_RANGE *)(*(_QWORD *)(v19 + 72) + 24 * v22),
                            v36,
                            v41);
                  if ( Files < 0 )
                    goto LABEL_87;
                  v23 = v41[0];
                  v24 = v36[0];
                  WUTrace(0, 0, 2, 5, 0, L"Range[%lu] covers blocks %lu to %lu");
                  v36[0] = v24;
                  if ( v24 <= v23 )
                  {
                    v25 = v24;
                    do
                    {
                      v26 = CSusSortedArrayList<unsigned long,CSusSortedArrayListItemOpsBasic<unsigned long>>::GetIndexOf(
                              v46,
                              v36);
                      if ( v26 >= DWORD1(v47) )
                      {
                        v50 = 0;
                        v51 = 0;
                        v48 = 0;
                        v49 = 0;
                        v27 = *((_QWORD *)v18 + 1);
                        if ( v25 >= *(_DWORD *)(*(_QWORD *)v27 + 52LL) )
                        {
                          Files = -2145124345;
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x3F,
                            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\BitsJobBlockTable.cpp",
                            (const char *)0x80240007LL,
                            v35);
                          goto LABEL_87;
                        }
                        v28 = *(_QWORD *)(*(_QWORD *)v27 + 56LL);
                        v29 = *(_QWORD *)(v28 + 24LL * v25);
                        v30 = *(unsigned int *)(v28 + 24LL * v25 + 8);
                        LODWORD(v48) = v25;
                        *((_QWORD *)&v48 + 1) = v29;
                        LODWORD(v49) = v30;
                        *(_QWORD *)&v39.Data1 = v29;
                        *(_QWORD *)v39.Data4 = v30;
                        WUTrace(0, 0, 2, 5, 0, L"    Block[%lu]: Offset: %I64u, Length: %lu");
                        Files = CSusArrayList<CertContext,CSusArrayListItemOpCertFree>::Add(lpMem, &v39, 0);
                        if ( Files < 0 )
                          goto LABEL_87;
                        v51 = v37;
                        Files = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)(v19 + 88) + 8LL))(
                                  v19 + 88,
                                  &v48,
                                  0);
                        if ( Files < 0 )
                          goto LABEL_87;
                        Files = CSusSortedArrayList<unsigned long,CSusSortedArrayListItemOpsBasic<unsigned long>>::Add(
                                  v46,
                                  v36,
                                  0);
                        if ( Files < 0 )
                          goto LABEL_87;
                        v37 += (unsigned int)v49;
                      }
                      v36[0] = ++v24;
                      v25 = v24;
                    }
                    while ( v24 <= v41[0] );
                  }
                  v22 = (unsigned int)(v22 + 1);
                }
                while ( (unsigned int)v22 < (unsigned int)v43 );
                v31 = HIDWORD(v45);
                v13 = (char *)lpMem[1];
              }
              else
              {
                v31 = v41[0];
              }
              if ( v31 )
              {
                v37 = v13;
                lpMem[1] = 0;
                v45 = 0;
                Files = (*(__int64 (__fastcall **)(CBitsJob *, unsigned __int64, _QWORD, _QWORD, unsigned int, char *, _QWORD, _QWORD))(*(_QWORD *)this + 352LL))(
                          this,
                          _mm_srli_si128(v15, 8).m128i_u64[0],
                          *(_QWORD *)(v19 + 8),
                          *(_QWORD *)(v19 + 48),
                          v31,
                          v13,
                          0,
                          0);
                if ( Files < 0 )
                {
                  if ( v13 )
                    SusFree(v13);
LABEL_87:
                  CSusArrayList<CWUDeploymentDirectoryInfo *,CSusArrayListItemOpDelete<CWUDeploymentDirectoryInfo *>>::~CSusArrayList<CWUDeploymentDirectoryInfo *,CSusArrayListItemOpDelete<CWUDeploymentDirectoryInfo *>>(v18);
                  operator delete(v18, (const struct std::nothrow_t *)0x18);
                  goto LABEL_93;
                }
                if ( v13 )
                  SusFree(v13);
              }
              v32 = *(void **)(v19 + 112);
              if ( v32 )
              {
                CSusArrayList<CWUDeploymentDirectoryInfo *,CSusArrayListItemOpDelete<CWUDeploymentDirectoryInfo *>>::~CSusArrayList<CWUDeploymentDirectoryInfo *,CSusArrayListItemOpDelete<CWUDeploymentDirectoryInfo *>>(*(_QWORD *)(v19 + 112));
                operator delete(v32, (const struct std::nothrow_t *)0x18);
              }
              *(_QWORD *)(v19 + 112) = v18;
              CSusArrayList<unsigned long,CSusSortedArrayListItemOpsBasic<unsigned long>>::~CSusArrayList<unsigned long,CSusSortedArrayListItemOpsBasic<unsigned long>>(v46);
              CSusArrayList<CUpdateDownloadJob::TimeStampedBytesTransferred,CSusArrayListItemOpNoop<CUpdateDownloadJob::TimeStampedBytesTransferred>>::~CSusArrayList<CUpdateDownloadJob::TimeStampedBytesTransferred,CSusArrayListItemOpNoop<CUpdateDownloadJob::TimeStampedBytesTransferred>>(lpMem);
              v10 = (_DWORD)pv + 1;
              LODWORD(pv) = v10;
              v11 = *((_DWORD *)this + 25);
              v12 = v11;
              if ( v10 >= v11 )
                goto LABEL_81;
            }
            Files = -2145124345;
LABEL_93:
            CSusArrayList<unsigned long,CSusSortedArrayListItemOpsBasic<unsigned long>>::~CSusArrayList<unsigned long,CSusSortedArrayListItemOpsBasic<unsigned long>>(v46);
            CSusArrayList<CUpdateDownloadJob::TimeStampedBytesTransferred,CSusArrayListItemOpNoop<CUpdateDownloadJob::TimeStampedBytesTransferred>>::~CSusArrayList<CUpdateDownloadJob::TimeStampedBytesTransferred,CSusArrayListItemOpNoop<CUpdateDownloadJob::TimeStampedBytesTransferred>>(lpMem);
          }
          else
          {
LABEL_81:
            v39 = (struct _GUID)*((_OWORD *)this + 1);
            v33 = Trace::GuidToString::GuidToString((Trace::GuidToString *)&v48, &v39);
            WUTrace(0, 0, 2, 5, 0, L"Enabling notification for progress too for job %ws", v33);
            Files = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 14) + 184LL))(
                      *((_QWORD *)this + 14),
                      11);
            if ( Files >= 0 )
              Files = (*(__int64 (__fastcall **)(CBitsJob *))(*(_QWORD *)this + 184LL))(this);
          }
        }
        else
        {
          Files = -2145124344;
        }
      }
    }
  }
  else
  {
    Files = -2145120257;
  }
LABEL_83:
  if ( v2 )
    SusFree(v2);
  return (unsigned int)Files;
}

```

## disassembly

```asm
0x1800faa60  mov     rax, rsp
0x1800faa63  mov     [rax+10h], rbx
0x1800faa67  mov     [rax+18h], rsi
0x1800faa6b  mov     [rax+20h], rdi
0x1800faa6f  push    rbp
0x1800faa70  push    r12
0x1800faa72  push    r13
0x1800faa74  push    r14
0x1800faa76  push    r15
0x1800faa78  lea     rbp, [rax-68h]
0x1800faa7c  sub     rsp, 140h
0x1800faa83  movaps  xmmword ptr [rax-38h], xmm6
0x1800faa87  mov     rax, cs:__security_cookie
0x1800faa8e  xor     rax, rsp
0x1800faa91  mov     [rbp+60h+var_40], rax
0x1800faa95  mov     r15, rcx
0x1800faa98  xor     edi, edi
0x1800faa9a  mov     qword ptr [rsp+160h+var_100.Data1], rdi
0x1800faa9f  mov     [rbp+60h+var_E0], edi
0x1800faaa2  cmp     [rcx+8], dil
0x1800faaa6  jnz     short loc_1800FAAB2
0x1800faaa8  mov     esi, 80240FFFh
0x1800faaad  jmp     loc_1800FB1AD
0x1800faab2  mov     rax, [rcx]
0x1800faab5  mov     rax, [rax+0B0h]
0x1800faabc  call    _guard_dispatch_icall
0x1800faac1  mov     esi, eax
0x1800faac3  test    eax, eax
0x1800faac5  js      loc_1800FB1AD
0x1800faacb  mov     byte ptr [r15+8], 0
0x1800faad0  lea     r8, [rbp+60h+var_E0]; unsigned int *
0x1800faad4  lea     rdx, [rsp+160h+var_100]; struct IBackgroundCopyFile ***
0x1800faad9  mov     rcx, r15; this
0x1800faadc  call    ?GetFiles@CBitsJob@@AEAAJPEAPEAPEAUIBackgroundCopyFile@@PEAK@Z; CBitsJob::GetFiles(IBackgroundCopyFile * * *,ulong *)
0x1800faae1  mov     esi, eax
0x1800faae3  mov     rdi, qword ptr [rsp+160h+var_100.Data1]
0x1800faae8  test    eax, eax
0x1800faaea  js      loc_1800FB1AD
0x1800faaf0  mov     r12d, [rbp+60h+var_E0]
0x1800faaf4  test    r12d, r12d
0x1800faaf7  jnz     short loc_1800FAB03
0x1800faaf9  mov     esi, 80240008h
0x1800faafe  jmp     loc_1800FB1AD
0x1800fab03  xor     r14d, r14d
0x1800fab06  test    r12d, r12d
0x1800fab09  jz      loc_1800FAC22
0x1800fab0f  mov     qword ptr [rbp+60h+var_E0], 0
0x1800fab17  mov     [rbp+60h+pv], 0
0x1800fab1f  mov     [rbp+60h+var_D0], 0
0x1800fab27  mov     rcx, [rdi+r14*8]
0x1800fab2b  mov     rax, [rcx]
0x1800fab2e  lea     r8, [rbp+60h+var_E0]
0x1800fab32  lea     rdx, _GUID_659cdeaa_489e_11d9_a9cd_000d56965251
0x1800fab39  mov     rax, [rax]
0x1800fab3c  call    _guard_dispatch_icall
0x1800fab41  mov     esi, eax
0x1800fab43  test    eax, eax
0x1800fab45  js      loc_1800FADA6
0x1800fab4b  mov     rbx, qword ptr [rbp+60h+var_E0]
0x1800fab4f  mov     rax, [rbx]
0x1800fab52  mov     rsi, [rax+40h]
0x1800fab56  mov     rcx, [rbp+60h+pv]; pv
0x1800fab5a  test    rcx, rcx
0x1800fab5d  jz      short loc_1800FAB6D
0x1800fab5f  call    cs:__imp_CoTaskMemFree
0x1800fab65  mov     [rbp+60h+pv], 0
0x1800fab6d  lea     rdx, [rbp+60h+pv]
0x1800fab71  mov     rcx, rbx
0x1800fab74  mov     rax, rsi
0x1800fab77  call    _guard_dispatch_icall
0x1800fab7c  mov     esi, eax
0x1800fab7e  test    eax, eax
0x1800fab80  js      loc_1800FAD5D
0x1800fab86  mov     rbx, [rdi+r14*8]
0x1800fab8a  mov     rax, [rbx]
0x1800fab8d  mov     rsi, [rax+20h]
0x1800fab91  mov     rcx, [rbp+60h+var_D0]; pv
0x1800fab95  test    rcx, rcx
0x1800fab98  jz      short loc_1800FABA8
0x1800fab9a  call    cs:__imp_CoTaskMemFree
0x1800faba0  mov     [rbp+60h+var_D0], 0
0x1800faba8  lea     rdx, [rbp+60h+var_D0]
0x1800fabac  mov     rcx, rbx
0x1800fabaf  mov     rax, rsi
0x1800fabb2  call    _guard_dispatch_icall
0x1800fabb7  mov     esi, eax
0x1800fabb9  test    eax, eax
0x1800fabbb  js      loc_1800FAD14
0x1800fabc1  mov     rax, [rbp+60h+pv]
0x1800fabc5  mov     [rsp+160h+var_108], rax
0x1800fabca  mov     rax, [rbp+60h+var_D0]
0x1800fabce  mov     qword ptr [rsp+160h+var_110], rax
0x1800fabd3  lea     rcx, [r15+30h]
0x1800fabd7  lea     r8, [rsp+160h+var_108]
0x1800fabdc  lea     rdx, [rsp+160h+var_110]
0x1800fabe1  call    ?Add@?$CSusMap@PEA_WPEAVCStreamingInfo@CBitsJob@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusSortedArrayListItemOpsDelete@PEAVCStreamingInfo@CBitsJob@@@@@@QEAAJAEBQEA_WAEBQEAVCStreamingInfo@CBitsJob@@@Z; CSusMap<wchar_t *,CBitsJob::CStreamingInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsDelete<CBitsJob::CStreamingInfo *>>::Add(wchar_t * const &,CBitsJob::CStreamingInfo * const &)
0x1800fabe6  mov     esi, eax
0x1800fabe8  test    eax, eax
0x1800fabea  js      loc_1800FACCB
0x1800fabf0  mov     [rbp+60h+var_D0], 0
0x1800fabf8  mov     [rbp+60h+pv], 0
0x1800fac00  mov     rcx, qword ptr [rbp+60h+var_E0]
0x1800fac04  test    rcx, rcx
0x1800fac07  jz      short loc_1800FAC16
0x1800fac09  mov     rax, [rcx]
0x1800fac0c  mov     rax, [rax+10h]
0x1800fac10  call    _guard_dispatch_icall
0x1800fac15  nop
0x1800fac16  inc     r14d
0x1800fac19  cmp     r14d, r12d
0x1800fac1c  jb      loc_1800FAB0F
0x1800fac22  xor     ecx, ecx
0x1800fac24  mov     dword ptr [rbp+60h+pv], ecx
0x1800fac27  mov     eax, [r15+64h]
0x1800fac2b  test    eax, eax
0x1800fac2d  jz      loc_1800FB137
0x1800fac33  mov     r8d, eax
0x1800fac36  xorps   xmm0, xmm0
0x1800fac39  movups  xmmword ptr [rbp+60h+lpMem], xmm0
0x1800fac3d  lea     rdx, ??_7?$CSusArrayList@URequestJobRange@@V?$CSusArrayListItemOpNoop@URequestJobRange@@@@@@6B@; const CSusArrayList<RequestJobRange,CSusArrayListItemOpNoop<RequestJobRange>>::`vftable'
0x1800fac44  mov     [rbp+60h+lpMem], rdx
0x1800fac48  xor     ebx, ebx
0x1800fac4a  mov     [rbp+60h+lpMem+8], rbx
0x1800fac4e  mov     [rbp+60h+var_B8], rbx
0x1800fac52  xor     edx, edx
0x1800fac54  mov     [rbp+60h+var_E0], edx
0x1800fac57  movups  [rbp+60h+var_B0], xmm0
0x1800fac5b  movups  [rbp+60h+var_A0], xmm0
0x1800fac5f  mov     qword ptr [rbp+60h+var_B0+8], rdx
0x1800fac63  mov     qword ptr [rbp+60h+var_A0], rdx
0x1800fac67  lea     rdx, ??_7?$CSusSortedArrayList@KV?$CSusSortedArrayListItemOpsBasic@K@@@@6B@; const CSusSortedArrayList<ulong,CSusSortedArrayListItemOpsBasic<ulong>>::`vftable'
0x1800fac6e  mov     qword ptr [rbp+60h+var_B0], rdx
0x1800fac72  mov     dword ptr [rbp+60h+var_A0+8], ebx
0x1800fac75  cmp     ecx, r8d
0x1800fac78  jnb     loc_1800FB23A
0x1800fac7e  mov     r12d, ecx
0x1800fac81  add     r12, r12
0x1800fac84  mov     rdx, [r15+58h]
0x1800fac88  movups  xmm6, xmmword ptr [rdx+r12*8]
0x1800fac8d  cmp     ecx, eax
0x1800fac8f  jnb     loc_1800FB23A
0x1800fac95  mov     r12, [rdx+r12*8]
0x1800fac99  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800faca0  lea     ecx, [rbx+18h]; unsigned __int64
0x1800faca3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800faca8  mov     r14, rax
0x1800facab  test    rax, rax
0x1800facae  jz      loc_1800FADEF
0x1800facb4  mov     [rax+8], rbx
0x1800facb8  mov     [rax+10h], rbx
0x1800facbc  lea     rax, ??_7?$CSusArray@PEAVCAppxBlockTableBase@@V?$CSusArrayListItemOpDelete@PEAVCAppxBlockTableBase@@@@@@6B@; const CSusArray<CAppxBlockTableBase *,CSusArrayListItemOpDelete<CAppxBlockTableBase *>>::`vftable'
0x1800facc3  mov     [r14], rax
0x1800facc6  jmp     loc_1800FADF2
0x1800faccb  mov     rcx, [rbp+60h+var_D0]; pv
0x1800faccf  test    rcx, rcx
0x1800facd2  jz      short loc_1800FACE2
0x1800facd4  call    cs:__imp_CoTaskMemFree
0x1800facda  mov     [rbp+60h+var_D0], 0
0x1800face2  mov     rcx, [rbp+60h+pv]; pv
0x1800face6  test    rcx, rcx
0x1800face9  jz      short loc_1800FACF9
0x1800faceb  call    cs:__imp_CoTaskMemFree
0x1800facf1  mov     [rbp+60h+pv], 0
0x1800facf9  mov     rcx, qword ptr [rbp+60h+var_E0]
0x1800facfd  test    rcx, rcx
0x1800fad00  jz      short loc_1800FAD0F
0x1800fad02  mov     rax, [rcx]
0x1800fad05  mov     rax, [rax+10h]
0x1800fad09  call    _guard_dispatch_icall
0x1800fad0e  nop
0x1800fad0f  jmp     loc_1800FB1AD
0x1800fad14  mov     rcx, [rbp+60h+var_D0]; pv
0x1800fad18  test    rcx, rcx
0x1800fad1b  jz      short loc_1800FAD2B
0x1800fad1d  call    cs:__imp_CoTaskMemFree
0x1800fad23  mov     [rbp+60h+var_D0], 0
0x1800fad2b  mov     rcx, [rbp+60h+pv]; pv
0x1800fad2f  test    rcx, rcx
0x1800fad32  jz      short loc_1800FAD42
0x1800fad34  call    cs:__imp_CoTaskMemFree
0x1800fad3a  mov     [rbp+60h+pv], 0
0x1800fad42  mov     rcx, qword ptr [rbp+60h+var_E0]
0x1800fad46  test    rcx, rcx
0x1800fad49  jz      short loc_1800FAD58
0x1800fad4b  mov     rax, [rcx]
0x1800fad4e  mov     rax, [rax+10h]
0x1800fad52  call    _guard_dispatch_icall
0x1800fad57  nop
0x1800fad58  jmp     loc_1800FB1AD
0x1800fad5d  mov     rcx, [rbp+60h+var_D0]; pv
0x1800fad61  test    rcx, rcx
0x1800fad64  jz      short loc_1800FAD74
0x1800fad66  call    cs:__imp_CoTaskMemFree
0x1800fad6c  mov     [rbp+60h+var_D0], 0
0x1800fad74  mov     rcx, [rbp+60h+pv]; pv
0x1800fad78  test    rcx, rcx
0x1800fad7b  jz      short loc_1800FAD8B
0x1800fad7d  call    cs:__imp_CoTaskMemFree
0x1800fad83  mov     [rbp+60h+pv], 0
0x1800fad8b  mov     rcx, qword ptr [rbp+60h+var_E0]
0x1800fad8f  test    rcx, rcx
0x1800fad92  jz      short loc_1800FADA1
0x1800fad94  mov     rax, [rcx]
0x1800fad97  mov     rax, [rax+10h]
0x1800fad9b  call    _guard_dispatch_icall
0x1800fada0  nop
0x1800fada1  jmp     loc_1800FB1AD
0x1800fada6  mov     rcx, [rbp+60h+var_D0]; pv
0x1800fadaa  test    rcx, rcx
0x1800fadad  jz      short loc_1800FADBD
0x1800fadaf  call    cs:__imp_CoTaskMemFree
0x1800fadb5  mov     [rbp+60h+var_D0], 0
0x1800fadbd  mov     rcx, [rbp+60h+pv]; pv
0x1800fadc1  test    rcx, rcx
0x1800fadc4  jz      short loc_1800FADD4
0x1800fadc6  call    cs:__imp_CoTaskMemFree
0x1800fadcc  mov     [rbp+60h+pv], 0
0x1800fadd4  mov     rcx, qword ptr [rbp+60h+var_E0]
0x1800fadd8  test    rcx, rcx
0x1800faddb  jz      short loc_1800FADEA
0x1800faddd  mov     rax, [rcx]
0x1800fade0  mov     rax, [rax+10h]
0x1800fade4  call    _guard_dispatch_icall
0x1800fade9  nop
0x1800fadea  jmp     loc_1800FB1AD
0x1800fadef  xor     r14d, r14d
0x1800fadf2  mov     [rsp+160h+var_E8], r14
0x1800fadf7  mov     rax, r14
0x1800fadfa  neg     rax
0x1800fadfd  sbb     esi, esi
0x1800fadff  not     esi
0x1800fae01  and     esi, 8007000Eh
0x1800fae07  test    r14, r14
0x1800fae0a  jz      loc_1800FB238
0x1800fae10  mov     rax, [r12+10h]
0x1800fae15  mov     [rsp+160h+var_138], rax; wchar_t *
0x1800fae1a  mov     rax, [r12+18h]
0x1800fae1f  mov     [rsp+160h+var_140], rax; unsigned __int8 *
0x1800fae24  mov     r9d, [r12+20h]; unsigned int
0x1800fae29  mov     r8, [r12+38h]; wchar_t *
0x1800fae2e  mov     rdx, [r12+28h]; wchar_t *
0x1800fae33  mov     rcx, r14; this
0x1800fae36  call    ?Init@CBlockInfoProvider@BitsJobBlockTable@@QEAAJPEB_W0KPEBE0@Z; BitsJobBlockTable::CBlockInfoProvider::Init(wchar_t const *,wchar_t const *,ulong,uchar const *,wchar_t const *)
0x1800fae3b  mov     r13, r12
0x1800fae3e  test    eax, eax
0x1800fae40  jns     short loc_1800FAEB3
0x1800fae42  cmp     eax, 80070002h
0x1800fae47  jnz     short loc_1800FAEB3
0x1800fae49  mov     rax, [r12+38h]
0x1800fae4e  mov     [rsp+160h+var_108], rax
0x1800fae53  lea     rdx, [rsp+160h+var_108]
0x1800fae58  lea     rcx, [r15+30h]
0x1800fae5c  call    ?GetIndexOf@?$CSusMap@PEA_WPEAVCStreamingInfo@CBitsJob@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusSortedArrayListItemOpsDelete@PEAVCStreamingInfo@CBitsJob@@@@@@QEBAKAEBQEA_W@Z; CSusMap<wchar_t *,CBitsJob::CStreamingInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsDelete<CBitsJob::CStreamingInfo *>>::GetIndexOf(wchar_t * const &)
0x1800fae61  cmp     eax, [r15+44h]
0x1800fae65  jnb     loc_1800FB1EE
0x1800fae6b  mov     ecx, eax
0x1800fae6d  add     rcx, rcx
0x1800fae70  mov     rax, [r15+38h]
0x1800fae74  mov     r8, [rax+rcx*8]; wchar_t *
0x1800fae78  xor     esi, esi
0x1800fae7a  test    r8, r8
0x1800fae7d  jz      loc_1800FB1F3
0x1800fae83  mov     rax, [r12+10h]
0x1800fae88  mov     [rsp+160h+var_138], rax; wchar_t *
0x1800fae8d  mov     rax, [r12+18h]
0x1800fae92  mov     [rsp+160h+var_140], rax; unsigned __int8 *
0x1800fae97  mov     r9d, [r12+20h]; unsigned int
0x1800fae9c  mov     rdx, [r12+28h]; wchar_t *
0x1800faea1  mov     rcx, r14; this
0x1800faea4  call    ?Init@CBlockInfoProvider@BitsJobBlockTable@@QEAAJPEB_W0KPEBE0@Z; BitsJobBlockTable::CBlockInfoProvider::Init(wchar_t const *,wchar_t const *,ulong,uchar const *,wchar_t const *)
0x1800faea9  mov     esi, eax
0x1800faeab  test    eax, eax
0x1800faead  js      loc_1800FB1F3
0x1800faeb3  mov     [rsp+160h+var_108], 0
0x1800faebc  mov     eax, [r13+54h]
0x1800faec0  mov     dword ptr [rbp+60h+var_D0], eax
0x1800faec3  xor     r12d, r12d
0x1800faec6  test    eax, eax
0x1800faec8  jz      loc_1800FB079
0x1800faece  cmp     r12d, [r13+54h]
0x1800faed2  jnb     loc_1800FB1EE
0x1800faed8  mov     [rsp+160h+var_110], 0
0x1800faee0  mov     [rbp+60h+var_E0], 0
0x1800faee7  lea     rcx, [r12+r12*2]
0x1800faeeb  mov     rax, [r13+48h]
0x1800faeef  lea     rdx, [rax+rcx*8]; struct _BG_FILE_RANGE *
0x1800faef3  lea     r9, [rbp+60h+var_E0]; unsigned int *
0x1800faef7  lea     r8, [rsp+160h+var_110]; unsigned int *
0x1800faefc  mov     rcx, r14; this
0x1800faeff  call    ?GetBlockInfos@CBlockInfoProvider@BitsJobBlockTable@@QEAAJAEBU_BG_FILE_RANGE@@PEAK1@Z; BitsJobBlockTable::CBlockInfoProvider::GetBlockInfos(_BG_FILE_RANGE const &,ulong *,ulong *)
0x1800faf04  mov     esi, eax
0x1800faf06  test    eax, eax
0x1800faf08  js      loc_1800FB1F3
0x1800faf0e  mov     esi, [rbp+60h+var_E0]
0x1800faf11  mov     [rsp+160h+var_120], esi
0x1800faf15  mov     ebx, [rsp+160h+var_110]
0x1800faf19  mov     [rsp+160h+var_128], ebx
0x1800faf1d  mov     dword ptr [rsp+160h+var_130], r12d
0x1800faf22  lea     rax, aRangeLuCoversB; "Range[%lu] covers blocks %lu to %lu"
0x1800faf29  mov     [rsp+160h+var_138], rax
  ... truncated ...
```
