# MvmCreateGpadl

- ea: `0x14000d410`
- end: `0x14000d60b`
- name: `MvmCreateGpadl`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000a9e0`

## callees

- `0x14000d410`
- `0x14000dd98`
- `0x14000e050`
- `0x14000e0a0`
- `0x14000e0f0`
- `0x14000e8ec`
- `0x14000e910`
- `0x14000e9f4`
- `0x140017540`

## pseudocode

```c
char __fastcall MvmCreateGpadl(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4, _DWORD *a5)
{
  unsigned int v9; // esi
  __int64 v11; // rdi
  unsigned int v12; // eax
  __int64 v13; // r14
  int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  _QWORD v17[38]; // [rsp+20h] [rbp-E0h] BYREF

  memset(v17, 0, 0xF4u);
  v9 = (a3 + a4 + 4095) >> 12;
  if ( !(unsigned __int8)MvmpCreateGpadlHelper(a1, a2, v9) )
  {
    *a5 = 0;
    return 0;
  }
  *a5 = 0;
  *a5 = (*(_DWORD *)(*(_QWORD *)(a1 + 40) + 88LL))++;
  memset(v17, 0, 0xF4u);
  HIDWORD(v17[1]) = *(_DWORD *)(a1 + 48);
  LODWORD(v17[2]) = *a5;
  v17[3] = __PAIR64__(a3, a4);
  WORD2(v17[2]) = 8 * (v9 + 1);
  v11 = 0;
  v17[0] = 0x8000000F0LL;
  HIWORD(v17[2]) = 1;
  while ( 1 )
  {
    v12 = 26;
    if ( v9 < 0x1A )
      v12 = v9;
    if ( (unsigned int)v11 >= v12 )
      break;
    v17[v11 + 4] = *(_QWORD *)(a2 + 8 * v11);
    v11 = (unsigned int)(v11 + 1);
  }
  v13 = MvmpEstablishGhcbPage(*(_QWORD *)(a1 + 40));
  MvmpEstablishMessagePage(*(_QWORD *)(a1 + 40), v13, 0);
  while ( 1 )
  {
    MvmpSendMessageSynchronous(*(_QWORD *)(a1 + 40), v13, v17);
    if ( v9 == (_DWORD)v11 )
      break;
    memset(v17, 0, 0xF4u);
    v14 = *a5;
    v15 = 0;
    v17[0] = 0x9000000F0LL;
    LODWORD(v17[2]) = v14;
    while ( 1 )
    {
      v16 = 28;
      if ( v9 - (unsigned int)v11 < 0x1C )
        v16 = v9 - v11;
      if ( (unsigned int)v15 >= v16 )
        break;
      *(_QWORD *)((char *)&v17[v15 + 2] + 4) = *(_QWORD *)(a2 + 8LL * (unsigned int)(v11 + v15));
      v15 = (unsigned int)(v15 + 1);
    }
    LODWORD(v11) = v11 + v15;
  }
  MvmpReceiveMessageIgnoreUnsupported(*(_QWORD *)(a1 + 40), v13, v17);
  MvmpReleaseMessagePage(*(_QWORD *)(a1 + 40), v13);
  MvmpReleaseGhcbPage(*(_QWORD *)(a1 + 40), v13);
  if ( v17[0] != 0xA00000014LL || *(_QWORD *)((char *)&v17[1] + 4) != __PAIR64__(*a5, *(_DWORD *)(a1 + 48)) )
    __fastfail(0x3Au);
  if ( v17[2] < 0 )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 40) + 208LL) = 12;
    *a5 = 0;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x14000d410  push    rbp
0x14000d412  push    rbx
0x14000d413  push    rsi
0x14000d414  push    rdi
0x14000d415  push    r12
0x14000d417  push    r14
0x14000d419  push    r15
0x14000d41b  lea     rbp, [rsp-20h]
0x14000d420  sub     rsp, 120h
0x14000d427  mov     r14d, r8d
0x14000d42a  mov     r12, rdx
0x14000d42d  mov     rbx, rcx
0x14000d430  xor     edx, edx; Val
0x14000d432  mov     r8d, 0F4h; Size
0x14000d438  lea     rcx, [rsp+150h+var_130]; void *
0x14000d43d  mov     edi, r9d
0x14000d440  call    memset
0x14000d445  lea     esi, [rdi+0FFFh]
0x14000d44b  mov     rdx, r12
0x14000d44e  add     esi, r14d
0x14000d451  mov     rcx, rbx
0x14000d454  shr     esi, 0Ch
0x14000d457  mov     r8d, esi
0x14000d45a  call    MvmpCreateGpadlHelper
0x14000d45f  test    al, al
0x14000d461  jnz     short loc_14000D485
0x14000d463  mov     rax, [rbp+50h+arg_20]
0x14000d46a  mov     dword ptr [rax], 0
0x14000d470  xor     al, al
0x14000d472  add     rsp, 120h
0x14000d479  pop     r15
0x14000d47b  pop     r14
0x14000d47d  pop     r12
0x14000d47f  pop     rdi
0x14000d480  pop     rsi
0x14000d481  pop     rbx
0x14000d482  pop     rbp
0x14000d483  retn
0x14000d485  mov     r15, [rbp+50h+arg_20]
0x14000d48c  xor     eax, eax
0x14000d48e  xor     edx, edx; Val
0x14000d490  mov     r8d, 0F4h; Size
0x14000d496  mov     [r15], eax
0x14000d499  mov     rax, [rbx+28h]
0x14000d49d  mov     ecx, [rax+58h]
0x14000d4a0  mov     [r15], ecx
0x14000d4a3  lea     rcx, [rsp+150h+var_130]; void *
0x14000d4a8  mov     rax, [rbx+28h]
0x14000d4ac  inc     dword ptr [rax+58h]
0x14000d4af  call    memset
0x14000d4b4  mov     eax, [rbx+30h]
0x14000d4b7  mov     edx, 1
0x14000d4bc  mov     [rsp+150h+var_124], eax
0x14000d4c0  mov     eax, [r15]
0x14000d4c3  mov     [rsp+150h+var_120], eax
0x14000d4c7  lea     eax, [rdx+rsi]
0x14000d4ca  mov     dword ptr [rsp+150h+var_11C+4], edi
0x14000d4ce  shl     ax, 3
0x14000d4d2  mov     word ptr [rsp+150h+var_11C], ax
0x14000d4d7  xor     edi, edi
0x14000d4d9  mov     [rsp+150h+var_12C], 8
0x14000d4e1  mov     [rsp+150h+var_130], 0F0h
0x14000d4e9  mov     word ptr [rsp+150h+var_11C+2], dx
0x14000d4ee  mov     [rsp+150h+var_114], r14d
0x14000d4f3  mov     eax, 1Ah
0x14000d4f8  cmp     esi, eax
0x14000d4fa  cmovb   eax, esi
0x14000d4fd  cmp     edi, eax
0x14000d4ff  jnb     short loc_14000D50E
0x14000d501  mov     rax, [r12+rdi*8]
0x14000d505  mov     [rsp+rdi*8+150h+var_110], rax
0x14000d50a  add     edi, edx
0x14000d50c  jmp     short loc_14000D4F3
0x14000d50e  mov     rcx, [rbx+28h]
0x14000d512  call    MvmpEstablishGhcbPage
0x14000d517  mov     rcx, [rbx+28h]
0x14000d51b  xor     r8d, r8d
0x14000d51e  mov     rdx, rax
0x14000d521  mov     r14, rax
0x14000d524  call    MvmpEstablishMessagePage
0x14000d529  jmp     short loc_14000D57E
0x14000d52b  xor     edx, edx; Val
0x14000d52d  lea     rcx, [rsp+150h+var_130]; void *
0x14000d532  mov     r8d, 0F4h; Size
0x14000d538  call    memset
0x14000d53d  mov     eax, [r15]
0x14000d540  xor     edx, edx
0x14000d542  mov     r8d, esi
0x14000d545  mov     [rsp+150h+var_12C], 9
0x14000d54d  sub     r8d, edi
0x14000d550  mov     [rsp+150h+var_130], 0F0h
0x14000d558  mov     [rsp+150h+var_120], eax
0x14000d55c  mov     eax, 1Ch
0x14000d561  lea     ecx, [rdi+rdx]
0x14000d564  cmp     r8d, eax
0x14000d567  cmovb   eax, r8d
0x14000d56b  cmp     edx, eax
0x14000d56d  jnb     short loc_14000D57C
0x14000d56f  mov     rax, [r12+rcx*8]
0x14000d573  mov     [rsp+rdx*8+150h+var_11C], rax
0x14000d578  inc     edx
0x14000d57a  jmp     short loc_14000D55C
0x14000d57c  mov     edi, ecx
0x14000d57e  mov     rcx, [rbx+28h]
0x14000d582  lea     r8, [rsp+150h+var_130]
0x14000d587  mov     rdx, r14
0x14000d58a  call    MvmpSendMessageSynchronous
0x14000d58f  cmp     esi, edi
0x14000d591  jnz     short loc_14000D52B
0x14000d593  mov     rcx, [rbx+28h]
0x14000d597  lea     r8, [rsp+150h+var_130]
0x14000d59c  mov     rdx, r14
0x14000d59f  call    MvmpReceiveMessageIgnoreUnsupported
0x14000d5a4  mov     rcx, [rbx+28h]
0x14000d5a8  mov     rdx, r14
0x14000d5ab  call    MvmpReleaseMessagePage
0x14000d5b0  mov     rcx, [rbx+28h]
0x14000d5b4  mov     rdx, r14
0x14000d5b7  call    MvmpReleaseGhcbPage
0x14000d5bc  cmp     [rsp+150h+var_12C], 0Ah
0x14000d5c1  jnz     short loc_14000D604
0x14000d5c3  cmp     [rsp+150h+var_130], 14h
0x14000d5c8  jnz     short loc_14000D604
0x14000d5ca  mov     eax, [rbx+30h]
0x14000d5cd  cmp     [rsp+150h+var_124], eax
0x14000d5d1  jnz     short loc_14000D604
0x14000d5d3  mov     eax, [r15]
0x14000d5d6  cmp     [rsp+150h+var_120], eax
0x14000d5da  jnz     short loc_14000D604
0x14000d5dc  cmp     dword ptr [rsp+150h+var_11C], 0
0x14000d5e1  jge     short loc_14000D5FD
0x14000d5e3  mov     rax, [rbx+28h]
0x14000d5e7  mov     dword ptr [rax+0D0h], 0Ch
0x14000d5f1  mov     dword ptr [r15], 0
0x14000d5f8  jmp     loc_14000D470
0x14000d5fd  mov     al, 1
0x14000d5ff  jmp     loc_14000D472
0x14000d604  mov     ecx, 3Ah ; ':'
0x14000d609  int     29h; Win8: RtlFailFast(ecx)
```
