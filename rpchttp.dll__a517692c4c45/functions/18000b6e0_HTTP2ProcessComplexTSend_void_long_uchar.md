# HTTP2ProcessComplexTSend(void *,long,uchar * *)

- ea: `0x18000b6e0`
- end: `0x18000b77a`
- name: `?HTTP2ProcessComplexTSend@@YAJPEAXJPEAPEAE@Z`
- size: `154`
- prototype: `__int64 __fastcall(struct BASE_CONNECTION **, __int64, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ab40`
- `0x180025010`

## import_xrefs

- `RPCRT4!I_RpcLogEvent` at `0x18000b716`
- `RPCRT4!I_RpcLogEvent` at `0x18000b762`
- `RPCRT4!I_RpcLogEvent` at `0x18000b716`
- `RPCRT4!I_RpcLogEvent` at `0x18000b762`

## pseudocode

```c
__int64 __fastcall HTTP2ProcessComplexTSend(struct BASE_CONNECTION **a1, __int64 a2, unsigned __int8 **a3)
{
  struct BASE_CONNECTION **v3; // rdi
  unsigned int v5; // esi
  struct BASE_HTTP2_CONNECTION *v6; // rax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v11; // [rsp+20h] [rbp-28h]

  v3 = a1;
  v5 = a2;
  v11 = (int)a1;
  LOBYTE(a2) = 111;
  LOBYTE(a1) = 50;
  I_RpcLogEvent(a1, a2, 0, 17563666, v11, 0, 0);
  *a3 = (unsigned __int8 *)v3[6];
  v6 = BASE_HTTP2_CONNECTION::From_BASE_CONNECTION(*v3);
  v7 = (*(__int64 (__fastcall **)(struct BASE_HTTP2_CONNECTION *, _QWORD, struct BASE_CONNECTION **))(*(_QWORD *)v6 + 8LL))(
         v6,
         v5,
         v3);
  LOBYTE(v8) = 111;
  LOBYTE(v9) = 50;
  LODWORD(a3) = v7;
  I_RpcLogEvent(v9, v8, 0, 786450, v7, 0, 0);
  return (unsigned int)a3;
}

```

## disassembly

```asm
0x18000b6e0  mov     rax, rsp
0x18000b6e3  mov     [rax+8], rbx
0x18000b6e7  mov     [rax+10h], rsi
0x18000b6eb  push    rdi
0x18000b6ec  sub     rsp, 40h
0x18000b6f0  mov     rdi, rcx
0x18000b6f3  mov     dword ptr [rax-18h], 0
0x18000b6fa  mov     rbx, r8
0x18000b6fd  mov     dword ptr [rax-20h], 0
0x18000b704  mov     esi, edx
0x18000b706  mov     [rax-28h], edi
0x18000b709  xor     r8d, r8d
0x18000b70c  mov     dl, 6Fh ; 'o'
0x18000b70e  mov     cl, 32h ; '2'
0x18000b710  mov     r9d, 10C0012h
0x18000b716  call    cs:__imp_I_RpcLogEvent
0x18000b71c  mov     rax, [rdi+30h]
0x18000b720  mov     [rbx], rax
0x18000b723  mov     rcx, [rdi]; struct BASE_CONNECTION *
0x18000b726  call    ?From_BASE_CONNECTION@BASE_HTTP2_CONNECTION@@SAPEAV1@PEAVBASE_CONNECTION@@@Z; BASE_HTTP2_CONNECTION::From_BASE_CONNECTION(BASE_CONNECTION *)
0x18000b72b  mov     rcx, rax
0x18000b72e  mov     edx, esi
0x18000b730  mov     r8, [rax]
0x18000b733  mov     rax, [r8+8]
0x18000b737  mov     r8, rdi
0x18000b73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b73f  mov     [rsp+48h+var_18], 0
0x18000b747  mov     r9d, 0C0012h
0x18000b74d  mov     [rsp+48h+var_20], 0
0x18000b755  xor     r8d, r8d
0x18000b758  mov     dl, 6Fh ; 'o'
0x18000b75a  mov     [rsp+48h+var_28], eax
0x18000b75e  mov     cl, 32h ; '2'
0x18000b760  mov     ebx, eax
0x18000b762  call    cs:__imp_I_RpcLogEvent
0x18000b768  mov     rsi, [rsp+48h+arg_8]
0x18000b76d  mov     eax, ebx
0x18000b76f  mov     rbx, [rsp+48h+arg_0]
0x18000b774  add     rsp, 40h
0x18000b778  pop     rdi
0x18000b779  retn
```
