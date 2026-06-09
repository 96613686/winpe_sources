# s_DisableDeviceLockoutState

- ea: `0x180002760`
- end: `0x180002868`
- name: `s_DisableDeviceLockoutState`
- size: `264`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001e04`
- `0x180001f58`
- `0x1800026e0`
- `0x180002760`
- `0x180004010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002855`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002855`
- `RPCRT4!RpcImpersonateClient` at `0x18000276c`
- `RPCRT4!RpcImpersonateClient` at `0x18000276c`

## pseudocode

```c
__int64 s_DisableDeviceLockoutState()
{
  RPC_STATUS v0; // eax
  unsigned int v1; // ebx
  int v2; // eax
  _QWORD *v3; // rcx
  __int64 v4; // rdx

  v0 = RpcImpersonateClient(0);
  v1 = v0;
  if ( !v0 )
  {
    v2 = CheckCallerAdminAccess();
    v1 = v2;
    if ( v2 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
      v2 = ((__int64 (*)(void))xmmword_180008728)();
      v1 = v2;
      if ( v2 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
        goto LABEL_19;
      }
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_19:
        RevertToSelf();
        return v1;
      }
      v4 = 36;
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v4 = 34;
    }
    WPP_SF_D(v3[2], v4, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids, (unsigned int)v2);
    goto LABEL_19;
  }
  if ( v0 >= 0 )
    return (unsigned __int16)v0 | 0x80010000;
  return v1;
}

```

## disassembly

```asm
0x180002760  mov     [rsp+arg_0], rbx
0x180002765  push    rdi
0x180002766  sub     rsp, 20h
0x18000276a  xor     ecx, ecx; BindingHandle
0x18000276c  call    cs:__imp_RpcImpersonateClient
0x180002772  mov     ebx, eax
0x180002774  test    eax, eax
0x180002776  jz      short loc_18000278C
0x180002778  js      loc_18000285B
0x18000277e  movzx   ebx, ax
0x180002781  or      ebx, 80010000h
0x180002787  jmp     loc_18000285B
0x18000278c  call    ?CheckCallerAdminAccess@@YAJXZ; CheckCallerAdminAccess(void)
0x180002791  mov     ebx, eax
0x180002793  test    eax, eax
0x180002795  jns     short loc_1800027D5
0x180002797  mov     rcx, cs:WPP_GLOBAL_Control
0x18000279e  lea     rdi, WPP_GLOBAL_Control
0x1800027a5  cmp     rcx, rdi
0x1800027a8  jz      loc_180002855
0x1800027ae  test    byte ptr [rcx+1Ch], 1
0x1800027b2  jz      loc_180002855
0x1800027b8  mov     edx, 22h ; '"'
0x1800027bd  mov     rcx, [rcx+10h]
0x1800027c1  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x1800027c8  mov     r9d, eax
0x1800027cb  call    WPP_SF_D
0x1800027d0  jmp     loc_180002855
0x1800027d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027dc  lea     rdi, WPP_GLOBAL_Control
0x1800027e3  cmp     rcx, rdi
0x1800027e6  jz      short loc_180002803
0x1800027e8  test    byte ptr [rcx+1Ch], 20h
0x1800027ec  jz      short loc_180002803
0x1800027ee  mov     rcx, [rcx+10h]
0x1800027f2  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x1800027f9  mov     edx, 23h ; '#'
0x1800027fe  call    WPP_SF_
0x180002803  mov     rax, qword ptr cs:xmmword_180008728
0x18000280a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000280f  mov     ebx, eax
0x180002811  test    eax, eax
0x180002813  jns     short loc_18000282E
0x180002815  mov     rcx, cs:WPP_GLOBAL_Control
0x18000281c  cmp     rcx, rdi
0x18000281f  jz      short loc_180002855
0x180002821  test    byte ptr [rcx+1Ch], 1
0x180002825  jz      short loc_180002855
0x180002827  mov     edx, 24h ; '$'
0x18000282c  jmp     short loc_1800027BD
0x18000282e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002835  cmp     rcx, rdi
0x180002838  jz      short loc_180002855
0x18000283a  test    byte ptr [rcx+1Ch], 20h
0x18000283e  jz      short loc_180002855
0x180002840  mov     rcx, [rcx+10h]
0x180002844  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x18000284b  mov     edx, 25h ; '%'
0x180002850  call    WPP_SF_
0x180002855  call    cs:__imp_RevertToSelf
0x18000285b  mov     eax, ebx
0x18000285d  mov     rbx, [rsp+28h+arg_0]
0x180002862  add     rsp, 20h
0x180002866  pop     rdi
0x180002867  retn
```
