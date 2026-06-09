# xxxConnectService

- ea: `0x1400b604c`
- end: `0x1400b6662`
- name: `xxxConnectService`
- size: `1558`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1401d5de0`

## callees

- `0x1400b604c`
- `0x1400b6668`
- `0x1400b6698`
- `0x1400b66fc`
- `0x1400dd43c`
- `0x1402b3930`

## import_xrefs

- `ntoskrnl!SeExports` at `0x1400b61e2`
- `ntoskrnl!SeExports` at `0x1400b622b`
- `ntoskrnl!ObCloseHandle` at `0x1400b6467`
- `ntoskrnl!ObCloseHandle` at `0x1400b6467`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400b60dc`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400b6146`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400b60dc`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400b6146`
- `ntoskrnl!ZwClose` at `0x1400b6159`
- `ntoskrnl!ZwClose` at `0x1400b64ef`
- `ntoskrnl!ZwClose` at `0x1400b65aa`
- `ntoskrnl!ZwClose` at `0x1400b6159`
- `ntoskrnl!ZwClose` at `0x1400b64ef`
- `ntoskrnl!ZwClose` at `0x1400b65aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b63e9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b63e9`
- `win32kbase!AllocAce` at `0x1400b618f`
- `win32kbase!AllocAce` at `0x1400b61c7`
- `win32kbase!AllocAce` at `0x1400b6210`
- `win32kbase!AllocAce` at `0x1400b6259`
- `win32kbase!AllocAce` at `0x1400b618f`
- `win32kbase!AllocAce` at `0x1400b61c7`
- `win32kbase!AllocAce` at `0x1400b6210`
- `win32kbase!AllocAce` at `0x1400b6259`
- `win32kbase!CreateSecurityDescriptor` at `0x1400b6289`
- `win32kbase!CreateSecurityDescriptor` at `0x1400b6289`
- `win32kbase!OpenEffectiveToken` at `0x1400b609e`
- `win32kbase!OpenEffectiveToken` at `0x1400b609e`
- `win32kbase!Win32AllocPoolZInit` at `0x1400b6106`
- `win32kbase!Win32AllocPoolZInit` at `0x1400b6106`
- `win32kbase!Win32FreePool` at `0x1400b64a7`
- `win32kbase!Win32FreePool` at `0x1400b663d`
- `win32kbase!Win32FreePool` at `0x1400b6651`
- `win32kbase!Win32FreePool` at `0x1400b62a9`
- `win32kbase!Win32FreePool` at `0x1400b62c0`
- `win32kbase!Win32FreePool` at `0x1400b62d7`
- `win32kbase!Win32FreePool` at `0x1400b64a7`
- `win32kbase!Win32FreePool` at `0x1400b663d`
- `win32kbase!Win32FreePool` at `0x1400b6651`
- `WIN32K!W32GetUserSessionState` at `0x1400b655f`
- `WIN32K!W32GetUserSessionState` at `0x1400b65dd`
- `WIN32K!W32GetUserSessionState` at `0x1400b655f`
- `WIN32K!W32GetUserSessionState` at `0x1400b65dd`

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
  __int64 v15; // rdx
  char v16; // di
  bool v17; // r13
  __int64 v18; // rdx
  bool v19; // r13
  __int64 v20; // rax
  int v21; // r8d
  int v22; // edx
  __int64 UserSessionState; // rax
  int v24; // r8d
  int v25; // edx
  HANDLE TokenHandle; // [rsp+60h] [rbp-F8h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-F0h] BYREF
  __int128 v28; // [rsp+70h] [rbp-E8h] BYREF
  __int128 v29; // [rsp+80h] [rbp-D8h]
  __int128 v30; // [rsp+90h] [rbp-C8h]
  _QWORD *v31; // [rsp+A0h] [rbp-B8h]
  void *v32; // [rsp+A8h] [rbp-B0h]
  __int64 v33; // [rsp+B0h] [rbp-A8h]
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-A0h] BYREF
  _BYTE v35[24]; // [rsp+D0h] [rbp-88h] BYREF
  _BYTE v36[24]; // [rsp+E8h] [rbp-70h] BYREF
  _BYTE v37[88]; // [rsp+100h] [rbp-58h] BYREF
  ULONG TokenInformationLength; // [rsp+178h] [rbp+20h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
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
  v31 = v8;
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
            v33 = v14;
            SecurityDescriptor = (void *)CreateSecurityDescriptor(v14, TokenInformationLength, 0);
            v32 = SecurityDescriptor;
            if ( SecurityDescriptor )
            {
              Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(
                v37,
                v8,
                Win32FreePool);
              Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(
                v36,
                v4,
                Win32FreePool);
              Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(
                v35,
                SecurityDescriptor,
                Win32FreePool);
              LODWORD(v28) = 48;
              *((_QWORD *)&v28 + 1) = 0;
              DWORD2(v29) = 128;
              *(_QWORD *)&v29 = a1;
              v30 = (unsigned __int64)SecurityDescriptor;
              Desktop = xxxCreateWindowStation((__int64)&v28, 0, 0x2000000u, 0, 0, 0, 0, 0, 0, 0, -1, &Handle);
              if ( Desktop < 0 )
              {
                *a2 = 0;
              }
              else
              {
                if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                  || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
                  || (v16 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
                {
                  v16 = 0;
                }
                v17 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
                if ( v16 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  UserSessionState = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v15);
                  LOBYTE(v24) = v17;
                  LOBYTE(v25) = v16;
                  WPP_RECORDER_AND_TRACE_SF_(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    v25,
                    v24,
                    *(_QWORD *)(UserSessionState + 69152),
                    4,
                    3,
                    10,
                    (__int64)WPP_de3ba4457d7f3f536bbae76fb0a4650d_Traceguids);
                }
                RtlInitUnicodeString(&DestinationString, L"Default");
                LODWORD(v28) = 48;
                *((_QWORD *)&v28 + 1) = Handle;
                DWORD2(v29) = 192;
                *(_QWORD *)&v29 = &DestinationString;
                v30 = 0;
                Desktop = xxxCreateDesktopEx((__int64)&v28, 0, 0x2000000, 0, a2, 1);
                if ( Desktop >= 0 )
                {
                  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) == 0
                    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
                  {
                    v6 = 0;
                  }
                  v19 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
                  if ( v6 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                  {
                    v20 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v18);
                    LOBYTE(v21) = v19;
                    LOBYTE(v22) = v6;
                    WPP_RECORDER_AND_TRACE_SF_(
                      *((_QWORD *)WPP_GLOBAL_Control + 3),
                      v22,
                      v21,
                      *(_QWORD *)(v20 + 69152),
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
              Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>::~Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>(v35);
              Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>::~Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>(v36);
              Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>::~Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>(v37);
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
0x1400b604c  mov     rax, rsp
0x1400b604f  mov     [rax+18h], r8
0x1400b6053  mov     [rax+10h], rdx
0x1400b6057  mov     [rax+8], rcx
0x1400b605b  push    rbx
0x1400b605c  push    rsi
0x1400b605d  push    rdi
0x1400b605e  push    r12
0x1400b6060  push    r13
0x1400b6062  push    r14
0x1400b6064  push    r15
0x1400b6066  sub     rsp, 120h
0x1400b606d  xor     ebx, ebx
0x1400b606f  mov     [rsp+158h+TokenHandle], rbx
0x1400b6074  mov     [rax+20h], ebx
0x1400b6077  xorps   xmm0, xmm0
0x1400b607a  movups  [rsp+158h+var_E8], xmm0
0x1400b607f  movups  xmmword ptr [rax-0D8h], xmm0
0x1400b6086  movups  xmmword ptr [rax-0C8h], xmm0
0x1400b608d  mov     [rsp+158h+Handle], rbx
0x1400b6092  movups  xmmword ptr [rax-0A0h], xmm0
0x1400b6099  lea     rcx, [rsp+158h+TokenHandle]
0x1400b609e  call    cs:__imp_OpenEffectiveToken
0x1400b60a5  nop     dword ptr [rax+rax+00h]
0x1400b60aa  test    eax, eax
0x1400b60ac  js      loc_1400B64C7
0x1400b60b2  mov     r14d, ebx
0x1400b60b5  mov     r12d, ebx
0x1400b60b8  mov     [rsp+158h+Handle], rbx
0x1400b60bd  lea     rax, [rsp+158h+TokenInformationLength]
0x1400b60c5  mov     [rsp+158h+ReturnLength], rax; ReturnLength
0x1400b60ca  xor     r9d, r9d; TokenInformationLength
0x1400b60cd  xor     r8d, r8d; TokenInformation
0x1400b60d0  lea     r15d, [rbx+1]
0x1400b60d4  mov     edx, r15d; TokenInformationClass
0x1400b60d7  mov     rcx, [rsp+158h+TokenHandle]; TokenHandle
0x1400b60dc  call    cs:__imp_ZwQueryInformationToken
0x1400b60e3  nop     dword ptr [rax+rax+00h]
0x1400b60e8  mov     edi, eax
0x1400b60ea  mov     eax, 80000000h
0x1400b60ef  lea     ecx, [rdi+rax]
0x1400b60f2  test    eax, ecx
0x1400b60f4  jz      loc_1400B64DB
0x1400b60fa  mov     ecx, [rsp+158h+TokenInformationLength]
0x1400b6101  mov     edx, 6F747355h
0x1400b6106  call    cs:__imp_Win32AllocPoolZInit
0x1400b610d  nop     dword ptr [rax+rax+00h]
0x1400b6112  mov     rsi, rax
0x1400b6115  mov     [rsp+158h+var_B8], rax
0x1400b611d  mov     rcx, [rsp+158h+TokenHandle]; Handle
0x1400b6122  test    rax, rax
0x1400b6125  jz      loc_1400B65AA
0x1400b612b  lea     rax, [rsp+158h+TokenInformationLength]
0x1400b6133  mov     [rsp+158h+ReturnLength], rax; ReturnLength
0x1400b6138  mov     r9d, [rsp+158h+TokenInformationLength]; TokenInformationLength
0x1400b6140  mov     r8, rsi; TokenInformation
0x1400b6143  mov     edx, r15d; TokenInformationClass
0x1400b6146  call    cs:__imp_ZwQueryInformationToken
0x1400b614d  nop     dword ptr [rax+rax+00h]
0x1400b6152  mov     edi, eax
0x1400b6154  mov     rcx, [rsp+158h+TokenHandle]; Handle
0x1400b6159  call    cs:__imp_ZwClose
0x1400b6160  nop     dword ptr [rax+rax+00h]
0x1400b6165  test    edi, edi
0x1400b6167  js      loc_1400B649F
0x1400b616d  mov     r13, [rsi]
0x1400b6170  lea     rax, [rsp+158h+TokenInformationLength]
0x1400b6178  mov     [rsp+158h+var_130], rax
0x1400b617d  mov     [rsp+158h+ReturnLength], r13
0x1400b6182  mov     r9d, 0F006Eh
0x1400b6188  xor     r8d, r8d
0x1400b618b  xor     edx, edx
0x1400b618d  xor     ecx, ecx
0x1400b618f  call    cs:__imp_AllocAce
0x1400b6196  nop     dword ptr [rax+rax+00h]
0x1400b619b  mov     r14, rax
0x1400b619e  test    rax, rax
0x1400b61a1  jz      loc_1400B65B6
0x1400b61a7  lea     rax, [rsp+158h+TokenInformationLength]
0x1400b61af  mov     [rsp+158h+var_130], rax
0x1400b61b4  mov     [rsp+158h+ReturnLength], r13
0x1400b61b9  mov     r9d, 0F00CFh
0x1400b61bf  mov     r8b, 0Dh
0x1400b61c2  xor     edx, edx
0x1400b61c4  mov     rcx, r14
0x1400b61c7  call    cs:__imp_AllocAce
0x1400b61ce  nop     dword ptr [rax+rax+00h]
0x1400b61d3  mov     rcx, rax
0x1400b61d6  test    rax, rax
0x1400b61d9  jz      loc_1400B65B6
0x1400b61df  mov     r14, rax
0x1400b61e2  mov     rax, cs:__imp_SeExports
0x1400b61e9  mov     rax, [rax]
0x1400b61ec  lea     rdx, [rsp+158h+TokenInformationLength]
0x1400b61f4  mov     [rsp+158h+var_130], rdx
0x1400b61f9  mov     rax, [rax+110h]
0x1400b6200  mov     [rsp+158h+ReturnLength], rax
0x1400b6205  mov     r9d, 100h
0x1400b620b  xor     r8d, r8d
0x1400b620e  xor     edx, edx
0x1400b6210  call    cs:__imp_AllocAce
0x1400b6217  nop     dword ptr [rax+rax+00h]
0x1400b621c  mov     rcx, rax
0x1400b621f  test    rax, rax
0x1400b6222  jz      loc_1400B65B6
0x1400b6228  mov     r14, rax
0x1400b622b  mov     rax, cs:__imp_SeExports
0x1400b6232  mov     rax, [rax]
0x1400b6235  lea     rdx, [rsp+158h+TokenInformationLength]
0x1400b623d  mov     [rsp+158h+var_130], rdx
0x1400b6242  mov     rax, [rax+110h]
0x1400b6249  mov     [rsp+158h+ReturnLength], rax
0x1400b624e  mov     r9d, 0C1h
0x1400b6254  mov     r8b, 0Dh
0x1400b6257  xor     edx, edx
0x1400b6259  call    cs:__imp_AllocAce
0x1400b6260  nop     dword ptr [rax+rax+00h]
0x1400b6265  mov     r13, rax
0x1400b6268  test    rax, rax
0x1400b626b  jz      loc_1400B65B6
0x1400b6271  mov     r14, rax
0x1400b6274  mov     [rsp+158h+var_A8], rax
0x1400b627c  xor     r8d, r8d
0x1400b627f  mov     edx, [rsp+158h+TokenInformationLength]
0x1400b6286  mov     rcx, rax
0x1400b6289  call    cs:__imp_CreateSecurityDescriptor
0x1400b6290  nop     dword ptr [rax+rax+00h]
0x1400b6295  mov     r12, rax
0x1400b6298  mov     [rsp+158h+var_B0], rax
0x1400b62a0  test    rax, rax
0x1400b62a3  jz      loc_1400B65B6
0x1400b62a9  mov     r8, cs:__imp_Win32FreePool
0x1400b62b0  mov     rdx, rsi
0x1400b62b3  lea     rcx, [rsp+158h+var_58]
0x1400b62bb  call    ??0?$Win32RawLockedItemNoCleanup@U_ACCESS_ALLOWED_ACE@@$0A@@@QEAA@PEAU_ACCESS_ALLOWED_ACE@@P6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(_ACCESS_ALLOWED_ACE *,void (*)(void *))
0x1400b62c0  mov     r8, cs:__imp_Win32FreePool
0x1400b62c7  mov     rdx, r14
0x1400b62ca  lea     rcx, [rsp+158h+var_70]
0x1400b62d2  call    ??0?$Win32RawLockedItemNoCleanup@U_ACCESS_ALLOWED_ACE@@$0A@@@QEAA@PEAU_ACCESS_ALLOWED_ACE@@P6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(_ACCESS_ALLOWED_ACE *,void (*)(void *))
0x1400b62d7  mov     r8, cs:__imp_Win32FreePool
0x1400b62de  mov     rdx, r12
0x1400b62e1  lea     rcx, [rsp+158h+var_88]
0x1400b62e9  call    ??0?$Win32RawLockedItemNoCleanup@U_ACCESS_ALLOWED_ACE@@$0A@@@QEAA@PEAU_ACCESS_ALLOWED_ACE@@P6AXPEAX@Z@Z; Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>::Win32RawLockedItemNoCleanup<_ACCESS_ALLOWED_ACE,0>(_ACCESS_ALLOWED_ACE *,void (*)(void *))
0x1400b62ee  nop
0x1400b62ef  mov     dword ptr [rsp+158h+var_E8], 30h ; '0'
0x1400b62f7  mov     qword ptr [rsp+158h+var_E8+8], rbx
0x1400b62fc  mov     [rsp+158h+var_D0], 80h
0x1400b6307  mov     rax, [rsp+158h+arg_0]
0x1400b630f  mov     [rsp+158h+var_D8], rax
0x1400b6317  mov     qword ptr [rsp+158h+var_C8], r12
0x1400b631f  mov     qword ptr [rsp+158h+var_C8+8], rbx
0x1400b6327  jmp     short loc_1400B6349
0x1400b6329  mov     edi, eax
0x1400b632b  xor     ebx, ebx
0x1400b632d  lea     r15d, [rbx+1]
0x1400b6331  mov     rsi, [rsp+158h+var_B8]
0x1400b6339  mov     r12, [rsp+158h+var_B0]
0x1400b6341  mov     r14, [rsp+158h+var_A8]
0x1400b6349  test    edi, edi
0x1400b634b  js      loc_1400B654F
0x1400b6351  lea     rax, [rsp+158h+Handle]
0x1400b6356  mov     [rsp+158h+var_100], rax
0x1400b635b  mov     [rsp+158h+var_108], 0FFFFFFFFh
0x1400b6363  mov     [rsp+158h+var_110], ebx
0x1400b6367  mov     [rsp+158h+var_118], ebx
0x1400b636b  mov     [rsp+158h+var_120], rbx
0x1400b6370  mov     [rsp+158h+var_128], rbx
0x1400b6375  mov     dword ptr [rsp+158h+var_130], ebx
0x1400b6379  mov     dword ptr [rsp+158h+ReturnLength], ebx
0x1400b637d  xor     r9d, r9d
0x1400b6380  xor     edx, edx
0x1400b6382  mov     r8d, 2000000h
0x1400b6388  lea     rcx, [rsp+158h+var_E8]
0x1400b638d  call    ?xxxCreateWindowStation@@YAJPEAU_OBJECT_ATTRIBUTES@@DKPEAXKKPEAUtagKBDTABLE_MULT_INTERNAL@@PEBGIW4tagWINDOWSTATIONFLAGS@@KPEAPEAUHWINSTA__@@@Z; xxxCreateWindowStation(_OBJECT_ATTRIBUTES *,char,ulong,void *,ulong,ulong,tagKBDTABLE_MULT_INTERNAL *,ushort const *,uint,tagWINDOWSTATIONFLAGS,ulong,HWINSTA__ * *)
0x1400b6392  mov     edi, eax
0x1400b6394  test    eax, eax
0x1400b6396  js      loc_1400B654F
0x1400b639c  lea     rax, WPP_GLOBAL_Control
0x1400b63a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b63aa  cmp     rcx, rax
0x1400b63ad  jnz     loc_1400B65C0
0x1400b63b3  mov     dil, bl
0x1400b63b6  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400b63bd  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400b63c4  setnz   r13b
0x1400b63c8  test    dil, dil
0x1400b63cb  jnz     loc_1400B65DD
0x1400b63d1  test    r13b, r13b
0x1400b63d4  jnz     loc_1400B65DD
0x1400b63da  lea     rdx, aDefault; "Default"
0x1400b63e1  lea     rcx, [rsp+158h+DestinationString]; DestinationString
0x1400b63e9  call    cs:__imp_RtlInitUnicodeString
0x1400b63f0  nop     dword ptr [rax+rax+00h]
0x1400b63f5  mov     dword ptr [rsp+158h+var_E8], 30h ; '0'
0x1400b63fd  mov     rax, [rsp+158h+Handle]
0x1400b6402  mov     qword ptr [rsp+158h+var_E8+8], rax
0x1400b6407  mov     [rsp+158h+var_D0], 0C0h
0x1400b6412  lea     rax, [rsp+158h+DestinationString]
0x1400b641a  mov     [rsp+158h+var_D8], rax
0x1400b6422  xorps   xmm0, xmm0
0x1400b6425  movdqu  [rsp+158h+var_C8], xmm0
0x1400b642e  mov     dword ptr [rsp+158h+var_130], r15d
0x1400b6433  mov     rax, [rsp+158h+arg_8]
0x1400b643b  mov     [rsp+158h+ReturnLength], rax
0x1400b6440  xor     r9d, r9d
0x1400b6443  xor     edx, edx
0x1400b6445  mov     r8d, 2000000h
0x1400b644b  lea     rcx, [rsp+158h+var_E8]
0x1400b6450  call    xxxCreateDesktopEx
0x1400b6455  mov     edi, eax
0x1400b6457  test    eax, eax
0x1400b6459  jns     loc_1400B64FD
0x1400b645f  mov     dl, r15b; PreviousMode
0x1400b6462  mov     rcx, [rsp+158h+Handle]; Handle
0x1400b6467  call    cs:__imp_ObCloseHandle
0x1400b646e  nop     dword ptr [rax+rax+00h]
0x1400b6473  mov     [rsp+158h+Handle], rbx
0x1400b6478  lea     rcx, [rsp+158h+var_88]
0x1400b6480  call    ??1?$Win32RawLockedItemNoCleanup@UtagINTDDEINFO@@$0A@@@QEAA@XZ; Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>::~Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>(void)
0x1400b6485  lea     rcx, [rsp+158h+var_70]
0x1400b648d  call    ??1?$Win32RawLockedItemNoCleanup@UtagINTDDEINFO@@$0A@@@QEAA@XZ; Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>::~Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>(void)
0x1400b6492  lea     rcx, [rsp+158h+var_58]
0x1400b649a  call    ??1?$Win32RawLockedItemNoCleanup@UtagINTDDEINFO@@$0A@@@QEAA@XZ; Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>::~Win32RawLockedItemNoCleanup<tagINTDDEINFO,0>(void)
0x1400b649f  test    rsi, rsi
0x1400b64a2  jz      short loc_1400B64B3
0x1400b64a4  mov     rcx, rsi
0x1400b64a7  call    cs:__imp_Win32FreePool
0x1400b64ae  nop     dword ptr [rax+rax+00h]
0x1400b64b3  test    r14, r14
0x1400b64b6  jnz     loc_1400B663A
0x1400b64bc  test    r12, r12
0x1400b64bf  jnz     loc_1400B664E
0x1400b64c5  mov     eax, edi
0x1400b64c7  add     rsp, 120h
0x1400b64ce  pop     r15
0x1400b64d0  pop     r14
0x1400b64d2  pop     r13
0x1400b64d4  pop     r12
0x1400b64d6  pop     rdi
0x1400b64d7  pop     rsi
0x1400b64d8  pop     rbx
0x1400b64d9  retn
0x1400b64db  cmp     edi, 0C0000023h
0x1400b64e1  jz      loc_1400B60FA
0x1400b64e7  mov     rsi, rbx
0x1400b64ea  mov     rcx, [rsp+158h+TokenHandle]; Handle
0x1400b64ef  call    cs:__imp_ZwClose
0x1400b64f6  nop     dword ptr [rax+rax+00h]
0x1400b64fb  jmp     short loc_1400B649F
0x1400b64fd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b6504  lea     rax, WPP_GLOBAL_Control
0x1400b650b  cmp     rcx, rax
0x1400b650e  jz      short loc_1400B651B
0x1400b6510  mov     eax, [rcx+2Ch]
0x1400b6513  test    al, 4
0x1400b6515  jnz     loc_1400B662B
0x1400b651b  mov     r15b, bl
0x1400b651e  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400b6525  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400b652c  setnz   r13b
0x1400b6530  test    r15b, r15b
0x1400b6533  jnz     short loc_1400B655F
0x1400b6535  test    r13b, r13b
0x1400b6538  jnz     short loc_1400B655F
0x1400b653a  mov     rax, [rsp+158h+Handle]
0x1400b653f  mov     rcx, [rsp+158h+arg_10]
0x1400b6547  mov     [rcx], rax
0x1400b654a  jmp     loc_1400B6478
0x1400b654f  mov     rax, [rsp+158h+arg_8]
0x1400b6557  mov     [rax], rbx
0x1400b655a  jmp     loc_1400B6478
0x1400b655f  call    cs:__imp_W32GetUserSessionState
0x1400b6566  nop     dword ptr [rax+rax+00h]
0x1400b656b  mov     r9, [rax+10E20h]
0x1400b6572  lea     rax, WPP_de3ba4457d7f3f536bbae76fb0a4650d_Traceguids
0x1400b6579  mov     [rsp+158h+var_120], rax
0x1400b657e  mov     word ptr [rsp+158h+var_128], 0Bh
0x1400b6585  mov     dword ptr [rsp+158h+var_130], 3
0x1400b658d  mov     byte ptr [rsp+158h+ReturnLength], 4
0x1400b6592  mov     r8b, r13b
0x1400b6595  mov     dl, r15b
0x1400b6598  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b659f  mov     rcx, [rcx+18h]
0x1400b65a3  call    WPP_RECORDER_AND_TRACE_SF_
0x1400b65a8  jmp     short loc_1400B653A
0x1400b65aa  call    cs:__imp_ZwClose
0x1400b65b1  nop     dword ptr [rax+rax+00h]
0x1400b65b6  mov     edi, 0C0000017h
0x1400b65bb  jmp     loc_1400B649F
0x1400b65c0  mov     eax, [rcx+2Ch]
0x1400b65c3  test    al, 4
0x1400b65c5  jz      loc_1400B63B3
0x1400b65cb  cmp     byte ptr [rcx+29h], 4
0x1400b65cf  mov     dil, r15b
0x1400b65d2  jnb     loc_1400B63B6
0x1400b65d8  jmp     loc_1400B63B3
0x1400b65dd  call    cs:__imp_W32GetUserSessionState
0x1400b65e4  nop     dword ptr [rax+rax+00h]
0x1400b65e9  mov     r9, [rax+10E20h]
0x1400b65f0  lea     rax, WPP_de3ba4457d7f3f536bbae76fb0a4650d_Traceguids
  ... truncated ...
```
