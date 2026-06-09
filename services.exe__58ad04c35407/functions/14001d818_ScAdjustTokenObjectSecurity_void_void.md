# ScAdjustTokenObjectSecurity(void *,void *)

- ea: `0x14001d818`
- end: `0x14001dc66`
- name: `?ScAdjustTokenObjectSecurity@@YAKPEAX0@Z`
- size: `1102`
- prototype: `unsigned int(void *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003ae4c`

## callees

- `0x140004c58`
- `0x140008b90`
- `0x1400188fc`
- `0x14001d818`
- `0x14001df34`
- `0x14001e12c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d8bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d91c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d9b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001da0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001da5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001daa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001db24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001db85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001dbc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d8bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d91c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001d9b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001da0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001da5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001daa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001db24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001db85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001dbc0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001d85c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14001d85c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001dc46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001dc46`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x14001dbb6`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x14001dbb6`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x14001d9af`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x14001da50`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x14001d9af`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x14001da50`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001d90e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001d9fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001db16`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001d90e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001d9fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001db16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001dad6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001dc11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001dc1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001dc24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001dc2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001dc37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001dad6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001dc11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001dc1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001dc24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001dc2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001dc37`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14001db7b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14001db7b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x14001da9c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x14001da9c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14001d8b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14001d8b2`

## pseudocode

```c
__int64 __fastcall ScAdjustTokenObjectSecurity(void *a1, void *a2)
{
  unsigned __int16 *v3; // r14
  unsigned __int16 *v4; // r12
  DWORD LastError; // eax
  unsigned int v6; // ebx
  PRPC_ASYNC_STATE v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax
  unsigned __int64 v10; // r15
  wchar_t *v11; // rax
  DWORD v12; // eax
  HLOCAL v13; // rax
  unsigned __int64 v14; // rbx
  unsigned __int16 *v15; // rax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-18h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+40h] [rbp-10h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-8h] BYREF
  DWORD nLengthNeeded; // [rsp+A0h] [rbp+50h] BYREF
  ULONG StringSecurityDescriptorLen; // [rsp+A8h] [rbp+58h] BYREF

  nLengthNeeded = 0;
  SecurityDescriptor = 0;
  TokenHandle = 0;
  v3 = 0;
  StringSecurityDescriptor = 0;
  v4 = 0;
  StringSecurityDescriptorLen = 0;
  StringSid = 0;
  if ( OpenProcessToken(a1, 0x60000u, &TokenHandle) )
  {
    if ( ConvertSidToStringSidW(a2, &StringSid) )
    {
      v9 = -1;
      do
        ++v9;
      while ( StringSid[v9] );
      v10 = (unsigned int)(v9 + 14);
      v11 = (wchar_t *)LocalAlloc(0x40u, 2 * v10);
      v3 = v11;
      if ( v11 )
      {
        StringCchPrintfW(v11, v10, L"(A;;GA;;;%ws)", StringSid);
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
        {
          WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 93, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, v3);
        }
        if ( GetKernelObjectSecurity(TokenHandle, 4u, 0, 0, &nLengthNeeded) || (v12 = GetLastError(), v12 == 122) )
        {
          v13 = LocalAlloc(0x40u, nLengthNeeded);
          SecurityDescriptor = v13;
          if ( v13 )
          {
            if ( GetKernelObjectSecurity(TokenHandle, 4u, v13, nLengthNeeded, &nLengthNeeded) )
            {
              if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
                     SecurityDescriptor,
                     1u,
                     4u,
                     &StringSecurityDescriptor,
                     &StringSecurityDescriptorLen) )
              {
                LocalFree(SecurityDescriptor);
                SecurityDescriptor = 0;
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
                {
                  WPP_SF_S(
                    WPP_GLOBAL_Control->StubInfo,
                    98,
                    WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
                    StringSecurityDescriptor);
                }
                v14 = (unsigned int)v10 + StringSecurityDescriptorLen;
                v15 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v14);
                v4 = v15;
                if ( v15 )
                {
                  StringCchCopyW(v15, v14, StringSecurityDescriptor);
                  StringCchCatW(v4, v14, v3);
                  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v4, 1u, &SecurityDescriptor, 0) )
                  {
                    if ( SetKernelObjectSecurity(TokenHandle, 4u, SecurityDescriptor) )
                    {
                      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
                      {
                        WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 102, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, v4);
                      }
                      v6 = 0;
                    }
                    else
                    {
                      LastError = GetLastError();
                      v6 = LastError;
                      v7 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                        && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                      {
                        v8 = 101;
                        goto LABEL_5;
                      }
                    }
                  }
                  else
                  {
                    LastError = GetLastError();
                    v6 = LastError;
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                      && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                    {
                      v8 = 100;
                      goto LABEL_5;
                    }
                  }
                }
                else
                {
                  LastError = GetLastError();
                  v6 = LastError;
                  v7 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                  {
                    v8 = 99;
                    goto LABEL_5;
                  }
                }
              }
              else
              {
                LastError = GetLastError();
                v6 = LastError;
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                {
                  v8 = 97;
                  goto LABEL_5;
                }
              }
            }
            else
            {
              LastError = GetLastError();
              v6 = LastError;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                v8 = 96;
                goto LABEL_5;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            v6 = LastError;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              v8 = 95;
              goto LABEL_5;
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 94, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, v12);
          }
          v6 = 13;
        }
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v8 = 92;
          goto LABEL_5;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        v8 = 91;
        goto LABEL_5;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v8 = 90;
LABEL_5:
      WPP_SF_d(v7->StubInfo, v8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, LastError);
    }
  }
  LocalFree(SecurityDescriptor);
  LocalFree(StringSecurityDescriptor);
  LocalFree(v4);
  LocalFree(v3);
  LocalFree(StringSid);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v6;
}

```

## disassembly

```asm
0x14001d818  mov     [rsp-38h+arg_0], rbx
0x14001d81d  push    rbp
0x14001d81e  push    rsi
0x14001d81f  push    rdi
0x14001d820  push    r12
0x14001d822  push    r13
0x14001d824  push    r14
0x14001d826  push    r15
0x14001d828  mov     rbp, rsp
0x14001d82b  sub     rsp, 50h
0x14001d82f  xor     r13d, r13d
0x14001d832  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14001d836  mov     rbx, rdx
0x14001d839  mov     [rbp+nLengthNeeded], r13d
0x14001d83d  mov     edx, 60000h; DesiredAccess
0x14001d842  mov     [rbp+SecurityDescriptor], r13
0x14001d846  mov     [rbp+TokenHandle], r13
0x14001d84a  mov     r14d, r13d
0x14001d84d  mov     [rbp+StringSecurityDescriptor], r13
0x14001d851  mov     r12d, r13d
0x14001d854  mov     [rbp+StringSecurityDescriptorLen], r13d
0x14001d858  mov     [rbp+StringSid], r13
0x14001d85c  call    cs:__imp_OpenProcessToken
0x14001d862  test    eax, eax
0x14001d864  jnz     short loc_14001D8AB
0x14001d866  call    cs:__imp_GetLastError
0x14001d86c  mov     ebx, eax
0x14001d86e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d875  lea     rdi, WPP_GLOBAL_Control
0x14001d87c  cmp     rcx, rdi
0x14001d87f  jz      loc_14001DC0D
0x14001d885  test    byte ptr [rcx+1Ch], 1
0x14001d889  jz      loc_14001DC0D
0x14001d88f  lea     edx, [r13+5Ah]
0x14001d893  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x14001d89a  mov     rcx, [rcx+10h]
0x14001d89e  mov     r9d, eax
0x14001d8a1  call    WPP_SF_d
0x14001d8a6  jmp     loc_14001DC0D
0x14001d8ab  lea     rdx, [rbp+StringSid]; StringSid
0x14001d8af  mov     rcx, rbx; Sid
0x14001d8b2  call    cs:__imp_ConvertSidToStringSidW
0x14001d8b8  test    eax, eax
0x14001d8ba  jnz     short loc_14001D8EC
0x14001d8bc  call    cs:__imp_GetLastError
0x14001d8c2  mov     ebx, eax
0x14001d8c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d8cb  lea     rdi, WPP_GLOBAL_Control
0x14001d8d2  cmp     rcx, rdi
0x14001d8d5  jz      loc_14001DC0D
0x14001d8db  test    byte ptr [rcx+1Ch], 1
0x14001d8df  jz      loc_14001DC0D
0x14001d8e5  mov     edx, 5Bh ; '['
0x14001d8ea  jmp     short loc_14001D893
0x14001d8ec  mov     rcx, [rbp+StringSid]
0x14001d8f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001d8f4  inc     rax
0x14001d8f7  cmp     [rcx+rax*2], r13w
0x14001d8fc  jnz     short loc_14001D8F4
0x14001d8fe  lea     r15d, [rax+0Eh]
0x14001d902  mov     ecx, 40h ; '@'; uFlags
0x14001d907  lea     rdx, [r15+r15]; uBytes
0x14001d90b  mov     ebx, r15d
0x14001d90e  call    cs:__imp_LocalAlloc
0x14001d914  mov     r14, rax
0x14001d917  test    rax, rax
0x14001d91a  jnz     short loc_14001D94E
0x14001d91c  call    cs:__imp_GetLastError
0x14001d922  mov     ebx, eax
0x14001d924  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d92b  lea     rdi, WPP_GLOBAL_Control
0x14001d932  cmp     rcx, rdi
0x14001d935  jz      loc_14001DC0D
0x14001d93b  test    byte ptr [rcx+1Ch], 1
0x14001d93f  jz      loc_14001DC0D
0x14001d945  lea     edx, [r14+5Ch]
0x14001d949  jmp     loc_14001D893
0x14001d94e  mov     r9, [rbp+StringSid]
0x14001d952  lea     r8, aAGaWs; "(A;;GA;;;%ws)"
0x14001d959  mov     rdx, rbx; unsigned __int64
0x14001d95c  mov     rcx, r14; Buffer
0x14001d95f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001d964  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d96b  lea     rdi, WPP_GLOBAL_Control
0x14001d972  lea     rsi, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x14001d979  mov     ebx, 4
0x14001d97e  cmp     rcx, rdi
0x14001d981  jz      short loc_14001D99A
0x14001d983  test    [rcx+1Ch], bl
0x14001d986  jz      short loc_14001D99A
0x14001d988  mov     rcx, [rcx+10h]
0x14001d98c  lea     edx, [rbx+59h]
0x14001d98f  mov     r9, r14
0x14001d992  mov     r8, rsi
0x14001d995  call    WPP_SF_S
0x14001d99a  mov     rcx, [rbp+TokenHandle]; Handle
0x14001d99e  lea     rax, [rbp+nLengthNeeded]
0x14001d9a2  xor     r9d, r9d; nLength
0x14001d9a5  mov     [rsp+50h+lpnLengthNeeded], rax; lpnLengthNeeded
0x14001d9aa  xor     r8d, r8d; pSecurityDescriptor
0x14001d9ad  mov     edx, ebx; RequestedInformation
0x14001d9af  call    cs:__imp_GetKernelObjectSecurity
0x14001d9b5  test    eax, eax
0x14001d9b7  jnz     short loc_14001D9F4
0x14001d9b9  call    cs:__imp_GetLastError
0x14001d9bf  cmp     eax, 7Ah ; 'z'
0x14001d9c2  jz      short loc_14001D9F4
0x14001d9c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d9cb  cmp     rcx, rdi
0x14001d9ce  jz      short loc_14001D9EA
0x14001d9d0  test    byte ptr [rcx+1Ch], 1
0x14001d9d4  jz      short loc_14001D9EA
0x14001d9d6  mov     rcx, [rcx+10h]
0x14001d9da  mov     edx, 5Eh ; '^'
0x14001d9df  mov     r9d, eax
0x14001d9e2  mov     r8, rsi
0x14001d9e5  call    WPP_SF_d
0x14001d9ea  mov     ebx, 0Dh
0x14001d9ef  jmp     loc_14001DC0D
0x14001d9f4  mov     edx, [rbp+nLengthNeeded]; uBytes
0x14001d9f7  mov     ecx, 40h ; '@'; uFlags
0x14001d9fc  call    cs:__imp_LocalAlloc
0x14001da02  mov     [rbp+SecurityDescriptor], rax
0x14001da06  test    rax, rax
0x14001da09  jnz     short loc_14001DA3A
0x14001da0b  call    cs:__imp_GetLastError
0x14001da11  mov     ebx, eax
0x14001da13  mov     rcx, cs:WPP_GLOBAL_Control
0x14001da1a  cmp     rcx, rdi
0x14001da1d  jz      loc_14001DC0D
0x14001da23  test    byte ptr [rcx+1Ch], 1
0x14001da27  jz      loc_14001DC0D
0x14001da2d  mov     edx, 5Fh ; '_'
0x14001da32  mov     r8, rsi
0x14001da35  jmp     loc_14001D89A
0x14001da3a  mov     r9d, [rbp+nLengthNeeded]; nLength
0x14001da3e  lea     rcx, [rbp+nLengthNeeded]
0x14001da42  mov     [rsp+50h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x14001da47  mov     r8, rax; pSecurityDescriptor
0x14001da4a  mov     rcx, [rbp+TokenHandle]; Handle
0x14001da4e  mov     edx, ebx; RequestedInformation
0x14001da50  call    cs:__imp_GetKernelObjectSecurity
0x14001da56  test    eax, eax
0x14001da58  jnz     short loc_14001DA83
0x14001da5a  call    cs:__imp_GetLastError
0x14001da60  mov     ebx, eax
0x14001da62  mov     rcx, cs:WPP_GLOBAL_Control
0x14001da69  cmp     rcx, rdi
0x14001da6c  jz      loc_14001DC0D
0x14001da72  test    byte ptr [rcx+1Ch], 1
0x14001da76  jz      loc_14001DC0D
0x14001da7c  mov     edx, 60h ; '`'
0x14001da81  jmp     short loc_14001DA32
0x14001da83  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14001da87  lea     rax, [rbp+StringSecurityDescriptorLen]
0x14001da8b  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x14001da8f  mov     [rsp+50h+lpnLengthNeeded], rax; StringSecurityDescriptorLen
0x14001da94  mov     r8d, ebx; SecurityInformation
0x14001da97  mov     edx, 1; RequestedStringSDRevision
0x14001da9c  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x14001daa2  test    eax, eax
0x14001daa4  jnz     short loc_14001DAD2
0x14001daa6  call    cs:__imp_GetLastError
0x14001daac  mov     ebx, eax
0x14001daae  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dab5  cmp     rcx, rdi
0x14001dab8  jz      loc_14001DC0D
0x14001dabe  test    byte ptr [rcx+1Ch], 1
0x14001dac2  jz      loc_14001DC0D
0x14001dac8  mov     edx, 61h ; 'a'
0x14001dacd  jmp     loc_14001DA32
0x14001dad2  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x14001dad6  call    cs:__imp_LocalFree
0x14001dadc  mov     [rbp+SecurityDescriptor], r13
0x14001dae0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dae7  cmp     rcx, rdi
0x14001daea  jz      short loc_14001DB06
0x14001daec  test    [rcx+1Ch], bl
0x14001daef  jz      short loc_14001DB06
0x14001daf1  mov     r9, [rbp+StringSecurityDescriptor]
0x14001daf5  mov     edx, 62h ; 'b'
0x14001dafa  mov     rcx, [rcx+10h]
0x14001dafe  mov     r8, rsi
0x14001db01  call    WPP_SF_S
0x14001db06  mov     edx, [rbp+StringSecurityDescriptorLen]
0x14001db09  mov     ecx, 40h ; '@'; uFlags
0x14001db0e  add     edx, r15d
0x14001db11  mov     ebx, edx
0x14001db13  add     rdx, rdx; uBytes
0x14001db16  call    cs:__imp_LocalAlloc
0x14001db1c  mov     r12, rax
0x14001db1f  test    rax, rax
0x14001db22  jnz     short loc_14001DB50
0x14001db24  call    cs:__imp_GetLastError
0x14001db2a  mov     ebx, eax
0x14001db2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001db33  cmp     rcx, rdi
0x14001db36  jz      loc_14001DC0D
0x14001db3c  test    byte ptr [rcx+1Ch], 1
0x14001db40  jz      loc_14001DC0D
0x14001db46  lea     edx, [r12+63h]
0x14001db4b  jmp     loc_14001DA32
0x14001db50  mov     r8, [rbp+StringSecurityDescriptor]; unsigned __int16 *
0x14001db54  mov     rdx, rbx; unsigned __int64
0x14001db57  mov     rcx, r12; unsigned __int16 *
0x14001db5a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001db5f  mov     r8, r14; unsigned __int16 *
0x14001db62  mov     rdx, rbx; unsigned __int64
0x14001db65  mov     rcx, r12; unsigned __int16 *
0x14001db68  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001db6d  xor     r9d, r9d; SecurityDescriptorSize
0x14001db70  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14001db74  mov     rcx, r12; StringSecurityDescriptor
0x14001db77  lea     edx, [r9+1]; StringSDRevision
0x14001db7b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14001db81  test    eax, eax
0x14001db83  jnz     short loc_14001DBA9
0x14001db85  call    cs:__imp_GetLastError
0x14001db8b  mov     ebx, eax
0x14001db8d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001db94  cmp     rcx, rdi
0x14001db97  jz      short loc_14001DC0D
0x14001db99  test    byte ptr [rcx+1Ch], 1
0x14001db9d  jz      short loc_14001DC0D
0x14001db9f  mov     edx, 64h ; 'd'
0x14001dba4  jmp     loc_14001DA32
0x14001dba9  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14001dbad  mov     edx, 4; SecurityInformation
0x14001dbb2  mov     rcx, [rbp+TokenHandle]; Handle
0x14001dbb6  call    cs:__imp_SetKernelObjectSecurity
0x14001dbbc  test    eax, eax
0x14001dbbe  jnz     short loc_14001DBE4
0x14001dbc0  call    cs:__imp_GetLastError
0x14001dbc6  mov     ebx, eax
0x14001dbc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dbcf  cmp     rcx, rdi
0x14001dbd2  jz      short loc_14001DC0D
0x14001dbd4  test    byte ptr [rcx+1Ch], 1
0x14001dbd8  jz      short loc_14001DC0D
0x14001dbda  mov     edx, 65h ; 'e'
0x14001dbdf  jmp     loc_14001DA32
0x14001dbe4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dbeb  cmp     rcx, rdi
0x14001dbee  jz      short loc_14001DC0A
0x14001dbf0  test    byte ptr [rcx+1Ch], 4
0x14001dbf4  jz      short loc_14001DC0A
0x14001dbf6  mov     rcx, [rcx+10h]
0x14001dbfa  mov     edx, 66h ; 'f'
0x14001dbff  mov     r9, r12
0x14001dc02  mov     r8, rsi
0x14001dc05  call    WPP_SF_S
0x14001dc0a  mov     ebx, r13d
0x14001dc0d  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x14001dc11  call    cs:__imp_LocalFree
0x14001dc17  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x14001dc1b  call    cs:__imp_LocalFree
0x14001dc21  mov     rcx, r12; hMem
0x14001dc24  call    cs:__imp_LocalFree
0x14001dc2a  mov     rcx, r14; hMem
0x14001dc2d  call    cs:__imp_LocalFree
0x14001dc33  mov     rcx, [rbp+StringSid]; hMem
0x14001dc37  call    cs:__imp_LocalFree
0x14001dc3d  mov     rcx, [rbp+TokenHandle]; hObject
0x14001dc41  test    rcx, rcx
0x14001dc44  jz      short loc_14001DC4C
0x14001dc46  call    cs:__imp_CloseHandle
0x14001dc4c  mov     eax, ebx
0x14001dc4e  mov     rbx, [rsp+50h+arg_0]
0x14001dc56  add     rsp, 50h
0x14001dc5a  pop     r15
0x14001dc5c  pop     r14
0x14001dc5e  pop     r13
0x14001dc60  pop     r12
0x14001dc62  pop     rdi
0x14001dc63  pop     rsi
0x14001dc64  pop     rbp
0x14001dc65  retn
```
