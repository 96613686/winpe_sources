# WP_IPM::HandleCustomAction(IPM_MESSAGE const *)

- ea: `0x180007c80`
- end: `0x180007db4`
- name: `?HandleCustomAction@WP_IPM@@QEAAJPEBVIPM_MESSAGE@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this, const struct IPM_MESSAGE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001180`

## callees

- `0x180006ea4`
- `0x180007c80`
- `0x18000e010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007cfe`
- `iisutil!PuDbgPrint` at `0x180007cfe`

## string_xrefs

- `0x180007cf7`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
__int64 __fastcall WP_IPM::HandleCustomAction(WP_IPM *this, const struct IPM_MESSAGE *a2)
{
  int *v5; // rdi
  int v6; // r14d
  const unsigned __int16 *v7; // rdi
  __int64 v8; // rax
  unsigned int v9; // ebp
  unsigned int v10; // eax
  W3WP_HOST *v11; // rcx

  if ( *(_DWORD *)(*((_QWORD *)g_pW3WPHost + 39) + 88LL) )
    return 0;
  v5 = (int *)(*(__int64 (__fastcall **)(const struct IPM_MESSAGE *))(*(_QWORD *)a2 + 16LL))(a2);
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
0x180007c80  push    rbx
0x180007c82  push    rbp
0x180007c83  push    rsi
0x180007c84  push    rdi
0x180007c85  push    r14
0x180007c87  sub     rsp, 30h
0x180007c8b  mov     rax, cs:?g_pW3WPHost@@3PEAVW3WP_HOST@@EA; W3WP_HOST * g_pW3WPHost
0x180007c92  xor     ebp, ebp
0x180007c94  mov     rbx, rdx
0x180007c97  mov     rsi, rcx
0x180007c9a  mov     r8, [rax+138h]
0x180007ca1  cmp     [r8+58h], ebp
0x180007ca5  jz      short loc_180007CAE
0x180007ca7  xor     eax, eax
0x180007ca9  jmp     loc_180007DA8
0x180007cae  mov     rax, [rdx]
0x180007cb1  mov     rcx, rbx
0x180007cb4  mov     rax, [rax+10h]
0x180007cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cbd  mov     ecx, cs:g_dwDebugFlags
0x180007cc3  mov     rdi, rax
0x180007cc6  test    cl, 3
0x180007cc9  setnz   dl
0x180007ccc  bt      ecx, 13h
0x180007cd0  setb    cl
0x180007cd3  test    cl, dl
0x180007cd5  jz      short loc_180007D0A
0x180007cd7  mov     rcx, cs:g_pDebug
0x180007cde  lea     rax, aHandleWpDataRe; "Handle WP Data Request\n\n"
0x180007ce5  lea     r9, aWpIpmHandlecus; "WP_IPM::HandleCustomAction"
0x180007cec  mov     [rsp+58h+var_38], rax
0x180007cf1  mov     r8d, 3A0h
0x180007cf7  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007cfe  call    cs:__imp_PuDbgPrint
0x180007d05  nop     dword ptr [rax+rax+00h]
0x180007d0a  mov     rax, [rbx]
0x180007d0d  mov     rcx, rbx
0x180007d10  mov     rax, [rax+8]
0x180007d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d19  cmp     eax, 8
0x180007d1c  jb      loc_180007DA3
0x180007d22  mov     rax, [rbx]
0x180007d25  mov     rcx, rbx
0x180007d28  mov     rax, [rax+8]
0x180007d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d31  test    al, 1
0x180007d33  jnz     short loc_180007DA3
0x180007d35  mov     rax, [rbx]
0x180007d38  mov     rcx, rbx
0x180007d3b  mov     rax, [rax+8]
0x180007d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d44  mov     eax, eax
0x180007d46  shr     rax, 1
0x180007d49  cmp     [rdi+rax*2-2], bp
0x180007d4e  jnz     short loc_180007DA3
0x180007d50  mov     r14d, [rdi]
0x180007d53  add     rdi, 4
0x180007d57  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007d5b  inc     rax
0x180007d5e  cmp     [rdi+rax*2], bp
0x180007d62  jnz     short loc_180007D5B
0x180007d64  lea     ebp, ds:2[rax*2]
0x180007d6b  mov     rcx, rbx
0x180007d6e  mov     rax, [rbx]
0x180007d71  mov     rax, [rax+8]
0x180007d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d7a  lea     ecx, [rbp+4]
0x180007d7d  mov     r9d, eax
0x180007d80  add     rcx, 2; this
0x180007d84  cmp     rcx, r9
0x180007d87  ja      short loc_180007DA3
0x180007d89  lock inc dword ptr [rsi+40h]
0x180007d8d  mov     r9d, ebp
0x180007d90  mov     r8, rdi; unsigned __int16 *
0x180007d93  add     r9, rdi; unsigned __int16 *
0x180007d96  mov     edx, r14d; unsigned int
0x180007d99  call    ?RequestCustomAction@W3WP_HOST@@QEAAXKPEBG0@Z; W3WP_HOST::RequestCustomAction(ulong,ushort const *,ushort const *)
0x180007d9e  jmp     loc_180007CA7
0x180007da3  mov     eax, 80070057h
0x180007da8  add     rsp, 30h
0x180007dac  pop     r14
0x180007dae  pop     rdi
0x180007daf  pop     rsi
0x180007db0  pop     rbp
0x180007db1  pop     rbx
0x180007db2  retn
```
