# INTERNET_HANDLE_OBJECT::SetProxyInfo(ulong,char const *,char const *)

- ea: `0x18002be34`
- end: `0x18002c2c8`
- name: `?SetProxyInfo@INTERNET_HANDLE_OBJECT@@QEAAJKPEBD0@Z`
- size: `1172`
- prototype: `int(INTERNET_HANDLE_OBJECT *__hidden this, unsigned int, const char *, const char *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002bb10`
- `0x1800610f0`

## callees

- `0x18002be34`
- `0x1800e96f0`
- `0x180100a68`
- `0x180110240`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x18016e4b0`
- `0x18019110c`
- `0x1801d46cc`
- `0x1801e1790`
- `0x1801e3c24`
- `0x1801e3c78`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bf0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bf0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bede`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bede`
- `WINHTTP!WinHttpCreateProxyManager` at `0x18002bfe9`
- `WINHTTP!WinHttpCreateProxyManager` at `0x18002c023`
- `WINHTTP!WinHttpCreateProxyManager` at `0x18002bfe9`
- `WINHTTP!WinHttpCreateProxyManager` at `0x18002c023`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bf19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bf30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bf19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bf30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfd1`

## pseudocode

```c
__int64 __fastcall INTERNET_HANDLE_OBJECT::SetProxyInfo(
        INTERNET_HANDLE_OBJECT *this,
        unsigned int a2,
        const char *a3,
        const char *a4)
{
  signed int ProxyOptions; // edi
  struct WininetGlobalSettingsFiltered *v9; // rbx
  unsigned int v10; // ecx
  struct IProxyResolver *v11; // rsi
  __int64 v12; // rcx
  struct tagProxyOptions *v14; // rcx
  int v15; // eax
  int v16; // eax
  unsigned int v17; // eax
  int v18; // edx
  int v19; // ecx
  int v20; // r8d
  unsigned int v21; // esi
  unsigned int v22; // esi
  int v23; // eax
  struct WininetGlobalSettingsFiltered *v24; // [rsp+58h] [rbp-81h] BYREF
  struct IProxyResolver *v25; // [rsp+60h] [rbp-79h] BYREF
  struct tagProxyOptions *v26; // [rsp+68h] [rbp-71h] BYREF
  _DWORD v27[4]; // [rsp+70h] [rbp-69h] BYREF
  int v28; // [rsp+80h] [rbp-59h] BYREF
  int v29; // [rsp+84h] [rbp-55h]
  _BYTE v30[16]; // [rsp+88h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-41h]
  LPVOID v32; // [rsp+A0h] [rbp-39h]

  if ( (xmmword_180266B60 & 0x40) != 0 )
  {
    v17 = (unsigned int)InternetMapOpenType(a2);
    WPP_SF_sdqsqs(v19, v18, v20, v17, a2, (__int64)a3, (__int64)a3, (__int64)a4, (__int64)a4);
  }
  ProxyOptions = 0;
  v9 = 0;
  v25 = 0;
  v24 = 0;
  v26 = 0;
  memset_0(&v28, 0, 0x70u);
  v27[0] = 0;
  if ( !a2 )
  {
    v11 = GlobalProxyInfo;
    if ( GlobalProxyInfo )
      (*(void (__fastcall **)(struct IProxyResolver *))(*(_QWORD *)GlobalProxyInfo + 8LL))(GlobalProxyInfo);
    v25 = v11;
    goto LABEL_7;
  }
  v21 = a2 - 1;
  if ( v21 )
  {
    v22 = v21 - 2;
    if ( v22 )
    {
      if ( v22 != 1 )
      {
        ProxyOptions = -2147024809;
        goto LABEL_10;
      }
      v23 = WininetGlobalSettingsFiltered::CreateInstance(v10, &v24);
      v9 = v24;
      ProxyOptions = v23;
      if ( v23 >= 0 )
      {
        AutoInterface<IUnknown>::operator=(&v25, v24);
LABEL_7:
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
        v12 = *((_QWORD *)this + 36);
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        *((_QWORD *)this + 36) = v25;
        v25 = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
      }
    }
    else
    {
      v15 = WinHttpCreateProxyManager(13, 0, GlobalProxyList, &v25);
      ProxyOptions = v15;
      if ( v15 > 0 )
        ProxyOptions = (unsigned __int16)v15 | 0x80070000;
      if ( ProxyOptions >= 0 )
      {
        if ( !a3 )
        {
          ProxyOptions = -2147024809;
          goto LABEL_10;
        }
        ProxyOptions = GetProxyOptions(&v26);
        if ( ProxyOptions >= 0 )
        {
          ProxyOptions = (*(__int64 (__fastcall **)(struct IProxyResolver *, struct tagProxyOptions *))(*(_QWORD *)v25 + 104LL))(
                           v25,
                           v26);
          if ( ProxyOptions >= 0 )
          {
            memset_0(v30, 0, 0x68u);
            v28 = 112;
            v29 = 3;
            ProxyOptions = InetNewStringAtoW(a3, -1);
            if ( ProxyOptions >= 0 )
            {
              if ( !a4 || (ProxyOptions = InetNewStringAtoW(a4, -1), ProxyOptions >= 0) )
              {
                ProxyOptions = (*(__int64 (__fastcall **)(struct IProxyResolver *, int *, __int64, __int64, _DWORD *))(*(_QWORD *)v25 + 40LL))(
                                 v25,
                                 &v28,
                                 1,
                                 1,
                                 v27);
                if ( ProxyOptions >= 0 )
                  goto LABEL_7;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v16 = WinHttpCreateProxyManager(13, 0, GlobalProxyList, &v25);
    ProxyOptions = v16;
    if ( v16 > 0 )
      ProxyOptions = (unsigned __int16)v16 | 0x80070000;
    if ( ProxyOptions >= 0 )
    {
      ProxyOptions = GetProxyOptions(&v26);
      if ( ProxyOptions >= 0 )
      {
        ProxyOptions = (*(__int64 (__fastcall **)(struct IProxyResolver *, struct tagProxyOptions *))(*(_QWORD *)v25 + 104LL))(
                         v25,
                         v26);
        if ( ProxyOptions >= 0 )
        {
          memset_0(v30, 0, 0x68u);
          v28 = 112;
          v29 = 1;
          ProxyOptions = (*(__int64 (__fastcall **)(struct IProxyResolver *, int *, __int64, __int64, _DWORD *))(*(_QWORD *)v25 + 40LL))(
                           v25,
                           &v28,
                           1,
                           1,
                           v27);
          if ( ProxyOptions >= 0 )
            goto LABEL_7;
        }
      }
    }
  }
LABEL_10:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v32 )
  {
    CoTaskMemFree(v32);
    v32 = 0;
  }
  if ( (xmmword_180266B60 & 0x40) != 0 )
    WPP_SF_d(1030, 43, WPP_a85fccec657a30c16cbc767298893445_Traceguids, (unsigned int)ProxyOptions);
  if ( v26 )
  {
    if ( (xmmword_180266B60 & 0x20) != 0 )
      WPP_SF_q(1029, 17, WPP_6ab49dfb88213ef993fa13ad0186785e_Traceguids, &v26);
    v14 = v26;
    v26 = 0;
    if ( v14 )
      CoTaskMemFree(v14);
    if ( (xmmword_180266B60 & 0x20) != 0 )
      WPP_SF_(1029, 18, WPP_6ab49dfb88213ef993fa13ad0186785e_Traceguids);
  }
  if ( v9 )
    (*(void (__fastcall **)(struct WininetGlobalSettingsFiltered *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v25 )
    (*(void (__fastcall **)(struct IProxyResolver *))(*(_QWORD *)v25 + 16LL))(v25);
  return (unsigned int)ProxyOptions;
}

```

## disassembly

```asm
0x18002be34  push    rbp
0x18002be36  push    rbx
0x18002be37  push    rsi
0x18002be38  push    rdi
0x18002be39  push    r13
0x18002be3b  push    r14
0x18002be3d  push    r15
0x18002be3f  lea     rbp, [rsp-27h]
0x18002be44  sub     rsp, 100h
0x18002be4b  mov     rax, cs:__security_cookie
0x18002be52  xor     rax, rsp
0x18002be55  mov     [rbp+57h+var_40], rax
0x18002be59  mov     r14, r9
0x18002be5c  mov     r15, r8
0x18002be5f  mov     esi, edx
0x18002be61  mov     r13, rcx
0x18002be64  test    byte ptr cs:xmmword_180266B60, 40h
0x18002be6b  jnz     loc_18002C04D
0x18002be71  xor     edi, edi
0x18002be73  lea     rcx, [rbp+57h+var_B0]; void *
0x18002be77  xor     ebx, ebx
0x18002be79  mov     [rsp+130h+var_DC], edi
0x18002be7d  xor     edx, edx; Val
0x18002be7f  mov     [rbp+57h+var_D0], rdi
0x18002be83  mov     [rsp+130h+var_D8], rbx
0x18002be88  lea     r8d, [rdi+70h]; Size
0x18002be8c  mov     [rbp+57h+var_C8], rbx
0x18002be90  call    memset_0
0x18002be95  mov     [rbp+57h+var_C0], ebx
0x18002be98  test    esi, esi
0x18002be9a  jnz     loc_18002C079
0x18002bea0  mov     rsi, cs:GlobalProxyInfo
0x18002bea7  test    rsi, rsi
0x18002beaa  jz      short loc_18002BED0
0x18002beac  mov     rax, [rsi]
0x18002beaf  mov     rcx, rsi
0x18002beb2  mov     rax, [rax+8]
0x18002beb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bebb  mov     rcx, [rbp+57h+var_D0]
0x18002bebf  test    rcx, rcx
0x18002bec2  jz      short loc_18002BED0
0x18002bec4  mov     rax, [rcx]
0x18002bec7  mov     rax, [rax+10h]
0x18002becb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bed0  mov     [rbp+57h+var_D0], rsi
0x18002bed4  lea     rsi, [r13+128h]
0x18002bedb  mov     rcx, rsi; lpCriticalSection
0x18002bede  call    cs:__imp_EnterCriticalSection
0x18002bee4  mov     rcx, [r13+120h]
0x18002beeb  test    rcx, rcx
0x18002beee  jnz     loc_18002C269
0x18002bef4  mov     rax, [rbp+57h+var_D0]
0x18002bef8  mov     rcx, rsi; lpCriticalSection
0x18002befb  mov     [r13+120h], rax
0x18002bf02  mov     [rbp+57h+var_D0], 0
0x18002bf0a  call    cs:__imp_LeaveCriticalSection
0x18002bf10  mov     rcx, [rbp+57h+pv]; pv
0x18002bf14  test    rcx, rcx
0x18002bf17  jz      short loc_18002BF27
0x18002bf19  call    cs:__imp_CoTaskMemFree
0x18002bf1f  mov     [rbp+57h+pv], 0
0x18002bf27  mov     rcx, [rbp+57h+var_90]; pv
0x18002bf2b  test    rcx, rcx
0x18002bf2e  jz      short loc_18002BF3E
0x18002bf30  call    cs:__imp_CoTaskMemFree
0x18002bf36  mov     [rbp+57h+var_90], 0
0x18002bf3e  test    byte ptr cs:xmmword_180266B60, 40h
0x18002bf45  jnz     loc_18002C27A
0x18002bf4b  cmp     [rbp+57h+var_C8], 0
0x18002bf50  jnz     short loc_18002BF90
0x18002bf52  test    rbx, rbx
0x18002bf55  jnz     loc_18002C2B4
0x18002bf5b  mov     rcx, [rbp+57h+var_D0]
0x18002bf5f  test    rcx, rcx
0x18002bf62  jz      short loc_18002BF70
0x18002bf64  mov     rdx, [rcx]
0x18002bf67  mov     rax, [rdx+10h]
0x18002bf6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf70  mov     eax, edi
0x18002bf72  mov     rcx, [rbp+57h+var_40]
0x18002bf76  xor     rcx, rsp; StackCookie
0x18002bf79  call    __security_check_cookie
0x18002bf7e  add     rsp, 100h
0x18002bf85  pop     r15
0x18002bf87  pop     r14
0x18002bf89  pop     r13
0x18002bf8b  pop     rdi
0x18002bf8c  pop     rsi
0x18002bf8d  pop     rbx
0x18002bf8e  pop     rbp
0x18002bf8f  retn
0x18002bf90  test    byte ptr cs:xmmword_180266B60, 20h
0x18002bf97  mov     esi, 405h
0x18002bf9c  jnz     loc_18002C298
0x18002bfa2  mov     rcx, [rbp+57h+var_C8]; pv
0x18002bfa6  mov     [rbp+57h+var_C8], 0
0x18002bfae  test    rcx, rcx
0x18002bfb1  jnz     short loc_18002BFD1
0x18002bfb3  test    byte ptr cs:xmmword_180266B60, 20h
0x18002bfba  jz      short loc_18002BF52
0x18002bfbc  mov     edx, 12h
0x18002bfc1  lea     r8, WPP_6ab49dfb88213ef993fa13ad0186785e_Traceguids
0x18002bfc8  mov     ecx, esi
0x18002bfca  call    WPP_SF_
0x18002bfcf  jmp     short loc_18002BF52
0x18002bfd1  call    cs:__imp_CoTaskMemFree
0x18002bfd7  jmp     short loc_18002BFB3
0x18002bfd9  mov     r8, cs:GlobalProxyList
0x18002bfe0  lea     r9, [rbp+57h+var_D0]
0x18002bfe4  xor     edx, edx
0x18002bfe6  lea     ecx, [rdx+0Dh]
0x18002bfe9  call    cs:__imp_WinHttpCreateProxyManager
0x18002bfef  mov     edi, eax
0x18002bff1  test    eax, eax
0x18002bff3  jle     short loc_18002BFFE
0x18002bff5  movzx   edi, ax
0x18002bff8  or      edi, 80070000h
0x18002bffe  test    edi, edi
0x18002c000  jns     loc_18002C0D1
0x18002c006  mov     [rsp+130h+var_DC], 6B5h
0x18002c00e  jmp     loc_18002BF10
0x18002c013  mov     r8, cs:GlobalProxyList
0x18002c01a  lea     r9, [rbp+57h+var_D0]
0x18002c01e  xor     edx, edx
0x18002c020  lea     ecx, [rdx+0Dh]
0x18002c023  call    cs:__imp_WinHttpCreateProxyManager
0x18002c029  mov     edi, eax
0x18002c02b  test    eax, eax
0x18002c02d  jle     short loc_18002C038
0x18002c02f  movzx   edi, ax
0x18002c032  or      edi, 80070000h
0x18002c038  test    edi, edi
0x18002c03a  jns     loc_18002C1CF
0x18002c040  mov     [rsp+130h+var_DC], 69Dh
0x18002c048  jmp     loc_18002BF10
0x18002c04d  mov     ecx, esi; unsigned int
0x18002c04f  call    ?InternetMapOpenType@@YAPEBDK@Z; InternetMapOpenType(ulong)
0x18002c054  mov     [rsp+130h+var_F0], r14
0x18002c059  mov     r9, rax
0x18002c05c  mov     [rsp+130h+var_F8], r14
0x18002c061  mov     [rsp+130h+var_100], r15
0x18002c066  mov     [rsp+130h+var_108], r15
0x18002c06b  mov     dword ptr [rsp+130h+var_110], esi
0x18002c06f  call    WPP_SF_sdqsqs
0x18002c074  jmp     loc_18002BE71
0x18002c079  sub     esi, 1
0x18002c07c  jz      short loc_18002C013
0x18002c07e  sub     esi, 2
0x18002c081  jz      loc_18002BFD9
0x18002c087  cmp     esi, 1
0x18002c08a  jz      short loc_18002C09E
0x18002c08c  mov     edi, 80070057h
0x18002c091  mov     [rsp+130h+var_DC], 6DCh
0x18002c099  jmp     loc_18002BF10
0x18002c09e  lea     rdx, [rsp+130h+var_D8]; struct WininetGlobalSettingsFiltered **
0x18002c0a3  call    ?CreateInstance@WininetGlobalSettingsFiltered@@SAJKPEAPEAV1@@Z; WininetGlobalSettingsFiltered::CreateInstance(ulong,WininetGlobalSettingsFiltered * *)
0x18002c0a8  mov     rbx, [rsp+130h+var_D8]
0x18002c0ad  mov     edi, eax
0x18002c0af  test    eax, eax
0x18002c0b1  jns     short loc_18002C0C0
0x18002c0b3  mov     [rsp+130h+var_DC], 6D5h
0x18002c0bb  jmp     loc_18002BF10
0x18002c0c0  mov     rdx, rbx
0x18002c0c3  lea     rcx, [rbp+57h+var_D0]
0x18002c0c7  call    ??4?$AutoInterface@UIUnknown@@@@QEAAXPEAUIUnknown@@@Z; AutoInterface<IUnknown>::operator=(IUnknown *)
0x18002c0cc  jmp     loc_18002BED4
0x18002c0d1  test    r15, r15
0x18002c0d4  jnz     short loc_18002C0E8
0x18002c0d6  mov     edi, 80070057h
0x18002c0db  mov     [rsp+130h+var_DC], 6B6h
0x18002c0e3  jmp     loc_18002BF10
0x18002c0e8  lea     rcx, [rbp+57h+var_C8]; struct tagProxyOptions **
0x18002c0ec  call    ?GetProxyOptions@@YAJPEAPEAUtagProxyOptions@@@Z; GetProxyOptions(tagProxyOptions * *)
0x18002c0f1  mov     edi, eax
0x18002c0f3  test    eax, eax
0x18002c0f5  jns     short loc_18002C104
0x18002c0f7  mov     [rsp+130h+var_DC], 6B8h
0x18002c0ff  jmp     loc_18002BF10
0x18002c104  mov     rcx, [rbp+57h+var_D0]
0x18002c108  mov     rdx, [rbp+57h+var_C8]
0x18002c10c  mov     rax, [rcx]
0x18002c10f  mov     rax, [rax+68h]
0x18002c113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c118  mov     edi, eax
0x18002c11a  test    eax, eax
0x18002c11c  jns     short loc_18002C12B
0x18002c11e  mov     [rsp+130h+var_DC], 6BAh
0x18002c126  jmp     loc_18002BF10
0x18002c12b  xor     edx, edx; Val
0x18002c12d  lea     rcx, [rbp+57h+var_A8]; void *
0x18002c131  lea     r8d, [rdx+68h]; Size
0x18002c135  call    memset_0
0x18002c13a  or      esi, 0FFFFFFFFh
0x18002c13d  mov     [rbp+57h+var_B0], 70h ; 'p'
0x18002c144  mov     edx, esi; cbMultiByte
0x18002c146  mov     [rbp+57h+var_AC], 3
0x18002c14d  lea     r8, [rbp+57h+pv]
0x18002c151  mov     rcx, r15; lpMultiByteStr
0x18002c154  call    InetNewStringAtoW
0x18002c159  mov     edi, eax
0x18002c15b  test    eax, eax
0x18002c15d  jns     short loc_18002C16C
0x18002c15f  mov     [rsp+130h+var_DC], 6C4h
0x18002c167  jmp     loc_18002BF10
0x18002c16c  test    r14, r14
0x18002c16f  jz      short loc_18002C192
0x18002c171  lea     r8, [rbp+57h+var_90]
0x18002c175  mov     edx, esi; cbMultiByte
0x18002c177  mov     rcx, r14; lpMultiByteStr
0x18002c17a  call    InetNewStringAtoW
0x18002c17f  mov     edi, eax
0x18002c181  test    eax, eax
0x18002c183  jns     short loc_18002C192
0x18002c185  mov     [rsp+130h+var_DC], 6CBh
0x18002c18d  jmp     loc_18002BF10
0x18002c192  mov     rcx, [rbp+57h+var_D0]
0x18002c196  lea     rdx, [rbp+57h+var_C0]
0x18002c19a  mov     r8d, 1
0x18002c1a0  mov     [rsp+130h+var_110], rdx
0x18002c1a5  mov     r9d, r8d
0x18002c1a8  lea     rdx, [rbp+57h+var_B0]
0x18002c1ac  mov     rax, [rcx]
0x18002c1af  mov     rax, [rax+28h]
0x18002c1b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1b8  mov     edi, eax
0x18002c1ba  test    eax, eax
0x18002c1bc  jns     loc_18002BED4
0x18002c1c2  mov     [rsp+130h+var_DC], 6CEh
0x18002c1ca  jmp     loc_18002BF10
0x18002c1cf  lea     rcx, [rbp+57h+var_C8]; struct tagProxyOptions **
0x18002c1d3  call    ?GetProxyOptions@@YAJPEAPEAUtagProxyOptions@@@Z; GetProxyOptions(tagProxyOptions * *)
0x18002c1d8  mov     edi, eax
0x18002c1da  test    eax, eax
0x18002c1dc  jns     short loc_18002C1EB
0x18002c1de  mov     [rsp+130h+var_DC], 69Fh
0x18002c1e6  jmp     loc_18002BF10
0x18002c1eb  mov     rcx, [rbp+57h+var_D0]
0x18002c1ef  mov     rdx, [rbp+57h+var_C8]
0x18002c1f3  mov     rax, [rcx]
0x18002c1f6  mov     rax, [rax+68h]
0x18002c1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1ff  mov     edi, eax
0x18002c201  test    eax, eax
0x18002c203  jns     short loc_18002C212
0x18002c205  mov     [rsp+130h+var_DC], 6A1h
0x18002c20d  jmp     loc_18002BF10
0x18002c212  xor     edx, edx; Val
0x18002c214  lea     rcx, [rbp+57h+var_A8]; void *
0x18002c218  lea     r8d, [rdx+68h]; Size
0x18002c21c  call    memset_0
0x18002c221  mov     rcx, [rbp+57h+var_D0]
0x18002c225  lea     rdx, [rbp+57h+var_C0]
0x18002c229  mov     r8d, 1
0x18002c22f  mov     [rbp+57h+var_B0], 70h ; 'p'
0x18002c236  mov     [rbp+57h+var_AC], r8d
0x18002c23a  mov     r9d, r8d
0x18002c23d  mov     [rsp+130h+var_110], rdx
0x18002c242  lea     rdx, [rbp+57h+var_B0]
0x18002c246  mov     rax, [rcx]
0x18002c249  mov     rax, [rax+28h]
0x18002c24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c252  mov     edi, eax
0x18002c254  test    eax, eax
0x18002c256  jns     loc_18002BED4
0x18002c25c  mov     [rsp+130h+var_DC], 6A7h
0x18002c264  jmp     loc_18002BF10
0x18002c269  mov     rax, [rcx]
0x18002c26c  mov     rax, [rax+10h]
0x18002c270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c275  jmp     loc_18002BEF4
0x18002c27a  mov     edx, 2Bh ; '+'
0x18002c27f  lea     r8, WPP_a85fccec657a30c16cbc767298893445_Traceguids
0x18002c286  mov     ecx, 406h
0x18002c28b  mov     r9d, edi
0x18002c28e  call    WPP_SF_d
0x18002c293  jmp     loc_18002BF4B
0x18002c298  mov     edx, 11h
0x18002c29d  lea     r9, [rbp+57h+var_C8]
0x18002c2a1  mov     ecx, esi
0x18002c2a3  lea     r8, WPP_6ab49dfb88213ef993fa13ad0186785e_Traceguids
0x18002c2aa  call    WPP_SF_q
0x18002c2af  jmp     loc_18002BFA2
0x18002c2b4  mov     rax, [rbx]
0x18002c2b7  mov     rcx, rbx
0x18002c2ba  mov     rax, [rax+10h]
0x18002c2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2c3  jmp     loc_18002BF5B
```
