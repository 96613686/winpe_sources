# LocalRpcBindingCreateWithSecurity

- ea: `0x180037900`
- end: `0x180037a96`
- name: `LocalRpcBindingCreateWithSecurity`
- size: `406`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE_TEMPLATE_V1_W *Template@<rcx>, RPC_BINDING_HANDLE_OPTIONS_V1 *Options@<rdx>, RPC_IF_HANDLE IfSpec@<r8>, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180012100`
- `0x180012290`
- `0x180037900`
- `0x180037d3c`
- `0x18004fa50`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x180037a22`
- `RPCRT4!RpcBindingCreateW` at `0x180037a22`
- `RPCRT4!RpcBindingBind` at `0x180037a4c`
- `RPCRT4!RpcBindingBind` at `0x180037a4c`

## pseudocode

```c
__int64 __fastcall LocalRpcBindingCreateWithSecurity(
        RPC_BINDING_HANDLE_TEMPLATE_V1_W *Template,
        RPC_BINDING_HANDLE_OPTIONS_V1 *Options,
        RPC_IF_HANDLE IfSpec,
        __int64 a4,
        RPC_BINDING_HANDLE *a5)
{
  int v9; // ebx
  int v10; // eax
  RPC_BINDING_HANDLE_TEMPLATE_V1_W *v11; // rcx
  RPC_STATUS v12; // eax
  bool v13; // cc
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-A1h] BYREF
  PSECURITY_DESCRIPTOR v16; // [rsp+28h] [rbp-99h] BYREF
  __int64 v17; // [rsp+30h] [rbp-91h] BYREF
  int v18; // [rsp+38h] [rbp-89h]
  __int64 v19; // [rsp+3Ch] [rbp-85h]
  int v20; // [rsp+44h] [rbp-7Dh]
  __int128 v21; // [rsp+48h] [rbp-79h]
  __int64 v22; // [rsp+58h] [rbp-69h]
  PSECURITY_DESCRIPTOR v23; // [rsp+60h] [rbp-61h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+68h] [rbp-59h] BYREF
  _QWORD v25[2]; // [rsp+90h] [rbp-31h] BYREF
  __int128 v26; // [rsp+A0h] [rbp-21h]
  __int64 v27; // [rsp+B0h] [rbp-11h]
  int v28; // [rsp+B8h] [rbp-9h]
  __int64 v29; // [rsp+BCh] [rbp-5h]
  int v30; // [rsp+C4h] [rbp+3h]

  Binding = 0;
  v29 = 0;
  v30 = 0;
  v20 = 0;
  v25[0] = 1;
  Security.Version = 1;
  v16 = 0;
  v25[1] = 3;
  v27 = 0;
  v28 = 0;
  v17 = 5;
  v18 = 0;
  v19 = 2;
  v22 = 0;
  v23 = 0;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v17;
  v26 = 0;
  v21 = 0;
  if ( a5 && a4 )
  {
    v9 = StringEndsWith(a4, L"\\Server");
    if ( v9 >= 0 )
    {
      v10 = QueryTransientObjectSecurityDescriptor(9, a4, &v16);
      if ( v10 >= 0 )
      {
        v11 = (RPC_BINDING_HANDLE_TEMPLATE_V1_W *)v25;
        v23 = v16;
        if ( Template )
          v11 = Template;
        v12 = RpcBindingCreateW(v11, &Security, Options, &Binding);
        v13 = v12 <= 0;
        if ( v12 || IfSpec && (v12 = RpcBindingBind(0, Binding, IfSpec), v13 = v12 <= 0, v12) )
        {
          if ( v13 )
            v9 = v12;
          else
            v9 = (unsigned __int16)v12 | 0x80070000;
        }
        else
        {
          *a5 = Binding;
        }
      }
      else
      {
        v9 = v10 | 0x10000000;
      }
    }
  }
  else
  {
    v9 = -2147024809;
  }
  if ( v16 )
    FreeTransientObjectSecurityDescriptor(v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180037900  push    rbp
0x180037902  push    rbx
0x180037903  push    rsi
0x180037904  push    rdi
0x180037905  push    r12
0x180037907  push    r13
0x180037909  push    r14
0x18003790b  push    r15
0x18003790d  lea     rbp, [rsp-17h]
0x180037912  sub     rsp, 0D8h
0x180037919  mov     rax, cs:__security_cookie
0x180037920  xor     rax, rsp
0x180037923  mov     [rbp+4Fh+var_48], rax
0x180037927  mov     r15, [rbp+4Fh+arg_20]
0x18003792b  xor     r13d, r13d
0x18003792e  xor     eax, eax
0x180037930  mov     [rsp+110h+Binding], r13
0x180037935  mov     [rbp+4Fh+var_54], rax
0x180037939  xorps   xmm0, xmm0
0x18003793c  mov     [rbp+4Fh+var_4C], eax
0x18003793f  mov     r14, rcx
0x180037942  mov     [rbp+4Fh+var_CC], eax
0x180037945  lea     ecx, [r13+1]
0x180037949  mov     [rbp+4Fh+var_80], rcx
0x18003794d  lea     rax, [rsp+110h+var_E0]
0x180037952  mov     [rbp+4Fh+Security.Version], ecx
0x180037955  mov     rdi, r9
0x180037958  mov     [rsp+110h+var_E8], r13
0x18003795d  mov     rsi, r8
0x180037960  mov     [rbp+4Fh+var_78], 3
0x180037968  mov     r12, rdx
0x18003796b  mov     [rbp+4Fh+var_60], r13
0x18003796f  mov     [rbp+4Fh+var_58], r13d
0x180037973  mov     [rsp+110h+var_E0], 5
0x18003797c  mov     [rsp+110h+var_D8], r13d
0x180037981  mov     [rsp+110h+var_D4], 2
0x18003798a  mov     [rbp+4Fh+var_B8], r13
0x18003798e  mov     [rbp+4Fh+var_B0], r13
0x180037992  mov     qword ptr [rbp+4Fh+Security+4], r13
0x180037996  mov     dword ptr [rbp+4Fh+Security.ServerPrincName+4], r13d
0x18003799a  mov     [rbp+4Fh+Security.AuthIdentity], r13
0x18003799e  mov     [rbp+4Fh+Security.AuthnLevel], 6
0x1800379a5  mov     [rbp+4Fh+Security.AuthnSvc], 0Ah
0x1800379ac  mov     [rbp+4Fh+Security.SecurityQos], rax
0x1800379b0  movdqu  [rbp+4Fh+var_70], xmm0
0x1800379b5  movdqu  [rbp+4Fh+var_C8], xmm0
0x1800379ba  test    r15, r15
0x1800379bd  jz      loc_180037A60
0x1800379c3  test    r9, r9
0x1800379c6  jz      loc_180037A60
0x1800379cc  lea     rdx, aServer; "\\Server"
0x1800379d3  mov     rcx, r9
0x1800379d6  call    StringEndsWith
0x1800379db  mov     ebx, eax
0x1800379dd  test    eax, eax
0x1800379df  js      loc_180037A65
0x1800379e5  lea     r8, [rsp+110h+var_E8]
0x1800379ea  mov     rdx, rdi
0x1800379ed  lea     ecx, [r13+9]
0x1800379f1  call    QueryTransientObjectSecurityDescriptor
0x1800379f6  test    eax, eax
0x1800379f8  jns     short loc_180037A02
0x1800379fa  mov     ebx, eax
0x1800379fc  bts     ebx, 1Ch
0x180037a00  jmp     short loc_180037A65
0x180037a02  mov     rax, [rsp+110h+var_E8]
0x180037a07  lea     rcx, [rbp+4Fh+var_80]
0x180037a0b  test    r14, r14
0x180037a0e  mov     [rbp+4Fh+var_B0], rax
0x180037a12  lea     r9, [rsp+110h+Binding]; Binding
0x180037a17  mov     r8, r12; Options
0x180037a1a  cmovnz  rcx, r14; Template
0x180037a1e  lea     rdx, [rbp+4Fh+Security]; Security
0x180037a22  call    cs:__imp_RpcBindingCreateW
0x180037a28  test    eax, eax
0x180037a2a  jz      short loc_180037A3D
0x180037a2c  jg      short loc_180037A32
0x180037a2e  mov     ebx, eax
0x180037a30  jmp     short loc_180037A65
0x180037a32  movzx   ebx, ax
0x180037a35  or      ebx, 80070000h
0x180037a3b  jmp     short loc_180037A65
0x180037a3d  test    rsi, rsi
0x180037a40  jz      short loc_180037A56
0x180037a42  mov     rdx, [rsp+110h+Binding]; Binding
0x180037a47  mov     r8, rsi; IfSpec
0x180037a4a  xor     ecx, ecx; pAsync
0x180037a4c  call    cs:__imp_RpcBindingBind
0x180037a52  test    eax, eax
0x180037a54  jnz     short loc_180037A2C
0x180037a56  mov     rax, [rsp+110h+Binding]
0x180037a5b  mov     [r15], rax
0x180037a5e  jmp     short loc_180037A65
0x180037a60  mov     ebx, 80070057h
0x180037a65  mov     rcx, [rsp+110h+var_E8]
0x180037a6a  test    rcx, rcx
0x180037a6d  jz      short loc_180037A74
0x180037a6f  call    FreeTransientObjectSecurityDescriptor
0x180037a74  mov     eax, ebx
0x180037a76  mov     rcx, [rbp+4Fh+var_48]
0x180037a7a  xor     rcx, rsp; StackCookie
0x180037a7d  call    __security_check_cookie
0x180037a82  add     rsp, 0D8h
0x180037a89  pop     r15
0x180037a8b  pop     r14
0x180037a8d  pop     r13
0x180037a8f  pop     r12
0x180037a91  pop     rdi
0x180037a92  pop     rsi
0x180037a93  pop     rbx
0x180037a94  pop     rbp
0x180037a95  retn
```
