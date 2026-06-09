# SpMapKsrRuns(ulong,_KSR_MEMORY_RUN *,_MDL * *)

- ea: `0x1400343c4`
- end: `0x1400344e9`
- name: `?SpMapKsrRuns@@YAJKPEAU_KSR_MEMORY_RUN@@PEAPEAU_MDL@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(unsigned int, struct _KSR_MEMORY_RUN *, struct _MDL **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400331b8`
- `0x1400341d0`

## callees

- `0x1400268c0`
- `0x1400343c4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400344c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400344c6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400344b0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400344b0`

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
0x1400343c4  push    rbx
0x1400343c6  push    rsi
0x1400343c7  push    rdi
0x1400343c8  push    r14
0x1400343ca  push    r15
0x1400343cc  sub     rsp, 30h
0x1400343d0  xor     edi, edi
0x1400343d2  xor     r9d, r9d
0x1400343d5  mov     [r8], rdi
0x1400343d8  mov     r14, r8
0x1400343db  mov     r15, rdx
0x1400343de  mov     esi, ecx
0x1400343e0  test    ecx, ecx
0x1400343e2  jz      short loc_1400343F6
0x1400343e4  mov     rdx, [r15+r9*8]
0x1400343e8  inc     r9d
0x1400343eb  shr     rdx, 28h
0x1400343ef  add     edi, edx
0x1400343f1  cmp     r9d, esi
0x1400343f4  jb      short loc_1400343E4
0x1400343f6  lea     ecx, ds:30h[rdi*8]; unsigned __int64
0x1400343fd  xor     r9d, r9d; unsigned int
0x140034400  xor     r8d, r8d; unsigned __int8
0x140034403  mov     edx, 58587053h; unsigned int
0x140034408  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14003440d  mov     rbx, rax
0x140034410  test    rax, rax
0x140034413  jnz     short loc_14003441F
0x140034415  mov     eax, 0C000009Ah
0x14003441a  jmp     loc_1400344DC
0x14003441f  mov     qword ptr [rax], 0
0x140034426  lea     r11, [rbx+30h]
0x14003442a  mov     ecx, edi
0x14003442c  lea     eax, [rdi+6]
0x14003442f  shl     rcx, 0Ch
0x140034433  shl     ax, 3
0x140034437  mov     [rbx+28h], ecx
0x14003443a  xor     ecx, ecx
0x14003443c  mov     [rbx+8], ax
0x140034440  mov     qword ptr [rbx+20h], 0
0x140034448  mov     dword ptr [rbx+2Ch], 0
0x14003444f  mov     word ptr [rbx+0Ah], 2
0x140034455  test    esi, esi
0x140034457  jz      short loc_140034494
0x140034459  mov     r9, [r15+rcx*8]
0x14003445d  mov     rax, 0FFFFFFFFFFh
0x140034467  mov     rdx, r9
0x14003446a  xor     r10d, r10d
0x14003446d  and     rdx, rax
0x140034470  shr     r9, 28h
0x140034474  test    r9d, r9d
0x140034477  jz      short loc_14003448E
0x140034479  mov     rax, rdx
0x14003447c  inc     r10d
0x14003447f  mov     [r11], rax
0x140034482  inc     rdx
0x140034485  add     r11, 8
0x140034489  cmp     r10d, r9d
0x14003448c  jb      short loc_140034479
0x14003448e  inc     ecx
0x140034490  cmp     ecx, esi
0x140034492  jb      short loc_140034459
0x140034494  xor     r9d, r9d; RequestedAddress
0x140034497  mov     [rsp+58h+Priority], 40000020h; Priority
0x14003449f  xor     edx, edx; AccessMode
0x1400344a1  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400344a9  mov     rcx, rbx; MemoryDescriptorList
0x1400344ac  lea     r8d, [r9+1]; CacheType
0x1400344b0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400344b7  nop     dword ptr [rax+rax+00h]
0x1400344bc  test    rax, rax
0x1400344bf  jnz     short loc_1400344D7
0x1400344c1  xor     edx, edx; Tag
0x1400344c3  mov     rcx, rbx; P
0x1400344c6  call    cs:__imp_ExFreePoolWithTag
0x1400344cd  nop     dword ptr [rax+rax+00h]
0x1400344d2  jmp     loc_140034415
0x1400344d7  xor     eax, eax
0x1400344d9  mov     [r14], rbx
0x1400344dc  add     rsp, 30h
0x1400344e0  pop     r15
0x1400344e2  pop     r14
0x1400344e4  pop     rdi
0x1400344e5  pop     rsi
0x1400344e6  pop     rbx
0x1400344e7  retn
```
