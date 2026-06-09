# s_ValidateDeviceLockoutState

- ea: `0x180002f90`
- end: `0x1800030b0`
- name: `s_ValidateDeviceLockoutState`
- size: `288`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001e04`
- `0x180002148`
- `0x1800026e0`
- `0x180002f90`
- `0x180004010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000309d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000309d`
- `ntdll!RtlNtStatusToDosError` at `0x180002fc7`
- `ntdll!RtlNtStatusToDosError` at `0x180002fc7`
- `RPCRT4!RpcImpersonateClient` at `0x180002f9c`
- `RPCRT4!RpcImpersonateClient` at `0x180002f9c`

## pseudocode

```c
__int64 s_ValidateDeviceLockoutState()
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
      v5 = 26;
      v6 = v1;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
      v7 = (*((__int64 (**)(void))&xmmword_180008718 + 1))();
      v1 = v7;
      if ( v7 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
        goto LABEL_21;
      }
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_21:
        RevertToSelf();
        return v1;
      }
      v5 = 28;
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
0x180002f90  mov     [rsp+arg_0], rbx
0x180002f95  push    rdi
0x180002f96  sub     rsp, 20h
0x180002f9a  xor     ecx, ecx; BindingHandle
0x180002f9c  call    cs:__imp_RpcImpersonateClient
0x180002fa2  mov     ebx, eax
0x180002fa4  test    eax, eax
0x180002fa6  jz      short loc_180002FBC
0x180002fa8  js      loc_1800030A3
0x180002fae  movzx   ebx, ax
0x180002fb1  or      ebx, 80010000h
0x180002fb7  jmp     loc_1800030A3
0x180002fbc  call    ?WepCheckCallerPrivilege@@YAJK@Z; WepCheckCallerPrivilege(ulong)
0x180002fc1  test    eax, eax
0x180002fc3  jz      short loc_18000301A
0x180002fc5  mov     ecx, eax; Status
0x180002fc7  call    cs:__imp_RtlNtStatusToDosError
0x180002fcd  mov     ebx, eax
0x180002fcf  test    eax, eax
0x180002fd1  jle     short loc_180002FDC
0x180002fd3  movzx   ebx, ax
0x180002fd6  or      ebx, 80070000h
0x180002fdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fe3  lea     rdi, WPP_GLOBAL_Control
0x180002fea  cmp     rcx, rdi
0x180002fed  jz      loc_18000309D
0x180002ff3  test    byte ptr [rcx+1Ch], 1
0x180002ff7  jz      loc_18000309D
0x180002ffd  mov     edx, 1Ah
0x180003002  mov     r9d, ebx
0x180003005  mov     rcx, [rcx+10h]
0x180003009  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180003010  call    WPP_SF_D
0x180003015  jmp     loc_18000309D
0x18000301a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003021  lea     rdi, WPP_GLOBAL_Control
0x180003028  cmp     rcx, rdi
0x18000302b  jz      short loc_180003048
0x18000302d  test    byte ptr [rcx+1Ch], 20h
0x180003031  jz      short loc_180003048
0x180003033  mov     rcx, [rcx+10h]
0x180003037  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x18000303e  mov     edx, 1Bh
0x180003043  call    WPP_SF_
0x180003048  mov     rax, qword ptr cs:xmmword_180008718+8
0x18000304f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003054  mov     ebx, eax
0x180003056  test    eax, eax
0x180003058  jns     short loc_180003076
0x18000305a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003061  cmp     rcx, rdi
0x180003064  jz      short loc_18000309D
0x180003066  test    byte ptr [rcx+1Ch], 1
0x18000306a  jz      short loc_18000309D
0x18000306c  mov     edx, 1Ch
0x180003071  mov     r9d, eax
0x180003074  jmp     short loc_180003005
0x180003076  mov     rcx, cs:WPP_GLOBAL_Control
0x18000307d  cmp     rcx, rdi
0x180003080  jz      short loc_18000309D
0x180003082  test    byte ptr [rcx+1Ch], 20h
0x180003086  jz      short loc_18000309D
0x180003088  mov     rcx, [rcx+10h]
0x18000308c  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180003093  mov     edx, 1Dh
0x180003098  call    WPP_SF_
0x18000309d  call    cs:__imp_RevertToSelf
0x1800030a3  mov     eax, ebx
0x1800030a5  mov     rbx, [rsp+28h+arg_0]
0x1800030aa  add     rsp, 20h
0x1800030ae  pop     rdi
0x1800030af  retn
```
