# GetLocalSystemToken(void * *)

- ea: `0x1800384f4`
- end: `0x180038990`
- name: `?GetLocalSystemToken@@YAJPEAPEAX@Z`
- size: `1180`
- prototype: `__int64 __fastcall(void **, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039080`

## callees

- `0x180001600`
- `0x18002c8d4`
- `0x180036994`
- `0x1800384f4`
- `0x180038ca8`
- `0x18003b000`
- `0x18003b44c`
- `0x18003cb8c`

## import_xrefs

- `KERNEL32!K32EnumProcesses` at `0x18003861b`
- `KERNEL32!K32EnumProcesses` at `0x18003861b`
- `KERNEL32!HeapAlloc` at `0x180038658`
- `KERNEL32!HeapAlloc` at `0x180038658`
- `KERNEL32!GetCurrentThread` at `0x180038586`
- `KERNEL32!GetCurrentThread` at `0x180038586`
- `KERNEL32!OpenProcess` at `0x1800386a9`
- `KERNEL32!OpenProcess` at `0x1800386a9`
- `KERNEL32!GetCurrentProcess` at `0x1800385b3`
- `KERNEL32!GetCurrentProcess` at `0x1800385b3`
- `KERNEL32!CloseHandle` at `0x180038607`
- `KERNEL32!CloseHandle` at `0x180038795`
- `KERNEL32!CloseHandle` at `0x1800387ae`
- `KERNEL32!CloseHandle` at `0x1800387db`
- `KERNEL32!CloseHandle` at `0x1800387ed`
- `KERNEL32!CloseHandle` at `0x18003886a`
- `KERNEL32!CloseHandle` at `0x18003887a`
- `KERNEL32!CloseHandle` at `0x180038895`
- `KERNEL32!CloseHandle` at `0x1800388d8`
- `KERNEL32!CloseHandle` at `0x180038607`
- `KERNEL32!CloseHandle` at `0x180038795`
- `KERNEL32!CloseHandle` at `0x1800387ae`
- `KERNEL32!CloseHandle` at `0x1800387db`
- `KERNEL32!CloseHandle` at `0x1800387ed`
- `KERNEL32!CloseHandle` at `0x18003886a`
- `KERNEL32!CloseHandle` at `0x18003887a`
- `KERNEL32!CloseHandle` at `0x180038895`
- `KERNEL32!CloseHandle` at `0x1800388d8`
- `KERNEL32!GetLastError` at `0x1800385a4`
- `KERNEL32!GetLastError` at `0x1800385ce`
- `KERNEL32!GetLastError` at `0x180038845`
- `KERNEL32!GetLastError` at `0x1800388e3`
- `KERNEL32!GetLastError` at `0x1800388fd`
- `KERNEL32!GetLastError` at `0x180038922`
- `KERNEL32!GetLastError` at `0x18003893c`
- `KERNEL32!GetLastError` at `0x1800385a4`
- `KERNEL32!GetLastError` at `0x1800385ce`
- `KERNEL32!GetLastError` at `0x180038845`
- `KERNEL32!GetLastError` at `0x1800388e3`
- `KERNEL32!GetLastError` at `0x1800388fd`
- `KERNEL32!GetLastError` at `0x180038922`
- `KERNEL32!GetLastError` at `0x18003893c`
- `ADVAPI32!OpenThreadToken` at `0x18003859a`
- `ADVAPI32!OpenThreadToken` at `0x18003859a`
- `ADVAPI32!OpenProcessToken` at `0x1800385c4`
- `ADVAPI32!OpenProcessToken` at `0x1800386cd`
- `ADVAPI32!OpenProcessToken` at `0x180038702`
- `ADVAPI32!OpenProcessToken` at `0x1800385c4`
- `ADVAPI32!OpenProcessToken` at `0x1800386cd`
- `ADVAPI32!OpenProcessToken` at `0x180038702`
- `ADVAPI32!DuplicateTokenEx` at `0x180038732`
- `ADVAPI32!DuplicateTokenEx` at `0x180038732`
- `ADVAPI32!SetKernelObjectSecurity` at `0x18003877d`
- `ADVAPI32!SetKernelObjectSecurity` at `0x18003883b`
- `ADVAPI32!SetKernelObjectSecurity` at `0x18003877d`
- `ADVAPI32!SetKernelObjectSecurity` at `0x18003883b`

## string_xrefs

- `0x18003852f`: `SeDebugPrivilege`
- `0x180038570`: `SeTakeOwnershipPrivilege`

## pseudocode

```c
__int64 __fastcall GetLocalSystemToken(void **a1, int a2)
{
  void **v2; // r13
  struct _TOKEN_USER *v3; // r12
  DWORD *v4; // r15
  struct _TOKEN_USER *v5; // r14
  PSECURITY_DESCRIPTOR v6; // rsi
  int v7; // edx
  unsigned int TokenUser; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  DWORD v12; // edi
  DWORD v13; // edx
  unsigned int i; // r13d
  int v15; // r12d
  struct _TOKEN_USER *v16; // rcx
  struct _TOKEN_USER *v17; // rax
  __int64 v18; // rdx
  signed int v19; // eax
  HANDLE v20; // rcx
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  signed int v24; // eax
  struct _TOKEN_USER *v26; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbNeeded; // [rsp+38h] [rbp-C8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  void **v31; // [rsp+58h] [rbp-A8h]
  HANDLE hExistingToken; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  DWORD idProcess[128]; // [rsp+70h] [rbp-90h] BYREF

  v31 = a1;
  v2 = a1;
  cbNeeded = 0;
  Handle = 0;
  v3 = 0;
  hObject = 0;
  hExistingToken = 0;
  v4 = idProcess;
  TokenHandle = 0;
  v5 = 0;
  v26 = 0;
  v6 = 0;
  SecurityDescriptor = 0;
  TokenUser = SetCurrentPrivilege(L"SeDebugPrivilege", a2);
  if ( TokenUser )
    goto LABEL_46;
  TokenUser = SetCurrentPrivilege(L"SeTakeOwnershipPrivilege", v7);
  if ( TokenUser )
    goto LABEL_46;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    TokenUser = LastError;
    if ( LastError != 1008 )
      goto LABEL_7;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
      LastError = GetLastError();
      TokenUser = LastError;
LABEL_7:
      if ( LastError > 0 )
        TokenUser = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_46;
    }
  }
  v12 = 512;
  TokenUser = GetTokenUser(TokenHandle, &v26);
  CloseHandle(TokenHandle);
  if ( TokenUser )
  {
LABEL_16:
    v5 = v26;
  }
  else
  {
    while ( 1 )
    {
      if ( !K32EnumProcesses(v4, v12, &cbNeeded) )
      {
        v24 = GetLastError();
        TokenUser = v24;
        if ( v24 > 0 )
          TokenUser = (unsigned __int16)v24 | 0x80070000;
        goto LABEL_16;
      }
      v13 = cbNeeded;
      if ( cbNeeded < v12 )
        break;
      if ( v4 != idProcess )
        ServerFree(v4);
      v12 += 256;
      v4 = (DWORD *)HeapAlloc(ghTapisrvHeap, 8u, v12);
      if ( !v4 )
      {
        TokenUser = -2147483580;
        goto LABEL_16;
      }
    }
    v5 = v26;
    for ( i = 1; ; ++i )
    {
      v15 = 0;
      v16 = 0;
      if ( i >= v13 >> 2 )
        goto LABEL_38;
      v17 = (struct _TOKEN_USER *)OpenProcess(0x1FFFFFu, 0, v4[i]);
      v26 = v17;
      v3 = v17;
      if ( !v17 || !OpenProcessToken(v17, 0x60000u, &Handle) )
        break;
      TokenUser = AddSIDToKernelObjectDacl(v5->User.Sid, v18, Handle, &SecurityDescriptor);
      if ( TokenUser )
      {
        v6 = SecurityDescriptor;
        goto LABEL_45;
      }
      if ( !OpenProcessToken(v3, 2u, &hExistingToken)
        || !DuplicateTokenEx(hExistingToken, 0xF01FFu, 0, SecurityImpersonation, TokenPrimary, &hObject) )
      {
        v22 = GetLastError();
        TokenUser = v22;
        if ( v22 > 0 )
          TokenUser = (unsigned __int16)v22 | 0x80070000;
        v6 = SecurityDescriptor;
        goto LABEL_41;
      }
      if ( !(unsigned int)IsLocalSystem(hObject) )
      {
        v15 = 1;
        if ( !(unsigned int)SetTokenDefaultDacl(hObject, v5->User.Sid) )
        {
          v13 = cbNeeded;
          v6 = SecurityDescriptor;
          v16 = v26;
LABEL_38:
          v26 = v16;
          if ( i >= v13 >> 2 )
            TokenUser = 1;
          if ( !v15 )
          {
            v3 = v16;
            goto LABEL_45;
          }
LABEL_41:
          if ( !SetKernelObjectSecurity(Handle, 4u, v6) )
          {
            v19 = GetLastError();
            TokenUser = v19;
            if ( v19 > 0 )
              TokenUser = (unsigned __int16)v19 | 0x80070000;
          }
          v3 = v26;
          goto LABEL_45;
        }
        v3 = v26;
      }
      v6 = SecurityDescriptor;
      if ( !SetKernelObjectSecurity(Handle, 4u, SecurityDescriptor) )
      {
        v21 = GetLastError();
        TokenUser = v21;
        if ( v21 > 0 )
          TokenUser = (unsigned __int16)v21 | 0x80070000;
        goto LABEL_41;
      }
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      if ( hExistingToken )
      {
        CloseHandle(hExistingToken);
        hExistingToken = 0;
      }
      if ( v6 )
      {
        ServerFree(v6);
        v6 = 0;
        SecurityDescriptor = 0;
      }
      if ( Handle )
      {
        CloseHandle(Handle);
        Handle = 0;
      }
      CloseHandle(v3);
      v13 = cbNeeded;
    }
    v23 = GetLastError();
    TokenUser = v23;
    if ( v23 > 0 )
      TokenUser = (unsigned __int16)v23 | 0x80070000;
LABEL_45:
    v2 = v31;
  }
LABEL_46:
  if ( hExistingToken )
    CloseHandle(hExistingToken);
  if ( Handle )
    CloseHandle(Handle);
  if ( v6 )
    ServerFree(v6);
  if ( v3 )
    CloseHandle(v3);
  if ( v4 != idProcess )
    ServerFree(v4);
  if ( v5 )
    ServerFree(v5);
  if ( TokenUser )
  {
    v20 = hObject;
    *v2 = 0;
    if ( v20 )
      CloseHandle(v20);
  }
  else
  {
    *v2 = hObject;
  }
  return TokenUser;
}

```

## disassembly

```asm
0x1800384f4  push    rbp
0x1800384f6  push    rbx
0x1800384f7  push    rsi
0x1800384f8  push    rdi
0x1800384f9  push    r12
0x1800384fb  push    r13
0x1800384fd  push    r14
0x1800384ff  push    r15
0x180038501  lea     rbp, [rsp-188h]
0x180038509  sub     rsp, 288h
0x180038510  mov     rax, cs:__security_cookie
0x180038517  xor     rax, rsp
0x18003851a  mov     [rbp+1C0h+var_50], rax
0x180038521  xor     edi, edi
0x180038523  mov     [rsp+2C0h+var_268], rcx
0x180038528  mov     r13, rcx
0x18003852b  mov     [rsp+2C0h+cbNeeded], edi
0x18003852f  lea     rcx, aSedebugprivile; "SeDebugPrivilege"
0x180038536  mov     [rsp+2C0h+Handle], rdi
0x18003853b  mov     r12d, edi
0x18003853e  mov     [rsp+2C0h+hObject], rdi
0x180038543  mov     [rsp+2C0h+hExistingToken], rdi
0x180038548  lea     r15, [rsp+2C0h+idProcess]
0x18003854d  mov     [rsp+2C0h+TokenHandle], rdi
0x180038552  mov     r14d, edi
0x180038555  mov     [rsp+2C0h+var_290], rdi
0x18003855a  mov     esi, edi
0x18003855c  mov     [rsp+2C0h+SecurityDescriptor], rdi
0x180038561  call    ?SetCurrentPrivilege@@YAJPEBGH@Z; SetCurrentPrivilege(ushort const *,int)
0x180038566  mov     ebx, eax
0x180038568  test    eax, eax
0x18003856a  jnz     loc_180038860
0x180038570  lea     rcx, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x180038577  call    ?SetCurrentPrivilege@@YAJPEBGH@Z; SetCurrentPrivilege(ushort const *,int)
0x18003857c  mov     ebx, eax
0x18003857e  test    eax, eax
0x180038580  jnz     loc_180038860
0x180038586  call    cs:__imp_GetCurrentThread
0x18003858c  lea     r9, [rsp+2C0h+TokenHandle]; TokenHandle
0x180038591  xor     r8d, r8d; OpenAsSelf
0x180038594  mov     rcx, rax; ThreadHandle
0x180038597  lea     edx, [rdi+28h]; DesiredAccess
0x18003859a  call    cs:__imp_OpenThreadToken
0x1800385a0  test    eax, eax
0x1800385a2  jnz     short loc_1800385EC
0x1800385a4  call    cs:__imp_GetLastError
0x1800385aa  mov     ebx, eax
0x1800385ac  cmp     eax, 3F0h
0x1800385b1  jnz     short loc_1800385D6
0x1800385b3  call    cs:__imp_GetCurrentProcess
0x1800385b9  mov     rcx, rax; ProcessHandle
0x1800385bc  lea     r8, [rsp+2C0h+TokenHandle]; TokenHandle
0x1800385c1  lea     edx, [rdi+28h]; DesiredAccess
0x1800385c4  call    cs:__imp_OpenProcessToken
0x1800385ca  test    eax, eax
0x1800385cc  jnz     short loc_1800385EC
0x1800385ce  call    cs:__imp_GetLastError
0x1800385d4  mov     ebx, eax
0x1800385d6  test    eax, eax
0x1800385d8  jle     loc_180038860
0x1800385de  movzx   ebx, ax
0x1800385e1  or      ebx, 80070000h
0x1800385e7  jmp     loc_180038860
0x1800385ec  mov     rcx, [rsp+2C0h+TokenHandle]; TokenHandle
0x1800385f1  lea     rdx, [rsp+2C0h+var_290]; struct _TOKEN_USER **
0x1800385f6  mov     edi, 200h
0x1800385fb  call    ?GetTokenUser@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; GetTokenUser(void *,_TOKEN_USER * *)
0x180038600  mov     rcx, [rsp+2C0h+TokenHandle]; hObject
0x180038605  mov     ebx, eax
0x180038607  call    cs:__imp_CloseHandle
0x18003860d  test    ebx, ebx
0x18003860f  jnz     short loc_18003866B
0x180038611  lea     r8, [rsp+2C0h+cbNeeded]; lpcbNeeded
0x180038616  mov     edx, edi; cb
0x180038618  mov     rcx, r15; lpidProcess
0x18003861b  call    cs:__imp_K32EnumProcesses
0x180038621  test    eax, eax
0x180038623  jz      loc_18003893C
0x180038629  mov     edx, [rsp+2C0h+cbNeeded]
0x18003862d  cmp     edx, edi
0x18003862f  jb      short loc_180038675
0x180038631  lea     rax, [rsp+2C0h+idProcess]
0x180038636  cmp     r15, rax
0x180038639  jz      short loc_180038643
0x18003863b  mov     rcx, r15; lpMem
0x18003863e  call    ServerFree
0x180038643  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18003864a  add     edi, 100h
0x180038650  mov     r8d, edi; dwBytes
0x180038653  mov     edx, 8; dwFlags
0x180038658  call    cs:__imp_HeapAlloc
0x18003865e  mov     r15, rax
0x180038661  test    rax, rax
0x180038664  jnz     short loc_180038611
0x180038666  mov     ebx, 80000044h
0x18003866b  mov     r14, [rsp+2C0h+var_290]
0x180038670  jmp     loc_180038860
0x180038675  mov     r14, [rsp+2C0h+var_290]
0x18003867a  mov     r13d, 1
0x180038680  mov     r8d, r13d
0x180038683  mov     eax, edx
0x180038685  xor     r12d, r12d
0x180038688  shr     eax, 2
0x18003868b  xor     ecx, ecx
0x18003868d  mov     edi, 80070000h
0x180038692  cmp     r13d, eax
0x180038695  jnb     loc_180038816
0x18003869b  mov     r8d, r13d
0x18003869e  xor     edx, edx; bInheritHandle
0x1800386a0  mov     ecx, 1FFFFFh; dwDesiredAccess
0x1800386a5  mov     r8d, [r15+r8*4]; dwProcessId
0x1800386a9  call    cs:__imp_OpenProcess
0x1800386af  mov     [rsp+2C0h+var_290], rax
0x1800386b4  mov     r12, rax
0x1800386b7  test    rax, rax
0x1800386ba  jz      loc_180038922
0x1800386c0  lea     r8, [rsp+2C0h+Handle]; TokenHandle
0x1800386c5  mov     edx, 60000h; DesiredAccess
0x1800386ca  mov     rcx, rax; ProcessHandle
0x1800386cd  call    cs:__imp_OpenProcessToken
0x1800386d3  test    eax, eax
0x1800386d5  jz      loc_180038922
0x1800386db  mov     r8, [rsp+2C0h+Handle]; void *
0x1800386e0  lea     r9, [rsp+2C0h+SecurityDescriptor]; void **
0x1800386e5  mov     rcx, [r14]; pSid
0x1800386e8  call    ?AddSIDToKernelObjectDacl@@YAJPEAXK0PEAPEAX@Z; AddSIDToKernelObjectDacl(void *,ulong,void *,void * *)
0x1800386ed  mov     ebx, eax
0x1800386ef  test    eax, eax
0x1800386f1  jnz     loc_180038918
0x1800386f7  lea     r8, [rsp+2C0h+hExistingToken]; TokenHandle
0x1800386fc  mov     rcx, r12; ProcessHandle
0x1800386ff  lea     edx, [rax+2]; DesiredAccess
0x180038702  call    cs:__imp_OpenProcessToken
0x180038708  test    eax, eax
0x18003870a  jz      loc_1800388FD
0x180038710  mov     rcx, [rsp+2C0h+hExistingToken]; hExistingToken
0x180038715  lea     rax, [rsp+2C0h+hObject]
0x18003871a  mov     [rsp+2C0h+phNewToken], rax; phNewToken
0x18003871f  lea     esi, [rbx+1]
0x180038722  lea     r9d, [rbx+2]; ImpersonationLevel
0x180038726  mov     [rsp+2C0h+TokenType], esi; TokenType
0x18003872a  xor     r8d, r8d; lpTokenAttributes
0x18003872d  mov     edx, 0F01FFh; dwDesiredAccess
0x180038732  call    cs:__imp_DuplicateTokenEx
0x180038738  test    eax, eax
0x18003873a  jz      loc_1800388FD
0x180038740  mov     rcx, [rsp+2C0h+hObject]
0x180038745  call    IsLocalSystem
0x18003874a  test    eax, eax
0x18003874c  jnz     short loc_18003876B
0x18003874e  mov     rdx, [r14]; pSid
0x180038751  mov     r12d, esi
0x180038754  mov     rcx, [rsp+2C0h+hObject]; TokenHandle
0x180038759  call    ?SetTokenDefaultDacl@@YAJPEAX0@Z; SetTokenDefaultDacl(void *,void *)
0x18003875e  test    eax, eax
0x180038760  jz      loc_180038805
0x180038766  mov     r12, [rsp+2C0h+var_290]
0x18003876b  mov     rsi, [rsp+2C0h+SecurityDescriptor]
0x180038770  mov     edx, 4; SecurityInformation
0x180038775  mov     rcx, [rsp+2C0h+Handle]; Handle
0x18003877a  mov     r8, rsi; SecurityDescriptor
0x18003877d  call    cs:__imp_SetKernelObjectSecurity
0x180038783  test    eax, eax
0x180038785  jz      loc_1800388E3
0x18003878b  mov     rcx, [rsp+2C0h+hObject]; hObject
0x180038790  test    rcx, rcx
0x180038793  jz      short loc_1800387A4
0x180038795  call    cs:__imp_CloseHandle
0x18003879b  mov     [rsp+2C0h+hObject], 0
0x1800387a4  mov     rcx, [rsp+2C0h+hExistingToken]; hObject
0x1800387a9  test    rcx, rcx
0x1800387ac  jz      short loc_1800387BD
0x1800387ae  call    cs:__imp_CloseHandle
0x1800387b4  mov     [rsp+2C0h+hExistingToken], 0
0x1800387bd  test    rsi, rsi
0x1800387c0  jz      short loc_1800387D1
0x1800387c2  mov     rcx, rsi; lpMem
0x1800387c5  call    ServerFree
0x1800387ca  xor     esi, esi
0x1800387cc  mov     [rsp+2C0h+SecurityDescriptor], rsi
0x1800387d1  mov     rcx, [rsp+2C0h+Handle]; hObject
0x1800387d6  test    rcx, rcx
0x1800387d9  jz      short loc_1800387EA
0x1800387db  call    cs:__imp_CloseHandle
0x1800387e1  mov     [rsp+2C0h+Handle], 0
0x1800387ea  mov     rcx, r12; hObject
0x1800387ed  call    cs:__imp_CloseHandle
0x1800387f3  mov     edx, [rsp+2C0h+cbNeeded]
0x1800387f7  mov     r8d, 1
0x1800387fd  add     r13d, r8d
0x180038800  jmp     loc_180038683
0x180038805  mov     edx, [rsp+2C0h+cbNeeded]
0x180038809  mov     r8d, r12d
0x18003880c  mov     rsi, [rsp+2C0h+SecurityDescriptor]
0x180038811  mov     rcx, [rsp+2C0h+var_290]
0x180038816  shr     edx, 2
0x180038819  cmp     r13d, edx
0x18003881c  mov     [rsp+2C0h+var_290], rcx
0x180038821  cmovnb  ebx, r8d
0x180038825  test    r12d, r12d
0x180038828  jz      loc_18003895A
0x18003882e  mov     rcx, [rsp+2C0h+Handle]; Handle
0x180038833  mov     r8, rsi; SecurityDescriptor
0x180038836  mov     edx, 4; SecurityInformation
0x18003883b  call    cs:__imp_SetKernelObjectSecurity
0x180038841  test    eax, eax
0x180038843  jnz     short loc_180038856
0x180038845  call    cs:__imp_GetLastError
0x18003884b  mov     ebx, eax
0x18003884d  test    eax, eax
0x18003884f  jle     short loc_180038856
0x180038851  movzx   ebx, ax
0x180038854  or      ebx, edi
0x180038856  mov     r12, [rsp+2C0h+var_290]
0x18003885b  mov     r13, [rsp+2C0h+var_268]
0x180038860  mov     rcx, [rsp+2C0h+hExistingToken]; hObject
0x180038865  test    rcx, rcx
0x180038868  jz      short loc_180038870
0x18003886a  call    cs:__imp_CloseHandle
0x180038870  mov     rcx, [rsp+2C0h+Handle]; hObject
0x180038875  test    rcx, rcx
0x180038878  jz      short loc_180038880
0x18003887a  call    cs:__imp_CloseHandle
0x180038880  test    rsi, rsi
0x180038883  jz      short loc_18003888D
0x180038885  mov     rcx, rsi; lpMem
0x180038888  call    ServerFree
0x18003888d  test    r12, r12
0x180038890  jz      short loc_18003889B
0x180038892  mov     rcx, r12; hObject
0x180038895  call    cs:__imp_CloseHandle
0x18003889b  lea     rax, [rsp+2C0h+idProcess]
0x1800388a0  cmp     r15, rax
0x1800388a3  jz      short loc_1800388AD
0x1800388a5  mov     rcx, r15; lpMem
0x1800388a8  call    ServerFree
0x1800388ad  test    r14, r14
0x1800388b0  jz      short loc_1800388BA
0x1800388b2  mov     rcx, r14; lpMem
0x1800388b5  call    ServerFree
0x1800388ba  test    ebx, ebx
0x1800388bc  jz      loc_180038962
0x1800388c2  mov     rcx, [rsp+2C0h+hObject]; hObject
0x1800388c7  mov     qword ptr [r13+0], 0
0x1800388cf  test    rcx, rcx
0x1800388d2  jz      loc_18003896B
0x1800388d8  call    cs:__imp_CloseHandle
0x1800388de  jmp     loc_18003896B
0x1800388e3  call    cs:__imp_GetLastError
0x1800388e9  mov     ebx, eax
0x1800388eb  test    eax, eax
0x1800388ed  jle     loc_18003882E
0x1800388f3  movzx   ebx, ax
0x1800388f6  or      ebx, edi
0x1800388f8  jmp     loc_18003882E
0x1800388fd  call    cs:__imp_GetLastError
0x180038903  mov     ebx, eax
0x180038905  test    eax, eax
0x180038907  jle     short loc_18003890E
0x180038909  movzx   ebx, ax
0x18003890c  or      ebx, edi
0x18003890e  mov     rsi, [rsp+2C0h+SecurityDescriptor]
0x180038913  jmp     loc_18003882E
0x180038918  mov     rsi, [rsp+2C0h+SecurityDescriptor]
0x18003891d  jmp     loc_18003885B
0x180038922  call    cs:__imp_GetLastError
0x180038928  mov     ebx, eax
0x18003892a  test    eax, eax
0x18003892c  jle     loc_18003885B
0x180038932  movzx   ebx, ax
0x180038935  or      ebx, edi
0x180038937  jmp     loc_18003885B
0x18003893c  call    cs:__imp_GetLastError
0x180038942  mov     ebx, eax
0x180038944  test    eax, eax
0x180038946  jle     loc_18003866B
0x18003894c  movzx   ebx, ax
0x18003894f  or      ebx, 80070000h
0x180038955  jmp     loc_18003866B
0x18003895a  mov     r12, rcx
0x18003895d  jmp     loc_18003885B
0x180038962  mov     rax, [rsp+2C0h+hObject]
0x180038967  mov     [r13+0], rax
0x18003896b  mov     eax, ebx
0x18003896d  mov     rcx, [rbp+1C0h+var_50]
0x180038974  xor     rcx, rsp; StackCookie
0x180038977  call    __security_check_cookie
0x18003897c  add     rsp, 288h
0x180038983  pop     r15
0x180038985  pop     r14
0x180038987  pop     r13
0x180038989  pop     r12
0x18003898b  pop     rdi
0x18003898c  pop     rsi
0x18003898d  pop     rbx
0x18003898e  pop     rbp
0x18003898f  retn
```
