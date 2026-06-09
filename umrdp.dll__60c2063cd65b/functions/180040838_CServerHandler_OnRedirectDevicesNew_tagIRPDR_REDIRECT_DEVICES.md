# CServerHandler::OnRedirectDevicesNew(tagIRPDR_REDIRECT_DEVICES *)

- ea: `0x180040838`
- end: `0x180040f32`
- name: `?OnRedirectDevicesNew@CServerHandler@@AEAAJPEAUtagIRPDR_REDIRECT_DEVICES@@@Z`
- size: `1786`
- prototype: `__int64 __fastcall(CServerHandler *this, struct tagIRPDR_REDIRECT_DEVICES *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180040460`

## callees

- `0x180007da0`
- `0x18000abc0`
- `0x18000b3d0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18002c600`
- `0x180033878`
- `0x180040838`
- `0x180041990`
- `0x180047ea6`
- `0x180047ef0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040a61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040aa4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040aa4`

## string_xrefs

- `0x180040ec0`: `CRemoteDevice::CreateInstance FAILED`
- `0x180040c63`: `spRemoteDevice->SetCompatibilityId FAILED`

## pseudocode

```c
__int64 __fastcall CServerHandler::OnRedirectDevicesNew(CServerHandler *this, struct tagIRPDR_REDIRECT_DEVICES *a2)
{
  struct IRemoteDevice *v3; // rbx
  struct tagIRPDR_REDIRECT_DEVICES *v4; // r15
  int v5; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  unsigned int *v9; // rsi
  unsigned int i; // r13d
  char *v11; // r15
  char *v12; // r12
  char *v13; // r12
  char *v14; // r12
  unsigned int *v15; // rdi
  char *v16; // rax
  char *v17; // r13
  char *v18; // rdi
  char *v19; // r13
  char *v20; // rdx
  int v21; // ecx
  char *v22; // rdi
  unsigned int v23; // eax
  unsigned int v24; // eax
  char *v26; // [rsp+30h] [rbp-40h] BYREF
  struct IRemoteDevice *v27; // [rsp+38h] [rbp-38h] BYREF
  char *v28; // [rsp+40h] [rbp-30h] BYREF
  struct tagIRPDR_REDIRECT_DEVICES *v29; // [rsp+48h] [rbp-28h]
  __m128i si128; // [rsp+50h] [rbp-20h] BYREF

  v29 = a2;
  v3 = 0;
  v27 = 0;
  v4 = a2;
  TCntPtr<ITSAsyncCallback>::SafeAddRef(&v27);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v26 = (char *)this + 72;
  CTSCriticalSection::Lock((CServerHandler *)((char *)this + 72));
  if ( *((_DWORD *)this + 34) != 1 || *((_DWORD *)this + 32) != 3 )
  {
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v26);
    TCntPtr<IDispatch>::SafeRelease(&v27);
    return 2147500037LL;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v26);
  v5 = CCommonPNPPDUHandler::VerifyRedirectDevicesPDU((CServerHandler *)((char *)this + 64), v4);
  if ( v5 < 0 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
    {
      goto LABEL_86;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 30;
    v8 = "VerifyRedirectDevicesPDU failed";
    goto LABEL_85;
  }
  v9 = (unsigned int *)((char *)v4 + 12);
  for ( i = 0; ; ++i )
  {
    LODWORD(v26) = i;
    if ( i >= *((_DWORD *)v4 + 2) )
      goto LABEL_86;
    if ( v3 )
    {
      TCntPtr<IDispatch>::SafeRelease(&v27);
      v27 = 0;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v27);
    }
    v5 = CRemoteDevice::CreateInstance(&v27);
    if ( v5 < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_86;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 31;
      v8 = "CRemoteDevice::CreateInstance FAILED";
LABEL_85:
      WPP_SF_DsD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        v7,
        (unsigned int)WPP_f70cd3a88afa3710197e4c5386561e98_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v8,
        v5);
      goto LABEL_86;
    }
    v3 = v27;
    v5 = (*(__int64 (__fastcall **)(struct IRemoteDevice *, _QWORD))(*(_QWORD *)v27 + 168LL))(v27, *v9);
    if ( v5 < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_86;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 32;
      v8 = "spRemoteDevice->SetRemoteId FAILED";
      goto LABEL_85;
    }
    if ( !v9[1] )
      continue;
    v11 = (char *)(v9 + 2);
    v5 = (*(__int64 (__fastcall **)(struct IRemoteDevice *, unsigned int *, _QWORD))(*(_QWORD *)v3 + 88LL))(
           v3,
           v9 + 3,
           v9[2] >> 4);
    if ( v5 < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_86;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 33;
      v8 = "spRemoteDevice->SetInterfaces FAILED";
      goto LABEL_85;
    }
    v12 = (char *)v9 + *(unsigned int *)v11 + 12;
    if ( v12 - v11 != v9[1] )
      break;
LABEL_35:
    v5 = (*(__int64 (__fastcall **)(struct IRemoteDevice *, __m128i *))(*(_QWORD *)v3 + 152LL))(v3, &si128);
    if ( v5 < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_86;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 38;
      v8 = "RemoteDevice->SetDeviceCaps";
      goto LABEL_85;
    }
    v26 = 0;
    v28 = (char *)this + 88;
    CTSCriticalSection::Lock((CServerHandler *)((char *)this + 88));
    v22 = 0;
    if ( *((_QWORD *)this + 13) )
    {
      TCntPtr<IDispatch>::SafeRelease(&v26);
      v22 = (char *)*((_QWORD *)this + 13);
      v26 = v22;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&v26);
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v28);
    if ( !v22 )
    {
      v5 = -2147467259;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v24 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          40,
          (unsigned int)WPP_f70cd3a88afa3710197e4c5386561e98_Traceguids,
          v24,
          (__int64)"spCallback was NULL",
          5);
      }
      goto LABEL_64;
    }
    v5 = (*(__int64 (__fastcall **)(char *, struct IRemoteDevice *, _QWORD))(*(_QWORD *)v22 + 24LL))(
           v22,
           v3,
           *((unsigned int *)this + 36));
    if ( v5 < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v23 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          39,
          (unsigned int)WPP_f70cd3a88afa3710197e4c5386561e98_Traceguids,
          v23,
          (__int64)"spCallback->OnNewDevice FAILED",
          v5);
      }
LABEL_64:
      TCntPtr<IDispatch>::SafeRelease(&v26);
      goto LABEL_86;
    }
    v9 = (unsigned int *)((char *)v9 + v9[1] + 8);
    TCntPtr<IDispatch>::SafeRelease(&v26);
    v4 = v29;
  }
  v5 = (*(__int64 (__fastcall **)(struct IRemoteDevice *, _DWORD *, _QWORD))(*(_QWORD *)v3 + 104LL))(
         v3,
         (_DWORD *)v12 + 1,
         *(_DWORD *)v12 >> 1);
  if ( v5 >= 0 )
  {
    v13 = &v12[*(unsigned int *)v12 + 4];
    if ( v13 - v11 != v9[1] )
    {
      if ( *(_DWORD *)v13 )
      {
        v5 = (*(__int64 (__fastcall **)(struct IRemoteDevice *, _DWORD *, _QWORD))(*(_QWORD *)v3 + 120LL))(
               v3,
               (_DWORD *)v13 + 1,
               *(_DWORD *)v13 >> 1);
        if ( v5 < 0 )
        {
          if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
            && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v7 = 35;
            v8 = "spRemoteDevice->SetCompatibilityId FAILED";
            goto LABEL_85;
          }
          goto LABEL_86;
        }
      }
      v14 = &v13[*(unsigned int *)v13 + 4];
      if ( v14 - v11 != v9[1] )
      {
        v15 = (unsigned int *)(v14 + 4);
        if ( *(_DWORD *)v14 )
        {
          v16 = (char *)CoTaskMemAlloc(*(unsigned int *)v14 + 2LL);
          v17 = v16;
          if ( !v16 )
          {
            v5 = -2147024882;
            goto LABEL_86;
          }
          memcpy_0(v16, v14 + 4, *(unsigned int *)v14);
          *(_WORD *)&v17[*(unsigned int *)v14] = 0;
          v5 = (*(__int64 (__fastcall **)(struct IRemoteDevice *, char *))(*(_QWORD *)v3 + 40LL))(v3, v17);
          CoTaskMemFree(v17);
          if ( v5 < 0 )
          {
            if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
              && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v7 = 36;
              v8 = "spRemoteDevice->SetDeviceDescription FAILED";
              goto LABEL_85;
            }
            goto LABEL_86;
          }
          v15 = (unsigned int *)(v14 + 4);
        }
        v18 = (char *)v15 + *(unsigned int *)v14;
        if ( v18 - v11 != v9[1] )
        {
          if ( *(_DWORD *)v18 != 4 )
            goto LABEL_51;
          (*(void (__fastcall **)(struct IRemoteDevice *, _QWORD))(*(_QWORD *)v3 + 232LL))(v3, (unsigned __int8)v18[4]);
          v19 = &v18[*(unsigned int *)v18];
          if ( v19 + 4 - v11 != v9[1] )
          {
            if ( *((_DWORD *)v19 + 1) != 16 )
              goto LABEL_51;
            v5 = (*(__int64 (__fastcall **)(struct IRemoteDevice *, char *))(*(_QWORD *)v3 + 136LL))(v3, v19 + 8);
            if ( v5 < 0 )
            {
              if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
                && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v7 = 37;
                v8 = "spRemoteDevice->SetContainerId FAILED";
                goto LABEL_85;
              }
              goto LABEL_86;
            }
            v20 = &v19[*((unsigned int *)v19 + 1) + 8];
            if ( v20 - v11 != v9[1] )
            {
              if ( *(_DWORD *)v20 != 4 )
              {
LABEL_51:
                v5 = -2147418113;
                goto LABEL_86;
              }
              v21 = *((_DWORD *)v20 + 1);
              si128.m128i_i32[0] = v21 & 1;
              si128.m128i_i32[1] = ((unsigned __int8)v21 >> 1) & 1;
              si128.m128i_i32[2] = ((unsigned __int8)v21 >> 2) & 1;
              si128.m128i_i32[3] = ((unsigned __int8)v21 >> 3) & 1;
            }
          }
        }
      }
    }
    i = (unsigned int)v26;
    goto LABEL_35;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 34;
    v8 = "spRemoteDevice->SetHardwareId FAILED";
    goto LABEL_85;
  }
LABEL_86:
  TCntPtr<IDispatch>::SafeRelease(&v27);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180040838  mov     [rsp-38h+arg_10], rbx
0x18004083d  push    rbp
0x18004083e  push    rsi
0x18004083f  push    rdi
0x180040840  push    r12
0x180040842  push    r13
0x180040844  push    r14
0x180040846  push    r15
0x180040848  mov     rbp, rsp
0x18004084b  sub     rsp, 70h
0x18004084f  mov     rax, cs:__security_cookie
0x180040856  xor     rax, rsp
0x180040859  mov     [rbp+var_10], rax
0x18004085d  mov     r14, rcx
0x180040860  mov     [rbp+var_28], rdx
0x180040864  xor     ebx, ebx
0x180040866  lea     rcx, [rbp+var_38]
0x18004086a  mov     [rbp+var_38], rbx
0x18004086e  mov     r15, rdx
0x180040871  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180040876  movdqa  xmm0, cs:__xmm@00000000000000010000000000000000
0x18004087e  lea     rcx, [r14+48h]; this
0x180040882  movdqu  [rbp+var_20], xmm0
0x180040887  mov     [rbp+var_40], rcx
0x18004088b  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180040890  cmp     dword ptr [r14+88h], 1
0x180040898  jnz     loc_180040EF7
0x18004089e  cmp     dword ptr [r14+80h], 3
0x1800408a6  jnz     loc_180040EF7
0x1800408ac  lea     rcx, [rbp+var_40]; this
0x1800408b0  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800408b5  lea     rcx, [r14+40h]; this
0x1800408b9  mov     rdx, r15; struct tagIRPDR_REDIRECT_DEVICES *
0x1800408bc  call    ?VerifyRedirectDevicesPDU@CCommonPNPPDUHandler@@MEAAJPEAUtagIRPDR_REDIRECT_DEVICES@@@Z; CCommonPNPPDUHandler::VerifyRedirectDevicesPDU(tagIRPDR_REDIRECT_DEVICES *)
0x1800408c1  mov     edi, eax
0x1800408c3  test    eax, eax
0x1800408c5  jns     short loc_180040906
0x1800408c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800408ce  lea     rax, WPP_GLOBAL_Control
0x1800408d5  cmp     rcx, rax
0x1800408d8  jz      loc_180040EEA
0x1800408de  test    byte ptr [rcx+1Ch], 8
0x1800408e2  jz      loc_180040EEA
0x1800408e8  cmp     byte ptr [rcx+19h], 2
0x1800408ec  jb      loc_180040EEA
0x1800408f2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800408f7  lea     edx, [rbx+1Eh]
0x1800408fa  lea     rcx, aVerifyredirect; "VerifyRedirectDevicesPDU failed"
0x180040901  jmp     loc_180040EC7
0x180040906  lea     rsi, [r15+0Ch]
0x18004090a  xor     r13d, r13d
0x18004090d  mov     dword ptr [rbp+var_40], r13d
0x180040911  cmp     r13d, [r15+8]
0x180040915  jnb     loc_180040EEA
0x18004091b  test    rbx, rbx
0x18004091e  jz      short loc_18004093A
0x180040920  lea     rcx, [rbp+var_38]
0x180040924  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x180040929  lea     rcx, [rbp+var_38]
0x18004092d  mov     [rbp+var_38], 0
0x180040935  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18004093a  lea     rcx, [rbp+var_38]; struct IRemoteDevice **
0x18004093e  call    ?CreateInstance@CRemoteDevice@@SAJPEAPEAUIRemoteDevice@@@Z; CRemoteDevice::CreateInstance(IRemoteDevice * *)
0x180040943  mov     edi, eax
0x180040945  test    eax, eax
0x180040947  js      loc_180040E97
0x18004094d  mov     rbx, [rbp+var_38]
0x180040951  mov     edx, [rsi]
0x180040953  mov     rcx, rbx
0x180040956  mov     rax, [rbx]
0x180040959  mov     rax, [rax+0A8h]
0x180040960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040965  mov     edi, eax
0x180040967  test    eax, eax
0x180040969  js      loc_180040E65
0x18004096f  cmp     dword ptr [rsi+4], 0
0x180040973  jz      loc_180040C26
0x180040979  mov     rax, [rbx]
0x18004097c  lea     r15, [rsi+8]
0x180040980  mov     r8d, [r15]
0x180040983  lea     r12, [r15+4]
0x180040987  shr     r8d, 4
0x18004098b  mov     rdx, r12
0x18004098e  mov     rcx, rbx
0x180040991  mov     rax, [rax+58h]
0x180040995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004099a  mov     edi, eax
0x18004099c  test    eax, eax
0x18004099e  js      loc_180040E27
0x1800409a4  mov     eax, [r15]
0x1800409a7  add     r12, rax
0x1800409aa  mov     eax, [rsi+4]
0x1800409ad  mov     rcx, r12
0x1800409b0  sub     rcx, r15
0x1800409b3  cmp     rcx, rax
0x1800409b6  jz      loc_180040B83
0x1800409bc  mov     rax, [rbx]
0x1800409bf  lea     r13, [r12+4]
0x1800409c4  mov     r8d, [r12]
0x1800409c8  mov     rdx, r13
0x1800409cb  shr     r8d, 1
0x1800409ce  mov     rcx, rbx
0x1800409d1  mov     rax, [rax+68h]
0x1800409d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409da  mov     edi, eax
0x1800409dc  test    eax, eax
0x1800409de  js      loc_180040D05
0x1800409e4  mov     r12d, [r12]
0x1800409e8  mov     eax, [rsi+4]
0x1800409eb  add     r12, r13
0x1800409ee  mov     rcx, r12
0x1800409f1  sub     rcx, r15
0x1800409f4  cmp     rcx, rax
0x1800409f7  jz      loc_180040B7F
0x1800409fd  mov     r8d, [r12]
0x180040a01  lea     r13, [r12+4]
0x180040a06  test    r8d, r8d
0x180040a09  jz      short loc_180040A2A
0x180040a0b  mov     rax, [rbx]
0x180040a0e  mov     rdx, r13
0x180040a11  shr     r8d, 1
0x180040a14  mov     rcx, rbx
0x180040a17  mov     rax, [rax+78h]
0x180040a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a20  mov     edi, eax
0x180040a22  test    eax, eax
0x180040a24  js      loc_180040C2E
0x180040a2a  mov     r12d, [r12]
0x180040a2e  mov     eax, [rsi+4]
0x180040a31  add     r12, r13
0x180040a34  mov     rcx, r12
0x180040a37  sub     rcx, r15
0x180040a3a  cmp     rcx, rax
0x180040a3d  jz      loc_180040B7F
0x180040a43  cmp     dword ptr [r12], 0
0x180040a48  lea     rdi, [r12+4]
0x180040a4d  jz      short loc_180040AB7
0x180040a4f  mov     ecx, [r12]
0x180040a53  add     rcx, 2; cb
0x180040a57  cmp     rcx, 2
0x180040a5b  jb      loc_180040CBA
0x180040a61  call    cs:__imp_CoTaskMemAlloc
0x180040a67  mov     r13, rax
0x180040a6a  test    rax, rax
0x180040a6d  jz      loc_180040CB0
0x180040a73  mov     r8d, [r12]; Size
0x180040a77  mov     rdx, rdi; Src
0x180040a7a  mov     rcx, rax; void *
0x180040a7d  call    memcpy_0
0x180040a82  mov     ecx, [r12]
0x180040a86  xor     eax, eax
0x180040a88  mov     rdx, r13
0x180040a8b  mov     [rcx+r13], ax
0x180040a90  mov     rcx, [rbx]
0x180040a93  mov     rax, [rcx+28h]
0x180040a97  mov     rcx, rbx
0x180040a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a9f  mov     rcx, r13; pv
0x180040aa2  mov     edi, eax
0x180040aa4  call    cs:__imp_CoTaskMemFree
0x180040aaa  test    edi, edi
0x180040aac  js      loc_180040C6F
0x180040ab2  lea     rdi, [r12+4]
0x180040ab7  mov     eax, [r12]
0x180040abb  add     rdi, rax
0x180040abe  mov     eax, [rsi+4]
0x180040ac1  mov     rcx, rdi
0x180040ac4  sub     rcx, r15
0x180040ac7  cmp     rcx, rax
0x180040aca  jz      loc_180040B7F
0x180040ad0  cmp     dword ptr [rdi], 4
0x180040ad3  jnz     loc_180040CBA
0x180040ad9  mov     rax, [rbx]
0x180040adc  mov     rcx, rbx
0x180040adf  movzx   edx, byte ptr [rdi+4]
0x180040ae3  mov     rax, [rax+0E8h]
0x180040aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040aef  mov     r13d, [rdi]
0x180040af2  mov     eax, [rsi+4]
0x180040af5  add     r13, rdi
0x180040af8  lea     rcx, [r13+4]
0x180040afc  sub     rcx, r15
0x180040aff  cmp     rcx, rax
0x180040b02  jz      short loc_180040B7F
0x180040b04  cmp     dword ptr [r13+4], 10h
0x180040b09  jnz     loc_180040CBA
0x180040b0f  mov     rax, [rbx]
0x180040b12  lea     r12, [r13+8]
0x180040b16  mov     rdx, r12
0x180040b19  mov     rcx, rbx
0x180040b1c  mov     rax, [rax+88h]
0x180040b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b28  mov     edi, eax
0x180040b2a  test    eax, eax
0x180040b2c  js      loc_180040CC4
0x180040b32  mov     edx, [r13+4]
0x180040b36  mov     eax, [rsi+4]
0x180040b39  add     rdx, r12
0x180040b3c  mov     rcx, rdx
0x180040b3f  sub     rcx, r15
0x180040b42  cmp     rcx, rax
0x180040b45  jz      short loc_180040B7F
0x180040b47  cmp     dword ptr [rdx], 4
0x180040b4a  jnz     loc_180040CBA
0x180040b50  mov     ecx, [rdx+4]
0x180040b53  movzx   eax, cl
0x180040b56  and     eax, 1
0x180040b59  mov     dword ptr [rbp+var_20], eax
0x180040b5c  movzx   eax, cl
0x180040b5f  shr     eax, 1
0x180040b61  and     eax, 1
0x180040b64  mov     dword ptr [rbp+var_20+4], eax
0x180040b67  movzx   eax, cl
0x180040b6a  shr     eax, 2
0x180040b6d  and     eax, 1
0x180040b70  mov     dword ptr [rbp+var_20+8], eax
0x180040b73  movzx   eax, cl
0x180040b76  shr     eax, 3
0x180040b79  and     eax, 1
0x180040b7c  mov     dword ptr [rbp+var_20+0Ch], eax
0x180040b7f  mov     r13d, dword ptr [rbp+var_40]
0x180040b83  mov     rax, [rbx]
0x180040b86  lea     rdx, [rbp+var_20]
0x180040b8a  mov     rcx, rbx
0x180040b8d  mov     rax, [rax+98h]
0x180040b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b99  mov     edi, eax
0x180040b9b  test    eax, eax
0x180040b9d  js      loc_180040DE6
0x180040ba3  lea     rcx, [r14+58h]; this
0x180040ba7  mov     [rbp+var_40], 0
0x180040baf  mov     [rbp+var_30], rcx
0x180040bb3  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180040bb8  xor     edi, edi
0x180040bba  cmp     [r14+68h], rdi
0x180040bbe  jz      short loc_180040BDA
0x180040bc0  lea     rcx, [rbp+var_40]
0x180040bc4  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x180040bc9  mov     rdi, [r14+68h]
0x180040bcd  lea     rcx, [rbp+var_40]
0x180040bd1  mov     [rbp+var_40], rdi
0x180040bd5  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180040bda  lea     rcx, [rbp+var_30]; this
0x180040bde  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180040be3  test    rdi, rdi
0x180040be6  jz      loc_180040DA7
0x180040bec  mov     rax, [rdi]
0x180040bef  mov     rdx, rbx
0x180040bf2  mov     r8d, [r14+90h]
0x180040bf9  mov     rcx, rdi
0x180040bfc  mov     rax, [rax+18h]
0x180040c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c05  mov     edi, eax
0x180040c07  test    eax, eax
0x180040c09  js      loc_180040D46
0x180040c0f  mov     eax, [rsi+4]
0x180040c12  lea     rcx, [rbp+var_40]
0x180040c16  add     rax, 8
0x180040c1a  add     rsi, rax
0x180040c1d  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x180040c22  mov     r15, [rbp+var_28]
0x180040c26  inc     r13d
0x180040c29  jmp     loc_18004090D
0x180040c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c35  lea     rax, WPP_GLOBAL_Control
0x180040c3c  cmp     rcx, rax
0x180040c3f  jz      loc_180040EEA
0x180040c45  test    byte ptr [rcx+1Ch], 8
0x180040c49  jz      loc_180040EEA
0x180040c4f  cmp     byte ptr [rcx+19h], 2
0x180040c53  jb      loc_180040EEA
0x180040c59  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040c5e  mov     edx, 23h ; '#'
0x180040c63  lea     rcx, aSpremotedevice; "spRemoteDevice->SetCompatibilityId FAIL"...
0x180040c6a  jmp     loc_180040EC7
0x180040c6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040c76  lea     rax, WPP_GLOBAL_Control
0x180040c7d  cmp     rcx, rax
0x180040c80  jz      loc_180040EEA
0x180040c86  test    byte ptr [rcx+1Ch], 8
0x180040c8a  jz      loc_180040EEA
0x180040c90  cmp     byte ptr [rcx+19h], 2
0x180040c94  jb      loc_180040EEA
0x180040c9a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040c9f  mov     edx, 24h ; '$'
0x180040ca4  lea     rcx, aSpremotedevice_4; "spRemoteDevice->SetDeviceDescription FA"...
0x180040cab  jmp     loc_180040EC7
0x180040cb0  mov     edi, 8007000Eh
0x180040cb5  jmp     loc_180040EEA
0x180040cba  mov     edi, 8000FFFFh
0x180040cbf  jmp     loc_180040EEA
0x180040cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ccb  lea     rax, WPP_GLOBAL_Control
0x180040cd2  cmp     rcx, rax
0x180040cd5  jz      loc_180040EEA
0x180040cdb  test    byte ptr [rcx+1Ch], 8
0x180040cdf  jz      loc_180040EEA
0x180040ce5  cmp     byte ptr [rcx+19h], 2
0x180040ce9  jb      loc_180040EEA
0x180040cef  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
  ... truncated ...
```
