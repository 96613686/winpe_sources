# SOS_MemoryTopLevelBlockAllocator::AllocateBlock(bool,ushort,void * *,uchar *)

- ea: `0x1004378f0`
- end: `0x1004379d8`
- name: `?AllocateBlock@SOS_MemoryTopLevelBlockAllocator@@QEAAPEAX_NGPEAPEAXPEAE@Z`
- size: `232`
- prototype: `void *__fastcall(SOS_MemoryTopLevelBlockAllocator *__hidden this, bool, unsigned __int16, void **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1004167c0`

## callees

- `0x1004060e0`
- `0x1004378f0`
- `0x10049db30`
- `0x1004a76e0`
- `0x1004a7800`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x1004a67a3`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a68a3`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a6986`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a67a3`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a68a3`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004a6986`
- `KERNEL32!InterlockedPopEntrySList` at `0x100437954`
- `KERNEL32!InterlockedPopEntrySList` at `0x10043798d`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a674b`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a6858`
- `KERNEL32!InterlockedPopEntrySList` at `0x100437954`
- `KERNEL32!InterlockedPopEntrySList` at `0x10043798d`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a674b`
- `KERNEL32!InterlockedPopEntrySList` at `0x1004a6858`
- `KERNEL32!QueryDepthSList` at `0x1004a6931`
- `KERNEL32!QueryDepthSList` at `0x1004a6943`
- `KERNEL32!QueryDepthSList` at `0x1004a6931`
- `KERNEL32!QueryDepthSList` at `0x1004a6943`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall SOS_MemoryTopLevelBlockAllocator::AllocateBlock(
        SOS_MemoryTopLevelBlockAllocator *this,
        char a2,
        unsigned __int16 a3,
        unsigned __int8 **a4,
        unsigned __int8 *a5)
{
  char v5; // si
  SOS_MemoryTopLevelBlockAllocator *v6; // rbp
  int v7; // r14d
  __int64 v8; // rbx
  unsigned __int8 *v9; // r15
  char v10; // r13
  union _SLIST_HEADER *v11; // r12
  PSLIST_ENTRY v12; // rax
  unsigned __int8 *v13; // rdi
  union _SLIST_HEADER *v14; // r14
  PSLIST_ENTRY v15; // rax
  struct _SLIST_ENTRY *v16; // rcx
  unsigned __int8 *v18; // rbx
  struct _SLIST_ENTRY *v19; // rcx
  struct _SLIST_ENTRY *v20; // rsi
  unsigned __int8 *v21; // rbp
  unsigned __int64 v22; // rax
  struct _SLIST_ENTRY *v23; // rdx
  PSLIST_ENTRY v24; // rax
  unsigned __int8 **v25; // r8
  unsigned __int8 *v26; // rax
  unsigned __int8 *v27; // rcx
  unsigned __int8 **v28; // r8
  unsigned __int8 *v29; // rax
  unsigned __int8 *v30; // rcx
  struct _SLIST_ENTRY *v31; // rbx
  struct _SLIST_ENTRY *v32; // rsi
  unsigned __int8 *v33; // rbp
  unsigned __int64 v34; // rax
  struct _SLIST_ENTRY *v35; // rdx
  PSLIST_ENTRY v36; // rax
  struct _SLIST_ENTRY *v37; // r8
  struct _SLIST_ENTRY *v38; // rax
  struct _SLIST_ENTRY *Next; // rcx
  struct _SLIST_ENTRY **p_Next; // r8
  struct _SLIST_ENTRY *v41; // rax
  struct SOS_MemoryFragmentDescriptor *Fragment; // rax
  struct _SLIST_ENTRY *v43; // rbx
  int v44; // eax
  char *v45; // rbx
  bool v46; // zf
  char *v47; // rcx
  signed __int32 v48[8]; // [rsp+0h] [rbp-98h] BYREF
  struct _SLIST_ENTRY *v49; // [rsp+20h] [rbp-78h] BYREF
  __int64 v50; // [rsp+28h] [rbp-70h]
  __int64 v51; // [rsp+30h] [rbp-68h]
  char *v52; // [rsp+38h] [rbp-60h] BYREF
  int v53; // [rsp+40h] [rbp-58h]
  int v56; // [rsp+B0h] [rbp+18h]

  v51 = -2;
  v5 = a2;
  v6 = this;
  v7 = dword_100720F58;
  v56 = dword_100720F58;
  v8 = a3;
  v50 = a3;
  v9 = a5;
  while ( 1 )
  {
    v10 = 0;
    v11 = (union _SLIST_HEADER *)(*((_QWORD *)v6 + 10) + (v8 << *((_BYTE *)v6 + 92)));
    v12 = InterlockedPopEntrySList(v11);
    v13 = 0;
    if ( v12 )
      v13 = (unsigned __int8 *)v12;
    if ( !v9 )
      break;
    if ( v13 )
    {
      v18 = 0;
      a5 = 0;
      v19 = 0;
      do
      {
        v20 = (struct _SLIST_ENTRY *)v13;
        v21 = v13;
        v22 = *((_QWORD *)v13 + 5);
        if ( (unsigned __int64)v9 >= v22 )
        {
          v23 = v19;
          if ( (unsigned __int64)v9 < v22 + 0x1000000 )
            break;
        }
        *(_QWORD *)v13 = v18;
        v18 = v13;
        v13 = 0;
        v24 = InterlockedPopEntrySList(v11);
        if ( v24 )
          v13 = (unsigned __int8 *)v24;
        v19 = (struct _SLIST_ENTRY *)v21;
        v23 = v20;
      }
      while ( v13 );
      a5 = v18;
      if ( v23 )
      {
        v25 = &a5;
        v26 = (unsigned __int8 *)v23;
        while ( 1 )
        {
          v27 = *(unsigned __int8 **)v26;
          if ( v26 == (unsigned __int8 *)v23 )
            break;
          v25 = (unsigned __int8 **)v26;
          v26 = *(unsigned __int8 **)v26;
          if ( !v27 )
            goto LABEL_25;
        }
        *v25 = v27;
        *(_QWORD *)v26 = 0;
        v18 = a5;
        do
        {
LABEL_25:
          InterlockedPushEntrySList(v11, v23);
          v23 = (struct _SLIST_ENTRY *)v18;
          if ( v18 )
          {
            v28 = &a5;
            v29 = v18;
            while ( 1 )
            {
              v30 = *(unsigned __int8 **)v29;
              if ( v29 == v18 )
                break;
              v28 = (unsigned __int8 **)v29;
              v29 = *(unsigned __int8 **)v29;
              if ( !v30 )
                goto LABEL_29;
            }
            *v28 = v30;
            *(_QWORD *)v29 = 0;
            v18 = a5;
          }
LABEL_29:
          ;
        }
        while ( v23 );
      }
      v5 = a2;
      v8 = v50;
      v6 = this;
      break;
    }
LABEL_6:
    if ( v7 == 1 )
      goto LABEL_12;
    if ( v5 )
    {
      v13 = 0;
      v14 = (union _SLIST_HEADER *)((char *)v6 + 64);
      v15 = InterlockedPopEntrySList((PSLIST_HEADER)v6 + 4);
      if ( v15 )
        v13 = (unsigned __int8 *)v15;
      if ( v9 )
      {
        if ( !v13 )
          goto LABEL_69;
        v31 = 0;
        v49 = 0;
        v16 = 0;
        do
        {
          v32 = (struct _SLIST_ENTRY *)v13;
          v33 = v13;
          v34 = *((_QWORD *)v13 + 5);
          if ( (unsigned __int64)v9 >= v34 )
          {
            v35 = v16;
            if ( (unsigned __int64)v9 < v34 + 0x1000000 )
              break;
          }
          *(_QWORD *)v13 = v31;
          v31 = (struct _SLIST_ENTRY *)v13;
          v13 = 0;
          v36 = InterlockedPopEntrySList(v14);
          if ( v36 )
            v13 = (unsigned __int8 *)v36;
          v16 = (struct _SLIST_ENTRY *)v33;
          v35 = v32;
        }
        while ( v13 );
        v49 = v31;
        if ( v35 )
        {
          v37 = (struct _SLIST_ENTRY *)&v49;
          v38 = v35;
          while ( 1 )
          {
            Next = v38->Next;
            if ( v38 == v35 )
              break;
            v37 = v38;
            v38 = v38->Next;
            if ( !Next )
              goto LABEL_44;
          }
          v37->Next = Next;
          v38->Next = 0;
          v31 = v49;
          do
          {
LABEL_44:
            InterlockedPushEntrySList(v14, v35);
            v35 = v31;
            if ( v31 )
            {
              p_Next = &v49;
              v41 = v31;
              while ( 1 )
              {
                v16 = v41->Next;
                if ( v41 == v31 )
                  break;
                p_Next = &v41->Next;
                v41 = v41->Next;
                if ( !v16 )
                  goto LABEL_48;
              }
              *p_Next = v16;
              v41->Next = 0;
              v31 = v49;
            }
LABEL_48:
            ;
          }
          while ( v35 );
        }
        v6 = this;
      }
      if ( v13 )
        goto LABEL_12;
      if ( v9 )
      {
LABEL_69:
        *a4 = v13;
        return 0;
      }
      v52 = (char *)v6 + 96;
      v53 = 0;
      if ( !(unsigned int)SOS_MemoryTopLevelBlockAllocator::AcquireMutexNoAbort(v16, &v52) )
      {
        if ( QueryDepthSList(v11) || QueryDepthSList(v14) )
        {
          v10 = 1;
        }
        else
        {
          v10 = 1;
          Fragment = SOS_MemoryFragmentManager::AllocateFragment(&SOS_MemoryFragmentManager::sm_MemoryFragmentManager);
          v43 = (struct _SLIST_ENTRY *)Fragment;
          if ( Fragment )
          {
            if ( !SOS_MemoryTopLevelBlockAllocator::InitDescriptorList(v6, Fragment) )
              InterlockedPushEntrySList(&SOS_MemoryFragmentManager::sm_MemoryFragmentManager, v43);
          }
          else
          {
            v10 = 0;
          }
        }
      }
      v44 = v53;
      if ( v53 )
      {
        v45 = v52;
        do
        {
          v46 = (*((_QWORD *)v45 + 8))-- == 1;
          if ( v46 )
          {
            _InterlockedOr(v48, 0);
            v47 = v52;
            *((_QWORD *)v52 + 6) = 0;
            *((_QWORD *)v47 + 7) = 0;
            EventAutoInternal<SuspendQueueSLock>::Signal(v47, 0);
            v44 = v53;
          }
          v46 = v44-- == 1;
          v53 = v44;
        }
        while ( !v46 );
      }
      v7 = v56;
      v5 = a2;
    }
    if ( !v10 )
      goto LABEL_12;
    v8 = v50;
  }
  if ( !v13 )
    goto LABEL_6;
  _InterlockedExchangeAdd64(
    (volatile signed __int64 *)(*((_QWORD *)v6 + 10) + (v8 << *((_BYTE *)v6 + 92)) + 24),
    0xFFFFFFFFFFFFFFFFuLL);
LABEL_12:
  *a4 = v13;
  if ( v13 )
    return (void *)*((_QWORD *)v13 + 5);
  return 0;
}

```

## disassembly

```asm
0x1004378f0  mov     [rsp+arg_18], r9
0x1004378f5  mov     [rsp+arg_8], dl
0x1004378f9  mov     [rsp+arg_0], rcx
0x1004378fe  push    rbx
0x1004378ff  push    rbp
0x100437900  push    rsi
0x100437901  push    rdi
0x100437902  push    r12
0x100437904  push    r13
0x100437906  push    r14
0x100437908  push    r15
0x10043790a  sub     rsp, 58h
0x10043790e  mov     [rsp+98h+var_68], 0FFFFFFFFFFFFFFFEh
0x100437917  movzx   esi, dl
0x10043791a  mov     rbp, rcx
0x10043791d  mov     r14d, cs:dword_100720F58
0x100437924  mov     [rsp+98h+arg_10], r14d
0x10043792c  movzx   ebx, r8w
0x100437930  mov     [rsp+98h+var_70], rbx
0x100437935  mov     r15, [rsp+98h+arg_20]
0x10043793d  nop     dword ptr [rax]
0x100437940  xor     r13b, r13b
0x100437943  movzx   ecx, byte ptr [rbp+5Ch]
0x100437947  mov     r12, rbx
0x10043794a  shl     r12, cl
0x10043794d  add     r12, [rbp+50h]
0x100437951  mov     rcx, r12; ListHead
0x100437954  call    cs:__imp_InterlockedPopEntrySList
0x10043795a  xor     edi, edi
0x10043795c  test    rax, rax
0x10043795f  cmovnz  rdi, rax
0x100437963  test    r15, r15
0x100437966  jnz     loc_1004A670E
0x10043796c  test    rdi, rdi
0x10043796f  jnz     loc_1004A6A16
0x100437975  cmp     r14d, 1
0x100437979  jz      short loc_1004379AC
0x10043797b  test    sil, sil
0x10043797e  jz      loc_1004A69DB
0x100437984  xor     edi, edi
0x100437986  lea     r14, [rbp+40h]
0x10043798a  mov     rcx, r14; ListHead
0x10043798d  call    cs:__imp_InterlockedPopEntrySList
0x100437993  test    rax, rax
0x100437996  cmovnz  rdi, rax
0x10043799a  test    r15, r15
0x10043799d  jnz     loc_1004A681C
0x1004379a3  test    rdi, rdi
0x1004379a6  jz      loc_1004A6909
0x1004379ac  mov     rax, [rsp+98h+arg_18]
0x1004379b4  mov     [rax], rdi
0x1004379b7  test    rdi, rdi
0x1004379ba  jz      loc_1004A6A0E
0x1004379c0  mov     rax, [rdi+28h]
0x1004379c4  jmp     short loc_1004379C7
0x1004379c7  add     rsp, 58h
0x1004379cb  pop     r15
0x1004379cd  pop     r14
0x1004379cf  pop     r13
0x1004379d1  pop     r12
0x1004379d3  pop     rdi
0x1004379d4  pop     rsi
0x1004379d5  pop     rbp
0x1004379d6  pop     rbx
0x1004379d7  retn
0x1004a670e  test    rdi, rdi
0x1004a6711  jz      loc_100437975
0x1004a6717  xor     ebx, ebx
0x1004a6719  mov     [rsp+98h+arg_20], rbx
0x1004a6721  xor     ecx, ecx
0x1004a6723  mov     rsi, rdi
0x1004a6726  mov     rbp, rdi
0x1004a6729  mov     rax, [rdi+28h]
0x1004a672d  cmp     r15, rax
0x1004a6730  jb      short loc_1004A6740
0x1004a6732  mov     rdx, rcx
0x1004a6735  add     rax, 1000000h
0x1004a673b  cmp     r15, rax
0x1004a673e  jb      short loc_1004A6763
0x1004a6740  mov     [rdi], rbx
0x1004a6743  mov     rbx, rdi
0x1004a6746  xor     edi, edi
0x1004a6748  mov     rcx, r12; ListHead
0x1004a674b  call    cs:__imp_InterlockedPopEntrySList
0x1004a6751  test    rax, rax
0x1004a6754  cmovnz  rdi, rax
0x1004a6758  mov     rcx, rbp
0x1004a675b  mov     rdx, rsi; ListEntry
0x1004a675e  test    rdi, rdi
0x1004a6761  jnz     short loc_1004A6723
0x1004a6763  mov     [rsp+98h+arg_20], rbx
0x1004a676b  test    rdx, rdx
0x1004a676e  jz      short loc_1004A67DB
0x1004a6770  lea     r8, [rsp+98h+arg_20]
0x1004a6778  mov     rax, rdx
0x1004a677b  nop     dword ptr [rax+rax+00h]
0x1004a6780  mov     rcx, [rax]
0x1004a6783  cmp     rax, rdx
0x1004a6786  jz      short loc_1004A67F6
0x1004a6788  mov     r8, rax
0x1004a678b  mov     rax, rcx
0x1004a678e  test    rcx, rcx
0x1004a6791  jnz     short loc_1004A6780
0x1004a6793  jmp     short loc_1004A6796
0x1004a6796  xor     esi, esi
0x1004a6798  nop     dword ptr [rax+rax+00000000h]
0x1004a67a0  mov     rcx, r12; ListHead
0x1004a67a3  call    cs:__imp_InterlockedPushEntrySList
0x1004a67a9  mov     rdx, rbx
0x1004a67ac  test    rbx, rbx
0x1004a67af  jz      short loc_1004A67D6
0x1004a67b1  lea     r8, [rsp+98h+arg_20]
0x1004a67b9  mov     rax, rbx
0x1004a67bc  nop     dword ptr [rax+00h]
0x1004a67c0  mov     rcx, [rax]
0x1004a67c3  cmp     rax, rbx
0x1004a67c6  jz      short loc_1004A680B
0x1004a67c8  mov     r8, rax
0x1004a67cb  mov     rax, rcx
0x1004a67ce  test    rcx, rcx
0x1004a67d1  jnz     short loc_1004A67C0
0x1004a67d3  jmp     short loc_1004A67D6
0x1004a67d6  test    rdx, rdx
0x1004a67d9  jnz     short loc_1004A67A0
0x1004a67db  movzx   esi, [rsp+98h+arg_8]
0x1004a67e3  mov     rbx, [rsp+98h+var_70]
0x1004a67e8  mov     rbp, [rsp+98h+arg_0]
0x1004a67f0  jmp     loc_10043796C
0x1004a67f6  mov     [r8], rcx
0x1004a67f9  mov     qword ptr [rax], 0
0x1004a6800  mov     rbx, [rsp+98h+arg_20]
0x1004a6808  jmp     short loc_1004A6796
0x1004a680b  mov     [r8], rcx
0x1004a680e  mov     [rax], rsi
0x1004a6811  mov     rbx, [rsp+98h+arg_20]
0x1004a6819  jmp     short loc_1004A67D6
0x1004a681c  test    rdi, rdi
0x1004a681f  jz      loc_1004A6A03
0x1004a6825  xor     ebx, ebx
0x1004a6827  mov     [rsp+98h+var_78], rbx
0x1004a682c  xor     ecx, ecx
0x1004a682e  xchg    ax, ax
0x1004a6830  mov     rsi, rdi
0x1004a6833  mov     rbp, rdi
0x1004a6836  mov     rax, [rdi+28h]
0x1004a683a  cmp     r15, rax
0x1004a683d  jb      short loc_1004A684D
0x1004a683f  mov     rdx, rcx
0x1004a6842  add     rax, 1000000h
0x1004a6848  cmp     r15, rax
0x1004a684b  jb      short loc_1004A6870
0x1004a684d  mov     [rdi], rbx
0x1004a6850  mov     rbx, rdi
0x1004a6853  xor     edi, edi
0x1004a6855  mov     rcx, r14; ListHead
0x1004a6858  call    cs:__imp_InterlockedPopEntrySList
0x1004a685e  test    rax, rax
0x1004a6861  cmovnz  rdi, rax
0x1004a6865  mov     rcx, rbp
0x1004a6868  mov     rdx, rsi; ListEntry
0x1004a686b  test    rdi, rdi
0x1004a686e  jnz     short loc_1004A6830
0x1004a6870  mov     [rsp+98h+var_78], rbx
0x1004a6875  test    rdx, rdx
0x1004a6878  jz      short loc_1004A68DB
0x1004a687a  lea     r8, [rsp+98h+var_78]
0x1004a687f  mov     rax, rdx
0x1004a6882  mov     rcx, [rax]
0x1004a6885  cmp     rax, rdx
0x1004a6888  jz      short loc_1004A68E9
0x1004a688a  mov     r8, rax
0x1004a688d  mov     rax, rcx
0x1004a6890  test    rcx, rcx
0x1004a6893  jnz     short loc_1004A6882
0x1004a6895  jmp     short loc_1004A6898
0x1004a6898  xor     esi, esi
0x1004a689a  nop     word ptr [rax+rax+00h]
0x1004a68a0  mov     rcx, r14; ListHead
0x1004a68a3  call    cs:__imp_InterlockedPushEntrySList
0x1004a68a9  mov     rdx, rbx
0x1004a68ac  test    rbx, rbx
0x1004a68af  jz      short loc_1004A68D6
0x1004a68b1  lea     r8, [rsp+98h+var_78]
0x1004a68b6  mov     rax, rbx
0x1004a68b9  nop     dword ptr [rax+00000000h]
0x1004a68c0  mov     rcx, [rax]
0x1004a68c3  cmp     rax, rbx
0x1004a68c6  jz      short loc_1004A68FB
0x1004a68c8  mov     r8, rax
0x1004a68cb  mov     rax, rcx
0x1004a68ce  test    rcx, rcx
0x1004a68d1  jnz     short loc_1004A68C0
0x1004a68d3  jmp     short loc_1004A68D6
0x1004a68d6  test    rdx, rdx
0x1004a68d9  jnz     short loc_1004A68A0
0x1004a68db  mov     rbp, [rsp+98h+arg_0]
0x1004a68e3  jmp     loc_1004379A3
0x1004a68e9  mov     [r8], rcx
0x1004a68ec  mov     qword ptr [rax], 0
0x1004a68f3  mov     rbx, [rsp+98h+var_78]
0x1004a68f8  jmp     short loc_1004A6898
0x1004a68fb  mov     [r8], rcx
0x1004a68fe  mov     [rax], rsi
0x1004a6901  mov     rbx, [rsp+98h+var_78]
0x1004a6906  jmp     short loc_1004A68D6
0x1004a6909  test    r15, r15
0x1004a690c  jnz     loc_1004A6A03
0x1004a6912  lea     rax, [rbp+60h]
0x1004a6916  mov     [rsp+98h+var_60], rax
0x1004a691b  mov     [rsp+98h+var_58], r15d
0x1004a6920  lea     rdx, [rsp+98h+var_60]
0x1004a6925  call    ?AcquireMutexNoAbort@SOS_MemoryTopLevelBlockAllocator@@AEAA?AW4SOS_RESULT@@PEAV?$TAutoMutex@VSOS_RecursiveMutex@@$0PPPPPPPP@@@@Z; SOS_MemoryTopLevelBlockAllocator::AcquireMutexNoAbort(TAutoMutex<SOS_RecursiveMutex,4294967295> *)
0x1004a692a  test    eax, eax
0x1004a692c  jnz     short loc_1004A698F
0x1004a692e  mov     rcx, r12; ListHead
0x1004a6931  call    cs:__imp_QueryDepthSList
0x1004a6937  test    ax, ax
0x1004a693a  jnz     loc_1004A69FD
0x1004a6940  mov     rcx, r14; ListHead
0x1004a6943  call    cs:__imp_QueryDepthSList
0x1004a6949  test    ax, ax
0x1004a694c  jnz     loc_1004A69FD
0x1004a6952  mov     r13b, 1
0x1004a6955  lea     rcx, ?sm_MemoryFragmentManager@SOS_MemoryFragmentManager@@2V1@A; ListHead
0x1004a695c  call    ?AllocateFragment@SOS_MemoryFragmentManager@@QEAAPEAVSOS_MemoryFragmentDescriptor@@XZ; SOS_MemoryFragmentManager::AllocateFragment(void)
0x1004a6961  mov     rbx, rax
0x1004a6964  test    rax, rax
0x1004a6967  jz      loc_1004A69F8
0x1004a696d  mov     rdx, rax; struct SOS_MemoryFragmentDescriptor *
0x1004a6970  mov     rcx, rbp; this
0x1004a6973  call    ?InitDescriptorList@SOS_MemoryTopLevelBlockAllocator@@AEAA_NPEAVSOS_MemoryFragmentDescriptor@@@Z; SOS_MemoryTopLevelBlockAllocator::InitDescriptorList(SOS_MemoryFragmentDescriptor *)
0x1004a6978  test    al, al
0x1004a697a  jnz     short loc_1004A698F
0x1004a697c  mov     rdx, rbx; ListEntry
0x1004a697f  lea     rcx, ?sm_MemoryFragmentManager@SOS_MemoryFragmentManager@@2V1@A; ListHead
0x1004a6986  call    cs:__imp_InterlockedPushEntrySList
0x1004a698c  jmp     short loc_1004A698F
0x1004a698f  mov     eax, [rsp+98h+var_58]
0x1004a6993  test    eax, eax
0x1004a6995  jz      short loc_1004A69CB
0x1004a6997  mov     rbx, [rsp+98h+var_60]
0x1004a699c  sub     qword ptr [rbx+40h], 1
0x1004a69a1  jnz     short loc_1004A69C2
0x1004a69a3  lock or [rsp+98h+var_98], 0
0x1004a69a8  mov     rcx, [rsp+98h+var_60]
0x1004a69ad  xor     eax, eax
0x1004a69af  mov     [rcx+30h], rax
0x1004a69b3  mov     [rcx+38h], rax
0x1004a69b7  xor     edx, edx
0x1004a69b9  call    ?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z; EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)
0x1004a69be  mov     eax, [rsp+98h+var_58]
0x1004a69c2  add     eax, 0FFFFFFFFh
0x1004a69c5  mov     [rsp+98h+var_58], eax
0x1004a69c9  jnz     short loc_1004A699C
0x1004a69cb  mov     r14d, [rsp+98h+arg_10]
0x1004a69d3  movzx   esi, [rsp+98h+arg_8]
0x1004a69db  test    rdi, rdi
0x1004a69de  jnz     loc_1004379AC
0x1004a69e4  test    r13b, r13b
0x1004a69e7  jz      loc_1004379AC
0x1004a69ed  mov     rbx, [rsp+98h+var_70]
0x1004a69f2  jmp     loc_100437940
0x1004a69f8  xor     r13b, r13b
0x1004a69fb  jmp     short loc_1004A698F
0x1004a69fd  mov     r13b, 1
0x1004a6a00  jmp     short loc_1004A698F
0x1004a6a03  mov     rax, [rsp+98h+arg_18]
0x1004a6a0b  mov     [rax], rdi
0x1004a6a0e  xor     eax, eax
0x1004a6a10  jmp     loc_1004379C7
0x1004a6a16  movzx   ecx, byte ptr [rbp+5Ch]
0x1004a6a1a  shl     rbx, cl
0x1004a6a1d  add     rbx, [rbp+50h]
0x1004a6a21  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1004a6a28  lock xadd [rbx+18h], rax
0x1004a6a2e  jmp     loc_1004379AC
```
