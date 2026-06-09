# WP_IPM::HandleStartListenerChannel(IPM_MESSAGE const *)

- ea: `0x1800077a0`
- end: `0x1800078b3`
- name: `?HandleStartListenerChannel@WP_IPM@@QEAAJPEBVIPM_MESSAGE@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(WP_IPM *__hidden this, const struct IPM_MESSAGE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001170`

## callees

- `0x180006e3c`
- `0x1800077a0`
- `0x18000d010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007879`
- `iisutil!PuDbgPrint` at `0x180007879`

## string_xrefs

- `0x180007867`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\wpipm.cxx`

## pseudocode

```c
__int64 __fastcall WP_IPM::HandleStartListenerChannel(WP_IPM *this, const struct IPM_MESSAGE *a2)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  const unsigned __int16 *v4; // rbx
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
  v4 = (const unsigned __int16 *)v2;
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  v6 = 2 * v5 + 2;
  v7 = -1;
  v8 = (const unsigned __int16 *)((char *)v4 + v6);
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
      (_DWORD)v4);
  W3WP_HOST::StartListenerChannel(v12, v8, v9, v4, v15, v16, (unsigned __int8 *)&v14[v11 + 8]);
  return 0;
}

```

## disassembly

```asm
0x1800077a0  push    rbx
0x1800077a2  push    rbp
0x1800077a3  push    rsi
0x1800077a4  push    rdi
0x1800077a5  push    r12
0x1800077a7  push    r14
0x1800077a9  push    r15
0x1800077ab  sub     rsp, 40h
0x1800077af  mov     rax, [rdx]
0x1800077b2  mov     rcx, rdx
0x1800077b5  mov     rax, [rax+10h]
0x1800077b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077be  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800077c2  mov     rbx, rax
0x1800077c5  mov     rax, rdx
0x1800077c8  xor     r9d, r9d
0x1800077cb  inc     rax
0x1800077ce  cmp     [rbx+rax*2], r9w
0x1800077d3  jnz     short loc_1800077CB
0x1800077d5  lea     r8d, ds:2[rax*2]
0x1800077dd  mov     rax, rdx
0x1800077e0  mov     edi, r8d
0x1800077e3  add     rdi, rbx
0x1800077e6  inc     rax
0x1800077e9  cmp     [rdi+rax*2], r9w
0x1800077ee  jnz     short loc_1800077E6
0x1800077f0  lea     ecx, ds:2[rax*2]
0x1800077f7  mov     esi, ecx
0x1800077f9  add     rsi, rdi
0x1800077fc  inc     rdx
0x1800077ff  cmp     [rsi+rdx*2], r9w
0x180007804  jnz     short loc_1800077FC
0x180007806  mov     eax, cs:g_dwDebugFlags
0x18000780c  lea     edx, ds:2[rdx*2]
0x180007813  add     ecx, edx
0x180007815  mov     r14d, edx
0x180007818  add     ecx, r8d
0x18000781b  mov     r15d, 4
0x180007821  and     ecx, 3
0x180007824  sub     r15d, ecx
0x180007827  test    ecx, ecx
0x180007829  cmovz   r15d, ecx
0x18000782d  add     r15, rsi
0x180007830  test    al, 3
0x180007832  setnz   cl
0x180007835  bt      eax, 13h
0x180007839  mov     ebp, [rdx+r15]
0x18000783d  mov     r12d, [rdx+r15+4]
0x180007842  setb    al
0x180007845  test    al, cl
0x180007847  jz      short loc_18000787F
0x180007849  mov     rcx, cs:g_pDebug
0x180007850  lea     rax, aStartListenerc; "Start ListenerChannel Requested for: %S"...
0x180007857  mov     dword ptr [rsp+78h+var_48], ebp
0x18000785b  lea     r9, aWpIpmHandlesta; "WP_IPM::HandleStartListenerChannel"
0x180007862  mov     qword ptr [rsp+78h+var_50], rbx
0x180007867  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000786e  mov     r8d, 308h
0x180007874  mov     qword ptr [rsp+78h+var_58], rax
0x180007879  call    cs:__imp_PuDbgPrint
0x18000787f  lea     rax, [r15+8]
0x180007883  mov     r9, rbx; unsigned __int16 *
0x180007886  add     rax, r14
0x180007889  mov     r8, rsi; unsigned __int16 *
0x18000788c  mov     [rsp+78h+var_48], rax; unsigned __int8 *
0x180007891  mov     rdx, rdi; unsigned __int16 *
0x180007894  mov     [rsp+78h+var_50], r12d; unsigned int
0x180007899  mov     [rsp+78h+var_58], ebp; unsigned int
0x18000789d  call    ?StartListenerChannel@W3WP_HOST@@QEAAXPEBG00KKPEAE@Z; W3WP_HOST::StartListenerChannel(ushort const *,ushort const *,ushort const *,ulong,ulong,uchar *)
0x1800078a2  xor     eax, eax
0x1800078a4  add     rsp, 40h
0x1800078a8  pop     r15
0x1800078aa  pop     r14
0x1800078ac  pop     r12
0x1800078ae  pop     rdi
0x1800078af  pop     rsi
0x1800078b0  pop     rbp
0x1800078b1  pop     rbx
0x1800078b2  retn
```
