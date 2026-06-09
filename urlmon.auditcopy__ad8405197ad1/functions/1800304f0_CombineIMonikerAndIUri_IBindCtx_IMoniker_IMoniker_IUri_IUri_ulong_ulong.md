# CombineIMonikerAndIUri(IBindCtx *,IMoniker *,IMoniker *,IUri *,IUri * *,ulong,ulong)

- ea: `0x1800304f0`
- end: `0x1800309e7`
- name: `?CombineIMonikerAndIUri@@YAJPEAUIBindCtx@@PEAUIMoniker@@1PEAUIUri@@PEAPEAU3@KK@Z`
- size: `1271`
- prototype: `__int64 __fastcall(struct IBindCtx *, struct IMoniker *, struct IMoniker *, struct IUri *, struct IUri **, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f4fc`
- `0x18002f604`
- `0x18002ff10`
- `0x1800f42b0`

## callees

- `0x18001db50`
- `0x18001db94`
- `0x1800304f0`
- `0x18003e100`
- `0x1800672a0`
- `0x1800a5e20`
- `0x1801285e6`
- `0x180129010`

## import_xrefs

- `iertutil!CreateUri` at `0x18003098d`
- `iertutil!CreateUri` at `0x18003098d`
- `iertutil!GetIUriPriv` at `0x180030613`
- `iertutil!GetIUriPriv` at `0x180030613`
- `iertutil!PrivateCoInternetCanonicalizeIUri` at `0x180030716`
- `iertutil!PrivateCoInternetCanonicalizeIUri` at `0x180030716`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800306a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030852`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800306a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030852`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030677`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800309d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800309d6`

## pseudocode

```c
__int64 __fastcall CombineIMonikerAndIUri(
        struct IBindCtx *a1,
        struct IMoniker *a2,
        struct IMoniker *a3,
        struct IUri *a4,
        struct IUri **a5,
        unsigned int a6,
        unsigned int a7)
{
  unsigned int v10; // r13d
  int v11; // r14d
  int IUriPriv; // ebx
  HRESULT v13; // eax
  int v14; // r15d
  void *v15; // rdi
  COInetSession *v16; // rax
  COInetSession *v17; // rbx
  int v18; // eax
  __int64 v19; // rbx
  COInetSession *v21; // rax
  int v22; // r9d
  unsigned int v23; // r8d
  struct IMoniker *v24; // rcx
  struct IMonikerVtbl *lpVtbl; // rax
  DWORD v26; // eax
  IUri *v27; // rcx
  __int64 v28; // [rsp+38h] [rbp-21h] BYREF
  struct IMoniker *v29; // [rsp+40h] [rbp-19h] BYREF
  IUri *ppURI; // [rsp+48h] [rbp-11h] BYREF
  __int64 v31; // [rsp+50h] [rbp-9h] BYREF
  LPCWSTR pwzURI; // [rsp+58h] [rbp-1h] BYREF
  struct IUri *v33; // [rsp+60h] [rbp+7h] BYREF
  void *v34; // [rsp+68h] [rbp+Fh] BYREF
  int v35; // [rsp+B0h] [rbp+57h] BYREF

  v10 = a6;
  v11 = 0;
  v31 = 0;
  IUriPriv = 0;
  v29 = 0;
  ppURI = 0;
  v33 = 0;
  pwzURI = 0;
  v35 = 0;
  if ( a2 )
  {
    v29 = a2;
    v24 = a2;
    lpVtbl = a2->lpVtbl;
LABEL_65:
    ((void (__fastcall *)(struct IMoniker *, struct IMoniker *, struct IMoniker *))lpVtbl->AddRef)(v24, a2, a3);
    goto LABEL_4;
  }
  if ( !a1 )
  {
    if ( !a3 )
      goto LABEL_14;
    v29 = a3;
    v24 = a3;
    lpVtbl = a3->lpVtbl;
    goto LABEL_65;
  }
  IUriPriv = ((__int64 (__fastcall *)(struct IBindCtx *, const wchar_t *, struct IMoniker **))a1->lpVtbl->GetObjectParam)(
               a1,
               L"URL Context",
               &v29);
  if ( IUriPriv < 0 )
  {
    v29 = 0;
    IUriPriv = 0;
    goto LABEL_14;
  }
LABEL_4:
  if ( v29 )
  {
    LODWORD(v28) = 0;
    IUriPriv = ((__int64 (__fastcall *)(struct IMoniker *, __int64 *))v29->lpVtbl->IsSystemMoniker)(v29, &v28);
    if ( IUriPriv < 0 )
      goto LABEL_36;
    if ( (_DWORD)v28 != 6 )
      goto LABEL_14;
    if ( ((__int64 (__fastcall *)(struct IMoniker *, GUID *, __int64 *))v29->lpVtbl->QueryInterface)(
           v29,
           &IID_IUriContainer,
           &v31) >= 0
      && v31 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, IUri **))(*(_QWORD *)v31 + 24LL))(v31, &ppURI);
    }
    else
    {
      IUriPriv = ((__int64 (__fastcall *)(struct IMoniker *, struct IBindCtx *, _QWORD, LPCWSTR *))v29->lpVtbl->GetDisplayName)(
                   v29,
                   a1,
                   0,
                   &pwzURI);
      if ( IUriPriv < 0 )
        goto LABEL_36;
      v26 = HelperAddUriDefaultFlags(50342784, v10);
      v13 = CreateUri(pwzURI, v26, 0, &ppURI);
    }
    IUriPriv = v13;
  }
  if ( IUriPriv < 0 )
    goto LABEL_36;
LABEL_14:
  v14 = a7;
  if ( !a4 )
    goto LABEL_29;
  v28 = 0;
  IUriPriv = GetIUriPriv(a4, &v28);
  if ( IUriPriv < 0 )
    goto LABEL_36;
  if ( v28 )
  {
    IUriPriv = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 360LL))(v28, &v35);
    if ( IUriPriv >= 0 && (v35 & 0x20) == 0 && (v10 & 0x10) == 0 )
    {
      v34 = 0;
      v15 = 0;
      EnterCriticalSection(&g_mxsOInet);
      v16 = g_pCOInetSession;
      if ( g_pCOInetSession
        || ((v21 = (COInetSession *)operator new(0x180u)) == 0 || (v16 = COInetSession::COInetSession(v21)) == 0
          ? (COInetSession *)(v16 = g_pCOInetSession, v11 = -2147024882)
          : (g_pCOInetSession = v16),
            v16) )
      {
        _InterlockedIncrement((volatile signed __int32 *)v16 + 4);
        v17 = g_pCOInetSession;
        LeaveCriticalSection(&g_mxsOInet);
        if ( !v11 )
        {
          if ( v17 )
          {
            if ( !memcmp_0(&GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b, &IID_IInternetProtocolInfo, 0x10u) )
            {
              v15 = (char *)v17 + 8;
              v19 = (__int64)v17 + 16;
              _InterlockedIncrement((volatile signed __int32 *)v19);
            }
            else
            {
              v18 = COInetSession::QueryInterface(v17, &GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b, &v34);
              v19 = (__int64)v17 + 16;
              if ( !v18 )
                v15 = v34;
            }
          }
          else
          {
            v19 = 16;
          }
          _InterlockedDecrement((volatile signed __int32 *)v19);
        }
      }
      else
      {
        LeaveCriticalSection(&g_mxsOInet);
      }
      IUriPriv = PrivateCoInternetCanonicalizeIUri(a4, 0x10000, &v33, v15, v14);
      if ( v15 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
LABEL_29:
    if ( IUriPriv < 0 )
      goto LABEL_36;
  }
  if ( v33 )
    a4 = v33;
  if ( ppURI )
  {
    if ( a4 )
    {
      v22 = ((v10 & 0x80) << 18) | 0x10000;
      if ( (v10 & 0x20) == 0 )
        v22 = (v10 & 0x80) << 18;
      v23 = v22 | 0x8000000;
      if ( (a6 & 0x10) == 0 )
        v23 = v22;
      IUriPriv = CoInternetCombineIUriInternal((__int64)ppURI, (__int64)a4, v23, (__int64)a5, 0, v14);
    }
    else
    {
      v27 = ppURI;
      *a5 = ppURI;
      ((void (__fastcall *)(IUri *))v27->lpVtbl->AddRef)(v27);
    }
  }
  else if ( !a4 || a2 && (v35 & 0x20) != 0 )
  {
    IUriPriv = -2147024809;
  }
  else
  {
    *a5 = a4;
    ((void (__fastcall *)(struct IUri *))a4->lpVtbl->AddRef)(a4);
  }
LABEL_36:
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( ppURI )
  {
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
    ppURI = 0;
  }
  if ( v29 )
  {
    ((void (__fastcall *)(struct IMoniker *))v29->lpVtbl->Release)(v29);
    v29 = 0;
  }
  if ( pwzURI )
    CoTaskMemFree((LPVOID)pwzURI);
  if ( v33 )
    ((void (__fastcall *)(struct IUri *))v33->lpVtbl->Release)(v33);
  return (unsigned int)IUriPriv;
}

```

## disassembly

```asm
0x1800304f0  mov     rax, rsp
0x1800304f3  push    rbp
0x1800304f4  push    rbx
0x1800304f5  lea     rbp, [rax-47h]
0x1800304f9  sub     rsp, 88h
0x180030500  mov     [rax+8], rsi
0x180030504  mov     rsi, r9
0x180030507  mov     [rax+18h], rdi
0x18003050b  mov     rdi, rcx
0x18003050e  mov     [rax+20h], r12
0x180030512  mov     r12, rdx
0x180030515  mov     [rax-18h], r13
0x180030519  mov     r13d, [rbp+3Fh+arg_28]
0x18003051d  mov     [rax-20h], r14
0x180030521  xor     r14d, r14d
0x180030524  mov     [rbp+3Fh+var_48], r14
0x180030528  mov     ebx, r14d
0x18003052b  mov     [rbp+3Fh+var_58], r14
0x18003052f  mov     [rbp+3Fh+ppURI], r14
0x180030533  mov     [rbp+3Fh+var_38], r14
0x180030537  mov     [rbp+3Fh+pwzURI], r14
0x18003053b  mov     [rbp+3Fh+arg_8], r14d
0x18003053f  test    rdx, rdx
0x180030542  jnz     loc_18003091C
0x180030548  test    rcx, rcx
0x18003054b  jz      loc_1800305ED
0x180030551  mov     rax, [rcx]
0x180030554  lea     r8, [rbp+3Fh+var_58]
0x180030558  lea     rdx, aUrlContext; "URL Context"
0x18003055f  mov     rax, [rax+50h]
0x180030563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030568  mov     ebx, eax
0x18003056a  test    eax, eax
0x18003056c  js      loc_180030928
0x180030572  mov     rcx, [rbp+3Fh+var_58]
0x180030576  test    rcx, rcx
0x180030579  jz      short loc_1800305E3
0x18003057b  mov     dword ptr [rbp+3Fh+var_60], r14d
0x18003057f  lea     rdx, [rbp+3Fh+var_60]
0x180030583  mov     rax, [rcx]
0x180030586  mov     rax, [rax+0B0h]
0x18003058d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030592  mov     ebx, eax
0x180030594  test    eax, eax
0x180030596  js      loc_180030794
0x18003059c  cmp     dword ptr [rbp+3Fh+var_60], 6
0x1800305a0  jnz     short loc_1800305F6
0x1800305a2  mov     rcx, [rbp+3Fh+var_58]
0x1800305a6  lea     r8, [rbp+3Fh+var_48]
0x1800305aa  lea     rdx, IID_IUriContainer
0x1800305b1  mov     rax, [rcx]
0x1800305b4  mov     rax, [rax]
0x1800305b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305bc  test    eax, eax
0x1800305be  js      loc_18003094C
0x1800305c4  mov     rcx, [rbp+3Fh+var_48]
0x1800305c8  test    rcx, rcx
0x1800305cb  jz      loc_18003094C
0x1800305d1  mov     rax, [rcx]
0x1800305d4  lea     rdx, [rbp+3Fh+ppURI]
0x1800305d8  mov     rax, [rax+18h]
0x1800305dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305e1  mov     ebx, eax
0x1800305e3  test    ebx, ebx
0x1800305e5  js      loc_180030794
0x1800305eb  jmp     short loc_1800305F6
0x1800305ed  test    r8, r8
0x1800305f0  jnz     loc_180030934
0x1800305f6  mov     [rsp+90h+var_20], r15
0x1800305fb  mov     r15d, [rbp+3Fh+arg_30]
0x1800305ff  test    rsi, rsi
0x180030602  jz      loc_18003074B
0x180030608  lea     rdx, [rbp+3Fh+var_60]
0x18003060c  mov     [rbp+3Fh+var_60], r14
0x180030610  mov     rcx, rsi
0x180030613  call    cs:__imp_GetIUriPriv
0x18003061a  nop     dword ptr [rax+rax+00h]
0x18003061f  mov     ebx, eax
0x180030621  test    eax, eax
0x180030623  js      loc_18003078F
0x180030629  mov     rcx, [rbp+3Fh+var_60]
0x18003062d  test    rcx, rcx
0x180030630  jz      loc_18003074F
0x180030636  mov     rax, [rcx]
0x180030639  lea     rdx, [rbp+3Fh+arg_8]
0x18003063d  mov     rax, [rax+168h]
0x180030644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030649  mov     ebx, eax
0x18003064b  test    eax, eax
0x18003064d  js      loc_18003073B
0x180030653  test    byte ptr [rbp+3Fh+arg_8], 20h
0x180030657  setz    cl
0x18003065a  test    r13b, 10h
0x18003065e  setz    al
0x180030661  test    al, cl
0x180030663  jz      loc_18003073B
0x180030669  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x180030670  mov     [rbp+3Fh+var_30], r14
0x180030674  mov     rdi, r14
0x180030677  call    cs:__imp_EnterCriticalSection
0x18003067e  nop     dword ptr [rax+rax+00h]
0x180030683  mov     rax, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x18003068a  test    rax, rax
0x18003068d  jz      loc_18003081F
0x180030693  lock inc dword ptr [rax+10h]
0x180030697  mov     rbx, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x18003069e  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x1800306a5  call    cs:__imp_LeaveCriticalSection
0x1800306ac  nop     dword ptr [rax+rax+00h]
0x1800306b1  test    r14d, r14d
0x1800306b4  jnz     short loc_180030702
0x1800306b6  test    rbx, rbx
0x1800306b9  jz      loc_1800308BE
0x1800306bf  mov     r8d, 10h; Size
0x1800306c5  lea     rdx, IID_IInternetProtocolInfo; Buf2
0x1800306cc  lea     rcx, _GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b; Buf1
0x1800306d3  call    memcmp_0
0x1800306d8  test    eax, eax
0x1800306da  jz      loc_18003080F
0x1800306e0  lea     r8, [rbp+3Fh+var_30]; void **
0x1800306e4  mov     rcx, rbx; this
0x1800306e7  lea     rdx, _GUID_79eac9ec_baf9_11ce_8c82_00aa004ba90b; struct _GUID *
0x1800306ee  call    ?QueryInterface@COInetSession@@UEAAJAEBU_GUID@@PEAPEAX@Z; COInetSession::QueryInterface(_GUID const &,void * *)
0x1800306f3  add     rbx, 10h
0x1800306f7  test    eax, eax
0x1800306f9  jz      loc_18003099E
0x1800306ff  lock dec dword ptr [rbx]
0x180030702  mov     r9, rdi
0x180030705  mov     [rsp+90h+var_70], r15d
0x18003070a  lea     r8, [rbp+3Fh+var_38]
0x18003070e  mov     edx, 10000h
0x180030713  mov     rcx, rsi
0x180030716  call    cs:__imp_PrivateCoInternetCanonicalizeIUri
0x18003071d  nop     dword ptr [rax+rax+00h]
0x180030722  mov     ebx, eax
0x180030724  test    rdi, rdi
0x180030727  jz      short loc_180030738
0x180030729  mov     rax, [rdi]
0x18003072c  mov     rcx, rdi
0x18003072f  mov     rax, [rax+10h]
0x180030733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030738  xor     r14d, r14d
0x18003073b  mov     rcx, [rbp+3Fh+var_60]
0x18003073f  mov     rax, [rcx]
0x180030742  mov     rax, [rax+10h]
0x180030746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003074b  test    ebx, ebx
0x18003074d  js      short loc_18003078F
0x18003074f  mov     rcx, [rbp+3Fh+var_38]
0x180030753  mov     r10, [rbp+3Fh+ppURI]
0x180030757  test    rcx, rcx
0x18003075a  cmovnz  rsi, rcx
0x18003075e  test    r10, r10
0x180030761  jnz     loc_1800308C7
0x180030767  test    rsi, rsi
0x18003076a  jz      loc_180030863
0x180030770  test    r12, r12
0x180030773  jnz     loc_1800309C6
0x180030779  mov     rax, [rbp+3Fh+arg_20]
0x18003077d  mov     rcx, rsi
0x180030780  mov     [rax], rsi
0x180030783  mov     rax, [rsi]
0x180030786  mov     rax, [rax+8]
0x18003078a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003078f  mov     r15, [rsp+90h+var_20]
0x180030794  mov     rcx, [rbp+3Fh+var_48]
0x180030798  mov     r13, [rsp+80h]
0x1800307a0  mov     r12, [rsp+90h+arg_18]
0x1800307a8  mov     rdi, [rsp+90h+arg_10]
0x1800307b0  mov     rsi, [rsp+90h+arg_0]
0x1800307b8  test    rcx, rcx
0x1800307bb  jnz     loc_18003087C
0x1800307c1  mov     r10, [rbp+3Fh+ppURI]
0x1800307c5  test    r10, r10
0x1800307c8  jnz     loc_1800308A6
0x1800307ce  mov     rcx, [rbp+3Fh+var_58]
0x1800307d2  test    rcx, rcx
0x1800307d5  jnz     loc_180030891
0x1800307db  mov     rcx, [rbp+3Fh+pwzURI]; pv
0x1800307df  mov     r14, [rsp+90h+var_18]
0x1800307e4  test    rcx, rcx
0x1800307e7  jnz     loc_1800309D6
0x1800307ed  mov     rcx, [rbp+3Fh+var_38]
0x1800307f1  test    rcx, rcx
0x1800307f4  jz      short loc_180030802
0x1800307f6  mov     rax, [rcx]
0x1800307f9  mov     rax, [rax+10h]
0x1800307fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030802  mov     eax, ebx
0x180030804  add     rsp, 88h
0x18003080b  pop     rbx
0x18003080c  pop     rbp
0x18003080d  retn
0x18003080f  lea     rdi, [rbx+8]
0x180030813  add     rbx, 10h
0x180030817  lock inc dword ptr [rbx]
0x18003081a  jmp     loc_1800306FF
0x18003081f  mov     ecx, 180h; Size
0x180030824  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030829  test    rax, rax
0x18003082c  jz      short loc_18003086D
0x18003082e  mov     rcx, rax; this
0x180030831  call    ??0COInetSession@@QEAA@XZ; COInetSession::COInetSession(void)
0x180030836  test    rax, rax
0x180030839  jz      short loc_18003086D
0x18003083b  mov     cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA, rax; COInetSession * g_pCOInetSession
0x180030842  test    rax, rax
0x180030845  jnz     loc_180030693
0x18003084b  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x180030852  call    cs:__imp_LeaveCriticalSection
0x180030859  nop     dword ptr [rax+rax+00h]
0x18003085e  jmp     loc_180030702
0x180030863  mov     ebx, 80070057h
0x180030868  jmp     loc_18003078F
0x18003086d  mov     rax, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x180030874  mov     r14d, 8007000Eh
0x18003087a  jmp     short loc_180030842
0x18003087c  mov     rax, [rcx]
0x18003087f  mov     rax, [rax+10h]
0x180030883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030888  mov     [rbp+3Fh+var_48], r14
0x18003088c  jmp     loc_1800307C1
0x180030891  mov     rax, [rcx]
0x180030894  mov     rax, [rax+10h]
0x180030898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003089d  mov     [rbp+3Fh+var_58], r14
0x1800308a1  jmp     loc_1800307DB
0x1800308a6  mov     rax, [r10]
0x1800308a9  mov     rcx, r10
0x1800308ac  mov     rax, [rax+10h]
0x1800308b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308b5  mov     [rbp+3Fh+ppURI], r14
0x1800308b9  jmp     loc_1800307CE
0x1800308be  add     rbx, 10h
0x1800308c2  jmp     loc_1800306FF
0x1800308c7  test    rsi, rsi
0x1800308ca  jz      loc_1800309A7
0x1800308d0  mov     ecx, r13d
0x1800308d3  mov     [rsp+28h], r15d
0x1800308d8  and     ecx, 80h
0x1800308de  mov     qword ptr [rsp+90h+var_70], r14
0x1800308e3  shl     ecx, 12h
0x1800308e6  mov     rdx, rsi
0x1800308e9  mov     r9d, ecx
0x1800308ec  bts     r9d, 10h
0x1800308f1  test    r13b, 20h
0x1800308f5  cmovz   r9d, ecx
0x1800308f9  mov     rcx, r10
0x1800308fc  mov     r8d, r9d
0x1800308ff  bts     r8d, 1Bh
0x180030904  test    byte ptr [rbp+3Fh+arg_28], 10h
0x180030908  cmovz   r8d, r9d
0x18003090c  mov     r9, [rbp+3Fh+arg_20]
0x180030910  call    CoInternetCombineIUriInternal
0x180030915  mov     ebx, eax
0x180030917  jmp     loc_18003078F
0x18003091c  mov     [rbp+3Fh+var_58], r12
0x180030920  mov     rcx, r12
0x180030923  mov     rax, [rdx]
0x180030926  jmp     short loc_18003093E
0x180030928  mov     [rbp+3Fh+var_58], r14
0x18003092c  mov     ebx, r14d
0x18003092f  jmp     loc_1800305F6
0x180030934  mov     [rbp+3Fh+var_58], r8
0x180030938  mov     rcx, r8
0x18003093b  mov     rax, [r8]
0x18003093e  mov     rax, [rax+8]
0x180030942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030947  jmp     loc_180030572
0x18003094c  mov     rcx, [rbp+3Fh+var_58]
0x180030950  lea     r9, [rbp+3Fh+pwzURI]
0x180030954  xor     r8d, r8d
0x180030957  mov     rdx, rdi
0x18003095a  mov     rax, [rcx]
0x18003095d  mov     rax, [rax+0A0h]
0x180030964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030969  mov     ebx, eax
0x18003096b  test    eax, eax
0x18003096d  js      loc_180030794
0x180030973  mov     edx, r13d; unsigned int
0x180030976  mov     ecx, 3002B80h; unsigned int
0x18003097b  call    ?HelperAddUriDefaultFlags@@YAKKK@Z; HelperAddUriDefaultFlags(ulong,ulong)
0x180030980  mov     rcx, [rbp+3Fh+pwzURI]; pwzURI
0x180030984  lea     r9, [rbp+3Fh+ppURI]; ppURI
0x180030988  mov     edx, eax; dwFlags
0x18003098a  xor     r8d, r8d; dwReserved
0x18003098d  call    cs:__imp_CreateUri
0x180030994  nop     dword ptr [rax+rax+00h]
0x180030999  jmp     loc_1800305E1
0x18003099e  mov     rdi, [rbp+3Fh+var_30]
0x1800309a2  jmp     loc_1800306FF
0x1800309a7  mov     r10, [rbp+3Fh+ppURI]
0x1800309ab  mov     rax, [rbp+3Fh+arg_20]
0x1800309af  mov     rcx, r10
0x1800309b2  mov     [rax], r10
0x1800309b5  mov     rax, [r10]
0x1800309b8  mov     rax, [rax+8]
0x1800309bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309c1  jmp     loc_18003078F
0x1800309c6  mov     eax, [rbp+3Fh+arg_8]
  ... truncated ...
```
