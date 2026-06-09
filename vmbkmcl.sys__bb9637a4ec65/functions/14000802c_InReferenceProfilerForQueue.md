# InReferenceProfilerForQueue

- ea: `0x14000802c`
- end: `0x140008139`
- name: `InReferenceProfilerForQueue`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008b48`

## callees

- `0x14000802c`
- `0x1400084f0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14000811d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000811d`
- `ntoskrnl!ExAcquireFastMutex` at `0x140008051`
- `ntoskrnl!ExAcquireFastMutex` at `0x140008051`
- `ntoskrnl!RtlCompareMemory` at `0x1400080aa`
- `ntoskrnl!RtlCompareMemory` at `0x1400080aa`

## pseudocode

```c
__int64 __fastcall InReferenceProfilerForQueue(__int64 *a1, unsigned int a2, __int64 **a3)
{
  __int64 *v6; // rdi
  __int64 v7; // rdx
  __int64 *v8; // rbx
  __int64 *v9; // rcx
  int v10; // ebx
  __int64 *v12; // [rsp+60h] [rbp+8h] BYREF

  v12 = 0;
  ExAcquireFastMutex(&KmclProfilerListLock);
  if ( *(_BYTE *)(*a1 + 1728) )
  {
    v6 = (__int64 *)KmclProfilerList;
    if ( (__int64 *)KmclProfilerList != &KmclProfilerList )
    {
      do
      {
        v7 = *a1;
        v8 = v6 - 1;
        v12 = v6 - 1;
        if ( v6[5] == *(_QWORD *)(v7 + 3264)
          && RtlCompareMemory(v8 + 3, (const void *)(v7 + 2736), 0x10u) == 16
          && *(_WORD *)(*a1 + 3272) == *((_WORD *)v8 + 20)
          && *((_DWORD *)v8 + 1) < 4u )
        {
          v9 = v6 - 1;
          if ( a2 <= *(_DWORD *)v8 << 10 )
            break;
        }
        v6 = (__int64 *)*v6;
        v8 = 0;
        v9 = 0;
        v12 = 0;
      }
      while ( v6 != &KmclProfilerList );
      if ( v9 )
        goto LABEL_12;
    }
  }
  v10 = InpAllocatePacketProfilerLocked(a1, a2, &v12);
  if ( v10 >= 0 )
  {
    v8 = v12;
LABEL_12:
    ++*((_DWORD *)v8 + 1);
    *a3 = v8;
    v10 = 0;
  }
  ExReleaseFastMutex(&KmclProfilerListLock);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000802c  push    rbx
0x14000802e  push    rbp
0x14000802f  push    rsi
0x140008030  push    rdi
0x140008031  push    r14
0x140008033  push    r15
0x140008035  sub     rsp, 28h
0x140008039  mov     rsi, rcx
0x14000803c  mov     [rsp+58h+arg_0], 0
0x140008045  lea     rcx, KmclProfilerListLock; FastMutex
0x14000804c  mov     r14, r8
0x14000804f  mov     ebp, edx
0x140008051  call    cs:__imp_ExAcquireFastMutex
0x140008058  nop     dword ptr [rax+rax+00h]
0x14000805d  mov     rax, [rsi]
0x140008060  cmp     byte ptr [rax+6C0h], 0
0x140008067  jz      loc_1400080F4
0x14000806d  mov     rdi, cs:KmclProfilerList
0x140008074  lea     r15, KmclProfilerList
0x14000807b  cmp     rdi, r15
0x14000807e  jz      short loc_1400080F4
0x140008080  mov     rdx, [rsi]
0x140008083  lea     rbx, [rdi-8]
0x140008087  mov     [rsp+58h+arg_0], rbx
0x14000808c  mov     rax, [rdx+0CC0h]
0x140008093  cmp     [rbx+30h], rax
0x140008097  jnz     short loc_1400080DE
0x140008099  add     rdx, 0AB0h; Source2
0x1400080a0  lea     rcx, [rbx+18h]; Source1
0x1400080a4  mov     r8d, 10h; Length
0x1400080aa  call    cs:__imp_RtlCompareMemory
0x1400080b1  nop     dword ptr [rax+rax+00h]
0x1400080b6  cmp     rax, 10h
0x1400080ba  jnz     short loc_1400080DE
0x1400080bc  mov     rcx, [rsi]
0x1400080bf  movzx   eax, word ptr [rbx+28h]
0x1400080c3  cmp     [rcx+0CC8h], ax
0x1400080ca  jnz     short loc_1400080DE
0x1400080cc  cmp     dword ptr [rbx+4], 4
0x1400080d0  jnb     short loc_1400080DE
0x1400080d2  mov     eax, [rbx]
0x1400080d4  mov     rcx, rbx
0x1400080d7  shl     eax, 0Ah
0x1400080da  cmp     ebp, eax
0x1400080dc  jbe     short loc_1400080EF
0x1400080de  mov     rdi, [rdi]
0x1400080e1  xor     ebx, ebx
0x1400080e3  xor     ecx, ecx
0x1400080e5  mov     [rsp+58h+arg_0], rbx
0x1400080ea  cmp     rdi, r15
0x1400080ed  jnz     short loc_140008080
0x1400080ef  test    rcx, rcx
0x1400080f2  jnz     short loc_14000810E
0x1400080f4  lea     r8, [rsp+58h+arg_0]
0x1400080f9  mov     edx, ebp
0x1400080fb  mov     rcx, rsi
0x1400080fe  call    InpAllocatePacketProfilerLocked
0x140008103  mov     ebx, eax
0x140008105  test    eax, eax
0x140008107  js      short loc_140008116
0x140008109  mov     rbx, [rsp+58h+arg_0]
0x14000810e  inc     dword ptr [rbx+4]
0x140008111  mov     [r14], rbx
0x140008114  xor     ebx, ebx
0x140008116  lea     rcx, KmclProfilerListLock; FastMutex
0x14000811d  call    cs:__imp_ExReleaseFastMutex
0x140008124  nop     dword ptr [rax+rax+00h]
0x140008129  mov     eax, ebx
0x14000812b  add     rsp, 28h
0x14000812f  pop     r15
0x140008131  pop     r14
0x140008133  pop     rdi
0x140008134  pop     rsi
0x140008135  pop     rbp
0x140008136  pop     rbx
0x140008137  retn
```
