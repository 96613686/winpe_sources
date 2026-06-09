# UdfLookupInitialDirEntry

- ea: `0x140041110`
- end: `0x1400413e2`
- name: `UdfLookupInitialDirEntry`
- size: `722`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, _QWORD *, char, unsigned int)`
- caller_count: `14`
- callee_count: `7`
- tags: ``

## callers

- `0x140004514`
- `0x140016478`
- `0x1400168d8`
- `0x1400177ac`
- `0x14003269c`
- `0x1400333bc`
- `0x140033548`
- `0x140034450`
- `0x14003803c`
- `0x140039d14`
- `0x1400407cc`
- `0x140040820`
- `0x1400413f0`
- `0x140041750`

## callees

- `0x140004340`
- `0x14000b938`
- `0x14001c080`
- `0x140041110`
- `0x1400425b0`
- `0x14004f8ac`
- `0x1400591e0`

## import_xrefs

- `ntoskrnl!CcMapData` at `0x14004126a`
- `ntoskrnl!CcMapData` at `0x14004126a`
- `ntoskrnl!CcUnpinData` at `0x140041164`
- `ntoskrnl!CcUnpinData` at `0x140041225`
- `ntoskrnl!CcUnpinData` at `0x140041164`
- `ntoskrnl!CcUnpinData` at `0x140041225`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041145`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041145`
- `ntoskrnl!ExRaiseStatus` at `0x1400412fa`
- `ntoskrnl!ExRaiseStatus` at `0x1400412fa`
- `ntoskrnl!CcPinRead` at `0x140041332`
- `ntoskrnl!CcPinRead` at `0x140041332`

## pseudocode

```c
__int64 __fastcall UdfLookupInitialDirEntry(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4, char a5, unsigned int a6)
{
  void *v10; // rcx
  PVOID *v11; // r15
  void *v12; // rcx
  _QWORD *v13; // rsi
  unsigned int v14; // r13d
  __int64 v15; // rcx
  __int64 v16; // rdx
  union _LARGE_INTEGER *v17; // rcx
  unsigned __int8 v18; // cf
  ULONG *v19; // rdi
  union _LARGE_INTEGER v20; // rdx
  ULONG v21; // r8d
  struct _FILE_OBJECT *v22; // rcx
  unsigned int v23; // eax
  _DWORD *v25; // r9
  __int64 v26; // r8
  PVOID *Bcb; // [rsp+20h] [rbp-68h]
  PVOID *Bcba; // [rsp+20h] [rbp-68h]
  union _LARGE_INTEGER FileOffset; // [rsp+98h] [rbp+10h] BYREF

  if ( (a3[7] & 0x40) != 0 )
  {
    v10 = (void *)a3[16];
    if ( v10 )
    {
      ExFreePoolWithTag(v10, 0);
      a3[16] = 0;
    }
  }
  v11 = (PVOID *)(a3 + 1);
  v12 = (void *)a3[1];
  if ( v12 )
  {
    CcUnpinData(v12);
    *v11 = 0;
  }
  if ( (a3[7] & 4) != 0 )
    UdfFreePool(a3 + 4);
  memset(a3, 0, 0x98u);
  v13 = (_QWORD *)(a1 + 16);
  if ( !*(_QWORD *)(a2 + 504) )
    UdfCreateInternalStream(a1, *v13, a2, 0);
  v14 = a6;
  if ( a5 && !a6 && ((v25 = (_DWORD *)*v13, *(_QWORD *)(*v13 + 352LL)) || (v25[12] & 0x20000000) != 0) )
  {
    if ( a4 )
      v26 = v25[19] & (unsigned int)(*a4 >> v25[18]);
    else
      v26 = 0;
    UdfSeqCacheReserveFileRegion(a1, a2, v26, (unsigned int)v25[20], 0, 0, (*(_DWORD *)(a1 + 28) & 0x10) != 0);
    v15 = a1 + 16;
  }
  else
  {
    v15 = a1 + 16;
  }
  if ( _bittest((const signed __int32 *)(a2 + 212), 0x1Bu) )
    v16 = *(unsigned int *)(*(_QWORD *)v15 + 68LL);
  else
    v16 = 4096;
  v17 = (union _LARGE_INTEGER *)(a3 + 2);
  if ( a4 )
  {
    *((_DWORD *)a3 + 14) = 3;
    a3[6] = *a4;
    v17->QuadPart = *a4 & -v16;
    *((_DWORD *)a3 + 7) = *(_DWORD *)a4 & (v16 - 1);
  }
  v18 = _bittest((const signed __int32 *)(a2 + 212), 0x1Bu);
  FileOffset.QuadPart = 0;
  v19 = (ULONG *)(a3 + 3);
  if ( v18 )
  {
    UdfFindDataInMetadataStream(a1, a2, a3 + 2, &FileOffset, a3 + 3);
    if ( FileOffset.QuadPart + *v19 > *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 320LL) + 24LL) )
    {
      *(_DWORD *)(a1 + 24) = -1073741566;
      ExRaiseStatus(-1073741566);
    }
  }
  else
  {
    v20 = *v17;
    *v19 = 4096;
    if ( v20.QuadPart + 4096 > *(_QWORD *)(a2 + 32) )
      *v19 = *(_DWORD *)(a2 + 32) - v20.LowPart;
    FileOffset = v20;
  }
  if ( *v11 )
  {
    CcUnpinData(*v11);
    *v11 = 0;
  }
  v21 = *v19;
  v22 = *(struct _FILE_OBJECT **)(a2 + 504);
  Bcb = (PVOID *)(a3 + 1);
  if ( (*(_DWORD *)(*v13 + 48LL) & 0x4000) != 0 )
  {
    CcMapData(v22, &FileOffset, v21, 1u, Bcb, (PVOID *)a3);
    v23 = a3[7] & 0xFFFFFFEF;
  }
  else
  {
    CcPinRead(v22, &FileOffset, v21, 1u, Bcb, (PVOID *)a3);
    v23 = *((_DWORD *)a3 + 14) | 0x10;
  }
  *((_DWORD *)a3 + 14) = v23 & 0xFFFFFFDF;
  a3[4] = *a3 + *((unsigned int *)a3 + 7);
  return UdfLookupDirEntryPostProcessing(a1, a2, (__int64)a3, a4 != 0, (size_t)Bcba, v14);
}

```

## disassembly

```asm
0x140041110  push    rbx
0x140041112  push    rbp
0x140041113  push    rsi
0x140041114  push    rdi
0x140041115  push    r12
0x140041117  push    r13
0x140041119  push    r14
0x14004111b  push    r15
0x14004111d  sub     rsp, 48h
0x140041121  mov     eax, [r8+38h]
0x140041125  xor     edi, edi
0x140041127  mov     r12, r9
0x14004112a  mov     rbx, r8
0x14004112d  mov     r14, rdx
0x140041130  mov     rbp, rcx
0x140041133  test    al, 40h
0x140041135  jz      short loc_140041158
0x140041137  mov     rcx, [r8+80h]; P
0x14004113e  test    rcx, rcx
0x140041141  jz      short loc_140041158
0x140041143  xor     edx, edx; Tag
0x140041145  call    cs:__imp_ExFreePoolWithTag
0x14004114c  nop     dword ptr [rax+rax+00h]
0x140041151  mov     [rbx+80h], rdi
0x140041158  lea     r15, [rbx+8]
0x14004115c  mov     rcx, [r15]; Bcb
0x14004115f  test    rcx, rcx
0x140041162  jz      short loc_140041173
0x140041164  call    cs:__imp_CcUnpinData
0x14004116b  nop     dword ptr [rax+rax+00h]
0x140041170  mov     [r15], rdi
0x140041173  mov     eax, [rbx+38h]
0x140041176  test    al, 4
0x140041178  jnz     loc_140041395
0x14004117e  xor     edx, edx; Val
0x140041180  mov     r8d, 98h; Size
0x140041186  mov     rcx, rbx; void *
0x140041189  call    memset
0x14004118e  lea     rsi, [rbp+10h]
0x140041192  cmp     [r14+1F8h], rdi
0x140041199  jz      loc_1400413A3
0x14004119f  mov     r13d, [rsp+88h+arg_28]
0x1400411a7  cmp     [rsp+88h+arg_20], dil
0x1400411af  jnz     loc_140041349
0x1400411b5  mov     rcx, rsi
0x1400411b8  bt      dword ptr [r14+0D4h], 1Bh
0x1400411c1  mov     r8d, 1000h
0x1400411c7  jb      loc_14004138A
0x1400411cd  mov     edx, r8d
0x1400411d0  lea     rcx, [rbx+10h]
0x1400411d4  test    r12, r12
0x1400411d7  jnz     loc_140041307
0x1400411dd  bt      dword ptr [r14+0D4h], 1Bh
0x1400411e6  mov     qword ptr [rsp+88h+FileOffset], rdi
0x1400411ee  lea     rdi, [rbx+18h]
0x1400411f2  jb      loc_1400412B8
0x1400411f8  mov     rdx, [rcx]
0x1400411fb  mov     [rdi], r8d
0x1400411fe  lea     rax, [rdx+1000h]
0x140041205  cmp     rax, [r14+20h]
0x140041209  jle     short loc_140041215
0x14004120b  mov     ecx, [r14+20h]
0x14004120f  mov     eax, edx
0x140041211  sub     ecx, eax
0x140041213  mov     [rdi], ecx
0x140041215  mov     qword ptr [rsp+88h+FileOffset], rdx
0x14004121d  mov     rcx, [r15]; Bcb
0x140041220  test    rcx, rcx
0x140041223  jz      short loc_140041238
0x140041225  call    cs:__imp_CcUnpinData
0x14004122c  nop     dword ptr [rax+rax+00h]
0x140041231  mov     qword ptr [r15], 0
0x140041238  mov     rax, [rsi]
0x14004123b  lea     rdx, [rsp+88h+FileOffset]; FileOffset
0x140041243  mov     r8d, [rdi]; Length
0x140041246  mov     r9d, 1; Flags
0x14004124c  mov     rcx, [r14+1F8h]; FileObject
0x140041253  mov     [rsp+88h+Buffer], rbx; Buffer
0x140041258  test    dword ptr [rax+30h], 4000h
0x14004125f  mov     [rsp+88h+Bcb], r15; Size
0x140041264  jz      loc_140041332
0x14004126a  call    cs:__imp_CcMapData
0x140041271  nop     dword ptr [rax+rax+00h]
0x140041276  mov     eax, [rbx+38h]
0x140041279  and     eax, 0FFFFFFEFh
0x14004127c  and     eax, 0FFFFFFDFh
0x14004127f  mov     dword ptr [rsp+88h+Buffer], r13d; int
0x140041284  mov     [rbx+38h], eax
0x140041287  mov     r8, rbx; int
0x14004128a  mov     eax, [rbx+1Ch]
0x14004128d  mov     rdx, r14; int
0x140041290  add     rax, [rbx]
0x140041293  mov     rcx, rbp; int
0x140041296  test    r12, r12
0x140041299  mov     [rbx+20h], rax
0x14004129d  setnz   r9b; int
0x1400412a1  call    UdfLookupDirEntryPostProcessing
0x1400412a6  add     rsp, 48h
0x1400412aa  pop     r15
0x1400412ac  pop     r14
0x1400412ae  pop     r13
0x1400412b0  pop     r12
0x1400412b2  pop     rdi
0x1400412b3  pop     rsi
0x1400412b4  pop     rbp
0x1400412b5  pop     rbx
0x1400412b6  retn
0x1400412b8  mov     r8, rcx
0x1400412bb  mov     [rsp+88h+Bcb], rdi
0x1400412c0  mov     rcx, rbp
0x1400412c3  lea     r9, [rsp+88h+FileOffset]
0x1400412cb  mov     rdx, r14
0x1400412ce  call    UdfFindDataInMetadataStream
0x1400412d3  mov     rax, [rbp+10h]
0x1400412d7  mov     edx, [rdi]
0x1400412d9  add     rdx, qword ptr [rsp+88h+FileOffset]
0x1400412e1  mov     rcx, [rax+140h]
0x1400412e8  cmp     rdx, [rcx+18h]
0x1400412ec  jle     loc_14004121D
0x1400412f2  mov     ecx, 0C0000102h; Status
0x1400412f7  mov     [rbp+18h], ecx
0x1400412fa  call    cs:__imp_ExRaiseStatus
0x140041307  mov     dword ptr [rbx+38h], 3
0x14004130e  mov     rax, [r12]
0x140041312  mov     [rbx+30h], rax
0x140041316  mov     rax, rdx
0x140041319  neg     rax
0x14004131c  and     rax, [r12]
0x140041320  mov     [rcx], rax
0x140041323  lea     eax, [rdx-1]
0x140041326  and     eax, [r12]
0x14004132a  mov     [rbx+1Ch], eax
0x14004132d  jmp     loc_1400411DD
0x140041332  call    cs:__imp_CcPinRead
0x140041339  nop     dword ptr [rax+rax+00h]
0x14004133e  mov     eax, [rbx+38h]
0x140041341  or      eax, 10h
0x140041344  jmp     loc_14004127C
0x140041349  test    r13d, r13d
0x14004134c  jnz     loc_1400411B5
0x140041352  mov     r9, [rsi]
0x140041355  cmp     [r9+160h], rdi
0x14004135c  jnz     short loc_14004136C
0x14004135e  test    dword ptr [r9+30h], 20000000h
0x140041366  jz      loc_1400411B5
0x14004136c  mov     eax, [rbp+1Ch]
0x14004136f  shr     eax, 4
0x140041372  and     al, 1
0x140041374  test    r12, r12
0x140041377  jz      short loc_1400413B9
0x140041379  mov     r8, [r12]
0x14004137d  mov     ecx, [r9+48h]
0x140041381  shr     r8, cl
0x140041384  and     r8d, [r9+4Ch]
0x140041388  jmp     short loc_1400413BC
0x14004138a  mov     rax, [rcx]
0x14004138d  mov     edx, [rax+44h]
0x140041390  jmp     loc_1400411D0
0x140041395  lea     rcx, [rbx+20h]
0x140041399  call    UdfFreePool
0x14004139e  jmp     loc_14004117E
0x1400413a3  mov     rdx, [rsi]
0x1400413a6  xor     r9d, r9d
0x1400413a9  mov     r8, r14
0x1400413ac  mov     rcx, rbp
0x1400413af  call    UdfCreateInternalStream
0x1400413b4  jmp     loc_14004119F
0x1400413b9  mov     r8d, edi
0x1400413bc  mov     r9d, [r9+50h]
0x1400413c0  mov     rdx, r14
0x1400413c3  mov     [rsp+88h+var_58], al
0x1400413c7  mov     rcx, rbp
0x1400413ca  mov     byte ptr [rsp+88h+Buffer], dil
0x1400413cf  mov     [rsp+88h+Bcb], rdi
0x1400413d4  call    UdfSeqCacheReserveFileRegion
0x1400413d9  lea     rcx, [rbp+10h]
0x1400413dd  jmp     loc_1400411B8
```
