# I_RpcBindingCreateNP

- ea: `0x1800a2e10`
- end: `0x1800a3066`
- name: `I_RpcBindingCreateNP`
- size: `598`
- prototype: `RPC_STATUS __stdcall(RPC_WSTR ServerName, RPC_WSTR ServiceName, RPC_WSTR NetworkOptions, RPC_BINDING_HANDLE *Binding)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180023020`
- `0x180023a40`
- `0x1800258b4`
- `0x18002e330`
- `0x18002e4f0`
- `0x180086460`
- `0x180086bf0`
- `0x1800a2e10`
- `0x1800cec91`
- `0x1800ceda0`

## import_xrefs

- `ntdll!_wcsnicmp` at `0x1800a2e93`
- `ntdll!_wcsnicmp` at `0x1800a2f89`
- `ntdll!_wcsnicmp` at `0x1800a2fd1`
- `ntdll!_wcsnicmp` at `0x1800a2e93`
- `ntdll!_wcsnicmp` at `0x1800a2f89`
- `ntdll!_wcsnicmp` at `0x1800a2fd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800a2fb0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800a2fb0`

## pseudocode

```c
RPC_STATUS __stdcall I_RpcBindingCreateNP(
        RPC_WSTR ServerName,
        RPC_WSTR ServiceName,
        RPC_WSTR NetworkOptions,
        RPC_BINDING_HANDLE *Binding)
{
  unsigned __int16 *v4; // rbx
  RPC_STATUS result; // eax
  __int64 v10; // rsi
  unsigned __int64 v11; // rax
  unsigned __int16 *v12; // rbp
  unsigned __int16 *v13; // rax
  RPC_STATUS v14; // ebx
  void *v15; // r14
  _DWORD *v16; // rax
  __int64 v17; // rcx
  size_t v18; // rsi
  DWORD nSize; // [rsp+30h] [rbp-278h] BYREF
  RPC_WSTR String; // [rsp+38h] [rbp-270h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-268h] BYREF

  v4 = 0;
  nSize = 261;
  String = 0;
  if ( RpcHasBeenInitialized || (result = PerformRpcInitialization()) == 0 )
  {
    v10 = -1;
    *Binding = 0;
    v11 = -1;
    do
      ++v11;
    while ( ServiceName[v11] );
    if ( v11 < 6 || (v12 = 0, _wcsnicmp(ServiceName, L"\\PIPE\\", 6u)) )
    {
      v13 = DuplicateString2(L"\\PIPE\\", ServiceName);
      v12 = v13;
      if ( !v13 )
        return 14;
      ServiceName = v13;
    }
    v15 = 0;
    if ( !ServerName )
      goto LABEL_29;
    do
      ++v10;
    while ( ServerName[v10] );
    if ( !*ServerName )
      goto LABEL_29;
    if ( *ServerName == 92 && ServerName[1] == 92 )
    {
      LODWORD(v10) = v10 - 2;
      v4 = (unsigned __int16 *)((unsigned __int64)ServerName & -(__int64)((_DWORD)v10 != 0));
      if ( ((unsigned __int64)(ServerName + 2) & -(__int64)((_DWORD)v10 != 0)) == 0 )
      {
LABEL_29:
        v14 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", v4, ServiceName, NetworkOptions, &String);
        if ( !v14 )
        {
          v14 = RpcBindingFromStringBindingW(String, Binding);
          RpcStringFreeW(&String);
        }
        goto LABEL_31;
      }
      ServerName = (RPC_WSTR)((unsigned __int64)(ServerName + 2) & -(__int64)((_DWORD)v10 != 0));
    }
    else
    {
      v16 = AllocWrapper(saturated_mul((unsigned int)(v10 + 3), 2u));
      v15 = v16;
      if ( !v16 )
      {
        v14 = 14;
LABEL_31:
        if ( v12 )
          FreeWrapper(v12);
        if ( v15 )
          FreeWrapper(v15);
        return v14;
      }
      *v16 = 6029404;
      memcpy_0(v16 + 1, ServerName, 2LL * (unsigned int)(v10 + 1));
      v4 = (unsigned __int16 *)v15;
    }
    v17 = (unsigned int)(v10 - 1);
    if ( ServerName[v17] != 46 )
      LODWORD(v17) = v10;
    v18 = (unsigned int)v17;
    if ( (_DWORD)v17 == gLocalComputerNameLength - 1 && !_wcsnicmp(gLocalComputerName, ServerName, (unsigned int)v17)
      || (unsigned int)v18 <= 0x104
      && GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, &nSize)
      && (_DWORD)v18 == nSize
      && !_wcsnicmp(Buffer, ServerName, v18) )
    {
      v4 = 0;
    }
    goto LABEL_29;
  }
  return result;
}

```

## disassembly

```asm
0x1800a2e10  push    rbx
0x1800a2e12  push    rbp
0x1800a2e13  push    rsi
0x1800a2e14  push    rdi
0x1800a2e15  push    r12
0x1800a2e17  push    r13
0x1800a2e19  push    r14
0x1800a2e1b  push    r15
0x1800a2e1d  sub     rsp, 268h
0x1800a2e24  mov     rax, cs:__security_cookie
0x1800a2e2b  xor     rax, rsp
0x1800a2e2e  mov     [rsp+2A8h+var_58], rax
0x1800a2e36  xor     ebx, ebx
0x1800a2e38  mov     [rsp+2A8h+nSize], 105h
0x1800a2e40  cmp     cs:?RpcHasBeenInitialized@@3HA, ebx; int RpcHasBeenInitialized
0x1800a2e46  mov     r12, r9
0x1800a2e49  mov     r13, r8
0x1800a2e4c  mov     [rsp+2A8h+String], rbx
0x1800a2e51  mov     r15, rdx
0x1800a2e54  mov     rdi, rcx
0x1800a2e57  jnz     short loc_1800A2E66
0x1800a2e59  call    ?PerformRpcInitialization@@YAJXZ; PerformRpcInitialization(void)
0x1800a2e5e  test    eax, eax
0x1800a2e60  jnz     loc_1800A3041
0x1800a2e66  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800a2e6a  mov     [r12], rbx
0x1800a2e6e  mov     rax, rsi
0x1800a2e71  inc     rax
0x1800a2e74  cmp     [r15+rax*2], bx
0x1800a2e79  jnz     short loc_1800A2E71
0x1800a2e7b  mov     r8d, 6; MaxCount
0x1800a2e81  cmp     rax, r8
0x1800a2e84  jb      short loc_1800A2EA3
0x1800a2e86  lea     rdx, aPipe_0; "\\PIPE\\"
0x1800a2e8d  mov     rcx, r15; String1
0x1800a2e90  mov     rbp, rbx
0x1800a2e93  call    cs:__imp__wcsnicmp
0x1800a2e9a  nop     dword ptr [rax+rax+00h]
0x1800a2e9f  test    eax, eax
0x1800a2ea1  jz      short loc_1800A2EC5
0x1800a2ea3  mov     rdx, r15; unsigned __int16 *
0x1800a2ea6  lea     rcx, aPipe_0; "\\PIPE\\"
0x1800a2ead  call    ?DuplicateString2@@YAPEAGPEBG0@Z; DuplicateString2(ushort const *,ushort const *)
0x1800a2eb2  mov     rbp, rax
0x1800a2eb5  test    rax, rax
0x1800a2eb8  jnz     short loc_1800A2EC2
0x1800a2eba  lea     ebx, [rax+0Eh]
0x1800a2ebd  jmp     loc_1800A303F
0x1800a2ec2  mov     r15, rax
0x1800a2ec5  mov     r14, rbx
0x1800a2ec8  test    rdi, rdi
0x1800a2ecb  jz      loc_1800A2FE3
0x1800a2ed1  inc     rsi
0x1800a2ed4  cmp     [rdi+rsi*2], bx
0x1800a2ed8  jnz     short loc_1800A2ED1
0x1800a2eda  cmp     [rdi], bx
0x1800a2edd  jz      loc_1800A2FE3
0x1800a2ee3  mov     eax, 5Ch ; '\'
0x1800a2ee8  cmp     [rdi], ax
0x1800a2eeb  jnz     short loc_1800A2F19
0x1800a2eed  cmp     [rdi+2], ax
0x1800a2ef1  jnz     short loc_1800A2F19
0x1800a2ef3  add     esi, 0FFFFFFFEh
0x1800a2ef6  lea     rcx, [rdi+4]
0x1800a2efa  mov     eax, esi
0x1800a2efc  neg     eax
0x1800a2efe  mov     eax, esi
0x1800a2f00  sbb     rdx, rdx
0x1800a2f03  neg     eax
0x1800a2f05  sbb     rbx, rbx
0x1800a2f08  and     rbx, rdi
0x1800a2f0b  and     rdx, rcx
0x1800a2f0e  jz      loc_1800A2FE3
0x1800a2f14  mov     rdi, rdx
0x1800a2f17  jmp     short loc_1800A2F63
0x1800a2f19  lea     ecx, [rsi+3]
0x1800a2f1c  mov     eax, 2
0x1800a2f21  mul     rcx
0x1800a2f24  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a2f2b  cmovb   rax, rcx
0x1800a2f2f  mov     rcx, rax; dwBytes
0x1800a2f32  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800a2f37  mov     r14, rax
0x1800a2f3a  test    rax, rax
0x1800a2f3d  jnz     short loc_1800A2F47
0x1800a2f3f  lea     ebx, [rax+0Eh]
0x1800a2f42  jmp     loc_1800A3025
0x1800a2f47  lea     r8d, [rsi+1]
0x1800a2f4b  mov     dword ptr [rax], 5C005Ch
0x1800a2f51  add     r8, r8; Size
0x1800a2f54  lea     rcx, [rax+4]; void *
0x1800a2f58  mov     rdx, rdi; Src
0x1800a2f5b  call    memcpy_0
0x1800a2f60  mov     rbx, r14
0x1800a2f63  mov     eax, cs:?gLocalComputerNameLength@@3KA; ulong gLocalComputerNameLength
0x1800a2f69  lea     ecx, [rsi-1]
0x1800a2f6c  cmp     word ptr [rdi+rcx*2], 2Eh ; '.'
0x1800a2f71  cmovnz  ecx, esi
0x1800a2f74  dec     eax
0x1800a2f76  mov     esi, ecx
0x1800a2f78  cmp     ecx, eax
0x1800a2f7a  jnz     short loc_1800A2F99
0x1800a2f7c  mov     rcx, cs:?gLocalComputerName@@3PEAGEA; String1
0x1800a2f83  mov     r8d, esi; MaxCount
0x1800a2f86  mov     rdx, rdi; String2
0x1800a2f89  call    cs:__imp__wcsnicmp
0x1800a2f90  nop     dword ptr [rax+rax+00h]
0x1800a2f95  test    eax, eax
0x1800a2f97  jz      short loc_1800A2FE1
0x1800a2f99  cmp     esi, 104h
0x1800a2f9f  ja      short loc_1800A2FE3
0x1800a2fa1  lea     r8, [rsp+2A8h+nSize]; nSize
0x1800a2fa6  mov     ecx, 3; NameType
0x1800a2fab  lea     rdx, [rsp+2A8h+Buffer]; lpBuffer
0x1800a2fb0  call    cs:__imp_GetComputerNameExW
0x1800a2fb7  nop     dword ptr [rax+rax+00h]
0x1800a2fbc  test    eax, eax
0x1800a2fbe  jz      short loc_1800A2FE3
0x1800a2fc0  cmp     esi, [rsp+2A8h+nSize]
0x1800a2fc4  jnz     short loc_1800A2FE3
0x1800a2fc6  mov     r8, rsi; MaxCount
0x1800a2fc9  lea     rcx, [rsp+2A8h+Buffer]; String1
0x1800a2fce  mov     rdx, rdi; String2
0x1800a2fd1  call    cs:__imp__wcsnicmp
0x1800a2fd8  nop     dword ptr [rax+rax+00h]
0x1800a2fdd  test    eax, eax
0x1800a2fdf  jnz     short loc_1800A2FE3
0x1800a2fe1  xor     ebx, ebx
0x1800a2fe3  lea     rax, [rsp+2A8h+String]
0x1800a2fe8  mov     r9, r15; Endpoint
0x1800a2feb  mov     [rsp+2A8h+StringBinding], rax; StringBinding
0x1800a2ff0  lea     rdx, aNcacnNp; "ncacn_np"
0x1800a2ff7  mov     r8, rbx; NetworkAddr
0x1800a2ffa  mov     [rsp+2A8h+Options], r13; Options
0x1800a2fff  xor     ecx, ecx; ObjUuid
0x1800a3001  call    RpcStringBindingComposeW
0x1800a3006  mov     ebx, eax
0x1800a3008  test    eax, eax
0x1800a300a  jnz     short loc_1800A3025
0x1800a300c  mov     rcx, [rsp+2A8h+String]; StringBinding
0x1800a3011  mov     rdx, r12; Binding
0x1800a3014  call    RpcBindingFromStringBindingW
0x1800a3019  lea     rcx, [rsp+2A8h+String]; String
0x1800a301e  mov     ebx, eax
0x1800a3020  call    RpcStringFreeW
0x1800a3025  test    rbp, rbp
0x1800a3028  jz      short loc_1800A3032
0x1800a302a  mov     rcx, rbp; lpMem
0x1800a302d  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800a3032  test    r14, r14
0x1800a3035  jz      short loc_1800A303F
0x1800a3037  mov     rcx, r14; lpMem
0x1800a303a  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800a303f  mov     eax, ebx
0x1800a3041  mov     rcx, [rsp+2A8h+var_58]
0x1800a3049  xor     rcx, rsp; StackCookie
0x1800a304c  call    __security_check_cookie
0x1800a3051  add     rsp, 268h
0x1800a3058  pop     r15
0x1800a305a  pop     r14
0x1800a305c  pop     r13
0x1800a305e  pop     r12
0x1800a3060  pop     rdi
0x1800a3061  pop     rsi
0x1800a3062  pop     rbp
0x1800a3063  pop     rbx
0x1800a3064  retn
```
