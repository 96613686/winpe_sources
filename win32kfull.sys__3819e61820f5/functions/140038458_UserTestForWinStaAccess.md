# _UserTestForWinStaAccess

- ea: `0x140038458`
- end: `0x140038775`
- name: `_UserTestForWinStaAccess`
- size: `797`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401e48a0`

## callees

- `0x1400381a8`
- `0x140038458`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x1400385e7`
- `ntoskrnl!ObCloseHandle` at `0x1400385e7`
- `ntoskrnl!ExWindowStationObjectType` at `0x14003854b`
- `ntoskrnl!ExWindowStationObjectType` at `0x140038597`
- `ntoskrnl!ObReferenceObjectByName` at `0x140038572`
- `ntoskrnl!ObReferenceObjectByName` at `0x140038572`
- `ntoskrnl!ZwQueryInformationToken` at `0x140038503`
- `ntoskrnl!ZwQueryInformationToken` at `0x140038614`
- `ntoskrnl!ZwQueryInformationToken` at `0x140038666`
- `ntoskrnl!ZwQueryInformationToken` at `0x140038503`
- `ntoskrnl!ZwQueryInformationToken` at `0x140038614`
- `ntoskrnl!ZwQueryInformationToken` at `0x140038666`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400384c6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400384c6`
- `ntoskrnl!ZwClose` at `0x140038530`
- `ntoskrnl!ZwClose` at `0x1400386c0`
- `ntoskrnl!ZwClose` at `0x140038747`
- `ntoskrnl!ZwClose` at `0x140038530`
- `ntoskrnl!ZwClose` at `0x1400386c0`
- `ntoskrnl!ZwClose` at `0x140038747`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400384b0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400384b0`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400385b2`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400385b2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400385c4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400385c4`
- `win32kbase!WinStaMapping` at `0x140038720`
- `win32kbase!AccessCheckObject` at `0x14003872c`
- `win32kbase!AccessCheckObject` at `0x14003872c`
- `win32kbase!luidSystem` at `0x140038707`
- `win32kbase!OpenEffectiveToken` at `0x1400384d8`
- `win32kbase!OpenEffectiveToken` at `0x1400384d8`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x140038635`
- `win32kbase!Win32AllocPoolWithQuotaZInit` at `0x140038635`
- `win32kbase!Win32FreePool` at `0x1400386cf`
- `win32kbase!Win32FreePool` at `0x1400386cf`
- `WIN32K!W32GetUserSessionState` at `0x14003867d`
- `WIN32K!W32GetUserSessionState` at `0x140038693`
- `WIN32K!W32GetUserSessionState` at `0x14003867d`
- `WIN32K!W32GetUserSessionState` at `0x140038693`

## pseudocode

```c
int __fastcall UserTestForWinStaAccess(PCUNICODE_STRING String1, int a2)
{
  ACCESS_MASK v4; // esi
  BOOLEAN v5; // bl
  int result; // eax
  int v7; // eax
  NTSTATUS v8; // ebx
  NTSTATUS v9; // ebx
  _DWORD *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 UserSessionState; // rax
  __int64 v20; // r8
  int v21; // edx
  __int64 v22; // rcx
  int v23; // eax
  HANDLE TokenHandle; // [rsp+40h] [rbp-30h] BYREF
  PVOID Object; // [rsp+48h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-18h] BYREF
  ULONG TokenInformationLength; // [rsp+A0h] [rbp+30h] BYREF
  int TokenInformation; // [rsp+A8h] [rbp+38h] BYREF

  TokenInformationLength = 0;
  Handle = 0;
  TokenHandle = 0;
  Object = 0;
  TokenInformation = 0;
  DestinationString = 0;
  v4 = 0x20000000;
  RtlInitUnicodeString(&DestinationString, L"\\Windows\\WindowStations\\WinSta0");
  v5 = RtlEqualUnicodeString(String1, &DestinationString, 1u);
  result = OpenEffectiveToken(&TokenHandle);
  if ( result >= 0 )
  {
    result = ZwQueryInformationToken(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &TokenInformationLength);
    if ( result >= 0 )
    {
      if ( TokenInformation )
        v4 = 131104;
    }
  }
  if ( v5 )
  {
    if ( !TokenHandle )
      return result;
    v8 = ZwQueryInformationToken(TokenHandle, TokenStatistics, 0, 0, &TokenInformationLength);
    if ( v8 == -1073741789 )
    {
      v10 = (_DWORD *)Win32AllocPoolWithQuotaZInit(TokenInformationLength, 1702064981);
      if ( v10 )
      {
        v8 = ZwQueryInformationToken(TokenHandle, TokenStatistics, v10, TokenInformationLength, &TokenInformationLength);
        if ( v8 >= 0 )
        {
          v8 = -1073741790;
          if ( *(_QWORD *)(W32GetUserSessionState(v12, v11, v13, v14) + 63288) )
          {
            UserSessionState = W32GetUserSessionState(v16, v15, v17, v18);
            v21 = v10[2];
            v22 = *(_QWORD *)(UserSessionState + 63288);
            v23 = *(_DWORD *)(v22 + 152);
            if ( a2 )
            {
              if ( v21 == v23 && v10[3] == *(_DWORD *)(v22 + 156)
                || v21 == luidSystem[0] && v10[3] == luidSystem[1]
                || (LOBYTE(v20) = 1, (unsigned int)AccessCheckObject(v22, v4, v20, WinStaMapping)) )
              {
                v8 = 0;
              }
            }
            else if ( v21 == v23 && v10[3] == *(_DWORD *)(v22 + 156) )
            {
              v8 = 0;
            }
          }
        }
        ZwClose(TokenHandle);
        Win32FreePool(v10);
        return v8;
      }
      v8 = -1073741801;
    }
    ZwClose(TokenHandle);
    return v8;
  }
  if ( TokenHandle )
    ZwClose(TokenHandle);
  v7 = ObReferenceObjectByName(String1, 64, 0, v4, ExWindowStationObjectType, 0, 0, &Object);
  v8 = v7;
  if ( v7 < 0 )
  {
    SetLastNtError((unsigned int)v7);
    return v8;
  }
  v9 = ObOpenObjectByPointer(Object, 0x40u, 0, v4, ExWindowStationObjectType, 1, &Handle);
  ObfDereferenceObject(Object);
  if ( v9 >= 0 && Handle )
    return ObCloseHandle(Handle, 1);
  else
    return -1073741790;
}

```

## disassembly

```asm
0x140038458  mov     [rsp-18h+arg_0], rbx
0x14003845d  mov     [rsp-18h+arg_8], rsi
0x140038462  push    rbp
0x140038463  push    rdi
0x140038464  push    r14
0x140038466  mov     rbp, rsp
0x140038469  sub     rsp, 70h
0x14003846d  mov     r14d, edx
0x140038470  mov     [rbp+TokenInformationLength], 0
0x140038477  mov     rdi, rcx
0x14003847a  mov     [rbp+var_20], 0
0x140038482  xorps   xmm0, xmm0
0x140038485  mov     [rbp+TokenHandle], 0
0x14003848d  lea     rdx, SourceString; "\\Windows\\WindowStations\\WinSta0"
0x140038494  mov     [rbp+Object], 0
0x14003849c  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400384a0  mov     [rbp+TokenInformation], 0
0x1400384a7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400384ab  mov     esi, 20000000h
0x1400384b0  call    cs:__imp_RtlInitUnicodeString
0x1400384b7  nop     dword ptr [rax+rax+00h]
0x1400384bc  mov     r8b, 1; CaseInSensitive
0x1400384bf  lea     rdx, [rbp+DestinationString]; String2
0x1400384c3  mov     rcx, rdi; String1
0x1400384c6  call    cs:__imp_RtlEqualUnicodeString
0x1400384cd  nop     dword ptr [rax+rax+00h]
0x1400384d2  lea     rcx, [rbp+TokenHandle]
0x1400384d6  mov     bl, al
0x1400384d8  call    cs:__imp_OpenEffectiveToken
0x1400384df  nop     dword ptr [rax+rax+00h]
0x1400384e4  test    eax, eax
0x1400384e6  js      short loc_14003851F
0x1400384e8  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1400384ec  lea     rax, [rbp+TokenInformationLength]
0x1400384f0  mov     r9d, 4; TokenInformationLength
0x1400384f6  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1400384fb  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1400384ff  lea     edx, [r9+19h]; TokenInformationClass
0x140038503  call    cs:__imp_ZwQueryInformationToken
0x14003850a  nop     dword ptr [rax+rax+00h]
0x14003850f  test    eax, eax
0x140038511  js      short loc_14003851F
0x140038513  cmp     [rbp+TokenInformation], 0
0x140038517  mov     ecx, 20020h
0x14003851c  cmovnz  esi, ecx
0x14003851f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140038523  test    bl, bl
0x140038525  jnz     loc_1400385F8
0x14003852b  test    rcx, rcx
0x14003852e  jz      short loc_14003853C
0x140038530  call    cs:__imp_ZwClose
0x140038537  nop     dword ptr [rax+rax+00h]
0x14003853c  lea     rax, [rbp+Object]
0x140038540  xor     r8d, r8d
0x140038543  mov     [rsp+70h+var_38], rax
0x140038548  mov     r9d, esi
0x14003854b  mov     rax, cs:__imp_ExWindowStationObjectType
0x140038552  mov     [rsp+70h+Handle], 0
0x14003855b  lea     r14d, [r8+40h]
0x14003855f  mov     [rsp+70h+AccessMode], 0
0x140038564  mov     edx, r14d
0x140038567  mov     rcx, [rax]
0x14003856a  mov     [rsp+70h+ReturnLength], rcx
0x14003856f  mov     rcx, rdi
0x140038572  call    cs:__imp_ObReferenceObjectByName
0x140038579  nop     dword ptr [rax+rax+00h]
0x14003857e  mov     ebx, eax
0x140038580  test    eax, eax
0x140038582  js      loc_1400386FA
0x140038588  lea     rax, [rbp+var_20]
0x14003858c  mov     r9d, esi; DesiredAccess
0x14003858f  mov     [rsp+70h+Handle], rax; Handle
0x140038594  xor     r8d, r8d; PassedAccessState
0x140038597  mov     rax, cs:__imp_ExWindowStationObjectType
0x14003859e  mov     edx, r14d; HandleAttributes
0x1400385a1  mov     [rsp+70h+AccessMode], 1; AccessMode
0x1400385a6  mov     rcx, [rax]
0x1400385a9  mov     [rsp+70h+ReturnLength], rcx; ObjectType
0x1400385ae  mov     rcx, [rbp+Object]; Object
0x1400385b2  call    cs:__imp_ObOpenObjectByPointer
0x1400385b9  nop     dword ptr [rax+rax+00h]
0x1400385be  mov     rcx, [rbp+Object]; Object
0x1400385c2  mov     ebx, eax
0x1400385c4  call    cs:__imp_ObfDereferenceObject
0x1400385cb  nop     dword ptr [rax+rax+00h]
0x1400385d0  test    ebx, ebx
0x1400385d2  js      loc_1400386F3
0x1400385d8  mov     rcx, [rbp+var_20]; Handle
0x1400385dc  test    rcx, rcx
0x1400385df  jz      loc_1400386F3
0x1400385e5  mov     dl, 1; PreviousMode
0x1400385e7  call    cs:__imp_ObCloseHandle
0x1400385ee  nop     dword ptr [rax+rax+00h]
0x1400385f3  jmp     loc_1400386DD
0x1400385f8  test    rcx, rcx
0x1400385fb  jz      loc_1400386DD
0x140038601  xor     r9d, r9d; TokenInformationLength
0x140038604  lea     rax, [rbp+TokenInformationLength]
0x140038608  xor     r8d, r8d; TokenInformation
0x14003860b  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x140038610  lea     edx, [r9+0Ah]; TokenInformationClass
0x140038614  call    cs:__imp_ZwQueryInformationToken
0x14003861b  nop     dword ptr [rax+rax+00h]
0x140038620  mov     ebx, eax
0x140038622  cmp     eax, 0C0000023h
0x140038627  jnz     loc_140038743
0x14003862d  mov     ecx, [rbp+TokenInformationLength]
0x140038630  mov     edx, 65737355h
0x140038635  call    cs:__imp_Win32AllocPoolWithQuotaZInit
0x14003863c  nop     dword ptr [rax+rax+00h]
0x140038641  mov     rdi, rax
0x140038644  test    rax, rax
0x140038647  jz      loc_14003873E
0x14003864d  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x140038651  lea     rax, [rbp+TokenInformationLength]
0x140038655  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140038659  mov     r8, rdi; TokenInformation
0x14003865c  mov     edx, 0Ah; TokenInformationClass
0x140038661  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x140038666  call    cs:__imp_ZwQueryInformationToken
0x14003866d  nop     dword ptr [rax+rax+00h]
0x140038672  mov     ebx, eax
0x140038674  test    eax, eax
0x140038676  js      short loc_1400386BC
0x140038678  mov     ebx, 0C0000022h
0x14003867d  call    cs:__imp_W32GetUserSessionState
0x140038684  nop     dword ptr [rax+rax+00h]
0x140038689  cmp     qword ptr [rax+0F738h], 0
0x140038691  jz      short loc_1400386BC
0x140038693  call    cs:__imp_W32GetUserSessionState
0x14003869a  nop     dword ptr [rax+rax+00h]
0x14003869f  mov     edx, [rdi+8]
0x1400386a2  mov     rcx, [rax+0F738h]
0x1400386a9  mov     eax, [rcx+98h]
0x1400386af  test    r14d, r14d
0x1400386b2  jnz     short loc_140038703
0x1400386b4  cmp     edx, eax
0x1400386b6  jz      loc_140038762
0x1400386bc  mov     rcx, [rbp+TokenHandle]; Handle
0x1400386c0  call    cs:__imp_ZwClose
0x1400386c7  nop     dword ptr [rax+rax+00h]
0x1400386cc  mov     rcx, rdi
0x1400386cf  call    cs:__imp_Win32FreePool
0x1400386d6  nop     dword ptr [rax+rax+00h]
0x1400386db  mov     eax, ebx
0x1400386dd  lea     r11, [rsp+70h+var_s0]
0x1400386e2  mov     rbx, [r11+20h]
0x1400386e6  mov     rsi, [r11+28h]
0x1400386ea  mov     rsp, r11
0x1400386ed  pop     r14
0x1400386ef  pop     rdi
0x1400386f0  pop     rbp
0x1400386f1  retn
0x1400386f3  mov     eax, 0C0000022h
0x1400386f8  jmp     short loc_1400386DD
0x1400386fa  mov     ecx, ebx
0x1400386fc  call    SetLastNtError
0x140038701  jmp     short loc_1400386DB
0x140038703  cmp     edx, eax
0x140038705  jz      short loc_140038755
0x140038707  mov     rax, cs:__imp_luidSystem
0x14003870e  cmp     edx, [rax]
0x140038710  jnz     short loc_140038720
0x140038712  mov     r9d, [rax+4]
0x140038716  cmp     [rdi+0Ch], r9d
0x14003871a  jnz     short loc_140038720
0x14003871c  xor     ebx, ebx
0x14003871e  jmp     short loc_1400386BC
0x140038720  mov     r9, cs:__imp_WinStaMapping
0x140038727  mov     r8b, 1
0x14003872a  mov     edx, esi
0x14003872c  call    cs:__imp_AccessCheckObject
0x140038733  nop     dword ptr [rax+rax+00h]
0x140038738  test    eax, eax
0x14003873a  jz      short loc_1400386BC
0x14003873c  jmp     short loc_14003871C
0x14003873e  mov     ebx, 0C0000017h
0x140038743  mov     rcx, [rbp+TokenHandle]; Handle
0x140038747  call    cs:__imp_ZwClose
0x14003874e  nop     dword ptr [rax+rax+00h]
0x140038753  jmp     short loc_1400386DB
0x140038755  mov     eax, [rcx+9Ch]
0x14003875b  cmp     [rdi+0Ch], eax
0x14003875e  jz      short loc_14003871C
0x140038760  jmp     short loc_140038707
0x140038762  mov     ecx, [rcx+9Ch]
0x140038768  xor     edx, edx
0x14003876a  cmp     [rdi+0Ch], ecx
0x14003876d  cmovz   ebx, edx
0x140038770  jmp     loc_1400386BC
```
