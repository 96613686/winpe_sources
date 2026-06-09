# WinSetupMonDuplicateCapturedUnicodeStringFromMode

- ea: `0x14001e044`
- end: `0x14001e106`
- name: `WinSetupMonDuplicateCapturedUnicodeStringFromMode`
- size: `194`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14001e174`
- `0x14001e23c`
- `0x14001e2ec`
- `0x14001e464`
- `0x14001e524`
- `0x14001e630`
- `0x14001e71c`

## callees

- `0x140001220`
- `0x14000f930`
- `0x14001e044`
- `0x14001e10c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001e081`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001e081`

## pseudocode

```c
__int64 __fastcall WinSetupMonDuplicateCapturedUnicodeStringFromMode(_OWORD *a1, void **a2, char a3)
{
  __int128 v6; // xmm0
  SIZE_T v7; // rdx
  PVOID PoolWithTag; // rcx
  unsigned int v9; // ebx
  unsigned int v10; // eax
  __int128 v12; // [rsp+30h] [rbp-38h] BYREF

  v6 = 0;
  v12 = 0;
  v7 = *(unsigned __int16 *)a2;
  if ( !(_WORD)v7 )
    goto LABEL_8;
  if ( !a3 )
  {
    v6 = *(_OWORD *)a2;
    goto LABEL_8;
  }
  if ( a3 != 1 )
  {
LABEL_8:
    v9 = 0;
    *a1 = v6;
    v12 = 0;
    goto LABEL_9;
  }
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, v7, 0x6E6D7377u);
  *((_QWORD *)&v12 + 1) = PoolWithTag;
  if ( PoolWithTag )
  {
    v10 = *(unsigned __int16 *)a2;
    LOWORD(v12) = v10;
    WORD1(v12) = v10;
    RtlCopyFromUser(PoolWithTag, a2[1], v10);
    v6 = v12;
    goto LABEL_8;
  }
  v9 = -1073741670;
LABEL_9:
  LOBYTE(v7) = a3;
  WinSetupMonFreeCapturedUnicodeStringFromMode(&v12, v7);
  return v9;
}

```

## disassembly

```asm
0x14001e044  mov     [rsp+arg_10], r8b
0x14001e049  push    rbx
0x14001e04a  push    rsi
0x14001e04b  push    rdi
0x14001e04c  push    r14
0x14001e04e  sub     rsp, 48h
0x14001e052  movsx   edi, r8b
0x14001e056  mov     rbx, rdx
0x14001e059  mov     rsi, rcx
0x14001e05c  xorps   xmm0, xmm0
0x14001e05f  movaps  [rsp+68h+var_38], xmm0
0x14001e064  movzx   edx, word ptr [rdx]; NumberOfBytes
0x14001e067  xor     r14d, r14d
0x14001e06a  test    dx, dx
0x14001e06d  jz      short loc_14001E0DC
0x14001e06f  test    r8b, r8b
0x14001e072  jz      short loc_14001E0D9
0x14001e074  cmp     edi, 1
0x14001e077  jnz     short loc_14001E0DC
0x14001e079  mov     ecx, edi; PoolType
0x14001e07b  mov     r8d, 6E6D7377h; Tag
0x14001e081  call    cs:__imp_ExAllocatePoolWithTag
0x14001e088  nop     dword ptr [rax+rax+00h]
0x14001e08d  mov     rcx, rax; void *
0x14001e090  mov     qword ptr [rsp+68h+var_38+8], rax
0x14001e095  test    rax, rax
0x14001e098  jnz     short loc_14001E0A1
0x14001e09a  mov     ebx, 0C000009Ah
0x14001e09f  jmp     short loc_14001E0EC
0x14001e0a1  movzx   eax, word ptr [rbx]
0x14001e0a4  mov     word ptr [rsp+68h+var_38], ax
0x14001e0a9  mov     word ptr [rsp+68h+var_38+2], ax
0x14001e0ae  mov     rdx, [rbx+8]; Src
0x14001e0b2  mov     r8d, eax; Size
0x14001e0b5  test    dil, dil
0x14001e0b8  jz      short loc_14001E0C1
0x14001e0ba  call    RtlCopyFromUser
0x14001e0bf  jmp     short loc_14001E0C6
0x14001e0c1  call    RtlCopyVolatileMemory
0x14001e0c6  movaps  xmm0, [rsp+68h+var_38]
0x14001e0cb  jmp     short loc_14001E0DC
0x14001e0cd  mov     ebx, eax
0x14001e0cf  mov     dil, [rsp+68h+arg_10]
0x14001e0d7  jmp     short loc_14001E0EC
0x14001e0d9  movups  xmm0, xmmword ptr [rbx]
0x14001e0dc  mov     ebx, r14d
0x14001e0df  movdqu  xmmword ptr [rsi], xmm0
0x14001e0e3  xorps   xmm0, xmm0
0x14001e0e6  movdqa  [rsp+68h+var_38], xmm0
0x14001e0ec  mov     dl, dil
0x14001e0ef  lea     rcx, [rsp+68h+var_38]
0x14001e0f4  call    WinSetupMonFreeCapturedUnicodeStringFromMode
0x14001e0f9  mov     eax, ebx
0x14001e0fb  add     rsp, 48h
0x14001e0ff  pop     r14
0x14001e101  pop     rdi
0x14001e102  pop     rsi
0x14001e103  pop     rbx
0x14001e104  retn
0x140021bed  push    rbp
0x140021bef  sub     rsp, 20h
0x140021bf3  mov     rbp, rdx
0x140021bf6  xor     eax, eax
0x140021bf8  cmp     [rbp+80h], al
0x140021bfe  setnz   al
0x140021c01  mov     [rbp+20h], eax
0x140021c04  mov     eax, [rbp+20h]
0x140021c07  add     rsp, 20h
0x140021c0b  pop     rbp
0x140021c0c  retn
```
