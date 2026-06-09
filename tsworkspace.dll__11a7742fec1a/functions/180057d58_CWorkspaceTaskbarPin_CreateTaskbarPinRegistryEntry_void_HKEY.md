# CWorkspaceTaskbarPin::CreateTaskbarPinRegistryEntry(void *,HKEY__ *)

- ea: `0x180057d58`
- end: `0x1800581e6`
- name: `?CreateTaskbarPinRegistryEntry@CWorkspaceTaskbarPin@@QEAAJPEAXPEAUHKEY__@@@Z`
- size: `1166`
- prototype: `int(CWorkspaceTaskbarPin *__hidden this, void *, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003708c`

## callees

- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x180057d58`
- `0x180058314`

## import_xrefs

- `ADVAPI32!RegCreateKeyTransactedW` at `0x180057f56`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180057f56`
- `ADVAPI32!RegSetValueExW` at `0x180057ffe`
- `ADVAPI32!RegSetValueExW` at `0x1800580a9`
- `ADVAPI32!RegSetValueExW` at `0x180058156`
- `ADVAPI32!RegSetValueExW` at `0x180057ffe`
- `ADVAPI32!RegSetValueExW` at `0x1800580a9`
- `ADVAPI32!RegSetValueExW` at `0x180058156`

## string_xrefs

- `0x18005809a`: `IconPath`
- `0x180058147`: `RelaunchCommand`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CWorkspaceTaskbarPin::CreateTaskbarPinRegistryEntry(CWorkspaceTaskbarPin *this, void *a2, HKEY a3)
{
  void *hTransaction; // rbx
  __int64 v6; // r14
  __int64 v7; // rsi
  __int64 v8; // rdi
  __int64 v9; // rbx
  int v10; // ebx
  __int64 v11; // r14
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v14; // rbx
  unsigned int v15; // eax
  const WCHAR *v16; // rax
  unsigned int v17; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  const BYTE *v19; // rax
  unsigned int v20; // edi
  unsigned int v21; // eax
  const BYTE *v22; // rax
  unsigned int v23; // edi
  unsigned int v24; // eax
  const BYTE *v25; // rax
  unsigned int v26; // edi
  unsigned int v27; // eax
  int v29; // [rsp+60h] [rbp-58h]
  __int64 v30; // [rsp+68h] [rbp-50h]
  DWORD dwDisposition; // [rsp+C0h] [rbp+8h] BYREF
  void *v32; // [rsp+C8h] [rbp+10h]
  HKEY hKey; // [rsp+D8h] [rbp+20h] BYREF

  v32 = a2;
  v30 = -2;
  hTransaction = a2;
  hKey = 0;
  dwDisposition = 0;
  if ( !*((_BYTE *)this + 177) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 144);
      v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 112);
      v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 80);
      v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 48);
      RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSSSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v8, v7, v6);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 144);
    v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 112);
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 80);
    v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 48);
    RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSSSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v13, v12, v11);
    hTransaction = v32;
  }
  if ( *((_BYTE *)this + 176) )
  {
    v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 48);
    v10 = RegCreateKeyTransactedW(a3, v16, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition, hTransaction, 0);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( v10 > 0 )
          v17 = (unsigned __int16)v10 | 0x80070000;
        else
          v17 = v10;
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          &WPP_7cf14ad00a6c321045f9ab9e92b61e0d_Traceguids,
          CurrentThreadActivityIdPrefix,
          v17);
      }
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      v29 = v10;
    }
    else
    {
      v19 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 80);
      v10 = RegSetValueExW(hKey, L"DisplayName", 0, 1u, v19, 2 * *((_DWORD *)this + 24) + 2);
      if ( v10 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          if ( v10 > 0 )
            v20 = (unsigned __int16)v10 | 0x80070000;
          else
            v20 = v10;
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_7cf14ad00a6c321045f9ab9e92b61e0d_Traceguids, v21, v20);
        }
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        v29 = v10;
      }
      else
      {
        v22 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 112);
        v10 = RegSetValueExW(hKey, L"IconPath", 0, 1u, v22, 2 * *((_DWORD *)this + 32) + 2);
        if ( v10 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v10 > 0 )
              v23 = (unsigned __int16)v10 | 0x80070000;
            else
              v23 = v10;
            v24 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              &WPP_7cf14ad00a6c321045f9ab9e92b61e0d_Traceguids,
              v24,
              v23);
          }
          if ( v10 > 0 )
            v10 = (unsigned __int16)v10 | 0x80070000;
          v29 = v10;
        }
        else
        {
          v25 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 144);
          v10 = RegSetValueExW(hKey, L"RelaunchCommand", 0, 1u, v25, 2 * *((_DWORD *)this + 40) + 2);
          if ( !v10 )
            return 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v10 > 0 )
              v26 = (unsigned __int16)v10 | 0x80070000;
            else
              v26 = v10;
            v27 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              &WPP_7cf14ad00a6c321045f9ab9e92b61e0d_Traceguids,
              v27,
              v26);
          }
          if ( v10 > 0 )
            v10 = (unsigned __int16)v10 | 0x80070000;
          v29 = v10;
        }
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_7cf14ad00a6c321045f9ab9e92b61e0d_Traceguids,
        v15,
        -2147019873);
    }
    v10 = -2147019873;
    v29 = -2147019873;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180057d58  mov     rax, rsp
0x180057d5b  mov     [rax+10h], rdx
0x180057d5f  push    rbx
0x180057d60  push    rsi
0x180057d61  push    rdi
0x180057d62  push    r12
0x180057d64  push    r13
0x180057d66  push    r14
0x180057d68  push    r15
0x180057d6a  sub     rsp, 80h
0x180057d71  mov     qword ptr [rax-50h], 0FFFFFFFFFFFFFFFEh
0x180057d79  mov     r12, r8
0x180057d7c  mov     rbx, rdx
0x180057d7f  mov     r13, rcx
0x180057d82  xor     esi, esi
0x180057d84  mov     [rax+20h], rsi
0x180057d88  mov     [rax+8], esi
0x180057d8b  cmp     [rcx+0B1h], sil
0x180057d92  jnz     loc_180057E24
0x180057d98  lea     r15, WPP_GLOBAL_Control
0x180057d9f  mov     rax, cs:WPP_GLOBAL_Control
0x180057da6  cmp     rax, r15
0x180057da9  jz      short loc_180057E1D
0x180057dab  test    byte ptr [rax+1Ch], 1
0x180057daf  jz      short loc_180057E1D
0x180057db1  cmp     byte ptr [rax+19h], 4
0x180057db5  jb      short loc_180057E1D
0x180057db7  add     rcx, 90h
0x180057dbe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180057dc3  mov     r14, rax
0x180057dc6  lea     rcx, [r13+70h]
0x180057dca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180057dcf  mov     rsi, rax
0x180057dd2  lea     rcx, [r13+50h]
0x180057dd6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180057ddb  mov     rdi, rax
0x180057dde  lea     rcx, [r13+30h]
0x180057de2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180057de7  mov     rbx, rax
0x180057dea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180057def  mov     edx, 0Bh
0x180057df4  mov     [rsp+0B8h+phkResult], r14; __int64
0x180057df9  mov     [rsp+0B8h+lpSecurityAttributes], rsi; __int64
0x180057dfe  mov     qword ptr [rsp+0B8h+samDesired], rdi; __int64
0x180057e03  mov     qword ptr [rsp+0B8h+dwOptions], rbx; __int64
0x180057e08  mov     r9d, eax
0x180057e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180057e12  mov     rcx, [rcx+10h]; LoggerHandle
0x180057e16  call    WPP_SF_DSSSS
0x180057e1b  xor     esi, esi
0x180057e1d  mov     ebx, esi
0x180057e1f  jmp     loc_1800581D1
0x180057e24  lea     r15, WPP_GLOBAL_Control
0x180057e2b  mov     rax, cs:WPP_GLOBAL_Control
0x180057e32  cmp     rax, r15
0x180057e35  jz      short loc_180057EB1
0x180057e37  test    byte ptr [rax+1Ch], 1
0x180057e3b  jz      short loc_180057EB1
0x180057e3d  cmp     byte ptr [rax+19h], 4
0x180057e41  jb      short loc_180057EB1
0x180057e43  add     rcx, 90h
0x180057e4a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180057e4f  mov     r14, rax
0x180057e52  lea     rcx, [r13+70h]
0x180057e56  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180057e5b  mov     rsi, rax
0x180057e5e  lea     rcx, [r13+50h]
0x180057e62  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180057e67  mov     rdi, rax
0x180057e6a  lea     rcx, [r13+30h]
0x180057e6e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180057e73  mov     rbx, rax
0x180057e76  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180057e7b  mov     edx, 0Ch
0x180057e80  mov     [rsp+0B8h+phkResult], r14; __int64
0x180057e85  mov     [rsp+0B8h+lpSecurityAttributes], rsi; __int64
0x180057e8a  mov     qword ptr [rsp+0B8h+samDesired], rdi; __int64
0x180057e8f  mov     qword ptr [rsp+0B8h+dwOptions], rbx; __int64
0x180057e94  mov     r9d, eax
0x180057e97  mov     rcx, cs:WPP_GLOBAL_Control
0x180057e9e  mov     rcx, [rcx+10h]; LoggerHandle
0x180057ea2  call    WPP_SF_DSSSS
0x180057ea7  mov     rbx, [rsp+0B8h+arg_8]
0x180057eaf  xor     esi, esi
0x180057eb1  cmp     [r13+0B0h], sil
0x180057eb8  jnz     short loc_180057F0C
0x180057eba  mov     rax, cs:WPP_GLOBAL_Control
0x180057ec1  cmp     rax, r15
0x180057ec4  jz      short loc_180057EFE
0x180057ec6  test    byte ptr [rax+1Ch], 8
0x180057eca  jz      short loc_180057EFE
0x180057ecc  cmp     byte ptr [rax+19h], 2
0x180057ed0  jb      short loc_180057EFE
0x180057ed2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180057ed7  mov     edx, 0Dh
0x180057edc  mov     [rsp+0B8h+dwOptions], 8007139Fh
0x180057ee4  mov     r9d, eax
0x180057ee7  lea     r8, WPP_7cf14ad00a6c321045f9ab9e92b61e0d_Traceguids
0x180057eee  mov     rcx, cs:WPP_GLOBAL_Control
0x180057ef5  mov     rcx, [rcx+10h]
0x180057ef9  call    WPP_SF_Dd
0x180057efe  mov     ebx, 8007139Fh
0x180057f03  mov     [rsp+0B8h+var_58], ebx
0x180057f07  jmp     loc_1800581D1
0x180057f0c  lea     rcx, [r13+30h]
0x180057f10  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180057f15  mov     [rsp+0B8h+pExtendedParemeter], rsi; pExtendedParemeter
0x180057f1a  mov     [rsp+0B8h+hTransaction], rbx; hTransaction
0x180057f1f  lea     rcx, [rsp+0B8h+dwDisposition]
0x180057f27  mov     [rsp+0B8h+lpdwDisposition], rcx; lpdwDisposition
0x180057f2c  lea     rcx, [rsp+0B8h+hKey]
0x180057f34  mov     [rsp+0B8h+phkResult], rcx; phkResult
0x180057f39  mov     [rsp+0B8h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180057f3e  mov     [rsp+0B8h+samDesired], 20006h; samDesired
0x180057f46  mov     [rsp+0B8h+dwOptions], esi; dwOptions
0x180057f4a  xor     r9d, r9d; lpClass
0x180057f4d  xor     r8d, r8d; Reserved
0x180057f50  mov     rdx, rax; lpSubKey
0x180057f53  mov     rcx, r12; hKey
0x180057f56  call    cs:__imp_RegCreateKeyTransactedW
0x180057f5c  mov     ebx, eax
0x180057f5e  test    eax, eax
0x180057f60  jz      short loc_180057FC9
0x180057f62  mov     rax, cs:WPP_GLOBAL_Control
0x180057f69  cmp     rax, r15
0x180057f6c  jz      short loc_180057FB3
0x180057f6e  test    byte ptr [rax+1Ch], 8
0x180057f72  jz      short loc_180057FB3
0x180057f74  cmp     byte ptr [rax+19h], 2
0x180057f78  jb      short loc_180057FB3
0x180057f7a  test    ebx, ebx
0x180057f7c  jg      short loc_180057F82
0x180057f7e  mov     edi, ebx
0x180057f80  jmp     short loc_180057F8B
0x180057f82  movzx   edi, bx
0x180057f85  or      edi, 80070000h
0x180057f8b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180057f90  mov     edx, 0Eh
0x180057f95  mov     [rsp+0B8h+dwOptions], edi
0x180057f99  mov     r9d, eax
0x180057f9c  lea     r8, WPP_7cf14ad00a6c321045f9ab9e92b61e0d_Traceguids
0x180057fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180057faa  mov     rcx, [rcx+10h]
0x180057fae  call    WPP_SF_Dd
0x180057fb3  test    ebx, ebx
0x180057fb5  jle     short loc_180057FC0
0x180057fb7  movzx   ebx, bx
0x180057fba  or      ebx, 80070000h
0x180057fc0  mov     [rsp+0B8h+var_58], ebx
0x180057fc4  jmp     loc_1800581D1
0x180057fc9  lea     rcx, [r13+50h]
0x180057fcd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180057fd2  mov     edx, [r13+60h]
0x180057fd6  lea     edx, ds:2[rdx*2]
0x180057fdd  mov     [rsp+0B8h+samDesired], edx; cbData
0x180057fe1  mov     qword ptr [rsp+0B8h+dwOptions], rax; lpData
0x180057fe6  mov     r9d, 1; dwType
0x180057fec  xor     r8d, r8d; Reserved
0x180057fef  lea     rdx, aDisplayname; "DisplayName"
0x180057ff6  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180057ffe  call    cs:__imp_RegSetValueExW
0x180058004  mov     ebx, eax
0x180058006  test    eax, eax
0x180058008  jz      short loc_180058071
0x18005800a  mov     rax, cs:WPP_GLOBAL_Control
0x180058011  cmp     rax, r15
0x180058014  jz      short loc_18005805B
0x180058016  test    byte ptr [rax+1Ch], 8
0x18005801a  jz      short loc_18005805B
0x18005801c  cmp     byte ptr [rax+19h], 2
0x180058020  jb      short loc_18005805B
0x180058022  test    ebx, ebx
0x180058024  jg      short loc_18005802A
0x180058026  mov     edi, ebx
0x180058028  jmp     short loc_180058033
0x18005802a  movzx   edi, bx
0x18005802d  or      edi, 80070000h
0x180058033  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180058038  mov     edx, 0Fh
0x18005803d  mov     [rsp+0B8h+dwOptions], edi
0x180058041  mov     r9d, eax
0x180058044  lea     r8, WPP_7cf14ad00a6c321045f9ab9e92b61e0d_Traceguids
0x18005804b  mov     rcx, cs:WPP_GLOBAL_Control
0x180058052  mov     rcx, [rcx+10h]
0x180058056  call    WPP_SF_Dd
0x18005805b  test    ebx, ebx
0x18005805d  jle     short loc_180058068
0x18005805f  movzx   ebx, bx
0x180058062  or      ebx, 80070000h
0x180058068  mov     [rsp+0B8h+var_58], ebx
0x18005806c  jmp     loc_1800581D1
0x180058071  lea     rcx, [r13+70h]
0x180058075  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005807a  mov     edx, [r13+80h]
0x180058081  lea     edx, ds:2[rdx*2]
0x180058088  mov     [rsp+0B8h+samDesired], edx; cbData
0x18005808c  mov     qword ptr [rsp+0B8h+dwOptions], rax; lpData
0x180058091  mov     r9d, 1; dwType
0x180058097  xor     r8d, r8d; Reserved
0x18005809a  lea     rdx, aIconpath; "IconPath"
0x1800580a1  mov     rcx, [rsp+0B8h+hKey]; hKey
0x1800580a9  call    cs:__imp_RegSetValueExW
0x1800580af  mov     ebx, eax
0x1800580b1  test    eax, eax
0x1800580b3  jz      short loc_18005811C
0x1800580b5  mov     rax, cs:WPP_GLOBAL_Control
0x1800580bc  cmp     rax, r15
0x1800580bf  jz      short loc_180058106
0x1800580c1  test    byte ptr [rax+1Ch], 8
0x1800580c5  jz      short loc_180058106
0x1800580c7  cmp     byte ptr [rax+19h], 2
0x1800580cb  jb      short loc_180058106
0x1800580cd  test    ebx, ebx
0x1800580cf  jg      short loc_1800580D5
0x1800580d1  mov     edi, ebx
0x1800580d3  jmp     short loc_1800580DE
0x1800580d5  movzx   edi, bx
0x1800580d8  or      edi, 80070000h
0x1800580de  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800580e3  mov     edx, 10h
0x1800580e8  mov     [rsp+0B8h+dwOptions], edi
0x1800580ec  mov     r9d, eax
0x1800580ef  lea     r8, WPP_7cf14ad00a6c321045f9ab9e92b61e0d_Traceguids
0x1800580f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800580fd  mov     rcx, [rcx+10h]
0x180058101  call    WPP_SF_Dd
0x180058106  test    ebx, ebx
0x180058108  jle     short loc_180058113
0x18005810a  movzx   ebx, bx
0x18005810d  or      ebx, 80070000h
0x180058113  mov     [rsp+0B8h+var_58], ebx
0x180058117  jmp     loc_1800581D1
0x18005811c  lea     rbx, [r13+90h]
0x180058123  mov     rcx, rbx
0x180058126  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005812b  mov     edx, [rbx+10h]
0x18005812e  lea     edx, ds:2[rdx*2]
0x180058135  mov     [rsp+0B8h+samDesired], edx; cbData
0x180058139  mov     qword ptr [rsp+0B8h+dwOptions], rax; lpData
0x18005813e  mov     r9d, 1; dwType
0x180058144  xor     r8d, r8d; Reserved
0x180058147  lea     rdx, aRelaunchcomman; "RelaunchCommand"
0x18005814e  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180058156  call    cs:__imp_RegSetValueExW
0x18005815c  mov     ebx, eax
0x18005815e  test    eax, eax
0x180058160  jz      short loc_1800581C6
0x180058162  mov     rax, cs:WPP_GLOBAL_Control
0x180058169  cmp     rax, r15
0x18005816c  jz      short loc_1800581B3
0x18005816e  test    byte ptr [rax+1Ch], 8
0x180058172  jz      short loc_1800581B3
0x180058174  cmp     byte ptr [rax+19h], 2
0x180058178  jb      short loc_1800581B3
0x18005817a  test    ebx, ebx
0x18005817c  jg      short loc_180058182
0x18005817e  mov     edi, ebx
0x180058180  jmp     short loc_18005818B
0x180058182  movzx   edi, bx
0x180058185  or      edi, 80070000h
0x18005818b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180058190  mov     edx, 11h
0x180058195  mov     [rsp+0B8h+dwOptions], edi
0x180058199  mov     r9d, eax
0x18005819c  lea     r8, WPP_7cf14ad00a6c321045f9ab9e92b61e0d_Traceguids
0x1800581a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800581aa  mov     rcx, [rcx+10h]
0x1800581ae  call    WPP_SF_Dd
0x1800581b3  test    ebx, ebx
0x1800581b5  jle     short loc_1800581C0
0x1800581b7  movzx   ebx, bx
0x1800581ba  or      ebx, 80070000h
0x1800581c0  mov     [rsp+0B8h+var_58], ebx
0x1800581c4  jmp     short loc_1800581D1
0x1800581c6  jmp     loc_180057E1D
0x1800581cb  jmp     short $+2
0x1800581cd  mov     ebx, [rsp+0B8h+var_58]
0x1800581d1  mov     eax, ebx
0x1800581d3  add     rsp, 80h
0x1800581da  pop     r15
0x1800581dc  pop     r14
0x1800581de  pop     r13
0x1800581e0  pop     r12
0x1800581e2  pop     rdi
0x1800581e3  pop     rsi
0x1800581e4  pop     rbx
0x1800581e5  retn
```
