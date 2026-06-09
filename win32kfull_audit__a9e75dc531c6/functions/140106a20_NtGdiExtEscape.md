# NtGdiExtEscape

- ea: `0x140106a20`
- end: `0x1401070e2`
- name: `NtGdiExtEscape`
- size: `1730`
- prototype: `__int64 __fastcall(HDC, const void *, int, unsigned int, int, struct tagUMFD_WINLOGON_ESCAPE_ARGUMENT *, signed int, char *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, installer_update`

## callees

- `0x140047284`
- `0x1400add74`
- `0x140106a20`
- `0x1401070e8`
- `0x140107e00`
- `0x140109570`
- `0x140157384`
- `0x14020c5b4`
- `0x140227ae8`
- `0x140285af4`
- `0x14028912c`
- `0x140295f2c`
- `0x140342fa0`
- `0x140343500`

## import_xrefs

- `ntoskrnl!_wcsicmp` at `0x140106d03`
- `ntoskrnl!_wcsicmp` at `0x140106d03`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140106b59`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140106b59`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14010707a`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14010707a`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140106cc0`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140106dea`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140106cc0`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x140106dea`
- `win32kbase!PopThreadGuardedObject` at `0x140106f27`
- `win32kbase!PopThreadGuardedObject` at `0x140106f49`
- `win32kbase!PopThreadGuardedObject` at `0x140107020`
- `win32kbase!PopThreadGuardedObject` at `0x140107046`
- `win32kbase!PopThreadGuardedObject` at `0x140106f27`
- `win32kbase!PopThreadGuardedObject` at `0x140106f49`
- `win32kbase!PopThreadGuardedObject` at `0x140107020`
- `win32kbase!PopThreadGuardedObject` at `0x140107046`
- `win32kbase!PushThreadGuardedObject` at `0x140106ed9`
- `win32kbase!PushThreadGuardedObject` at `0x140106f05`
- `win32kbase!PushThreadGuardedObject` at `0x140106f76`
- `win32kbase!PushThreadGuardedObject` at `0x140106f9e`
- `win32kbase!PushThreadGuardedObject` at `0x140106ed9`
- `win32kbase!PushThreadGuardedObject` at `0x140106f05`
- `win32kbase!PushThreadGuardedObject` at `0x140106f76`
- `win32kbase!PushThreadGuardedObject` at `0x140106f9e`
- `win32kbase!?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z` at `0x140106d57`
- `win32kbase!?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z` at `0x140106d57`
- `win32kbase!?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z` at `0x140106e35`
- `win32kbase!?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z` at `0x140106e35`
- `win32kbase!?GrepGetWinLogonW32PID@@YAKXZ` at `0x140106b0c`
- `win32kbase!?GrepGetWinLogonW32PID@@YAKXZ` at `0x140106b0c`
- `win32kbase!Win32FreePool` at `0x1401070b4`
- `win32kbase!Win32FreePool` at `0x1401070d1`
- `win32kbase!Win32FreePool` at `0x140106ec7`
- `win32kbase!Win32FreePool` at `0x140106ef3`
- `win32kbase!Win32FreePool` at `0x140106f64`
- `win32kbase!Win32FreePool` at `0x140106f8c`
- `win32kbase!Win32FreePool` at `0x1401070b4`
- `win32kbase!Win32FreePool` at `0x1401070d1`
- `WIN32K!W32GetSessionState` at `0x140106bbb`
- `WIN32K!W32GetSessionState` at `0x140106faa`
- `WIN32K!W32GetSessionState` at `0x140106bbb`
- `WIN32K!W32GetSessionState` at `0x140106faa`

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
  __int64 SessionState; // rax
  int IsEnabledDeviceUsageNoInline; // ecx
  char v18; // dl
  unsigned int v19; // eax
  int v20; // eax
  __int64 v21; // rax
  unsigned int v22; // eax
  unsigned int Str1; // [rsp+58h] [rbp-340h]
  wchar_t *Str1a; // [rsp+58h] [rbp-340h]
  __int64 v29; // [rsp+88h] [rbp-310h] BYREF
  __int128 v30; // [rsp+90h] [rbp-308h]
  __int64 v31; // [rsp+A0h] [rbp-2F8h]
  __int64 v32; // [rsp+A8h] [rbp-2F0h] BYREF
  __int128 v33; // [rsp+B0h] [rbp-2E8h]
  __int64 v34; // [rsp+C0h] [rbp-2D8h]
  _BYTE v35[56]; // [rsp+C8h] [rbp-2D0h] BYREF
  char v36; // [rsp+100h] [rbp-298h] BYREF
  char v37; // [rsp+120h] [rbp-278h] BYREF
  _WORD v38[264]; // [rsp+140h] [rbp-258h] BYREF

  v8 = a7;
  v9 = -1;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
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
    Str1a = v38;
    GreProbeAndReadFromUntrustedVa(v38, 2LL * a3, a2, 2LL * a3, 2u);
    v38[a3] = 0;
    v8 = a7;
    v15 = v38;
  }
  if ( v15 && !_wcsicmp(v15, L"GSESC") && (int)GreScalingDispatchEscape(a6) >= 0 )
    return 0;
  if ( a5 )
  {
    if ( GreIsUMPD(a1) )
    {
      v20 = a5;
      if ( a5 > 32 )
      {
        v13 = a6;
        GreProbeForReadFromUntrustedVa(a6, a5, 1u);
        goto LABEL_14;
      }
    }
    else
    {
      v20 = a5;
      if ( a5 > 32 )
      {
        if ( a5 <= 40960000 )
        {
          v13 = (struct tagUMFD_WINLOGON_ESCAPE_ARGUMENT *)PALLOCNOZ((unsigned int)a5, 1886221383);
          v20 = a5;
        }
        if ( !v13 )
          goto LABEL_27;
        v10 = 1;
        goto LABEL_47;
      }
    }
    v13 = (struct tagUMFD_WINLOGON_ESCAPE_ARGUMENT *)&v36;
LABEL_47:
    GreProbeAndReadFromUntrustedVa(v13, v20, a6, v20, 1u);
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
        v12 = &v37;
      }
      memset_0(v12, 0, v8);
    }
  }
  if ( (unsigned int)Feature_Servicing_UmfdDeadlockFix__private_IsEnabledDeviceUsageNoInline() )
  {
    SessionState = W32GetSessionState();
    EUDCCountRegion::EUDCCountRegion(
      (EUDCCountRegion *)v35,
      (struct Gre::Font::GLOBALS *)(*(_QWORD *)(SessionState + 96) + 4864LL));
    IsEnabledDeviceUsageNoInline = Feature_Servicing_UmfdDeadlockFix__private_IsEnabledDeviceUsageNoInline();
    v18 = 1;
    if ( IsEnabledDeviceUsageNoInline )
      v18 = v35[48];
    if ( v18 )
    {
      if ( v10 && v13 )
        PushThreadGuardedObject(&v29, v13, Win32FreePool);
      if ( v11 && v12 )
        PushThreadGuardedObject(&v32, v12, Win32FreePool);
      if ( Str1a )
        v19 = GreNamedEscape(Str1a, a4, a5, v13, v8, v12);
      else
        v19 = GreExtEscape(a1, a4, a5, (char *)v13, v8, v12);
      v9 = v19;
      if ( v10 && v13 )
        PopThreadGuardedObject(&v29);
      if ( v11 && v12 )
        PopThreadGuardedObject(&v32);
    }
    EUDCCountRegion::~EUDCCountRegion((EUDCCountRegion *)v35);
  }
  else
  {
    if ( v10 && v13 )
      PushThreadGuardedObject(&v29, v13, Win32FreePool);
    if ( v11 && v12 )
      PushThreadGuardedObject(&v32, v12, Win32FreePool);
    v21 = W32GetSessionState();
    EUDCCountRegion::EUDCCountRegion(
      (EUDCCountRegion *)v35,
      (struct Gre::Font::GLOBALS *)(*(_QWORD *)(v21 + 96) + 4864LL));
    if ( Str1a )
      v22 = GreNamedEscape(Str1a, a4, a5, v13, v8, v12);
    else
      v22 = GreExtEscape(a1, a4, a5, (char *)v13, v8, v12);
    v9 = v22;
    EUDCCountRegion::~EUDCCountRegion((EUDCCountRegion *)v35);
    if ( v10 && v13 )
      PopThreadGuardedObject(&v29);
    if ( v11 && v12 )
      PopThreadGuardedObject(&v32);
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
0x140106a20  mov     r11, rsp
0x140106a23  push    rbx
0x140106a24  push    rsi
0x140106a25  push    rdi
0x140106a26  push    r12
0x140106a28  push    r13
0x140106a2a  push    r14
0x140106a2c  push    r15
0x140106a2e  sub     rsp, 360h
0x140106a35  mov     rax, cs:__security_cookie
0x140106a3c  xor     rax, rsp
0x140106a3f  mov     [rsp+398h+var_48], rax
0x140106a47  mov     [rsp+398h+var_358], r9d
0x140106a4c  mov     [rsp+398h+var_328], r8d
0x140106a51  mov     [rsp+398h+var_318], rdx
0x140106a59  mov     r9, rcx
0x140106a5c  mov     [rsp+398h+var_330], rcx
0x140106a61  mov     eax, [rsp+398h+arg_20]
0x140106a68  mov     [rsp+398h+var_368], eax
0x140106a6c  mov     rcx, [rsp+398h+arg_28]
0x140106a74  mov     [rsp+398h+var_338], rcx
0x140106a79  mov     ebx, [rsp+398h+arg_30]
0x140106a80  mov     [rsp+398h+var_324], ebx
0x140106a84  mov     rcx, [rsp+398h+arg_38]
0x140106a8c  mov     [rsp+398h+var_320], rcx
0x140106a91  or      r13d, 0FFFFFFFFh
0x140106a95  mov     [rsp+398h+var_35C], r13d
0x140106a9a  xor     edi, edi
0x140106a9c  mov     [r11-310h], rdi
0x140106aa3  xorps   xmm0, xmm0
0x140106aa6  xor     ecx, ecx
0x140106aa8  movups  [rsp+398h+var_308], xmm0
0x140106ab0  mov     [r11-2F8h], rcx
0x140106ab7  mov     [r11-2F0h], rdi
0x140106abe  movups  [rsp+398h+var_2E8], xmm0
0x140106ac6  mov     [r11-2D8h], rcx
0x140106acd  mov     r12d, edi
0x140106ad0  mov     [rsp+398h+var_360], edi
0x140106ad4  mov     r15d, edi
0x140106ad7  mov     [rsp+398h+var_364], edi
0x140106adb  mov     esi, edi
0x140106add  mov     [rsp+398h+var_348], rdi
0x140106ae2  mov     r14d, edi
0x140106ae5  mov     [rsp+398h+var_350], rdi
0x140106aea  test    eax, eax
0x140106aec  js      loc_140106C5C
0x140106af2  test    ebx, ebx
0x140106af4  js      loc_140106C5C
0x140106afa  test    r8d, r8d
0x140106afd  js      loc_140106C5C
0x140106b03  test    r9, r9
0x140106b06  jnz     loc_140106C82
0x140106b0c  call    cs:__imp_?GrepGetWinLogonW32PID@@YAKXZ; GrepGetWinLogonW32PID(void)
0x140106b13  nop     dword ptr [rax+rax+00h]
0x140106b18  mov     dword ptr [rsp+398h+Str1], eax
0x140106b1c  test    eax, eax
0x140106b1e  jnz     short loc_140106B59
0x140106b20  call    ?IsCurrentProcessUmfdHost@UmfdHostLifeTimeManager@@SA_NXZ; UmfdHostLifeTimeManager::IsCurrentProcessUmfdHost(void)
0x140106b25  test    al, al
0x140106b27  jz      short loc_140106B7A
0x140106b29  mov     rcx, [rsp+398h+var_338]; struct tagUMFD_ESCAPE_ARGUMENT *
0x140106b2e  call    ?UmfdDispatchEscape@@YAXPEAUtagUMFD_ESCAPE_ARGUMENT@@@Z; UmfdDispatchEscape(tagUMFD_ESCAPE_ARGUMENT *)
0x140106b33  xor     eax, eax
0x140106b35  mov     rcx, [rsp+398h+var_48]
0x140106b3d  xor     rcx, rsp; StackCookie
0x140106b40  call    __security_check_cookie
0x140106b45  add     rsp, 360h
0x140106b4c  pop     r15
0x140106b4e  pop     r14
0x140106b50  pop     r13
0x140106b52  pop     r12
0x140106b54  pop     rdi
0x140106b55  pop     rsi
0x140106b56  pop     rbx
0x140106b57  retn
0x140106b59  call    cs:__imp_PsGetCurrentProcessId
0x140106b60  nop     dword ptr [rax+rax+00h]
0x140106b65  and     eax, 0FFFFFFFCh
0x140106b68  cmp     dword ptr [rsp+398h+Str1], eax
0x140106b6c  jnz     short loc_140106B20
0x140106b6e  mov     rcx, [rsp+398h+var_338]; struct tagUMFD_WINLOGON_ESCAPE_ARGUMENT *
0x140106b73  call    ?UmfdDispatchWinLogonEscape@@YAXPEAUtagUMFD_WINLOGON_ESCAPE_ARGUMENT@@@Z; UmfdDispatchWinLogonEscape(tagUMFD_WINLOGON_ESCAPE_ARGUMENT *)
0x140106b78  jmp     short loc_140106B33
0x140106b7a  mov     rax, rdi
0x140106b7d  mov     [rsp+398h+Str1], rax
0x140106b82  mov     r8, [rsp+398h+var_318]
0x140106b8a  test    r8, r8
0x140106b8d  jnz     loc_140106C8C
0x140106b93  test    rax, rax
0x140106b96  jnz     loc_140106CF9
0x140106b9c  cmp     [rsp+398h+var_368], edi
0x140106ba0  jnz     loc_140106D2E
0x140106ba6  test    ebx, ebx
0x140106ba8  jnz     loc_140106E16
0x140106bae  call    Feature_Servicing_UmfdDeadlockFix__private_IsEnabledDeviceUsageNoInline
0x140106bb3  test    eax, eax
0x140106bb5  jz      loc_140106F5A
0x140106bbb  call    cs:__imp_W32GetSessionState
0x140106bc2  nop     dword ptr [rax+rax+00h]
0x140106bc7  mov     rdx, [rax+60h]
0x140106bcb  add     rdx, 1300h; struct Gre::Font::GLOBALS *
0x140106bd2  lea     rcx, [rsp+398h+var_2D0]; this
0x140106bda  call    ??0EUDCCountRegion@@QEAA@AEAUGLOBALS@Font@Gre@@@Z; EUDCCountRegion::EUDCCountRegion(Gre::Font::GLOBALS &)
0x140106bdf  call    Feature_Servicing_UmfdDeadlockFix__private_IsEnabledDeviceUsageNoInline
0x140106be4  mov     ecx, eax
0x140106be6  mov     edx, 1
0x140106beb  movzx   eax, [rsp+398h+var_2A0]
0x140106bf3  test    ecx, ecx
0x140106bf5  cmovnz  edx, eax
0x140106bf8  test    dl, dl
0x140106bfa  jz      short loc_140106C47
0x140106bfc  test    r12d, r12d
0x140106bff  jnz     loc_140106EBE
0x140106c05  test    r15d, r15d
0x140106c08  jnz     loc_140106EEA
0x140106c0e  mov     rcx, [rsp+398h+Str1]; Str1
0x140106c13  mov     [rsp+398h+var_370], rsi; char *
0x140106c18  mov     r9, r14; char *
0x140106c1b  mov     r8d, [rsp+398h+var_368]; int
0x140106c20  mov     edx, [rsp+398h+var_358]; int
0x140106c24  mov     [rsp+398h+var_378], ebx; int
0x140106c28  test    rcx, rcx
0x140106c2b  jz      short loc_140106C76
0x140106c2d  call    GreNamedEscape
0x140106c32  mov     r13d, eax
0x140106c35  test    r12d, r12d
0x140106c38  jnz     loc_140106F16
0x140106c3e  test    r15d, r15d
0x140106c41  jnz     loc_140106F38
0x140106c47  lea     rcx, [rsp+398h+var_2D0]; this
0x140106c4f  call    ??1EUDCCountRegion@@QEAA@XZ; EUDCCountRegion::~EUDCCountRegion(void)
0x140106c54  test    ebx, ebx
0x140106c56  jnz     loc_140107057
0x140106c5c  test    r15d, r15d
0x140106c5f  jnz     loc_1401070A8
0x140106c65  test    r12d, r12d
0x140106c68  jnz     loc_1401070C5
0x140106c6e  mov     eax, r13d
0x140106c71  jmp     loc_140106B35
0x140106c76  mov     rcx, [rsp+398h+var_330]; HDC
0x140106c7b  call    ?GreExtEscape@@YAHPEAUHDC__@@HHPEADH1@Z; GreExtEscape(HDC__ *,int,int,char *,int,char *)
0x140106c80  jmp     short loc_140106C32
0x140106c82  test    rdx, rdx
0x140106c85  jnz     short loc_140106C5C
0x140106c87  jmp     loc_140106B0C
0x140106c8c  movsxd  rax, [rsp+398h+var_328]
0x140106c91  cmp     eax, 104h
0x140106c96  jg      short loc_140106C5C
0x140106c98  lea     rcx, [rsp+398h+var_258]
0x140106ca0  mov     [rsp+398h+Str1], rcx
0x140106ca5  lea     rbx, [rax+rax]
0x140106ca9  mov     qword ptr [rsp+398h+var_378], 2
0x140106cb2  mov     r9, rbx
0x140106cb5  mov     rdx, rbx
0x140106cb8  lea     rcx, [rsp+398h+var_258]
0x140106cc0  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x140106cc7  nop     dword ptr [rax+rax+00h]
0x140106ccc  mov     [rsp+rbx+398h+var_258], di
0x140106cd4  mov     ebx, [rsp+398h+var_324]
0x140106cd8  mov     rax, [rsp+398h+Str1]
0x140106cdd  jmp     loc_140106B93
0x140106ce2  xor     edi, edi
0x140106ce4  mov     r14d, edi
0x140106ce7  mov     esi, edi
0x140106ce9  mov     r15d, esi
0x140106cec  mov     r12d, esi
0x140106cef  mov     r13d, [rsp+398h+var_35C]
0x140106cf4  jmp     loc_140106C5C
0x140106cf9  lea     rdx, aGsesc; "GSESC"
0x140106d00  mov     rcx, rax; Str1
0x140106d03  call    cs:__imp__wcsicmp
0x140106d0a  nop     dword ptr [rax+rax+00h]
0x140106d0f  test    eax, eax
0x140106d11  jnz     loc_140106B9C
0x140106d17  mov     rcx, [rsp+398h+var_338]; struct tagGDISCALE_ESCAPE_ARGUMENT *
0x140106d1c  call    ?GreScalingDispatchEscape@@YAJPEAUtagGDISCALE_ESCAPE_ARGUMENT@@@Z; GreScalingDispatchEscape(tagGDISCALE_ESCAPE_ARGUMENT *)
0x140106d21  test    eax, eax
0x140106d23  jns     loc_140106B33
0x140106d29  jmp     loc_140106B9C
0x140106d2e  mov     rcx, [rsp+398h+var_330]; HDC
0x140106d33  call    ?GreIsUMPD@@YA_NPEAUHDC__@@@Z; GreIsUMPD(HDC__ *)
0x140106d38  test    al, al
0x140106d3a  jz      short loc_140106D86
0x140106d3c  movsxd  rax, [rsp+398h+var_368]
0x140106d41  cmp     eax, 20h ; ' '
0x140106d44  jle     short loc_140106DB0
0x140106d46  mov     rdx, rax
0x140106d49  mov     r8d, 1
0x140106d4f  mov     r14, [rsp+398h+var_338]
0x140106d54  mov     rcx, r14
0x140106d57  call    cs:__imp_?GreProbeForReadFromUntrustedVa@@YAXPEBX_K1@Z; GreProbeForReadFromUntrustedVa(void const *,unsigned __int64,unsigned __int64)
0x140106d5e  nop     dword ptr [rax+rax+00h]
0x140106d63  jmp     short loc_140106D7C
0x140106d65  xor     edi, edi
0x140106d67  mov     r14d, edi
0x140106d6a  mov     esi, edi
0x140106d6c  mov     r15d, esi
0x140106d6f  mov     r12d, esi
0x140106d72  mov     r13d, [rsp+398h+var_35C]
0x140106d77  jmp     loc_140106C5C
0x140106d7c  mov     [rsp+398h+var_350], r14
0x140106d81  jmp     loc_140106BA6
0x140106d86  mov     eax, [rsp+398h+var_368]
0x140106d8a  cmp     eax, 20h ; ' '
0x140106d8d  jle     short loc_140106DB0
0x140106d8f  cmp     eax, 2710000h
0x140106d94  jg      short loc_140106DBF
0x140106d96  mov     edx, 706D7447h
0x140106d9b  mov     ecx, eax
0x140106d9d  call    PALLOCNOZ
0x140106da2  mov     r14, rax
0x140106da5  mov     [rsp+398h+var_350], rax
0x140106daa  mov     eax, [rsp+398h+var_368]
0x140106dae  jmp     short loc_140106DBF
0x140106db0  lea     r14, [rsp+398h+var_298]
0x140106db8  mov     [rsp+398h+var_350], r14
0x140106dbd  jmp     short loc_140106DD3
0x140106dbf  test    r14, r14
0x140106dc2  jz      loc_140106C5C
0x140106dc8  mov     r12d, 1
0x140106dce  mov     [rsp+398h+var_360], r12d
0x140106dd3  movsxd  rdx, eax
0x140106dd6  mov     qword ptr [rsp+398h+var_378], 1
0x140106ddf  mov     r9, rdx
0x140106de2  mov     r8, [rsp+398h+var_338]
0x140106de7  mov     rcx, r14
0x140106dea  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x140106df1  nop     dword ptr [rax+rax+00h]
0x140106df6  jmp     loc_140106BA6
0x140106dfb  xor     edi, edi
0x140106dfd  mov     r14, [rsp+398h+var_350]
0x140106e02  mov     esi, edi
0x140106e04  mov     r15d, esi
0x140106e07  mov     r12d, [rsp+398h+var_360]
0x140106e0c  mov     r13d, [rsp+398h+var_35C]
0x140106e11  jmp     loc_140106C5C
0x140106e16  mov     rcx, [rsp+398h+var_330]; HDC
0x140106e1b  call    ?GreIsUMPD@@YA_NPEAUHDC__@@@Z; GreIsUMPD(HDC__ *)
0x140106e20  test    al, al
0x140106e22  jz      short loc_140106E68
0x140106e24  movsxd  rdx, ebx
0x140106e27  mov     r8d, 1
0x140106e2d  mov     rsi, [rsp+398h+var_320]
0x140106e32  mov     rcx, rsi
0x140106e35  call    cs:__imp_?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z; GreProbeForWriteToUntrustedVa(void *,unsigned __int64,unsigned __int64)
0x140106e3c  nop     dword ptr [rax+rax+00h]
0x140106e41  jmp     short loc_140106E5E
0x140106e43  xor     edi, edi
0x140106e45  mov     r14, [rsp+398h+var_350]
0x140106e4a  mov     esi, edi
0x140106e4c  mov     r15d, esi
0x140106e4f  mov     r12d, [rsp+398h+var_360]
0x140106e54  mov     r13d, [rsp+398h+var_35C]
0x140106e59  jmp     loc_140106C5C
0x140106e5e  mov     [rsp+398h+var_348], rsi
0x140106e63  jmp     loc_140106BAE
0x140106e68  cmp     ebx, 20h ; ' '
0x140106e6b  jg      short loc_140106E7C
0x140106e6d  lea     rsi, [rsp+398h+var_278]
0x140106e75  mov     [rsp+398h+var_348], rsi
0x140106e7a  jmp     short loc_140106EAC
0x140106e7c  cmp     ebx, 2710000h
0x140106e82  jg      short loc_140106E98
0x140106e84  mov     edx, 706D7447h
0x140106e89  mov     ecx, ebx
0x140106e8b  call    PALLOCNOZ
0x140106e90  mov     rsi, rax
0x140106e93  mov     [rsp+398h+var_348], rax
0x140106e98  test    rsi, rsi
0x140106e9b  jz      loc_140106C5C
0x140106ea1  mov     r15d, 1
0x140106ea7  mov     [rsp+398h+var_364], r15d
0x140106eac  movsxd  r8, ebx; Size
0x140106eaf  xor     edx, edx; Val
0x140106eb1  mov     rcx, rsi; void *
0x140106eb4  call    memset_0
0x140106eb9  jmp     loc_140106BAE
0x140106ebe  test    r14, r14
0x140106ec1  jz      loc_140106C05
0x140106ec7  mov     r8, cs:__imp_Win32FreePool
0x140106ece  mov     rdx, r14
0x140106ed1  lea     rcx, [rsp+398h+var_310]
0x140106ed9  call    cs:__imp_PushThreadGuardedObject
0x140106ee0  nop     dword ptr [rax+rax+00h]
0x140106ee5  jmp     loc_140106C05
0x140106eea  test    rsi, rsi
0x140106eed  jz      loc_140106C0E
0x140106ef3  mov     r8, cs:__imp_Win32FreePool
0x140106efa  mov     rdx, rsi
0x140106efd  lea     rcx, [rsp+398h+var_2F0]
0x140106f05  call    cs:__imp_PushThreadGuardedObject
0x140106f0c  nop     dword ptr [rax+rax+00h]
0x140106f11  jmp     loc_140106C0E
0x140106f16  test    r14, r14
0x140106f19  jz      loc_140106C3E
0x140106f1f  lea     rcx, [rsp+398h+var_310]
0x140106f27  call    cs:__imp_PopThreadGuardedObject
0x140106f2e  nop     dword ptr [rax+rax+00h]
0x140106f33  jmp     loc_140106C3E
0x140106f38  test    rsi, rsi
  ... truncated ...
```
