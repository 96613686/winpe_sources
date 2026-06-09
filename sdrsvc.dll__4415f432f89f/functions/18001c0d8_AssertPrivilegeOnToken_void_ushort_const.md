# AssertPrivilegeOnToken(void *,ushort const *)

- ea: `0x18001c0d8`
- end: `0x18001c286`
- name: `?AssertPrivilegeOnToken@@YAJPEAXPEBG@Z`
- size: `430`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPCWSTR lpName)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001764c`
- `0x18001bfcc`

## callees

- `0x18000ea0c`
- `0x18001586c`
- `0x180015974`
- `0x18001c0d8`
- `0x18001c58c`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c231`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c1df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c1df`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001c203`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18001c203`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001c19c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18001c19c`

## string_xrefs

- `0x18001c13a`: `AssertPrivilegeOnToken`

## pseudocode

```c
__int64 __fastcall AssertPrivilegeOnToken(HANDLE TokenHandle, LPCWSTR lpName)
{
  __int16 v4; // ax
  signed int LastFailureAsHRESULT; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  signed int LastError; // eax
  _LUID Luid; // [rsp+30h] [rbp-9h] BYREF
  int v11; // [rsp+38h] [rbp-1h] BYREF
  __int16 v12; // [rsp+3Ch] [rbp+3h]
  __int16 v13; // [rsp+3Eh] [rbp+5h]
  struct _TOKEN_PRIVILEGES NewState; // [rsp+70h] [rbp+37h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v11, "AssertPrivilegeOnToken", 1255, 1);
  Luid = 0;
  v4 = 1259;
  NewState = 0;
  if ( TokenHandle && (v12 = 1259, v4 = 1260, lpName) )
  {
    v11 = 0;
    v12 = 1260;
    if ( LookupPrivilegeValueW(0, lpName, &Luid) )
    {
      v11 = 0;
      v12 = 1262;
      NewState.Privileges[0].Luid = Luid;
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Attributes = 2;
      SetLastError(0);
      if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
      {
        v11 = 0;
        v12 = 1270;
        LastError = GetLastError();
        LastFailureAsHRESULT = LastError;
        if ( LastError > 0 )
          LastFailureAsHRESULT = (unsigned __int16)LastError | 0x80070000;
        v11 = LastFailureAsHRESULT;
        v4 = 1273;
        if ( LastFailureAsHRESULT >= 0 )
        {
          v12 = 1273;
          goto LABEL_16;
        }
      }
      else
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
        v11 = LastFailureAsHRESULT;
        v4 = 1270;
      }
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6);
      v11 = LastFailureAsHRESULT;
      v4 = 1262;
    }
  }
  else
  {
    LastFailureAsHRESULT = -2147024809;
    v11 = -2147024809;
  }
  v13 = v4;
LABEL_16:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001c0d8  mov     [rsp-8+arg_10], rbx
0x18001c0dd  mov     [rsp-8+arg_18], rdi
0x18001c0e2  push    rbp
0x18001c0e3  lea     rbp, [rsp-57h]
0x18001c0e8  sub     rsp, 90h
0x18001c0ef  mov     rax, cs:__security_cookie
0x18001c0f6  xor     rax, rsp
0x18001c0f9  mov     [rbp+57h+var_10], rax
0x18001c0fd  mov     rbx, rdx
0x18001c100  mov     rdi, rcx
0x18001c103  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c10a  lea     rax, WPP_GLOBAL_Control
0x18001c111  cmp     rcx, rax
0x18001c114  jz      short loc_18001C134
0x18001c116  test    dword ptr [rcx+1Ch], 20000000h
0x18001c11d  jz      short loc_18001C134
0x18001c11f  mov     rcx, [rcx+10h]
0x18001c123  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18001c12a  mov     edx, 24h ; '$'
0x18001c12f  call    WPP_SF_
0x18001c134  mov     r9d, 1; unsigned __int16
0x18001c13a  lea     rdx, aAssertprivileg_0; "AssertPrivilegeOnToken"
0x18001c141  mov     r8d, 4E7h; unsigned __int16
0x18001c147  lea     rcx, [rbp+57h+var_58]; this
0x18001c14b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001c150  mov     qword ptr [rbp+57h+Luid.LowPart], 0
0x18001c158  xorps   xmm0, xmm0
0x18001c15b  mov     eax, 4EBh
0x18001c160  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x18001c164  test    rdi, rdi
0x18001c167  jnz     short loc_18001C17A
0x18001c169  mov     ebx, 80070057h
0x18001c16e  mov     [rbp+57h+var_58], ebx
0x18001c171  mov     [rbp+57h+var_52], ax
0x18001c175  jmp     loc_18001C25A
0x18001c17a  mov     [rbp+57h+var_54], ax
0x18001c17e  mov     eax, 4ECh
0x18001c183  test    rbx, rbx
0x18001c186  jz      short loc_18001C169
0x18001c188  lea     r8, [rbp+57h+Luid]; lpLuid
0x18001c18c  mov     [rbp+57h+var_58], 0
0x18001c193  mov     rdx, rbx; lpName
0x18001c196  mov     [rbp+57h+var_54], ax
0x18001c19a  xor     ecx, ecx; lpSystemName
0x18001c19c  call    cs:__imp_LookupPrivilegeValueW
0x18001c1a2  test    eax, eax
0x18001c1a4  jnz     short loc_18001C1B7
0x18001c1a6  call    GetLastFailureAsHRESULT
0x18001c1ab  mov     ebx, eax
0x18001c1ad  mov     [rbp+57h+var_58], eax
0x18001c1b0  mov     eax, 4EEh
0x18001c1b5  jmp     short loc_18001C171
0x18001c1b7  mov     eax, 4EEh
0x18001c1bc  mov     [rbp+57h+var_58], 0
0x18001c1c3  mov     [rbp+57h+var_54], ax
0x18001c1c7  xor     ecx, ecx; dwErrCode
0x18001c1c9  mov     rax, qword ptr [rbp+57h+Luid.LowPart]
0x18001c1cd  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], rax
0x18001c1d1  mov     [rbp+57h+NewState.PrivilegeCount], 1
0x18001c1d8  mov     [rbp+57h+NewState.Privileges.Attributes], 2
0x18001c1df  call    cs:__imp_SetLastError
0x18001c1e5  xor     r9d, r9d; BufferLength
0x18001c1e8  mov     [rsp+90h+ReturnLength], 0; ReturnLength
0x18001c1f1  lea     r8, [rbp+57h+NewState]; NewState
0x18001c1f5  mov     [rsp+90h+PreviousState], 0; PreviousState
0x18001c1fe  xor     edx, edx; DisableAllPrivileges
0x18001c200  mov     rcx, rdi; TokenHandle
0x18001c203  call    cs:__imp_AdjustTokenPrivileges
0x18001c209  test    eax, eax
0x18001c20b  jnz     short loc_18001C221
0x18001c20d  call    GetLastFailureAsHRESULT
0x18001c212  mov     ebx, eax
0x18001c214  mov     [rbp+57h+var_58], eax
0x18001c217  mov     eax, 4F6h
0x18001c21c  jmp     loc_18001C171
0x18001c221  mov     eax, 4F6h
0x18001c226  mov     [rbp+57h+var_58], 0
0x18001c22d  mov     [rbp+57h+var_54], ax
0x18001c231  call    cs:__imp_GetLastError
0x18001c237  mov     ebx, eax
0x18001c239  test    eax, eax
0x18001c23b  jle     short loc_18001C246
0x18001c23d  movzx   ebx, ax
0x18001c240  or      ebx, 80070000h
0x18001c246  mov     [rbp+57h+var_58], ebx
0x18001c249  mov     eax, 4F9h
0x18001c24e  test    ebx, ebx
0x18001c250  js      loc_18001C171
0x18001c256  mov     [rbp+57h+var_54], ax
0x18001c25a  lea     rcx, [rbp+57h+var_58]; this
0x18001c25e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001c263  mov     eax, ebx
0x18001c265  mov     rcx, [rbp+57h+var_10]
0x18001c269  xor     rcx, rsp; StackCookie
0x18001c26c  call    __security_check_cookie
0x18001c271  lea     r11, [rsp+90h+var_s0]
0x18001c279  mov     rbx, [r11+20h]
0x18001c27d  mov     rdi, [r11+28h]
0x18001c281  mov     rsp, r11
0x18001c284  pop     rbp
0x18001c285  retn
```
