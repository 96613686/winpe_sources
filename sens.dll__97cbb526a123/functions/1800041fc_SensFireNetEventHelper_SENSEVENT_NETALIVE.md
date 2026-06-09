# SensFireNetEventHelper(_SENSEVENT_NETALIVE *)

- ea: `0x1800041fc`
- end: `0x180004785`
- name: `?SensFireNetEventHelper@@YAJPEAU_SENSEVENT_NETALIVE@@@Z`
- size: `1417`
- prototype: `__int64 __fastcall(struct _SENSEVENT_NETALIVE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003690`

## callees

- `0x1800041fc`
- `0x180005e00`
- `0x180005f80`
- `0x180008300`
- `0x1800093b0`
- `0x18000a7a0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000429d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000429d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800043a8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800043d1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800044f5`
- `OLEAUT32!__imp_SysAllocString` at `0x180004624`
- `OLEAUT32!__imp_SysAllocString` at `0x1800043a8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800043d1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800044f5`
- `OLEAUT32!__imp_SysAllocString` at `0x180004624`
- `OLEAUT32!__imp_SysFreeString` at `0x1800044e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000474b`
- `OLEAUT32!__imp_SysFreeString` at `0x180004754`
- `OLEAUT32!__imp_SysFreeString` at `0x1800044e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000474b`
- `OLEAUT32!__imp_SysFreeString` at `0x180004754`

## pseudocode

```c
__int64 __fastcall SensFireNetEventHelper(struct _SENSEVENT_NETALIVE *a1)
{
  OLECHAR *v2; // r12
  OLECHAR *v3; // r14
  HRESULT v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rax
  __int64 v10; // r8
  unsigned __int16 *v11; // rax
  struct IDispatch *v13; // [rsp+30h] [rbp-69h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-61h] BYREF
  void **v15; // [rsp+40h] [rbp-59h] BYREF
  void **v16; // [rsp+48h] [rbp-51h] BYREF
  int v17; // [rsp+50h] [rbp-49h]
  __int64 v18; // [rsp+58h] [rbp-41h]
  __int128 v19; // [rsp+60h] [rbp-39h]
  __int128 v20; // [rsp+70h] [rbp-29h]
  __int64 v21; // [rsp+80h] [rbp-19h]
  __int128 v22; // [rsp+90h] [rbp-9h] BYREF

  v15 = &CImpISensNetworkFilter::`vftable'{for `ISensNetwork'};
  v16 = &CImpISensNetworkFilter::`vftable'{for `IPublisherFilter'};
  v17 = 1;
  v22 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  _InterlockedAdd(&g_cFilterObj, 1u);
  ppv = 0;
  v13 = 0;
  v2 = 0;
  v3 = 0;
  v4 = CoCreateInstance(&SENSGUID_EVENTCLASS_NETWORK, 0, 0x15u, &IID_ISensNetwork, &ppv);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids);
    }
    v4 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IDispatch **))ppv)(ppv, &IID_IEventControl, &v13);
    v5 = v4;
    if ( v4 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids);
      }
      ((void (__fastcall *)(struct IDispatch *, _QWORD))v13->lpVtbl[1].Release)(v13, 0);
      v2 = SysAllocString(*((const OLECHAR **)a1 + 3));
      if ( v2 )
      {
        if ( *((_DWORD *)a1 + 1) )
        {
          v8 = SysAllocString(L"ConnectionMadeNoQOCInfo");
          v3 = v8;
          if ( v8 )
          {
            v4 = CImpISensNetworkFilter::Initialize((CImpISensNetworkFilter *)&v16, v8, v13);
            v5 = v4;
            if ( v4 < 0 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v7 = 28;
                goto LABEL_82;
              }
              goto LABEL_83;
            }
            v4 = ((__int64 (__fastcall *)(struct IDispatch *, OLECHAR *, void ***))v13->lpVtbl[1].QueryInterface)(
                   v13,
                   v3,
                   &v16);
            v5 = v4;
            if ( v4 < 0 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v7 = 29;
                goto LABEL_82;
              }
              goto LABEL_83;
            }
            v4 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD))(*(_QWORD *)ppv + 64LL))(
                   ppv,
                   v2,
                   *((unsigned int *)a1 + 3));
            v5 = v4;
            if ( v4 < 0 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v7 = 30;
                goto LABEL_82;
              }
              goto LABEL_83;
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                31,
                WPP_7617987f8fa93304f2df28234d8870cd_Traceguids,
                (unsigned int)v4);
            }
            SysFreeString(v3);
            v9 = SysAllocString(L"ConnectionMade");
            v3 = v9;
            if ( v9 )
            {
              v4 = CImpISensNetworkFilter::Initialize((CImpISensNetworkFilter *)&v16, v9, v13);
              v5 = v4;
              if ( v4 >= 0 )
              {
                v4 = ((__int64 (__fastcall *)(struct IDispatch *, OLECHAR *, void ***))v13->lpVtbl[1].QueryInterface)(
                       v13,
                       v3,
                       &v16);
                v5 = v4;
                if ( v4 >= 0 )
                {
                  v10 = *((unsigned int *)a1 + 3);
                  v22 = *(_OWORD *)((char *)a1 + 8);
                  v4 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int64, __int128 *))(*(_QWORD *)ppv + 56LL))(
                         ppv,
                         v2,
                         v10,
                         &v22);
                  v5 = v4;
                  if ( v4 >= 0 )
                  {
                    v6 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                    {
                      v7 = 35;
                      goto LABEL_82;
                    }
                  }
                  else
                  {
                    v6 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v7 = 34;
                      goto LABEL_82;
                    }
                  }
                }
                else
                {
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v7 = 33;
                    goto LABEL_82;
                  }
                }
              }
              else
              {
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v7 = 32;
                  goto LABEL_82;
                }
              }
              goto LABEL_83;
            }
          }
        }
        else
        {
          v11 = SysAllocString(L"ConnectionLost");
          v3 = v11;
          if ( v11 )
          {
            v4 = CImpISensNetworkFilter::Initialize((CImpISensNetworkFilter *)&v16, v11, v13);
            v5 = v4;
            if ( v4 >= 0 )
            {
              v4 = ((__int64 (__fastcall *)(struct IDispatch *, OLECHAR *, void ***))v13->lpVtbl[1].QueryInterface)(
                     v13,
                     v3,
                     &v16);
              v5 = v4;
              if ( v4 >= 0 )
              {
                v4 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD))(*(_QWORD *)ppv + 72LL))(
                       ppv,
                       v2,
                       *((unsigned int *)a1 + 3));
                v5 = v4;
                if ( v4 >= 0 )
                {
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                  {
                    v7 = 39;
                    goto LABEL_82;
                  }
                }
                else
                {
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v7 = 38;
                    goto LABEL_82;
                  }
                }
              }
              else
              {
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v7 = 37;
                  goto LABEL_82;
                }
              }
            }
            else
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v7 = 36;
                goto LABEL_82;
              }
            }
            goto LABEL_83;
          }
        }
      }
      v5 = -2147024882;
      goto LABEL_83;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 26;
      goto LABEL_82;
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 24;
LABEL_82:
      WPP_SF_d(v6[2], v7, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids, (unsigned int)v4);
    }
  }
LABEL_83:
  if ( v13 )
    ((void (__fastcall *)(struct IDispatch *))v13->lpVtbl->Release)(v13);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  SysFreeString(v3);
  SysFreeString(v2);
  CImpISensNetworkFilter::~CImpISensNetworkFilter((CImpISensNetworkFilter *)&v15);
  return v5;
}

```

## disassembly

```asm
0x1800041fc  push    rbp
0x1800041fe  push    rbx
0x1800041ff  push    rsi
0x180004200  push    rdi
0x180004201  push    r12
0x180004203  push    r13
0x180004205  push    r14
0x180004207  push    r15
0x180004209  lea     rbp, [rsp-1Fh]
0x18000420e  sub     rsp, 0B8h
0x180004215  mov     rax, cs:__security_cookie
0x18000421c  xor     rax, rsp
0x18000421f  mov     [rbp+57h+var_50], rax
0x180004223  xor     edi, edi
0x180004225  lea     rax, ??_7CImpISensNetworkFilter@@6BISensNetwork@@@; const CImpISensNetworkFilter::`vftable'{for `ISensNetwork'}
0x18000422c  xorps   xmm0, xmm0
0x18000422f  mov     [rbp+57h+var_B0], rax
0x180004233  lea     rax, ??_7CImpISensNetworkFilter@@6BIPublisherFilter@@@; const CImpISensNetworkFilter::`vftable'{for `IPublisherFilter'}
0x18000423a  mov     [rbp+57h+var_B8], rdi
0x18000423e  xorps   xmm1, xmm1
0x180004241  mov     [rbp+57h+var_C0], rdi
0x180004245  lea     r13d, [rdi+1]
0x180004249  mov     [rbp+57h+var_A8], rax
0x18000424d  mov     [rbp+57h+var_A0], r13d
0x180004251  mov     r15, rcx
0x180004254  movups  [rbp+57h+var_60], xmm0
0x180004258  mov     [rbp+57h+var_98], rdi
0x18000425c  movdqa  [rbp+57h+var_90], xmm0
0x180004261  movdqa  [rbp+57h+var_80], xmm1
0x180004266  mov     [rbp+57h+var_70], rdi
0x18000426a  lock add cs:?g_cFilterObj@@3JA, r13d; long g_cFilterObj
0x180004272  lea     rax, [rbp+57h+var_B8]
0x180004276  mov     [rbp+57h+var_B8], rdi
0x18000427a  lea     r9, IID_ISensNetwork; riid
0x180004281  mov     [rsp+0F0h+ppv], rax; ppv
0x180004286  xor     edx, edx; pUnkOuter
0x180004288  mov     [rbp+57h+var_C0], rdi
0x18000428c  lea     r8d, [rdi+15h]; dwClsContext
0x180004290  mov     r12d, edi
0x180004293  lea     rcx, SENSGUID_EVENTCLASS_NETWORK; rclsid
0x18000429a  mov     r14d, edi
0x18000429d  call    cs:__imp_CoCreateInstance
0x1800042a3  mov     ebx, eax
0x1800042a5  test    eax, eax
0x1800042a7  jns     short loc_1800042E4
0x1800042a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042b0  lea     rdi, WPP_GLOBAL_Control
0x1800042b7  cmp     rcx, rdi
0x1800042ba  jz      loc_18000471E
0x1800042c0  test    [rcx+1Ch], r13b
0x1800042c4  jz      loc_18000471E
0x1800042ca  cmp     byte ptr [rcx+19h], 2
0x1800042ce  jb      loc_18000471E
0x1800042d4  lea     edx, [r14+18h]
0x1800042d8  lea     r8, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x1800042df  jmp     loc_180004712
0x1800042e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042eb  lea     rdi, WPP_GLOBAL_Control
0x1800042f2  lea     rsi, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x1800042f9  cmp     rcx, rdi
0x1800042fc  jz      short loc_18000431B
0x1800042fe  test    [rcx+1Ch], r13b
0x180004302  jz      short loc_18000431B
0x180004304  cmp     byte ptr [rcx+19h], 5
0x180004308  jb      short loc_18000431B
0x18000430a  mov     rcx, [rcx+10h]
0x18000430e  mov     edx, 19h
0x180004313  mov     r8, rsi
0x180004316  call    WPP_SF_
0x18000431b  mov     rcx, [rbp+57h+var_B8]
0x18000431f  lea     r8, [rbp+57h+var_C0]
0x180004323  lea     rdx, IID_IEventControl
0x18000432a  mov     rax, [rcx]
0x18000432d  mov     rax, [rax]
0x180004330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004335  mov     ebx, eax
0x180004337  test    eax, eax
0x180004339  jns     short loc_180004369
0x18000433b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004342  cmp     rcx, rdi
0x180004345  jz      loc_18000471E
0x18000434b  test    [rcx+1Ch], r13b
0x18000434f  jz      loc_18000471E
0x180004355  cmp     byte ptr [rcx+19h], 2
0x180004359  jb      loc_18000471E
0x18000435f  mov     edx, 1Ah
0x180004364  jmp     loc_18000470F
0x180004369  mov     rcx, cs:WPP_GLOBAL_Control
0x180004370  cmp     rcx, rdi
0x180004373  jz      short loc_180004392
0x180004375  test    [rcx+1Ch], r13b
0x180004379  jz      short loc_180004392
0x18000437b  cmp     byte ptr [rcx+19h], 5
0x18000437f  jb      short loc_180004392
0x180004381  mov     rcx, [rcx+10h]
0x180004385  mov     edx, 1Bh
0x18000438a  mov     r8, rsi
0x18000438d  call    WPP_SF_
0x180004392  mov     rcx, [rbp+57h+var_C0]
0x180004396  xor     edx, edx
0x180004398  mov     rax, [rcx]
0x18000439b  mov     rax, [rax+48h]
0x18000439f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a4  mov     rcx, [r15+18h]; psz
0x1800043a8  call    cs:__imp_SysAllocString
0x1800043ae  mov     r12, rax
0x1800043b1  test    rax, rax
0x1800043b4  jnz     short loc_1800043C0
0x1800043b6  mov     ebx, 8007000Eh
0x1800043bb  jmp     loc_18000471E
0x1800043c0  cmp     [r15+4], r14d
0x1800043c4  jz      loc_18000461D
0x1800043ca  lea     rcx, psz; "ConnectionMadeNoQOCInfo"
0x1800043d1  call    cs:__imp_SysAllocString
0x1800043d7  mov     r14, rax
0x1800043da  test    rax, rax
0x1800043dd  jz      short loc_1800043B6
0x1800043df  mov     r8, [rbp+57h+var_C0]; struct IDispatch *
0x1800043e3  lea     rcx, [rbp+57h+var_A8]; this
0x1800043e7  mov     rdx, rax; unsigned __int16 *
0x1800043ea  call    ?Initialize@CImpISensNetworkFilter@@UEAAJPEAGPEAUIDispatch@@@Z; CImpISensNetworkFilter::Initialize(ushort *,IDispatch *)
0x1800043ef  mov     ebx, eax
0x1800043f1  test    eax, eax
0x1800043f3  jns     short loc_180004423
0x1800043f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043fc  cmp     rcx, rdi
0x1800043ff  jz      loc_18000471E
0x180004405  test    [rcx+1Ch], r13b
0x180004409  jz      loc_18000471E
0x18000440f  cmp     byte ptr [rcx+19h], 2
0x180004413  jb      loc_18000471E
0x180004419  mov     edx, 1Ch
0x18000441e  jmp     loc_18000470F
0x180004423  mov     rcx, [rbp+57h+var_C0]
0x180004427  lea     r8, [rbp+57h+var_A8]
0x18000442b  mov     rdx, r14
0x18000442e  mov     rax, [rcx]
0x180004431  mov     rax, [rax+38h]
0x180004435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000443a  mov     ebx, eax
0x18000443c  test    eax, eax
0x18000443e  jns     short loc_18000446E
0x180004440  mov     rcx, cs:WPP_GLOBAL_Control
0x180004447  cmp     rcx, rdi
0x18000444a  jz      loc_18000471E
0x180004450  test    [rcx+1Ch], r13b
0x180004454  jz      loc_18000471E
0x18000445a  cmp     byte ptr [rcx+19h], 2
0x18000445e  jb      loc_18000471E
0x180004464  mov     edx, 1Dh
0x180004469  jmp     loc_18000470F
0x18000446e  mov     rcx, [rbp+57h+var_B8]
0x180004472  mov     rdx, r12
0x180004475  mov     r8d, [r15+0Ch]
0x180004479  mov     rax, [rcx]
0x18000447c  mov     rax, [rax+40h]
0x180004480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004485  mov     ebx, eax
0x180004487  test    eax, eax
0x180004489  jns     short loc_1800044B9
0x18000448b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004492  cmp     rcx, rdi
0x180004495  jz      loc_18000471E
0x18000449b  test    [rcx+1Ch], r13b
0x18000449f  jz      loc_18000471E
0x1800044a5  cmp     byte ptr [rcx+19h], 2
0x1800044a9  jb      loc_18000471E
0x1800044af  mov     edx, 1Eh
0x1800044b4  jmp     loc_18000470F
0x1800044b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044c0  cmp     rcx, rdi
0x1800044c3  jz      short loc_1800044E5
0x1800044c5  test    [rcx+1Ch], r13b
0x1800044c9  jz      short loc_1800044E5
0x1800044cb  cmp     byte ptr [rcx+19h], 5
0x1800044cf  jb      short loc_1800044E5
0x1800044d1  mov     rcx, [rcx+10h]
0x1800044d5  mov     edx, 1Fh
0x1800044da  mov     r9d, eax
0x1800044dd  mov     r8, rsi
0x1800044e0  call    WPP_SF_d
0x1800044e5  mov     rcx, r14; bstrString
0x1800044e8  call    cs:__imp_SysFreeString
0x1800044ee  lea     rcx, String2; "ConnectionMade"
0x1800044f5  call    cs:__imp_SysAllocString
0x1800044fb  mov     r14, rax
0x1800044fe  test    rax, rax
0x180004501  jz      loc_1800043B6
0x180004507  mov     r8, [rbp+57h+var_C0]; struct IDispatch *
0x18000450b  lea     rcx, [rbp+57h+var_A8]; this
0x18000450f  mov     rdx, rax; unsigned __int16 *
0x180004512  call    ?Initialize@CImpISensNetworkFilter@@UEAAJPEAGPEAUIDispatch@@@Z; CImpISensNetworkFilter::Initialize(ushort *,IDispatch *)
0x180004517  mov     ebx, eax
0x180004519  test    eax, eax
0x18000451b  jns     short loc_18000454B
0x18000451d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004524  cmp     rcx, rdi
0x180004527  jz      loc_18000471E
0x18000452d  test    [rcx+1Ch], r13b
0x180004531  jz      loc_18000471E
0x180004537  cmp     byte ptr [rcx+19h], 2
0x18000453b  jb      loc_18000471E
0x180004541  mov     edx, 20h ; ' '
0x180004546  jmp     loc_18000470F
0x18000454b  mov     rcx, [rbp+57h+var_C0]
0x18000454f  lea     r8, [rbp+57h+var_A8]
0x180004553  mov     rdx, r14
0x180004556  mov     rax, [rcx]
0x180004559  mov     rax, [rax+38h]
0x18000455d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004562  mov     ebx, eax
0x180004564  test    eax, eax
0x180004566  jns     short loc_180004596
0x180004568  mov     rcx, cs:WPP_GLOBAL_Control
0x18000456f  cmp     rcx, rdi
0x180004572  jz      loc_18000471E
0x180004578  test    [rcx+1Ch], r13b
0x18000457c  jz      loc_18000471E
0x180004582  cmp     byte ptr [rcx+19h], 2
0x180004586  jb      loc_18000471E
0x18000458c  mov     edx, 21h ; '!'
0x180004591  jmp     loc_18000470F
0x180004596  movups  xmm0, xmmword ptr [r15+8]
0x18000459b  mov     rcx, [rbp+57h+var_B8]
0x18000459f  lea     r9, [rbp+57h+var_60]
0x1800045a3  mov     r8d, [r15+0Ch]
0x1800045a7  mov     rdx, r12
0x1800045aa  movdqu  [rbp+57h+var_60], xmm0
0x1800045af  mov     rax, [rcx]
0x1800045b2  mov     rax, [rax+38h]
0x1800045b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045bb  mov     ebx, eax
0x1800045bd  test    eax, eax
0x1800045bf  jns     short loc_1800045EF
0x1800045c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045c8  cmp     rcx, rdi
0x1800045cb  jz      loc_18000471E
0x1800045d1  test    [rcx+1Ch], r13b
0x1800045d5  jz      loc_18000471E
0x1800045db  cmp     byte ptr [rcx+19h], 2
0x1800045df  jb      loc_18000471E
0x1800045e5  mov     edx, 22h ; '"'
0x1800045ea  jmp     loc_18000470F
0x1800045ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045f6  cmp     rcx, rdi
0x1800045f9  jz      loc_18000471E
0x1800045ff  test    [rcx+1Ch], r13b
0x180004603  jz      loc_18000471E
0x180004609  cmp     byte ptr [rcx+19h], 5
0x18000460d  jb      loc_18000471E
0x180004613  mov     edx, 23h ; '#'
0x180004618  jmp     loc_18000470F
0x18000461d  lea     rcx, aConnectionlost; "ConnectionLost"
0x180004624  call    cs:__imp_SysAllocString
0x18000462a  mov     r14, rax
0x18000462d  test    rax, rax
0x180004630  jz      loc_1800043B6
0x180004636  mov     r8, [rbp+57h+var_C0]; struct IDispatch *
0x18000463a  lea     rcx, [rbp+57h+var_A8]; this
0x18000463e  mov     rdx, rax; unsigned __int16 *
0x180004641  call    ?Initialize@CImpISensNetworkFilter@@UEAAJPEAGPEAUIDispatch@@@Z; CImpISensNetworkFilter::Initialize(ushort *,IDispatch *)
0x180004646  mov     ebx, eax
0x180004648  test    eax, eax
0x18000464a  jns     short loc_18000467A
0x18000464c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004653  cmp     rcx, rdi
0x180004656  jz      loc_18000471E
0x18000465c  test    [rcx+1Ch], r13b
0x180004660  jz      loc_18000471E
0x180004666  cmp     byte ptr [rcx+19h], 2
0x18000466a  jb      loc_18000471E
0x180004670  mov     edx, 24h ; '$'
0x180004675  jmp     loc_18000470F
0x18000467a  mov     rcx, [rbp+57h+var_C0]
0x18000467e  lea     r8, [rbp+57h+var_A8]
0x180004682  mov     rdx, r14
0x180004685  mov     rax, [rcx]
0x180004688  mov     rax, [rax+38h]
0x18000468c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004691  mov     ebx, eax
0x180004693  test    eax, eax
0x180004695  jns     short loc_1800046B6
0x180004697  mov     rcx, cs:WPP_GLOBAL_Control
0x18000469e  cmp     rcx, rdi
0x1800046a1  jz      short loc_18000471E
0x1800046a3  test    [rcx+1Ch], r13b
0x1800046a7  jz      short loc_18000471E
0x1800046a9  cmp     byte ptr [rcx+19h], 2
0x1800046ad  jb      short loc_18000471E
0x1800046af  mov     edx, 25h ; '%'
0x1800046b4  jmp     short loc_18000470F
0x1800046b6  mov     rcx, [rbp+57h+var_B8]
0x1800046ba  mov     rdx, r12
0x1800046bd  mov     r8d, [r15+0Ch]
0x1800046c1  mov     rax, [rcx]
0x1800046c4  mov     rax, [rax+48h]
0x1800046c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046cd  mov     ebx, eax
0x1800046cf  test    eax, eax
0x1800046d1  jns     short loc_1800046F2
  ... truncated ...
```
