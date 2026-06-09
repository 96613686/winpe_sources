# CWNPTransportImpl::FinalConstruct(void)

- ea: `0x180023908`
- end: `0x180023c2c`
- name: `?FinalConstruct@CWNPTransportImpl@@IEAAJXZ`
- size: `804`
- prototype: `__int64 __fastcall(CWNPTransportImpl *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022a98`

## callees

- `0x180007440`
- `0x180008294`
- `0x18000ba54`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x180023908`
- `0x18002651c`
- `0x1800319b4`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023a35`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023a35`
- `WS2_32!__imp_WSAStartup` at `0x180023ab7`
- `WS2_32!__imp_WSAStartup` at `0x180023ab7`

## pseudocode

```c
__int64 __fastcall CWNPTransportImpl::FinalConstruct(CWNPTransportImpl *this)
{
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // ebx
  PVOID *v7; // rcx
  __int64 v8; // rdx
  HRESULT Instance; // eax
  bool v10; // sf
  __int64 v11; // r9
  bool v12; // sf
  int v13; // eax
  int ppv; // [rsp+20h] [rbp-1E8h]
  int ppva; // [rsp+20h] [rbp-1E8h]
  WSAData WSAData; // [rsp+30h] [rbp-1D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids);
  }
  memset_0(&WSAData, 0, sizeof(WSAData));
  v2 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *, _QWORD))(*((_QWORD *)this + 5) + 8LL))(
         (char *)this + 40,
         L"CWNPTransportImpl",
         0);
  v6 = v2;
  if ( v2 >= 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 224, v3, v4, v5);
    Instance = CoCreateInstance(
                 &CLSID_NetworkListManager,
                 0,
                 1u,
                 &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b,
                 (LPVOID *)this + 28);
    v6 = Instance;
    if ( Instance >= 0 )
    {
      v6 = WSAStartup(0x202u, &WSAData);
      v10 = v6 < 0;
      if ( v6 > 0 )
        v10 = 1;
      if ( v10
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( v6 > 0 )
          v11 = (unsigned __int16)v6 | 0x80070000;
        else
          v11 = (unsigned int)v6;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids, v11);
      }
      v12 = v6 < 0;
      if ( v6 > 0 )
      {
        v6 = (unsigned __int16)v6 | 0x80070000;
        v12 = v6 < 0;
      }
      if ( v12 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF0,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnptransimpl.cpp",
          (const char *)(unsigned int)v6,
          ppva);
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return (unsigned int)v6;
        if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_48;
        v8 = 28;
        goto LABEL_13;
      }
      *((_BYTE *)this + 160) = 1;
      v13 = PdcInitialize();
      v6 = v13;
      if ( v13 >= 0 )
      {
        CWNPTransportImpl::LogInitialConnectivity(this);
        *((_BYTE *)this + 161) = 1;
        goto LABEL_47;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids,
          (unsigned int)v13);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF6,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnptransimpl.cpp",
        (const char *)(unsigned int)v6,
        ppva);
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v8 = 30;
          goto LABEL_13;
        }
        goto LABEL_48;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids,
          (unsigned int)Instance);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xEC,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnptransimpl.cpp",
        (const char *)(unsigned int)v6,
        ppva);
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v8 = 26;
          goto LABEL_13;
        }
LABEL_48:
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 && *((_BYTE *)v7 + 25) >= 6u )
          WPP_SF_d(v7[2], 31, &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids, (unsigned int)v6);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids,
        (unsigned int)v2);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnptransimpl.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v8 = 24;
LABEL_13:
        WPP_SF_d(v7[2], v8, &WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids, (unsigned int)v6);
LABEL_47:
        v7 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_48;
      }
      goto LABEL_48;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180023908  push    rbx
0x18002390a  push    rbp
0x18002390b  push    rsi
0x18002390c  push    rdi
0x18002390d  sub     rsp, 1E8h
0x180023914  mov     rax, cs:__security_cookie
0x18002391b  xor     rax, rsp
0x18002391e  mov     [rsp+208h+var_38], rax
0x180023926  mov     rdi, rcx
0x180023929  mov     rcx, cs:WPP_GLOBAL_Control
0x180023930  lea     rsi, WPP_GLOBAL_Control
0x180023937  lea     rbp, WPP_d87b5673a8153a3fa4480ccb5964d521_Traceguids
0x18002393e  cmp     rcx, rsi
0x180023941  jz      short loc_180023960
0x180023943  test    byte ptr [rcx+1Ch], 4
0x180023947  jz      short loc_180023960
0x180023949  cmp     byte ptr [rcx+19h], 6
0x18002394d  jb      short loc_180023960
0x18002394f  mov     rcx, [rcx+10h]
0x180023953  mov     edx, 16h
0x180023958  mov     r8, rbp
0x18002395b  call    WPP_SF_
0x180023960  xor     edx, edx; Val
0x180023962  lea     rcx, [rsp+208h+WSAData]; void *
0x180023967  mov     r8d, 198h; Size
0x18002396d  call    memset_0
0x180023972  lea     rcx, [rdi+28h]
0x180023976  xor     r8d, r8d
0x180023979  mov     rax, [rcx]
0x18002397c  lea     rdx, ?g_cszWnpTransportImplWindow@@3QBGB; "CWNPTransportImpl"
0x180023983  mov     rax, [rax+8]
0x180023987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002398c  mov     ebx, eax
0x18002398e  test    eax, eax
0x180023990  jns     short loc_180023A0D
0x180023992  mov     rcx, cs:WPP_GLOBAL_Control
0x180023999  cmp     rcx, rsi
0x18002399c  jz      short loc_1800239BE
0x18002399e  test    byte ptr [rcx+1Ch], 4
0x1800239a2  jz      short loc_1800239BE
0x1800239a4  cmp     byte ptr [rcx+19h], 2
0x1800239a8  jb      short loc_1800239BE
0x1800239aa  mov     rcx, [rcx+10h]
0x1800239ae  mov     edx, 17h
0x1800239b3  mov     r9d, eax
0x1800239b6  mov     r8, rbp
0x1800239b9  call    WPP_SF_d
0x1800239be  mov     rcx, [rsp+208h]; this
0x1800239c6  lea     r8, aOnecoreuapBase_38; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800239cd  mov     r9d, ebx; char *
0x1800239d0  mov     edx, 0E7h; void *
0x1800239d5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800239da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239e1  cmp     rcx, rsi
0x1800239e4  jz      loc_180023C0E
0x1800239ea  test    byte ptr [rcx+1Ch], 80h
0x1800239ee  jz      loc_180023BE9
0x1800239f4  mov     edx, 18h
0x1800239f9  mov     rcx, [rcx+10h]
0x1800239fd  mov     r9d, ebx
0x180023a00  mov     r8, rbp
0x180023a03  call    WPP_SF_d
0x180023a08  jmp     loc_180023BE2
0x180023a0d  lea     rbx, [rdi+0E0h]
0x180023a14  mov     rcx, rbx
0x180023a17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023a1c  xor     edx, edx; pUnkOuter
0x180023a1e  mov     qword ptr [rsp+208h+ppv], rbx; int
0x180023a23  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x180023a2a  lea     rcx, CLSID_NetworkListManager; rclsid
0x180023a31  lea     r8d, [rdx+1]; dwClsContext
0x180023a35  call    cs:__imp_CoCreateInstance
0x180023a3b  mov     ebx, eax
0x180023a3d  test    eax, eax
0x180023a3f  jns     short loc_180023AAD
0x180023a41  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a48  cmp     rcx, rsi
0x180023a4b  jz      short loc_180023A6D
0x180023a4d  test    byte ptr [rcx+1Ch], 4
0x180023a51  jz      short loc_180023A6D
0x180023a53  cmp     byte ptr [rcx+19h], 2
0x180023a57  jb      short loc_180023A6D
0x180023a59  mov     rcx, [rcx+10h]
0x180023a5d  mov     edx, 19h
0x180023a62  mov     r9d, eax
0x180023a65  mov     r8, rbp
0x180023a68  call    WPP_SF_d
0x180023a6d  mov     rcx, [rsp+208h]; this
0x180023a75  lea     r8, aOnecoreuapBase_38; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180023a7c  mov     r9d, ebx; char *
0x180023a7f  mov     edx, 0ECh; void *
0x180023a84  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023a89  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a90  cmp     rcx, rsi
0x180023a93  jz      loc_180023C0E
0x180023a99  test    byte ptr [rcx+1Ch], 80h
0x180023a9d  jz      loc_180023BE9
0x180023aa3  mov     edx, 1Ah
0x180023aa8  jmp     loc_1800239F9
0x180023aad  mov     ecx, 202h; wVersionRequested
0x180023ab2  lea     rdx, [rsp+208h+WSAData]; lpWSAData
0x180023ab7  call    cs:__imp_WSAStartup
0x180023abd  mov     ebx, eax
0x180023abf  test    eax, eax
0x180023ac1  jle     short loc_180023ACD
0x180023ac3  movzx   eax, bx
0x180023ac6  or      eax, 80070000h
0x180023acb  test    eax, eax
0x180023acd  jns     short loc_180023B0C
0x180023acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ad6  cmp     rcx, rsi
0x180023ad9  jz      short loc_180023B0C
0x180023adb  test    byte ptr [rcx+1Ch], 4
0x180023adf  jz      short loc_180023B0C
0x180023ae1  cmp     byte ptr [rcx+19h], 2
0x180023ae5  jb      short loc_180023B0C
0x180023ae7  test    ebx, ebx
0x180023ae9  jg      short loc_180023AF0
0x180023aeb  mov     r9d, ebx
0x180023aee  jmp     short loc_180023AFB
0x180023af0  movzx   r9d, bx
0x180023af4  or      r9d, 80070000h
0x180023afb  mov     rcx, [rcx+10h]
0x180023aff  mov     edx, 1Bh
0x180023b04  mov     r8, rbp
0x180023b07  call    WPP_SF_d
0x180023b0c  test    ebx, ebx
0x180023b0e  jle     short loc_180023B1B
0x180023b10  movzx   ebx, bx
0x180023b13  or      ebx, 80070000h
0x180023b19  test    ebx, ebx
0x180023b1b  jns     short loc_180023B5D
0x180023b1d  mov     rcx, [rsp+208h]; this
0x180023b25  lea     r8, aOnecoreuapBase_38; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180023b2c  mov     r9d, ebx; char *
0x180023b2f  mov     edx, 0F0h; void *
0x180023b34  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023b39  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b40  cmp     rcx, rsi
0x180023b43  jz      loc_180023C0E
0x180023b49  test    byte ptr [rcx+1Ch], 80h
0x180023b4d  jz      loc_180023BE9
0x180023b53  mov     edx, 1Ch
0x180023b58  jmp     loc_1800239F9
0x180023b5d  mov     byte ptr [rdi+0A0h], 1
0x180023b64  call    ?PdcInitialize@@YAJXZ; PdcInitialize(void)
0x180023b69  mov     ebx, eax
0x180023b6b  test    eax, eax
0x180023b6d  jns     short loc_180023BD3
0x180023b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b76  cmp     rcx, rsi
0x180023b79  jz      short loc_180023B9B
0x180023b7b  test    byte ptr [rcx+1Ch], 4
0x180023b7f  jz      short loc_180023B9B
0x180023b81  cmp     byte ptr [rcx+19h], 2
0x180023b85  jb      short loc_180023B9B
0x180023b87  mov     rcx, [rcx+10h]
0x180023b8b  mov     edx, 1Dh
0x180023b90  mov     r9d, eax
0x180023b93  mov     r8, rbp
0x180023b96  call    WPP_SF_d
0x180023b9b  mov     rcx, [rsp+208h]; this
0x180023ba3  lea     r8, aOnecoreuapBase_38; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180023baa  mov     r9d, ebx; char *
0x180023bad  mov     edx, 0F6h; void *
0x180023bb2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180023bbe  cmp     rcx, rsi
0x180023bc1  jz      short loc_180023C0E
0x180023bc3  test    byte ptr [rcx+1Ch], 80h
0x180023bc7  jz      short loc_180023BE9
0x180023bc9  mov     edx, 1Eh
0x180023bce  jmp     loc_1800239F9
0x180023bd3  mov     rcx, rdi; this
0x180023bd6  call    ?LogInitialConnectivity@CWNPTransportImpl@@AEAAXXZ; CWNPTransportImpl::LogInitialConnectivity(void)
0x180023bdb  mov     byte ptr [rdi+0A1h], 1
0x180023be2  mov     rcx, cs:WPP_GLOBAL_Control
0x180023be9  cmp     rcx, rsi
0x180023bec  jz      short loc_180023C0E
0x180023bee  test    byte ptr [rcx+1Ch], 4
0x180023bf2  jz      short loc_180023C0E
0x180023bf4  cmp     byte ptr [rcx+19h], 6
0x180023bf8  jb      short loc_180023C0E
0x180023bfa  mov     rcx, [rcx+10h]
0x180023bfe  mov     edx, 1Fh
0x180023c03  mov     r9d, ebx
0x180023c06  mov     r8, rbp
0x180023c09  call    WPP_SF_d
0x180023c0e  mov     eax, ebx
0x180023c10  mov     rcx, [rsp+208h+var_38]
0x180023c18  xor     rcx, rsp; StackCookie
0x180023c1b  call    __security_check_cookie
0x180023c20  add     rsp, 1E8h
0x180023c27  pop     rdi
0x180023c28  pop     rsi
0x180023c29  pop     rbp
0x180023c2a  pop     rbx
0x180023c2b  retn
```
