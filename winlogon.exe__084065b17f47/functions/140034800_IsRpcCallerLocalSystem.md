# IsRpcCallerLocalSystem

- ea: `0x140034800`
- end: `0x1400349fc`
- name: `IsRpcCallerLocalSystem`
- size: `508`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400347e0`

## callees

- `0x1400057f4`
- `0x140034800`
- `0x14003cb6c`
- `0x140041c34`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140034897`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140034897`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x140034826`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x140034826`
- `RPCRT4!RpcRevertToSelf` at `0x1400349af`
- `RPCRT4!RpcRevertToSelf` at `0x14009e3af`
- `RPCRT4!RpcRevertToSelf` at `0x1400349af`
- `RPCRT4!RpcRevertToSelf` at `0x14009e3af`
- `RPCRT4!RpcImpersonateClient` at `0x140034872`
- `RPCRT4!RpcImpersonateClient` at `0x140034872`

## pseudocode

```c
__int64 IsRpcCallerLocalSystem()
{
  int v0; // ebx
  unsigned int IsClientLocal; // eax
  __int64 v2; // r9
  CUser *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  const char *v6; // r9
  __int64 v7; // r9
  WINBOOL IsMember; // [rsp+40h] [rbp+8h] BYREF
  unsigned int ClientLocalFlag; // [rsp+48h] [rbp+10h] BYREF

  ClientLocalFlag = 0;
  IsMember = 0;
  v0 = 0;
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  if ( IsClientLocal )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 12;
LABEL_15:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_809920f00406303c4ef054ac00db20a5_Traceguids, IsClientLocal);
    }
  }
  else if ( ClientLocalFlag )
  {
    IsClientLocal = RpcImpersonateClient(0);
    if ( IsClientLocal )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v4 = 14;
        goto LABEL_15;
      }
    }
    else
    {
      v0 = 1;
      if ( CheckTokenMembership(0, &qword_1400ABD00, &IsMember) )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = "TRUE";
          if ( !IsMember )
            v6 = "FALSE";
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_809920f00406303c4ef054ac00db20a5_Traceguids, v6);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_809920f00406303c4ef054ac00db20a5_Traceguids, v5);
        }
        IsMember = 0;
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_809920f00406303c4ef054ac00db20a5_Traceguids, v2);
  }
  if ( v0
    && RpcRevertToSelf()
    && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_809920f00406303c4ef054ac00db20a5_Traceguids, v7);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x140034800  mov     [rsp+arg_10], rbx
0x140034805  mov     [rsp+arg_18], rsi
0x14003480a  push    rdi
0x14003480b  sub     rsp, 30h
0x14003480f  xor     esi, esi
0x140034811  mov     [rsp+38h+ClientLocalFlag], esi
0x140034815  mov     [rsp+38h+IsMember], esi
0x140034819  mov     ebx, esi
0x14003481b  mov     [rsp+38h+var_18], ebx
0x14003481f  lea     rdx, [rsp+38h+ClientLocalFlag]; ClientLocalFlag
0x140034824  xor     ecx, ecx; BindingHandle
0x140034826  call    cs:__imp_I_RpcBindingIsClientLocal
0x14003482c  test    eax, eax
0x14003482e  jz      short loc_140034865
0x140034830  lea     rdi, WPP_GLOBAL_Control
0x140034837  mov     rcx, cs:WPP_GLOBAL_Control
0x14003483e  cmp     rcx, rdi
0x140034841  jz      loc_1400349AB
0x140034847  test    byte ptr [rcx+1Ch], 1
0x14003484b  jz      loc_1400349AB
0x140034851  cmp     byte ptr [rcx+19h], 2
0x140034855  jb      loc_1400349AB
0x14003485b  mov     edx, 0Ch
0x140034860  jmp     loc_140034905
0x140034865  cmp     [rsp+38h+ClientLocalFlag], 0
0x14003486a  jz      loc_14003491D
0x140034870  xor     ecx, ecx; BindingHandle
0x140034872  call    cs:__imp_RpcImpersonateClient
0x140034878  test    eax, eax
0x14003487a  jnz     loc_140034953
0x140034880  mov     ebx, 1
0x140034885  mov     [rsp+38h+var_18], ebx
0x140034889  lea     r8, [rsp+38h+IsMember]; IsMember
0x14003488e  lea     rdx, qword_1400ABD00; SidToCheck
0x140034895  xor     ecx, ecx; TokenHandle
0x140034897  call    cs:__imp_CheckTokenMembership
0x14003489d  test    eax, eax
0x14003489f  jz      loc_140034974
0x1400348a5  lea     rdi, WPP_GLOBAL_Control
0x1400348ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400348b3  cmp     rcx, rdi
0x1400348b6  jz      loc_1400349AB
0x1400348bc  test    [rcx+1Ch], bl
0x1400348bf  jz      loc_1400349AB
0x1400348c5  cmp     byte ptr [rcx+19h], 2
0x1400348c9  jb      loc_1400349AB
0x1400348cf  lea     r9, aTrue_0; "TRUE"
0x1400348d6  lea     rax, aFalse; "FALSE"
0x1400348dd  cmp     [rsp+38h+IsMember], 0
0x1400348e2  cmovz   r9, rax
0x1400348e6  mov     edx, 10h
0x1400348eb  lea     r8, WPP_809920f00406303c4ef054ac00db20a5_Traceguids
0x1400348f2  mov     rcx, [rcx+10h]
0x1400348f6  call    WPP_SF_s
0x1400348fb  jmp     loc_1400349AB
0x140034900  mov     edx, 0Eh
0x140034905  mov     r9d, eax
0x140034908  lea     r8, WPP_809920f00406303c4ef054ac00db20a5_Traceguids
0x14003490f  mov     rcx, [rcx+10h]
0x140034913  call    WPP_SF_d
0x140034918  jmp     loc_1400349AB
0x14003491d  lea     rdi, WPP_GLOBAL_Control
0x140034924  mov     rcx, cs:WPP_GLOBAL_Control
0x14003492b  cmp     rcx, rdi
0x14003492e  jz      short loc_1400349AB
0x140034930  test    byte ptr [rcx+1Ch], 1
0x140034934  jz      short loc_1400349AB
0x140034936  cmp     byte ptr [rcx+19h], 2
0x14003493a  jb      short loc_1400349AB
0x14003493c  mov     edx, 0Dh
0x140034941  lea     r8, WPP_809920f00406303c4ef054ac00db20a5_Traceguids
0x140034948  mov     rcx, [rcx+10h]
0x14003494c  call    WPP_SF_
0x140034951  jmp     short loc_1400349AB
0x140034953  lea     rdi, WPP_GLOBAL_Control
0x14003495a  mov     rcx, cs:WPP_GLOBAL_Control
0x140034961  cmp     rcx, rdi
0x140034964  jz      short loc_1400349AB
0x140034966  test    byte ptr [rcx+1Ch], 1
0x14003496a  jz      short loc_1400349AB
0x14003496c  cmp     byte ptr [rcx+19h], 2
0x140034970  jb      short loc_1400349AB
0x140034972  jmp     short loc_140034900
0x140034974  lea     rdi, WPP_GLOBAL_Control
0x14003497b  mov     rcx, cs:WPP_GLOBAL_Control
0x140034982  cmp     rcx, rdi
0x140034985  jz      short loc_1400349A7
0x140034987  test    [rcx+1Ch], bl
0x14003498a  jz      short loc_1400349A7
0x14003498c  cmp     byte ptr [rcx+19h], 2
0x140034990  jb      short loc_1400349A7
0x140034992  mov     edx, 0Fh
0x140034997  lea     r8, WPP_809920f00406303c4ef054ac00db20a5_Traceguids
0x14003499e  mov     rcx, [rcx+10h]
0x1400349a2  call    WPP_SF_
0x1400349a7  mov     [rsp+38h+IsMember], esi
0x1400349ab  test    ebx, ebx
0x1400349ad  jz      short loc_1400349B9
0x1400349af  call    cs:__imp_RpcRevertToSelf
0x1400349b5  test    eax, eax
0x1400349b7  jnz     short loc_1400349CD
0x1400349b9  mov     eax, [rsp+38h+IsMember]
0x1400349bd  mov     rbx, [rsp+38h+arg_10]
0x1400349c2  mov     rsi, [rsp+38h+arg_18]
0x1400349c7  add     rsp, 30h
0x1400349cb  pop     rdi
0x1400349cc  retn
0x1400349cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400349d4  cmp     rcx, rdi
0x1400349d7  jz      short loc_1400349B9
0x1400349d9  test    byte ptr [rcx+1Ch], 1
0x1400349dd  jz      short loc_1400349B9
0x1400349df  cmp     byte ptr [rcx+19h], 2
0x1400349e3  jb      short loc_1400349B9
0x1400349e5  mov     edx, 11h
0x1400349ea  lea     r8, WPP_809920f00406303c4ef054ac00db20a5_Traceguids
0x1400349f1  mov     rcx, [rcx+10h]
0x1400349f5  call    WPP_SF_
0x1400349fa  jmp     short loc_1400349B9
0x14009e3a0  push    rbp
0x14009e3a2  sub     rsp, 20h
0x14009e3a6  mov     rbp, rdx
0x14009e3a9  cmp     dword ptr [rbp+20h], 0
0x14009e3ad  jz      short loc_14009E3EE
0x14009e3af  call    cs:__imp_RpcRevertToSelf
0x14009e3b5  test    eax, eax
0x14009e3b7  jz      short loc_14009E3EE
0x14009e3b9  lea     rax, WPP_GLOBAL_Control
0x14009e3c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14009e3c7  cmp     rcx, rax
0x14009e3ca  jz      short loc_14009E3EE
0x14009e3cc  test    byte ptr [rcx+1Ch], 1
0x14009e3d0  jz      short loc_14009E3EE
0x14009e3d2  cmp     byte ptr [rcx+19h], 2
0x14009e3d6  jb      short loc_14009E3EE
0x14009e3d8  mov     edx, 11h
0x14009e3dd  lea     r8, WPP_809920f00406303c4ef054ac00db20a5_Traceguids
0x14009e3e4  mov     rcx, [rcx+10h]
0x14009e3e8  call    WPP_SF_
0x14009e3ed  nop
0x14009e3ee  add     rsp, 20h
0x14009e3f2  pop     rbp
0x14009e3f3  retn
```
