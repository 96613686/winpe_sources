# CVssDebugInfo::operator<<(ushort const *)

- ea: `0x180034038`
- end: `0x1800340dc`
- name: `??6CVssDebugInfo@@QEAA?AU0@PEBG@Z`
- size: `164`
- prototype: `CVssDebugInfo *__fastcall(struct CVssDebugInfo *, CVssDebugInfo *this, unsigned __int16 *)`
- caller_count: `17`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011178`
- `0x18001b130`
- `0x180020c6c`
- `0x180021bc4`
- `0x180033df4`
- `0x180033e60`
- `0x1800340e4`
- `0x1800341c0`
- `0x180034cfc`
- `0x180035f44`
- `0x180036c10`
- `0x180036f10`
- `0x180037080`
- `0x1800372e8`
- `0x18003750c`
- `0x1800377c4`
- `0x18003ced0`

## callees

- `0x180007604`
- `0x1800339c0`
- `0x180034038`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034088`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034088`

## pseudocode

```c
CVssDebugInfo *__fastcall CVssDebugInfo::operator<<(
        struct CVssDebugInfo *a1,
        CVssDebugInfo *this,
        unsigned __int16 *a3)
{
  __int64 v6; // rax
  unsigned __int64 v7; // r14
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbp

  if ( a3 && !*((_BYTE *)a1 + 162) && *((_BYTE *)a1 + 163) && *((_WORD *)a1 + 80) < 0xFu )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = v6 + 1;
    v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v6 + 1));
    v9 = v8;
    if ( v8 )
    {
      StringCchCopyW(v8, v7, a3);
      *((_QWORD *)a1 + (unsigned __int16)(*((_WORD *)a1 + 80))++ + 5) = v9;
    }
    else
    {
      *((_BYTE *)a1 + 162) = 1;
    }
  }
  CVssDebugInfo::CVssDebugInfo(this, a1);
  return this;
}

```

## disassembly

```asm
0x180034038  push    rbx
0x18003403a  push    rbp
0x18003403b  push    rsi
0x18003403c  push    rdi
0x18003403d  push    r14
0x18003403f  push    r15
0x180034041  sub     rsp, 28h
0x180034045  xor     r15d, r15d
0x180034048  mov     rsi, r8
0x18003404b  mov     rdi, rdx
0x18003404e  mov     rbx, rcx
0x180034051  test    r8, r8
0x180034054  jz      short loc_1800340C1
0x180034056  cmp     [rcx+0A2h], r15b
0x18003405d  jnz     short loc_1800340C1
0x18003405f  cmp     [rcx+0A3h], r15b
0x180034066  jz      short loc_1800340C1
0x180034068  cmp     word ptr [rcx+0A0h], 0Fh
0x180034070  jnb     short loc_1800340C1
0x180034072  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034076  inc     rax
0x180034079  cmp     [r8+rax*2], r15w
0x18003407e  jnz     short loc_180034076
0x180034080  lea     r14, [rax+1]
0x180034084  lea     rcx, [r14+r14]; cb
0x180034088  call    cs:__imp_CoTaskMemAlloc
0x18003408e  mov     rbp, rax
0x180034091  test    rax, rax
0x180034094  jnz     short loc_18003409F
0x180034096  mov     byte ptr [rbx+0A2h], 1
0x18003409d  jmp     short loc_1800340C1
0x18003409f  mov     r8, rsi; unsigned __int16 *
0x1800340a2  mov     rdx, r14; unsigned __int64
0x1800340a5  mov     rcx, rbp; unsigned __int16 *
0x1800340a8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800340ad  movzx   r11d, word ptr [rbx+0A0h]
0x1800340b5  mov     [rbx+r11*8+28h], rbp
0x1800340ba  inc     word ptr [rbx+0A0h]
0x1800340c1  mov     rdx, rbx; struct CVssDebugInfo *
0x1800340c4  mov     rcx, rdi; this
0x1800340c7  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x1800340cc  mov     rax, rdi
0x1800340cf  add     rsp, 28h
0x1800340d3  pop     r15
0x1800340d5  pop     r14
0x1800340d7  pop     rdi
0x1800340d8  pop     rsi
0x1800340d9  pop     rbp
0x1800340da  pop     rbx
0x1800340db  retn
```
