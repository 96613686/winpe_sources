# HTTP2ProcessComplexTReceive(void * *,long,ulong,uchar * *,uint *)

- ea: `0x18000b4c0`
- end: `0x18000b6ce`
- name: `?HTTP2ProcessComplexTReceive@@YAJPEAPEAXJKPEAPEAEPEAI@Z`
- size: `526`
- prototype: `__int64 __fastcall(struct BASE_CONNECTION **, unsigned int, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000ab40`
- `0x18000b4c0`
- `0x18000dfe8`
- `0x18000eebc`
- `0x180025010`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x18000b51b`
- `RPCRT4!I_RpcLogEvent` at `0x18000b6b2`
- `RPCRT4!I_RpcLogEvent` at `0x18000b51b`
- `RPCRT4!I_RpcLogEvent` at `0x18000b6b2`

## pseudocode

```c
__int64 __fastcall HTTP2ProcessComplexTReceive(
        struct BASE_CONNECTION **a1,
        unsigned int a2,
        unsigned int a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  struct BASE_CONNECTION *v5; // rdi
  struct BASE_HTTP2_CONNECTION *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  struct BASE_HTTP2_CONNECTION *v13; // r14
  unsigned int *v14; // rbx
  unsigned __int8 *v15; // rbp
  unsigned int v16; // r14d
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  struct HTTP2ServerVirtualConnection *v21; // [rsp+70h] [rbp+8h] BYREF
  int v22; // [rsp+78h] [rbp+10h] BYREF

  v5 = *a1;
  v10 = BASE_HTTP2_CONNECTION::From_BASE_CONNECTION(*a1);
  LOBYTE(v11) = 111;
  LOBYTE(v12) = 50;
  v21 = 0;
  v13 = v10;
  v22 = 0;
  I_RpcLogEvent(v12, v11, 0, 17629202, a2, 0, 0);
  if ( a2 == -1073606610 )
  {
    v14 = a5;
    v15 = *a4;
    v16 = *a5;
    if ( (unsigned int)(*((_DWORD *)v5 + 3) - 13) > 1 )
      (*((void (__fastcall **)(struct BASE_CONNECTION *))pRuntimeImportTable + 38))(v5);
    if ( !(unsigned int)HTTP2ServerVirtualConnection::InitializeServerConnection(v15, v16, v5, &v21, &v22) )
    {
      *a4 = 0;
      *v14 = 0;
      (*((void (__fastcall **)(unsigned __int8 *))pRuntimeImportTable + 1))(v15);
      a2 = -1073606615;
      goto LABEL_25;
    }
    if ( !v22 )
    {
      if ( (unsigned int)(*((_DWORD *)v5 + 3) - 13) > 1 )
        (*((void (__fastcall **)(struct BASE_CONNECTION *))pRuntimeImportTable + 39))(v5);
      a2 = -1073606647;
      goto LABEL_25;
    }
    a2 = -1073606647;
LABEL_11:
    *a1 = v5;
    goto LABEL_25;
  }
  *a1 = (struct BASE_CONNECTION *)*((_QWORD *)v13 + 4);
  if ( !a3 || a2 )
  {
    if ( (unsigned int)IsHTTPv2Protocol(*((_DWORD *)v5 + 3))
      && *((_DWORD *)v5 + 2) == 20
      && (unsigned int)(v18 - 13) > 1 )
    {
      goto LABEL_11;
    }
    v19 = a2;
    if ( !a2 )
      v19 = 3221360649LL;
    a2 = (**(__int64 (__fastcall ***)(struct BASE_HTTP2_CONNECTION *, __int64))v13)(v13, v19);
    if ( a2 == -1073606638 )
      a2 = -1073606647;
  }
  else
  {
    a2 = (*(__int64 (__fastcall **)(struct BASE_HTTP2_CONNECTION *, _QWORD, unsigned __int8 **, unsigned int *))(*(_QWORD *)v13 + 16LL))(
           v13,
           a3,
           a4,
           a5);
    if ( a2 == -1073606622 )
    {
      if ( (*((unsigned int (__fastcall **)(struct BASE_CONNECTION *))pRuntimeImportTable + 50))(v5) )
        a2 = (**(__int64 (__fastcall ***)(struct BASE_HTTP2_CONNECTION *, __int64))v13)(v13, 3221360658LL);
      else
        a2 = -1073606622;
    }
  }
LABEL_25:
  LOBYTE(v17) = 111;
  LOBYTE(v18) = 50;
  I_RpcLogEvent(v18, v17, 0, 851986, a2, 0, 0);
  return a2;
}

```

## disassembly

```asm
0x18000b4c0  mov     [rsp+arg_10], rbx
0x18000b4c5  push    rbp
0x18000b4c6  push    rsi
0x18000b4c7  push    rdi
0x18000b4c8  push    r14
0x18000b4ca  push    r15
0x18000b4cc  sub     rsp, 40h
0x18000b4d0  mov     rdi, [rcx]
0x18000b4d3  mov     r15, rcx
0x18000b4d6  mov     rcx, rdi; struct BASE_CONNECTION *
0x18000b4d9  mov     rsi, r9
0x18000b4dc  mov     ebp, r8d
0x18000b4df  mov     ebx, edx
0x18000b4e1  call    ?From_BASE_CONNECTION@BASE_HTTP2_CONNECTION@@SAPEAV1@PEAVBASE_CONNECTION@@@Z; BASE_HTTP2_CONNECTION::From_BASE_CONNECTION(BASE_CONNECTION *)
0x18000b4e6  mov     [rsp+68h+var_38], 0
0x18000b4ee  mov     r9d, 10D0012h
0x18000b4f4  mov     [rsp+68h+var_40], 0
0x18000b4fc  xor     r8d, r8d
0x18000b4ff  mov     dl, 6Fh ; 'o'
0x18000b501  mov     dword ptr [rsp+68h+var_48], ebx
0x18000b505  mov     cl, 32h ; '2'
0x18000b507  mov     [rsp+68h+arg_0], 0
0x18000b510  mov     r14, rax
0x18000b513  mov     [rsp+68h+arg_8], 0
0x18000b51b  call    cs:__imp_I_RpcLogEvent
0x18000b521  cmp     ebx, 0C002102Eh
0x18000b527  jnz     loc_18000B5E2
0x18000b52d  mov     rbx, [rsp+68h+arg_20]
0x18000b535  mov     eax, [rdi+0Ch]
0x18000b538  mov     rbp, [rsi]
0x18000b53b  sub     eax, 0Dh
0x18000b53e  mov     r14d, [rbx]
0x18000b541  cmp     eax, 1
0x18000b544  jbe     short loc_18000B55C
0x18000b546  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000b54d  mov     rcx, rdi
0x18000b550  mov     rax, [rax+130h]
0x18000b557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b55c  lea     rax, [rsp+68h+arg_8]
0x18000b561  mov     r8, rdi; struct BASE_CONNECTION *
0x18000b564  lea     r9, [rsp+68h+arg_0]; struct HTTP2ServerVirtualConnection **
0x18000b569  mov     [rsp+68h+var_48], rax; int *
0x18000b56e  mov     edx, r14d; unsigned int
0x18000b571  mov     rcx, rbp; unsigned __int8 *
0x18000b574  call    ?InitializeServerConnection@HTTP2ServerVirtualConnection@@SAJPEAEKPEAVBASE_CONNECTION@@PEAPEAV1@PEAH@Z; HTTP2ServerVirtualConnection::InitializeServerConnection(uchar *,ulong,BASE_CONNECTION *,HTTP2ServerVirtualConnection * *,int *)
0x18000b579  test    eax, eax
0x18000b57b  jnz     short loc_18000B5A3
0x18000b57d  mov     qword ptr [rsi], 0
0x18000b584  mov     rcx, rbp
0x18000b587  mov     [rbx], eax
0x18000b589  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000b590  mov     rax, [rax+8]
0x18000b594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b599  mov     ebx, 0C0021029h
0x18000b59e  jmp     loc_18000B691
0x18000b5a3  cmp     [rsp+68h+arg_8], 0
0x18000b5a8  jnz     short loc_18000B5D5
0x18000b5aa  mov     eax, [rdi+0Ch]
0x18000b5ad  sub     eax, 0Dh
0x18000b5b0  cmp     eax, 1
0x18000b5b3  jbe     short loc_18000B5CB
0x18000b5b5  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000b5bc  mov     rcx, rdi
0x18000b5bf  mov     rax, [rax+138h]
0x18000b5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5cb  mov     ebx, 0C0021009h
0x18000b5d0  jmp     loc_18000B691
0x18000b5d5  mov     ebx, 0C0021009h
0x18000b5da  mov     [r15], rdi
0x18000b5dd  jmp     loc_18000B691
0x18000b5e2  mov     rax, [r14+20h]
0x18000b5e6  mov     [r15], rax
0x18000b5e9  test    ebp, ebp
0x18000b5eb  jz      short loc_18000B64E
0x18000b5ed  test    ebx, ebx
0x18000b5ef  jnz     short loc_18000B64E
0x18000b5f1  mov     rax, [r14]
0x18000b5f4  mov     r8, rsi
0x18000b5f7  mov     r9, [rsp+68h+arg_20]
0x18000b5ff  mov     edx, ebp
0x18000b601  mov     rcx, r14
0x18000b604  mov     rax, [rax+10h]
0x18000b608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b60d  mov     ebx, eax
0x18000b60f  cmp     eax, 0C0021022h
0x18000b614  jnz     short loc_18000B691
0x18000b616  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000b61d  mov     rcx, rdi
0x18000b620  mov     rax, [rax+190h]
0x18000b627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b62c  test    eax, eax
0x18000b62e  jz      short loc_18000B647
0x18000b630  mov     rax, [r14]
0x18000b633  mov     edx, 0C0021012h
0x18000b638  mov     rcx, r14
0x18000b63b  mov     rax, [rax]
0x18000b63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b643  mov     ebx, eax
0x18000b645  jmp     short loc_18000B691
0x18000b647  mov     ebx, 0C0021022h
0x18000b64c  jmp     short loc_18000B691
0x18000b64e  mov     ecx, [rdi+0Ch]; int
0x18000b651  call    ?IsHTTPv2Protocol@@YAHH@Z; IsHTTPv2Protocol(int)
0x18000b656  test    eax, eax
0x18000b658  jz      short loc_18000B66C
0x18000b65a  cmp     dword ptr [rdi+8], 14h
0x18000b65e  jnz     short loc_18000B66C
0x18000b660  lea     eax, [rcx-0Dh]
0x18000b663  cmp     eax, 1
0x18000b666  ja      loc_18000B5DA
0x18000b66c  mov     rax, [r14]
0x18000b66f  mov     esi, 0C0021009h
0x18000b674  mov     rcx, r14
0x18000b677  mov     edx, ebx
0x18000b679  mov     rax, [rax]
0x18000b67c  test    ebx, ebx
0x18000b67e  jnz     short loc_18000B682
0x18000b680  mov     edx, esi
0x18000b682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b687  cmp     eax, 0C0021012h
0x18000b68c  mov     ebx, eax
0x18000b68e  cmovz   ebx, esi
0x18000b691  mov     [rsp+68h+var_38], 0
0x18000b699  mov     r9d, 0D0012h
0x18000b69f  mov     [rsp+68h+var_40], 0
0x18000b6a7  xor     r8d, r8d
0x18000b6aa  mov     dl, 6Fh ; 'o'
0x18000b6ac  mov     dword ptr [rsp+68h+var_48], ebx
0x18000b6b0  mov     cl, 32h ; '2'
0x18000b6b2  call    cs:__imp_I_RpcLogEvent
0x18000b6b8  mov     eax, ebx
0x18000b6ba  mov     rbx, [rsp+68h+arg_10]
0x18000b6c2  add     rsp, 40h
0x18000b6c6  pop     r15
0x18000b6c8  pop     r14
0x18000b6ca  pop     rdi
0x18000b6cb  pop     rsi
0x18000b6cc  pop     rbp
0x18000b6cd  retn
```
