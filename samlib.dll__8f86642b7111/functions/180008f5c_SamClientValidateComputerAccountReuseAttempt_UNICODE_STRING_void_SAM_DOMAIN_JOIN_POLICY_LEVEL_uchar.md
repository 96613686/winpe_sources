# SamClientValidateComputerAccountReuseAttempt(_UNICODE_STRING *,void *,SAM_DOMAIN_JOIN_POLICY_LEVEL,uchar *)

- ea: `0x180008f5c`
- end: `0x180009184`
- name: `?SamClientValidateComputerAccountReuseAttempt@@YAJPEAU_UNICODE_STRING@@PEAXW4SAM_DOMAIN_JOIN_POLICY_LEVEL@@PEAE@Z`
- size: `552`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014440`

## callees

- `0x180001800`
- `0x180004dd0`
- `0x18000807c`
- `0x180008f5c`
- `0x18001444c`
- `0x1800145ac`
- `0x18001461c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800090cb`
- `RPCRT4!NdrClientCall3` at `0x1800090cb`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000910e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000910e`

## pseudocode

```c
__int64 __fastcall SamClientValidateComputerAccountReuseAttempt(__int64 a1, __int64 a2, unsigned int a3, _BYTE *a4)
{
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  int Pointer; // ebx
  _QWORD *v12; // rcx
  int v13; // ebx
  CLIENT_CALL_RETURN v14; // rax
  _BYTE v16[4]; // [rsp+30h] [rbp-38h] BYREF
  int v17; // [rsp+34h] [rbp-34h]
  void *v18; // [rsp+38h] [rbp-30h] BYREF
  CLIENT_CALL_RETURN v19; // [rsp+40h] [rbp-28h]

  v18 = 0;
  v16[0] = 0;
  *a4 = 0;
  v8 = SamConnect(a1, &v18, 32, 0);
  Pointer = v8;
  v12 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_ZD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      385,
      (unsigned int)&WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
      a1,
      v8);
    v12 = WPP_GLOBAL_Control;
  }
  if ( Pointer >= 0 )
  {
    if ( (*((_BYTE *)v18 + 12) & 0x40) != 0 )
      v13 = 2;
    else
      v13 = (*((unsigned __int8 *)v18 + 12) >> 5) & 1;
    if ( (*((_BYTE *)v12 + 28) & 2) != 0 && *((_BYTE *)v12 + 25) >= 4u )
    {
      WPP_SF_DD(v12[2], v9, v10, a3, v13);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v13 )
    {
      if ( v13 == a3 )
      {
        v19.Simple = 0;
        v14.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&samr_ProxyInfo, 0x4Au, 0, *(_QWORD *)v18, a2, v16).Pointer;
        Pointer = (int)v14.Pointer;
        v19.Pointer = v14.Pointer;
        v17 = (int)v14.Pointer;
        *a4 = v16[0];
        goto LABEL_20;
      }
      Pointer = -1073741637;
      if ( (*((_BYTE *)v12 + 28) & 2) != 0 && *((_BYTE *)v12 + 25) >= 4u )
      {
        WPP_SF_ZD(v12[2], 389, (unsigned int)&WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1, 187);
        goto LABEL_20;
      }
    }
    else
    {
      Pointer = -1073741637;
      if ( (*((_BYTE *)v12 + 28) & 2) != 0 && *((_BYTE *)v12 + 25) >= 4u )
      {
        WPP_SF_Z(v12[2], 388, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, a1);
LABEL_20:
        v12 = WPP_GLOBAL_Control;
      }
    }
  }
  if ( v18 )
  {
    SamCloseHandle(v18);
    v12 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v12 + 28) & 2) != 0 && *((_BYTE *)v12 + 25) >= 4u )
    WPP_SF_D(v12[2], 391, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids, (unsigned int)Pointer);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180008f5c  mov     rax, rsp
0x180008f5f  mov     [rax+8], rbx
0x180008f63  mov     [rax+10h], rsi
0x180008f67  mov     [rax+20h], r9
0x180008f6b  push    r12
0x180008f6d  push    r14
0x180008f6f  push    r15
0x180008f71  sub     rsp, 50h
0x180008f75  mov     r14, r9
0x180008f78  mov     r15d, r8d
0x180008f7b  mov     r12, rdx
0x180008f7e  mov     rsi, rcx
0x180008f81  mov     qword ptr [rax-30h], 0
0x180008f89  mov     byte ptr [rax-38h], 0
0x180008f8d  mov     byte ptr [r9], 0
0x180008f91  xor     r9d, r9d
0x180008f94  lea     r8d, [r9+20h]
0x180008f98  lea     rdx, [rax-30h]
0x180008f9c  call    SamConnect
0x180008fa1  mov     ebx, eax
0x180008fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180008faa  test    byte ptr [rcx+1Ch], 2
0x180008fae  jz      short loc_180008FD9
0x180008fb0  cmp     byte ptr [rcx+19h], 4
0x180008fb4  jb      short loc_180008FD9
0x180008fb6  mov     edx, 181h
0x180008fbb  mov     dword ptr [rsp+68h+var_48], eax
0x180008fbf  mov     r9, rsi
0x180008fc2  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180008fc9  mov     rcx, [rcx+10h]
0x180008fcd  call    WPP_SF_ZD
0x180008fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fd9  test    ebx, ebx
0x180008fdb  js      loc_180009130
0x180008fe1  mov     rax, [rsp+68h+var_30]
0x180008fe6  test    byte ptr [rax+0Ch], 40h
0x180008fea  jz      short loc_180008FF3
0x180008fec  mov     ebx, 2
0x180008ff1  jmp     short loc_180008FFD
0x180008ff3  movzx   ebx, byte ptr [rax+0Ch]
0x180008ff7  shr     ebx, 5
0x180008ffa  and     ebx, 1
0x180008ffd  test    byte ptr [rcx+1Ch], 2
0x180009001  jz      short loc_180009020
0x180009003  cmp     byte ptr [rcx+19h], 4
0x180009007  jb      short loc_180009020
0x180009009  mov     dword ptr [rsp+68h+var_48], ebx
0x18000900d  mov     r9d, r15d
0x180009010  mov     rcx, [rcx+10h]
0x180009014  call    WPP_SF_DD
0x180009019  mov     rcx, cs:WPP_GLOBAL_Control
0x180009020  test    ebx, ebx
0x180009022  jnz     short loc_18000905A
0x180009024  mov     ebx, 0C00000BBh
0x180009029  test    byte ptr [rcx+1Ch], 2
0x18000902d  jz      loc_180009130
0x180009033  cmp     byte ptr [rcx+19h], 4
0x180009037  jb      loc_180009130
0x18000903d  mov     edx, 184h
0x180009042  mov     r9, rsi
0x180009045  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000904c  mov     rcx, [rcx+10h]
0x180009050  call    WPP_SF_Z
0x180009055  jmp     loc_180009129
0x18000905a  cmp     ebx, r15d
0x18000905d  jz      short loc_18000909D
0x18000905f  mov     ebx, 0C00000BBh
0x180009064  test    byte ptr [rcx+1Ch], 2
0x180009068  jz      loc_180009130
0x18000906e  cmp     byte ptr [rcx+19h], 4
0x180009072  jb      loc_180009130
0x180009078  mov     edx, 185h
0x18000907d  mov     dword ptr [rsp+68h+var_48], 0C00000BBh
0x180009085  mov     r9, rsi
0x180009088  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000908f  mov     rcx, [rcx+10h]
0x180009093  call    WPP_SF_ZD
0x180009098  jmp     loc_180009129
0x18000909d  mov     rax, [rsp+68h+var_30]
0x1800090a2  mov     [rsp+68h+var_28], 0
0x1800090ab  lea     rcx, [rsp+68h+var_38]
0x1800090b0  mov     [rsp+68h+var_40], rcx
0x1800090b5  mov     [rsp+68h+var_48], r12
0x1800090ba  mov     r9, [rax]
0x1800090bd  xor     r8d, r8d; pReturnValue
0x1800090c0  lea     edx, [r8+4Ah]; nProcNum
0x1800090c4  lea     rcx, ?samr_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800090cb  call    cs:__imp_NdrClientCall3
0x1800090d1  mov     rbx, rax
0x1800090d4  mov     [rsp+68h+var_28], rax
0x1800090d9  mov     [rsp+68h+var_34], eax
0x1800090dd  jmp     short loc_180009122
0x1800090df  mov     ebx, eax
0x1800090e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090e8  test    byte ptr [rcx+1Ch], 2
0x1800090ec  jz      short loc_18000910C
0x1800090ee  cmp     byte ptr [rcx+19h], 3
0x1800090f2  jb      short loc_18000910C
0x1800090f4  mov     r9d, eax
0x1800090f7  mov     edx, 186h
0x1800090fc  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180009103  mov     rcx, [rcx+10h]
0x180009107  call    WPP_SF_D
0x18000910c  mov     ecx, ebx; Status
0x18000910e  call    cs:__imp_I_RpcMapWin32Status
0x180009114  mov     ebx, eax
0x180009116  mov     [rsp+68h+var_34], eax
0x18000911a  mov     r14, [rsp+68h+arg_18]
0x180009122  mov     al, [rsp+68h+var_38]
0x180009126  mov     [r14], al
0x180009129  mov     rcx, cs:WPP_GLOBAL_Control
0x180009130  cmp     [rsp+68h+var_30], 0
0x180009136  jz      short loc_180009149
0x180009138  mov     rcx, [rsp+68h+var_30]; void *
0x18000913d  call    SamCloseHandle
0x180009142  mov     rcx, cs:WPP_GLOBAL_Control
0x180009149  test    byte ptr [rcx+1Ch], 2
0x18000914d  jz      short loc_18000916D
0x18000914f  cmp     byte ptr [rcx+19h], 4
0x180009153  jb      short loc_18000916D
0x180009155  mov     edx, 187h
0x18000915a  mov     r9d, ebx
0x18000915d  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180009164  mov     rcx, [rcx+10h]
0x180009168  call    WPP_SF_D
0x18000916d  mov     eax, ebx
0x18000916f  mov     rbx, [rsp+68h+arg_0]
0x180009174  mov     rsi, [rsp+68h+arg_8]
0x180009179  add     rsp, 50h
0x18000917d  pop     r15
0x18000917f  pop     r14
0x180009181  pop     r12
0x180009183  retn
0x180017dbc  push    rbp
0x180017dbe  sub     rsp, 30h
0x180017dc2  mov     rbp, rdx
0x180017dc5  mov     rcx, [rcx]
0x180017dc8  mov     ecx, [rcx]; ExceptionCode
0x180017dca  call    cs:__imp_I_RpcExceptionFilter
0x180017dd0  nop
0x180017dd1  add     rsp, 30h
0x180017dd5  pop     rbp
0x180017dd6  retn
```
