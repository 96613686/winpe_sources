# LB_RPCHTTP_SERVER::SubmitPingRequests(void)

- ea: `0x180023428`
- end: `0x18002367f`
- name: `?SubmitPingRequests@LB_RPCHTTP_SERVER@@AEAAJXZ`
- size: `599`
- prototype: `__int64 __fastcall(LB_RPCHTTP_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002330c`

## callees

- `0x18001f984`
- `0x18001fbdc`
- `0x180023428`
- `0x180024640`

## import_xrefs

- `ntdll!_itow_s` at `0x1800234b7`
- `ntdll!_itow_s` at `0x1800234b7`
- `KERNEL32!CreateEventW` at `0x1800235ab`
- `KERNEL32!CreateEventW` at `0x1800235ab`
- `RPCRT4!I_RpcFree` at `0x180023580`
- `RPCRT4!I_RpcFree` at `0x180023580`
- `RPCRT4!RpcBindingFree` at `0x18002358d`
- `RPCRT4!RpcBindingFree` at `0x1800235c1`
- `RPCRT4!RpcBindingFree` at `0x18002364a`
- `RPCRT4!RpcBindingFree` at `0x18002358d`
- `RPCRT4!RpcBindingFree` at `0x1800235c1`
- `RPCRT4!RpcBindingFree` at `0x18002364a`
- `RPCRT4!NdrAsyncClientCall` at `0x1800235ee`
- `RPCRT4!NdrAsyncClientCall` at `0x180023606`
- `RPCRT4!NdrAsyncClientCall` at `0x1800235ee`
- `RPCRT4!NdrAsyncClientCall` at `0x180023606`
- `RPCRT4!RpcStringFreeW` at `0x18002350b`
- `RPCRT4!RpcStringFreeW` at `0x18002350b`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180023575`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180023575`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800234de`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800234de`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800234fe`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800234fe`
- `RPCRT4!RpcExceptionFilter` at `0x180024796`
- `RPCRT4!RpcExceptionFilter` at `0x180024796`

## pseudocode

```c
__int64 __fastcall LB_RPCHTTP_SERVER::SubmitPingRequests(LB_RPCHTTP_SERVER *this)
{
  _DWORD *v2; // r15
  _DWORD *v4; // r14
  unsigned __int16 *v5; // r9
  RPC_BINDING_HANDLE *v6; // r12
  RPC_STATUS v7; // ebx
  unsigned __int16 *SPN; // r13
  RPC_STATUS v9; // ebx
  HANDLE EventW; // rax
  __int64 v11; // r9
  char *v12; // r8
  RPC_WSTR String[4]; // [rsp+40h] [rbp-78h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+60h] [rbp-58h] BYREF
  wchar_t Buffer[8]; // [rsp+70h] [rbp-48h] BYREF

  String[1] = (RPC_WSTR)this;
  String[0] = 0;
  SecurityQOS = 0;
  v2 = (_DWORD *)((char *)this + 192);
  String[2] = (RPC_WSTR)((char *)this + 192);
  if ( *((_DWORD *)this + 48) == 1 )
    return 0;
  v4 = (_DWORD *)((char *)this + 200);
  String[3] = (RPC_WSTR)((char *)this + 200);
  if ( !*((_DWORD *)this + 50) )
  {
    if ( *((_WORD *)this + 17) )
    {
      _itow_s(*((unsigned __int16 *)this + 17), Buffer, 6u, 10);
      v5 = Buffer;
    }
    else
    {
      v5 = 0;
    }
    if ( RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_ip_tcp", *((RPC_WSTR *)this + 3), v5, 0, String) )
      return 14;
    v6 = (RPC_BINDING_HANDLE *)((char *)this + 72);
    v7 = RpcBindingFromStringBindingW(String[0], (RPC_BINDING_HANDLE *)this + 9);
    RpcStringFreeW(String);
    if ( v7 )
    {
      *v6 = 0;
      return 14;
    }
    if ( !LODWORD(g_pConfigurationManager[1].LockSemaphore) )
    {
      SecurityQOS.Version = 1;
      *(_QWORD *)&SecurityQOS.Capabilities = 1;
      SecurityQOS.ImpersonationType = 2;
      SPN = CreateSPN(*((unsigned __int16 **)this + 3));
      if ( !SPN || (v9 = RpcBindingSetAuthInfoExW(*v6, SPN, 6u, 9u, 0, 0, &SecurityQOS), I_RpcFree(SPN), v9) )
      {
        RpcBindingFree((RPC_BINDING_HANDLE *)this + 9);
        return 14;
      }
    }
  }
  if ( *((_QWORD *)this + 16) || (EventW = CreateEventW(0, 0, 0, 0), (*((_QWORD *)this + 16) = EventW) != 0) )
  {
    v11 = *((_QWORD *)this + 9);
    v12 = (char *)this + 80;
    if ( *v4 )
      NdrAsyncClientCall(&pStubDescriptor, &byte_180028906, v12, v11);
    else
      NdrAsyncClientCall(&pStubDescriptor, &byte_1800288E2, v12, v11, (char *)this + 36);
    LB_RPCHTTP_SERVER::AddReference(this);
    *((_DWORD *)this + 49) = 10;
    *v2 = 1;
    return 0;
  }
  else
  {
    RpcBindingFree((RPC_BINDING_HANDLE *)this + 9);
    return 1721;
  }
}

```

## disassembly

```asm
0x180023428  mov     [rsp+arg_8], rbx
0x18002342d  mov     [rsp+arg_10], rsi
0x180023432  push    rdi
0x180023433  push    r12
0x180023435  push    r13
0x180023437  push    r14
0x180023439  push    r15
0x18002343b  sub     rsp, 90h
0x180023442  mov     rax, cs:__security_cookie
0x180023449  xor     rax, rsp
0x18002344c  mov     [rsp+0B8h+var_38], rax
0x180023454  mov     rsi, rcx
0x180023457  mov     [rsp+0B8h+var_70], rcx
0x18002345c  xor     edi, edi
0x18002345e  mov     [rsp+0B8h+String], rdi
0x180023463  xorps   xmm0, xmm0
0x180023466  movups  xmmword ptr [rsp+0B8h+var_58.Version], xmm0
0x18002346b  lea     r15, [rcx+0C0h]
0x180023472  mov     [rsp+0B8h+var_68], r15
0x180023477  cmp     dword ptr [r15], 1
0x18002347b  jnz     short loc_180023484
0x18002347d  xor     eax, eax
0x18002347f  jmp     loc_180023652
0x180023484  lea     r14, [rcx+0C8h]
0x18002348b  mov     [rsp+0B8h+var_60], r14
0x180023490  cmp     [r14], edi
0x180023493  jnz     loc_180023598
0x180023499  cmp     [rcx+22h], di
0x18002349d  jnz     short loc_1800234A4
0x18002349f  mov     r9, rdi
0x1800234a2  jmp     short loc_1800234C2
0x1800234a4  movzx   ecx, word ptr [rcx+22h]; Value
0x1800234a8  mov     r9d, 0Ah; Radix
0x1800234ae  lea     r8d, [r9-4]; BufferCount
0x1800234b2  lea     rdx, [rsp+0B8h+Buffer]; Buffer
0x1800234b7  call    cs:__imp__itow_s
0x1800234bd  lea     r9, [rsp+0B8h+Buffer]; Endpoint
0x1800234c2  lea     rax, [rsp+0B8h+String]
0x1800234c7  mov     [rsp+0B8h+StringBinding], rax; StringBinding
0x1800234cc  mov     [rsp+0B8h+Options], rdi; Options
0x1800234d1  mov     r8, [rsi+18h]; NetworkAddr
0x1800234d5  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x1800234dc  xor     ecx, ecx; ObjUuid
0x1800234de  call    cs:__imp_RpcStringBindingComposeW
0x1800234e4  test    eax, eax
0x1800234e6  jz      short loc_1800234F2
0x1800234e8  mov     eax, 0Eh
0x1800234ed  jmp     loc_180023652
0x1800234f2  lea     r12, [rsi+48h]
0x1800234f6  mov     rdx, r12; Binding
0x1800234f9  mov     rcx, [rsp+0B8h+String]; StringBinding
0x1800234fe  call    cs:__imp_RpcBindingFromStringBindingW
0x180023504  mov     ebx, eax
0x180023506  lea     rcx, [rsp+0B8h+String]; String
0x18002350b  call    cs:__imp_RpcStringFreeW
0x180023511  test    ebx, ebx
0x180023513  jz      short loc_18002351B
0x180023515  mov     [r12], rdi
0x180023519  jmp     short loc_1800234E8
0x18002351b  mov     rax, cs:?g_pConfigurationManager@@3PEAVLB_CONFIGURATION_MANAGER@@EA; LB_CONFIGURATION_MANAGER * g_pConfigurationManager
0x180023522  cmp     [rax+40h], edi
0x180023525  jnz     short loc_180023598
0x180023527  mov     [rsp+0B8h+var_58.Version], 1
0x18002352f  mov     qword ptr [rsp+0B8h+var_58.Capabilities], 1
0x180023538  mov     [rsp+0B8h+var_58.ImpersonationType], 2
0x180023540  mov     rcx, [rsi+18h]; Src
0x180023544  call    ?CreateSPN@@YAPEAGPEAG@Z; CreateSPN(ushort *)
0x180023549  mov     r13, rax
0x18002354c  test    rax, rax
0x18002354f  jz      short loc_18002358A
0x180023551  lea     rax, [rsp+0B8h+var_58]
0x180023556  mov     [rsp+0B8h+SecurityQOS], rax; SecurityQOS
0x18002355b  mov     dword ptr [rsp+0B8h+StringBinding], edi; AuthzSvc
0x18002355f  mov     [rsp+0B8h+Options], rdi; AuthIdentity
0x180023564  mov     r9d, 9; AuthnSvc
0x18002356a  lea     r8d, [r9-3]; AuthnLevel
0x18002356e  mov     rdx, r13; ServerPrincName
0x180023571  mov     rcx, [r12]; Binding
0x180023575  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18002357b  mov     ebx, eax
0x18002357d  mov     rcx, r13; Object
0x180023580  call    cs:__imp_I_RpcFree
0x180023586  test    ebx, ebx
0x180023588  jz      short loc_180023598
0x18002358a  mov     rcx, r12; Binding
0x18002358d  call    cs:__imp_RpcBindingFree
0x180023593  jmp     loc_1800234E8
0x180023598  cmp     [rsi+80h], rdi
0x18002359f  jnz     short loc_1800235D1
0x1800235a1  xor     r9d, r9d; lpName
0x1800235a4  xor     r8d, r8d; bInitialState
0x1800235a7  xor     edx, edx; bManualReset
0x1800235a9  xor     ecx, ecx; lpEventAttributes
0x1800235ab  call    cs:__imp_CreateEventW
0x1800235b1  mov     [rsi+80h], rax
0x1800235b8  test    rax, rax
0x1800235bb  jnz     short loc_1800235D1
0x1800235bd  lea     rcx, [rsi+48h]; Binding
0x1800235c1  call    cs:__imp_RpcBindingFree
0x1800235c7  mov     eax, 6B9h
0x1800235cc  jmp     loc_180023652
0x1800235d1  mov     ebx, edi
0x1800235d3  mov     r9, [rsi+48h]
0x1800235d7  lea     r8, [rsi+50h]
0x1800235db  lea     rcx, pStubDescriptor; pStubDescriptor
0x1800235e2  cmp     [r14], edi
0x1800235e5  jz      short loc_1800235F6
0x1800235e7  lea     rdx, byte_180028906; pFormat
0x1800235ee  call    cs:__imp_NdrAsyncClientCall
0x1800235f4  jmp     short loc_18002360C
0x1800235f6  lea     rax, [rsi+24h]
0x1800235fa  mov     [rsp+0B8h+Options], rax
0x1800235ff  lea     rdx, byte_1800288E2; pFormat
0x180023606  call    cs:__imp_NdrAsyncClientCall
0x18002360c  jmp     short loc_180023621
0x18002360e  mov     ebx, eax
0x180023610  xor     edi, edi
0x180023612  mov     rsi, [rsp+0B8h+var_70]
0x180023617  mov     r15, [rsp+0B8h+var_68]
0x18002361c  mov     r14, [rsp+0B8h+var_60]
0x180023621  test    ebx, ebx
0x180023623  jnz     short loc_180023640
0x180023625  mov     rcx, rsi; this
0x180023628  call    ?AddReference@LB_RPCHTTP_SERVER@@QEAAXXZ; LB_RPCHTTP_SERVER::AddReference(void)
0x18002362d  mov     dword ptr [rsi+0C4h], 0Ah
0x180023637  mov     dword ptr [r15], 1
0x18002363e  jmp     short loc_180023650
0x180023640  mov     [r15], edi
0x180023643  mov     [r14], edi
0x180023646  lea     rcx, [rsi+48h]; Binding
0x18002364a  call    cs:__imp_RpcBindingFree
0x180023650  mov     eax, ebx
0x180023652  mov     rcx, [rsp+0B8h+var_38]
0x18002365a  xor     rcx, rsp; StackCookie
0x18002365d  call    __security_check_cookie
0x180023662  lea     r11, [rsp+0B8h+var_28]
0x18002366a  mov     rbx, [r11+38h]
0x18002366e  mov     rsi, [r11+40h]
0x180023672  mov     rsp, r11
0x180023675  pop     r15
0x180023677  pop     r14
0x180023679  pop     r13
0x18002367b  pop     r12
0x18002367d  pop     rdi
0x18002367e  retn
0x180024788  push    rbp
0x18002478a  sub     rsp, 40h
0x18002478e  mov     rbp, rdx
0x180024791  mov     rcx, [rcx]
0x180024794  mov     ecx, [rcx]; ExceptionCode
0x180024796  call    cs:__imp_RpcExceptionFilter
0x18002479c  nop
0x18002479d  add     rsp, 40h
0x1800247a1  pop     rbp
0x1800247a2  retn
```
