# CTask::CTask(HWND__ * const,_GUID const *,tagXW_WIZARD_TYPE,IPXWizardPropertyBag *,IMultiObjectElevationFactory * *)

- ea: `0x18001f6f8`
- end: `0x18001fe35`
- name: `??0CTask@@QEAA@QEAUHWND__@@PEBU_GUID@@W4tagXW_WIZARD_TYPE@@PEAUIPXWizardPropertyBag@@PEAPEAUIMultiObjectElevationFactory@@@Z`
- size: `1853`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001e180`

## callees

- `0x180004370`
- `0x18000ae04`
- `0x180010b0c`
- `0x18001f6f8`
- `0x180024c90`
- `0x180025f50`
- `0x180029eb4`
- `0x18002f9c8`
- `0x18003174c`
- `0x180032a02`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f906`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f964`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001fadd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001fbbb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f906`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f964`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001fadd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001fbbb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f8a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f8a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CTask::CTask(
        __int64 a1,
        unsigned __int16 *a2,
        const struct _GUID *a3,
        int a4,
        __int64 a5,
        struct CUnknown *a6)
{
  _DWORD *v10; // rbp
  _QWORD *v11; // r12
  int *v12; // r15
  HANDLE ProcessHeap; // rax
  int Instance; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  int v17; // edx
  __int64 v18; // r9
  struct CUnknown *v19; // rbx
  int v20; // eax
  _QWORD *v21; // rbx
  LPVOID *v22; // r8

  *(_QWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 320) = 0;
  *(_QWORD *)(a1 + 328) = 0;
  *(_QWORD *)(a1 + 336) = 0;
  *(_QWORD *)(a1 + 344) = 0;
  *(_QWORD *)(a1 + 352) = 0;
  *(_QWORD *)(a1 + 360) = 0;
  *(_QWORD *)(a1 + 368) = 0;
  *(_QWORD *)(a1 + 376) = 0;
  CPXWizardSemaphoreLock::CPXWizardSemaphoreLock((CPXWizardSemaphoreLock *)(a1 + 976), a2, a3, a4);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = a2;
  v10 = (_DWORD *)(a1 + 32);
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  *(_QWORD *)(a1 + 256) = 0;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = 0;
  v11 = (_QWORD *)(a1 + 304);
  *(_QWORD *)(a1 + 304) = 0;
  *(_QWORD *)(a1 + 1016) = 0;
  *(_QWORD *)(a1 + 1024) = 0;
  *(_DWORD *)(a1 + 416) = 0;
  *(_QWORD *)(a1 + 424) = 0;
  *(_QWORD *)(a1 + 408) = 0;
  *(_DWORD *)(a1 + 432) = 0;
  *(_QWORD *)(a1 + 440) = 0;
  *(_QWORD *)(a1 + 968) = 0;
  *(_DWORD *)(a1 + 220) = a4;
  *(_QWORD *)(a1 + 1032) = 0;
  *(_DWORD *)(a1 + 240) = 0;
  *(_DWORD *)(a1 + 112) = 0;
  v12 = (int *)(a1 + 116);
  *(_DWORD *)(a1 + 116) = 0;
  *(_DWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 1040) = 0;
  *(_QWORD *)(a1 + 1048) = 0;
  *(_QWORD *)(a1 + 1056) = a6;
  *(_OWORD *)(a1 + 224) = 0;
  *(_OWORD *)(a1 + 124) = 0;
  *(_OWORD *)(a1 + 140) = 0;
  *(_OWORD *)(a1 + 156) = 0;
  *(_OWORD *)(a1 + 172) = 0;
  *(_OWORD *)(a1 + 188) = 0;
  *(_OWORD *)(a1 + 204) = 0;
  memset_0((void *)(a1 + 40), 0, 0x48u);
  *(struct _GUID *)(a1 + 16) = *a3;
  *(_DWORD *)(a1 + 40) = 72;
  *(_QWORD *)(a1 + 48) = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 56) = a1 + 16;
  *(_DWORD *)(a1 + 64) = *(_DWORD *)(a1 + 220);
  ProcessHeap = GetProcessHeap();
  *(_QWORD *)(a1 + 400) = ProcessHeap;
  if ( ProcessHeap )
  {
    Instance = CoCreateInstance(
                 &CLSID_CPXWizardRegistryInfo,
                 0,
                 0x401u,
                 &IID_IPXWizardRegistryInfo,
                 (LPVOID *)(a1 + 304));
    *(_DWORD *)a1 = Instance;
    if ( Instance < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v16 = 13;
        goto LABEL_82;
      }
      return a1;
    }
    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(*(_QWORD *)*v11 + 88LL))(
                 *v11,
                 *(unsigned int *)(a1 + 220),
                 a1 + 224,
                 0);
    *(_DWORD *)a1 = Instance;
    if ( Instance < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v16 = 12;
        goto LABEL_82;
      }
      return a1;
    }
    Instance = CoCreateInstance((const IID *const)(a1 + 224), 0, 0x401u, &IID_IPXWizardTypeEvent, (LPVOID *)(a1 + 288));
    *(_DWORD *)a1 = Instance;
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(*(_QWORD *)*v11 + 72LL))(
                   *v11,
                   a1 + 16,
                   a1 + 32,
                   a1 + 116);
      *(_DWORD *)a1 = Instance;
      if ( Instance >= 0 )
      {
        v17 = *v12;
        if ( (*v12 & 0x2000) != 0 )
          _InterlockedAdd((volatile signed __int32 *)(a1 + 1052), 1u);
        if ( (*v12 & 0x200) != 0 )
          _InterlockedAdd((volatile signed __int32 *)(a1 + 1048), 1u);
        if ( *v10 == 2 )
        {
          if ( (v17 & 0x1000) != 0 || (v17 & 0x100) != 0 )
          {
            if ( (v17 & 0x1000) != 0 )
              v22 = *(LPVOID **)(a1 + 1056);
            else
              v22 = 0;
            Instance = CPXWizardTaskProxy::HrCreateInstance(
                         *(HWND *)(a1 + 8),
                         (struct _GUID *)(a1 + 16),
                         v22,
                         *(struct IPXWizardTypeEvent **)(a1 + 288),
                         (struct IXWizardTaskEvent **)(a1 + 256));
          }
          else
          {
            Instance = CoCreateInstance(
                         (const IID *const)(a1 + 16),
                         0,
                         0x401u,
                         &IID_IXWizardTaskEvent,
                         (LPVOID *)(a1 + 256));
          }
          *(_DWORD *)a1 = Instance;
          if ( Instance < 0 )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v16 = 17;
              goto LABEL_82;
            }
            return a1;
          }
        }
        else
        {
          if ( *v10 != 3 )
          {
            *(_DWORD *)a1 = -2147024809;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v16 = 18;
              v18 = 2147942487LL;
LABEL_83:
              WPP_SF_d(v15[2], v16, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, v18);
              return a1;
            }
            return a1;
          }
          *v12 &= ~0x20u;
          a6 = 0;
          Instance = CWTask::CreateComponentInstance((const struct _GUID *)(a1 + 16), 0, &a6);
          *(_DWORD *)a1 = Instance;
          if ( Instance < 0 )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v16 = 16;
              goto LABEL_82;
            }
            return a1;
          }
          v19 = a6;
          v20 = (**(__int64 (__fastcall ***)(struct CUnknown *, GUID *, __int64))a6)(
                  a6,
                  &IID_IXWizardTaskEvent,
                  a1 + 256);
          *(_DWORD *)a1 = v20;
          if ( v20 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                15,
                &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
                (unsigned int)v20);
            if ( v19 )
              (*(void (__fastcall **)(struct CUnknown *, __int64))(*(_QWORD *)v19 + 24LL))(v19, 1);
            return a1;
          }
          (*(void (__fastcall **)(struct CUnknown *))(*(_QWORD *)v19 + 16LL))(v19);
        }
        v21 = (_QWORD *)(a1 + 248);
        Instance = CoCreateInstance(&CLSID_CXWizard, 0, 0x401u, &IID_IXWizard, (LPVOID *)(a1 + 248));
        *(_DWORD *)a1 = Instance;
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v21 + 216LL))(
                       *v21,
                       1,
                       *(_QWORD *)(a1 + 8));
          *(_DWORD *)a1 = Instance;
          if ( Instance >= 0 )
          {
            Instance = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v21 + 216LL))(
                         *v21,
                         301,
                         **(_QWORD **)(a1 + 1056));
            *(_DWORD *)a1 = Instance;
            if ( Instance >= 0 )
            {
              Instance = CPXWizardTypeSource::HrCreateInstance(
                           (const struct CTask *)a1,
                           (struct IPXWizardTypeSource **)(a1 + 296));
              *(_DWORD *)a1 = Instance;
              if ( Instance >= 0 )
              {
                if ( a5 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)a5 + 8LL))(a5);
                  *(_QWORD *)(a1 + 272) = a5;
                  Instance = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a5 + 64LL))(a5, a1 + 16);
                }
                else
                {
                  Instance = CPXWizardPropertyBag::HrCreateInstance(
                               (const struct _GUID *)(a1 + 16),
                               (struct IPXWizardPropertyBag **)(a1 + 272));
                }
                *(_DWORD *)a1 = Instance;
                if ( Instance >= 0 )
                {
                  Instance = CXWizardSource::HrCreateInstance(
                               (const struct CTask *)a1,
                               0,
                               (const struct _GUID *)(a1 + 16),
                               (struct IXWizardSource **)(a1 + 280));
                  *(_DWORD *)a1 = Instance;
                  if ( Instance >= 0 )
                  {
                    v15 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      v16 = 25;
                      goto LABEL_82;
                    }
                  }
                  else
                  {
                    v15 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    {
                      v16 = 24;
                      goto LABEL_82;
                    }
                  }
                }
                else
                {
                  v15 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  {
                    v16 = 23;
                    goto LABEL_82;
                  }
                }
              }
              else
              {
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                {
                  v16 = 22;
                  goto LABEL_82;
                }
              }
            }
            else
            {
              v15 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                v16 = 21;
                goto LABEL_82;
              }
            }
          }
          else
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v16 = 20;
              goto LABEL_82;
            }
          }
        }
        else
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v16 = 19;
            goto LABEL_82;
          }
        }
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v16 = 14;
          goto LABEL_82;
        }
      }
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v16 = 11;
        goto LABEL_82;
      }
    }
  }
  else
  {
    Instance = GetLastErrorHRESULT();
    *(_DWORD *)a1 = Instance;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v16 = 10;
LABEL_82:
      v18 = (unsigned int)Instance;
      goto LABEL_83;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18001f6f8  mov     [rsp+arg_0], rcx
0x18001f6fd  push    rbx
0x18001f6fe  push    rbp
0x18001f6ff  push    rsi
0x18001f700  push    rdi
0x18001f701  push    r12
0x18001f703  push    r13
0x18001f705  push    r14
0x18001f707  push    r15
0x18001f709  sub     rsp, 38h
0x18001f70d  mov     edi, r9d
0x18001f710  mov     rsi, r8
0x18001f713  mov     rbx, rdx
0x18001f716  mov     r14, rcx
0x18001f719  xor     r15d, r15d
0x18001f71c  mov     [rcx+138h], r15
0x18001f723  mov     [rcx+140h], r15
0x18001f72a  mov     [rcx+148h], r15
0x18001f731  mov     [rcx+150h], r15
0x18001f738  mov     [rcx+158h], r15
0x18001f73f  mov     [rcx+160h], r15
0x18001f746  mov     [rcx+168h], r15
0x18001f74d  mov     [rcx+170h], r15
0x18001f754  mov     [rcx+178h], r15
0x18001f75b  add     rcx, 3D0h; this
0x18001f762  call    ??0CPXWizardSemaphoreLock@@QEAA@QEAGPEBU_GUID@@H@Z; CPXWizardSemaphoreLock::CPXWizardSemaphoreLock(ushort * const,_GUID const *,int)
0x18001f767  nop
0x18001f768  mov     [r14], r15
0x18001f76b  mov     [r14+8], rbx
0x18001f76f  lea     rbp, [r14+20h]
0x18001f773  mov     [rbp+0], r15d
0x18001f777  mov     [r14+0F8h], r15
0x18001f77e  lea     r13, [r14+100h]
0x18001f785  mov     [r13+0], r15
0x18001f789  mov     [r14+108h], r15
0x18001f790  mov     [r14+110h], r15
0x18001f797  mov     [r14+118h], r15
0x18001f79e  mov     [r14+120h], r15
0x18001f7a5  mov     [r14+128h], r15
0x18001f7ac  lea     r12, [r14+130h]
0x18001f7b3  mov     [r12], r15
0x18001f7b7  mov     [r14+3F8h], r15
0x18001f7be  mov     [r14+400h], r15
0x18001f7c5  mov     [r14+1A0h], r15d
0x18001f7cc  mov     [r14+1A8h], r15
0x18001f7d3  mov     [r14+198h], r15
0x18001f7da  mov     [r14+1B0h], r15d
0x18001f7e1  mov     [r14+1B8h], r15
0x18001f7e8  mov     [r14+3C8h], r15
0x18001f7ef  mov     [r14+0DCh], edi
0x18001f7f6  mov     [r14+408h], r15
0x18001f7fd  mov     [r14+0F0h], r15d
0x18001f804  mov     [r14+70h], r15d
0x18001f808  lea     r15, [r14+74h]
0x18001f80c  xor     eax, eax
0x18001f80e  mov     [r15], eax
0x18001f811  mov     [r14+78h], eax
0x18001f815  mov     [r14+410h], rax
0x18001f81c  mov     [r14+418h], rax
0x18001f823  mov     rax, [rsp+78h+arg_28]
0x18001f82b  mov     [r14+420h], rax
0x18001f832  xorps   xmm0, xmm0
0x18001f835  movups  xmmword ptr [r14+0E0h], xmm0
0x18001f83d  movups  xmmword ptr [r14+7Ch], xmm0
0x18001f842  xorps   xmm1, xmm1
0x18001f845  movups  xmmword ptr [r14+8Ch], xmm1
0x18001f84d  movups  xmmword ptr [r14+9Ch], xmm0
0x18001f855  movups  xmmword ptr [r14+0ACh], xmm1
0x18001f85d  movups  xmmword ptr [r14+0BCh], xmm0
0x18001f865  movups  xmmword ptr [r14+0CCh], xmm1
0x18001f86d  xor     edx, edx; Val
0x18001f86f  lea     r8d, [rdx+48h]; Size
0x18001f873  lea     rcx, [r14+28h]; void *
0x18001f877  call    memset_0
0x18001f87c  lea     rdi, [r14+10h]
0x18001f880  movups  xmm0, xmmword ptr [rsi]
0x18001f883  movdqu  xmmword ptr [rdi], xmm0
0x18001f887  mov     dword ptr [r14+28h], 48h ; 'H'
0x18001f88f  mov     rax, [r14+8]
0x18001f893  mov     [r14+30h], rax
0x18001f897  mov     [r14+38h], rdi
0x18001f89b  mov     eax, [r14+0DCh]
0x18001f8a2  mov     [r14+40h], eax
0x18001f8a6  call    cs:__imp_GetProcessHeap
0x18001f8ac  mov     [r14+190h], rax
0x18001f8b3  test    rax, rax
0x18001f8b6  jnz     short loc_18001F8EB
0x18001f8b8  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001f8bd  mov     [r14], eax
0x18001f8c0  lea     rdx, WPP_GLOBAL_Control
0x18001f8c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8ce  cmp     rcx, rdx
0x18001f8d1  jz      loc_18001FE21
0x18001f8d7  test    byte ptr [rcx+1Ch], 4
0x18001f8db  jz      loc_18001FE21
0x18001f8e1  mov     edx, 0Ah
0x18001f8e6  jmp     loc_18001FE0D
0x18001f8eb  mov     [rsp+78h+ppv], r12; ppv
0x18001f8f0  lea     r9, IID_IPXWizardRegistryInfo; riid
0x18001f8f7  xor     edx, edx; pUnkOuter
0x18001f8f9  mov     r8d, 401h; dwClsContext
0x18001f8ff  lea     rcx, CLSID_CPXWizardRegistryInfo; rclsid
0x18001f906  call    cs:__imp_CoCreateInstance
0x18001f90c  mov     [r14], eax
0x18001f90f  test    eax, eax
0x18001f911  js      loc_18001FDEF
0x18001f917  mov     rcx, [r12]
0x18001f91b  mov     rax, [rcx]
0x18001f91e  xor     r9d, r9d
0x18001f921  lea     rbx, [r14+0E0h]
0x18001f928  mov     r8, rbx
0x18001f92b  mov     edx, [r14+0DCh]
0x18001f932  mov     rax, [rax+58h]
0x18001f936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f93b  mov     [r14], eax
0x18001f93e  test    eax, eax
0x18001f940  js      loc_18001FDCF
0x18001f946  lea     rsi, [r14+120h]
0x18001f94d  mov     [rsp+78h+ppv], rsi; ppv
0x18001f952  lea     r9, IID_IPXWizardTypeEvent; riid
0x18001f959  xor     edx, edx; pUnkOuter
0x18001f95b  mov     r8d, 401h; dwClsContext
0x18001f961  mov     rcx, rbx; rclsid
0x18001f964  call    cs:__imp_CoCreateInstance
0x18001f96a  mov     [r14], eax
0x18001f96d  test    eax, eax
0x18001f96f  jns     short loc_18001F99C
0x18001f971  lea     rdx, WPP_GLOBAL_Control
0x18001f978  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f97f  cmp     rcx, rdx
0x18001f982  jz      loc_18001FE21
0x18001f988  test    byte ptr [rcx+1Ch], 4
0x18001f98c  jz      loc_18001FE21
0x18001f992  mov     edx, 0Bh
0x18001f997  jmp     loc_18001FE0D
0x18001f99c  mov     rcx, [r12]
0x18001f9a0  mov     rax, [rcx]
0x18001f9a3  mov     r9, r15
0x18001f9a6  mov     r8, rbp
0x18001f9a9  mov     rdx, rdi
0x18001f9ac  mov     rax, [rax+48h]
0x18001f9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9b5  mov     [r14], eax
0x18001f9b8  test    eax, eax
0x18001f9ba  jns     short loc_18001F9E7
0x18001f9bc  lea     rdx, WPP_GLOBAL_Control
0x18001f9c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9ca  cmp     rcx, rdx
0x18001f9cd  jz      loc_18001FE21
0x18001f9d3  test    byte ptr [rcx+1Ch], 4
0x18001f9d7  jz      loc_18001FE21
0x18001f9dd  mov     edx, 0Eh
0x18001f9e2  jmp     loc_18001FE0D
0x18001f9e7  mov     edx, [r15]
0x18001f9ea  mov     r12d, 1
0x18001f9f0  bt      edx, 0Dh
0x18001f9f4  jnb     short loc_18001F9FE
0x18001f9f6  lock add [r14+41Ch], r12d
0x18001f9fe  test    dword ptr [r15], 200h
0x18001fa05  jz      short loc_18001FA0F
0x18001fa07  lock add [r14+418h], r12d
0x18001fa0f  mov     ecx, [rbp+0]
0x18001fa12  sub     ecx, 2
0x18001fa15  jz      loc_18001FB95
0x18001fa1b  cmp     ecx, r12d
0x18001fa1e  jz      short loc_18001FA58
0x18001fa20  mov     dword ptr [r14], 80070057h
0x18001fa27  lea     rdx, WPP_GLOBAL_Control
0x18001fa2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa35  cmp     rcx, rdx
0x18001fa38  jz      loc_18001FE21
0x18001fa3e  test    byte ptr [rcx+1Ch], 4
0x18001fa42  jz      loc_18001FE21
0x18001fa48  mov     edx, 12h
0x18001fa4d  mov     r9d, 80070057h
0x18001fa53  jmp     loc_18001FE10
0x18001fa58  and     dword ptr [r15], 0FFFFFFDFh
0x18001fa5c  mov     [rsp+78h+arg_28], 0
0x18001fa68  lea     r8, [rsp+78h+arg_28]; struct CUnknown **
0x18001fa70  xor     edx, edx; struct IUnknown *
0x18001fa72  mov     rcx, rdi; struct _GUID *
0x18001fa75  call    ?CreateComponentInstance@CWTask@@SAJPEBU_GUID@@PEAUIUnknown@@PEAPEAVCUnknown@@@Z; CWTask::CreateComponentInstance(_GUID const *,IUnknown *,CUnknown * *)
0x18001fa7a  mov     [r14], eax
0x18001fa7d  test    eax, eax
0x18001fa7f  js      loc_18001FB6A
0x18001fa85  mov     rbx, [rsp+78h+arg_28]
0x18001fa8d  mov     rax, [rbx]
0x18001fa90  mov     r8, r13
0x18001fa93  lea     rdx, IID_IXWizardTaskEvent
0x18001fa9a  mov     rcx, rbx
0x18001fa9d  mov     rax, [rax]
0x18001faa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001faa5  mov     [r14], eax
0x18001faa8  test    eax, eax
0x18001faaa  js      short loc_18001FB19
0x18001faac  mov     rax, [rbx]
0x18001faaf  mov     rcx, rbx
0x18001fab2  mov     rax, [rax+10h]
0x18001fab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fabb  lea     rbx, [r14+0F8h]
0x18001fac2  mov     [rsp+78h+ppv], rbx; ppv
0x18001fac7  lea     r9, IID_IXWizard; riid
0x18001face  xor     edx, edx; pUnkOuter
0x18001fad0  mov     r8d, 401h; dwClsContext
0x18001fad6  lea     rcx, CLSID_CXWizard; rclsid
0x18001fadd  call    cs:__imp_CoCreateInstance
0x18001fae3  mov     [r14], eax
0x18001fae6  test    eax, eax
0x18001fae8  jns     loc_18001FC1D
0x18001faee  lea     rdx, WPP_GLOBAL_Control
0x18001faf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fafc  cmp     rcx, rdx
0x18001faff  jz      loc_18001FE21
0x18001fb05  test    byte ptr [rcx+1Ch], 4
0x18001fb09  jz      loc_18001FE21
0x18001fb0f  mov     edx, 13h
0x18001fb14  jmp     loc_18001FE0D
0x18001fb19  lea     rdx, WPP_GLOBAL_Control
0x18001fb20  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb27  cmp     rcx, rdx
0x18001fb2a  jz      short loc_18001FB4A
0x18001fb2c  test    byte ptr [rcx+1Ch], 4
0x18001fb30  jz      short loc_18001FB4A
0x18001fb32  mov     edx, 0Fh
0x18001fb37  mov     r9d, eax
0x18001fb3a  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x18001fb41  mov     rcx, [rcx+10h]
0x18001fb45  call    WPP_SF_d
0x18001fb4a  test    rbx, rbx
0x18001fb4d  jz      loc_18001FE21
0x18001fb53  mov     rax, [rbx]
0x18001fb56  mov     edx, r12d
0x18001fb59  mov     rcx, rbx
0x18001fb5c  mov     rax, [rax+18h]
0x18001fb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb65  jmp     loc_18001FE21
0x18001fb6a  lea     rdx, WPP_GLOBAL_Control
0x18001fb71  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb78  cmp     rcx, rdx
0x18001fb7b  jz      loc_18001FE21
0x18001fb81  test    byte ptr [rcx+1Ch], 4
0x18001fb85  jz      loc_18001FE21
0x18001fb8b  mov     edx, 10h
0x18001fb90  jmp     loc_18001FE0D
0x18001fb95  mov     eax, edx
0x18001fb97  and     eax, 1000h
0x18001fb9c  jnz     short loc_18001FBC3
0x18001fb9e  bt      edx, 8
0x18001fba2  jb      short loc_18001FBC3
0x18001fba4  mov     [rsp+78h+ppv], r13; ppv
0x18001fba9  lea     r9, IID_IXWizardTaskEvent; riid
0x18001fbb0  xor     edx, edx; pUnkOuter
0x18001fbb2  mov     r8d, 401h; dwClsContext
0x18001fbb8  mov     rcx, rdi; rclsid
0x18001fbbb  call    cs:__imp_CoCreateInstance
0x18001fbc1  jmp     short loc_18001FBE7
0x18001fbc3  test    eax, eax
0x18001fbc5  jz      short loc_18001FBD0
0x18001fbc7  mov     r8, [r14+420h]
0x18001fbce  jmp     short loc_18001FBD3
0x18001fbd0  xor     r8d, r8d; struct IMultiObjectElevationFactory **
0x18001fbd3  mov     [rsp+78h+ppv], r13; struct IXWizardTaskEvent **
0x18001fbd8  mov     r9, [rsi]; struct IPXWizardTypeEvent *
0x18001fbdb  mov     rdx, rdi; struct _GUID *
0x18001fbde  mov     rcx, [r14+8]; HWND
0x18001fbe2  call    ?HrCreateInstance@CPXWizardTaskProxy@@SAJPEAUHWND__@@PEAU_GUID@@PEAPEAUIMultiObjectElevationFactory@@PEAUIPXWizardTypeEvent@@PEAPEAUIXWizardTaskEvent@@@Z; CPXWizardTaskProxy::HrCreateInstance(HWND__ *,_GUID *,IMultiObjectElevationFactory * *,IPXWizardTypeEvent *,IXWizardTaskEvent * *)
0x18001fbe7  mov     [r14], eax
0x18001fbea  test    eax, eax
0x18001fbec  jns     loc_18001FABB
0x18001fbf2  lea     rdx, WPP_GLOBAL_Control
0x18001fbf9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc00  cmp     rcx, rdx
0x18001fc03  jz      loc_18001FE21
0x18001fc09  test    byte ptr [rcx+1Ch], 4
0x18001fc0d  jz      loc_18001FE21
0x18001fc13  mov     edx, 11h
0x18001fc18  jmp     loc_18001FE0D
0x18001fc1d  mov     rcx, [rbx]
0x18001fc20  mov     rax, [rcx]
0x18001fc23  mov     r8, [r14+8]
0x18001fc27  mov     edx, r12d
0x18001fc2a  mov     rax, [rax+0D8h]
0x18001fc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc36  mov     [r14], eax
0x18001fc39  test    eax, eax
0x18001fc3b  jns     short loc_18001FC68
0x18001fc3d  lea     rdx, WPP_GLOBAL_Control
0x18001fc44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc4b  cmp     rcx, rdx
0x18001fc4e  jz      loc_18001FE21
0x18001fc54  test    byte ptr [rcx+1Ch], 4
0x18001fc58  jz      loc_18001FE21
0x18001fc5e  mov     edx, 14h
0x18001fc63  jmp     loc_18001FE0D
0x18001fc68  mov     rcx, [rbx]
0x18001fc6b  mov     rax, [rcx]
0x18001fc6e  mov     r8, [r14+420h]
0x18001fc75  mov     r8, [r8]
0x18001fc78  mov     edx, 12Dh
0x18001fc7d  mov     rax, [rax+0D8h]
  ... truncated ...
```
