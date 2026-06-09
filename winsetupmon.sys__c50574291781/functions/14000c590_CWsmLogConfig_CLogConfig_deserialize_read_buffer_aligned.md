# CWsmLogConfig::CLogConfig::deserialize(read_buffer_aligned &)

- ea: `0x14000c590`
- end: `0x14000c6e1`
- name: `?deserialize@CLogConfig@CWsmLogConfig@@UEAAJAEAVread_buffer_aligned@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(CWsmLogConfig::CLogConfig *__hidden this, struct read_buffer_aligned *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x140008c08`
- `0x14000c590`
- `0x14000f9e0`
- `0x14000fa40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c5db`

## pseudocode

```c
__int64 __fastcall CWsmLogConfig::CLogConfig::deserialize(
        CWsmLogConfig::CLogConfig *this,
        struct read_buffer_aligned *a2)
{
  void **v2; // rdi
  void *v5; // rcx
  __int64 result; // rax
  __int64 *v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // edx
  unsigned int v10; // eax
  unsigned int v11; // ecx
  unsigned int v12; // r8d
  int v13; // edi
  unsigned int v14; // edi
  int v15; // [rsp+50h] [rbp+8h] BYREF

  v2 = (void **)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v2 )
  {
    v5 = *v2;
    if ( *v2 != v2 + 2 && v5 )
      ExFreePoolWithTag(v5, 0x6E6D7377u);
    ExFreePoolWithTag(v2, 0x6E6D7377u);
  }
  v15 = 0;
  *(_OWORD *)((char *)this + 8) = 0;
  result = read_buffer_aligned::read<unsigned long>((__int64)a2, &v15);
  if ( (int)result >= 0 )
  {
    if ( v15 != 1852666743 )
      return 3221227289LL;
    v15 = 0;
    result = read_buffer_aligned::read<unsigned long>((__int64)a2, &v15);
    if ( (int)result >= 0 )
    {
      if ( v15 != 2 )
        return 3221225561LL;
      result = (*(__int64 (__fastcall **)(char *, struct read_buffer_aligned *))(*((_QWORD *)this + 3) + 8LL))(
                 (char *)this + 24,
                 a2);
      if ( (int)result >= 0 )
      {
        v7 = (__int64 *)*((_QWORD *)this + 4);
        if ( v7 )
          v8 = *v7;
        else
          v8 = 0;
        *((_QWORD *)this + 1) = v8;
        v9 = *((_DWORD *)a2 + 3);
        if ( (v9 & 7) != 0 )
        {
          v10 = v9 + (*((_DWORD *)a2 + 3) & 7);
          v11 = -1;
          if ( v10 >= v9 )
            v11 = v9 + (*((_DWORD *)a2 + 3) & 7);
          v12 = v10 < v9 ? 0xC0000095 : 0;
          if ( v10 < v9 )
            return v12;
          *((_DWORD *)a2 + 3) = v11;
        }
        else
        {
          v11 = *((_DWORD *)a2 + 3);
        }
        v13 = *((_DWORD *)a2 + 2);
        if ( v11 != v13 )
        {
          v14 = v13 - v11;
          if ( v14 >= 8 )
            v14 = 8;
          memmove((char *)this + 16, (const void *)(*(_QWORD *)a2 + v11), v14);
          *((_DWORD *)a2 + 3) += v14;
          return 0;
        }
        return (unsigned int)-2147483614;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000c590  push    rbx
0x14000c592  push    rsi
0x14000c593  push    rdi
0x14000c594  push    r14
0x14000c596  sub     rsp, 28h
0x14000c59a  mov     rdi, [rcx+20h]
0x14000c59e  mov     rbx, rdx
0x14000c5a1  mov     qword ptr [rcx+20h], 0
0x14000c5a9  mov     rsi, rcx
0x14000c5ac  test    rdi, rdi
0x14000c5af  jz      short loc_14000C5E7
0x14000c5b1  mov     rcx, [rdi]; P
0x14000c5b4  lea     rax, [rdi+10h]
0x14000c5b8  cmp     rcx, rax
0x14000c5bb  jz      short loc_14000C5D3
0x14000c5bd  test    rcx, rcx
0x14000c5c0  jz      short loc_14000C5D3
0x14000c5c2  mov     edx, 6E6D7377h; Tag
0x14000c5c7  call    cs:__imp_ExFreePoolWithTag
0x14000c5ce  nop     dword ptr [rax+rax+00h]
0x14000c5d3  mov     edx, 6E6D7377h; Tag
0x14000c5d8  mov     rcx, rdi; P
0x14000c5db  call    cs:__imp_ExFreePoolWithTag
0x14000c5e2  nop     dword ptr [rax+rax+00h]
0x14000c5e7  xorps   xmm0, xmm0
0x14000c5ea  mov     [rsp+48h+arg_0], 0
0x14000c5f2  lea     rdx, [rsp+48h+arg_0]
0x14000c5f7  mov     rcx, rbx
0x14000c5fa  movups  xmmword ptr [rsi+8], xmm0
0x14000c5fe  call    ??$read@K@read_buffer_aligned@@QEAAJAEAK@Z; read_buffer_aligned::read<ulong>(ulong &)
0x14000c603  test    eax, eax
0x14000c605  js      loc_14000C6D6
0x14000c60b  cmp     [rsp+48h+arg_0], 6E6D7377h
0x14000c613  jz      short loc_14000C61F
0x14000c615  mov     eax, 0C0000719h
0x14000c61a  jmp     loc_14000C6D6
0x14000c61f  lea     rdx, [rsp+48h+arg_0]
0x14000c624  mov     [rsp+48h+arg_0], 0
0x14000c62c  mov     rcx, rbx
0x14000c62f  call    ??$read@K@read_buffer_aligned@@QEAAJAEAK@Z; read_buffer_aligned::read<ulong>(ulong &)
0x14000c634  test    eax, eax
0x14000c636  js      loc_14000C6D6
0x14000c63c  cmp     [rsp+48h+arg_0], 2
0x14000c641  jz      short loc_14000C64D
0x14000c643  mov     eax, 0C0000059h
0x14000c648  jmp     loc_14000C6D6
0x14000c64d  mov     rax, [rsi+18h]
0x14000c651  lea     rcx, [rsi+18h]
0x14000c655  mov     rdx, rbx
0x14000c658  mov     rax, [rax+8]
0x14000c65c  call    _guard_dispatch_icall
0x14000c661  test    eax, eax
0x14000c663  js      short loc_14000C6D6
0x14000c665  mov     rax, [rsi+20h]
0x14000c669  test    rax, rax
0x14000c66c  jz      short loc_14000C673
0x14000c66e  mov     rcx, [rax]
0x14000c671  jmp     short loc_14000C675
0x14000c673  xor     ecx, ecx
0x14000c675  mov     [rsi+8], rcx
0x14000c679  mov     edx, [rbx+0Ch]
0x14000c67c  mov     eax, edx
0x14000c67e  and     eax, 7
0x14000c681  jz      short loc_14000C6A0
0x14000c683  add     eax, edx
0x14000c685  or      ecx, 0FFFFFFFFh
0x14000c688  cmp     eax, edx
0x14000c68a  cmovnb  ecx, eax
0x14000c68d  sbb     r8d, r8d
0x14000c690  and     r8d, 0C0000095h
0x14000c697  cmp     eax, edx
0x14000c699  jb      short loc_14000C6D3
0x14000c69b  mov     [rbx+0Ch], ecx
0x14000c69e  jmp     short loc_14000C6A2
0x14000c6a0  mov     ecx, edx
0x14000c6a2  mov     edi, [rbx+8]
0x14000c6a5  cmp     ecx, edi
0x14000c6a7  jz      short loc_14000C6CD
0x14000c6a9  sub     edi, ecx
0x14000c6ab  mov     edx, ecx
0x14000c6ad  mov     eax, 8
0x14000c6b2  lea     rcx, [rsi+10h]; void *
0x14000c6b6  cmp     edi, eax
0x14000c6b8  cmovnb  edi, eax
0x14000c6bb  add     rdx, [rbx]; Src
0x14000c6be  mov     r8d, edi; Size
0x14000c6c1  call    memmove
0x14000c6c6  add     [rbx+0Ch], edi
0x14000c6c9  xor     eax, eax
0x14000c6cb  jmp     short loc_14000C6D6
0x14000c6cd  mov     r8d, 80000022h
0x14000c6d3  mov     eax, r8d
0x14000c6d6  add     rsp, 28h
0x14000c6da  pop     r14
0x14000c6dc  pop     rdi
0x14000c6dd  pop     rsi
0x14000c6de  pop     rbx
0x14000c6df  retn
```
