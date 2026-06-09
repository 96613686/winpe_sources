# UbpmDeriveToken

- ea: `0x1800275bc`
- end: `0x180027765`
- name: `UbpmDeriveToken`
- size: `425`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001eaf4`

## callees

- `0x1800275bc`
- `0x18002776c`
- `0x1800351ec`
- `0x180036c60`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18002760c`
- `ntdll!NtQueryInformationToken` at `0x1800276b8`
- `ntdll!NtQueryInformationToken` at `0x18002760c`
- `ntdll!NtQueryInformationToken` at `0x1800276b8`
- `ntdll!RtlNtStatusToDosError` at `0x18002766f`
- `ntdll!RtlNtStatusToDosError` at `0x180027719`
- `ntdll!RtlNtStatusToDosError` at `0x18002766f`
- `ntdll!RtlNtStatusToDosError` at `0x180027719`

## pseudocode

```c
__int64 __fastcall UbpmDeriveToken(HANDLE ExistingTokenHandle, int a2, void **a3)
{
  int v6; // eax
  int v7; // edi
  ULONG v8; // ebx
  NTSTATUS v10; // eax
  ULONG v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  _DWORD v14[10]; // [rsp+30h] [rbp-28h] BYREF
  int TokenInformation; // [rsp+70h] [rbp+18h] BYREF
  ULONG ReturnLength; // [rsp+78h] [rbp+20h] BYREF

  ReturnLength = 0;
  v14[0] = 0;
  TokenInformation = 1;
  *a3 = 0;
  v6 = NtQueryInformationToken(ExistingTokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( v6 < 0 )
    goto LABEL_18;
  if ( TokenInformation != 2 )
  {
    v7 = 0;
    if ( TokenInformation != 1 )
      goto LABEL_4;
    v6 = NtQueryInformationToken(ExistingTokenHandle, TokenElevation, v14, 4u, &ReturnLength);
    if ( v6 >= 0 )
    {
      if ( !v14[0] )
        goto LABEL_4;
      goto LABEL_14;
    }
LABEL_18:
    v11 = RtlNtStatusToDosError(v6);
    v8 = v11;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v8;
    v13 = 56;
LABEL_21:
    WPP_SF_d(v12[2], v13, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, v11);
    return v8;
  }
LABEL_14:
  v7 = 1;
LABEL_4:
  v8 = 0;
  if ( a2 == 1 )
  {
    if ( v7 )
      return v8;
    v10 = LUAGetElevatedToken(ExistingTokenHandle, a3);
    if ( v10 >= 0 )
      return v8;
    v11 = RtlNtStatusToDosError(v10);
    v8 = v11;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v8;
    v13 = 57;
    goto LABEL_21;
  }
  if ( v7 == 1 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_134408c016563692a0776b6ad2359b4f_Traceguids);
  return v8;
}

```

## disassembly

```asm
0x1800275bc  mov     rax, rsp
0x1800275bf  mov     [rax+8], rbx
0x1800275c3  mov     [rax+10h], rbp
0x1800275c7  push    rsi
0x1800275c8  push    rdi
0x1800275c9  push    r14
0x1800275cb  sub     rsp, 40h
0x1800275cf  mov     ebx, 4
0x1800275d4  mov     dword ptr [rax+20h], 0
0x1800275db  mov     dword ptr [rax-28h], 0
0x1800275e2  mov     r14, r8
0x1800275e5  mov     dword ptr [rax+18h], 1
0x1800275ec  lea     rax, [rax+20h]
0x1800275f0  mov     ebp, edx
0x1800275f2  mov     qword ptr [r8], 0
0x1800275f9  lea     edx, [rbx+0Eh]; TokenInformationClass
0x1800275fc  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180027601  mov     r9d, ebx; TokenInformationLength
0x180027604  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x180027609  mov     rsi, rcx
0x18002760c  call    cs:__imp_NtQueryInformationToken
0x180027613  nop     dword ptr [rax+rax+00h]
0x180027618  test    eax, eax
0x18002761a  js      loc_180027717
0x180027620  cmp     [rsp+58h+TokenInformation], 2
0x180027625  jz      loc_1800276D2
0x18002762b  xor     edi, edi
0x18002762d  cmp     [rsp+58h+TokenInformation], 1
0x180027632  jz      short loc_18002769E
0x180027634  xor     ebx, ebx
0x180027636  cmp     ebp, 1
0x180027639  jz      short loc_18002765A
0x18002763b  cmp     edi, 1
0x18002763e  jz      loc_1800276DC
0x180027644  mov     rbp, [rsp+58h+arg_8]
0x180027649  mov     eax, ebx
0x18002764b  mov     rbx, [rsp+58h+arg_0]
0x180027650  add     rsp, 40h
0x180027654  pop     r14
0x180027656  pop     rdi
0x180027657  pop     rsi
0x180027658  retn
0x18002765a  test    edi, edi
0x18002765c  jnz     short loc_180027644
0x18002765e  mov     rdx, r14; NewTokenHandle
0x180027661  mov     rcx, rsi; ExistingTokenHandle
0x180027664  call    LUAGetElevatedToken
0x180027669  test    eax, eax
0x18002766b  jns     short loc_180027644
0x18002766d  mov     ecx, eax; Status
0x18002766f  call    cs:__imp_RtlNtStatusToDosError
0x180027676  nop     dword ptr [rax+rax+00h]
0x18002767b  mov     ebx, eax
0x18002767d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027684  lea     rdx, WPP_GLOBAL_Control
0x18002768b  cmp     rcx, rdx
0x18002768e  jz      short loc_180027644
0x180027690  test    byte ptr [rcx+1Ch], 1
0x180027694  jz      short loc_180027644
0x180027696  lea     edx, [rdi+39h]
0x180027699  jmp     loc_18002774D
0x18002769e  lea     rax, [rsp+58h+arg_18]
0x1800276a3  mov     r9d, ebx; TokenInformationLength
0x1800276a6  lea     r8, [rsp+58h+var_28]; TokenInformation
0x1800276ab  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800276b0  mov     edx, 14h; TokenInformationClass
0x1800276b5  mov     rcx, rsi; TokenHandle
0x1800276b8  call    cs:__imp_NtQueryInformationToken
0x1800276bf  nop     dword ptr [rax+rax+00h]
0x1800276c4  test    eax, eax
0x1800276c6  js      short loc_180027717
0x1800276c8  cmp     [rsp+58h+var_28], edi
0x1800276cc  jz      loc_180027634
0x1800276d2  mov     edi, 1
0x1800276d7  jmp     loc_180027634
0x1800276dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800276e3  lea     rdx, WPP_GLOBAL_Control
0x1800276ea  cmp     rcx, rdx
0x1800276ed  jz      loc_180027644
0x1800276f3  test    byte ptr [rcx+1Ch], 2
0x1800276f7  jz      loc_180027644
0x1800276fd  mov     rcx, [rcx+10h]
0x180027701  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180027708  mov     edx, 3Bh ; ';'
0x18002770d  call    WPP_SF_
0x180027712  jmp     loc_180027644
0x180027717  mov     ecx, eax; Status
0x180027719  call    cs:__imp_RtlNtStatusToDosError
0x180027720  nop     dword ptr [rax+rax+00h]
0x180027725  mov     ebx, eax
0x180027727  mov     rcx, cs:WPP_GLOBAL_Control
0x18002772e  lea     rdx, WPP_GLOBAL_Control
0x180027735  cmp     rcx, rdx
0x180027738  jz      loc_180027644
0x18002773e  test    byte ptr [rcx+1Ch], 1
0x180027742  jz      loc_180027644
0x180027748  mov     edx, 38h ; '8'
0x18002774d  mov     rcx, [rcx+10h]
0x180027751  lea     r8, WPP_134408c016563692a0776b6ad2359b4f_Traceguids
0x180027758  mov     r9d, eax
0x18002775b  call    WPP_SF_d
0x180027760  jmp     loc_180027644
```
