# StopTsgQec(void)

- ea: `0x180003ef8`
- end: `0x180004033`
- name: `?StopTsgQec@@YAKXZ`
- size: `315`
- prototype: `unsigned int(void)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003c6c`
- `0x180004970`
- `0x180005260`

## callees

- `0x180003970`
- `0x180003ef8`
- `0x1800053ec`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIfEx` at `0x180003fda`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180003fda`
- `RPCRT4!RpcBindingVectorFree` at `0x180003f76`
- `RPCRT4!RpcBindingVectorFree` at `0x180003f76`
- `RPCRT4!RpcEpUnregister` at `0x180003f23`
- `RPCRT4!RpcEpUnregister` at `0x180003f23`

## pseudocode

```c
__int64 StopTsgQec(void)
{
  RPC_STATUS v0; // ebx
  int CurrentThreadActivityIdPrefix; // eax
  RPC_STATUS v2; // eax
  RPC_STATUS v3; // ebx
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v8; // [rsp+20h] [rbp-18h]
  RPC_STATUS v9; // [rsp+20h] [rbp-18h]

  if ( g_pQECBindingVector )
  {
    v0 = RpcEpUnregister(qword_18000DE40, g_pQECBindingVector, 0);
    if ( v0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = v0;
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0x2Du,
        &WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids,
        CurrentThreadActivityIdPrefix,
        v9);
    }
    v2 = RpcBindingVectorFree(&g_pQECBindingVector);
    g_pQECBindingVector = 0;
    v3 = v2;
    if ( v2
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v8) = v3;
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Eu, &WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids, v4, v8);
    }
  }
  v5 = RpcServerUnregisterIfEx(qword_18000DE40, 0, 1);
  if ( v5
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v8) = v5;
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Fu, &WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids, v6, v8);
  }
  return v5;
}

```

## disassembly

```asm
0x180003ef8  mov     [rsp+arg_0], rbx
0x180003efd  push    rbp
0x180003efe  sub     rsp, 30h
0x180003f02  mov     rdx, cs:?g_pQECBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA; BindingVector
0x180003f09  lea     rbp, WPP_GLOBAL_Control
0x180003f10  test    rdx, rdx
0x180003f13  jz      loc_180003FCD
0x180003f19  xor     r8d, r8d; UuidVector
0x180003f1c  lea     rcx, qword_18000DE40; IfSpec
0x180003f23  call    cs:__imp_RpcEpUnregister
0x180003f29  mov     ebx, eax
0x180003f2b  test    eax, eax
0x180003f2d  jz      short loc_180003F6F
0x180003f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f36  cmp     rcx, rbp
0x180003f39  jz      short loc_180003F6F
0x180003f3b  test    byte ptr [rcx+1Ch], 1
0x180003f3f  jz      short loc_180003F6F
0x180003f41  cmp     byte ptr [rcx+19h], 2
0x180003f45  jb      short loc_180003F6F
0x180003f47  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180003f4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f53  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x180003f5a  mov     edx, 2Dh ; '-'
0x180003f5f  mov     dword ptr [rsp+38h+var_18], ebx
0x180003f63  mov     r9d, eax
0x180003f66  mov     rcx, [rcx+10h]
0x180003f6a  call    WPP_SF_Dd
0x180003f6f  lea     rcx, ?g_pQECBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA; BindingVector
0x180003f76  call    cs:__imp_RpcBindingVectorFree
0x180003f7c  mov     cs:?g_pQECBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA, 0; _RPC_BINDING_VECTOR * g_pQECBindingVector
0x180003f87  mov     ebx, eax
0x180003f89  test    eax, eax
0x180003f8b  jz      short loc_180003FCD
0x180003f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f94  cmp     rcx, rbp
0x180003f97  jz      short loc_180003FCD
0x180003f99  test    byte ptr [rcx+1Ch], 1
0x180003f9d  jz      short loc_180003FCD
0x180003f9f  cmp     byte ptr [rcx+19h], 2
0x180003fa3  jb      short loc_180003FCD
0x180003fa5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180003faa  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fb1  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x180003fb8  mov     edx, 2Eh ; '.'
0x180003fbd  mov     dword ptr [rsp+38h+var_18], ebx
0x180003fc1  mov     r9d, eax
0x180003fc4  mov     rcx, [rcx+10h]
0x180003fc8  call    WPP_SF_Dd
0x180003fcd  xor     edx, edx; MgrTypeUuid
0x180003fcf  lea     rcx, qword_18000DE40; IfSpec
0x180003fd6  lea     r8d, [rdx+1]; RundownContextHandles
0x180003fda  call    cs:__imp_RpcServerUnregisterIfEx
0x180003fe0  mov     ebx, eax
0x180003fe2  test    eax, eax
0x180003fe4  jz      short loc_180004026
0x180003fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fed  cmp     rcx, rbp
0x180003ff0  jz      short loc_180004026
0x180003ff2  test    byte ptr [rcx+1Ch], 1
0x180003ff6  jz      short loc_180004026
0x180003ff8  cmp     byte ptr [rcx+19h], 2
0x180003ffc  jb      short loc_180004026
0x180003ffe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180004003  mov     rcx, cs:WPP_GLOBAL_Control
0x18000400a  lea     r8, WPP_083a1ad08f423aa06f8910225f9f0303_Traceguids
0x180004011  mov     edx, 2Fh ; '/'
0x180004016  mov     dword ptr [rsp+38h+var_18], ebx
0x18000401a  mov     r9d, eax
0x18000401d  mov     rcx, [rcx+10h]
0x180004021  call    WPP_SF_Dd
0x180004026  mov     eax, ebx
0x180004028  mov     rbx, [rsp+38h+arg_0]
0x18000402d  add     rsp, 30h
0x180004031  pop     rbp
0x180004032  retn
```
