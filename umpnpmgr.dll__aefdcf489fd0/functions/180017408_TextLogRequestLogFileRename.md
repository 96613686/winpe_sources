# TextLogRequestLogFileRename

- ea: `0x180017408`
- end: `0x1800174fa`
- name: `TextLogRequestLogFileRename`
- size: `242`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000b160`

## callees

- `0x18000b890`
- `0x180017408`
- `0x180018248`

## pseudocode

```c
__int64 __fastcall TextLogRequestLogFileRename(__int64 a1)
{
  unsigned int v1; // edi
  unsigned int v2; // esi
  unsigned int v3; // edx
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdi
  unsigned int v8; // ebp
  __int64 v9; // rcx
  __int64 v11; // rbx
  __int128 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+30h] [rbp-38h]

  v13 = 0;
  v1 = 0;
  v2 = 0;
  v12 = 0;
  v3 = 0;
  v4 = a1;
  while ( (unsigned int)TextLogEnumerateOpenSections(a1, v3, (__int64)&v12) )
  {
    ++v1;
    if ( DWORD1(v12) || (v13 & 0x10000) == 0 )
      ++v2;
    v3 = v1;
    a1 = v4;
  }
  v7 = *(_QWORD *)(v4 + 32);
  if ( !v2 )
  {
    *(_DWORD *)(v7 + 28) = 0;
    v8 = 1;
    *(_DWORD *)(*(_QWORD *)(v4 + 32) + 32LL) = 0;
    *(_DWORD *)(*(_QWORD *)(v4 + 32) + 48LL) = 0;
    return v8;
  }
  v8 = 0;
  if ( *(_DWORD *)(v4 + 24) - *(_DWORD *)(v4 + 16) < (unsigned int)(*(_DWORD *)(v7 + 8) + 0x40000) )
    goto LABEL_15;
  v9 = *(unsigned int *)(v7 + 28);
  if ( !(_DWORD)v9 )
  {
LABEL_11:
    *(_DWORD *)(v7 + 28) = v2;
    *(_DWORD *)(v7 + 32) = 0;
LABEL_16:
    *(_DWORD *)(v7 + 48) = 0;
    return v8;
  }
  if ( v2 == (_DWORD)v9 )
  {
    if ( ++*(_DWORD *)(v7 + 48) < 4u )
      return v8;
    v8 = 1;
LABEL_15:
    *(_QWORD *)(v7 + 28) = 0;
    goto LABEL_16;
  }
  if ( v2 <= (unsigned int)v9 )
    goto LABEL_11;
  if ( !*(_DWORD *)(v7 + 32) || *(_DWORD *)(v7 + 32) < v2 - (unsigned int)v9 )
  {
    *(_DWORD *)(v7 + 32) = v2 - v9;
    *(_QWORD *)(v7 + 40) = pSetupGetTickCount(v9, v5, v6);
    return v8;
  }
  v11 = *(_QWORD *)(v7 + 40);
  if ( (unsigned __int64)(pSetupGetTickCount(v9, v5, v6) - v11) > 0x493E0 )
    goto LABEL_11;
  return v8;
}

```

## disassembly

```asm
0x180017408  push    rbx
0x18001740a  push    rbp
0x18001740b  push    rsi
0x18001740c  push    rdi
0x18001740d  push    r14
0x18001740f  sub     rsp, 40h
0x180017413  xor     r14d, r14d
0x180017416  xor     eax, eax
0x180017418  xorps   xmm0, xmm0
0x18001741b  mov     [rsp+68h+var_38], eax
0x18001741f  mov     edi, r14d
0x180017422  mov     esi, r14d
0x180017425  movups  [rsp+68h+var_48], xmm0
0x18001742a  xor     edx, edx
0x18001742c  mov     rbx, rcx
0x18001742f  jmp     short loc_180017448
0x180017431  inc     edi
0x180017433  cmp     dword ptr [rsp+68h+var_48+4], r14d
0x180017438  jnz     short loc_180017441
0x18001743a  test    byte ptr [rsp+68h+var_38+2], 1
0x18001743f  jnz     short loc_180017443
0x180017441  inc     esi
0x180017443  mov     edx, edi
0x180017445  mov     rcx, rbx
0x180017448  lea     r8, [rsp+68h+var_48]
0x18001744d  call    TextLogEnumerateOpenSections
0x180017452  test    eax, eax
0x180017454  jnz     short loc_180017431
0x180017456  mov     rdi, [rbx+20h]
0x18001745a  test    esi, esi
0x18001745c  jnz     short loc_180017477
0x18001745e  mov     [rdi+1Ch], r14d
0x180017462  lea     ebp, [rsi+1]
0x180017465  mov     rax, [rbx+20h]
0x180017469  mov     [rax+20h], r14d
0x18001746d  mov     rax, [rbx+20h]
0x180017471  mov     [rax+30h], r14d
0x180017475  jmp     short loc_1800174B6
0x180017477  mov     ecx, [rbx+18h]
0x18001747a  mov     ebp, r14d
0x18001747d  mov     eax, [rdi+8]
0x180017480  sub     ecx, [rbx+10h]
0x180017483  add     eax, 40000h
0x180017488  cmp     ecx, eax
0x18001748a  jb      short loc_1800174AE
0x18001748c  mov     ecx, [rdi+1Ch]
0x18001748f  test    ecx, ecx
0x180017491  jnz     short loc_18001749C
0x180017493  mov     [rdi+1Ch], esi
0x180017496  mov     [rdi+20h], r14d
0x18001749a  jmp     short loc_1800174B2
0x18001749c  cmp     esi, ecx
0x18001749e  jnz     short loc_1800174C3
0x1800174a0  inc     dword ptr [rdi+30h]
0x1800174a3  cmp     dword ptr [rdi+30h], 4
0x1800174a7  jb      short loc_1800174B6
0x1800174a9  mov     ebp, 1
0x1800174ae  mov     [rdi+1Ch], r14
0x1800174b2  mov     [rdi+30h], r14d
0x1800174b6  mov     eax, ebp
0x1800174b8  add     rsp, 40h
0x1800174bc  pop     r14
0x1800174be  pop     rdi
0x1800174bf  pop     rsi
0x1800174c0  pop     rbp
0x1800174c1  pop     rbx
0x1800174c2  retn
0x1800174c3  jbe     short loc_180017493
0x1800174c5  cmp     [rdi+20h], r14d
0x1800174c9  jz      short loc_1800174EA
0x1800174cb  mov     eax, esi
0x1800174cd  sub     eax, ecx
0x1800174cf  cmp     [rdi+20h], eax
0x1800174d2  jb      short loc_1800174EA
0x1800174d4  mov     rbx, [rdi+28h]
0x1800174d8  call    pSetupGetTickCount
0x1800174dd  sub     rax, rbx
0x1800174e0  cmp     rax, 493E0h
0x1800174e6  jbe     short loc_1800174B6
0x1800174e8  jmp     short loc_180017493
0x1800174ea  sub     esi, ecx
0x1800174ec  mov     [rdi+20h], esi
0x1800174ef  call    pSetupGetTickCount
0x1800174f4  mov     [rdi+28h], rax
0x1800174f8  jmp     short loc_1800174B6
```
