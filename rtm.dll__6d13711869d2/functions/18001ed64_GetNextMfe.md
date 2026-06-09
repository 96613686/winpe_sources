# GetNextMfe

- ea: `0x18001ed64`
- end: `0x18001f094`
- name: `GetNextMfe`
- size: `816`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: ``

## callers

- `0x180012d80`
- `0x180012ed0`
- `0x180013260`
- `0x180013390`

## callees

- `0x180014bfc`
- `0x180014d2c`
- `0x180015100`
- `0x180015178`
- `0x18001dc28`
- `0x18001dd8c`
- `0x18001de20`
- `0x18001e374`
- `0x18001e4b0`
- `0x18001e5a0`
- `0x18001ed64`
- `0x18001f474`

## pseudocode

```c
__int64 __fastcall GetNextMfe(unsigned int *a1, unsigned int *a2, _DWORD *a3, _DWORD *a4, int a5, int a6)
{
  unsigned int v9; // edx
  __int64 v10; // rbx
  char *v11; // rbp
  __int64 GroupEntry; // rax
  __int64 *v13; // rdi
  int v14; // ebp
  int v15; // r8d
  int v16; // eax
  unsigned int v17; // ebx
  unsigned int v18; // r12d
  unsigned int v19; // esi
  _DWORD *v20; // r15
  int v21; // r8d
  __int64 *v22; // r13
  unsigned int v23; // edx
  int v24; // r8d
  __int64 v25; // rsi
  unsigned int v26; // ebp
  unsigned int v27; // r15d
  _DWORD *v28; // r12
  int v29; // eax
  int v30; // r14d
  int v31; // r14d
  unsigned int v32; // r14d
  _QWORD v34[11]; // [rsp+30h] [rbp-58h] BYREF
  __int64 *v35; // [rsp+90h] [rbp+8h] BYREF
  unsigned int *v36; // [rsp+98h] [rbp+10h]
  _DWORD *v37; // [rsp+A0h] [rbp+18h]
  _DWORD *v38; // [rsp+A8h] [rbp+20h]

  v38 = a4;
  v37 = a3;
  v36 = a2;
  if ( *a1 )
    v9 = *a1 % (dword_18002B930 - 1) + 1;
  else
    v9 = 0;
  v10 = 32LL * v9;
  AcquireReadLock((char *)qword_18002BA40 + v10 + 16);
  AcquireWriteLock(&qword_18002BA10);
  MergeTempAndMasterGroupLists(&qword_18002BA00);
  AcquireReadLock(&qword_18002BA30);
  ReleaseWriteLock((__int64)&qword_18002BA10);
  v11 = (char *)qword_18002BA40 + v10;
  GroupEntry = GetGroupEntry((char *)qword_18002BA40 + v10, *a1);
  v35 = (__int64 *)GroupEntry;
  v13 = (__int64 *)GroupEntry;
  if ( GroupEntry )
  {
    AcquireWriteLock((_QWORD *)(GroupEntry + 40));
    ReleaseReadLock((__int64)qword_18002BA40 + v10 + 16);
    v14 = a5;
  }
  else
  {
    ReleaseReadLock((__int64)(v11 + 16));
    v16 = FindGroupEntry((unsigned int)&qword_18002BA20, *a1, v15, (unsigned int)&v35, 0);
    v13 = v35;
    if ( !v16 && !v35 )
    {
LABEL_8:
      v17 = 259;
      goto LABEL_47;
    }
    AcquireWriteLock(v35 + 5);
    v14 = 1;
  }
  v18 = *a2;
  LODWORD(v35) = *a2;
  *a4 = 0;
  if ( v14 )
    v19 = 0;
  else
    v19 = a1[1];
  v20 = v38;
  while ( 1 )
  {
    v34[0] = 0;
    v17 = 234;
    MergeTempAndMasterSourceLists((__int64)v13);
    v22 = v13 + 9;
    if ( v19 )
      v23 = v19 % (dword_18002B934 - 1) + 1;
    else
      v23 = 0;
    if ( (unsigned int)FindSourceEntry((unsigned int)v13 + 16 * v23 + 88, v19, v21, (unsigned int)v34, 1) )
    {
      if ( v14 )
        v25 = v34[0];
      else
        v25 = *(_QWORD *)v34[0];
    }
    else
    {
      v34[0] = 0;
      FindSourceEntry((_DWORD)v13 + 72, 0, v24, (unsigned int)v34, 0);
      v25 = v34[0];
      v26 = 0;
      if ( !v34[0] )
        goto LABEL_41;
    }
    v26 = 0;
    if ( (__int64 *)v25 != v22 )
    {
      v27 = v18;
      v28 = v37;
      while ( 1 )
      {
        if ( *(_DWORD *)(v25 + 112) )
        {
          v29 = a6;
          v30 = *(_DWORD *)(v25 + 80);
          if ( a6 )
          {
            v31 = 28 * v30;
            if ( a6 == 1 )
              v32 = v31 + 64;
            else
              v32 = v31 + 84;
          }
          else
          {
            v32 = 16 * v30 + 60;
          }
          if ( v27 < v32 )
          {
            v20 = v38;
            v17 = 122;
            if ( !*v38 )
              v26 = v32;
LABEL_40:
            v18 = (unsigned int)v35;
            break;
          }
          if ( a6 && *(_DWORD *)(v25 + 144) )
          {
            GetMfeFromForwarder((__int64)v13, v25);
            v29 = a6;
          }
          CopyMfe((__int64)v13, v25, v28, v29);
          v27 -= v32;
          v26 += v32;
          v28 = (_DWORD *)((char *)v28 + v32);
          ++*v38;
        }
        v25 = *(_QWORD *)v25;
        if ( (__int64 *)v25 == v22 )
        {
          v20 = v38;
          goto LABEL_40;
        }
      }
    }
LABEL_41:
    ReleaseWriteLock((__int64)(v13 + 5));
    if ( v17 != 234 )
      break;
    v13 = (__int64 *)*v13;
    if ( v13 == &qword_18002BA20 )
      goto LABEL_8;
    v37 = (_DWORD *)((char *)v37 + v26);
    v18 -= v26;
    LODWORD(v35) = v18;
    AcquireWriteLock(v13 + 5);
    v19 = 0;
    v14 = 1;
  }
  if ( *v20 )
    v17 = 234;
  else
    *v36 = v26;
LABEL_47:
  ReleaseReadLock((__int64)&qword_18002BA30);
  return v17;
}

```

## disassembly

```asm
0x18001ed64  mov     [rsp+arg_18], r9
0x18001ed69  mov     [rsp+arg_10], r8
0x18001ed6e  mov     [rsp+arg_8], rdx
0x18001ed73  push    rbx
0x18001ed74  push    rbp
0x18001ed75  push    rsi
0x18001ed76  push    rdi
0x18001ed77  push    r12
0x18001ed79  push    r13
0x18001ed7b  push    r14
0x18001ed7d  push    r15
0x18001ed7f  sub     rsp, 48h
0x18001ed83  mov     eax, [rcx]
0x18001ed85  mov     r14, r9
0x18001ed88  mov     r15, rdx
0x18001ed8b  mov     rsi, rcx
0x18001ed8e  test    eax, eax
0x18001ed90  jz      short loc_18001EDA5
0x18001ed92  mov     r10d, cs:dword_18002B930
0x18001ed99  xor     edx, edx
0x18001ed9b  dec     r10d
0x18001ed9e  div     r10d
0x18001eda1  inc     edx
0x18001eda3  jmp     short loc_18001EDA7
0x18001eda5  xor     edx, edx
0x18001eda7  mov     rcx, cs:qword_18002BA40
0x18001edae  mov     ebx, edx
0x18001edb0  add     rcx, 10h
0x18001edb4  shl     rbx, 5
0x18001edb8  add     rcx, rbx
0x18001edbb  call    AcquireReadLock
0x18001edc0  lea     rcx, qword_18002BA10
0x18001edc7  call    AcquireWriteLock
0x18001edcc  lea     rcx, qword_18002BA00
0x18001edd3  call    MergeTempAndMasterGroupLists
0x18001edd8  lea     rcx, qword_18002BA30
0x18001eddf  call    AcquireReadLock
0x18001ede4  lea     rcx, qword_18002BA10
0x18001edeb  call    ReleaseWriteLock
0x18001edf0  mov     rbp, cs:qword_18002BA40
0x18001edf7  mov     edx, [rsi]
0x18001edf9  add     rbp, rbx
0x18001edfc  mov     rcx, rbp
0x18001edff  call    GetGroupEntry
0x18001ee04  mov     [rsp+88h+arg_0], rax
0x18001ee0c  mov     rdi, rax
0x18001ee0f  test    rax, rax
0x18001ee12  jz      short loc_18001EE39
0x18001ee14  lea     rcx, [rax+28h]
0x18001ee18  call    AcquireWriteLock
0x18001ee1d  mov     rcx, cs:qword_18002BA40
0x18001ee24  add     rcx, 10h
0x18001ee28  add     rcx, rbx
0x18001ee2b  call    ReleaseReadLock
0x18001ee30  mov     ebp, [rsp+88h+arg_20]
0x18001ee37  jmp     short loc_18001EE89
0x18001ee39  lea     rcx, [rbp+10h]
0x18001ee3d  call    ReleaseReadLock
0x18001ee42  mov     edx, [rsi]
0x18001ee44  lea     r9, [rsp+88h+arg_0]
0x18001ee4c  lea     rcx, qword_18002BA20
0x18001ee53  mov     [rsp+88h+var_68], 0
0x18001ee5b  call    FindGroupEntry
0x18001ee60  mov     rdi, [rsp+88h+arg_0]
0x18001ee68  test    eax, eax
0x18001ee6a  jnz     short loc_18001EE7B
0x18001ee6c  test    rdi, rdi
0x18001ee6f  jnz     short loc_18001EE7B
0x18001ee71  mov     ebx, 103h
0x18001ee76  jmp     loc_18001F075
0x18001ee7b  lea     rcx, [rdi+28h]
0x18001ee7f  call    AcquireWriteLock
0x18001ee84  mov     ebp, 1
0x18001ee89  mov     r12d, [r15]
0x18001ee8c  mov     dword ptr [rsp+88h+arg_0], r12d
0x18001ee94  mov     dword ptr [r14], 0
0x18001ee9b  test    ebp, ebp
0x18001ee9d  jz      short loc_18001EEA3
0x18001ee9f  xor     esi, esi
0x18001eea1  jmp     short loc_18001EEA6
0x18001eea3  mov     esi, [rsi+4]
0x18001eea6  mov     r15, [rsp+88h+arg_18]
0x18001eeae  mov     rcx, rdi
0x18001eeb1  mov     [rsp+88h+var_58], 0
0x18001eeba  mov     ebx, 0EAh
0x18001eebf  call    MergeTempAndMasterSourceLists
0x18001eec4  lea     r13, [rdi+48h]
0x18001eec8  test    esi, esi
0x18001eeca  jz      short loc_18001EEDE
0x18001eecc  mov     ecx, cs:dword_18002B934
0x18001eed2  xor     edx, edx
0x18001eed4  dec     ecx
0x18001eed6  mov     eax, esi
0x18001eed8  div     ecx
0x18001eeda  inc     edx
0x18001eedc  jmp     short loc_18001EEE0
0x18001eede  xor     edx, edx
0x18001eee0  mov     ecx, edx
0x18001eee2  lea     r9, [rsp+88h+var_58]
0x18001eee7  shl     rcx, 4
0x18001eeeb  mov     edx, esi
0x18001eeed  add     rcx, 58h ; 'X'
0x18001eef1  mov     [rsp+88h+var_68], 1
0x18001eef9  add     rcx, rdi
0x18001eefc  call    FindSourceEntry
0x18001ef01  test    eax, eax
0x18001ef03  jnz     short loc_18001EF33
0x18001ef05  lea     r9, [rsp+88h+var_58]
0x18001ef0a  mov     [rsp+88h+var_58], 0
0x18001ef13  xor     edx, edx
0x18001ef15  mov     [rsp+88h+var_68], eax
0x18001ef19  mov     rcx, r13
0x18001ef1c  call    FindSourceEntry
0x18001ef21  mov     rsi, [rsp+88h+var_58]
0x18001ef26  xor     ebp, ebp
0x18001ef28  test    rsi, rsi
0x18001ef2b  jz      loc_18001F00D
0x18001ef31  jmp     short loc_18001EF46
0x18001ef33  test    ebp, ebp
0x18001ef35  jnz     short loc_18001EF41
0x18001ef37  mov     rax, [rsp+88h+var_58]
0x18001ef3c  mov     rsi, [rax]
0x18001ef3f  jmp     short loc_18001EF46
0x18001ef41  mov     rsi, [rsp+88h+var_58]
0x18001ef46  xor     ebp, ebp
0x18001ef48  cmp     rsi, r13
0x18001ef4b  jz      loc_18001F00D
0x18001ef51  mov     r15d, r12d
0x18001ef54  mov     r12, [rsp+88h+arg_10]
0x18001ef5c  cmp     dword ptr [rsi+70h], 0
0x18001ef60  jz      short loc_18001EFDA
0x18001ef62  mov     eax, [rsp+88h+arg_28]
0x18001ef69  mov     r14d, [rsi+50h]
0x18001ef6d  test    eax, eax
0x18001ef6f  jz      short loc_18001EF86
0x18001ef71  imul    r14d, 1Ch
0x18001ef75  cmp     eax, 1
0x18001ef78  jnz     short loc_18001EF80
0x18001ef7a  add     r14d, 40h ; '@'
0x18001ef7e  jmp     short loc_18001EF8E
0x18001ef80  add     r14d, 54h ; 'T'
0x18001ef84  jmp     short loc_18001EF8E
0x18001ef86  shl     r14d, 4
0x18001ef8a  add     r14d, 3Ch ; '<'
0x18001ef8e  cmp     r15d, r14d
0x18001ef91  jb      short loc_18001EFF0
0x18001ef93  test    eax, eax
0x18001ef95  jz      short loc_18001EFB2
0x18001ef97  cmp     dword ptr [rsi+90h], 0
0x18001ef9e  jz      short loc_18001EFB2
0x18001efa0  mov     rdx, rsi
0x18001efa3  mov     rcx, rdi
0x18001efa6  call    GetMfeFromForwarder
0x18001efab  mov     eax, [rsp+88h+arg_28]
0x18001efb2  mov     r9d, eax
0x18001efb5  mov     r8, r12
0x18001efb8  mov     rdx, rsi
0x18001efbb  mov     rcx, rdi
0x18001efbe  call    CopyMfe
0x18001efc3  mov     eax, r14d
0x18001efc6  sub     r15d, r14d
0x18001efc9  add     ebp, r14d
0x18001efcc  add     r12, rax
0x18001efcf  mov     r14, [rsp+88h+arg_18]
0x18001efd7  inc     dword ptr [r14]
0x18001efda  mov     rsi, [rsi]
0x18001efdd  cmp     rsi, r13
0x18001efe0  jnz     loc_18001EF5C
0x18001efe6  mov     r15, [rsp+88h+arg_18]
0x18001efee  jmp     short loc_18001F005
0x18001eff0  mov     r15, [rsp+88h+arg_18]
0x18001eff8  mov     ebx, 7Ah ; 'z'
0x18001effd  cmp     dword ptr [r15], 0
0x18001f001  cmovz   ebp, r14d
0x18001f005  mov     r12d, dword ptr [rsp+88h+arg_0]
0x18001f00d  lea     rcx, [rdi+28h]
0x18001f011  call    ReleaseWriteLock
0x18001f016  cmp     ebx, 0EAh
0x18001f01c  jnz     short loc_18001F059
0x18001f01e  mov     rdi, [rdi]
0x18001f021  lea     rax, qword_18002BA20
0x18001f028  cmp     rdi, rax
0x18001f02b  jz      loc_18001EE71
0x18001f031  mov     eax, ebp
0x18001f033  lea     rcx, [rdi+28h]
0x18001f037  add     [rsp+88h+arg_10], rax
0x18001f03f  sub     r12d, ebp
0x18001f042  mov     dword ptr [rsp+88h+arg_0], r12d
0x18001f04a  call    AcquireWriteLock
0x18001f04f  xor     esi, esi
0x18001f051  lea     ebp, [rsi+1]
0x18001f054  jmp     loc_18001EEAE
0x18001f059  cmp     ebx, 7Ah ; 'z'
0x18001f05c  jnz     short loc_18001F075
0x18001f05e  cmp     dword ptr [r15], 0
0x18001f062  jz      short loc_18001F06B
0x18001f064  mov     ebx, 0EAh
0x18001f069  jmp     short loc_18001F075
0x18001f06b  mov     rax, [rsp+88h+arg_8]
0x18001f073  mov     [rax], ebp
0x18001f075  lea     rcx, qword_18002BA30
0x18001f07c  call    ReleaseReadLock
0x18001f081  mov     eax, ebx
0x18001f083  add     rsp, 48h
0x18001f087  pop     r15
0x18001f089  pop     r14
0x18001f08b  pop     r13
0x18001f08d  pop     r12
0x18001f08f  pop     rdi
0x18001f090  pop     rsi
0x18001f091  pop     rbp
0x18001f092  pop     rbx
0x18001f093  retn
```
