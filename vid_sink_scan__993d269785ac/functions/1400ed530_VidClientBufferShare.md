# VidClientBufferShare

- ea: `0x1400ed530`
- end: `0x1400ed7b8`
- name: `VidClientBufferShare`
- size: `648`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, int, PVOID Object, _QWORD *)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x140008da4`
- `0x140009274`
- `0x140079ec0`
- `0x14007a268`
- `0x140084554`
- `0x14008974c`
- `0x140089e1c`
- `0x140089f7c`
- `0x1400eca70`
- `0x1400ecd6c`
- `0x1400ed478`
- `0x1400fdab0`

## callees

- `0x140021650`
- `0x1400ed330`
- `0x1400ed530`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x1400ed780`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400ed780`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400ed5fe`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x1400ed5fe`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400ed60e`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400ed60e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ed64c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400ed64c`
- `ntoskrnl!ExAllocatePool2` at `0x1400ed717`
- `ntoskrnl!ExAllocatePool2` at `0x1400ed717`
- `ntoskrnl!KeStackAttachProcess` at `0x1400ed762`
- `ntoskrnl!KeStackAttachProcess` at `0x1400ed762`

## pseudocode

```c
__int64 __fastcall VidClientBufferShare(__int64 a1, __int64 a2, _QWORD *a3, int a4, PVOID Object, _QWORD *a6)
{
  _QWORD *v7; // rdi
  unsigned int v10; // esi
  _QWORD *v11; // r15
  _QWORD *v12; // rax
  char v13; // r15
  struct _KPROCESS *v14; // r14
  ULONG Priority; // eax
  __int64 v16; // rax
  _QWORD **v18; // rcx
  _QWORD *v19; // rdx
  __int64 Pool2; // rax
  _QWORD *v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  struct _KAPC_STATE ApcState; // [rsp+50h] [rbp-68h] BYREF

  v7 = a3;
  memset(&ApcState, 0, sizeof(ApcState));
  v10 = 0;
  if ( a6 )
    *a6 = 0;
  if ( !*(_QWORD *)(a1 + 24) && !*(_QWORD *)(a1 + 32) )
  {
    v11 = (_QWORD *)(a1 + 40);
    if ( a3 != (_QWORD *)a1 || (_QWORD *)*v11 == v11 )
    {
      v12 = 0;
      if ( a2 )
      {
        v18 = (_QWORD **)(a1 + 40);
        v19 = *v18;
        if ( *v18 == v18 )
        {
          v11 = v18;
        }
        else
        {
          do
          {
            v12 = v19 - 1;
            v11 = v18;
            if ( *(v19 - 1) == a2 )
              break;
            v19 = (_QWORD *)*v19;
            v12 = 0;
          }
          while ( v19 != v18 );
        }
      }
      if ( !v12 )
      {
        if ( a3 != (_QWORD *)a1 )
        {
          Pool2 = ExAllocatePool2(64, 40, 1917084758);
          v21 = (_QWORD *)Pool2;
          if ( !Pool2 )
            goto LABEL_30;
          v22 = (_QWORD *)v11[1];
          if ( (_QWORD *)*v22 != v11 )
            __fastfail(3u);
          v23 = (_QWORD *)(Pool2 + 8);
          *v23 = v11;
          v23[1] = v22;
          *v22 = v23;
          v11[1] = v23;
          v7 = v21;
        }
        v13 = 0;
        *v7 = a2;
        v7[3] = Object;
        ObfReferenceObjectWithTag(Object, 0x72446456u);
        v14 = (struct _KPROCESS *)v7[3];
        if ( v14 != (struct _KPROCESS *)PsGetCurrentProcess() )
        {
          KeStackAttachProcess(v14, &ApcState);
          v13 = 1;
        }
        Priority = -536870896;
        if ( !a4 )
          Priority = 1610612752;
        v7[4] = MmMapLockedPagesSpecifyCache(*(PMDL *)(a1 + 56), 1, MmCached, 0, 0, Priority);
        if ( v13 )
          KeUnstackDetachProcess(&ApcState);
        v16 = v7[4];
        if ( v16 )
        {
          if ( a6 )
            *a6 = v16;
          return v10;
        }
LABEL_30:
        v10 = -1073741670;
        if ( v7 )
          VidClientBufferpUnShareInternal(a1, v7);
        return v10;
      }
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400ed530  mov     [rsp+arg_8], rbx
0x1400ed535  mov     [rsp+arg_18], rsi
0x1400ed53a  push    rdi
0x1400ed53b  push    r12
0x1400ed53d  push    r13
0x1400ed53f  push    r14
0x1400ed541  push    r15
0x1400ed543  sub     rsp, 90h
0x1400ed54a  mov     rax, cs:__security_cookie
0x1400ed551  xor     rax, rsp
0x1400ed554  mov     [rsp+0B8h+var_38], rax
0x1400ed55c  mov     r13d, r9d
0x1400ed55f  mov     rdi, r8
0x1400ed562  mov     r14, rdx
0x1400ed565  mov     rbx, rcx
0x1400ed568  mov     [rsp+0B8h+var_78], rcx
0x1400ed56d  mov     [rsp+0B8h+var_80], r8
0x1400ed572  mov     r12, [rsp+0B8h+arg_28]
0x1400ed57a  mov     [rsp+0B8h+var_70], r12
0x1400ed57f  xorps   xmm0, xmm0
0x1400ed582  movups  xmmword ptr [rsp+0B8h+ApcState.ApcListHead.Flink], xmm0
0x1400ed587  movups  xmmword ptr [rsp+0B8h+ApcState.ApcListHead.Flink+10h], xmm0
0x1400ed58c  movups  xmmword ptr [rsp+0B8h+ApcState.Process], xmm0
0x1400ed591  xor     esi, esi
0x1400ed593  test    r12, r12
0x1400ed596  jz      short loc_1400ED59C
0x1400ed598  mov     [r12], rsi
0x1400ed59c  cmp     qword ptr [rcx+18h], 0
0x1400ed5a1  jnz     loc_1400ED6CC
0x1400ed5a7  cmp     qword ptr [rcx+20h], 0
0x1400ed5ac  jnz     loc_1400ED6CC
0x1400ed5b2  lea     r15, [rcx+28h]
0x1400ed5b6  cmp     rdi, rbx
0x1400ed5b9  jnz     short loc_1400ED5C4
0x1400ed5bb  cmp     [r15], r15
0x1400ed5be  jnz     loc_1400ED6CC
0x1400ed5c4  mov     rax, rsi
0x1400ed5c7  test    r14, r14
0x1400ed5ca  jnz     loc_1400ED6D3
0x1400ed5d0  test    rax, rax
0x1400ed5d3  jnz     loc_1400ED6CC
0x1400ed5d9  cmp     rdi, rbx
0x1400ed5dc  jnz     loc_1400ED707
0x1400ed5e2  xor     r15b, r15b
0x1400ed5e5  mov     [rsp+0B8h+var_88], r15b
0x1400ed5ea  mov     [rdi], r14
0x1400ed5ed  mov     rcx, [rsp+0B8h+Object]; Object
0x1400ed5f5  mov     [rdi+18h], rcx
0x1400ed5f9  mov     edx, 72446456h; Tag
0x1400ed5fe  call    cs:__imp_ObfReferenceObjectWithTag
0x1400ed605  nop     dword ptr [rax+rax+00h]
0x1400ed60a  mov     r14, [rdi+18h]
0x1400ed60e  call    cs:__imp_PsGetCurrentProcess
0x1400ed615  nop     dword ptr [rax+rax+00h]
0x1400ed61a  cmp     r14, rax
0x1400ed61d  jnz     loc_1400ED75A
0x1400ed623  mov     eax, 0E0000010h
0x1400ed628  mov     ecx, 60000010h
0x1400ed62d  test    r13d, r13d
0x1400ed630  cmovz   eax, ecx
0x1400ed633  mov     [rsp+0B8h+Priority], eax; Priority
0x1400ed637  mov     [rsp+0B8h+BugCheckOnFailure], esi; BugCheckOnFailure
0x1400ed63b  xor     r9d, r9d; RequestedAddress
0x1400ed63e  mov     r8d, 1; CacheType
0x1400ed644  movzx   edx, r8b; AccessMode
0x1400ed648  mov     rcx, [rbx+38h]; MemoryDescriptorList
0x1400ed64c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400ed653  nop     dword ptr [rax+rax+00h]
0x1400ed658  mov     [rdi+20h], rax
0x1400ed65c  jmp     short loc_1400ED67D
0x1400ed65e  mov     rdi, [rsp+0B8h+var_80]
0x1400ed663  mov     qword ptr [rdi+20h], 0
0x1400ed66b  xor     esi, esi
0x1400ed66d  movzx   r15d, [rsp+0B8h+var_88]
0x1400ed673  mov     rbx, [rsp+0B8h+var_78]
0x1400ed678  mov     r12, [rsp+0B8h+var_70]
0x1400ed67d  test    r15b, r15b
0x1400ed680  jnz     loc_1400ED77B
0x1400ed686  mov     rax, [rdi+20h]
0x1400ed68a  test    rax, rax
0x1400ed68d  jz      loc_1400ED791
0x1400ed693  test    r12, r12
0x1400ed696  jnz     loc_1400ED7AF
0x1400ed69c  mov     eax, esi
0x1400ed69e  mov     rcx, [rsp+0B8h+var_38]
0x1400ed6a6  xor     rcx, rsp; StackCookie
0x1400ed6a9  call    __security_check_cookie
0x1400ed6ae  lea     r11, [rsp+0B8h+var_28]
0x1400ed6b6  mov     rbx, [r11+38h]
0x1400ed6ba  mov     rsi, [r11+48h]
0x1400ed6be  mov     rsp, r11
0x1400ed6c1  pop     r15
0x1400ed6c3  pop     r14
0x1400ed6c5  pop     r13
0x1400ed6c7  pop     r12
0x1400ed6c9  pop     rdi
0x1400ed6ca  retn
0x1400ed6cc  mov     eax, 0C000000Dh
0x1400ed6d1  jmp     short loc_1400ED69E
0x1400ed6d3  add     rcx, 28h ; '('
0x1400ed6d7  mov     rdx, [rcx]
0x1400ed6da  cmp     rdx, rcx
0x1400ed6dd  jz      short loc_1400ED6FF
0x1400ed6df  lea     rax, [rdx-8]
0x1400ed6e3  mov     r15, rcx
0x1400ed6e6  cmp     [rax], r14
0x1400ed6e9  jz      loc_1400ED5D0
0x1400ed6ef  mov     rdx, [rdx]
0x1400ed6f2  mov     rax, rsi
0x1400ed6f5  cmp     rdx, rcx
0x1400ed6f8  jnz     short loc_1400ED6DF
0x1400ed6fa  jmp     loc_1400ED5D0
0x1400ed6ff  mov     r15, rcx
0x1400ed702  jmp     loc_1400ED5D0
0x1400ed707  mov     edx, 28h ; '('
0x1400ed70c  mov     ecx, 40h ; '@'
0x1400ed711  mov     r8d, 72446456h
0x1400ed717  call    cs:__imp_ExAllocatePool2
0x1400ed71e  nop     dword ptr [rax+rax+00h]
0x1400ed723  mov     rdx, rax
0x1400ed726  test    rax, rax
0x1400ed729  jz      short loc_1400ED791
0x1400ed72b  mov     rcx, [r15+8]
0x1400ed72f  cmp     [rcx], r15
0x1400ed732  jnz     short loc_1400ED753
0x1400ed734  add     rax, 8
0x1400ed738  mov     [rax], r15
0x1400ed73b  mov     [rax+8], rcx
0x1400ed73f  mov     [rcx], rax
0x1400ed742  mov     [r15+8], rax
0x1400ed746  mov     rdi, rdx
0x1400ed749  mov     [rsp+0B8h+var_80], rdx
0x1400ed74e  jmp     loc_1400ED5E2
0x1400ed753  mov     ecx, 3
0x1400ed758  int     29h; Win8: RtlFailFast(ecx)
0x1400ed75a  lea     rdx, [rsp+0B8h+ApcState]; ApcState
0x1400ed75f  mov     rcx, r14; PROCESS
0x1400ed762  call    cs:__imp_KeStackAttachProcess
0x1400ed769  nop     dword ptr [rax+rax+00h]
0x1400ed76e  mov     r15b, 1
0x1400ed771  mov     [rsp+0B8h+var_88], r15b
0x1400ed776  jmp     loc_1400ED623
0x1400ed77b  lea     rcx, [rsp+0B8h+ApcState]; ApcState
0x1400ed780  call    cs:__imp_KeUnstackDetachProcess
0x1400ed787  nop     dword ptr [rax+rax+00h]
0x1400ed78c  jmp     loc_1400ED686
0x1400ed791  mov     esi, 0C000009Ah
0x1400ed796  test    rdi, rdi
0x1400ed799  jz      loc_1400ED69C
0x1400ed79f  mov     rdx, rdi
0x1400ed7a2  mov     rcx, rbx
0x1400ed7a5  call    VidClientBufferpUnShareInternal
0x1400ed7aa  jmp     loc_1400ED69C
0x1400ed7af  mov     [r12], rax
0x1400ed7b3  jmp     loc_1400ED69C
```
