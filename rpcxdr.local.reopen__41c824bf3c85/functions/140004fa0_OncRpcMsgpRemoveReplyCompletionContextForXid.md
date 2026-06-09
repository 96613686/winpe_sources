# OncRpcMsgpRemoveReplyCompletionContextForXid

- ea: `0x140004fa0`
- end: `0x140005045`
- name: `OncRpcMsgpRemoveReplyCompletionContextForXid`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003cb4`
- `0x1400056d0`

## callees

- `0x1400020c0`
- `0x140004fa0`

## pseudocode

```c
__int64 *__fastcall OncRpcMsgpRemoveReplyCompletionContextForXid(unsigned int a1)
{
  __int64 *v1; // rbx
  __int64 *v3; // rdx
  __int64 *i; // rax
  __int64 *v5; // rcx
  __int64 **v6; // rdx

  v1 = 0;
  v3 = (__int64 *)((char *)P + 16 * (a1 % dword_14001A968));
  for ( i = (__int64 *)*v3; i != v3; i = (__int64 *)*i )
  {
    v1 = i;
    v5 = (__int64 *)*i;
    if ( *((_DWORD *)i + 8) == a1 )
    {
      if ( (__int64 *)v5[1] != i || (v6 = (__int64 **)i[1], *v6 != i) )
        __fastfail(3u);
      *v6 = v5;
      v5[1] = (__int64)v6;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids, a1);
      break;
    }
  }
  if ( !v1 || *((_DWORD *)v1 + 8) != a1 )
    return 0;
  return v1;
}

```

## disassembly

```asm
0x140004fa0  mov     [rsp+arg_0], rbx
0x140004fa5  push    rdi
0x140004fa6  sub     rsp, 20h
0x140004faa  xor     edx, edx
0x140004fac  mov     eax, ecx
0x140004fae  div     cs:dword_14001A968
0x140004fb4  xor     ebx, ebx
0x140004fb6  mov     edi, ecx
0x140004fb8  shl     rdx, 4
0x140004fbc  add     rdx, cs:P
0x140004fc3  mov     rax, [rdx]
0x140004fc6  cmp     rax, rdx
0x140004fc9  jz      short loc_140005023
0x140004fcb  mov     rbx, rax
0x140004fce  mov     rcx, [rax]
0x140004fd1  cmp     [rax+20h], edi
0x140004fd4  jz      short loc_140004FDB
0x140004fd6  mov     rax, rcx
0x140004fd9  jmp     short loc_140004FC6
0x140004fdb  cmp     [rcx+8], rax
0x140004fdf  jnz     short loc_14000503E
0x140004fe1  mov     rdx, [rax+8]
0x140004fe5  cmp     [rdx], rax
0x140004fe8  jnz     short loc_14000503E
0x140004fea  mov     [rdx], rcx
0x140004fed  mov     [rcx+8], rdx
0x140004ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ff8  lea     rax, WPP_GLOBAL_Control
0x140004fff  cmp     rcx, rax
0x140005002  jz      short loc_140005023
0x140005004  mov     eax, [rcx+2Ch]
0x140005007  test    al, 4
0x140005009  jz      short loc_140005023
0x14000500b  mov     rcx, [rcx+18h]
0x14000500f  lea     r8, WPP_805c0885a8ed3962ecc38e19173d6373_Traceguids
0x140005016  mov     edx, 0Ah
0x14000501b  mov     r9d, edi
0x14000501e  call    WPP_SF_d
0x140005023  test    rbx, rbx
0x140005026  jz      short loc_14000502D
0x140005028  cmp     [rbx+20h], edi
0x14000502b  jz      short loc_14000502F
0x14000502d  xor     ebx, ebx
0x14000502f  mov     rax, rbx
0x140005032  mov     rbx, [rsp+28h+arg_0]
0x140005037  add     rsp, 20h
0x14000503b  pop     rdi
0x14000503c  retn
0x14000503e  mov     ecx, 3
0x140005043  int     29h; Win8: RtlFailFast(ecx)
```
