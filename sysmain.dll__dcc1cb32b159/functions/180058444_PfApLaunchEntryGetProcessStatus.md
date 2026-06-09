# PfApLaunchEntryGetProcessStatus

- ea: `0x180058444`
- end: `0x1800586dc`
- name: `PfApLaunchEntryGetProcessStatus`
- size: `664`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180065e0c`
- `0x18006d810`

## callees

- `0x180021e0c`
- `0x180058444`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x180058510`
- `ntdll!NtQueryInformationProcess` at `0x180058510`
- `ntdll!RtlQueryPackageIdentity` at `0x1800585a2`
- `ntdll!RtlQueryPackageIdentity` at `0x1800585a2`
- `ntdll!RtlNtStatusToDosError` at `0x18005851c`
- `ntdll!RtlNtStatusToDosError` at `0x1800585b1`
- `ntdll!RtlNtStatusToDosError` at `0x18005851c`
- `ntdll!RtlNtStatusToDosError` at `0x1800585b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800584be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800584be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005853d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005854b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005869b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800586a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005853d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005854b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005869b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800586a9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800584d5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800584d5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800584b0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800584b0`
- `api-ms-win-appmodel-runtime-l1-1-1!FormatApplicationUserModelId` at `0x180058634`
- `api-ms-win-appmodel-runtime-l1-1-1!FormatApplicationUserModelId` at `0x180058634`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18005860e`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18005860e`

## pseudocode

```c
__int64 __fastcall PfApLaunchEntryGetProcessStatus(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  DWORD v6; // r8d
  DWORD v7; // edi
  void *v8; // r14
  void *v9; // rsi
  unsigned int v10; // r12d
  HANDLE v11; // rax
  void *v12; // rbx
  DWORD LastError; // eax
  int InformationProcess; // eax
  NTSTATUS v15; // eax
  ULONG v16; // eax
  __int16 v17; // cx
  wchar_t *v18; // rax
  int v19; // edx
  int v20; // ecx
  _BYTE v22[8]; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  ULONG applicationUserModelIdLength[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h]
  _QWORD ProcessInformation[7]; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+88h] [rbp-78h]
  WCHAR packageRelativeApplicationId[72]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t pszDest[136]; // [rsp+1B0h] [rbp+B0h] BYREF
  WCHAR packageFullName[128]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v25 = a1;
  memset_0(ProcessInformation, 0, 0x40u);
  v6 = *(_DWORD *)(a1 + 48);
  v7 = 0;
  applicationUserModelIdLength[0] = 0;
  TokenHandle = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = OpenProcess(0x3008u, 0, v6);
  v12 = v11;
  if ( !v11 || !OpenProcessToken(v11, 8u, &TokenHandle) )
  {
    LastError = GetLastError();
LABEL_3:
    v7 = LastError;
    goto LABEL_8;
  }
  memset_0(ProcessInformation, 0, 0x40u);
  ProcessInformation[0] = 64;
  InformationProcess = NtQueryInformationProcess(
                         v12,
                         ProcessBasicInformation,
                         ProcessInformation,
                         0x40u,
                         applicationUserModelIdLength);
  if ( InformationProcess < 0 )
  {
    LastError = RtlNtStatusToDosError(InformationProcess);
    goto LABEL_3;
  }
  v8 = TokenHandle;
  v9 = v12;
  TokenHandle = 0;
  v12 = 0;
LABEL_8:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v12 )
    CloseHandle(v12);
  if ( !v7 && (v27 & 4) == 0 )
  {
    v22[0] = 0;
    TokenHandle = (void *)254;
    *(_QWORD *)applicationUserModelIdLength = 130;
    v15 = ((__int64 (__fastcall *)(void *, WCHAR *, void **, WCHAR *, ULONG *, _BYTE *))RtlQueryPackageIdentity)(
            v8,
            packageFullName,
            &TokenHandle,
            packageRelativeApplicationId,
            applicationUserModelIdLength,
            v22);
    if ( v15 >= 0 )
    {
      v17 = ((unsigned __int16)TokenHandle >> 1) - 1;
    }
    else
    {
      v16 = RtlNtStatusToDosError(v15);
      v17 = 127;
      if ( v16 )
        goto LABEL_31;
    }
    applicationUserModelIdLength[0] = 0;
    if ( v17 )
    {
      LODWORD(TokenHandle) = 65;
      if ( PackageFamilyNameFromFullName(packageFullName, (UINT32 *)&TokenHandle, packageFamilyName) )
        goto LABEL_31;
      applicationUserModelIdLength[0] = 130;
      if ( FormatApplicationUserModelId(
             packageFamilyName,
             packageRelativeApplicationId,
             applicationUserModelIdLength,
             pszDest) )
      {
        goto LABEL_31;
      }
    }
    else
    {
      StringCchPrintfW(pszDest, 0x82u, L"DefaultBrowser_NOPUBLISHERID!%ws", packageRelativeApplicationId);
    }
    v18 = pszDest;
    do
    {
      v19 = *(wchar_t *)((char *)v18 + *(_QWORD *)(v25 + 16) - (_QWORD)pszDest);
      v20 = *v18 - v19;
      if ( v20 )
        break;
      ++v18;
    }
    while ( v19 );
    if ( !v20 )
    {
      v10 = 1;
      *a2 = (v27 & 0x10) != 0 ? 1 : ((unsigned __int8)~(_BYTE)v27 >> 4) & 2;
      if ( a3 )
      {
        *a3 = v9;
        v9 = 0;
      }
    }
  }
LABEL_31:
  if ( v8 )
    CloseHandle(v8);
  if ( v9 )
    CloseHandle(v9);
  return v10;
}

```

## disassembly

```asm
0x180058444  mov     [rsp-8+arg_18], rbx
0x180058449  push    rbp
0x18005844a  push    rsi
0x18005844b  push    rdi
0x18005844c  push    r12
0x18005844e  push    r13
0x180058450  push    r14
0x180058452  push    r15
0x180058454  lea     rbp, [rsp-2D0h]
0x18005845c  sub     rsp, 3D0h
0x180058463  mov     rax, cs:__security_cookie
0x18005846a  xor     rax, rsp
0x18005846d  mov     [rbp+300h+var_40], rax
0x180058474  mov     r13, rdx
0x180058477  mov     [rsp+400h+var_3B8], rcx
0x18005847c  xor     edx, edx; Val
0x18005847e  mov     r15, r8
0x180058481  mov     rbx, rcx
0x180058484  lea     rcx, [rsp+400h+ProcessInformation]; void *
0x180058489  lea     r8d, [rdx+40h]; Size
0x18005848d  call    memset_0
0x180058492  mov     r8d, [rbx+30h]; dwProcessId
0x180058496  xor     edi, edi
0x180058498  xor     edx, edx; bInheritHandle
0x18005849a  mov     [rsp+400h+applicationUserModelIdLength], edi
0x18005849e  mov     ecx, 3008h; dwDesiredAccess
0x1800584a3  mov     [rsp+400h+TokenHandle], rdi
0x1800584a8  mov     r14d, edi
0x1800584ab  mov     esi, edi
0x1800584ad  mov     r12d, edi
0x1800584b0  call    cs:__imp_OpenProcess
0x1800584b6  mov     rbx, rax
0x1800584b9  test    rax, rax
0x1800584bc  jnz     short loc_1800584C8
0x1800584be  call    cs:__imp_GetLastError
0x1800584c4  mov     edi, eax
0x1800584c6  jmp     short loc_180058533
0x1800584c8  lea     r8, [rsp+400h+TokenHandle]; TokenHandle
0x1800584cd  mov     edx, 8; DesiredAccess
0x1800584d2  mov     rcx, rbx; ProcessHandle
0x1800584d5  call    cs:__imp_OpenProcessToken
0x1800584db  test    eax, eax
0x1800584dd  jz      short loc_1800584BE
0x1800584df  xor     edx, edx; Val
0x1800584e1  lea     rcx, [rsp+400h+ProcessInformation]; void *
0x1800584e6  lea     r8d, [rdx+40h]; Size
0x1800584ea  call    memset_0
0x1800584ef  mov     ecx, 40h ; '@'
0x1800584f4  lea     rax, [rsp+400h+applicationUserModelIdLength]
0x1800584f9  mov     [rsp+400h+ProcessInformation], rcx
0x1800584fe  lea     r8, [rsp+400h+ProcessInformation]; ProcessInformation
0x180058503  mov     r9d, ecx; ProcessInformationLength
0x180058506  mov     [rsp+400h+ReturnLength], rax; ReturnLength
0x18005850b  mov     rcx, rbx; ProcessHandle
0x18005850e  xor     edx, edx; ProcessInformationClass
0x180058510  call    cs:__imp_NtQueryInformationProcess
0x180058516  test    eax, eax
0x180058518  jns     short loc_180058524
0x18005851a  mov     ecx, eax; Status
0x18005851c  call    cs:__imp_RtlNtStatusToDosError
0x180058522  jmp     short loc_1800584C4
0x180058524  mov     r14, [rsp+400h+TokenHandle]
0x180058529  mov     rsi, rbx
0x18005852c  mov     [rsp+400h+TokenHandle], rdi
0x180058531  xor     ebx, ebx
0x180058533  mov     rcx, [rsp+400h+TokenHandle]; hObject
0x180058538  test    rcx, rcx
0x18005853b  jz      short loc_180058543
0x18005853d  call    cs:__imp_CloseHandle
0x180058543  test    rbx, rbx
0x180058546  jz      short loc_180058551
0x180058548  mov     rcx, rbx; hObject
0x18005854b  call    cs:__imp_CloseHandle
0x180058551  xor     ebx, ebx
0x180058553  test    edi, edi
0x180058555  jnz     loc_180058693
0x18005855b  test    byte ptr [rbp+300h+var_378], 4
0x18005855f  jnz     loc_180058693
0x180058565  lea     rax, [rsp+400h+var_3D0]
0x18005856a  mov     [rsp+400h+var_3D0], bl
0x18005856e  mov     [rsp+400h+var_3D8], rax
0x180058573  lea     r9, [rbp+300h+packageRelativeApplicationId]
0x180058577  lea     rax, [rsp+400h+applicationUserModelIdLength]
0x18005857c  mov     [rsp+400h+TokenHandle], 0FEh
0x180058585  lea     r8, [rsp+400h+TokenHandle]
0x18005858a  mov     [rsp+400h+ReturnLength], rax
0x18005858f  lea     rdx, [rbp+300h+packageFullName]
0x180058596  mov     qword ptr [rsp+400h+applicationUserModelIdLength], 82h
0x18005859f  mov     rcx, r14
0x1800585a2  call    cs:__imp_RtlQueryPackageIdentity
0x1800585a8  lea     edi, [rbx+1]
0x1800585ab  test    eax, eax
0x1800585ad  jns     short loc_1800585C4
0x1800585af  mov     ecx, eax; Status
0x1800585b1  call    cs:__imp_RtlNtStatusToDosError
0x1800585b7  lea     ecx, [rbx+7Fh]
0x1800585ba  test    eax, eax
0x1800585bc  jnz     loc_180058693
0x1800585c2  jmp     short loc_1800585CF
0x1800585c4  movzx   ecx, word ptr [rsp+400h+TokenHandle]
0x1800585c9  shr     cx, 1
0x1800585cc  sub     cx, di
0x1800585cf  mov     [rsp+400h+applicationUserModelIdLength], ebx
0x1800585d3  test    cx, cx
0x1800585d6  jnz     short loc_1800585F6
0x1800585d8  lea     r9, [rbp+300h+packageRelativeApplicationId]
0x1800585dc  mov     edx, 82h; cchDest
0x1800585e1  lea     r8, aDefaultbrowser; "DefaultBrowser_NOPUBLISHERID!%ws"
0x1800585e8  lea     rcx, [rbp+300h+pszDest]; pszDest
0x1800585ef  call    StringCchPrintfW
0x1800585f4  jmp     short loc_18005863E
0x1800585f6  lea     r8, [rbp+300h+packageFamilyName]; packageFamilyName
0x1800585fa  mov     dword ptr [rsp+400h+TokenHandle], 41h ; 'A'
0x180058602  lea     rdx, [rsp+400h+TokenHandle]; packageFamilyNameLength
0x180058607  lea     rcx, [rbp+300h+packageFullName]; packageFullName
0x18005860e  call    cs:__imp_PackageFamilyNameFromFullName
0x180058614  test    eax, eax
0x180058616  jnz     short loc_180058693
0x180058618  lea     r9, [rbp+300h+pszDest]; applicationUserModelId
0x18005861f  mov     [rsp+400h+applicationUserModelIdLength], 82h
0x180058627  lea     r8, [rsp+400h+applicationUserModelIdLength]; applicationUserModelIdLength
0x18005862c  lea     rdx, [rbp+300h+packageRelativeApplicationId]; packageRelativeApplicationId
0x180058630  lea     rcx, [rbp+300h+packageFamilyName]; packageFamilyName
0x180058634  call    cs:__imp_FormatApplicationUserModelId
0x18005863a  test    eax, eax
0x18005863c  jnz     short loc_180058693
0x18005863e  mov     r8, [rsp+400h+var_3B8]
0x180058643  lea     rax, [rbp+300h+pszDest]
0x18005864a  mov     r8, [r8+10h]
0x18005864e  sub     r8, rax
0x180058651  movzx   ecx, word ptr [rax]
0x180058654  movzx   edx, word ptr [rax+r8]
0x180058659  sub     ecx, edx
0x18005865b  jnz     short loc_180058665
0x18005865d  add     rax, 2
0x180058661  test    edx, edx
0x180058663  jnz     short loc_180058651
0x180058665  test    ecx, ecx
0x180058667  jnz     short loc_180058693
0x180058669  mov     eax, [rbp+300h+var_378]
0x18005866c  mov     r12d, edi
0x18005866f  test    al, 10h
0x180058671  jz      short loc_180058679
0x180058673  mov     [r13+0], edi
0x180058677  jmp     short loc_180058688
0x180058679  not     al
0x18005867b  movzx   eax, al
0x18005867e  shr     eax, 4
0x180058681  and     eax, 2
0x180058684  mov     [r13+0], eax
0x180058688  test    r15, r15
0x18005868b  jz      short loc_180058693
0x18005868d  mov     [r15], rsi
0x180058690  mov     rsi, rbx
0x180058693  test    r14, r14
0x180058696  jz      short loc_1800586A1
0x180058698  mov     rcx, r14; hObject
0x18005869b  call    cs:__imp_CloseHandle
0x1800586a1  test    rsi, rsi
0x1800586a4  jz      short loc_1800586AF
0x1800586a6  mov     rcx, rsi; hObject
0x1800586a9  call    cs:__imp_CloseHandle
0x1800586af  mov     eax, r12d
0x1800586b2  mov     rcx, [rbp+300h+var_40]
0x1800586b9  xor     rcx, rsp; StackCookie
0x1800586bc  call    __security_check_cookie
0x1800586c1  mov     rbx, [rsp+400h+arg_18]
0x1800586c9  add     rsp, 3D0h
0x1800586d0  pop     r15
0x1800586d2  pop     r14
0x1800586d4  pop     r13
0x1800586d6  pop     r12
0x1800586d8  pop     rdi
0x1800586d9  pop     rsi
0x1800586da  pop     rbp
0x1800586db  retn
```
