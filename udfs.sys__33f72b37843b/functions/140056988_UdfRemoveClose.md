# UdfRemoveClose

- ea: `0x140056988`
- end: `0x140056af2`
- name: `UdfRemoveClose`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008790`

## callees

- `0x140056988`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005699e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005699e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140056a08`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140056a08`

## pseudocode

```c
__int64 *__fastcall UdfRemoveClose(__int64 a1)
{
  __int64 *v2; // rdi
  __int64 *i; // rax
  __int64 *j; // rdx
  __int64 v6; // rax
  __int64 *v7; // rcx
  __int64 v8; // rdx
  __int64 *v9; // r8

  v2 = 0;
  ExAcquireFastMutexUnsafe(&FastMutex);
  qword_140025B78 = (__int64)KeGetCurrentThread();
  for ( i = (__int64 *)qword_140025B40; ; i = (__int64 *)*i )
  {
    if ( i == &qword_140025B40 )
      goto LABEL_3;
    if ( !a1 || *(i - 7) == a1 )
      break;
  }
  v8 = *i;
  if ( *(__int64 **)(*i + 8) != i )
    goto LABEL_26;
  v9 = (__int64 *)i[1];
  if ( (__int64 *)*v9 != i )
    goto LABEL_26;
  *v9 = v8;
  v2 = i - 9;
  *(_QWORD *)(v8 + 8) = v9;
  --dword_140025B50;
  if ( i != (__int64 *)72 )
    goto LABEL_6;
LABEL_3:
  if ( !a1 && (!HIBYTE(word_140025B54) || dword_140025B68 <= (unsigned int)dword_140025B70) )
    goto LABEL_14;
  for ( j = (__int64 *)qword_140025B58; ; j = (__int64 *)*j )
  {
    if ( j == &qword_140025B58 )
      goto LABEL_6;
    if ( !a1 || *(_QWORD *)(*(_QWORD *)(*(j - 1) + 136) + 8LL) == a1 )
      break;
  }
  v6 = *j;
  if ( *(__int64 **)(*j + 8) != j || (v7 = (__int64 *)j[1], (__int64 *)*v7 != j) )
LABEL_26:
    __fastfail(3u);
  *v7 = v6;
  v2 = j - 2;
  *(_QWORD *)(v6 + 8) = v7;
  --dword_140025B68;
LABEL_6:
  if ( !a1 && !v2 )
LABEL_14:
    word_140025B54 = 0;
  qword_140025B78 = 0;
  ExReleaseFastMutexUnsafe(&FastMutex);
  return v2;
}

```

## disassembly

```asm
0x140056988  mov     [rsp+arg_0], rbx
0x14005698d  push    rdi
0x14005698e  sub     rsp, 20h
0x140056992  mov     rbx, rcx
0x140056995  xor     edi, edi
0x140056997  lea     rcx, FastMutex; FastMutex
0x14005699e  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400569a5  nop     dword ptr [rax+rax+00h]
0x1400569aa  mov     rax, gs:188h
0x1400569b3  mov     cs:qword_140025B78, rax
0x1400569ba  mov     rax, cs:qword_140025B40
0x1400569c1  lea     rcx, qword_140025B40
0x1400569c8  or      r9d, 0FFFFFFFFh
0x1400569cc  cmp     rax, rcx
0x1400569cf  jnz     loc_140056AD4
0x1400569d5  test    rbx, rbx
0x1400569d8  jz      short loc_140056A56
0x1400569da  mov     rdx, cs:qword_140025B58
0x1400569e1  lea     rax, qword_140025B58
0x1400569e8  cmp     rdx, rax
0x1400569eb  jnz     short loc_140056A23
0x1400569ed  test    rbx, rbx
0x1400569f0  jz      loc_140056A7F
0x1400569f6  lea     rcx, FastMutex; FastMutex
0x1400569fd  mov     cs:qword_140025B78, 0
0x140056a08  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140056a0f  nop     dword ptr [rax+rax+00h]
0x140056a14  mov     rbx, [rsp+28h+arg_0]
0x140056a19  mov     rax, rdi
0x140056a1c  add     rsp, 20h
0x140056a20  pop     rdi
0x140056a21  retn
0x140056a23  test    rbx, rbx
0x140056a26  jnz     short loc_140056A8A
0x140056a28  mov     rax, [rdx]
0x140056a2b  cmp     [rax+8], rdx
0x140056a2f  jnz     loc_140056AEB
0x140056a35  mov     rcx, [rdx+8]
0x140056a39  cmp     [rcx], rdx
0x140056a3c  jnz     loc_140056AEB
0x140056a42  mov     [rcx], rax
0x140056a45  lea     rdi, [rdx-10h]
0x140056a49  mov     [rax+8], rcx
0x140056a4d  add     cs:dword_140025B68, r9d
0x140056a54  jmp     short loc_1400569ED
0x140056a56  cmp     byte ptr cs:word_140025B54+1, 0
0x140056a5d  jz      short loc_140056A71
0x140056a5f  mov     eax, cs:dword_140025B70
0x140056a65  cmp     cs:dword_140025B68, eax
0x140056a6b  ja      loc_1400569DA
0x140056a71  mov     cs:word_140025B54, 0
0x140056a7a  jmp     loc_1400569F6
0x140056a7f  test    rdi, rdi
0x140056a82  jnz     loc_1400569F6
0x140056a88  jmp     short loc_140056A71
0x140056a8a  mov     rax, [rdx-8]
0x140056a8e  mov     rcx, [rax+88h]
0x140056a95  cmp     [rcx+8], rbx
0x140056a99  jz      short loc_140056A28
0x140056a9b  mov     rdx, [rdx]
0x140056a9e  jmp     loc_1400569E1
0x140056aa3  mov     rdx, [rax]
0x140056aa6  cmp     [rdx+8], rax
0x140056aaa  jnz     short loc_140056AEB
0x140056aac  mov     r8, [rax+8]
0x140056ab0  cmp     [r8], rax
0x140056ab3  jnz     short loc_140056AEB
0x140056ab5  mov     [r8], rdx
0x140056ab8  mov     rdi, rcx
0x140056abb  mov     [rdx+8], r8
0x140056abf  add     cs:dword_140025B50, r9d
0x140056ac6  test    rcx, rcx
0x140056ac9  jnz     loc_1400569ED
0x140056acf  jmp     loc_1400569D5
0x140056ad4  lea     rcx, [rax-48h]
0x140056ad8  test    rbx, rbx
0x140056adb  jz      short loc_140056AA3
0x140056add  cmp     [rcx+10h], rbx
0x140056ae1  jz      short loc_140056AA3
0x140056ae3  mov     rax, [rax]
0x140056ae6  jmp     loc_1400569C1
0x140056aeb  mov     ecx, 3
0x140056af0  int     29h; Win8: RtlFailFast(ecx)
```
