# EmailHelper::HandleResponseBodies(IMessage *,IMessage *,int,int,ushort const *,UdmEmailMessageBodyKind,ushort const *)

- ea: `0x180070254`
- end: `0x180070656`
- name: `?HandleResponseBodies@EmailHelper@@YAJPEAUIMessage@@0HHPEBGW4UdmEmailMessageBodyKind@@1@Z`
- size: `1026`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18007065c`

## callees

- `0x180008ee8`
- `0x18003cda4`
- `0x18003ed7c`
- `0x18006f0a8`
- `0x180070254`
- `0x180070c10`
- `0x180071228`
- `0x1800977ac`
- `0x1800f8148`
- `0x1800f830c`
- `0x180114890`
- `0x18012e010`

## import_xrefs

- `UserDataTypeHelperUtil!CopyStream` at `0x1800703fa`
- `UserDataTypeHelperUtil!CopyStream` at `0x18007053b`
- `UserDataTypeHelperUtil!CopyStream` at `0x1800703fa`
- `UserDataTypeHelperUtil!CopyStream` at `0x18007053b`
- `UserDataTypeHelperUtil!ReadStreamContent` at `0x180070459`
- `UserDataTypeHelperUtil!ReadStreamContent` at `0x18007059e`
- `UserDataTypeHelperUtil!ReadStreamContent` at `0x180070459`
- `UserDataTypeHelperUtil!ReadStreamContent` at `0x18007059e`
- `UserDataPlatformHelperUtil!ConvertHtmlStringToPlainTextStringOneCore` at `0x18007031b`
- `UserDataPlatformHelperUtil!ConvertHtmlStringToPlainTextStringOneCore` at `0x18007031b`

## pseudocode

```c
__int64 __fastcall EmailHelper::HandleResponseBodies(
        EmailHelper *a1,
        __int64 a2,
        struct IStream **a3,
        int a4,
        void *Block,
        unsigned int a6,
        __int64 a7)
{
  __int64 v7; // rdx
  int v8; // esi
  int v9; // r14d
  const unsigned __int16 *v10; // rbx
  const unsigned __int16 *v11; // r15
  const unsigned __int16 *v12; // r12
  unsigned int v13; // edi
  __int64 v14; // r9
  __int64 v15; // rcx
  unsigned __int16 **v16; // rax
  int v17; // eax
  _QWORD *v18; // rax
  int PlainTextBody; // eax
  __int64 v20; // r8
  __int64 v21; // r9
  struct IMessageVtbl *lpVtbl; // rbx
  int v23; // eax
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rax
  int HtmlBody; // eax
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rbx
  int v31; // eax
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // rax
  struct IMessage v36; // [rsp+40h] [rbp-40h] BYREF
  __int64 v37; // [rsp+48h] [rbp-38h] BYREF
  void *v38; // [rsp+50h] [rbp-30h] BYREF
  __int64 v39; // [rsp+58h] [rbp-28h] BYREF
  __int64 v40; // [rsp+60h] [rbp-20h] BYREF
  const unsigned __int16 *v41; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v42[2]; // [rsp+70h] [rbp-10h] BYREF

  v7 = 0;
  v8 = (int)a3;
  if ( !a4 || (v9 = 0, !(_DWORD)a3) )
    v9 = 1;
  v10 = (const unsigned __int16 *)Block;
  v11 = 0;
  v42[0] = 0;
  v12 = 0;
  v41 = 0;
  if ( Block && *(_WORD *)Block )
  {
    if ( a6 )
    {
      if ( a6 != 1 )
      {
        v13 = -2147024809;
        v14 = 2459;
        v15 = 2147942487LL;
LABEL_12:
        Log_HREvent_1(v15, v7, a3, v14);
        goto LABEL_61;
      }
      v16 = (unsigned __int16 **)tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(v42);
      v17 = ConvertPlainTextStringToHtmlString(v10, v16);
      v13 = v17;
      if ( v17 < 0 )
      {
        v14 = 2452;
LABEL_11:
        v7 = 1;
        v15 = (unsigned int)v17;
        goto LABEL_12;
      }
      v11 = (const unsigned __int16 *)v42[0];
      v12 = v10;
    }
    else
    {
      v18 = tlx::replace<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v41);
      v17 = ConvertHtmlStringToPlainTextStringOneCore(v10, v18);
      v13 = v17;
      if ( v17 < 0 )
      {
        v14 = 2445;
        goto LABEL_11;
      }
      v12 = v41;
      v11 = v10;
    }
  }
  v36.lpVtbl = 0;
  PlainTextBody = EmailHelper::GetPlainTextBody(a1, &v36, a3);
  Block = 0;
  v13 = PlainTextBody;
  if ( PlainTextBody != -2147221233 )
  {
    if ( PlainTextBody < 0 )
    {
      v21 = 2470;
LABEL_20:
      Log_HREvent_1((unsigned int)PlainTextBody, 1, v20, v21);
LABEL_21:
      if ( Block )
        operator delete(Block);
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v36);
      goto LABEL_61;
    }
    lpVtbl = v36.lpVtbl;
    if ( v8 )
    {
      v39 = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int, __int64 *))(*(_QWORD *)a2 + 56LL))(
              a2,
              2185297951LL,
              0,
              0,
              3,
              &v39);
      v13 = v23;
      if ( v23 < 0 )
      {
        v25 = 2480;
LABEL_27:
        Log_HREvent_1((unsigned int)v23, 1, v24, v25);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v39);
        goto LABEL_21;
      }
      v23 = CopyStream(lpVtbl, v39);
      v13 = v23;
      if ( v23 < 0 )
      {
        v25 = 2482;
        goto LABEL_27;
      }
      v23 = (*((__int64 (__fastcall **)(struct IMessageVtbl *, _QWORD, _QWORD, _QWORD))lpVtbl->QueryInterface + 5))(
              lpVtbl,
              0,
              0,
              0);
      v13 = v23;
      if ( v23 < 0 )
      {
        v25 = 2486;
        goto LABEL_27;
      }
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v39);
    }
    if ( v9 )
    {
      v26 = tlx::replace<unsigned short,&void tlx::_delete_array<unsigned short>(unsigned short *)>((__int64)&Block);
      PlainTextBody = ReadStreamContent(lpVtbl, v26, 0xFFFFFFFFLL);
      v13 = PlainTextBody;
      if ( PlainTextBody < 0 )
      {
        v21 = 2491;
        goto LABEL_20;
      }
    }
  }
  v38 = 0;
  v37 = 0;
  HtmlBody = EmailHelper::GetHtmlBody(a1);
  v13 = HtmlBody;
  if ( HtmlBody != -2147221233 )
  {
    if ( HtmlBody < 0 )
    {
      v29 = 2500;
LABEL_39:
      Log_HREvent_1((unsigned int)HtmlBody, 1, v28, v29);
      goto LABEL_40;
    }
    v30 = v37;
    if ( v8 )
    {
      v40 = 0;
      v31 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int, __int64 *))(*(_QWORD *)a2 + 56LL))(
              a2,
              2185363487LL,
              0,
              0,
              3,
              &v40);
      v13 = v31;
      if ( v31 < 0 )
      {
        v33 = 2510;
LABEL_45:
        Log_HREvent_1((unsigned int)v31, 1, v32, v33);
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v40);
LABEL_40:
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v37);
        if ( v38 )
          operator delete(v38);
        goto LABEL_21;
      }
      v31 = CopyStream(v30, v40);
      v13 = v31;
      if ( v31 < 0 )
      {
        v33 = 2512;
        goto LABEL_45;
      }
      v31 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v30 + 40LL))(v30, 0, 0, 0);
      v13 = v31;
      if ( v31 < 0 )
      {
        v33 = 2516;
        goto LABEL_45;
      }
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v40);
    }
    if ( v9 )
    {
      v34 = tlx::replace<unsigned short,&void tlx::_delete_array<unsigned short>(unsigned short *)>((__int64)&v38);
      HtmlBody = ReadStreamContent(v30, v34, 0xFFFFFFFFLL);
      v13 = HtmlBody;
      if ( HtmlBody < 0 )
      {
        v29 = 2521;
        goto LABEL_39;
      }
    }
  }
  HtmlBody = EmailHelper::SetResponseMessageBodies(a2, v12, v11, a6, a7, Block, v38);
  v13 = HtmlBody;
  if ( HtmlBody < 0 )
  {
    v29 = 2532;
    goto LABEL_39;
  }
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v37);
  if ( v38 )
    operator delete(v38);
  if ( Block )
    operator delete(Block);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v36);
  v13 = 0;
LABEL_61:
  tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(&v41);
  tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::~auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>(v42);
  return v13;
}

```

## disassembly

```asm
0x180070254  mov     rax, rsp
0x180070257  mov     [rax+18h], rbx
0x18007025b  mov     [rax+20h], rsi
0x18007025f  mov     [rax+10h], rdx
0x180070263  mov     [rax+8], rcx
0x180070267  push    rbp
0x180070268  push    rdi
0x180070269  push    r12
0x18007026b  push    r14
0x18007026d  push    r15
0x18007026f  mov     rbp, rsp
0x180070272  sub     rsp, 80h
0x180070279  xor     edx, edx
0x18007027b  mov     esi, r8d
0x18007027e  test    r9d, r9d
0x180070281  jz      short loc_18007028B
0x180070283  mov     r14d, edx
0x180070286  test    r8d, r8d
0x180070289  jnz     short loc_180070291
0x18007028b  mov     r14d, 1
0x180070291  mov     rbx, [rbp+Block]
0x180070295  mov     r15, rdx
0x180070298  mov     [rbp+var_10], rdx
0x18007029c  mov     r12, rdx
0x18007029f  mov     [rbp+var_18], rdx
0x1800702a3  test    rbx, rbx
0x1800702a6  jz      loc_180070338
0x1800702ac  cmp     [rbx], dx
0x1800702af  jz      loc_180070338
0x1800702b5  mov     ecx, [rbp+arg_28]
0x1800702b8  test    ecx, ecx
0x1800702ba  jz      short loc_18007030C
0x1800702bc  cmp     ecx, 1
0x1800702bf  jz      short loc_1800702D0
0x1800702c1  mov     edi, 80070057h
0x1800702c6  mov     r9d, 99Bh
0x1800702cc  mov     ecx, edi
0x1800702ce  jmp     short loc_1800702F9
0x1800702d0  lea     rcx, [rbp+var_10]
0x1800702d4  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x1800702d9  mov     rdx, rax; unsigned __int16 **
0x1800702dc  mov     rcx, rbx; unsigned __int16 *
0x1800702df  call    ?ConvertPlainTextStringToHtmlString@@YAJPEBGPEAPEAG@Z; ConvertPlainTextStringToHtmlString(ushort const *,ushort * *)
0x1800702e4  xor     edx, edx
0x1800702e6  mov     edi, eax
0x1800702e8  test    eax, eax
0x1800702ea  jns     short loc_180070303
0x1800702ec  mov     r9d, 994h
0x1800702f2  mov     edx, 1
0x1800702f7  mov     ecx, eax
0x1800702f9  call    Log_HREvent_1
0x1800702fe  jmp     loc_180070626
0x180070303  mov     r15, [rbp+var_10]
0x180070307  mov     r12, rbx
0x18007030a  jmp     short loc_180070338
0x18007030c  lea     rcx, [rbp+var_18]
0x180070310  call    ??$replace@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@YAPEAPEAGAEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::replace<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> &)
0x180070315  mov     rdx, rax
0x180070318  mov     rcx, rbx
0x18007031b  call    cs:__imp_ConvertHtmlStringToPlainTextStringOneCore
0x180070321  xor     edx, edx
0x180070323  mov     edi, eax
0x180070325  test    eax, eax
0x180070327  jns     short loc_180070331
0x180070329  mov     r9d, 98Dh
0x18007032f  jmp     short loc_1800702F2
0x180070331  mov     r12, [rbp+var_18]
0x180070335  mov     r15, rbx
0x180070338  mov     rcx, [rbp+arg_0]; this
0x18007033c  mov     [rbp+var_40.lpVtbl], rdx
0x180070340  lea     rdx, [rbp+var_40]; struct IMessage *
0x180070344  call    ?GetPlainTextBody@EmailHelper@@YAJPEAUIMessage@@PEAPEAUIStream@@@Z; EmailHelper::GetPlainTextBody(IMessage *,IStream * *)
0x180070349  mov     [rbp+Block], 0
0x180070351  mov     edi, eax
0x180070353  cmp     eax, 8004010Fh
0x180070358  jz      loc_180070470
0x18007035e  test    eax, eax
0x180070360  jns     short loc_180070390
0x180070362  mov     r9d, 9A6h
0x180070368  mov     edx, 1
0x18007036d  mov     ecx, eax
0x18007036f  call    Log_HREvent_1
0x180070374  mov     rcx, [rbp+Block]; Block
0x180070378  test    rcx, rcx
0x18007037b  jz      short loc_180070382
0x18007037d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180070382  lea     rcx, [rbp+var_40]
0x180070386  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18007038b  jmp     loc_180070626
0x180070390  mov     rbx, [rbp+var_40.lpVtbl]
0x180070394  test    esi, esi
0x180070396  jz      loc_180070441
0x18007039c  mov     rcx, [rbp+arg_8]
0x1800703a0  lea     rdx, [rbp+var_28]
0x1800703a4  mov     [rsp+80h+var_58], rdx
0x1800703a9  xor     r9d, r9d
0x1800703ac  xor     r8d, r8d
0x1800703af  mov     [rbp+var_28], 0
0x1800703b7  mov     edx, 8241001Fh
0x1800703bc  mov     dword ptr [rsp+80h+var_60], 3
0x1800703c4  mov     rax, [rcx]
0x1800703c7  mov     rax, [rax+38h]
0x1800703cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800703d0  mov     edi, eax
0x1800703d2  test    eax, eax
0x1800703d4  jns     short loc_1800703F3
0x1800703d6  mov     r9d, 9B0h
0x1800703dc  mov     edx, 1
0x1800703e1  mov     ecx, eax
0x1800703e3  call    Log_HREvent_1
0x1800703e8  lea     rcx, [rbp+var_28]
0x1800703ec  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800703f1  jmp     short loc_180070374
0x1800703f3  mov     rdx, [rbp+var_28]
0x1800703f7  mov     rcx, rbx
0x1800703fa  call    cs:__imp_CopyStream
0x180070400  mov     edi, eax
0x180070402  test    eax, eax
0x180070404  jns     short loc_18007040E
0x180070406  mov     r9d, 9B2h
0x18007040c  jmp     short loc_1800703DC
0x18007040e  mov     rax, [rbx]
0x180070411  xor     r9d, r9d
0x180070414  mov     rdx, cs:qword_180141350
0x18007041b  xor     r8d, r8d
0x18007041e  mov     rcx, rbx
0x180070421  mov     rax, [rax+28h]
0x180070425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007042a  mov     edi, eax
0x18007042c  test    eax, eax
0x18007042e  jns     short loc_180070438
0x180070430  mov     r9d, 9B6h
0x180070436  jmp     short loc_1800703DC
0x180070438  lea     rcx, [rbp+var_28]
0x18007043c  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180070441  test    r14d, r14d
0x180070444  jz      short loc_180070470
0x180070446  lea     rcx, [rbp+Block]
0x18007044a  call    ??$replace@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@tlx@@YAPEAPEAGAEAV?$auto_array_ptr@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@0@@Z; tlx::replace<ushort,&tlx::_delete_array<ushort>(ushort *)>(tlx::auto_array_ptr<ushort,&tlx::_delete_array<ushort>(ushort *)> &)
0x18007044f  or      r8d, 0FFFFFFFFh
0x180070453  mov     rdx, rax
0x180070456  mov     rcx, rbx
0x180070459  call    cs:__imp_ReadStreamContent
0x18007045f  mov     edi, eax
0x180070461  test    eax, eax
0x180070463  jns     short loc_180070470
0x180070465  mov     r9d, 9BBh
0x18007046b  jmp     loc_180070368
0x180070470  mov     rcx, [rbp+arg_0]; this
0x180070474  lea     rdx, [rbp+var_38]
0x180070478  mov     [rbp+var_30], 0
0x180070480  mov     [rbp+var_38], 0
0x180070488  call    EmailHelper__GetHtmlBody
0x18007048d  mov     edi, eax
0x18007048f  cmp     eax, 8004010Fh
0x180070494  jz      loc_1800705B5
0x18007049a  test    eax, eax
0x18007049c  jns     short loc_1800704D0
0x18007049e  mov     r9d, 9C4h
0x1800704a4  mov     edx, 1
0x1800704a9  mov     ecx, eax
0x1800704ab  call    Log_HREvent_1
0x1800704b0  lea     rcx, [rbp+var_38]
0x1800704b4  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800704b9  mov     rcx, [rbp+var_30]; Block
0x1800704bd  test    rcx, rcx
0x1800704c0  jz      loc_180070374
0x1800704c6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800704cb  jmp     loc_180070374
0x1800704d0  mov     rbx, [rbp+var_38]
0x1800704d4  test    esi, esi
0x1800704d6  jz      loc_180070584
0x1800704dc  mov     rcx, [rbp+arg_8]
0x1800704e0  lea     rdx, [rbp+var_20]
0x1800704e4  mov     [rsp+80h+var_58], rdx
0x1800704e9  xor     esi, esi
0x1800704eb  xor     r9d, r9d
0x1800704ee  mov     [rbp+var_20], rsi
0x1800704f2  xor     r8d, r8d
0x1800704f5  mov     dword ptr [rsp+80h+var_60], 3
0x1800704fd  mov     rax, [rcx]
0x180070500  mov     edx, 8242001Fh
0x180070505  mov     rax, [rax+38h]
0x180070509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007050e  mov     edi, eax
0x180070510  test    eax, eax
0x180070512  jns     short loc_180070534
0x180070514  mov     r9d, 9CEh
0x18007051a  mov     edx, 1
0x18007051f  mov     ecx, eax
0x180070521  call    Log_HREvent_1
0x180070526  lea     rcx, [rbp+var_20]
0x18007052a  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18007052f  jmp     loc_1800704B0
0x180070534  mov     rdx, [rbp+var_20]
0x180070538  mov     rcx, rbx
0x18007053b  call    cs:__imp_CopyStream
0x180070541  mov     edi, eax
0x180070543  test    eax, eax
0x180070545  jns     short loc_18007054F
0x180070547  mov     r9d, 9D0h
0x18007054d  jmp     short loc_18007051A
0x18007054f  mov     rax, [rbx]
0x180070552  xor     r9d, r9d
0x180070555  mov     rdx, cs:qword_180141350
0x18007055c  xor     r8d, r8d
0x18007055f  mov     rcx, rbx
0x180070562  mov     rax, [rax+28h]
0x180070566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007056b  mov     edi, eax
0x18007056d  test    eax, eax
0x18007056f  jns     short loc_180070579
0x180070571  mov     r9d, 9D4h
0x180070577  jmp     short loc_18007051A
0x180070579  lea     rcx, [rbp+var_20]
0x18007057d  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180070582  jmp     short loc_180070586
0x180070584  xor     esi, esi
0x180070586  test    r14d, r14d
0x180070589  jz      short loc_1800705B7
0x18007058b  lea     rcx, [rbp+var_30]
0x18007058f  call    ??$replace@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@tlx@@YAPEAPEAGAEAV?$auto_array_ptr@G$1??$_delete_array@G@tlx@@YAXPEAG@Z@0@@Z; tlx::replace<ushort,&tlx::_delete_array<ushort>(ushort *)>(tlx::auto_array_ptr<ushort,&tlx::_delete_array<ushort>(ushort *)> &)
0x180070594  or      r8d, 0FFFFFFFFh
0x180070598  mov     rdx, rax
0x18007059b  mov     rcx, rbx
0x18007059e  call    cs:__imp_ReadStreamContent
0x1800705a4  mov     edi, eax
0x1800705a6  test    eax, eax
0x1800705a8  jns     short loc_1800705B7
0x1800705aa  mov     r9d, 9D9h
0x1800705b0  jmp     loc_1800704A4
0x1800705b5  xor     esi, esi
0x1800705b7  mov     rax, [rbp+var_30]
0x1800705bb  mov     r8, r15
0x1800705be  mov     rcx, [rbp+Block]
0x1800705c2  mov     rdx, r12
0x1800705c5  mov     r9d, [rbp+arg_28]
0x1800705c9  mov     [rsp+80h+var_50], rax
0x1800705ce  mov     rax, [rbp+arg_30]
0x1800705d2  mov     [rsp+80h+var_58], rcx
0x1800705d7  mov     rcx, [rbp+arg_8]
0x1800705db  mov     [rsp+80h+var_60], rax
0x1800705e0  call    ?SetResponseMessageBodies@EmailHelper@@YAJPEAUIMessage@@PEBG1W4UdmEmailMessageBodyKind@@111@Z; EmailHelper::SetResponseMessageBodies(IMessage *,ushort const *,ushort const *,UdmEmailMessageBodyKind,ushort const *,ushort const *,ushort const *)
0x1800705e5  mov     edi, eax
0x1800705e7  test    eax, eax
0x1800705e9  jns     short loc_1800705F6
0x1800705eb  mov     r9d, 9E4h
0x1800705f1  jmp     loc_1800704A4
0x1800705f6  lea     rcx, [rbp+var_38]
0x1800705fa  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800705ff  mov     rcx, [rbp+var_30]; Block
0x180070603  test    rcx, rcx
0x180070606  jz      short loc_18007060D
0x180070608  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007060d  mov     rcx, [rbp+Block]; Block
0x180070611  test    rcx, rcx
0x180070614  jz      short loc_18007061B
0x180070616  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007061b  lea     rcx, [rbp+var_40]
0x18007061f  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x180070624  mov     edi, esi
0x180070626  lea     rcx, [rbp+var_18]
0x18007062a  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x18007062f  lea     rcx, [rbp+var_10]
0x180070633  call    ??1?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::~auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>(void)
0x180070638  lea     r11, [rsp+80h+var_s0]
0x180070640  mov     eax, edi
0x180070642  mov     rbx, [r11+40h]
0x180070646  mov     rsi, [r11+48h]
0x18007064a  mov     rsp, r11
0x18007064d  pop     r15
0x18007064f  pop     r14
0x180070651  pop     r12
0x180070653  pop     rdi
0x180070654  pop     rbp
0x180070655  retn
```
