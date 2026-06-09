# SpMapKsrRuns(ulong,_KSR_MEMORY_RUN *,_MDL * *)

- ea: `0x140034304`
- end: `0x140034429`
- name: `?SpMapKsrRuns@@YAJKPEAU_KSR_MEMORY_RUN@@PEAPEAU_MDL@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(unsigned int, struct _KSR_MEMORY_RUN *, struct _MDL **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140033108`
- `0x140034110`

## callees

- `0x1400268c0`
- `0x140034304`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140034406`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034406`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400343f0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400343f0`

## pseudocode

```c
__int64 __fastcall SpMapKsrRuns(unsigned int a1, struct _KSR_MEMORY_RUN *a2, struct _MDL **a3)
{
  int v3; // edi
  __int64 v4; // r9
  unsigned __int64 v8; // rdx
  struct _MDL *v9; // rax
  struct _MDL *v10; // rbx
  __int64 result; // rax
  struct _MDL *v12; // r11
  __int64 v13; // rcx
  unsigned int v14; // r10d
  __int64 v15; // rdx
  __int64 v16; // r9

  v3 = 0;
  v4 = 0;
  for ( *a3 = 0; (unsigned int)v4 < a1; v3 += v8 >> 40 )
  {
    v8 = *((_QWORD *)a2 + v4);
    v4 = (unsigned int)(v4 + 1);
  }
  v9 = (struct _MDL *)SC_ENV::Allocate((unsigned int)(8 * v3 + 48), 0x58587053u, 0, 0);
  v10 = v9;
  if ( !v9 )
    return 3221225626LL;
  v9->Next = 0;
  v12 = v9 + 1;
  v9->ByteCount = v3 << 12;
  v13 = 0;
  v9->Size = 8 * (v3 + 6);
  v9->StartVa = 0;
  v9->ByteOffset = 0;
  for ( v9->MdlFlags = 2; (unsigned int)v13 < a1; v13 = (unsigned int)(v13 + 1) )
  {
    v14 = 0;
    v15 = *((_QWORD *)a2 + v13) & 0xFFFFFFFFFFLL;
    v16 = *((_QWORD *)a2 + v13) >> 40;
    if ( (_DWORD)v16 )
    {
      do
      {
        ++v14;
        v12->Next = (struct _MDL *)v15++;
        v12 = (struct _MDL *)((char *)v12 + 8);
      }
      while ( v14 < (unsigned int)v16 );
    }
  }
  if ( !MmMapLockedPagesSpecifyCache(v9, 0, MmCached, 0, 0, 0x40000020u) )
  {
    ExFreePoolWithTag(v10, 0);
    return 3221225626LL;
  }
  result = 0;
  *a3 = v10;
  return result;
}

```

## disassembly

```asm
0x140034304  push    rbx
0x140034306  push    rsi
0x140034307  push    rdi
0x140034308  push    r14
0x14003430a  push    r15
0x14003430c  sub     rsp, 30h
0x140034310  xor     edi, edi
0x140034312  xor     r9d, r9d
0x140034315  mov     [r8], rdi
0x140034318  mov     r14, r8
0x14003431b  mov     r15, rdx
0x14003431e  mov     esi, ecx
0x140034320  test    ecx, ecx
0x140034322  jz      short loc_140034336
0x140034324  mov     rdx, [r15+r9*8]
0x140034328  inc     r9d
0x14003432b  shr     rdx, 28h
0x14003432f  add     edi, edx
0x140034331  cmp     r9d, esi
0x140034334  jb      short loc_140034324
0x140034336  lea     ecx, ds:30h[rdi*8]; unsigned __int64
0x14003433d  xor     r9d, r9d; unsigned int
0x140034340  xor     r8d, r8d; unsigned __int8
0x140034343  mov     edx, 58587053h; unsigned int
0x140034348  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14003434d  mov     rbx, rax
0x140034350  test    rax, rax
0x140034353  jnz     short loc_14003435F
0x140034355  mov     eax, 0C000009Ah
0x14003435a  jmp     loc_14003441C
0x14003435f  mov     qword ptr [rax], 0
0x140034366  lea     r11, [rbx+30h]
0x14003436a  mov     ecx, edi
0x14003436c  lea     eax, [rdi+6]
0x14003436f  shl     rcx, 0Ch
0x140034373  shl     ax, 3
0x140034377  mov     [rbx+28h], ecx
0x14003437a  xor     ecx, ecx
0x14003437c  mov     [rbx+8], ax
0x140034380  mov     qword ptr [rbx+20h], 0
0x140034388  mov     dword ptr [rbx+2Ch], 0
0x14003438f  mov     word ptr [rbx+0Ah], 2
0x140034395  test    esi, esi
0x140034397  jz      short loc_1400343D4
0x140034399  mov     r9, [r15+rcx*8]
0x14003439d  mov     rax, 0FFFFFFFFFFh
0x1400343a7  mov     rdx, r9
0x1400343aa  xor     r10d, r10d
0x1400343ad  and     rdx, rax
0x1400343b0  shr     r9, 28h
0x1400343b4  test    r9d, r9d
0x1400343b7  jz      short loc_1400343CE
0x1400343b9  mov     rax, rdx
0x1400343bc  inc     r10d
0x1400343bf  mov     [r11], rax
0x1400343c2  inc     rdx
0x1400343c5  add     r11, 8
0x1400343c9  cmp     r10d, r9d
0x1400343cc  jb      short loc_1400343B9
0x1400343ce  inc     ecx
0x1400343d0  cmp     ecx, esi
0x1400343d2  jb      short loc_140034399
0x1400343d4  xor     r9d, r9d; RequestedAddress
0x1400343d7  mov     [rsp+58h+Priority], 40000020h; Priority
0x1400343df  xor     edx, edx; AccessMode
0x1400343e1  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400343e9  mov     rcx, rbx; MemoryDescriptorList
0x1400343ec  lea     r8d, [r9+1]; CacheType
0x1400343f0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400343f7  nop     dword ptr [rax+rax+00h]
0x1400343fc  test    rax, rax
0x1400343ff  jnz     short loc_140034417
0x140034401  xor     edx, edx; Tag
0x140034403  mov     rcx, rbx; P
0x140034406  call    cs:__imp_ExFreePoolWithTag
0x14003440d  nop     dword ptr [rax+rax+00h]
0x140034412  jmp     loc_140034355
0x140034417  xor     eax, eax
0x140034419  mov     [r14], rbx
0x14003441c  add     rsp, 30h
0x140034420  pop     r15
0x140034422  pop     r14
0x140034424  pop     rdi
0x140034425  pop     rsi
0x140034426  pop     rbx
0x140034427  retn
```
