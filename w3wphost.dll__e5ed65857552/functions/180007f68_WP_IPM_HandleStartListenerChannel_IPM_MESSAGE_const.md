# WP_IPM::HandleStartListenerChannel(IPM_MESSAGE const *)

- ea: `0x180007f68`
- end: `0x180008082`
- name: `?HandleStartListenerChannel@WP_IPM@@QEAAJPEBVIPM_MESSAGE@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this, const struct IPM_MESSAGE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001180`

## callees

- `0x18000750c`
- `0x180007f68`
- `0x18000e010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180008041`
- `iisutil!PuDbgPrint` at `0x180008041`

## string_xrefs

- `0x18000802f`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
__int64 __fastcall WP_IPM::HandleStartListenerChannel(WP_IPM *this, const struct IPM_MESSAGE *a2)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  const wchar_t *v4; // rbx
  __int64 v5; // rax
  unsigned int v6; // r8d
  __int64 v7; // rax
  const unsigned __int16 *v8; // rdi
  const unsigned __int16 *v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // r14
  W3WP_HOST *v12; // rcx
  __int64 v13; // r15
  char *v14; // r15
  unsigned int v15; // ebp
  unsigned int v16; // r12d

  v2 = (*(__int64 (__fastcall **)(const struct IPM_MESSAGE *))(*(_QWORD *)a2 + 16LL))(a2);
  v3 = -1;
  v4 = (const wchar_t *)v2;
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  v6 = 2 * v5 + 2;
  v7 = -1;
  v8 = (const wchar_t *)((char *)v4 + v6);
  do
    ++v7;
  while ( v8[v7] );
  v9 = (const unsigned __int16 *)((char *)v8 + (unsigned int)(2 * v7 + 2));
  do
    ++v3;
  while ( v9[v3] );
  v10 = (unsigned int)(2 * v3 + 2);
  v11 = (unsigned int)v10;
  v12 = (W3WP_HOST *)(((_BYTE)v6 + (_BYTE)v10 + 2 * (_BYTE)v7 + 2) & 3);
  v13 = (unsigned int)(4 - (_DWORD)v12);
  if ( (((_BYTE)v6 + (_BYTE)v10 + 2 * (_BYTE)v7 + 2) & 3) == 0 )
    v13 = 0;
  v14 = (char *)v9 + v13;
  LOBYTE(v12) = (g_dwDebugFlags & 3) != 0;
  v15 = *(_DWORD *)&v14[v10];
  v16 = *(_DWORD *)&v14[v10 + 4];
  if ( ((unsigned __int8)v12 & ((g_dwDebugFlags & 0x80000) != 0)) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\wpipm.cxx",
      776,
      "WP_IPM::HandleStartListenerChannel",
      "Start ListenerChannel Requested for: %S, ListenerChannelId:%d\n",
      v4,
      *(_DWORD *)&v14[v10]);
  W3WP_HOST::StartListenerChannel(v12, v8, v9, v4, v15, v16, (unsigned __int8 *)&v14[v11 + 8]);
  return 0;
}

```

## disassembly

```asm
0x180007f68  push    rbx
0x180007f6a  push    rbp
0x180007f6b  push    rsi
0x180007f6c  push    rdi
0x180007f6d  push    r12
0x180007f6f  push    r14
0x180007f71  push    r15
0x180007f73  sub     rsp, 40h
0x180007f77  mov     rax, [rdx]
0x180007f7a  mov     rcx, rdx
0x180007f7d  mov     rax, [rax+10h]
0x180007f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f86  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180007f8a  mov     rbx, rax
0x180007f8d  mov     rax, rdx
0x180007f90  xor     r9d, r9d
0x180007f93  inc     rax
0x180007f96  cmp     [rbx+rax*2], r9w
0x180007f9b  jnz     short loc_180007F93
0x180007f9d  lea     r8d, ds:2[rax*2]
0x180007fa5  mov     rax, rdx
0x180007fa8  mov     edi, r8d
0x180007fab  add     rdi, rbx
0x180007fae  inc     rax
0x180007fb1  cmp     [rdi+rax*2], r9w
0x180007fb6  jnz     short loc_180007FAE
0x180007fb8  lea     ecx, ds:2[rax*2]
0x180007fbf  mov     esi, ecx
0x180007fc1  add     rsi, rdi
0x180007fc4  inc     rdx
0x180007fc7  cmp     [rsi+rdx*2], r9w
0x180007fcc  jnz     short loc_180007FC4
0x180007fce  mov     eax, cs:g_dwDebugFlags
0x180007fd4  lea     edx, ds:2[rdx*2]
0x180007fdb  add     ecx, edx
0x180007fdd  mov     r14d, edx
0x180007fe0  add     ecx, r8d
0x180007fe3  mov     r15d, 4
0x180007fe9  and     ecx, 3
0x180007fec  sub     r15d, ecx
0x180007fef  test    ecx, ecx
0x180007ff1  cmovz   r15d, ecx
0x180007ff5  add     r15, rsi
0x180007ff8  test    al, 3
0x180007ffa  setnz   cl
0x180007ffd  bt      eax, 13h
0x180008001  mov     ebp, [rdx+r15]
0x180008005  mov     r12d, [rdx+r15+4]
0x18000800a  setb    al
0x18000800d  test    al, cl
0x18000800f  jz      short loc_18000804D
0x180008011  mov     rcx, cs:g_pDebug
0x180008018  lea     rax, aStartListenerc; "Start ListenerChannel Requested for: %S"...
0x18000801f  mov     dword ptr [rsp+78h+var_48], ebp
0x180008023  lea     r9, aWpIpmHandlesta; "WP_IPM::HandleStartListenerChannel"
0x18000802a  mov     qword ptr [rsp+78h+var_50], rbx
0x18000802f  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008036  mov     r8d, 308h
0x18000803c  mov     qword ptr [rsp+78h+var_58], rax
0x180008041  call    cs:__imp_PuDbgPrint
0x180008048  nop     dword ptr [rax+rax+00h]
0x18000804d  lea     rax, [r15+8]
0x180008051  mov     r9, rbx; unsigned __int16 *
0x180008054  add     rax, r14
0x180008057  mov     r8, rsi; unsigned __int16 *
0x18000805a  mov     [rsp+78h+var_48], rax; unsigned __int8 *
0x18000805f  mov     rdx, rdi; unsigned __int16 *
0x180008062  mov     [rsp+78h+var_50], r12d; unsigned int
0x180008067  mov     [rsp+78h+var_58], ebp; unsigned int
0x18000806b  call    ?StartListenerChannel@W3WP_HOST@@QEAAXPEBG00KKPEAE@Z; W3WP_HOST::StartListenerChannel(ushort const *,ushort const *,ushort const *,ulong,ulong,uchar *)
0x180008070  xor     eax, eax
0x180008072  add     rsp, 40h
0x180008076  pop     r15
0x180008078  pop     r14
0x18000807a  pop     r12
0x18000807c  pop     rdi
0x18000807d  pop     rsi
0x18000807e  pop     rbp
0x18000807f  pop     rbx
0x180008080  retn
```
