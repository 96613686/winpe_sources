# AutoProfile::LoadProfile(HKEY__ * &)

- ea: `0x180006524`
- end: `0x180006739`
- name: `?LoadProfile@AutoProfile@@QEAAJAEAPEAUHKEY__@@@Z`
- size: `533`
- prototype: `__int64 __fastcall(AutoProfile *__hidden this, HKEY *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002770`
- `0x1800043c0`
- `0x180011cf0`

## callees

- `0x180006524`
- `0x180007ca8`
- `0x180007d10`
- `0x180013838`
- `0x180015680`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006658`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800065d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800065d5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800065eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800065eb`
- `wbemcomn!GetMemLogObject` at `0x180006689`
- `wbemcomn!GetMemLogObject` at `0x180006689`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006695`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006695`
- `wbemcomn!ErrorTrace` at `0x180006678`
- `wbemcomn!ErrorTrace` at `0x180006678`
- `wbemcomn!DebugTrace` at `0x180006592`
- `wbemcomn!DebugTrace` at `0x1800066f3`
- `wbemcomn!DebugTrace` at `0x180006592`
- `wbemcomn!DebugTrace` at `0x1800066f3`
- `USERENV!GetProfileType` at `0x180006574`
- `USERENV!GetProfileType` at `0x180006574`
- `USERENV!LoadUserProfileW` at `0x180006643`
- `USERENV!LoadUserProfileW` at `0x180006643`
- `SspiCli!GetUserNameExW` at `0x180006615`
- `SspiCli!GetUserNameExW` at `0x180006615`

## pseudocode

```c
__int64 __fastcall AutoProfile::LoadProfile(AutoProfile *this, HKEY *a2)
{
  __int64 result; // rax
  HANDLE CurrentThread; // rax
  DWORD LastError; // edi
  int v7; // ebx
  CMemoryLog *MemLogObject; // rax
  __int64 v9; // r8
  HKEY hProfile; // rcx
  DWORD dwFlags; // [rsp+30h] [rbp-D0h] BYREF
  ULONG nSize; // [rsp+34h] [rbp-CCh] BYREF
  _PROFILEINFOW ProfileInfo; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR NameBuffer[264]; // [rsp+70h] [rbp-90h] BYREF

  dwFlags = 0;
  memset(&ProfileInfo, 0, sizeof(ProfileInfo));
  if ( GetProfileType(&dwFlags) )
  {
    DebugTrace(9, "Profile@0x%x GetProfileType = 0x%x.\n", (_DWORD)this, dwFlags);
    *a2 = HKEY_CURRENT_USER;
    return 0;
  }
  if ( *(_DWORD *)this )
  {
    *a2 = (HKEY)*((_QWORD *)this + 2);
    return 0;
  }
  memset(&ProfileInfo, 0, sizeof(ProfileInfo));
  ProfileInfo.dwSize = 56;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, (PHANDLE)this + 1) )
  {
    nSize = 257;
    NameBuffer[0] = 0;
    if ( GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
    {
      ProfileInfo.dwFlags = 1;
      ProfileInfo.lpUserName = NameBuffer;
      WbemCoRevertToSelf();
      if ( LoadUserProfileW(*((HANDLE *)this + 1), &ProfileInfo) )
      {
        DebugTrace(9, "Profile@0x%x %S loaded.\n", (_DWORD)this, ProfileInfo.lpUserName);
        result = WbemCoImpersonateClient();
        hProfile = (HKEY)ProfileInfo.hProfile;
        *((_QWORD *)this + 2) = ProfileInfo.hProfile;
        *(_DWORD *)this = 1;
        *a2 = hProfile;
        return result;
      }
      *a2 = 0;
      LastError = GetLastError();
      ErrorTrace(9, "Profile@0x%x %S loading failed 0x%x.\n", (_DWORD)this, ProfileInfo.lpUserName, LastError);
      v7 = WbemCoImpersonateClient();
      if ( v7 < 0 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -1);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v9, (unsigned int)v7);
        }
      }
      if ( LastError == 5 || LastError == 1314 )
        return 2147749891LL;
    }
  }
  return 2147749889LL;
}

```

## disassembly

```asm
0x180006524  mov     [rsp-8+arg_10], rbx
0x180006529  push    rbp
0x18000652a  push    rsi
0x18000652b  push    rdi
0x18000652c  lea     rbp, [rsp-190h]
0x180006534  sub     rsp, 290h
0x18000653b  mov     rax, cs:__security_cookie
0x180006542  xor     rax, rsp
0x180006545  mov     [rbp+1A0h+var_20], rax
0x18000654c  xorps   xmm0, xmm0
0x18000654f  xor     eax, eax
0x180006551  mov     rbx, rcx
0x180006554  mov     [rsp+2A0h+ProfileInfo.hProfile], rax
0x180006559  lea     rcx, [rsp+2A0h+dwFlags]; dwFlags
0x18000655e  mov     [rsp+2A0h+dwFlags], eax
0x180006562  movups  xmmword ptr [rsp+2A0h+ProfileInfo.dwSize], xmm0
0x180006567  mov     rdi, rdx
0x18000656a  movups  xmmword ptr [rsp+2A0h+ProfileInfo.lpProfilePath], xmm0
0x18000656f  movups  xmmword ptr [rsp+2A0h+ProfileInfo.lpServerName], xmm0
0x180006574  call    cs:__imp_GetProfileType
0x18000657a  test    eax, eax
0x18000657c  jz      short loc_1800065A6
0x18000657e  mov     r9d, [rsp+2A0h+dwFlags]
0x180006583  lea     rdx, aProfile0xXGetp; "Profile@0x%x GetProfileType = 0x%x.\n"
0x18000658a  mov     r8, rbx
0x18000658d  mov     ecx, 9
0x180006592  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x180006598  mov     qword ptr [rdi], 0FFFFFFFF80000001h
0x18000659f  xor     eax, eax
0x1800065a1  jmp     loc_180006717
0x1800065a6  cmp     dword ptr [rbx], 0
0x1800065a9  jz      short loc_1800065B4
0x1800065ab  mov     rax, [rbx+10h]
0x1800065af  mov     [rdi], rax
0x1800065b2  jmp     short loc_18000659F
0x1800065b4  xorps   xmm0, xmm0
0x1800065b7  xor     eax, eax
0x1800065b9  movups  xmmword ptr [rsp+2A0h+ProfileInfo.dwSize], xmm0
0x1800065be  mov     [rsp+2A0h+ProfileInfo.dwSize], 38h ; '8'
0x1800065c6  movups  xmmword ptr [rsp+2A0h+ProfileInfo.lpProfilePath], xmm0
0x1800065cb  mov     [rsp+2A0h+ProfileInfo.hProfile], rax
0x1800065d0  movups  xmmword ptr [rsp+2A0h+ProfileInfo.lpServerName], xmm0
0x1800065d5  call    cs:__imp_GetCurrentThread
0x1800065db  mov     edx, 0Eh; DesiredAccess
0x1800065e0  lea     r9, [rbx+8]; TokenHandle
0x1800065e4  mov     rcx, rax; ThreadHandle
0x1800065e7  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1800065eb  call    cs:__imp_OpenThreadToken
0x1800065f1  test    eax, eax
0x1800065f3  jz      loc_180006712
0x1800065f9  xor     eax, eax
0x1800065fb  mov     [rsp+2A0h+nSize], 101h
0x180006603  lea     r8, [rsp+2A0h+nSize]; nSize
0x180006608  mov     [rsp+2A0h+NameBuffer], ax
0x18000660d  lea     rdx, [rsp+2A0h+NameBuffer]; lpNameBuffer
0x180006612  lea     ecx, [rax+2]; NameFormat
0x180006615  call    cs:__imp_GetUserNameExW
0x18000661b  test    al, al
0x18000661d  jz      loc_180006712
0x180006623  lea     rax, [rsp+2A0h+NameBuffer]
0x180006628  mov     [rsp+2A0h+ProfileInfo.dwFlags], 1
0x180006630  mov     [rsp+2A0h+ProfileInfo.lpUserName], rax
0x180006635  call    ?WbemCoRevertToSelf@@YAJXZ; WbemCoRevertToSelf(void)
0x18000663a  mov     rcx, [rbx+8]; hToken
0x18000663e  lea     rdx, [rsp+2A0h+ProfileInfo]; lpProfileInfo
0x180006643  call    cs:__imp_LoadUserProfileW
0x180006649  test    eax, eax
0x18000664b  jnz     loc_1800066DF
0x180006651  mov     qword ptr [rdi], 0
0x180006658  call    cs:__imp_GetLastError
0x18000665e  mov     r9, [rsp+2A0h+ProfileInfo.lpUserName]
0x180006663  lea     rdx, aProfile0xXSLoa; "Profile@0x%x %S loading failed 0x%x.\n"
0x18000666a  mov     r8, rbx
0x18000666d  mov     [rsp+2A0h+var_280], eax
0x180006671  mov     ecx, 9
0x180006676  mov     edi, eax
0x180006678  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x18000667e  call    ?WbemCoImpersonateClient@@YAJXZ; WbemCoImpersonateClient(void)
0x180006683  mov     ebx, eax
0x180006685  test    eax, eax
0x180006687  jns     short loc_1800066CB
0x180006689  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000668f  mov     rcx, rax
0x180006692  or      edx, 0FFFFFFFFh
0x180006695  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000669b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066a2  lea     rax, WPP_GLOBAL_Control
0x1800066a9  cmp     rcx, rax
0x1800066ac  jz      short loc_1800066CB
0x1800066ae  test    byte ptr [rcx+1Ch], 4
0x1800066b2  jz      short loc_1800066CB
0x1800066b4  cmp     byte ptr [rcx+19h], 2
0x1800066b8  jb      short loc_1800066CB
0x1800066ba  mov     rcx, [rcx+10h]
0x1800066be  mov     edx, 0Ah
0x1800066c3  mov     r9d, ebx
0x1800066c6  call    WPP_SF_D
0x1800066cb  cmp     edi, 5
0x1800066ce  jz      short loc_1800066D8
0x1800066d0  cmp     edi, 522h
0x1800066d6  jnz     short loc_180006712
0x1800066d8  mov     eax, 80041003h
0x1800066dd  jmp     short loc_180006717
0x1800066df  mov     r9, [rsp+2A0h+ProfileInfo.lpUserName]
0x1800066e4  lea     rdx, aProfile0xXSLoa_0; "Profile@0x%x %S loaded.\n"
0x1800066eb  mov     r8, rbx
0x1800066ee  mov     ecx, 9
0x1800066f3  call    cs:__imp_?DebugTrace@@YAHDPEBDZZ; DebugTrace(char,char const *,...)
0x1800066f9  call    ?WbemCoImpersonateClient@@YAJXZ; WbemCoImpersonateClient(void)
0x1800066fe  mov     rcx, [rsp+2A0h+ProfileInfo.hProfile]
0x180006703  mov     [rbx+10h], rcx
0x180006707  mov     dword ptr [rbx], 1
0x18000670d  mov     [rdi], rcx
0x180006710  jmp     short loc_180006717
0x180006712  mov     eax, 80041001h
0x180006717  mov     rcx, [rbp+1A0h+var_20]
0x18000671e  xor     rcx, rsp; StackCookie
0x180006721  call    __security_check_cookie
0x180006726  mov     rbx, [rsp+2A0h+arg_10]
0x18000672e  add     rsp, 290h
0x180006735  pop     rdi
0x180006736  pop     rsi
0x180006737  pop     rbp
0x180006738  retn
```
