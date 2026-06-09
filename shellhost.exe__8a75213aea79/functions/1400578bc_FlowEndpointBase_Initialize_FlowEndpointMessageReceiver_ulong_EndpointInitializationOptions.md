# FlowEndpointBase::Initialize(FlowEndpointMessageReceiver *,ulong,EndpointInitializationOptions)

- ea: `0x1400578bc`
- end: `0x14005799f`
- name: `?Initialize@FlowEndpointBase@@QEAAXPEAVFlowEndpointMessageReceiver@@KW4EndpointInitializationOptions@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000acdc`
- `0x14005bd30`

## callees

- `0x14004eb14`
- `0x140052bf8`
- `0x140054fec`
- `0x1400578bc`
- `0x14005d1a8`
- `0x14005fcbc`
- `0x14005fcdc`

## import_xrefs

- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x14005790b`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x14005790b`

## string_xrefs

- `0x14005797b`: `shellcommon\internal\shell\inc\ValueSetChannel.h`
- `0x14005798d`: `shellcommon\internal\shell\inc\ValueSetChannel.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FlowEndpointBase::Initialize(__int64 a1, HWND a2)
{
  int v3; // eax
  __int64 *v4; // rdi
  __int64 *v5; // rbx
  __int64 v6; // rcx
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  char v10; // [rsp+48h] [rbp+10h] BYREF

  *(_QWORD *)(a1 + 80) = a2;
  *(_DWORD *)(a1 + 88) = -1;
  CImpWorkerWndProc::CreateWorkerWindow((CImpWorkerWndProc *)a1, a2);
  if ( !*(_QWORD *)(a1 + 8) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\ValueSetChannel.h",
      *(_QWORD *)(a1 + 8) == 0 ? (const char *)0x8007000ELL : 0,
      v7);
  v9 = 0;
  v3 = RoCreatePropertySetSerializer(&v9);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\ValueSetChannel.h",
      (const char *)(unsigned int)v3,
      v7);
  v4 = (__int64 *)winrt::com_ptr<Windows::Storage::Streams::IPropertySetSerializer>::as<winrt::Windows::Storage::Streams::IPropertySetSerializer>(
                    &v9,
                    &v10);
  v5 = (__int64 *)(a1 + 72);
  if ( v5 != v4 )
  {
    if ( *v5 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v5);
    v6 = *v4;
    *v4 = 0;
    *v5 = v6;
  }
  winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass((winrt::Windows::Foundation::IUriRuntimeClass *)&v10);
  if ( v9 )
    winrt::com_ptr<IUnknown>::unconditional_release_ref(&v9);
}

```

## disassembly

```asm
0x1400578bc  mov     [rsp+arg_10], rbx
0x1400578c1  push    rdi
0x1400578c2  sub     rsp, 30h
0x1400578c6  mov     rbx, rcx
0x1400578c9  mov     [rcx+50h], rdx
0x1400578cd  mov     dword ptr [rcx+58h], 0FFFFFFFFh
0x1400578d4  call    ?CreateWorkerWindow@CImpWorkerWndProc@@IEAAPEAUHWND__@@PEAU2@KKPEAUHMENU__@@@Z; CImpWorkerWndProc::CreateWorkerWindow(HWND__ *,ulong,ulong,HMENU__ *)
0x1400578d9  mov     rax, [rbx+8]
0x1400578dd  neg     rax
0x1400578e0  sbb     r9d, r9d
0x1400578e3  not     r9d
0x1400578e6  and     r9d, 8007000Eh; char *
0x1400578ed  mov     rcx, [rsp+38h]; this
0x1400578f2  cmp     qword ptr [rbx+8], 0
0x1400578f7  jz      loc_14005798D
0x1400578fd  mov     [rsp+38h+arg_0], 0
0x140057906  lea     rcx, [rsp+38h+arg_0]
0x14005790b  call    cs:__imp_RoCreatePropertySetSerializer
0x140057911  mov     rcx, [rsp+38h]; this
0x140057916  test    eax, eax
0x140057918  js      short loc_140057978
0x14005791a  lea     rdx, [rsp+38h+arg_8]
0x14005791f  lea     rcx, [rsp+38h+arg_0]
0x140057924  call    ??$as@UIPropertySetSerializer@Streams@Storage@Windows@winrt@@@?$com_ptr@UIPropertySetSerializer@Streams@Storage@Windows@@@winrt@@QEBA?A_PXZ
0x140057929  mov     rdi, rax
0x14005792c  add     rbx, 48h ; 'H'
0x140057930  cmp     rbx, rax
0x140057933  jz      short loc_140057950
0x140057935  cmp     qword ptr [rbx], 0
0x140057939  jz      short loc_140057943
0x14005793b  mov     rcx, rbx
0x14005793e  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x140057943  mov     rcx, [rdi]
0x140057946  mov     qword ptr [rdi], 0
0x14005794d  mov     [rbx], rcx
0x140057950  lea     rcx, [rsp+38h+arg_8]; this
0x140057955  call    ??1IUriRuntimeClass@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IUriRuntimeClass::~IUriRuntimeClass(void)
0x14005795a  nop
0x14005795b  cmp     [rsp+38h+arg_0], 0
0x140057961  jz      short loc_14005796D
0x140057963  lea     rcx, [rsp+38h+arg_0]
0x140057968  call    ?unconditional_release_ref@?$com_ptr@UIUnknown@@@winrt@@AEAAXXZ; winrt::com_ptr<IUnknown>::unconditional_release_ref(void)
0x14005796d  mov     rbx, [rsp+38h+arg_10]
0x140057972  add     rsp, 30h
0x140057976  pop     rdi
0x140057977  retn
0x140057978  mov     r9d, eax; char *
0x14005797b  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\Valu"...
0x140057982  mov     edx, 5Ch ; '\'; void *
0x140057987  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14005798d  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\Valu"...
0x140057994  mov     edx, 59h ; 'Y'; void *
0x140057999  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
