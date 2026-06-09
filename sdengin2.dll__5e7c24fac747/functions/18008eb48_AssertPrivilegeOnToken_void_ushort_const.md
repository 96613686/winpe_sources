# AssertPrivilegeOnToken(void *,ushort const *)

- ea: `0x18008eb48`
- end: `0x18008ecf6`
- name: `?AssertPrivilegeOnToken@@YAJPEAXPEBG@Z`
- size: `430`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPCWSTR lpName)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180088e88`
- `0x18008ea3c`

## callees

- `0x1800081d8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008eb48`
- `0x18008f5d0`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008eca1`
- `KERNEL32!GetLastError` at `0x18008eca1`
- `KERNEL32!SetLastError` at `0x18008ec4f`
- `KERNEL32!SetLastError` at `0x18008ec4f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18008ec73`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18008ec73`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18008ec0c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18008ec0c`

## string_xrefs

- `0x18008ebaa`: `AssertPrivilegeOnToken`

## pseudocode

```c
__int64 __fastcall AssertPrivilegeOnToken(HANDLE TokenHandle, LPCWSTR lpName)
{
  __int16 v4; // ax
  signed int LastFailureAsHRESULT; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  signed int LastError; // eax
  struct _LUID Luid; // [rsp+30h] [rbp-9h] BYREF
  int v11; // [rsp+38h] [rbp-1h] BYREF
  __int16 v12; // [rsp+3Ch] [rbp+3h]
  __int16 v13; // [rsp+3Eh] [rbp+5h]
  struct _TOKEN_PRIVILEGES NewState; // [rsp+70h] [rbp+37h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
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
0x18008eb48  mov     [rsp-8+arg_10], rbx
0x18008eb4d  mov     [rsp-8+arg_18], rdi
0x18008eb52  push    rbp
0x18008eb53  lea     rbp, [rsp-57h]
0x18008eb58  sub     rsp, 90h
0x18008eb5f  mov     rax, cs:__security_cookie
0x18008eb66  xor     rax, rsp
0x18008eb69  mov     [rbp+57h+var_10], rax
0x18008eb6d  mov     rbx, rdx
0x18008eb70  mov     rdi, rcx
0x18008eb73  mov     rcx, cs:WPP_GLOBAL_Control
0x18008eb7a  lea     rax, WPP_GLOBAL_Control
0x18008eb81  cmp     rcx, rax
0x18008eb84  jz      short loc_18008EBA4
0x18008eb86  test    dword ptr [rcx+1Ch], 20000000h
0x18008eb8d  jz      short loc_18008EBA4
0x18008eb8f  mov     rcx, [rcx+10h]
0x18008eb93  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18008eb9a  mov     edx, 24h ; '$'
0x18008eb9f  call    WPP_SF_
0x18008eba4  mov     r9d, 1; unsigned __int16
0x18008ebaa  lea     rdx, aAssertprivileg_0; "AssertPrivilegeOnToken"
0x18008ebb1  mov     r8d, 4E7h; unsigned __int16
0x18008ebb7  lea     rcx, [rbp+57h+var_58]; this
0x18008ebbb  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008ebc0  mov     qword ptr [rbp+57h+Luid.LowPart], 0
0x18008ebc8  xorps   xmm0, xmm0
0x18008ebcb  mov     eax, 4EBh
0x18008ebd0  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x18008ebd4  test    rdi, rdi
0x18008ebd7  jnz     short loc_18008EBEA
0x18008ebd9  mov     ebx, 80070057h
0x18008ebde  mov     [rbp+57h+var_58], ebx
0x18008ebe1  mov     [rbp+57h+var_52], ax
0x18008ebe5  jmp     loc_18008ECCA
0x18008ebea  mov     [rbp+57h+var_54], ax
0x18008ebee  mov     eax, 4ECh
0x18008ebf3  test    rbx, rbx
0x18008ebf6  jz      short loc_18008EBD9
0x18008ebf8  lea     r8, [rbp+57h+Luid]; lpLuid
0x18008ebfc  mov     [rbp+57h+var_58], 0
0x18008ec03  mov     rdx, rbx; lpName
0x18008ec06  mov     [rbp+57h+var_54], ax
0x18008ec0a  xor     ecx, ecx; lpSystemName
0x18008ec0c  call    cs:__imp_LookupPrivilegeValueW
0x18008ec12  test    eax, eax
0x18008ec14  jnz     short loc_18008EC27
0x18008ec16  call    GetLastFailureAsHRESULT
0x18008ec1b  mov     ebx, eax
0x18008ec1d  mov     [rbp+57h+var_58], eax
0x18008ec20  mov     eax, 4EEh
0x18008ec25  jmp     short loc_18008EBE1
0x18008ec27  mov     eax, 4EEh
0x18008ec2c  mov     [rbp+57h+var_58], 0
0x18008ec33  mov     [rbp+57h+var_54], ax
0x18008ec37  xor     ecx, ecx; dwErrCode
0x18008ec39  mov     rax, qword ptr [rbp+57h+Luid.LowPart]
0x18008ec3d  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], rax
0x18008ec41  mov     [rbp+57h+NewState.PrivilegeCount], 1
0x18008ec48  mov     [rbp+57h+NewState.Privileges.Attributes], 2
0x18008ec4f  call    cs:__imp_SetLastError
0x18008ec55  xor     r9d, r9d; BufferLength
0x18008ec58  mov     [rsp+90h+ReturnLength], 0; ReturnLength
0x18008ec61  lea     r8, [rbp+57h+NewState]; NewState
0x18008ec65  mov     [rsp+90h+PreviousState], 0; PreviousState
0x18008ec6e  xor     edx, edx; DisableAllPrivileges
0x18008ec70  mov     rcx, rdi; TokenHandle
0x18008ec73  call    cs:__imp_AdjustTokenPrivileges
0x18008ec79  test    eax, eax
0x18008ec7b  jnz     short loc_18008EC91
0x18008ec7d  call    GetLastFailureAsHRESULT
0x18008ec82  mov     ebx, eax
0x18008ec84  mov     [rbp+57h+var_58], eax
0x18008ec87  mov     eax, 4F6h
0x18008ec8c  jmp     loc_18008EBE1
0x18008ec91  mov     eax, 4F6h
0x18008ec96  mov     [rbp+57h+var_58], 0
0x18008ec9d  mov     [rbp+57h+var_54], ax
0x18008eca1  call    cs:__imp_GetLastError
0x18008eca7  mov     ebx, eax
0x18008eca9  test    eax, eax
0x18008ecab  jle     short loc_18008ECB6
0x18008ecad  movzx   ebx, ax
0x18008ecb0  or      ebx, 80070000h
0x18008ecb6  mov     [rbp+57h+var_58], ebx
0x18008ecb9  mov     eax, 4F9h
0x18008ecbe  test    ebx, ebx
0x18008ecc0  js      loc_18008EBE1
0x18008ecc6  mov     [rbp+57h+var_54], ax
0x18008ecca  lea     rcx, [rbp+57h+var_58]; this
0x18008ecce  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008ecd3  mov     eax, ebx
0x18008ecd5  mov     rcx, [rbp+57h+var_10]
0x18008ecd9  xor     rcx, rsp; StackCookie
0x18008ecdc  call    __security_check_cookie
0x18008ece1  lea     r11, [rsp+90h+var_s0]
0x18008ece9  mov     rbx, [r11+20h]
0x18008eced  mov     rdi, [r11+28h]
0x18008ecf1  mov     rsp, r11
0x18008ecf4  pop     rbp
0x18008ecf5  retn
```
