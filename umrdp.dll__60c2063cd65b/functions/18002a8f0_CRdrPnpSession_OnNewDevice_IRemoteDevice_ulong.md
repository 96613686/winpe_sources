# CRdrPnpSession::OnNewDevice(IRemoteDevice *,ulong)

- ea: `0x18002a8f0`
- end: `0x18002afce`
- name: `?OnNewDevice@CRdrPnpSession@@UEAAJPEAUIRemoteDevice@@K@Z`
- size: `1758`
- prototype: `int(CRdrPnpSession *__hidden this, struct IRemoteDevice *, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180007da0`
- `0x18000b3d0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18002a440`
- `0x18002a580`
- `0x18002a8f0`
- `0x18002b4c8`
- `0x18002b580`
- `0x18002ca80`
- `0x180047ef0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aa9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aa9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002af79`

## string_xrefs

- `0x18002ad43`: `pDevice->SetCompatId failed`
- `0x18002adfe`: `CDeviceEntry::CreateInstance FAILED`

## pseudocode

```c
__int64 __fastcall CRdrPnpSession::OnNewDevice(
        CRdrPnpSession *this,
        struct IRemoteDevice *a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned int v4; // r13d
  struct CDeviceEntry *v5; // rsi
  int PDO; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v10; // edx
  const char *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // r15d
  CRdrPnpSession *v16; // rcx
  const unsigned __int16 *v17; // rbx
  CRdrPnpSession *v18; // rcx
  unsigned int v19; // eax
  _QWORD *v20; // rax
  __int64 *v21; // rdi
  __int64 v22; // rcx
  __int64 *v23; // rax
  unsigned int v25; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v26; // [rsp+34h] [rbp-CCh] BYREF
  struct CDeviceEntry *v27; // [rsp+38h] [rbp-C8h] BYREF
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v29; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v30; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v33[512]; // [rsp+70h] [rbp-90h] BYREF

  v4 = *((_DWORD *)this + 8);
  v5 = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  *((_DWORD *)this + 8) = v4 + 1;
  PDO = CRdrPnpSession::EncodeDevice(*((_DWORD *)this + 7), v4, v33, a4);
  if ( PDO < 0 )
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 23;
      v11 = "EncodeDeviceId failed";
LABEL_6:
      WPP_SF_DsD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        v10,
        (unsigned int)WPP_20fce98516ba3efe262bf7803cb2ce9d_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v11,
        PDO);
      goto LABEL_81;
    }
    goto LABEL_81;
  }
  PDO = (*(__int64 (__fastcall **)(struct IRemoteDevice *, unsigned __int16 *))(*(_QWORD *)a2 + 24LL))(a2, v33);
  if ( PDO >= 0 )
  {
    v12 = *(_QWORD *)a2;
    pv[0] = 0;
    v31 = 0;
    (*(void (__fastcall **)(struct IRemoteDevice *, LPVOID *, int *))(v12 + 48))(a2, pv, &v31);
    if ( pv[0] )
    {
      CoTaskMemFree(pv[0]);
    }
    else
    {
      PDO = (*(__int64 (__fastcall **)(struct IRemoteDevice *, unsigned __int16 *))(*(_QWORD *)a2 + 40LL))(a2, v33);
      if ( PDO < 0 )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_81;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 25;
        goto LABEL_18;
      }
    }
    PDO = (*(__int64 (__fastcall **)(struct IRemoteDevice *, unsigned __int16 *))(*(_QWORD *)a2 + 56LL))(a2, v33);
    if ( PDO < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_81;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 26;
LABEL_18:
      v11 = "pDevice->SetDeviceDescription failed";
      goto LABEL_6;
    }
    v13 = *(_QWORD *)a2;
    v25 = 0;
    PDO = (*(__int64 (__fastcall **)(struct IRemoteDevice *, unsigned __int16 **, unsigned int *))(v13 + 112))(
            a2,
            &v29,
            &v25);
    if ( PDO < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 27;
        v11 = "pDevice->GetHardwareId FAILED";
        goto LABEL_6;
      }
      goto LABEL_81;
    }
    v14 = *(_QWORD *)a2;
    v28 = 0;
    (*(void (__fastcall **)(struct IRemoteDevice *, int *))(v14 + 240))(a2, &v28);
    v15 = v28 & 1;
    PDO = CRdrPnpSession::MarshalHardWareId(v16, &v29, v25, 0, &v25, v15);
    if ( PDO < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_81;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 28;
      goto LABEL_35;
    }
    PDO = (*(__int64 (__fastcall **)(struct IRemoteDevice *, unsigned __int16 *, _QWORD))(*(_QWORD *)a2 + 104LL))(
            a2,
            v29,
            v25);
    if ( PDO < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 29;
        v11 = "pDevice->SetHardwareId failed";
        goto LABEL_6;
      }
      goto LABEL_81;
    }
    v26 = 0;
    v17 = L"TS_POS_DEVICE";
    if ( !(_BYTE)v15 )
      v17 = L"TS_GENERIC_PNP_DEVICE";
    if ( (*(unsigned int (__fastcall **)(struct IRemoteDevice *, unsigned __int16 **, unsigned int *))(*(_QWORD *)a2 + 128LL))(
           a2,
           &v30,
           &v26)
      || v26 <= 2 )
    {
      PDO = (*(__int64 (__fastcall **)(struct IRemoteDevice *, const unsigned __int16 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
              a2,
              v17,
              8 * (v15 ^ 1u) + 15);
      if ( PDO < 0 )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_81;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 32;
LABEL_55:
        v11 = "pDevice->SetCompatId failed";
        goto LABEL_6;
      }
    }
    else
    {
      PDO = CRdrPnpSession::MarshalHardWareId(v18, &v30, v26, v17, &v26, v15);
      if ( PDO < 0 )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_81;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 30;
LABEL_35:
        v11 = "MarshalHardWareId failed";
        goto LABEL_6;
      }
      PDO = (*(__int64 (__fastcall **)(struct IRemoteDevice *, unsigned __int16 *, _QWORD))(*(_QWORD *)a2 + 120LL))(
              a2,
              v30,
              v26);
      if ( PDO < 0 )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_81;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 31;
        goto LABEL_55;
      }
    }
    PDO = CDeviceEntry::CreateInstance(
            a2,
            *((_DWORD *)this + 7),
            *((struct CSessionThreadPool **)this + 13),
            *((struct IDispatch **)this + 6),
            *((struct IComTsBus **)this + 7),
            &v27);
    if ( PDO < 0 )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          33,
          (unsigned int)WPP_20fce98516ba3efe262bf7803cb2ce9d_Traceguids,
          v19,
          (__int64)"CDeviceEntry::CreateInstance FAILED",
          PDO);
      }
      v5 = v27;
      goto LABEL_81;
    }
    v5 = v27;
    PDO = (*(__int64 (__fastcall **)(struct IRemoteDevice *, struct CDeviceEntry *))(*(_QWORD *)a2 + 200LL))(a2, v27);
    if ( PDO >= 0 )
    {
      PDO = (*(__int64 (__fastcall **)(struct IRemoteDevice *, _QWORD))(*(_QWORD *)a2 + 184LL))(
              a2,
              *((unsigned int *)v5 + 17));
      if ( PDO >= 0 )
      {
        v27 = (CRdrPnpSession *)((char *)this + 88);
        CTSCriticalSection::Lock((CRdrPnpSession *)((char *)this + 88));
        v20 = (_QWORD *)*((_QWORD *)this + 10);
        v21 = (__int64 *)((char *)v5 + 48);
        *((_QWORD *)v5 + 6) = (char *)this + 72;
        *((_QWORD *)v5 + 7) = v20;
        *v20 = (char *)v5 + 48;
        ++*((_DWORD *)this + 16);
        *((_QWORD *)this + 10) = (char *)v5 + 48;
        *((_DWORD *)v5 + 16) = v4;
        PDO = CDeviceEntry::AsyncCreatePDO(v5);
        if ( PDO )
        {
          --*((_DWORD *)this + 16);
          v22 = *v21;
          v23 = (__int64 *)*((_QWORD *)v5 + 7);
          *v23 = *v21;
          *(_QWORD *)(v22 + 8) = v23;
          CDeviceEntry::Terminate((struct CDeviceEntry *)((char *)v5 + 8));
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 + 4) + 16LL))(*((_QWORD *)v5 + 4));
          v5 = 0;
        }
        CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v27);
        goto LABEL_81;
      }
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_81;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 35;
    }
    else
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_81;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 34;
    }
    v11 = " pDevice->SetContextData FAILED";
    goto LABEL_6;
  }
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 24;
    v11 = "pDevice->SetIdentity failed";
    goto LABEL_6;
  }
LABEL_81:
  if ( v29 )
    CoTaskMemFree(v29);
  if ( v30 )
    CoTaskMemFree(v30);
  if ( PDO && v5 )
  {
    CDeviceEntry::Terminate((struct CDeviceEntry *)((char *)v5 + 8));
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 + 4) + 16LL))(*((_QWORD *)v5 + 4));
  }
  return (unsigned int)PDO;
}

```

## disassembly

```asm
0x18002a8f0  mov     [rsp-8+arg_10], rbx
0x18002a8f5  mov     [rsp-8+arg_18], rsi
0x18002a8fa  push    rbp
0x18002a8fb  push    rdi
0x18002a8fc  push    r13
0x18002a8fe  push    r14
0x18002a900  push    r15
0x18002a902  lea     rbp, [rsp-380h]
0x18002a90a  sub     rsp, 480h
0x18002a911  mov     rax, cs:__security_cookie
0x18002a918  xor     rax, rsp
0x18002a91b  mov     [rbp+3A0h+var_30], rax
0x18002a922  mov     r13d, [rcx+20h]
0x18002a926  lea     r8, [rsp+4A0h+var_430]; unsigned __int16 *
0x18002a92b  xor     esi, esi
0x18002a92d  mov     rdi, rdx
0x18002a930  mov     r14, rcx
0x18002a933  mov     [rsp+4A0h+var_468], rsi
0x18002a938  mov     edx, r13d; unsigned int
0x18002a93b  mov     [rsp+4A0h+var_458], rsi
0x18002a940  lea     eax, [r13+1]
0x18002a944  mov     [rsp+4A0h+var_450], rsi
0x18002a949  mov     [rcx+20h], eax
0x18002a94c  mov     ecx, [rcx+1Ch]; unsigned int
0x18002a94f  call    ?EncodeDevice@CRdrPnpSession@@SAJKKPEAGK@Z; CRdrPnpSession::EncodeDevice(ulong,ulong,ushort *,ulong)
0x18002a954  mov     ebx, eax
0x18002a956  test    eax, eax
0x18002a958  jns     short loc_18002A9BC
0x18002a95a  mov     rax, cs:WPP_GLOBAL_Control
0x18002a961  lea     rcx, WPP_GLOBAL_Control
0x18002a968  cmp     rax, rcx
0x18002a96b  jz      loc_18002AF5F
0x18002a971  test    byte ptr [rax+1Ch], 8
0x18002a975  jz      loc_18002AF5F
0x18002a97b  cmp     byte ptr [rax+19h], 2
0x18002a97f  jb      loc_18002AF5F
0x18002a985  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002a98a  lea     edx, [rsi+17h]
0x18002a98d  lea     rcx, aEncodedeviceid; "EncodeDeviceId failed"
0x18002a994  mov     dword ptr [rsp+4A0h+var_478], ebx
0x18002a998  lea     r8, WPP_20fce98516ba3efe262bf7803cb2ce9d_Traceguids
0x18002a99f  mov     [rsp+4A0h+var_480], rcx
0x18002a9a4  mov     r9d, eax
0x18002a9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a9ae  mov     rcx, [rcx+10h]
0x18002a9b2  call    WPP_SF_DsD
0x18002a9b7  jmp     loc_18002AF5F
0x18002a9bc  mov     rax, [rdi]
0x18002a9bf  lea     rdx, [rsp+4A0h+var_430]
0x18002a9c4  mov     rcx, rdi
0x18002a9c7  mov     rax, [rax+18h]
0x18002a9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9d0  mov     ebx, eax
0x18002a9d2  test    eax, eax
0x18002a9d4  jns     short loc_18002AA14
0x18002a9d6  mov     rax, cs:WPP_GLOBAL_Control
0x18002a9dd  lea     rcx, WPP_GLOBAL_Control
0x18002a9e4  cmp     rax, rcx
0x18002a9e7  jz      loc_18002AF5F
0x18002a9ed  test    byte ptr [rax+1Ch], 8
0x18002a9f1  jz      loc_18002AF5F
0x18002a9f7  cmp     byte ptr [rax+19h], 2
0x18002a9fb  jb      loc_18002AF5F
0x18002aa01  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002aa06  mov     edx, 18h
0x18002aa0b  lea     rcx, aPdeviceSetiden; "pDevice->SetIdentity failed"
0x18002aa12  jmp     short loc_18002A994
0x18002aa14  mov     rax, [rdi]
0x18002aa17  lea     r8, [rsp+4A0h+var_448]
0x18002aa1c  lea     rdx, [rsp+4A0h+pv]
0x18002aa21  mov     [rsp+4A0h+pv], rsi
0x18002aa26  mov     rcx, rdi
0x18002aa29  mov     [rsp+4A0h+var_448], esi
0x18002aa2d  mov     rax, [rax+30h]
0x18002aa31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa36  mov     rcx, [rsp+4A0h+pv]; pv
0x18002aa3b  test    rcx, rcx
0x18002aa3e  jnz     short loc_18002AA9B
0x18002aa40  mov     rax, [rdi]
0x18002aa43  lea     rdx, [rsp+4A0h+var_430]
0x18002aa48  mov     rcx, rdi
0x18002aa4b  mov     rax, [rax+28h]
0x18002aa4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa54  mov     ebx, eax
0x18002aa56  test    eax, eax
0x18002aa58  jns     short loc_18002AAA1
0x18002aa5a  mov     rax, cs:WPP_GLOBAL_Control
0x18002aa61  lea     rcx, WPP_GLOBAL_Control
0x18002aa68  cmp     rax, rcx
0x18002aa6b  jz      loc_18002AF5F
0x18002aa71  test    byte ptr [rax+1Ch], 8
0x18002aa75  jz      loc_18002AF5F
0x18002aa7b  cmp     byte ptr [rax+19h], 2
0x18002aa7f  jb      loc_18002AF5F
0x18002aa85  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002aa8a  mov     edx, 19h
0x18002aa8f  lea     rcx, aPdeviceSetdevi; "pDevice->SetDeviceDescription failed"
0x18002aa96  jmp     loc_18002A994
0x18002aa9b  call    cs:__imp_CoTaskMemFree
0x18002aaa1  mov     rax, [rdi]
0x18002aaa4  lea     rdx, [rsp+4A0h+var_430]
0x18002aaa9  mov     rcx, rdi
0x18002aaac  mov     rax, [rax+38h]
0x18002aab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aab5  mov     ebx, eax
0x18002aab7  test    eax, eax
0x18002aab9  jns     short loc_18002AAF2
0x18002aabb  mov     rax, cs:WPP_GLOBAL_Control
0x18002aac2  lea     rcx, WPP_GLOBAL_Control
0x18002aac9  cmp     rax, rcx
0x18002aacc  jz      loc_18002AF5F
0x18002aad2  test    byte ptr [rax+1Ch], 8
0x18002aad6  jz      loc_18002AF5F
0x18002aadc  cmp     byte ptr [rax+19h], 2
0x18002aae0  jb      loc_18002AF5F
0x18002aae6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002aaeb  mov     edx, 1Ah
0x18002aaf0  jmp     short loc_18002AA8F
0x18002aaf2  mov     rax, [rdi]
0x18002aaf5  lea     r8, [rsp+4A0h+var_470]
0x18002aafa  lea     rdx, [rsp+4A0h+var_458]
0x18002aaff  mov     [rsp+4A0h+var_470], esi
0x18002ab03  mov     rcx, rdi
0x18002ab06  mov     rax, [rax+70h]
0x18002ab0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab0f  mov     ebx, eax
0x18002ab11  test    eax, eax
0x18002ab13  jns     short loc_18002AB56
0x18002ab15  mov     rax, cs:WPP_GLOBAL_Control
0x18002ab1c  lea     rcx, WPP_GLOBAL_Control
0x18002ab23  cmp     rax, rcx
0x18002ab26  jz      loc_18002AF5F
0x18002ab2c  test    byte ptr [rax+1Ch], 8
0x18002ab30  jz      loc_18002AF5F
0x18002ab36  cmp     byte ptr [rax+19h], 2
0x18002ab3a  jb      loc_18002AF5F
0x18002ab40  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ab45  mov     edx, 1Bh
0x18002ab4a  lea     rcx, aPdeviceGethard; "pDevice->GetHardwareId FAILED"
0x18002ab51  jmp     loc_18002A994
0x18002ab56  mov     rax, [rdi]
0x18002ab59  lea     rdx, [rsp+4A0h+var_460]
0x18002ab5e  mov     rcx, rdi
0x18002ab61  mov     [rsp+4A0h+var_460], esi
0x18002ab65  mov     rax, [rax+0F0h]
0x18002ab6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab71  mov     al, byte ptr [rsp+4A0h+var_460]
0x18002ab75  lea     rdx, [rsp+4A0h+var_458]; unsigned __int16 **
0x18002ab7a  mov     r8d, [rsp+4A0h+var_470]; unsigned int
0x18002ab7f  and     al, 1
0x18002ab81  movzx   r15d, al
0x18002ab85  xor     r9d, r9d; unsigned __int16 *
0x18002ab88  lea     rax, [rsp+4A0h+var_470]
0x18002ab8d  mov     dword ptr [rsp+4A0h+var_478], r15d; int
0x18002ab92  mov     [rsp+4A0h+var_480], rax; unsigned int *
0x18002ab97  call    ?MarshalHardWareId@CRdrPnpSession@@AEAAJPEAPEAGKPEBGPEAKH@Z; CRdrPnpSession::MarshalHardWareId(ushort * *,ulong,ushort const *,ulong *,int)
0x18002ab9c  mov     ebx, eax
0x18002ab9e  test    eax, eax
0x18002aba0  jns     short loc_18002ABE3
0x18002aba2  mov     rax, cs:WPP_GLOBAL_Control
0x18002aba9  lea     rcx, WPP_GLOBAL_Control
0x18002abb0  cmp     rax, rcx
0x18002abb3  jz      loc_18002AF5F
0x18002abb9  test    byte ptr [rax+1Ch], 8
0x18002abbd  jz      loc_18002AF5F
0x18002abc3  cmp     byte ptr [rax+19h], 2
0x18002abc7  jb      loc_18002AF5F
0x18002abcd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002abd2  mov     edx, 1Ch
0x18002abd7  lea     rcx, aMarshalhardwar; "MarshalHardWareId failed"
0x18002abde  jmp     loc_18002A994
0x18002abe3  mov     rax, [rdi]
0x18002abe6  mov     rcx, rdi
0x18002abe9  mov     r8d, [rsp+4A0h+var_470]
0x18002abee  mov     rdx, [rsp+4A0h+var_458]
0x18002abf3  mov     rax, [rax+68h]
0x18002abf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abfc  mov     ebx, eax
0x18002abfe  test    eax, eax
0x18002ac00  jns     short loc_18002AC43
0x18002ac02  mov     rax, cs:WPP_GLOBAL_Control
0x18002ac09  lea     rcx, WPP_GLOBAL_Control
0x18002ac10  cmp     rax, rcx
0x18002ac13  jz      loc_18002AF5F
0x18002ac19  test    byte ptr [rax+1Ch], 8
0x18002ac1d  jz      loc_18002AF5F
0x18002ac23  cmp     byte ptr [rax+19h], 2
0x18002ac27  jb      loc_18002AF5F
0x18002ac2d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ac32  mov     edx, 1Dh
0x18002ac37  lea     rcx, aPdeviceSethard; "pDevice->SetHardwareId failed"
0x18002ac3e  jmp     loc_18002A994
0x18002ac43  lea     rax, aTsGenericPnpDe; "TS_GENERIC_PNP_DEVICE"
0x18002ac4a  mov     [rsp+4A0h+var_46C], esi
0x18002ac4e  test    r15b, r15b
0x18002ac51  lea     rbx, aTsPosDevice; "TS_POS_DEVICE"
0x18002ac58  lea     r8, [rsp+4A0h+var_46C]
0x18002ac5d  mov     rcx, rdi
0x18002ac60  cmovz   rbx, rax
0x18002ac64  lea     rdx, [rsp+4A0h+var_450]
0x18002ac69  mov     rax, [rdi]
0x18002ac6c  mov     rax, [rax+80h]
0x18002ac73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac78  test    eax, eax
0x18002ac7a  jnz     loc_18002AD4F
0x18002ac80  mov     r8d, [rsp+4A0h+var_46C]; unsigned int
0x18002ac85  cmp     r8d, 2
0x18002ac89  jbe     loc_18002AD4F
0x18002ac8f  lea     rax, [rsp+4A0h+var_46C]
0x18002ac94  mov     dword ptr [rsp+4A0h+var_478], r15d; int
0x18002ac99  mov     r9, rbx; unsigned __int16 *
0x18002ac9c  mov     [rsp+4A0h+var_480], rax; unsigned int *
0x18002aca1  lea     rdx, [rsp+4A0h+var_450]; unsigned __int16 **
0x18002aca6  call    ?MarshalHardWareId@CRdrPnpSession@@AEAAJPEAPEAGKPEBGPEAKH@Z; CRdrPnpSession::MarshalHardWareId(ushort * *,ulong,ushort const *,ulong *,int)
0x18002acab  mov     ebx, eax
0x18002acad  test    eax, eax
0x18002acaf  jns     short loc_18002ACEB
0x18002acb1  mov     rax, cs:WPP_GLOBAL_Control
0x18002acb8  lea     rcx, WPP_GLOBAL_Control
0x18002acbf  cmp     rax, rcx
0x18002acc2  jz      loc_18002AF5F
0x18002acc8  test    byte ptr [rax+1Ch], 8
0x18002accc  jz      loc_18002AF5F
0x18002acd2  cmp     byte ptr [rax+19h], 2
0x18002acd6  jb      loc_18002AF5F
0x18002acdc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ace1  mov     edx, 1Eh
0x18002ace6  jmp     loc_18002ABD7
0x18002aceb  mov     rax, [rdi]
0x18002acee  mov     rcx, rdi
0x18002acf1  mov     r8d, [rsp+4A0h+var_46C]
0x18002acf6  mov     rdx, [rsp+4A0h+var_450]
0x18002acfb  mov     rax, [rax+78h]
0x18002acff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad04  mov     ebx, eax
0x18002ad06  test    eax, eax
0x18002ad08  jns     loc_18002ADAD
0x18002ad0e  mov     rax, cs:WPP_GLOBAL_Control
0x18002ad15  lea     rcx, WPP_GLOBAL_Control
0x18002ad1c  cmp     rax, rcx
0x18002ad1f  jz      loc_18002AF5F
0x18002ad25  test    byte ptr [rax+1Ch], 8
0x18002ad29  jz      loc_18002AF5F
0x18002ad2f  cmp     byte ptr [rax+19h], 2
0x18002ad33  jb      loc_18002AF5F
0x18002ad39  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ad3e  mov     edx, 1Fh
0x18002ad43  lea     rcx, aPdeviceSetcomp; "pDevice->SetCompatId failed"
0x18002ad4a  jmp     loc_18002A994
0x18002ad4f  mov     rax, [rdi]
0x18002ad52  mov     r8d, r15d
0x18002ad55  xor     r8d, 1
0x18002ad59  mov     rdx, rbx
0x18002ad5c  mov     rcx, rdi
0x18002ad5f  mov     rax, [rax+78h]
0x18002ad63  lea     r8d, ds:0Fh[r8*8]
0x18002ad6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad70  mov     ebx, eax
0x18002ad72  test    eax, eax
0x18002ad74  jns     short loc_18002ADAD
0x18002ad76  mov     rax, cs:WPP_GLOBAL_Control
0x18002ad7d  lea     rcx, WPP_GLOBAL_Control
0x18002ad84  cmp     rax, rcx
0x18002ad87  jz      loc_18002AF5F
0x18002ad8d  test    byte ptr [rax+1Ch], 8
0x18002ad91  jz      loc_18002AF5F
0x18002ad97  cmp     byte ptr [rax+19h], 2
0x18002ad9b  jb      loc_18002AF5F
0x18002ada1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ada6  mov     edx, 20h ; ' '
0x18002adab  jmp     short loc_18002AD43
0x18002adad  mov     r9, [r14+30h]; struct IDispatch *
0x18002adb1  lea     rax, [rsp+4A0h+var_468]
0x18002adb6  mov     r8, [r14+68h]; struct CSessionThreadPool *
0x18002adba  mov     rcx, rdi; struct IRemoteDevice *
0x18002adbd  mov     edx, [r14+1Ch]; unsigned int
0x18002adc1  mov     [rsp+4A0h+var_478], rax; struct CDeviceEntry **
0x18002adc6  mov     rax, [r14+38h]
0x18002adca  mov     [rsp+4A0h+var_480], rax; struct IComTsBus *
0x18002adcf  call    ?CreateInstance@CDeviceEntry@@SAJPEAUIRemoteDevice@@KPEAVCSessionThreadPool@@PEAUIDispatch@@PEAUIComTsBus@@PEAPEAV1@@Z; CDeviceEntry::CreateInstance(IRemoteDevice *,ulong,CSessionThreadPool *,IDispatch *,IComTsBus *,CDeviceEntry * *)
0x18002add4  mov     ebx, eax
0x18002add6  test    eax, eax
0x18002add8  jns     short loc_18002AE37
0x18002adda  mov     rax, cs:WPP_GLOBAL_Control
0x18002ade1  lea     rcx, WPP_GLOBAL_Control
0x18002ade8  cmp     rax, rcx
0x18002adeb  jz      short loc_18002AE2D
0x18002aded  test    byte ptr [rax+1Ch], 8
0x18002adf1  jz      short loc_18002AE2D
0x18002adf3  cmp     byte ptr [rax+19h], 2
0x18002adf7  jb      short loc_18002AE2D
0x18002adf9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002adfe  lea     rcx, aCdeviceentryCr; "CDeviceEntry::CreateInstance FAILED"
0x18002ae05  mov     dword ptr [rsp+4A0h+var_478], ebx
0x18002ae09  mov     [rsp+4A0h+var_480], rcx
0x18002ae0e  lea     r8, WPP_20fce98516ba3efe262bf7803cb2ce9d_Traceguids
0x18002ae15  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae1c  mov     edx, 21h ; '!'
0x18002ae21  mov     r9d, eax
0x18002ae24  mov     rcx, [rcx+10h]
  ... truncated ...
```
