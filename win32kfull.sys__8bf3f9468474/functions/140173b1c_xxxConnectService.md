# xxxConnectService

- ea: `0x140173b1c`
- end: `0x140174132`
- name: `xxxConnectService`
- size: `1558`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1401e48a0`

## callees

- `0x1400b71ac`
- `0x1400c2ab8`
- `0x140173b1c`
- `0x140174138`
- `0x140174168`
- `0x1402b1f80`

## import_xrefs

- `ntoskrnl!SeExports` at `0x140173cb2`
- `ntoskrnl!SeExports` at `0x140173cfb`
- `ntoskrnl!ObCloseHandle` at `0x140173f37`
- `ntoskrnl!ObCloseHandle` at `0x140173f37`
- `ntoskrnl!ZwQueryInformationToken` at `0x140173bac`
- `ntoskrnl!ZwQueryInformationToken` at `0x140173c16`
- `ntoskrnl!ZwQueryInformationToken` at `0x140173bac`
- `ntoskrnl!ZwQueryInformationToken` at `0x140173c16`
- `ntoskrnl!ZwClose` at `0x140173c29`
- `ntoskrnl!ZwClose` at `0x140173fbf`
- `ntoskrnl!ZwClose` at `0x14017407a`
- `ntoskrnl!ZwClose` at `0x140173c29`
- `ntoskrnl!ZwClose` at `0x140173fbf`
- `ntoskrnl!ZwClose` at `0x14017407a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140173eb9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140173eb9`
- `win32kbase!AllocAce` at `0x140173c5f`
- `win32kbase!AllocAce` at `0x140173c97`
- `win32kbase!AllocAce` at `0x140173ce0`
- `win32kbase!AllocAce` at `0x140173d29`
- `win32kbase!AllocAce` at `0x140173c5f`
- `win32kbase!AllocAce` at `0x140173c97`
- `win32kbase!AllocAce` at `0x140173ce0`
- `win32kbase!AllocAce` at `0x140173d29`
- `win32kbase!CreateSecurityDescriptor` at `0x140173d59`
- `win32kbase!CreateSecurityDescriptor` at `0x140173d59`
- `win32kbase!OpenEffectiveToken` at `0x140173b6e`
- `win32kbase!OpenEffectiveToken` at `0x140173b6e`
- `win32kbase!Win32AllocPoolZInit` at `0x140173bd6`
- `win32kbase!Win32AllocPoolZInit` at `0x140173bd6`
- `win32kbase!Win32FreePool` at `0x140173f77`
- `win32kbase!Win32FreePool` at `0x14017410d`
- `win32kbase!Win32FreePool` at `0x140174121`
- `win32kbase!Win32FreePool` at `0x140173d79`
- `win32kbase!Win32FreePool` at `0x140173d90`
- `win32kbase!Win32FreePool` at `0x140173da7`
- `win32kbase!Win32FreePool` at `0x140173f77`
- `win32kbase!Win32FreePool` at `0x14017410d`
- `win32kbase!Win32FreePool` at `0x140174121`
- `WIN32K!W32GetUserSessionState` at `0x14017402f`
- `WIN32K!W32GetUserSessionState` at `0x1401740ad`
- `WIN32K!W32GetUserSessionState` at `0x14017402f`
- `WIN32K!W32GetUserSessionState` at `0x1401740ad`

## pseudocode

```c
__int64 __fastcall xxxConnectService(__int64 a1, HANDLE *a2, HANDLE *a3)
{
  __int64 result; // rax
  void *v4; // r14
  void *SecurityDescriptor; // r12
  char v6; // r15
  int Desktop; // edi
  _QWORD *v8; // rsi
  __int64 v9; // r13
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // r9
  __int64 v16; // r9
  __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  char v21; // di
  bool v22; // r13
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  bool v26; // r13
  __int64 v27; // rax
  int v28; // r8d
  int v29; // edx
  __int64 UserSessionState; // rax
  int v31; // r8d
  int v32; // edx
  HANDLE TokenHandle; // [rsp+60h] [rbp-F8h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-F0h] BYREF
  __int128 v35; // [rsp+70h] [rbp-E8h] BYREF
  __int128 v36; // [rsp+80h] [rbp-D8h]
  __int128 v37; // [rsp+90h] [rbp-C8h]
  _QWORD *v38; // [rsp+A0h] [rbp-B8h]
  void *v39; // [rsp+A8h] [rbp-B0h]
  __int64 v40; // [rsp+B0h] [rbp-A8h]
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-A0h] BYREF
  _BYTE v42[24]; // [rsp+D0h] [rbp-88h] BYREF
  _BYTE v43[24]; // [rsp+E8h] [rbp-70h] BYREF
  _BYTE v44[88]; // [rsp+100h] [rbp-58h] BYREF
  ULONG TokenInformationLength; // [rsp+178h] [rbp+20h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  Handle = 0;
  DestinationString = 0;
  result = OpenEffectiveToken(&TokenHandle);
  if ( (int)result < 0 )
    return result;
  v4 = 0;
  SecurityDescriptor = 0;
  Handle = 0;
  v6 = 1;
  Desktop = ZwQueryInformationToken(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( (int)(Desktop + 0x80000000) >= 0 && Desktop != -1073741789 )
  {
    v8 = 0;
    ZwClose(TokenHandle);
    goto LABEL_18;
  }
  v8 = (_QWORD *)Win32AllocPoolZInit(TokenInformationLength, 1869902677);
  v38 = v8;
  if ( !v8 )
  {
    ZwClose(TokenHandle);
LABEL_37:
    Desktop = -1073741801;
    goto LABEL_18;
  }
  Desktop = ZwQueryInformationToken(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength);
  ZwClose(TokenHandle);
  if ( Desktop >= 0 )
  {
    v9 = *v8;
    v4 = (void *)AllocAce(0, 0, 0, 983150, *v8, &TokenInformationLength);
    if ( v4 )
    {
      LOBYTE(v10) = 13;
      v11 = AllocAce(v4, 0, v10, 983247, v9, &TokenInformationLength);
      if ( v11 )
      {
        v4 = (void *)v11;
        v12 = AllocAce(v11, 0, 0, 256, SeExports->SeAliasAdminsSid, &TokenInformationLength);
        if ( v12 )
        {
          v4 = (void *)v12;
          LOBYTE(v13) = 13;
          v14 = AllocAce(v12, 0, v13, 193, SeExports->SeAliasAdminsSid, &TokenInformationLength);
          if ( v14 )
          {
            v4 = (void *)v14;
            v40 = v14;
            SecurityDescriptor = (void *)CreateSecurityDescriptor(v14, TokenInformationLength, 0);
            v39 = SecurityDescriptor;
            if ( SecurityDescriptor )
            {
              Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(
                v44,
                v8,
                Win32FreePool,
                v15);
              Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(
                v43,
                v4,
                Win32FreePool,
                v16);
              Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(
                v42,
                SecurityDescriptor,
                Win32FreePool,
                v17);
              LODWORD(v35) = 48;
              *((_QWORD *)&v35 + 1) = 0;
              DWORD2(v36) = 128;
              *(_QWORD *)&v36 = a1;
              v37 = (unsigned __int64)SecurityDescriptor;
              Desktop = xxxCreateWindowStation((__int64)&v35, 0, 0x2000000, 0, 0, 0, 0, 0, 0, 0, -1, &Handle);
              if ( Desktop < 0 )
              {
                *a2 = 0;
              }
              else
              {
                if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
                  || (v21 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
                {
                  v21 = 0;
                }
                v22 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
                if ( v21 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  UserSessionState = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v18, v19, v20);
                  LOBYTE(v31) = v22;
                  LOBYTE(v32) = v21;
                  WPP_RECORDER_AND_TRACE_SF_(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    v32,
                    v31,
                    *(_QWORD *)(UserSessionState + 69152),
                    4,
                    3,
                    10,
                    (__int64)WPP_de3ba4457d7f3f536bbae76fb0a4650d_Traceguids);
                }
                RtlInitUnicodeString(&DestinationString, L"Default");
                LODWORD(v35) = 48;
                *((_QWORD *)&v35 + 1) = Handle;
                DWORD2(v36) = 192;
                *(_QWORD *)&v36 = &DestinationString;
                v37 = 0;
                Desktop = xxxCreateDesktopEx((__int64)&v35, 0, 0x2000000, 0, a2, 1);
                if ( Desktop >= 0 )
                {
                  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
                  {
                    v6 = 0;
                  }
                  v26 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
                  if ( v6 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                  {
                    v27 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v23, v24, v25);
                    LOBYTE(v28) = v26;
                    LOBYTE(v29) = v6;
                    WPP_RECORDER_AND_TRACE_SF_(
                      *((_QWORD *)WPP_GLOBAL_Control + 3),
                      v29,
                      v28,
                      *(_QWORD *)(v27 + 69152),
                      4,
                      3,
                      11,
                      (__int64)WPP_de3ba4457d7f3f536bbae76fb0a4650d_Traceguids);
                  }
                  *a3 = Handle;
                }
                else
                {
                  ObCloseHandle(Handle, 1);
                  Handle = 0;
                }
              }
              Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>::~Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>(v42);
              Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>::~Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>(v43);
              Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>::~Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>(v44);
              goto LABEL_18;
            }
          }
        }
      }
    }
    goto LABEL_37;
  }
LABEL_18:
  if ( v8 )
    Win32FreePool(v8);
  if ( v4 )
    Win32FreePool(v4);
  if ( SecurityDescriptor )
    Win32FreePool(SecurityDescriptor);
  return (unsigned int)Desktop;
}

```

## disassembly

```asm
0x140173b1c  mov     rax, rsp
0x140173b1f  mov     [rax+18h], r8
0x140173b23  mov     [rax+10h], rdx
0x140173b27  mov     [rax+8], rcx
0x140173b2b  push    rbx
0x140173b2c  push    rsi
0x140173b2d  push    rdi
0x140173b2e  push    r12
0x140173b30  push    r13
0x140173b32  push    r14
0x140173b34  push    r15
0x140173b36  sub     rsp, 120h
0x140173b3d  xor     ebx, ebx
0x140173b3f  mov     [rsp+158h+TokenHandle], rbx
0x140173b44  mov     [rax+20h], ebx
0x140173b47  xorps   xmm0, xmm0
0x140173b4a  movups  [rsp+158h+var_E8], xmm0
0x140173b4f  movups  xmmword ptr [rax-0D8h], xmm0
0x140173b56  movups  xmmword ptr [rax-0C8h], xmm0
0x140173b5d  mov     [rsp+158h+Handle], rbx
0x140173b62  movups  xmmword ptr [rax-0A0h], xmm0
0x140173b69  lea     rcx, [rsp+158h+TokenHandle]
0x140173b6e  call    cs:__imp_OpenEffectiveToken
0x140173b75  nop     dword ptr [rax+rax+00h]
0x140173b7a  test    eax, eax
0x140173b7c  js      loc_140173F97
0x140173b82  mov     r14d, ebx
0x140173b85  mov     r12d, ebx
0x140173b88  mov     [rsp+158h+Handle], rbx
0x140173b8d  lea     rax, [rsp+158h+TokenInformationLength]
0x140173b95  mov     [rsp+158h+ReturnLength], rax; ReturnLength
0x140173b9a  xor     r9d, r9d; TokenInformationLength
0x140173b9d  xor     r8d, r8d; TokenInformation
0x140173ba0  lea     r15d, [rbx+1]
0x140173ba4  mov     edx, r15d; TokenInformationClass
0x140173ba7  mov     rcx, [rsp+158h+TokenHandle]; TokenHandle
0x140173bac  call    cs:__imp_ZwQueryInformationToken
0x140173bb3  nop     dword ptr [rax+rax+00h]
0x140173bb8  mov     edi, eax
0x140173bba  mov     eax, 80000000h
0x140173bbf  lea     ecx, [rdi+rax]
0x140173bc2  test    eax, ecx
0x140173bc4  jz      loc_140173FAB
0x140173bca  mov     ecx, [rsp+158h+TokenInformationLength]
0x140173bd1  mov     edx, 6F747355h
0x140173bd6  call    cs:__imp_Win32AllocPoolZInit
0x140173bdd  nop     dword ptr [rax+rax+00h]
0x140173be2  mov     rsi, rax
0x140173be5  mov     [rsp+158h+var_B8], rax
0x140173bed  mov     rcx, [rsp+158h+TokenHandle]; Handle
0x140173bf2  test    rax, rax
0x140173bf5  jz      loc_14017407A
0x140173bfb  lea     rax, [rsp+158h+TokenInformationLength]
0x140173c03  mov     [rsp+158h+ReturnLength], rax; ReturnLength
0x140173c08  mov     r9d, [rsp+158h+TokenInformationLength]; TokenInformationLength
0x140173c10  mov     r8, rsi; TokenInformation
0x140173c13  mov     edx, r15d; TokenInformationClass
0x140173c16  call    cs:__imp_ZwQueryInformationToken
0x140173c1d  nop     dword ptr [rax+rax+00h]
0x140173c22  mov     edi, eax
0x140173c24  mov     rcx, [rsp+158h+TokenHandle]; Handle
0x140173c29  call    cs:__imp_ZwClose
0x140173c30  nop     dword ptr [rax+rax+00h]
0x140173c35  test    edi, edi
0x140173c37  js      loc_140173F6F
0x140173c3d  mov     r13, [rsi]
0x140173c40  lea     rax, [rsp+158h+TokenInformationLength]
0x140173c48  mov     [rsp+158h+var_130], rax
0x140173c4d  mov     [rsp+158h+ReturnLength], r13
0x140173c52  mov     r9d, 0F006Eh
0x140173c58  xor     r8d, r8d
0x140173c5b  xor     edx, edx
0x140173c5d  xor     ecx, ecx
0x140173c5f  call    cs:__imp_AllocAce
0x140173c66  nop     dword ptr [rax+rax+00h]
0x140173c6b  mov     r14, rax
0x140173c6e  test    rax, rax
0x140173c71  jz      loc_140174086
0x140173c77  lea     rax, [rsp+158h+TokenInformationLength]
0x140173c7f  mov     [rsp+158h+var_130], rax
0x140173c84  mov     [rsp+158h+ReturnLength], r13
0x140173c89  mov     r9d, 0F00CFh
0x140173c8f  mov     r8b, 0Dh
0x140173c92  xor     edx, edx
0x140173c94  mov     rcx, r14
0x140173c97  call    cs:__imp_AllocAce
0x140173c9e  nop     dword ptr [rax+rax+00h]
0x140173ca3  mov     rcx, rax
0x140173ca6  test    rax, rax
0x140173ca9  jz      loc_140174086
0x140173caf  mov     r14, rax
0x140173cb2  mov     rax, cs:__imp_SeExports
0x140173cb9  mov     rax, [rax]
0x140173cbc  lea     rdx, [rsp+158h+TokenInformationLength]
0x140173cc4  mov     [rsp+158h+var_130], rdx
0x140173cc9  mov     rax, [rax+110h]
0x140173cd0  mov     [rsp+158h+ReturnLength], rax
0x140173cd5  mov     r9d, 100h
0x140173cdb  xor     r8d, r8d
0x140173cde  xor     edx, edx
0x140173ce0  call    cs:__imp_AllocAce
0x140173ce7  nop     dword ptr [rax+rax+00h]
0x140173cec  mov     rcx, rax
0x140173cef  test    rax, rax
0x140173cf2  jz      loc_140174086
0x140173cf8  mov     r14, rax
0x140173cfb  mov     rax, cs:__imp_SeExports
0x140173d02  mov     rax, [rax]
0x140173d05  lea     rdx, [rsp+158h+TokenInformationLength]
0x140173d0d  mov     [rsp+158h+var_130], rdx
0x140173d12  mov     rax, [rax+110h]
0x140173d19  mov     [rsp+158h+ReturnLength], rax
0x140173d1e  mov     r9d, 0C1h
0x140173d24  mov     r8b, 0Dh
0x140173d27  xor     edx, edx
0x140173d29  call    cs:__imp_AllocAce
0x140173d30  nop     dword ptr [rax+rax+00h]
0x140173d35  mov     r13, rax
0x140173d38  test    rax, rax
0x140173d3b  jz      loc_140174086
0x140173d41  mov     r14, rax
0x140173d44  mov     [rsp+158h+var_A8], rax
0x140173d4c  xor     r8d, r8d
0x140173d4f  mov     edx, [rsp+158h+TokenInformationLength]
0x140173d56  mov     rcx, rax
0x140173d59  call    cs:__imp_CreateSecurityDescriptor
0x140173d60  nop     dword ptr [rax+rax+00h]
0x140173d65  mov     r12, rax
0x140173d68  mov     [rsp+158h+var_B0], rax
0x140173d70  test    rax, rax
0x140173d73  jz      loc_140174086
0x140173d79  mov     r8, cs:__imp_Win32FreePool
0x140173d80  mov     rdx, rsi
0x140173d83  lea     rcx, [rsp+158h+var_58]
0x140173d8b  call    ??0?$Win32RawLockedItemNoCleanup@U_ACCESS_ALLOWED_ACE@@$0A@@@QEAA@PEAU_ACCESS_ALLOWED_ACE@@P6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(_ACCESS_ALLOWED_ACE *,void (*)(void *))
0x140173d90  mov     r8, cs:__imp_Win32FreePool
0x140173d97  mov     rdx, r14
0x140173d9a  lea     rcx, [rsp+158h+var_70]
0x140173da2  call    ??0?$Win32RawLockedItemNoCleanup@U_ACCESS_ALLOWED_ACE@@$0A@@@QEAA@PEAU_ACCESS_ALLOWED_ACE@@P6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(_ACCESS_ALLOWED_ACE *,void (*)(void *))
0x140173da7  mov     r8, cs:__imp_Win32FreePool
0x140173dae  mov     rdx, r12
0x140173db1  lea     rcx, [rsp+158h+var_88]
0x140173db9  call    ??0?$Win32RawLockedItemNoCleanup@U_ACCESS_ALLOWED_ACE@@$0A@@@QEAA@PEAU_ACCESS_ALLOWED_ACE@@P6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(_ACCESS_ALLOWED_ACE *,void (*)(void *))
0x140173dbe  nop
0x140173dbf  mov     dword ptr [rsp+158h+var_E8], 30h ; '0'
0x140173dc7  mov     qword ptr [rsp+158h+var_E8+8], rbx
0x140173dcc  mov     [rsp+158h+var_D0], 80h
0x140173dd7  mov     rax, [rsp+158h+arg_0]
0x140173ddf  mov     [rsp+158h+var_D8], rax
0x140173de7  mov     qword ptr [rsp+158h+var_C8], r12
0x140173def  mov     qword ptr [rsp+158h+var_C8+8], rbx
0x140173df7  jmp     short loc_140173E19
0x140173df9  mov     edi, eax
0x140173dfb  xor     ebx, ebx
0x140173dfd  lea     r15d, [rbx+1]
0x140173e01  mov     rsi, [rsp+158h+var_B8]
0x140173e09  mov     r12, [rsp+158h+var_B0]
0x140173e11  mov     r14, [rsp+158h+var_A8]
0x140173e19  test    edi, edi
0x140173e1b  js      loc_14017401F
0x140173e21  lea     rax, [rsp+158h+Handle]
0x140173e26  mov     [rsp+158h+var_100], rax
0x140173e2b  mov     [rsp+158h+var_108], 0FFFFFFFFh
0x140173e33  mov     [rsp+158h+var_110], ebx
0x140173e37  mov     [rsp+158h+var_118], ebx
0x140173e3b  mov     [rsp+158h+var_120], rbx
0x140173e40  mov     [rsp+158h+var_128], rbx
0x140173e45  mov     dword ptr [rsp+158h+var_130], ebx
0x140173e49  mov     dword ptr [rsp+158h+ReturnLength], ebx
0x140173e4d  xor     r9d, r9d
0x140173e50  xor     edx, edx
0x140173e52  mov     r8d, 2000000h
0x140173e58  lea     rcx, [rsp+158h+var_E8]
0x140173e5d  call    ?xxxCreateWindowStation@@YAJPEAU_OBJECT_ATTRIBUTES@@DKPEAXKKPEAUtagKBDTABLE_MULT_INTERNAL@@PEBGIW4tagWINDOWSTATIONFLAGS@@KPEAPEAUHWINSTA__@@@Z; xxxCreateWindowStation(_OBJECT_ATTRIBUTES *,char,ulong,void *,ulong,ulong,tagKBDTABLE_MULT_INTERNAL *,ushort const *,uint,tagWINDOWSTATIONFLAGS,ulong,HWINSTA__ * *)
0x140173e62  mov     edi, eax
0x140173e64  test    eax, eax
0x140173e66  js      loc_14017401F
0x140173e6c  lea     rax, WPP_GLOBAL_Control
0x140173e73  mov     rcx, cs:WPP_GLOBAL_Control
0x140173e7a  cmp     rcx, rax
0x140173e7d  jnz     loc_140174090
0x140173e83  mov     dil, bl
0x140173e86  lea     rcx, WPP_RECORDER_INITIALIZED
0x140173e8d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140173e94  setnz   r13b
0x140173e98  test    dil, dil
0x140173e9b  jnz     loc_1401740AD
0x140173ea1  test    r13b, r13b
0x140173ea4  jnz     loc_1401740AD
0x140173eaa  lea     rdx, aDefault; "Default"
0x140173eb1  lea     rcx, [rsp+158h+DestinationString]; DestinationString
0x140173eb9  call    cs:__imp_RtlInitUnicodeString
0x140173ec0  nop     dword ptr [rax+rax+00h]
0x140173ec5  mov     dword ptr [rsp+158h+var_E8], 30h ; '0'
0x140173ecd  mov     rax, [rsp+158h+Handle]
0x140173ed2  mov     qword ptr [rsp+158h+var_E8+8], rax
0x140173ed7  mov     [rsp+158h+var_D0], 0C0h
0x140173ee2  lea     rax, [rsp+158h+DestinationString]
0x140173eea  mov     [rsp+158h+var_D8], rax
0x140173ef2  xorps   xmm0, xmm0
0x140173ef5  movdqu  [rsp+158h+var_C8], xmm0
0x140173efe  mov     dword ptr [rsp+158h+var_130], r15d
0x140173f03  mov     rax, [rsp+158h+arg_8]
0x140173f0b  mov     [rsp+158h+ReturnLength], rax
0x140173f10  xor     r9d, r9d
0x140173f13  xor     edx, edx
0x140173f15  mov     r8d, 2000000h
0x140173f1b  lea     rcx, [rsp+158h+var_E8]
0x140173f20  call    xxxCreateDesktopEx
0x140173f25  mov     edi, eax
0x140173f27  test    eax, eax
0x140173f29  jns     loc_140173FCD
0x140173f2f  mov     dl, r15b; PreviousMode
0x140173f32  mov     rcx, [rsp+158h+Handle]; Handle
0x140173f37  call    cs:__imp_ObCloseHandle
0x140173f3e  nop     dword ptr [rax+rax+00h]
0x140173f43  mov     [rsp+158h+Handle], rbx
0x140173f48  lea     rcx, [rsp+158h+var_88]
0x140173f50  call    ??1?$Win32RawLockedItemNoCleanup@UtagINTDDEINFO@@$0A@@@QEAA@XZ; Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>::~Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>(void)
0x140173f55  lea     rcx, [rsp+158h+var_70]
0x140173f5d  call    ??1?$Win32RawLockedItemNoCleanup@UtagINTDDEINFO@@$0A@@@QEAA@XZ; Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>::~Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>(void)
0x140173f62  lea     rcx, [rsp+158h+var_58]
0x140173f6a  call    ??1?$Win32RawLockedItemNoCleanup@UtagINTDDEINFO@@$0A@@@QEAA@XZ; Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>::~Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>(void)
0x140173f6f  test    rsi, rsi
0x140173f72  jz      short loc_140173F83
0x140173f74  mov     rcx, rsi
0x140173f77  call    cs:__imp_Win32FreePool
0x140173f7e  nop     dword ptr [rax+rax+00h]
0x140173f83  test    r14, r14
0x140173f86  jnz     loc_14017410A
0x140173f8c  test    r12, r12
0x140173f8f  jnz     loc_14017411E
0x140173f95  mov     eax, edi
0x140173f97  add     rsp, 120h
0x140173f9e  pop     r15
0x140173fa0  pop     r14
0x140173fa2  pop     r13
0x140173fa4  pop     r12
0x140173fa6  pop     rdi
0x140173fa7  pop     rsi
0x140173fa8  pop     rbx
0x140173fa9  retn
0x140173fab  cmp     edi, 0C0000023h
0x140173fb1  jz      loc_140173BCA
0x140173fb7  mov     rsi, rbx
0x140173fba  mov     rcx, [rsp+158h+TokenHandle]; Handle
0x140173fbf  call    cs:__imp_ZwClose
0x140173fc6  nop     dword ptr [rax+rax+00h]
0x140173fcb  jmp     short loc_140173F6F
0x140173fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x140173fd4  lea     rax, WPP_GLOBAL_Control
0x140173fdb  cmp     rcx, rax
0x140173fde  jz      short loc_140173FEB
0x140173fe0  mov     eax, [rcx+2Ch]
0x140173fe3  test    al, 4
0x140173fe5  jnz     loc_1401740FB
0x140173feb  mov     r15b, bl
0x140173fee  lea     rcx, WPP_RECORDER_INITIALIZED
0x140173ff5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140173ffc  setnz   r13b
0x140174000  test    r15b, r15b
0x140174003  jnz     short loc_14017402F
0x140174005  test    r13b, r13b
0x140174008  jnz     short loc_14017402F
0x14017400a  mov     rax, [rsp+158h+Handle]
0x14017400f  mov     rcx, [rsp+158h+arg_10]
0x140174017  mov     [rcx], rax
0x14017401a  jmp     loc_140173F48
0x14017401f  mov     rax, [rsp+158h+arg_8]
0x140174027  mov     [rax], rbx
0x14017402a  jmp     loc_140173F48
0x14017402f  call    cs:__imp_W32GetUserSessionState
0x140174036  nop     dword ptr [rax+rax+00h]
0x14017403b  mov     r9, [rax+10E20h]
0x140174042  lea     rax, WPP_de3ba4457d7f3f536bbae76fb0a4650d_Traceguids
0x140174049  mov     [rsp+158h+var_120], rax
0x14017404e  mov     word ptr [rsp+158h+var_128], 0Bh
0x140174055  mov     dword ptr [rsp+158h+var_130], 3
0x14017405d  mov     byte ptr [rsp+158h+ReturnLength], 4
0x140174062  mov     r8b, r13b
0x140174065  mov     dl, r15b
0x140174068  mov     rcx, cs:WPP_GLOBAL_Control
0x14017406f  mov     rcx, [rcx+18h]
0x140174073  call    WPP_RECORDER_AND_TRACE_SF_
0x140174078  jmp     short loc_14017400A
0x14017407a  call    cs:__imp_ZwClose
0x140174081  nop     dword ptr [rax+rax+00h]
0x140174086  mov     edi, 0C0000017h
0x14017408b  jmp     loc_140173F6F
0x140174090  mov     eax, [rcx+2Ch]
0x140174093  test    al, 4
0x140174095  jz      loc_140173E83
0x14017409b  cmp     byte ptr [rcx+29h], 4
0x14017409f  mov     dil, r15b
0x1401740a2  jnb     loc_140173E86
0x1401740a8  jmp     loc_140173E83
0x1401740ad  call    cs:__imp_W32GetUserSessionState
0x1401740b4  nop     dword ptr [rax+rax+00h]
0x1401740b9  mov     r9, [rax+10E20h]
0x1401740c0  lea     rax, WPP_de3ba4457d7f3f536bbae76fb0a4650d_Traceguids
  ... truncated ...
```
