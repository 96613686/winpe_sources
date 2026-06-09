# CDDisplayManager::Initialize(void)

- ea: `0x18005f4f0`
- end: `0x18005f66a`
- name: `?Initialize@CDDisplayManager@@AEAAJXZ`
- size: `378`
- prototype: `__int64 __fastcall(CDDisplayManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18007056c`

## callees

- `0x1800029dc`
- `0x18001f43c`
- `0x18005f4f0`
- `0x180095130`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005f58a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005f58a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f62a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f62a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005f545`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005f545`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDDisplayManager::Initialize(CDDisplayManager *this)
{
  HRESULT v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int v6; // ebx
  __int64 v7; // rax
  int ActivationFactory; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, char *); // rsi
  __int64 v11; // rcx
  int v12; // eax
  __int64 v14; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF

  v14 = 0;
  string = 0;
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  v2 = WindowsCreateStringReference(L"Windows.Devices.Display.Core.DisplayManager", 0x2Bu, &hstringHeader, &string);
  v6 = v2;
  if ( v2 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v2, 0x24u, 0);
  }
  else
  {
    v14 = 0;
    v7 = winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(
           &v14,
           v3,
           v4,
           v5);
    ActivationFactory = RoGetActivationFactory(string, &GUID_2b6b9446_b999_5535_9d69_53f092c780a1, v7);
    v6 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, ActivationFactory, 0x25u, 0);
    }
    else
    {
      v9 = v14;
      v10 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v14 + 48LL);
      v11 = *((_QWORD *)this + 2);
      *((_QWORD *)this + 2) = 0;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      v12 = v10(v9, 2, (char *)this + 16);
      v6 = v12;
      if ( v12 < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v12, 0x28u, 0);
    }
  }
  if ( string )
    WindowsDeleteString(string);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return v6;
}

```

## disassembly

```asm
0x18005f4f0  mov     [rsp-18h+arg_8], rbx
0x18005f4f5  mov     [rsp-18h+arg_10], rsi
0x18005f4fa  push    rbp
0x18005f4fb  push    rdi
0x18005f4fc  push    r14
0x18005f4fe  mov     rbp, rsp
0x18005f501  sub     rsp, 60h
0x18005f505  mov     rax, cs:__security_cookie
0x18005f50c  xor     rax, rsp
0x18005f50f  mov     [rbp+var_8], rax
0x18005f513  mov     r14, rcx
0x18005f516  mov     [rbp+var_30], 0
0x18005f51e  mov     [rbp+string], 0
0x18005f526  xorps   xmm0, xmm0
0x18005f529  xor     eax, eax
0x18005f52b  movups  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x18005f52f  mov     qword ptr [rbp+hstringHeader.Reserved+10h], rax
0x18005f533  lea     r9, [rbp+string]; string
0x18005f537  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18005f53b  lea     edx, [rax+2Bh]; length
0x18005f53e  lea     rcx, ?RuntimeClass_Windows_Devices_Display_Core_DisplayManager@@3QBGB; "Windows.Devices.Display.Core.DisplayMan"...
0x18005f545  call    cs:__imp_WindowsCreateStringReference
0x18005f54b  mov     ebx, eax
0x18005f54d  test    eax, eax
0x18005f54f  js      loc_18005F600
0x18005f555  mov     rcx, [rbp+var_30]
0x18005f559  mov     [rbp+var_30], 0
0x18005f561  test    rcx, rcx
0x18005f564  jz      short loc_18005F573
0x18005f566  mov     rax, [rcx]
0x18005f569  mov     rax, [rax+10h]
0x18005f56d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f572  nop
0x18005f573  lea     rcx, [rbp+var_30]
0x18005f577  call    ??$to_abi@UITransitionAnimationVisualNative@@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@@winrt@@YAPEAUITransitionAnimationVisualNative@@PEBU?$producer_convert@UTopLevelWindow3DWrapper@implementation@Transitions@Udwm@winrt@@UITransitionAnimationVisualNative@@X@impl@0@@Z; winrt::to_abi<ITransitionAnimationVisualNative,winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper>(winrt::impl::producer_convert<winrt::Udwm::Transitions::implementation::TopLevelWindow3DWrapper,ITransitionAnimationVisualNative,void> const *)
0x18005f57c  mov     r8, rax
0x18005f57f  lea     rdx, _GUID_2b6b9446_b999_5535_9d69_53f092c780a1
0x18005f586  mov     rcx, [rbp+string]
0x18005f58a  call    cs:__imp_RoGetActivationFactory
0x18005f590  mov     ebx, eax
0x18005f592  test    eax, eax
0x18005f594  js      short loc_18005F5ED
0x18005f596  mov     rdi, [rbp+var_30]
0x18005f59a  mov     rax, [rdi]
0x18005f59d  mov     rsi, [rax+30h]
0x18005f5a1  lea     rbx, [r14+10h]
0x18005f5a5  mov     rcx, [rbx]
0x18005f5a8  mov     qword ptr [rbx], 0
0x18005f5af  test    rcx, rcx
0x18005f5b2  jz      short loc_18005F5C1
0x18005f5b4  mov     rdx, [rcx]
0x18005f5b7  mov     rax, [rdx+10h]
0x18005f5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f5c0  nop
0x18005f5c1  mov     r8, rbx
0x18005f5c4  mov     edx, 2
0x18005f5c9  mov     rcx, rdi
0x18005f5cc  mov     rax, rsi
0x18005f5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f5d4  mov     ebx, eax
0x18005f5d6  test    eax, eax
0x18005f5d8  jns     short loc_18005F621
0x18005f5da  mov     [rsp+60h+var_38], 0
0x18005f5e3  mov     [rsp+60h+var_40], 28h ; '('
0x18005f5eb  jmp     short loc_18005F611
0x18005f5ed  mov     [rsp+60h+var_38], 0
0x18005f5f6  mov     [rsp+60h+var_40], 25h ; '%'
0x18005f5fe  jmp     short loc_18005F611
0x18005f600  mov     [rsp+60h+var_38], 0; void *
0x18005f609  mov     [rsp+60h+var_40], 24h ; '$'; unsigned int
0x18005f611  mov     r9d, eax; int
0x18005f614  xor     r8d, r8d; unsigned int
0x18005f617  xor     edx, edx; int *
0x18005f619  lea     ecx, [rdx+14h]; unsigned int
0x18005f61c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18005f621  mov     rcx, [rbp+string]; string
0x18005f625  test    rcx, rcx
0x18005f628  jz      short loc_18005F631
0x18005f62a  call    cs:__imp_WindowsDeleteString
0x18005f630  nop
0x18005f631  mov     rcx, [rbp+var_30]
0x18005f635  test    rcx, rcx
0x18005f638  jz      short loc_18005F647
0x18005f63a  mov     rax, [rcx]
0x18005f63d  mov     rax, [rax+10h]
0x18005f641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f646  nop
0x18005f647  mov     eax, ebx
0x18005f649  mov     rcx, [rbp+var_8]
0x18005f64d  xor     rcx, rsp; StackCookie
0x18005f650  call    __security_check_cookie
0x18005f655  lea     r11, [rsp+60h+var_s0]
0x18005f65a  mov     rbx, [r11+28h]
0x18005f65e  mov     rsi, [r11+30h]
0x18005f662  mov     rsp, r11
0x18005f665  pop     r14
0x18005f667  pop     rdi
0x18005f668  pop     rbp
0x18005f669  retn
```
