# KsppAllocateAndCopyString

- ea: `0x180014070`
- end: `0x180014170`
- name: `KsppAllocateAndCopyString`
- size: `256`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180014ecc`
- `0x180015a5c`
- `0x180025ff0`
- `0x180027054`
- `0x1800283dc`

## callees

- `0x180009e76`
- `0x18000a3c8`
- `0x180011fd8`
- `0x180014070`
- `0x18002ad70`
- `0x18002b140`

## pseudocode

```c
__int64 __fastcall KsppAllocateAndCopyString(_QWORD *a1, const void *a2, unsigned int a3)
{
  size_t v3; // rdi
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  size_t v9; // rbp
  void *v10; // rax
  __int64 v11; // rcx
  void *v12; // rdi

  v3 = a3;
  if ( a2 && a3 && *((_WORD *)a2 + ((unsigned __int64)a3 >> 1) - 1) )
  {
    WppTraceIndent((__int64)a1, 2u);
    v6 = -2146893785;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 15;
LABEL_8:
      WPP_SF_d(v7[2], v8, &WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids, v6);
    }
  }
  else
  {
    v6 = 0;
    if ( !*a1 || (KspFreeBuffer(), *a1 = 0, a2) && (_DWORD)v3 )
    {
      v9 = v3;
      v10 = MIDL_user_allocate(v3);
      v12 = v10;
      if ( v10 )
      {
        memcpy_0(v10, a2, v9);
        *a1 = v12;
        return v6;
      }
      WppTraceIndent(v11, 2u);
      v6 = 8;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 16;
        goto LABEL_8;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180014070  push    rbx
0x180014072  push    rbp
0x180014073  push    rsi
0x180014074  push    rdi
0x180014075  push    r14
0x180014077  push    r15
0x180014079  sub     rsp, 28h
0x18001407d  xor     r15d, r15d
0x180014080  mov     edi, r8d
0x180014083  mov     rsi, rdx
0x180014086  mov     r14, rcx
0x180014089  test    rdx, rdx
0x18001408c  jz      short loc_1800140F2
0x18001408e  test    r8d, r8d
0x180014091  jz      short loc_1800140F2
0x180014093  mov     eax, edi
0x180014095  shr     rax, 1
0x180014098  cmp     [rdx+rax*2-2], r15w
0x18001409e  jz      short loc_1800140F2
0x1800140a0  lea     edx, [r15+2]
0x1800140a4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800140a9  mov     ebx, 80090027h
0x1800140ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140b5  lea     rax, WPP_GLOBAL_Control
0x1800140bc  cmp     rcx, rax
0x1800140bf  jz      loc_180014161
0x1800140c5  test    byte ptr [rcx+1Ch], 1
0x1800140c9  jz      loc_180014161
0x1800140cf  cmp     byte ptr [rcx+19h], 2
0x1800140d3  jb      loc_180014161
0x1800140d9  lea     edx, [r15+0Fh]
0x1800140dd  mov     rcx, [rcx+10h]
0x1800140e1  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x1800140e8  mov     r9d, ebx
0x1800140eb  call    WPP_SF_d
0x1800140f0  jmp     short loc_180014161
0x1800140f2  mov     rcx, [rcx]
0x1800140f5  mov     ebx, r15d
0x1800140f8  test    rcx, rcx
0x1800140fb  jz      short loc_18001410E
0x1800140fd  call    KspFreeBuffer
0x180014102  mov     [r14], r15
0x180014105  test    rsi, rsi
0x180014108  jz      short loc_180014161
0x18001410a  test    edi, edi
0x18001410c  jz      short loc_180014161
0x18001410e  mov     rcx, rdi; size
0x180014111  mov     rbp, rdi
0x180014114  call    MIDL_user_allocate
0x180014119  mov     rdi, rax
0x18001411c  test    rax, rax
0x18001411f  jnz     short loc_180014150
0x180014121  lea     edx, [rax+2]
0x180014124  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180014129  lea     ebx, [rdi+8]
0x18001412c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014133  lea     rax, WPP_GLOBAL_Control
0x18001413a  cmp     rcx, rax
0x18001413d  jz      short loc_180014161
0x18001413f  test    byte ptr [rcx+1Ch], 1
0x180014143  jz      short loc_180014161
0x180014145  cmp     byte ptr [rcx+19h], 2
0x180014149  jb      short loc_180014161
0x18001414b  lea     edx, [rdi+10h]
0x18001414e  jmp     short loc_1800140DD
0x180014150  mov     r8, rbp; Size
0x180014153  mov     rdx, rsi; Src
0x180014156  mov     rcx, rdi; void *
0x180014159  call    memcpy_0
0x18001415e  mov     [r14], rdi
0x180014161  mov     eax, ebx
0x180014163  add     rsp, 28h
0x180014167  pop     r15
0x180014169  pop     r14
0x18001416b  pop     rdi
0x18001416c  pop     rsi
0x18001416d  pop     rbp
0x18001416e  pop     rbx
0x18001416f  retn
```
