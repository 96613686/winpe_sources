# s_LockDevice

- ea: `0x180002c40`
- end: `0x180002d60`
- name: `s_LockDevice`
- size: `288`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001e04`
- `0x180002148`
- `0x1800026e0`
- `0x180002c40`
- `0x180004010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002d4d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002d4d`
- `ntdll!RtlNtStatusToDosError` at `0x180002c77`
- `ntdll!RtlNtStatusToDosError` at `0x180002c77`
- `RPCRT4!RpcImpersonateClient` at `0x180002c4c`
- `RPCRT4!RpcImpersonateClient` at `0x180002c4c`

## pseudocode

```c
__int64 s_LockDevice()
{
  RPC_STATUS v0; // eax
  unsigned int v1; // ebx
  NTSTATUS v2; // eax
  signed int v3; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  int v7; // eax

  v0 = RpcImpersonateClient(0);
  v1 = v0;
  if ( !v0 )
  {
    v2 = WepCheckCallerPrivilege();
    if ( v2 )
    {
      v3 = RtlNtStatusToDosError(v2);
      v1 = v3;
      if ( v3 > 0 )
        v1 = (unsigned __int16)v3 | 0x80070000;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_21;
      v5 = 17;
      v6 = v1;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
      v7 = ((__int64 (*)(void))xmmword_180008718)();
      v1 = v7;
      if ( v7 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
        goto LABEL_21;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_21:
        RevertToSelf();
        return v1;
      }
      v5 = 19;
      v6 = (unsigned int)v7;
    }
    WPP_SF_D(v4[2], v5, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids, v6);
    goto LABEL_21;
  }
  if ( v0 >= 0 )
    return (unsigned __int16)v0 | 0x80010000;
  return v1;
}

```

## disassembly

```asm
0x180002c40  mov     [rsp+arg_0], rbx
0x180002c45  push    rdi
0x180002c46  sub     rsp, 20h
0x180002c4a  xor     ecx, ecx; BindingHandle
0x180002c4c  call    cs:__imp_RpcImpersonateClient
0x180002c52  mov     ebx, eax
0x180002c54  test    eax, eax
0x180002c56  jz      short loc_180002C6C
0x180002c58  js      loc_180002D53
0x180002c5e  movzx   ebx, ax
0x180002c61  or      ebx, 80010000h
0x180002c67  jmp     loc_180002D53
0x180002c6c  call    ?WepCheckCallerPrivilege@@YAJK@Z; WepCheckCallerPrivilege(ulong)
0x180002c71  test    eax, eax
0x180002c73  jz      short loc_180002CCA
0x180002c75  mov     ecx, eax; Status
0x180002c77  call    cs:__imp_RtlNtStatusToDosError
0x180002c7d  mov     ebx, eax
0x180002c7f  test    eax, eax
0x180002c81  jle     short loc_180002C8C
0x180002c83  movzx   ebx, ax
0x180002c86  or      ebx, 80070000h
0x180002c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c93  lea     rdi, WPP_GLOBAL_Control
0x180002c9a  cmp     rcx, rdi
0x180002c9d  jz      loc_180002D4D
0x180002ca3  test    byte ptr [rcx+1Ch], 1
0x180002ca7  jz      loc_180002D4D
0x180002cad  mov     edx, 11h
0x180002cb2  mov     r9d, ebx
0x180002cb5  mov     rcx, [rcx+10h]
0x180002cb9  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002cc0  call    WPP_SF_D
0x180002cc5  jmp     loc_180002D4D
0x180002cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cd1  lea     rdi, WPP_GLOBAL_Control
0x180002cd8  cmp     rcx, rdi
0x180002cdb  jz      short loc_180002CF8
0x180002cdd  test    byte ptr [rcx+1Ch], 20h
0x180002ce1  jz      short loc_180002CF8
0x180002ce3  mov     rcx, [rcx+10h]
0x180002ce7  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002cee  mov     edx, 12h
0x180002cf3  call    WPP_SF_
0x180002cf8  mov     rax, qword ptr cs:xmmword_180008718
0x180002cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d04  mov     ebx, eax
0x180002d06  test    eax, eax
0x180002d08  jns     short loc_180002D26
0x180002d0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d11  cmp     rcx, rdi
0x180002d14  jz      short loc_180002D4D
0x180002d16  test    byte ptr [rcx+1Ch], 1
0x180002d1a  jz      short loc_180002D4D
0x180002d1c  mov     edx, 13h
0x180002d21  mov     r9d, eax
0x180002d24  jmp     short loc_180002CB5
0x180002d26  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d2d  cmp     rcx, rdi
0x180002d30  jz      short loc_180002D4D
0x180002d32  test    byte ptr [rcx+1Ch], 20h
0x180002d36  jz      short loc_180002D4D
0x180002d38  mov     rcx, [rcx+10h]
0x180002d3c  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002d43  mov     edx, 14h
0x180002d48  call    WPP_SF_
0x180002d4d  call    cs:__imp_RevertToSelf
0x180002d53  mov     eax, ebx
0x180002d55  mov     rbx, [rsp+28h+arg_0]
0x180002d5a  add     rsp, 20h
0x180002d5e  pop     rdi
0x180002d5f  retn
```
