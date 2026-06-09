# SearchUpdates(IUpdateSearcher *,ushort *,ushort * *,IUpdateCollection * *)

- ea: `0x14000a4bc`
- end: `0x14000aa3e`
- name: `?SearchUpdates@@YAJPEAUIUpdateSearcher@@PEAGPEAPEAGPEAPEAUIUpdateCollection@@@Z`
- size: `1410`
- prototype: `__int64 __fastcall(struct IUpdateSearcher *, unsigned __int16 *, unsigned __int16 **, struct IUpdateCollection **)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400075b0`

## callees

- `0x14000a4bc`
- `0x14000ec58`
- `0x140013490`
- `0x140015010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000a8d2`
- `KERNEL32!GetLastError` at `0x14000a8d2`
- `KERNEL32!SetLastError` at `0x14000a8e5`
- `KERNEL32!SetLastError` at `0x14000a8e5`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a8dd`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a9d1`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a8dd`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a9d1`

## string_xrefs

- `0x14000a8ad`: `Failed to get update out of collection`
- `0x14000a90b`: `Failed to get update title`
- `0x14000a854`: `Failed to display no-update message box`
- `0x14000a502`: `SearchUpdates`
- `0x14000a53c`: `SearchUpdates`
- `0x14000a58a`: `SearchUpdates`
- `0x14000a59b`: `SearchUpdates`
- `0x14000a530`: `Invalid argument: bstrUpdateTitle is NULL`
- `0x14000a557`: `Invalid argument: ppUpdates is NULL`
- `0x14000a5c4`: `Failed; user cancelled the install`
- `0x14000a739`: `Update requires new servicing stack`
- `0x14000a7c0`: `Failed to get update collection from search result`
- `0x14000a7eb`: `Failed to get count of updates to install`
- `0x14000a809`: `There should be only one update to install`
- `0x14000a81e`: `There is no update bundle to install`
- `0x14000a93e`: `Failed to query whether update is already installed`
- `0x14000a956`: `Update is already installed`
- `0x14000a995`: `Failed to display update-installed message box`

## pseudocode

```c
__int64 __fastcall SearchUpdates(
        struct IUpdateSearcher *a1,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        struct IUpdateCollection **a4)
{
  int v6; // ebx
  const char *v7; // r8
  __int64 v8; // rdx
  int v9; // r9d
  __int64 v10; // rcx
  __int64 *v11; // rbx
  __int64 v12; // rax
  __int64 (__fastcall *v13)(__int64 *, __int64 *); // rsi
  unsigned int v14; // esi
  __int64 v15; // rax
  __int64 v16; // rcx
  struct IUpdateCollection *v17; // rbx
  struct IUpdateCollectionVtbl *lpVtbl; // rax
  HRESULT (__stdcall *get_Item)(IUpdateCollection *, LONG, IUpdate **); // rsi
  __int64 v20; // r14
  OLECHAR *v21; // rsi
  __int64 (__fastcall *v22)(__int64, BSTR *); // r15
  DWORD LastError; // ebx
  struct IUpdateCollection *v25; // [rsp+30h] [rbp-48h] BYREF
  int v26; // [rsp+38h] [rbp-40h] BYREF
  int v27; // [rsp+3Ch] [rbp-3Ch] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-38h] BYREF
  __int64 v29; // [rsp+48h] [rbp-30h] BYREF
  __int64 v30; // [rsp+50h] [rbp-28h] BYREF
  __int64 v31; // [rsp+58h] [rbp-20h] BYREF
  int v32; // [rsp+60h] [rbp-18h] BYREF
  int v33; // [rsp+64h] [rbp-14h] BYREF
  __int64 *v34; // [rsp+68h] [rbp-10h] BYREF
  __int16 v35; // [rsp+C0h] [rbp+48h] BYREF

  v34 = 0;
  v31 = 0;
  v25 = 0;
  v30 = 0;
  bstrString = 0;
  v33 = 0;
  if ( !a1 )
  {
    WusaLogDebugEventA(L"SearchUpdates", 838, "Invalid argument: pSearcher is NULL");
LABEL_3:
    v6 = -2147024809;
    goto LABEL_68;
  }
  if ( !a2 )
  {
    WusaLogDebugEventA(L"SearchUpdates", 839, "Invalid argument: bstrSearchCriteria is NULL");
    goto LABEL_3;
  }
  if ( !a3 )
  {
    WusaLogDebugEventA(L"SearchUpdates", 840, "Invalid argument: bstrUpdateTitle is NULL");
LABEL_8:
    v6 = -2147024882;
    goto LABEL_68;
  }
  if ( !a4 )
  {
    WusaLogDebugEventA(L"SearchUpdates", 841, "Invalid argument: ppUpdates is NULL");
    goto LABEL_8;
  }
  v6 = ((__int64 (__fastcall *)(struct IUpdateSearcher *, unsigned __int16 *, __int64 **))a1->lpVtbl->Search)(
         a1,
         a2,
         &v34);
  if ( v6 < 0 )
  {
    v7 = "Failed to begin search";
    v8 = 844;
LABEL_13:
    WusaLogDebugEventA(L"SearchUpdates", v8, v7);
    goto LABEL_68;
  }
  WusaLogDebugEventA(L"SearchUpdates", 846, "End of search");
  if ( dword_1400201AC )
  {
    v6 = -2147023673;
    v7 = "Failed; user cancelled the install";
    v8 = 851;
    goto LABEL_13;
  }
  v27 = 4;
  v6 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v34 + 56))(v34, &v27);
  if ( v6 < 0 )
  {
    v7 = "Failed to get search result code";
    v8 = 858;
    goto LABEL_13;
  }
  v9 = v27;
  switch ( v27 )
  {
    case 2:
      v15 = *v34;
      v25 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64 *, struct IUpdateCollection **))(v15 + 72))(v34, &v25);
      if ( v6 < 0 )
      {
        v7 = "Failed to get update collection from search result";
        v8 = 913;
        goto LABEL_13;
      }
      v6 = ((__int64 (__fastcall *)(struct IUpdateCollection *, int *))v25->lpVtbl->get_Count)(v25, &v33);
      if ( v6 < 0 )
      {
        v7 = "Failed to get count of updates to install";
        v8 = 916;
        goto LABEL_13;
      }
      if ( v33 > 1 )
      {
        v6 = -2147467259;
        v7 = "There should be only one update to install";
        v8 = 921;
        goto LABEL_13;
      }
      if ( v33 > 0 )
      {
        v16 = v30;
        v17 = v25;
        lpVtbl = v25->lpVtbl;
        v30 = 0;
        get_Item = lpVtbl->get_Item;
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        v6 = ((__int64 (__fastcall *)(struct IUpdateCollection *, _QWORD, __int64 *))get_Item)(v17, 0, &v30);
        if ( v6 < 0 )
        {
          v7 = "Failed to get update out of collection";
          v8 = 938;
          goto LABEL_13;
        }
        v20 = v30;
        v21 = bstrString;
        v22 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v30 + 56LL);
        if ( bstrString )
        {
          LastError = GetLastError();
          SysFreeString(v21);
          SetLastError(LastError);
        }
        bstrString = 0;
        v6 = v22(v20, &bstrString);
        if ( v6 < 0 )
        {
          v7 = "Failed to get update title";
          v8 = 941;
          goto LABEL_13;
        }
        v35 = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v30 + 208LL))(v30, &v35);
        if ( v6 < 0 )
        {
          v7 = "Failed to query whether update is already installed";
          v8 = 945;
          goto LABEL_13;
        }
        if ( v35 == -1 )
        {
          WusaLogDebugEventA(L"SearchUpdates", 949, "Update is already installed");
          if ( (int)WusaMessageBox(0xEA6Eu, 0xEA60u, 1, (PCWSTR)0xFFFF, 0, bstrString) < 0 )
            WusaLogDebugEventA(L"SearchUpdates", 953, "Failed to display update-installed message box");
          v6 = 2359302;
        }
        else
        {
          *a4 = v25;
          *a3 = bstrString;
          v25 = 0;
          bstrString = 0;
        }
      }
      else
      {
        WusaLogDebugEventA(L"SearchUpdates", 926, "There is no update bundle to install");
        if ( (int)WusaMessageBox(0xEA64u, 0xEA60u, 1, (PCWSTR)0xFFFE, 0) < 0 )
          WusaLogDebugEventA(L"SearchUpdates", 930, "Failed to display no-update message box");
        v6 = -2145124329;
      }
      break;
    case 3:
      v10 = v31;
      v11 = v34;
      v26 = 0;
      v12 = *v34;
      v31 = 0;
      v13 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(v12 + 80);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v6 = v13(v11, &v31);
      if ( v6 < 0 )
      {
        v7 = "Failed to get search warnings";
        v8 = 880;
        goto LABEL_13;
      }
      v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 72LL))(v31, &v26);
      if ( v6 < 0 )
      {
        v7 = "Failed to get warning count";
        v8 = 883;
        goto LABEL_13;
      }
      v14 = 0;
      if ( v26 <= 0 )
      {
LABEL_35:
        v9 = v27;
        goto LABEL_36;
      }
      while ( 1 )
      {
        v32 = 0;
        v29 = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 56LL))(v31, v14, &v29);
        if ( v6 < 0 )
          break;
        v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 64LL))(v29, &v32);
        if ( v6 < 0 )
        {
          WusaLogDebugEventA(L"SearchUpdates", 893, "Failed to get warning HRESULsT");
          goto LABEL_41;
        }
        if ( v32 == -2145116137 )
        {
          v6 = -2145116137;
          WusaLogDebugEventA(L"SearchUpdates", 900, "Update requires new servicing stack");
          goto LABEL_41;
        }
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        if ( (int)++v14 >= v26 )
          goto LABEL_35;
      }
      WusaLogDebugEventA(L"SearchUpdates", 890, "Failed to get warning");
LABEL_41:
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      break;
    case 5:
      v6 = -2147023673;
LABEL_37:
      WusaLogDebugEventA(L"SearchUpdates", 910, "Failed. Search result code is %u", v9);
      break;
    default:
LABEL_36:
      v6 = -2147467259;
      goto LABEL_37;
  }
LABEL_68:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v25 )
    ((void (__fastcall *)(struct IUpdateCollection *))v25->lpVtbl->Release)(v25);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v34 )
    (*(void (__fastcall **)(__int64 *))(*v34 + 16))(v34);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000a4bc  push    rbp
0x14000a4be  push    rbx
0x14000a4bf  push    rsi
0x14000a4c0  push    rdi
0x14000a4c1  push    r12
0x14000a4c3  push    r13
0x14000a4c5  push    r14
0x14000a4c7  push    r15
0x14000a4c9  mov     rbp, rsp
0x14000a4cc  sub     rsp, 78h
0x14000a4d0  xor     r14d, r14d
0x14000a4d3  mov     r12, r9
0x14000a4d6  mov     [rbp+var_10], r14
0x14000a4da  mov     r13, r8
0x14000a4dd  mov     [rbp+var_20], r14
0x14000a4e1  mov     [rbp+var_48], r14
0x14000a4e5  mov     [rbp+var_28], r14
0x14000a4e9  mov     [rbp+bstrString], r14
0x14000a4ed  mov     [rbp+var_14], r14d
0x14000a4f1  test    rcx, rcx
0x14000a4f4  jnz     short loc_14000A518
0x14000a4f6  lea     r8, aInvalidArgumen; "Invalid argument: pSearcher is NULL"
0x14000a4fd  mov     edx, 346h
0x14000a502  lea     rcx, aSearchupdates; "SearchUpdates"
0x14000a509  call    WusaLogDebugEventA
0x14000a50e  mov     ebx, 80070057h
0x14000a513  jmp     loc_14000A9C8
0x14000a518  test    rdx, rdx
0x14000a51b  jnz     short loc_14000A52B
0x14000a51d  lea     r8, aInvalidArgumen_1; "Invalid argument: bstrSearchCriteria is"...
0x14000a524  mov     edx, 347h
0x14000a529  jmp     short loc_14000A502
0x14000a52b  test    r13, r13
0x14000a52e  jnz     short loc_14000A552
0x14000a530  lea     r8, aInvalidArgumen_3; "Invalid argument: bstrUpdateTitle is NU"...
0x14000a537  mov     edx, 348h
0x14000a53c  lea     rcx, aSearchupdates; "SearchUpdates"
0x14000a543  call    WusaLogDebugEventA
0x14000a548  mov     ebx, 8007000Eh
0x14000a54d  jmp     loc_14000A9C8
0x14000a552  test    r12, r12
0x14000a555  jnz     short loc_14000A565
0x14000a557  lea     r8, aInvalidArgumen_0; "Invalid argument: ppUpdates is NULL"
0x14000a55e  mov     edx, 349h
0x14000a563  jmp     short loc_14000A53C
0x14000a565  mov     rax, [rcx]
0x14000a568  lea     r8, [rbp+var_10]
0x14000a56c  mov     rax, [rax+98h]
0x14000a573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a578  mov     ebx, eax
0x14000a57a  test    eax, eax
0x14000a57c  jns     short loc_14000A59B
0x14000a57e  lea     r8, aFailedToBeginS; "Failed to begin search"
0x14000a585  mov     edx, 34Ch
0x14000a58a  lea     rcx, aSearchupdates; "SearchUpdates"
0x14000a591  call    WusaLogDebugEventA
0x14000a596  jmp     loc_14000A9C8
0x14000a59b  lea     rdi, aSearchupdates; "SearchUpdates"
0x14000a5a2  mov     edx, 34Eh
0x14000a5a7  mov     rcx, rdi
0x14000a5aa  lea     r8, aEndOfSearch; "End of search"
0x14000a5b1  call    WusaLogDebugEventA
0x14000a5b6  cmp     cs:dword_1400201AC, r14d
0x14000a5bd  jz      short loc_14000A5D5
0x14000a5bf  mov     ebx, 800704C7h
0x14000a5c4  lea     r8, aFailedUserCanc_1; "Failed; user cancelled the install"
0x14000a5cb  mov     edx, 353h
0x14000a5d0  mov     rcx, rdi
0x14000a5d3  jmp     short loc_14000A591
0x14000a5d5  mov     rcx, [rbp+var_10]
0x14000a5d9  lea     rdx, [rbp+var_3C]
0x14000a5dd  mov     [rbp+var_3C], 4
0x14000a5e4  mov     rax, [rcx]
0x14000a5e7  mov     rax, [rax+38h]
0x14000a5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a5f0  mov     ebx, eax
0x14000a5f2  test    eax, eax
0x14000a5f4  jns     short loc_14000A604
0x14000a5f6  lea     r8, aFailedToGetSea_0; "Failed to get search result code"
0x14000a5fd  mov     edx, 35Ah
0x14000a602  jmp     short loc_14000A5D0
0x14000a604  mov     r9d, [rbp+var_3C]
0x14000a608  mov     ecx, r9d
0x14000a60b  sub     ecx, 2
0x14000a60e  jz      loc_14000A787
0x14000a614  sub     ecx, 1
0x14000a617  jz      short loc_14000A62C
0x14000a619  cmp     ecx, 2
0x14000a61c  jnz     loc_14000A718
0x14000a622  mov     ebx, 800704C7h
0x14000a627  jmp     loc_14000A71D
0x14000a62c  mov     rcx, [rbp+var_20]
0x14000a630  mov     rbx, [rbp+var_10]
0x14000a634  mov     [rbp+var_40], r14d
0x14000a638  mov     rax, [rbx]
0x14000a63b  mov     [rbp+var_20], r14
0x14000a63f  mov     rsi, [rax+50h]
0x14000a643  test    rcx, rcx
0x14000a646  jz      short loc_14000A654
0x14000a648  mov     rdx, [rcx]
0x14000a64b  mov     rax, [rdx+10h]
0x14000a64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a654  lea     rdx, [rbp+var_20]
0x14000a658  mov     rcx, rbx
0x14000a65b  mov     rax, rsi
0x14000a65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a663  mov     ebx, eax
0x14000a665  test    eax, eax
0x14000a667  jns     short loc_14000A67A
0x14000a669  lea     r8, aFailedToGetSea; "Failed to get search warnings"
0x14000a670  mov     edx, 370h
0x14000a675  jmp     loc_14000A5D0
0x14000a67a  mov     rcx, [rbp+var_20]
0x14000a67e  lea     rdx, [rbp+var_40]
0x14000a682  mov     rax, [rcx]
0x14000a685  mov     rax, [rax+48h]
0x14000a689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a68e  mov     ebx, eax
0x14000a690  test    eax, eax
0x14000a692  jns     short loc_14000A6A5
0x14000a694  lea     r8, aFailedToGetWar_2; "Failed to get warning count"
0x14000a69b  mov     edx, 373h
0x14000a6a0  jmp     loc_14000A5D0
0x14000a6a5  mov     esi, r14d
0x14000a6a8  cmp     [rbp+var_40], r14d
0x14000a6ac  jle     short loc_14000A714
0x14000a6ae  mov     r15d, 80242017h
0x14000a6b4  mov     rcx, [rbp+var_20]
0x14000a6b8  lea     r8, [rbp+var_30]
0x14000a6bc  mov     [rbp+var_18], r14d
0x14000a6c0  mov     edx, esi
0x14000a6c2  mov     [rbp+var_30], r14
0x14000a6c6  mov     rax, [rcx]
0x14000a6c9  mov     rax, [rax+38h]
0x14000a6cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a6d2  mov     ebx, eax
0x14000a6d4  test    eax, eax
0x14000a6d6  js      short loc_14000A755
0x14000a6d8  mov     rcx, [rbp+var_30]
0x14000a6dc  lea     rdx, [rbp+var_18]
0x14000a6e0  mov     rax, [rcx]
0x14000a6e3  mov     rax, [rax+40h]
0x14000a6e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a6ec  mov     ebx, eax
0x14000a6ee  test    eax, eax
0x14000a6f0  js      short loc_14000A747
0x14000a6f2  cmp     [rbp+var_18], r15d
0x14000a6f6  jz      short loc_14000A736
0x14000a6f8  mov     rcx, [rbp+var_30]
0x14000a6fc  test    rcx, rcx
0x14000a6ff  jz      short loc_14000A70D
0x14000a701  mov     rax, [rcx]
0x14000a704  mov     rax, [rax+10h]
0x14000a708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a70d  inc     esi
0x14000a70f  cmp     esi, [rbp+var_40]
0x14000a712  jl      short loc_14000A6B4
0x14000a714  mov     r9d, [rbp+var_3C]
0x14000a718  mov     ebx, 80004005h
0x14000a71d  lea     r8, aFailedSearchRe; "Failed. Search result code is %u"
0x14000a724  mov     edx, 38Eh
0x14000a729  mov     rcx, rdi
0x14000a72c  call    WusaLogDebugEventA
0x14000a731  jmp     loc_14000A9C8
0x14000a736  mov     ebx, r15d
0x14000a739  lea     r8, aUpdateRequires; "Update requires new servicing stack"
0x14000a740  mov     edx, 384h
0x14000a745  jmp     short loc_14000A761
0x14000a747  lea     r8, aFailedToGetWar_0; "Failed to get warning HRESULsT"
0x14000a74e  mov     edx, 37Dh
0x14000a753  jmp     short loc_14000A761
0x14000a755  lea     r8, aFailedToGetWar_1; "Failed to get warning"
0x14000a75c  mov     edx, 37Ah
0x14000a761  mov     rcx, rdi
0x14000a764  call    WusaLogDebugEventA
0x14000a769  mov     rcx, [rbp+var_30]
0x14000a76d  test    rcx, rcx
0x14000a770  jz      loc_14000A9C8
0x14000a776  mov     rax, [rcx]
0x14000a779  mov     rax, [rax+10h]
0x14000a77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a782  jmp     loc_14000A9C8
0x14000a787  mov     rcx, [rbp+var_48]
0x14000a78b  mov     rbx, [rbp+var_10]
0x14000a78f  mov     rax, [rbx]
0x14000a792  mov     [rbp+var_48], r14
0x14000a796  mov     rsi, [rax+48h]
0x14000a79a  test    rcx, rcx
0x14000a79d  jz      short loc_14000A7AB
0x14000a79f  mov     rdx, [rcx]
0x14000a7a2  mov     rax, [rdx+10h]
0x14000a7a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7ab  lea     rdx, [rbp+var_48]
0x14000a7af  mov     rcx, rbx
0x14000a7b2  mov     rax, rsi
0x14000a7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7ba  mov     ebx, eax
0x14000a7bc  test    eax, eax
0x14000a7be  jns     short loc_14000A7D1
0x14000a7c0  lea     r8, aFailedToGetUpd_5; "Failed to get update collection from se"...
0x14000a7c7  mov     edx, 391h
0x14000a7cc  jmp     loc_14000A5D0
0x14000a7d1  mov     rcx, [rbp+var_48]
0x14000a7d5  lea     rdx, [rbp+var_14]
0x14000a7d9  mov     rax, [rcx]
0x14000a7dc  mov     rax, [rax+50h]
0x14000a7e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7e5  mov     ebx, eax
0x14000a7e7  test    eax, eax
0x14000a7e9  jns     short loc_14000A7FC
0x14000a7eb  lea     r8, aFailedToGetCou_0; "Failed to get count of updates to insta"...
0x14000a7f2  mov     edx, 394h
0x14000a7f7  jmp     loc_14000A5D0
0x14000a7fc  mov     eax, [rbp+var_14]
0x14000a7ff  cmp     eax, 1
0x14000a802  jle     short loc_14000A81A
0x14000a804  mov     ebx, 80004005h
0x14000a809  lea     r8, aThereShouldBeO; "There should be only one update to inst"...
0x14000a810  mov     edx, 399h
0x14000a815  jmp     loc_14000A5D0
0x14000a81a  test    eax, eax
0x14000a81c  jg      short loc_14000A872
0x14000a81e  lea     r8, aThereIsNoUpdat; "There is no update bundle to install"
0x14000a825  mov     edx, 39Eh
0x14000a82a  mov     rcx, rdi
0x14000a82d  call    WusaLogDebugEventA
0x14000a832  mov     edx, 0EA60h; DWORD
0x14000a837  mov     [rsp+78h+var_58], r14; int *
0x14000a83c  mov     r9d, 0FFFEh; pszIcon
0x14000a842  mov     r8d, 1; dwCommonButtons
0x14000a848  lea     ecx, [rdx+4]; dwMessageId
0x14000a84b  call    ?WusaMessageBox@@YAJHHHPEBGPEAHZZ; WusaMessageBox(int,int,int,ushort const *,int *,...)
0x14000a850  test    eax, eax
0x14000a852  jns     short loc_14000A868
0x14000a854  lea     r8, aFailedToDispla_4; "Failed to display no-update message box"
0x14000a85b  mov     edx, 3A2h
0x14000a860  mov     rcx, rdi
0x14000a863  call    WusaLogDebugEventA
0x14000a868  mov     ebx, 80240017h
0x14000a86d  jmp     loc_14000A9C8
0x14000a872  mov     rcx, [rbp+var_28]
0x14000a876  mov     rbx, [rbp+var_48]
0x14000a87a  mov     rax, [rbx]
0x14000a87d  mov     [rbp+var_28], r14
0x14000a881  mov     rsi, [rax+38h]
0x14000a885  test    rcx, rcx
0x14000a888  jz      short loc_14000A896
0x14000a88a  mov     rdx, [rcx]
0x14000a88d  mov     rax, [rdx+10h]
0x14000a891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a896  lea     r8, [rbp+var_28]
0x14000a89a  xor     edx, edx
0x14000a89c  mov     rcx, rbx
0x14000a89f  mov     rax, rsi
0x14000a8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a8a7  mov     ebx, eax
0x14000a8a9  test    eax, eax
0x14000a8ab  jns     short loc_14000A8BE
0x14000a8ad  lea     r8, aFailedToGetUpd_3; "Failed to get update out of collection"
0x14000a8b4  mov     edx, 3AAh
0x14000a8b9  jmp     loc_14000A5D0
0x14000a8be  mov     r14, [rbp+var_28]
0x14000a8c2  mov     rsi, [rbp+bstrString]
0x14000a8c6  mov     rax, [r14]
0x14000a8c9  mov     r15, [rax+38h]
0x14000a8cd  test    rsi, rsi
0x14000a8d0  jz      short loc_14000A8EB
0x14000a8d2  call    cs:__imp_GetLastError
0x14000a8d8  mov     rcx, rsi; bstrString
0x14000a8db  mov     ebx, eax
0x14000a8dd  call    cs:__imp_SysFreeString
0x14000a8e3  mov     ecx, ebx; dwErrCode
0x14000a8e5  call    cs:__imp_SetLastError
0x14000a8eb  lea     rdx, [rbp+bstrString]
0x14000a8ef  mov     [rbp+bstrString], 0
0x14000a8f7  mov     rcx, r14
0x14000a8fa  mov     rax, r15
0x14000a8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a902  xor     r14d, r14d
0x14000a905  mov     ebx, eax
0x14000a907  test    eax, eax
0x14000a909  jns     short loc_14000A91C
0x14000a90b  lea     r8, aFailedToGetUpd_7; "Failed to get update title"
0x14000a912  mov     edx, 3ADh
0x14000a917  jmp     loc_14000A5D0
0x14000a91c  mov     rcx, [rbp+var_28]
0x14000a920  lea     rdx, [rbp+arg_0]
0x14000a924  mov     [rbp+arg_0], r14w
0x14000a929  mov     rax, [rcx]
0x14000a92c  mov     rax, [rax+0D0h]
0x14000a933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a938  mov     ebx, eax
0x14000a93a  test    eax, eax
0x14000a93c  jns     short loc_14000A94F
0x14000a93e  lea     r8, aFailedToQueryW; "Failed to query whether update is alrea"...
0x14000a945  mov     edx, 3B1h
0x14000a94a  jmp     loc_14000A5D0
0x14000a94f  cmp     [rbp+arg_0], 0FFFFh
0x14000a954  jnz     short loc_14000A9B0
0x14000a956  lea     r8, aUpdateIsAlread; "Update is already installed"
  ... truncated ...
```
