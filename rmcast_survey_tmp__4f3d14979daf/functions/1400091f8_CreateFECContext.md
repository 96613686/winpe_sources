# CreateFECContext

- ea: `0x1400091f8`
- end: `0x140009485`
- name: `CreateFECContext`
- size: `653`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, char)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140005e3c`
- `0x140010ae4`
- `0x140012efc`

## callees

- `0x1400091f8`
- `0x140009bb4`
- `0x140009d3c`
- `0x140009e08`
- `0x140009fbc`
- `0x14001d300`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140009238`
- `ntoskrnl!ExAllocatePool2` at `0x140009260`
- `ntoskrnl!ExAllocatePool2` at `0x140009291`
- `ntoskrnl!ExAllocatePool2` at `0x1400092b8`
- `ntoskrnl!ExAllocatePool2` at `0x140009238`
- `ntoskrnl!ExAllocatePool2` at `0x140009260`
- `ntoskrnl!ExAllocatePool2` at `0x140009291`
- `ntoskrnl!ExAllocatePool2` at `0x1400092b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400093c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009420`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009436`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000944c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009462`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400093c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009420`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009436`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000944c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009462`

## pseudocode

```c
__int64 __fastcall CreateFECContext(__int64 a1, int a2, unsigned int a3, char a4)
{
  __int64 v4; // rdi
  void *v7; // rbx
  __int64 v9; // r15
  __int64 v10; // rdx
  void *Pool2; // rbp
  __int64 v12; // r8
  _BYTE *v13; // rsi
  int v14; // r8d
  _BYTE *v15; // r11
  int i; // r10d
  int j; // r9d
  unsigned __int8 v18; // al
  __int64 v19; // r9
  _BYTE *v20; // rcx
  int k; // edx

  v4 = a2;
  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  v7 = 0;
  v9 = 0;
  Pool2 = (void *)ExAllocatePool2(64, (int)(a3 * a2), 812476240);
  if ( Pool2 )
  {
    v13 = (_BYTE *)ExAllocatePool2(64, (int)(v4 * (a3 + 3)), 812476240);
    if ( v13 )
    {
      if ( !a4
        || (v7 = (void *)ExAllocatePool2(64, (int)v4 * (int)v4, 812476240)) != 0
        && (v9 = ExAllocatePool2(64, 20 * v4, 812476240)) != 0 )
      {
        *(_DWORD *)a1 = v4;
        *(_DWORD *)(a1 + 4) = a3;
        *(_QWORD *)(a1 + 8) = Pool2;
        *(_QWORD *)(a1 + 16) = v7;
        *(_QWORD *)(a1 + 24) = v9;
        *v13 = 1;
        if ( (int)v4 > 1 )
          memset(v13 + 1, 0, v4 - 1);
        v14 = 0;
        v15 = &v13[v4];
        for ( i = v4; v14 < (int)(a3 - 1); v15 += v4 )
        {
          for ( j = 0; j < (int)v4; j = v19 + 1 )
          {
            v18 = ModNN((unsigned int)(v14 * j));
            v15[v19] = *((_BYTE *)&gFECExp + v18);
          }
          ++v14;
        }
        InvertVdm(
          v4,
          (_DWORD)v13,
          (_DWORD)v13 + a3 * v4,
          (_DWORD)v13 + a3 * v4 + i,
          (__int64)&v13[2 * (int)v4 + (int)(a3 * v4)]);
        MatrixMultiply(v4 * v4 + (_DWORD)v13, (_DWORD)v13, v4 * v4 + *(_QWORD *)(a1 + 8), a3 - v4, v4, v4);
        memset(*(void **)(a1 + 8), 0, (int)v4 * (int)v4);
        v20 = *(_BYTE **)(a1 + 8);
        for ( k = 0; k < (int)v4; v20 += (int)v4 + 1 )
        {
          *v20 = 1;
          ++k;
        }
        ExFreePoolWithTag(v13, 0);
        return 0;
      }
    }
  }
  else
  {
    v13 = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_ddqqqq(WPP_GLOBAL_Control->AttachedDevice, v10, v12, a3, v4, a1, Pool2, v7, v13);
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  return 3221225626LL;
}

```

## disassembly

```asm
0x1400091f8  push    rbx
0x1400091fa  push    rbp
0x1400091fb  push    rsi
0x1400091fc  push    rdi
0x1400091fd  push    r12
0x1400091ff  push    r13
0x140009201  push    r14
0x140009203  push    r15
0x140009205  sub     rsp, 58h
0x140009209  movsxd  rdi, edx
0x14000920c  xorps   xmm0, xmm0
0x14000920f  movups  xmmword ptr [rcx], xmm0
0x140009212  mov     eax, edi
0x140009214  mov     r13d, r8d
0x140009217  imul    eax, r8d
0x14000921b  mov     r14, rcx
0x14000921e  movups  xmmword ptr [rcx+10h], xmm0
0x140009222  xor     ebx, ebx
0x140009224  mov     esi, 306D6750h
0x140009229  mov     r8d, esi
0x14000922c  mov     r12b, r9b
0x14000922f  xor     r15d, r15d
0x140009232  movsxd  rdx, eax
0x140009235  lea     ecx, [rbx+40h]
0x140009238  call    cs:__imp_ExAllocatePool2
0x14000923f  nop     dword ptr [rax+rax+00h]
0x140009244  mov     rbp, rax
0x140009247  test    rax, rax
0x14000924a  jz      loc_1400093D6
0x140009250  lea     eax, [r13+3]
0x140009254  mov     r8d, esi
0x140009257  imul    eax, edi
0x14000925a  lea     ecx, [rbx+40h]
0x14000925d  movsxd  rdx, eax
0x140009260  call    cs:__imp_ExAllocatePool2
0x140009267  nop     dword ptr [rax+rax+00h]
0x14000926c  mov     rsi, rax
0x14000926f  test    rax, rax
0x140009272  jz      loc_1400093D8
0x140009278  test    r12b, r12b
0x14000927b  jz      short loc_1400092D0
0x14000927d  mov     eax, edi
0x14000927f  lea     ecx, [rbx+40h]
0x140009282  imul    eax, edi
0x140009285  mov     r12d, 306D6750h
0x14000928b  mov     r8d, r12d
0x14000928e  movsxd  rdx, eax
0x140009291  call    cs:__imp_ExAllocatePool2
0x140009298  nop     dword ptr [rax+rax+00h]
0x14000929d  mov     rbx, rax
0x1400092a0  test    rax, rax
0x1400092a3  jz      loc_1400093D8
0x1400092a9  lea     rdx, [rdi+rdi*4]
0x1400092ad  mov     r8d, r12d
0x1400092b0  shl     rdx, 2
0x1400092b4  lea     ecx, [r15+40h]
0x1400092b8  call    cs:__imp_ExAllocatePool2
0x1400092bf  nop     dword ptr [rax+rax+00h]
0x1400092c4  mov     r15, rax
0x1400092c7  test    rax, rax
0x1400092ca  jz      loc_1400093D8
0x1400092d0  mov     [r14], edi
0x1400092d3  mov     [r14+4], r13d
0x1400092d7  mov     [r14+8], rbp
0x1400092db  mov     [r14+10h], rbx
0x1400092df  mov     [r14+18h], r15
0x1400092e3  mov     byte ptr [rsi], 1
0x1400092e6  cmp     edi, 1
0x1400092e9  jle     short loc_1400092FA
0x1400092eb  lea     r8, [rdi-1]; Size
0x1400092ef  xor     edx, edx; Val
0x1400092f1  lea     rcx, [rsi+1]; void *
0x1400092f5  call    memset
0x1400092fa  xor     r8d, r8d
0x1400092fd  lea     ebx, [r13-1]
0x140009301  lea     r11, [rdi+rsi]
0x140009305  mov     r10, rdi
0x140009308  test    ebx, ebx
0x14000930a  jle     short loc_140009343
0x14000930c  xor     r9d, r9d
0x14000930f  test    edi, edi
0x140009311  jle     short loc_140009338
0x140009313  mov     ecx, r9d
0x140009316  imul    ecx, r8d
0x14000931a  call    ModNN
0x14000931f  movzx   eax, al
0x140009322  lea     rdx, gFECExp
0x140009329  mov     al, [rax+rdx]
0x14000932c  mov     [r9+r11], al
0x140009330  inc     r9d
0x140009333  cmp     r9d, edi
0x140009336  jl      short loc_140009313
0x140009338  inc     r8d
0x14000933b  add     r11, rdi
0x14000933e  cmp     r8d, ebx
0x140009341  jl      short loc_14000930C
0x140009343  mov     eax, edi
0x140009345  mov     rdx, rsi
0x140009348  imul    eax, r13d
0x14000934c  movsxd  r8, eax
0x14000934f  lea     eax, [rdi+rdi]
0x140009352  add     r8, rsi
0x140009355  movsxd  rcx, eax
0x140009358  add     rcx, r8
0x14000935b  mov     [rsp+98h+var_78], rcx
0x140009360  mov     ecx, edi
0x140009362  lea     r9, [r8+r10]
0x140009366  call    InvertVdm
0x14000936b  mov     r8, [r14+8]
0x14000936f  mov     eax, edi
0x140009371  imul    eax, edi
0x140009374  sub     r13d, edi
0x140009377  mov     dword ptr [rsp+98h+var_70], edi
0x14000937b  mov     r9d, r13d
0x14000937e  mov     rdx, rsi
0x140009381  mov     dword ptr [rsp+98h+var_78], edi
0x140009385  movsxd  rbx, eax
0x140009388  add     r8, rbx
0x14000938b  lea     rcx, [rbx+rsi]
0x14000938f  call    MatrixMultiply
0x140009394  mov     rcx, [r14+8]; void *
0x140009398  mov     r8, rbx; Size
0x14000939b  xor     edx, edx; Val
0x14000939d  call    memset
0x1400093a2  mov     rcx, [r14+8]
0x1400093a6  xor     edx, edx
0x1400093a8  test    edi, edi
0x1400093aa  jle     short loc_1400093BE
0x1400093ac  lea     eax, [rdi+1]
0x1400093af  movsxd  r8, eax
0x1400093b2  mov     byte ptr [rcx], 1
0x1400093b5  inc     edx
0x1400093b7  add     rcx, r8
0x1400093ba  cmp     edx, edi
0x1400093bc  jl      short loc_1400093B2
0x1400093be  xor     edx, edx; Tag
0x1400093c0  mov     rcx, rsi; P
0x1400093c3  call    cs:__imp_ExFreePoolWithTag
0x1400093ca  nop     dword ptr [rax+rax+00h]
0x1400093cf  xor     eax, eax
0x1400093d1  jmp     loc_140009473
0x1400093d6  xor     esi, esi
0x1400093d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400093df  lea     rax, WPP_GLOBAL_Control
0x1400093e6  cmp     rcx, rax
0x1400093e9  jz      short loc_140009416
0x1400093eb  mov     eax, [rcx+2Ch]
0x1400093ee  test    al, 2
0x1400093f0  jz      short loc_140009416
0x1400093f2  mov     rcx, [rcx+18h]
0x1400093f6  mov     r9d, r13d
0x1400093f9  mov     [rsp+98h+var_58], rsi
0x1400093fe  mov     [rsp+98h+var_60], rbx
0x140009403  mov     [rsp+98h+var_68], rbp
0x140009408  mov     [rsp+98h+var_70], r14
0x14000940d  mov     dword ptr [rsp+98h+var_78], edi
0x140009411  call    WPP_SF_ddqqqq
0x140009416  test    r15, r15
0x140009419  jz      short loc_14000942C
0x14000941b  xor     edx, edx; Tag
0x14000941d  mov     rcx, r15; P
0x140009420  call    cs:__imp_ExFreePoolWithTag
0x140009427  nop     dword ptr [rax+rax+00h]
0x14000942c  test    rbx, rbx
0x14000942f  jz      short loc_140009442
0x140009431  xor     edx, edx; Tag
0x140009433  mov     rcx, rbx; P
0x140009436  call    cs:__imp_ExFreePoolWithTag
0x14000943d  nop     dword ptr [rax+rax+00h]
0x140009442  test    rsi, rsi
0x140009445  jz      short loc_140009458
0x140009447  xor     edx, edx; Tag
0x140009449  mov     rcx, rsi; P
0x14000944c  call    cs:__imp_ExFreePoolWithTag
0x140009453  nop     dword ptr [rax+rax+00h]
0x140009458  test    rbp, rbp
0x14000945b  jz      short loc_14000946E
0x14000945d  xor     edx, edx; Tag
0x14000945f  mov     rcx, rbp; P
0x140009462  call    cs:__imp_ExFreePoolWithTag
0x140009469  nop     dword ptr [rax+rax+00h]
0x14000946e  mov     eax, 0C000009Ah
0x140009473  add     rsp, 58h
0x140009477  pop     r15
0x140009479  pop     r14
0x14000947b  pop     r13
0x14000947d  pop     r12
0x14000947f  pop     rdi
0x140009480  pop     rsi
0x140009481  pop     rbp
0x140009482  pop     rbx
0x140009483  retn
```
