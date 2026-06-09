# std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::_Eqrange<_GUID>(_GUID const &)

- ea: `0x1402a2158`
- end: `0x1402a225e`
- name: `??$_Eqrange@U_GUID@@@?$_Tree@V?$_Tset_traits@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA?AU?$pair@PEAU?$_Tree_node@U_GUID@@PEAX@std@@PEAU12@@1@AEBU_GUID@@@Z`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1402a23b8`

## callees

- `0x14011ea40`
- `0x1402a2158`

## import_xrefs

- `RPCRT4!UuidCompare` at `0x1402a219f`
- `RPCRT4!UuidCompare` at `0x1402a21cf`
- `RPCRT4!UuidCompare` at `0x1402a2218`
- `RPCRT4!UuidCompare` at `0x1402a219f`
- `RPCRT4!UuidCompare` at `0x1402a21cf`
- `RPCRT4!UuidCompare` at `0x1402a2218`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::_Eqrange<_GUID>(
        __int64 *a1,
        __int64 *a2,
        UUID *a3)
{
  __int64 v3; // rbp
  __int64 v7; // rdi
  __int64 i; // rbx
  __int64 j; // rbx
  __int64 *result; // rax
  RPC_STATUS Status; // [rsp+20h] [rbp-48h] BYREF

  v3 = *a1;
  v7 = *a1;
  for ( i = *(_QWORD *)(*a1 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)i )
  {
    Status = 0;
    if ( UuidCompare((UUID *)(i + 28), a3, &Status) >= 0 )
    {
      if ( *(_BYTE *)(v7 + 25) )
      {
        Status = 0;
        if ( UuidCompare(a3, (UUID *)(i + 28), &Status) < 0 )
          v7 = i;
      }
      v3 = i;
    }
    else
    {
      i += 16;
    }
  }
  if ( *(_BYTE *)(v7 + 25) )
    j = *a1 + 8;
  else
    j = v7;
LABEL_13:
  for ( j = *(_QWORD *)j; !*(_BYTE *)(j + 25); j = *(_QWORD *)(j + 16) )
  {
    Status = 0;
    if ( UuidCompare(a3, (UUID *)(j + 28), &Status) < 0 )
    {
      v7 = j;
      goto LABEL_13;
    }
  }
  *a2 = v3;
  result = a2;
  a2[1] = v7;
  return result;
}

```

## disassembly

```asm
0x1402a2158  push    rbx
0x1402a215a  push    rbp
0x1402a215b  push    rsi
0x1402a215c  push    rdi
0x1402a215d  push    r12
0x1402a215f  push    r14
0x1402a2161  push    r15
0x1402a2163  sub     rsp, 30h
0x1402a2167  mov     rax, cs:__security_cookie
0x1402a216e  xor     rax, rsp
0x1402a2171  mov     [rsp+68h+var_40], rax
0x1402a2176  mov     rbp, [rcx]
0x1402a2179  mov     r12, r8
0x1402a217c  mov     rsi, rdx
0x1402a217f  mov     r15, rcx
0x1402a2182  mov     rdi, rbp
0x1402a2185  mov     rbx, [rbp+8]
0x1402a2189  jmp     short loc_1402A21E7
0x1402a218b  lea     r8, [rsp+68h+Status]; Status
0x1402a2190  mov     [rsp+68h+Status], 0
0x1402a2198  mov     rdx, r12; Uuid2
0x1402a219b  lea     rcx, [rbx+1Ch]; Uuid1
0x1402a219f  call    cs:__imp_UuidCompare
0x1402a21a6  nop     dword ptr [rax+rax+00h]
0x1402a21ab  test    eax, eax
0x1402a21ad  jns     short loc_1402A21B5
0x1402a21af  add     rbx, 10h
0x1402a21b3  jmp     short loc_1402A21E4
0x1402a21b5  cmp     byte ptr [rdi+19h], 0
0x1402a21b9  jz      short loc_1402A21E1
0x1402a21bb  lea     r8, [rsp+68h+Status]; Status
0x1402a21c0  mov     [rsp+68h+Status], 0
0x1402a21c8  lea     rdx, [rbx+1Ch]; Uuid2
0x1402a21cc  mov     rcx, r12; Uuid1
0x1402a21cf  call    cs:__imp_UuidCompare
0x1402a21d6  nop     dword ptr [rax+rax+00h]
0x1402a21db  test    eax, eax
0x1402a21dd  cmovs   rdi, rbx
0x1402a21e1  mov     rbp, rbx
0x1402a21e4  mov     rbx, [rbx]
0x1402a21e7  cmp     byte ptr [rbx+19h], 0
0x1402a21eb  jz      short loc_1402A218B
0x1402a21ed  cmp     byte ptr [rdi+19h], 0
0x1402a21f1  jz      short loc_1402A21FC
0x1402a21f3  mov     rbx, [r15]
0x1402a21f6  add     rbx, 8
0x1402a21fa  jmp     short loc_1402A21FF
0x1402a21fc  mov     rbx, rdi
0x1402a21ff  mov     rbx, [rbx]
0x1402a2202  jmp     short loc_1402A2231
0x1402a2204  lea     rdx, [rbx+1Ch]; Uuid2
0x1402a2208  mov     [rsp+68h+Status], 0
0x1402a2210  lea     r8, [rsp+68h+Status]; Status
0x1402a2215  mov     rcx, r12; Uuid1
0x1402a2218  call    cs:__imp_UuidCompare
0x1402a221f  nop     dword ptr [rax+rax+00h]
0x1402a2224  test    eax, eax
0x1402a2226  jns     short loc_1402A222D
0x1402a2228  mov     rdi, rbx
0x1402a222b  jmp     short loc_1402A21FF
0x1402a222d  mov     rbx, [rbx+10h]
0x1402a2231  cmp     byte ptr [rbx+19h], 0
0x1402a2235  jz      short loc_1402A2204
0x1402a2237  mov     [rsi], rbp
0x1402a223a  mov     rax, rsi
0x1402a223d  mov     [rsi+8], rdi
0x1402a2241  mov     rcx, [rsp+68h+var_40]
0x1402a2246  xor     rcx, rsp; StackCookie
0x1402a2249  call    __security_check_cookie
0x1402a224e  add     rsp, 30h
0x1402a2252  pop     r15
0x1402a2254  pop     r14
0x1402a2256  pop     r12
0x1402a2258  pop     rdi
0x1402a2259  pop     rsi
0x1402a225a  pop     rbp
0x1402a225b  pop     rbx
0x1402a225c  retn
```
