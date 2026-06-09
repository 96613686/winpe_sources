# WP_IPM::HandleCustomAction(IPM_MESSAGE const *)

- ea: `0x1800074dc`
- end: `0x180007609`
- name: `?HandleCustomAction@WP_IPM@@QEAAJPEBVIPM_MESSAGE@@@Z`
- size: `301`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this, const struct IPM_MESSAGE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001170`

## callees

- `0x180006830`
- `0x1800074dc`
- `0x18000d010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000755a`
- `iisutil!PuDbgPrint` at `0x18000755a`

## string_xrefs

- `0x180007553`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
__int64 __fastcall WP_IPM::HandleCustomAction(WP_IPM *this, const struct IPM_MESSAGE *a2)
{
  unsigned int *v5; // rdi
  unsigned int v6; // r14d
  const unsigned __int16 *v7; // rdi
  __int64 v8; // rax
  unsigned int v9; // ebp
  unsigned int v10; // eax
  W3WP_HOST *v11; // rcx

  if ( *(_DWORD *)(*((_QWORD *)g_pW3WPHost + 39) + 88LL) )
    return 0;
  v5 = (unsigned int *)(*(__int64 (__fastcall **)(const struct IPM_MESSAGE *))(*(_QWORD *)a2 + 16LL))(a2);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x80000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      928,
      "WP_IPM::HandleCustomAction",
      "Handle WP Data Request\n\n");
  if ( (*(unsigned int (__fastcall **)(const struct IPM_MESSAGE *))(*(_QWORD *)a2 + 8LL))(a2) >= 8
    && ((*(__int64 (__fastcall **)(const struct IPM_MESSAGE *))(*(_QWORD *)a2 + 8LL))(a2) & 1) == 0
    && !*((_WORD *)v5
        + ((unsigned __int64)(*(unsigned int (__fastcall **)(const struct IPM_MESSAGE *))(*(_QWORD *)a2 + 8LL))(a2) >> 1)
        - 1) )
  {
    v6 = *v5;
    v7 = (const unsigned __int16 *)(v5 + 1);
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    v9 = 2 * v8 + 2;
    v10 = (*(__int64 (__fastcall **)(const struct IPM_MESSAGE *))(*(_QWORD *)a2 + 8LL))(a2);
    v11 = (W3WP_HOST *)(v9 + 4 + 2LL);
    if ( (unsigned __int64)v11 <= v10 )
    {
      _InterlockedIncrement((volatile signed __int32 *)this + 16);
      W3WP_HOST::RequestCustomAction(v11, v6, v7, (const unsigned __int16 *)((char *)v7 + v9));
      return 0;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800074dc  push    rbx
0x1800074de  push    rbp
0x1800074df  push    rsi
0x1800074e0  push    rdi
0x1800074e1  push    r14
0x1800074e3  sub     rsp, 30h
0x1800074e7  mov     rax, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x1800074ee  xor     ebp, ebp
0x1800074f0  mov     rbx, rdx
0x1800074f3  mov     rsi, rcx
0x1800074f6  mov     r8, [rax+138h]
0x1800074fd  cmp     [r8+58h], ebp
0x180007501  jz      short loc_18000750A
0x180007503  xor     eax, eax
0x180007505  jmp     loc_1800075FE
0x18000750a  mov     rax, [rdx]
0x18000750d  mov     rcx, rbx
0x180007510  mov     rax, [rax+10h]
0x180007514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007519  mov     ecx, cs:g_dwDebugFlags
0x18000751f  mov     rdi, rax
0x180007522  test    cl, 3
0x180007525  setnz   dl
0x180007528  bt      ecx, 13h
0x18000752c  setb    cl
0x18000752f  test    cl, dl
0x180007531  jz      short loc_180007560
0x180007533  mov     rcx, cs:g_pDebug
0x18000753a  lea     rax, aHandleWpDataRe; "Handle WP Data Request\n\n"
0x180007541  lea     r9, aWpIpmHandlecus; "WP_IPM::HandleCustomAction"
0x180007548  mov     [rsp+58h+var_38], rax
0x18000754d  mov     r8d, 3A0h
0x180007553  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000755a  call    cs:__imp_PuDbgPrint
0x180007560  mov     rax, [rbx]
0x180007563  mov     rcx, rbx
0x180007566  mov     rax, [rax+8]
0x18000756a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000756f  cmp     eax, 8
0x180007572  jb      loc_1800075F9
0x180007578  mov     rax, [rbx]
0x18000757b  mov     rcx, rbx
0x18000757e  mov     rax, [rax+8]
0x180007582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007587  test    al, 1
0x180007589  jnz     short loc_1800075F9
0x18000758b  mov     rax, [rbx]
0x18000758e  mov     rcx, rbx
0x180007591  mov     rax, [rax+8]
0x180007595  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000759a  mov     eax, eax
0x18000759c  shr     rax, 1
0x18000759f  cmp     [rdi+rax*2-2], bp
0x1800075a4  jnz     short loc_1800075F9
0x1800075a6  mov     r14d, [rdi]
0x1800075a9  add     rdi, 4
0x1800075ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800075b1  inc     rax
0x1800075b4  cmp     [rdi+rax*2], bp
0x1800075b8  jnz     short loc_1800075B1
0x1800075ba  lea     ebp, ds:2[rax*2]
0x1800075c1  mov     rcx, rbx
0x1800075c4  mov     rax, [rbx]
0x1800075c7  mov     rax, [rax+8]
0x1800075cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075d0  lea     ecx, [rbp+4]
0x1800075d3  mov     r9d, eax
0x1800075d6  add     rcx, 2; this
0x1800075da  cmp     rcx, r9
0x1800075dd  ja      short loc_1800075F9
0x1800075df  lock inc dword ptr [rsi+40h]
0x1800075e3  mov     r9d, ebp
0x1800075e6  mov     r8, rdi; unsigned __int16 *
0x1800075e9  add     r9, rdi; unsigned __int16 *
0x1800075ec  mov     edx, r14d; unsigned int
0x1800075ef  call    ?RequestCustomAction@W3WP_HOST@@QEAAXKPEBG0@Z; W3WP_HOST::RequestCustomAction(ulong,ushort const *,ushort const *)
0x1800075f4  jmp     loc_180007503
0x1800075f9  mov     eax, 80070057h
0x1800075fe  add     rsp, 30h
0x180007602  pop     r14
0x180007604  pop     rdi
0x180007605  pop     rsi
0x180007606  pop     rbp
0x180007607  pop     rbx
0x180007608  retn
```
