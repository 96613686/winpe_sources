# SxGetSidFromToken(void *,_SID *,ulong)

- ea: `0x18002cac4`
- end: `0x18002cc1f`
- name: `?SxGetSidFromToken@@YAJPEAXPEAU_SID@@K@Z`
- size: `347`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID pDestinationSid, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c5a4`

## callees

- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002cac4`
- `0x18002d6e8`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002cb8f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002cb8f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002cbca`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002cbca`

## string_xrefs

- `0x18002cb26`: `SxGetSidFromToken`

## pseudocode

```c
__int64 __fastcall SxGetSidFromToken(HANDLE TokenHandle, PSID pDestinationSid)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int LastFailureAsHRESULT; // ebx
  __int64 v7; // rcx
  __int16 v8; // ax
  __int64 v9; // rcx
  DWORD ReturnLength; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v12; // [rsp+38h] [rbp-51h] BYREF
  __int16 v13; // [rsp+3Ch] [rbp-4Dh]
  __int16 v14; // [rsp+3Eh] [rbp-4Bh]
  PSID TokenInformation[12]; // [rsp+70h] [rbp-19h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "SxGetSidFromToken", 564, 1);
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  if ( !pDestinationSid )
  {
    LastFailureAsHRESULT = -2147024809;
    v14 = 570;
LABEL_12:
    v12 = LastFailureAsHRESULT;
    goto LABEL_13;
  }
  v13 = 570;
  v12 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
  {
    v13 = 573;
    v12 = 0;
    if ( CopySid(0x44u, pDestinationSid, TokenInformation[0]) )
    {
      LastFailureAsHRESULT = 0;
      v13 = 575;
      goto LABEL_12;
    }
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
    v12 = LastFailureAsHRESULT;
    v8 = 575;
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
    v12 = LastFailureAsHRESULT;
    v8 = 573;
  }
  v14 = v8;
LABEL_13:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12, v4, v5);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18002cac4  mov     [rsp-8+arg_10], rbx
0x18002cac9  mov     [rsp-8+arg_18], rdi
0x18002cace  push    rbp
0x18002cacf  lea     rbp, [rsp-57h]
0x18002cad4  sub     rsp, 0E0h
0x18002cadb  mov     rax, cs:__security_cookie
0x18002cae2  xor     rax, rsp
0x18002cae5  mov     [rbp+57h+var_10], rax
0x18002cae9  mov     rbx, rdx
0x18002caec  mov     rdi, rcx
0x18002caef  mov     rcx, cs:WPP_GLOBAL_Control
0x18002caf6  lea     rax, WPP_GLOBAL_Control
0x18002cafd  cmp     rcx, rax
0x18002cb00  jz      short loc_18002CB20
0x18002cb02  test    dword ptr [rcx+1Ch], 20000000h
0x18002cb09  jz      short loc_18002CB20
0x18002cb0b  mov     rcx, [rcx+10h]
0x18002cb0f  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18002cb16  mov     edx, 14h
0x18002cb1b  call    WPP_SF_
0x18002cb20  mov     r9d, 1; unsigned __int16
0x18002cb26  lea     rdx, aSxgetsidfromto; "SxGetSidFromToken"
0x18002cb2d  mov     r8d, 234h; unsigned __int16
0x18002cb33  lea     rcx, [rbp+57h+var_A8]; this
0x18002cb37  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002cb3c  xor     edx, edx; Val
0x18002cb3e  lea     rcx, [rbp+57h+TokenInformation]; void *
0x18002cb42  lea     r8d, [rdx+58h]; Size
0x18002cb46  call    memset_0
0x18002cb4b  mov     [rbp+57h+var_B0], 0
0x18002cb52  mov     eax, 23Ah
0x18002cb57  test    rbx, rbx
0x18002cb5a  jnz     short loc_18002CB6A
0x18002cb5c  mov     ebx, 80070057h
0x18002cb61  mov     [rbp+57h+var_A2], ax
0x18002cb65  jmp     loc_18002CBF0
0x18002cb6a  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18002cb70  mov     [rbp+57h+var_A4], ax
0x18002cb74  lea     rax, [rbp+57h+var_B0]
0x18002cb78  mov     [rbp+57h+var_A8], 0
0x18002cb7f  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18002cb83  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18002cb88  mov     rcx, rdi; TokenHandle
0x18002cb8b  lea     edx, [r9-57h]; TokenInformationClass
0x18002cb8f  call    cs:__imp_GetTokenInformation
0x18002cb95  test    eax, eax
0x18002cb97  jnz     short loc_18002CBAE
0x18002cb99  call    GetLastFailureAsHRESULT
0x18002cb9e  mov     ebx, eax
0x18002cba0  mov     [rbp+57h+var_A8], eax
0x18002cba3  mov     eax, 23Dh
0x18002cba8  mov     [rbp+57h+var_A2], ax
0x18002cbac  jmp     short loc_18002CBF3
0x18002cbae  mov     r8, [rbp+57h+TokenInformation]; pSourceSid
0x18002cbb2  mov     eax, 23Dh
0x18002cbb7  mov     rdx, rbx; pDestinationSid
0x18002cbba  mov     [rbp+57h+var_A4], ax
0x18002cbbe  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x18002cbc3  mov     [rbp+57h+var_A8], 0
0x18002cbca  call    cs:__imp_CopySid
0x18002cbd0  test    eax, eax
0x18002cbd2  jnz     short loc_18002CBE5
0x18002cbd4  call    GetLastFailureAsHRESULT
0x18002cbd9  mov     ebx, eax
0x18002cbdb  mov     [rbp+57h+var_A8], eax
0x18002cbde  mov     eax, 23Fh
0x18002cbe3  jmp     short loc_18002CBA8
0x18002cbe5  mov     eax, 23Fh
0x18002cbea  xor     ebx, ebx
0x18002cbec  mov     [rbp+57h+var_A4], ax
0x18002cbf0  mov     [rbp+57h+var_A8], ebx
0x18002cbf3  lea     rcx, [rbp+57h+var_A8]; this
0x18002cbf7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002cbfc  mov     eax, ebx
0x18002cbfe  mov     rcx, [rbp+57h+var_10]
0x18002cc02  xor     rcx, rsp; StackCookie
0x18002cc05  call    __security_check_cookie
0x18002cc0a  lea     r11, [rsp+0E0h+var_s0]
0x18002cc12  mov     rbx, [r11+20h]
0x18002cc16  mov     rdi, [r11+28h]
0x18002cc1a  mov     rsp, r11
0x18002cc1d  pop     rbp
0x18002cc1e  retn
```
