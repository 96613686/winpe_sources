# DavImpersonateAndGetSessionId

- ea: `0x1800056f4`
- end: `0x18000583e`
- name: `DavImpersonateAndGetSessionId`
- size: `330`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000656c`
- `0x180006d20`

## callees

- `0x1800056f4`
- `0x18000591c`
- `0x180006618`
- `0x18000b7dc`
- `0x18000b8e8`
- `0x18000bfe0`
- `0x180028a00`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180005784`
- `ntdll!NtQueryInformationToken` at `0x180005784`

## pseudocode

```c
__int64 __fastcall DavImpersonateAndGetSessionId(_DWORD *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // esi
  unsigned int v4; // eax
  __int64 v5; // r8
  unsigned int v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // r8
  unsigned int v11; // esi
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  TokenInformation = 0;
  ReturnLength = 0;
  v2 = DavImpersonateClient();
  v3 = v2;
  if ( v2 )
  {
    v4 = DavMapErrorToNtStatus(v2);
    v6 = v4;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_LL(*((_QWORD *)WPP_GLOBAL_Control + 2), 207, v5, v3, v4);
  }
  else
  {
    v7 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenSessionId, &TokenInformation, 4u, &ReturnLength);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 208, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v7);
    }
    else
    {
      *a1 = TokenInformation;
    }
    v8 = DavRevertToSelf();
    v6 = v8;
    if ( v8 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v8);
  }
  v9 = NetpNtStatusToApiStatus(v6);
  v11 = v9;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_LL(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, v10, v6, v9);
  return v11;
}

```

## disassembly

```asm
0x1800056f4  mov     rax, rsp
0x1800056f7  mov     [rax+8], rbx
0x1800056fb  mov     [rax+20h], rsi
0x1800056ff  push    rdi
0x180005700  sub     rsp, 30h
0x180005704  mov     rbx, rcx
0x180005707  mov     dword ptr [rax+10h], 0
0x18000570e  mov     dword ptr [rax+18h], 0
0x180005715  call    DavImpersonateClient
0x18000571a  mov     esi, eax
0x18000571c  test    eax, eax
0x18000571e  jz      short loc_180005764
0x180005720  mov     ecx, eax
0x180005722  call    DavMapErrorToNtStatus
0x180005727  mov     ebx, eax
0x180005729  mov     rcx, cs:WPP_GLOBAL_Control
0x180005730  lea     rdi, WPP_GLOBAL_Control
0x180005737  cmp     rcx, rdi
0x18000573a  jz      loc_1800057FC
0x180005740  test    byte ptr [rcx+1Ch], 1
0x180005744  jz      loc_1800057FC
0x18000574a  mov     rcx, [rcx+10h]
0x18000574e  mov     edx, 0CFh
0x180005753  mov     r9d, esi
0x180005756  mov     dword ptr [rsp+38h+ReturnLength], eax
0x18000575a  call    WPP_SF_LL
0x18000575f  jmp     loc_1800057FC
0x180005764  mov     r9d, 4; TokenInformationLength
0x18000576a  lea     rax, [rsp+38h+arg_10]
0x18000576f  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x180005774  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180005779  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x180005780  lea     edx, [r9+8]; TokenInformationClass
0x180005784  call    cs:__imp_NtQueryInformationToken
0x18000578a  lea     rdi, WPP_GLOBAL_Control
0x180005791  test    eax, eax
0x180005793  jz      short loc_1800057C1
0x180005795  mov     rcx, cs:WPP_GLOBAL_Control
0x18000579c  cmp     rcx, rdi
0x18000579f  jz      short loc_1800057C7
0x1800057a1  test    byte ptr [rcx+1Ch], 1
0x1800057a5  jz      short loc_1800057C7
0x1800057a7  mov     rcx, [rcx+10h]
0x1800057ab  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x1800057b2  mov     edx, 0D0h
0x1800057b7  mov     r9d, eax
0x1800057ba  call    WPP_SF_d
0x1800057bf  jmp     short loc_1800057C7
0x1800057c1  mov     eax, [rsp+38h+TokenInformation]
0x1800057c5  mov     [rbx], eax
0x1800057c7  call    DavRevertToSelf
0x1800057cc  mov     ebx, eax
0x1800057ce  test    eax, eax
0x1800057d0  jz      short loc_1800057FC
0x1800057d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057d9  cmp     rcx, rdi
0x1800057dc  jz      short loc_1800057FC
0x1800057de  test    byte ptr [rcx+1Ch], 1
0x1800057e2  jz      short loc_1800057FC
0x1800057e4  mov     rcx, [rcx+10h]
0x1800057e8  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x1800057ef  mov     edx, 0D1h
0x1800057f4  mov     r9d, eax
0x1800057f7  call    WPP_SF_d
0x1800057fc  mov     ecx, ebx
0x1800057fe  call    NetpNtStatusToApiStatus
0x180005803  mov     esi, eax
0x180005805  mov     rcx, cs:WPP_GLOBAL_Control
0x18000580c  cmp     rcx, rdi
0x18000580f  jz      short loc_18000582C
0x180005811  test    byte ptr [rcx+1Ch], 1
0x180005815  jz      short loc_18000582C
0x180005817  mov     rcx, [rcx+10h]
0x18000581b  mov     edx, 0D2h
0x180005820  mov     r9d, ebx
0x180005823  mov     dword ptr [rsp+38h+ReturnLength], eax
0x180005827  call    WPP_SF_LL
0x18000582c  mov     rbx, [rsp+38h+arg_0]
0x180005831  mov     eax, esi
0x180005833  mov     rsi, [rsp+38h+arg_18]
0x180005838  add     rsp, 30h
0x18000583c  pop     rdi
0x18000583d  retn
```
