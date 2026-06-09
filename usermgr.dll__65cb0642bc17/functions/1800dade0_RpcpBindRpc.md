# RpcpBindRpc

- ea: `0x1800dade0`
- end: `0x1800db09d`
- name: `RpcpBindRpc`
- size: `701`
- prototype: `__int64 __fastcall(RPC_WSTR NetworkAddr)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800dacd0`

## callees

- `0x18006c426`
- `0x180075898`
- `0x1800dade0`
- `0x1800de450`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800daee4`
- `msvcrt!_wcsnicmp` at `0x1800daf49`
- `msvcrt!_wcsnicmp` at `0x1800daee4`
- `msvcrt!_wcsnicmp` at `0x1800daf49`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800daec8`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800daf2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800daec8`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800daf2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800daf5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800db00d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800db05e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800db071`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800daf5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800db00d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800db05e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800db071`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dae7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800daf03`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800daf6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dae7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800daf03`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800daf6c`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800db002`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800db002`
- `RPCRT4!RpcStringFreeW` at `0x1800db02e`
- `RPCRT4!RpcStringFreeW` at `0x1800db02e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800db022`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800db022`

## pseudocode

```c
__int64 __fastcall RpcpBindRpc(RPC_WSTR NetworkAddr, __int64 a2, __int64 a3, RPC_BINDING_HANDLE *a4)
{
  RPC_WSTR v5; // rdi
  unsigned __int16 *v6; // r14
  size_t v7; // rbx
  unsigned int v8; // ebx
  unsigned __int64 v9; // rsi
  unsigned __int16 *v10; // rax
  size_t v11; // r15
  WCHAR *v12; // rax
  wchar_t *v13; // rbx
  unsigned __int16 *v14; // rax
  __int64 v15; // r8
  unsigned __int16 *v16; // rdi
  __int64 v17; // r11
  unsigned __int64 v18; // r8
  unsigned __int16 *v19; // rax
  __int64 v20; // rdx
  RPC_STATUS v21; // ebx
  RPC_STATUS v22; // ebx
  int v23; // ecx
  DWORD nSize; // [rsp+30h] [rbp-40h] BYREF
  RPC_WSTR String; // [rsp+38h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+40h] [rbp-30h] BYREF

  String = 0;
  v5 = NetworkAddr;
  nSize = 0;
  v6 = 0;
  *a4 = 0;
  if ( !NetworkAddr )
    goto LABEL_26;
  v7 = -1;
  do
    ++v7;
  while ( NetworkAddr[v7] );
  if ( !*NetworkAddr )
    goto LABEL_26;
  if ( *NetworkAddr == 92 )
  {
    if ( NetworkAddr[1] != 92 )
      return (unsigned int)-1073741534;
    v7 -= 2LL;
    if ( !v7 )
      return (unsigned int)-1073741534;
    v9 = (unsigned __int64)NetworkAddr;
    if ( NetworkAddr == (RPC_WSTR)-4LL )
      goto LABEL_27;
    v5 = NetworkAddr + 2;
  }
  else
  {
    v10 = (unsigned __int16 *)LocalAlloc(0, 2 * v7 + 6);
    v6 = v10;
    if ( !v10 )
      return (unsigned int)-1073741801;
    *(_DWORD *)v10 = 6029404;
    memcpy_0(v10 + 2, v5, 2 * v7 + 2);
    v9 = (unsigned __int64)v6;
  }
  if ( v7 <= 0xF )
  {
    nSize = 16;
    if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
    {
      if ( v7 == nSize && !_wcsnicmp(Buffer, v5, v7) )
      {
LABEL_26:
        v9 = 0;
        goto LABEL_27;
      }
    }
  }
  v11 = v7 - 1;
  if ( v5[v7 - 1] != 46 )
    v11 = v7;
  v12 = (WCHAR *)LocalAlloc(0, 0x20Au);
  v13 = v12;
  if ( !v12 )
    goto LABEL_21;
  nSize = 261;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, v12, &nSize) && v11 == nSize )
    v9 &= -(__int64)(_wcsnicmp(v13, v5, v11) != 0);
  LocalFree(v13);
LABEL_27:
  v14 = (unsigned __int16 *)LocalAlloc(0, 0x1Cu);
  v16 = v14;
  if ( !v14 )
  {
LABEL_21:
    v8 = -1073741801;
    goto LABEL_41;
  }
  if ( (int)RtlStringCopyWorkerW(v14, 14, v15, L"\\PIPE\\") >= 0 )
  {
    v18 = (unsigned int)v17;
    v19 = v16;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v18;
    }
    while ( v18 );
    if ( v18 )
    {
      v20 = (v17 - v18) & ((unsigned __int128)-(__int128)v18 >> 64);
      if ( (int)RtlStringCopyWorkerW(&v16[v20], v17 - v20, v18, L"lsarpc") >= 0 )
      {
        v21 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", (RPC_WSTR)v9, v16, 0, &String);
        LocalFree(v16);
        if ( !v21 )
        {
          v22 = RpcBindingFromStringBindingW(String, a4);
          RpcStringFreeW(&String);
          if ( v22 )
          {
            *a4 = 0;
            v23 = -1073741534;
            if ( (unsigned int)(v22 - 1706) > 1 )
              v23 = -1073741801;
            v8 = v23;
          }
          else
          {
            v8 = 0;
          }
          goto LABEL_41;
        }
        goto LABEL_21;
      }
    }
  }
  LocalFree(v16);
  v8 = -1073741811;
LABEL_41:
  if ( v6 )
    LocalFree(v6);
  return v8;
}

```

## disassembly

```asm
0x1800dade0  mov     [rsp-38h+arg_8], rbx
0x1800dade5  push    rbp
0x1800dade6  push    rsi
0x1800dade7  push    rdi
0x1800dade8  push    r12
0x1800dadea  push    r13
0x1800dadec  push    r14
0x1800dadee  push    r15
0x1800dadf0  mov     rbp, rsp
0x1800dadf3  sub     rsp, 70h
0x1800dadf7  mov     rax, cs:__security_cookie
0x1800dadfe  xor     rax, rsp
0x1800dae01  mov     [rbp+var_10], rax
0x1800dae05  xor     r13d, r13d
0x1800dae08  mov     r12, r9
0x1800dae0b  mov     [rbp+String], r13
0x1800dae0f  mov     rdi, rcx
0x1800dae12  mov     [rbp+nSize], r13d
0x1800dae16  mov     r14d, r13d
0x1800dae19  mov     [r9], r13
0x1800dae1c  test    rcx, rcx
0x1800dae1f  jz      loc_1800DAF62
0x1800dae25  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800dae29  inc     rbx
0x1800dae2c  cmp     [rcx+rbx*2], r13w
0x1800dae31  jnz     short loc_1800DAE29
0x1800dae33  cmp     [rcx], r13w
0x1800dae37  jz      loc_1800DAF62
0x1800dae3d  mov     esi, 5Ch ; '\'
0x1800dae42  cmp     [rcx], si
0x1800dae45  jnz     short loc_1800DAE72
0x1800dae47  cmp     [rcx+2], si
0x1800dae4b  jnz     short loc_1800DAE53
0x1800dae4d  add     rbx, 0FFFFFFFFFFFFFFFEh
0x1800dae51  jnz     short loc_1800DAE5D
0x1800dae53  mov     ebx, 0C0000122h
0x1800dae58  jmp     loc_1800DB077
0x1800dae5d  lea     rax, [rcx+4]
0x1800dae61  mov     rsi, rdi
0x1800dae64  test    rax, rax
0x1800dae67  jz      loc_1800DAF65
0x1800dae6d  mov     rdi, rax
0x1800dae70  jmp     short loc_1800DAEB1
0x1800dae72  lea     rdx, ds:6[rbx*2]; uBytes
0x1800dae7a  xor     ecx, ecx; uFlags
0x1800dae7c  call    cs:__imp_LocalAlloc
0x1800dae82  mov     r14, rax
0x1800dae85  test    rax, rax
0x1800dae88  jnz     short loc_1800DAE94
0x1800dae8a  mov     ebx, 0C0000017h
0x1800dae8f  jmp     loc_1800DB077
0x1800dae94  lea     r8, ds:2[rbx*2]; Size
0x1800dae9c  mov     dword ptr [rax], 5C005Ch
0x1800daea2  lea     rcx, [rax+4]; void *
0x1800daea6  mov     rdx, rdi; Src
0x1800daea9  call    memcpy_0
0x1800daeae  mov     rsi, r14
0x1800daeb1  cmp     rbx, 0Fh
0x1800daeb5  ja      short loc_1800DAEEE
0x1800daeb7  lea     r8, [rbp+nSize]; nSize
0x1800daebb  mov     [rbp+nSize], 10h
0x1800daec2  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800daec6  xor     ecx, ecx; NameType
0x1800daec8  call    cs:__imp_GetComputerNameExW
0x1800daece  test    eax, eax
0x1800daed0  jz      short loc_1800DAEEE
0x1800daed2  mov     eax, [rbp+nSize]
0x1800daed5  cmp     rbx, rax
0x1800daed8  jnz     short loc_1800DAEEE
0x1800daeda  mov     r8, rbx; MaxCount
0x1800daedd  lea     rcx, [rbp+Buffer]; String1
0x1800daee1  mov     rdx, rdi; String2
0x1800daee4  call    cs:__imp__wcsnicmp
0x1800daeea  test    eax, eax
0x1800daeec  jz      short loc_1800DAF62
0x1800daeee  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x1800daef4  lea     r15, [rbx-1]
0x1800daef8  mov     edx, 20Ah; uBytes
0x1800daefd  cmovnz  r15, rbx
0x1800daf01  xor     ecx, ecx; uFlags
0x1800daf03  call    cs:__imp_LocalAlloc
0x1800daf09  mov     rbx, rax
0x1800daf0c  test    rax, rax
0x1800daf0f  jnz     short loc_1800DAF1B
0x1800daf11  mov     ebx, 0C0000017h
0x1800daf16  jmp     loc_1800DB069
0x1800daf1b  lea     r8, [rbp+nSize]; nSize
0x1800daf1f  mov     [rbp+nSize], 105h
0x1800daf26  mov     rdx, rbx; lpBuffer
0x1800daf29  mov     ecx, 3; NameType
0x1800daf2e  call    cs:__imp_GetComputerNameExW
0x1800daf34  test    eax, eax
0x1800daf36  jz      short loc_1800DAF57
0x1800daf38  mov     eax, [rbp+nSize]
0x1800daf3b  cmp     r15, rax
0x1800daf3e  jnz     short loc_1800DAF57
0x1800daf40  mov     r8, r15; MaxCount
0x1800daf43  mov     rdx, rdi; String2
0x1800daf46  mov     rcx, rbx; String1
0x1800daf49  call    cs:__imp__wcsnicmp
0x1800daf4f  neg     eax
0x1800daf51  sbb     rcx, rcx
0x1800daf54  and     rsi, rcx
0x1800daf57  mov     rcx, rbx; hMem
0x1800daf5a  call    cs:__imp_LocalFree
0x1800daf60  jmp     short loc_1800DAF65
0x1800daf62  mov     rsi, r13
0x1800daf65  mov     edx, 1Ch; uBytes
0x1800daf6a  xor     ecx, ecx; uFlags
0x1800daf6c  call    cs:__imp_LocalAlloc
0x1800daf72  mov     rdi, rax
0x1800daf75  test    rax, rax
0x1800daf78  jz      short loc_1800DAF11
0x1800daf7a  mov     r11d, 0Eh
0x1800daf80  lea     r9, aPipe; "\\PIPE\\"
0x1800daf87  mov     edx, r11d
0x1800daf8a  mov     rcx, rax
0x1800daf8d  call    RtlStringCopyWorkerW
0x1800daf92  test    eax, eax
0x1800daf94  js      loc_1800DB05B
0x1800daf9a  mov     r8d, r11d
0x1800daf9d  mov     rax, rdi
0x1800dafa0  cmp     [rax], r13w
0x1800dafa4  jz      short loc_1800DAFB0
0x1800dafa6  add     rax, 2
0x1800dafaa  sub     r8, 1
0x1800dafae  jnz     short loc_1800DAFA0
0x1800dafb0  mov     rcx, r11
0x1800dafb3  mov     rax, r8
0x1800dafb6  sub     rcx, r8
0x1800dafb9  neg     rax
0x1800dafbc  sbb     rdx, rdx
0x1800dafbf  and     rdx, rcx
0x1800dafc2  test    r8, r8
0x1800dafc5  jz      loc_1800DB05B
0x1800dafcb  sub     r11, rdx
0x1800dafce  lea     rcx, [rdi+rdx*2]
0x1800dafd2  mov     rdx, r11
0x1800dafd5  lea     r9, aLsarpc; "lsarpc"
0x1800dafdc  call    RtlStringCopyWorkerW
0x1800dafe1  test    eax, eax
0x1800dafe3  js      short loc_1800DB05B
0x1800dafe5  lea     rax, [rbp+String]
0x1800dafe9  mov     r9, rdi; Endpoint
0x1800dafec  mov     [rsp+70h+StringBinding], rax; StringBinding
0x1800daff1  lea     rdx, ProtSeq; "ncacn_np"
0x1800daff8  mov     r8, rsi; NetworkAddr
0x1800daffb  mov     [rsp+70h+Options], r13; Options
0x1800db000  xor     ecx, ecx; ObjUuid
0x1800db002  call    cs:__imp_RpcStringBindingComposeW
0x1800db008  mov     rcx, rdi; hMem
0x1800db00b  mov     ebx, eax
0x1800db00d  call    cs:__imp_LocalFree
0x1800db013  test    ebx, ebx
0x1800db015  jnz     loc_1800DAF11
0x1800db01b  mov     rcx, [rbp+String]; StringBinding
0x1800db01f  mov     rdx, r12; Binding
0x1800db022  call    cs:__imp_RpcBindingFromStringBindingW
0x1800db028  lea     rcx, [rbp+String]; String
0x1800db02c  mov     ebx, eax
0x1800db02e  call    cs:__imp_RpcStringFreeW
0x1800db034  test    ebx, ebx
0x1800db036  jz      short loc_1800DB056
0x1800db038  lea     eax, [rbx-6AAh]
0x1800db03e  mov     [r12], r13
0x1800db042  mov     ebx, 0C0000017h
0x1800db047  cmp     eax, 1
0x1800db04a  mov     ecx, 0C0000122h
0x1800db04f  cmova   ecx, ebx
0x1800db052  mov     ebx, ecx
0x1800db054  jmp     short loc_1800DB069
0x1800db056  mov     ebx, r13d
0x1800db059  jmp     short loc_1800DB069
0x1800db05b  mov     rcx, rdi; hMem
0x1800db05e  call    cs:__imp_LocalFree
0x1800db064  mov     ebx, 0C000000Dh
0x1800db069  test    r14, r14
0x1800db06c  jz      short loc_1800DB077
0x1800db06e  mov     rcx, r14; hMem
0x1800db071  call    cs:__imp_LocalFree
0x1800db077  mov     eax, ebx
0x1800db079  mov     rcx, [rbp+var_10]
0x1800db07d  xor     rcx, rsp; StackCookie
0x1800db080  call    __security_check_cookie
0x1800db085  mov     rbx, [rsp+70h+arg_8]
0x1800db08d  add     rsp, 70h
0x1800db091  pop     r15
0x1800db093  pop     r14
0x1800db095  pop     r13
0x1800db097  pop     r12
0x1800db099  pop     rdi
0x1800db09a  pop     rsi
0x1800db09b  pop     rbp
0x1800db09c  retn
```
