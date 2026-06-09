# RegisterAuthServices(void)

- ea: `0x180003a04`
- end: `0x180003b16`
- name: `?RegisterAuthServices@@YAKXZ`
- size: `274`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180003c6c`

## callees

- `0x180003970`
- `0x180003a04`
- `0x180005438`
- `0x180005518`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180003ac0`
- `RPCRT4!RpcStringFreeW` at `0x180003ac0`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180003ab3`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180003ab3`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x180003a25`
- `RPCRT4!RpcServerInqDefaultPrincNameW` at `0x180003a25`

## pseudocode

```c
__int64 RegisterAuthServices(void)
{
  unsigned int v0; // edi
  int v1; // r8d
  _QWORD *v2; // rcx
  RPC_WSTR v3; // rbx
  int CurrentThreadActivityIdPrefix; // eax
  int v5; // edx
  const wchar_t *v6; // r9
  RPC_WSTR ServerPrincName; // [rsp+40h] [rbp+8h] BYREF

  ServerPrincName = 0;
  v0 = RpcServerInqDefaultPrincNameW(9u, &ServerPrincName);
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = ServerPrincName;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      (unsigned int)&WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v3);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v0 )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 && *((_BYTE *)v2 + 25) >= 2u )
    {
      v5 = 51;
      v6 = L"RpcServerInqDefaultPrincName";
LABEL_15:
      WPP_SF_SD(v2[2], v5, v1, (_DWORD)v6, v0);
    }
  }
  else
  {
    v0 = RpcServerRegisterAuthInfoW(ServerPrincName, 9u, 0, 0);
    RpcStringFreeW(&ServerPrincName);
    ServerPrincName = 0;
    if ( v0 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 52;
        v6 = L"RpcServerRegisterAuthInfo";
        goto LABEL_15;
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180003a04  mov     rax, rsp
0x180003a07  mov     [rax+10h], rbx
0x180003a0b  mov     [rax+18h], rbp
0x180003a0f  push    rdi
0x180003a10  sub     rsp, 30h
0x180003a14  lea     rdx, [rax+8]; PrincName
0x180003a18  mov     qword ptr [rax+8], 0
0x180003a20  mov     ecx, 9; AuthnSvc
0x180003a25  call    cs:__imp_RpcServerInqDefaultPrincNameW
0x180003a2b  mov     edi, eax
0x180003a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a34  lea     rbp, WPP_GLOBAL_Control
0x180003a3b  cmp     rcx, rbp
0x180003a3e  jz      short loc_180003A81
0x180003a40  test    byte ptr [rcx+1Ch], 1
0x180003a44  jz      short loc_180003A81
0x180003a46  cmp     byte ptr [rcx+19h], 2
0x180003a4a  jb      short loc_180003A81
0x180003a4c  mov     rbx, [rsp+38h+ServerPrincName]
0x180003a51  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180003a56  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a5d  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x180003a64  mov     edx, 32h ; '2'
0x180003a69  mov     [rsp+38h+var_18], rbx
0x180003a6e  mov     r9d, eax
0x180003a71  mov     rcx, [rcx+10h]
0x180003a75  call    WPP_SF_DS
0x180003a7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a81  test    edi, edi
0x180003a83  jz      short loc_180003AA4
0x180003a85  cmp     rcx, rbp
0x180003a88  jz      short loc_180003B04
0x180003a8a  test    byte ptr [rcx+1Ch], 8
0x180003a8e  jz      short loc_180003B04
0x180003a90  cmp     byte ptr [rcx+19h], 2
0x180003a94  jb      short loc_180003B04
0x180003a96  mov     edx, 33h ; '3'
0x180003a9b  lea     r9, aRpcserverinqde; "RpcServerInqDefaultPrincName"
0x180003aa2  jmp     short loc_180003AF7
0x180003aa4  mov     rcx, [rsp+38h+ServerPrincName]; ServerPrincName
0x180003aa9  xor     r9d, r9d; Arg
0x180003aac  xor     r8d, r8d; GetKeyFn
0x180003aaf  lea     edx, [r9+9]; AuthnSvc
0x180003ab3  call    cs:__imp_RpcServerRegisterAuthInfoW
0x180003ab9  lea     rcx, [rsp+38h+ServerPrincName]; String
0x180003abe  mov     edi, eax
0x180003ac0  call    cs:__imp_RpcStringFreeW
0x180003ac6  mov     [rsp+38h+ServerPrincName], 0
0x180003acf  test    edi, edi
0x180003ad1  jz      short loc_180003B04
0x180003ad3  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ada  cmp     rcx, rbp
0x180003add  jz      short loc_180003B04
0x180003adf  test    byte ptr [rcx+1Ch], 8
0x180003ae3  jz      short loc_180003B04
0x180003ae5  cmp     byte ptr [rcx+19h], 2
0x180003ae9  jb      short loc_180003B04
0x180003aeb  mov     edx, 34h ; '4'
0x180003af0  lea     r9, aRpcserverregis; "RpcServerRegisterAuthInfo"
0x180003af7  mov     rcx, [rcx+10h]
0x180003afb  mov     dword ptr [rsp+38h+var_18], edi
0x180003aff  call    WPP_SF_SD
0x180003b04  mov     rbx, [rsp+38h+arg_8]
0x180003b09  mov     eax, edi
0x180003b0b  mov     rbp, [rsp+38h+arg_10]
0x180003b10  add     rsp, 30h
0x180003b14  pop     rdi
0x180003b15  retn
```
