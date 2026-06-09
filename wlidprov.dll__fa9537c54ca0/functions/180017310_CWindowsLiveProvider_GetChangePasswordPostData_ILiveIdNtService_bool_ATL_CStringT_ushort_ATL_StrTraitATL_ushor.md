# CWindowsLiveProvider::GetChangePasswordPostData(ILiveIdNtService *,bool &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180017310`
- end: `0x180017707`
- name: `?GetChangePasswordPostData@CWindowsLiveProvider@@AEAAJPEAVILiveIdNtService@@AEA_NAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1015`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018d5c`

## callees

- `0x1800034c0`
- `0x180004b44`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x18000e9f4`
- `0x18000ebc4`
- `0x180010b80`
- `0x1800130a4`
- `0x180013434`
- `0x180017310`
- `0x180025a38`
- `0x180058010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800176c2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800176c2`

## string_xrefs

- `0x1800174c8`: `WLIDCAcquireTokens failed, hr=0x%X`
- `0x1800175d5`: `WLIDCAcquireTokens returned hrAuthState=0x%X, hrRequestStatus=0x%X`
- `0x180017556`: `GetServiceTicket for %s:%s returned hrAuthRequired=0x%X, hrRequestStatus=0x%X`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWindowsLiveProvider::GetChangePasswordPostData(__int64 a1, __int64 a2, _BYTE *a3, __int64 a4)
{
  __int64 (__fastcall *v7)(__int64, void *, __int64, __int64, __int64 *, int *, int *, int *, void **, int *); // rbx
  void **Handle; // rax
  int v9; // eax
  _WORD *v10; // rcx
  __int64 (__fastcall *v11)(__int64, void *, const unsigned __int16 *, __int64 *); // rbx
  void **v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  const unsigned __int16 *v16; // [rsp+28h] [rbp-99h]
  __int64 v17; // [rsp+28h] [rbp-99h]
  __int64 v18; // [rsp+28h] [rbp-99h]
  __int64 v19; // [rsp+28h] [rbp-99h]
  __int64 v20; // [rsp+30h] [rbp-91h]
  __int64 v21; // [rsp+38h] [rbp-89h]
  __int64 v22; // [rsp+40h] [rbp-81h]
  int v23; // [rsp+68h] [rbp-59h] BYREF
  void *Block; // [rsp+70h] [rbp-51h] BYREF
  __int64 v25; // [rsp+78h] [rbp-49h] BYREF
  __int64 v26; // [rsp+80h] [rbp-41h] BYREF
  int v27; // [rsp+88h] [rbp-39h] BYREF
  int v28; // [rsp+8Ch] [rbp-35h] BYREF
  __int64 v29; // [rsp+90h] [rbp-31h] BYREF
  __int64 v30; // [rsp+98h] [rbp-29h] BYREF
  void *v31; // [rsp+A0h] [rbp-21h] BYREF
  __int64 v32; // [rsp+A8h] [rbp-19h] BYREF
  __int64 v33; // [rsp+B0h] [rbp-11h] BYREF
  __int128 v34; // [rsp+B8h] [rbp-9h]
  __int128 v35; // [rsp+C8h] [rbp+7h]
  _QWORD v36[4]; // [rsp+D8h] [rbp+17h] BYREF
  int v37; // [rsp+128h] [rbp+67h] BYREF
  int v38; // [rsp+12Ch] [rbp+6Bh]
  int v39; // [rsp+130h] [rbp+6Fh] BYREF

  v38 = HIDWORD(a1);
  v37 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v26 = 0;
  v31 = 0;
  v23 = 0;
  v28 = 0;
  v39 = 0;
  v27 = 0;
  v25 = 0;
  v30 = 0;
  Block = 0;
  v36[0] = "CWindowsLiveProvider::GetChangePasswordPostData";
  v36[1] = &v37;
  v36[2] = 0;
  v36[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
    "CWindowsLiveProvider::GetChangePasswordPostData",
    (const char *)0x762,
    0,
    v16);
  ATL::CSimpleStringT<unsigned short,0>::Truncate(a4, 0);
  v37 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, __int64, void **))(*(_QWORD *)a2 + 48LL))(
          a2,
          &qword_180063440,
          L"{2a2059e7-a58a-445c-befe-6a173ffe7ffd}",
          0x800000,
          &v31);
  if ( v37 >= 0 )
  {
    RefWLIDHandle::Attach((RefWLIDHandle *)&v26, v31);
    v37 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)a2 + 104LL))(
            a2,
            L"cfg:AccountDomain",
            &v25);
    if ( v37 >= 0 )
    {
      v37 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 104LL))(
              a2,
              L"cfg:AccountPolicy",
              &v30);
      if ( v37 >= 0 )
      {
        v33 = v25;
        *(_QWORD *)&v34 = L"mbi_ssl";
        HIDWORD(v35) = 1;
        *(_QWORD *)&v35 = 0;
        v7 = *(__int64 (__fastcall **)(__int64, void *, __int64, __int64, __int64 *, int *, int *, int *, void **, int *))(*(_QWORD *)a2 + 8LL);
        Handle = RefWLIDHandle::GetHandle((RefWLIDHandle *)&v26);
        v9 = v7(a2, *Handle, 512, 1, &v33, &v23, &v28, &v39, &Block, &v27);
        v37 = v9;
        if ( v9 >= 0 )
        {
          if ( v23 < 0 || v39 < 0 )
          {
            LODWORD(v20) = v39;
            LODWORD(v17) = v23;
            TracePrintW(
              2u,
              "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
              0x7A0u,
              L"WLIDCAcquireTokens returned hrAuthState=0x%X, hrRequestStatus=0x%X",
              v17,
              v20);
            if ( v39 >= 0 )
            {
              v37 = v23;
            }
            else
            {
              v29 = 0;
              v37 = v39;
              v11 = *(__int64 (__fastcall **)(__int64, void *, const unsigned __int16 *, __int64 *))(*(_QWORD *)a2 + 152LL);
              v12 = RefWLIDHandle::GetHandle((RefWLIDHandle *)&v26);
              v13 = v11(a2, *v12, L"FlowUrl", &v29);
              if ( v13 < 0 )
              {
                LODWORD(v19) = v13;
                TracePrintW(
                  2u,
                  "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
                  0x7BBu,
                  L"WLIDCGetIdentityProperty fails with 0x%x",
                  v19);
              }
              else
              {
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                  &v32,
                  v29);
                if ( *(_DWORD *)(v32 - 16) )
                {
                  LODWORD(v19) = v39;
                  TracePrintW(
                    5u,
                    "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
                    0x7B5u,
                    L"Interrupt Error: 0x%x, FlowUrl: '%s'",
                    v19,
                    v32);
                  *a3 = 1;
                }
                ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v32);
              }
              CMIDLPtr<unsigned short *>::Clear(&v29);
            }
          }
          else if ( *(int *)Block < 0 || *((int *)Block + 1) < 0 )
          {
            LODWORD(v22) = *((_DWORD *)Block + 1);
            LODWORD(v21) = *(_DWORD *)Block;
            TracePrintW(
              2u,
              "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
              0x7CDu,
              L"GetServiceTicket for %s:%s returned hrAuthRequired=0x%X, hrRequestStatus=0x%X",
              v25,
              v30,
              v21,
              v22);
            if ( *((int *)Block + 1) >= 0 )
            {
              v37 = *(_DWORD *)Block;
            }
            else
            {
              v37 = *((_DWORD *)Block + 1);
              v10 = (_WORD *)*((_QWORD *)Block + 7);
              if ( v10 && *v10 )
              {
                LODWORD(v18) = *((_DWORD *)Block + 1);
                TracePrintW(
                  5u,
                  "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
                  0x7D9u,
                  L"Interrupt Error: 0x%x, FlowUrl: '%s'",
                  v18,
                  *((_QWORD *)Block + 7));
                *a3 = 1;
              }
            }
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(a4, *((_QWORD *)Block + 5));
            TracePrintW(
              5u,
              "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
              0x7EAu,
              L"PostData: '%s'",
              *((_QWORD *)Block + 5));
          }
        }
        else
        {
          LODWORD(v17) = v9;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
            0x799u,
            L"WLIDCAcquireTokens failed, hr=0x%X",
            v17);
        }
      }
    }
  }
  v14 = v37;
  CTraceFuncW<long>::~CTraceFuncW<long>(v36);
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  CMIDLPtr<unsigned short *>::Clear(&v30);
  CMIDLPtr<unsigned short *>::Clear(&v25);
  CAutoRefPtr<SmartWLIDHandle>::Deinit(&v26);
  return v14;
}

```

## disassembly

```asm
0x180017310  mov     rax, rsp
0x180017313  mov     [rax+18h], rbx
0x180017317  mov     [rax+20h], rsi
0x18001731b  mov     [rax+8], rcx
0x18001731f  push    rbp
0x180017320  push    rdi
0x180017321  push    r12
0x180017323  push    r14
0x180017325  push    r15
0x180017327  lea     rbp, [rax-5Fh]
0x18001732b  sub     rsp, 0F0h
0x180017332  mov     r14, r9
0x180017335  mov     rsi, r8
0x180017338  mov     rdi, rdx
0x18001733b  xor     r15d, r15d
0x18001733e  mov     [rbp+57h+arg_0], r15d
0x180017342  mov     [rbp+57h+var_68], r15
0x180017346  xorps   xmm0, xmm0
0x180017349  movups  [rbp+57h+var_60], xmm0
0x18001734d  movups  [rbp+57h+var_50], xmm0
0x180017351  mov     [rbp+57h+var_98], r15
0x180017355  mov     [rbp+57h+var_78], r15
0x180017359  mov     [rbp+57h+var_B0], r15d
0x18001735d  mov     [rbp+57h+var_8C], r15d
0x180017361  mov     [rbp+57h+arg_8], r15d
0x180017365  mov     [rbp+57h+var_90], r15d
0x180017369  mov     [rbp+57h+var_A0], r15
0x18001736d  mov     [rbp+57h+var_80], r15
0x180017371  mov     [rbp+57h+Block], r15
0x180017375  lea     rdx, aCwindowslivepr_14; "CWindowsLiveProvider::GetChangePassword"...
0x18001737c  mov     [rbp+57h+var_40], rdx
0x180017380  lea     rax, [rbp+57h+arg_0]
0x180017384  mov     [rbp+57h+var_38], rax
0x180017388  mov     [rbp+57h+var_30], r15
0x18001738c  mov     [rbp+57h+var_28], r15
0x180017390  xor     r9d, r9d; unsigned int
0x180017393  mov     r8d, 762h; char *
0x180017399  lea     r12, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800173a0  mov     rcx, r12; this
0x1800173a3  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800173a8  nop
0x1800173a9  xor     edx, edx
0x1800173ab  mov     rcx, r14
0x1800173ae  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x1800173b3  mov     rax, [rdi]
0x1800173b6  lea     rcx, [rbp+57h+var_78]
0x1800173ba  mov     [rsp+110h+var_F0], rcx
0x1800173bf  mov     r9d, 800000h
0x1800173c5  lea     r8, a2a2059e7A58a44; "{2a2059e7-a58a-445c-befe-6a173ffe7ffd}"
0x1800173cc  lea     rdx, qword_180063440
0x1800173d3  mov     rcx, rdi
0x1800173d6  mov     rax, [rax+30h]
0x1800173da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173df  mov     [rbp+57h+arg_0], eax
0x1800173e2  test    eax, eax
0x1800173e4  js      loc_1800176AC
0x1800173ea  mov     rdx, [rbp+57h+var_78]; void *
0x1800173ee  lea     rcx, [rbp+57h+var_98]; this
0x1800173f2  call    ?Attach@RefWLIDHandle@@QEAAXPEAX@Z; RefWLIDHandle::Attach(void *)
0x1800173f7  mov     rax, [rdi]
0x1800173fa  lea     r8, [rbp+57h+var_A0]
0x1800173fe  lea     rdx, aCfgAccountdoma; "cfg:AccountDomain"
0x180017405  mov     rcx, rdi
0x180017408  mov     rax, [rax+68h]
0x18001740c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017411  mov     [rbp+57h+arg_0], eax
0x180017414  test    eax, eax
0x180017416  js      loc_1800176AC
0x18001741c  mov     rax, [rdi]
0x18001741f  lea     r8, [rbp+57h+var_80]
0x180017423  lea     rdx, aCfgAccountpoli; "cfg:AccountPolicy"
0x18001742a  mov     rcx, rdi
0x18001742d  mov     rax, [rax+68h]
0x180017431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017436  mov     [rbp+57h+arg_0], eax
0x180017439  test    eax, eax
0x18001743b  js      loc_1800176AC
0x180017441  mov     rax, [rbp+57h+var_A0]
0x180017445  mov     [rbp+57h+var_68], rax
0x180017449  lea     rax, aMbiSsl; "mbi_ssl"
0x180017450  mov     qword ptr [rbp+57h+var_60], rax
0x180017454  mov     dword ptr [rbp+57h+var_50+0Ch], 1
0x18001745b  mov     qword ptr [rbp+57h+var_50], r15
0x18001745f  mov     rax, [rdi]
0x180017462  mov     rbx, [rax+8]
0x180017466  lea     rcx, [rbp+57h+var_98]; this
0x18001746a  call    ?GetHandle@RefWLIDHandle@@AEAAPEAPEAXXZ; RefWLIDHandle::GetHandle(void)
0x18001746f  lea     rcx, [rbp+57h+var_90]
0x180017473  mov     [rsp+110h+var_C8], rcx
0x180017478  lea     rcx, [rbp+57h+Block]
0x18001747c  mov     [rsp+110h+var_D0], rcx
0x180017481  lea     rcx, [rbp+57h+arg_8]
0x180017485  mov     [rsp+110h+var_D8], rcx
0x18001748a  lea     rcx, [rbp+57h+var_8C]
0x18001748e  mov     [rsp+110h+var_E0], rcx
0x180017493  lea     rcx, [rbp+57h+var_B0]
0x180017497  mov     [rsp+110h+var_E8], rcx
0x18001749c  lea     rcx, [rbp+57h+var_68]
0x1800174a0  mov     [rsp+110h+var_F0], rcx
0x1800174a5  lea     r9d, [r15+1]
0x1800174a9  mov     r8d, 200h
0x1800174af  mov     rdx, [rax]
0x1800174b2  mov     rcx, rdi
0x1800174b5  mov     rax, rbx
0x1800174b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174bd  mov     [rbp+57h+arg_0], eax
0x1800174c0  test    eax, eax
0x1800174c2  jns     short loc_1800174E6
0x1800174c4  mov     dword ptr [rsp+110h+var_F0], eax
0x1800174c8  lea     r9, aWlidcacquireto_4; "WLIDCAcquireTokens failed, hr=0x%X"
0x1800174cf  mov     r8d, 799h; unsigned int
0x1800174d5  lea     ecx, [r15+2]; unsigned __int8
0x1800174d9  mov     rdx, r12; char *
0x1800174dc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800174e1  jmp     loc_1800176AC
0x1800174e6  mov     eax, [rbp+57h+arg_8]
0x1800174e9  mov     ecx, [rbp+57h+var_B0]
0x1800174ec  test    ecx, ecx
0x1800174ee  js      loc_1800175CD
0x1800174f4  test    eax, eax
0x1800174f6  js      loc_1800175CD
0x1800174fc  mov     rax, [rbp+57h+Block]
0x180017500  mov     edx, [rax]
0x180017502  test    edx, edx
0x180017504  js      short loc_180017539
0x180017506  cmp     [rax+4], r15d
0x18001750a  jl      short loc_180017539
0x18001750c  mov     rdx, [rax+28h]
0x180017510  mov     rcx, r14
0x180017513  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180017518  mov     rax, [rbp+57h+Block]
0x18001751c  mov     rcx, [rax+28h]
0x180017520  mov     [rsp+110h+var_F0], rcx
0x180017525  lea     r9, aPostdataS; "PostData: '%s'"
0x18001752c  mov     r8d, 7EAh
0x180017532  mov     ecx, 5
0x180017537  jmp     short loc_1800174D9
0x180017539  mov     ecx, [rax+4]
0x18001753c  mov     dword ptr [rsp+110h+var_D8], ecx
0x180017540  mov     dword ptr [rsp+110h+var_E0], edx
0x180017544  mov     rax, [rbp+57h+var_80]
0x180017548  mov     [rsp+110h+var_E8], rax
0x18001754d  mov     rax, [rbp+57h+var_A0]
0x180017551  mov     [rsp+110h+var_F0], rax
0x180017556  lea     r9, aGetservicetick; "GetServiceTicket for %s:%s returned hrA"...
0x18001755d  mov     r8d, 7CDh; unsigned int
0x180017563  mov     rdx, r12; char *
0x180017566  mov     ecx, 2; unsigned __int8
0x18001756b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180017570  mov     rax, [rbp+57h+Block]
0x180017574  mov     ecx, [rax+4]
0x180017577  test    ecx, ecx
0x180017579  jns     short loc_1800175C3
0x18001757b  mov     [rbp+57h+arg_0], ecx
0x18001757e  mov     rcx, [rax+38h]
0x180017582  test    rcx, rcx
0x180017585  jz      loc_1800176AC
0x18001758b  cmp     [rcx], r15w
0x18001758f  jz      loc_1800176AC
0x180017595  mov     [rsp+110h+var_E8], rcx
0x18001759a  mov     ecx, [rax+4]
0x18001759d  mov     dword ptr [rsp+110h+var_F0], ecx
0x1800175a1  lea     r9, aInterruptError; "Interrupt Error: 0x%x, FlowUrl: '%s'"
0x1800175a8  mov     r8d, 7D9h; unsigned int
0x1800175ae  mov     rdx, r12; char *
0x1800175b1  mov     ecx, 5; unsigned __int8
0x1800175b6  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800175bb  mov     byte ptr [rsi], 1
0x1800175be  jmp     loc_1800176AC
0x1800175c3  mov     ecx, [rax]
0x1800175c5  mov     [rbp+57h+arg_0], ecx
0x1800175c8  jmp     loc_1800176AC
0x1800175cd  mov     dword ptr [rsp+110h+var_E8], eax
0x1800175d1  mov     dword ptr [rsp+110h+var_F0], ecx
0x1800175d5  lea     r9, aWlidcacquireto_0; "WLIDCAcquireTokens returned hrAuthState"...
0x1800175dc  mov     r8d, 7A0h; unsigned int
0x1800175e2  mov     rdx, r12; char *
0x1800175e5  mov     ecx, 2; unsigned __int8
0x1800175ea  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800175ef  mov     eax, [rbp+57h+arg_8]
0x1800175f2  test    eax, eax
0x1800175f4  jns     loc_1800176A6
0x1800175fa  mov     [rbp+57h+var_88], r15
0x1800175fe  mov     [rbp+57h+arg_0], eax
0x180017601  mov     rax, [rdi]
0x180017604  mov     rbx, [rax+98h]
0x18001760b  lea     rcx, [rbp+57h+var_98]; this
0x18001760f  call    ?GetHandle@RefWLIDHandle@@AEAAPEAPEAXXZ; RefWLIDHandle::GetHandle(void)
0x180017614  lea     r9, [rbp+57h+var_88]
0x180017618  lea     r8, aFlowurl; "FlowUrl"
0x18001761f  mov     rdx, [rax]
0x180017622  mov     rcx, rdi
0x180017625  mov     rax, rbx
0x180017628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001762d  test    eax, eax
0x18001762f  js      short loc_18001767C
0x180017631  mov     rdx, [rbp+57h+var_88]
0x180017635  lea     rcx, [rbp+57h+var_70]
0x180017639  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001763e  mov     rax, [rbp+57h+var_70]
0x180017642  cmp     [rax-10h], r15d
0x180017646  jz      short loc_180017671
0x180017648  mov     [rsp+110h+var_E8], rax
0x18001764d  mov     eax, [rbp+57h+arg_8]
0x180017650  mov     dword ptr [rsp+110h+var_F0], eax
0x180017654  lea     r9, aInterruptError; "Interrupt Error: 0x%x, FlowUrl: '%s'"
0x18001765b  mov     r8d, 7B5h; unsigned int
0x180017661  mov     rdx, r12; char *
0x180017664  mov     ecx, 5; unsigned __int8
0x180017669  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001766e  mov     byte ptr [rsi], 1
0x180017671  lea     rcx, [rbp+57h+var_70]; void *
0x180017675  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18001767a  jmp     short loc_18001769B
0x18001767c  mov     dword ptr [rsp+110h+var_F0], eax
0x180017680  lea     r9, aWlidcgetidenti_0; "WLIDCGetIdentityProperty fails with 0x%"...
0x180017687  mov     r8d, 7BBh; unsigned int
0x18001768d  mov     rdx, r12; char *
0x180017690  mov     ecx, 2; unsigned __int8
0x180017695  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001769a  nop
0x18001769b  lea     rcx, [rbp+57h+var_88]
0x18001769f  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x1800176a4  jmp     short loc_1800176AC
0x1800176a6  mov     eax, [rbp+57h+var_B0]
0x1800176a9  mov     [rbp+57h+arg_0], eax
0x1800176ac  mov     ebx, [rbp+57h+arg_0]
0x1800176af  lea     rcx, [rbp+57h+var_40]
0x1800176b3  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800176b8  nop
0x1800176b9  mov     rcx, [rbp+57h+Block]; Block
0x1800176bd  test    rcx, rcx
0x1800176c0  jz      short loc_1800176CC
0x1800176c2  call    cs:__imp_free
0x1800176c8  mov     [rbp+57h+Block], r15
0x1800176cc  lea     rcx, [rbp+57h+var_80]
0x1800176d0  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x1800176d5  nop
0x1800176d6  lea     rcx, [rbp+57h+var_A0]
0x1800176da  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x1800176df  nop
0x1800176e0  lea     rcx, [rbp+57h+var_98]
0x1800176e4  call    ?Deinit@?$CAutoRefPtr@VSmartWLIDHandle@@@@IEAAXXZ; CAutoRefPtr<SmartWLIDHandle>::Deinit(void)
0x1800176e9  mov     eax, ebx
0x1800176eb  lea     r11, [rsp+110h+var_20]
0x1800176f3  mov     rbx, [r11+40h]
0x1800176f7  mov     rsi, [r11+48h]
0x1800176fb  mov     rsp, r11
0x1800176fe  pop     r15
0x180017700  pop     r14
0x180017702  pop     r12
0x180017704  pop     rdi
0x180017705  pop     rbp
0x180017706  retn
```
