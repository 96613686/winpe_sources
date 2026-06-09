# SrvGrovelerConnect

- ea: `0x140047ae4`
- end: `0x140047e8f`
- name: `SrvGrovelerConnect`
- size: `939`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140048020`

## callees

- `0x14001389c`
- `0x140015790`
- `0x14002a3e0`
- `0x140047ae4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140047b93`
- `ntoskrnl!KeGetCurrentIrql` at `0x140047b93`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047b80`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047e5b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047b80`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047e5b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140047b58`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140047b58`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140047b3d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140047b3d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140047b74`
- `ntoskrnl!ExReleaseResourceLite` at `0x140047e4f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140047b74`
- `ntoskrnl!ExReleaseResourceLite` at `0x140047e4f`
- `msrpc!RpcBindingSetOption` at `0x140047ce2`
- `msrpc!RpcBindingSetOption` at `0x140047ce2`
- `msrpc!RpcBindingFree` at `0x140047d37`
- `msrpc!RpcBindingFree` at `0x140047db8`
- `msrpc!RpcBindingFree` at `0x140047e29`
- `msrpc!RpcBindingFree` at `0x140047d37`
- `msrpc!RpcBindingFree` at `0x140047db8`
- `msrpc!RpcBindingFree` at `0x140047e29`
- `msrpc!RpcBindingBind` at `0x140047d63`
- `msrpc!RpcBindingBind` at `0x140047d63`
- `msrpc!RpcBindingCreateW` at `0x140047c7b`
- `msrpc!RpcBindingCreateW` at `0x140047c7b`

## pseudocode

```c
__int64 SrvGrovelerConnect()
{
  unsigned int v1; // ebx
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-A0h] BYREF
  __int128 v3; // [rsp+50h] [rbp-78h] BYREF
  __int128 v4; // [rsp+60h] [rbp-68h]
  __int64 *v5; // [rsp+70h] [rbp-58h]
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+78h] [rbp-50h] BYREF

  memset(&Template, 0, sizeof(Template));
  v3 = 0;
  v4 = 0;
  v5 = 0;
  memset(&Security, 0, 36);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&SrvGrovelerResource, 1u);
  if ( SrvGrovelerStatus == 2 )
  {
    ExReleaseResourceLite(&SrvGrovelerResource);
    KeLeaveCriticalRegion();
    return 0;
  }
  if ( !KeGetCurrentIrql() )
  {
    *(_QWORD *)&Template.ProtocolSequence = 3;
    *(_QWORD *)&Template.Version = 1;
    memset(&Template.NetworkAddress, 0, 40);
    v4 = 0;
    LODWORD(v3) = 3;
    *(_QWORD *)((char *)&v3 + 4) = 1;
    HIDWORD(v3) = 3;
    v5 = LocalSystem;
    *(_QWORD *)(&Security.Version + 1) = 0;
    HIDWORD(Security.ServerPrincName) = 0;
    Security.AuthIdentity = 0;
    Security.Version = 1;
    Security.AuthnLevel = 6;
    Security.AuthnSvc = 10;
    Security.SecurityQos = (RPC_SECURITY_QOS *)&v3;
    v1 = RpcBindingCreateW(&Template, &Security, 0, &SrvGrovelerRpcBindingHandle);
    if ( v1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids, v1);
      }
      goto LABEL_28;
    }
    v1 = RpcBindingSetOption(SrvGrovelerRpcBindingHandle, 9u, 1u);
    if ( v1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids, v1);
      }
    }
    else
    {
      v1 = RpcBindingBind(0, SrvGrovelerRpcBindingHandle, qword_14002EC70);
      if ( !v1 )
      {
        SrvGrovelerStatus = 2;
        goto LABEL_28;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids, v1);
      }
    }
    RpcBindingFree(&SrvGrovelerRpcBindingHandle);
    SrvGrovelerRpcBindingHandle = 0;
LABEL_28:
    ExReleaseResourceLite(&SrvGrovelerResource);
    KeLeaveCriticalRegion();
    return v1;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids);
  }
  return 3221225701LL;
}

```

## disassembly

```asm
0x140047ae4  mov     r11, rsp
0x140047ae7  mov     [r11+8], rbx
0x140047aeb  mov     [r11+10h], rsi
0x140047aef  push    rdi
0x140047af0  sub     rsp, 0C0h
0x140047af7  mov     rax, cs:__security_cookie
0x140047afe  xor     rax, rsp
0x140047b01  mov     [rsp+0C8h+var_18], rax
0x140047b09  xorps   xmm0, xmm0
0x140047b0c  xor     eax, eax
0x140047b0e  movups  xmmword ptr [rsp+0C8h+Template.Version], xmm0
0x140047b13  movups  xmmword ptr [r11-40h], xmm0
0x140047b18  movups  xmmword ptr [r11-30h], xmm0
0x140047b1d  mov     [r11-20h], rax
0x140047b21  movups  [rsp+0C8h+var_78], xmm0
0x140047b26  movups  [rsp+0C8h+var_68], xmm0
0x140047b2b  mov     [r11-58h], rax
0x140047b2f  movups  xmmword ptr [rsp+0C8h+Security.Version], xmm0
0x140047b34  movups  xmmword ptr [rsp+0C8h+Security.AuthnLevel], xmm0
0x140047b39  mov     dword ptr [rsp+0C8h+Security.SecurityQos], eax
0x140047b3d  call    cs:__imp_KeEnterCriticalRegion
0x140047b44  nop     dword ptr [rax+rax+00h]
0x140047b49  mov     esi, 1
0x140047b4e  mov     dl, sil; Wait
0x140047b51  lea     rcx, SrvGrovelerResource; Resource
0x140047b58  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140047b5f  nop     dword ptr [rax+rax+00h]
0x140047b64  cmp     cs:SrvGrovelerStatus, 2
0x140047b6b  jnz     short loc_140047B93
0x140047b6d  lea     rcx, SrvGrovelerResource; Resource
0x140047b74  call    cs:__imp_ExReleaseResourceLite
0x140047b7b  nop     dword ptr [rax+rax+00h]
0x140047b80  call    cs:__imp_KeLeaveCriticalRegion
0x140047b87  nop     dword ptr [rax+rax+00h]
0x140047b8c  xor     eax, eax
0x140047b8e  jmp     loc_140047E69
0x140047b93  call    cs:__imp_KeGetCurrentIrql
0x140047b9a  nop     dword ptr [rax+rax+00h]
0x140047b9f  xor     edi, edi
0x140047ba1  test    al, al
0x140047ba3  jz      short loc_140047BE2
0x140047ba5  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140047bac  mov     rcx, cs:WPP_GLOBAL_Control
0x140047bb3  cmp     rcx, rax
0x140047bb6  jz      short loc_140047BD8
0x140047bb8  mov     eax, [rcx+2Ch]
0x140047bbb  test    al, 10h
0x140047bbd  jz      short loc_140047BD8
0x140047bbf  cmp     [rcx+29h], sil
0x140047bc3  jb      short loc_140047BD8
0x140047bc5  lea     edx, [rdi+0Ah]
0x140047bc8  lea     r8, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids
0x140047bcf  mov     rcx, [rcx+18h]
0x140047bd3  call    WPP_SF_
0x140047bd8  mov     eax, 0C00000E5h
0x140047bdd  jmp     loc_140047E69
0x140047be2  mov     [rsp+0C8h+var_A8], edi
0x140047be6  mov     qword ptr [rsp+0C8h+Template.ProtocolSequence], 3
0x140047bf2  xorps   xmm0, xmm0
0x140047bf5  movdqu  xmmword ptr [rsp+0C8h+Template.ObjectUuid.Data1], xmm0
0x140047bfe  mov     qword ptr [rsp+0C8h+Template.Version], rsi
0x140047c03  mov     eax, 3
0x140047c08  movdqu  xmmword ptr [rsp+0C8h+Template.NetworkAddress], xmm0
0x140047c11  mov     qword ptr [rsp+0C8h+Template.u1], rdi
0x140047c19  xorps   xmm1, xmm1
0x140047c1c  movdqu  [rsp+0C8h+var_68], xmm1
0x140047c22  mov     dword ptr [rsp+0C8h+var_78], eax
0x140047c26  mov     qword ptr [rsp+0C8h+var_78+4], rsi
0x140047c2b  mov     dword ptr [rsp+0C8h+var_78+0Ch], eax
0x140047c2f  lea     rax, LocalSystem
0x140047c36  mov     [rsp+0C8h+var_58], rax
0x140047c3b  mov     qword ptr [rsp+0C8h+Security+4], rdi
0x140047c40  mov     dword ptr [rsp+0C8h+Security.ServerPrincName+4], edi
0x140047c44  mov     [rsp+0C8h+Security.AuthIdentity], rdi
0x140047c49  mov     [rsp+0C8h+Security.Version], esi
0x140047c4d  mov     [rsp+0C8h+Security.AuthnLevel], 6
0x140047c55  mov     [rsp+0C8h+Security.AuthnSvc], 0Ah
0x140047c5d  lea     rax, [rsp+0C8h+var_78]
0x140047c62  mov     [rsp+0C8h+Security.SecurityQos], rax
0x140047c67  lea     r9, SrvGrovelerRpcBindingHandle; Binding
0x140047c6e  xor     r8d, r8d; Options
0x140047c71  lea     rdx, [rsp+0C8h+Security]; Security
0x140047c76  lea     rcx, [rsp+0C8h+Template]; Template
0x140047c7b  call    cs:__imp_RpcBindingCreateW
0x140047c82  nop     dword ptr [rax+rax+00h]
0x140047c87  mov     ebx, eax
0x140047c89  mov     [rsp+0C8h+var_A4], eax
0x140047c8d  test    eax, eax
0x140047c8f  jz      short loc_140047CCF
0x140047c91  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140047c98  mov     rcx, cs:WPP_GLOBAL_Control
0x140047c9f  cmp     rcx, rax
0x140047ca2  jz      short loc_140047CCA
0x140047ca4  mov     edx, [rcx+2Ch]
0x140047ca7  test    dl, 10h
0x140047caa  jz      short loc_140047CCA
0x140047cac  cmp     [rcx+29h], sil
0x140047cb0  jb      short loc_140047CCA
0x140047cb2  mov     edx, 0Bh
0x140047cb7  mov     r9d, ebx
0x140047cba  lea     r8, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids
0x140047cc1  mov     rcx, [rcx+18h]
0x140047cc5  call    WPP_SF_d
0x140047cca  jmp     loc_140047E48
0x140047ccf  mov     [rsp+0C8h+var_A8], esi
0x140047cd3  mov     r8, rsi; optionValue
0x140047cd6  mov     edx, 9; option
0x140047cdb  mov     rcx, cs:SrvGrovelerRpcBindingHandle; hBinding
0x140047ce2  call    cs:__imp_RpcBindingSetOption
0x140047ce9  nop     dword ptr [rax+rax+00h]
0x140047cee  mov     ebx, eax
0x140047cf0  mov     [rsp+0C8h+var_A4], eax
0x140047cf4  test    eax, eax
0x140047cf6  jz      short loc_140047D53
0x140047cf8  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140047cff  mov     rcx, cs:WPP_GLOBAL_Control
0x140047d06  cmp     rcx, rax
0x140047d09  jz      short loc_140047D30
0x140047d0b  mov     eax, [rcx+2Ch]
0x140047d0e  test    al, 10h
0x140047d10  jz      short loc_140047D30
0x140047d12  cmp     [rcx+29h], sil
0x140047d16  jb      short loc_140047D30
0x140047d18  mov     edx, 0Ch
0x140047d1d  mov     r9d, ebx
0x140047d20  lea     r8, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids
0x140047d27  mov     rcx, [rcx+18h]
0x140047d2b  call    WPP_SF_d
0x140047d30  lea     rcx, SrvGrovelerRpcBindingHandle; Binding
0x140047d37  call    cs:__imp_RpcBindingFree
0x140047d3e  nop     dword ptr [rax+rax+00h]
0x140047d43  mov     cs:SrvGrovelerRpcBindingHandle, rdi
0x140047d4a  mov     [rsp+0C8h+var_A8], edi
0x140047d4e  jmp     loc_140047E48
0x140047d53  lea     r8, qword_14002EC70; IfSpec
0x140047d5a  mov     rdx, cs:SrvGrovelerRpcBindingHandle; Binding
0x140047d61  xor     ecx, ecx; pAsync
0x140047d63  call    cs:__imp_RpcBindingBind
0x140047d6a  nop     dword ptr [rax+rax+00h]
0x140047d6f  mov     ebx, eax
0x140047d71  mov     [rsp+0C8h+var_A4], eax
0x140047d75  test    eax, eax
0x140047d77  jz      short loc_140047DD1
0x140047d79  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140047d80  mov     rcx, cs:WPP_GLOBAL_Control
0x140047d87  cmp     rcx, rax
0x140047d8a  jz      short loc_140047DB1
0x140047d8c  mov     eax, [rcx+2Ch]
0x140047d8f  test    al, 10h
0x140047d91  jz      short loc_140047DB1
0x140047d93  cmp     [rcx+29h], sil
0x140047d97  jb      short loc_140047DB1
0x140047d99  mov     edx, 0Dh
0x140047d9e  mov     r9d, ebx
0x140047da1  lea     r8, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids
0x140047da8  mov     rcx, [rcx+18h]
0x140047dac  call    WPP_SF_d
0x140047db1  lea     rcx, SrvGrovelerRpcBindingHandle; Binding
0x140047db8  call    cs:__imp_RpcBindingFree
0x140047dbf  nop     dword ptr [rax+rax+00h]
0x140047dc4  mov     cs:SrvGrovelerRpcBindingHandle, rdi
0x140047dcb  mov     [rsp+0C8h+var_A8], edi
0x140047dcf  jmp     short loc_140047E48
0x140047dd1  mov     cs:SrvGrovelerStatus, 2
0x140047ddb  jmp     short loc_140047E48
0x140047ddd  mov     ebx, eax
0x140047ddf  mov     [rsp+0C8h+var_A4], eax
0x140047de3  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140047dea  mov     rcx, cs:WPP_GLOBAL_Control
0x140047df1  cmp     rcx, rax
0x140047df4  jz      short loc_140047E1B
0x140047df6  mov     eax, [rcx+2Ch]
0x140047df9  test    al, 10h
0x140047dfb  jz      short loc_140047E1B
0x140047dfd  cmp     byte ptr [rcx+29h], 1
0x140047e01  jb      short loc_140047E1B
0x140047e03  mov     edx, 0Eh
0x140047e08  mov     r9d, ebx
0x140047e0b  lea     r8, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids
0x140047e12  mov     rcx, [rcx+18h]
0x140047e16  call    WPP_SF_d
0x140047e1b  cmp     [rsp+0C8h+var_A8], 0
0x140047e20  jz      short loc_140047E48
0x140047e22  lea     rcx, SrvGrovelerRpcBindingHandle; Binding
0x140047e29  call    cs:__imp_RpcBindingFree
0x140047e30  nop     dword ptr [rax+rax+00h]
0x140047e35  mov     cs:SrvGrovelerRpcBindingHandle, 0
0x140047e40  mov     [rsp+0C8h+var_A8], 0
0x140047e48  lea     rcx, SrvGrovelerResource; Resource
0x140047e4f  call    cs:__imp_ExReleaseResourceLite
0x140047e56  nop     dword ptr [rax+rax+00h]
0x140047e5b  call    cs:__imp_KeLeaveCriticalRegion
0x140047e62  nop     dword ptr [rax+rax+00h]
0x140047e67  mov     eax, ebx
0x140047e69  mov     rcx, [rsp+0C8h+var_18]
0x140047e71  xor     rcx, rsp; StackCookie
0x140047e74  call    __security_check_cookie
0x140047e79  lea     r11, [rsp+0C8h+var_8]
0x140047e81  mov     rbx, [r11+10h]
0x140047e85  mov     rsi, [r11+18h]
0x140047e89  mov     rsp, r11
0x140047e8c  pop     rdi
0x140047e8d  retn
0x1400574e0  push    rbp
0x1400574e2  sub     rsp, 20h
0x1400574e6  mov     rbp, rdx
0x1400574e9  mov     rcx, [rcx]
0x1400574ec  mov     ecx, [rcx]; ExceptionCode
0x1400574ee  call    cs:__imp_I_RpcExceptionFilter
0x1400574f5  nop     dword ptr [rax+rax+00h]
0x1400574fa  nop
0x1400574fb  add     rsp, 20h
0x1400574ff  pop     rbp
0x140057500  retn
```
