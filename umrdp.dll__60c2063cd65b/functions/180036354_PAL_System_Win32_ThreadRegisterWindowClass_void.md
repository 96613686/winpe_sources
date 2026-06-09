# PAL_System_Win32_ThreadRegisterWindowClass(void)

- ea: `0x180036354`
- end: `0x1800365cd`
- name: `?PAL_System_Win32_ThreadRegisterWindowClass@@YAJXZ`
- size: `633`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180036088`

## callees

- `0x1800011c8`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000f79c`
- `0x180036354`
- `0x180037208`
- `0x180047ebe`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003642b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800364e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003642b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800364e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180036421`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180036421`
- `USER32!GetClassInfoExW` at `0x180036484`
- `USER32!GetClassInfoExW` at `0x180036484`
- `USER32!RegisterClassExW` at `0x1800364d8`
- `USER32!RegisterClassExW` at `0x1800364d8`

## string_xrefs

- `0x180036534`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18003651d`: `PAL_System_Win32_ThreadRegisterWindowClass`

## pseudocode

```c
__int64 PAL_System_Win32_ThreadRegisterWindowClass(void)
{
  const unsigned __int16 *v0; // rcx
  unsigned int v1; // r8d
  signed int ModuleSpecificClassName; // ebx
  unsigned int v3; // eax
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  ATOM v6; // bx
  signed int v7; // eax
  int v8; // r8d
  int v9; // r9d
  signed int v11; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+54h] [rbp-ACh] BYREF
  signed int v13; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-A0h] BYREF
  const char *v15; // [rsp+68h] [rbp-98h] BYREF
  const char *v16; // [rsp+70h] [rbp-90h] BYREF
  const char *v17; // [rsp+78h] [rbp-88h] BYREF
  tagWNDCLASSEXW wcx; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szClass[264]; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(&wcx, 0, sizeof(wcx));
  phModule = 0;
  memset_0(szClass, 0, 0x208u);
  ModuleSpecificClassName = PAL_System_Win32_GetModuleSpecificClassName(v0, szClass, v1);
  if ( ModuleSpecificClassName >= 0 )
  {
    if ( !GetModuleHandleExW(2u, 0, &phModule) )
    {
      LastError = GetLastError();
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          19,
          WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
          CurrentThreadActivityIdPrefix,
          LastError);
      }
    }
    if ( GetClassInfoExW(0, szClass, &wcx) )
      goto LABEL_19;
    wcx.cbSize = 80;
    wcx.lpfnWndProc = (WNDPROC)PAL_System_Win32_ThreadWndProc;
    wcx.hInstance = phModule;
    wcx.style = 3;
    wcx.lpszClassName = szClass;
    *(_QWORD *)&wcx.cbClsExtra = 0;
    memset(&wcx.hIcon, 0, 32);
    wcx.hIconSm = 0;
    v6 = RegisterClassExW(&wcx);
    v7 = GetLastError();
    if ( v6 || v7 == 1410 )
    {
LABEL_19:
      g_PAL_SYS_fThreadWndClassRegistered = 1;
      return 0;
    }
    else
    {
      if ( v7 > 0 )
        ModuleSpecificClassName = (unsigned __int16)v7 | 0x80070000;
      else
        ModuleSpecificClassName = v7;
      if ( (unsigned int)dword_18005C008 > 2 )
      {
        v11 = v7;
        v15 = "PAL_System_Win32_ThreadRegisterWindowClass";
        v12 = 538;
        v16 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
        v17 = "Failed to register window class [Win32err = %d]";
        v13 = ModuleSpecificClassName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v7,
          (unsigned int)byte_1800547AB,
          v8,
          v9,
          (__int64)&v17,
          (__int64)&v13,
          (__int64)&v16,
          (__int64)&v12,
          (__int64)&v15,
          (__int64)&v11);
      }
    }
  }
  else if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
         && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v3 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      18,
      (unsigned int)WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
      v3,
      (__int64)"Failed to get module specific class name",
      ModuleSpecificClassName);
  }
  return (unsigned int)ModuleSpecificClassName;
}

```

## disassembly

```asm
0x180036354  mov     [rsp-8+arg_0], rbx
0x180036359  mov     [rsp-8+arg_8], rdi
0x18003635e  push    rbp
0x18003635f  lea     rbp, [rsp-1F0h]
0x180036367  sub     rsp, 2F0h
0x18003636e  mov     rax, cs:__security_cookie
0x180036375  xor     rax, rsp
0x180036378  mov     [rbp+1F0h+var_10], rax
0x18003637f  xor     edx, edx; Val
0x180036381  lea     rcx, [rbp+1F0h+wcx]; void *
0x180036385  lea     r8d, [rdx+50h]; Size
0x180036389  call    memset_0
0x18003638e  xor     edi, edi
0x180036390  lea     rcx, [rbp+1F0h+szClass]; void *
0x180036394  xor     edx, edx; Val
0x180036396  mov     [rsp+2F0h+phModule], rdi
0x18003639b  mov     r8d, 208h; Size
0x1800363a1  call    memset_0
0x1800363a6  lea     rdx, [rbp+1F0h+szClass]; unsigned __int16 *
0x1800363aa  call    ?PAL_System_Win32_GetModuleSpecificClassName@@YAJPEBGPEAGK@Z; PAL_System_Win32_GetModuleSpecificClassName(ushort const *,ushort *,ulong)
0x1800363af  mov     ebx, eax
0x1800363b1  test    eax, eax
0x1800363b3  jns     short loc_180036417
0x1800363b5  mov     rax, cs:WPP_GLOBAL_Control
0x1800363bc  lea     rcx, WPP_GLOBAL_Control
0x1800363c3  cmp     rax, rcx
0x1800363c6  jz      loc_1800365A7
0x1800363cc  test    byte ptr [rax+1Ch], 8
0x1800363d0  jz      loc_1800365A7
0x1800363d6  cmp     byte ptr [rax+19h], 2
0x1800363da  jb      loc_1800365A7
0x1800363e0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800363e5  lea     rcx, aFailedToGetMod; "Failed to get module specific class nam"...
0x1800363ec  mov     dword ptr [rsp+2F0h+var_2C8], ebx
0x1800363f0  mov     [rsp+2F0h+var_2D0], rcx
0x1800363f5  lea     edx, [rdi+12h]
0x1800363f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800363ff  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x180036406  mov     r9d, eax
0x180036409  mov     rcx, [rcx+10h]
0x18003640d  call    WPP_SF_DsD
0x180036412  jmp     loc_1800365A7
0x180036417  xor     edx, edx; lpModuleName
0x180036419  lea     r8, [rsp+2F0h+phModule]; phModule
0x18003641e  lea     ecx, [rdx+2]; dwFlags
0x180036421  call    cs:__imp_GetModuleHandleExW
0x180036427  test    eax, eax
0x180036429  jnz     short loc_18003647A
0x18003642b  call    cs:__imp_GetLastError
0x180036431  mov     ebx, eax
0x180036433  mov     rdx, cs:WPP_GLOBAL_Control
0x18003643a  lea     rcx, WPP_GLOBAL_Control
0x180036441  cmp     rdx, rcx
0x180036444  jz      short loc_18003647A
0x180036446  test    byte ptr [rdx+1Ch], 8
0x18003644a  jz      short loc_18003647A
0x18003644c  cmp     byte ptr [rdx+19h], 2
0x180036450  jb      short loc_18003647A
0x180036452  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180036457  mov     rcx, cs:WPP_GLOBAL_Control
0x18003645e  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x180036465  mov     edx, 13h
0x18003646a  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x18003646e  mov     r9d, eax
0x180036471  mov     rcx, [rcx+10h]
0x180036475  call    WPP_SF_Dd
0x18003647a  lea     r8, [rbp+1F0h+wcx]; lpwcx
0x18003647e  xor     ecx, ecx; hInstance
0x180036480  lea     rdx, [rbp+1F0h+szClass]; lpszClass
0x180036484  call    cs:__imp_GetClassInfoExW
0x18003648a  test    eax, eax
0x18003648c  jnz     loc_18003659B
0x180036492  lea     rax, ?PAL_System_Win32_ThreadWndProc@@YA_JPEAUHWND__@@I_K_J@Z; PAL_System_Win32_ThreadWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180036499  mov     [rbp+1F0h+wcx.cbSize], 50h ; 'P'
0x1800364a0  mov     [rbp+1F0h+wcx.lpfnWndProc], rax
0x1800364a4  lea     rcx, [rbp+1F0h+wcx]; WNDCLASSEXW *
0x1800364a8  mov     rax, [rsp+2F0h+phModule]
0x1800364ad  xorps   xmm0, xmm0
0x1800364b0  mov     [rbp+1F0h+wcx.hInstance], rax
0x1800364b4  xorps   xmm1, xmm1
0x1800364b7  lea     rax, [rbp+1F0h+szClass]
0x1800364bb  mov     [rbp+1F0h+wcx.style], 3
0x1800364c2  mov     [rbp+1F0h+wcx.lpszClassName], rax
0x1800364c6  mov     qword ptr [rbp+1F0h+wcx.cbClsExtra], rdi
0x1800364ca  movdqa  xmmword ptr [rbp+1F0h+wcx.hIcon], xmm0
0x1800364cf  movdqa  xmmword ptr [rbp+1F0h+wcx.hbrBackground], xmm1
0x1800364d4  mov     [rbp+1F0h+wcx.hIconSm], rdi
0x1800364d8  call    cs:__imp_RegisterClassExW
0x1800364de  movzx   ebx, ax
0x1800364e1  call    cs:__imp_GetLastError
0x1800364e7  mov     ecx, eax
0x1800364e9  test    bx, bx
0x1800364ec  jnz     loc_18003659B
0x1800364f2  cmp     eax, 582h
0x1800364f7  jz      loc_18003659B
0x1800364fd  test    eax, eax
0x1800364ff  jg      short loc_180036505
0x180036501  mov     ebx, eax
0x180036503  jmp     short loc_18003650E
0x180036505  movzx   ebx, cx
0x180036508  or      ebx, 80070000h
0x18003650e  mov     eax, cs:dword_18005C008
0x180036514  cmp     eax, 2
0x180036517  jbe     loc_1800365A7
0x18003651d  lea     rax, aPalSystemWin32; "PAL_System_Win32_ThreadRegisterWindowCl"...
0x180036524  mov     [rsp+2F0h+var_2A0], ecx
0x180036528  mov     [rsp+2F0h+var_288], rax
0x18003652d  lea     rdx, byte_1800547AB
0x180036534  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18003653b  mov     [rsp+2F0h+var_29C], 21Ah
0x180036543  mov     [rsp+2F0h+var_280], rax
0x180036548  lea     rax, aFailedToRegist; "Failed to register window class [Win32e"...
0x18003654f  mov     [rsp+2F0h+var_278], rax
0x180036554  lea     rax, [rsp+2F0h+var_2A0]
0x180036559  mov     [rsp+2F0h+var_2A8], rax
0x18003655e  lea     rax, [rsp+2F0h+var_288]
0x180036563  mov     [rsp+2F0h+var_2B0], rax
0x180036568  lea     rax, [rsp+2F0h+var_29C]
0x18003656d  mov     [rsp+2F0h+var_2B8], rax
0x180036572  lea     rax, [rsp+2F0h+var_280]
0x180036577  mov     [rsp+2F0h+var_2C0], rax
0x18003657c  lea     rax, [rsp+2F0h+var_298]
0x180036581  mov     [rsp+2F0h+var_2C8], rax
0x180036586  lea     rax, [rsp+2F0h+var_278]
0x18003658b  mov     [rsp+2F0h+var_2D0], rax
0x180036590  mov     [rsp+2F0h+var_298], ebx
0x180036594  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180036599  jmp     short loc_1800365A7
0x18003659b  mov     cs:?g_PAL_SYS_fThreadWndClassRegistered@@3HA, 1; int g_PAL_SYS_fThreadWndClassRegistered
0x1800365a5  mov     ebx, edi
0x1800365a7  mov     eax, ebx
0x1800365a9  mov     rcx, [rbp+1F0h+var_10]
0x1800365b0  xor     rcx, rsp; StackCookie
0x1800365b3  call    __security_check_cookie
0x1800365b8  lea     r11, [rsp+2F0h+var_s0]
0x1800365c0  mov     rbx, [r11+10h]
0x1800365c4  mov     rdi, [r11+18h]
0x1800365c8  mov     rsp, r11
0x1800365cb  pop     rbp
0x1800365cc  retn
```
