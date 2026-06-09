# ScExtpLaunchService

- ea: `0x140018294`
- end: `0x1400186f7`
- name: `ScExtpLaunchService`
- size: `1123`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x140017a50`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x140018294`
- `0x140018700`
- `0x1400188fc`
- `0x14001895c`
- `0x140019014`
- `0x140040038`
- `0x1400575b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001839c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001843f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400186b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001839c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001843f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400186b5`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140018405`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001840e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140018405`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14001840e`
- `api-ms-win-service-management-l1-1-0!ControlServiceExW` at `0x14001838e`
- `api-ms-win-service-management-l1-1-0!ControlServiceExW` at `0x14001838e`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x14001853b`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x14001853b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400182eb`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400182eb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140018307`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140018307`

## pseudocode

```c
__int64 __fastcall ScExtpLaunchService(LPCWSTR lpServiceName, unsigned int a2)
{
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // r13
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // r15
  DWORD v8; // eax
  DWORD v9; // ebx
  DWORD v10; // r8d
  char v11; // bl
  PRPC_ASYNC_STATE v12; // rcx
  DWORD v14; // eax
  __int64 v15; // rdx
  DWORD v16; // edx
  DWORD LastError; // eax
  PRPC_ASYNC_STATE v18; // rcx
  int v19; // edx
  int v20; // eax
  int v21; // [rsp+30h] [rbp-59h]
  int v22; // [rsp+30h] [rbp-59h]
  _WORD v23[2]; // [rsp+40h] [rbp-49h] BYREF
  int v24; // [rsp+44h] [rbp-45h] BYREF
  LPCWSTR v25; // [rsp+48h] [rbp-41h] BYREF
  wchar_t *v26; // [rsp+50h] [rbp-39h]
  __int128 pControlParams; // [rsp+58h] [rbp-31h] BYREF
  __int128 v28; // [rsp+68h] [rbp-21h]
  __int128 v29; // [rsp+78h] [rbp-11h]
  __int64 v30; // [rsp+88h] [rbp-1h]
  wchar_t Buffer[16]; // [rsp+90h] [rbp+7h] BYREF

  v25 = L"TriggerStarted";
  v26 = 0;
  v23[0] = 0;
  v24 = 0;
  v4 = OpenSCManagerW(0, 0, 1u);
  v5 = v4;
  if ( v4 )
  {
    v6 = OpenServiceW(v4, lpServiceName, 0x1Cu);
    v7 = v6;
    if ( !v6 )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          98,
          (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
          (_DWORD)lpServiceName,
          LastError);
      goto LABEL_18;
    }
    v8 = ScExtpWaitForService(v6, (__int64)&v24, (__int64)v23 + 1, v21, (__int64)v23);
    v9 = v8;
    if ( v8 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_17;
      v19 = 99;
      goto LABEL_44;
    }
    if ( (v24 == 4 || v24 == 7) && !HIBYTE(v23[0]) )
    {
      v30 = 0;
      v24 = 0;
      pControlParams = 0;
      v28 = 0;
      v29 = 0;
      if ( ControlServiceExW(v7, 0x20u, 1u, &pControlParams) )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control )
        {
LABEL_16:
          v9 = 0;
LABEL_17:
          CloseServiceHandle(v7);
LABEL_18:
          CloseServiceHandle(v5);
          return v9;
        }
        if ( (BYTE4(WPP_GLOBAL_Control->UserInfo) & 8) != 0 )
        {
          WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 121, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids, lpServiceName);
          v12 = WPP_GLOBAL_Control;
        }
        goto LABEL_14;
      }
      v10 = GetLastError();
      if ( v10 == 1062 || (v11 = 0, DWORD1(v28) == 1) )
        v11 = 1;
      if ( v10 != 1115 && DWORD1(v28) != 3 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_13;
        }
        WPP_SF_SLd(
          WPP_GLOBAL_Control->StubInfo,
          120,
          (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
          (_DWORD)lpServiceName,
          v10,
          v11);
        goto LABEL_29;
      }
      v20 = ScExtpWaitForService(v7, (__int64)&v24, 0, v22, (__int64)v23);
      if ( v20 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
LABEL_13:
          if ( !v11 )
          {
LABEL_14:
            if ( v12 == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(v12->UserInfo) & 8) == 0 )
              goto LABEL_16;
            v15 = 100;
            goto LABEL_27;
          }
          goto LABEL_30;
        }
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          122,
          (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
          (_DWORD)lpServiceName,
          v20);
LABEL_29:
        v12 = WPP_GLOBAL_Control;
        goto LABEL_13;
      }
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 8) != 0 )
        WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 123, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids, lpServiceName);
    }
LABEL_30:
    v16 = 1;
    if ( a2 )
    {
      swprintf_s(Buffer, 0x10u, L"%d", a2);
      v16 = 2;
      v26 = Buffer;
    }
    if ( StartServiceW(v7, v16, &v25) )
      goto LABEL_33;
    v8 = GetLastError();
    v9 = v8;
    if ( v8 == 1056 )
    {
      ScExtpTriggerRunningService(v7);
LABEL_33:
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 8) == 0 )
        goto LABEL_16;
      v15 = 102;
LABEL_27:
      WPP_SF_S(v12->StubInfo, v15, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids, lpServiceName);
      goto LABEL_16;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      goto LABEL_17;
    v19 = 101;
LABEL_44:
    WPP_SF_Sd(
      v18->StubInfo,
      v19,
      (unsigned int)WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids,
      (_DWORD)lpServiceName,
      v8);
    goto LABEL_17;
  }
  v14 = GetLastError();
  v9 = v14;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 97, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids, v14);
  return v9;
}

```

## disassembly

```asm
0x140018294  mov     [rsp-8+arg_10], rbx
0x140018299  mov     [rsp-8+arg_18], rdi
0x14001829e  push    rbp
0x14001829f  push    r12
0x1400182a1  push    r13
0x1400182a3  push    r14
0x1400182a5  push    r15
0x1400182a7  lea     rbp, [rsp-37h]
0x1400182ac  sub     rsp, 0C0h
0x1400182b3  mov     rax, cs:__security_cookie
0x1400182ba  xor     rax, rsp
0x1400182bd  mov     [rbp+57h+var_30], rax
0x1400182c1  xor     edi, edi
0x1400182c3  lea     rax, aTriggerstarted; "TriggerStarted"
0x1400182ca  mov     r12d, edx
0x1400182cd  mov     byte ptr [rbp+57h+var_A0+1], dil
0x1400182d1  mov     r14, rcx
0x1400182d4  mov     [rbp+57h+var_98], rax
0x1400182d8  xor     edx, edx; lpDatabaseName
0x1400182da  mov     [rbp+57h+var_90], rdi
0x1400182de  lea     r8d, [rdi+1]; dwDesiredAccess
0x1400182e2  mov     byte ptr [rbp+57h+var_A0], dil
0x1400182e6  xor     ecx, ecx; lpMachineName
0x1400182e8  mov     dword ptr [rbp+57h+var_A0+4], edi
0x1400182eb  call    cs:__imp_OpenSCManagerW
0x1400182f1  mov     r13, rax
0x1400182f4  test    rax, rax
0x1400182f7  jz      loc_14001843F
0x1400182fd  lea     r8d, [rdi+1Ch]; dwDesiredAccess
0x140018301  mov     rdx, r14; lpServiceName
0x140018304  mov     rcx, rax; hSCManager
0x140018307  call    cs:__imp_OpenServiceW
0x14001830d  mov     r15, rax
0x140018310  test    rax, rax
0x140018313  jz      loc_140018579
0x140018319  lea     rax, [rbp+57h+var_A0]
0x14001831d  mov     rdx, r14
0x140018320  mov     [rsp+0E0h+var_A8], rax; __int64
0x140018325  lea     r8d, [rdi+49h]
0x140018329  lea     rax, [rbp+57h+var_A0+1]
0x14001832d  mov     rcx, r15; hService
0x140018330  mov     [rsp+0E0h+var_B8], rax; __int64
0x140018335  lea     rax, [rbp+57h+var_A0+4]
0x140018339  mov     [rsp+0E0h+var_C0], rax; __int64
0x14001833e  call    ScExtpWaitForService
0x140018343  mov     ebx, eax
0x140018345  test    eax, eax
0x140018347  jnz     loc_1400185C3
0x14001834d  cmp     dword ptr [rbp+57h+var_A0+4], 4
0x140018351  lea     rdi, WPP_GLOBAL_Control
0x140018358  jnz     loc_14001856D
0x14001835e  cmp     byte ptr [rbp+57h+var_A0+1], 0
0x140018362  jnz     loc_140018505
0x140018368  xor     eax, eax
0x14001836a  lea     r9, [rbp+57h+pControlParams]; pControlParams
0x14001836e  xorps   xmm0, xmm0
0x140018371  mov     [rbp+57h+var_58], rax
0x140018375  mov     rcx, r15; hService
0x140018378  mov     dword ptr [rbp+57h+var_A0+4], eax
0x14001837b  movups  [rbp+57h+pControlParams], xmm0
0x14001837f  lea     edx, [rax+20h]; dwControl
0x140018382  lea     r8d, [rax+1]; dwInfoLevel
0x140018386  movups  [rbp+57h+var_78], xmm0
0x14001838a  movups  [rbp+57h+var_68], xmm0
0x14001838e  call    cs:__imp_ControlServiceExW
0x140018394  test    eax, eax
0x140018396  jnz     loc_14001847A
0x14001839c  call    cs:__imp_GetLastError
0x1400183a2  mov     r8d, eax
0x1400183a5  cmp     eax, 426h
0x1400183aa  jz      loc_14001860C
0x1400183b0  xor     bl, bl
0x1400183b2  cmp     dword ptr [rbp+57h+var_78+4], 1
0x1400183b6  jz      loc_14001860C
0x1400183bc  cmp     r8d, 45Bh
0x1400183c3  jz      loc_140018613
0x1400183c9  cmp     dword ptr [rbp+57h+var_78+4], 3
0x1400183cd  jz      loc_140018613
0x1400183d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400183da  cmp     rcx, rdi
0x1400183dd  jz      short loc_1400183E9
0x1400183df  test    byte ptr [rcx+1Ch], 1
0x1400183e3  jnz     loc_1400184D5
0x1400183e9  test    bl, bl
0x1400183eb  jnz     loc_140018505
0x1400183f1  cmp     rcx, rdi
0x1400183f4  jz      short loc_140018400
0x1400183f6  test    byte ptr [rcx+1Ch], 8
0x1400183fa  jnz     loc_1400184B8
0x140018400  xor     ebx, ebx
0x140018402  mov     rcx, r15; hSCObject
0x140018405  call    cs:__imp_CloseServiceHandle
0x14001840b  mov     rcx, r13; hSCObject
0x14001840e  call    cs:__imp_CloseServiceHandle
0x140018414  mov     eax, ebx
0x140018416  mov     rcx, [rbp+57h+var_30]
0x14001841a  xor     rcx, rsp; StackCookie
0x14001841d  call    __security_check_cookie
0x140018422  lea     r11, [rsp+0E0h+var_20]
0x14001842a  mov     rbx, [r11+40h]
0x14001842e  mov     rdi, [r11+48h]
0x140018432  mov     rsp, r11
0x140018435  pop     r15
0x140018437  pop     r14
0x140018439  pop     r13
0x14001843b  pop     r12
0x14001843d  pop     rbp
0x14001843e  retn
0x14001843f  call    cs:__imp_GetLastError
0x140018445  mov     ebx, eax
0x140018447  mov     rcx, cs:WPP_GLOBAL_Control
0x14001844e  lea     rdi, WPP_GLOBAL_Control
0x140018455  cmp     rcx, rdi
0x140018458  jz      short loc_140018414
0x14001845a  test    byte ptr [rcx+1Ch], 1
0x14001845e  jz      short loc_140018414
0x140018460  mov     rcx, [rcx+10h]
0x140018464  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x14001846b  mov     edx, 61h ; 'a'
0x140018470  mov     r9d, eax
0x140018473  call    WPP_SF_d
0x140018478  jmp     short loc_140018414
0x14001847a  mov     rcx, cs:WPP_GLOBAL_Control
0x140018481  cmp     rcx, rdi
0x140018484  jz      loc_140018400
0x14001848a  test    byte ptr [rcx+1Ch], 8
0x14001848e  jz      loc_1400183F1
0x140018494  mov     rcx, [rcx+10h]
0x140018498  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x14001849f  mov     edx, 79h ; 'y'
0x1400184a4  mov     r9, r14
0x1400184a7  call    WPP_SF_S
0x1400184ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400184b3  jmp     loc_1400183F1
0x1400184b8  mov     edx, 64h ; 'd'
0x1400184bd  mov     rcx, [rcx+10h]
0x1400184c1  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x1400184c8  mov     r9, r14
0x1400184cb  call    WPP_SF_S
0x1400184d0  jmp     loc_140018400
0x1400184d5  mov     rcx, [rcx+10h]
0x1400184d9  mov     edx, 78h ; 'x'
0x1400184de  movzx   eax, bl
0x1400184e1  mov     r9, r14
0x1400184e4  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1400184e8  mov     dword ptr [rsp+0E0h+var_C0], r8d
0x1400184ed  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x1400184f4  call    WPP_SF_SLd
0x1400184f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140018500  jmp     loc_1400183E9
0x140018505  mov     edx, 1
0x14001850a  test    r12d, r12d
0x14001850d  jz      short loc_140018534
0x14001850f  mov     r9d, r12d
0x140018512  lea     r8, aD; "%d"
0x140018519  mov     edx, 10h; BufferCount
0x14001851e  lea     rcx, [rbp+57h+Buffer]; Buffer
0x140018522  call    swprintf_s
0x140018527  lea     rax, [rbp+57h+Buffer]
0x14001852b  mov     edx, 2; dwNumServiceArgs
0x140018530  mov     [rbp+57h+var_90], rax
0x140018534  lea     r8, [rbp+57h+var_98]; lpServiceArgVectors
0x140018538  mov     rcx, r15; hService
0x14001853b  call    cs:__imp_StartServiceW
0x140018541  test    eax, eax
0x140018543  jz      loc_1400186B5
0x140018549  mov     rcx, cs:WPP_GLOBAL_Control
0x140018550  cmp     rcx, rdi
0x140018553  jz      loc_140018400
0x140018559  test    byte ptr [rcx+1Ch], 8
0x14001855d  jz      loc_140018400
0x140018563  mov     edx, 66h ; 'f'
0x140018568  jmp     loc_1400184BD
0x14001856d  cmp     dword ptr [rbp+57h+var_A0+4], 7
0x140018571  jz      loc_14001835E
0x140018577  jmp     short loc_140018505
0x140018579  call    cs:__imp_GetLastError
0x14001857f  mov     ebx, eax
0x140018581  mov     rcx, cs:WPP_GLOBAL_Control
0x140018588  lea     rdi, WPP_GLOBAL_Control
0x14001858f  cmp     rcx, rdi
0x140018592  jz      loc_14001840B
0x140018598  test    byte ptr [rcx+1Ch], 1
0x14001859c  jz      loc_14001840B
0x1400185a2  mov     rcx, [rcx+10h]
0x1400185a6  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x1400185ad  mov     edx, 62h ; 'b'
0x1400185b2  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1400185b6  mov     r9, r14
0x1400185b9  call    WPP_SF_Sd
0x1400185be  jmp     loc_14001840B
0x1400185c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400185ca  lea     rdi, WPP_GLOBAL_Control
0x1400185d1  cmp     rcx, rdi
0x1400185d4  jz      loc_140018402
0x1400185da  test    byte ptr [rcx+1Ch], 1
0x1400185de  jz      loc_140018402
0x1400185e4  mov     edx, 63h ; 'c'
0x1400185e9  jmp     short loc_1400185F0
0x1400185eb  mov     edx, 65h ; 'e'
0x1400185f0  mov     rcx, [rcx+10h]
0x1400185f4  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x1400185fb  mov     r9, r14
0x1400185fe  mov     dword ptr [rsp+0E0h+var_C0], eax
0x140018602  call    WPP_SF_Sd
0x140018607  jmp     loc_140018402
0x14001860c  mov     bl, 1
0x14001860e  jmp     loc_1400183BC
0x140018613  lea     rax, [rbp+57h+var_A0]
0x140018617  mov     r8d, 1
0x14001861d  mov     [rsp+0E0h+var_A8], rax; __int64
0x140018622  mov     rdx, r14
0x140018625  lea     rax, [rbp+57h+var_A0+4]
0x140018629  mov     [rsp+0E0h+var_B8], 0; __int64
0x140018632  mov     rcx, r15; hService
0x140018635  mov     [rsp+0E0h+var_C0], rax; __int64
0x14001863a  call    ScExtpWaitForService
0x14001863f  test    eax, eax
0x140018641  jz      short loc_14001867E
0x140018643  mov     rcx, cs:WPP_GLOBAL_Control
0x14001864a  cmp     rcx, rdi
0x14001864d  jz      loc_1400183E9
0x140018653  test    byte ptr [rcx+1Ch], 1
0x140018657  jz      loc_1400183E9
0x14001865d  mov     rcx, [rcx+10h]
0x140018661  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x140018668  mov     edx, 7Ah ; 'z'
0x14001866d  mov     dword ptr [rsp+0E0h+var_C0], eax
0x140018671  mov     r9, r14
0x140018674  call    WPP_SF_Sd
0x140018679  jmp     loc_1400184F9
0x14001867e  mov     rcx, cs:WPP_GLOBAL_Control
0x140018685  cmp     rcx, rdi
0x140018688  jz      loc_140018505
0x14001868e  test    byte ptr [rcx+1Ch], 8
0x140018692  jz      loc_140018505
0x140018698  mov     rcx, [rcx+10h]
0x14001869c  lea     r8, WPP_33ca3c9d568834eb2422a5f850c17021_Traceguids
0x1400186a3  mov     edx, 7Bh ; '{'
0x1400186a8  mov     r9, r14
0x1400186ab  call    WPP_SF_S
0x1400186b0  jmp     loc_140018505
0x1400186b5  call    cs:__imp_GetLastError
0x1400186bb  mov     ebx, eax
0x1400186bd  cmp     eax, 420h
0x1400186c2  jnz     short loc_1400186D8
0x1400186c4  lea     r8, [rbp+57h+var_A0]
0x1400186c8  mov     rdx, r14
0x1400186cb  mov     rcx, r15; hService
0x1400186ce  call    ScExtpTriggerRunningService
0x1400186d3  jmp     loc_140018549
0x1400186d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400186df  cmp     rcx, rdi
0x1400186e2  jz      loc_140018402
0x1400186e8  test    byte ptr [rcx+1Ch], 1
0x1400186ec  jz      loc_140018402
0x1400186f2  jmp     loc_1400185EB
```
