# CWerService::SnapHostOrGuestOneTrace(wchar_t const *,ulong *)

- ea: `0x180017f88`
- end: `0x1800181ef`
- name: `?SnapHostOrGuestOneTrace@CWerService@@AEAAJPEB_WPEAK@Z`
- size: `615`
- prototype: `int(CWerService *__hidden this, const wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180018c5c`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x180004a44`
- `0x180011ef8`
- `0x180016318`
- `0x180017f88`
- `0x18001bccc`
- `0x18002c12c`
- `0x18002c188`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180017fe9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180017fe9`
- `RPCRT4!RpcBindingFree` at `0x1800181aa`
- `RPCRT4!RpcBindingFree` at `0x1800181aa`
- `RPCRT4!RpcStringBindingComposeW` at `0x180018015`
- `RPCRT4!RpcStringBindingComposeW` at `0x180018015`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180018042`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180018042`
- `RPCRT4!RpcStringFreeW` at `0x180018057`
- `RPCRT4!RpcStringFreeW` at `0x180018057`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWerService::SnapHostOrGuestOneTrace(CWerService *this, const wchar_t *a2, unsigned int *a3)
{
  RPC_STATUS v5; // eax
  int v6; // edx
  const wchar_t *v7; // r8
  const wchar_t *v8; // r9
  int v9; // ebx
  RPC_STATUS v10; // eax
  const wchar_t *v11; // rdi
  __int64 v12; // rcx
  HANDLE *v13; // rcx
  int v14; // eax
  int Options; // [rsp+20h] [rbp-49h]
  RPC_WSTR String; // [rsp+30h] [rbp-39h] BYREF
  void **v18; // [rsp+38h] [rbp-31h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-29h] BYREF
  wchar_t *v20[2]; // [rsp+48h] [rbp-21h] BYREF
  _WORD v21[8]; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int16 ProtSeq[20]; // [rsp+68h] [rbp-1h] BYREF

  v20[0] = v21;
  v20[1] = v21;
  v21[0] = 0;
  Binding = 0;
  v18 = &Microsoft::Diagnostics::UtcAdminApiWrapper::`vftable';
  _o_wcscpy_s(ProtSeq, 20, L"ncalrpc");
  String = 0;
  v5 = RpcStringBindingComposeW(0, ProtSeq, 0, 0, 0, &String);
  v9 = v5;
  if ( v5 > 0 )
    v9 = (unsigned __int16)v5 | 0x80070000;
  if ( v9 >= 0 )
  {
    v10 = RpcBindingFromStringBindingW(String, &Binding);
    v9 = v10;
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    RpcStringFreeW(&String);
    if ( v9 >= 0 )
    {
      v11 = L"GuestTrace_";
      v9 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
             v20,
             L"%s\\%s",
             a2,
             L"GuestTrace_");
      if ( v9 >= 0 )
      {
        v9 = Microsoft::Diagnostics::UtcAdminApiWrapper::SnapAgentMiniTrace(
               (Microsoft::Diagnostics::UtcAdminApiWrapper *)&v18,
               v20[0],
               v7);
        v12 = 0x80000000LL;
        if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147467263 )
        {
          if ( v9 >= 0
            || (v11 = L"HostTrace_",
                v9 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                       v20,
                       L"%s\\%s",
                       a2,
                       L"HostTrace_"),
                v9 >= 0)
            && (v9 = Microsoft::Diagnostics::UtcAdminApiWrapper::SnapHostMiniTrace(
                       (Microsoft::Diagnostics::UtcAdminApiWrapper *)&v18,
                       v20[0]),
                v9 >= 0) )
          {
            v9 = CWerService::MoveEtlsInDirectory((CWerService *)v12, v20[0], a2, v11, a3);
            if ( v9 >= 0 )
              goto LABEL_21;
          }
        }
        else
        {
          v13 = (HANDLE *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_21;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_18;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            116,
            WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
            (unsigned int)v9);
        }
      }
    }
  }
  v13 = (HANDLE *)WPP_GLOBAL_Control;
LABEL_18:
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
    WPP_SF_d(v13[2], 117, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, (unsigned int)v9);
LABEL_21:
  v14 = UtilRecursiveRemoveDirectory(v20[0], v6, v7, v8, Options);
  if ( v14 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      118,
      WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids,
      (unsigned int)v14);
  v18 = &Microsoft::Diagnostics::UtcAdminApiWrapper::`vftable';
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( v20[0] != v21 )
    operator delete(v20[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180017f88  mov     [rsp-8+arg_0], rbx
0x180017f8d  push    rbp
0x180017f8e  push    rsi
0x180017f8f  push    rdi
0x180017f90  push    r13
0x180017f92  push    r14
0x180017f94  lea     rbp, [rsp-37h]
0x180017f99  sub     rsp, 0A0h
0x180017fa0  mov     rax, cs:__security_cookie
0x180017fa7  xor     rax, rsp
0x180017faa  mov     [rbp+57h+var_30], rax
0x180017fae  mov     r14, r8
0x180017fb1  mov     rsi, rdx
0x180017fb4  lea     rax, [rbp+57h+var_68]
0x180017fb8  mov     [rbp+57h+var_78], rax
0x180017fbc  lea     rax, [rbp+57h+var_68]
0x180017fc0  mov     [rbp+57h+var_70], rax
0x180017fc4  xor     eax, eax
0x180017fc6  mov     [rbp+57h+var_68], ax
0x180017fca  mov     [rbp+57h+Binding], rax
0x180017fce  lea     rax, ??_7UtcAdminApiWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcAdminApiWrapper::`vftable'
0x180017fd5  mov     [rbp+57h+var_88], rax
0x180017fd9  lea     r8, aNcalrpc; "ncalrpc"
0x180017fe0  mov     edx, 14h
0x180017fe5  lea     rcx, [rbp+57h+ProtSeq]
0x180017fe9  call    cs:__imp__o_wcscpy_s
0x180017fef  mov     [rbp+57h+String], 0
0x180017ff7  lea     rax, [rbp+57h+String]
0x180017ffb  mov     [rsp+0C0h+StringBinding], rax; StringBinding
0x180018000  mov     [rsp+0C0h+Options], 0; Options
0x180018009  xor     r9d, r9d; Endpoint
0x18001800c  xor     r8d, r8d; NetworkAddr
0x18001800f  lea     rdx, [rbp+57h+ProtSeq]; ProtSeq
0x180018013  xor     ecx, ecx; ObjUuid
0x180018015  call    cs:__imp_RpcStringBindingComposeW
0x18001801b  mov     ebx, eax
0x18001801d  mov     edi, 80070000h
0x180018022  test    eax, eax
0x180018024  jle     short loc_18001802B
0x180018026  movzx   ebx, ax
0x180018029  or      ebx, edi
0x18001802b  lea     r13, WPP_GLOBAL_Control
0x180018032  test    ebx, ebx
0x180018034  js      loc_180018132
0x18001803a  lea     rdx, [rbp+57h+Binding]; Binding
0x18001803e  mov     rcx, [rbp+57h+String]; StringBinding
0x180018042  call    cs:__imp_RpcBindingFromStringBindingW
0x180018048  mov     ebx, eax
0x18001804a  test    eax, eax
0x18001804c  jle     short loc_180018053
0x18001804e  movzx   ebx, ax
0x180018051  or      ebx, edi
0x180018053  lea     rcx, [rbp+57h+String]; String
0x180018057  call    cs:__imp_RpcStringFreeW
0x18001805d  test    ebx, ebx
0x18001805f  js      loc_180018132
0x180018065  lea     rdi, aGuesttrace; "GuestTrace_"
0x18001806c  mov     r9, rdi
0x18001806f  mov     r8, rsi
0x180018072  lea     rdx, aSS; "%s\\%s"
0x180018079  lea     rcx, [rbp+57h+var_78]
0x18001807d  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180018082  mov     ebx, eax
0x180018084  test    eax, eax
0x180018086  js      loc_180018132
0x18001808c  mov     rdx, [rbp+57h+var_78]; wchar_t *
0x180018090  lea     rcx, [rbp+57h+var_88]; this
0x180018094  call    ?SnapAgentMiniTrace@UtcAdminApiWrapper@Diagnostics@Microsoft@@QEAAJPEB_W0@Z; Microsoft::Diagnostics::UtcAdminApiWrapper::SnapAgentMiniTrace(wchar_t const *,wchar_t const *)
0x180018099  mov     ebx, eax
0x18001809b  mov     ecx, 80000000h
0x1800180a0  add     eax, ecx
0x1800180a2  test    ecx, eax
0x1800180a4  jnz     short loc_1800180DE
0x1800180a6  cmp     ebx, 80004001h
0x1800180ac  jz      short loc_1800180DE
0x1800180ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180b5  cmp     rcx, r13
0x1800180b8  jz      loc_18001815C
0x1800180be  test    byte ptr [rcx+1Ch], 1
0x1800180c2  jz      short loc_180018139
0x1800180c4  mov     edx, 74h ; 't'
0x1800180c9  mov     r9d, ebx
0x1800180cc  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x1800180d3  mov     rcx, [rcx+10h]
0x1800180d7  call    WPP_SF_d
0x1800180dc  jmp     short loc_180018132
0x1800180de  test    ebx, ebx
0x1800180e0  jns     short loc_180018118
0x1800180e2  lea     rdi, aHosttrace; "HostTrace_"
0x1800180e9  mov     r9, rdi
0x1800180ec  mov     r8, rsi
0x1800180ef  lea     rdx, aSS; "%s\\%s"
0x1800180f6  lea     rcx, [rbp+57h+var_78]
0x1800180fa  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800180ff  mov     ebx, eax
0x180018101  test    eax, eax
0x180018103  js      short loc_180018132
0x180018105  mov     rdx, [rbp+57h+var_78]; wchar_t *
0x180018109  lea     rcx, [rbp+57h+var_88]; this
0x18001810d  call    ?SnapHostMiniTrace@UtcAdminApiWrapper@Diagnostics@Microsoft@@QEAAJPEB_W@Z; Microsoft::Diagnostics::UtcAdminApiWrapper::SnapHostMiniTrace(wchar_t const *)
0x180018112  mov     ebx, eax
0x180018114  test    eax, eax
0x180018116  js      short loc_180018132
0x180018118  mov     [rsp+0C0h+Options], r14; int
0x18001811d  mov     r9, rdi; wchar_t *
0x180018120  mov     r8, rsi; wchar_t *
0x180018123  mov     rdx, [rbp+57h+var_78]; wchar_t *
0x180018127  call    ?MoveEtlsInDirectory@CWerService@@AEAAJPEB_W00PEAK@Z; CWerService::MoveEtlsInDirectory(wchar_t const *,wchar_t const *,wchar_t const *,ulong *)
0x18001812c  mov     ebx, eax
0x18001812e  test    eax, eax
0x180018130  jns     short loc_18001815C
0x180018132  mov     rcx, cs:WPP_GLOBAL_Control
0x180018139  cmp     rcx, r13
0x18001813c  jz      short loc_18001815C
0x18001813e  test    byte ptr [rcx+1Ch], 1
0x180018142  jz      short loc_18001815C
0x180018144  mov     edx, 75h ; 'u'
0x180018149  mov     r9d, ebx
0x18001814c  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180018153  mov     rcx, [rcx+10h]
0x180018157  call    WPP_SF_d
0x18001815c  mov     rcx, [rbp+57h+var_78]; wchar_t *
0x180018160  call    ?UtilRecursiveRemoveDirectory@@YAJPEB_WH00H@Z; UtilRecursiveRemoveDirectory(wchar_t const *,int,wchar_t const *,wchar_t const *,int)
0x180018165  test    eax, eax
0x180018167  jns     short loc_180018194
0x180018169  mov     rcx, cs:WPP_GLOBAL_Control
0x180018170  cmp     rcx, r13
0x180018173  jz      short loc_180018194
0x180018175  test    byte ptr [rcx+1Ch], 1
0x180018179  jz      short loc_180018194
0x18001817b  mov     edx, 76h ; 'v'
0x180018180  mov     r9d, eax
0x180018183  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001818a  mov     rcx, [rcx+10h]
0x18001818e  call    WPP_SF_d
0x180018193  nop
0x180018194  lea     rax, ??_7UtcAdminApiWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcAdminApiWrapper::`vftable'
0x18001819b  mov     [rbp+57h+var_88], rax
0x18001819f  cmp     [rbp+57h+Binding], 0
0x1800181a4  jz      short loc_1800181B1
0x1800181a6  lea     rcx, [rbp+57h+Binding]; Binding
0x1800181aa  call    cs:__imp_RpcBindingFree
0x1800181b0  nop
0x1800181b1  lea     rax, [rbp+57h+var_68]
0x1800181b5  mov     rcx, [rbp+57h+var_78]; void *
0x1800181b9  cmp     rcx, rax
0x1800181bc  jz      short loc_1800181CA
0x1800181be  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800181c5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800181ca  mov     eax, ebx
0x1800181cc  mov     rcx, [rbp+57h+var_30]
0x1800181d0  xor     rcx, rsp; StackCookie
0x1800181d3  call    __security_check_cookie
0x1800181d8  mov     rbx, [rsp+0C0h+arg_0]
0x1800181e0  add     rsp, 0A0h
0x1800181e7  pop     r14
0x1800181e9  pop     r13
0x1800181eb  pop     rdi
0x1800181ec  pop     rsi
0x1800181ed  pop     rbp
0x1800181ee  retn
```
