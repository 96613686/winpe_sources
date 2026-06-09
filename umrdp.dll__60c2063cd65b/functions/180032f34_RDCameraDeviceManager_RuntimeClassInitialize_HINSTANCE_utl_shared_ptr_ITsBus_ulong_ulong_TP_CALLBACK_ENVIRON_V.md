# RDCameraDeviceManager::RuntimeClassInitialize(HINSTANCE__ *,utl::shared_ptr<ITsBus>,ulong,ulong,_TP_CALLBACK_ENVIRON_V3 const &)

- ea: `0x180032f34`
- end: `0x1800331dc`
- name: `?RuntimeClassInitialize@RDCameraDeviceManager@@QEAAJPEAUHINSTANCE__@@V?$shared_ptr@VITsBus@@@utl@@KKAEBU_TP_CALLBACK_ENVIRON_V3@@@Z`
- size: `680`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031508`

## callees

- `0x1800096e8`
- `0x180009fa8`
- `0x18000a4f0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000f79c`
- `0x180030e48`
- `0x180032f34`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003302b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003302b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032f66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032f66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800331a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800331a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180032ff7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180032ff7`

## string_xrefs

- `0x1800330f7`: `CreateServerSideVCManager failed`
- `0x1800330a0`: `StringCchCopy(m_szFriendlyNameTemplate) failed`
- `0x180033171`: `spVCManager->OpenDynamicChannel failed`

## pseudocode

```c
__int64 __fastcall RDCameraDeviceManager::RuntimeClassInitialize(
        __int64 a1,
        HINSTANCE a2,
        __int64 *a3,
        int a4,
        int a5,
        __int64 a6)
{
  struct _RTL_CRITICAL_SECTION *v6; // r14
  __int64 v11; // rax
  __int64 v12; // rcx
  utl::_RefCountBase *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v20; // ebx
  unsigned int v21; // eax
  int v22; // edx
  const char *v23; // rcx
  struct IServerVCChannelManager *v24; // rsi
  __int64 (__fastcall *v25)(struct IServerVCChannelManager *, const char *, _QWORD, _QWORD, _DWORD, __int64, __int64); // rdi
  utl::_RefCountBase *v26; // rcx
  struct IServerVCChannelManager *v28; // [rsp+70h] [rbp+8h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  v28 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v11 = a3[1];
  v12 = *a3;
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  *(_QWORD *)(a1 + 56) = v12;
  v13 = *(utl::_RefCountBase **)(a1 + 64);
  *(_QWORD *)(a1 + 64) = v11;
  if ( v13 )
    utl::_RefCountBase::_DecStrong(v13);
  *(_DWORD *)(a1 + 596) = a5;
  v14 = a6;
  *(_DWORD *)(a1 + 592) = a4;
  *(_OWORD *)(a1 + 640) = *(_OWORD *)v14;
  *(_OWORD *)(a1 + 656) = *(_OWORD *)(v14 + 16);
  *(_OWORD *)(a1 + 672) = *(_OWORD *)(v14 + 32);
  *(_OWORD *)(a1 + 688) = *(_OWORD *)(v14 + 48);
  *(_QWORD *)(a1 + 704) = *(_QWORD *)(v14 + 64);
  if ( LoadStringW(a2, 0x836u, (LPWSTR)(a1 + 72), 260) )
    goto LABEL_15;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    LastError = GetLastError();
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      14,
      WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
  }
  v20 = StringCchCopyW((unsigned __int16 *)(a1 + 72), 0x104u, L"%1 (redirected)");
  if ( v20 >= 0 )
  {
LABEL_15:
    Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(&v28, v15, v16, v17);
    v20 = CreateServerSideVCManager(&v28);
    if ( v20 >= 0 )
    {
      v24 = v28;
      v25 = *(__int64 (__fastcall **)(struct IServerVCChannelManager *, const char *, _QWORD, _QWORD, _DWORD, __int64, __int64))(*(_QWORD *)v28 + 32LL);
      Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(a1 + 600, v15, v16, v17);
      v20 = v25(v24, "RDCamera_Device_Enumerator", *(unsigned int *)(a1 + 592), 0, 0, a1, a1 + 600);
      if ( v20 < 0
        && *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v21 = RdpWppGetCurrentThreadActivityIdPrefix();
        v22 = 17;
        v23 = "spVCManager->OpenDynamicChannel failed";
        goto LABEL_25;
      }
    }
    else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
           && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      v22 = 16;
      v23 = "CreateServerSideVCManager failed";
      goto LABEL_25;
    }
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v21 = RdpWppGetCurrentThreadActivityIdPrefix();
    v22 = 15;
    v23 = "StringCchCopy(m_szFriendlyNameTemplate) failed";
LABEL_25:
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      v22,
      (unsigned int)WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
      v21,
      (__int64)v23,
      v20);
  }
  if ( v6 )
    LeaveCriticalSection(v6);
  Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(&v28, v15, v16, v17);
  v26 = (utl::_RefCountBase *)a3[1];
  if ( v26 )
    utl::_RefCountBase::_DecStrong(v26);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180032f34  mov     [rsp+arg_8], rbx
0x180032f39  mov     [rsp+arg_10], rbp
0x180032f3e  push    rsi
0x180032f3f  push    rdi
0x180032f40  push    r13
0x180032f42  push    r14
0x180032f44  push    r15
0x180032f46  sub     rsp, 40h
0x180032f4a  lea     r14, [rcx+10h]
0x180032f4e  mov     [rsp+68h+arg_0], 0
0x180032f57  mov     rbp, rcx
0x180032f5a  mov     ebx, r9d
0x180032f5d  mov     rcx, r14; lpCriticalSection
0x180032f60  mov     r15, r8
0x180032f63  mov     rsi, rdx
0x180032f66  call    cs:__imp_EnterCriticalSection
0x180032f6c  mov     rax, [r15+8]
0x180032f70  mov     rcx, [r15]
0x180032f73  test    rax, rax
0x180032f76  jz      short loc_180032F7C
0x180032f78  lock inc dword ptr [rax+8]
0x180032f7c  mov     [rbp+38h], rcx
0x180032f80  mov     rcx, [rbp+40h]; this
0x180032f84  mov     [rbp+40h], rax
0x180032f88  test    rcx, rcx
0x180032f8b  jz      short loc_180032F92
0x180032f8d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180032f92  mov     eax, [rsp+68h+arg_20]
0x180032f99  lea     r8, [rbp+48h]; lpBuffer
0x180032f9d  mov     [rbp+254h], eax
0x180032fa3  mov     r9d, 104h; cchBufferMax
0x180032fa9  mov     rax, [rsp+68h+arg_28]
0x180032fb1  mov     edx, 836h; uID
0x180032fb6  mov     [rbp+250h], ebx
0x180032fbc  mov     rcx, rsi; hInstance
0x180032fbf  movups  xmm0, xmmword ptr [rax]
0x180032fc2  movups  xmmword ptr [rbp+280h], xmm0
0x180032fc9  movups  xmm1, xmmword ptr [rax+10h]
0x180032fcd  movups  xmmword ptr [rbp+290h], xmm1
0x180032fd4  movups  xmm0, xmmword ptr [rax+20h]
0x180032fd8  movups  xmmword ptr [rbp+2A0h], xmm0
0x180032fdf  movups  xmm1, xmmword ptr [rax+30h]
0x180032fe3  movups  xmmword ptr [rbp+2B0h], xmm1
0x180032fea  movsd   xmm0, qword ptr [rax+40h]
0x180032fef  movsd   qword ptr [rbp+2C0h], xmm0
0x180032ff7  call    cs:__imp_LoadStringW
0x180032ffd  lea     r13, WPP_GLOBAL_Control
0x180033004  lea     rsi, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x18003300b  test    eax, eax
0x18003300d  jnz     loc_1800330AF
0x180033013  mov     rax, cs:WPP_GLOBAL_Control
0x18003301a  cmp     rax, r13
0x18003301d  jz      short loc_180033057
0x18003301f  test    byte ptr [rax+1Ch], 1
0x180033023  jz      short loc_180033057
0x180033025  cmp     byte ptr [rax+19h], 2
0x180033029  jb      short loc_180033057
0x18003302b  call    cs:__imp_GetLastError
0x180033031  mov     ebx, eax
0x180033033  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180033038  mov     rcx, cs:WPP_GLOBAL_Control
0x18003303f  mov     edx, 0Eh
0x180033044  mov     r9d, eax
0x180033047  mov     dword ptr [rsp+68h+var_48], ebx
0x18003304b  mov     r8, rsi
0x18003304e  mov     rcx, [rcx+10h]
0x180033052  call    WPP_SF_Dd
0x180033057  lea     r8, a1Redirected; "%1 (redirected)"
0x18003305e  mov     edx, 104h; unsigned __int64
0x180033063  lea     rcx, [rbp+48h]; unsigned __int16 *
0x180033067  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003306c  mov     ebx, eax
0x18003306e  test    eax, eax
0x180033070  jns     short loc_1800330AF
0x180033072  mov     rax, cs:WPP_GLOBAL_Control
0x180033079  cmp     rax, r13
0x18003307c  jz      loc_18003319B
0x180033082  test    byte ptr [rax+1Ch], 8
0x180033086  jz      loc_18003319B
0x18003308c  cmp     byte ptr [rax+19h], 2
0x180033090  jb      loc_18003319B
0x180033096  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003309b  mov     edx, 0Fh
0x1800330a0  lea     rcx, aStringcchcopyM; "StringCchCopy(m_szFriendlyNameTemplate)"...
0x1800330a7  mov     r8, rsi
0x1800330aa  jmp     loc_18003317F
0x1800330af  lea     rcx, [rsp+68h+arg_0]
0x1800330b4  call    ?InternalRelease@?$ComPtr@UIServerVCChannelManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(void)
0x1800330b9  lea     rcx, [rsp+68h+arg_0]; struct IServerVCChannelManager **
0x1800330be  call    ?CreateServerSideVCManager@@YAJPEAPEAUIServerVCChannelManager@@@Z; CreateServerSideVCManager(IServerVCChannelManager * *)
0x1800330c3  mov     ebx, eax
0x1800330c5  test    eax, eax
0x1800330c7  jns     short loc_180033100
0x1800330c9  mov     rax, cs:WPP_GLOBAL_Control
0x1800330d0  cmp     rax, r13
0x1800330d3  jz      loc_18003319B
0x1800330d9  test    byte ptr [rax+1Ch], 8
0x1800330dd  jz      loc_18003319B
0x1800330e3  cmp     byte ptr [rax+19h], 2
0x1800330e7  jb      loc_18003319B
0x1800330ed  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800330f2  mov     edx, 10h
0x1800330f7  lea     rcx, aCreateserversi; "CreateServerSideVCManager failed"
0x1800330fe  jmp     short loc_1800330A7
0x180033100  mov     rsi, [rsp+68h+arg_0]
0x180033105  lea     rbx, [rbp+258h]
0x18003310c  mov     rcx, rbx
0x18003310f  mov     rax, [rsi]
0x180033112  mov     rdi, [rax+20h]
0x180033116  call    ?InternalRelease@?$ComPtr@UIServerVCChannelManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(void)
0x18003311b  mov     r8d, [rbp+250h]
0x180033122  lea     rdx, aRdcameraDevice; "RDCamera_Device_Enumerator"
0x180033129  mov     [rsp+68h+var_38], rbx
0x18003312e  xor     r9d, r9d
0x180033131  mov     [rsp+68h+var_40], rbp
0x180033136  mov     rcx, rsi
0x180033139  mov     rax, rdi
0x18003313c  mov     dword ptr [rsp+68h+var_48], 0
0x180033144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033149  mov     ebx, eax
0x18003314b  test    eax, eax
0x18003314d  jns     short loc_18003319B
0x18003314f  mov     rax, cs:WPP_GLOBAL_Control
0x180033156  cmp     rax, r13
0x180033159  jz      short loc_18003319B
0x18003315b  test    byte ptr [rax+1Ch], 8
0x18003315f  jz      short loc_18003319B
0x180033161  cmp     byte ptr [rax+19h], 2
0x180033165  jb      short loc_18003319B
0x180033167  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003316c  mov     edx, 11h
0x180033171  lea     rcx, aSpvcmanagerOpe; "spVCManager->OpenDynamicChannel failed"
0x180033178  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x18003317f  mov     dword ptr [rsp+68h+var_40], ebx
0x180033183  mov     r9d, eax
0x180033186  mov     [rsp+68h+var_48], rcx
0x18003318b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033192  mov     rcx, [rcx+10h]
0x180033196  call    WPP_SF_DsD
0x18003319b  test    r14, r14
0x18003319e  jz      short loc_1800331A9
0x1800331a0  mov     rcx, r14; lpCriticalSection
0x1800331a3  call    cs:__imp_LeaveCriticalSection
0x1800331a9  lea     rcx, [rsp+68h+arg_0]
0x1800331ae  call    ?InternalRelease@?$ComPtr@UIServerVCChannelManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IServerVCChannelManager>::InternalRelease(void)
0x1800331b3  mov     rcx, [r15+8]; this
0x1800331b7  test    rcx, rcx
0x1800331ba  jz      short loc_1800331C1
0x1800331bc  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800331c1  lea     r11, [rsp+68h+var_28]
0x1800331c6  mov     eax, ebx
0x1800331c8  mov     rbx, [r11+38h]
0x1800331cc  mov     rbp, [r11+40h]
0x1800331d0  mov     rsp, r11
0x1800331d3  pop     r15
0x1800331d5  pop     r14
0x1800331d7  pop     r13
0x1800331d9  pop     rdi
0x1800331da  pop     rsi
0x1800331db  retn
```
