# RpcpBindRpc

- ea: `0x1800b9eb8`
- end: `0x1800ba173`
- name: `RpcpBindRpc`
- size: `699`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800b40e0`

## callees

- `0x18002cd80`
- `0x18002d6e4`
- `0x1800b9eb8`
- `0x1800ba1a4`
- `0x1800bb788`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b9f54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b9fda`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ba042`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b9f54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b9fda`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ba042`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ba030`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ba0e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ba134`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ba147`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ba030`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ba0e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ba134`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ba147`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800b9fa0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800ba005`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800b9fa0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800ba005`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800ba0f8`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800ba0f8`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800ba0d8`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800ba0d8`
- `RPCRT4!RpcStringFreeW` at `0x1800ba104`
- `RPCRT4!RpcStringFreeW` at `0x1800ba104`

## pseudocode

```c
__int64 __fastcall RpcpBindRpc(char *Src, __int64 a2, __int64 a3, RPC_BINDING_HANDLE *a4)
{
  char *v5; // rdi
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
  v5 = Src;
  nSize = 0;
  v6 = 0;
  *a4 = 0;
  if ( !Src )
    goto LABEL_26;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)&Src[2 * v7] );
  if ( !*(_WORD *)Src )
    goto LABEL_26;
  if ( *(_WORD *)Src == 92 )
  {
    if ( *((_WORD *)Src + 1) != 92 )
      return (unsigned int)-1073741534;
    v7 -= 2LL;
    if ( !v7 )
      return (unsigned int)-1073741534;
    v9 = (unsigned __int64)Src;
    if ( Src == (char *)-4LL )
      goto LABEL_27;
    v5 = Src + 4;
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
      if ( v7 == nSize && !wcsnicmp(Buffer, (const wchar_t *)v5, v7) )
      {
LABEL_26:
        v9 = 0;
        goto LABEL_27;
      }
    }
  }
  v11 = v7 - 1;
  if ( *(_WORD *)&v5[2 * v7 - 2] != 46 )
    v11 = v7;
  v12 = (WCHAR *)LocalAlloc(0, 0x20Au);
  v13 = v12;
  if ( !v12 )
    goto LABEL_21;
  nSize = 261;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, v12, &nSize) && v11 == nSize )
    v9 &= -(__int64)(wcsnicmp(v13, (const wchar_t *)v5, v11) != 0);
  LocalFree(v13);
LABEL_27:
  v14 = (unsigned __int16 *)LocalAlloc(0, 0x18u);
  v16 = v14;
  if ( !v14 )
  {
LABEL_21:
    v8 = -1073741801;
    goto LABEL_41;
  }
  if ( (int)RtlStringCopyWorkerW_1(v14, 12, v15, L"\\PIPE\\") >= 0 )
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
      if ( (int)RtlStringCopyWorkerW_1(&v16[v20], v17 - v20, v18, L"samr") >= 0 )
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
0x1800b9eb8  mov     [rsp-38h+arg_8], rbx
0x1800b9ebd  push    rbp
0x1800b9ebe  push    rsi
0x1800b9ebf  push    rdi
0x1800b9ec0  push    r12
0x1800b9ec2  push    r13
0x1800b9ec4  push    r14
0x1800b9ec6  push    r15
0x1800b9ec8  mov     rbp, rsp
0x1800b9ecb  sub     rsp, 70h
0x1800b9ecf  mov     rax, cs:__security_cookie
0x1800b9ed6  xor     rax, rsp
0x1800b9ed9  mov     [rbp+var_10], rax
0x1800b9edd  xor     r13d, r13d
0x1800b9ee0  mov     r12, r9
0x1800b9ee3  mov     [rbp+String], r13
0x1800b9ee7  mov     rdi, rcx
0x1800b9eea  mov     [rbp+nSize], r13d
0x1800b9eee  mov     r14d, r13d
0x1800b9ef1  mov     [r9], r13
0x1800b9ef4  test    rcx, rcx
0x1800b9ef7  jz      loc_1800BA038
0x1800b9efd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b9f01  inc     rbx
0x1800b9f04  cmp     [rcx+rbx*2], r13w
0x1800b9f09  jnz     short loc_1800B9F01
0x1800b9f0b  cmp     [rcx], r13w
0x1800b9f0f  jz      loc_1800BA038
0x1800b9f15  mov     esi, 5Ch ; '\'
0x1800b9f1a  cmp     [rcx], si
0x1800b9f1d  jnz     short loc_1800B9F4A
0x1800b9f1f  cmp     [rcx+2], si
0x1800b9f23  jnz     short loc_1800B9F2B
0x1800b9f25  add     rbx, 0FFFFFFFFFFFFFFFEh
0x1800b9f29  jnz     short loc_1800B9F35
0x1800b9f2b  mov     ebx, 0C0000122h
0x1800b9f30  jmp     loc_1800BA14D
0x1800b9f35  lea     rax, [rcx+4]
0x1800b9f39  mov     rsi, rdi
0x1800b9f3c  test    rax, rax
0x1800b9f3f  jz      loc_1800BA03B
0x1800b9f45  mov     rdi, rax
0x1800b9f48  jmp     short loc_1800B9F89
0x1800b9f4a  lea     rdx, ds:6[rbx*2]; uBytes
0x1800b9f52  xor     ecx, ecx; uFlags
0x1800b9f54  call    cs:__imp_LocalAlloc
0x1800b9f5a  mov     r14, rax
0x1800b9f5d  test    rax, rax
0x1800b9f60  jnz     short loc_1800B9F6C
0x1800b9f62  mov     ebx, 0C0000017h
0x1800b9f67  jmp     loc_1800BA14D
0x1800b9f6c  lea     r8, ds:2[rbx*2]; Size
0x1800b9f74  mov     dword ptr [rax], 5C005Ch
0x1800b9f7a  lea     rcx, [rax+4]; void *
0x1800b9f7e  mov     rdx, rdi; Src
0x1800b9f81  call    memcpy_0
0x1800b9f86  mov     rsi, r14
0x1800b9f89  cmp     rbx, 0Fh
0x1800b9f8d  ja      short loc_1800B9FC5
0x1800b9f8f  lea     r8, [rbp+nSize]; nSize
0x1800b9f93  mov     [rbp+nSize], 10h
0x1800b9f9a  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800b9f9e  xor     ecx, ecx; NameType
0x1800b9fa0  call    cs:__imp_GetComputerNameExW
0x1800b9fa6  test    eax, eax
0x1800b9fa8  jz      short loc_1800B9FC5
0x1800b9faa  mov     eax, [rbp+nSize]
0x1800b9fad  cmp     rbx, rax
0x1800b9fb0  jnz     short loc_1800B9FC5
0x1800b9fb2  mov     r8, rbx; MaxCount
0x1800b9fb5  lea     rcx, [rbp+Buffer]; String1
0x1800b9fb9  mov     rdx, rdi; String2
0x1800b9fbc  call    _wcsnicmp
0x1800b9fc1  test    eax, eax
0x1800b9fc3  jz      short loc_1800BA038
0x1800b9fc5  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x1800b9fcb  lea     r15, [rbx-1]
0x1800b9fcf  mov     edx, 20Ah; uBytes
0x1800b9fd4  cmovnz  r15, rbx
0x1800b9fd8  xor     ecx, ecx; uFlags
0x1800b9fda  call    cs:__imp_LocalAlloc
0x1800b9fe0  mov     rbx, rax
0x1800b9fe3  test    rax, rax
0x1800b9fe6  jnz     short loc_1800B9FF2
0x1800b9fe8  mov     ebx, 0C0000017h
0x1800b9fed  jmp     loc_1800BA13F
0x1800b9ff2  lea     r8, [rbp+nSize]; nSize
0x1800b9ff6  mov     [rbp+nSize], 105h
0x1800b9ffd  mov     rdx, rbx; lpBuffer
0x1800ba000  mov     ecx, 3; NameType
0x1800ba005  call    cs:__imp_GetComputerNameExW
0x1800ba00b  test    eax, eax
0x1800ba00d  jz      short loc_1800BA02D
0x1800ba00f  mov     eax, [rbp+nSize]
0x1800ba012  cmp     r15, rax
0x1800ba015  jnz     short loc_1800BA02D
0x1800ba017  mov     r8, r15; MaxCount
0x1800ba01a  mov     rdx, rdi; String2
0x1800ba01d  mov     rcx, rbx; String1
0x1800ba020  call    _wcsnicmp
0x1800ba025  neg     eax
0x1800ba027  sbb     rcx, rcx
0x1800ba02a  and     rsi, rcx
0x1800ba02d  mov     rcx, rbx; hMem
0x1800ba030  call    cs:__imp_LocalFree
0x1800ba036  jmp     short loc_1800BA03B
0x1800ba038  mov     rsi, r13
0x1800ba03b  mov     edx, 18h; uBytes
0x1800ba040  xor     ecx, ecx; uFlags
0x1800ba042  call    cs:__imp_LocalAlloc
0x1800ba048  mov     rdi, rax
0x1800ba04b  test    rax, rax
0x1800ba04e  jz      short loc_1800B9FE8
0x1800ba050  mov     r11d, 0Ch
0x1800ba056  lea     r9, aPipe; "\\PIPE\\"
0x1800ba05d  mov     edx, r11d
0x1800ba060  mov     rcx, rax
0x1800ba063  call    RtlStringCopyWorkerW_1
0x1800ba068  test    eax, eax
0x1800ba06a  js      loc_1800BA131
0x1800ba070  mov     r8d, r11d
0x1800ba073  mov     rax, rdi
0x1800ba076  cmp     [rax], r13w
0x1800ba07a  jz      short loc_1800BA086
0x1800ba07c  add     rax, 2
0x1800ba080  sub     r8, 1
0x1800ba084  jnz     short loc_1800BA076
0x1800ba086  mov     rcx, r11
0x1800ba089  mov     rax, r8
0x1800ba08c  sub     rcx, r8
0x1800ba08f  neg     rax
0x1800ba092  sbb     rdx, rdx
0x1800ba095  and     rdx, rcx
0x1800ba098  test    r8, r8
0x1800ba09b  jz      loc_1800BA131
0x1800ba0a1  sub     r11, rdx
0x1800ba0a4  lea     rcx, [rdi+rdx*2]
0x1800ba0a8  mov     rdx, r11
0x1800ba0ab  lea     r9, aSamr; "samr"
0x1800ba0b2  call    RtlStringCopyWorkerW_1
0x1800ba0b7  test    eax, eax
0x1800ba0b9  js      short loc_1800BA131
0x1800ba0bb  lea     rax, [rbp+String]
0x1800ba0bf  mov     r9, rdi; Endpoint
0x1800ba0c2  mov     [rsp+70h+StringBinding], rax; StringBinding
0x1800ba0c7  lea     rdx, aNcacnNp; "ncacn_np"
0x1800ba0ce  mov     r8, rsi; NetworkAddr
0x1800ba0d1  mov     [rsp+70h+Options], r13; Options
0x1800ba0d6  xor     ecx, ecx; ObjUuid
0x1800ba0d8  call    cs:__imp_RpcStringBindingComposeW
0x1800ba0de  mov     rcx, rdi; hMem
0x1800ba0e1  mov     ebx, eax
0x1800ba0e3  call    cs:__imp_LocalFree
0x1800ba0e9  test    ebx, ebx
0x1800ba0eb  jnz     loc_1800B9FE8
0x1800ba0f1  mov     rcx, [rbp+String]; StringBinding
0x1800ba0f5  mov     rdx, r12; Binding
0x1800ba0f8  call    cs:__imp_RpcBindingFromStringBindingW
0x1800ba0fe  lea     rcx, [rbp+String]; String
0x1800ba102  mov     ebx, eax
0x1800ba104  call    cs:__imp_RpcStringFreeW
0x1800ba10a  test    ebx, ebx
0x1800ba10c  jz      short loc_1800BA12C
0x1800ba10e  lea     eax, [rbx-6AAh]
0x1800ba114  mov     [r12], r13
0x1800ba118  mov     ebx, 0C0000017h
0x1800ba11d  cmp     eax, 1
0x1800ba120  mov     ecx, 0C0000122h
0x1800ba125  cmova   ecx, ebx
0x1800ba128  mov     ebx, ecx
0x1800ba12a  jmp     short loc_1800BA13F
0x1800ba12c  mov     ebx, r13d
0x1800ba12f  jmp     short loc_1800BA13F
0x1800ba131  mov     rcx, rdi; hMem
0x1800ba134  call    cs:__imp_LocalFree
0x1800ba13a  mov     ebx, 0C000000Dh
0x1800ba13f  test    r14, r14
0x1800ba142  jz      short loc_1800BA14D
0x1800ba144  mov     rcx, r14; hMem
0x1800ba147  call    cs:__imp_LocalFree
0x1800ba14d  mov     eax, ebx
0x1800ba14f  mov     rcx, [rbp+var_10]
0x1800ba153  xor     rcx, rsp; StackCookie
0x1800ba156  call    __security_check_cookie
0x1800ba15b  mov     rbx, [rsp+70h+arg_8]
0x1800ba163  add     rsp, 70h
0x1800ba167  pop     r15
0x1800ba169  pop     r14
0x1800ba16b  pop     r13
0x1800ba16d  pop     r12
0x1800ba16f  pop     rdi
0x1800ba170  pop     rsi
0x1800ba171  pop     rbp
0x1800ba172  retn
```
