# TEMPLATE_LIST::CreateBinXMLIfPossible(TEMPLATE_ENTRY *)

- ea: `0x18001bb98`
- end: `0x18001bdb2`
- name: `?CreateBinXMLIfPossible@TEMPLATE_LIST@@AEAAXPEAVTEMPLATE_ENTRY@@@Z`
- size: `538`
- prototype: `void __fastcall(TEMPLATE_LIST *__hidden this, struct TEMPLATE_ENTRY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800193cc`

## callees

- `0x180001084`
- `0x180018d08`
- `0x18001b340`
- `0x18001bb98`
- `0x180021490`
- `0x18002fab0`
- `0x18004c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall TEMPLATE_LIST::CreateBinXMLIfPossible(TEMPLATE_LIST *this, struct TEMPLATE_ENTRY *a2)
{
  struct TEMPLATE_ENTRY *v2; // rdi
  __int64 v4; // r8
  __int64 v5; // rcx
  unsigned __int64 v6; // rbx
  __int64 v7; // rcx
  int v8; // eax
  char *v9; // rsi
  char *v10; // rdx
  int v11; // eax
  __int64 v12; // rdx
  char *v13; // rdx
  __int128 v14; // [rsp+50h] [rbp-20h] BYREF
  __int64 v15; // [rsp+60h] [rbp-10h]
  int v16; // [rsp+C0h] [rbp+50h] BYREF

  v2 = a2;
  v14 = 0;
  v4 = 0;
  v15 = 0;
  if ( *((_QWORD *)this + 1) )
  {
    v5 = *((_QWORD *)a2 + 13);
    if ( (*((_QWORD *)a2 + 14) - v5) >> 3 )
    {
      v6 = 0;
      while ( 1 )
      {
        v7 = *(_QWORD *)(v5 + 8 * v6);
        v8 = 14;
        if ( !*(_BYTE *)(v7 + 208) )
          v8 = *(unsigned __int16 *)(v7 + 240);
        v16 = v8;
        if ( *(_WORD *)(v7 + 128) || *(_QWORD *)(v7 + 264) )
        {
          v8 |= 0x80u;
          v16 = v8;
        }
        if ( *((_QWORD *)&v14 + 1) == v4 )
        {
          std::vector<unsigned long>::_Emplace_reallocate<unsigned long const &>(&v14, *((_QWORD *)&v14 + 1), &v16);
        }
        else
        {
          **((_DWORD **)&v14 + 1) = v8;
          *((_QWORD *)&v14 + 1) += 4LL;
        }
        ++v6;
        v5 = *((_QWORD *)v2 + 13);
        if ( v6 >= (*((_QWORD *)v2 + 14) - v5) >> 3 )
          break;
        v4 = v15;
      }
    }
    v9 = (char *)v2 + 64;
    if ( *((_QWORD *)v2 + 11) <= 7u )
      v10 = (char *)v2 + 64;
    else
      v10 = *(char **)v9;
    v11 = (*((__int64 (__fastcall **)(_QWORD, char *, __int64))this + 1))(
            *((unsigned int *)v2 + 20),
            v10,
            (__int64)(*((_QWORD *)&v14 + 1) - v14) >> 2);
    if ( v11 == 122 )
    {
      v12 = *((_QWORD *)v2 + 16);
      if ( *((_QWORD *)v2 + 17) != v12 )
        *((_QWORD *)v2 + 17) = v12;
      if ( *((_QWORD *)v2 + 11) <= 7u )
        v13 = (char *)v2 + 64;
      else
        v13 = *(char **)v9;
      v11 = (*((__int64 (__fastcall **)(_QWORD, char *, __int64))this + 1))(
              *((unsigned int *)v2 + 20),
              v13,
              (__int64)(*((_QWORD *)&v14 + 1) - v14) >> 2);
    }
    if ( v11 )
    {
      if ( *((_QWORD *)v2 + 11) > 7u )
        v9 = *(char **)v9;
      if ( *((_QWORD *)v2 + 3) > 7u )
        v2 = *(struct TEMPLATE_ENTRY **)v2;
      ThrowWithFormatMessage(-1073221780, v2, v9);
    }
    if ( (_QWORD)v14 )
      std::_Deallocate<16>(v14, (v15 - v14) & 0xFFFFFFFFFFFFFFFCuLL);
  }
}

```

## disassembly

```asm
0x18001bb98  mov     [rsp-38h+arg_8], rbx
0x18001bb9d  push    rbp
0x18001bb9e  push    rsi
0x18001bb9f  push    rdi
0x18001bba0  push    r12
0x18001bba2  push    r13
0x18001bba4  push    r14
0x18001bba6  push    r15
0x18001bba8  mov     rbp, rsp
0x18001bbab  sub     rsp, 70h
0x18001bbaf  mov     rdi, rdx
0x18001bbb2  mov     r15, rcx
0x18001bbb5  xor     r13d, r13d
0x18001bbb8  mov     [rbp+arg_0], r13d
0x18001bbbc  xorps   xmm0, xmm0
0x18001bbbf  movdqu  [rbp+var_20], xmm0
0x18001bbc4  mov     r8d, r13d
0x18001bbc7  mov     [rbp+var_10], r13
0x18001bbcb  cmp     [rcx+8], r13
0x18001bbcf  jnz     short loc_18001BBD6
0x18001bbd1  jmp     loc_18001BD9A
0x18001bbd6  mov     rcx, [rdx+68h]
0x18001bbda  mov     rax, [rdx+70h]
0x18001bbde  sub     rax, rcx
0x18001bbe1  sar     rax, 3
0x18001bbe5  test    rax, rax
0x18001bbe8  jz      short loc_18001BC5F
0x18001bbea  mov     rbx, r13
0x18001bbed  mov     rcx, [rcx+rbx*8]
0x18001bbf1  cmp     [rcx+0D0h], r13b
0x18001bbf8  mov     eax, 0Eh
0x18001bbfd  jnz     short loc_18001BC06
0x18001bbff  movzx   eax, word ptr [rcx+0F0h]
0x18001bc06  mov     [rbp+arg_10], eax
0x18001bc09  cmp     [rcx+80h], r13w
0x18001bc11  ja      short loc_18001BC1C
0x18001bc13  cmp     [rcx+108h], r13
0x18001bc1a  jz      short loc_18001BC23
0x18001bc1c  bts     eax, 7
0x18001bc20  mov     [rbp+arg_10], eax
0x18001bc23  mov     rdx, qword ptr [rbp+var_20+8]
0x18001bc27  cmp     rdx, r8
0x18001bc2a  jz      short loc_18001BC35
0x18001bc2c  mov     [rdx], eax
0x18001bc2e  add     qword ptr [rbp+var_20+8], 4
0x18001bc33  jmp     short loc_18001BC42
0x18001bc35  lea     r8, [rbp+arg_10]
0x18001bc39  lea     rcx, [rbp+var_20]
0x18001bc3d  call    ??$_Emplace_reallocate@AEBK@?$vector@KV?$allocator@K@std@@@std@@AEAAPEAKQEAKAEBK@Z; std::vector<ulong>::_Emplace_reallocate<ulong const &>(ulong * const,ulong const &)
0x18001bc42  inc     rbx
0x18001bc45  mov     rcx, [rdi+68h]
0x18001bc49  mov     rax, [rdi+70h]
0x18001bc4d  sub     rax, rcx
0x18001bc50  sar     rax, 3
0x18001bc54  cmp     rbx, rax
0x18001bc57  jnb     short loc_18001BC5F
0x18001bc59  mov     r8, [rbp+var_10]
0x18001bc5d  jmp     short loc_18001BBED
0x18001bc5f  mov     r9, qword ptr [rbp+var_20]
0x18001bc63  mov     r8, qword ptr [rbp+var_20+8]
0x18001bc67  sub     r8, r9
0x18001bc6a  sar     r8, 2
0x18001bc6e  lea     rsi, [rdi+40h]
0x18001bc72  cmp     qword ptr [rsi+18h], 7
0x18001bc77  jbe     short loc_18001BC7E
0x18001bc79  mov     rdx, [rsi]
0x18001bc7c  jmp     short loc_18001BC81
0x18001bc7e  mov     rdx, rsi
0x18001bc81  lea     r12, [rdi+98h]
0x18001bc88  mov     [rsp+70h+var_38], r12
0x18001bc8d  lea     rax, [rbp+arg_0]
0x18001bc91  mov     [rsp+70h+var_40], rax
0x18001bc96  mov     [rsp+70h+var_48], r13
0x18001bc9b  mov     [rsp+70h+var_50], r13d
0x18001bca0  mov     ecx, [rdi+50h]
0x18001bca3  mov     rax, [r15+8]
0x18001bca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcac  cmp     eax, 7Ah ; 'z'
0x18001bcaf  jnz     loc_18001BD58
0x18001bcb5  lea     r14, [rdi+80h]
0x18001bcbc  mov     r8d, [rbp+arg_0]
0x18001bcc0  mov     rdx, [r14]
0x18001bcc3  mov     r9, [r14+8]
0x18001bcc7  mov     rcx, r9
0x18001bcca  sub     rcx, rdx
0x18001bccd  cmp     r8, rcx
0x18001bcd0  jnb     short loc_18001BCDC
0x18001bcd2  lea     rax, [rdx+r8]
0x18001bcd6  mov     [r14+8], rax
0x18001bcda  jmp     short loc_18001BD0C
0x18001bcdc  jbe     short loc_18001BD0C
0x18001bcde  mov     rax, [r14+10h]
0x18001bce2  sub     rax, rdx
0x18001bce5  cmp     r8, rax
0x18001bce8  jbe     short loc_18001BCF7
0x18001bcea  mov     rdx, r8
0x18001bced  mov     rcx, r14
0x18001bcf0  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001bcf5  jmp     short loc_18001BD0C
0x18001bcf7  sub     r8, rcx; Size
0x18001bcfa  lea     rbx, [r8+r9]
0x18001bcfe  xor     edx, edx; Val
0x18001bd00  mov     rcx, r9; void *
0x18001bd03  call    memset_0
0x18001bd08  mov     [r14+8], rbx
0x18001bd0c  mov     rcx, [r14]
0x18001bd0f  mov     eax, [rdi+88h]
0x18001bd15  sub     eax, ecx
0x18001bd17  mov     r9, qword ptr [rbp+var_20]
0x18001bd1b  mov     r8, qword ptr [rbp+var_20+8]
0x18001bd1f  sub     r8, r9
0x18001bd22  sar     r8, 2
0x18001bd26  cmp     qword ptr [rsi+18h], 7
0x18001bd2b  jbe     short loc_18001BD32
0x18001bd2d  mov     rdx, [rsi]
0x18001bd30  jmp     short loc_18001BD35
0x18001bd32  mov     rdx, rsi
0x18001bd35  mov     [rsp+70h+var_38], r12
0x18001bd3a  lea     r10, [rbp+arg_0]
0x18001bd3e  mov     [rsp+70h+var_40], r10
0x18001bd43  mov     [rsp+70h+var_48], rcx
0x18001bd48  mov     [rsp+70h+var_50], eax
0x18001bd4c  mov     ecx, [rdi+50h]
0x18001bd4f  mov     rax, [r15+8]
0x18001bd53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd58  test    eax, eax
0x18001bd5a  jz      short loc_18001BD81
0x18001bd5c  cmp     qword ptr [rsi+18h], 7
0x18001bd61  jbe     short loc_18001BD66
0x18001bd63  mov     rsi, [rsi]
0x18001bd66  cmp     qword ptr [rdi+18h], 7
0x18001bd6b  jbe     short loc_18001BD70
0x18001bd6d  mov     rdi, [rdi]
0x18001bd70  mov     r8, rsi
0x18001bd73  mov     rdx, rdi
0x18001bd76  mov     ecx, 0C007EF6Ch; int
0x18001bd7b  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x18001bd81  mov     rcx, qword ptr [rbp+var_20]
0x18001bd85  test    rcx, rcx
0x18001bd88  jz      short loc_18001BD9A
0x18001bd8a  mov     rdx, [rbp+var_10]
0x18001bd8e  sub     rdx, rcx
0x18001bd91  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18001bd95  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001bd9a  mov     rbx, [rsp+70h+arg_8]
0x18001bda2  add     rsp, 70h
0x18001bda6  pop     r15
0x18001bda8  pop     r14
0x18001bdaa  pop     r13
0x18001bdac  pop     r12
0x18001bdae  pop     rdi
0x18001bdaf  pop     rsi
0x18001bdb0  pop     rbp
0x18001bdb1  retn
```
