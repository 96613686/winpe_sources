# NetworkingTriageScenario::OnDemand::OnDemandRequestRemoveHttpRouteAction(NetworkingTriageScenario::OnDemand::RequiredFields const &,ushort const *,bool,long)

- ea: `0x18000e8a8`
- end: `0x18000e99d`
- name: `?OnDemandRequestRemoveHttpRouteAction@OnDemand@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBG_NJ@Z`
- size: `245`
- prototype: `void __fastcall(const struct NetworkingTriageScenario::OnDemand::RequiredFields *, const unsigned __int16 *, bool, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800133d0`

## callees

- `0x1800057b4`
- `0x180005b34`
- `0x180005dcc`
- `0x180006408`
- `0x1800065d4`
- `0x18000e8a8`

## pseudocode

```c
void __fastcall NetworkingTriageScenario::OnDemand::OnDemandRequestRemoveHttpRouteAction(
        const struct NetworkingTriageScenario::OnDemand::RequiredFields *a1,
        const unsigned __int16 *a2,
        unsigned __int8 a3,
        int a4)
{
  int v5; // r14d
  _DWORD *v8; // rdi
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // [rsp+60h] [rbp-58h] BYREF
  int v14; // [rsp+64h] [rbp-54h] BYREF
  __int64 v15; // [rsp+68h] [rbp-50h] BYREF
  __int64 *v16; // [rsp+70h] [rbp-48h] BYREF
  __int64 v17; // [rsp+78h] [rbp-40h] BYREF
  const unsigned __int16 *v18; // [rsp+80h] [rbp-38h] BYREF
  const char *v19; // [rsp+88h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v5 = a3;
  v8 = *(_DWORD **)(wil::details::static_lazy<NetworkingTriageScenario::OnDemand>::get() + 8);
  if ( *v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL) )
  {
    v15 = 2048;
    v13 = a4;
    v14 = v5;
    v16 = (__int64 *)a2;
    v17 = (__int64)a1 + 8;
    try
    {
      v18 = (const unsigned __int16 *)NetworkingTriageScenario::OnDemand::EnumToString();
      v19 = NetworkingTriageScenario::EnumToString(*(_DWORD *)a1);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (__int64)v8,
        (unsigned __int8 *)byte_1800251D7,
        v9,
        v10,
        (const unsigned __int16 **)&v19,
        &v18,
        &v17,
        &v16,
        (__int64)&v14,
        (__int64)&v13,
        (__int64)&v15);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0xA7A, v11, v12);
    }
  }
}

```

## disassembly

```asm
0x18000e8a8  push    rbx
0x18000e8aa  push    rsi
0x18000e8ab  push    rdi
0x18000e8ac  push    r14
0x18000e8ae  push    r15
0x18000e8b0  sub     rsp, 90h
0x18000e8b7  mov     esi, r9d
0x18000e8ba  movzx   r14d, r8b
0x18000e8be  mov     r15, rdx
0x18000e8c1  mov     rbx, rcx
0x18000e8c4  call    ?get@?$static_lazy@VOnDemand@NetworkingTriageScenario@@@details@wil@@QEAAPEAVOnDemand@NetworkingTriageScenario@@P6AXXZ@Z; wil::details::static_lazy<NetworkingTriageScenario::OnDemand>::get(void (*)(void))
0x18000e8c9  mov     rdi, [rax+8]
0x18000e8cd  mov     eax, [rdi]
0x18000e8cf  cmp     eax, 5
0x18000e8d2  jbe     loc_18000E98D
0x18000e8d8  mov     rdx, 400000000000h
0x18000e8e2  mov     rcx, rdi
0x18000e8e5  call    _tlgKeywordOn
0x18000e8ea  test    al, al
0x18000e8ec  jz      loc_18000E98D
0x18000e8f2  mov     [rsp+0B8h+var_50], 800h
0x18000e8fb  mov     [rsp+0B8h+var_58], esi
0x18000e8ff  mov     [rsp+0B8h+var_54], r14d
0x18000e904  mov     [rsp+0B8h+var_48], r15
0x18000e909  lea     rax, [rbx+8]
0x18000e90d  mov     [rsp+0B8h+var_40], rax
0x18000e912  mov     ecx, [rbx+4]
0x18000e915  call    ?EnumToString@OnDemand@NetworkingTriageScenario@@SAPEBDW4Type@12@@Z; NetworkingTriageScenario::OnDemand::EnumToString(NetworkingTriageScenario::OnDemand::Type)
0x18000e91a  mov     [rsp+0B8h+var_38], rax
0x18000e922  mov     ecx, [rbx]
0x18000e924  call    ?EnumToString@NetworkingTriageScenario@@YAPEBDW4EventSources@1@@Z; NetworkingTriageScenario::EnumToString(NetworkingTriageScenario::EventSources)
0x18000e929  mov     [rsp+0B8h+var_30], rax
0x18000e931  lea     rax, [rsp+0B8h+var_50]
0x18000e936  mov     [rsp+0B8h+var_68], rax
0x18000e93b  lea     rax, [rsp+0B8h+var_58]
0x18000e940  mov     [rsp+0B8h+var_70], rax
0x18000e945  lea     rax, [rsp+0B8h+var_54]
0x18000e94a  mov     [rsp+0B8h+var_78], rax
0x18000e94f  lea     rax, [rsp+0B8h+var_48]
0x18000e954  mov     [rsp+0B8h+var_80], rax
0x18000e959  lea     rax, [rsp+0B8h+var_40]
0x18000e95e  mov     [rsp+0B8h+var_88], rax
0x18000e963  lea     rax, [rsp+0B8h+var_38]
0x18000e96b  mov     [rsp+0B8h+var_90], rax
0x18000e970  lea     rax, [rsp+0B8h+var_30]
0x18000e978  mov     [rsp+0B8h+var_98], rax
0x18000e97d  lea     rdx, byte_1800251D7
0x18000e984  mov     rcx, rdi
0x18000e987  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U4@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@6AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18000e98c  nop
0x18000e98d  add     rsp, 90h
0x18000e994  pop     r15
0x18000e996  pop     r14
0x18000e998  pop     rdi
0x18000e999  pop     rsi
0x18000e99a  pop     rbx
0x18000e99b  retn
```
