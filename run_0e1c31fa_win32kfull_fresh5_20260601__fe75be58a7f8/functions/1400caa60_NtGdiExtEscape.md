# NtGdiExtEscape

- ea: `0x1400caa60`
- end: `0x1400cb122`
- name: `NtGdiExtEscape`
- size: `1730`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, installer_update`

## callees

- `0x14004a080`
- `0x140053654`
- `0x140054a9c`
- `0x140097774`
- `0x1400caa60`
- `0x1400cb128`
- `0x1400ccad8`
- `0x140226e08`
- `0x140237d4c`
- `0x140284a50`
- `0x14028776c`
- `0x1402939dc`
- `0x140341ff0`
- `0x140342540`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x1400cad43`
- `ntoskrnl!_wcsicmp` at `0x1400cad43`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400cab99`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400cab99`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1400cb0ba`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1400cb0ba`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1400cad00`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1400cae2a`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1400cad00`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1400cae2a`
- `win32kbase!PopThreadGuardedObject` at `0x1400caf67`
- `win32kbase!PopThreadGuardedObject` at `0x1400caf89`
- `win32kbase!PopThreadGuardedObject` at `0x1400cb060`
- `win32kbase!PopThreadGuardedObject` at `0x1400cb086`
- `win32kbase!PopThreadGuardedObject` at `0x1400caf67`
- `win32kbase!PopThreadGuardedObject` at `0x1400caf89`
- `win32kbase!PopThreadGuardedObject` at `0x1400cb060`
- `win32kbase!PopThreadGuardedObject` at `0x1400cb086`
- `win32kbase!PushThreadGuardedObject` at `0x1400caf19`
- `win32kbase!PushThreadGuardedObject` at `0x1400caf45`
- `win32kbase!PushThreadGuardedObject` at `0x1400cafb6`
- `win32kbase!PushThreadGuardedObject` at `0x1400cafde`
- `win32kbase!PushThreadGuardedObject` at `0x1400caf19`
- `win32kbase!PushThreadGuardedObject` at `0x1400caf45`
- `win32kbase!PushThreadGuardedObject` at `0x1400cafb6`
- `win32kbase!PushThreadGuardedObject` at `0x1400cafde`
- `win32kbase!?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z` at `0x1400cad97`
- `win32kbase!?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z` at `0x1400cad97`
- `win32kbase!?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z` at `0x1400cae75`
- `win32kbase!?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z` at `0x1400cae75`
- `win32kbase!?GrepGetWinLogonW32PID@@YAKXZ` at `0x1400cab4c`
- `win32kbase!?GrepGetWinLogonW32PID@@YAKXZ` at `0x1400cab4c`
- `win32kbase!Win32FreePool` at `0x1400cb0f4`
- `win32kbase!Win32FreePool` at `0x1400cb111`
- `win32kbase!Win32FreePool` at `0x1400caf07`
- `win32kbase!Win32FreePool` at `0x1400caf33`
- `win32kbase!Win32FreePool` at `0x1400cafa4`
- `win32kbase!Win32FreePool` at `0x1400cafcc`
- `win32kbase!Win32FreePool` at `0x1400cb0f4`
- `win32kbase!Win32FreePool` at `0x1400cb111`
- `WIN32K!W32GetSessionState` at `0x1400cabfb`
- `WIN32K!W32GetSessionState` at `0x1400cafea`
- `WIN32K!W32GetSessionState` at `0x1400cabfb`
- `WIN32K!W32GetSessionState` at `0x1400cafea`

## pseudocode

```c
__int64 __fastcall NtGdiExtEscape(
        HDC a1,
        const void *a2,
        int a3,
        unsigned int a4,
        int a5,
        struct tagUMFD_WINLOGON_ESCAPE_ARGUMENT *a6,
        signed int a7,
        char *a8)
{
  int v8; // ebx
  unsigned int v9; // r13d
  int v10; // r12d
  int v11; // r15d
  char *v12; // rsi
  struct tagUMFD_WINLOGON_ESCAPE_ARGUMENT *v13; // r14
  const wchar_t *v15; // rax
  __int64 v16; // rcx
  __int64 SessionState; // rax
  int IsEnabledDeviceUsageNoInline; // ecx
  char v19; // dl
  unsigned int v20; // eax
  int v21; // eax
  __int64 v22; // rax
  unsigned int v23; // eax
  unsigned int Str1; // [rsp+58h] [rbp-340h]
  wchar_t *Str1a; // [rsp+58h] [rbp-340h]
  __int64 v30; // [rsp+88h] [rbp-310h] BYREF
  __int128 v31; // [rsp+90h] [rbp-308h]
  __int64 v32; // [rsp+A0h] [rbp-2F8h]
  __int64 v33; // [rsp+A8h] [rbp-2F0h] BYREF
  __int128 v34; // [rsp+B0h] [rbp-2E8h]
  __int64 v35; // [rsp+C0h] [rbp-2D8h]
  _BYTE v36[56]; // [rsp+C8h] [rbp-2D0h] BYREF
  char v37; // [rsp+100h] [rbp-298h] BYREF
  char v38; // [rsp+120h] [rbp-278h] BYREF
  _WORD v39[264]; // [rsp+140h] [rbp-258h] BYREF

  v8 = a7;
  v9 = -1;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( a5 < 0 || a7 < 0 || a3 < 0 || a1 && a2 )
    goto LABEL_27;
  Str1 = GrepGetWinLogonW32PID();
  if ( Str1 && Str1 == ((unsigned int)PsGetCurrentProcessId() & 0xFFFFFFFC) )
  {
    UmfdDispatchWinLogonEscape(a6);
    return 0;
  }
  if ( UmfdHostLifeTimeManager::IsCurrentProcessUmfdHost() )
  {
    UmfdDispatchEscape(a6);
    return 0;
  }
  v15 = 0;
  Str1a = 0;
  if ( a2 )
  {
    if ( a3 > 260 )
      goto LABEL_27;
    Str1a = v39;
    GreProbeAndReadFromUntrustedVa(v39, 2LL * a3, a2, 2LL * a3, 2u);
    v39[a3] = 0;
    v8 = a7;
    v15 = v39;
  }
  if ( v15 && !_wcsicmp(v15, L"GSESC") && (int)GreScalingDispatchEscape(a6) >= 0 )
    return 0;
  if ( a5 )
  {
    if ( GreIsUMPD(a1) )
    {
      v21 = a5;
      if ( a5 > 32 )
      {
        v13 = a6;
        GreProbeForReadFromUntrustedVa(a6, a5, 1u);
        goto LABEL_14;
      }
    }
    else
    {
      v21 = a5;
      if ( a5 > 32 )
      {
        if ( a5 <= 40960000 )
        {
          v13 = (struct tagUMFD_WINLOGON_ESCAPE_ARGUMENT *)PALLOCNOZ((unsigned int)a5, 1886221383);
          v21 = a5;
        }
        if ( !v13 )
          goto LABEL_27;
        v10 = 1;
        goto LABEL_47;
      }
    }
    v13 = (struct tagUMFD_WINLOGON_ESCAPE_ARGUMENT *)&v37;
LABEL_47:
    GreProbeAndReadFromUntrustedVa(v13, v21, a6, v21, 1u);
  }
LABEL_14:
  if ( v8 )
  {
    if ( GreIsUMPD(a1) )
    {
      v12 = a8;
      GreProbeForWriteToUntrustedVa(a8, v8, 1u);
    }
    else
    {
      if ( v8 > 32 )
      {
        if ( v8 <= 40960000 )
          v12 = (char *)PALLOCNOZ((unsigned int)v8, 1886221383);
        if ( !v12 )
          goto LABEL_27;
        v11 = 1;
      }
      else
      {
        v12 = &v38;
      }
      memset_0(v12, 0, v8);
    }
  }
  if ( (unsigned int)Feature_Servicing_UmfdDeadlockFix__private_IsEnabledDeviceUsageNoInline() )
  {
    SessionState = W32GetSessionState(v16);
    EUDCCountRegion::EUDCCountRegion(
      (EUDCCountRegion *)v36,
      (struct Gre::Font::GLOBALS *)(*(_QWORD *)(SessionState + 96) + 4864LL));
    IsEnabledDeviceUsageNoInline = Feature_Servicing_UmfdDeadlockFix__private_IsEnabledDeviceUsageNoInline();
    v19 = 1;
    if ( IsEnabledDeviceUsageNoInline )
      v19 = v36[48];
    if ( v19 )
    {
      if ( v10 && v13 )
        PushThreadGuardedObject(&v30, v13, Win32FreePool);
      if ( v11 && v12 )
        PushThreadGuardedObject(&v33, v12, Win32FreePool);
      if ( Str1a )
        v20 = GreNamedEscape(Str1a, a4, a5, v13, v8, v12);
      else
        v20 = GreExtEscape(a1, a4, a5, (char *)v13, v8, v12);
      v9 = v20;
      if ( v10 && v13 )
        PopThreadGuardedObject(&v30);
      if ( v11 && v12 )
        PopThreadGuardedObject(&v33);
    }
    EUDCCountRegion::~EUDCCountRegion((EUDCCountRegion *)v36);
  }
  else
  {
    if ( v10 && v13 )
      PushThreadGuardedObject(&v30, v13, Win32FreePool);
    if ( v11 && v12 )
      PushThreadGuardedObject(&v33, v12, Win32FreePool);
    v22 = W32GetSessionState(v16);
    EUDCCountRegion::EUDCCountRegion(
      (EUDCCountRegion *)v36,
      (struct Gre::Font::GLOBALS *)(*(_QWORD *)(v22 + 96) + 4864LL));
    if ( Str1a )
      v23 = GreNamedEscape(Str1a, a4, a5, v13, v8, v12);
    else
      v23 = GreExtEscape(a1, a4, a5, (char *)v13, v8, v12);
    v9 = v23;
    EUDCCountRegion::~EUDCCountRegion((EUDCCountRegion *)v36);
    if ( v10 && v13 )
      PopThreadGuardedObject(&v30);
    if ( v11 && v12 )
      PopThreadGuardedObject(&v33);
  }
  if ( v8 && v12 != a8 )
    GreProbeAndWriteToUntrustedVa(a8, v8, v12, v8, 1u);
LABEL_27:
  if ( v11 && v12 )
    Win32FreePool(v12);
  if ( v10 )
  {
    if ( v13 )
      Win32FreePool(v13);
  }
  return v9;
}

```

## disassembly

```asm
0x1400caa60  mov     r11, rsp
0x1400caa63  push    rbx
0x1400caa64  push    rsi
0x1400caa65  push    rdi
0x1400caa66  push    r12
0x1400caa68  push    r13
0x1400caa6a  push    r14
0x1400caa6c  push    r15
0x1400caa6e  sub     rsp, 360h
0x1400caa75  mov     rax, cs:__security_cookie
0x1400caa7c  xor     rax, rsp
0x1400caa7f  mov     [rsp+398h+var_48], rax
0x1400caa87  mov     [rsp+398h+var_358], r9d
0x1400caa8c  mov     [rsp+398h+var_328], r8d
0x1400caa91  mov     [rsp+398h+var_318], rdx
0x1400caa99  mov     r9, rcx
0x1400caa9c  mov     [rsp+398h+var_330], rcx
0x1400caaa1  mov     eax, [rsp+398h+arg_20]
0x1400caaa8  mov     [rsp+398h+var_368], eax
0x1400caaac  mov     rcx, [rsp+398h+arg_28]
0x1400caab4  mov     [rsp+398h+var_338], rcx
0x1400caab9  mov     ebx, [rsp+398h+arg_30]
0x1400caac0  mov     [rsp+398h+var_324], ebx
0x1400caac4  mov     rcx, [rsp+398h+arg_38]
0x1400caacc  mov     [rsp+398h+var_320], rcx
0x1400caad1  or      r13d, 0FFFFFFFFh
0x1400caad5  mov     [rsp+398h+var_35C], r13d
0x1400caada  xor     edi, edi
0x1400caadc  mov     [r11-310h], rdi
0x1400caae3  xorps   xmm0, xmm0
0x1400caae6  xor     ecx, ecx
0x1400caae8  movups  [rsp+398h+var_308], xmm0
0x1400caaf0  mov     [r11-2F8h], rcx
0x1400caaf7  mov     [r11-2F0h], rdi
0x1400caafe  movups  [rsp+398h+var_2E8], xmm0
0x1400cab06  mov     [r11-2D8h], rcx
0x1400cab0d  mov     r12d, edi
0x1400cab10  mov     [rsp+398h+var_360], edi
0x1400cab14  mov     r15d, edi
0x1400cab17  mov     [rsp+398h+var_364], edi
0x1400cab1b  mov     esi, edi
0x1400cab1d  mov     [rsp+398h+var_348], rdi
0x1400cab22  mov     r14d, edi
0x1400cab25  mov     [rsp+398h+var_350], rdi
0x1400cab2a  test    eax, eax
0x1400cab2c  js      loc_1400CAC9C
0x1400cab32  test    ebx, ebx
0x1400cab34  js      loc_1400CAC9C
0x1400cab3a  test    r8d, r8d
0x1400cab3d  js      loc_1400CAC9C
0x1400cab43  test    r9, r9
0x1400cab46  jnz     loc_1400CACC2
0x1400cab4c  call    cs:__imp_?GrepGetWinLogonW32PID@@YAKXZ; GrepGetWinLogonW32PID(void)
0x1400cab53  nop     dword ptr [rax+rax+00h]
0x1400cab58  mov     dword ptr [rsp+398h+Str1], eax
0x1400cab5c  test    eax, eax
0x1400cab5e  jnz     short loc_1400CAB99
0x1400cab60  call    ?IsCurrentProcessUmfdHost@UmfdHostLifeTimeManager@@SA_NXZ; UmfdHostLifeTimeManager::IsCurrentProcessUmfdHost(void)
0x1400cab65  test    al, al
0x1400cab67  jz      short loc_1400CABBA
0x1400cab69  mov     rcx, [rsp+398h+var_338]; struct tagUMFD_ESCAPE_ARGUMENT *
0x1400cab6e  call    ?UmfdDispatchEscape@@YAXPEAUtagUMFD_ESCAPE_ARGUMENT@@@Z; UmfdDispatchEscape(tagUMFD_ESCAPE_ARGUMENT *)
0x1400cab73  xor     eax, eax
0x1400cab75  mov     rcx, [rsp+398h+var_48]
0x1400cab7d  xor     rcx, rsp; StackCookie
0x1400cab80  call    __security_check_cookie
0x1400cab85  add     rsp, 360h
0x1400cab8c  pop     r15
0x1400cab8e  pop     r14
0x1400cab90  pop     r13
0x1400cab92  pop     r12
0x1400cab94  pop     rdi
0x1400cab95  pop     rsi
0x1400cab96  pop     rbx
0x1400cab97  retn
0x1400cab99  call    cs:__imp_PsGetCurrentProcessId
0x1400caba0  nop     dword ptr [rax+rax+00h]
0x1400caba5  and     eax, 0FFFFFFFCh
0x1400caba8  cmp     dword ptr [rsp+398h+Str1], eax
0x1400cabac  jnz     short loc_1400CAB60
0x1400cabae  mov     rcx, [rsp+398h+var_338]; struct tagUMFD_WINLOGON_ESCAPE_ARGUMENT *
0x1400cabb3  call    ?UmfdDispatchWinLogonEscape@@YAXPEAUtagUMFD_WINLOGON_ESCAPE_ARGUMENT@@@Z; UmfdDispatchWinLogonEscape(tagUMFD_WINLOGON_ESCAPE_ARGUMENT *)
0x1400cabb8  jmp     short loc_1400CAB73
0x1400cabba  mov     rax, rdi
0x1400cabbd  mov     [rsp+398h+Str1], rax
0x1400cabc2  mov     r8, [rsp+398h+var_318]
0x1400cabca  test    r8, r8
0x1400cabcd  jnz     loc_1400CACCC
0x1400cabd3  test    rax, rax
0x1400cabd6  jnz     loc_1400CAD39
0x1400cabdc  cmp     [rsp+398h+var_368], edi
0x1400cabe0  jnz     loc_1400CAD6E
0x1400cabe6  test    ebx, ebx
0x1400cabe8  jnz     loc_1400CAE56
0x1400cabee  call    Feature_Servicing_UmfdDeadlockFix__private_IsEnabledDeviceUsageNoInline
0x1400cabf3  test    eax, eax
0x1400cabf5  jz      loc_1400CAF9A
0x1400cabfb  call    cs:__imp_W32GetSessionState
0x1400cac02  nop     dword ptr [rax+rax+00h]
0x1400cac07  mov     rdx, [rax+60h]
0x1400cac0b  add     rdx, 1300h; struct Gre::Font::GLOBALS *
0x1400cac12  lea     rcx, [rsp+398h+var_2D0]; this
0x1400cac1a  call    ??0EUDCCountRegion@@QEAA@AEAUGLOBALS@Font@Gre@@@Z; EUDCCountRegion::EUDCCountRegion(Gre::Font::GLOBALS &)
0x1400cac1f  call    Feature_Servicing_UmfdDeadlockFix__private_IsEnabledDeviceUsageNoInline
0x1400cac24  mov     ecx, eax
0x1400cac26  mov     edx, 1
0x1400cac2b  movzx   eax, [rsp+398h+var_2A0]
0x1400cac33  test    ecx, ecx
0x1400cac35  cmovnz  edx, eax
0x1400cac38  test    dl, dl
0x1400cac3a  jz      short loc_1400CAC87
0x1400cac3c  test    r12d, r12d
0x1400cac3f  jnz     loc_1400CAEFE
0x1400cac45  test    r15d, r15d
0x1400cac48  jnz     loc_1400CAF2A
0x1400cac4e  mov     rcx, [rsp+398h+Str1]; Str1
0x1400cac53  mov     [rsp+398h+var_370], rsi; char *
0x1400cac58  mov     r9, r14; char *
0x1400cac5b  mov     r8d, [rsp+398h+var_368]; int
0x1400cac60  mov     edx, [rsp+398h+var_358]; int
0x1400cac64  mov     [rsp+398h+var_378], ebx; int
0x1400cac68  test    rcx, rcx
0x1400cac6b  jz      short loc_1400CACB6
0x1400cac6d  call    GreNamedEscape
0x1400cac72  mov     r13d, eax
0x1400cac75  test    r12d, r12d
0x1400cac78  jnz     loc_1400CAF56
0x1400cac7e  test    r15d, r15d
0x1400cac81  jnz     loc_1400CAF78
0x1400cac87  lea     rcx, [rsp+398h+var_2D0]; this
0x1400cac8f  call    ??1EUDCCountRegion@@QEAA@XZ; EUDCCountRegion::~EUDCCountRegion(void)
0x1400cac94  test    ebx, ebx
0x1400cac96  jnz     loc_1400CB097
0x1400cac9c  test    r15d, r15d
0x1400cac9f  jnz     loc_1400CB0E8
0x1400caca5  test    r12d, r12d
0x1400caca8  jnz     loc_1400CB105
0x1400cacae  mov     eax, r13d
0x1400cacb1  jmp     loc_1400CAB75
0x1400cacb6  mov     rcx, [rsp+398h+var_330]; HDC
0x1400cacbb  call    ?GreExtEscape@@YAHPEAUHDC__@@HHPEADH1@Z; GreExtEscape(HDC__ *,int,int,char *,int,char *)
0x1400cacc0  jmp     short loc_1400CAC72
0x1400cacc2  test    rdx, rdx
0x1400cacc5  jnz     short loc_1400CAC9C
0x1400cacc7  jmp     loc_1400CAB4C
0x1400caccc  movsxd  rax, [rsp+398h+var_328]
0x1400cacd1  cmp     eax, 104h
0x1400cacd6  jg      short loc_1400CAC9C
0x1400cacd8  lea     rcx, [rsp+398h+var_258]
0x1400cace0  mov     [rsp+398h+Str1], rcx
0x1400cace5  lea     rbx, [rax+rax]
0x1400cace9  mov     qword ptr [rsp+398h+var_378], 2
0x1400cacf2  mov     r9, rbx
0x1400cacf5  mov     rdx, rbx
0x1400cacf8  lea     rcx, [rsp+398h+var_258]
0x1400cad00  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x1400cad07  nop     dword ptr [rax+rax+00h]
0x1400cad0c  mov     [rsp+rbx+398h+var_258], di
0x1400cad14  mov     ebx, [rsp+398h+var_324]
0x1400cad18  mov     rax, [rsp+398h+Str1]
0x1400cad1d  jmp     loc_1400CABD3
0x1400cad22  xor     edi, edi
0x1400cad24  mov     r14d, edi
0x1400cad27  mov     esi, edi
0x1400cad29  mov     r15d, esi
0x1400cad2c  mov     r12d, esi
0x1400cad2f  mov     r13d, [rsp+398h+var_35C]
0x1400cad34  jmp     loc_1400CAC9C
0x1400cad39  lea     rdx, aGsesc; "GSESC"
0x1400cad40  mov     rcx, rax; Str1
0x1400cad43  call    cs:__imp__wcsicmp
0x1400cad4a  nop     dword ptr [rax+rax+00h]
0x1400cad4f  test    eax, eax
0x1400cad51  jnz     loc_1400CABDC
0x1400cad57  mov     rcx, [rsp+398h+var_338]; struct tagGDISCALE_ESCAPE_ARGUMENT *
0x1400cad5c  call    ?GreScalingDispatchEscape@@YAJPEAUtagGDISCALE_ESCAPE_ARGUMENT@@@Z; GreScalingDispatchEscape(tagGDISCALE_ESCAPE_ARGUMENT *)
0x1400cad61  test    eax, eax
0x1400cad63  jns     loc_1400CAB73
0x1400cad69  jmp     loc_1400CABDC
0x1400cad6e  mov     rcx, [rsp+398h+var_330]; HDC
0x1400cad73  call    ?GreIsUMPD@@YA_NPEAUHDC__@@@Z; GreIsUMPD(HDC__ *)
0x1400cad78  test    al, al
0x1400cad7a  jz      short loc_1400CADC6
0x1400cad7c  movsxd  rax, [rsp+398h+var_368]
0x1400cad81  cmp     eax, 20h ; ' '
0x1400cad84  jle     short loc_1400CADF0
0x1400cad86  mov     rdx, rax
0x1400cad89  mov     r8d, 1
0x1400cad8f  mov     r14, [rsp+398h+var_338]
0x1400cad94  mov     rcx, r14
0x1400cad97  call    cs:__imp_?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z; GreProbeForReadFromUntrustedVa(void const *,unsigned __int64,unsigned __int64)
0x1400cad9e  nop     dword ptr [rax+rax+00h]
0x1400cada3  jmp     short loc_1400CADBC
0x1400cada5  xor     edi, edi
0x1400cada7  mov     r14d, edi
0x1400cadaa  mov     esi, edi
0x1400cadac  mov     r15d, esi
0x1400cadaf  mov     r12d, esi
0x1400cadb2  mov     r13d, [rsp+398h+var_35C]
0x1400cadb7  jmp     loc_1400CAC9C
0x1400cadbc  mov     [rsp+398h+var_350], r14
0x1400cadc1  jmp     loc_1400CABE6
0x1400cadc6  mov     eax, [rsp+398h+var_368]
0x1400cadca  cmp     eax, 20h ; ' '
0x1400cadcd  jle     short loc_1400CADF0
0x1400cadcf  cmp     eax, 2710000h
0x1400cadd4  jg      short loc_1400CADFF
0x1400cadd6  mov     edx, 706D7447h
0x1400caddb  mov     ecx, eax
0x1400caddd  call    PALLOCNOZ
0x1400cade2  mov     r14, rax
0x1400cade5  mov     [rsp+398h+var_350], rax
0x1400cadea  mov     eax, [rsp+398h+var_368]
0x1400cadee  jmp     short loc_1400CADFF
0x1400cadf0  lea     r14, [rsp+398h+var_298]
0x1400cadf8  mov     [rsp+398h+var_350], r14
0x1400cadfd  jmp     short loc_1400CAE13
0x1400cadff  test    r14, r14
0x1400cae02  jz      loc_1400CAC9C
0x1400cae08  mov     r12d, 1
0x1400cae0e  mov     [rsp+398h+var_360], r12d
0x1400cae13  movsxd  rdx, eax
0x1400cae16  mov     qword ptr [rsp+398h+var_378], 1
0x1400cae1f  mov     r9, rdx
0x1400cae22  mov     r8, [rsp+398h+var_338]
0x1400cae27  mov     rcx, r14
0x1400cae2a  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x1400cae31  nop     dword ptr [rax+rax+00h]
0x1400cae36  jmp     loc_1400CABE6
0x1400cae3b  xor     edi, edi
0x1400cae3d  mov     r14, [rsp+398h+var_350]
0x1400cae42  mov     esi, edi
0x1400cae44  mov     r15d, esi
0x1400cae47  mov     r12d, [rsp+398h+var_360]
0x1400cae4c  mov     r13d, [rsp+398h+var_35C]
0x1400cae51  jmp     loc_1400CAC9C
0x1400cae56  mov     rcx, [rsp+398h+var_330]; HDC
0x1400cae5b  call    ?GreIsUMPD@@YA_NPEAUHDC__@@@Z; GreIsUMPD(HDC__ *)
0x1400cae60  test    al, al
0x1400cae62  jz      short loc_1400CAEA8
0x1400cae64  movsxd  rdx, ebx
0x1400cae67  mov     r8d, 1
0x1400cae6d  mov     rsi, [rsp+398h+var_320]
0x1400cae72  mov     rcx, rsi
0x1400cae75  call    cs:__imp_?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z; GreProbeForWriteToUntrustedVa(void *,unsigned __int64,unsigned __int64)
0x1400cae7c  nop     dword ptr [rax+rax+00h]
0x1400cae81  jmp     short loc_1400CAE9E
0x1400cae83  xor     edi, edi
0x1400cae85  mov     r14, [rsp+398h+var_350]
0x1400cae8a  mov     esi, edi
0x1400cae8c  mov     r15d, esi
0x1400cae8f  mov     r12d, [rsp+398h+var_360]
0x1400cae94  mov     r13d, [rsp+398h+var_35C]
0x1400cae99  jmp     loc_1400CAC9C
0x1400cae9e  mov     [rsp+398h+var_348], rsi
0x1400caea3  jmp     loc_1400CABEE
0x1400caea8  cmp     ebx, 20h ; ' '
0x1400caeab  jg      short loc_1400CAEBC
0x1400caead  lea     rsi, [rsp+398h+var_278]
0x1400caeb5  mov     [rsp+398h+var_348], rsi
0x1400caeba  jmp     short loc_1400CAEEC
0x1400caebc  cmp     ebx, 2710000h
0x1400caec2  jg      short loc_1400CAED8
0x1400caec4  mov     edx, 706D7447h
0x1400caec9  mov     ecx, ebx
0x1400caecb  call    PALLOCNOZ
0x1400caed0  mov     rsi, rax
0x1400caed3  mov     [rsp+398h+var_348], rax
0x1400caed8  test    rsi, rsi
0x1400caedb  jz      loc_1400CAC9C
0x1400caee1  mov     r15d, 1
0x1400caee7  mov     [rsp+398h+var_364], r15d
0x1400caeec  movsxd  r8, ebx; Size
0x1400caeef  xor     edx, edx; Val
0x1400caef1  mov     rcx, rsi; void *
0x1400caef4  call    memset_0
0x1400caef9  jmp     loc_1400CABEE
0x1400caefe  test    r14, r14
0x1400caf01  jz      loc_1400CAC45
0x1400caf07  mov     r8, cs:__imp_Win32FreePool
0x1400caf0e  mov     rdx, r14
0x1400caf11  lea     rcx, [rsp+398h+var_310]
0x1400caf19  call    cs:__imp_PushThreadGuardedObject
0x1400caf20  nop     dword ptr [rax+rax+00h]
0x1400caf25  jmp     loc_1400CAC45
0x1400caf2a  test    rsi, rsi
0x1400caf2d  jz      loc_1400CAC4E
0x1400caf33  mov     r8, cs:__imp_Win32FreePool
0x1400caf3a  mov     rdx, rsi
0x1400caf3d  lea     rcx, [rsp+398h+var_2F0]
0x1400caf45  call    cs:__imp_PushThreadGuardedObject
0x1400caf4c  nop     dword ptr [rax+rax+00h]
0x1400caf51  jmp     loc_1400CAC4E
0x1400caf56  test    r14, r14
0x1400caf59  jz      loc_1400CAC7E
0x1400caf5f  lea     rcx, [rsp+398h+var_310]
0x1400caf67  call    cs:__imp_PopThreadGuardedObject
0x1400caf6e  nop     dword ptr [rax+rax+00h]
0x1400caf73  jmp     loc_1400CAC7E
0x1400caf78  test    rsi, rsi
  ... truncated ...
```
