# CCDLAgent::StartDownload(void)

- ea: `0x180004300`
- end: `0x18000476a`
- name: `?StartDownload@CCDLAgent@@MEAAJXZ`
- size: `1130`
- prototype: `__int64 __fastcall(CCDLAgent *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180003950`
- `0x180004300`
- `0x180004770`
- `0x180005674`
- `0x18001ba08`
- `0x18001ba40`
- `0x18002a010`

## import_xrefs

- `ole32!CreateBindCtx` at `0x1800045df`
- `ole32!CreateBindCtx` at `0x1800045df`
- `ole32!CoCreateInstance` at `0x180004362`
- `ole32!CoCreateInstance` at `0x18000439f`
- `ole32!CoCreateInstance` at `0x18000448a`
- `ole32!CoCreateInstance` at `0x180004362`
- `ole32!CoCreateInstance` at `0x18000439f`
- `ole32!CoCreateInstance` at `0x18000448a`
- `urlmon!RegisterBindStatusCallback` at `0x180004600`
- `urlmon!RegisterBindStatusCallback` at `0x180004600`

## pseudocode

```c
__int64 __fastcall CCDLAgent::StartDownload(CCDLAgent *this)
{
  HRESULT Instance; // ebx
  _QWORD *v3; // r15
  int v4; // r14d
  unsigned int v5; // eax
  HRESULT v6; // eax
  int v7; // ecx
  bool v8; // zf
  int v9; // eax
  int v10; // ecx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rbx
  int v13; // edx
  int v14; // ecx
  const unsigned __int16 *v15; // r8
  __int64 v16; // rcx
  HRESULT v17; // eax
  _DWORD *v18; // rax
  void *v19; // rsi
  __int64 v20; // rax
  void *lpMem; // [rsp+50h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-18h] BYREF
  LPVOID v24; // [rsp+60h] [rbp-10h] BYREF
  int v25; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v26; // [rsp+B8h] [rbp+48h] BYREF
  int v27; // [rsp+C0h] [rbp+50h] BYREF
  LPBC ppbc; // [rsp+C8h] [rbp+58h] BYREF

  Instance = *((_DWORD *)this + 27);
  ppbc = 0;
  lpMem = 0;
  v26 = 0;
  v25 = 0;
  v27 = 0;
  ppv = 0;
  if ( Instance < 0 )
  {
LABEL_51:
    v20 = *(_QWORD *)this;
    *((_DWORD *)this + 27) = Instance;
    (*(void (__fastcall **)(CCDLAgent *))(v20 + 120))(this);
    return (unsigned int)Instance;
  }
  v3 = (_QWORD *)((char *)this + 240);
  v4 = 0;
  Instance = CoCreateInstance(&CLSID_SoftDistExt, 0, 1u, &IID_ISoftDistExt, (LPVOID *)this + 30);
  if ( Instance >= 0 )
  {
    if ( *((_QWORD *)this + 15) )
    {
      v25 = -65536;
      if ( CoCreateInstance(&CLSID_InternetSecurityManager, 0, 1u, &IID_IInternetSecurityManager, &ppv) < 0 || !ppv )
        goto LABEL_28;
      Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, int *, int, int *, int, int, _DWORD))(*(_QWORD *)ppv + 56LL))(
                   ppv,
                   *((_QWORD *)this + 16),
                   7685,
                   &v25,
                   4,
                   &v27,
                   4,
                   1,
                   0);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( Instance < 0 )
        goto LABEL_47;
      v5 = v25 & 0xFFFF0000;
      v25 = v5;
      if ( v5 == 0x10000 )
      {
LABEL_28:
        Instance = -2147024891;
        goto LABEL_47;
      }
      if ( ((v5 - 0x20000) & 0xFFFEFFFF) != 0 )
      {
        Instance = -2147024809;
        goto LABEL_47;
      }
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *))(*(_QWORD *)*v3 + 24LL))(
             *v3,
             *((_QWORD *)this + 16),
             *((_QWORD *)this + 15),
             (char *)this + 144);
      Instance = v6;
      if ( (*((_BYTE *)this + 148) & 8) != 0 )
      {
        v24 = 0;
        if ( CoCreateInstance(&CLSID_SubscriptionMgr, 0, 1u, &IID_ISubscriptionMgr, &v24) >= 0 )
        {
          (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)v24 + 24LL))(v24, *((_QWORD *)this + 16), 0);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
        }
        Instance = 1;
        goto LABEL_14;
      }
      if ( v6 )
      {
LABEL_14:
        *((_QWORD *)this + 31) = 0;
LABEL_15:
        v4 = 1;
        goto LABEL_47;
      }
      v7 = *((_DWORD *)this + 37);
      *((_DWORD *)this + 63) = v7 != 0;
      if ( (v7 & 4) != 0 )
      {
        v8 = v25 == 196608;
        *((_DWORD *)this + 64) = 0;
        v9 = v8;
      }
      else
      {
        v9 = ((unsigned __int8)v7 >> 1) & 1;
      }
      *((_DWORD *)this + 62) = v9;
      if ( !v9 )
        goto LABEL_15;
      v10 = *((_DWORD *)this + 65) & 4;
      if ( (*((_DWORD *)this + 65) & 2) == 0 && !v10 )
        goto LABEL_15;
      if ( v10 )
        *((_DWORD *)this + 67) = 0;
    }
    v11 = (unsigned __int16 *)operator new(0x1088u);
    v12 = v11;
    if ( v11 )
    {
      v13 = *((_DWORD *)this + 67);
      v14 = *((_DWORD *)this + 64);
      v15 = (const unsigned __int16 *)*((_QWORD *)this + 16);
      *(_QWORD *)v11 = &CDLAgentBSC::`vftable'{for `IBindStatusCallback'};
      *((_QWORD *)v11 + 1) = &CDLAgentBSC::`vftable'{for `IServiceProvider'};
      *((_DWORD *)v11 + 11) = v14;
      *((_DWORD *)v11 + 12) = v13 << 10;
      *((_QWORD *)v11 + 2) = &CDLAgentBSC::`vftable'{for `IInternetHostSecurityManager'};
      *((_DWORD *)v11 + 10) = 1;
      *((_QWORD *)v11 + 3) = 0;
      *((_QWORD *)v11 + 4) = this;
      *((_QWORD *)v11 + 528) = 0;
      StringCchCopyW(v11 + 26, 0x824u, v15);
      v16 = *((_QWORD *)v12 + 4);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
    }
    else
    {
      v12 = 0;
    }
    *((_QWORD *)this + 29) = v12;
    if ( !v12 )
      goto LABEL_31;
    Instance = CreateBindCtx(0, &ppbc);
    if ( Instance >= 0 )
    {
      Instance = RegisterBindStatusCallback(ppbc, *((IBindStatusCallback **)this + 29), 0, 0);
      if ( Instance >= 0 )
      {
        if ( *((_QWORD *)this + 15) )
        {
          v17 = (*(__int64 (__fastcall **)(_QWORD, LPBC, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v3 + 48LL))(
                  *v3,
                  ppbc,
                  0,
                  0,
                  0);
          Instance = v17;
          if ( v17 )
          {
            if ( v17 == -2147467263 )
            {
              if ( (*(int (__fastcall **)(_QWORD, void **, unsigned int *))(*(_QWORD *)*v3 + 32LL))(*v3, &lpMem, &v26) >= 0
                && lpMem )
              {
                Instance = CCDLAgent::StartNextDownload(this, (const unsigned __int16 *)lpMem, v26);
                if ( lpMem )
                {
                  operator delete(lpMem);
                  lpMem = 0;
                }
              }
              else
              {
                v4 = 1;
                Instance = 0;
              }
            }
          }
          else
          {
            CDeliveryAgent::SendUpdateNone(this);
          }
        }
        else
        {
          v18 = operator new(0x28u);
          v19 = v18;
          if ( !v18 )
          {
LABEL_31:
            Instance = -2147024882;
            goto LABEL_47;
          }
          *v18 = 40;
          *((_QWORD *)v18 + 1) = *((_QWORD *)this + 17);
          *((_QWORD *)v18 + 2) = *((_QWORD *)this + 16);
          v18[6] = *((_DWORD *)this + 56);
          v18[7] = *((_DWORD *)this + 57);
          v18[8] = 0;
          Instance = (*(__int64 (__fastcall **)(_QWORD, LPBC, _QWORD, _QWORD, _DWORD *))(*(_QWORD *)*v3 + 48LL))(
                       *v3,
                       ppbc,
                       0,
                       0,
                       v18);
          if ( !Instance )
            CDeliveryAgent::SendUpdateNone(this);
          operator delete(v19);
        }
      }
    }
  }
LABEL_47:
  if ( ppbc )
  {
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    ppbc = 0;
  }
  if ( Instance < 0 || v4 )
    goto LABEL_51;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180004300  push    rbp
0x180004302  push    rbx
0x180004303  push    rsi
0x180004304  push    rdi
0x180004305  push    r12
0x180004307  push    r14
0x180004309  push    r15
0x18000430b  mov     rbp, rsp
0x18000430e  sub     rsp, 70h
0x180004312  mov     ebx, [rcx+6Ch]
0x180004315  xor     r12d, r12d
0x180004318  mov     [rbp+ppbc], r12
0x18000431c  mov     rdi, rcx
0x18000431f  mov     [rbp+lpMem], r12
0x180004323  mov     [rbp+arg_8], r12d
0x180004327  mov     [rbp+arg_0], r12d
0x18000432b  mov     [rbp+arg_10], r12d
0x18000432f  mov     [rbp+var_18], r12
0x180004333  test    ebx, ebx
0x180004335  js      loc_180004747
0x18000433b  lea     r15, [rcx+0F0h]
0x180004342  xor     edx, edx; pUnkOuter
0x180004344  lea     esi, [r12+1]
0x180004349  mov     [rsp+70h+ppv], r15; ppv
0x18000434e  mov     r8d, esi; dwClsContext
0x180004351  lea     r9, IID_ISoftDistExt; riid
0x180004358  lea     rcx, CLSID_SoftDistExt; rclsid
0x18000435f  mov     r14d, r12d
0x180004362  call    cs:__imp_CoCreateInstance
0x180004368  mov     ebx, eax
0x18000436a  test    eax, eax
0x18000436c  js      loc_180004725
0x180004372  cmp     [rdi+78h], r12
0x180004376  jz      loc_180004531
0x18000437c  lea     rax, [rbp+var_18]
0x180004380  mov     [rbp+arg_0], 0FFFF0000h
0x180004387  lea     r9, IID_IInternetSecurityManager; riid
0x18000438e  mov     [rsp+70h+ppv], rax; ppv
0x180004393  mov     r8d, esi; dwClsContext
0x180004396  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x18000439d  xor     edx, edx; pUnkOuter
0x18000439f  call    cs:__imp_CoCreateInstance
0x1800043a5  test    eax, eax
0x1800043a7  js      loc_1800045B6
0x1800043ad  mov     rcx, [rbp+var_18]
0x1800043b1  test    rcx, rcx
0x1800043b4  jz      loc_1800045B6
0x1800043ba  mov     rax, [rcx]
0x1800043bd  lea     r8d, [r12+4]
0x1800043c2  mov     [rsp+70h+var_30], r12d
0x1800043c7  lea     rdx, [rbp+arg_10]
0x1800043cb  mov     [rsp+70h+var_38], esi
0x1800043cf  lea     r9, [rbp+arg_0]
0x1800043d3  mov     [rsp+70h+var_40], r8d
0x1800043d8  mov     rax, [rax+38h]
0x1800043dc  mov     [rsp+70h+var_48], rdx
0x1800043e1  mov     rdx, [rdi+80h]
0x1800043e8  mov     dword ptr [rsp+70h+ppv], r8d
0x1800043ed  mov     r8d, 1E05h
0x1800043f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043f8  mov     rcx, [rbp+var_18]
0x1800043fc  mov     ebx, eax
0x1800043fe  mov     rax, [rcx]
0x180004401  mov     rax, [rax+10h]
0x180004405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000440a  test    ebx, ebx
0x18000440c  js      loc_180004725
0x180004412  mov     eax, [rbp+arg_0]
0x180004415  and     eax, 0FFFF0000h
0x18000441a  mov     [rbp+arg_0], eax
0x18000441d  cmp     eax, 10000h
0x180004422  jz      loc_1800045B6
0x180004428  add     eax, 0FFFE0000h
0x18000442d  test    eax, 0FFFEFFFFh
0x180004432  jz      short loc_18000443E
0x180004434  mov     ebx, 80070057h
0x180004439  jmp     loc_180004725
0x18000443e  mov     rcx, [r15]
0x180004441  lea     r9, [rdi+90h]
0x180004448  mov     r8, [rdi+78h]
0x18000444c  mov     rdx, [rdi+80h]
0x180004453  mov     rax, [rcx]
0x180004456  mov     rax, [rax+18h]
0x18000445a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000445f  test    byte ptr [rdi+94h], 8
0x180004466  mov     ebx, eax
0x180004468  jz      short loc_1800044CF
0x18000446a  lea     rax, [rbp+var_10]
0x18000446e  mov     [rbp+var_10], r12
0x180004472  lea     r9, IID_ISubscriptionMgr; riid
0x180004479  mov     [rsp+70h+ppv], rax; ppv
0x18000447e  mov     r8d, esi; dwClsContext
0x180004481  lea     rcx, CLSID_SubscriptionMgr; rclsid
0x180004488  xor     edx, edx; pUnkOuter
0x18000448a  call    cs:__imp_CoCreateInstance
0x180004490  test    eax, eax
0x180004492  js      short loc_1800044BE
0x180004494  mov     rcx, [rbp+var_10]
0x180004498  xor     r8d, r8d
0x18000449b  mov     rdx, [rdi+80h]
0x1800044a2  mov     rax, [rcx]
0x1800044a5  mov     rax, [rax+18h]
0x1800044a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ae  mov     rcx, [rbp+var_10]
0x1800044b2  mov     rax, [rcx]
0x1800044b5  mov     rax, [rax+10h]
0x1800044b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044be  mov     ebx, esi
0x1800044c0  mov     [rdi+0F8h], r12
0x1800044c7  mov     r14d, esi
0x1800044ca  jmp     loc_180004725
0x1800044cf  test    eax, eax
0x1800044d1  jnz     short loc_1800044C0
0x1800044d3  mov     ecx, [rdi+94h]
0x1800044d9  mov     eax, r12d
0x1800044dc  test    ecx, ecx
0x1800044de  setnz   al
0x1800044e1  mov     [rdi+0FCh], eax
0x1800044e7  test    cl, 4
0x1800044ea  jz      short loc_180004502
0x1800044ec  cmp     [rbp+arg_0], 30000h
0x1800044f3  mov     eax, r12d
0x1800044f6  mov     [rdi+100h], r12d
0x1800044fd  setz    al
0x180004500  jmp     short loc_180004509
0x180004502  movzx   eax, cl
0x180004505  shr     eax, 1
0x180004507  and     eax, esi
0x180004509  mov     [rdi+0F8h], eax
0x18000450f  test    eax, eax
0x180004511  jz      short loc_1800044C7
0x180004513  mov     eax, [rdi+104h]
0x180004519  mov     ecx, eax
0x18000451b  and     ecx, 4
0x18000451e  test    al, 2
0x180004520  jnz     short loc_180004526
0x180004522  test    ecx, ecx
0x180004524  jz      short loc_1800044C7
0x180004526  test    ecx, ecx
0x180004528  jz      short loc_180004531
0x18000452a  mov     [rdi+10Ch], r12d
0x180004531  mov     ecx, 1088h; dwBytes
0x180004536  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000453b  mov     rbx, rax
0x18000453e  test    rax, rax
0x180004541  jz      short loc_1800045C0
0x180004543  mov     edx, [rdi+10Ch]
0x180004549  lea     rax, ??_7CDLAgentBSC@@6BIBindStatusCallback@@@; const CDLAgentBSC::`vftable'{for `IBindStatusCallback'}
0x180004550  mov     ecx, [rdi+100h]
0x180004556  mov     r8, [rdi+80h]; unsigned __int16 *
0x18000455d  mov     [rbx], rax
0x180004560  lea     rax, ??_7CDLAgentBSC@@6BIServiceProvider@@@; const CDLAgentBSC::`vftable'{for `IServiceProvider'}
0x180004567  shl     edx, 0Ah
0x18000456a  mov     [rbx+8], rax
0x18000456e  lea     rax, ??_7CDLAgentBSC@@6BIInternetHostSecurityManager@@@; const CDLAgentBSC::`vftable'{for `IInternetHostSecurityManager'}
0x180004575  mov     [rbx+2Ch], ecx
0x180004578  lea     rcx, [rbx+34h]; unsigned __int16 *
0x18000457c  mov     [rbx+30h], edx
0x18000457f  mov     edx, 824h; unsigned __int64
0x180004584  mov     [rbx+10h], rax
0x180004588  mov     [rbx+28h], esi
0x18000458b  mov     [rbx+18h], r12
0x18000458f  mov     [rbx+20h], rdi
0x180004593  mov     [rbx+1080h], r12
0x18000459a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000459f  mov     rcx, [rbx+20h]
0x1800045a3  test    rcx, rcx
0x1800045a6  jz      short loc_1800045C3
0x1800045a8  mov     rax, [rcx]
0x1800045ab  mov     rax, [rax+8]
0x1800045af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045b4  jmp     short loc_1800045C3
0x1800045b6  mov     ebx, 80070005h
0x1800045bb  jmp     loc_180004725
0x1800045c0  mov     rbx, r12
0x1800045c3  mov     [rdi+0E8h], rbx
0x1800045ca  test    rbx, rbx
0x1800045cd  jnz     short loc_1800045D9
0x1800045cf  mov     ebx, 8007000Eh
0x1800045d4  jmp     loc_180004725
0x1800045d9  lea     rdx, [rbp+ppbc]; ppbc
0x1800045dd  xor     ecx, ecx; reserved
0x1800045df  call    cs:__imp_CreateBindCtx
0x1800045e5  mov     ebx, eax
0x1800045e7  test    eax, eax
0x1800045e9  js      loc_180004725
0x1800045ef  mov     rdx, [rdi+0E8h]; pBSCb
0x1800045f6  xor     r9d, r9d; dwReserved
0x1800045f9  mov     rcx, [rbp+ppbc]; pBC
0x1800045fd  xor     r8d, r8d; ppBSCBPrev
0x180004600  call    cs:__imp_RegisterBindStatusCallback
0x180004606  mov     ebx, eax
0x180004608  test    eax, eax
0x18000460a  js      loc_180004725
0x180004610  cmp     [rdi+78h], r12
0x180004614  jz      loc_1800046AB
0x18000461a  mov     rcx, [r15]
0x18000461d  xor     r9d, r9d
0x180004620  mov     rdx, [rbp+ppbc]
0x180004624  xor     r8d, r8d
0x180004627  mov     [rsp+70h+ppv], r12
0x18000462c  mov     rax, [rcx]
0x18000462f  mov     rax, [rax+30h]
0x180004633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004638  mov     ebx, eax
0x18000463a  test    eax, eax
0x18000463c  jnz     short loc_18000464B
0x18000463e  mov     rcx, rdi; this
0x180004641  call    ?SendUpdateNone@CDeliveryAgent@@IEAAXXZ; CDeliveryAgent::SendUpdateNone(void)
0x180004646  jmp     loc_180004725
0x18000464b  cmp     eax, 80004001h
0x180004650  jnz     loc_180004725
0x180004656  mov     rcx, [r15]
0x180004659  lea     r8, [rbp+arg_8]
0x18000465d  lea     rdx, [rbp+lpMem]
0x180004661  mov     rax, [rcx]
0x180004664  mov     rax, [rax+20h]
0x180004668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000466d  test    eax, eax
0x18000466f  js      short loc_1800046A3
0x180004671  mov     rdx, [rbp+lpMem]; unsigned __int16 *
0x180004675  test    rdx, rdx
0x180004678  jz      short loc_1800046A3
0x18000467a  mov     r8d, [rbp+arg_8]; unsigned int
0x18000467e  mov     rcx, rdi; this
0x180004681  call    ?StartNextDownload@CCDLAgent@@QEAAJPEBGK@Z; CCDLAgent::StartNextDownload(ushort const *,ulong)
0x180004686  mov     rcx, [rbp+lpMem]; lpMem
0x18000468a  mov     ebx, eax
0x18000468c  test    rcx, rcx
0x18000468f  jz      loc_180004725
0x180004695  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000469a  mov     [rbp+lpMem], r12
0x18000469e  jmp     loc_180004725
0x1800046a3  mov     r14d, esi
0x1800046a6  mov     ebx, r12d
0x1800046a9  jmp     short loc_180004725
0x1800046ab  mov     ebx, 28h ; '('
0x1800046b0  mov     ecx, ebx; dwBytes
0x1800046b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800046b7  mov     rsi, rax
0x1800046ba  test    rax, rax
0x1800046bd  jz      loc_1800045CF
0x1800046c3  mov     [rax], ebx
0x1800046c5  xor     r9d, r9d
0x1800046c8  mov     rax, [rdi+88h]
0x1800046cf  xor     r8d, r8d
0x1800046d2  mov     [rsi+8], rax
0x1800046d6  mov     rax, [rdi+80h]
0x1800046dd  mov     [rsi+10h], rax
0x1800046e1  mov     eax, [rdi+0E0h]
0x1800046e7  mov     [rsi+18h], eax
0x1800046ea  mov     eax, [rdi+0E4h]
0x1800046f0  mov     [rsi+1Ch], eax
0x1800046f3  mov     [rsi+20h], r12d
0x1800046f7  mov     rcx, [r15]
0x1800046fa  mov     rdx, [rbp+ppbc]
0x1800046fe  mov     [rsp+70h+ppv], rsi
0x180004703  mov     rax, [rcx]
0x180004706  mov     rax, [rax+30h]
0x18000470a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000470f  mov     ebx, eax
0x180004711  test    eax, eax
0x180004713  jnz     short loc_18000471D
0x180004715  mov     rcx, rdi; this
0x180004718  call    ?SendUpdateNone@CDeliveryAgent@@IEAAXXZ; CDeliveryAgent::SendUpdateNone(void)
0x18000471d  mov     rcx, rsi; lpMem
0x180004720  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004725  mov     rcx, [rbp+ppbc]
0x180004729  test    rcx, rcx
0x18000472c  jz      short loc_18000473E
0x18000472e  mov     rax, [rcx]
0x180004731  mov     rax, [rax+10h]
0x180004735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473a  mov     [rbp+ppbc], r12
0x18000473e  test    ebx, ebx
0x180004740  js      short loc_180004747
0x180004742  test    r14d, r14d
0x180004745  jz      short loc_180004759
0x180004747  mov     rax, [rdi]
0x18000474a  mov     rcx, rdi
0x18000474d  mov     [rdi+6Ch], ebx
0x180004750  mov     rax, [rax+78h]
0x180004754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004759  mov     eax, ebx
0x18000475b  add     rsp, 70h
0x18000475f  pop     r15
0x180004761  pop     r14
0x180004763  pop     r12
0x180004765  pop     rdi
0x180004766  pop     rsi
0x180004767  pop     rbx
0x180004768  pop     rbp
0x180004769  retn
```
