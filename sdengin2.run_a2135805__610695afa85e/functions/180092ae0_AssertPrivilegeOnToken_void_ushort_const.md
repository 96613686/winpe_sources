# AssertPrivilegeOnToken(void *,ushort const *)

- ea: `0x180092ae0`
- end: `0x180092ca7`
- name: `?AssertPrivilegeOnToken@@YAJPEAXPEBG@Z`
- size: `455`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPCWSTR lpName)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008c94c`
- `0x1800929c4`

## callees

- `0x180008370`
- `0x180072e08`
- `0x180072f14`
- `0x180092ae0`
- `0x1800935fc`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180092c4b`
- `KERNEL32!GetLastError` at `0x180092c4b`
- `KERNEL32!SetLastError` at `0x180092bed`
- `KERNEL32!SetLastError` at `0x180092bed`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180092c17`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180092c17`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180092ba4`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180092ba4`

## string_xrefs

- `0x180092b42`: `AssertPrivilegeOnToken`

## pseudocode

```c
__int64 __fastcall AssertPrivilegeOnToken(HANDLE TokenHandle, LPCWSTR lpName, __int64 a3, __int64 a4)
{
  __int16 v6; // ax
  signed int LastFailureAsHRESULT; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  signed int LastError; // eax
  struct _LUID Luid; // [rsp+30h] [rbp-9h] BYREF
  int v13; // [rsp+38h] [rbp-1h] BYREF
  __int16 v14; // [rsp+3Ch] [rbp+3h]
  __int16 v15; // [rsp+3Eh] [rbp+5h]
  struct _TOKEN_PRIVILEGES NewState; // [rsp+70h] [rbp+37h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids, a4);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "AssertPrivilegeOnToken", 0x4E7u, 1u);
  Luid = 0;
  v6 = 1259;
  NewState = 0;
  if ( TokenHandle && (v14 = 1259, v6 = 1260, lpName) )
  {
    v13 = 0;
    v14 = 1260;
    if ( LookupPrivilegeValueW(0, lpName, &Luid) )
    {
      v13 = 0;
      v14 = 1262;
      NewState.Privileges[0].Luid = Luid;
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Attributes = 2;
      SetLastError(0);
      if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
      {
        v13 = 0;
        v14 = 1270;
        LastError = GetLastError();
        LastFailureAsHRESULT = LastError;
        if ( LastError > 0 )
          LastFailureAsHRESULT = (unsigned __int16)LastError | 0x80070000;
        v13 = LastFailureAsHRESULT;
        v6 = 1273;
        if ( LastFailureAsHRESULT >= 0 )
        {
          v14 = 1273;
          goto LABEL_16;
        }
      }
      else
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
        v13 = LastFailureAsHRESULT;
        v6 = 1270;
      }
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
      v13 = LastFailureAsHRESULT;
      v6 = 1262;
    }
  }
  else
  {
    LastFailureAsHRESULT = -2147024809;
    v13 = -2147024809;
  }
  v15 = v6;
LABEL_16:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180092ae0  mov     [rsp-8+arg_10], rbx
0x180092ae5  mov     [rsp-8+arg_18], rdi
0x180092aea  push    rbp
0x180092aeb  lea     rbp, [rsp-57h]
0x180092af0  sub     rsp, 90h
0x180092af7  mov     rax, cs:__security_cookie
0x180092afe  xor     rax, rsp
0x180092b01  mov     [rbp+57h+var_10], rax
0x180092b05  mov     rbx, rdx
0x180092b08  mov     rdi, rcx
0x180092b0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180092b12  lea     rax, WPP_GLOBAL_Control
0x180092b19  cmp     rcx, rax
0x180092b1c  jz      short loc_180092B3C
0x180092b1e  test    dword ptr [rcx+1Ch], 20000000h
0x180092b25  jz      short loc_180092B3C
0x180092b27  mov     rcx, [rcx+10h]
0x180092b2b  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x180092b32  mov     edx, 24h ; '$'
0x180092b37  call    WPP_SF_
0x180092b3c  mov     r9d, 1; unsigned __int16
0x180092b42  lea     rdx, aAssertprivileg_0; "AssertPrivilegeOnToken"
0x180092b49  mov     r8d, 4E7h; unsigned __int16
0x180092b4f  lea     rcx, [rbp+57h+var_58]; this
0x180092b53  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180092b58  mov     qword ptr [rbp+57h+Luid.LowPart], 0
0x180092b60  xorps   xmm0, xmm0
0x180092b63  mov     eax, 4EBh
0x180092b68  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x180092b6c  test    rdi, rdi
0x180092b6f  jnz     short loc_180092B82
0x180092b71  mov     ebx, 80070057h
0x180092b76  mov     [rbp+57h+var_58], ebx
0x180092b79  mov     [rbp+57h+var_52], ax
0x180092b7d  jmp     loc_180092C7A
0x180092b82  mov     [rbp+57h+var_54], ax
0x180092b86  mov     eax, 4ECh
0x180092b8b  test    rbx, rbx
0x180092b8e  jz      short loc_180092B71
0x180092b90  lea     r8, [rbp+57h+Luid]; lpLuid
0x180092b94  mov     [rbp+57h+var_58], 0
0x180092b9b  mov     rdx, rbx; lpName
0x180092b9e  mov     [rbp+57h+var_54], ax
0x180092ba2  xor     ecx, ecx; lpSystemName
0x180092ba4  call    cs:__imp_LookupPrivilegeValueW
0x180092bab  nop     dword ptr [rax+rax+00h]
0x180092bb0  test    eax, eax
0x180092bb2  jnz     short loc_180092BC5
0x180092bb4  call    GetLastFailureAsHRESULT
0x180092bb9  mov     ebx, eax
0x180092bbb  mov     [rbp+57h+var_58], eax
0x180092bbe  mov     eax, 4EEh
0x180092bc3  jmp     short loc_180092B79
0x180092bc5  mov     eax, 4EEh
0x180092bca  mov     [rbp+57h+var_58], 0
0x180092bd1  mov     [rbp+57h+var_54], ax
0x180092bd5  xor     ecx, ecx; dwErrCode
0x180092bd7  mov     rax, qword ptr [rbp+57h+Luid.LowPart]
0x180092bdb  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], rax
0x180092bdf  mov     [rbp+57h+NewState.PrivilegeCount], 1
0x180092be6  mov     [rbp+57h+NewState.Privileges.Attributes], 2
0x180092bed  call    cs:__imp_SetLastError
0x180092bf4  nop     dword ptr [rax+rax+00h]
0x180092bf9  xor     r9d, r9d; BufferLength
0x180092bfc  mov     [rsp+90h+ReturnLength], 0; ReturnLength
0x180092c05  lea     r8, [rbp+57h+NewState]; NewState
0x180092c09  mov     [rsp+90h+PreviousState], 0; PreviousState
0x180092c12  xor     edx, edx; DisableAllPrivileges
0x180092c14  mov     rcx, rdi; TokenHandle
0x180092c17  call    cs:__imp_AdjustTokenPrivileges
0x180092c1e  nop     dword ptr [rax+rax+00h]
0x180092c23  test    eax, eax
0x180092c25  jnz     short loc_180092C3B
0x180092c27  call    GetLastFailureAsHRESULT
0x180092c2c  mov     ebx, eax
0x180092c2e  mov     [rbp+57h+var_58], eax
0x180092c31  mov     eax, 4F6h
0x180092c36  jmp     loc_180092B79
0x180092c3b  mov     eax, 4F6h
0x180092c40  mov     [rbp+57h+var_58], 0
0x180092c47  mov     [rbp+57h+var_54], ax
0x180092c4b  call    cs:__imp_GetLastError
0x180092c52  nop     dword ptr [rax+rax+00h]
0x180092c57  mov     ebx, eax
0x180092c59  test    eax, eax
0x180092c5b  jle     short loc_180092C66
0x180092c5d  movzx   ebx, ax
0x180092c60  or      ebx, 80070000h
0x180092c66  mov     [rbp+57h+var_58], ebx
0x180092c69  mov     eax, 4F9h
0x180092c6e  test    ebx, ebx
0x180092c70  js      loc_180092B79
0x180092c76  mov     [rbp+57h+var_54], ax
0x180092c7a  lea     rcx, [rbp+57h+var_58]; this
0x180092c7e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180092c83  mov     eax, ebx
0x180092c85  mov     rcx, [rbp+57h+var_10]
0x180092c89  xor     rcx, rsp; StackCookie
0x180092c8c  call    __security_check_cookie
0x180092c91  lea     r11, [rsp+90h+var_s0]
0x180092c99  mov     rbx, [r11+20h]
0x180092c9d  mov     rdi, [r11+28h]
0x180092ca1  mov     rsp, r11
0x180092ca4  pop     rbp
0x180092ca5  retn
```
