# RpcpBindRpc

- ea: `0x1800137b8`
- end: `0x180013a3c`
- name: `RpcpBindRpc`
- size: `644`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800136d0`

## callees

- `0x1800137b8`
- `0x180017270`
- `0x1800195b8`
- `0x18004f902`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800138bc`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180013921`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x1800138bc`
- `api-ms-win-core-crt-l1-1-0!_wcsnicmp` at `0x180013921`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013854`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800138db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013946`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013854`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800138db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013946`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013932`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001396c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800139bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013a10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013932`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001396c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800139bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013a10`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800138a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180013906`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800138a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180013906`
- `RPCRT4!RpcStringFreeW` at `0x1800139dd`
- `RPCRT4!RpcStringFreeW` at `0x1800139dd`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800139d1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800139d1`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800139b1`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800139b1`

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
  unsigned __int16 *v15; // rdi
  int v16; // eax
  unsigned __int16 *v17; // rcx
  RPC_STATUS v18; // ebx
  RPC_STATUS v19; // ebx
  int v20; // ecx
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
  v15 = v14;
  if ( !v14 )
  {
LABEL_21:
    v8 = -1073741801;
    goto LABEL_38;
  }
  v16 = RtlStringCbCopyW(v14, 28, L"\\PIPE\\");
  v17 = v15;
  if ( v16 >= 0 )
  {
    if ( (int)RtlStringCbCatW(v15, 28, L"lsarpc") >= 0 )
    {
      v18 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_np", (RPC_WSTR)v9, v15, 0, &String);
      LocalFree(v15);
      if ( !v18 )
      {
        v19 = RpcBindingFromStringBindingW(String, a4);
        RpcStringFreeW(&String);
        if ( v19 )
        {
          *a4 = 0;
          v20 = -1073741534;
          if ( (unsigned int)(v19 - 1706) > 1 )
            v20 = -1073741801;
          v8 = v20;
        }
        else
        {
          v8 = 0;
        }
        goto LABEL_38;
      }
      goto LABEL_21;
    }
    v17 = v15;
  }
  LocalFree(v17);
  v8 = -1073741811;
LABEL_38:
  if ( v6 )
    LocalFree(v6);
  return v8;
}

```

## disassembly

```asm
0x1800137b8  mov     [rsp-38h+arg_8], rbx
0x1800137bd  push    rbp
0x1800137be  push    rsi
0x1800137bf  push    rdi
0x1800137c0  push    r12
0x1800137c2  push    r13
0x1800137c4  push    r14
0x1800137c6  push    r15
0x1800137c8  mov     rbp, rsp
0x1800137cb  sub     rsp, 70h
0x1800137cf  mov     rax, cs:__security_cookie
0x1800137d6  xor     rax, rsp
0x1800137d9  mov     [rbp+var_10], rax
0x1800137dd  xor     r13d, r13d
0x1800137e0  mov     r12, r9
0x1800137e3  mov     [rbp+String], r13
0x1800137e7  mov     rdi, rcx
0x1800137ea  mov     [rbp+nSize], r13d
0x1800137ee  mov     r14d, r13d
0x1800137f1  mov     [r9], r13
0x1800137f4  test    rcx, rcx
0x1800137f7  jz      loc_18001393A
0x1800137fd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013801  inc     rbx
0x180013804  cmp     [rcx+rbx*2], r13w
0x180013809  jnz     short loc_180013801
0x18001380b  cmp     [rcx], r13w
0x18001380f  jz      loc_18001393A
0x180013815  mov     esi, 5Ch ; '\'
0x18001381a  cmp     [rcx], si
0x18001381d  jnz     short loc_18001384A
0x18001381f  cmp     [rcx+2], si
0x180013823  jnz     short loc_18001382B
0x180013825  add     rbx, 0FFFFFFFFFFFFFFFEh
0x180013829  jnz     short loc_180013835
0x18001382b  mov     ebx, 0C0000122h
0x180013830  jmp     loc_180013A16
0x180013835  lea     rax, [rcx+4]
0x180013839  mov     rsi, rdi
0x18001383c  test    rax, rax
0x18001383f  jz      loc_18001393D
0x180013845  mov     rdi, rax
0x180013848  jmp     short loc_180013889
0x18001384a  lea     rdx, ds:6[rbx*2]; uBytes
0x180013852  xor     ecx, ecx; uFlags
0x180013854  call    cs:__imp_LocalAlloc
0x18001385a  mov     r14, rax
0x18001385d  test    rax, rax
0x180013860  jnz     short loc_18001386C
0x180013862  mov     ebx, 0C0000017h
0x180013867  jmp     loc_180013A16
0x18001386c  lea     r8, ds:2[rbx*2]; Size
0x180013874  mov     dword ptr [rax], 5C005Ch
0x18001387a  lea     rcx, [rax+4]; void *
0x18001387e  mov     rdx, rdi; Src
0x180013881  call    memcpy_0
0x180013886  mov     rsi, r14
0x180013889  cmp     rbx, 0Fh
0x18001388d  ja      short loc_1800138C6
0x18001388f  lea     r8, [rbp+nSize]; nSize
0x180013893  mov     [rbp+nSize], 10h
0x18001389a  lea     rdx, [rbp+Buffer]; lpBuffer
0x18001389e  xor     ecx, ecx; NameType
0x1800138a0  call    cs:__imp_GetComputerNameExW
0x1800138a6  test    eax, eax
0x1800138a8  jz      short loc_1800138C6
0x1800138aa  mov     eax, [rbp+nSize]
0x1800138ad  cmp     rbx, rax
0x1800138b0  jnz     short loc_1800138C6
0x1800138b2  mov     r8, rbx; MaxCount
0x1800138b5  lea     rcx, [rbp+Buffer]; String1
0x1800138b9  mov     rdx, rdi; String2
0x1800138bc  call    cs:__imp__wcsnicmp
0x1800138c2  test    eax, eax
0x1800138c4  jz      short loc_18001393A
0x1800138c6  cmp     word ptr [rdi+rbx*2-2], 2Eh ; '.'
0x1800138cc  lea     r15, [rbx-1]
0x1800138d0  mov     edx, 20Ah; uBytes
0x1800138d5  cmovnz  r15, rbx
0x1800138d9  xor     ecx, ecx; uFlags
0x1800138db  call    cs:__imp_LocalAlloc
0x1800138e1  mov     rbx, rax
0x1800138e4  test    rax, rax
0x1800138e7  jnz     short loc_1800138F3
0x1800138e9  mov     ebx, 0C0000017h
0x1800138ee  jmp     loc_180013A08
0x1800138f3  lea     r8, [rbp+nSize]; nSize
0x1800138f7  mov     [rbp+nSize], 105h
0x1800138fe  mov     rdx, rbx; lpBuffer
0x180013901  mov     ecx, 3; NameType
0x180013906  call    cs:__imp_GetComputerNameExW
0x18001390c  test    eax, eax
0x18001390e  jz      short loc_18001392F
0x180013910  mov     eax, [rbp+nSize]
0x180013913  cmp     r15, rax
0x180013916  jnz     short loc_18001392F
0x180013918  mov     r8, r15; MaxCount
0x18001391b  mov     rdx, rdi; String2
0x18001391e  mov     rcx, rbx; String1
0x180013921  call    cs:__imp__wcsnicmp
0x180013927  neg     eax
0x180013929  sbb     rcx, rcx
0x18001392c  and     rsi, rcx
0x18001392f  mov     rcx, rbx; hMem
0x180013932  call    cs:__imp_LocalFree
0x180013938  jmp     short loc_18001393D
0x18001393a  mov     rsi, r13
0x18001393d  mov     ebx, 1Ch
0x180013942  xor     ecx, ecx; uFlags
0x180013944  mov     edx, ebx; uBytes
0x180013946  call    cs:__imp_LocalAlloc
0x18001394c  mov     rdi, rax
0x18001394f  test    rax, rax
0x180013952  jz      short loc_1800138E9
0x180013954  lea     r8, aPipe; "\\PIPE\\"
0x18001395b  mov     edx, ebx
0x18001395d  mov     rcx, rax
0x180013960  call    RtlStringCbCopyW
0x180013965  mov     rcx, rdi; hMem
0x180013968  test    eax, eax
0x18001396a  jns     short loc_18001397C
0x18001396c  call    cs:__imp_LocalFree
0x180013972  mov     ebx, 0C000000Dh
0x180013977  jmp     loc_180013A08
0x18001397c  lea     r8, aLsarpc; "lsarpc"
0x180013983  mov     rdx, rbx
0x180013986  call    RtlStringCbCatW
0x18001398b  test    eax, eax
0x18001398d  jns     short loc_180013994
0x18001398f  mov     rcx, rdi
0x180013992  jmp     short loc_18001396C
0x180013994  lea     rax, [rbp+String]
0x180013998  mov     r9, rdi; Endpoint
0x18001399b  mov     [rsp+70h+StringBinding], rax; StringBinding
0x1800139a0  lea     rdx, ProtSeq; "ncacn_np"
0x1800139a7  mov     r8, rsi; NetworkAddr
0x1800139aa  mov     [rsp+70h+Options], r13; Options
0x1800139af  xor     ecx, ecx; ObjUuid
0x1800139b1  call    cs:__imp_RpcStringBindingComposeW
0x1800139b7  mov     rcx, rdi; hMem
0x1800139ba  mov     ebx, eax
0x1800139bc  call    cs:__imp_LocalFree
0x1800139c2  test    ebx, ebx
0x1800139c4  jnz     loc_1800138E9
0x1800139ca  mov     rcx, [rbp+String]; StringBinding
0x1800139ce  mov     rdx, r12; Binding
0x1800139d1  call    cs:__imp_RpcBindingFromStringBindingW
0x1800139d7  lea     rcx, [rbp+String]; String
0x1800139db  mov     ebx, eax
0x1800139dd  call    cs:__imp_RpcStringFreeW
0x1800139e3  test    ebx, ebx
0x1800139e5  jz      short loc_180013A05
0x1800139e7  lea     eax, [rbx-6AAh]
0x1800139ed  mov     [r12], r13
0x1800139f1  mov     ebx, 0C0000017h
0x1800139f6  cmp     eax, 1
0x1800139f9  mov     ecx, 0C0000122h
0x1800139fe  cmova   ecx, ebx
0x180013a01  mov     ebx, ecx
0x180013a03  jmp     short loc_180013A08
0x180013a05  mov     ebx, r13d
0x180013a08  test    r14, r14
0x180013a0b  jz      short loc_180013A16
0x180013a0d  mov     rcx, r14; hMem
0x180013a10  call    cs:__imp_LocalFree
0x180013a16  mov     eax, ebx
0x180013a18  mov     rcx, [rbp+var_10]
0x180013a1c  xor     rcx, rsp; StackCookie
0x180013a1f  call    __security_check_cookie
0x180013a24  mov     rbx, [rsp+70h+arg_8]
0x180013a2c  add     rsp, 70h
0x180013a30  pop     r15
0x180013a32  pop     r14
0x180013a34  pop     r13
0x180013a36  pop     r12
0x180013a38  pop     rdi
0x180013a39  pop     rsi
0x180013a3a  pop     rbp
0x180013a3b  retn
```
