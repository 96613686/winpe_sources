# RestoreOrigPrivilegeOnToken(void *,_TOKEN_PRIVILEGES *)

- ea: `0x18002b8cc`
- end: `0x18002b9d3`
- name: `?RestoreOrigPrivilegeOnToken@@YAJPEAXPEAU_TOKEN_PRIVILEGES@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PTOKEN_PRIVILEGES NewState)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c2e8`
- `0x18001faf8`

## callees

- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002b8cc`
- `0x18002d6e8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002b99a`
- `KERNEL32!GetLastError` at `0x18002b99a`
- `KERNEL32!SetLastError` at `0x18002b958`
- `KERNEL32!SetLastError` at `0x18002b958`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002b973`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002b973`

## string_xrefs

- `0x18002b915`: `RestoreOrigPrivilegeOnToken`

## pseudocode

```c
__int64 __fastcall RestoreOrigPrivilegeOnToken(HANDLE TokenHandle, PTOKEN_PRIVILEGES NewState)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int16 v6; // ax
  signed int LastFailureAsHRESULT; // ebx
  __int64 v8; // rcx
  signed int LastError; // eax
  int v11; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+34h] [rbp-44h]
  __int16 v13; // [rsp+36h] [rbp-42h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "RestoreOrigPrivilegeOnToken", 1331, 1);
  v6 = 1333;
  if ( !NewState )
  {
    LastFailureAsHRESULT = -2147024809;
    v11 = -2147024809;
LABEL_6:
    v13 = v6;
    goto LABEL_15;
  }
  LastFailureAsHRESULT = 0;
  v12 = 1333;
  v11 = 0;
  if ( NewState->PrivilegeCount && TokenHandle != (HANDLE)-1LL )
  {
    SetLastError(0);
    if ( AdjustTokenPrivileges(TokenHandle, 0, NewState, 0, 0, 0) )
    {
      v11 = 0;
      v12 = 1344;
      LastError = GetLastError();
      LastFailureAsHRESULT = LastError;
      if ( LastError > 0 )
        LastFailureAsHRESULT = (unsigned __int16)LastError | 0x80070000;
      v11 = LastFailureAsHRESULT;
      v6 = 1347;
      if ( LastFailureAsHRESULT >= 0 )
      {
        v12 = 1347;
        goto LABEL_15;
      }
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
      v11 = LastFailureAsHRESULT;
      v6 = 1344;
    }
    goto LABEL_6;
  }
LABEL_15:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11, v4, v5);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18002b8cc  push    rbp
0x18002b8ce  push    rbx
0x18002b8cf  push    rsi
0x18002b8d0  push    rdi
0x18002b8d1  mov     rbp, rsp
0x18002b8d4  sub     rsp, 78h
0x18002b8d8  mov     rdi, rdx
0x18002b8db  mov     rsi, rcx
0x18002b8de  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8e5  lea     rax, WPP_GLOBAL_Control
0x18002b8ec  cmp     rcx, rax
0x18002b8ef  jz      short loc_18002B90F
0x18002b8f1  test    dword ptr [rcx+1Ch], 20000000h
0x18002b8f8  jz      short loc_18002B90F
0x18002b8fa  mov     rcx, [rcx+10h]
0x18002b8fe  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18002b905  mov     edx, 26h ; '&'
0x18002b90a  call    WPP_SF_
0x18002b90f  mov     r9d, 1; unsigned __int16
0x18002b915  lea     rdx, aRestoreorigpri; "RestoreOrigPrivilegeOnToken"
0x18002b91c  mov     r8d, 533h; unsigned __int16
0x18002b922  lea     rcx, [rbp+var_48]; this
0x18002b926  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002b92b  mov     eax, 535h
0x18002b930  test    rdi, rdi
0x18002b933  jnz     short loc_18002B943
0x18002b935  mov     ebx, 80070057h
0x18002b93a  mov     [rbp+var_48], ebx
0x18002b93d  mov     [rbp+var_42], ax
0x18002b941  jmp     short loc_18002B9BF
0x18002b943  xor     ebx, ebx
0x18002b945  mov     [rbp+var_44], ax
0x18002b949  mov     [rbp+var_48], ebx
0x18002b94c  cmp     [rdi], ebx
0x18002b94e  jbe     short loc_18002B9BF
0x18002b950  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002b954  jz      short loc_18002B9BF
0x18002b956  xor     ecx, ecx; dwErrCode
0x18002b958  call    cs:__imp_SetLastError
0x18002b95e  xor     r9d, r9d; BufferLength
0x18002b961  mov     [rsp+78h+ReturnLength], rbx; ReturnLength
0x18002b966  mov     r8, rdi; NewState
0x18002b969  mov     [rsp+78h+PreviousState], rbx; PreviousState
0x18002b96e  xor     edx, edx; DisableAllPrivileges
0x18002b970  mov     rcx, rsi; TokenHandle
0x18002b973  call    cs:__imp_AdjustTokenPrivileges
0x18002b979  test    eax, eax
0x18002b97b  jnz     short loc_18002B98E
0x18002b97d  call    GetLastFailureAsHRESULT
0x18002b982  mov     ebx, eax
0x18002b984  mov     [rbp+var_48], eax
0x18002b987  mov     eax, 540h
0x18002b98c  jmp     short loc_18002B93D
0x18002b98e  mov     eax, 540h
0x18002b993  mov     [rbp+var_48], ebx
0x18002b996  mov     [rbp+var_44], ax
0x18002b99a  call    cs:__imp_GetLastError
0x18002b9a0  mov     ebx, eax
0x18002b9a2  test    eax, eax
0x18002b9a4  jle     short loc_18002B9AF
0x18002b9a6  movzx   ebx, ax
0x18002b9a9  or      ebx, 80070000h
0x18002b9af  mov     [rbp+var_48], ebx
0x18002b9b2  mov     eax, 543h
0x18002b9b7  test    ebx, ebx
0x18002b9b9  js      short loc_18002B93D
0x18002b9bb  mov     [rbp+var_44], ax
0x18002b9bf  lea     rcx, [rbp+var_48]; this
0x18002b9c3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002b9c8  mov     eax, ebx
0x18002b9ca  add     rsp, 78h
0x18002b9ce  pop     rdi
0x18002b9cf  pop     rsi
0x18002b9d0  pop     rbx
0x18002b9d1  pop     rbp
0x18002b9d2  retn
```
