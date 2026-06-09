# CWdsMetadata::GetInstancesOfTag(ushort const *,CDynArray<CWdsMetadataEntry const *,CDeallocateNone> *)

- ea: `0x180009770`
- end: `0x18000989e`
- name: `?GetInstancesOfTag@CWdsMetadata@@QEBAKPEBGPEAV?$CDynArray@PEBVCWdsMetadataEntry@@VCDeallocateNone@@@@@Z`
- size: `302`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000906c`
- `0x18000b6d4`
- `0x18000bc94`

## callees

- `0x1800015d4`
- `0x180001934`
- `0x180009684`
- `0x180009770`
- `0x18000c274`
- `0x18000cc1c`

## import_xrefs

- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000983d`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000983d`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::GetInstancesOfTag(__int64 *a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // edi
  int GroupIndex; // eax
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rax
  unsigned int v10; // esi
  __int64 v11; // rcx
  unsigned int v12; // ebp
  __int64 *v13; // r14
  __int64 v14; // rdx
  unsigned int v15; // ecx
  __int64 v16; // r13
  int v17; // eax
  unsigned int v18; // r15d
  unsigned __int64 v19; // rax
  void *v20; // rax
  void *v21; // r12

  v5 = 0;
  GroupIndex = CWdsMetadata::FindGroupIndex(a1, a1, a2);
  if ( GroupIndex >= 0 )
  {
    _mm_lfence();
    v8 = GroupIndex;
    v9 = *a1;
    v10 = 0;
    v11 = *(_QWORD *)(v9 + 8 * v8);
    v12 = *(_DWORD *)(v11 + 20);
    v13 = *(__int64 **)(v11 + 8);
    if ( v12 )
    {
      v14 = 32;
      while ( 1 )
      {
        v15 = *(_DWORD *)(a3 + 8);
        v5 = 0;
        v16 = *v13;
        if ( *(_DWORD *)(a3 + 12) == v15 )
        {
          v17 = v15 >> 1;
          if ( v15 >> 1 < 0x20 )
            v17 = 32;
          v18 = v15 + v17;
          if ( v15 + v17 < v15 )
          {
            v5 = WIN32_FROM_HRESULT(-2147024362);
            if ( v5 )
              goto LABEL_15;
          }
          else
          {
            v19 = 8LL * v18;
            if ( !is_mul_ok(v18, 8u) )
              v19 = -1;
            v20 = operator new[](v19, (const struct std::nothrow_t *)&std::nothrow);
            v21 = v20;
            if ( !v20 )
            {
              v5 = 8;
              goto LABEL_15;
            }
            memmove_0(v20, *(const void **)a3, 8LL * *(unsigned int *)(a3 + 8));
            operator delete(*(void **)a3);
            *(_QWORD *)a3 = v21;
            *(_DWORD *)(a3 + 8) = v18;
          }
        }
        *(_QWORD *)(*(_QWORD *)a3 + 8LL * (unsigned int)(*(_DWORD *)(a3 + 12))++) = v16;
LABEL_15:
        if ( !(unsigned int)ElValidateWin32_1(v5, v14, v7, 0xE11u) )
        {
          ++v10;
          v14 = 32;
          ++v13;
          if ( v10 < v12 )
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
0x180009770  mov     [rsp+arg_8], rbx
0x180009775  mov     [rsp+arg_10], rbp
0x18000977a  mov     [rsp+arg_18], rsi
0x18000977f  push    rdi
0x180009780  push    r12
0x180009782  push    r13
0x180009784  push    r14
0x180009786  push    r15
0x180009788  sub     rsp, 20h
0x18000978c  mov     rbx, r8
0x18000978f  mov     rsi, rcx
0x180009792  mov     r8, rdx
0x180009795  xor     edi, edi
0x180009797  mov     rdx, rcx
0x18000979a  call    ?FindGroupIndex@CWdsMetadata@@AEBAHPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBG@Z; CWdsMetadata::FindGroupIndex(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *)
0x18000979f  test    eax, eax
0x1800097a1  js      loc_18000987E
0x1800097a7  lfence
0x1800097aa  movsxd  rdx, eax
0x1800097ad  mov     rax, [rsi]
0x1800097b0  xor     esi, esi
0x1800097b2  mov     rcx, [rax+rdx*8]
0x1800097b6  mov     ebp, [rcx+14h]
0x1800097b9  mov     r14, [rcx+8]
0x1800097bd  test    ebp, ebp
0x1800097bf  jz      loc_18000987E
0x1800097c5  lea     edx, [rdi+20h]
0x1800097c8  mov     ecx, [rbx+8]
0x1800097cb  xor     edi, edi
0x1800097cd  mov     r13, [r14]
0x1800097d0  cmp     [rbx+0Ch], ecx
0x1800097d3  jnz     short loc_18000984F
0x1800097d5  mov     eax, ecx
0x1800097d7  shr     eax, 1
0x1800097d9  cmp     eax, edx
0x1800097db  cmovb   eax, edx
0x1800097de  lea     r15d, [rcx+rax]
0x1800097e2  cmp     r15d, ecx
0x1800097e5  jb      short loc_180009838
0x1800097e7  mov     ecx, r15d
0x1800097ea  lea     eax, [rdi+8]
0x1800097ed  mul     rcx
0x1800097f0  lea     rcx, [rdi-1]
0x1800097f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800097fb  cmovb   rax, rcx
0x1800097ff  mov     rcx, rax; unsigned __int64
0x180009802  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009807  mov     r12, rax
0x18000980a  test    rax, rax
0x18000980d  jnz     short loc_180009814
0x18000980f  lea     edi, [rax+8]
0x180009812  jmp     short loc_18000985C
0x180009814  mov     r8d, [rbx+8]
0x180009818  mov     rcx, r12; void *
0x18000981b  mov     rdx, [rbx]; Src
0x18000981e  shl     r8, 3; Size
0x180009822  call    memmove_0
0x180009827  mov     rcx, [rbx]; Block
0x18000982a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000982f  mov     [rbx], r12
0x180009832  mov     [rbx+8], r15d
0x180009836  jmp     short loc_18000984F
0x180009838  mov     ecx, 80070216h
0x18000983d  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180009844  nop     dword ptr [rax+rax+00h]
0x180009849  mov     edi, eax
0x18000984b  test    eax, eax
0x18000984d  jnz     short loc_18000985C
0x18000984f  mov     ecx, [rbx+0Ch]
0x180009852  mov     rax, [rbx]
0x180009855  mov     [rax+rcx*8], r13
0x180009859  inc     dword ptr [rbx+0Ch]
0x18000985c  mov     r9d, 0E11h
0x180009862  mov     ecx, edi
0x180009864  call    ElValidateWin32_1
0x180009869  test    eax, eax
0x18000986b  jnz     short loc_18000987E
0x18000986d  inc     esi
0x18000986f  lea     edx, [rax+20h]
0x180009872  add     r14, 8
0x180009876  cmp     esi, ebp
0x180009878  jb      loc_1800097C8
0x18000987e  mov     rbx, [rsp+48h+arg_8]
0x180009883  mov     eax, edi
0x180009885  mov     rbp, [rsp+48h+arg_10]
0x18000988a  mov     rsi, [rsp+48h+arg_18]
0x18000988f  add     rsp, 20h
0x180009893  pop     r15
0x180009895  pop     r14
0x180009897  pop     r13
0x180009899  pop     r12
0x18000989b  pop     rdi
0x18000989c  retn
```
