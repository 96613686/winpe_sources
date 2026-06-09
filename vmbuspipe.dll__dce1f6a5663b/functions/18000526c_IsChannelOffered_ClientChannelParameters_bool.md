# IsChannelOffered(ClientChannelParameters *,bool *)

- ea: `0x18000526c`
- end: `0x1800052e7`
- name: `?IsChannelOffered@@YAJPEAUClientChannelParameters@@PEA_N@Z`
- size: `123`
- prototype: `__int64 __fastcall(const struct _GUID **, bool *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001d30`
- `0x180005a50`
- `0x180005b10`
- `0x1800071f0`

## callees

- `0x180001b44`
- `0x18000526c`
- `0x180006718`

## string_xrefs

- `0x1800052a8`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`

## pseudocode

```c
__int64 __fastcall IsChannelOffered(const struct _GUID **a1, bool *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  bool v7; // al
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  bool v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = 0;
  v4 = VmbusPipeClientEnumeratePipesInternal(a1[1], a1, InternalOnOfferNotification, &v10);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v7 = v10 && *((_BYTE *)a1 + 24);
    *a2 = v7;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
      (const char *)(unsigned int)v4,
      v8);
    return v5;
  }
}

```

## disassembly

```asm
0x18000526c  mov     rax, rsp
0x18000526f  mov     [rax+10h], rbx
0x180005273  mov     [rax+18h], rsi
0x180005277  push    rdi; int
0x180005278  sub     rsp, 20h
0x18000527c  mov     rsi, rdx
0x18000527f  mov     byte ptr [rax+8], 0
0x180005283  mov     rdx, rcx; void *
0x180005286  lea     r9, [rax+8]; bool *
0x18000528a  mov     rdi, rcx
0x18000528d  lea     r8, InternalOnOfferNotification; void (*)(void *, unsigned __int8 *, struct _VMBUS_PIPE_CHANNEL_INFO *, const struct _GUID *)
0x180005294  mov     rcx, [rcx+8]; struct _GUID *
0x180005298  call    ?VmbusPipeClientEnumeratePipesInternal@@YAJPEBU_GUID@@PEAXP6AX1PEAEPEAU_VMBUS_PIPE_CHANNEL_INFO@@0@ZPEA_N@Z; VmbusPipeClientEnumeratePipesInternal(_GUID const *,void *,void (*)(void *,uchar *,_VMBUS_PIPE_CHANNEL_INFO *,_GUID const *),bool *)
0x18000529d  mov     ebx, eax
0x18000529f  test    eax, eax
0x1800052a1  jns     short loc_1800052C0
0x1800052a3  mov     rcx, [rsp+28h]; this
0x1800052a8  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x1800052af  mov     r9d, eax; char *
0x1800052b2  mov     edx, 1EFh; void *
0x1800052b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052bc  mov     eax, ebx
0x1800052be  jmp     short loc_1800052D7
0x1800052c0  cmp     [rsp+28h+arg_0], 0
0x1800052c5  jz      short loc_1800052D1
0x1800052c7  cmp     byte ptr [rdi+18h], 0
0x1800052cb  jz      short loc_1800052D1
0x1800052cd  mov     al, 1
0x1800052cf  jmp     short loc_1800052D3
0x1800052d1  xor     al, al
0x1800052d3  mov     [rsi], al
0x1800052d5  xor     eax, eax
0x1800052d7  mov     rbx, [rsp+28h+arg_8]
0x1800052dc  mov     rsi, [rsp+28h+arg_10]
0x1800052e1  add     rsp, 20h
0x1800052e5  pop     rdi
0x1800052e6  retn
```
