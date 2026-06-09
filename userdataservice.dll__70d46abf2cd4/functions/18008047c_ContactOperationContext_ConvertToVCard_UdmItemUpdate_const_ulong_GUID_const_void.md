# ContactOperationContext::ConvertToVCard(UdmItemUpdate const *,ulong,_GUID const &,void * *)

- ea: `0x18008047c`
- end: `0x180080a6e`
- name: `?ConvertToVCard@ContactOperationContext@@QEAAJPEBUUdmItemUpdate@@KAEBU_GUID@@PEAPEAX@Z`
- size: `1522`
- prototype: `__int64 __fastcall(ContactOperationContext *__hidden this, const struct UdmItemUpdate *, unsigned int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800c77a0`

## callees

- `0x1800049f0`
- `0x180008ee8`
- `0x18000e1f8`
- `0x180018c20`
- `0x18001b340`
- `0x1800303cc`
- `0x180030948`
- `0x180035040`
- `0x180035fec`
- `0x18005f34c`
- `0x180062e54`
- `0x18008047c`
- `0x1800810a8`
- `0x1800a0b40`
- `0x1800b94cc`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008096f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800809dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008096f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800809dd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180080965`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180080965`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180080909`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180080909`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800808cc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800808cc`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x180080949`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x180080949`
- `VCardParser!CreateVCardGen` at `0x1800806ac`
- `VCardParser!CreateVCardGen` at `0x1800806ac`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800807ff`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800807ff`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180080824`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180080824`

## pseudocode

```c
__int64 __fastcall ContactOperationContext::ConvertToVCard(
        ContactOperationContext *this,
        const struct UdmItemUpdate *a2,
        unsigned int a3,
        const struct _GUID *a4,
        void **a5)
{
  __int64 v9; // rax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // r8
  unsigned int v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 (__fastcall *v17)(ContactOperationContext *, __int64, HANDLE *, _QWORD *, __int64 *); // rbx
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r9
  int v26; // eax
  unsigned int i; // ebx
  int v28; // eax
  __int64 v29; // r8
  unsigned int v30; // edi
  int v31; // eax
  __int64 v32; // r8
  HRESULT v33; // eax
  __int64 v34; // r8
  __int64 v35; // r9
  int TempFilePath; // eax
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // rcx
  HANDLE FileW; // rax
  __int64 v42; // r8
  signed int v43; // eax
  __int64 v44; // r8
  __int64 v45; // r9
  signed int LastError; // eax
  signed int v48; // eax
  __int64 v49; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v50; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v52; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+60h] [rbp-A0h] BYREF
  LPCVOID lpBuffer; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v55[3]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v56; // [rsp+A0h] [rbp-60h] BYREF
  char v57; // [rsp+A8h] [rbp-58h]
  _QWORD v58[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v59[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v60[16]; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE hFile; // [rsp+E0h] [rbp-20h] BYREF
  int v62; // [rsp+E8h] [rbp-18h]
  __int64 v63; // [rsp+F0h] [rbp-10h] BYREF
  int v64; // [rsp+F8h] [rbp-8h]
  GUID pguid; // [rsp+100h] [rbp+0h] BYREF
  OLECHAR sz[40]; // [rsp+110h] [rbp+10h] BYREF

  v58[1] = &s_Contact_PropMap;
  v58[0] = 29;
  v59[1] = &s_ContactStream_PropMap;
  *a5 = 0;
  v59[0] = 1;
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v55);
  v9 = *(_QWORD *)this;
  v56 = v55;
  v57 = 1;
  v11 = (*(__int64 (__fastcall **)(ContactOperationContext *, _QWORD *, __int64, _QWORD *))(v9 + 112))(
          this,
          v58,
          v10,
          v55);
  v13 = v11;
  if ( v11 >= 0 )
  {
    v15 = *((_QWORD *)this + 6);
    v63 = 0;
    v64 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 80LL))(v15, &v63);
    v13 = v11;
    if ( v11 < 0 )
    {
      v14 = 127;
      goto LABEL_5;
    }
    v16 = *(_QWORD *)this;
    v51 = 0;
    v17 = *(__int64 (__fastcall **)(ContactOperationContext *, __int64, HANDLE *, _QWORD *, __int64 *))(v16 + 104);
    v18 = PoomIdToContactUdmId(v60, &v63);
    hFile = *(HANDLE *)v18;
    v62 = *(_DWORD *)(v18 + 8);
    v19 = v17(this, 37, &hFile, v55, &v51);
    v13 = v19;
    if ( v19 < 0 )
    {
      Log_HREvent_17((unsigned int)v19, 1, v20, 132);
LABEL_70:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v51);
      goto LABEL_71;
    }
    ATL::CComQIPtr<IItem2,&__s_GUID const _GUID_7268d1d3_d871_4b70_b1c0_79aefc11c9df>::CComQIPtr<IItem2,&__s_GUID const _GUID_7268d1d3_d871_4b70_b1c0_79aefc11c9df>(
      &v50,
      v51);
    v22 = v50;
    if ( !v50 )
    {
      v13 = -2147467262;
      v23 = 0;
      v24 = 2147500034LL;
      v25 = 135;
LABEL_10:
      Log_HREvent_17(v24, v23, v21, v25);
LABEL_69:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v50);
      goto LABEL_70;
    }
    if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v55[1] - v55[0]) >> 3) )
    {
      v26 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v50 + 40LL))(v50, 0);
      v13 = v26;
      if ( v26 < 0 )
      {
        v23 = 1;
        v25 = 139;
        v24 = (unsigned int)v26;
        goto LABEL_10;
      }
      v22 = v50;
    }
    for ( i = 0; i < *((_DWORD *)a2 + 10); ++i )
    {
      v28 = SetStreamProperty(v22, v59, *((_QWORD *)a2 + 6) + 16LL * i);
      v30 = v28;
      if ( v28 < 0 )
      {
        Log_HREvent_17((unsigned int)v28, 1, v29, 144);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v50);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v51);
        v13 = v30;
        goto LABEL_71;
      }
      v22 = v50;
    }
    v49 = 0;
    v31 = CreateVCardGen(&v49);
    v13 = v31;
    if ( v31 < 0 )
    {
      Log_HREvent_17((unsigned int)v31, 1, v32, 148);
LABEL_68:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v49);
      goto LABEL_69;
    }
    v52 = 0;
    if ( v50 )
      (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v50)(v50, &GUID_0130d8d2_5961_4655_a29e_58895a8c2fda, &v52);
    v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 32LL))(v49);
    v13 = v33;
    if ( v33 < 0 )
    {
      v35 = 151;
LABEL_26:
      Log_HREvent_17((unsigned int)v33, 1, v34, v35);
LABEL_67:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v52);
      goto LABEL_68;
    }
    v33 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 24LL))(v49, 0);
    v13 = v33;
    if ( v33 < 0 )
    {
      v35 = 152;
      goto LABEL_26;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 48LL))(v49, 6);
    v33 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 40LL))(v49, 3);
    v13 = v33;
    if ( v33 < 0 )
    {
      v35 = 154;
      goto LABEL_26;
    }
    v33 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v49 + 72LL))(v49, a3);
    v13 = v33;
    if ( v33 < 0 )
    {
      v35 = 155;
      goto LABEL_26;
    }
    v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 80LL))(v49);
    v13 = v33;
    if ( v33 < 0 )
    {
      v35 = 156;
      goto LABEL_26;
    }
    lpBuffer = 0;
    v33 = (*(__int64 (__fastcall **)(__int64, LPCVOID *))(*(_QWORD *)v49 + 88LL))(v49, &lpBuffer);
    v13 = v33;
    if ( v33 < 0 )
    {
      v35 = 159;
      goto LABEL_26;
    }
    pguid = 0;
    v33 = CoCreateGuid(&pguid);
    v13 = v33;
    if ( v33 < 0 )
    {
      v35 = 162;
      goto LABEL_26;
    }
    StringFromGUID2(&pguid, sz, 39);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpFileName);
    TempFilePath = GetTempFilePath((__int64)lpFileName);
    v13 = TempFilePath;
    if ( TempFilePath < 0 )
    {
      v38 = 168;
LABEL_41:
      v39 = 1;
      v40 = (unsigned int)TempFilePath;
LABEL_60:
      Log_HREvent_17(v40, v39, v37, v38);
LABEL_66:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
      goto LABEL_67;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             lpFileName,
                             sz) )
    {
      v13 = -2147024882;
      v38 = 169;
      goto LABEL_59;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             lpFileName,
                             L".tmp") )
    {
      v13 = -2147024882;
      v38 = 170;
      goto LABEL_59;
    }
    hFile = 0;
    FileW = CreateFileW(lpFileName[0], 0x40000000u, 7u, 0, 2u, 0, 0);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::reset(&hFile, FileW);
    if ( hFile )
    {
      v42 = -1;
      do
        ++v42;
      while ( *((_BYTE *)lpBuffer + v42) );
      if ( WriteFile(hFile, lpBuffer, v42, 0, 0) )
      {
        tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&hFile);
        TempFilePath = CreateRandomAccessStreamOnFile(lpFileName[0], 1, a4, a5);
        v13 = TempFilePath;
        if ( TempFilePath < 0 )
        {
          v38 = 194;
          goto LABEL_41;
        }
        if ( DeleteFileW(lpFileName[0]) )
        {
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v52);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v49);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v50);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v51);
          tlx::_UndoSolo__lambda_333678605516086a1f1a94676e90df95___::__UndoSolo__lambda_333678605516086a1f1a94676e90df95___(&v56);
          utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v55);
          return 0;
        }
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        v38 = 196;
LABEL_59:
        v39 = 0;
        v40 = v13;
        goto LABEL_60;
      }
      v43 = GetLastError();
      v13 = v43;
      if ( v43 > 0 )
        v13 = (unsigned __int16)v43 | 0x80070000;
      v45 = 185;
    }
    else
    {
      v48 = GetLastError();
      v13 = v48;
      if ( v48 > 0 )
        v13 = (unsigned __int16)v48 | 0x80070000;
      v45 = 184;
    }
    Log_HREvent_17(v13, 0, v44, v45);
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&hFile);
    goto LABEL_66;
  }
  v14 = 124;
LABEL_5:
  Log_HREvent_17((unsigned int)v11, 1, v12, v14);
LABEL_71:
  tlx::_UndoSolo__lambda_333678605516086a1f1a94676e90df95___::__UndoSolo__lambda_333678605516086a1f1a94676e90df95___(&v56);
  utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v55);
  return v13;
}

```

## disassembly

```asm
0x18008047c  push    rbp
0x18008047e  push    rbx
0x18008047f  push    rsi
0x180080480  push    rdi
0x180080481  push    r12
0x180080483  push    r14
0x180080485  push    r15
0x180080487  lea     rbp, [rsp-70h]
0x18008048c  sub     rsp, 170h
0x180080493  mov     rax, cs:__security_cookie
0x18008049a  xor     rax, rsp
0x18008049d  mov     [rbp+0A0h+var_40], rax
0x1800804a1  mov     r15, [rbp+0A0h+arg_20]
0x1800804a8  lea     rax, ?s_Contact_PropMap@@3QBUUdmPoomPropIdMap@@B; UdmPoomPropIdMap const near * const s_Contact_PropMap
0x1800804af  mov     [rbp+0A0h+var_E8], rax
0x1800804b3  mov     rdi, rcx
0x1800804b6  lea     rax, ?s_ContactStream_PropMap@@3QBUUdmPoomPropIdMap@@B; UdmPoomPropIdMap const near * const s_ContactStream_PropMap
0x1800804bd  mov     [rbp+0A0h+var_F0], 1Dh
0x1800804c5  lea     rcx, [rbp+0A0h+var_118]
0x1800804c9  mov     [rbp+0A0h+var_D8], rax
0x1800804cd  mov     qword ptr [r15], 0
0x1800804d4  mov     r12, r9
0x1800804d7  mov     r14d, r8d
0x1800804da  mov     [rbp+0A0h+var_E0], 1
0x1800804e2  mov     rsi, rdx
0x1800804e5  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800804ea  mov     rax, [rdi]
0x1800804ed  lea     rcx, [rbp+0A0h+var_118]
0x1800804f1  mov     [rbp+0A0h+var_100], rcx
0x1800804f5  lea     r9, [rbp+0A0h+var_118]
0x1800804f9  mov     r8, rdx
0x1800804fc  mov     [rbp+0A0h+var_F8], 1
0x180080500  lea     rdx, [rbp+0A0h+var_F0]
0x180080504  mov     rcx, rdi
0x180080507  mov     rax, [rax+70h]
0x18008050b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080510  mov     ebx, eax
0x180080512  test    eax, eax
0x180080514  jns     short loc_18008051E
0x180080516  mov     r9d, 7Ch ; '|'
0x18008051c  jmp     short loc_180080547
0x18008051e  mov     rcx, [rdi+30h]
0x180080522  lea     rdx, [rbp+0A0h+var_B0]
0x180080526  xor     eax, eax
0x180080528  mov     [rbp+0A0h+var_B0], rax
0x18008052c  mov     [rbp+0A0h+var_A8], eax
0x18008052f  mov     rax, [rcx]
0x180080532  mov     rax, [rax+50h]
0x180080536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008053b  mov     ebx, eax
0x18008053d  test    eax, eax
0x18008053f  jns     short loc_180080558
0x180080541  mov     r9d, 7Fh
0x180080547  mov     edx, 1
0x18008054c  mov     ecx, eax
0x18008054e  call    Log_HREvent_17
0x180080553  jmp     loc_180080A3C
0x180080558  mov     rax, [rdi]
0x18008055b  lea     rdx, [rbp+0A0h+var_B0]
0x18008055f  lea     rcx, [rbp+0A0h+var_D0]
0x180080563  mov     [rsp+1A0h+var_150], 0
0x18008056c  mov     rbx, [rax+68h]
0x180080570  call    ?PoomIdToContactUdmId@@YA?AUUdmObjectId@@AEBUOLITEMID@@@Z; PoomIdToContactUdmId(OLITEMID const &)
0x180080575  lea     r9, [rbp+0A0h+var_118]
0x180080579  mov     rcx, rdi
0x18008057c  lea     r8, [rbp+0A0h+hFile]
0x180080580  movsd   xmm0, qword ptr [rax]
0x180080584  movsd   [rbp+0A0h+hFile], xmm0
0x180080589  mov     edx, [rax+8]
0x18008058c  lea     rax, [rsp+1A0h+var_150]
0x180080591  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rax
0x180080596  mov     rax, rbx
0x180080599  mov     [rbp+0A0h+var_B8], edx
0x18008059c  mov     edx, 25h ; '%'
0x1800805a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800805a6  mov     ebx, eax
0x1800805a8  test    eax, eax
0x1800805aa  jns     short loc_1800805C3
0x1800805ac  mov     edx, 1
0x1800805b1  mov     r9d, 84h
0x1800805b7  mov     ecx, eax
0x1800805b9  call    Log_HREvent_17
0x1800805be  jmp     loc_180080A32
0x1800805c3  mov     rdx, [rsp+1A0h+var_150]
0x1800805c8  lea     rcx, [rsp+1A0h+var_158]
0x1800805cd  call    ??0?$CComQIPtr@UIItem2@@$1?_GUID_7268d1d3_d871_4b70_b1c0_79aefc11c9df@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IItem2,&__s_GUID const _GUID_7268d1d3_d871_4b70_b1c0_79aefc11c9df>::CComQIPtr<IItem2,&__s_GUID const _GUID_7268d1d3_d871_4b70_b1c0_79aefc11c9df>(IUnknown *)
0x1800805d2  mov     rcx, [rsp+1A0h+var_158]
0x1800805d7  test    rcx, rcx
0x1800805da  jnz     short loc_1800805F5
0x1800805dc  mov     ebx, 80004002h
0x1800805e1  xor     edx, edx
0x1800805e3  mov     ecx, ebx
0x1800805e5  mov     r9d, 87h
0x1800805eb  call    Log_HREvent_17
0x1800805f0  jmp     loc_180080A28
0x1800805f5  mov     r8, [rbp+0A0h+var_110]
0x1800805f9  mov     rax, 0AAAAAAAAAAAAAAABh
0x180080603  mov     r9, [rbp+0A0h+var_118]
0x180080607  sub     r8, r9
0x18008060a  sar     r8, 3
0x18008060e  imul    r8, rax
0x180080612  test    r8, r8
0x180080615  jz      short loc_18008063F
0x180080617  mov     rax, [rcx]
0x18008061a  xor     edx, edx
0x18008061c  mov     rax, [rax+28h]
0x180080620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080625  mov     ebx, eax
0x180080627  test    eax, eax
0x180080629  jns     short loc_18008063A
0x18008062b  mov     edx, 1
0x180080630  mov     r9d, 8Bh
0x180080636  mov     ecx, eax
0x180080638  jmp     short loc_1800805EB
0x18008063a  mov     rcx, [rsp+1A0h+var_158]
0x18008063f  xor     ebx, ebx
0x180080641  lea     edi, [rbx+1]
0x180080644  cmp     ebx, [rsi+28h]
0x180080647  jnb     short loc_18008069E
0x180080649  mov     r8d, ebx
0x18008064c  lea     rdx, [rbp+0A0h+var_E0]
0x180080650  shl     r8, 4
0x180080654  add     r8, [rsi+30h]
0x180080658  call    ?SetStreamProperty@@YAJPEAUIItem2@@AEBV?$Vector@$$CBUUdmPoomPropIdMap@@@Udm@@PEAUUdmStreamPropertyValue@@@Z; SetStreamProperty(IItem2 *,Udm::Vector<UdmPoomPropIdMap const> const &,UdmStreamPropertyValue *)
0x18008065d  mov     edi, eax
0x18008065f  test    eax, eax
0x180080661  js      short loc_180080671
0x180080663  mov     rcx, [rsp+1A0h+var_158]
0x180080668  mov     edi, 1
0x18008066d  add     ebx, edi
0x18008066f  jmp     short loc_180080644
0x180080671  mov     edx, 1
0x180080676  mov     r9d, 90h
0x18008067c  mov     ecx, edi
0x18008067e  call    Log_HREvent_17
0x180080683  lea     rcx, [rsp+1A0h+var_158]
0x180080688  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18008068d  lea     rcx, [rsp+1A0h+var_150]
0x180080692  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180080697  mov     ebx, edi
0x180080699  jmp     loc_180080A3C
0x18008069e  lea     rcx, [rsp+1A0h+var_160]
0x1800806a3  mov     [rsp+1A0h+var_160], 0
0x1800806ac  call    cs:__imp_CreateVCardGen
0x1800806b2  mov     ebx, eax
0x1800806b4  test    eax, eax
0x1800806b6  jns     short loc_1800806CC
0x1800806b8  mov     r9d, 94h
0x1800806be  mov     edx, edi
0x1800806c0  mov     ecx, eax
0x1800806c2  call    Log_HREvent_17
0x1800806c7  jmp     loc_180080A1E
0x1800806cc  mov     rcx, [rsp+1A0h+var_158]
0x1800806d1  xor     edx, edx
0x1800806d3  mov     [rsp+1A0h+var_148], rdx
0x1800806d8  test    rcx, rcx
0x1800806db  jz      short loc_1800806F9
0x1800806dd  mov     rax, [rcx]
0x1800806e0  lea     r8, [rsp+1A0h+var_148]
0x1800806e5  lea     rdx, _GUID_0130d8d2_5961_4655_a29e_58895a8c2fda
0x1800806ec  mov     rax, [rax]
0x1800806ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800806f4  mov     rdx, [rsp+1A0h+var_148]
0x1800806f9  mov     rcx, [rsp+1A0h+var_160]
0x1800806fe  mov     rax, [rcx]
0x180080701  mov     rax, [rax+20h]
0x180080705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008070a  mov     ebx, eax
0x18008070c  test    eax, eax
0x18008070e  jns     short loc_180080724
0x180080710  mov     r9d, 97h
0x180080716  mov     edx, edi
0x180080718  mov     ecx, eax
0x18008071a  call    Log_HREvent_17
0x18008071f  jmp     loc_180080A14
0x180080724  mov     rcx, [rsp+1A0h+var_160]
0x180080729  xor     edx, edx
0x18008072b  mov     rax, [rcx]
0x18008072e  mov     rax, [rax+18h]
0x180080732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080737  mov     ebx, eax
0x180080739  test    eax, eax
0x18008073b  jns     short loc_180080745
0x18008073d  mov     r9d, 98h
0x180080743  jmp     short loc_180080716
0x180080745  mov     rcx, [rsp+1A0h+var_160]
0x18008074a  mov     edx, 6
0x18008074f  mov     rax, [rcx]
0x180080752  mov     rax, [rax+30h]
0x180080756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008075b  mov     rcx, [rsp+1A0h+var_160]
0x180080760  mov     edx, 3
0x180080765  mov     rax, [rcx]
0x180080768  mov     rax, [rax+28h]
0x18008076c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080771  mov     ebx, eax
0x180080773  test    eax, eax
0x180080775  jns     short loc_18008077F
0x180080777  mov     r9d, 9Ah
0x18008077d  jmp     short loc_180080716
0x18008077f  mov     rcx, [rsp+1A0h+var_160]
0x180080784  mov     edx, r14d
0x180080787  mov     rax, [rcx]
0x18008078a  mov     rax, [rax+48h]
0x18008078e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080793  mov     ebx, eax
0x180080795  test    eax, eax
0x180080797  jns     short loc_1800807A4
0x180080799  mov     r9d, 9Bh
0x18008079f  jmp     loc_180080716
0x1800807a4  mov     rcx, [rsp+1A0h+var_160]
0x1800807a9  mov     rax, [rcx]
0x1800807ac  mov     rax, [rax+50h]
0x1800807b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800807b5  mov     ebx, eax
0x1800807b7  test    eax, eax
0x1800807b9  jns     short loc_1800807C6
0x1800807bb  mov     r9d, 9Ch
0x1800807c1  jmp     loc_180080716
0x1800807c6  mov     rcx, [rsp+1A0h+var_160]
0x1800807cb  lea     rdx, [rbp+0A0h+lpBuffer]
0x1800807cf  mov     [rbp+0A0h+lpBuffer], 0
0x1800807d7  mov     rax, [rcx]
0x1800807da  mov     rax, [rax+58h]
0x1800807de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800807e3  mov     ebx, eax
0x1800807e5  test    eax, eax
0x1800807e7  jns     short loc_1800807F4
0x1800807e9  mov     r9d, 9Fh
0x1800807ef  jmp     loc_180080716
0x1800807f4  xorps   xmm0, xmm0
0x1800807f7  lea     rcx, [rbp+0A0h+pguid]; pguid
0x1800807fb  movups  xmmword ptr [rbp+0A0h+pguid.Data1], xmm0
0x1800807ff  call    cs:__imp_CoCreateGuid
0x180080805  mov     ebx, eax
0x180080807  test    eax, eax
0x180080809  jns     short loc_180080816
0x18008080b  mov     r9d, 0A2h
0x180080811  jmp     loc_180080716
0x180080816  mov     r8d, 27h ; '''; cchMax
0x18008081c  lea     rdx, [rbp+0A0h+sz]; lpsz
0x180080820  lea     rcx, [rbp+0A0h+pguid]; rguid
0x180080824  call    cs:__imp_StringFromGUID2
0x18008082a  lea     rcx, [rsp+1A0h+lpFileName]; void *
0x18008082f  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180080834  lea     rcx, [rsp+1A0h+lpFileName]
0x180080839  call    ?GetTempFilePath@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetTempFilePath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18008083e  mov     ebx, eax
0x180080840  test    eax, eax
0x180080842  jns     short loc_180080853
0x180080844  mov     r9d, 0A8h
0x18008084a  mov     edx, edi
0x18008084c  mov     ecx, eax
0x18008084e  jmp     loc_18008098E
0x180080853  lea     rdx, [rbp+0A0h+sz]
0x180080857  lea     rcx, [rsp+1A0h+lpFileName]
0x18008085c  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180080861  test    al, al
0x180080863  jnz     short loc_180080875
0x180080865  mov     ebx, 8007000Eh
0x18008086a  mov     r9d, 0A9h
0x180080870  jmp     loc_18008098A
0x180080875  lea     rdx, aTmp; ".tmp"
0x18008087c  lea     rcx, [rsp+1A0h+lpFileName]
0x180080881  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180080886  test    al, al
0x180080888  jnz     short loc_18008089A
0x18008088a  mov     ebx, 8007000Eh
0x18008088f  mov     r9d, 0AAh
0x180080895  jmp     loc_18008098A
0x18008089a  mov     rcx, [rsp+1A0h+lpFileName]; lpFileName
0x18008089f  xor     r9d, r9d; lpSecurityAttributes
0x1800808a2  mov     [rsp+1A0h+hTemplateFile], 0; hTemplateFile
0x1800808ab  mov     edx, 40000000h; dwDesiredAccess
0x1800808b0  mov     [rsp+1A0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800808b8  mov     [rbp+0A0h+hFile], 0
0x1800808c0  lea     r8d, [r9+7]; dwShareMode
0x1800808c4  mov     [rsp+1A0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800808cc  call    cs:__imp_CreateFileW
0x1800808d2  mov     rdx, rax
0x1800808d5  lea     rcx, [rbp+0A0h+hFile]
0x1800808d9  call    ?reset@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@QEAAXPEAX@Z; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::reset(void *)
0x1800808de  mov     rcx, [rbp+0A0h+hFile]; hFile
0x1800808e2  test    rcx, rcx
0x1800808e5  jz      loc_1800809DD
0x1800808eb  mov     rdx, [rbp+0A0h+lpBuffer]; lpBuffer
0x1800808ef  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800808f3  inc     r8; nNumberOfBytesToWrite
0x1800808f6  cmp     byte ptr [rdx+r8], 0
0x1800808fb  jnz     short loc_1800808F3
0x1800808fd  xor     r9d, r9d; lpNumberOfBytesWritten
0x180080900  mov     qword ptr [rsp+1A0h+dwCreationDisposition], 0; lpOverlapped
0x180080909  call    cs:__imp_WriteFile
0x18008090f  test    eax, eax
0x180080911  jnz     short loc_180080933
0x180080913  call    cs:__imp_GetLastError
0x180080919  mov     ebx, eax
0x18008091b  test    eax, eax
0x18008091d  jle     short loc_180080928
0x18008091f  movzx   ebx, ax
  ... truncated ...
```
