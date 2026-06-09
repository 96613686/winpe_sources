# LsaLookupClientFindTranslationsBySidInCache

- ea: `0x18001ffd4`
- end: `0x18002022d`
- name: `LsaLookupClientFindTranslationsBySidInCache`
- size: `601`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x18000d710`

## callees

- `0x180013ea8`
- `0x18001fdb4`
- `0x18001fde0`
- `0x18001ff34`
- `0x18001ffd4`
- `0x180020234`
- `0x1800202b8`
- `0x180020400`
- `0x180020480`
- `0x1800204c8`
- `0x18004f902`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180020049`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180020049`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800201ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800201ce`

## pseudocode

```c
__int64 __fastcall LsaLookupClientFindTranslationsBySidInCache(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        const void **a4,
        _QWORD *a5,
        unsigned int *a6,
        _BYTE *a7)
{
  __int64 v10; // rsi
  int v11; // ebx
  __int64 i; // r12
  void *v13; // rcx
  __int64 CacheEntryBySid; // rax
  __int64 v15; // rbp
  unsigned int v16; // ebx
  unsigned int v17; // esi
  void *Memory; // rax
  const void *v19; // rsi
  void *v20; // rax
  char *v21; // rdx
  int v22; // ecx
  __int64 v23; // rsi
  unsigned int v25; // [rsp+60h] [rbp+8h]
  void *v27; // [rsp+80h] [rbp+28h]
  _QWORD *v28; // [rsp+88h] [rbp+30h]
  unsigned __int16 v29; // [rsp+88h] [rbp+30h]

  v10 = a2;
  *a3 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  *a4 = 0;
  v11 = LsaLookupClientInitializeSidCache();
  if ( v11 >= 0 )
  {
    AcquireSRWLockShared(&LsaLookupClientSidCacheLock);
    for ( i = 0; !(_DWORD)i; i = 1 )
    {
      v13 = *(void **)(v10 + 8 * i);
      if ( v13 )
      {
        CacheEntryBySid = LsaLookupClientFindCacheEntryBySid(v13);
        v15 = CacheEntryBySid;
        if ( CacheEntryBySid )
        {
          if ( *(_BYTE *)(CacheEntryBySid + 88) )
          {
            v16 = *a6;
            v25 = *a6;
            LsaLookupClientInitializeReferencedDomains(a3);
            v17 = v16 + 1;
            v28 = (_QWORD *)(*a3 + 8LL);
            v11 = LsaLookupClientGrowTranslatedSidsList(v28, v16 + 1);
            if ( v11 < 0 )
              break;
            v11 = 0;
            if ( v17 == 1 )
            {
              *a4 = (const void *)LsaLookupClientAllocateMemory(32);
            }
            else
            {
              Memory = (void *)LsaLookupClientAllocateMemory(32 * v17);
              v19 = Memory;
              if ( Memory )
              {
                memcpy_0(Memory, *a4, 32LL * v25);
                LsaLookupClientFreeMemory(a4);
                *a4 = v19;
              }
              else
              {
                v11 = -1073741801;
              }
            }
            if ( !*a4 )
              goto LABEL_19;
            if ( v11 < 0 )
              break;
            v11 = LsaLookupClientFillDomainInfoFromCacheEntry(v15, (unsigned __int16 *)(*v28 + 24LL * v25));
            if ( v11 < 0 )
              break;
            v29 = *(_WORD *)(v15 + 58);
            v20 = (void *)LsaLookupClientAllocateMemory(v29);
            v27 = v20;
            if ( !v20 )
            {
LABEL_19:
              v11 = -1073741801;
              break;
            }
            memcpy_0(v20, *(const void **)(v15 + 64), v29);
            v21 = (char *)*a4;
            v22 = *(_DWORD *)(v15 + 16);
            ++*a6;
            v23 = 32LL * v25;
            *(_DWORD *)&v21[v23 + 24] = v25;
            *(_DWORD *)&v21[v23] = v22;
            *(_WORD *)&v21[v23 + 8] = *(_WORD *)(v15 + 56);
            *(_WORD *)&v21[v23 + 10] = v29;
            *(_QWORD *)&v21[v23 + 16] = v27;
            v10 = a2;
            ++*(_DWORD *)*a3;
          }
        }
      }
    }
    ReleaseSRWLockShared(&LsaLookupClientSidCacheLock);
    if ( *a6 == 1 )
      *a7 = 1;
  }
  if ( *a7 )
  {
    if ( v11 >= 0 )
      return (unsigned int)v11;
  }
  else
  {
    v11 = -1073741823;
  }
  if ( *a3 )
  {
    LsaLookupClientFreeTranslatedNames(*(unsigned int *)*a3, a4);
    LsaLookupClientFreeReferencedDomains(a3);
  }
  *a6 = 0;
  *a7 = 0;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001ffd4  mov     [rsp+arg_10], rbx
0x18001ffd9  mov     [rsp+arg_8], rdx
0x18001ffde  mov     [rsp+arg_0], ecx
0x18001ffe2  push    rbp
0x18001ffe3  push    rsi
0x18001ffe4  push    rdi
0x18001ffe5  push    r12
0x18001ffe7  push    r13
0x18001ffe9  push    r14
0x18001ffeb  push    r15
0x18001ffed  sub     rsp, 20h
0x18001fff1  mov     rax, [rsp+58h+arg_20]
0x18001fff9  mov     rdi, r9
0x18001fffc  mov     r13, [rsp+58h+arg_28]
0x180020004  mov     r15, r8
0x180020007  mov     r14, [rsp+58h+arg_30]
0x18002000f  mov     rsi, rdx
0x180020012  mov     qword ptr [r8], 0
0x180020019  mov     qword ptr [rax], 0
0x180020020  mov     dword ptr [r13+0], 0
0x180020028  mov     byte ptr [r14], 0
0x18002002c  mov     qword ptr [r9], 0
0x180020033  call    LsaLookupClientInitializeSidCache
0x180020038  mov     ebx, eax
0x18002003a  test    eax, eax
0x18002003c  js      loc_1800201DF
0x180020042  lea     rcx, LsaLookupClientSidCacheLock; SRWLock
0x180020049  call    cs:__imp_AcquireSRWLockShared
0x18002004f  xor     r12d, r12d
0x180020052  cmp     r12d, 1
0x180020056  jnb     loc_1800201C7
0x18002005c  mov     rcx, [rsi+r12*8]; Sid2
0x180020060  test    rcx, rcx
0x180020063  jz      loc_1800201BA
0x180020069  call    LsaLookupClientFindCacheEntryBySid
0x18002006e  mov     rbp, rax
0x180020071  test    rax, rax
0x180020074  jz      loc_1800201BA
0x18002007a  cmp     byte ptr [rax+58h], 0
0x18002007e  jz      loc_1800201BA
0x180020084  mov     ebx, [r13+0]
0x180020088  mov     rcx, r15
0x18002008b  mov     [rsp+58h+arg_0], ebx
0x18002008f  call    LsaLookupClientInitializeReferencedDomains
0x180020094  mov     rax, [r15]
0x180020097  lea     esi, [rbx+1]
0x18002009a  add     rax, 8
0x18002009e  mov     edx, esi
0x1800200a0  mov     rcx, rax
0x1800200a3  mov     [rsp+58h+arg_28], rax
0x1800200ab  call    LsaLookupClientGrowTranslatedSidsList
0x1800200b0  mov     ebx, eax
0x1800200b2  test    eax, eax
0x1800200b4  js      loc_1800201C7
0x1800200ba  xor     ebx, ebx
0x1800200bc  cmp     esi, 1
0x1800200bf  jnz     short loc_1800200CE
0x1800200c1  lea     ecx, [rbx+20h]
0x1800200c4  call    LsaLookupClientAllocateMemory
0x1800200c9  mov     [rdi], rax
0x1800200cc  jmp     short loc_180020106
0x1800200ce  shl     esi, 5
0x1800200d1  mov     ecx, esi
0x1800200d3  call    LsaLookupClientAllocateMemory
0x1800200d8  mov     rsi, rax
0x1800200db  test    rax, rax
0x1800200de  jnz     short loc_1800200E7
0x1800200e0  mov     ebx, 0C0000017h
0x1800200e5  jmp     short loc_180020106
0x1800200e7  mov     r8d, [rsp+58h+arg_0]
0x1800200ec  mov     rcx, rsi; void *
0x1800200ef  mov     rdx, [rdi]; Src
0x1800200f2  shl     r8, 5; Size
0x1800200f6  call    memcpy_0
0x1800200fb  mov     rcx, rdi
0x1800200fe  call    LsaLookupClientFreeMemory
0x180020103  mov     [rdi], rsi
0x180020106  cmp     qword ptr [rdi], 0
0x18002010a  jz      loc_1800201C2
0x180020110  test    ebx, ebx
0x180020112  js      loc_1800201C7
0x180020118  mov     rax, [rsp+58h+arg_28]
0x180020120  mov     esi, [rsp+58h+arg_0]
0x180020124  mov     rax, [rax]
0x180020127  lea     rcx, [rsi+rsi*2]
0x18002012b  lea     rdx, [rax+rcx*8]
0x18002012f  mov     rcx, rbp
0x180020132  call    LsaLookupClientFillDomainInfoFromCacheEntry
0x180020137  mov     ebx, eax
0x180020139  test    eax, eax
0x18002013b  js      loc_1800201C7
0x180020141  movzx   eax, word ptr [rbp+3Ah]
0x180020145  mov     ecx, eax
0x180020147  mov     dword ptr [rsp+58h+arg_28], eax
0x18002014e  call    LsaLookupClientAllocateMemory
0x180020153  mov     [rsp+58h+arg_20], rax
0x18002015b  test    rax, rax
0x18002015e  jz      short loc_1800201C2
0x180020160  movzx   r8d, word ptr [rsp+58h+arg_28]; Size
0x180020169  mov     rcx, rax; void *
0x18002016c  mov     rdx, [rbp+40h]; Src
0x180020170  call    memcpy_0
0x180020175  mov     rdx, [rdi]
0x180020178  mov     ecx, [rbp+10h]
0x18002017b  mov     eax, [rsp+58h+arg_0]
0x18002017f  inc     dword ptr [r13+0]
0x180020183  shl     rsi, 5
0x180020187  mov     [rsi+rdx+18h], eax
0x18002018b  mov     [rsi+rdx], ecx
0x18002018e  movzx   eax, word ptr [rbp+38h]
0x180020192  mov     [rsi+rdx+8], ax
0x180020197  mov     eax, dword ptr [rsp+58h+arg_28]
0x18002019e  mov     [rsi+rdx+0Ah], ax
0x1800201a3  mov     rax, [rsp+58h+arg_20]
0x1800201ab  mov     [rsi+rdx+10h], rax
0x1800201b0  mov     rax, [r15]
0x1800201b3  mov     rsi, [rsp+58h+arg_8]
0x1800201b8  inc     dword ptr [rax]
0x1800201ba  inc     r12d
0x1800201bd  jmp     loc_180020052
0x1800201c2  mov     ebx, 0C0000017h
0x1800201c7  lea     rcx, LsaLookupClientSidCacheLock; SRWLock
0x1800201ce  call    cs:__imp_ReleaseSRWLockShared
0x1800201d4  cmp     dword ptr [r13+0], 1
0x1800201d9  jnz     short loc_1800201DF
0x1800201db  mov     byte ptr [r14], 1
0x1800201df  cmp     byte ptr [r14], 0
0x1800201e3  jnz     short loc_1800201EC
0x1800201e5  mov     ebx, 0C0000001h
0x1800201ea  jmp     short loc_1800201F0
0x1800201ec  test    ebx, ebx
0x1800201ee  jns     short loc_180020216
0x1800201f0  mov     rcx, [r15]
0x1800201f3  test    rcx, rcx
0x1800201f6  jz      short loc_18002020A
0x1800201f8  mov     ecx, [rcx]
0x1800201fa  mov     rdx, rdi
0x1800201fd  call    LsaLookupClientFreeTranslatedNames
0x180020202  mov     rcx, r15
0x180020205  call    LsaLookupClientFreeReferencedDomains
0x18002020a  mov     dword ptr [r13+0], 0
0x180020212  mov     byte ptr [r14], 0
0x180020216  mov     eax, ebx
0x180020218  mov     rbx, [rsp+58h+arg_10]
0x18002021d  add     rsp, 20h
0x180020221  pop     r15
0x180020223  pop     r14
0x180020225  pop     r13
0x180020227  pop     r12
0x180020229  pop     rdi
0x18002022a  pop     rsi
0x18002022b  pop     rbp
0x18002022c  retn
```
