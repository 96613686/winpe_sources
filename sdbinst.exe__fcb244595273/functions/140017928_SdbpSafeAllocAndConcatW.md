# SdbpSafeAllocAndConcatW

- ea: `0x140017928`
- end: `0x140017bdc`
- name: `SdbpSafeAllocAndConcatW`
- size: `692`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x140016c98`

## callees

- `0x14001008c`
- `0x140011ce8`
- `0x140017928`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140017a67`
- `ntdll!RtlAllocateHeap` at `0x140017a67`
- `ntdll!RtlFreeHeap` at `0x140017b8c`
- `ntdll!RtlFreeHeap` at `0x140017b8c`

## string_xrefs

- `0x140017aa1`: `RtlStringCchCopyW failed to copy first string [%x]`

## pseudocode

```c
__int64 __fastcall SdbpSafeAllocAndConcatW(_QWORD *a1, _WORD *a2, unsigned __int64 a3, _WORD *a4, unsigned __int64 a5)
{
  _WORD *v5; // r12
  unsigned __int64 v6; // r15
  _WORD *v7; // rax
  int v9; // ebp
  __int64 v10; // rcx
  unsigned int v11; // ebx
  unsigned __int64 v12; // r14
  __int64 v13; // rcx
  _WORD *v14; // rax
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rdi
  char *Heap; // rax
  char *v18; // r13
  int v19; // eax
  __int64 v20; // r8
  const char *v21; // r9
  unsigned __int64 v22; // rcx
  _WORD *v23; // rax
  unsigned __int64 v24; // rax
  char *v25; // rdx
  unsigned __int64 i; // rdi
  char *v27; // rcx
  __int64 v28; // r8

  v5 = a4;
  v6 = a3;
  v7 = a2;
  if ( !a1 )
    return 3221225711LL;
  if ( !a2 )
    return 3221225712LL;
  if ( !a4 )
    return 3221225714LL;
  v9 = -1073741811;
  if ( a3 )
    goto LABEL_13;
  v10 = 0x7FFFFFFF;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v10;
  }
  while ( v10 );
  v11 = v10 == 0 ? 0xC000000D : 0;
  v6 = (0x7FFFFFFF - v10) & -(__int64)(v10 != 0);
  if ( v10 )
  {
LABEL_13:
    v12 = a5;
    if ( !a5 )
    {
      v13 = 0x7FFFFFFF;
      v14 = a4;
      do
      {
        if ( !*v14 )
          break;
        ++v14;
        --v13;
      }
      while ( v13 );
      v11 = v13 == 0 ? 0xC000000D : 0;
      v12 = (0x7FFFFFFF - v13) & -(__int64)(v13 != 0);
      if ( !v13 )
      {
        AslLogCallPrintf(1, "SdbpSafeAllocAndConcatW", 1647, "RtlStringCchLengthW failed [%x]", -1073741811);
        return v11;
      }
    }
    v15 = v6 + v12;
    if ( v6 + v12 < v6 )
    {
      v28 = 1657;
    }
    else
    {
      v16 = v15 + 1;
      if ( v15 + 1 >= v15 )
      {
        Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v16);
        v18 = Heap;
        if ( !Heap )
          return (unsigned int)-1073741801;
        v19 = RtlStringCchCopyNW(Heap, v16, a2, v6);
        v11 = v19;
        if ( v19 < 0 )
        {
          v20 = 1679;
          v21 = "RtlStringCchCopyW failed to copy first string [%x]";
          v9 = v19;
LABEL_46:
          AslLogCallPrintf(1, "SdbpSafeAllocAndConcatW", v20, v21, v9);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
          return v11;
        }
        if ( v16 - 1 > 0x7FFFFFFE )
        {
          v11 = -1073741811;
        }
        else
        {
          v22 = v16;
          v23 = v18;
          do
          {
            if ( !*v23 )
              break;
            ++v23;
            --v22;
          }
          while ( v22 );
          v11 = v22 == 0 ? 0xC000000D : 0;
          if ( v22 )
            v24 = v16 - v22;
          else
            v24 = 0;
          if ( v22 )
          {
            if ( v12 > 0x7FFFFFFE )
            {
              v11 = -1073741811;
LABEL_45:
              v20 = 1688;
              v21 = "RtlStringCchCatW failed to cat second string [%x]";
              goto LABEL_46;
            }
            v25 = &v18[2 * v24];
            for ( i = v16 - v24; i; --i )
            {
              if ( !v12 )
                break;
              if ( !*v5 )
                break;
              *(_WORD *)v25 = *v5++;
              v25 += 2;
              --v12;
            }
            v27 = v25 - 2;
            v11 = i == 0 ? 0x80000005 : 0;
            if ( i )
              v27 = v25;
            *(_WORD *)v27 = 0;
            if ( i )
            {
              *a1 = v18;
              return v11;
            }
          }
        }
        v9 = v11;
        goto LABEL_45;
      }
      v28 = 1664;
    }
    v11 = -1073741675;
    AslLogCallPrintf(1, "SdbpSafeAllocAndConcatW", v28, "RtlSizeTAdd failed [%x]", -1073741675);
    return v11;
  }
  AslLogCallPrintf(1, "SdbpSafeAllocAndConcatW", 1639, "RtlStringCchLengthW failed [%x]", -1073741811);
  return v11;
}

```

## disassembly

```asm
0x140017928  mov     [rsp+arg_10], rbx
0x14001792d  mov     [rsp+arg_8], rdx
0x140017932  mov     [rsp+arg_0], rcx
0x140017937  push    rbp
0x140017938  push    rsi
0x140017939  push    rdi
0x14001793a  push    r12
0x14001793c  push    r13
0x14001793e  push    r14
0x140017940  push    r15
0x140017942  sub     rsp, 30h
0x140017946  mov     r12, r9
0x140017949  mov     r15, r8
0x14001794c  xor     r9d, r9d
0x14001794f  mov     rax, rdx
0x140017952  test    rcx, rcx
0x140017955  jnz     short loc_140017961
0x140017957  mov     eax, 0C00000EFh
0x14001795c  jmp     loc_140017BC4
0x140017961  test    rax, rax
0x140017964  jnz     short loc_140017970
0x140017966  mov     eax, 0C00000F0h
0x14001796b  jmp     loc_140017BC4
0x140017970  test    r12, r12
0x140017973  jnz     short loc_14001797F
0x140017975  mov     eax, 0C00000F2h
0x14001797a  jmp     loc_140017BC4
0x14001797f  mov     esi, 1
0x140017984  mov     ebp, 0C000000Dh
0x140017989  mov     r8d, 7FFFFFFFh
0x14001798f  test    r15, r15
0x140017992  jnz     short loc_1400179DF
0x140017994  mov     ecx, r8d
0x140017997  cmp     [rax], r9w
0x14001799b  jz      short loc_1400179A6
0x14001799d  add     rax, 2
0x1400179a1  sub     rcx, rsi
0x1400179a4  jnz     short loc_140017997
0x1400179a6  mov     rax, rcx
0x1400179a9  mov     rdx, r8
0x1400179ac  neg     rax
0x1400179af  mov     rax, rcx
0x1400179b2  sbb     ebx, ebx
0x1400179b4  sub     rdx, rcx
0x1400179b7  not     ebx
0x1400179b9  and     ebx, ebp
0x1400179bb  neg     rax
0x1400179be  sbb     r15, r15
0x1400179c1  and     r15, rdx
0x1400179c4  test    rcx, rcx
0x1400179c7  jnz     short loc_1400179DF
0x1400179c9  mov     [rsp+68h+var_48], ebx
0x1400179cd  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x1400179d4  mov     r8d, 667h
0x1400179da  jmp     loc_140017BB4
0x1400179df  mov     r14, [rsp+68h+arg_20]
0x1400179e7  test    r14, r14
0x1400179ea  jnz     short loc_140017A37
0x1400179ec  mov     rcx, r8
0x1400179ef  mov     rax, r12
0x1400179f2  cmp     [rax], r9w
0x1400179f6  jz      short loc_140017A01
0x1400179f8  add     rax, 2
0x1400179fc  sub     rcx, rsi
0x1400179ff  jnz     short loc_1400179F2
0x140017a01  mov     rax, rcx
0x140017a04  neg     rax
0x140017a07  mov     rax, rcx
0x140017a0a  sbb     ebx, ebx
0x140017a0c  sub     r8, rcx
0x140017a0f  not     ebx
0x140017a11  and     ebx, ebp
0x140017a13  neg     rax
0x140017a16  sbb     r14, r14
0x140017a19  and     r14, r8
0x140017a1c  test    rcx, rcx
0x140017a1f  jnz     short loc_140017A37
0x140017a21  mov     [rsp+68h+var_48], ebx
0x140017a25  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x140017a2c  mov     r8d, 66Fh
0x140017a32  jmp     loc_140017BB4
0x140017a37  lea     rax, [r15+r14]
0x140017a3b  cmp     rax, r15
0x140017a3e  jb      loc_140017B9C
0x140017a44  lea     rdi, [rax+1]
0x140017a48  cmp     rdi, rax
0x140017a4b  jb      loc_140017B94
0x140017a51  mov     rcx, gs:60h
0x140017a5a  lea     r8, [rdi+rdi]; Size
0x140017a5e  mov     edx, 8; Flags
0x140017a63  mov     rcx, [rcx+30h]; HeapHandle
0x140017a67  call    cs:__imp_RtlAllocateHeap
0x140017a6d  mov     r13, rax
0x140017a70  test    rax, rax
0x140017a73  jnz     short loc_140017A7F
0x140017a75  mov     ebx, 0C0000017h
0x140017a7a  jmp     loc_140017BC2
0x140017a7f  mov     r8, [rsp+68h+arg_8]
0x140017a84  mov     r9, r15
0x140017a87  mov     rdx, rdi
0x140017a8a  mov     rcx, r13
0x140017a8d  call    RtlStringCchCopyNW
0x140017a92  xor     r8d, r8d
0x140017a95  mov     ebx, eax
0x140017a97  test    eax, eax
0x140017a99  jns     short loc_140017AAF
0x140017a9b  mov     r8d, 68Fh
0x140017aa1  lea     r9, aRtlstringcchco_1; "RtlStringCchCopyW failed to copy first "...
0x140017aa8  mov     ebp, eax
0x140017aaa  jmp     loc_140017B68
0x140017aaf  lea     rax, [rdi-1]
0x140017ab3  mov     edx, 7FFFFFFEh
0x140017ab8  cmp     rax, rdx
0x140017abb  ja      loc_140017B57
0x140017ac1  mov     rcx, rdi
0x140017ac4  mov     rax, r13
0x140017ac7  cmp     [rax], r8w
0x140017acb  jz      short loc_140017AD6
0x140017acd  add     rax, 2
0x140017ad1  sub     rcx, rsi
0x140017ad4  jnz     short loc_140017AC7
0x140017ad6  mov     rax, rcx
0x140017ad9  neg     rax
0x140017adc  sbb     ebx, ebx
0x140017ade  not     ebx
0x140017ae0  and     ebx, ebp
0x140017ae2  test    rcx, rcx
0x140017ae5  jz      short loc_140017AEF
0x140017ae7  mov     rax, rdi
0x140017aea  sub     rax, rcx
0x140017aed  jmp     short loc_140017AF2
0x140017aef  mov     rax, r8
0x140017af2  test    rcx, rcx
0x140017af5  jz      short loc_140017B59
0x140017af7  cmp     r14, rdx
0x140017afa  jbe     short loc_140017B00
0x140017afc  mov     ebx, ebp
0x140017afe  jmp     short loc_140017B5B
0x140017b00  lea     rdx, [r13+rax*2+0]
0x140017b05  sub     rdi, rax
0x140017b08  jz      short loc_140017B2C
0x140017b0a  test    r14, r14
0x140017b0d  jz      short loc_140017B2C
0x140017b0f  movzx   eax, word ptr [r12]
0x140017b14  test    ax, ax
0x140017b17  jz      short loc_140017B2C
0x140017b19  mov     [rdx], ax
0x140017b1c  add     r12, 2
0x140017b20  add     rdx, 2
0x140017b24  sub     r14, rsi
0x140017b27  sub     rdi, rsi
0x140017b2a  jnz     short loc_140017B0A
0x140017b2c  mov     rax, rdi
0x140017b2f  lea     rcx, [rdx-2]
0x140017b33  neg     rax
0x140017b36  sbb     ebx, ebx
0x140017b38  not     ebx
0x140017b3a  and     ebx, 80000005h
0x140017b40  test    rdi, rdi
0x140017b43  cmovnz  rcx, rdx
0x140017b47  mov     [rcx], r8w
0x140017b4b  jz      short loc_140017B59
0x140017b4d  mov     rax, [rsp+68h+arg_0]
0x140017b52  mov     [rax], r13
0x140017b55  jmp     short loc_140017BC2
0x140017b57  mov     ebx, ebp
0x140017b59  mov     ebp, ebx
0x140017b5b  mov     r8d, 698h
0x140017b61  lea     r9, aRtlstringcchca_0; "RtlStringCchCatW failed to cat second s"...
0x140017b68  lea     rdx, aSdbpsafealloca; "SdbpSafeAllocAndConcatW"
0x140017b6f  mov     [rsp+68h+var_48], ebp
0x140017b73  mov     ecx, esi
0x140017b75  call    AslLogCallPrintf
0x140017b7a  mov     rcx, gs:60h
0x140017b83  mov     r8, r13; P
0x140017b86  xor     edx, edx; Flags
0x140017b88  mov     rcx, [rcx+30h]; HeapHandle
0x140017b8c  call    cs:__imp_RtlFreeHeap
0x140017b92  jmp     short loc_140017BC2
0x140017b94  mov     r8d, 680h
0x140017b9a  jmp     short loc_140017BA2
0x140017b9c  mov     r8d, 679h
0x140017ba2  mov     eax, 0C0000095h
0x140017ba7  lea     r9, aRtlsizetaddFai; "RtlSizeTAdd failed [%x]"
0x140017bae  mov     [rsp+68h+var_48], eax
0x140017bb2  mov     ebx, eax
0x140017bb4  lea     rdx, aSdbpsafealloca; "SdbpSafeAllocAndConcatW"
0x140017bbb  mov     ecx, esi
0x140017bbd  call    AslLogCallPrintf
0x140017bc2  mov     eax, ebx
0x140017bc4  mov     rbx, [rsp+68h+arg_10]
0x140017bcc  add     rsp, 30h
0x140017bd0  pop     r15
0x140017bd2  pop     r14
0x140017bd4  pop     r13
0x140017bd6  pop     r12
0x140017bd8  pop     rdi
0x140017bd9  pop     rsi
0x140017bda  pop     rbp
0x140017bdb  retn
```
