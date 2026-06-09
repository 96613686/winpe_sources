# VhdmpiTryInitializeMergeAsyncCopyContext(VHD_INTERNAL_MERGE_CONTEXT *,VHD_INTERNAL_ASYNC_MERGE_COPY_CONTEXT *)

- ea: `0x1400b17b4`
- end: `0x1400b1a7e`
- name: `?VhdmpiTryInitializeMergeAsyncCopyContext@@YAXPEAUVHD_INTERNAL_MERGE_CONTEXT@@PEAUVHD_INTERNAL_ASYNC_MERGE_COPY_CONTEXT@@@Z`
- size: `714`
- prototype: `void(struct VHD_INTERNAL_MERGE_CONTEXT *, struct VHD_INTERNAL_ASYNC_MERGE_COPY_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400b073c`

## callees

- `0x140033598`
- `0x14005dd00`
- `0x1400b03f4`
- `0x1400b17b4`
- `0x1400b6cbc`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b17dd`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b17dd`
- `ntoskrnl!PsCreateSystemThread` at `0x1400b1a2b`
- `ntoskrnl!PsCreateSystemThread` at `0x1400b1a2b`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400b1a42`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400b1a42`
- `ntoskrnl!ExAllocatePool2` at `0x1400b1812`
- `ntoskrnl!ExAllocatePool2` at `0x1400b1832`
- `ntoskrnl!ExAllocatePool2` at `0x1400b184e`
- `ntoskrnl!ExAllocatePool2` at `0x1400b186e`
- `ntoskrnl!ExAllocatePool2` at `0x1400b188d`
- `ntoskrnl!ExAllocatePool2` at `0x1400b1812`
- `ntoskrnl!ExAllocatePool2` at `0x1400b1832`
- `ntoskrnl!ExAllocatePool2` at `0x1400b184e`
- `ntoskrnl!ExAllocatePool2` at `0x1400b186e`
- `ntoskrnl!ExAllocatePool2` at `0x1400b188d`
- `ntoskrnl!KeInitializeEvent` at `0x1400b1920`
- `ntoskrnl!KeInitializeEvent` at `0x1400b193b`
- `ntoskrnl!KeInitializeEvent` at `0x1400b1920`
- `ntoskrnl!KeInitializeEvent` at `0x1400b193b`

## pseudocode

```c
void __fastcall VhdmpiTryInitializeMergeAsyncCopyContext(struct _EX_RUNDOWN_REF *a1, struct _EX_RUNDOWN_REF *a2)
{
  __int64 v4; // rax
  __int64 Pool2; // rax
  __int64 v6; // rdx
  __int64 v7; // rax
  bool v8; // zf
  __int64 v9; // r15
  __int64 v10; // rsi
  __int64 v11; // rdi
  _OWORD *v12; // rax
  ULONG_PTR Count; // rbx
  unsigned int i; // ebx
  void **StartContext; // rdi
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-68h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ExInitializeRundownProtection(a2 + 1);
  v4 = (unsigned int)dword_14008E380;
  LODWORD(a2[2].Count) = dword_14008E380;
  if ( (_DWORD)v4 != 1 )
  {
    a2[3].Count = ExAllocatePool2(64, 24 * v4, 1732528214);
    Pool2 = ExAllocatePool2(64, 24LL * LODWORD(a2[2].Count), 1732528214);
    v6 = 8LL * LODWORD(a2[2].Count);
    a2[4].Count = Pool2;
    a2[5].Count = ExAllocatePool2(64, v6, 1732528214);
    a2[6].Count = ExAllocatePool2(64, 48LL * LODWORD(a2[2].Count), 1732528214);
    v7 = ExAllocatePool2(64, 328LL * LODWORD(a2[2].Count), 1732528214);
    v8 = a2[3].Count == 0;
    a2[7].Count = v7;
    if ( !v8 && a2[4].Count && a2[5].Count && a2[6].Count && v7 )
    {
      v9 = 0;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.ObjectName = 0;
      for ( *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            (unsigned int)v9 < LODWORD(a2[2].Count);
            *(struct _EX_RUNDOWN_REF *)(v11 + Count + 32) = a1[9] )
      {
        v10 = 3 * v9;
        KeInitializeEvent((PRKEVENT)(a2[3].Count + 24 * v9), SynchronizationEvent, 0);
        KeInitializeEvent((PRKEVENT)(a2[4].Count + 24 * v9), SynchronizationEvent, 0);
        v11 = 328LL * (unsigned int)v9;
        *(_QWORD *)(a2[5].Count + 8 * v9) = a2[4].Count + 24 * v9;
        v12 = (_OWORD *)(a2[6].Count + 48 * v9);
        *v12 = 0;
        v12[1] = 0;
        v12[2] = 0;
        Count = a2[7].Count;
        memset((void *)(v11 + Count + 8), 0, 0x140u);
        *(_QWORD *)(v11 + Count) = a1;
        v9 = (unsigned int)(v9 + 1);
        *(_QWORD *)(v11 + Count + 16) = a2[3].Count + 8 * v10;
        *(_QWORD *)(v11 + Count + 24) = a2[4].Count + 8 * v10;
      }
      for ( i = 0; i < LODWORD(a2[2].Count); ++i )
      {
        StartContext = (void **)(a2[7].Count + 328LL * i);
        if ( (int)VhdmpiInitializeInternalIoContext(StartContext + 5, a1[5].Count) < 0 )
          goto LABEL_15;
        if ( PsCreateSystemThread(
               StartContext + 1,
               0x1FFFFFu,
               &ObjectAttributes,
               0,
               0,
               VhdmpiMergeCopyThread,
               StartContext) < 0 )
        {
          VhdmpiCleanupInternalIoContext(StartContext + 5);
LABEL_15:
          if ( i < 2 )
            goto LABEL_17;
          LODWORD(a2[2].Count) = i;
          return;
        }
        ExAcquireRundownProtection(a1 + 47);
      }
    }
    else
    {
LABEL_17:
      VhdmpiCleanupMergeAsyncCopyContext((struct VHD_INTERNAL_ASYNC_MERGE_COPY_CONTEXT *)a2);
    }
  }
}

```

## disassembly

```asm
0x1400b17b4  push    rbx
0x1400b17b6  push    rbp
0x1400b17b7  push    rsi
0x1400b17b8  push    rdi
0x1400b17b9  push    r14
0x1400b17bb  push    r15
0x1400b17bd  sub     rsp, 78h
0x1400b17c1  xorps   xmm0, xmm0
0x1400b17c4  mov     r14, rcx
0x1400b17c7  lea     rcx, [rdx+8]; RunRef
0x1400b17cb  mov     rbp, rdx
0x1400b17ce  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x1400b17d3  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x1400b17d8  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400b17dd  call    cs:__imp_ExInitializeRundownProtection
0x1400b17e4  nop     dword ptr [rax+rax+00h]
0x1400b17e9  mov     eax, cs:dword_14008E380
0x1400b17ef  mov     [rbp+10h], eax
0x1400b17f2  cmp     eax, 1
0x1400b17f5  jz      loc_1400B1A70
0x1400b17fb  lea     rdx, [rax+rax*2]
0x1400b17ff  mov     edi, 67444856h
0x1400b1804  mov     ebx, 40h ; '@'
0x1400b1809  shl     rdx, 3
0x1400b180d  mov     r8d, edi
0x1400b1810  mov     ecx, ebx
0x1400b1812  call    cs:__imp_ExAllocatePool2
0x1400b1819  nop     dword ptr [rax+rax+00h]
0x1400b181e  mov     [rbp+18h], rax
0x1400b1822  mov     r8d, edi
0x1400b1825  mov     eax, [rbp+10h]
0x1400b1828  mov     ecx, ebx
0x1400b182a  lea     rdx, [rax+rax*2]
0x1400b182e  shl     rdx, 3
0x1400b1832  call    cs:__imp_ExAllocatePool2
0x1400b1839  nop     dword ptr [rax+rax+00h]
0x1400b183e  mov     edx, [rbp+10h]
0x1400b1841  mov     r8d, edi
0x1400b1844  shl     rdx, 3
0x1400b1848  mov     ecx, ebx
0x1400b184a  mov     [rbp+20h], rax
0x1400b184e  call    cs:__imp_ExAllocatePool2
0x1400b1855  nop     dword ptr [rax+rax+00h]
0x1400b185a  mov     [rbp+28h], rax
0x1400b185e  mov     r8d, edi
0x1400b1861  mov     eax, [rbp+10h]
0x1400b1864  mov     ecx, ebx
0x1400b1866  lea     rdx, [rax+rax*2]
0x1400b186a  shl     rdx, 4
0x1400b186e  call    cs:__imp_ExAllocatePool2
0x1400b1875  nop     dword ptr [rax+rax+00h]
0x1400b187a  mov     [rbp+30h], rax
0x1400b187e  mov     r8d, edi
0x1400b1881  mov     eax, [rbp+10h]
0x1400b1884  mov     ecx, ebx
0x1400b1886  imul    rdx, rax, 148h
0x1400b188d  call    cs:__imp_ExAllocatePool2
0x1400b1894  nop     dword ptr [rax+rax+00h]
0x1400b1899  cmp     qword ptr [rbp+18h], 0
0x1400b189e  mov     [rbp+38h], rax
0x1400b18a2  jz      loc_1400B1A68
0x1400b18a8  cmp     qword ptr [rbp+20h], 0
0x1400b18ad  jz      loc_1400B1A68
0x1400b18b3  cmp     qword ptr [rbp+28h], 0
0x1400b18b8  jz      loc_1400B1A68
0x1400b18be  cmp     qword ptr [rbp+30h], 0
0x1400b18c3  jz      loc_1400B1A68
0x1400b18c9  test    rax, rax
0x1400b18cc  jz      loc_1400B1A68
0x1400b18d2  xor     r15d, r15d
0x1400b18d5  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x1400b18dd  xorps   xmm0, xmm0
0x1400b18e0  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], 0
0x1400b18e9  mov     [rsp+0A8h+ObjectAttributes.Attributes], 200h
0x1400b18f1  mov     [rsp+0A8h+ObjectAttributes.ObjectName], 0
0x1400b18fa  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400b1900  cmp     [rbp+10h], r15d
0x1400b1904  jbe     loc_1400B19C4
0x1400b190a  mov     rax, [rbp+18h]
0x1400b190e  lea     rsi, [r15+r15*2]
0x1400b1912  xor     r8d, r8d; State
0x1400b1915  mov     ebx, r15d
0x1400b1918  lea     rcx, [rax+rsi*8]; Event
0x1400b191c  lea     edx, [r8+1]; Type
0x1400b1920  call    cs:__imp_KeInitializeEvent
0x1400b1927  nop     dword ptr [rax+rax+00h]
0x1400b192c  mov     rax, [rbp+20h]
0x1400b1930  xor     r8d, r8d; State
0x1400b1933  lea     rcx, [rax+rsi*8]; Event
0x1400b1937  lea     edx, [r8+1]; Type
0x1400b193b  call    cs:__imp_KeInitializeEvent
0x1400b1942  nop     dword ptr [rax+rax+00h]
0x1400b1947  mov     rax, [rbp+20h]
0x1400b194b  xorps   xmm0, xmm0
0x1400b194e  imul    rdi, rbx, 148h
0x1400b1955  lea     rcx, [rax+rsi*8]
0x1400b1959  xor     edx, edx; Val
0x1400b195b  mov     rax, [rbp+28h]
0x1400b195f  mov     r8d, 140h; Size
0x1400b1965  mov     [rax+r15*8], rcx
0x1400b1969  lea     rax, [r15+r15*2]
0x1400b196d  shl     rax, 4
0x1400b1971  add     rax, [rbp+30h]
0x1400b1975  movups  xmmword ptr [rax], xmm0
0x1400b1978  movups  xmmword ptr [rax+10h], xmm0
0x1400b197c  movups  xmmword ptr [rax+20h], xmm0
0x1400b1980  mov     rbx, [rbp+38h]
0x1400b1984  lea     rcx, [rbx+8]
0x1400b1988  add     rcx, rdi; void *
0x1400b198b  call    memset
0x1400b1990  mov     [rdi+rbx], r14
0x1400b1994  inc     r15d
0x1400b1997  mov     rax, [rbp+18h]
0x1400b199b  lea     rcx, [rax+rsi*8]
0x1400b199f  mov     [rdi+rbx+10h], rcx
0x1400b19a4  mov     rax, [rbp+20h]
0x1400b19a8  lea     rcx, [rax+rsi*8]
0x1400b19ac  mov     [rdi+rbx+18h], rcx
0x1400b19b1  mov     rax, [r14+48h]
0x1400b19b5  mov     [rdi+rbx+20h], rax
0x1400b19ba  cmp     r15d, [rbp+10h]
0x1400b19be  jb      loc_1400B190A
0x1400b19c4  xor     ebx, ebx
0x1400b19c6  cmp     ebx, [rbp+10h]
0x1400b19c9  jnb     loc_1400B1A70
0x1400b19cf  mov     r9, [r14+28h]
0x1400b19d3  mov     r8b, 1
0x1400b19d6  mov     edx, [r14+3Ch]
0x1400b19da  mov     eax, ebx
0x1400b19dc  imul    rdi, rax, 148h
0x1400b19e3  mov     [rsp+0A8h+ClientId], r9; __int64
0x1400b19e8  add     rdi, [rbp+38h]
0x1400b19ec  mov     r9, [r9+480h]
0x1400b19f3  lea     rcx, [rdi+28h]; void *
0x1400b19f7  call    VhdmpiInitializeInternalIoContext
0x1400b19fc  test    eax, eax
0x1400b19fe  js      short loc_1400B1A5E
0x1400b1a00  lea     rax, ?VhdmpiMergeCopyThread@@YAXPEAX@Z; VhdmpiMergeCopyThread(void *)
0x1400b1a07  mov     [rsp+0A8h+StartContext], rdi; StartContext
0x1400b1a0c  mov     [rsp+0A8h+StartRoutine], rax; StartRoutine
0x1400b1a11  lea     rcx, [rdi+8]; ThreadHandle
0x1400b1a15  xor     r9d, r9d; ProcessHandle
0x1400b1a18  mov     [rsp+0A8h+ClientId], 0; ClientId
0x1400b1a21  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x1400b1a26  mov     edx, 1FFFFFh; DesiredAccess
0x1400b1a2b  call    cs:__imp_PsCreateSystemThread
0x1400b1a32  nop     dword ptr [rax+rax+00h]
0x1400b1a37  test    eax, eax
0x1400b1a39  js      short loc_1400B1A55
0x1400b1a3b  lea     rcx, [r14+178h]; RunRef
0x1400b1a42  call    cs:__imp_ExAcquireRundownProtection
0x1400b1a49  nop     dword ptr [rax+rax+00h]
0x1400b1a4e  inc     ebx
0x1400b1a50  jmp     loc_1400B19C6
0x1400b1a55  lea     rcx, [rdi+28h]; void *
0x1400b1a59  call    VhdmpiCleanupInternalIoContext
0x1400b1a5e  cmp     ebx, 2
0x1400b1a61  jb      short loc_1400B1A68
0x1400b1a63  mov     [rbp+10h], ebx
0x1400b1a66  jmp     short loc_1400B1A70
0x1400b1a68  mov     rcx, rbp; struct VHD_INTERNAL_ASYNC_MERGE_COPY_CONTEXT *
0x1400b1a6b  call    ?VhdmpiCleanupMergeAsyncCopyContext@@YAXPEAUVHD_INTERNAL_ASYNC_MERGE_COPY_CONTEXT@@@Z; VhdmpiCleanupMergeAsyncCopyContext(VHD_INTERNAL_ASYNC_MERGE_COPY_CONTEXT *)
0x1400b1a70  add     rsp, 78h
0x1400b1a74  pop     r15
0x1400b1a76  pop     r14
0x1400b1a78  pop     rdi
0x1400b1a79  pop     rsi
0x1400b1a7a  pop     rbp
0x1400b1a7b  pop     rbx
0x1400b1a7c  retn
```
