# RtlCompareExchangePropertyStore

- ea: `0x1400d60c0`
- end: `0x1400d62d1`
- name: `RtlCompareExchangePropertyStore`
- size: `529`
- prototype: `__int64 __fastcall(void *Key)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1400010f0`
- `0x14000f0f0`
- `0x140035f58`
- `0x140037e68`
- `0x14003c19c`
- `0x14003c430`
- `0x1400d60c0`
- `0x1400f9780`

## pseudocode

```c
__int64 __fastcall RtlCompareExchangePropertyStore(_OWORD *Key, unsigned __int64 a2, __int64 *a3, _QWORD *a4)
{
  void *v7; // r15
  unsigned __int8 v8; // al
  unsigned __int64 v9; // rdx
  unsigned __int8 v10; // bp
  int v11; // ebx
  char *v12; // rax
  char *Pool; // rbx
  int v14; // edi
  unsigned int v15; // esi
  unsigned __int8 v16; // al
  __int64 v17; // rdx
  void *v18; // rdi
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned int v21; // ebx

  while ( 1 )
  {
    v7 = 0;
    v8 = RtlpAcquirePropStoreLockExclusive(RtlpPropStoreLock);
    v9 = (unsigned __int64)RtlpPropStoreEntries;
    v10 = v8;
    if ( RtlpPropStoreEntries )
    {
      v11 = 0;
      v12 = (char *)bsearch(
                      Key,
                      RtlpPropStoreEntries,
                      (unsigned int)RtlpPropStoreEntriesActiveCount,
                      0x18u,
                      RtlpComparePropertyEntry);
      if ( v12 )
        break;
    }
    if ( v10 > 2u )
    {
      v21 = -1073741670;
      goto LABEL_29;
    }
    Pool = (char *)RtlpPropStoreEntries;
    if ( RtlpPropStoreEntries && (_DWORD)RtlpPropStoreEntriesActiveCount + 1 != RtlpPropStoreEntriesTotalCount )
      goto LABEL_15;
    v14 = RtlpPropStoreEntriesTotalCount;
    if ( RtlpPropStoreEntriesTotalCount )
    {
      v15 = 2 * RtlpPropStoreEntriesTotalCount;
      if ( 2 * RtlpPropStoreEntriesTotalCount < (unsigned int)RtlpPropStoreEntriesTotalCount )
        goto LABEL_27;
    }
    else
    {
      v15 = 16;
    }
    LOBYTE(v9) = v10;
    SkReleaseSpinLockExclusive(RtlpPropStoreLock, v9);
    Pool = (char *)SkAllocatePool(512, 24LL * v15);
    if ( !Pool )
    {
LABEL_27:
      v21 = -1073741801;
      goto LABEL_29;
    }
    v16 = RtlpAcquirePropStoreLockExclusive(RtlpPropStoreLock);
    v10 = v16;
    if ( v14 == RtlpPropStoreEntriesTotalCount )
    {
      v18 = RtlpPropStoreEntries;
      if ( RtlpPropStoreEntries )
      {
        memmove(Pool, RtlpPropStoreEntries, 24LL * (unsigned int)RtlpPropStoreEntriesActiveCount);
        v7 = v18;
      }
      RtlpPropStoreEntries = Pool;
      RtlpPropStoreEntriesTotalCount = v15;
LABEL_15:
      v12 = &Pool[24 * (unsigned int)RtlpPropStoreEntriesActiveCount];
      v11 = 1;
      v9 = (unsigned int)(RtlpPropStoreEntriesActiveCount + 1);
      LODWORD(RtlpPropStoreEntriesActiveCount) = RtlpPropStoreEntriesActiveCount + 1;
      if ( a3 )
        v19 = *a3;
      else
        v19 = 0;
      *((_QWORD *)v12 + 2) = v19;
      *(_OWORD *)v12 = *Key;
      break;
    }
    LOBYTE(v17) = v16;
    SkReleaseSpinLockExclusive(RtlpPropStoreLock, v17);
    SkFreePool(512, Pool);
  }
  v20 = *((_QWORD *)v12 + 2);
  if ( !a3 || v20 == *a3 )
  {
    v9 = a2;
    *((_QWORD *)v12 + 2) = a2;
  }
  if ( a4 )
    *a4 = v20;
  if ( v11 )
  {
    qsort(RtlpPropStoreEntries, (unsigned int)RtlpPropStoreEntriesActiveCount, 0x18u, RtlpComparePropertyEntry);
    v21 = 0;
  }
  else
  {
    v21 = 0x40000000;
  }
LABEL_29:
  LOBYTE(v9) = v10;
  SkReleaseSpinLockExclusive(RtlpPropStoreLock, v9);
  if ( v7 )
    SkFreePool(512, v7);
  return v21;
}

```

## disassembly

```asm
0x1400d60c0  mov     [rsp+arg_8], rdx
0x1400d60c5  push    rbx
0x1400d60c6  push    rbp
0x1400d60c7  push    rsi
0x1400d60c8  push    rdi
0x1400d60c9  push    r12
0x1400d60cb  push    r13
0x1400d60cd  push    r14
0x1400d60cf  push    r15
0x1400d60d1  sub     rsp, 38h
0x1400d60d5  mov     r12, r9
0x1400d60d8  mov     r14, r8
0x1400d60db  mov     r13, rcx
0x1400d60de  lea     rcx, RtlpPropStoreLock
0x1400d60e5  xor     r15d, r15d
0x1400d60e8  call    RtlpAcquirePropStoreLockExclusive
0x1400d60ed  mov     rdx, cs:RtlpPropStoreEntries; Base
0x1400d60f4  mov     bpl, al
0x1400d60f7  test    rdx, rdx
0x1400d60fa  jz      short loc_1400D6126
0x1400d60fc  mov     r8d, cs:RtlpPropStoreEntriesActiveCount; NumOfElements
0x1400d6103  lea     rax, RtlpComparePropertyEntry
0x1400d610a  lea     r9d, [r15+18h]; SizeOfElements
0x1400d610e  mov     [rsp+78h+PtFuncCompare], rax; PtFuncCompare
0x1400d6113  mov     rcx, r13; Key
0x1400d6116  xor     ebx, ebx
0x1400d6118  call    bsearch
0x1400d611d  test    rax, rax
0x1400d6120  jnz     loc_1400D623F
0x1400d6126  cmp     bpl, 2
0x1400d612a  ja      loc_1400D6297
0x1400d6130  mov     rbx, cs:RtlpPropStoreEntries
0x1400d6137  test    rbx, rbx
0x1400d613a  jz      short loc_1400D6150
0x1400d613c  mov     eax, cs:RtlpPropStoreEntriesActiveCount
0x1400d6142  inc     eax
0x1400d6144  cmp     eax, cs:RtlpPropStoreEntriesTotalCount
0x1400d614a  jnz     loc_1400D620B
0x1400d6150  mov     edi, cs:RtlpPropStoreEntriesTotalCount
0x1400d6156  test    edi, edi
0x1400d6158  jnz     short loc_1400D615F
0x1400d615a  lea     esi, [rdi+10h]
0x1400d615d  jmp     short loc_1400D616A
0x1400d615f  lea     esi, [rdi+rdi]
0x1400d6162  cmp     esi, edi
0x1400d6164  jb      loc_1400D6290
0x1400d616a  mov     dl, bpl
0x1400d616d  lea     rcx, RtlpPropStoreLock
0x1400d6174  call    SkReleaseSpinLockExclusive
0x1400d6179  mov     eax, esi
0x1400d617b  mov     ecx, 200h
0x1400d6180  mov     r8d, 70725052h
0x1400d6186  lea     rdx, [rax+rax*2]
0x1400d618a  shl     rdx, 3
0x1400d618e  call    SkAllocatePool
0x1400d6193  mov     rbx, rax
0x1400d6196  test    rax, rax
0x1400d6199  jz      loc_1400D6290
0x1400d619f  lea     rcx, RtlpPropStoreLock
0x1400d61a6  call    RtlpAcquirePropStoreLockExclusive
0x1400d61ab  cmp     edi, cs:RtlpPropStoreEntriesTotalCount
0x1400d61b1  mov     bpl, al
0x1400d61b4  jz      short loc_1400D61D6
0x1400d61b6  mov     dl, al
0x1400d61b8  lea     rcx, RtlpPropStoreLock
0x1400d61bf  call    SkReleaseSpinLockExclusive
0x1400d61c4  mov     rdx, rbx
0x1400d61c7  mov     ecx, 200h
0x1400d61cc  call    SkFreePool
0x1400d61d1  jmp     loc_1400D60DE
0x1400d61d6  mov     rdi, cs:RtlpPropStoreEntries
0x1400d61dd  test    rdi, rdi
0x1400d61e0  jz      short loc_1400D61FE
0x1400d61e2  mov     eax, cs:RtlpPropStoreEntriesActiveCount
0x1400d61e8  mov     rdx, rdi; Src
0x1400d61eb  mov     rcx, rbx; void *
0x1400d61ee  lea     r8, [rax+rax*2]
0x1400d61f2  shl     r8, 3; Size
0x1400d61f6  call    memmove
0x1400d61fb  mov     r15, rdi
0x1400d61fe  mov     cs:RtlpPropStoreEntries, rbx
0x1400d6205  mov     cs:RtlpPropStoreEntriesTotalCount, esi
0x1400d620b  mov     edx, cs:RtlpPropStoreEntriesActiveCount
0x1400d6211  lea     rcx, [rdx+rdx*2]
0x1400d6215  lea     rax, [rbx+rcx*8]
0x1400d6219  mov     ebx, 1
0x1400d621e  add     edx, ebx
0x1400d6220  mov     cs:RtlpPropStoreEntriesActiveCount, edx
0x1400d6226  test    r14, r14
0x1400d6229  jz      short loc_1400D6230
0x1400d622b  mov     rcx, [r14]
0x1400d622e  jmp     short loc_1400D6232
0x1400d6230  xor     ecx, ecx
0x1400d6232  mov     [rax+10h], rcx
0x1400d6236  movups  xmm0, xmmword ptr [r13+0]
0x1400d623b  movdqu  xmmword ptr [rax], xmm0
0x1400d623f  mov     rcx, [rax+10h]
0x1400d6243  test    r14, r14
0x1400d6246  jz      short loc_1400D624D
0x1400d6248  cmp     rcx, [r14]
0x1400d624b  jnz     short loc_1400D6259
0x1400d624d  mov     rdx, [rsp+78h+arg_8]
0x1400d6255  mov     [rax+10h], rdx
0x1400d6259  test    r12, r12
0x1400d625c  jz      short loc_1400D6262
0x1400d625e  mov     [r12], rcx
0x1400d6262  test    ebx, ebx
0x1400d6264  jz      short loc_1400D6289
0x1400d6266  mov     edx, cs:RtlpPropStoreEntriesActiveCount; NumOfElements
0x1400d626c  lea     r9, RtlpComparePropertyEntry; PtFuncCompare
0x1400d6273  mov     rcx, cs:RtlpPropStoreEntries; Base
0x1400d627a  mov     r8d, 18h; SizeOfElements
0x1400d6280  call    qsort
0x1400d6285  xor     ebx, ebx
0x1400d6287  jmp     short loc_1400D629C
0x1400d6289  mov     ebx, 40000000h
0x1400d628e  jmp     short loc_1400D629C
0x1400d6290  mov     ebx, 0C0000017h
0x1400d6295  jmp     short loc_1400D629C
0x1400d6297  mov     ebx, 0C000009Ah
0x1400d629c  mov     dl, bpl
0x1400d629f  lea     rcx, RtlpPropStoreLock
0x1400d62a6  call    SkReleaseSpinLockExclusive
0x1400d62ab  test    r15, r15
0x1400d62ae  jz      short loc_1400D62BD
0x1400d62b0  mov     rdx, r15
0x1400d62b3  mov     ecx, 200h
0x1400d62b8  call    SkFreePool
0x1400d62bd  mov     eax, ebx
0x1400d62bf  add     rsp, 38h
0x1400d62c3  pop     r15
0x1400d62c5  pop     r14
0x1400d62c7  pop     r13
0x1400d62c9  pop     r12
0x1400d62cb  pop     rdi
0x1400d62cc  pop     rsi
0x1400d62cd  pop     rbp
0x1400d62ce  pop     rbx
0x1400d62cf  retn
```
