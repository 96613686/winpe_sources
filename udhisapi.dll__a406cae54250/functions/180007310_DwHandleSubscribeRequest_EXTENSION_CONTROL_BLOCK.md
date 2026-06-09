# DwHandleSubscribeRequest(_EXTENSION_CONTROL_BLOCK *)

- ea: `0x180007310`
- end: `0x18000772c`
- name: `?DwHandleSubscribeRequest@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@@Z`
- size: `1052`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800071bc`

## callees

- `0x18000249c`
- `0x1800024c4`
- `0x180002504`
- `0x1800025e8`
- `0x1800038ec`
- `0x180006d7c`
- `0x180007310`
- `0x180007ac8`
- `0x180007d5c`
- `0x1800080bc`
- `0x18000979c`
- `0x180009a74`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007541`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007552`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007604`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000761b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800076d8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800076e2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800076ec`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007700`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007541`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007552`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007604`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000761b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800076d8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800076e2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800076ec`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007700`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800076f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800076f6`

## pseudocode

```c
__int64 __fastcall DwHandleSubscribeRequest(struct _EXTENSION_CONTROL_BLOCK *a1)
{
  char *v1; // r15
  struct _EXTENSION_CONTROL_BLOCK *v2; // rbx
  unsigned int Header; // eax
  _QWORD *v4; // rcx
  unsigned int v5; // eax
  _QWORD *v6; // rcx
  unsigned int Timeout; // eax
  char *lpszQueryString; // rcx
  unsigned int v9; // edi
  int EventingManager; // esi
  unsigned __int16 *v11; // r12
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // r14
  const char *v14; // rax
  unsigned int v15; // r14d
  void **v16; // rbx
  LPCCH lpMultiByteStr; // [rsp+40h] [rbp-30h] BYREF
  LPCCH v19; // [rsp+48h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-20h] BYREF
  char *v21; // [rsp+58h] [rbp-18h] BYREF
  struct IUPnPEventingManager *v22; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+B8h] [rbp+48h] BYREF
  unsigned int v25; // [rsp+C0h] [rbp+50h] BYREF
  void *Block; // [rsp+C8h] [rbp+58h] BYREF

  a1->dwHttpStatusCode = 200;
  v25 = 0;
  pv = 0;
  v1 = 0;
  lpMultiByteStr = 0;
  v19 = 0;
  v2 = a1;
  v21 = 0;
  Block = 0;
  v24 = 0;
  v22 = 0;
  Header = DwQueryHeader(a1, "LOCAL_ADDR", (char **)&lpMultiByteStr);
  if ( Header )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids, Header);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
        WPP_SF_sd(
          v4[2],
          22,
          (unsigned int)WPP_604df09e42be3037ea2c3a056a88862f_Traceguids,
          (unsigned int)"Could not obtain local IP address!",
          5);
    }
  }
  v5 = DwQueryHeader(v2, "REMOTE_ADDR", (char **)&v19);
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids, v5);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
        WPP_SF_sd(
          v6[2],
          24,
          (unsigned int)WPP_604df09e42be3037ea2c3a056a88862f_Traceguids,
          (unsigned int)"Could not obtain remote IP address!",
          5);
    }
  }
  if ( DwQueryHeader(v2, "HTTP_CALLBACK", &v21) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids);
    goto LABEL_52;
  }
  if ( !(unsigned int)FParseCallbackUrl(v21, &v24, (unsigned __int16 ***)&Block) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids, v21);
LABEL_52:
    v2->dwHttpStatusCode = 412;
LABEL_53:
    v9 = 4;
    goto LABEL_54;
  }
  Timeout = DwGetTimeout(v2);
  lpszQueryString = v2->lpszQueryString;
  v25 = Timeout;
  v9 = 0;
  EventingManager = HrGetEventingManager(lpszQueryString, &v22);
  if ( EventingManager >= 0 )
  {
    if ( !lpMultiByteStr || !v19 )
      goto LABEL_35;
    v11 = WszFromSz(lpMultiByteStr);
    v12 = WszFromSz(v19);
    v13 = v12;
    if ( v11 )
    {
      if ( v12 )
        EventingManager = (*(__int64 (__fastcall **)(struct IUPnPEventingManager *, _QWORD, void *, unsigned __int16 *, unsigned __int16 *, unsigned int *, LPVOID *))(*(_QWORD *)v22 + 32LL))(
                            v22,
                            v24,
                            Block,
                            v11,
                            v12,
                            &v25,
                            &pv);
      free(v11);
    }
    if ( v13 )
      free(v13);
    if ( EventingManager < 0 )
    {
      if ( EventingManager == -2147024894 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids);
        v2->dwHttpStatusCode = 404;
        v9 = 4;
        EventingManager = 0;
      }
    }
    else
    {
LABEL_35:
      if ( pv )
      {
        v14 = SzFromWsz((LPCWCH)pv);
        v1 = (char *)v14;
        if ( v14 )
        {
          v9 = DwSendSubscribeResponse(v2, v25, v14);
          (*(void (__fastcall **)(struct IUPnPEventingManager *, LPVOID))(*(_QWORD *)v22 + 40LL))(v22, pv);
        }
        else
        {
          v2->dwHttpStatusCode = 503;
          v9 = 4;
        }
      }
    }
  }
  v15 = 0;
  if ( v24 )
  {
    v16 = (void **)Block;
    do
      free(v16[v15++]);
    while ( v15 < v24 );
    v2 = a1;
  }
  free(Block);
  if ( EventingManager < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)WPP_604df09e42be3037ea2c3a056a88862f_Traceguids,
        (unsigned int)"DwHandleSubscribeRequest",
        EventingManager);
    v2->dwHttpStatusCode = 500;
    goto LABEL_53;
  }
LABEL_54:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids, v9);
  free(v1);
  free((void *)lpMultiByteStr);
  free((void *)v19);
  CoTaskMemFree(pv);
  free(v21);
  if ( v22 )
    (*(void (__fastcall **)(struct IUPnPEventingManager *))(*(_QWORD *)v22 + 16LL))(v22);
  return v9;
}

```

## disassembly

```asm
0x180007310  mov     [rsp-38h+arg_0], rcx
0x180007315  push    rbp
0x180007316  push    rbx
0x180007317  push    rsi
0x180007318  push    rdi
0x180007319  push    r12
0x18000731b  push    r14
0x18000731d  push    r15
0x18000731f  mov     rbp, rsp
0x180007322  sub     rsp, 70h
0x180007326  xor     r12d, r12d
0x180007329  mov     dword ptr [rcx+10h], 0C8h
0x180007330  lea     r8, [rbp+lpMultiByteStr]; char **
0x180007334  mov     [rbp+arg_10], r12d
0x180007338  lea     rdx, aLocalAddr; "LOCAL_ADDR"
0x18000733f  mov     [rbp+pv], r12
0x180007343  mov     r15d, r12d
0x180007346  mov     [rbp+lpMultiByteStr], r12
0x18000734a  mov     [rbp+var_28], r12
0x18000734e  mov     rbx, rcx
0x180007351  mov     [rbp+var_18], r12
0x180007355  mov     [rbp+Block], r12
0x180007359  mov     [rbp+arg_8], r12d
0x18000735d  mov     [rbp+var_10], r12
0x180007361  call    ?DwQueryHeader@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@PEBDPEAPEAD@Z; DwQueryHeader(_EXTENSION_CONTROL_BLOCK *,char const *,char * *)
0x180007366  lea     rdi, WPP_GLOBAL_Control
0x18000736d  mov     r14d, 80004005h
0x180007373  mov     esi, 800h
0x180007378  test    eax, eax
0x18000737a  jz      short loc_1800073D8
0x18000737c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007383  cmp     rcx, rdi
0x180007386  jz      short loc_1800073D8
0x180007388  test    [rcx+1Ch], esi
0x18000738b  jz      short loc_1800073AC
0x18000738d  mov     rcx, [rcx+10h]
0x180007391  lea     edx, [r12+15h]
0x180007396  mov     r9d, eax
0x180007399  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x1800073a0  call    WPP_SF_d
0x1800073a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073ac  cmp     rcx, rdi
0x1800073af  jz      short loc_1800073D8
0x1800073b1  test    byte ptr [rcx+1Ch], 1
0x1800073b5  jz      short loc_1800073D8
0x1800073b7  mov     rcx, [rcx+10h]
0x1800073bb  lea     r9, aCouldNotObtain_0; "Could not obtain local IP address!"
0x1800073c2  mov     edx, 16h
0x1800073c7  mov     dword ptr [rsp+70h+var_50], r14d
0x1800073cc  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x1800073d3  call    WPP_SF_sd
0x1800073d8  lea     r8, [rbp+var_28]; char **
0x1800073dc  mov     rcx, rbx; struct _EXTENSION_CONTROL_BLOCK *
0x1800073df  lea     rdx, aRemoteAddr; "REMOTE_ADDR"
0x1800073e6  call    ?DwQueryHeader@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@PEBDPEAPEAD@Z; DwQueryHeader(_EXTENSION_CONTROL_BLOCK *,char const *,char * *)
0x1800073eb  test    eax, eax
0x1800073ed  jz      short loc_18000744B
0x1800073ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073f6  cmp     rcx, rdi
0x1800073f9  jz      short loc_18000744B
0x1800073fb  test    [rcx+1Ch], esi
0x1800073fe  jz      short loc_18000741F
0x180007400  mov     rcx, [rcx+10h]
0x180007404  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x18000740b  mov     edx, 17h
0x180007410  mov     r9d, eax
0x180007413  call    WPP_SF_d
0x180007418  mov     rcx, cs:WPP_GLOBAL_Control
0x18000741f  cmp     rcx, rdi
0x180007422  jz      short loc_18000744B
0x180007424  test    byte ptr [rcx+1Ch], 1
0x180007428  jz      short loc_18000744B
0x18000742a  mov     rcx, [rcx+10h]
0x18000742e  lea     r9, aCouldNotObtain; "Could not obtain remote IP address!"
0x180007435  mov     edx, 18h
0x18000743a  mov     dword ptr [rsp+70h+var_50], r14d
0x18000743f  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x180007446  call    WPP_SF_sd
0x18000744b  lea     r8, [rbp+var_18]; char **
0x18000744f  mov     rcx, rbx; struct _EXTENSION_CONTROL_BLOCK *
0x180007452  lea     rdx, aHttpCallback; "HTTP_CALLBACK"
0x180007459  call    ?DwQueryHeader@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@PEBDPEAPEAD@Z; DwQueryHeader(_EXTENSION_CONTROL_BLOCK *,char const *,char * *)
0x18000745e  test    eax, eax
0x180007460  jnz     loc_180007673
0x180007466  mov     rcx, [rbp+var_18]; char *
0x18000746a  lea     r8, [rbp+Block]; unsigned __int16 ***
0x18000746e  lea     rdx, [rbp+arg_8]; unsigned int *
0x180007472  call    ?FParseCallbackUrl@@YAHPEBDPEAKPEAPEAPEAG@Z; FParseCallbackUrl(char const *,ulong *,ushort * * *)
0x180007477  test    eax, eax
0x180007479  jnz     short loc_1800074B0
0x18000747b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007482  cmp     rcx, rdi
0x180007485  jz      loc_180007699
0x18000748b  test    [rcx+1Ch], esi
0x18000748e  jz      loc_180007699
0x180007494  mov     r9, [rbp+var_18]
0x180007498  lea     edx, [rax+19h]
0x18000749b  mov     rcx, [rcx+10h]
0x18000749f  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x1800074a6  call    WPP_SF_s
0x1800074ab  jmp     loc_180007699
0x1800074b0  mov     rcx, rbx; struct _EXTENSION_CONTROL_BLOCK *
0x1800074b3  call    ?DwGetTimeout@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@@Z; DwGetTimeout(_EXTENSION_CONTROL_BLOCK *)
0x1800074b8  mov     rcx, [rbx+70h]; char *
0x1800074bc  lea     rdx, [rbp+var_10]; struct IUPnPEventingManager **
0x1800074c0  mov     [rbp+arg_10], eax
0x1800074c3  mov     edi, r12d
0x1800074c6  call    ?HrGetEventingManager@@YAJPEADPEAPEAUIUPnPEventingManager@@@Z; HrGetEventingManager(char *,IUPnPEventingManager * *)
0x1800074cb  mov     esi, eax
0x1800074cd  test    eax, eax
0x1800074cf  js      loc_1800075F0
0x1800074d5  cmp     [rbp+lpMultiByteStr], r12
0x1800074d9  jz      loc_1800075AA
0x1800074df  cmp     [rbp+var_28], r12
0x1800074e3  jz      loc_1800075AA
0x1800074e9  mov     rcx, [rbp+lpMultiByteStr]; lpMultiByteStr
0x1800074ed  call    ?WszFromSz@@YAPEAGPEBD@Z; WszFromSz(char const *)
0x1800074f2  mov     rcx, [rbp+var_28]; lpMultiByteStr
0x1800074f6  mov     r12, rax
0x1800074f9  call    ?WszFromSz@@YAPEAGPEBD@Z; WszFromSz(char const *)
0x1800074fe  mov     r14, rax
0x180007501  test    r12, r12
0x180007504  jz      short loc_180007547
0x180007506  test    rax, rax
0x180007509  jz      short loc_18000753E
0x18000750b  mov     rcx, [rbp+var_10]
0x18000750f  lea     rdx, [rbp+pv]
0x180007513  mov     r8, [rbp+Block]
0x180007517  mov     r9, r12
0x18000751a  mov     [rsp+70h+var_40], rdx
0x18000751f  lea     rdx, [rbp+arg_10]
0x180007523  mov     [rsp+70h+var_48], rdx
0x180007528  mov     rax, [rcx]
0x18000752b  mov     edx, [rbp+arg_8]
0x18000752e  mov     [rsp+70h+var_50], r14
0x180007533  mov     rax, [rax+20h]
0x180007537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000753c  mov     esi, eax
0x18000753e  mov     rcx, r12; Block
0x180007541  call    cs:__imp_free
0x180007547  xor     r12d, r12d
0x18000754a  test    r14, r14
0x18000754d  jz      short loc_180007558
0x18000754f  mov     rcx, r14; Block
0x180007552  call    cs:__imp_free
0x180007558  test    esi, esi
0x18000755a  jns     short loc_1800075AA
0x18000755c  cmp     esi, 80070002h
0x180007562  jnz     loc_1800075F0
0x180007568  mov     rcx, cs:WPP_GLOBAL_Control
0x18000756f  lea     rax, WPP_GLOBAL_Control
0x180007576  cmp     rcx, rax
0x180007579  jz      short loc_180007599
0x18000757b  test    dword ptr [rcx+1Ch], 800h
0x180007582  jz      short loc_180007599
0x180007584  mov     rcx, [rcx+10h]
0x180007588  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x18000758f  mov     edx, 1Ah
0x180007594  call    WPP_SF_
0x180007599  mov     dword ptr [rbx+10h], 194h
0x1800075a0  mov     edi, 4
0x1800075a5  mov     esi, r12d
0x1800075a8  jmp     short loc_1800075F0
0x1800075aa  mov     rcx, [rbp+pv]; lpWideCharStr
0x1800075ae  test    rcx, rcx
0x1800075b1  jz      short loc_1800075F0
0x1800075b3  call    ?SzFromWsz@@YAPEADPEBG@Z; SzFromWsz(ushort const *)
0x1800075b8  mov     r15, rax
0x1800075bb  test    rax, rax
0x1800075be  jnz     short loc_1800075CC
0x1800075c0  mov     dword ptr [rbx+10h], 1F7h
0x1800075c7  lea     edi, [rax+4]
0x1800075ca  jmp     short loc_1800075F0
0x1800075cc  mov     edx, [rbp+arg_10]; unsigned int
0x1800075cf  mov     r8, rax; char *
0x1800075d2  mov     rcx, rbx; struct _EXTENSION_CONTROL_BLOCK *
0x1800075d5  call    ?DwSendSubscribeResponse@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@KPEBD@Z; DwSendSubscribeResponse(_EXTENSION_CONTROL_BLOCK *,ulong,char const *)
0x1800075da  mov     rcx, [rbp+var_10]
0x1800075de  mov     edi, eax
0x1800075e0  mov     rdx, [rcx]
0x1800075e3  mov     rax, [rdx+28h]
0x1800075e7  mov     rdx, [rbp+pv]
0x1800075eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075f0  mov     r14d, r12d
0x1800075f3  cmp     [rbp+arg_8], r12d
0x1800075f7  jbe     short loc_180007617
0x1800075f9  mov     rbx, [rbp+Block]
0x1800075fd  mov     ecx, r14d
0x180007600  mov     rcx, [rbx+rcx*8]; Block
0x180007604  call    cs:__imp_free
0x18000760a  inc     r14d
0x18000760d  cmp     r14d, [rbp+arg_8]
0x180007611  jb      short loc_1800075FD
0x180007613  mov     rbx, [rbp+arg_0]
0x180007617  mov     rcx, [rbp+Block]; Block
0x18000761b  call    cs:__imp_free
0x180007621  test    esi, esi
0x180007623  jns     short loc_18000766C
0x180007625  mov     rcx, cs:WPP_GLOBAL_Control
0x18000762c  lea     rax, WPP_GLOBAL_Control
0x180007633  cmp     rcx, rax
0x180007636  jz      short loc_18000765E
0x180007638  test    byte ptr [rcx+1Ch], 1
0x18000763c  jz      short loc_18000765E
0x18000763e  mov     rcx, [rcx+10h]
0x180007642  lea     r9, aDwhandlesubscr; "DwHandleSubscribeRequest"
0x180007649  mov     edx, 1Ch
0x18000764e  mov     dword ptr [rsp+70h+var_50], esi
0x180007652  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x180007659  call    WPP_SF_sd
0x18000765e  mov     dword ptr [rbx+10h], 1F4h
0x180007665  mov     esi, 800h
0x18000766a  jmp     short loc_1800076A0
0x18000766c  mov     esi, 800h
0x180007671  jmp     short loc_1800076A5
0x180007673  mov     rcx, cs:WPP_GLOBAL_Control
0x18000767a  cmp     rcx, rdi
0x18000767d  jz      short loc_180007699
0x18000767f  test    [rcx+1Ch], esi
0x180007682  jz      short loc_180007699
0x180007684  mov     rcx, [rcx+10h]
0x180007688  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x18000768f  mov     edx, 1Bh
0x180007694  call    WPP_SF_
0x180007699  mov     dword ptr [rbx+10h], 19Ch
0x1800076a0  mov     edi, 4
0x1800076a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076ac  lea     rax, WPP_GLOBAL_Control
0x1800076b3  cmp     rcx, rax
0x1800076b6  jz      short loc_1800076D5
0x1800076b8  test    [rcx+1Ch], esi
0x1800076bb  jz      short loc_1800076D5
0x1800076bd  mov     rcx, [rcx+10h]
0x1800076c1  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x1800076c8  mov     edx, 1Dh
0x1800076cd  mov     r9d, edi
0x1800076d0  call    WPP_SF_d
0x1800076d5  mov     rcx, r15; Block
0x1800076d8  call    cs:__imp_free
0x1800076de  mov     rcx, [rbp+lpMultiByteStr]; Block
0x1800076e2  call    cs:__imp_free
0x1800076e8  mov     rcx, [rbp+var_28]; Block
0x1800076ec  call    cs:__imp_free
0x1800076f2  mov     rcx, [rbp+pv]; pv
0x1800076f6  call    cs:__imp_CoTaskMemFree
0x1800076fc  mov     rcx, [rbp+var_18]; Block
0x180007700  call    cs:__imp_free
0x180007706  mov     rcx, [rbp+var_10]
0x18000770a  test    rcx, rcx
0x18000770d  jz      short loc_18000771B
0x18000770f  mov     rax, [rcx]
0x180007712  mov     rax, [rax+10h]
0x180007716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000771b  mov     eax, edi
0x18000771d  add     rsp, 70h
0x180007721  pop     r15
0x180007723  pop     r14
0x180007725  pop     r12
0x180007727  pop     rdi
0x180007728  pop     rsi
0x180007729  pop     rbx
0x18000772a  pop     rbp
0x18000772b  retn
```
