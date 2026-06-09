# CBackstackManager::GetBackstack(IObjectArray * *,int)

- ea: `0x180042df0`
- end: `0x1800433a4`
- name: `?GetBackstack@CBackstackManager@@UEAAJPEAPEAUIObjectArray@@H@Z`
- size: `1460`
- prototype: `__int64 __fastcall(CBackstackManager *__hidden this, struct IObjectArray **, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000b7e8`
- `0x180011884`
- `0x180014e60`
- `0x1800150c0`
- `0x180036bc8`
- `0x180038108`
- `0x18003c5e4`
- `0x1800424d4`
- `0x180042a60`
- `0x180042df0`
- `0x1800433b0`
- `0x180044adc`
- `0x18013d330`
- `0x180192214`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004318c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18004318c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042f38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800430c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800431e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043350`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042f38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800430c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800431e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043228`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043350`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180042e80`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180042e80`

## pseudocode

```c
__int64 __fastcall CBackstackManager::GetBackstack(IUnknown **this, struct IObjectArray **a2, __int64 a3)
{
  unsigned __int64 v5; // r14
  __int64 v6; // r8
  IUnknown *v7; // rcx
  int v8; // r15d
  int Instance; // ebx
  int v10; // eax
  unsigned int v11; // edi
  char *v12; // rcx
  unsigned __int64 i; // rbx
  unsigned int v15; // esi
  __int64 v16; // rdi
  int (__fastcall *v17)(__int64, _QWORD, GUID *, struct IImmersiveApplication **); // rbx
  const struct _GUID *v18; // r8
  unsigned __int64 v19; // rcx
  FILETIME *v20; // rdx
  unsigned int v21; // edx
  void *v22; // rcx
  void **v23; // rax
  const struct _GUID *v24; // rdx
  int v25; // ecx
  unsigned __int64 v26; // r13
  unsigned __int64 v27; // r12
  __int64 v28; // rsi
  int (__fastcall *v29)(__int64, GUID *, __int64 *); // rbx
  __int64 v30; // rdi
  int (__fastcall *v31)(__int64, LPVOID *); // rbx
  __int64 v32; // r9
  __int64 v33; // rcx
  struct IImmersiveApplication *v34; // rcx
  __int64 v35; // rcx
  char *v36; // rcx
  unsigned __int64 j; // rdi
  void *v38; // rcx
  int v39; // [rsp+20h] [rbp-79h]
  __int64 v40; // [rsp+30h] [rbp-69h] BYREF
  FILETIME FileTime1; // [rsp+38h] [rbp-61h] BYREF
  __int64 v42; // [rsp+40h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-51h] BYREF
  unsigned __int64 v44; // [rsp+50h] [rbp-49h]
  LPVOID v45; // [rsp+58h] [rbp-41h] BYREF
  __int64 v46; // [rsp+60h] [rbp-39h]
  char v47[8]; // [rsp+68h] [rbp-31h] BYREF
  LPVOID v48; // [rsp+70h] [rbp-29h] BYREF
  void *ppvOut; // [rsp+78h] [rbp-21h] BYREF
  int v50; // [rsp+80h] [rbp-19h]
  IUnknown **v51; // [rsp+88h] [rbp-11h]
  struct IImmersiveApplication *v52[2]; // [rsp+90h] [rbp-9h] BYREF
  struct IObjectArray **v53; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v50 = a3;
  v53 = a2;
  v51 = this;
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_TWINUI_PUBLISHER_Context,
      BackstackManager_GetBackstack_Start,
      a3,
      1,
      v52);
  v5 = 0;
  *a2 = 0;
  ppvOut = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvOut);
  IUnknown_QueryService(*(this - 9), &IID_IProjectionManager, &GUID_d9cd01a5_a926_412d_a6cd_c3b51c2a9bc8, &ppvOut);
  pv = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v42 = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v42);
  v7 = this[5];
  v42 = 0;
  if ( v7 )
  {
    v8 = 0;
    Instance = ((__int64 (__fastcall *)(IUnknown *, __int64 *))v7->lpVtbl[1].QueryInterface)(v7, &v42);
    if ( Instance >= 0 )
    {
      LODWORD(v40) = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 24LL))(v42, &v40);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC0,
          (unsigned int)"shell\\twinui\\backstackmanager\\lib\\backstackmanager.cpp",
          (const char *)(unsigned int)v10,
          v39);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v42);
        v12 = (char *)pv;
        if ( pv )
        {
          for ( i = 0; i < v44; ++i )
          {
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v12[8 * i]);
            v12 = (char *)pv;
          }
          CoTaskMemFree(v12);
          pv = 0;
        }
        v44 = 0;
        v46 = 0;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvOut);
        return v11;
      }
      v15 = 0;
      if ( (_DWORD)v40 )
      {
        while ( 1 )
        {
          v16 = v42;
          v52[0] = 0;
          v17 = *(int (__fastcall **)(__int64, _QWORD, GUID *, struct IImmersiveApplication **))(*(_QWORD *)v42 + 32LL);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(v52);
          if ( v17(v16, v15, &GUID_8b14e88b_5663_4caf_b196_c31479262831, v52) >= 0 )
            break;
LABEL_25:
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(v52);
          if ( ++v15 >= (unsigned int)v40 )
            goto LABEL_28;
        }
        LODWORD(v48) = 0;
        if ( ppvOut )
          (*(void (__fastcall **)(void *, struct IImmersiveApplication *, LPVOID *))(*(_QWORD *)ppvOut + 48LL))(
            ppvOut,
            v52[0],
            &v48);
        FileTime1 = 0;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&FileTime1);
        if ( (int)CBackstackApp::CreateInstance(v52[0], (_DWORD)v48 != 0, v18, (void **)&FileTime1) < 0 )
        {
LABEL_24:
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&FileTime1);
          goto LABEL_25;
        }
        v19 = v44;
        if ( v44 == v46 )
        {
          if ( (int)CTSimpleArray<IGestureClient *,4294967294,CTPolicyCoTaskMem<IGestureClient *>,CSimpleArrayStandardCompareHelper<IGestureClient *>,CSimpleArrayStandardMergeHelper<IGestureClient *>>::_EnsureCapacity(
                      &pv,
                      v44 + 1) < 0 )
          {
LABEL_22:
            if ( (_DWORD)v48 )
              ++v8;
            goto LABEL_24;
          }
          v19 = v44;
        }
        v44 = v19 + 1;
        v20 = (FILETIME *)((char *)pv + 8 * v19);
        if ( v20 )
        {
          *v20 = FileTime1;
          if ( FileTime1 )
            (*(void (__fastcall **)(FILETIME))(**(_QWORD **)&FileTime1 + 8LL))(FileTime1);
        }
        goto LABEL_22;
      }
    }
    if ( Instance >= 0 )
    {
LABEL_28:
      if ( v44 > 1 )
      {
        v45 = 0;
        v52[0] = 0;
        if ( (int)ULongLongMult(v44 >> 1, 8u, (unsigned __int64 *)v52) >= 0
          && CTCoAllocPolicy::Realloc(v22, v21, 0, (unsigned __int64)v52[0], &v45) >= 0 )
        {
          CTSimpleArray<Microsoft::WRL::ComPtr<IBackstackApp>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IBackstackApp>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IBackstackApp>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IBackstackApp>>>::_MergeSort<CBackstackAppSort>(
            &pv,
            v47,
            0,
            v44);
          CoTaskMemFree(v45);
          v45 = 0;
        }
      }
      v52[0] = 0;
      v23 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(v52);
      Instance = CEnumerableObjectCollection::CreateInstance(v25, v24, v23);
      if ( Instance >= 0 )
      {
        v26 = v44;
        v27 = 0;
        if ( v44 )
        {
          do
          {
            v28 = *((_QWORD *)pv + v5);
            if ( v28 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v28 + 8LL))(*((_QWORD *)pv + v5));
            FileTime1 = 0;
            (*(void (__fastcall **)(__int64, FILETIME *))(*(_QWORD *)v28 + 24LL))(v28, &FileTime1);
            v40 = 0;
            v29 = *(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v28 + 32LL);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v40);
            if ( v29(v28, &GUID_8b14e88b_5663_4caf_b196_c31479262831, &v40) >= 0
              && ((*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v28 + 48LL))(v28)
               || v27 < (unsigned int)-v8 && CompareFileTime(&FileTime1, &BackstackHelpers::s_FILETIME_MIN))
              && (*(int (__fastcall **)(struct IImmersiveApplication *, __int64))(*(_QWORD *)v52[0] + 40LL))(
                   v52[0],
                   v40) >= 0 )
            {
              ++v27;
              if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v28 + 48LL))(v28) )
                --v8;
              if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
              {
                v48 = 0;
                v30 = v40;
                v31 = *(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v40 + 32LL);
                CoTaskMemFree(0);
                if ( v31(v30, &v48) >= 0 && (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
                  McTemplateU0z_EventWriteTransfer(
                    &MICROSOFT_TWINUI_PUBLISHER_Context,
                    BackstackManager_GetBackstack_Info,
                    v48);
                CoTaskMemFree(v48);
              }
            }
            else if ( v50 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 40LL))(v28);
              if ( v40 )
              {
                LOBYTE(v32) = FileTime1.dwLowDateTime + ((unsigned __int64)FileTime1.dwHighDateTime << 32) != 0;
                CBackstackManager::_CleanupAppStateOnRemoval(v51 - 11, v40, 2, v32);
              }
            }
            v33 = v40;
            if ( v40 )
            {
              v40 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            ++v5;
          }
          while ( v5 < v26 );
        }
        Instance = (**(__int64 (__fastcall ***)(struct IImmersiveApplication *, GUID *, struct IObjectArray **))v52[0])(
                     v52[0],
                     &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
                     v53);
      }
      v34 = v52[0];
      if ( v52[0] )
      {
        v52[0] = 0;
        (*(void (__fastcall **)(struct IImmersiveApplication *))(*(_QWORD *)v34 + 16LL))(v34);
      }
    }
  }
  else
  {
    Instance = -2147019873;
  }
  if ( (Microsoft_Windows_Immersive_ShellEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_TWINUI_PUBLISHER_Context,
      BackstackManager_GetBackstack_Stop,
      v6,
      1,
      &v53);
  v35 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = (char *)pv;
  if ( pv )
  {
    for ( j = 0; j < v44; ++j )
    {
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v36[8 * j]);
      v36 = (char *)pv;
    }
    CoTaskMemFree(v36);
    pv = 0;
  }
  v38 = ppvOut;
  v44 = 0;
  v46 = 0;
  if ( ppvOut )
  {
    ppvOut = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v38 + 16LL))(v38);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180042df0  mov     [rsp-8+arg_10], rbx
0x180042df5  push    rbp
0x180042df6  push    rsi
0x180042df7  push    rdi
0x180042df8  push    r12
0x180042dfa  push    r13
0x180042dfc  push    r14
0x180042dfe  push    r15
0x180042e00  lea     rbp, [rsp-27h]
0x180042e05  sub     rsp, 0C0h
0x180042e0c  mov     rax, cs:__security_cookie
0x180042e13  xor     rax, rsp
0x180042e16  mov     [rbp+57h+var_40], rax
0x180042e1a  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x180042e21  mov     rdi, rdx
0x180042e24  mov     [rbp+57h+var_70], r8d
0x180042e28  mov     rbx, rcx
0x180042e2b  mov     [rbp+57h+var_50], rdx
0x180042e2f  mov     [rbp+57h+var_68], rcx
0x180042e33  jz      short loc_180042E57
0x180042e35  lea     rax, [rbp+57h+var_60]
0x180042e39  mov     r9d, 1
0x180042e3f  lea     rdx, BackstackManager_GetBackstack_Start
0x180042e46  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x180042e4b  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x180042e52  call    McGenEventWrite_EventWriteTransfer
0x180042e57  xor     r14d, r14d
0x180042e5a  lea     rcx, [rbp+57h+ppvOut]
0x180042e5e  mov     [rdi], r14
0x180042e61  mov     [rbp+57h+ppvOut], r14
0x180042e65  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180042e6a  mov     rcx, [rbx-48h]; punk
0x180042e6e  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x180042e72  lea     r8, _GUID_d9cd01a5_a926_412d_a6cd_c3b51c2a9bc8; riid
0x180042e79  lea     rdx, IID_IProjectionManager; guidService
0x180042e80  call    cs:__imp_IUnknown_QueryService
0x180042e86  lea     rcx, [rbp+57h+var_B0]
0x180042e8a  mov     [rbp+57h+pv], r14
0x180042e8e  mov     [rbp+57h+var_A0], r14
0x180042e92  mov     [rbp+57h+var_98], r14
0x180042e96  mov     [rbp+57h+var_90], r14
0x180042e9a  mov     [rbp+57h+var_B0], r14
0x180042e9e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180042ea3  mov     rcx, [rbx+28h]
0x180042ea7  mov     [rbp+57h+var_B0], r14
0x180042eab  test    rcx, rcx
0x180042eae  jz      loc_1800432DF
0x180042eb4  mov     rax, [rcx]
0x180042eb7  lea     rdx, [rbp+57h+var_B0]
0x180042ebb  mov     r15d, r14d
0x180042ebe  mov     rax, [rax+18h]
0x180042ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ec7  mov     ebx, eax
0x180042ec9  test    eax, eax
0x180042ecb  js      loc_180043060
0x180042ed1  mov     rcx, [rbp+57h+var_B0]
0x180042ed5  lea     rdx, [rbp+57h+var_C0]
0x180042ed9  mov     dword ptr [rbp+57h+var_C0], r14d
0x180042edd  mov     rax, [rcx]
0x180042ee0  mov     rax, [rax+18h]
0x180042ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ee9  mov     edi, eax
0x180042eeb  test    eax, eax
0x180042eed  jns     short loc_180042F5A
0x180042eef  mov     rcx, [rbp+5Fh]; this
0x180042ef3  lea     r8, aShellTwinuiBac; "shell\\twinui\\backstackmanager\\lib\\b"...
0x180042efa  mov     r9d, eax; char *
0x180042efd  mov     edx, 0C0h; void *
0x180042f02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042f07  lea     rcx, [rbp+57h+var_B0]
0x180042f0b  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180042f10  mov     rcx, [rbp+57h+pv]
0x180042f14  test    rcx, rcx
0x180042f17  jz      short loc_180042F42
0x180042f19  mov     ebx, r14d
0x180042f1c  cmp     [rbp+57h+var_A0], r14
0x180042f20  jbe     short loc_180042F38
0x180042f22  lea     rcx, [rcx+rbx*8]
0x180042f26  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180042f2b  mov     rcx, [rbp+57h+pv]; pv
0x180042f2f  inc     rbx
0x180042f32  cmp     rbx, [rbp+57h+var_A0]
0x180042f36  jb      short loc_180042F22
0x180042f38  call    cs:__imp_CoTaskMemFree
0x180042f3e  mov     [rbp+57h+pv], r14
0x180042f42  lea     rcx, [rbp+57h+ppvOut]
0x180042f46  mov     [rbp+57h+var_A0], r14
0x180042f4a  mov     [rbp+57h+var_90], r14
0x180042f4e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180042f53  mov     eax, edi
0x180042f55  jmp     loc_18004337D
0x180042f5a  mov     esi, r14d
0x180042f5d  cmp     dword ptr [rbp+57h+var_C0], r14d
0x180042f61  jbe     loc_180043060
0x180042f67  mov     rdi, [rbp+57h+var_B0]
0x180042f6b  lea     rcx, [rbp+57h+var_60]
0x180042f6f  mov     [rbp+57h+var_60], r14
0x180042f73  mov     rax, [rdi]
0x180042f76  mov     rbx, [rax+20h]
0x180042f7a  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180042f7f  lea     r9, [rbp+57h+var_60]
0x180042f83  mov     edx, esi
0x180042f85  lea     r8, _GUID_8b14e88b_5663_4caf_b196_c31479262831
0x180042f8c  mov     rcx, rdi
0x180042f8f  mov     rax, rbx
0x180042f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f97  test    eax, eax
0x180042f99  js      loc_18004304A
0x180042f9f  mov     rcx, [rbp+57h+ppvOut]
0x180042fa3  mov     dword ptr [rbp+57h+var_80], r14d
0x180042fa7  test    rcx, rcx
0x180042faa  jz      short loc_180042FC0
0x180042fac  mov     rax, [rcx]
0x180042faf  lea     r8, [rbp+57h+var_80]
0x180042fb3  mov     rdx, [rbp+57h+var_60]
0x180042fb7  mov     rax, [rax+30h]
0x180042fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042fc0  lea     rcx, [rbp+57h+FileTime1]
0x180042fc4  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], r14
0x180042fc8  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180042fcd  cmp     dword ptr [rbp+57h+var_80], r14d
0x180042fd1  lea     r9, [rbp+57h+FileTime1]; void **
0x180042fd5  mov     rcx, [rbp+57h+var_60]; struct IImmersiveApplication *
0x180042fd9  setnz   dl; bool
0x180042fdc  call    ?CreateInstance@CBackstackApp@@SAJPEAUIImmersiveApplication@@_NAEBU_GUID@@PEAPEAX@Z; CBackstackApp::CreateInstance(IImmersiveApplication *,bool,_GUID const &,void * *)
0x180042fe1  test    eax, eax
0x180042fe3  js      short loc_180043041
0x180042fe5  mov     rcx, [rbp+57h+var_A0]
0x180042fe9  cmp     rcx, [rbp+57h+var_90]
0x180042fed  jnz     short loc_180043004
0x180042fef  lea     rdx, [rcx+1]
0x180042ff3  lea     rcx, [rbp+57h+pv]
0x180042ff7  call    ?_EnsureCapacity@?$CTSimpleArray@PEAUIGestureClient@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@PEAUIGestureClient@@@@V?$CSimpleArrayStandardCompareHelper@PEAUIGestureClient@@@@V?$CSimpleArrayStandardMergeHelper@PEAUIGestureClient@@@@@@QEAAJ_K0@Z; CTSimpleArray<IGestureClient *,4294967294,CTPolicyCoTaskMem<IGestureClient *>,CSimpleArrayStandardCompareHelper<IGestureClient *>,CSimpleArrayStandardMergeHelper<IGestureClient *>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180042ffc  test    eax, eax
0x180042ffe  js      short loc_180043038
0x180043000  mov     rcx, [rbp+57h+var_A0]
0x180043004  mov     rdx, [rbp+57h+pv]
0x180043008  inc     rcx
0x18004300b  add     rdx, 0FFFFFFFFFFFFFFF8h
0x18004300f  mov     [rbp+57h+var_A0], rcx
0x180043013  lea     rdx, [rdx+rcx*8]
0x180043017  test    rdx, rdx
0x18004301a  jz      short loc_180043038
0x18004301c  mov     rax, qword ptr [rbp+57h+FileTime1.dwLowDateTime]
0x180043020  mov     [rdx], rax
0x180043023  mov     rcx, qword ptr [rbp+57h+FileTime1.dwLowDateTime]
0x180043027  test    rcx, rcx
0x18004302a  jz      short loc_180043038
0x18004302c  mov     rax, [rcx]
0x18004302f  mov     rax, [rax+8]
0x180043033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043038  cmp     dword ptr [rbp+57h+var_80], r14d
0x18004303c  jz      short loc_180043041
0x18004303e  inc     r15d
0x180043041  lea     rcx, [rbp+57h+FileTime1]
0x180043045  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18004304a  lea     rcx, [rbp+57h+var_60]
0x18004304e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180043053  inc     esi
0x180043055  cmp     esi, dword ptr [rbp+57h+var_C0]
0x180043058  jb      loc_180042F67
0x18004305e  jmp     short loc_180043068
0x180043060  test    ebx, ebx
0x180043062  js      loc_1800432E4
0x180043068  mov     rcx, [rbp+57h+var_A0]
0x18004306c  cmp     rcx, 1
0x180043070  jbe     short loc_1800430CA
0x180043072  shr     rcx, 1; unsigned __int64
0x180043075  lea     r8, [rbp+57h+var_60]; unsigned __int64 *
0x180043079  mov     edx, 8; unsigned __int64
0x18004307e  mov     [rbp+57h+var_98], r14
0x180043082  mov     [rbp+57h+var_60], r14
0x180043086  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004308b  test    eax, eax
0x18004308d  js      short loc_1800430CA
0x18004308f  mov     r9, [rbp+57h+var_60]; unsigned __int64
0x180043093  lea     rax, [rbp+57h+var_98]
0x180043097  xor     r8d, r8d; void *
0x18004309a  mov     qword ptr [rsp+0F0h+var_D0], rax; void **
0x18004309f  call    ?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z; CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)
0x1800430a4  test    eax, eax
0x1800430a6  js      short loc_1800430CA
0x1800430a8  mov     r9, [rbp+57h+var_A0]
0x1800430ac  lea     rdx, [rbp+57h+var_88]
0x1800430b0  xor     r8d, r8d
0x1800430b3  lea     rcx, [rbp+57h+pv]
0x1800430b7  call    ??$_MergeSort@VCBackstackAppSort@@@?$CTSimpleArray@V?$ComPtr@UIBackstackApp@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$ComPtr@UIBackstackApp@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@UIBackstackApp@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@UIBackstackApp@@@WRL@Microsoft@@@@@@QEAAXAEBVCBackstackAppSort@@_K1@Z; CTSimpleArray<Microsoft::WRL::ComPtr<IBackstackApp>,4294967294,CTPolicyCoTaskMem<Microsoft::WRL::ComPtr<IBackstackApp>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<IBackstackApp>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<IBackstackApp>>>::_MergeSort<CBackstackAppSort>(CBackstackAppSort const &,unsigned __int64,unsigned __int64)
0x1800430bc  mov     rcx, [rbp+57h+var_98]; pv
0x1800430c0  call    cs:__imp_CoTaskMemFree
0x1800430c6  mov     [rbp+57h+var_98], r14
0x1800430ca  lea     rcx, [rbp+57h+var_60]
0x1800430ce  mov     [rbp+57h+var_60], r14
0x1800430d2  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IImmersiveMonitor>>)
0x1800430d7  mov     r8, rax; void **
0x1800430da  call    ?CreateInstance@CEnumerableObjectCollection@@SAJHAEBU_GUID@@PEAPEAX@Z; CEnumerableObjectCollection::CreateInstance(int,_GUID const &,void * *)
0x1800430df  mov     ebx, eax
0x1800430e1  test    eax, eax
0x1800430e3  js      loc_1800432C4
0x1800430e9  mov     r13, [rbp+57h+var_A0]
0x1800430ed  xor     edi, edi
0x1800430ef  mov     r12, r14
0x1800430f2  test    r13, r13
0x1800430f5  jz      loc_1800432A5
0x1800430fb  mov     rax, [rbp+57h+pv]
0x1800430ff  mov     rsi, [rax+r14*8]
0x180043103  test    rsi, rsi
0x180043106  jz      short loc_180043117
0x180043108  mov     rax, [rsi]
0x18004310b  mov     rcx, rsi
0x18004310e  mov     rax, [rax+8]
0x180043112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043117  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], rdi
0x18004311b  lea     rdx, [rbp+57h+FileTime1]
0x18004311f  mov     rax, [rsi]
0x180043122  mov     rcx, rsi
0x180043125  mov     rax, [rax+18h]
0x180043129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004312e  mov     [rbp+57h+var_C0], rdi
0x180043132  lea     rcx, [rbp+57h+var_C0]
0x180043136  mov     rax, [rsi]
0x180043139  mov     rbx, [rax+20h]
0x18004313d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180043142  lea     r8, [rbp+57h+var_C0]
0x180043146  mov     rcx, rsi
0x180043149  lea     rdx, _GUID_8b14e88b_5663_4caf_b196_c31479262831
0x180043150  mov     rax, rbx
0x180043153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043158  test    eax, eax
0x18004315a  js      loc_180043230
0x180043160  mov     rax, [rsi]
0x180043163  mov     rcx, rsi
0x180043166  mov     rax, [rax+30h]
0x18004316a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004316f  test    al, al
0x180043171  jnz     short loc_18004319A
0x180043173  mov     eax, r15d
0x180043176  neg     eax
0x180043178  cmp     r12, rax
0x18004317b  jnb     loc_180043230
0x180043181  lea     rdx, ?s_FILETIME_MIN@BackstackHelpers@@3U_FILETIME@@B; lpFileTime2
0x180043188  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x18004318c  call    cs:__imp_CompareFileTime
0x180043192  test    eax, eax
0x180043194  jz      loc_180043230
0x18004319a  mov     rcx, [rbp+57h+var_60]
0x18004319e  mov     rdx, [rbp+57h+var_C0]
0x1800431a2  mov     rax, [rcx]
0x1800431a5  mov     rax, [rax+28h]
0x1800431a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431ae  test    eax, eax
0x1800431b0  js      short loc_180043230
0x1800431b2  mov     rax, [rsi]
0x1800431b5  mov     rcx, rsi
0x1800431b8  inc     r12
0x1800431bb  mov     rax, [rax+30h]
0x1800431bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431c4  test    al, al
0x1800431c6  jz      short loc_1800431CB
0x1800431c8  dec     r15d
0x1800431cb  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x1800431d2  jz      loc_180043271
0x1800431d8  mov     [rbp+57h+var_80], rdi
0x1800431dc  xor     ecx, ecx; pv
0x1800431de  mov     rdi, [rbp+57h+var_C0]
0x1800431e2  mov     rax, [rdi]
0x1800431e5  mov     rbx, [rax+20h]
0x1800431e9  call    cs:__imp_CoTaskMemFree
0x1800431ef  lea     rdx, [rbp+57h+var_80]
0x1800431f3  mov     rcx, rdi
0x1800431f6  mov     rax, rbx
0x1800431f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431fe  xor     edi, edi
0x180043200  test    eax, eax
0x180043202  js      short loc_180043224
0x180043204  test    byte ptr cs:Microsoft_Windows_Immersive_ShellEnableBits, 8
0x18004320b  jz      short loc_180043224
0x18004320d  mov     r8, [rbp+57h+var_80]
0x180043211  lea     rdx, BackstackManager_GetBackstack_Info
0x180043218  lea     rcx, MICROSOFT_TWINUI_PUBLISHER_Context
0x18004321f  call    McTemplateU0z_EventWriteTransfer
0x180043224  mov     rcx, [rbp+57h+var_80]; pv
0x180043228  call    cs:__imp_CoTaskMemFree
0x18004322e  jmp     short loc_180043271
0x180043230  cmp     [rbp+57h+var_70], edi
0x180043233  jz      short loc_180043271
0x180043235  mov     rax, [rsi]
0x180043238  mov     rcx, rsi
0x18004323b  mov     rax, [rax+28h]
0x18004323f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043244  mov     rdx, [rbp+57h+var_C0]
0x180043248  test    rdx, rdx
0x18004324b  jz      short loc_180043271
0x18004324d  mov     ecx, [rbp+57h+FileTime1.dwHighDateTime]
0x180043250  mov     r8d, 2
0x180043256  mov     eax, [rbp+57h+FileTime1.dwLowDateTime]
0x180043259  shl     rcx, 20h
0x18004325d  add     rcx, rax
0x180043260  mov     rcx, [rbp+57h+var_68]
0x180043264  setnz   r9b
0x180043268  add     rcx, 0FFFFFFFFFFFFFFA8h
  ... truncated ...
```
