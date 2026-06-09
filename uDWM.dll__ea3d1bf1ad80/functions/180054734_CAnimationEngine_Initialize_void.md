# CAnimationEngine::Initialize(void)

- ea: `0x180054734`
- end: `0x180054868`
- name: `?Initialize@CAnimationEngine@@QEAAJXZ`
- size: `308`
- prototype: `__int64 __fastcall(CAnimationEngine *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800afb50`

## callees

- `0x1800029dc`
- `0x18001f43c`
- `0x180054734`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054766`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054797`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800547c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054766`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054797`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800547c5`

## pseudocode

```c
__int64 __fastcall CAnimationEngine::Initialize(CAnimationEngine *this, __int64 a2)
{
  _QWORD *v2; // r14
  LPVOID *ppv; // rax
  _QWORD *v5; // rdi
  __int64 v6; // rdx
  HRESULT Instance; // ebx
  LPVOID *v8; // rax
  __int64 v9; // rdx
  LPVOID *v10; // rax
  unsigned int v11; // eax
  __int64 v12; // rcx

  v2 = (_QWORD *)((char *)this + 8);
  ppv = (LPVOID *)winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
                    (char *)this + 8,
                    a2);
  v5 = (_QWORD *)((char *)this + 16);
  Instance = CoCreateInstance(&CLSID_UIAnimationManager2, 0, 1u, &GUID_d8b6f7d4_4109_4d3f_acee_879926968cb1, ppv);
  if ( Instance < 0 )
  {
    v11 = 87;
  }
  else
  {
    v8 = (LPVOID *)winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
                     (char *)this + 16,
                     v6);
    Instance = CoCreateInstance(
                 &CLSID_UIAnimationTransitionLibrary2,
                 0,
                 1u,
                 &GUID_03cfae53_9580_4ee3_b363_2ece51b4af6a,
                 v8);
    if ( Instance < 0 )
    {
      v11 = 88;
    }
    else
    {
      v10 = (LPVOID *)winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
                        (char *)this + 24,
                        v9);
      Instance = CoCreateInstance(
                   &CLSID_UIAnimationTransitionFactory2,
                   0,
                   1u,
                   &GUID_937d4916_c1a6_42d5_88d8_30344d6efe31,
                   v10);
      if ( Instance >= 0 )
      {
        *((_BYTE *)this + 120) = 1;
        return (unsigned int)Instance;
      }
      v11 = 89;
    }
  }
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, Instance, v11, 0);
  if ( *v2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
    *v2 = 0;
  }
  if ( *v5 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 16LL))(*v5);
    *v5 = 0;
  }
  v12 = *((_QWORD *)this + 3);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *((_QWORD *)this + 3) = 0;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180054734  push    rbx
0x180054736  push    rsi
0x180054737  push    rdi
0x180054738  push    r14
0x18005473a  sub     rsp, 38h
0x18005473e  lea     r14, [rcx+8]
0x180054742  mov     rsi, rcx
0x180054745  mov     rcx, r14
0x180054748  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18005474d  xor     edx, edx; pUnkOuter
0x18005474f  mov     [rsp+58h+ppv], rax; ppv
0x180054754  lea     r9, _GUID_d8b6f7d4_4109_4d3f_acee_879926968cb1; riid
0x18005475b  lea     rcx, CLSID_UIAnimationManager2; rclsid
0x180054762  lea     r8d, [rdx+1]; dwClsContext
0x180054766  call    cs:__imp_CoCreateInstance
0x18005476c  lea     rdi, [rsi+10h]
0x180054770  mov     ebx, eax
0x180054772  test    eax, eax
0x180054774  js      short loc_1800547E8
0x180054776  mov     rcx, rdi
0x180054779  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18005477e  xor     edx, edx; pUnkOuter
0x180054780  mov     [rsp+58h+ppv], rax; ppv
0x180054785  lea     r9, _GUID_03cfae53_9580_4ee3_b363_2ece51b4af6a; riid
0x18005478c  lea     rcx, CLSID_UIAnimationTransitionLibrary2; rclsid
0x180054793  lea     r8d, [rdx+1]; dwClsContext
0x180054797  call    cs:__imp_CoCreateInstance
0x18005479d  mov     ebx, eax
0x18005479f  test    eax, eax
0x1800547a1  js      short loc_1800547E1
0x1800547a3  lea     rcx, [rsi+18h]
0x1800547a7  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x1800547ac  xor     edx, edx; pUnkOuter
0x1800547ae  mov     [rsp+58h+ppv], rax; ppv
0x1800547b3  lea     r9, _GUID_937d4916_c1a6_42d5_88d8_30344d6efe31; riid
0x1800547ba  lea     rcx, CLSID_UIAnimationTransitionFactory2; rclsid
0x1800547c1  lea     r8d, [rdx+1]; dwClsContext
0x1800547c5  call    cs:__imp_CoCreateInstance
0x1800547cb  mov     ebx, eax
0x1800547cd  test    eax, eax
0x1800547cf  js      short loc_1800547DA
0x1800547d1  mov     byte ptr [rsi+78h], 1
0x1800547d5  jmp     loc_18005485C
0x1800547da  mov     eax, 59h ; 'Y'
0x1800547df  jmp     short loc_1800547ED
0x1800547e1  mov     eax, 58h ; 'X'
0x1800547e6  jmp     short loc_1800547ED
0x1800547e8  mov     eax, 57h ; 'W'
0x1800547ed  xor     edx, edx; int *
0x1800547ef  xor     r10d, r10d
0x1800547f2  mov     [rsp+58h+var_30], r10; void *
0x1800547f7  xor     r8d, r8d; unsigned int
0x1800547fa  mov     r9d, ebx; int
0x1800547fd  mov     dword ptr [rsp+58h+ppv], eax; unsigned int
0x180054801  lea     ecx, [rdx+14h]; unsigned int
0x180054804  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180054809  mov     rcx, [r14]
0x18005480c  test    rcx, rcx
0x18005480f  jz      short loc_180054824
0x180054811  mov     rax, [rcx]
0x180054814  mov     rax, [rax+10h]
0x180054818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005481d  mov     qword ptr [r14], 0
0x180054824  mov     rcx, [rdi]
0x180054827  test    rcx, rcx
0x18005482a  jz      short loc_18005483F
0x18005482c  mov     rax, [rcx]
0x18005482f  mov     rax, [rax+10h]
0x180054833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054838  mov     qword ptr [rdi], 0
0x18005483f  mov     rcx, [rsi+18h]
0x180054843  test    rcx, rcx
0x180054846  jz      short loc_18005485C
0x180054848  mov     rax, [rcx]
0x18005484b  mov     rax, [rax+10h]
0x18005484f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054854  mov     qword ptr [rsi+18h], 0
0x18005485c  mov     eax, ebx
0x18005485e  add     rsp, 38h
0x180054862  pop     r14
0x180054864  pop     rdi
0x180054865  pop     rsi
0x180054866  pop     rbx
0x180054867  retn
```
