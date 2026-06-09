# Windows::Internal::CloudNotifications::HomeCloudHandler::VerifyConsumerWebAccount(winrt::Windows::Security::Credentials::IWebAccount)

- ea: `0x18006786c`
- end: `0x180067975`
- name: `?VerifyConsumerWebAccount@HomeCloudHandler@CloudNotifications@Internal@Windows@@AEAA_NUIWebAccount@Credentials@Security@4winrt@@@Z`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180061d10`

## callees

- `0x1800034f7`
- `0x1800035ab`
- `0x18000e4a4`
- `0x18000ed24`
- `0x180013f6c`
- `0x1800142a4`
- `0x180014364`
- `0x18006786c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180067956`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180067956`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800678f1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800678f1`

## string_xrefs

- `0x180067963`: `onecoreuap\shell\clouddirect\serviceimplementations\afs\src\homecloudhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall Windows::Internal::CloudNotifications::HomeCloudHandler::VerifyConsumerWebAccount(
        __int64 a1,
        _QWORD *a2)
{
  volatile signed __int32 *v3; // rbx
  const WCHAR *v4; // rcx
  bool v5; // bp
  int v6; // esi
  HANDLE ProcessHeap; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF
  _QWORD *v12; // [rsp+58h] [rbp+10h]
  LPVOID lpMem; // [rsp+60h] [rbp+18h] BYREF

  v12 = a2;
  v11 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(a2, &v11) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF3,
      (unsigned int)"onecoreuap\\shell\\clouddirect\\serviceimplementations\\afs\\src\\homecloudhandler.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
  winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(
    a2,
    &v11);
  winrt::impl::consume_Windows_Security_Credentials_IWebAccountProvider2<winrt::Windows::Security::Credentials::WebAccountProvider>::Authority(
    &v11,
    &lpMem);
  v3 = (volatile signed __int32 *)lpMem;
  if ( lpMem )
    v4 = (const WCHAR *)*((_QWORD *)lpMem + 2);
  else
    v4 = &Name;
  v5 = CompareStringOrdinal(v4, -1, L"consumers", -1, 1) == 2;
  if ( v3 )
  {
    v6 = _InterlockedDecrement(v3 + 6);
    if ( v6 )
    {
      if ( v6 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v3);
    }
  }
  if ( v11 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  if ( *a2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
  return v5;
}

```

## disassembly

```asm
0x18006786c  mov     rax, rsp
0x18006786f  mov     [rax+20h], rbx
0x180067873  mov     [rax+10h], rdx
0x180067877  mov     [rax+8], rcx
0x18006787b  push    rbp
0x18006787c  push    rsi
0x18006787d  push    rdi
0x18006787e  sub     rsp, 30h
0x180067882  mov     rdi, rdx
0x180067885  mov     qword ptr [rax+8], 0
0x18006788d  lea     rdx, [rax+8]
0x180067891  mov     rcx, rdi
0x180067894  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180067899  mov     rcx, [rsp+48h]; this
0x18006789e  test    al, al
0x1800678a0  jnz     loc_18006795D
0x1800678a6  lea     rdx, [rsp+48h+arg_0]
0x1800678ab  mov     rcx, rdi
0x1800678ae  call    ?ClientId@?$consume_Windows_Internal_CloudRequestor_IEnvironmentConfig@UIEnvironmentConfig@CloudRequestor@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_CloudRequestor_IEnvironmentConfig<winrt::Windows::Internal::CloudRequestor::IEnvironmentConfig>::ClientId(void)
0x1800678b3  nop
0x1800678b4  lea     rdx, [rsp+48h+lpMem]
0x1800678b9  lea     rcx, [rsp+48h+arg_0]
0x1800678be  call    ?Authority@?$consume_Windows_Security_Credentials_IWebAccountProvider2@UWebAccountProvider@Credentials@Security@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Security_Credentials_IWebAccountProvider2<winrt::Windows::Security::Credentials::WebAccountProvider>::Authority(void)
0x1800678c3  mov     rbx, [rsp+48h+lpMem]
0x1800678c8  test    rbx, rbx
0x1800678cb  jz      short loc_1800678D3
0x1800678cd  mov     rcx, [rbx+10h]
0x1800678d1  jmp     short loc_1800678DA
0x1800678d3  lea     rcx, Name; lpString1
0x1800678da  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x1800678e2  or      esi, 0FFFFFFFFh
0x1800678e5  mov     r9d, esi; cchCount2
0x1800678e8  lea     r8, aConsumers; "consumers"
0x1800678ef  mov     edx, esi; cchCount1
0x1800678f1  call    cs:__imp_CompareStringOrdinal
0x1800678f7  cmp     eax, 2
0x1800678fa  setz    bpl
0x1800678fe  test    rbx, rbx
0x180067901  jz      short loc_180067921
0x180067903  lock xadd [rbx+18h], esi
0x180067908  sub     esi, 1
0x18006790b  jnz     short loc_180067952
0x18006790d  nop
0x18006790e  call    WINRT_IMPL_GetProcessHeap
0x180067913  mov     rcx, rax; hHeap
0x180067916  mov     r8, rbx; lpMem
0x180067919  xor     edx, edx; dwFlags
0x18006791b  call    WINRT_IMPL_HeapFree
0x180067920  nop
0x180067921  cmp     [rsp+48h+arg_0], 0
0x180067927  jz      short loc_180067934
0x180067929  lea     rcx, [rsp+48h+arg_0]
0x18006792e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180067933  nop
0x180067934  cmp     qword ptr [rdi], 0
0x180067938  jz      short loc_180067942
0x18006793a  mov     rcx, rdi
0x18006793d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180067942  mov     al, bpl
0x180067945  mov     rbx, [rsp+48h+arg_18]
0x18006794a  add     rsp, 30h
0x18006794e  pop     rdi
0x18006794f  pop     rsi
0x180067950  pop     rbp
0x180067951  retn
0x180067952  test    esi, esi
0x180067954  jns     short loc_180067921
0x180067956  call    cs:__imp_abort
0x18006795d  mov     r9d, 80070057h; char *
0x180067963  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\clouddirect\\service"...
0x18006796a  mov     edx, 0F3h; void *
0x18006796f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
