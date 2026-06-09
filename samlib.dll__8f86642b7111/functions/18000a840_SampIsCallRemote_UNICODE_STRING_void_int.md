# SampIsCallRemote(_UNICODE_STRING *,void *,int *)

- ea: `0x18000a840`
- end: `0x18000aa6e`
- name: `?SampIsCallRemote@@YAJPEAU_UNICODE_STRING@@PEAXPEAH@Z`
- size: `558`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a3f0`

## callees

- `0x18000a500`
- `0x18000a840`
- `0x18000b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000aa16`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000aa16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a942`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a942`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aa4f`
- `ntdll!RtlInitUnicodeString` at `0x18000a975`
- `ntdll!RtlInitUnicodeString` at `0x18000a9a7`
- `ntdll!RtlInitUnicodeString` at `0x18000a975`
- `ntdll!RtlInitUnicodeString` at `0x18000a9a7`
- `ntdll!RtlEqualComputerName` at `0x18000a983`
- `ntdll!RtlEqualComputerName` at `0x18000a983`
- `ntdll!RtlEqualUnicodeString` at `0x18000a9b8`
- `ntdll!RtlEqualUnicodeString` at `0x18000a9b8`
- `RPCRT4!RpcStringFreeW` at `0x18000aa27`
- `RPCRT4!RpcStringFreeW` at `0x18000aa31`
- `RPCRT4!RpcStringFreeW` at `0x18000aa63`
- `RPCRT4!RpcStringFreeW` at `0x18000aa27`
- `RPCRT4!RpcStringFreeW` at `0x18000aa31`
- `RPCRT4!RpcStringFreeW` at `0x18000aa63`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000a9d9`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000a9d9`
- `RPCRT4!RpcStringBindingParseW` at `0x18000a9fb`
- `RPCRT4!RpcStringBindingParseW` at `0x18000a9fb`
- `DNSAPI!DnsNameCompare_W` at `0x18000a931`
- `DNSAPI!DnsNameCompare_W` at `0x18000a931`

## pseudocode

```c
__int64 __fastcall SampIsCallRemote(__m128i *a1, void **a2, int *a3)
{
  int LocalMachineName; // edi
  WCHAR *v7; // r14
  __m128i v9; // xmm0
  unsigned __int16 v10; // cx
  _WORD *v11; // xmm0_8
  int v12; // eax
  void *v13; // rcx
  struct _UNICODE_STRING ComputerName1; // [rsp+30h] [rbp-30h] BYREF
  PCWSTR pName1[2]; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int8 v17; // [rsp+A0h] [rbp+40h] BYREF
  PCWSTR pName2; // [rsp+B0h] [rbp+50h] BYREF
  RPC_WSTR StringBinding; // [rsp+B8h] [rbp+58h] BYREF

  *a3 = 1;
  pName2 = 0;
  pName1[0] = 0;
  v17 = 0;
  StringBinding = 0;
  LocalMachineName = 0;
  v7 = 0;
  if ( !a1 )
  {
    if ( !a2 )
    {
LABEL_3:
      *a3 = 0;
      return (unsigned int)LocalMachineName;
    }
    goto LABEL_23;
  }
  ComputerName1 = 0;
  if ( !a1->m128i_i16[0] || !a1->m128i_i64[1] )
    goto LABEL_3;
  LocalMachineName = SampGetLocalMachineName(ComputerNameDnsFullyQualified, (unsigned __int16 **)&pName2);
  if ( LocalMachineName >= 0 )
  {
    v9 = *a1;
    v10 = _mm_cvtsi128_si32(*a1);
    ComputerName1 = (struct _UNICODE_STRING)*a1;
    if ( v10 > 4u )
    {
      v11 = (_WORD *)_mm_srli_si128(v9, 8).m128i_u64[0];
      if ( *v11 == 92 && v11[1] == 92 )
      {
        ComputerName1.Buffer = v11 + 2;
        ComputerName1.MaximumLength -= 4;
        ComputerName1.Length = v10 - 4;
      }
    }
    v12 = SampNullTerminateUnicodeString(&ComputerName1, (unsigned __int16 **)pName1, &v17);
    v7 = (WCHAR *)pName1[0];
    LocalMachineName = v12;
    if ( v12 >= 0 )
    {
      if ( DnsNameCompare_W(pName1[0], pName2) )
        *a3 = 0;
      LocalFree((HLOCAL)pName2);
      pName2 = 0;
      if ( *a3 )
      {
        *(_OWORD *)pName1 = 0;
        LocalMachineName = SampGetLocalMachineName(ComputerNameNetBIOS, (unsigned __int16 **)&pName2);
        if ( LocalMachineName < 0 )
          goto LABEL_29;
        RtlInitUnicodeString((PUNICODE_STRING)pName1, pName2);
        if ( RtlEqualComputerName(&ComputerName1, (PUNICODE_STRING)pName1) )
          *a3 = 0;
        if ( *a3 )
        {
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"127.0.0.1");
          if ( RtlEqualUnicodeString(&DestinationString, &ComputerName1, 1u) )
            *a3 = 0;
        }
      }
      if ( a2 )
      {
LABEL_23:
        v13 = *a2;
        pName1[0] = 0;
        *(_QWORD *)&ComputerName1.Length = 0;
        if ( !RpcBindingToStringBindingW(v13, &StringBinding)
          && !RpcStringBindingParseW(StringBinding, 0, (RPC_WSTR *)&ComputerName1, (RPC_WSTR *)pName1, 0, 0) )
        {
          if ( !pName1[0] || !(unsigned int)_o__wcsicmp(*(_QWORD *)&ComputerName1.Length, L"ncalrpc") )
            *a3 = 0;
          RpcStringFreeW((RPC_WSTR *)&ComputerName1);
          RpcStringFreeW((RPC_WSTR *)pName1);
        }
      }
    }
  }
LABEL_29:
  if ( pName2 )
    LocalFree((HLOCAL)pName2);
  if ( v17 )
    LocalFree(v7);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return (unsigned int)LocalMachineName;
}

```

## disassembly

```asm
0x18000a840  push    rbp
0x18000a842  push    rbx
0x18000a843  push    rsi
0x18000a844  push    rdi
0x18000a845  push    r12
0x18000a847  push    r14
0x18000a849  push    r15
0x18000a84b  mov     rbp, rsp
0x18000a84e  sub     rsp, 60h
0x18000a852  xor     r12d, r12d
0x18000a855  mov     dword ptr [r8], 1
0x18000a85c  mov     [rbp+pName2], r12
0x18000a860  mov     rbx, r8
0x18000a863  mov     [rbp+pName1], r12
0x18000a867  mov     r15, rdx
0x18000a86a  mov     [rbp+arg_0], r12b
0x18000a86e  mov     rsi, rcx
0x18000a871  mov     [rbp+StringBinding], r12
0x18000a875  mov     edi, r12d
0x18000a878  mov     r14d, r12d
0x18000a87b  test    rcx, rcx
0x18000a87e  jnz     short loc_18000A89D
0x18000a880  test    rdx, rdx
0x18000a883  jnz     loc_18000A9CA
0x18000a889  mov     [r8], r12d
0x18000a88c  mov     eax, edi
0x18000a88e  add     rsp, 60h
0x18000a892  pop     r15
0x18000a894  pop     r14
0x18000a896  pop     r12
0x18000a898  pop     rdi
0x18000a899  pop     rsi
0x18000a89a  pop     rbx
0x18000a89b  pop     rbp
0x18000a89c  retn
0x18000a89d  xorps   xmm0, xmm0
0x18000a8a0  movups  xmmword ptr [rbp+ComputerName1.Length], xmm0
0x18000a8a4  cmp     [rcx], r12w
0x18000a8a8  jz      short loc_18000A889
0x18000a8aa  cmp     [rcx+8], r12
0x18000a8ae  jz      short loc_18000A889
0x18000a8b0  lea     rdx, [rbp+pName2]; unsigned __int16 **
0x18000a8b4  mov     ecx, 3; NameType
0x18000a8b9  call    ?SampGetLocalMachineName@@YAJW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z; SampGetLocalMachineName(_COMPUTER_NAME_FORMAT,ushort * *)
0x18000a8be  mov     edi, eax
0x18000a8c0  test    eax, eax
0x18000a8c2  js      loc_18000AA37
0x18000a8c8  movups  xmm0, xmmword ptr [rsi]
0x18000a8cb  mov     edx, 4
0x18000a8d0  movd    ecx, xmm0
0x18000a8d4  movups  xmmword ptr [rbp+ComputerName1.Length], xmm0
0x18000a8d8  cmp     cx, dx
0x18000a8db  jbe     short loc_18000A90B
0x18000a8dd  psrldq  xmm0, 8
0x18000a8e2  movq    rax, xmm0
0x18000a8e7  cmp     word ptr [rax], 5Ch ; '\'
0x18000a8eb  jnz     short loc_18000A90B
0x18000a8ed  cmp     word ptr [rax+2], 5Ch ; '\'
0x18000a8f2  jnz     short loc_18000A90B
0x18000a8f4  add     rax, rdx
0x18000a8f7  mov     [rbp+ComputerName1.Buffer], rax
0x18000a8fb  mov     eax, 0FFFCh
0x18000a900  add     cx, ax
0x18000a903  add     [rbp+ComputerName1.MaximumLength], ax
0x18000a907  mov     [rbp+ComputerName1.Length], cx
0x18000a90b  lea     r8, [rbp+arg_0]; unsigned __int8 *
0x18000a90f  lea     rdx, [rbp+pName1]; unsigned __int16 **
0x18000a913  lea     rcx, [rbp+ComputerName1]; struct _UNICODE_STRING *
0x18000a917  call    ?SampNullTerminateUnicodeString@@YAJPEAU_UNICODE_STRING@@PEAPEAGPEAE@Z; SampNullTerminateUnicodeString(_UNICODE_STRING *,ushort * *,uchar *)
0x18000a91c  mov     r14, [rbp+pName1]
0x18000a920  mov     edi, eax
0x18000a922  test    eax, eax
0x18000a924  js      loc_18000AA37
0x18000a92a  mov     rdx, [rbp+pName2]; pName2
0x18000a92e  mov     rcx, r14; pName1
0x18000a931  call    cs:__imp_DnsNameCompare_W
0x18000a937  test    eax, eax
0x18000a939  jz      short loc_18000A93E
0x18000a93b  mov     [rbx], r12d
0x18000a93e  mov     rcx, [rbp+pName2]; hMem
0x18000a942  call    cs:__imp_LocalFree
0x18000a948  mov     [rbp+pName2], r12
0x18000a94c  cmp     [rbx], r12d
0x18000a94f  jz      short loc_18000A9C5
0x18000a951  xorps   xmm0, xmm0
0x18000a954  lea     rdx, [rbp+pName2]; unsigned __int16 **
0x18000a958  xor     ecx, ecx; NameType
0x18000a95a  movups  xmmword ptr [rbp+pName1], xmm0
0x18000a95e  call    ?SampGetLocalMachineName@@YAJW4_COMPUTER_NAME_FORMAT@@PEAPEAG@Z; SampGetLocalMachineName(_COMPUTER_NAME_FORMAT,ushort * *)
0x18000a963  mov     edi, eax
0x18000a965  test    eax, eax
0x18000a967  js      loc_18000AA37
0x18000a96d  mov     rdx, [rbp+pName2]; SourceString
0x18000a971  lea     rcx, [rbp+pName1]; DestinationString
0x18000a975  call    cs:__imp_RtlInitUnicodeString
0x18000a97b  lea     rdx, [rbp+pName1]; ComputerName2
0x18000a97f  lea     rcx, [rbp+ComputerName1]; ComputerName1
0x18000a983  call    cs:__imp_RtlEqualComputerName
0x18000a989  test    al, al
0x18000a98b  jz      short loc_18000A990
0x18000a98d  mov     [rbx], r12d
0x18000a990  cmp     [rbx], r12d
0x18000a993  jz      short loc_18000A9C5
0x18000a995  xorps   xmm0, xmm0
0x18000a998  lea     rdx, SourceString; "127.0.0.1"
0x18000a99f  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a9a3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000a9a7  call    cs:__imp_RtlInitUnicodeString
0x18000a9ad  mov     r8b, 1; CaseInsensitive
0x18000a9b0  lea     rdx, [rbp+ComputerName1]; String2
0x18000a9b4  lea     rcx, [rbp+DestinationString]; String1
0x18000a9b8  call    cs:__imp_RtlEqualUnicodeString
0x18000a9be  test    al, al
0x18000a9c0  jz      short loc_18000A9C5
0x18000a9c2  mov     [rbx], r12d
0x18000a9c5  test    r15, r15
0x18000a9c8  jz      short loc_18000AA37
0x18000a9ca  mov     rcx, [r15]; Binding
0x18000a9cd  lea     rdx, [rbp+StringBinding]; StringBinding
0x18000a9d1  mov     [rbp+pName1], r12
0x18000a9d5  mov     qword ptr [rbp+ComputerName1.Length], r12
0x18000a9d9  call    cs:__imp_RpcBindingToStringBindingW
0x18000a9df  test    eax, eax
0x18000a9e1  jnz     short loc_18000AA37
0x18000a9e3  mov     rcx, [rbp+StringBinding]; StringBinding
0x18000a9e7  lea     r9, [rbp+pName1]; NetworkAddr
0x18000a9eb  mov     [rsp+60h+NetworkOptions], r12; NetworkOptions
0x18000a9f0  lea     r8, [rbp+ComputerName1]; Protseq
0x18000a9f4  xor     edx, edx; ObjUuid
0x18000a9f6  mov     [rsp+60h+Endpoint], r12; Endpoint
0x18000a9fb  call    cs:__imp_RpcStringBindingParseW
0x18000aa01  test    eax, eax
0x18000aa03  jnz     short loc_18000AA37
0x18000aa05  cmp     [rbp+pName1], r12
0x18000aa09  jz      short loc_18000AA20
0x18000aa0b  mov     rcx, qword ptr [rbp+ComputerName1.Length]
0x18000aa0f  lea     rdx, aNcalrpc; "ncalrpc"
0x18000aa16  call    cs:__imp__o__wcsicmp
0x18000aa1c  test    eax, eax
0x18000aa1e  jnz     short loc_18000AA23
0x18000aa20  mov     [rbx], r12d
0x18000aa23  lea     rcx, [rbp+ComputerName1]; String
0x18000aa27  call    cs:__imp_RpcStringFreeW
0x18000aa2d  lea     rcx, [rbp+pName1]; String
0x18000aa31  call    cs:__imp_RpcStringFreeW
0x18000aa37  mov     rcx, [rbp+pName2]; hMem
0x18000aa3b  test    rcx, rcx
0x18000aa3e  jz      short loc_18000AA46
0x18000aa40  call    cs:__imp_LocalFree
0x18000aa46  cmp     [rbp+arg_0], r12b
0x18000aa4a  jz      short loc_18000AA55
0x18000aa4c  mov     rcx, r14; hMem
0x18000aa4f  call    cs:__imp_LocalFree
0x18000aa55  cmp     [rbp+StringBinding], r12
0x18000aa59  jz      loc_18000A88C
0x18000aa5f  lea     rcx, [rbp+StringBinding]; String
0x18000aa63  call    cs:__imp_RpcStringFreeW
0x18000aa69  jmp     loc_18000A88C
```
