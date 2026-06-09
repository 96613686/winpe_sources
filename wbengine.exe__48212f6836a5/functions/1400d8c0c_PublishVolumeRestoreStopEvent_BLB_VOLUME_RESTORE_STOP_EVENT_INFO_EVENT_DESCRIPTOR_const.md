# PublishVolumeRestoreStopEvent(_BLB_VOLUME_RESTORE_STOP_EVENT_INFO *,_EVENT_DESCRIPTOR const *)

- ea: `0x1400d8c0c`
- end: `0x1400d9166`
- name: `?PublishVolumeRestoreStopEvent@@YAJPEAU_BLB_VOLUME_RESTORE_STOP_EVENT_INFO@@PEBU_EVENT_DESCRIPTOR@@@Z`
- size: `1370`
- prototype: `__int64 __fastcall(struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `5`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x140059750`
- `0x1400d8994`
- `0x1400d8a5c`
- `0x1400d8b30`
- `0x1400d916c`

## callees

- `0x1400063b4`
- `0x140006a64`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000bfd8`
- `0x14000c248`
- `0x14001358c`
- `0x1400154f0`
- `0x140051e98`
- `0x1400d3000`
- `0x1400d6444`
- `0x1400d8c0c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1400d8c8e`
- `KERNEL32!RaiseException` at `0x1400d8c8e`
- `ole32!CoTaskMemAlloc` at `0x1400d8e52`
- `ole32!CoTaskMemAlloc` at `0x1400d9026`
- `ole32!CoTaskMemAlloc` at `0x1400d8e52`
- `ole32!CoTaskMemAlloc` at `0x1400d9026`
- `ole32!CoTaskMemFree` at `0x1400d8f73`
- `ole32!CoTaskMemFree` at `0x1400d8fab`
- `ole32!CoTaskMemFree` at `0x1400d8fd2`
- `ole32!CoTaskMemFree` at `0x1400d8fe0`
- `ole32!CoTaskMemFree` at `0x1400d8f73`
- `ole32!CoTaskMemFree` at `0x1400d8fab`
- `ole32!CoTaskMemFree` at `0x1400d8fd2`
- `ole32!CoTaskMemFree` at `0x1400d8fe0`

## string_xrefs

- `0x1400d8edd`: `<VolumeInfoItem Name="%ws" RecoveryTargetVolumeName="%ws" HResult="%d" DetailedHResult="%d" VolumeRestoreState="%d" NoOfBytesProcessed="%lld" NoOfBytesToProcess="%lld"  Warnings="%lu" ChkDskHResult="%d" OriginalSectorSize="%lu" TargetSectorSize="%lu" BackupTargetUnreadableBytes="%I64d" RestoreTargetUnwritableBytes="%I64d" /> `

## pseudocode

```c
__int64 __fastcall PublishVolumeRestoreStopEvent(
        struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *a1,
        const struct _EVENT_DESCRIPTOR *a2)
{
  struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *v2; // r15
  unsigned __int16 *v4; // rdi
  void *v5; // r14
  int v6; // eax
  int ErrorCodeStringForEvent; // eax
  int v8; // ebx
  __int64 v9; // rsi
  __int64 v10; // rax
  struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned int v19; // ebx
  void *v20; // rax
  void *v21; // rdi
  unsigned int j; // esi
  LPVOID *v23; // rax
  unsigned __int64 v25; // r14
  SIZE_T v26; // rbx
  unsigned __int16 *v27; // rax
  unsigned int i; // r15d
  unsigned __int16 **v29; // rax
  int v30; // eax
  __int64 v31; // [rsp+28h] [rbp-D8h]
  __int64 v32; // [rsp+30h] [rbp-D0h]
  __int64 v33; // [rsp+38h] [rbp-C8h]
  __int64 v34; // [rsp+50h] [rbp-B0h]
  __int64 v35; // [rsp+58h] [rbp-A8h]
  __int64 v36; // [rsp+60h] [rbp-A0h]
  __int64 v37; // [rsp+68h] [rbp-98h]
  struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *v38; // [rsp+80h] [rbp-80h] BYREF
  __int64 v39; // [rsp+88h] [rbp-78h]
  LPVOID v40; // [rsp+90h] [rbp-70h] BYREF
  void *v41[3]; // [rsp+98h] [rbp-68h] BYREF
  int v42; // [rsp+B0h] [rbp-50h]
  __int64 v43; // [rsp+B8h] [rbp-48h]
  void *v44; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v45; // [rsp+C8h] [rbp-38h]
  __int64 v46; // [rsp+D0h] [rbp-30h]
  int v47; // [rsp+D8h] [rbp-28h]
  LPVOID pv; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v49; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v50; // [rsp+F0h] [rbp-10h]
  int v51; // [rsp+150h] [rbp+50h]
  unsigned int v53; // [rsp+160h] [rbp+60h]
  int v54; // [rsp+168h] [rbp+68h]

  v2 = (struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 64);
  memset(v41, 0, sizeof(v41));
  v4 = 0;
  v5 = 0;
  v42 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v49 = 0;
  v40 = 0;
  if ( !*((_DWORD *)a1 + 16) )
  {
    BlbAssert("base\\stor\\blb\\blbevents\\publisher\\blbpublisher.cpp", 0xCA7u, "FALSE");
    RaiseException(0x80070057, 1u, 0, 0);
  }
  v38 = a1;
  v39 = 16;
  v6 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v41, &v38);
  if ( v6 >= 0 )
  {
    LODWORD(v39) = 8;
    v38 = (struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 16);
    v6 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v41, &v38);
    if ( v6 >= 0 )
    {
      LODWORD(v39) = 16;
      v38 = (struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 24);
      v6 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v41, &v38);
      if ( v6 >= 0 )
      {
        LODWORD(v39) = 4;
        v38 = (struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 40);
        v6 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v41, &v38);
        if ( v6 >= 0 )
        {
          v38 = (struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 44);
          v6 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v41, &v38);
          if ( v6 >= 0 )
          {
            v38 = (struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 48);
            v6 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v41, &v38);
            if ( v6 >= 0 )
            {
              ErrorCodeStringForEvent = GetErrorCodeStringForEvent(*((unsigned int *)a1 + 11), &v40);
              v5 = v40;
              v8 = ErrorCodeStringForEvent;
              if ( ErrorCodeStringForEvent < 0 )
                goto LABEL_27;
              v9 = -1;
              v38 = (struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)v40;
              v10 = -1;
              do
                ++v10;
              while ( *((_WORD *)v40 + v10) );
              LODWORD(v39) = 2 * v10 + 2;
              v6 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v41, &v38);
              if ( v6 >= 0 )
              {
                v11 = (struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)*((_QWORD *)a1 + 7);
                v12 = -1;
                v38 = v11;
                do
                  ++v12;
                while ( *((_WORD *)v11 + v12) );
                LODWORD(v39) = 2 * v12 + 2;
                v6 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v41, &v38);
                if ( v6 >= 0 )
                {
                  v38 = v2;
                  LODWORD(v39) = 4;
                  v6 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v41, &v38);
                  if ( v6 >= 0 )
                  {
                    v13 = 30;
                    v14 = 0;
                    v51 = 30;
                    while ( 1 )
                    {
                      v53 = v14;
                      if ( v14 >= *(_DWORD *)v2 )
                        break;
                      v15 = v14;
                      v16 = -1;
                      v17 = *((_QWORD *)a1 + 9);
                      v43 = v15;
                      do
                        ++v16;
                      while ( *(_WORD *)(*(_QWORD *)(v17 + 8 * v15) + 2 * v16) );
                      do
                        ++v9;
                      while ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)a1 + 10) + 8 * v15) + 2 * v9) );
                      v18 = (unsigned int)(v9 + v16 + 1327);
                      v19 = v18;
                      v54 = v9 + v16 + 1327;
                      v50 = (unsigned int)v18;
                      v20 = CoTaskMemAlloc(2 * v18);
                      pv = v20;
                      if ( !v20 )
                      {
                        v4 = v49;
                        v8 = -2147024882;
                        goto LABEL_26;
                      }
                      memset_0(v20, 0, v19);
                      LODWORD(v37) = *(_DWORD *)(*((_QWORD *)a1 + 15) + 4 * v43);
                      LODWORD(v36) = *(_DWORD *)(*((_QWORD *)a1 + 14) + 4 * v43);
                      LODWORD(v35) = *(_DWORD *)(*((_QWORD *)a1 + 12) + 4 * v43);
                      LODWORD(v34) = *(_DWORD *)(*((_QWORD *)a1 + 13) + 4 * v43);
                      v21 = pv;
                      LODWORD(v33) = *(_DWORD *)(*((_QWORD *)a1 + 17) + 4 * v43);
                      LODWORD(v32) = *(_DWORD *)(*((_QWORD *)a1 + 16) + 4 * v43);
                      LODWORD(v31) = *(_DWORD *)(*((_QWORD *)a1 + 11) + 4 * v43);
                      v8 = StringCchPrintfW(
                             (unsigned __int16 *)pv,
                             v50,
                             L"<VolumeInfoItem Name=\"%ws\" RecoveryTargetVolumeName=\"%ws\" HResult=\"%d\" DetailedHResul"
                              "t=\"%d\" VolumeRestoreState=\"%d\" NoOfBytesProcessed=\"%lld\" NoOfBytesToProcess=\"%lld\""
                              "  Warnings=\"%lu\" ChkDskHResult=\"%d\" OriginalSectorSize=\"%lu\" TargetSectorSize=\"%lu\""
                              " BackupTargetUnreadableBytes=\"%I64d\" RestoreTargetUnwritableBytes=\"%I64d\" /> ",
                             *(_QWORD *)(*((_QWORD *)a1 + 9) + 8 * v43),
                             *(_QWORD *)(*((_QWORD *)a1 + 10) + 8 * v43),
                             v31,
                             v32,
                             v33,
                             *(_QWORD *)(*((_QWORD *)a1 + 18) + 8 * v43),
                             *(_QWORD *)(*((_QWORD *)a1 + 19) + 8 * v43),
                             v34,
                             v35,
                             v36,
                             v37,
                             *(_QWORD *)(*((_QWORD *)a1 + 20) + 8 * v43),
                             *(_QWORD *)(*((_QWORD *)a1 + 21) + 8 * v43));
                      if ( v8 < 0 )
                      {
                        CoTaskMemFree(v21);
                        v4 = 0;
                        goto LABEL_26;
                      }
                      v13 = v54 + v51;
                      v51 += v54;
                      ATL::CAtlArray<ATL::CComObject<CBlbComponentRestoreContext> *,ATL::CElementTraits<ATL::CComObject<CBlbComponentRestoreContext> *>>::Add(
                        &v44,
                        &pv);
                      v2 = (struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 64);
                      v14 = v53 + 1;
                      v9 = -1;
                    }
                    v25 = v13;
                    v26 = 2LL * v13;
                    v27 = (unsigned __int16 *)CoTaskMemAlloc(v26);
                    v4 = v27;
                    if ( !v27 )
                    {
                      v8 = -2147024882;
LABEL_26:
                      v5 = v40;
                      goto LABEL_27;
                    }
                    memset_0(v27, 0, v26);
                    v8 = StringCchCopyW(v4, v25, L"<VolumeInfo>");
                    if ( v8 < 0 )
                      goto LABEL_26;
                    for ( i = 0; i < v45; ++i )
                    {
                      v29 = (unsigned __int16 **)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                                   &v44,
                                                   i);
                      v8 = StringCchCatW(v4, v25, *v29);
                      if ( v8 < 0 )
                        goto LABEL_26;
                    }
                    v8 = StringCchCatW(v4, v25, L"</VolumeInfo>");
                    if ( v8 < 0 )
                      goto LABEL_26;
                    v38 = (struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)v4;
                    do
                      ++v9;
                    while ( v4[v9] );
                    LODWORD(v39) = 2 * v9 + 2;
                    v30 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v41, &v38);
                    if ( v30 >= 0 )
                    {
                      v38 = (struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 184);
                      LODWORD(v39) = 4;
                      v30 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v41, &v38);
                      if ( v30 >= 0 )
                      {
                        LODWORD(v39) = 8;
                        v38 = (struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 176);
                        v30 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v41, &v38);
                        if ( v30 >= 0 )
                        {
                          LODWORD(v39) = 4;
                          v38 = (struct _BLB_VOLUME_RESTORE_STOP_EVENT_INFO *)((char *)a1 + 188);
                          v8 = ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(v41, &v38);
                          if ( v8 < 0 )
                            goto LABEL_26;
                          v30 = PublishEvent(v41, a2);
                        }
                      }
                    }
                    v8 = v30;
                    goto LABEL_26;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v8 = v6;
LABEL_27:
  for ( j = 0; j < v45; ++j )
  {
    if ( *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                      &v44,
                      j) )
    {
      v23 = (LPVOID *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                        &v44,
                        j);
      CoTaskMemFree(*v23);
      *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                   &v44,
                   j) = 0;
    }
  }
  if ( v4 )
    CoTaskMemFree(v4);
  if ( v5 )
    CoTaskMemFree(v5);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(&v44);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(v41);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400d8c0c  mov     [rsp-8+arg_8], rdx
0x1400d8c11  push    rbp
0x1400d8c12  push    rbx
0x1400d8c13  push    rsi
0x1400d8c14  push    rdi
0x1400d8c15  push    r12
0x1400d8c17  push    r13
0x1400d8c19  push    r14
0x1400d8c1b  push    r15
0x1400d8c1d  lea     rbp, [rsp-8]
0x1400d8c22  sub     rsp, 108h
0x1400d8c29  xor     r12d, r12d
0x1400d8c2c  lea     r15, [rcx+40h]
0x1400d8c30  mov     r13, rcx
0x1400d8c33  mov     [rbp+40h+var_A8], r12
0x1400d8c37  mov     edi, r12d
0x1400d8c3a  mov     [rbp+40h+var_A0], r12
0x1400d8c3e  mov     r14d, r12d
0x1400d8c41  mov     [rbp+40h+var_98], r12
0x1400d8c45  mov     [rbp+40h+var_90], r12d
0x1400d8c49  mov     [rbp+40h+var_80], r12
0x1400d8c4d  mov     [rbp+40h+var_78], r12
0x1400d8c51  mov     [rbp+40h+var_70], r12
0x1400d8c55  mov     [rbp+40h+var_68], r12d
0x1400d8c59  mov     [rbp+40h+var_58], r12
0x1400d8c5d  mov     [rbp+40h+var_B0], r12
0x1400d8c61  cmp     [r15], r12d
0x1400d8c64  ja      short loc_1400D8C94
0x1400d8c66  lea     r8, aFalse_1; "FALSE"
0x1400d8c6d  mov     edx, 0CA7h; unsigned int
0x1400d8c72  lea     rcx, aBaseStorBlbBlb_1; "base\\stor\\blb\\blbevents\\publisher\\"...
0x1400d8c79  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400d8c7e  xor     r9d, r9d; lpArguments
0x1400d8c81  lea     edx, [r12+1]; dwExceptionFlags
0x1400d8c86  xor     r8d, r8d; nNumberOfArguments
0x1400d8c89  mov     ecx, 80070057h; dwExceptionCode
0x1400d8c8e  call    cs:__imp_RaiseException
0x1400d8c94  mov     ebx, 10h
0x1400d8c99  mov     [rbp+40h+var_C0], r13
0x1400d8c9d  lea     rdx, [rbp+40h+var_C0]
0x1400d8ca1  mov     [rbp+40h+var_B8], rbx
0x1400d8ca5  lea     rcx, [rbp+40h+var_A8]
0x1400d8ca9  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d8cae  test    eax, eax
0x1400d8cb0  js      loc_1400D915F
0x1400d8cb6  lea     rax, [r13+10h]
0x1400d8cba  mov     dword ptr [rbp+40h+var_B8], 8
0x1400d8cc1  lea     rdx, [rbp+40h+var_C0]
0x1400d8cc5  mov     [rbp+40h+var_C0], rax
0x1400d8cc9  lea     rcx, [rbp+40h+var_A8]
0x1400d8ccd  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d8cd2  test    eax, eax
0x1400d8cd4  js      loc_1400D915F
0x1400d8cda  lea     rax, [r13+18h]
0x1400d8cde  mov     dword ptr [rbp+40h+var_B8], ebx
0x1400d8ce1  lea     rdx, [rbp+40h+var_C0]
0x1400d8ce5  mov     [rbp+40h+var_C0], rax
0x1400d8ce9  lea     rcx, [rbp+40h+var_A8]
0x1400d8ced  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d8cf2  test    eax, eax
0x1400d8cf4  js      loc_1400D915F
0x1400d8cfa  lea     rax, [r13+28h]
0x1400d8cfe  mov     dword ptr [rbp+40h+var_B8], 4
0x1400d8d05  lea     rdx, [rbp+40h+var_C0]
0x1400d8d09  mov     [rbp+40h+var_C0], rax
0x1400d8d0d  lea     rcx, [rbp+40h+var_A8]
0x1400d8d11  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d8d16  test    eax, eax
0x1400d8d18  js      loc_1400D915F
0x1400d8d1e  lea     rbx, [r13+2Ch]
0x1400d8d22  lea     rdx, [rbp+40h+var_C0]
0x1400d8d26  mov     [rbp+40h+var_C0], rbx
0x1400d8d2a  lea     rcx, [rbp+40h+var_A8]
0x1400d8d2e  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d8d33  test    eax, eax
0x1400d8d35  js      loc_1400D915F
0x1400d8d3b  lea     rax, [r13+30h]
0x1400d8d3f  lea     rdx, [rbp+40h+var_C0]
0x1400d8d43  mov     [rbp+40h+var_C0], rax
0x1400d8d47  lea     rcx, [rbp+40h+var_A8]
0x1400d8d4b  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d8d50  test    eax, eax
0x1400d8d52  js      loc_1400D915F
0x1400d8d58  mov     ecx, [rbx]
0x1400d8d5a  lea     rdx, [rbp+40h+var_B0]
0x1400d8d5e  call    GetErrorCodeStringForEvent
0x1400d8d63  mov     r14, [rbp+40h+var_B0]
0x1400d8d67  mov     ebx, eax
0x1400d8d69  test    eax, eax
0x1400d8d6b  js      loc_1400D8F80
0x1400d8d71  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400d8d75  mov     [rbp+40h+var_C0], r14
0x1400d8d79  mov     rax, rsi
0x1400d8d7c  inc     rax
0x1400d8d7f  cmp     [r14+rax*2], r12w
0x1400d8d84  jnz     short loc_1400D8D7C
0x1400d8d86  lea     eax, ds:2[rax*2]
0x1400d8d8d  lea     rdx, [rbp+40h+var_C0]
0x1400d8d91  mov     dword ptr [rbp+40h+var_B8], eax
0x1400d8d94  lea     rcx, [rbp+40h+var_A8]
0x1400d8d98  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d8d9d  test    eax, eax
0x1400d8d9f  js      loc_1400D915F
0x1400d8da5  mov     rcx, [r13+38h]
0x1400d8da9  mov     rax, rsi
0x1400d8dac  mov     [rbp+40h+var_C0], rcx
0x1400d8db0  inc     rax
0x1400d8db3  cmp     [rcx+rax*2], r12w
0x1400d8db8  jnz     short loc_1400D8DB0
0x1400d8dba  lea     eax, ds:2[rax*2]
0x1400d8dc1  lea     rdx, [rbp+40h+var_C0]
0x1400d8dc5  mov     dword ptr [rbp+40h+var_B8], eax
0x1400d8dc8  lea     rcx, [rbp+40h+var_A8]
0x1400d8dcc  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d8dd1  test    eax, eax
0x1400d8dd3  js      loc_1400D915F
0x1400d8dd9  lea     rdx, [rbp+40h+var_C0]
0x1400d8ddd  mov     [rbp+40h+var_C0], r15
0x1400d8de1  lea     rcx, [rbp+40h+var_A8]
0x1400d8de5  mov     dword ptr [rbp+40h+var_B8], 4
0x1400d8dec  call    ?Add@?$CAtlArray@UBLB_TIME_EXTENT@@V?$CElementTraits@UBLB_TIME_EXTENT@@@ATL@@@ATL@@QEAA_KAEBUBLB_TIME_EXTENT@@@Z; ATL::CAtlArray<BLB_TIME_EXTENT,ATL::CElementTraits<BLB_TIME_EXTENT>>::Add(BLB_TIME_EXTENT const &)
0x1400d8df1  test    eax, eax
0x1400d8df3  js      loc_1400D915F
0x1400d8df9  mov     ebx, 1Eh
0x1400d8dfe  mov     eax, r12d
0x1400d8e01  mov     [rbp+40h+arg_0], ebx
0x1400d8e04  mov     [rbp+40h+arg_10], eax
0x1400d8e07  cmp     eax, [r15]
0x1400d8e0a  jnb     loc_1400D901C
0x1400d8e10  mov     edx, eax
0x1400d8e12  mov     rcx, rsi
0x1400d8e15  mov     rax, [r13+48h]
0x1400d8e19  mov     [rbp+40h+var_88], rdx
0x1400d8e1d  mov     r8, [rax+rdx*8]
0x1400d8e21  inc     rcx
0x1400d8e24  cmp     [r8+rcx*2], r12w
0x1400d8e29  jnz     short loc_1400D8E21
0x1400d8e2b  mov     rax, [r13+50h]
0x1400d8e2f  mov     r8, [rax+rdx*8]
0x1400d8e33  inc     rsi
0x1400d8e36  cmp     [r8+rsi*2], r12w
0x1400d8e3b  jnz     short loc_1400D8E33
0x1400d8e3d  lea     eax, [rcx+52Fh]
0x1400d8e43  add     eax, esi
0x1400d8e45  mov     ebx, eax
0x1400d8e47  mov     [rbp+40h+arg_18], eax
0x1400d8e4a  mov     [rbp+40h+var_50], rbx
0x1400d8e4e  lea     rcx, [rax+rax]; cb
0x1400d8e52  call    cs:__imp_CoTaskMemAlloc
0x1400d8e58  mov     [rbp+40h+pv], rax
0x1400d8e5c  test    rax, rax
0x1400d8e5f  jz      loc_1400D900E
0x1400d8e65  mov     r8d, ebx; Size
0x1400d8e68  xor     edx, edx; Val
0x1400d8e6a  mov     rcx, rax; void *
0x1400d8e6d  call    memset_0
0x1400d8e72  mov     r12, [rbp+40h+var_88]
0x1400d8e76  mov     rcx, [r13+0A0h]
0x1400d8e7d  mov     rdx, [r13+78h]
0x1400d8e81  mov     r8, [r13+70h]
0x1400d8e85  mov     r9, [r13+60h]
0x1400d8e89  mov     rdi, [r13+88h]
0x1400d8e90  mov     rax, [r13+0A8h]
0x1400d8e97  mov     r10, [r13+68h]
0x1400d8e9b  mov     r11, [r13+98h]
0x1400d8ea2  mov     rbx, [r13+90h]
0x1400d8ea9  mov     rax, [rax+r12*8]
0x1400d8ead  mov     rsi, [r13+80h]
0x1400d8eb4  mov     r14, [r13+58h]
0x1400d8eb8  mov     r15, [r13+50h]
0x1400d8ebc  mov     [rsp+140h+var_C8], rax
0x1400d8ec1  mov     rax, [rcx+r12*8]
0x1400d8ec5  mov     rcx, r12
0x1400d8ec8  mov     [rsp+140h+var_D0], rax
0x1400d8ecd  mov     eax, [rdx+r12*4]
0x1400d8ed1  mov     rdx, [rbp+40h+var_50]; unsigned __int64
0x1400d8ed5  mov     dword ptr [rsp+140h+var_D8], eax
0x1400d8ed9  mov     eax, [r8+r12*4]
0x1400d8edd  lea     r8, aVolumeinfoitem; "<VolumeInfoItem Name=\"%ws\" RecoveryTa"...
0x1400d8ee4  mov     dword ptr [rsp+140h+var_E0], eax
0x1400d8ee8  mov     eax, [r9+r12*4]
0x1400d8eec  mov     dword ptr [rsp+140h+var_E8], eax
0x1400d8ef0  mov     eax, [r10+r12*4]
0x1400d8ef4  mov     dword ptr [rsp+140h+var_F0], eax
0x1400d8ef8  mov     rax, [r11+r12*8]
0x1400d8efc  mov     [rsp+140h+var_F8], rax
0x1400d8f01  mov     rax, [rbx+r12*8]
0x1400d8f05  mov     [rsp+140h+var_100], rax
0x1400d8f0a  mov     eax, [rdi+r12*4]
0x1400d8f0e  mov     rdi, [rbp+40h+pv]
0x1400d8f12  mov     dword ptr [rsp+140h+var_108], eax
0x1400d8f16  mov     eax, [rsi+r12*4]
0x1400d8f1a  mov     dword ptr [rsp+140h+var_110], eax
0x1400d8f1e  mov     eax, [r14+r12*4]
0x1400d8f22  mov     dword ptr [rsp+140h+var_118], eax
0x1400d8f26  mov     rax, [r15+r12*8]
0x1400d8f2a  mov     r12, [r13+48h]
0x1400d8f2e  mov     [rsp+140h+var_120], rax
0x1400d8f33  mov     r9, [r12+rcx*8]
0x1400d8f37  mov     rcx, rdi; unsigned __int16 *
0x1400d8f3a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400d8f3f  xor     r12d, r12d
0x1400d8f42  mov     ebx, eax
0x1400d8f44  test    eax, eax
0x1400d8f46  js      short loc_1400D8F70
0x1400d8f48  mov     ebx, [rbp+40h+arg_0]
0x1400d8f4b  lea     rdx, [rbp+40h+pv]
0x1400d8f4f  add     ebx, [rbp+40h+arg_18]
0x1400d8f52  lea     rcx, [rbp+40h+var_80]
0x1400d8f56  mov     [rbp+40h+arg_0], ebx
0x1400d8f59  call    ?Add@?$CAtlArray@PEAV?$CComObject@VCBlbComponentRestoreContext@@@ATL@@V?$CElementTraits@PEAV?$CComObject@VCBlbComponentRestoreContext@@@ATL@@@2@@ATL@@QEAA_KAEBQEAV?$CComObject@VCBlbComponentRestoreContext@@@2@@Z; ATL::CAtlArray<ATL::CComObject<CBlbComponentRestoreContext> *,ATL::CElementTraits<ATL::CComObject<CBlbComponentRestoreContext> *>>::Add(ATL::CComObject<CBlbComponentRestoreContext> * const &)
0x1400d8f5e  mov     eax, [rbp+40h+arg_10]
0x1400d8f61  lea     r15, [r13+40h]
0x1400d8f65  inc     eax
0x1400d8f67  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400d8f6b  jmp     loc_1400D8E04
0x1400d8f70  mov     rcx, rdi; pv
0x1400d8f73  call    cs:__imp_CoTaskMemFree
0x1400d8f79  mov     rdi, r12
0x1400d8f7c  mov     r14, [rbp+40h+var_B0]
0x1400d8f80  mov     esi, r12d
0x1400d8f83  cmp     [rbp+40h+var_78], r12
0x1400d8f87  jbe     short loc_1400D8FCA
0x1400d8f89  mov     edx, esi
0x1400d8f8b  lea     rcx, [rbp+40h+var_80]
0x1400d8f8f  mov     r15d, esi
0x1400d8f92  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x1400d8f97  cmp     [rax], r12
0x1400d8f9a  jz      short loc_1400D8FC0
0x1400d8f9c  mov     edx, r15d
0x1400d8f9f  lea     rcx, [rbp+40h+var_80]
0x1400d8fa3  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x1400d8fa8  mov     rcx, [rax]; pv
0x1400d8fab  call    cs:__imp_CoTaskMemFree
0x1400d8fb1  mov     edx, r15d
0x1400d8fb4  lea     rcx, [rbp+40h+var_80]
0x1400d8fb8  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x1400d8fbd  mov     [rax], r12
0x1400d8fc0  inc     esi
0x1400d8fc2  mov     eax, esi
0x1400d8fc4  cmp     rax, [rbp+40h+var_78]
0x1400d8fc8  jb      short loc_1400D8F89
0x1400d8fca  test    rdi, rdi
0x1400d8fcd  jz      short loc_1400D8FD8
0x1400d8fcf  mov     rcx, rdi; pv
0x1400d8fd2  call    cs:__imp_CoTaskMemFree
0x1400d8fd8  test    r14, r14
0x1400d8fdb  jz      short loc_1400D8FE6
0x1400d8fdd  mov     rcx, r14; pv
0x1400d8fe0  call    cs:__imp_CoTaskMemFree
0x1400d8fe6  lea     rcx, [rbp+40h+var_80]
0x1400d8fea  call    ??1?$CAtlArray@U_BLB_COMPONENT@@V?$CElementTraits@U_BLB_COMPONENT@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(void)
0x1400d8fef  lea     rcx, [rbp+40h+var_A8]
0x1400d8ff3  call    ??1?$CAtlArray@U_BLB_COMPONENT@@V?$CElementTraits@U_BLB_COMPONENT@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(void)
0x1400d8ff8  mov     eax, ebx
0x1400d8ffa  add     rsp, 108h
0x1400d9001  pop     r15
0x1400d9003  pop     r14
0x1400d9005  pop     r13
0x1400d9007  pop     r12
0x1400d9009  pop     rdi
0x1400d900a  pop     rsi
0x1400d900b  pop     rbx
0x1400d900c  pop     rbp
0x1400d900d  retn
0x1400d900e  mov     rdi, [rbp+40h+var_58]
0x1400d9012  mov     ebx, 8007000Eh
0x1400d9017  jmp     loc_1400D8F7C
0x1400d901c  mov     r14d, ebx
0x1400d901f  lea     rbx, [r14+r14]
0x1400d9023  mov     rcx, rbx; cb
0x1400d9026  call    cs:__imp_CoTaskMemAlloc
0x1400d902c  mov     rdi, rax
0x1400d902f  test    rax, rax
0x1400d9032  jnz     short loc_1400D903E
0x1400d9034  mov     ebx, 8007000Eh
0x1400d9039  jmp     loc_1400D8F7C
0x1400d903e  mov     r8, rbx; Size
0x1400d9041  xor     edx, edx; Val
0x1400d9043  mov     rcx, rdi; void *
0x1400d9046  call    memset_0
0x1400d904b  lea     r8, aVolumeinfo; "<VolumeInfo>"
0x1400d9052  mov     rdx, r14; unsigned __int64
0x1400d9055  mov     rcx, rdi; unsigned __int16 *
0x1400d9058  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400d905d  mov     ebx, eax
0x1400d905f  test    eax, eax
0x1400d9061  js      loc_1400D8F7C
0x1400d9067  mov     r15d, r12d
0x1400d906a  mov     edx, r15d
0x1400d906d  cmp     rdx, [rbp+40h+var_78]
0x1400d9071  jnb     short loc_1400D9099
0x1400d9073  lea     rcx, [rbp+40h+var_80]
0x1400d9077  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x1400d907c  mov     rdx, r14; unsigned __int64
0x1400d907f  mov     rcx, rdi; unsigned __int16 *
0x1400d9082  mov     r8, [rax]; unsigned __int16 *
0x1400d9085  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400d908a  mov     ebx, eax
0x1400d908c  test    eax, eax
  ... truncated ...
```
