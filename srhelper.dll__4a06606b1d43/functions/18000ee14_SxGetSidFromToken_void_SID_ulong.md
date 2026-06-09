# SxGetSidFromToken(void *,_SID *,ulong)

- ea: `0x18000ee14`
- end: `0x18000ef69`
- name: `?SxGetSidFromToken@@YAJPEAXPEAU_SID@@K@Z`
- size: `341`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID pDestinationSid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18000ea60`

## callees

- `0x180003ce0`
- `0x18000d348`
- `0x18000d43c`
- `0x18000ee14`
- `0x18000f154`
- `0x1800157be`
- `0x1800157f0`

## import_xrefs

- `ADVAPI32!CopySid` at `0x18000ef14`
- `ADVAPI32!CopySid` at `0x18000ef14`
- `ADVAPI32!GetTokenInformation` at `0x18000eed9`
- `ADVAPI32!GetTokenInformation` at `0x18000eed9`

## string_xrefs

- `0x18000ee76`: `SxGetSidFromToken`

## pseudocode

```c
__int64 __fastcall SxGetSidFromToken(HANDLE TokenHandle, PSID pDestinationSid)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int LastFailureAsHRESULT; // ebx
  __int16 v7; // ax
  DWORD ReturnLength; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v10; // [rsp+38h] [rbp-51h] BYREF
  __int16 v11; // [rsp+3Ch] [rbp-4Dh]
  __int16 v12; // [rsp+3Eh] [rbp-4Bh]
  PSID TokenInformation[12]; // [rsp+70h] [rbp-19h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "SxGetSidFromToken", 564);
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  if ( !pDestinationSid )
  {
    LastFailureAsHRESULT = -2147024809;
    v12 = 570;
LABEL_12:
    v10 = LastFailureAsHRESULT;
    goto LABEL_13;
  }
  v11 = 570;
  v10 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
  {
    v11 = 573;
    v10 = 0;
    if ( CopySid(0x44u, pDestinationSid, TokenInformation[0]) )
    {
      LastFailureAsHRESULT = 0;
      v11 = 575;
      goto LABEL_12;
    }
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v10 = LastFailureAsHRESULT;
    v7 = 575;
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT();
    v10 = LastFailureAsHRESULT;
    v7 = 573;
  }
  v12 = v7;
LABEL_13:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10, v4, v5);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18000ee14  mov     [rsp-8+arg_10], rbx
0x18000ee19  mov     [rsp-8+arg_18], rdi
0x18000ee1e  push    rbp
0x18000ee1f  lea     rbp, [rsp-57h]
0x18000ee24  sub     rsp, 0E0h
0x18000ee2b  mov     rax, cs:__security_cookie
0x18000ee32  xor     rax, rsp
0x18000ee35  mov     [rbp+57h+var_10], rax
0x18000ee39  mov     rbx, rdx
0x18000ee3c  mov     rdi, rcx
0x18000ee3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee46  lea     rax, WPP_GLOBAL_Control
0x18000ee4d  cmp     rcx, rax
0x18000ee50  jz      short loc_18000EE70
0x18000ee52  test    dword ptr [rcx+1Ch], 20000000h
0x18000ee59  jz      short loc_18000EE70
0x18000ee5b  mov     rcx, [rcx+10h]
0x18000ee5f  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18000ee66  mov     edx, 14h
0x18000ee6b  call    WPP_SF_
0x18000ee70  mov     r8d, 234h; unsigned __int16
0x18000ee76  lea     rdx, aSxgetsidfromto; "SxGetSidFromToken"
0x18000ee7d  lea     rcx, [rbp+57h+var_A8]; this
0x18000ee81  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000ee86  xor     edx, edx; Val
0x18000ee88  lea     rcx, [rbp+57h+TokenInformation]; void *
0x18000ee8c  lea     r8d, [rdx+58h]; Size
0x18000ee90  call    memset_0
0x18000ee95  mov     [rbp+57h+var_B0], 0
0x18000ee9c  mov     eax, 23Ah
0x18000eea1  test    rbx, rbx
0x18000eea4  jnz     short loc_18000EEB4
0x18000eea6  mov     ebx, 80070057h
0x18000eeab  mov     [rbp+57h+var_A2], ax
0x18000eeaf  jmp     loc_18000EF3A
0x18000eeb4  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18000eeba  mov     [rbp+57h+var_A4], ax
0x18000eebe  lea     rax, [rbp+57h+var_B0]
0x18000eec2  mov     [rbp+57h+var_A8], 0
0x18000eec9  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18000eecd  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18000eed2  mov     rcx, rdi; TokenHandle
0x18000eed5  lea     edx, [r9-57h]; TokenInformationClass
0x18000eed9  call    cs:__imp_GetTokenInformation
0x18000eedf  test    eax, eax
0x18000eee1  jnz     short loc_18000EEF8
0x18000eee3  call    GetLastFailureAsHRESULT
0x18000eee8  mov     ebx, eax
0x18000eeea  mov     [rbp+57h+var_A8], eax
0x18000eeed  mov     eax, 23Dh
0x18000eef2  mov     [rbp+57h+var_A2], ax
0x18000eef6  jmp     short loc_18000EF3D
0x18000eef8  mov     r8, [rbp+57h+TokenInformation]; pSourceSid
0x18000eefc  mov     eax, 23Dh
0x18000ef01  mov     rdx, rbx; pDestinationSid
0x18000ef04  mov     [rbp+57h+var_A4], ax
0x18000ef08  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18000ef0d  mov     [rbp+57h+var_A8], 0
0x18000ef14  call    cs:__imp_CopySid
0x18000ef1a  test    eax, eax
0x18000ef1c  jnz     short loc_18000EF2F
0x18000ef1e  call    GetLastFailureAsHRESULT
0x18000ef23  mov     ebx, eax
0x18000ef25  mov     [rbp+57h+var_A8], eax
0x18000ef28  mov     eax, 23Fh
0x18000ef2d  jmp     short loc_18000EEF2
0x18000ef2f  mov     eax, 23Fh
0x18000ef34  xor     ebx, ebx
0x18000ef36  mov     [rbp+57h+var_A4], ax
0x18000ef3a  mov     [rbp+57h+var_A8], ebx
0x18000ef3d  lea     rcx, [rbp+57h+var_A8]; this
0x18000ef41  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000ef46  mov     eax, ebx
0x18000ef48  mov     rcx, [rbp+57h+var_10]
0x18000ef4c  xor     rcx, rsp; StackCookie
0x18000ef4f  call    __security_check_cookie
0x18000ef54  lea     r11, [rsp+0E0h+var_s0]
0x18000ef5c  mov     rbx, [r11+20h]
0x18000ef60  mov     rdi, [r11+28h]
0x18000ef64  mov     rsp, r11
0x18000ef67  pop     rbp
0x18000ef68  retn
```
