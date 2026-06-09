# SrvXsConnect

- ea: `0x140055bb0`
- end: `0x140055f55`
- name: `SrvXsConnect`
- size: `933`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140050940`

## callees

- `0x14001389c`
- `0x140015790`
- `0x14002a3e0`
- `0x140055bb0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140055c47`
- `ntoskrnl!KeGetCurrentIrql` at `0x140055c47`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140055c37`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140055c37`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140055cf7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140055f42`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140055cf7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140055f42`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055c20`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055c20`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140055ccf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140055ccf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140055cb5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140055cb5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140055ceb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140055f36`
- `ntoskrnl!ExReleaseResourceLite` at `0x140055ceb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140055f36`
- `msrpc!RpcBindingFree` at `0x140055e97`
- `msrpc!RpcBindingFree` at `0x140055f10`
- `msrpc!RpcBindingFree` at `0x140055e97`
- `msrpc!RpcBindingFree` at `0x140055f10`
- `msrpc!I_RpcExceptionFilter` at `0x1400574c6`
- `msrpc!I_RpcExceptionFilter` at `0x1400574c6`
- `msrpc!RpcBindingBind` at `0x140055e43`
- `msrpc!RpcBindingBind` at `0x140055e43`
- `msrpc!RpcBindingCreateW` at `0x140055ddc`
- `msrpc!RpcBindingCreateW` at `0x140055ddc`

## pseudocode

```c
__int64 __fastcall SrvXsConnect(PCUNICODE_STRING String1)
{
  unsigned int v3; // edi
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-C0h] BYREF
  __int128 v5; // [rsp+50h] [rbp-98h] BYREF
  __int128 v6; // [rsp+60h] [rbp-88h]
  __int64 *v7; // [rsp+70h] [rbp-78h]
  UNICODE_STRING String2; // [rsp+78h] [rbp-70h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+88h] [rbp-60h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+C0h] [rbp-28h] BYREF

  memset(&Template, 0, sizeof(Template));
  v5 = 0;
  v6 = 0;
  v7 = 0;
  memset(&Security, 0, 36);
  Options = 0;
  String2 = 0;
  RtlInitUnicodeString(&String2, L"ncalrpc");
  if ( !RtlEqualUnicodeString(String1, &String2, 0) )
    return 3221225701LL;
  if ( KeGetCurrentIrql() )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_892563a873b4365dd8b1a9616810a533_Traceguids);
    }
    return 3221225701LL;
  }
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&SrvXsResource, 1u);
  if ( SrvXsStatus == 2 )
  {
    ExReleaseResourceLite(&SrvXsResource);
    KeLeaveCriticalRegion();
    return 0;
  }
  else
  {
    *(_QWORD *)&Template.ProtocolSequence = 3;
    *(_QWORD *)&Template.Version = 1;
    memset(&Template.NetworkAddress, 0, 40);
    v6 = 0;
    *(_QWORD *)&v5 = 0x100000003LL;
    *((_QWORD *)&v5 + 1) = 0x300000001LL;
    v7 = LocalSystem;
    *(_QWORD *)(&Security.Version + 1) = 0;
    HIDWORD(Security.ServerPrincName) = 0;
    Security.AuthIdentity = 0;
    Security.Version = 1;
    Security.AuthnLevel = 6;
    Security.AuthnSvc = 10;
    Security.SecurityQos = (RPC_SECURITY_QOS *)&v5;
    Options.Version = 1;
    Options.Flags = 1;
    *(_QWORD *)&Options.ComTimeout = 5;
    v3 = RpcBindingCreateW(&Template, &Security, &Options, &SrvXsRpcBindingHandle);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_892563a873b4365dd8b1a9616810a533_Traceguids, v3);
      }
    }
    else
    {
      v3 = RpcBindingBind(0, SrvXsRpcBindingHandle, qword_14002E070);
      if ( v3 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_892563a873b4365dd8b1a9616810a533_Traceguids, v3);
        }
        RpcBindingFree(&SrvXsRpcBindingHandle);
        SrvXsRpcBindingHandle = 0;
      }
      else
      {
        SrvXsStatus = 2;
      }
    }
    ExReleaseResourceLite(&SrvXsResource);
    KeLeaveCriticalRegion();
    return v3;
  }
}

```

## disassembly

```asm
0x140055bb0  mov     r11, rsp
0x140055bb3  mov     [r11+10h], rbx
0x140055bb7  push    rdi
0x140055bb8  sub     rsp, 0E0h
0x140055bbf  mov     rax, cs:__security_cookie
0x140055bc6  xor     rax, rsp
0x140055bc9  mov     [rsp+0E8h+var_18], rax
0x140055bd1  mov     rbx, rcx
0x140055bd4  xorps   xmm0, xmm0
0x140055bd7  xor     eax, eax
0x140055bd9  movups  xmmword ptr [r11-60h], xmm0
0x140055bde  movups  xmmword ptr [r11-50h], xmm0
0x140055be3  movups  xmmword ptr [r11-40h], xmm0
0x140055be8  mov     [r11-30h], rax
0x140055bec  movups  [rsp+0E8h+var_98], xmm0
0x140055bf1  movups  [rsp+0E8h+var_88], xmm0
0x140055bf6  mov     [r11-78h], rax
0x140055bfa  movups  xmmword ptr [rsp+0E8h+Security.Version], xmm0
0x140055bff  movups  xmmword ptr [rsp+0E8h+Security.AuthnLevel], xmm0
0x140055c04  mov     dword ptr [rsp+0E8h+Security.SecurityQos], eax
0x140055c08  movups  xmmword ptr [r11-28h], xmm0
0x140055c0d  xorps   xmm1, xmm1
0x140055c10  movups  xmmword ptr [rsp+0E8h+String2.Length], xmm1
0x140055c15  lea     rdx, aNcalrpc; "ncalrpc"
0x140055c1c  lea     rcx, [r11-70h]; DestinationString
0x140055c20  call    cs:__imp_RtlInitUnicodeString
0x140055c27  nop     dword ptr [rax+rax+00h]
0x140055c2c  xor     r8d, r8d; CaseInSensitive
0x140055c2f  lea     rdx, [rsp+0E8h+String2]; String2
0x140055c34  mov     rcx, rbx; String1
0x140055c37  call    cs:__imp_RtlEqualUnicodeString
0x140055c3e  nop     dword ptr [rax+rax+00h]
0x140055c43  test    al, al
0x140055c45  jz      short loc_140055C8E
0x140055c47  call    cs:__imp_KeGetCurrentIrql
0x140055c4e  nop     dword ptr [rax+rax+00h]
0x140055c53  test    al, al
0x140055c55  jz      short loc_140055CB5
0x140055c57  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140055c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140055c65  cmp     rcx, rax
0x140055c68  jz      short loc_140055C8E
0x140055c6a  mov     eax, [rcx+2Ch]
0x140055c6d  test    al, 10h
0x140055c6f  jz      short loc_140055C8E
0x140055c71  mov     ebx, 1
0x140055c76  cmp     [rcx+29h], bl
0x140055c79  jb      short loc_140055C8E
0x140055c7b  lea     edx, [rbx+9]
0x140055c7e  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x140055c85  mov     rcx, [rcx+18h]
0x140055c89  call    WPP_SF_
0x140055c8e  mov     eax, 0C00000E5h
0x140055c93  mov     rcx, [rsp+0E8h+var_18]
0x140055c9b  xor     rcx, rsp; StackCookie
0x140055c9e  call    __security_check_cookie
0x140055ca3  mov     rbx, [rsp+0E8h+arg_8]
0x140055cab  add     rsp, 0E0h
0x140055cb2  pop     rdi
0x140055cb3  retn
0x140055cb5  call    cs:__imp_KeEnterCriticalRegion
0x140055cbc  nop     dword ptr [rax+rax+00h]
0x140055cc1  mov     ebx, 1
0x140055cc6  mov     dl, bl; Wait
0x140055cc8  lea     rcx, SrvXsResource; Resource
0x140055ccf  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140055cd6  nop     dword ptr [rax+rax+00h]
0x140055cdb  cmp     cs:SrvXsStatus, 2
0x140055ce2  jnz     short loc_140055D07
0x140055ce4  lea     rcx, SrvXsResource; Resource
0x140055ceb  call    cs:__imp_ExReleaseResourceLite
0x140055cf2  nop     dword ptr [rax+rax+00h]
0x140055cf7  call    cs:__imp_KeLeaveCriticalRegion
0x140055cfe  nop     dword ptr [rax+rax+00h]
0x140055d03  xor     eax, eax
0x140055d05  jmp     short loc_140055C93
0x140055d07  mov     [rsp+0E8h+var_C8], 0
0x140055d0f  mov     qword ptr [rsp+0E8h+Template.ProtocolSequence], 3
0x140055d1b  xorps   xmm0, xmm0
0x140055d1e  movdqu  xmmword ptr [rsp+0E8h+Template.ObjectUuid.Data1], xmm0
0x140055d27  mov     qword ptr [rsp+0E8h+Template.Version], rbx
0x140055d2f  mov     eax, 3
0x140055d34  movdqu  xmmword ptr [rsp+0E8h+Template.NetworkAddress], xmm0
0x140055d3d  mov     qword ptr [rsp+0E8h+Template.u1], 0
0x140055d49  xorps   xmm1, xmm1
0x140055d4c  movdqu  [rsp+0E8h+var_88], xmm1
0x140055d52  mov     dword ptr [rsp+0E8h+var_98], eax
0x140055d56  mov     dword ptr [rsp+0E8h+var_98+4], ebx
0x140055d5a  mov     dword ptr [rsp+0E8h+var_98+8], ebx
0x140055d5e  mov     dword ptr [rsp+0E8h+var_98+0Ch], eax
0x140055d62  lea     rax, LocalSystem
0x140055d69  mov     [rsp+0E8h+var_78], rax
0x140055d6e  mov     qword ptr [rsp+0E8h+Security+4], 0
0x140055d77  mov     dword ptr [rsp+0E8h+Security.ServerPrincName+4], 0
0x140055d7f  mov     [rsp+0E8h+Security.AuthIdentity], 0
0x140055d88  mov     [rsp+0E8h+Security.Version], ebx
0x140055d8c  mov     [rsp+0E8h+Security.AuthnLevel], 6
0x140055d94  mov     [rsp+0E8h+Security.AuthnSvc], 0Ah
0x140055d9c  lea     rax, [rsp+0E8h+var_98]
0x140055da1  mov     [rsp+0E8h+Security.SecurityQos], rax
0x140055da6  mov     [rsp+0E8h+Options.Version], ebx
0x140055dad  mov     [rsp+0E8h+Options.Flags], ebx
0x140055db4  mov     qword ptr [rsp+0E8h+Options.ComTimeout], 5
0x140055dc0  lea     r9, SrvXsRpcBindingHandle; Binding
0x140055dc7  lea     r8, [rsp+0E8h+Options]; Options
0x140055dcf  lea     rdx, [rsp+0E8h+Security]; Security
0x140055dd4  lea     rcx, [rsp+0E8h+Template]; Template
0x140055ddc  call    cs:__imp_RpcBindingCreateW
0x140055de3  nop     dword ptr [rax+rax+00h]
0x140055de8  mov     edi, eax
0x140055dea  mov     [rsp+0E8h+var_C4], eax
0x140055dee  test    eax, eax
0x140055df0  jz      short loc_140055E2F
0x140055df2  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140055df9  mov     rcx, cs:WPP_GLOBAL_Control
0x140055e00  cmp     rcx, rax
0x140055e03  jz      short loc_140055E2A
0x140055e05  mov     edx, [rcx+2Ch]
0x140055e08  test    dl, 10h
0x140055e0b  jz      short loc_140055E2A
0x140055e0d  cmp     [rcx+29h], bl
0x140055e10  jb      short loc_140055E2A
0x140055e12  mov     edx, 0Bh
0x140055e17  mov     r9d, edi
0x140055e1a  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x140055e21  mov     rcx, [rcx+18h]
0x140055e25  call    WPP_SF_d
0x140055e2a  jmp     loc_140055F2F
0x140055e2f  mov     [rsp+0E8h+var_C8], ebx
0x140055e33  lea     r8, qword_14002E070; IfSpec
0x140055e3a  mov     rdx, cs:SrvXsRpcBindingHandle; Binding
0x140055e41  xor     ecx, ecx; pAsync
0x140055e43  call    cs:__imp_RpcBindingBind
0x140055e4a  nop     dword ptr [rax+rax+00h]
0x140055e4f  mov     edi, eax
0x140055e51  mov     [rsp+0E8h+var_C4], eax
0x140055e55  test    eax, eax
0x140055e57  jz      short loc_140055EB8
0x140055e59  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140055e60  mov     rcx, cs:WPP_GLOBAL_Control
0x140055e67  cmp     rcx, rax
0x140055e6a  jz      short loc_140055E90
0x140055e6c  mov     eax, [rcx+2Ch]
0x140055e6f  test    al, 10h
0x140055e71  jz      short loc_140055E90
0x140055e73  cmp     [rcx+29h], bl
0x140055e76  jb      short loc_140055E90
0x140055e78  mov     edx, 0Ch
0x140055e7d  mov     r9d, edi
0x140055e80  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x140055e87  mov     rcx, [rcx+18h]
0x140055e8b  call    WPP_SF_d
0x140055e90  lea     rcx, SrvXsRpcBindingHandle; Binding
0x140055e97  call    cs:__imp_RpcBindingFree
0x140055e9e  nop     dword ptr [rax+rax+00h]
0x140055ea3  mov     cs:SrvXsRpcBindingHandle, 0
0x140055eae  mov     [rsp+0E8h+var_C8], 0
0x140055eb6  jmp     short loc_140055F2F
0x140055eb8  mov     cs:SrvXsStatus, 2
0x140055ec2  jmp     short loc_140055F2F
0x140055ec4  mov     edi, eax
0x140055ec6  mov     [rsp+0E8h+var_C4], eax
0x140055eca  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140055ed1  mov     rcx, cs:WPP_GLOBAL_Control
0x140055ed8  cmp     rcx, rax
0x140055edb  jz      short loc_140055F02
0x140055edd  mov     eax, [rcx+2Ch]
0x140055ee0  test    al, 10h
0x140055ee2  jz      short loc_140055F02
0x140055ee4  cmp     byte ptr [rcx+29h], 1
0x140055ee8  jb      short loc_140055F02
0x140055eea  mov     edx, 0Dh
0x140055eef  mov     r9d, edi
0x140055ef2  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x140055ef9  mov     rcx, [rcx+18h]
0x140055efd  call    WPP_SF_d
0x140055f02  cmp     [rsp+0E8h+var_C8], 0
0x140055f07  jz      short loc_140055F2F
0x140055f09  lea     rcx, SrvXsRpcBindingHandle; Binding
0x140055f10  call    cs:__imp_RpcBindingFree
0x140055f17  nop     dword ptr [rax+rax+00h]
0x140055f1c  mov     cs:SrvXsRpcBindingHandle, 0
0x140055f27  mov     [rsp+0E8h+var_C8], 0
0x140055f2f  lea     rcx, SrvXsResource; Resource
0x140055f36  call    cs:__imp_ExReleaseResourceLite
0x140055f3d  nop     dword ptr [rax+rax+00h]
0x140055f42  call    cs:__imp_KeLeaveCriticalRegion
0x140055f49  nop     dword ptr [rax+rax+00h]
0x140055f4e  mov     eax, edi
0x140055f50  jmp     loc_140055C93
0x1400574b8  push    rbp
0x1400574ba  sub     rsp, 20h
0x1400574be  mov     rbp, rdx
0x1400574c1  mov     rcx, [rcx]
0x1400574c4  mov     ecx, [rcx]; ExceptionCode
0x1400574c6  call    cs:__imp_I_RpcExceptionFilter
0x1400574cd  nop     dword ptr [rax+rax+00h]
0x1400574d2  nop
0x1400574d3  add     rsp, 20h
0x1400574d7  pop     rbp
0x1400574d8  retn
```
