# RpcpBindRpc

- ea: `0x180014a78`
- end: `0x180014cf6`
- name: `RpcpBindRpc`
- size: `638`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014a30`

## callees

- `0x180014a78`
- `0x180021f6c`
- `0x180021fe4`
- `0x180022047`
- `0x180022190`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180014b7c`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180014be1`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180014b7c`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180014be1`
- `RPCRT4!RpcStringFreeW` at `0x180014c97`
- `RPCRT4!RpcStringFreeW` at `0x180014c97`
- `RPCRT4!RpcStringBindingComposeW` at `0x180014c6b`
- `RPCRT4!RpcStringBindingComposeW` at `0x180014c6b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180014c8b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180014c8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014bf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014cca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014bf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014cca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014b14`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014b9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014c06`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014b14`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014b9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014c06`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180014b60`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180014bc6`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180014b60`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180014bc6`

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
  int v17; // eax
  unsigned __int16 *v18; // rcx
  RPC_STATUS v19; // ebx
  RPC_STATUS v20; // ebx
  int v21; // ecx
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
      if ( v7 == nSize && !_wcsnicmp(Buffer, (const wchar_t *)v5, v7) )
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
    v9 &= -(__int64)(_wcsnicmp(v13, (const wchar_t *)v5, v11) != 0);
  LocalFree(v13);
LABEL_27:
  v14 = (unsigned __int16 *)LocalAlloc(0, 0x1Cu);
  v16 = v14;
  if ( !v14 )
  {
LABEL_21:
    v8 = -1073741801;
    goto LABEL_38;
  }
  v17 = RtlStringCopyWorkerW(v14, 14, v15, L"\\PIPE\\");
  v18 = v16;
  if ( v17 >= 0 )
  {
    if ( (int)RtlStringCbCatW(v16, 28) >= 0 )
    {
      v19 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", (RPC_WSTR)v9, v16, 0, &String);
      LocalFree(v16);
      if ( !v19 )
      {
        v20 = RpcBindingFromStringBindingW(String, a4);
        RpcStringFreeW(&String);
        if ( v20 )
        {
          *a4 = 0;
          v21 = -1073741534;
          if ( (unsigned int)(v20 - 1706) > 1 )
            v21 = -1073741801;
          v8 = v21;
        }
        else
        {
          v8 = 0;
        }
        goto LABEL_38;
      }
      goto LABEL_21;
    }
    v18 = v16;
  }
  LocalFree(v18);
  v8 = -1073741811;
LABEL_38:
  if ( v6 )
    LocalFree(v6);
  return v8;
}

```

## disassembly

```asm
0x180014a78  mov     [rsp-38h+arg_8], rbx
0x180014a7d  push    rbp
0x180014a7e  push    rsi
0x180014a7f  push    rdi
0x180014a80  push    r12
0x180014a82  push    r13
0x180014a84  push    r14
0x180014a86  push    r15
0x180014a88  mov     rbp, rsp
0x180014a8b  sub     rsp, 70h
0x180014a8f  mov     rax, cs:__security_cookie
0x180014a96  xor     rax, rsp
0x180014a99  mov     [rbp+var_10], rax
0x180014a9d  xor     r13d, r13d
0x180014aa0  mov     r12, r9
0x180014aa3  mov     [rbp+String], r13
0x180014aa7  mov     rdi, rcx
0x180014aaa  mov     [rbp+nSize], r13d
0x180014aae  mov     r14d, r13d
0x180014ab1  mov     [r9], r13
0x180014ab4  test    rcx, rcx
0x180014ab7  jz      loc_180014BFA
0x180014abd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180014ac1  inc     rbx
0x180014ac4  cmp     [rcx+rbx*2], r13w
0x180014ac9  jnz     short loc_180014AC1
0x180014acb  cmp     [rcx], r13w
0x180014acf  jz      loc_180014BFA
0x180014ad5  mov     esi, 5Ch ; '\'
0x180014ada  cmp     [rcx], si
0x180014add  jnz     short loc_180014B0A
0x180014adf  cmp     [rcx+2], si
0x180014ae3  jnz     short loc_180014AEB
0x180014ae5  add     rbx, 0FFFFFFFFFFFFFFFEh
0x180014ae9  jnz     short loc_180014AF5
0x180014aeb  mov     ebx, 0C0000122h
0x180014af0  jmp     loc_180014CD0
0x180014af5  lea     rax, [rcx+4]
0x180014af9  mov     rsi, rdi
0x180014afc  test    rax, rax
0x180014aff  jz      loc_180014BFD
0x180014b05  mov     rdi, rax
0x180014b08  jmp     short loc_180014B49
0x180014b0a  lea     rdx, ds:6[rbx*2]; uBytes
0x180014b12  xor     ecx, ecx; uFlags
0x180014b14  call    cs:__imp_LocalAlloc
0x180014b1a  mov     r14, rax
0x180014b1d  test    rax, rax
0x180014b20  jnz     short loc_180014B2C
0x180014b22  mov     ebx, 0C0000017h
0x180014b27  jmp     loc_180014CD0
0x180014b2c  lea     r8, ds:2[rbx*2]; Size
0x180014b34  mov     dword ptr [rax], 5C005Ch
0x180014b3a  lea     rcx, [rax+4]; void *
0x180014b3e  mov     rdx, rdi; Src
0x180014b41  call    memcpy_0
0x180014b46  mov     rsi, r14
0x180014b49  cmp     rbx, 0Fh
0x180014b4d  ja      short loc_180014B86
0x180014b4f  lea     r8, [rbp+nSize]; nSize
0x180014b53  mov     [rbp+nSize], 10h
0x180014b5a  lea     rdx, [rbp+Buffer]; lpBuffer
0x180014b5e  xor     ecx, ecx; NameType
0x180014b60  call    cs:__imp_GetComputerNameExW
0x180014b66  test    eax, eax
0x180014b68  jz      short loc_180014B86
0x180014b6a  mov     eax, [rbp+nSize]
0x180014b6d  cmp     rbx, rax
0x180014b70  jnz     short loc_180014B86
0x180014b72  mov     r8, rbx; MaxCount
0x180014b75  lea     rcx, [rbp+Buffer]; String1
0x180014b79  mov     rdx, rdi; String2
0x180014b7c  call    cs:__imp__wcsnicmp
0x180014b82  test    eax, eax
0x180014b84  jz      short loc_180014BFA
0x180014b86  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x180014b8c  lea     r15, [rbx-1]
0x180014b90  mov     edx, 20Ah; uBytes
0x180014b95  cmovnz  r15, rbx
0x180014b99  xor     ecx, ecx; uFlags
0x180014b9b  call    cs:__imp_LocalAlloc
0x180014ba1  mov     rbx, rax
0x180014ba4  test    rax, rax
0x180014ba7  jnz     short loc_180014BB3
0x180014ba9  mov     ebx, 0C0000017h
0x180014bae  jmp     loc_180014CC2
0x180014bb3  lea     r8, [rbp+nSize]; nSize
0x180014bb7  mov     [rbp+nSize], 105h
0x180014bbe  mov     rdx, rbx; lpBuffer
0x180014bc1  mov     ecx, 3; NameType
0x180014bc6  call    cs:__imp_GetComputerNameExW
0x180014bcc  test    eax, eax
0x180014bce  jz      short loc_180014BEF
0x180014bd0  mov     eax, [rbp+nSize]
0x180014bd3  cmp     r15, rax
0x180014bd6  jnz     short loc_180014BEF
0x180014bd8  mov     r8, r15; MaxCount
0x180014bdb  mov     rdx, rdi; String2
0x180014bde  mov     rcx, rbx; String1
0x180014be1  call    cs:__imp__wcsnicmp
0x180014be7  neg     eax
0x180014be9  sbb     rcx, rcx
0x180014bec  and     rsi, rcx
0x180014bef  mov     rcx, rbx; hMem
0x180014bf2  call    cs:__imp_LocalFree
0x180014bf8  jmp     short loc_180014BFD
0x180014bfa  mov     rsi, r13
0x180014bfd  mov     ebx, 1Ch
0x180014c02  xor     ecx, ecx; uFlags
0x180014c04  mov     edx, ebx; uBytes
0x180014c06  call    cs:__imp_LocalAlloc
0x180014c0c  mov     rdi, rax
0x180014c0f  test    rax, rax
0x180014c12  jz      short loc_180014BA9
0x180014c14  lea     r9, aPipe; "\\PIPE\\"
0x180014c1b  mov     rcx, rax
0x180014c1e  lea     edx, [rbx-0Eh]
0x180014c21  call    RtlStringCopyWorkerW
0x180014c26  mov     rcx, rdi; hMem
0x180014c29  test    eax, eax
0x180014c2b  jns     short loc_180014C3D
0x180014c2d  call    cs:__imp_LocalFree
0x180014c33  mov     ebx, 0C000000Dh
0x180014c38  jmp     loc_180014CC2
0x180014c3d  mov     rdx, rbx
0x180014c40  call    RtlStringCbCatW
0x180014c45  test    eax, eax
0x180014c47  jns     short loc_180014C4E
0x180014c49  mov     rcx, rdi
0x180014c4c  jmp     short loc_180014C2D
0x180014c4e  lea     rax, [rbp+String]
0x180014c52  mov     r9, rdi; Endpoint
0x180014c55  mov     [rsp+70h+StringBinding], rax; StringBinding
0x180014c5a  lea     rdx, aNcacnNp; "ncacn_np"
0x180014c61  mov     r8, rsi; NetworkAddr
0x180014c64  mov     [rsp+70h+Options], r13; Options
0x180014c69  xor     ecx, ecx; ObjUuid
0x180014c6b  call    cs:__imp_RpcStringBindingComposeW
0x180014c71  mov     rcx, rdi; hMem
0x180014c74  mov     ebx, eax
0x180014c76  call    cs:__imp_LocalFree
0x180014c7c  test    ebx, ebx
0x180014c7e  jnz     loc_180014BA9
0x180014c84  mov     rcx, [rbp+String]; StringBinding
0x180014c88  mov     rdx, r12; Binding
0x180014c8b  call    cs:__imp_RpcBindingFromStringBindingW
0x180014c91  lea     rcx, [rbp+String]; String
0x180014c95  mov     ebx, eax
0x180014c97  call    cs:__imp_RpcStringFreeW
0x180014c9d  test    ebx, ebx
0x180014c9f  jz      short loc_180014CBF
0x180014ca1  lea     eax, [rbx-6AAh]
0x180014ca7  mov     [r12], r13
0x180014cab  mov     ebx, 0C0000017h
0x180014cb0  cmp     eax, 1
0x180014cb3  mov     ecx, 0C0000122h
0x180014cb8  cmova   ecx, ebx
0x180014cbb  mov     ebx, ecx
0x180014cbd  jmp     short loc_180014CC2
0x180014cbf  mov     ebx, r13d
0x180014cc2  test    r14, r14
0x180014cc5  jz      short loc_180014CD0
0x180014cc7  mov     rcx, r14; hMem
0x180014cca  call    cs:__imp_LocalFree
0x180014cd0  mov     eax, ebx
0x180014cd2  mov     rcx, [rbp+var_10]
0x180014cd6  xor     rcx, rsp; StackCookie
0x180014cd9  call    __security_check_cookie
0x180014cde  mov     rbx, [rsp+70h+arg_8]
0x180014ce6  add     rsp, 70h
0x180014cea  pop     r15
0x180014cec  pop     r14
0x180014cee  pop     r13
0x180014cf0  pop     r12
0x180014cf2  pop     rdi
0x180014cf3  pop     rsi
0x180014cf4  pop     rbp
0x180014cf5  retn
```
