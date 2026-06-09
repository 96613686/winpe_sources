# HrUnregisterWizardComponentLinks(_GUID const *)

- ea: `0x18000a768`
- end: `0x18000a942`
- name: `?HrUnregisterWizardComponentLinks@@YAJPEBU_GUID@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009ca0`

## callees

- `0x180007820`
- `0x18000a168`
- `0x18000a768`
- `0x18000aa70`
- `0x180010dcc`
- `0x180012800`

## pseudocode

```c
__int64 __fastcall HrUnregisterWizardComponentLinks(GUID *rguid, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // ebx
  PVOID *v6; // rcx
  int v7; // eax
  int v8; // eax
  unsigned int v9; // edi
  unsigned int v11; // [rsp+30h] [rbp-20h] BYREF
  GUID rguida; // [rsp+38h] [rbp-18h] BYREF

  rguida = 0;
  v5 = 0;
LABEL_2:
  v6 = (PVOID *)WPP_GLOBAL_Control;
  while ( 1 )
  {
    if ( v5 < 0 )
      goto LABEL_24;
    v11 = 0;
    v7 = HrNextWizardComponent(rguid, a2, 1, a4, &v11, &rguida);
    v5 = v7;
    if ( !v7 )
    {
      v5 = HrUnregisterWizardComponentLink(&rguida, rguid);
      goto LABEL_2;
    }
    if ( v7 == 1 )
      break;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, v11, v7);
      goto LABEL_2;
    }
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, v11, 1);
LABEL_13:
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  while ( 1 )
  {
LABEL_14:
    if ( v5 < 0 )
      goto LABEL_24;
    v11 = 0;
    v8 = HrNextWizardComponent(rguid, a2, 2, a4, &v11, &rguida);
    v5 = v8;
    if ( !v8 )
    {
      v5 = HrUnregisterWizardComponentLink(rguid, &rguida);
      goto LABEL_13;
    }
    if ( v8 == 1 )
      break;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, v11, v8);
      goto LABEL_13;
    }
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, v11, 1);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_24:
  v9 = 0;
  if ( v5 != 1 )
    v9 = v5;
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
    WPP_SF_D(v6[2], 71, &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18000a768  mov     [rsp-18h+arg_8], rbx
0x18000a76d  mov     [rsp-18h+arg_10], rdi
0x18000a772  push    rbp
0x18000a773  push    r12
0x18000a775  push    r14
0x18000a777  mov     rbp, rsp
0x18000a77a  sub     rsp, 50h
0x18000a77e  mov     rax, cs:__security_cookie
0x18000a785  xor     rax, rsp
0x18000a788  mov     [rbp+var_8], rax
0x18000a78c  xorps   xmm0, xmm0
0x18000a78f  lea     r14, WPP_GLOBAL_Control
0x18000a796  movups  xmmword ptr [rbp+rguid.Data1], xmm0
0x18000a79a  mov     rdi, rcx
0x18000a79d  lea     r12, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x18000a7a4  xor     ebx, ebx
0x18000a7a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7ad  test    ebx, ebx
0x18000a7af  js      loc_18000A8F7
0x18000a7b5  lea     rax, [rbp+rguid]
0x18000a7b9  mov     [rbp+var_20], 0
0x18000a7c0  mov     [rsp+50h+var_28], rax
0x18000a7c5  mov     r8d, 1
0x18000a7cb  lea     rax, [rbp+var_20]
0x18000a7cf  mov     rcx, rdi
0x18000a7d2  mov     [rsp+50h+var_30], rax
0x18000a7d7  call    ?HrNextWizardComponent@@YAJPEBU_GUID@@W4tagXW_COMPONENT_TYPE@@W4tagXW_COMPONENT_HIERARCHY@@KQEAKPEAU1@@Z; HrNextWizardComponent(_GUID const *,tagXW_COMPONENT_TYPE,tagXW_COMPONENT_HIERARCHY,ulong,ulong * const,_GUID *)
0x18000a7dc  mov     ebx, eax
0x18000a7de  test    eax, eax
0x18000a7e0  jnz     short loc_18000A7F2
0x18000a7e2  mov     rdx, rdi; GUID *
0x18000a7e5  lea     rcx, [rbp+rguid]; rguid
0x18000a7e9  call    ?HrUnregisterWizardComponentLink@@YAJPEBU_GUID@@0@Z; HrUnregisterWizardComponentLink(_GUID const *,_GUID const *)
0x18000a7ee  mov     ebx, eax
0x18000a7f0  jmp     short loc_18000A7A6
0x18000a7f2  cmp     eax, 1
0x18000a7f5  jz      short loc_18000A824
0x18000a7f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7fe  cmp     rcx, r14
0x18000a801  jz      short loc_18000A7AD
0x18000a803  test    byte ptr [rcx+1Ch], 4
0x18000a807  jz      short loc_18000A7AD
0x18000a809  mov     r9d, [rbp+var_20]
0x18000a80d  mov     edx, 44h ; 'D'
0x18000a812  mov     rcx, [rcx+10h]
0x18000a816  mov     r8, r12
0x18000a819  mov     dword ptr [rsp+50h+var_30], eax
0x18000a81d  call    WPP_SF_DD
0x18000a822  jmp     short loc_18000A7A6
0x18000a824  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a82b  cmp     rcx, r14
0x18000a82e  jz      short loc_18000A85A
0x18000a830  test    byte ptr [rcx+1Ch], 10h
0x18000a834  jz      short loc_18000A85A
0x18000a836  mov     edx, 43h ; 'C'
0x18000a83b  mov     dword ptr [rsp+50h+var_30], 1
0x18000a843  mov     r9d, [rbp+var_20]
0x18000a847  mov     r8, r12
0x18000a84a  mov     rcx, [rcx+10h]
0x18000a84e  call    WPP_SF_DD
0x18000a853  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a85a  test    ebx, ebx
0x18000a85c  js      loc_18000A8F7
0x18000a862  lea     rax, [rbp+rguid]
0x18000a866  mov     [rbp+var_20], 0
0x18000a86d  mov     [rsp+50h+var_28], rax
0x18000a872  mov     r8d, 2
0x18000a878  lea     rax, [rbp+var_20]
0x18000a87c  mov     rcx, rdi
0x18000a87f  mov     [rsp+50h+var_30], rax
0x18000a884  call    ?HrNextWizardComponent@@YAJPEBU_GUID@@W4tagXW_COMPONENT_TYPE@@W4tagXW_COMPONENT_HIERARCHY@@KQEAKPEAU1@@Z; HrNextWizardComponent(_GUID const *,tagXW_COMPONENT_TYPE,tagXW_COMPONENT_HIERARCHY,ulong,ulong * const,_GUID *)
0x18000a889  mov     ebx, eax
0x18000a88b  test    eax, eax
0x18000a88d  jnz     short loc_18000A89F
0x18000a88f  lea     rdx, [rbp+rguid]; GUID *
0x18000a893  mov     rcx, rdi; rguid
0x18000a896  call    ?HrUnregisterWizardComponentLink@@YAJPEBU_GUID@@0@Z; HrUnregisterWizardComponentLink(_GUID const *,_GUID const *)
0x18000a89b  mov     ebx, eax
0x18000a89d  jmp     short loc_18000A853
0x18000a89f  cmp     eax, 1
0x18000a8a2  jz      short loc_18000A8C1
0x18000a8a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8ab  cmp     rcx, r14
0x18000a8ae  jz      short loc_18000A85A
0x18000a8b0  test    byte ptr [rcx+1Ch], 4
0x18000a8b4  jz      short loc_18000A85A
0x18000a8b6  mov     edx, 46h ; 'F'
0x18000a8bb  mov     dword ptr [rsp+50h+var_30], eax
0x18000a8bf  jmp     short loc_18000A843
0x18000a8c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8c8  cmp     rcx, r14
0x18000a8cb  jz      short loc_18000A8F7
0x18000a8cd  test    byte ptr [rcx+1Ch], 10h
0x18000a8d1  jz      short loc_18000A8F7
0x18000a8d3  mov     r9d, [rbp+var_20]
0x18000a8d7  mov     edx, 45h ; 'E'
0x18000a8dc  mov     rcx, [rcx+10h]
0x18000a8e0  mov     r8, r12
0x18000a8e3  mov     dword ptr [rsp+50h+var_30], 1
0x18000a8eb  call    WPP_SF_DD
0x18000a8f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8f7  xor     edi, edi
0x18000a8f9  cmp     ebx, 1
0x18000a8fc  cmovnz  edi, ebx
0x18000a8ff  cmp     rcx, r14
0x18000a902  jz      short loc_18000A91E
0x18000a904  test    byte ptr [rcx+1Ch], 10h
0x18000a908  jz      short loc_18000A91E
0x18000a90a  mov     rcx, [rcx+10h]
0x18000a90e  mov     edx, 47h ; 'G'
0x18000a913  mov     r9d, edi
0x18000a916  mov     r8, r12
0x18000a919  call    WPP_SF_D
0x18000a91e  mov     eax, edi
0x18000a920  mov     rcx, [rbp+var_8]
0x18000a924  xor     rcx, rsp; StackCookie
0x18000a927  call    __security_check_cookie
0x18000a92c  lea     r11, [rsp+50h+var_s0]
0x18000a931  mov     rbx, [r11+28h]
0x18000a935  mov     rdi, [r11+30h]
0x18000a939  mov     rsp, r11
0x18000a93c  pop     r14
0x18000a93e  pop     r12
0x18000a940  pop     rbp
0x18000a941  retn
```
