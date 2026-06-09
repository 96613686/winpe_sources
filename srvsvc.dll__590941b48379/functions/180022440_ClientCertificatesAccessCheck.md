# ClientCertificatesAccessCheck

- ea: `0x180022440`
- end: `0x18002256b`
- name: `ClientCertificatesAccessCheck`
- size: `299`
- prototype: `RPC_STATUS __fastcall(struct _RPC_ASYNC_STATE *, __int64, int, int, int, void *Src, unsigned __int16, __int64, int, __int64, int, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180020dc0`
- `0x180022440`
- `0x180022dfc`
- `0x180035dec`
- `0x180038d98`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022462`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022462`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180022564`

## pseudocode

```c
RPC_STATUS __fastcall ClientCertificatesAccessCheck(
        struct _RPC_ASYNC_STATE *a1,
        __int64 a2,
        int a3,
        int a4,
        int a5,
        void *Src,
        unsigned __int16 a7,
        __int64 a8,
        int a9,
        __int64 a10,
        int a11,
        int *a12)
{
  HLOCAL v15; // rax
  __int64 v16; // rbx
  int v17; // edi
  int v18; // edx
  int v19; // r8d

  v15 = LocalAlloc(0, a7 + 2LL);
  v16 = (__int64)v15;
  if ( v15 )
  {
    memcpy_0(v15, Src, a7);
    *(_WORD *)(v16 + 2 * ((unsigned __int64)a7 >> 1)) = 0;
    v17 = ClCertAccessCheck(a3, a4, a5, v16, a8, a10, a11);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, v17, v16);
    }
    ClCertLocalFree(v16);
  }
  else
  {
    v17 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_ba4cc97350ca3b6f3c632e36d119eafc_Traceguids);
    }
  }
  *a12 = v17;
  return RpcAsyncCompleteCall(a1, a12);
}

```

## disassembly

```asm
0x180022440  push    rbx
0x180022442  push    rbp
0x180022443  push    rsi
0x180022444  push    rdi
0x180022445  push    r14
0x180022447  sub     rsp, 40h
0x18002244b  movzx   edi, [rsp+68h+arg_30]
0x180022453  mov     rsi, rcx
0x180022456  xor     ecx, ecx; uFlags
0x180022458  mov     rbp, r9
0x18002245b  mov     r14d, r8d
0x18002245e  lea     rdx, [rdi+2]; uBytes
0x180022462  call    cs:__imp_LocalAlloc
0x180022468  mov     rbx, rax
0x18002246b  test    rax, rax
0x18002246e  jnz     short loc_1800224B9
0x180022470  lea     edi, [rax+8]
0x180022473  mov     rcx, cs:WPP_GLOBAL_Control
0x18002247a  lea     rax, WPP_GLOBAL_Control
0x180022481  cmp     rcx, rax
0x180022484  jz      loc_18002254D
0x18002248a  test    dword ptr [rcx+1Ch], 800h
0x180022491  jz      loc_18002254D
0x180022497  cmp     byte ptr [rcx+19h], 1
0x18002249b  jb      loc_18002254D
0x1800224a1  mov     rcx, [rcx+10h]
0x1800224a5  lea     edx, [rbx+13h]
0x1800224a8  lea     r8, WPP_ba4cc97350ca3b6f3c632e36d119eafc_Traceguids
0x1800224af  call    WPP_SF_
0x1800224b4  jmp     loc_18002254D
0x1800224b9  mov     rdx, [rsp+68h+Src]; Src
0x1800224c1  mov     r8, rdi; Size
0x1800224c4  mov     rcx, rbx; void *
0x1800224c7  call    memcpy_0
0x1800224cc  mov     r8d, [rsp+68h+arg_20]
0x1800224d4  xor     eax, eax
0x1800224d6  shr     rdi, 1
0x1800224d9  mov     r9, rbx
0x1800224dc  mov     rdx, rbp
0x1800224df  mov     ecx, r14d
0x1800224e2  mov     [rbx+rdi*2], ax
0x1800224e6  mov     eax, [rsp+68h+arg_50]
0x1800224ed  mov     [rsp+68h+var_38], eax
0x1800224f1  mov     rax, [rsp+68h+arg_48]
0x1800224f9  mov     [rsp+68h+var_40], rax
0x1800224fe  mov     rax, [rsp+68h+arg_38]
0x180022506  mov     [rsp+68h+var_48], rax
0x18002250b  call    ClCertAccessCheck
0x180022510  mov     edi, eax
0x180022512  mov     rcx, cs:WPP_GLOBAL_Control
0x180022519  lea     rax, WPP_GLOBAL_Control
0x180022520  cmp     rcx, rax
0x180022523  jz      short loc_180022545
0x180022525  test    dword ptr [rcx+1Ch], 800h
0x18002252c  jz      short loc_180022545
0x18002252e  cmp     byte ptr [rcx+19h], 2
0x180022532  jb      short loc_180022545
0x180022534  mov     rcx, [rcx+10h]
0x180022538  mov     r9d, edi
0x18002253b  mov     [rsp+68h+var_48], rbx
0x180022540  call    WPP_SF_DS
0x180022545  mov     rcx, rbx
0x180022548  call    ClCertLocalFree
0x18002254d  mov     rdx, [rsp+68h+arg_58]
0x180022555  mov     rcx, rsi
0x180022558  mov     [rdx], edi
0x18002255a  add     rsp, 40h
0x18002255e  pop     r14
0x180022560  pop     rdi
0x180022561  pop     rsi
0x180022562  pop     rbp
0x180022563  pop     rbx
0x180022564  jmp     cs:__imp_RpcAsyncCompleteCall
```
