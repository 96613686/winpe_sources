# SkmiDeletePartition

- ea: `0x1400710a0`
- end: `0x140071154`
- name: `SkmiDeletePartition`
- size: `180`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1400355f4`
- `0x14007115c`

## callees

- `0x140022f88`
- `0x140037e68`
- `0x140052970`
- `0x1400710a0`
- `0x1400bb7e0`
- `0x1400ee8b0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiDeletePartition(__int64 a1)
{
  unsigned int v3; // [rsp+20h] [rbp-88h] BYREF
  __int64 v4; // [rsp+28h] [rbp-80h]
  __int64 v5; // [rsp+30h] [rbp-78h]

  memset_0(&v3, 0, 0x68u);
  SkDequeueWorkItem(a1 + 192);
  SkmiFreeDeferredPages(a1);
  if ( *(_QWORD *)(a1 + 240) )
  {
    memset_0(&v3, 0, 0x68u);
    v4 = 0;
    HIWORD(v3) = 38;
    v5 = *(_QWORD *)(a1 + 248);
    SkCallNormalMode(&v3);
  }
  SkmiFreePageBundles(a1);
  return SkFreePool(512, a1);
}

```

## disassembly

```asm
0x1400710a0  push    rbx
0x1400710a2  sub     rsp, 0A0h
0x1400710a9  mov     rax, cs:__security_cookie
0x1400710b0  xor     rax, rsp
0x1400710b3  mov     [rsp+0A8h+var_18], rax
0x1400710bb  xor     edx, edx; Val
0x1400710bd  mov     rbx, rcx
0x1400710c0  lea     rcx, [rsp+0A8h+var_88]; void *
0x1400710c5  lea     r8d, [rdx+68h]; Size
0x1400710c9  call    memset_0
0x1400710ce  lea     rcx, [rbx+0C0h]
0x1400710d5  call    SkDequeueWorkItem
0x1400710da  mov     rcx, rbx
0x1400710dd  call    SkmiFreeDeferredPages
0x1400710e2  cmp     qword ptr [rbx+0F0h], 0
0x1400710ea  jz      short loc_140071125
0x1400710ec  xor     edx, edx; Val
0x1400710ee  lea     rcx, [rsp+0A8h+var_88]; void *
0x1400710f3  lea     r8d, [rdx+68h]; Size
0x1400710f7  call    memset_0
0x1400710fc  mov     eax, 26h ; '&'
0x140071101  mov     [rsp+0A8h+var_80], 0
0x14007110a  mov     [rsp+0A8h+var_86], ax
0x14007110f  lea     rcx, [rsp+0A8h+var_88]
0x140071114  mov     rax, [rbx+0F8h]
0x14007111b  mov     [rsp+0A8h+var_78], rax
0x140071120  call    SkCallNormalMode
0x140071125  mov     rcx, rbx
0x140071128  call    SkmiFreePageBundles
0x14007112d  mov     rdx, rbx
0x140071130  mov     ecx, 200h
0x140071135  call    SkFreePool
0x14007113a  mov     rcx, [rsp+0A8h+var_18]
0x140071142  xor     rcx, rsp; StackCookie
0x140071145  call    __security_check_cookie
0x14007114a  add     rsp, 0A0h
0x140071151  pop     rbx
0x140071152  retn
```
