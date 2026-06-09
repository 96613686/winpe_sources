# CReport::TryReportLock(void)

- ea: `0x1800739c0`
- end: `0x180073d6e`
- name: `?TryReportLock@CReport@@QEAAJXZ`
- size: `942`
- prototype: `__int64 __fastcall(CReport *__hidden this)`
- caller_count: `8`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18001a60c`
- `0x18004015c`
- `0x1800674f0`
- `0x18006ad60`
- `0x18006fc58`
- `0x180074114`
- `0x1800742f4`
- `0x180076b00`

## callees

- `0x180004bb4`
- `0x180007e34`
- `0x18000bc10`
- `0x18000cc74`
- `0x18000dad0`
- `0x180015520`
- `0x18001dc24`
- `0x18001fe24`
- `0x18002c198`
- `0x18003bf14`
- `0x180045bdc`
- `0x180046d74`
- `0x180050db0`
- `0x1800517cc`
- `0x18005b8d1`
- `0x1800739c0`
- `0x1800aa000`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073b24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073b24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073a0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073a0e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180073b13`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180073b13`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180073cdc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180073cdc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CReport::TryReportLock(CReport *this)
{
  unsigned int v2; // edi
  int UniqueIdentifier; // ebx
  wchar_t *v4; // rcx
  __int64 v5; // rdx
  HANDLE *v6; // r14
  HANDLE MutexW; // rax
  signed int LastError; // eax
  const wchar_t *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // r9
  wchar_t *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  char *v16; // [rsp+20h] [rbp-E0h] BYREF
  char v17; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpName[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE Src[1408]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v20; // [rsp+5D0h] [rbp+4D0h] BYREF
  _BYTE v21[38]; // [rsp+5D2h] [rbp+4D2h] BYREF
  int v22; // [rsp+5F8h] [rbp+4F8h]
  unsigned int v23; // [rsp+5FCh] [rbp+4FCh]
  __int64 v24; // [rsp+680h] [rbp+580h]
  _DWORD v25[12]; // [rsp+B50h] [rbp+A50h] BYREF
  wchar_t v26[680]; // [rsp+B80h] [rbp+A80h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpName);
  v16 = (char *)this + 46576;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 46576));
  v2 = 1;
  v17 = 1;
  if ( !(unsigned int)CReport::IsReportLocked(this) )
  {
    if ( (*((_DWORD *)this + 1654) & 0x200000) != 0 )
      goto LABEL_49;
    UniqueIdentifier = CReport::GetUniqueIdentifier(this, 0);
    if ( UniqueIdentifier < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_46;
      v5 = 325;
      goto LABEL_11;
    }
    UniqueIdentifier = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                         lpName,
                         L"Global\\%ls",
                         *((_QWORD *)this + 735));
    if ( UniqueIdentifier < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_46;
      v5 = 326;
      goto LABEL_11;
    }
    v6 = (HANDLE *)((char *)this + 46552);
    MutexW = CreateMutexW(0, 1, lpName[0]);
    tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 46552, MutexW);
    LastError = GetLastError();
    UniqueIdentifier = LastError;
    if ( LastError > 0 )
      UniqueIdentifier = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned __int64)*v6 + 1 <= 1 && UniqueIdentifier == -2147024891 )
    {
      v20 = 0;
      memset_0(v21, 0, 0x576u);
      memset_0(Src, 0, 0x578u);
      memcpy_0(v25, Src, 0x578u);
      v25[0] = 91751760;
      v25[10] = -1073741822;
      UniqueIdentifier = StringCchCopyW(v26, 0x40u, *((const wchar_t **)this + 735));
      if ( UniqueIdentifier < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_46;
        v5 = 327;
        goto LABEL_11;
      }
      UniqueIdentifier = UtilSendMessageToWersvc(v9, (struct _WERSVC_MSG *)v25, (struct _WERSVC_MSG *)&v20, 0);
      if ( UniqueIdentifier < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_46;
        v5 = 328;
LABEL_11:
        WPP_SF_d(
          *((_QWORD *)v4 + 2),
          v5,
          WPP_6898268820d636d20e115db2eaa75970_Traceguids,
          (unsigned int)UniqueIdentifier);
        goto LABEL_46;
      }
      if ( v22 != -1073741824 )
      {
        v11 = v23;
        UniqueIdentifier = v23 | 0x10000000;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        {
LABEL_40:
          if ( UniqueIdentifier >= 0 )
          {
LABEL_48:
            v2 = UniqueIdentifier;
            goto LABEL_49;
          }
LABEL_46:
          tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 46552, 0);
          goto LABEL_48;
        }
        v13 = 329;
LABEL_39:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_6898268820d636d20e115db2eaa75970_Traceguids, v11);
        goto LABEL_40;
      }
      v14 = v24;
      if ( !v24 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v10, 0);
        v14 = v24;
      }
      tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 46552, v14);
    }
    if ( (unsigned __int64)*v6 + 1 > 1 )
    {
      if ( WaitForSingleObject(*v6, 0) != 258 )
      {
        UniqueIdentifier = 0;
        goto LABEL_48;
      }
      UniqueIdentifier = -2147024713;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 331, WPP_6898268820d636d20e115db2eaa75970_Traceguids);
      goto LABEL_46;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_40;
    v13 = 330;
    v11 = (unsigned int)UniqueIdentifier;
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 324, WPP_6898268820d636d20e115db2eaa75970_Traceguids);
  v2 = 0;
LABEL_49:
  utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v16);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpName);
  return v2;
}

```

## disassembly

```asm
0x1800739c0  mov     [rsp-8+arg_8], rbx
0x1800739c5  mov     [rsp-8+arg_10], rsi
0x1800739ca  push    rbp
0x1800739cb  push    rdi
0x1800739cc  push    r14
0x1800739ce  lea     rbp, [rsp-0FE0h]
0x1800739d6  mov     eax, 10E0h
0x1800739db  call    _alloca_probe
0x1800739e0  sub     rsp, rax
0x1800739e3  mov     rax, cs:__security_cookie
0x1800739ea  xor     rax, rsp
0x1800739ed  mov     [rbp+0FF0h+var_20], rax
0x1800739f4  mov     rsi, rcx
0x1800739f7  lea     rcx, [rsp+10F0h+lpName]; void *
0x1800739fc  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180073a01  nop
0x180073a02  lea     rcx, [rsi+0B5F0h]; lpCriticalSection
0x180073a09  mov     [rsp+10F0h+var_10D0], rcx
0x180073a0e  call    cs:__imp_EnterCriticalSection
0x180073a14  mov     edi, 1
0x180073a19  mov     [rsp+10F0h+var_10C8], dil
0x180073a1e  mov     rcx, rsi; this
0x180073a21  call    ?IsReportLocked@CReport@@QEAAHXZ; CReport::IsReportLocked(void)
0x180073a26  test    eax, eax
0x180073a28  jz      short loc_180073A5F
0x180073a2a  lea     rax, WPP_GLOBAL_Control
0x180073a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180073a38  cmp     rcx, rax
0x180073a3b  jz      short loc_180073A58
0x180073a3d  test    byte ptr [rcx+1Ch], 4
0x180073a41  jz      short loc_180073A58
0x180073a43  mov     edx, 144h
0x180073a48  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180073a4f  mov     rcx, [rcx+10h]
0x180073a53  call    WPP_SF_
0x180073a58  xor     edi, edi
0x180073a5a  jmp     loc_180073D30
0x180073a5f  test    dword ptr [rsi+19D8h], 200000h
0x180073a69  jnz     loc_180073D30
0x180073a6f  xor     edx, edx
0x180073a71  mov     rcx, rsi
0x180073a74  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180073a79  mov     ebx, eax
0x180073a7b  test    eax, eax
0x180073a7d  jns     short loc_180073ABD
0x180073a7f  lea     rax, WPP_GLOBAL_Control
0x180073a86  mov     rcx, cs:WPP_GLOBAL_Control
0x180073a8d  cmp     rcx, rax
0x180073a90  jz      loc_180073D1C
0x180073a96  test    [rcx+1Ch], dil
0x180073a9a  jz      loc_180073D1C
0x180073aa0  mov     edx, 145h
0x180073aa5  mov     r9d, ebx
0x180073aa8  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180073aaf  mov     rcx, [rcx+10h]
0x180073ab3  call    WPP_SF_d
0x180073ab8  jmp     loc_180073D1C
0x180073abd  mov     r8, [rsi+16F8h]
0x180073ac4  lea     rdx, aGlobalLs; "Global\\%ls"
0x180073acb  lea     rcx, [rsp+10F0h+lpName]
0x180073ad0  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180073ad5  mov     ebx, eax
0x180073ad7  test    eax, eax
0x180073ad9  jns     short loc_180073B03
0x180073adb  lea     rax, WPP_GLOBAL_Control
0x180073ae2  mov     rcx, cs:WPP_GLOBAL_Control
0x180073ae9  cmp     rcx, rax
0x180073aec  jz      loc_180073D1C
0x180073af2  test    [rcx+1Ch], dil
0x180073af6  jz      loc_180073D1C
0x180073afc  mov     edx, 146h
0x180073b01  jmp     short loc_180073AA5
0x180073b03  lea     r14, [rsi+0B5D8h]
0x180073b0a  mov     r8, [rsp+10F0h+lpName]; lpName
0x180073b0f  mov     edx, edi; bInitialOwner
0x180073b11  xor     ecx, ecx; lpMutexAttributes
0x180073b13  call    cs:__imp_CreateMutexW
0x180073b19  mov     rdx, rax
0x180073b1c  mov     rcx, r14
0x180073b1f  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180073b24  call    cs:__imp_GetLastError
0x180073b2a  mov     ebx, eax
0x180073b2c  test    eax, eax
0x180073b2e  jle     short loc_180073B39
0x180073b30  movzx   ebx, ax
0x180073b33  or      ebx, 80070000h
0x180073b39  mov     rax, [r14]
0x180073b3c  add     rax, rdi
0x180073b3f  cmp     rax, rdi
0x180073b42  ja      loc_180073C97
0x180073b48  cmp     ebx, 80070005h
0x180073b4e  jnz     loc_180073C97
0x180073b54  xor     eax, eax
0x180073b56  mov     [rbp+0FF0h+var_B20], ax
0x180073b5d  xor     edx, edx; Val
0x180073b5f  mov     r8d, 576h; Size
0x180073b65  lea     rcx, [rbp+0FF0h+var_B1E]; void *
0x180073b6c  call    memset_0
0x180073b71  mov     ebx, 578h
0x180073b76  mov     r8d, ebx; Size
0x180073b79  xor     edx, edx; Val
0x180073b7b  lea     rcx, [rsp+10F0h+Src]; void *
0x180073b80  call    memset_0
0x180073b85  lea     rcx, [rbp+0FF0h+var_5A0]; void *
0x180073b8c  lea     rdx, [rsp+10F0h+Src]; Src
0x180073b91  mov     r8d, ebx; Size
0x180073b94  call    memcpy_0
0x180073b99  mov     [rbp+0FF0h+var_5A0], 5780550h
0x180073ba3  mov     [rbp+0FF0h+var_578], 0C0000002h
0x180073bad  mov     r8, [rsi+16F8h]; wchar_t *
0x180073bb4  mov     edx, 40h ; '@'; unsigned __int64
0x180073bb9  lea     rcx, [rbp+0FF0h+var_570]; wchar_t *
0x180073bc0  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180073bc5  mov     ebx, eax
0x180073bc7  test    eax, eax
0x180073bc9  jns     short loc_180073BF6
0x180073bcb  lea     rax, WPP_GLOBAL_Control
0x180073bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180073bd9  cmp     rcx, rax
0x180073bdc  jz      loc_180073D1C
0x180073be2  test    [rcx+1Ch], dil
0x180073be6  jz      loc_180073D1C
0x180073bec  mov     edx, 147h
0x180073bf1  jmp     loc_180073AA5
0x180073bf6  xor     r9d, r9d; unsigned int
0x180073bf9  lea     r8, [rbp+0FF0h+var_B20]; struct _WERSVC_MSG *
0x180073c00  lea     rdx, [rbp+0FF0h+var_5A0]; struct _WERSVC_MSG *
0x180073c07  call    ?UtilSendMessageToWersvc@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; UtilSendMessageToWersvc(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x180073c0c  mov     ebx, eax
0x180073c0e  test    eax, eax
0x180073c10  jns     short loc_180073C3D
0x180073c12  lea     rax, WPP_GLOBAL_Control
0x180073c19  mov     rcx, cs:WPP_GLOBAL_Control
0x180073c20  cmp     rcx, rax
0x180073c23  jz      loc_180073D1C
0x180073c29  test    [rcx+1Ch], dil
0x180073c2d  jz      loc_180073D1C
0x180073c33  mov     edx, 148h
0x180073c38  jmp     loc_180073AA5
0x180073c3d  cmp     [rbp+0FF0h+var_AF8], 0C0000000h
0x180073c47  jz      short loc_180073C77
0x180073c49  mov     r9d, [rbp+0FF0h+var_AF4]
0x180073c50  mov     ebx, r9d
0x180073c53  bts     ebx, 1Ch
0x180073c57  lea     rax, WPP_GLOBAL_Control
0x180073c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180073c65  cmp     rcx, rax
0x180073c68  jz      short loc_180073CD4
0x180073c6a  test    [rcx+1Ch], dil
0x180073c6e  jz      short loc_180073CD4
0x180073c70  mov     edx, 149h
0x180073c75  jmp     short loc_180073CC4
0x180073c77  mov     rdx, [rbp+0FF0h+var_A70]
0x180073c7e  test    rdx, rdx
0x180073c81  jnz     short loc_180073C8F
0x180073c83  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180073c88  mov     rdx, [rbp+0FF0h+var_A70]
0x180073c8f  mov     rcx, r14
0x180073c92  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180073c97  mov     rcx, [r14]; hHandle
0x180073c9a  lea     rax, [rcx+1]
0x180073c9e  cmp     rax, rdi
0x180073ca1  ja      short loc_180073CDA
0x180073ca3  lea     rax, WPP_GLOBAL_Control
0x180073caa  mov     rcx, cs:WPP_GLOBAL_Control
0x180073cb1  cmp     rcx, rax
0x180073cb4  jz      short loc_180073CD4
0x180073cb6  test    [rcx+1Ch], dil
0x180073cba  jz      short loc_180073CD4
0x180073cbc  mov     edx, 14Ah
0x180073cc1  mov     r9d, ebx
0x180073cc4  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180073ccb  mov     rcx, [rcx+10h]
0x180073ccf  call    WPP_SF_d
0x180073cd4  test    ebx, ebx
0x180073cd6  jns     short loc_180073D2E
0x180073cd8  jmp     short loc_180073D1C
0x180073cda  xor     edx, edx; dwMilliseconds
0x180073cdc  call    cs:__imp_WaitForSingleObject
0x180073ce2  cmp     eax, 102h
0x180073ce7  jnz     short loc_180073D2C
0x180073ce9  mov     ebx, 800700B7h
0x180073cee  lea     rax, WPP_GLOBAL_Control
0x180073cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180073cfc  cmp     rcx, rax
0x180073cff  jz      short loc_180073D1C
0x180073d01  test    byte ptr [rcx+1Ch], 4
0x180073d05  jz      short loc_180073D1C
0x180073d07  mov     edx, 14Bh
0x180073d0c  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x180073d13  mov     rcx, [rcx+10h]
0x180073d17  call    WPP_SF_
0x180073d1c  lea     rcx, [rsi+0B5D8h]
0x180073d23  xor     edx, edx
0x180073d25  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180073d2a  jmp     short loc_180073D2E
0x180073d2c  xor     ebx, ebx
0x180073d2e  mov     edi, ebx
0x180073d30  lea     rcx, [rsp+10F0h+var_10D0]
0x180073d35  call    ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
0x180073d3a  nop
0x180073d3b  lea     rcx, [rsp+10F0h+lpName]; void *
0x180073d40  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180073d45  mov     eax, edi
0x180073d47  mov     rcx, [rbp+0FF0h+var_20]
0x180073d4e  xor     rcx, rsp; StackCookie
0x180073d51  call    __security_check_cookie
0x180073d56  lea     r11, [rsp+10F0h+var_10]
0x180073d5e  mov     rbx, [r11+28h]
0x180073d62  mov     rsi, [r11+30h]
0x180073d66  mov     rsp, r11
0x180073d69  pop     r14
0x180073d6b  pop     rdi
0x180073d6c  pop     rbp
0x180073d6d  retn
```
