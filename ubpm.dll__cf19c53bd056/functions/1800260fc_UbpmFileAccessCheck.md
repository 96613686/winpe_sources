# UbpmFileAccessCheck

- ea: `0x1800260fc`
- end: `0x180026310`
- name: `UbpmFileAccessCheck`
- size: `532`
- prototype: `__int64 __fastcall(HANDLE ClientToken, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e660`
- `0x180022054`

## callees

- `0x18000f9a0`
- `0x1800260fc`
- `0x180032e38`
- `0x18003d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002618b`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180026236`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18002618b`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180026236`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800262d1`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800262d1`
- `ntdll!RtlFreeHeap` at `0x180026305`
- `ntdll!RtlFreeHeap` at `0x180026305`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026240`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026240`

## pseudocode

```c
__int64 __fastcall UbpmFileAccessCheck(HANDLE ClientToken, __int64 a2)
{
  DWORD LastError; // ebx
  void *v6; // rdi
  DWORD v7; // r8d
  DWORD nLengthNeeded; // [rsp+40h] [rbp-40h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp-3Ch] BYREF
  DWORD GrantedAccess; // [rsp+48h] [rbp-38h] BYREF
  DWORD PrivilegeSetLength; // [rsp+4Ch] [rbp-34h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+50h] [rbp-30h] BYREF
  _PRIVILEGE_SET PrivilegeSet; // [rsp+60h] [rbp-20h] BYREF

  LastError = 0;
  PrivilegeSetLength = 20;
  nLengthNeeded = 0;
  AccessStatus = 0;
  GrantedAccess = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GenericMapping = 0;
  if ( a2 )
  {
    if ( GetFileSecurityW(*(LPCWSTR *)a2, 7u, 0, 0, &nLengthNeeded) || (LastError = GetLastError(), LastError == 122) )
    {
      v6 = UbpmAlloc(nLengthNeeded);
      if ( v6 )
      {
        if ( GetFileSecurityW(*(LPCWSTR *)a2, 7u, v6, nLengthNeeded, &nLengthNeeded) )
        {
          v7 = *(_DWORD *)(a2 + 8);
          GenericMapping.GenericRead = 1179785;
          GenericMapping.GenericWrite = 1179926;
          GenericMapping.GenericExecute = 1179808;
          GenericMapping.GenericAll = 2032127;
          if ( !AccessCheck(
                  v6,
                  ClientToken,
                  v7,
                  &GenericMapping,
                  &PrivilegeSet,
                  &PrivilegeSetLength,
                  &GrantedAccess,
                  &AccessStatus)
            || !AccessStatus
            || (LastError = 0, (GrantedAccess & *(_DWORD *)(a2 + 8)) != *(_DWORD *)(a2 + 8)) )
          {
            LastError = 5;
          }
        }
        else
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              WPP_134408c016563692a0776b6ad2359b4f_Traceguids,
              LastError);
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, 0);
        return 0;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800260fc  mov     [rsp-18h+arg_10], rbx
0x180026101  mov     [rsp-18h+arg_18], rsi
0x180026106  push    rbp
0x180026107  push    rdi
0x180026108  push    r14
0x18002610a  mov     rbp, rsp
0x18002610d  sub     rsp, 80h
0x180026114  mov     rax, cs:__security_cookie
0x18002611b  xor     rax, rsp
0x18002611e  mov     [rbp+var_8], rax
0x180026122  xor     ebx, ebx
0x180026124  mov     [rbp+var_34], 14h
0x18002612b  xor     eax, eax
0x18002612d  mov     [rbp+nLengthNeeded], ebx
0x180026130  mov     [rbp+var_3C], ebx
0x180026133  xorps   xmm0, xmm0
0x180026136  mov     [rbp+var_38], ebx
0x180026139  mov     rsi, rdx
0x18002613c  mov     [rbp+PrivilegeSet.Privilege.Attributes], eax
0x18002613f  mov     r14, rcx
0x180026142  movups  xmmword ptr [rbp+PrivilegeSet.PrivilegeCount], xmm0
0x180026146  movups  xmmword ptr [rbp+GenericMapping.GenericRead], xmm0
0x18002614a  test    rdx, rdx
0x18002614d  jnz     short loc_180026175
0x18002614f  mov     eax, ebx
0x180026151  mov     rcx, [rbp+var_8]
0x180026155  xor     rcx, rsp; StackCookie
0x180026158  call    __security_check_cookie
0x18002615d  lea     r11, [rsp+80h+var_s0]
0x180026165  mov     rbx, [r11+30h]
0x180026169  mov     rsi, [r11+38h]
0x18002616d  mov     rsp, r11
0x180026170  pop     r14
0x180026172  pop     rdi
0x180026173  pop     rbp
0x180026174  retn
0x180026175  mov     rcx, [rsi]; lpFileName
0x180026178  lea     rax, [rbp+nLengthNeeded]
0x18002617c  xor     r9d, r9d; nLength
0x18002617f  mov     [rsp+80h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180026184  xor     r8d, r8d; pSecurityDescriptor
0x180026187  lea     edx, [r9+7]; RequestedInformation
0x18002618b  call    cs:__imp_GetFileSecurityW
0x180026191  test    eax, eax
0x180026193  jnz     short loc_1800261D8
0x180026195  call    cs:__imp_GetLastError
0x18002619b  mov     ebx, eax
0x18002619d  cmp     eax, 7Ah ; 'z'
0x1800261a0  jz      short loc_1800261D8
0x1800261a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261a9  lea     rax, WPP_GLOBAL_Control
0x1800261b0  cmp     rcx, rax
0x1800261b3  jz      short loc_18002614F
0x1800261b5  test    byte ptr [rcx+1Ch], 1
0x1800261b9  jz      short loc_18002614F
0x1800261bb  mov     rcx, [rcx+10h]
0x1800261bf  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x1800261c6  mov     edx, 13h
0x1800261cb  mov     r9d, ebx
0x1800261ce  call    WPP_SF_d
0x1800261d3  jmp     loc_18002614F
0x1800261d8  mov     ecx, [rbp+nLengthNeeded]; Size
0x1800261db  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x1800261e0  mov     rdi, rax
0x1800261e3  test    rax, rax
0x1800261e6  jnz     short loc_18002621E
0x1800261e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261ef  lea     rax, WPP_GLOBAL_Control
0x1800261f6  cmp     rcx, rax
0x1800261f9  jz      short loc_180026217
0x1800261fb  test    byte ptr [rcx+1Ch], 1
0x1800261ff  jz      short loc_180026217
0x180026201  mov     rcx, [rcx+10h]
0x180026205  lea     edx, [rdi+14h]
0x180026208  xor     r9d, r9d
0x18002620b  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180026212  call    WPP_SF_d
0x180026217  xor     ebx, ebx
0x180026219  jmp     loc_18002614F
0x18002621e  mov     r9d, [rbp+nLengthNeeded]; nLength
0x180026222  lea     rax, [rbp+nLengthNeeded]
0x180026226  mov     rcx, [rsi]; lpFileName
0x180026229  mov     r8, rdi; pSecurityDescriptor
0x18002622c  mov     edx, 7; RequestedInformation
0x180026231  mov     [rsp+80h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180026236  call    cs:__imp_GetFileSecurityW
0x18002623c  test    eax, eax
0x18002623e  jnz     short loc_180026283
0x180026240  call    cs:__imp_GetLastError
0x180026246  mov     ebx, eax
0x180026248  mov     rcx, cs:WPP_GLOBAL_Control
0x18002624f  lea     rax, WPP_GLOBAL_Control
0x180026256  cmp     rcx, rax
0x180026259  jz      loc_1800262F3
0x18002625f  test    byte ptr [rcx+1Ch], 1
0x180026263  jz      loc_1800262F3
0x180026269  mov     rcx, [rcx+10h]
0x18002626d  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180026274  mov     edx, 15h
0x180026279  mov     r9d, ebx
0x18002627c  call    WPP_SF_d
0x180026281  jmp     short loc_1800262F3
0x180026283  mov     r8d, [rsi+8]; DesiredAccess
0x180026287  lea     rax, [rbp+var_3C]
0x18002628b  mov     [rsp+80h+AccessStatus], rax; AccessStatus
0x180026290  lea     r9, [rbp+GenericMapping]; GenericMapping
0x180026294  lea     rax, [rbp+var_38]
0x180026298  mov     [rbp+GenericMapping.GenericRead], 120089h
0x18002629f  mov     [rsp+80h+GrantedAccess], rax; GrantedAccess
0x1800262a4  mov     rdx, r14; ClientToken
0x1800262a7  lea     rax, [rbp+var_34]
0x1800262ab  mov     [rbp+GenericMapping.GenericWrite], 120116h
0x1800262b2  mov     [rsp+80h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800262b7  mov     rcx, rdi; pSecurityDescriptor
0x1800262ba  lea     rax, [rbp+PrivilegeSet]
0x1800262be  mov     [rbp+GenericMapping.GenericExecute], 1200A0h
0x1800262c5  mov     [rsp+80h+lpnLengthNeeded], rax; PrivilegeSet
0x1800262ca  mov     [rbp+GenericMapping.GenericAll], 1F01FFh
0x1800262d1  call    cs:__imp_AccessCheck
0x1800262d7  test    eax, eax
0x1800262d9  jz      short loc_1800262EE
0x1800262db  cmp     [rbp+var_3C], 0
0x1800262df  jz      short loc_1800262EE
0x1800262e1  mov     eax, [rsi+8]
0x1800262e4  xor     ebx, ebx
0x1800262e6  and     eax, [rbp+var_38]
0x1800262e9  cmp     eax, [rsi+8]
0x1800262ec  jz      short loc_1800262F3
0x1800262ee  mov     ebx, 5
0x1800262f3  mov     rcx, gs:60h
0x1800262fc  mov     r8, rdi; P
0x1800262ff  xor     edx, edx; Flags
0x180026301  mov     rcx, [rcx+30h]; HeapHandle
0x180026305  call    cs:__imp_RtlFreeHeap
0x18002630b  jmp     loc_18002614F
```
