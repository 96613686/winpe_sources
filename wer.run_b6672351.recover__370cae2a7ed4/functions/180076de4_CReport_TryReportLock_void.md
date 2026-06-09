# CReport::TryReportLock(void)

- ea: `0x180076de4`
- end: `0x1800771ab`
- name: `?TryReportLock@CReport@@QEAAJXZ`
- size: `967`
- prototype: `__int64 __fastcall(CReport *__hidden this)`
- caller_count: `8`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180005cd4`
- `0x1800420c0`
- `0x18006a600`
- `0x18006df10`
- `0x180072f9c`
- `0x18007756c`
- `0x18007774c`
- `0x18007a000`

## callees

- `0x180004c64`
- `0x180008004`
- `0x18000cf50`
- `0x18000db80`
- `0x18000e31c`
- `0x180018090`
- `0x18001e288`
- `0x180020680`
- `0x18002d8f4`
- `0x18003de9c`
- `0x1800479ac`
- `0x180048b34`
- `0x180053300`
- `0x180053d3c`
- `0x18005dd11`
- `0x180076de4`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076f54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076e32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076e32`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180076f3d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180076f3d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180077112`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180077112`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  __int64 v11; // r8
  __int64 v12; // r9
  wchar_t *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  char *v17; // [rsp+20h] [rbp-E0h] BYREF
  char v18; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpName[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE Src[1408]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v21; // [rsp+5D0h] [rbp+4D0h] BYREF
  _BYTE v22[38]; // [rsp+5D2h] [rbp+4D2h] BYREF
  int v23; // [rsp+5F8h] [rbp+4F8h]
  unsigned int v24; // [rsp+5FCh] [rbp+4FCh]
  __int64 v25; // [rsp+680h] [rbp+580h]
  _DWORD v26[12]; // [rsp+B50h] [rbp+A50h] BYREF
  wchar_t v27[680]; // [rsp+B80h] [rbp+A80h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpName);
  v17 = (char *)this + 46576;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 46576));
  v2 = 1;
  v18 = 1;
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
      v5 = 326;
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
      v5 = 327;
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
      v21 = 0;
      memset_0(v22, 0, 0x576u);
      memset_0(Src, 0, 0x578u);
      memcpy_0(v26, Src, 0x578u);
      v26[0] = 91751760;
      v26[10] = -1073741822;
      UniqueIdentifier = StringCchCopyW(v27, 0x40u, *((const wchar_t **)this + 735));
      if ( UniqueIdentifier < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_46;
        v5 = 328;
        goto LABEL_11;
      }
      UniqueIdentifier = UtilSendMessageToWersvc(v9, (struct _WERSVC_MSG *)v26, (struct _WERSVC_MSG *)&v21, 0);
      if ( UniqueIdentifier < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_46;
        v5 = 329;
LABEL_11:
        WPP_SF_d(
          *((_QWORD *)v4 + 2),
          v5,
          WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids,
          (unsigned int)UniqueIdentifier);
        goto LABEL_46;
      }
      if ( v23 != -1073741824 )
      {
        v12 = v24;
        UniqueIdentifier = v24 | 0x10000000;
        v13 = WPP_GLOBAL_Control;
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
        v14 = 330;
LABEL_39:
        WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, v12);
        goto LABEL_40;
      }
      v15 = v25;
      if ( !v25 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v10, 0, v11);
        v15 = v25;
      }
      tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 46552, v15);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 332, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids);
      goto LABEL_46;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_40;
    v14 = 331;
    v12 = (unsigned int)UniqueIdentifier;
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 325, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids);
  v2 = 0;
LABEL_49:
  utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(&v17);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpName);
  return v2;
}

```

## disassembly

```asm
0x180076de4  mov     [rsp-8+arg_8], rbx
0x180076de9  mov     [rsp-8+arg_10], rsi
0x180076dee  push    rbp
0x180076def  push    rdi
0x180076df0  push    r14
0x180076df2  lea     rbp, [rsp-0FE0h]
0x180076dfa  mov     eax, 10E0h
0x180076dff  call    _alloca_probe
0x180076e04  sub     rsp, rax
0x180076e07  mov     rax, cs:__security_cookie
0x180076e0e  xor     rax, rsp
0x180076e11  mov     [rbp+0FF0h+var_20], rax
0x180076e18  mov     rsi, rcx
0x180076e1b  lea     rcx, [rsp+10F0h+lpName]; void *
0x180076e20  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180076e25  nop
0x180076e26  lea     rcx, [rsi+0B5F0h]; lpCriticalSection
0x180076e2d  mov     [rsp+10F0h+var_10D0], rcx
0x180076e32  call    cs:__imp_EnterCriticalSection
0x180076e39  nop     dword ptr [rax+rax+00h]
0x180076e3e  mov     edi, 1
0x180076e43  mov     [rsp+10F0h+var_10C8], dil
0x180076e48  mov     rcx, rsi; this
0x180076e4b  call    ?IsReportLocked@CReport@@QEAAHXZ; CReport::IsReportLocked(void)
0x180076e50  test    eax, eax
0x180076e52  jz      short loc_180076E89
0x180076e54  lea     rax, WPP_GLOBAL_Control
0x180076e5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180076e62  cmp     rcx, rax
0x180076e65  jz      short loc_180076E82
0x180076e67  test    byte ptr [rcx+1Ch], 4
0x180076e6b  jz      short loc_180076E82
0x180076e6d  mov     edx, 145h
0x180076e72  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180076e79  mov     rcx, [rcx+10h]
0x180076e7d  call    WPP_SF_
0x180076e82  xor     edi, edi
0x180076e84  jmp     loc_18007716C
0x180076e89  test    dword ptr [rsi+19D8h], 200000h
0x180076e93  jnz     loc_18007716C
0x180076e99  xor     edx, edx
0x180076e9b  mov     rcx, rsi
0x180076e9e  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180076ea3  mov     ebx, eax
0x180076ea5  test    eax, eax
0x180076ea7  jns     short loc_180076EE7
0x180076ea9  lea     rax, WPP_GLOBAL_Control
0x180076eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180076eb7  cmp     rcx, rax
0x180076eba  jz      loc_180077158
0x180076ec0  test    [rcx+1Ch], dil
0x180076ec4  jz      loc_180077158
0x180076eca  mov     edx, 146h
0x180076ecf  mov     r9d, ebx
0x180076ed2  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180076ed9  mov     rcx, [rcx+10h]
0x180076edd  call    WPP_SF_d
0x180076ee2  jmp     loc_180077158
0x180076ee7  mov     r8, [rsi+16F8h]
0x180076eee  lea     rdx, aGlobalLs; "Global\\%ls"
0x180076ef5  lea     rcx, [rsp+10F0h+lpName]
0x180076efa  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180076eff  mov     ebx, eax
0x180076f01  test    eax, eax
0x180076f03  jns     short loc_180076F2D
0x180076f05  lea     rax, WPP_GLOBAL_Control
0x180076f0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180076f13  cmp     rcx, rax
0x180076f16  jz      loc_180077158
0x180076f1c  test    [rcx+1Ch], dil
0x180076f20  jz      loc_180077158
0x180076f26  mov     edx, 147h
0x180076f2b  jmp     short loc_180076ECF
0x180076f2d  lea     r14, [rsi+0B5D8h]
0x180076f34  mov     r8, [rsp+10F0h+lpName]; lpName
0x180076f39  mov     edx, edi; bInitialOwner
0x180076f3b  xor     ecx, ecx; lpMutexAttributes
0x180076f3d  call    cs:__imp_CreateMutexW
0x180076f44  nop     dword ptr [rax+rax+00h]
0x180076f49  mov     rdx, rax
0x180076f4c  mov     rcx, r14
0x180076f4f  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180076f54  call    cs:__imp_GetLastError
0x180076f5b  nop     dword ptr [rax+rax+00h]
0x180076f60  mov     ebx, eax
0x180076f62  test    eax, eax
0x180076f64  jle     short loc_180076F6F
0x180076f66  movzx   ebx, ax
0x180076f69  or      ebx, 80070000h
0x180076f6f  mov     rax, [r14]
0x180076f72  add     rax, rdi
0x180076f75  cmp     rax, rdi
0x180076f78  ja      loc_1800770CD
0x180076f7e  cmp     ebx, 80070005h
0x180076f84  jnz     loc_1800770CD
0x180076f8a  xor     eax, eax
0x180076f8c  mov     [rbp+0FF0h+var_B20], ax
0x180076f93  xor     edx, edx; Val
0x180076f95  mov     r8d, 576h; Size
0x180076f9b  lea     rcx, [rbp+0FF0h+var_B1E]; void *
0x180076fa2  call    memset_0
0x180076fa7  mov     ebx, 578h
0x180076fac  mov     r8d, ebx; Size
0x180076faf  xor     edx, edx; Val
0x180076fb1  lea     rcx, [rsp+10F0h+Src]; void *
0x180076fb6  call    memset_0
0x180076fbb  lea     rcx, [rbp+0FF0h+var_5A0]; void *
0x180076fc2  lea     rdx, [rsp+10F0h+Src]; Src
0x180076fc7  mov     r8d, ebx; Size
0x180076fca  call    memcpy_0
0x180076fcf  mov     [rbp+0FF0h+var_5A0], 5780550h
0x180076fd9  mov     [rbp+0FF0h+var_578], 0C0000002h
0x180076fe3  mov     r8, [rsi+16F8h]; wchar_t *
0x180076fea  mov     edx, 40h ; '@'; unsigned __int64
0x180076fef  lea     rcx, [rbp+0FF0h+var_570]; wchar_t *
0x180076ff6  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180076ffb  mov     ebx, eax
0x180076ffd  test    eax, eax
0x180076fff  jns     short loc_18007702C
0x180077001  lea     rax, WPP_GLOBAL_Control
0x180077008  mov     rcx, cs:WPP_GLOBAL_Control
0x18007700f  cmp     rcx, rax
0x180077012  jz      loc_180077158
0x180077018  test    [rcx+1Ch], dil
0x18007701c  jz      loc_180077158
0x180077022  mov     edx, 148h
0x180077027  jmp     loc_180076ECF
0x18007702c  xor     r9d, r9d; unsigned int
0x18007702f  lea     r8, [rbp+0FF0h+var_B20]; struct _WERSVC_MSG *
0x180077036  lea     rdx, [rbp+0FF0h+var_5A0]; struct _WERSVC_MSG *
0x18007703d  call    ?UtilSendMessageToWersvc@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; UtilSendMessageToWersvc(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x180077042  mov     ebx, eax
0x180077044  test    eax, eax
0x180077046  jns     short loc_180077073
0x180077048  lea     rax, WPP_GLOBAL_Control
0x18007704f  mov     rcx, cs:WPP_GLOBAL_Control
0x180077056  cmp     rcx, rax
0x180077059  jz      loc_180077158
0x18007705f  test    [rcx+1Ch], dil
0x180077063  jz      loc_180077158
0x180077069  mov     edx, 149h
0x18007706e  jmp     loc_180076ECF
0x180077073  cmp     [rbp+0FF0h+var_AF8], 0C0000000h
0x18007707d  jz      short loc_1800770AD
0x18007707f  mov     r9d, [rbp+0FF0h+var_AF4]
0x180077086  mov     ebx, r9d
0x180077089  bts     ebx, 1Ch
0x18007708d  lea     rax, WPP_GLOBAL_Control
0x180077094  mov     rcx, cs:WPP_GLOBAL_Control
0x18007709b  cmp     rcx, rax
0x18007709e  jz      short loc_18007710A
0x1800770a0  test    [rcx+1Ch], dil
0x1800770a4  jz      short loc_18007710A
0x1800770a6  mov     edx, 14Ah
0x1800770ab  jmp     short loc_1800770FA
0x1800770ad  mov     rdx, [rbp+0FF0h+var_A70]
0x1800770b4  test    rdx, rdx
0x1800770b7  jnz     short loc_1800770C5
0x1800770b9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800770be  mov     rdx, [rbp+0FF0h+var_A70]
0x1800770c5  mov     rcx, r14
0x1800770c8  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800770cd  mov     rcx, [r14]; hHandle
0x1800770d0  lea     rax, [rcx+1]
0x1800770d4  cmp     rax, rdi
0x1800770d7  ja      short loc_180077110
0x1800770d9  lea     rax, WPP_GLOBAL_Control
0x1800770e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800770e7  cmp     rcx, rax
0x1800770ea  jz      short loc_18007710A
0x1800770ec  test    [rcx+1Ch], dil
0x1800770f0  jz      short loc_18007710A
0x1800770f2  mov     edx, 14Bh
0x1800770f7  mov     r9d, ebx
0x1800770fa  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180077101  mov     rcx, [rcx+10h]
0x180077105  call    WPP_SF_d
0x18007710a  test    ebx, ebx
0x18007710c  jns     short loc_18007716A
0x18007710e  jmp     short loc_180077158
0x180077110  xor     edx, edx; dwMilliseconds
0x180077112  call    cs:__imp_WaitForSingleObject
0x180077119  nop     dword ptr [rax+rax+00h]
0x18007711e  cmp     eax, 102h
0x180077123  jnz     short loc_180077168
0x180077125  mov     ebx, 800700B7h
0x18007712a  lea     rax, WPP_GLOBAL_Control
0x180077131  mov     rcx, cs:WPP_GLOBAL_Control
0x180077138  cmp     rcx, rax
0x18007713b  jz      short loc_180077158
0x18007713d  test    byte ptr [rcx+1Ch], 4
0x180077141  jz      short loc_180077158
0x180077143  mov     edx, 14Ch
0x180077148  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x18007714f  mov     rcx, [rcx+10h]
0x180077153  call    WPP_SF_
0x180077158  lea     rcx, [rsi+0B5D8h]
0x18007715f  xor     edx, edx
0x180077161  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180077166  jmp     short loc_18007716A
0x180077168  xor     ebx, ebx
0x18007716a  mov     edi, ebx
0x18007716c  lea     rcx, [rsp+10F0h+var_10D0]
0x180077171  call    ??1?$unique_lock@Vrecursive_mutex@utl@@@utl@@QEAA@XZ; utl::unique_lock<utl::recursive_mutex>::~unique_lock<utl::recursive_mutex>(void)
0x180077176  nop
0x180077177  lea     rcx, [rsp+10F0h+lpName]; void *
0x18007717c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180077181  mov     eax, edi
0x180077183  mov     rcx, [rbp+0FF0h+var_20]
0x18007718a  xor     rcx, rsp; StackCookie
0x18007718d  call    __security_check_cookie
0x180077192  lea     r11, [rsp+10F0h+var_10]
0x18007719a  mov     rbx, [r11+28h]
0x18007719e  mov     rsi, [r11+30h]
0x1800771a2  mov     rsp, r11
0x1800771a5  pop     r14
0x1800771a7  pop     rdi
0x1800771a8  pop     rbp
0x1800771a9  retn
```
