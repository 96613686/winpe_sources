# GetDirectAccessInfo(ushort const *,INDFEtw *,DIRECT_ACCESS_QUERY * *,int *,_WINHTTP_PROXY_INFO *)

- ea: `0x18000dfe8`
- end: `0x18000e228`
- name: `?GetDirectAccessInfo@@YAJPEBGPEAUINDFEtw@@PEAPEAVDIRECT_ACCESS_QUERY@@PEAHPEAU_WINHTTP_PROXY_INFO@@@Z`
- size: `576`
- prototype: `__int64 __usercall@<rax>(PCWSTR hostName@<rcx>, struct INDFEtw *@<rdx>, struct DIRECT_ACCESS_QUERY **@<r8>, int *@<r9>, struct _WINHTTP_PROXY_INFO *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180009e04`
- `0x18000d160`

## callees

- `0x1800012c0`
- `0x1800012e4`
- `0x1800087b4`
- `0x18000dfe8`
- `0x180014010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18000e1fd`
- `KERNEL32!GlobalFree` at `0x18000e1fd`
- `DNSAPI!DnsGetProxyInformation` at `0x18000e077`
- `DNSAPI!DnsGetProxyInformation` at `0x18000e077`
- `DNSAPI!DnsFreeProxyName` at `0x18000e04f`
- `DNSAPI!DnsFreeProxyName` at `0x18000e166`
- `DNSAPI!DnsFreeProxyName` at `0x18000e183`
- `DNSAPI!DnsFreeProxyName` at `0x18000e04f`
- `DNSAPI!DnsFreeProxyName` at `0x18000e166`
- `DNSAPI!DnsFreeProxyName` at `0x18000e183`

## string_xrefs

- `0x18000e0c3`: `Direct Access has no proxy configured for this URL.`
- `0x18000e12f`: `Unexpected Direct Access state encountered`
- `0x18000e1ae`: `Direct Access has specific proxy configured for this URL.`

## pseudocode

```c
__int64 __fastcall GetDirectAccessInfo(
        PCWSTR hostName,
        struct INDFEtw *a2,
        DNS_PROXY_INFORMATION **a3,
        int *a4,
        struct _WINHTTP_PROXY_INFO *a5)
{
  unsigned __int16 *v9; // rbp
  DNS_PROXY_INFORMATION *v10; // rax
  DNS_PROXY_INFORMATION *v11; // rbx
  int v12; // esi
  signed int ProxyInformation; // eax
  unsigned int v14; // edi
  int v15; // r15d
  int IsUseProxy; // eax
  WCHAR *proxyName; // rcx
  WCHAR *v18; // rcx
  struct _WINHTTP_PROXY_INFO *v19; // rax
  int v21; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int16 *v22; // [rsp+88h] [rbp+20h] BYREF

  v22 = 0;
  v21 = 0;
  *a3 = 0;
  *a4 = 0;
  v9 = 0;
  v10 = (DNS_PROXY_INFORMATION *)operator new(0x28u);
  v11 = v10;
  if ( !v10 )
    return (unsigned int)-2147024882;
  v12 = 1;
  v10->proxyName = 0;
  v10->version = 1;
  v10->proxyInformationType = DNS_PROXY_INFORMATION_DEFAULT_SETTINGS;
  v10[1].version = 1;
  v10[1].proxyName = 0;
  v10[1].proxyInformationType = DNS_PROXY_INFORMATION_DEFAULT_SETTINGS;
  v10[2].version = 0;
  v10->proxyInformationType = DNS_PROXY_INFORMATION_DEFAULT_SETTINGS;
  v10[1].proxyInformationType = DNS_PROXY_INFORMATION_DEFAULT_SETTINGS;
  ProxyInformation = DnsGetProxyInformation(hostName, v10, v10 + 1, 0, 0);
  v11[2].version = ProxyInformation;
  v14 = ProxyInformation;
  if ( ProxyInformation )
  {
    if ( ProxyInformation > 0 )
      v14 = (unsigned __int16)ProxyInformation | 0x80070000;
    goto LABEL_17;
  }
  if ( v11->proxyInformationType == DNS_PROXY_INFORMATION_DEFAULT_SETTINGS )
  {
    v12 = 0;
    v15 = 0;
  }
  else
  {
    v15 = 1;
    if ( v11->proxyInformationType )
    {
      IsUseProxy = DIRECT_ACCESS_QUERY::IsUseProxy((DIRECT_ACCESS_QUERY *)v11, &v22, &v21);
      v14 = IsUseProxy;
      if ( IsUseProxy )
      {
        if ( IsUseProxy > 0 )
          v14 = (unsigned __int16)IsUseProxy | 0x80070000;
      }
      else
      {
        if ( v21 )
        {
          v12 = 3;
          if ( a2 )
            (*(void (__fastcall **)(struct INDFEtw *, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
              a2,
              2,
              0,
              L"WinInetHelperClass",
              L"Direct Access has specific proxy configured for this URL.");
          v9 = v22;
          goto LABEL_25;
        }
        v14 = -2147418113;
        if ( a2 )
          (*(void (__fastcall **)(struct INDFEtw *, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
            a2,
            2,
            0,
            L"WinInetHelperClass",
            L"Unexpected Direct Access state encountered");
      }
      v9 = v22;
LABEL_17:
      proxyName = v11->proxyName;
      if ( proxyName )
      {
        DnsFreeProxyName(proxyName);
        v11->proxyName = 0;
      }
      v18 = v11[1].proxyName;
      if ( v18 )
      {
        DnsFreeProxyName(v18);
        v11[1].proxyName = 0;
      }
      operator delete(v11);
      goto LABEL_26;
    }
    if ( a2 )
      (*(void (__fastcall **)(struct INDFEtw *, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
        a2,
        2,
        0,
        L"WinInetHelperClass",
        L"Direct Access has no proxy configured for this URL.");
  }
LABEL_25:
  v19 = a5;
  v14 = 0;
  *a4 = v15;
  *((_QWORD *)v19 + 1) = v9;
  v9 = 0;
  *(_DWORD *)v19 = v12;
  *a3 = v11;
LABEL_26:
  if ( v9 )
    GlobalFree(v9);
  return v14;
}

```

## disassembly

```asm
0x18000dfe8  mov     rax, rsp
0x18000dfeb  mov     [rax+8], rbx
0x18000dfef  push    rbp
0x18000dff0  push    rsi
0x18000dff1  push    rdi
0x18000dff2  push    r12
0x18000dff4  push    r13
0x18000dff6  push    r14
0x18000dff8  push    r15
0x18000dffa  sub     rsp, 30h
0x18000dffe  xor     edi, edi
0x18000e000  mov     r15, rcx
0x18000e003  mov     r12, r9
0x18000e006  mov     [rax+20h], rdi
0x18000e00a  mov     r13, r8
0x18000e00d  mov     [rax+18h], edi
0x18000e010  mov     r14, rdx
0x18000e013  mov     [r8], rdi
0x18000e016  lea     ecx, [rdi+28h]; Size
0x18000e019  mov     [r9], edi
0x18000e01c  mov     ebp, edi
0x18000e01e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e023  mov     rbx, rax
0x18000e026  test    rax, rax
0x18000e029  jz      loc_18000E20B
0x18000e02f  lea     esi, [rdi+1]
0x18000e032  mov     [rax+8], rdi
0x18000e036  mov     ecx, edi; proxyName
0x18000e038  mov     [rax], esi
0x18000e03a  mov     [rax+4], esi
0x18000e03d  mov     [rax+10h], esi
0x18000e040  mov     [rax+18h], rdi
0x18000e044  mov     [rax+14h], esi
0x18000e047  mov     [rax+20h], edi
0x18000e04a  test    rcx, rcx
0x18000e04d  jz      short loc_18000E05F
0x18000e04f  call    cs:__imp_DnsFreeProxyName
0x18000e056  nop     dword ptr [rax+rax+00h]
0x18000e05b  mov     [rbx+18h], rdi
0x18000e05f  xor     r9d, r9d; completionRoutine
0x18000e062  mov     [rbx+4], esi
0x18000e065  lea     r8, [rbx+10h]; defaultProxyInformation
0x18000e069  mov     [rbx+14h], esi
0x18000e06c  mov     rdx, rbx; proxyInformation
0x18000e06f  mov     [rsp+68h+completionContext], rdi; completionContext
0x18000e074  mov     rcx, r15; hostName
0x18000e077  call    cs:__imp_DnsGetProxyInformation
0x18000e07e  nop     dword ptr [rax+rax+00h]
0x18000e083  mov     [rbx+20h], eax
0x18000e086  mov     edi, eax
0x18000e088  test    eax, eax
0x18000e08a  jz      short loc_18000E0A0
0x18000e08c  jle     loc_18000E15D
0x18000e092  movzx   edi, ax
0x18000e095  or      edi, 80070000h
0x18000e09b  jmp     loc_18000E15D
0x18000e0a0  cmp     [rbx+4], esi
0x18000e0a3  jnz     short loc_18000E0AF
0x18000e0a5  xor     esi, esi
0x18000e0a7  xor     r15d, r15d
0x18000e0aa  jmp     loc_18000E1DB
0x18000e0af  mov     r15d, esi
0x18000e0b2  cmp     [rbx+4], ebp
0x18000e0b5  jnz     short loc_18000E0EE
0x18000e0b7  test    r14, r14
0x18000e0ba  jz      loc_18000E1DB
0x18000e0c0  mov     rax, [r14]
0x18000e0c3  lea     rcx, aDirectAccessHa; "Direct Access has no proxy configured f"...
0x18000e0ca  xor     r8d, r8d
0x18000e0cd  mov     [rsp+68h+completionContext], rcx
0x18000e0d2  lea     r9, aWininethelperc; "WinInetHelperClass"
0x18000e0d9  mov     rcx, r14
0x18000e0dc  mov     rax, [rax+18h]
0x18000e0e0  lea     edx, [r8+2]
0x18000e0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0e9  jmp     loc_18000E1DB
0x18000e0ee  lea     r8, [rsp+68h+arg_10]; int *
0x18000e0f6  mov     rcx, rbx; this
0x18000e0f9  lea     rdx, [rsp+68h+arg_18]; unsigned __int16 **
0x18000e101  call    ?IsUseProxy@DIRECT_ACCESS_QUERY@@QEAAKPEAPEAGPEAH@Z; DIRECT_ACCESS_QUERY::IsUseProxy(ushort * *,int *)
0x18000e106  mov     edi, eax
0x18000e108  test    eax, eax
0x18000e10a  jz      short loc_18000E119
0x18000e10c  jle     short loc_18000E155
0x18000e10e  movzx   edi, ax
0x18000e111  or      edi, 80070000h
0x18000e117  jmp     short loc_18000E155
0x18000e119  cmp     [rsp+68h+arg_10], ebp
0x18000e120  jnz     short loc_18000E1A1
0x18000e122  mov     edi, 8000FFFFh
0x18000e127  test    r14, r14
0x18000e12a  jz      short loc_18000E155
0x18000e12c  mov     rax, [r14]
0x18000e12f  lea     rcx, aUnexpectedDire; "Unexpected Direct Access state encounte"...
0x18000e136  xor     r8d, r8d
0x18000e139  mov     [rsp+68h+completionContext], rcx
0x18000e13e  lea     r9, aWininethelperc; "WinInetHelperClass"
0x18000e145  mov     rcx, r14
0x18000e148  mov     rax, [rax+18h]
0x18000e14c  lea     edx, [r8+2]
0x18000e150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e155  mov     rbp, [rsp+68h+arg_18]
0x18000e15d  mov     rcx, [rbx+8]; proxyName
0x18000e161  test    rcx, rcx
0x18000e164  jz      short loc_18000E17A
0x18000e166  call    cs:__imp_DnsFreeProxyName
0x18000e16d  nop     dword ptr [rax+rax+00h]
0x18000e172  mov     qword ptr [rbx+8], 0
0x18000e17a  mov     rcx, [rbx+18h]; proxyName
0x18000e17e  test    rcx, rcx
0x18000e181  jz      short loc_18000E197
0x18000e183  call    cs:__imp_DnsFreeProxyName
0x18000e18a  nop     dword ptr [rax+rax+00h]
0x18000e18f  mov     qword ptr [rbx+18h], 0
0x18000e197  mov     rcx, rbx; Block
0x18000e19a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e19f  jmp     short loc_18000E1F5
0x18000e1a1  mov     esi, 3
0x18000e1a6  test    r14, r14
0x18000e1a9  jz      short loc_18000E1D3
0x18000e1ab  mov     rax, [r14]
0x18000e1ae  lea     rcx, aDirectAccessHa_0; "Direct Access has specific proxy config"...
0x18000e1b5  mov     [rsp+68h+completionContext], rcx
0x18000e1ba  lea     r9, aWininethelperc; "WinInetHelperClass"
0x18000e1c1  xor     r8d, r8d
0x18000e1c4  lea     edx, [rsi-1]
0x18000e1c7  mov     rcx, r14
0x18000e1ca  mov     rax, [rax+18h]
0x18000e1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1d3  mov     rbp, [rsp+68h+arg_18]
0x18000e1db  mov     rax, [rsp+68h+arg_20]
0x18000e1e3  xor     edi, edi
0x18000e1e5  mov     [r12], r15d
0x18000e1e9  mov     [rax+8], rbp
0x18000e1ed  xor     ebp, ebp
0x18000e1ef  mov     [rax], esi
0x18000e1f1  mov     [r13+0], rbx
0x18000e1f5  test    rbp, rbp
0x18000e1f8  jz      short loc_18000E210
0x18000e1fa  mov     rcx, rbp; hMem
0x18000e1fd  call    cs:__imp_GlobalFree
0x18000e204  nop     dword ptr [rax+rax+00h]
0x18000e209  jmp     short loc_18000E210
0x18000e20b  mov     edi, 8007000Eh
0x18000e210  mov     rbx, [rsp+68h+arg_0]
0x18000e215  mov     eax, edi
0x18000e217  add     rsp, 30h
0x18000e21b  pop     r15
0x18000e21d  pop     r14
0x18000e21f  pop     r13
0x18000e221  pop     r12
0x18000e223  pop     rdi
0x18000e224  pop     rsi
0x18000e225  pop     rbp
0x18000e226  retn
```
