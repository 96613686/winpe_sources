# SetChannelCommand::OpenConfig(wchar_t const *)

- ea: `0x140019c4c`
- end: `0x14001a0da`
- name: `?OpenConfig@SetChannelCommand@@AEAA?AU?$com_ptr@UIXMLDOMElement@@@winrt@@PEB_W@Z`
- size: `1166`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000fc50`

## callees

- `0x140002c70`
- `0x14000cabc`
- `0x140010450`
- `0x140011570`
- `0x14001159c`
- `0x14001950c`
- `0x140019c4c`
- `0x14001a508`
- `0x140021b00`
- `0x140022cec`
- `0x140025b2c`
- `0x140031810`
- `0x140034010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x140019f69`
- `OLEAUT32!__imp_SysStringLen` at `0x140019f7a`
- `OLEAUT32!__imp_SysStringLen` at `0x140019f69`
- `OLEAUT32!__imp_SysStringLen` at `0x140019f7a`

## string_xrefs

- `0x140019f8e`: `http://schemas.microsoft.com/win/2004/08/events`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 *__fastcall SetChannelCommand::OpenConfig(__int64 a1, __int64 *a2, wchar_t *a3)
{
  const char *v4; // r8
  WCHAR *v5; // rdx
  LPVOID *v6; // rax
  LPVOID v7; // rbx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64); // rbx
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64); // rbx
  __int64 v18; // rax
  int v19; // eax
  unsigned int v20; // ebx
  const wchar_t *v21; // rbx
  const char *v23; // [rsp+20h] [rbp-59h]
  BSTR pbstr; // [rsp+40h] [rbp-39h] BYREF
  int v25; // [rsp+48h] [rbp-31h]
  wchar_t *S2; // [rsp+50h] [rbp-29h] BYREF
  char v27[8]; // [rsp+58h] [rbp-21h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v29[2]; // [rsp+88h] [rbp+Fh] BYREF
  WCHAR Buffer[8]; // [rsp+98h] [rbp+1Fh] BYREF
  __m128i si128; // [rsp+A8h] [rbp+2Fh]

  v29[1] = a2;
  v25 = 0;
  *(_OWORD *)Buffer = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  Buffer[0] = 0;
  GetFullPath(a3, Buffer);
  v5 = Buffer;
  if ( si128.m128i_i64[1] > 7uLL )
    v5 = *(WCHAR **)Buffer;
  v6 = XmlLoad((LPVOID *)v27, v5, v4);
  v7 = *v6;
  *v6 = 0;
  v29[0] = v7;
  if ( *(_QWORD *)v27 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(v27);
  *a2 = 0;
  v25 = 1;
  v8 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v7 + 360LL))(v7, a2);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_2969cf25331937701283eddb1dcf16ae_Traceguids,
        (unsigned int)v8);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v9, 0, 0, v23, 97, 2u, 0);
    throw (EvtException *)pExceptionObject;
  }
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, 2147942487LL);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x80070057, 0, 0, v23, 101, 2u, 0);
    throw (EvtException *)pExceptionObject;
  }
  S2 = 0;
  v10 = *a2;
  v11 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)*a2 + 56LL);
  v12 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(&S2);
  v13 = v11(v10, v12);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_2969cf25331937701283eddb1dcf16ae_Traceguids,
        (unsigned int)v13);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v14, 0, 0, v23, 108, 2u, 0);
    throw (EvtException *)pExceptionObject;
  }
  v15 = -1;
  do
    ++v15;
  while ( S2[v15] );
  if ( v15 != 7 || wmemcmp(L"channel", S2, 7u) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, 2147942487LL);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x80070057, 0, 0, v23, 113, 0x25u, 0);
    throw (EvtException *)pExceptionObject;
  }
  pbstr = 0;
  v16 = *a2;
  v17 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)*a2 + 312LL);
  v18 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(&pbstr);
  v19 = v17(v16, v18);
  v20 = v19;
  if ( v19 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_2969cf25331937701283eddb1dcf16ae_Traceguids,
        (unsigned int)v19);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v20, 0, 0, v23, 120, 2u, 0);
    throw (EvtException *)pExceptionObject;
  }
  if ( v19 == 1
    || !SysStringLen(pbstr)
    || (v21 = pbstr, SysStringLen(pbstr) != 47)
    || wmemcmp(L"http://schemas.microsoft.com/win/2004/08/events", v21, 0x2Fu) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, 2147942487LL);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x80070057, 0, 0, v23, 127, 0x25u, 0);
    throw (EvtException *)pExceptionObject;
  }
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pbstr);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&S2);
  winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(v29);
  std::wstring::_Tidy_deallocate(Buffer);
  return a2;
}

```

## disassembly

```asm
0x140019c4c  mov     [rsp-8+arg_0], rbx
0x140019c51  mov     [rsp-8+arg_18], rsi
0x140019c56  push    rbp
0x140019c57  push    rdi
0x140019c58  push    r14
0x140019c5a  lea     rbp, [rsp-47h]
0x140019c5f  sub     rsp, 0C0h
0x140019c66  mov     rax, cs:__security_cookie
0x140019c6d  xor     rax, rsp
0x140019c70  mov     [rbp+57h+var_18], rax
0x140019c74  mov     rsi, rdx
0x140019c77  mov     [rbp+57h+var_40], rdx
0x140019c7b  xor     r14d, r14d
0x140019c7e  mov     [rbp+57h+var_88], r14d
0x140019c82  xorps   xmm0, xmm0
0x140019c85  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x140019c89  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140019c91  movdqu  [rbp+57h+var_28], xmm1
0x140019c96  mov     [rbp+57h+Buffer], r14w
0x140019c9b  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x140019c9f  mov     rcx, r8; Src
0x140019ca2  call    GetFullPath
0x140019ca7  lea     rdx, [rbp+57h+Buffer]
0x140019cab  cmp     qword ptr [rbp+57h+var_28+8], 7
0x140019cb0  cmova   rdx, qword ptr [rbp+57h+Buffer]; wchar_t *
0x140019cb5  lea     rcx, [rbp+57h+var_78]; char *
0x140019cb9  call    ?XmlLoad@@YA?AU?$com_ptr@UIXMLDOMDocument3@@@winrt@@PEB_W@Z; XmlLoad(wchar_t const *)
0x140019cbe  mov     rbx, [rax]
0x140019cc1  mov     [rax], r14
0x140019cc4  mov     [rbp+57h+var_48], rbx
0x140019cc8  cmp     qword ptr [rbp+57h+var_78], r14
0x140019ccc  jz      short loc_140019CD7
0x140019cce  lea     rcx, [rbp+57h+var_78]
0x140019cd2  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x140019cd7  mov     [rsi], r14
0x140019cda  mov     [rbp+57h+var_88], 1
0x140019ce1  mov     rax, [rbx]
0x140019ce4  mov     rdx, rsi
0x140019ce7  mov     rcx, rbx
0x140019cea  mov     rax, [rax+168h]
0x140019cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019cf6  mov     ebx, eax
0x140019cf8  test    eax, eax
0x140019cfa  jns     short loc_140019D6F
0x140019cfc  lea     rcx, WPP_GLOBAL_Control
0x140019d03  mov     r10, cs:WPP_GLOBAL_Control
0x140019d0a  cmp     r10, rcx
0x140019d0d  jz      short loc_140019D38
0x140019d0f  test    dword ptr [r10+1Ch], 400000h
0x140019d17  jz      short loc_140019D38
0x140019d19  cmp     byte ptr [r10+19h], 2
0x140019d1e  jb      short loc_140019D38
0x140019d20  mov     edx, 0Dh
0x140019d25  mov     r9d, eax
0x140019d28  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x140019d2f  mov     rcx, [r10+10h]
0x140019d33  call    WPP_SF_d
0x140019d38  mov     [rsp+0D0h+Src], r14; Src
0x140019d3d  mov     [rsp+0D0h+var_A0], 2; unsigned int
0x140019d45  mov     [rsp+0D0h+var_A8], 61h ; 'a'; int
0x140019d4d  xor     r9d, r9d; unsigned int
0x140019d50  xor     r8d, r8d; unsigned int
0x140019d53  mov     edx, ebx; unsigned int
0x140019d55  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140019d59  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140019d5e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140019d65  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140019d69  call    _CxxThrowException_0
0x140019d6f  test    ebx, ebx
0x140019d71  jz      short loc_140019DEA
0x140019d73  lea     rcx, WPP_GLOBAL_Control
0x140019d7a  mov     rax, cs:WPP_GLOBAL_Control
0x140019d81  cmp     rax, rcx
0x140019d84  jz      short loc_140019DB0
0x140019d86  test    dword ptr [rax+1Ch], 400000h
0x140019d8d  jz      short loc_140019DB0
0x140019d8f  cmp     byte ptr [rax+19h], 2
0x140019d93  jb      short loc_140019DB0
0x140019d95  mov     edx, 0Eh
0x140019d9a  mov     r9d, 80070057h
0x140019da0  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x140019da7  mov     rcx, [rax+10h]
0x140019dab  call    WPP_SF_d
0x140019db0  mov     [rsp+0D0h+Src], r14; Src
0x140019db5  mov     [rsp+0D0h+var_A0], 2; unsigned int
0x140019dbd  mov     [rsp+0D0h+var_A8], 65h ; 'e'; int
0x140019dc5  xor     r9d, r9d; unsigned int
0x140019dc8  xor     r8d, r8d; unsigned int
0x140019dcb  mov     edx, 80070057h; unsigned int
0x140019dd0  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140019dd4  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140019dd9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140019de0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140019de4  call    _CxxThrowException_0
0x140019dea  mov     [rbp+57h+S2], r14
0x140019dee  mov     rdi, [rsi]
0x140019df1  mov     rax, [rdi]
0x140019df4  mov     rbx, [rax+38h]
0x140019df8  lea     rcx, [rbp+57h+S2]
0x140019dfc  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(void)
0x140019e01  mov     rdx, rax
0x140019e04  mov     rcx, rdi
0x140019e07  mov     rax, rbx
0x140019e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019e0f  mov     ebx, eax
0x140019e11  test    eax, eax
0x140019e13  jns     short loc_140019E88
0x140019e15  lea     rcx, WPP_GLOBAL_Control
0x140019e1c  mov     r10, cs:WPP_GLOBAL_Control
0x140019e23  cmp     r10, rcx
0x140019e26  jz      short loc_140019E51
0x140019e28  test    dword ptr [r10+1Ch], 400000h
0x140019e30  jz      short loc_140019E51
0x140019e32  cmp     byte ptr [r10+19h], 2
0x140019e37  jb      short loc_140019E51
0x140019e39  mov     edx, 0Fh
0x140019e3e  mov     r9d, eax
0x140019e41  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x140019e48  mov     rcx, [r10+10h]
0x140019e4c  call    WPP_SF_d
0x140019e51  mov     [rsp+0D0h+Src], r14; Src
0x140019e56  mov     [rsp+0D0h+var_A0], 2; unsigned int
0x140019e5e  mov     [rsp+0D0h+var_A8], 6Ch ; 'l'; int
0x140019e66  xor     r9d, r9d; unsigned int
0x140019e69  xor     r8d, r8d; unsigned int
0x140019e6c  mov     edx, ebx; unsigned int
0x140019e6e  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140019e72  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140019e77  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140019e7e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140019e82  call    _CxxThrowException_0
0x140019e88  mov     rdx, [rbp+57h+S2]; S2
0x140019e8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140019e90  inc     rax
0x140019e93  cmp     [rdx+rax*2], r14w
0x140019e98  jnz     short loc_140019E90
0x140019e9a  cmp     rax, 7
0x140019e9e  jnz     loc_14001A063
0x140019ea4  mov     r8, rax; N
0x140019ea7  lea     rcx, aChannel; "channel"
0x140019eae  call    wmemcmp
0x140019eb3  test    eax, eax
0x140019eb5  jnz     loc_14001A063
0x140019ebb  mov     [rbp+57h+pbstr], r14
0x140019ebf  mov     rdi, [rsi]
0x140019ec2  mov     rax, [rdi]
0x140019ec5  mov     rbx, [rax+138h]
0x140019ecc  lea     rcx, [rbp+57h+pbstr]
0x140019ed0  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(void)
0x140019ed5  mov     rdx, rax
0x140019ed8  mov     rcx, rdi
0x140019edb  mov     rax, rbx
0x140019ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019ee3  mov     ebx, eax
0x140019ee5  test    eax, eax
0x140019ee7  jns     short loc_140019F5C
0x140019ee9  lea     rcx, WPP_GLOBAL_Control
0x140019ef0  mov     r10, cs:WPP_GLOBAL_Control
0x140019ef7  cmp     r10, rcx
0x140019efa  jz      short loc_140019F25
0x140019efc  test    dword ptr [r10+1Ch], 400000h
0x140019f04  jz      short loc_140019F25
0x140019f06  cmp     byte ptr [r10+19h], 2
0x140019f0b  jb      short loc_140019F25
0x140019f0d  mov     edx, 11h
0x140019f12  mov     r9d, eax
0x140019f15  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x140019f1c  mov     rcx, [r10+10h]
0x140019f20  call    WPP_SF_d
0x140019f25  mov     [rsp+0D0h+Src], r14; Src
0x140019f2a  mov     [rsp+0D0h+var_A0], 2; unsigned int
0x140019f32  mov     [rsp+0D0h+var_A8], 78h ; 'x'; int
0x140019f3a  xor     r9d, r9d; unsigned int
0x140019f3d  xor     r8d, r8d; unsigned int
0x140019f40  mov     edx, ebx; unsigned int
0x140019f42  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140019f46  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140019f4b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140019f52  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140019f56  call    _CxxThrowException_0
0x140019f5c  cmp     ebx, 1
0x140019f5f  jz      loc_140019FEC
0x140019f65  mov     rcx, [rbp+57h+pbstr]; pbstr
0x140019f69  call    cs:__imp_SysStringLen
0x140019f6f  test    eax, eax
0x140019f71  jz      short loc_140019FEC
0x140019f73  mov     rbx, [rbp+57h+pbstr]
0x140019f77  mov     rcx, rbx; pbstr
0x140019f7a  call    cs:__imp_SysStringLen
0x140019f80  mov     r8d, 2Fh ; '/'; N
0x140019f86  cmp     eax, r8d
0x140019f89  jnz     short loc_140019FEC
0x140019f8b  mov     rdx, rbx; S2
0x140019f8e  lea     rcx, aHttpSchemasMic; "http://schemas.microsoft.com/win/2004/0"...
0x140019f95  call    wmemcmp
0x140019f9a  test    eax, eax
0x140019f9c  jnz     short loc_140019FEC
0x140019f9e  lea     rcx, [rbp+57h+pbstr]
0x140019fa2  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x140019fa7  nop
0x140019fa8  lea     rcx, [rbp+57h+S2]
0x140019fac  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x140019fb1  nop
0x140019fb2  lea     rcx, [rbp+57h+var_48]
0x140019fb6  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x140019fbb  nop
0x140019fbc  lea     rcx, [rbp+57h+Buffer]
0x140019fc0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140019fc5  mov     rax, rsi
0x140019fc8  mov     rcx, [rbp+57h+var_18]
0x140019fcc  xor     rcx, rsp; StackCookie
0x140019fcf  call    __security_check_cookie
0x140019fd4  lea     r11, [rsp+0D0h+var_10]
0x140019fdc  mov     rbx, [r11+20h]
0x140019fe0  mov     rsi, [r11+38h]
0x140019fe4  mov     rsp, r11
0x140019fe7  pop     r14
0x140019fe9  pop     rdi
0x140019fea  pop     rbp
0x140019feb  retn
0x140019fec  lea     rcx, WPP_GLOBAL_Control
0x140019ff3  mov     rax, cs:WPP_GLOBAL_Control
0x140019ffa  cmp     rax, rcx
0x140019ffd  jz      short loc_14001A029
0x140019fff  test    dword ptr [rax+1Ch], 400000h
0x14001a006  jz      short loc_14001A029
0x14001a008  cmp     byte ptr [rax+19h], 2
0x14001a00c  jb      short loc_14001A029
0x14001a00e  mov     edx, 12h
0x14001a013  mov     r9d, 80070057h
0x14001a019  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x14001a020  mov     rcx, [rax+10h]
0x14001a024  call    WPP_SF_d
0x14001a029  mov     [rsp+0D0h+Src], r14; Src
0x14001a02e  mov     [rsp+0D0h+var_A0], 25h ; '%'; unsigned int
0x14001a036  mov     [rsp+0D0h+var_A8], 7Fh; int
0x14001a03e  xor     r9d, r9d; unsigned int
0x14001a041  xor     r8d, r8d; unsigned int
0x14001a044  mov     edx, 80070057h; unsigned int
0x14001a049  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14001a04d  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001a052  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001a059  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14001a05d  call    _CxxThrowException_0
0x14001a063  lea     rcx, WPP_GLOBAL_Control
0x14001a06a  mov     rax, cs:WPP_GLOBAL_Control
0x14001a071  cmp     rax, rcx
0x14001a074  jz      short loc_14001A0A0
0x14001a076  test    dword ptr [rax+1Ch], 400000h
0x14001a07d  jz      short loc_14001A0A0
0x14001a07f  cmp     byte ptr [rax+19h], 2
0x14001a083  jb      short loc_14001A0A0
0x14001a085  mov     edx, 10h
0x14001a08a  mov     r9d, 80070057h
0x14001a090  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x14001a097  mov     rcx, [rax+10h]
0x14001a09b  call    WPP_SF_d
0x14001a0a0  mov     [rsp+0D0h+Src], r14; Src
0x14001a0a5  mov     [rsp+0D0h+var_A0], 25h ; '%'; unsigned int
0x14001a0ad  mov     [rsp+0D0h+var_A8], 71h ; 'q'; int
0x14001a0b5  xor     r9d, r9d; unsigned int
0x14001a0b8  xor     r8d, r8d; unsigned int
0x14001a0bb  mov     edx, 80070057h; unsigned int
0x14001a0c0  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14001a0c4  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001a0c9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001a0d0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14001a0d4  call    _CxxThrowException_0
```
