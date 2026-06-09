# CVolumeManager::AddNodeToLinkedList(CVolumeNode *)

- ea: `0x18000c330`
- end: `0x18000c3cb`
- name: `?AddNodeToLinkedList@CVolumeManager@@AEAAXPEAVCVolumeNode@@@Z`
- size: `155`
- prototype: `void __fastcall(CVolumeManager *__hidden this, struct CVolumeNode *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800090c8`

## callees

- `0x18000c330`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c354`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c354`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c3b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c3b5`

## pseudocode

```c
void __fastcall CVolumeManager::AddNodeToLinkedList(CVolumeManager *this, struct CVolumeNode *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  unsigned __int64 v5; // rax
  _QWORD *v6; // rcx

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 208);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  v5 = *((_QWORD *)this + 25);
  if ( !v5 )
  {
    *((_QWORD *)a2 + 1) = 0;
LABEL_5:
    *((_QWORD *)this + 25) = a2;
    goto LABEL_11;
  }
  if ( (unsigned __int64)a2 < v5 )
  {
    *((_QWORD *)a2 + 1) = v5;
    goto LABEL_5;
  }
  do
  {
    v6 = (_QWORD *)(v5 + 8);
    v5 = *(_QWORD *)(v5 + 8);
    if ( !v5 )
    {
      *v6 = a2;
      *((_QWORD *)a2 + 1) = 0;
      goto LABEL_11;
    }
  }
  while ( v5 < (unsigned __int64)a2 );
  *((_QWORD *)a2 + 1) = v5;
  *v6 = a2;
LABEL_11:
  LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x18000c330  mov     [rsp+arg_8], rbx
0x18000c335  mov     [rsp+arg_10], rsi
0x18000c33a  push    rdi
0x18000c33b  sub     rsp, 20h
0x18000c33f  mov     rbx, rdx
0x18000c342  mov     rdi, rcx
0x18000c345  lea     rsi, [rcx+0D0h]
0x18000c34c  mov     [rsp+28h+arg_0], rsi
0x18000c351  mov     rcx, rsi; lpCriticalSection
0x18000c354  call    cs:__imp_EnterCriticalSection
0x18000c35a  nop
0x18000c35b  mov     rax, [rdi+0C8h]
0x18000c362  test    rax, rax
0x18000c365  jnz     short loc_18000C36D
0x18000c367  mov     [rbx+8], rax
0x18000c36b  jmp     short loc_18000C376
0x18000c36d  cmp     rbx, rax
0x18000c370  jnb     short loc_18000C37F
0x18000c372  mov     [rbx+8], rax
0x18000c376  mov     [rdi+0C8h], rbx
0x18000c37d  jmp     short loc_18000C3AB
0x18000c37f  lea     rcx, [rax+8]
0x18000c383  mov     rax, [rcx]
0x18000c386  test    rax, rax
0x18000c389  jz      short loc_18000C397
0x18000c38b  cmp     rax, rbx
0x18000c38e  jnb     short loc_18000C392
0x18000c390  jmp     short loc_18000C37F
0x18000c392  test    rax, rax
0x18000c395  jnz     short loc_18000C3A4
0x18000c397  mov     [rcx], rbx
0x18000c39a  mov     qword ptr [rbx+8], 0
0x18000c3a2  jmp     short loc_18000C3AB
0x18000c3a4  mov     [rbx+8], rax
0x18000c3a8  mov     [rcx], rbx
0x18000c3ab  jmp     short loc_18000C3B2
0x18000c3ad  mov     rsi, [rsp+28h+arg_0]
0x18000c3b2  mov     rcx, rsi; lpCriticalSection
0x18000c3b5  call    cs:__imp_LeaveCriticalSection
0x18000c3bb  mov     rbx, [rsp+28h+arg_8]
0x18000c3c0  mov     rsi, [rsp+28h+arg_10]
0x18000c3c5  add     rsp, 20h
0x18000c3c9  pop     rdi
0x18000c3ca  retn
```
