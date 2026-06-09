# CWdsMetadata::GetInstancesOfTag(ushort const *,CDynArray<CWdsMetadataEntry const *,CDeallocateNone> *)

- ea: `0x18000ae38`
- end: `0x18000af6f`
- name: `?GetInstancesOfTag@CWdsMetadata@@QEBAKPEBGPEAV?$CDynArray@PEBVCWdsMetadataEntry@@VCDeallocateNone@@@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800042f4`
- `0x18000af78`
- `0x18000b92c`
- `0x18000ca00`
- `0x18000e8f0`

## callees

- `0x18000a7ec`
- `0x18000ae38`
- `0x180014d58`
- `0x1800150b8`
- `0x1800157a4`
- `0x180015c91`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::GetInstancesOfTag(__int64 *a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // edi
  int GroupIndex; // eax
  __int64 v7; // rdx
  __int64 v8; // rax
  unsigned int v9; // esi
  __int64 v10; // rcx
  unsigned int v11; // r15d
  __int64 *v12; // r14
  __int64 v13; // rdx
  unsigned int v14; // ecx
  __int64 v15; // r13
  int v16; // eax
  unsigned int v17; // r12d
  unsigned __int64 v18; // rax
  void *v19; // rax
  void *v20; // rbp

  v5 = 0;
  GroupIndex = CWdsMetadata::FindGroupIndex(a1, a1, a2);
  if ( GroupIndex >= 0 )
  {
    _mm_lfence();
    v7 = GroupIndex;
    v8 = *a1;
    v9 = 0;
    v10 = *(_QWORD *)(v8 + 8 * v7);
    v11 = *(_DWORD *)(v10 + 20);
    v12 = *(__int64 **)(v10 + 8);
    if ( v11 )
    {
      v13 = 32;
      while ( 1 )
      {
        v14 = *(_DWORD *)(a3 + 8);
        v5 = 0;
        v15 = *v12;
        if ( *(_DWORD *)(a3 + 12) != v14 )
          goto LABEL_16;
        v16 = v14 >> 1;
        if ( v14 >> 1 < 0x20 )
          v16 = 32;
        v13 = v14 + v16;
        if ( (unsigned int)v13 < v14 )
        {
          v5 = (unsigned int)v13 < v14 ? 0x216 : 0;
        }
        else
        {
          v17 = v14 + v16;
          v18 = 8LL * (unsigned int)v13;
          if ( !is_mul_ok((unsigned int)v13, 8u) )
            v18 = -1;
          v19 = operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
          v20 = v19;
          if ( !v19 )
          {
            v5 = 8;
            goto LABEL_17;
          }
          memmove_0(v19, *(const void **)a3, 8LL * *(unsigned int *)(a3 + 8));
          operator delete(*(void **)a3);
          *(_QWORD *)a3 = v20;
          *(_DWORD *)(a3 + 8) = v17;
        }
        if ( !v5 )
LABEL_16:
          *(_QWORD *)(*(_QWORD *)a3 + 8LL * (unsigned int)(*(_DWORD *)(a3 + 12))++) = v15;
LABEL_17:
        if ( !(unsigned int)ElValidateWin32(
                              v5,
                              (const char *)v13,
                              "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp",
                              0xE11u) )
        {
          ++v9;
          v13 = 32;
          ++v12;
          if ( v9 < v11 )
            continue;
        }
        return v5;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000ae38  mov     [rsp+arg_0], rbx
0x18000ae3d  mov     [rsp+arg_8], rbp
0x18000ae42  mov     [rsp+arg_10], rsi
0x18000ae47  push    rdi
0x18000ae48  push    r12
0x18000ae4a  push    r13
0x18000ae4c  push    r14
0x18000ae4e  push    r15
0x18000ae50  sub     rsp, 20h
0x18000ae54  mov     rbx, r8
0x18000ae57  mov     rsi, rcx
0x18000ae5a  mov     r8, rdx
0x18000ae5d  xor     edi, edi
0x18000ae5f  mov     rdx, rcx
0x18000ae62  call    ?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z; CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)
0x18000ae67  test    eax, eax
0x18000ae69  js      loc_18000AF50
0x18000ae6f  lfence
0x18000ae72  movsxd  rdx, eax
0x18000ae75  mov     rax, [rsi]
0x18000ae78  xor     esi, esi
0x18000ae7a  mov     rcx, [rax+rdx*8]
0x18000ae7e  mov     r15d, [rcx+14h]
0x18000ae82  mov     r14, [rcx+8]
0x18000ae86  test    r15d, r15d
0x18000ae89  jz      loc_18000AF50
0x18000ae8f  lea     edx, [rdi+20h]
0x18000ae92  mov     ecx, [rbx+8]
0x18000ae95  xor     edi, edi
0x18000ae97  mov     r13, [r14]
0x18000ae9a  cmp     [rbx+0Ch], ecx
0x18000ae9d  jnz     short loc_18000AF19
0x18000ae9f  mov     eax, ecx
0x18000aea1  shr     eax, 1
0x18000aea3  cmp     eax, edx
0x18000aea5  cmovb   eax, edx
0x18000aea8  or      r12d, 0FFFFFFFFh
0x18000aeac  lea     edx, [rcx+rax]
0x18000aeaf  cmp     edx, ecx
0x18000aeb1  cmovnb  r12d, edx
0x18000aeb5  jnb     short loc_18000AEC1
0x18000aeb7  sbb     edi, edi
0x18000aeb9  and     edi, 216h
0x18000aebf  jmp     short loc_18000AF15
0x18000aec1  mov     ecx, r12d
0x18000aec4  mov     eax, 8
0x18000aec9  mul     rcx
0x18000aecc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000aed3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000aeda  cmovo   rax, rcx
0x18000aede  mov     rcx, rax; unsigned __int64
0x18000aee1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000aee6  mov     rbp, rax
0x18000aee9  test    rax, rax
0x18000aeec  jnz     short loc_18000AEF3
0x18000aeee  lea     edi, [rax+8]
0x18000aef1  jmp     short loc_18000AF26
0x18000aef3  mov     r8d, [rbx+8]
0x18000aef7  mov     rcx, rbp; void *
0x18000aefa  mov     rdx, [rbx]; Src
0x18000aefd  shl     r8, 3; Size
0x18000af01  call    memmove_0
0x18000af06  mov     rcx, [rbx]; Block
0x18000af09  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000af0e  mov     [rbx], rbp
0x18000af11  mov     [rbx+8], r12d
0x18000af15  test    edi, edi
0x18000af17  jnz     short loc_18000AF26
0x18000af19  mov     ecx, [rbx+0Ch]
0x18000af1c  mov     rax, [rbx]
0x18000af1f  mov     [rax+rcx*8], r13
0x18000af23  inc     dword ptr [rbx+0Ch]
0x18000af26  mov     r9d, 0E11h; unsigned int
0x18000af2c  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000af33  mov     ecx, edi; unsigned int
0x18000af35  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000af3a  test    eax, eax
0x18000af3c  jnz     short loc_18000AF50
0x18000af3e  inc     esi
0x18000af40  lea     edx, [rax+20h]
0x18000af43  add     r14, 8
0x18000af47  cmp     esi, r15d
0x18000af4a  jb      loc_18000AE92
0x18000af50  mov     rbx, [rsp+48h+arg_0]
0x18000af55  mov     eax, edi
0x18000af57  mov     rbp, [rsp+48h+arg_8]
0x18000af5c  mov     rsi, [rsp+48h+arg_10]
0x18000af61  add     rsp, 20h
0x18000af65  pop     r15
0x18000af67  pop     r14
0x18000af69  pop     r13
0x18000af6b  pop     r12
0x18000af6d  pop     rdi
0x18000af6e  retn
```
