# WARMUP_APPLICATION_CONTEXT::~WARMUP_APPLICATION_CONTEXT(void)

- ea: `0x1800045ac`
- end: `0x180004653`
- name: `??1WARMUP_APPLICATION_CONTEXT@@EEAA@XZ`
- size: `167`
- prototype: `void __fastcall(WARMUP_APPLICATION_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002d20`

## callees

- `0x180001048`
- `0x1800045ac`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180004604`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000460e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004618`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004622`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004604`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000460e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004618`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004622`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000464c`

## pseudocode

```c
void __fastcall WARMUP_APPLICATION_CONTEXT::~WARMUP_APPLICATION_CONTEXT(WARMUP_APPLICATION_CONTEXT *this)
{
  _QWORD **v1; // rbx
  _QWORD *v3; // rax
  _QWORD *v4; // rcx
  _QWORD *v5; // rsi

  *((_DWORD *)this + 2) = 2019784545;
  *(_QWORD *)this = &WARMUP_APPLICATION_CONTEXT::`vftable';
  v1 = (_QWORD **)((char *)this + 88);
  while ( 1 )
  {
    v3 = *v1;
    if ( *v1 == v1 )
      break;
    if ( (_QWORD **)v3[1] != v1 || (v4 = (_QWORD *)*v3, *(_QWORD **)(*v3 + 8LL) != v3) )
      __fastfail(3u);
    v5 = v3 - 29;
    *v1 = v4;
    v4[1] = v1;
    if ( v3 != (_QWORD *)232 )
    {
      STRU::~STRU((STRU *)(v5 + 22));
      STRU::~STRU((STRU *)(v5 + 15));
      STRU::~STRU((STRU *)(v5 + 8));
      STRU::~STRU((STRU *)(v5 + 1));
      operator delete(v5);
    }
  }
  STRU::~STRU((WARMUP_APPLICATION_CONTEXT *)((char *)this + 24));
}

```

## disassembly

```asm
0x1800045ac  mov     [rsp+arg_0], rbx
0x1800045b1  mov     [rsp+arg_8], rsi
0x1800045b6  push    rdi
0x1800045b7  sub     rsp, 20h
0x1800045bb  lea     rax, ??_7WARMUP_APPLICATION_CONTEXT@@6B@; const WARMUP_APPLICATION_CONTEXT::`vftable'
0x1800045c2  mov     dword ptr [rcx+8], 78637761h
0x1800045c9  mov     [rcx], rax
0x1800045cc  lea     rbx, [rcx+58h]
0x1800045d0  mov     rdi, rcx
0x1800045d3  mov     rax, [rbx]
0x1800045d6  cmp     rax, rbx
0x1800045d9  jz      short loc_180004639
0x1800045db  cmp     [rax+8], rbx
0x1800045df  jnz     short loc_180004632
0x1800045e1  mov     rcx, [rax]
0x1800045e4  cmp     [rcx+8], rax
0x1800045e8  jnz     short loc_180004632
0x1800045ea  lea     rsi, [rax-0E8h]
0x1800045f1  mov     [rbx], rcx
0x1800045f4  mov     [rcx+8], rbx
0x1800045f8  test    rsi, rsi
0x1800045fb  jz      short loc_1800045D3
0x1800045fd  lea     rcx, [rsi+0B0h]
0x180004604  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000460a  lea     rcx, [rsi+78h]
0x18000460e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004614  lea     rcx, [rsi+40h]
0x180004618  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000461e  lea     rcx, [rsi+8]
0x180004622  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004628  mov     rcx, rsi; Block
0x18000462b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004630  jmp     short loc_1800045D3
0x180004632  mov     ecx, 3
0x180004637  int     29h; Win8: RtlFailFast(ecx)
0x180004639  lea     rcx, [rdi+18h]
0x18000463d  mov     rbx, [rsp+28h+arg_0]
0x180004642  mov     rsi, [rsp+28h+arg_8]
0x180004647  add     rsp, 20h
0x18000464b  pop     rdi
0x18000464c  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
