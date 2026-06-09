# BuildRpcBinding(_NOTIFICATION_COMPONENT *)

- ea: `0x140026590`
- end: `0x14002695d`
- name: `?BuildRpcBinding@@YAKPEAU_NOTIFICATION_COMPONENT@@@Z`
- size: `973`
- prototype: `unsigned int __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140025d50`

## callees

- `0x1400057f4`
- `0x140026590`
- `0x140053720`
- `0x14005f3c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__tolower` at `0x140026813`
- `api-ms-win-crt-private-l1-1-0!_o__tolower` at `0x140026813`
- `api-ms-win-crt-private-l1-1-0!_o_isupper` at `0x14002672a`
- `api-ms-win-crt-private-l1-1-0!_o_isupper` at `0x14002672a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1400266e1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1400266e1`
- `RPCRT4!NdrClientCall3` at `0x14002683d`
- `RPCRT4!NdrClientCall3` at `0x14002683d`
- `RPCRT4!RpcBindingUnbind` at `0x140026955`
- `RPCRT4!RpcBindingUnbind` at `0x14009de77`
- `RPCRT4!RpcBindingUnbind` at `0x140026955`
- `RPCRT4!RpcBindingUnbind` at `0x14009de77`
- `RPCRT4!RpcBindingFree` at `0x140026946`
- `RPCRT4!RpcBindingFree` at `0x14009de85`
- `RPCRT4!RpcBindingFree` at `0x140026946`
- `RPCRT4!RpcBindingFree` at `0x14009de85`
- `RPCRT4!I_RpcExceptionFilter` at `0x14009de3e`
- `RPCRT4!I_RpcExceptionFilter` at `0x14009de3e`
- `RPCRT4!RpcBindingBind` at `0x1400267c3`
- `RPCRT4!RpcBindingBind` at `0x1400267c3`
- `RPCRT4!RpcBindingCreateW` at `0x1400267a3`
- `RPCRT4!RpcBindingCreateW` at `0x1400267a3`
- `ntdll!__isascii` at `0x14002671d`
- `ntdll!__isascii` at `0x14002671d`

## pseudocode

```c
__int64 __fastcall BuildRpcBinding(_QWORD *lpWideCharStr)
{
  RPC_BINDING_HANDLE *v1; // rsi
  RPC_BINDING_HANDLE *v2; // r15
  int v3; // r14d
  CHAR *v4; // rbx
  UUID *v5; // rdi
  char v6; // al
  unsigned int Pointer; // ebx
  CUser *v8; // rcx
  __int64 v9; // rdx
  int v10; // ecx
  _DWORD v12[3]; // [rsp+78h] [rbp-110h] BYREF
  __int64 v13; // [rsp+84h] [rbp-104h]
  int v14; // [rsp+8Ch] [rbp-FCh]
  __int64 v15; // [rsp+90h] [rbp-F8h]
  PSID v16; // [rsp+98h] [rbp-F0h]
  __int64 v17; // [rsp+A0h] [rbp-E8h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+A8h] [rbp-E0h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+D0h] [rbp-B8h] BYREF
  UUID v20; // [rsp+108h] [rbp-80h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+118h] [rbp-70h] BYREF
  CHAR lpMultiByteStr[24]; // [rsp+128h] [rbp-60h] BYREF

  *(_QWORD *)&Template.Version = 1;
  *(_QWORD *)&Template.ProtocolSequence = 3;
  memset(&Template.NetworkAddress, 0, 40);
  v12[0] = 4;
  v12[1] = 1;
  v12[2] = 1;
  v13 = 3;
  v14 = 0;
  v15 = 0;
  v16 = g_pSidSystem;
  v17 = 0;
  *(_QWORD *)&Security.Version = 1;
  Security.ServerPrincName = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.AuthIdentity = 0;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v12;
  *(_QWORD *)&Options.Version = 1;
  *(_QWORD *)&Options.ComTimeout = 5;
  v1 = (RPC_BINDING_HANDLE *)(lpWideCharStr + 70);
  if ( lpWideCharStr[70] )
    return 0;
  v2 = (RPC_BINDING_HANDLE *)(lpWideCharStr + 70);
  v3 = 0;
  if ( !WideCharToMultiByte(0, 0x400u, (LPCWCH)lpWideCharStr, -1, lpMultiByteStr, 17, 0, 0) )
    return 1610;
  v4 = lpMultiByteStr;
  v5 = &v20;
  v20 = 0;
  while ( *v4 )
  {
    if ( __isascii((unsigned __int8)*v4) && (unsigned int)_o_isupper((unsigned __int8)*v4) )
    {
      v10 = (unsigned __int8)*v4++;
      v6 = _tolower(v10);
    }
    else
    {
      v6 = *v4++;
    }
    LOBYTE(v5->Data1) = v6;
    v5 = (UUID *)((char *)v5 + 1);
  }
  Template.Flags = 1;
  Template.ObjectUuid = v20;
  Pointer = RpcBindingCreateW(&Template, &Security, &Options, v1);
  if ( Pointer )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v9 = 100;
  }
  else
  {
    Pointer = RpcBindingBind(0, *v1, qword_1400A2200);
    if ( Pointer )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_26;
      }
      v9 = 101;
    }
    else
    {
      v3 = 1;
      Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1400A2260, 0, 0, *v1).Pointer;
      v8 = WPP_GLOBAL_Control;
      if ( !Pointer
        || WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_26;
      }
      v9 = 103;
    }
  }
  WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids, Pointer);
LABEL_26:
  if ( Pointer && *v1 )
  {
    if ( v3 )
      RpcBindingUnbind(*v1);
    RpcBindingFree(v2);
  }
  return Pointer;
}

```

## disassembly

```asm
0x140026590  mov     r11, rsp
0x140026593  push    rbx
0x140026594  push    rsi
0x140026595  push    rdi
0x140026596  push    r12
0x140026598  push    r14
0x14002659a  push    r15
0x14002659c  sub     rsp, 158h
0x1400265a3  mov     rax, cs:__security_cookie
0x1400265aa  xor     rax, rsp
0x1400265ad  mov     [rsp+188h+var_48], rax
0x1400265b5  mov     [rsp+188h+var_138], rcx
0x1400265ba  mov     qword ptr [r11-0B8h], 1
0x1400265c5  xor     r12d, r12d
0x1400265c8  mov     qword ptr [r11-0B0h], 3
0x1400265d3  xorps   xmm0, xmm0
0x1400265d6  movdqu  xmmword ptr [rsp+188h+Template.NetworkAddress], xmm0
0x1400265df  mov     [r11-98h], r12
0x1400265e6  mov     [r11-90h], r12d
0x1400265ed  xor     eax, eax
0x1400265ef  mov     [r11-8Ch], rax
0x1400265f6  mov     dword ptr [rsp+188h+Template.ObjectUuid.Data4+4], eax
0x1400265fd  mov     [rsp+188h+var_110], 4
0x140026605  mov     [rsp+188h+var_10C], 1
0x14002660d  mov     [rsp+188h+var_108], 1
0x140026618  mov     qword ptr [r11-104h], 3
0x140026623  mov     [rsp+188h+var_FC], eax
0x14002662a  mov     [r11-0F8h], r12
0x140026631  mov     rax, cs:g_pSidSystem
0x140026638  mov     [r11-0F0h], rax
0x14002663f  mov     [r11-0E8h], r12
0x140026646  mov     qword ptr [r11-0E0h], 1
0x140026651  mov     [r11-0D8h], r12
0x140026658  mov     [rsp+188h+Security.AuthnLevel], 6
0x140026663  mov     [rsp+188h+Security.AuthnSvc], 0Ah
0x14002666e  mov     [r11-0C8h], r12
0x140026675  lea     rax, [rsp+188h+var_110]
0x14002667a  mov     [r11-0C0h], rax
0x140026681  mov     qword ptr [r11-70h], 1
0x140026689  mov     qword ptr [r11-68h], 5
0x140026691  lea     rsi, [rcx+230h]
0x140026698  cmp     [rsi], r12
0x14002669b  jnz     loc_140026932
0x1400266a1  mov     r15, rsi
0x1400266a4  mov     [rsp+188h+var_120], rsi
0x1400266a9  mov     [rsp+188h+var_148], r12d
0x1400266ae  mov     r14d, r12d
0x1400266b1  mov     [rsp+188h+var_144], r12d
0x1400266b6  mov     [rsp+188h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x1400266bb  mov     [rsp+188h+lpDefaultChar], r12; lpDefaultChar
0x1400266c0  mov     [rsp+188h+cbMultiByte], 11h; cbMultiByte
0x1400266c8  lea     rax, [r11-60h]
0x1400266cc  mov     [rsp+188h+lpMultiByteStr], rax; lpMultiByteStr
0x1400266d1  mov     r9d, 0FFFFFFFFh; cchWideChar
0x1400266d7  mov     r8, rcx; lpWideCharStr
0x1400266da  mov     edx, 400h; dwFlags
0x1400266df  xor     ecx, ecx; CodePage
0x1400266e1  call    cs:__imp_WideCharToMultiByte
0x1400266e7  test    eax, eax
0x1400266e9  jz      loc_14002694E
0x1400266ef  lea     rbx, [rsp+188h+var_60]
0x1400266f7  mov     [rsp+188h+var_140], rbx
0x1400266fc  lea     rdi, [rsp+188h+var_80]
0x140026704  mov     [rsp+188h+var_130], rdi
0x140026709  xorps   xmm0, xmm0
0x14002670c  movups  [rsp+188h+var_80], xmm0
0x140026714  movzx   eax, byte ptr [rbx]
0x140026717  test    al, al
0x140026719  jz      short loc_14002674F
0x14002671b  mov     ecx, eax; C
0x14002671d  call    cs:__imp___isascii
0x140026723  test    eax, eax
0x140026725  jz      short loc_140026738
0x140026727  movzx   ecx, byte ptr [rbx]
0x14002672a  call    cs:__imp__o_isupper
0x140026730  test    eax, eax
0x140026732  jnz     loc_140026808
0x140026738  movzx   eax, byte ptr [rbx]
0x14002673b  inc     rbx
0x14002673e  mov     [rsp+188h+var_140], rbx
0x140026743  mov     [rdi], al
0x140026745  inc     rdi
0x140026748  mov     [rsp+188h+var_130], rdi
0x14002674d  jmp     short loc_140026714
0x14002674f  mov     [rsp+188h+Template.Flags], 1
0x14002675a  mov     eax, dword ptr [rsp+188h+var_80]
0x140026761  mov     [rsp+188h+Template.ObjectUuid.Data1], eax
0x140026768  movsd   xmm0, qword ptr [rsp+188h+var_80+4]
0x140026771  movsd   qword ptr [rsp+188h+Template.ObjectUuid.Data2], xmm0
0x14002677a  mov     eax, dword ptr [rsp+188h+var_80+0Ch]
0x140026781  mov     dword ptr [rsp+188h+Template.ObjectUuid.Data4+4], eax
0x140026788  mov     r9, rsi; Binding
0x14002678b  lea     r8, [rsp+188h+Options]; Options
0x140026793  lea     rdx, [rsp+188h+Security]; Security
0x14002679b  lea     rcx, [rsp+188h+Template]; Template
0x1400267a3  call    cs:__imp_RpcBindingCreateW
0x1400267a9  mov     ebx, eax
0x1400267ab  mov     [rsp+188h+var_148], eax
0x1400267af  test    eax, eax
0x1400267b1  jnz     loc_1400268E5
0x1400267b7  lea     r8, qword_1400A2200; IfSpec
0x1400267be  mov     rdx, [rsi]; Binding
0x1400267c1  xor     ecx, ecx; pAsync
0x1400267c3  call    cs:__imp_RpcBindingBind
0x1400267c9  mov     ebx, eax
0x1400267cb  mov     [rsp+188h+var_148], eax
0x1400267cf  test    eax, eax
0x1400267d1  jz      short loc_14002681E
0x1400267d3  lea     rax, WPP_GLOBAL_Control
0x1400267da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400267e1  cmp     rcx, rax
0x1400267e4  jz      loc_14002690B
0x1400267ea  test    byte ptr [rcx+1Ch], 1
0x1400267ee  jz      loc_14002690B
0x1400267f4  cmp     byte ptr [rcx+19h], 2
0x1400267f8  jb      loc_14002690B
0x1400267fe  mov     edx, 65h ; 'e'
0x140026803  jmp     loc_1400268D0
0x140026808  movzx   ecx, byte ptr [rbx]; C
0x14002680b  inc     rbx
0x14002680e  mov     [rsp+188h+var_140], rbx
0x140026813  call    cs:__imp__tolower
0x140026819  jmp     loc_140026743
0x14002681e  mov     r14d, 1
0x140026824  mov     [rsp+188h+var_144], r14d
0x140026829  mov     [rsp+188h+var_128], r12
0x14002682e  mov     r9, [rsi]
0x140026831  xor     r8d, r8d; pReturnValue
0x140026834  xor     edx, edx; nProcNum
0x140026836  lea     rcx, stru_1400A2260; pProxyInfo
0x14002683d  call    cs:__imp_NdrClientCall3
0x140026843  mov     rbx, rax
0x140026846  mov     [rsp+188h+var_128], rax
0x14002684b  mov     [rsp+188h+var_148], eax
0x14002684f  mov     rcx, cs:WPP_GLOBAL_Control
0x140026856  jmp     short loc_1400268AF
0x140026858  mov     ebx, eax
0x14002685a  mov     [rsp+188h+var_148], eax
0x14002685e  lea     rdx, WPP_GLOBAL_Control
0x140026865  mov     rcx, cs:WPP_GLOBAL_Control
0x14002686c  cmp     rcx, rdx
0x14002686f  jz      short loc_1400268A2
0x140026871  test    byte ptr [rcx+1Ch], 1
0x140026875  jz      short loc_1400268A2
0x140026877  cmp     byte ptr [rcx+19h], 4
0x14002687b  jb      short loc_1400268A2
0x14002687d  mov     edx, 66h ; 'f'
0x140026882  mov     dword ptr [rsp+188h+lpMultiByteStr], eax
0x140026886  mov     r9, [rsp+188h+var_138]
0x14002688b  lea     r8, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x140026892  mov     rcx, [rcx+10h]
0x140026896  call    WPP_SF_SD
0x14002689b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400268a2  mov     r14d, [rsp+188h+var_144]
0x1400268a7  mov     r15, [rsp+188h+var_120]
0x1400268ac  mov     rsi, r15
0x1400268af  test    ebx, ebx
0x1400268b1  jz      short loc_14002690B
0x1400268b3  lea     rax, WPP_GLOBAL_Control
0x1400268ba  cmp     rcx, rax
0x1400268bd  jz      short loc_14002690B
0x1400268bf  test    byte ptr [rcx+1Ch], 1
0x1400268c3  jz      short loc_14002690B
0x1400268c5  cmp     byte ptr [rcx+19h], 2
0x1400268c9  jb      short loc_14002690B
0x1400268cb  mov     edx, 67h ; 'g'
0x1400268d0  mov     r9d, ebx
0x1400268d3  lea     r8, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x1400268da  mov     rcx, [rcx+10h]
0x1400268de  call    WPP_SF_d
0x1400268e3  jmp     short loc_14002690B
0x1400268e5  lea     rax, WPP_GLOBAL_Control
0x1400268ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400268f3  cmp     rcx, rax
0x1400268f6  jz      short loc_14002690B
0x1400268f8  test    byte ptr [rcx+1Ch], 1
0x1400268fc  jz      short loc_14002690B
0x1400268fe  cmp     byte ptr [rcx+19h], 2
0x140026902  jb      short loc_14002690B
0x140026904  mov     edx, 64h ; 'd'
0x140026909  jmp     short loc_1400268D0
0x14002690b  test    ebx, ebx
0x14002690d  jnz     short loc_140026936
0x14002690f  mov     eax, ebx
0x140026911  mov     rcx, [rsp+188h+var_48]
0x140026919  xor     rcx, rsp; StackCookie
0x14002691c  call    __security_check_cookie
0x140026921  add     rsp, 158h
0x140026928  pop     r15
0x14002692a  pop     r14
0x14002692c  pop     r12
0x14002692e  pop     rdi
0x14002692f  pop     rsi
0x140026930  pop     rbx
0x140026931  retn
0x140026932  xor     eax, eax
0x140026934  jmp     short loc_140026911
0x140026936  mov     rcx, [rsi]; Binding
0x140026939  test    rcx, rcx
0x14002693c  jz      short loc_14002690F
0x14002693e  test    r14d, r14d
0x140026941  jnz     short loc_140026955
0x140026943  mov     rcx, r15; Binding
0x140026946  call    cs:__imp_RpcBindingFree
0x14002694c  jmp     short loc_14002690F
0x14002694e  mov     eax, 64Ah
0x140026953  jmp     short loc_140026911
0x140026955  call    cs:__imp_RpcBindingUnbind
0x14002695b  jmp     short loc_140026943
0x14009de30  push    rbp
0x14009de32  sub     rsp, 40h
0x14009de36  mov     rbp, rdx
0x14009de39  mov     rcx, [rcx]
0x14009de3c  mov     ecx, [rcx]; ExceptionCode
0x14009de3e  call    cs:__imp_I_RpcExceptionFilter
0x14009de44  nop
0x14009de45  add     rsp, 40h
0x14009de49  pop     rbp
0x14009de4a  retn
0x14009de4c  push    rbx
0x14009de4e  push    rbp
0x14009de4f  sub     rsp, 48h
0x14009de53  mov     rbp, rdx
0x14009de56  cmp     dword ptr [rbp+40h], 0
0x14009de5a  jz      short loc_14009DE8C
0x14009de5c  mov     rbx, [rbp+50h]
0x14009de60  cmp     qword ptr [rbx+230h], 0
0x14009de68  jz      short loc_14009DE8C
0x14009de6a  cmp     dword ptr [rbp+44h], 0
0x14009de6e  jz      short loc_14009DE7E
0x14009de70  mov     rcx, [rbx+230h]; Binding
0x14009de77  call    cs:__imp_RpcBindingUnbind
0x14009de7d  nop
0x14009de7e  lea     rcx, [rbx+230h]; Binding
0x14009de85  call    cs:__imp_RpcBindingFree
0x14009de8b  nop
0x14009de8c  add     rsp, 48h
0x14009de90  pop     rbp
0x14009de91  pop     rbx
0x14009de92  retn
```
