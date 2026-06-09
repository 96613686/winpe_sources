# _InternalQueryUserToken(ulong,void * *)

- ea: `0x180039d70`
- end: `0x180039e27`
- name: `?_InternalQueryUserToken@@YAJKPEAPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(ULONG SessionId, PHANDLE phNewToken)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003c650`
- `0x1800b38ec`

## callees

- `0x180039d70`
- `0x1800624bc`
- `0x18006da60`
- `0x1800b7570`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180039dc8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180039dc8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180039de7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180039de7`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180039e09`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180039e09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039d97`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180039d8d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180039d8d`

## pseudocode

```c
signed int __fastcall _InternalQueryUserToken(ULONG SessionId, PHANDLE phNewToken)
{
  __int64 v4; // rcx
  signed int result; // eax
  int Error; // ebx

  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    if ( WTSQueryUserToken(SessionId, phNewToken) )
    {
      return 0;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    if ( (_BYTE)dword_180148288 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v4);
    AcquireSRWLockShared(&stru_180148210);
    if ( TargetHandle == (HANDLE)-1LL )
    {
      Error = -2147023888;
    }
    else if ( DuplicateTokenEx(TargetHandle, 0, 0, SecurityImpersonation, TokenPrimary, phNewToken) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    ReleaseSRWLockShared(&stru_180148210);
    return Error;
  }
  return result;
}

```

## disassembly

```asm
0x180039d70  mov     [rsp+arg_0], rbx
0x180039d75  push    rdi
0x180039d76  sub     rsp, 30h
0x180039d7a  mov     rbx, rdx
0x180039d7d  mov     edi, ecx
0x180039d7f  call    IsWTSEnumerateSessionsWPresent
0x180039d84  test    al, al
0x180039d86  jz      short loc_180039DB8
0x180039d88  mov     rdx, rbx; phToken
0x180039d8b  mov     ecx, edi; SessionId
0x180039d8d  call    cs:__imp_WTSQueryUserToken
0x180039d93  test    eax, eax
0x180039d95  jnz     short loc_180039DAB
0x180039d97  call    cs:__imp_GetLastError
0x180039d9d  test    eax, eax
0x180039d9f  jle     short loc_180039DAD
0x180039da1  movzx   eax, ax
0x180039da4  or      eax, 80070000h
0x180039da9  jmp     short loc_180039DAD
0x180039dab  xor     eax, eax
0x180039dad  mov     rbx, [rsp+38h+arg_0]
0x180039db2  add     rsp, 30h
0x180039db6  pop     rdi
0x180039db7  retn
0x180039db8  cmp     byte ptr cs:dword_180148288, 0
0x180039dbf  jnz     short loc_180039E17
0x180039dc1  lea     rcx, stru_180148210; SRWLock
0x180039dc8  call    cs:__imp_AcquireSRWLockShared
0x180039dce  mov     rcx, cs:TargetHandle; hExistingToken
0x180039dd5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180039dd9  jnz     short loc_180039DF1
0x180039ddb  mov     ebx, 800703F0h
0x180039de0  lea     rcx, stru_180148210; SRWLock
0x180039de7  call    cs:__imp_ReleaseSRWLockShared
0x180039ded  mov     eax, ebx
0x180039def  jmp     short loc_180039DAD
0x180039df1  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x180039df6  mov     r9d, 2; ImpersonationLevel
0x180039dfc  xor     r8d, r8d; lpTokenAttributes
0x180039dff  mov     [rsp+38h+TokenType], 1; TokenType
0x180039e07  xor     edx, edx; dwDesiredAccess
0x180039e09  call    cs:__imp_DuplicateTokenEx
0x180039e0f  test    eax, eax
0x180039e11  jz      short loc_180039E1E
0x180039e13  xor     ebx, ebx
0x180039e15  jmp     short loc_180039DE0
0x180039e17  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180039e1c  jmp     short loc_180039DC1
0x180039e1e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180039e23  mov     ebx, eax
0x180039e25  jmp     short loc_180039DE0
```
