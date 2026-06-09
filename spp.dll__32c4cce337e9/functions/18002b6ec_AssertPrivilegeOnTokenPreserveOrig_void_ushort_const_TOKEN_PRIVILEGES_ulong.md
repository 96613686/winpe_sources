# AssertPrivilegeOnTokenPreserveOrig(void *,ushort const *,_TOKEN_PRIVILEGES *,ulong)

- ea: `0x18002b6ec`
- end: `0x18002b8c4`
- name: `?AssertPrivilegeOnTokenPreserveOrig@@YAJPEAXPEBGPEAU_TOKEN_PRIVILEGES@@K@Z`
- size: `472`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, const unsigned __int16 *, struct _TOKEN_PRIVILEGES *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c2e8`
- `0x18001faf8`

## callees

- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002b6ec`
- `0x18002d6e8`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002b860`
- `KERNEL32!GetLastError` at `0x18002b860`
- `KERNEL32!SetLastError` at `0x18002b812`
- `KERNEL32!SetLastError` at `0x18002b812`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002b835`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002b835`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002b7cc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002b7cc`

## string_xrefs

- `0x18002b7c3`: `SeRestorePrivilege`
- `0x18002b74e`: `AssertPrivilegeOnTokenPreserveOrig`

## pseudocode

```c
__int64 __fastcall AssertPrivilegeOnTokenPreserveOrig(
        HANDLE TokenHandle,
        const unsigned __int16 *a2,
        struct _TOKEN_PRIVILEGES *a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  struct _TOKEN_PRIVILEGES *v8; // rax
  __int16 v9; // ax
  __int64 v10; // rcx
  signed int LastFailureAsHRESULT; // ebx
  __int64 v12; // rcx
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-9h] BYREF
  struct _LUID Luid; // [rsp+38h] [rbp-1h] BYREF
  int v17; // [rsp+40h] [rbp+7h] BYREF
  __int16 v18; // [rsp+44h] [rbp+Bh]
  __int16 v19; // [rsp+46h] [rbp+Dh]
  struct _TOKEN_PRIVILEGES NewState; // [rsp+78h] [rbp+3Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "AssertPrivilegeOnTokenPreserveOrig", 1289, 1);
  Luid = 0;
  ReturnLength = 0;
  NewState = 0;
  if ( !a3 )
  {
    v9 = 1297;
    goto LABEL_18;
  }
  v7 = 16;
  v8 = a3;
  do
  {
    LOBYTE(v8->PrivilegeCount) = 0;
    v8 = (struct _TOKEN_PRIVILEGES *)((char *)v8 + 1);
    --v7;
  }
  while ( v7 );
  v18 = 1297;
  if ( !TokenHandle )
  {
    v9 = 1298;
LABEL_18:
    LastFailureAsHRESULT = -2147024809;
    v17 = -2147024809;
    goto LABEL_19;
  }
  v17 = 0;
  v18 = 1299;
  if ( !LookupPrivilegeValueW(0, L"SeRestorePrivilege", &Luid) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
    v17 = LastFailureAsHRESULT;
    v9 = 1301;
LABEL_19:
    v19 = v9;
    goto LABEL_20;
  }
  v17 = 0;
  v18 = 1301;
  NewState.Privileges[0].Luid = Luid;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = 2;
  SetLastError(0);
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, a3, &ReturnLength) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
    v17 = LastFailureAsHRESULT;
    v9 = 1314;
    goto LABEL_19;
  }
  v17 = 0;
  v18 = 1314;
  LastError = GetLastError();
  LastFailureAsHRESULT = LastError;
  if ( LastError > 0 )
    LastFailureAsHRESULT = (unsigned __int16)LastError | 0x80070000;
  v17 = LastFailureAsHRESULT;
  v9 = 1317;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_19;
  v18 = 1317;
LABEL_20:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17, v5, v6);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18002b6ec  mov     [rsp-8+arg_8], rbx
0x18002b6f1  mov     [rsp-8+arg_18], rdi
0x18002b6f6  push    rbp
0x18002b6f7  lea     rbp, [rsp-57h]
0x18002b6fc  sub     rsp, 90h
0x18002b703  mov     rax, cs:__security_cookie
0x18002b70a  xor     rax, rsp
0x18002b70d  mov     [rbp+57h+var_8], rax
0x18002b711  mov     rbx, r8
0x18002b714  mov     rdi, rcx
0x18002b717  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b71e  lea     rax, WPP_GLOBAL_Control
0x18002b725  cmp     rcx, rax
0x18002b728  jz      short loc_18002B748
0x18002b72a  test    dword ptr [rcx+1Ch], 20000000h
0x18002b731  jz      short loc_18002B748
0x18002b733  mov     rcx, [rcx+10h]
0x18002b737  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18002b73e  mov     edx, 25h ; '%'
0x18002b743  call    WPP_SF_
0x18002b748  mov     r9d, 1; unsigned __int16
0x18002b74e  lea     rdx, aAssertprivileg; "AssertPrivilegeOnTokenPreserveOrig"
0x18002b755  mov     r8d, 509h; unsigned __int16
0x18002b75b  lea     rcx, [rbp+57h+var_50]; this
0x18002b75f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002b764  mov     qword ptr [rbp+57h+Luid.LowPart], 0
0x18002b76c  xorps   xmm0, xmm0
0x18002b76f  mov     [rbp+57h+var_60], 0
0x18002b776  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x18002b77a  test    rbx, rbx
0x18002b77d  jz      loc_18002B887
0x18002b783  mov     ecx, 10h
0x18002b788  mov     rax, rbx
0x18002b78b  mov     byte ptr [rax], 0
0x18002b78e  inc     rax
0x18002b791  sub     rcx, 1
0x18002b795  jnz     short loc_18002B78B
0x18002b797  mov     eax, 511h
0x18002b79c  mov     [rbp+57h+var_4C], ax
0x18002b7a0  test    rdi, rdi
0x18002b7a3  jnz     short loc_18002B7AF
0x18002b7a5  mov     eax, 512h
0x18002b7aa  jmp     loc_18002B88C
0x18002b7af  mov     eax, 513h
0x18002b7b4  mov     [rbp+57h+var_50], 0
0x18002b7bb  lea     r8, [rbp+57h+Luid]; lpLuid
0x18002b7bf  mov     [rbp+57h+var_4C], ax
0x18002b7c3  lea     rdx, Name; "SeRestorePrivilege"
0x18002b7ca  xor     ecx, ecx; lpSystemName
0x18002b7cc  call    cs:__imp_LookupPrivilegeValueW
0x18002b7d2  test    eax, eax
0x18002b7d4  jnz     short loc_18002B7EA
0x18002b7d6  call    GetLastFailureAsHRESULT
0x18002b7db  mov     ebx, eax
0x18002b7dd  mov     [rbp+57h+var_50], eax
0x18002b7e0  mov     eax, 515h
0x18002b7e5  jmp     loc_18002B894
0x18002b7ea  mov     eax, 515h
0x18002b7ef  mov     [rbp+57h+var_50], 0
0x18002b7f6  mov     [rbp+57h+var_4C], ax
0x18002b7fa  xor     ecx, ecx; dwErrCode
0x18002b7fc  mov     rax, qword ptr [rbp+57h+Luid.LowPart]
0x18002b800  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], rax
0x18002b804  mov     [rbp+57h+NewState.PrivilegeCount], 1
0x18002b80b  mov     [rbp+57h+NewState.Privileges.Attributes], 2
0x18002b812  call    cs:__imp_SetLastError
0x18002b818  lea     rax, [rbp+57h+var_60]
0x18002b81c  mov     r9d, 10h; BufferLength
0x18002b822  mov     [rsp+90h+ReturnLength], rax; ReturnLength
0x18002b827  lea     r8, [rbp+57h+NewState]; NewState
0x18002b82b  xor     edx, edx; DisableAllPrivileges
0x18002b82d  mov     [rsp+90h+PreviousState], rbx; PreviousState
0x18002b832  mov     rcx, rdi; TokenHandle
0x18002b835  call    cs:__imp_AdjustTokenPrivileges
0x18002b83b  test    eax, eax
0x18002b83d  jnz     short loc_18002B850
0x18002b83f  call    GetLastFailureAsHRESULT
0x18002b844  mov     ebx, eax
0x18002b846  mov     [rbp+57h+var_50], eax
0x18002b849  mov     eax, 522h
0x18002b84e  jmp     short loc_18002B894
0x18002b850  mov     eax, 522h
0x18002b855  mov     [rbp+57h+var_50], 0
0x18002b85c  mov     [rbp+57h+var_4C], ax
0x18002b860  call    cs:__imp_GetLastError
0x18002b866  mov     ebx, eax
0x18002b868  test    eax, eax
0x18002b86a  jle     short loc_18002B875
0x18002b86c  movzx   ebx, ax
0x18002b86f  or      ebx, 80070000h
0x18002b875  mov     [rbp+57h+var_50], ebx
0x18002b878  mov     eax, 525h
0x18002b87d  test    ebx, ebx
0x18002b87f  js      short loc_18002B894
0x18002b881  mov     [rbp+57h+var_4C], ax
0x18002b885  jmp     short loc_18002B898
0x18002b887  mov     eax, 511h
0x18002b88c  mov     ebx, 80070057h
0x18002b891  mov     [rbp+57h+var_50], ebx
0x18002b894  mov     [rbp+57h+var_4A], ax
0x18002b898  lea     rcx, [rbp+57h+var_50]; this
0x18002b89c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002b8a1  mov     eax, ebx
0x18002b8a3  mov     rcx, [rbp+57h+var_8]
0x18002b8a7  xor     rcx, rsp; StackCookie
0x18002b8aa  call    __security_check_cookie
0x18002b8af  lea     r11, [rsp+90h+var_s0]
0x18002b8b7  mov     rbx, [r11+18h]
0x18002b8bb  mov     rdi, [r11+28h]
0x18002b8bf  mov     rsp, r11
0x18002b8c2  pop     rbp
0x18002b8c3  retn
```
