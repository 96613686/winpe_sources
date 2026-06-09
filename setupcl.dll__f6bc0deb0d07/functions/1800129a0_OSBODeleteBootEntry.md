# OSBODeleteBootEntry

- ea: `0x1800129a0`
- end: `0x180012b25`
- name: `OSBODeleteBootEntry`
- size: `389`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800129a0`
- `0x180012c90`
- `0x180012cb8`
- `0x180012d4c`
- `0x1800179ad`
- `0x180018010`

## pseudocode

```c
char __fastcall OSBODeleteBootEntry(__int64 a1, __int64 a2)
{
  char v2; // bl
  __int64 v5; // rax
  __int64 v6; // rbp
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // r14
  unsigned int v11; // ebp
  char *v12; // rax
  char *v13; // r15
  bool v14; // zf

  v2 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v5 = *(_QWORD *)(a1 + 24);
      v6 = 0;
      while ( v5 != a2 )
      {
        v6 = v5;
        v5 = *(_QWORD *)(v5 + 3144);
      }
      if ( v5 )
      {
        *(_DWORD *)(a2 + 3128) |= 0x10000002u;
        *(_DWORD *)(a1 + 4) |= 0x10000000u;
        v2 = (*(__int64 (__fastcall **)(__int64))(a2 + 3160))(a2);
        if ( v2 )
        {
          v7 = *(_QWORD *)(a2 + 3144);
          if ( v6 )
            *(_QWORD *)(v6 + 3144) = v7;
          else
            *(_QWORD *)(a1 + 24) = v7;
          v8 = *(_DWORD *)(a1 + 40);
          if ( v8 )
            *(_DWORD *)(a1 + 40) = v8 - 1;
          v9 = OSBOFindBootEntryOrder(a1, *(unsigned int *)(a2 + 4));
          v10 = v9;
          if ( v9 != -1 )
          {
            v11 = *(_DWORD *)(a1 + 56) - 1;
            if ( *(_DWORD *)(a1 + 56) == 1 )
            {
              SBE_FREE(*(_QWORD *)(a1 + 48));
              *(_QWORD *)(a1 + 48) = 0;
              *(_DWORD *)(a1 + 56) = 0;
            }
            else if ( AllocRoutine && (v12 = (char *)AllocRoutine(4LL * v11), (v13 = v12) != 0) )
            {
              memcpy_0(v12, *(const void **)(a1 + 48), 4 * v10);
              memcpy_0(
                &v13[4 * v10],
                (const void *)(4 * v10 + *(_QWORD *)(a1 + 48) + 4LL),
                4LL * (v11 - (unsigned int)v10));
              SBE_FREE(*(_QWORD *)(a1 + 48));
              *(_QWORD *)(a1 + 48) = v13;
              v2 = 1;
              *(_DWORD *)(a1 + 56) = v11;
            }
            else
            {
              v2 = 0;
            }
          }
          if ( a2 == *(_QWORD *)(a1 + 32) )
          {
            v14 = *(_DWORD *)(a1 + 56) == 0;
            *(_QWORD *)(a1 + 32) = 0;
            if ( !v14 && **(_DWORD **)(a1 + 48) != -1 )
              *(_QWORD *)(a1 + 32) = OSBOFindBootEntry(a1);
          }
          *(_DWORD *)(a1 + 4) |= 0x10000000u;
          (*(void (__fastcall **)(__int64))(a2 + 3152))(a2);
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800129a0  push    rbx
0x1800129a2  push    rbp
0x1800129a3  push    rsi
0x1800129a4  push    rdi
0x1800129a5  push    r14
0x1800129a7  push    r15
0x1800129a9  sub     rsp, 28h
0x1800129ad  xor     bl, bl
0x1800129af  mov     rsi, rdx
0x1800129b2  mov     rdi, rcx
0x1800129b5  test    rcx, rcx
0x1800129b8  jz      loc_180012B16
0x1800129be  test    rdx, rdx
0x1800129c1  jz      loc_180012B16
0x1800129c7  mov     rax, [rcx+18h]
0x1800129cb  xor     ebp, ebp
0x1800129cd  jmp     short loc_1800129D9
0x1800129cf  mov     rbp, rax
0x1800129d2  mov     rax, [rax+0C48h]
0x1800129d9  cmp     rax, rsi
0x1800129dc  jnz     short loc_1800129CF
0x1800129de  test    rax, rax
0x1800129e1  jz      loc_180012B16
0x1800129e7  or      dword ptr [rdx+0C38h], 10000002h
0x1800129f1  bts     dword ptr [rcx+4], 1Ch
0x1800129f6  mov     rcx, rsi
0x1800129f9  mov     rax, [rdx+0C58h]
0x180012a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a05  mov     bl, al
0x180012a07  test    al, al
0x180012a09  jz      loc_180012B16
0x180012a0f  mov     rax, [rsi+0C48h]
0x180012a16  test    rbp, rbp
0x180012a19  jz      short loc_180012A24
0x180012a1b  mov     [rbp+0C48h], rax
0x180012a22  jmp     short loc_180012A28
0x180012a24  mov     [rdi+18h], rax
0x180012a28  mov     eax, [rdi+28h]
0x180012a2b  test    eax, eax
0x180012a2d  jz      short loc_180012A34
0x180012a2f  dec     eax
0x180012a31  mov     [rdi+28h], eax
0x180012a34  mov     edx, [rsi+4]
0x180012a37  mov     rcx, rdi
0x180012a3a  call    OSBOFindBootEntryOrder
0x180012a3f  mov     r14d, eax
0x180012a42  cmp     eax, 0FFFFFFFFh
0x180012a45  jz      loc_180012AD7
0x180012a4b  mov     ebp, [rdi+38h]
0x180012a4e  sub     ebp, 1
0x180012a51  jz      short loc_180012ABF
0x180012a53  mov     rax, cs:AllocRoutine
0x180012a5a  test    rax, rax
0x180012a5d  jz      short loc_180012ABB
0x180012a5f  mov     ecx, ebp
0x180012a61  shl     rcx, 2
0x180012a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a6a  mov     r15, rax
0x180012a6d  test    rax, rax
0x180012a70  jz      short loc_180012ABB
0x180012a72  mov     rdx, [rdi+30h]; Src
0x180012a76  lea     rbx, ds:0[r14*4]
0x180012a7e  mov     r8, rbx; Size
0x180012a81  mov     rcx, rax; void *
0x180012a84  call    memcpy_0
0x180012a89  mov     rdx, [rdi+30h]
0x180012a8d  lea     rcx, [rbx+r15]; void *
0x180012a91  mov     r8d, ebp
0x180012a94  add     rdx, 4
0x180012a98  sub     r8d, r14d
0x180012a9b  add     rdx, rbx; Src
0x180012a9e  shl     r8, 2; Size
0x180012aa2  call    memcpy_0
0x180012aa7  mov     rcx, [rdi+30h]
0x180012aab  call    SBE_FREE
0x180012ab0  mov     [rdi+30h], r15
0x180012ab4  mov     bl, 1
0x180012ab6  mov     [rdi+38h], ebp
0x180012ab9  jmp     short loc_180012AD7
0x180012abb  xor     bl, bl
0x180012abd  jmp     short loc_180012AD7
0x180012abf  mov     rcx, [rdi+30h]
0x180012ac3  call    SBE_FREE
0x180012ac8  mov     qword ptr [rdi+30h], 0
0x180012ad0  mov     dword ptr [rdi+38h], 0
0x180012ad7  cmp     rsi, [rdi+20h]
0x180012adb  jnz     short loc_180012B02
0x180012add  cmp     dword ptr [rdi+38h], 0
0x180012ae1  mov     qword ptr [rdi+20h], 0
0x180012ae9  jbe     short loc_180012B02
0x180012aeb  mov     rax, [rdi+30h]
0x180012aef  cmp     dword ptr [rax], 0FFFFFFFFh
0x180012af2  jz      short loc_180012B02
0x180012af4  mov     edx, [rax]
0x180012af6  mov     rcx, rdi
0x180012af9  call    OSBOFindBootEntry
0x180012afe  mov     [rdi+20h], rax
0x180012b02  bts     dword ptr [rdi+4], 1Ch
0x180012b07  mov     rcx, rsi
0x180012b0a  mov     rax, [rsi+0C50h]
0x180012b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b16  mov     al, bl
0x180012b18  add     rsp, 28h
0x180012b1c  pop     r15
0x180012b1e  pop     r14
0x180012b20  pop     rdi
0x180012b21  pop     rsi
0x180012b22  pop     rbp
0x180012b23  pop     rbx
0x180012b24  retn
```
