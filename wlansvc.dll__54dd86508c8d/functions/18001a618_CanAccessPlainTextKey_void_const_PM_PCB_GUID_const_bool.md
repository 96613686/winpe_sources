# CanAccessPlainTextKey(void * const,PM_PCB &,_GUID const &,bool)

- ea: `0x18001a618`
- end: `0x18001a8e6`
- name: `?CanAccessPlainTextKey@@YA_NQEAXAEAUPM_PCB@@AEBU_GUID@@_N@Z`
- size: `718`
- prototype: `bool __fastcall(HANDLE TokenHandle, struct PM_PCB *, const struct _GUID *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003e670`

## callees

- `0x18000a994`
- `0x18000aa0c`
- `0x18000c5a0`
- `0x18000c800`
- `0x180011530`
- `0x18001a618`
- `0x18001a8ec`
- `0x1800288c4`
- `0x18002f450`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a75f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a75f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a74c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a74c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a730`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001a71a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001a71a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001a6e8`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001a6e8`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001a7cf`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001a7e3`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001a7cf`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001a7e3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a6f9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a6f9`
- `MobileNetworking!VerifyRpcClientAccess` at `0x18001a80e`
- `MobileNetworking!VerifyRpcClientAccess` at `0x18001a80e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall CanAccessPlainTextKey(HANDLE TokenHandle, struct PM_PCB *a2, const struct _GUID *a3, __int64 a4)
{
  char v4; // r13
  void **ProfileOwnerSid; // rax
  void *v7; // rdi
  wil *v8; // rcx
  struct PM_PCB *v9; // rbx
  DWORD TokenUserInfo; // esi
  void *v11; // r15
  PSID v12; // rsi
  DWORD LengthSid; // r12d
  struct PM_PCB *v14; // rax
  struct PM_PCB *v15; // r14
  HANDLE ProcessHeap; // rax
  struct PM_PCB *v17; // rcx
  int v18; // ebx
  unsigned int v20; // eax
  int v21; // eax
  unsigned int lpMem; // [rsp+20h] [rbp-68h]
  LPVOID lpMema; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v24[2]; // [rsp+28h] [rbp-60h] BYREF
  struct PM_PCB *v25; // [rsp+38h] [rbp-50h]
  char v26; // [rsp+40h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  struct PM_PCB *v29; // [rsp+98h] [rbp+10h] BYREF
  const struct _GUID *v30; // [rsp+A0h] [rbp+18h]

  v30 = a3;
  v29 = a2;
  v4 = a4;
  if ( (*((_BYTE *)a2 + 72) & 3) == 0 )
  {
    try
    {
      v24[0] = 0;
      ProfileOwnerSid = (void **)GetProfileOwnerSid(&lpMema, a2, a3);
      v7 = *ProfileOwnerSid;
      *ProfileOwnerSid = 0;
      v24[0] = v7;
      v8 = (wil *)lpMema;
      if ( lpMema )
        FreeWLMem(lpMema);
    }
    catch ( ... )
    {
      v21 = wil::ResultFromCaughtException(v8);
      if ( v21 != -2147023728 )
        throw;
      v20 = StSaveProfileCreatorSIDMetaData(v30, (struct _GUID *)((char *)v29 + 56), TokenHandle);
      if ( v20 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xD97,
          (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
          (const char *)v20,
          lpMem);
      goto LABEL_42;
    }
    v29 = 0;
    v24[1] = &v29;
    v26 = 1;
    lpMema = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 22, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids);
    }
    v9 = 0;
    v25 = 0;
    TokenUserInfo = GetTokenUserInfo(TokenHandle, (struct _TOKEN_USER **)&lpMema);
    v11 = lpMema;
    if ( !TokenUserInfo )
    {
      v12 = *(PSID *)lpMema;
      if ( *(_QWORD *)lpMema && IsValidSid(*(PSID *)lpMema) )
      {
        LengthSid = GetLengthSid(v12);
        v14 = (struct PM_PCB *)AllocWLMem(LengthSid);
        v15 = v14;
        if ( v14 && CopySid(LengthSid, v14, v12) )
        {
          TokenUserInfo = 0;
          v9 = v15;
          v25 = v15;
        }
        else
        {
          TokenUserInfo = GetLastError();
          if ( TokenUserInfo && v15 )
            FreeWLMem(v15);
        }
      }
      else
      {
        TokenUserInfo = 87;
      }
    }
    if ( v11 )
    {
      ProcessHeap = GetProcessHeap();
      if ( ProcessHeap )
        HeapFree(ProcessHeap, 0, v11);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 23, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, TokenUserInfo);
    }
    if ( TokenUserInfo )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xD7C,
        (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
        (const char *)TokenUserInfo,
        (unsigned int)lpMema);
    v17 = v29;
    v29 = v9;
    if ( v17 )
    {
      FreeWLMem(v17);
      v9 = v29;
    }
    v18 = wlansvc::profile::g_shim(v9);
    if ( v29 )
      FreeWLMem(v29);
    if ( v18 )
    {
      if ( v7 )
        FreeWLMem(v7);
      return 1;
    }
    if ( IsWellKnownSid(v7, WinWorldSid) || IsWellKnownSid(v7, WinLocalSystemSid) )
    {
LABEL_42:
      std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>(v24);
      return 1;
    }
    if ( v7 )
      FreeWLMem(v7);
  }
  if ( !v4 )
    return (unsigned int)VerifyRpcClientAccess(13, 131073, a3, a4) == 0;
  return 1;
}

```

## disassembly

```asm
0x18001a618  mov     rax, rsp
0x18001a61b  mov     [rax+18h], r8
0x18001a61f  mov     [rax+10h], rdx
0x18001a623  mov     [rax+8], rcx
0x18001a627  push    rbx
0x18001a628  push    rsi
0x18001a629  push    rdi
0x18001a62a  push    r12
0x18001a62c  push    r13
0x18001a62e  push    r14
0x18001a630  push    r15
0x18001a632  sub     rsp, 50h
0x18001a636  mov     r13b, r9b
0x18001a639  mov     rsi, rcx
0x18001a63c  test    byte ptr [rdx+48h], 3
0x18001a640  jnz     loc_18001A7FF
0x18001a646  mov     qword ptr [rax-60h], 0
0x18001a64e  lea     rcx, [rax-68h]
0x18001a652  call    ?GetProfileOwnerSid@@YA?AV?$unique_ptr@EU?$integral_constant@P6AHPEAX@Z$1?FreeWLMem@@YAH0@Z@std@@@std@@AEBUPM_PCB@@AEBU_GUID@@@Z; GetProfileOwnerSid(PM_PCB const &,_GUID const &)
0x18001a657  mov     rdi, [rax]
0x18001a65a  mov     qword ptr [rax], 0
0x18001a661  mov     [rsp+88h+var_60], rdi
0x18001a666  mov     rcx, [rsp+88h+lpMem]
0x18001a66b  test    rcx, rcx
0x18001a66e  jz      short loc_18001A676
0x18001a670  call    FreeWLMem
0x18001a675  nop
0x18001a676  mov     [rsp+88h+arg_8], 0
0x18001a682  lea     rax, [rsp+88h+arg_8]
0x18001a68a  mov     [rsp+88h+var_58], rax
0x18001a68f  mov     [rsp+88h+var_48], 1
0x18001a694  mov     [rsp+88h+lpMem], 0; unsigned int
0x18001a69d  lea     r14, WPP_GLOBAL_Control
0x18001a6a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6ab  cmp     rcx, r14
0x18001a6ae  jz      short loc_18001A6BA
0x18001a6b0  cmp     byte ptr [rcx+69h], 4
0x18001a6b4  jnb     loc_18001A881
0x18001a6ba  xor     ebx, ebx
0x18001a6bc  mov     [rsp+88h+var_50], rbx
0x18001a6c1  lea     rdx, [rsp+88h+lpMem]; struct _TOKEN_USER **
0x18001a6c6  mov     rcx, rsi; TokenHandle
0x18001a6c9  call    ?GetTokenUserInfo@@YAKPEAXPEAPEAU_TOKEN_USER@@@Z; GetTokenUserInfo(void *,_TOKEN_USER * *)
0x18001a6ce  mov     esi, eax
0x18001a6d0  mov     r15, [rsp+88h+lpMem]
0x18001a6d5  test    eax, eax
0x18001a6d7  jnz     short loc_18001A747
0x18001a6d9  mov     rsi, [r15]
0x18001a6dc  test    rsi, rsi
0x18001a6df  jz      loc_18001A8BB
0x18001a6e5  mov     rcx, rsi; pSid
0x18001a6e8  call    cs:__imp_IsValidSid
0x18001a6ee  test    eax, eax
0x18001a6f0  jz      loc_18001A8BB
0x18001a6f6  mov     rcx, rsi; pSid
0x18001a6f9  call    cs:__imp_GetLengthSid
0x18001a6ff  mov     r12d, eax
0x18001a702  mov     ecx, eax; dwBytes
0x18001a704  call    AllocWLMem
0x18001a709  mov     r14, rax
0x18001a70c  test    rax, rax
0x18001a70f  jz      short loc_18001A730
0x18001a711  mov     r8, rsi; pSourceSid
0x18001a714  mov     rdx, rax; pDestinationSid
0x18001a717  mov     ecx, r12d; nDestinationSidLength
0x18001a71a  call    cs:__imp_CopySid
0x18001a720  test    eax, eax
0x18001a722  jz      short loc_18001A730
0x18001a724  xor     esi, esi
0x18001a726  mov     rbx, r14
0x18001a729  mov     [rsp+88h+var_50], rbx
0x18001a72e  jmp     short loc_18001A740
0x18001a730  call    cs:__imp_GetLastError
0x18001a736  mov     esi, eax
0x18001a738  test    eax, eax
0x18001a73a  jnz     loc_18001A8A5
0x18001a740  lea     r14, WPP_GLOBAL_Control
0x18001a747  test    r15, r15
0x18001a74a  jz      short loc_18001A765
0x18001a74c  call    cs:__imp_GetProcessHeap
0x18001a752  test    rax, rax
0x18001a755  jz      short loc_18001A765
0x18001a757  mov     r8, r15; lpMem
0x18001a75a  xor     edx, edx; dwFlags
0x18001a75c  mov     rcx, rax; hHeap
0x18001a75f  call    cs:__imp_HeapFree
0x18001a765  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a76c  cmp     rcx, r14
0x18001a76f  jnz     loc_18001A83B
0x18001a775  mov     rcx, [rsp+88h]; this
0x18001a77d  test    esi, esi
0x18001a77f  jnz     loc_18001A86C
0x18001a785  mov     rcx, [rsp+88h+arg_8]
0x18001a78d  mov     [rsp+88h+arg_8], rbx
0x18001a795  test    rcx, rcx
0x18001a798  jnz     loc_18001A8C5
0x18001a79e  mov     rdx, rdi
0x18001a7a1  mov     rcx, rbx
0x18001a7a4  mov     rax, cs:?g_shim@profile@wlansvc@@3UWin32Shim@12@A; wlansvc::profile::Win32Shim wlansvc::profile::g_shim
0x18001a7ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7b0  mov     ebx, eax
0x18001a7b2  mov     rcx, [rsp+88h+arg_8]
0x18001a7ba  test    rcx, rcx
0x18001a7bd  jz      short loc_18001A7C5
0x18001a7bf  call    FreeWLMem
0x18001a7c4  nop
0x18001a7c5  test    ebx, ebx
0x18001a7c7  jnz     short loc_18001A829
0x18001a7c9  lea     edx, [rbx+1]; WellKnownSidType
0x18001a7cc  mov     rcx, rdi; pSid
0x18001a7cf  call    cs:__imp_IsWellKnownSid
0x18001a7d5  test    eax, eax
0x18001a7d7  jnz     loc_18001A8D7
0x18001a7dd  lea     edx, [rbx+16h]; WellKnownSidType
0x18001a7e0  mov     rcx, rdi; pSid
0x18001a7e3  call    cs:__imp_IsWellKnownSid
0x18001a7e9  test    eax, eax
0x18001a7eb  jnz     loc_18001A8D7
0x18001a7f1  test    rdi, rdi
0x18001a7f4  jz      short loc_18001A7FF
0x18001a7f6  mov     rcx, rdi
0x18001a7f9  call    FreeWLMem
0x18001a7fe  nop
0x18001a7ff  test    r13b, r13b
0x18001a802  jnz     short loc_18001A837
0x18001a804  mov     edx, 20001h
0x18001a809  mov     ecx, 0Dh
0x18001a80e  call    cs:__imp_VerifyRpcClientAccess
0x18001a814  test    eax, eax
0x18001a816  setz    al
0x18001a819  add     rsp, 50h
0x18001a81d  pop     r15
0x18001a81f  pop     r14
0x18001a821  pop     r13
0x18001a823  pop     r12
0x18001a825  pop     rdi
0x18001a826  pop     rsi
0x18001a827  pop     rbx
0x18001a828  retn
0x18001a829  test    rdi, rdi
0x18001a82c  jz      short loc_18001A837
0x18001a82e  mov     rcx, rdi
0x18001a831  call    FreeWLMem
0x18001a836  nop
0x18001a837  mov     al, 1
0x18001a839  jmp     short loc_18001A819
0x18001a83b  cmp     byte ptr [rcx+69h], 4
0x18001a83f  jb      loc_18001A775
0x18001a845  test    byte ptr [rcx+6Ch], 1
0x18001a849  jz      loc_18001A775
0x18001a84f  mov     edx, 17h
0x18001a854  mov     r9d, esi
0x18001a857  lea     r8, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x18001a85e  mov     rcx, [rcx+60h]
0x18001a862  call    WPP_SF_d
0x18001a867  jmp     loc_18001A775
0x18001a86c  mov     r9d, esi; char *
0x18001a86f  lea     r8, aOnecoreuapNetW_63; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x18001a876  mov     edx, 0D7Ch; void *
0x18001a87b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001a881  test    byte ptr [rcx+6Ch], 1
0x18001a885  jz      loc_18001A6BA
0x18001a88b  mov     edx, 16h
0x18001a890  lea     r8, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x18001a897  mov     rcx, [rcx+60h]
0x18001a89b  call    WPP_SF_
0x18001a8a0  jmp     loc_18001A6BA
0x18001a8a5  test    r14, r14
0x18001a8a8  jz      loc_18001A740
0x18001a8ae  mov     rcx, r14
0x18001a8b1  call    FreeWLMem
0x18001a8b6  jmp     loc_18001A740
0x18001a8bb  mov     esi, 57h ; 'W'
0x18001a8c0  jmp     loc_18001A747
0x18001a8c5  call    FreeWLMem
0x18001a8ca  mov     rbx, [rsp+88h+arg_8]
0x18001a8d2  jmp     loc_18001A79E
0x18001a8d7  lea     rcx, [rsp+88h+var_60]
0x18001a8dc  call    ??1?$unique_ptr@U_DOT11_OFFLOAD_NETWORK_V2@@U?$integral_constant@P6AHPEAX@Z$1?FreeWLMem@@YAH0@Z@std@@@std@@QEAA@XZ; std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>(void)
0x18001a8e1  jmp     loc_18001A837
```
