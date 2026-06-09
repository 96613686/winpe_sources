# ContactOperationContext::VCardToContact(IStream *,ulong,ulong const * const,ulong *,UdmPropertyValue * *,_GUID const &,void * *)

- ea: `0x18007fef0`
- end: `0x180080372`
- name: `?VCardToContact@ContactOperationContext@@QEAAJPEAUIStream@@KQEBKPEAKPEAPEAUUdmPropertyValue@@AEBU_GUID@@PEAPEAX@Z`
- size: `1154`
- prototype: `__int64 __fastcall(ContactOperationContext *__hidden this, struct IStream *, unsigned int, const unsigned int *const, unsigned int *, struct UdmPropertyValue **, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800c7ab0`

## callees

- `0x1800049f0`
- `0x180008ee8`
- `0x18000e1f8`
- `0x180012988`
- `0x180018c20`
- `0x18001b340`
- `0x180025b60`
- `0x180027f60`
- `0x180035040`
- `0x180062674`
- `0x18007fef0`
- `0x1800810a8`
- `0x1800a0b40`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180080056`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180080136`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180080056`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180080136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008025b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800802ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008025b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800802ab`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800802a1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800802a1`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180080251`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180080251`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x180080286`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateRandomAccessStreamOnFile` at `0x180080286`
- `VCardParser!CreateCardParser` at `0x18007ff5f`
- `VCardParser!CreateCardParser` at `0x18007ff5f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800801ac`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800801ac`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800801ce`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800801ce`

## pseudocode

```c
__int64 __fastcall ContactOperationContext::VCardToContact(
        ContactOperationContext *this,
        struct IStream *a2,
        unsigned int a3,
        const unsigned int *a4,
        unsigned int *a5,
        struct UdmPropertyValue **a6,
        const struct _GUID *a7,
        void **a8)
{
  __int64 v11; // r14
  int v12; // eax
  __int64 v13; // r8
  unsigned int v14; // ebx
  int v15; // eax
  __int64 v16; // r8
  int v17; // eax
  __int64 v18; // r8
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64, _QWORD, void **, int *, HANDLE); // rdi
  HANDLE ProcessHeap; // rbx
  void **v22; // rax
  __int64 v23; // r15
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rsi
  __int64 (__fastcall *v28)(__int64, int *, __int64, __int64, void **, int *, HANDLE); // rdi
  HANDLE v29; // rbx
  void **v30; // rax
  HRESULT v31; // eax
  __int64 v32; // r8
  __int64 v33; // r9
  int TempFilePath; // eax
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // rdx
  __int64 v38; // rcx
  signed int LastError; // eax
  signed int v40; // eax
  __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  void *v43; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR *v44; // [rsp+50h] [rbp-B0h] BYREF
  int v45; // [rsp+58h] [rbp-A8h] BYREF
  int v46; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v47; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v48[3]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpNewFileName[4]; // [rsp+80h] [rbp-80h] BYREF
  int v50; // [rsp+A0h] [rbp-60h] BYREF
  struct UdmPropertyValue **v51; // [rsp+A8h] [rbp-58h]
  unsigned int *v52; // [rsp+B0h] [rbp-50h]
  const struct _GUID *v53; // [rsp+B8h] [rbp-48h]
  _QWORD v54[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v55; // [rsp+D0h] [rbp-30h] BYREF
  const unsigned int *v56; // [rsp+D8h] [rbp-28h]
  GUID pguid; // [rsp+E0h] [rbp-20h] BYREF
  OLECHAR sz[40]; // [rsp+F0h] [rbp-10h] BYREF

  v52 = a5;
  v51 = a6;
  v53 = a7;
  v11 = a3;
  *a8 = 0;
  v47 = 0;
  v12 = CreateCardParser(&v47);
  v14 = v12;
  if ( v12 < 0 )
  {
    Log_HREvent_17((unsigned int)v12, 1, v13, 25);
LABEL_43:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v47);
    return v14;
  }
  v46 = 0;
  v42 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, struct IStream *, _QWORD, int *, __int64 *))(*(_QWORD *)v47 + 40LL))(
          v47,
          a2,
          0,
          &v46,
          &v42);
  v14 = v15;
  if ( v15 < 0 )
  {
    Log_HREvent_17((unsigned int)v15, 1, v16, 29);
LABEL_42:
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v42);
    goto LABEL_43;
  }
  if ( v42 && v46 == 2 )
  {
    utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v48);
    v54[1] = a4;
    v54[0] = v11;
    v55 = v11;
    lpNewFileName[0] = (LPCWSTR)29;
    lpNewFileName[1] = (LPCWSTR)&s_Contact_PropMap;
    v56 = a4;
    v17 = UdmPropIdsToPoomPropIds(this, &v55, lpNewFileName, v48);
    v14 = v17;
    if ( v17 < 0 )
    {
      Log_HREvent_17((unsigned int)v17, 1, v18, 39);
LABEL_41:
      utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v48);
      goto LABEL_42;
    }
    v19 = v42;
    v45 = 0;
    v43 = 0;
    v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, void **, int *, HANDLE))(*(_QWORD *)v42 + 32LL);
    ProcessHeap = GetProcessHeap();
    v22 = tlx::replace<UdmPropertyValue,&void _MidlFreer<UdmPropertyValue>(UdmPropertyValue *)>(&v43);
    v23 = (__int64)(v48[1] - v48[0]) >> 2;
    v24 = v20(v19, v48[0], 1, (unsigned __int16)v23, v22, &v45, ProcessHeap);
    v14 = v24;
    if ( v24 < 0 )
    {
      v26 = 50;
LABEL_11:
      Log_HREvent_17((unsigned int)v24, 1, v25, v26);
LABEL_40:
      auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v43);
      goto LABEL_41;
    }
    *(_QWORD *)&pguid.Data1 = v23;
    v55 = 0;
    LODWORD(v56) = 0;
    *(_QWORD *)pguid.Data4 = v43;
    v24 = PoomPropsToUdmProps(
            (unsigned int)v54,
            (unsigned int)lpNewFileName,
            (unsigned int)&pguid,
            (_DWORD)this,
            (__int64)&v55,
            (__int64)v52,
            (__int64)v51);
    v14 = v24;
    if ( v24 < 0 )
    {
      v26 = 59;
      goto LABEL_11;
    }
    v27 = v42;
    v50 = 16449567;
    v44 = 0;
    v45 = 0;
    v28 = *(__int64 (__fastcall **)(__int64, int *, __int64, __int64, void **, int *, HANDLE))(*(_QWORD *)v42 + 32LL);
    v29 = GetProcessHeap();
    v30 = tlx::replace<UdmPropertyValue,&void _MidlFreer<UdmPropertyValue>(UdmPropertyValue *)>((void **)&v44);
    v31 = v28(v27, &v50, 1, 1, v30, &v45, v29);
    v14 = v31;
    if ( v31 < 0 )
    {
      v33 = 72;
LABEL_16:
      Log_HREvent_17((unsigned int)v31, 1, v32, v33);
LABEL_39:
      auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v44);
      goto LABEL_40;
    }
    if ( (*((_WORD *)v44 + 3) & 0x300) == 0 )
    {
      pguid = 0;
      v31 = CoCreateGuid(&pguid);
      v14 = v31;
      if ( v31 < 0 )
      {
        v33 = 77;
        goto LABEL_16;
      }
      StringFromGUID2(&pguid, sz, 39);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpNewFileName);
      TempFilePath = GetTempFilePath((__int64)lpNewFileName);
      v14 = TempFilePath;
      if ( TempFilePath < 0 )
      {
        v36 = 83;
LABEL_22:
        v37 = 1;
        v38 = (unsigned int)TempFilePath;
LABEL_38:
        Log_HREvent_17(v38, v37, v35, v36);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpNewFileName);
        goto LABEL_39;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               lpNewFileName,
                               sz) )
      {
        v14 = -2147024882;
        v36 = 84;
LABEL_37:
        v38 = v14;
        v37 = 0;
        goto LABEL_38;
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               lpNewFileName,
                               L".tmp") )
      {
        v14 = -2147024882;
        v36 = 85;
        goto LABEL_37;
      }
      if ( !CopyFileW(v44[1], lpNewFileName[0], 0) )
      {
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        v36 = 87;
        goto LABEL_37;
      }
      TempFilePath = CreateRandomAccessStreamOnFile(lpNewFileName[0], 1, v53, a8);
      v14 = TempFilePath;
      if ( TempFilePath < 0 )
      {
        v36 = 95;
        goto LABEL_22;
      }
      if ( !DeleteFileW(lpNewFileName[0]) )
      {
        v40 = GetLastError();
        v14 = v40;
        if ( v40 > 0 )
          v14 = (unsigned __int16)v40 | 0x80070000;
        v36 = 97;
        goto LABEL_37;
      }
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpNewFileName);
    }
    auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v44);
    auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v43);
    utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v48);
  }
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v42);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v47);
  return 0;
}

```

## disassembly

```asm
0x18007fef0  mov     [rsp-8+arg_10], rbx
0x18007fef5  push    rbp
0x18007fef6  push    rsi
0x18007fef7  push    rdi
0x18007fef8  push    r12
0x18007fefa  push    r13
0x18007fefc  push    r14
0x18007fefe  push    r15
0x18007ff00  lea     rbp, [rsp-50h]
0x18007ff05  sub     rsp, 150h
0x18007ff0c  mov     rax, cs:__security_cookie
0x18007ff13  xor     rax, rsp
0x18007ff16  mov     [rbp+80h+var_40], rax
0x18007ff1a  mov     rax, [rbp+80h+arg_20]
0x18007ff21  mov     r12, rcx
0x18007ff24  mov     r13, [rbp+80h+arg_38]
0x18007ff2b  lea     rcx, [rsp+180h+var_120]
0x18007ff30  mov     [rbp+80h+var_D0], rax
0x18007ff34  xor     r15d, r15d
0x18007ff37  mov     rax, [rbp+80h+arg_28]
0x18007ff3e  mov     rdi, r9
0x18007ff41  mov     [rbp+80h+var_D8], rax
0x18007ff45  mov     rsi, rdx
0x18007ff48  mov     rax, [rbp+80h+arg_30]
0x18007ff4f  mov     [rbp+80h+var_C8], rax
0x18007ff53  mov     r14d, r8d
0x18007ff56  mov     [r13+0], r15
0x18007ff5a  mov     [rsp+180h+var_120], r15
0x18007ff5f  call    cs:__imp_CreateCardParser
0x18007ff65  mov     ebx, eax
0x18007ff67  test    eax, eax
0x18007ff69  jns     short loc_18007FF7F
0x18007ff6b  lea     edx, [r15+1]
0x18007ff6f  mov     ecx, eax
0x18007ff71  lea     r9d, [r15+19h]
0x18007ff75  call    Log_HREvent_17
0x18007ff7a  jmp     loc_180080300
0x18007ff7f  mov     rcx, [rsp+180h+var_120]
0x18007ff84  lea     rdx, [rsp+180h+var_140]
0x18007ff89  mov     [rsp+180h+var_124], r15d
0x18007ff8e  lea     r9, [rsp+180h+var_124]
0x18007ff93  mov     [rsp+180h+var_140], r15
0x18007ff98  xor     r8d, r8d
0x18007ff9b  mov     [rsp+180h+var_160], rdx
0x18007ffa0  mov     rdx, rsi
0x18007ffa3  mov     rax, [rcx]
0x18007ffa6  mov     rax, [rax+28h]
0x18007ffaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ffaf  mov     ebx, eax
0x18007ffb1  test    eax, eax
0x18007ffb3  jns     short loc_18007FFCA
0x18007ffb5  mov     edx, 1
0x18007ffba  mov     ecx, eax
0x18007ffbc  lea     r9d, [rdx+1Ch]
0x18007ffc0  call    Log_HREvent_17
0x18007ffc5  jmp     loc_1800802F6
0x18007ffca  cmp     [rsp+180h+var_140], r15
0x18007ffcf  jz      loc_180080335
0x18007ffd5  cmp     [rsp+180h+var_124], 2
0x18007ffda  jnz     loc_180080335
0x18007ffe0  lea     rcx, [rsp+180h+var_118]
0x18007ffe5  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x18007ffea  mov     rcx, r14
0x18007ffed  mov     [rbp+80h+var_B8], rdi
0x18007fff1  mov     [rbp+80h+var_C0], rcx
0x18007fff5  lea     rax, ?s_Contact_PropMap@@3QBUUdmPoomPropIdMap@@B; UdmPoomPropIdMap const near * const s_Contact_PropMap
0x18007fffc  mov     [rbp+80h+var_B0], rcx
0x180080000  lea     r9, [rsp+180h+var_118]
0x180080005  mov     rcx, r12
0x180080008  mov     [rbp+80h+lpNewFileName], 1Dh
0x180080010  lea     r8, [rbp+80h+lpNewFileName]
0x180080014  mov     [rbp+80h+var_F8], rax
0x180080018  lea     rdx, [rbp+80h+var_B0]
0x18008001c  mov     [rbp+80h+var_A8], rdi
0x180080020  call    ?UdmPropIdsToPoomPropIds@@YAJPEAVPoomOperationContext@@AEBV?$Vector@$$CBK@Udm@@AEBV?$Vector@$$CBUUdmPoomPropIdMap@@@3@PEAV?$vector@KV?$allocator@K@utl@@@utl@@@Z; UdmPropIdsToPoomPropIds(PoomOperationContext *,Udm::Vector<ulong const> const &,Udm::Vector<UdmPoomPropIdMap const> const &,utl::vector<ulong,utl::allocator<ulong>> *)
0x180080025  mov     ebx, eax
0x180080027  test    eax, eax
0x180080029  jns     short loc_180080040
0x18008002b  mov     edx, 1
0x180080030  mov     ecx, eax
0x180080032  lea     r9d, [rdx+26h]
0x180080036  call    Log_HREvent_17
0x18008003b  jmp     loc_1800802EC
0x180080040  mov     rsi, [rsp+180h+var_140]
0x180080045  mov     [rsp+180h+var_128], r15d
0x18008004a  mov     [rsp+180h+var_138], r15
0x18008004f  mov     rax, [rsi]
0x180080052  mov     rdi, [rax+20h]
0x180080056  call    cs:__imp_GetProcessHeap
0x18008005c  lea     rcx, [rsp+180h+var_138]
0x180080061  mov     rbx, rax
0x180080064  call    ??$replace@UUdmPropertyValue@@$1??$_MidlFreer@UUdmPropertyValue@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAUUdmPropertyValue@@AEAV?$auto_ptr@UUdmPropertyValue@@$1??$_MidlFreer@UUdmPropertyValue@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<UdmPropertyValue,&_MidlFreer<UdmPropertyValue>(UdmPropertyValue *)>(tlx::auto_ptr<UdmPropertyValue,&_MidlFreer<UdmPropertyValue>(UdmPropertyValue *)> &)
0x180080069  mov     rdx, [rsp+180h+var_118]
0x18008006e  lea     rcx, [rsp+180h+var_128]
0x180080073  mov     r15, [rsp+180h+var_110]
0x180080078  mov     r14d, 1
0x18008007e  sub     r15, rdx
0x180080081  mov     [rsp+180h+var_150], rbx
0x180080086  mov     [rsp+180h+var_158], rcx
0x18008008b  mov     r8d, r14d
0x18008008e  mov     [rsp+180h+var_160], rax
0x180080093  mov     rcx, rsi
0x180080096  sar     r15, 2
0x18008009a  mov     rax, rdi
0x18008009d  movzx   r9d, r15w
0x1800800a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800800a6  mov     ebx, eax
0x1800800a8  test    eax, eax
0x1800800aa  jns     short loc_1800800BF
0x1800800ac  lea     r9d, [r14+31h]
0x1800800b0  mov     edx, r14d
0x1800800b3  mov     ecx, eax
0x1800800b5  call    Log_HREvent_17
0x1800800ba  jmp     loc_1800802E2
0x1800800bf  xor     eax, eax
0x1800800c1  mov     qword ptr [rbp+80h+pguid.Data1], r15
0x1800800c5  mov     [rbp+80h+var_B0], rax
0x1800800c9  lea     r8, [rbp+80h+pguid]
0x1800800cd  mov     dword ptr [rbp+80h+var_A8], eax
0x1800800d0  lea     rdx, [rbp+80h+lpNewFileName]
0x1800800d4  mov     rax, [rsp+180h+var_138]
0x1800800d9  lea     rcx, [rbp+80h+var_C0]
0x1800800dd  mov     qword ptr [rbp+80h+pguid.Data4], rax
0x1800800e1  mov     r9, r12
0x1800800e4  mov     rax, [rbp+80h+var_D8]
0x1800800e8  mov     [rsp+180h+var_150], rax
0x1800800ed  mov     rax, [rbp+80h+var_D0]
0x1800800f1  mov     [rsp+180h+var_158], rax
0x1800800f6  lea     rax, [rbp+80h+var_B0]
0x1800800fa  mov     [rsp+180h+var_160], rax
0x1800800ff  call    ?PoomPropsToUdmProps@@YAJAEBV?$Vector@K@Udm@@AEBV?$Vector@$$CBUUdmPoomPropIdMap@@@2@AEBV?$Vector@U_SQLCEPROPVAL@@@2@PEAVPoomOperationContext@@AEBUUdmObjectId@@PEAKPEAPEAUUdmPropertyValue@@@Z; PoomPropsToUdmProps(Udm::Vector<ulong> const &,Udm::Vector<UdmPoomPropIdMap const> const &,Udm::Vector<_SQLCEPROPVAL> const &,PoomOperationContext *,UdmObjectId const &,ulong *,UdmPropertyValue * *)
0x180080104  mov     ebx, eax
0x180080106  test    eax, eax
0x180080108  jns     short loc_180080112
0x18008010a  mov     r9d, 3Bh ; ';'
0x180080110  jmp     short loc_1800800B0
0x180080112  mov     rsi, [rsp+180h+var_140]
0x180080117  mov     [rbp+80h+var_E0], 0FB001Fh
0x18008011e  mov     [rsp+180h+var_130], 0
0x180080127  mov     [rsp+180h+var_128], 0
0x18008012f  mov     rax, [rsi]
0x180080132  mov     rdi, [rax+20h]
0x180080136  call    cs:__imp_GetProcessHeap
0x18008013c  lea     rcx, [rsp+180h+var_130]
0x180080141  mov     rbx, rax
0x180080144  call    ??$replace@UUdmPropertyValue@@$1??$_MidlFreer@UUdmPropertyValue@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAUUdmPropertyValue@@AEAV?$auto_ptr@UUdmPropertyValue@@$1??$_MidlFreer@UUdmPropertyValue@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<UdmPropertyValue,&_MidlFreer<UdmPropertyValue>(UdmPropertyValue *)>(tlx::auto_ptr<UdmPropertyValue,&_MidlFreer<UdmPropertyValue>(UdmPropertyValue *)> &)
0x180080149  lea     rcx, [rsp+180h+var_128]
0x18008014e  mov     [rsp+180h+var_150], rbx
0x180080153  mov     [rsp+180h+var_158], rcx
0x180080158  lea     rdx, [rbp+80h+var_E0]
0x18008015c  mov     [rsp+180h+var_160], rax
0x180080161  mov     r9d, r14d
0x180080164  mov     rax, rdi
0x180080167  mov     r8d, r14d
0x18008016a  mov     rcx, rsi
0x18008016d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080172  mov     ebx, eax
0x180080174  test    eax, eax
0x180080176  jns     short loc_18008018D
0x180080178  mov     r9d, 48h ; 'H'
0x18008017e  mov     edx, r14d
0x180080181  mov     ecx, eax
0x180080183  call    Log_HREvent_17
0x180080188  jmp     loc_1800802D8
0x18008018d  mov     rax, [rsp+180h+var_130]
0x180080192  mov     ecx, 300h
0x180080197  test    [rax+6], cx
0x18008019b  jnz     loc_180080317
0x1800801a1  xorps   xmm0, xmm0
0x1800801a4  lea     rcx, [rbp+80h+pguid]; pguid
0x1800801a8  movups  xmmword ptr [rbp+80h+pguid.Data1], xmm0
0x1800801ac  call    cs:__imp_CoCreateGuid
0x1800801b2  mov     ebx, eax
0x1800801b4  test    eax, eax
0x1800801b6  jns     short loc_1800801C0
0x1800801b8  mov     r9d, 4Dh ; 'M'
0x1800801be  jmp     short loc_18008017E
0x1800801c0  mov     r8d, 27h ; '''; cchMax
0x1800801c6  lea     rdx, [rbp+80h+sz]; lpsz
0x1800801ca  lea     rcx, [rbp+80h+pguid]; rguid
0x1800801ce  call    cs:__imp_StringFromGUID2
0x1800801d4  lea     rcx, [rbp+80h+lpNewFileName]; void *
0x1800801d8  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800801dd  lea     rcx, [rbp+80h+lpNewFileName]
0x1800801e1  call    ?GetTempFilePath@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; GetTempFilePath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800801e6  mov     ebx, eax
0x1800801e8  test    eax, eax
0x1800801ea  jns     short loc_1800801FC
0x1800801ec  mov     r9d, 53h ; 'S'
0x1800801f2  mov     edx, r14d
0x1800801f5  mov     ecx, eax
0x1800801f7  jmp     loc_1800802CA
0x1800801fc  lea     rdx, [rbp+80h+sz]
0x180080200  lea     rcx, [rbp+80h+lpNewFileName]
0x180080204  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x180080209  test    al, al
0x18008020b  jnz     short loc_18008021D
0x18008020d  mov     ebx, 8007000Eh
0x180080212  mov     r9d, 54h ; 'T'
0x180080218  jmp     loc_1800802C6
0x18008021d  lea     rdx, aTmp; ".tmp"
0x180080224  lea     rcx, [rbp+80h+lpNewFileName]
0x180080228  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18008022d  test    al, al
0x18008022f  jnz     short loc_180080241
0x180080231  mov     ebx, 8007000Eh
0x180080236  mov     r9d, 55h ; 'U'
0x18008023c  jmp     loc_1800802C6
0x180080241  mov     rcx, [rsp+180h+var_130]
0x180080246  xor     r8d, r8d; bFailIfExists
0x180080249  mov     rdx, [rbp+80h+lpNewFileName]; lpNewFileName
0x18008024d  mov     rcx, [rcx+8]; lpExistingFileName
0x180080251  call    cs:__imp_CopyFileW
0x180080257  test    eax, eax
0x180080259  jnz     short loc_180080278
0x18008025b  call    cs:__imp_GetLastError
0x180080261  mov     ebx, eax
0x180080263  test    eax, eax
0x180080265  jle     short loc_180080270
0x180080267  movzx   ebx, ax
0x18008026a  or      ebx, 80070000h
0x180080270  mov     r9d, 57h ; 'W'
0x180080276  jmp     short loc_1800802C6
0x180080278  mov     r8, [rbp+80h+var_C8]
0x18008027c  mov     r9, r13
0x18008027f  mov     rcx, [rbp+80h+lpNewFileName]
0x180080283  mov     edx, r14d
0x180080286  call    cs:__imp_CreateRandomAccessStreamOnFile
0x18008028c  mov     ebx, eax
0x18008028e  test    eax, eax
0x180080290  jns     short loc_18008029D
0x180080292  mov     r9d, 5Fh ; '_'
0x180080298  jmp     loc_1800801F2
0x18008029d  mov     rcx, [rbp+80h+lpNewFileName]; lpFileName
0x1800802a1  call    cs:__imp_DeleteFileW
0x1800802a7  test    eax, eax
0x1800802a9  jnz     short loc_18008030E
0x1800802ab  call    cs:__imp_GetLastError
0x1800802b1  mov     ebx, eax
0x1800802b3  test    eax, eax
0x1800802b5  jle     short loc_1800802C0
0x1800802b7  movzx   ebx, ax
0x1800802ba  or      ebx, 80070000h
0x1800802c0  mov     r9d, 61h ; 'a'
0x1800802c6  mov     ecx, ebx
0x1800802c8  xor     edx, edx
0x1800802ca  call    Log_HREvent_17
0x1800802cf  lea     rcx, [rbp+80h+lpNewFileName]; void *
0x1800802d3  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800802d8  lea     rcx, [rsp+180h+var_130]
0x1800802dd  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800802e2  lea     rcx, [rsp+180h+var_138]
0x1800802e7  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800802ec  lea     rcx, [rsp+180h+var_118]
0x1800802f1  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x1800802f6  lea     rcx, [rsp+180h+var_140]
0x1800802fb  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180080300  lea     rcx, [rsp+180h+var_120]
0x180080305  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18008030a  mov     eax, ebx
0x18008030c  jmp     short loc_18008034B
0x18008030e  lea     rcx, [rbp+80h+lpNewFileName]; void *
0x180080312  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180080317  lea     rcx, [rsp+180h+var_130]
0x18008031c  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x180080321  lea     rcx, [rsp+180h+var_138]
0x180080326  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x18008032b  lea     rcx, [rsp+180h+var_118]
0x180080330  call    ?_Uninit@?$vector@UUdmEmailParticipant@@V?$allocator@UUdmEmailParticipant@@@utl@@@utl@@AEAAXXZ; utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(void)
0x180080335  lea     rcx, [rsp+180h+var_140]
0x18008033a  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18008033f  lea     rcx, [rsp+180h+var_120]
0x180080344  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180080349  xor     eax, eax
0x18008034b  mov     rcx, [rbp+80h+var_40]
0x18008034f  xor     rcx, rsp; StackCookie
0x180080352  call    __security_check_cookie
0x180080357  mov     rbx, [rsp+180h+arg_10]
0x18008035f  add     rsp, 150h
0x180080366  pop     r15
0x180080368  pop     r14
0x18008036a  pop     r13
0x18008036c  pop     r12
0x18008036e  pop     rdi
0x18008036f  pop     rsi
0x180080370  pop     rbp
0x180080371  retn
```
