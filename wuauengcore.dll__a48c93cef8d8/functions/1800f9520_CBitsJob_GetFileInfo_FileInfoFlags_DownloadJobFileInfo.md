# CBitsJob::GetFileInfo(FileInfoFlags,DownloadJobFileInfo *)

- ea: `0x1800f9520`
- end: `0x1800f9a61`
- name: `?GetFileInfo@CBitsJob@@UEAAJW4FileInfoFlags@@PEAUDownloadJobFileInfo@@@Z`
- size: `1345`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800e7870`
- `0x1800f8464`
- `0x1800f9520`
- `0x180113ae8`
- `0x180113b9c`
- `0x18012b618`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f96be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f97c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f98b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f98f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f990e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9940`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f996f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f999e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f96be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f97c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f98b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f98f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f990e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f9940`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f996f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f999e`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CBitsJob::GetFileInfo(CBitsJob *a1, int a2, __int64 a3)
{
  struct IBackgroundCopyFile **v5; // rbx
  unsigned __int64 v6; // r15
  signed int Files; // edi
  void *v8; // rcx
  void *v9; // rax
  void *v10; // rcx
  void *v11; // rax
  __int64 v12; // r13
  int v13; // eax
  int IndexOf; // eax
  LPVOID v15; // rdi
  __int64 (__fastcall *v16)(LPVOID, LPVOID *); // r12
  void *v17; // rcx
  struct IBackgroundCopyFile **v18; // rsi
  __int64 v19; // r14
  struct IBackgroundCopyFile **v21; // [rsp+38h] [rbp-38h] BYREF
  int v22; // [rsp+40h] [rbp-30h]
  int i; // [rsp+44h] [rbp-2Ch]
  CBitsJob *v24; // [rsp+48h] [rbp-28h]
  LPVOID pv; // [rsp+50h] [rbp-20h] BYREF
  LPVOID v26; // [rsp+58h] [rbp-18h] BYREF
  LPVOID v27; // [rsp+60h] [rbp-10h] BYREF

  v24 = a1;
  v5 = 0;
  v21 = 0;
  LODWORD(v6) = 0;
  LODWORD(pv) = 0;
  if ( !a3 )
  {
    Files = -2147467261;
    goto LABEL_80;
  }
  if ( !a2 )
  {
    Files = 0;
    goto LABEL_80;
  }
  Files = CBitsJob::GetFiles(a1, &v21, (unsigned int *)&pv);
  if ( Files < 0 )
  {
    LODWORD(v6) = (_DWORD)pv;
    goto LABEL_79;
  }
  v6 = (unsigned int)pv;
  if ( !(_DWORD)pv )
  {
    Files = -2145124344;
LABEL_79:
    v5 = v21;
    goto LABEL_80;
  }
  if ( (a2 & 1) != 0 )
  {
    v8 = *(void **)(a3 + 8);
    if ( v8 )
    {
      SusFree(v8);
      *(_QWORD *)(a3 + 8) = 0;
    }
    if ( (_DWORD)v6 )
    {
      v9 = SafeSusAllocArray(v6, 0x18u);
      *(_QWORD *)(a3 + 8) = v9;
      Files = v9 == 0 ? 0x8007000E : 0;
      if ( !v9 )
        goto LABEL_79;
    }
    else
    {
      Files = 0;
    }
  }
  v22 = a2 & 0x10;
  if ( (a2 & 0x10) != 0 )
  {
    v10 = *(void **)(a3 + 88);
    if ( v10 )
    {
      SusFree(v10);
      *(_QWORD *)(a3 + 88) = 0;
    }
    if ( (_DWORD)v6 )
    {
      v11 = SafeSusAllocArray(v6, 1u);
      *(_QWORD *)(a3 + 88) = v11;
      Files = v11 == 0 ? 0x8007000E : 0;
      if ( !v11 )
        goto LABEL_79;
    }
    else
    {
      Files = 0;
    }
  }
  v12 = 0;
  v5 = v21;
  if ( !(_DWORD)v6 )
  {
LABEL_77:
    *(_DWORD *)a3 = a2 & 0xFFFFFFDF;
    goto LABEL_80;
  }
  v13 = a2 & 4;
  for ( i = v13; ; v13 = i )
  {
    if ( v13 )
    {
      pv = 0;
      Files = ((__int64 (__fastcall *)(struct IBackgroundCopyFile *, LPVOID *))v5[v12]->lpVtbl->GetLocalName)(
                v5[v12],
                &pv);
      if ( Files < 0 )
        goto LABEL_53;
      v27 = pv;
      IndexOf = CSusMap<wchar_t *,CBitsJob::CStreamingInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsDelete<CBitsJob::CStreamingInfo *>>::GetIndexOf(
                  (char *)v24 + 48,
                  &v27);
      if ( IndexOf != *((_DWORD *)v24 + 17) )
      {
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_51;
      }
      v27 = pv;
      Files = (*(__int64 (__fastcall **)(__int64, LPVOID *, _QWORD))(*(_QWORD *)(a3 + 40) + 8LL))(a3 + 40, &v27, 0);
      if ( Files < 0 )
      {
LABEL_53:
        v17 = pv;
        goto LABEL_54;
      }
    }
    if ( (a2 & 1) != 0 )
    {
      Files = ((__int64 (__fastcall *)(struct IBackgroundCopyFile *, __int64))v5[v12]->lpVtbl->GetProgress)(
                v5[v12],
                *(_QWORD *)(a3 + 8) + 24LL * *(unsigned int *)(a3 + 4));
      if ( Files < 0 )
        goto LABEL_80;
    }
    if ( (a2 & 2) != 0 )
    {
      v26 = 0;
      Files = ((__int64 (__fastcall *)(struct IBackgroundCopyFile *, LPVOID *))v5[v12]->lpVtbl->GetRemoteName)(
                v5[v12],
                &v26);
      if ( Files < 0 )
        break;
      v27 = v26;
      Files = (*(__int64 (__fastcall **)(__int64, LPVOID *, _QWORD))(*(_QWORD *)(a3 + 16) + 8LL))(a3 + 16, &v27, 0);
      if ( Files < 0 )
        break;
    }
    if ( (a2 & 8) != 0 )
    {
      v26 = 0;
      pv = 0;
      Files = ((__int64 (__fastcall *)(struct IBackgroundCopyFile *, GUID *, LPVOID *))v5[v12]->lpVtbl->QueryInterface)(
                v5[v12],
                &GUID_659cdeaa_489e_11d9_a9cd_000d56965251,
                &v26);
      if ( Files < 0 )
      {
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v26 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
        goto LABEL_80;
      }
      v15 = v26;
      v16 = *(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v26 + 64LL);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      Files = v16(v15, &pv);
      if ( Files < 0 )
      {
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v26 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
        goto LABEL_80;
      }
      v27 = pv;
      Files = (*(__int64 (__fastcall **)(__int64, LPVOID *, _QWORD))(*(_QWORD *)(a3 + 64) + 8LL))(a3 + 64, &v27, 0);
      if ( Files < 0 )
      {
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v26 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
        goto LABEL_80;
      }
      pv = 0;
      if ( v26 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
    }
    if ( v22 )
    {
      v27 = 0;
      Files = ((__int64 (__fastcall *)(struct IBackgroundCopyFile *, GUID *, LPVOID *))v5[v12]->lpVtbl->QueryInterface)(
                v5[v12],
                &GUID_83e81b93_0873_474d_8a8c_f2018b1a939c,
                &v27);
      if ( Files >= 0 )
      {
        LODWORD(pv) = 0;
        v26 = 0;
        Files = (*(__int64 (__fastcall **)(LPVOID, LPVOID *, LPVOID *))(*(_QWORD *)v27 + 48LL))(v27, &pv, &v26);
        if ( Files < 0 )
        {
          if ( v26 )
          {
            CoTaskMemFree(v26);
            v26 = 0;
          }
          if ( v27 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
          goto LABEL_80;
        }
        if ( (_DWORD)pv )
          *(_BYTE *)(*(unsigned int *)(a3 + 4) + *(_QWORD *)(a3 + 88)) = 1;
        if ( v26 )
          CoTaskMemFree(v26);
      }
      if ( v27 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    }
    ++*(_DWORD *)(a3 + 4);
LABEL_51:
    v12 = (unsigned int)(v12 + 1);
    if ( (unsigned int)v12 >= (unsigned int)v6 )
      goto LABEL_77;
  }
  v17 = v26;
LABEL_54:
  if ( v17 )
    CoTaskMemFree(v17);
LABEL_80:
  if ( (_DWORD)v6 )
  {
    v18 = v5;
    v19 = (unsigned int)v6;
    do
    {
      if ( *v18 )
        ((void (__fastcall *)(struct IBackgroundCopyFile *))(*v18)->lpVtbl->Release)(*v18);
      ++v18;
      --v19;
    }
    while ( v19 );
  }
  if ( Files < 0 )
    WUTrace("CBitsJob::GetFileInfo", 1792, 2, 1, Files, L"Failed to get the file info from the download job");
  if ( v5 )
    SusFree(v5);
  return (unsigned int)Files;
}

```

## disassembly

```asm
0x1800f9520  mov     [rsp-38h+arg_8], rbx
0x1800f9525  push    rbp
0x1800f9526  push    rsi
0x1800f9527  push    rdi
0x1800f9528  push    r12
0x1800f952a  push    r13
0x1800f952c  push    r14
0x1800f952e  push    r15
0x1800f9530  mov     rbp, rsp
0x1800f9533  sub     rsp, 70h
0x1800f9537  mov     rax, cs:__security_cookie
0x1800f953e  xor     rax, rsp
0x1800f9541  mov     [rbp+var_8], rax
0x1800f9545  mov     rsi, r8
0x1800f9548  mov     r14d, edx
0x1800f954b  mov     [rbp+var_28], rcx
0x1800f954f  xor     ebx, ebx
0x1800f9551  mov     [rbp+var_38], rbx
0x1800f9555  xor     r15d, r15d
0x1800f9558  mov     dword ptr [rbp+pv], r15d
0x1800f955c  test    r8, r8
0x1800f955f  jnz     short loc_1800F956B
0x1800f9561  mov     edi, 80004003h
0x1800f9566  jmp     loc_1800F99D5
0x1800f956b  test    r14d, r14d
0x1800f956e  jnz     short loc_1800F9577
0x1800f9570  xor     edi, edi
0x1800f9572  jmp     loc_1800F99D5
0x1800f9577  lea     r8, [rbp+pv]; unsigned int *
0x1800f957b  lea     rdx, [rbp+var_38]; struct IBackgroundCopyFile ***
0x1800f957f  call    ?GetFiles@CBitsJob@@AEAAJPEAPEAPEAUIBackgroundCopyFile@@PEAK@Z; CBitsJob::GetFiles(IBackgroundCopyFile * * *,ulong *)
0x1800f9584  mov     edi, eax
0x1800f9586  test    eax, eax
0x1800f9588  js      loc_1800F99CD
0x1800f958e  mov     r15d, dword ptr [rbp+pv]
0x1800f9592  test    r15d, r15d
0x1800f9595  jnz     short loc_1800F95A1
0x1800f9597  mov     edi, 80240008h
0x1800f959c  jmp     loc_1800F99D1
0x1800f95a1  mov     al, r14b
0x1800f95a4  mov     r12d, 8007000Eh
0x1800f95aa  and     al, 1
0x1800f95ac  mov     [rbp+var_40], al
0x1800f95af  jz      short loc_1800F95F7
0x1800f95b1  mov     rcx, [rsi+8]; lpMem
0x1800f95b5  test    rcx, rcx
0x1800f95b8  jz      short loc_1800F95C7
0x1800f95ba  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800f95bf  mov     qword ptr [rsi+8], 0
0x1800f95c7  test    r15d, r15d
0x1800f95ca  jnz     short loc_1800F95D0
0x1800f95cc  xor     edi, edi
0x1800f95ce  jmp     short loc_1800F95F7
0x1800f95d0  mov     edx, 18h; unsigned __int64
0x1800f95d5  mov     rcx, r15; unsigned __int64
0x1800f95d8  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x1800f95dd  mov     [rsi+8], rax
0x1800f95e1  mov     rcx, rax
0x1800f95e4  neg     rcx
0x1800f95e7  sbb     edi, edi
0x1800f95e9  not     edi
0x1800f95eb  and     edi, r12d
0x1800f95ee  test    rax, rax
0x1800f95f1  jz      loc_1800F99D1
0x1800f95f7  mov     eax, r14d
0x1800f95fa  and     eax, 10h
0x1800f95fd  mov     [rbp+var_30], eax
0x1800f9600  jz      short loc_1800F9648
0x1800f9602  mov     rcx, [rsi+58h]; lpMem
0x1800f9606  test    rcx, rcx
0x1800f9609  jz      short loc_1800F9618
0x1800f960b  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800f9610  mov     qword ptr [rsi+58h], 0
0x1800f9618  test    r15d, r15d
0x1800f961b  jnz     short loc_1800F9621
0x1800f961d  xor     edi, edi
0x1800f961f  jmp     short loc_1800F9648
0x1800f9621  mov     edx, 1; unsigned __int64
0x1800f9626  mov     rcx, r15; unsigned __int64
0x1800f9629  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x1800f962e  mov     [rsi+58h], rax
0x1800f9632  mov     rcx, rax
0x1800f9635  neg     rcx
0x1800f9638  sbb     edi, edi
0x1800f963a  not     edi
0x1800f963c  and     edi, r12d
0x1800f963f  test    rax, rax
0x1800f9642  jz      loc_1800F99D1
0x1800f9648  xor     r13d, r13d
0x1800f964b  mov     rbx, [rbp+var_38]
0x1800f964f  test    r15d, r15d
0x1800f9652  jz      loc_1800F99C4
0x1800f9658  mov     eax, r14d
0x1800f965b  and     eax, 4
0x1800f965e  mov     [rbp+var_2C], eax
0x1800f9661  test    eax, eax
0x1800f9663  jz      loc_1800F96F2
0x1800f9669  mov     [rbp+pv], 0
0x1800f9671  mov     rcx, [rbx+r13*8]
0x1800f9675  mov     rax, [rcx]
0x1800f9678  lea     rdx, [rbp+pv]
0x1800f967c  mov     rax, [rax+20h]
0x1800f9680  call    _guard_dispatch_icall
0x1800f9685  mov     edi, eax
0x1800f9687  test    eax, eax
0x1800f9689  js      loc_1800F98E7
0x1800f968f  mov     rax, [rbp+pv]
0x1800f9693  mov     [rbp+var_10], rax
0x1800f9697  mov     rcx, [rbp+var_28]
0x1800f969b  add     rcx, 30h ; '0'
0x1800f969f  lea     rdx, [rbp+var_10]
0x1800f96a3  call    ?GetIndexOf@?$CSusMap@PEA_WPEAVCStreamingInfo@CBitsJob@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusSortedArrayListItemOpsDelete@PEAVCStreamingInfo@CBitsJob@@@@@@QEBAKAEBQEA_W@Z; CSusMap<wchar_t *,CBitsJob::CStreamingInfo *,CSusSortedArrayListItemOpsLPWSTR,CSusSortedArrayListItemOpsDelete<CBitsJob::CStreamingInfo *>>::GetIndexOf(wchar_t * const &)
0x1800f96a8  mov     rcx, [rbp+var_28]
0x1800f96ac  cmp     eax, [rcx+44h]
0x1800f96af  jz      short loc_1800F96C9
0x1800f96b1  mov     rcx, [rbp+pv]; pv
0x1800f96b5  test    rcx, rcx
0x1800f96b8  jz      loc_1800F98D3
0x1800f96be  call    cs:__imp_CoTaskMemFree
0x1800f96c4  jmp     loc_1800F98D3
0x1800f96c9  lea     rcx, [rsi+28h]
0x1800f96cd  mov     rax, [rbp+pv]
0x1800f96d1  mov     [rbp+var_10], rax
0x1800f96d5  mov     rax, [rcx]
0x1800f96d8  xor     r8d, r8d
0x1800f96db  lea     rdx, [rbp+var_10]
0x1800f96df  mov     rax, [rax+8]
0x1800f96e3  call    _guard_dispatch_icall
0x1800f96e8  mov     edi, eax
0x1800f96ea  test    eax, eax
0x1800f96ec  js      loc_1800F98E7
0x1800f96f2  cmp     [rbp+var_40], 0
0x1800f96f6  jz      short loc_1800F9721
0x1800f96f8  mov     rcx, [rbx+r13*8]
0x1800f96fc  mov     eax, [rsi+4]
0x1800f96ff  lea     rdx, [rax+rax*2]
0x1800f9703  mov     rax, [rsi+8]
0x1800f9707  lea     rdx, [rax+rdx*8]
0x1800f970b  mov     rax, [rcx]
0x1800f970e  mov     rax, [rax+28h]
0x1800f9712  call    _guard_dispatch_icall
0x1800f9717  mov     edi, eax
0x1800f9719  test    eax, eax
0x1800f971b  js      loc_1800F99D5
0x1800f9721  test    r14b, 2
0x1800f9725  jz      short loc_1800F9776
0x1800f9727  mov     [rbp+var_18], 0
0x1800f972f  mov     rcx, [rbx+r13*8]
0x1800f9733  mov     rax, [rcx]
0x1800f9736  lea     rdx, [rbp+var_18]
0x1800f973a  mov     rax, [rax+18h]
0x1800f973e  call    _guard_dispatch_icall
0x1800f9743  mov     edi, eax
0x1800f9745  test    eax, eax
0x1800f9747  js      loc_1800F98FF
0x1800f974d  lea     rcx, [rsi+10h]
0x1800f9751  mov     rax, [rbp+var_18]
0x1800f9755  mov     [rbp+var_10], rax
0x1800f9759  mov     rax, [rcx]
0x1800f975c  xor     r8d, r8d
0x1800f975f  lea     rdx, [rbp+var_10]
0x1800f9763  mov     rax, [rax+8]
0x1800f9767  call    _guard_dispatch_icall
0x1800f976c  mov     edi, eax
0x1800f976e  test    eax, eax
0x1800f9770  js      loc_1800F98FF
0x1800f9776  test    r14b, 8
0x1800f977a  jz      loc_1800F9836
0x1800f9780  mov     [rbp+var_18], 0
0x1800f9788  mov     [rbp+pv], 0
0x1800f9790  mov     rcx, [rbx+r13*8]
0x1800f9794  mov     rax, [rcx]
0x1800f9797  lea     r8, [rbp+var_18]
0x1800f979b  lea     rdx, _GUID_659cdeaa_489e_11d9_a9cd_000d56965251
0x1800f97a2  mov     rax, [rax]
0x1800f97a5  call    _guard_dispatch_icall
0x1800f97aa  mov     edi, eax
0x1800f97ac  test    eax, eax
0x1800f97ae  js      loc_1800F9966
0x1800f97b4  mov     rdi, [rbp+var_18]
0x1800f97b8  mov     rax, [rdi]
0x1800f97bb  mov     r12, [rax+40h]
0x1800f97bf  mov     rcx, [rbp+pv]; pv
0x1800f97c3  test    rcx, rcx
0x1800f97c6  jz      short loc_1800F97D6
0x1800f97c8  call    cs:__imp_CoTaskMemFree
0x1800f97ce  mov     [rbp+pv], 0
0x1800f97d6  lea     rdx, [rbp+pv]
0x1800f97da  mov     rcx, rdi
0x1800f97dd  mov     rax, r12
0x1800f97e0  call    _guard_dispatch_icall
0x1800f97e5  mov     edi, eax
0x1800f97e7  test    eax, eax
0x1800f97e9  js      loc_1800F9937
0x1800f97ef  lea     rcx, [rsi+40h]
0x1800f97f3  mov     rax, [rbp+pv]
0x1800f97f7  mov     [rbp+var_10], rax
0x1800f97fb  mov     rax, [rcx]
0x1800f97fe  xor     r8d, r8d
0x1800f9801  lea     rdx, [rbp+var_10]
0x1800f9805  mov     rax, [rax+8]
0x1800f9809  call    _guard_dispatch_icall
0x1800f980e  mov     edi, eax
0x1800f9810  test    eax, eax
0x1800f9812  js      loc_1800F9905
0x1800f9818  mov     [rbp+pv], 0
0x1800f9820  mov     rcx, [rbp+var_18]
0x1800f9824  test    rcx, rcx
0x1800f9827  jz      short loc_1800F9836
0x1800f9829  mov     rax, [rcx]
0x1800f982c  mov     rax, [rax+10h]
0x1800f9830  call    _guard_dispatch_icall
0x1800f9835  nop
0x1800f9836  cmp     [rbp+var_30], 0
0x1800f983a  jz      loc_1800F98D0
0x1800f9840  mov     [rbp+var_10], 0
0x1800f9848  mov     rcx, [rbx+r13*8]
0x1800f984c  mov     rax, [rcx]
0x1800f984f  lea     r8, [rbp+var_10]
0x1800f9853  lea     rdx, _GUID_83e81b93_0873_474d_8a8c_f2018b1a939c
0x1800f985a  mov     rax, [rax]
0x1800f985d  call    _guard_dispatch_icall
0x1800f9862  mov     edi, eax
0x1800f9864  test    eax, eax
0x1800f9866  js      short loc_1800F98BA
0x1800f9868  mov     dword ptr [rbp+pv], 0
0x1800f986f  mov     [rbp+var_18], 0
0x1800f9877  mov     rcx, [rbp+var_10]
0x1800f987b  mov     rax, [rcx]
0x1800f987e  lea     r8, [rbp+var_18]
0x1800f9882  lea     rdx, [rbp+pv]
0x1800f9886  mov     rax, [rax+30h]
0x1800f988a  call    _guard_dispatch_icall
0x1800f988f  mov     edi, eax
0x1800f9891  test    eax, eax
0x1800f9893  js      loc_1800F9995
0x1800f9899  cmp     dword ptr [rbp+pv], 0
0x1800f989d  jbe     short loc_1800F98AA
0x1800f989f  mov     ecx, [rsi+4]
0x1800f98a2  mov     rax, [rsi+58h]
0x1800f98a6  mov     byte ptr [rcx+rax], 1
0x1800f98aa  mov     rcx, [rbp+var_18]; pv
0x1800f98ae  test    rcx, rcx
0x1800f98b1  jz      short loc_1800F98BA
0x1800f98b3  call    cs:__imp_CoTaskMemFree
0x1800f98b9  nop
0x1800f98ba  mov     rcx, [rbp+var_10]
0x1800f98be  test    rcx, rcx
0x1800f98c1  jz      short loc_1800F98D0
0x1800f98c3  mov     rax, [rcx]
0x1800f98c6  mov     rax, [rax+10h]
0x1800f98ca  call    _guard_dispatch_icall
0x1800f98cf  nop
0x1800f98d0  inc     dword ptr [rsi+4]
0x1800f98d3  inc     r13d
0x1800f98d6  cmp     r13d, r15d
0x1800f98d9  jnb     loc_1800F99C4
0x1800f98df  mov     eax, [rbp+var_2C]
0x1800f98e2  jmp     loc_1800F9661
0x1800f98e7  mov     rcx, [rbp+pv]; pv
0x1800f98eb  test    rcx, rcx
0x1800f98ee  jz      loc_1800F99D5
0x1800f98f4  call    cs:__imp_CoTaskMemFree
0x1800f98fa  jmp     loc_1800F99D5
0x1800f98ff  mov     rcx, [rbp+var_18]
0x1800f9903  jmp     short loc_1800F98EB
0x1800f9905  mov     rcx, [rbp+pv]; pv
0x1800f9909  test    rcx, rcx
0x1800f990c  jz      short loc_1800F991C
0x1800f990e  call    cs:__imp_CoTaskMemFree
0x1800f9914  mov     [rbp+pv], 0
0x1800f991c  mov     rcx, [rbp+var_18]
0x1800f9920  test    rcx, rcx
0x1800f9923  jz      short loc_1800F9932
0x1800f9925  mov     rax, [rcx]
0x1800f9928  mov     rax, [rax+10h]
0x1800f992c  call    _guard_dispatch_icall
0x1800f9931  nop
0x1800f9932  jmp     loc_1800F99D5
0x1800f9937  mov     rcx, [rbp+pv]; pv
0x1800f993b  test    rcx, rcx
0x1800f993e  jz      short loc_1800F994E
0x1800f9940  call    cs:__imp_CoTaskMemFree
0x1800f9946  mov     [rbp+pv], 0
0x1800f994e  mov     rcx, [rbp+var_18]
0x1800f9952  test    rcx, rcx
0x1800f9955  jz      short loc_1800F9964
0x1800f9957  mov     rax, [rcx]
0x1800f995a  mov     rax, [rax+10h]
0x1800f995e  call    _guard_dispatch_icall
0x1800f9963  nop
0x1800f9964  jmp     short loc_1800F99D5
0x1800f9966  mov     rcx, [rbp+pv]; pv
0x1800f996a  test    rcx, rcx
0x1800f996d  jz      short loc_1800F997D
0x1800f996f  call    cs:__imp_CoTaskMemFree
0x1800f9975  mov     [rbp+pv], 0
0x1800f997d  mov     rcx, [rbp+var_18]
0x1800f9981  test    rcx, rcx
0x1800f9984  jz      short loc_1800F9993
  ... truncated ...
```
