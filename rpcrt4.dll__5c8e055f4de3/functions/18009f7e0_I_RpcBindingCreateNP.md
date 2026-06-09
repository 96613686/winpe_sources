# I_RpcBindingCreateNP

- ea: `0x18009f7e0`
- end: `0x18009fa1d`
- name: `I_RpcBindingCreateNP`
- size: `573`
- prototype: `RPC_STATUS __stdcall(RPC_WSTR ServerName, RPC_WSTR ServiceName, RPC_WSTR NetworkOptions, RPC_BINDING_HANDLE *Binding)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180021e70`
- `0x180022870`
- `0x18002499c`
- `0x18002d000`
- `0x18002d1c0`
- `0x180084710`
- `0x180084cd8`
- `0x18009f7e0`
- `0x1800ca031`
- `0x1800ca140`

## import_xrefs

- `ntdll!_wcsnicmp` at `0x18009f863`
- `ntdll!_wcsnicmp` at `0x18009f953`
- `ntdll!_wcsnicmp` at `0x18009f98f`
- `ntdll!_wcsnicmp` at `0x18009f863`
- `ntdll!_wcsnicmp` at `0x18009f953`
- `ntdll!_wcsnicmp` at `0x18009f98f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18009f974`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18009f974`

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
0x18009f7e0  push    rbx
0x18009f7e2  push    rbp
0x18009f7e3  push    rsi
0x18009f7e4  push    rdi
0x18009f7e5  push    r12
0x18009f7e7  push    r13
0x18009f7e9  push    r14
0x18009f7eb  push    r15
0x18009f7ed  sub     rsp, 268h
0x18009f7f4  mov     rax, cs:__security_cookie
0x18009f7fb  xor     rax, rsp
0x18009f7fe  mov     [rsp+2A8h+var_58], rax
0x18009f806  xor     ebx, ebx
0x18009f808  mov     [rsp+2A8h+nSize], 105h
0x18009f810  cmp     cs:?RpcHasBeenInitialized@@3HA, ebx; int RpcHasBeenInitialized
0x18009f816  mov     r12, r9
0x18009f819  mov     r13, r8
0x18009f81c  mov     [rsp+2A8h+String], rbx
0x18009f821  mov     r15, rdx
0x18009f824  mov     rdi, rcx
0x18009f827  jnz     short loc_18009F836
0x18009f829  call    ?PerformRpcInitialization@@YAJXZ; PerformRpcInitialization(void)
0x18009f82e  test    eax, eax
0x18009f830  jnz     loc_18009F9F9
0x18009f836  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18009f83a  mov     [r12], rbx
0x18009f83e  mov     rax, rsi
0x18009f841  inc     rax
0x18009f844  cmp     [r15+rax*2], bx
0x18009f849  jnz     short loc_18009F841
0x18009f84b  mov     r8d, 6; MaxCount
0x18009f851  cmp     rax, r8
0x18009f854  jb      short loc_18009F86D
0x18009f856  lea     rdx, aPipe_0; "\\PIPE\\"
0x18009f85d  mov     rcx, r15; String1
0x18009f860  mov     rbp, rbx
0x18009f863  call    cs:__imp__wcsnicmp
0x18009f869  test    eax, eax
0x18009f86b  jz      short loc_18009F88F
0x18009f86d  mov     rdx, r15; unsigned __int16 *
0x18009f870  lea     rcx, aPipe_0; "\\PIPE\\"
0x18009f877  call    ?DuplicateString2@@YAPEAGPEBG0@Z; DuplicateString2(ushort const *,ushort const *)
0x18009f87c  mov     rbp, rax
0x18009f87f  test    rax, rax
0x18009f882  jnz     short loc_18009F88C
0x18009f884  lea     ebx, [rax+0Eh]
0x18009f887  jmp     loc_18009F9F7
0x18009f88c  mov     r15, rax
0x18009f88f  mov     r14, rbx
0x18009f892  test    rdi, rdi
0x18009f895  jz      loc_18009F99B
0x18009f89b  inc     rsi
0x18009f89e  cmp     [rdi+rsi*2], bx
0x18009f8a2  jnz     short loc_18009F89B
0x18009f8a4  cmp     [rdi], bx
0x18009f8a7  jz      loc_18009F99B
0x18009f8ad  mov     eax, 5Ch ; '\'
0x18009f8b2  cmp     [rdi], ax
0x18009f8b5  jnz     short loc_18009F8E3
0x18009f8b7  cmp     [rdi+2], ax
0x18009f8bb  jnz     short loc_18009F8E3
0x18009f8bd  add     esi, 0FFFFFFFEh
0x18009f8c0  lea     rcx, [rdi+4]
0x18009f8c4  mov     eax, esi
0x18009f8c6  neg     eax
0x18009f8c8  mov     eax, esi
0x18009f8ca  sbb     rdx, rdx
0x18009f8cd  neg     eax
0x18009f8cf  sbb     rbx, rbx
0x18009f8d2  and     rbx, rdi
0x18009f8d5  and     rdx, rcx
0x18009f8d8  jz      loc_18009F99B
0x18009f8de  mov     rdi, rdx
0x18009f8e1  jmp     short loc_18009F92D
0x18009f8e3  lea     ecx, [rsi+3]
0x18009f8e6  mov     eax, 2
0x18009f8eb  mul     rcx
0x18009f8ee  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18009f8f5  cmovb   rax, rcx
0x18009f8f9  mov     rcx, rax; dwBytes
0x18009f8fc  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x18009f901  mov     r14, rax
0x18009f904  test    rax, rax
0x18009f907  jnz     short loc_18009F911
0x18009f909  lea     ebx, [rax+0Eh]
0x18009f90c  jmp     loc_18009F9DD
0x18009f911  lea     r8d, [rsi+1]
0x18009f915  mov     dword ptr [rax], 5C005Ch
0x18009f91b  add     r8, r8; Size
0x18009f91e  lea     rcx, [rax+4]; void *
0x18009f922  mov     rdx, rdi; Src
0x18009f925  call    memcpy_0
0x18009f92a  mov     rbx, r14
0x18009f92d  mov     eax, cs:?gLocalComputerNameLength@@3KA; ulong gLocalComputerNameLength
0x18009f933  lea     ecx, [rsi-1]
0x18009f936  cmp     word ptr [rdi+rcx*2], 2Eh ; '.'
0x18009f93b  cmovnz  ecx, esi
0x18009f93e  dec     eax
0x18009f940  mov     esi, ecx
0x18009f942  cmp     ecx, eax
0x18009f944  jnz     short loc_18009F95D
0x18009f946  mov     rcx, cs:?gLocalComputerName@@3PEAGEA; String1
0x18009f94d  mov     r8d, esi; MaxCount
0x18009f950  mov     rdx, rdi; String2
0x18009f953  call    cs:__imp__wcsnicmp
0x18009f959  test    eax, eax
0x18009f95b  jz      short loc_18009F999
0x18009f95d  cmp     esi, 104h
0x18009f963  ja      short loc_18009F99B
0x18009f965  lea     r8, [rsp+2A8h+nSize]; nSize
0x18009f96a  mov     ecx, 3; NameType
0x18009f96f  lea     rdx, [rsp+2A8h+Buffer]; lpBuffer
0x18009f974  call    cs:__imp_GetComputerNameExW
0x18009f97a  test    eax, eax
0x18009f97c  jz      short loc_18009F99B
0x18009f97e  cmp     esi, [rsp+2A8h+nSize]
0x18009f982  jnz     short loc_18009F99B
0x18009f984  mov     r8, rsi; MaxCount
0x18009f987  lea     rcx, [rsp+2A8h+Buffer]; String1
0x18009f98c  mov     rdx, rdi; String2
0x18009f98f  call    cs:__imp__wcsnicmp
0x18009f995  test    eax, eax
0x18009f997  jnz     short loc_18009F99B
0x18009f999  xor     ebx, ebx
0x18009f99b  lea     rax, [rsp+2A8h+String]
0x18009f9a0  mov     r9, r15; Endpoint
0x18009f9a3  mov     [rsp+2A8h+StringBinding], rax; StringBinding
0x18009f9a8  lea     rdx, aNcacnNp; "ncacn_np"
0x18009f9af  mov     r8, rbx; NetworkAddr
0x18009f9b2  mov     [rsp+2A8h+Options], r13; Options
0x18009f9b7  xor     ecx, ecx; ObjUuid
0x18009f9b9  call    RpcStringBindingComposeW
0x18009f9be  mov     ebx, eax
0x18009f9c0  test    eax, eax
0x18009f9c2  jnz     short loc_18009F9DD
0x18009f9c4  mov     rcx, [rsp+2A8h+String]; StringBinding
0x18009f9c9  mov     rdx, r12; Binding
0x18009f9cc  call    RpcBindingFromStringBindingW
0x18009f9d1  lea     rcx, [rsp+2A8h+String]; String
0x18009f9d6  mov     ebx, eax
0x18009f9d8  call    RpcStringFreeW
0x18009f9dd  test    rbp, rbp
0x18009f9e0  jz      short loc_18009F9EA
0x18009f9e2  mov     rcx, rbp; lpMem
0x18009f9e5  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009f9ea  test    r14, r14
0x18009f9ed  jz      short loc_18009F9F7
0x18009f9ef  mov     rcx, r14; lpMem
0x18009f9f2  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x18009f9f7  mov     eax, ebx
0x18009f9f9  mov     rcx, [rsp+2A8h+var_58]
0x18009fa01  xor     rcx, rsp; StackCookie
0x18009fa04  call    __security_check_cookie
0x18009fa09  add     rsp, 268h
0x18009fa10  pop     r15
0x18009fa12  pop     r14
0x18009fa14  pop     r13
0x18009fa16  pop     r12
0x18009fa18  pop     rdi
0x18009fa19  pop     rsi
0x18009fa1a  pop     rbp
0x18009fa1b  pop     rbx
0x18009fa1c  retn
```
