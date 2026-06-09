# SkiTerminateAllThreads

- ea: `0x140099834`
- end: `0x1400999c3`
- name: `SkiTerminateAllThreads`
- size: `399`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140014dd0`
- `0x140099404`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x140034154`
- `0x140035c4c`
- `0x140099338`
- `0x140099834`
- `0x14009b778`
- `0x1400b5a84`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkiTerminateAllThreads(__int64 a1, char a2, unsigned int a3)
{
  volatile signed __int32 **v6; // rdi
  char v7; // r14
  volatile signed __int32 **i; // r10
  char v9; // al
  unsigned int v10; // r9d
  __int64 v11; // r10
  unsigned int v12; // ecx
  int v13; // ebx
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  volatile signed __int32 *j; // rbx
  _QWORD v18[3]; // [rsp+28h] [rbp-150h] BYREF
  signed __int32 v19[64]; // [rsp+40h] [rbp-138h] BYREF

  memset_0(v19, 0, sizeof(v19));
  v18[1] = v18;
  v18[0] = v18;
  v6 = (volatile signed __int32 **)(a1 + 16);
  v7 = SkAcquireSpinLockExclusive(a1 + 4);
  for ( i = *(volatile signed __int32 ***)(a1 + 16); i != v6; i = *(volatile signed __int32 ***)v11 )
  {
    v9 = SkAcquireRundownProtection(i + 27);
    v12 = v10 | 8;
    if ( !v9 )
      v12 = v10;
    _InterlockedOr((volatile signed __int32 *)(v11 + 172), v12);
  }
  v13 = 0;
  memset_0(v19, 0, sizeof(v19));
  v15 = 0;
  if ( (_DWORD)SkeNumberProcessors )
  {
    do
    {
      v14 = (unsigned int)v15;
      if ( *(_QWORD *)(SkeProcessorBlock[v15] + 64) == a1 )
      {
        v14 = (unsigned __int64)(unsigned int)v15 >> 5;
        _interlockedbittestandset(&v19[v14], v15 & 0x1F);
        ++v13;
      }
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < (unsigned int)SkeNumberProcessors );
    if ( v13 )
      SkeGenericIpiCall(v19, 0, 0, 0);
  }
  for ( j = *v6; j != (volatile signed __int32 *)v6; j = *(volatile signed __int32 **)j )
  {
    if ( a2 )
    {
      LOBYTE(v14) = 1;
      SkiSetThreadExitStatus(j, v14, a3);
    }
    if ( (j[43] & 8) != 0 )
    {
      _InterlockedAnd(j + 43, 0xFFFFFFF7);
      SkReleaseRundownProtection(j + 54, v18);
    }
  }
  LOBYTE(v14) = v7;
  SkReleaseSpinLockExclusive(a1 + 4, v14);
  return SkWakeDeferredRundownList(v18);
}

```

## disassembly

```asm
0x140099834  mov     [rsp+arg_8], rbx
0x140099839  mov     [rsp+arg_10], rbp
0x14009983e  push    rsi
0x14009983f  push    rdi
0x140099840  push    r12
0x140099842  push    r14
0x140099844  push    r15
0x140099846  sub     rsp, 150h
0x14009984d  mov     rax, cs:__security_cookie
0x140099854  xor     rax, rsp
0x140099857  mov     [rsp+178h+var_38], rax
0x14009985f  mov     r12d, r8d
0x140099862  mov     r15b, dl
0x140099865  mov     rsi, rcx
0x140099868  xor     edx, edx; Val
0x14009986a  mov     r8d, 100h; Size
0x140099870  lea     rcx, [rsp+178h+var_138]; void *
0x140099875  call    memset_0
0x14009987a  lea     rax, [rsp+178h+var_150]
0x14009987f  mov     [rsp+178h+var_148], rax
0x140099884  lea     rcx, [rsi+4]
0x140099888  lea     rax, [rsp+178h+var_150]
0x14009988d  mov     [rsp+178h+var_150], rax
0x140099892  call    SkAcquireSpinLockExclusive
0x140099897  lea     rdi, [rsi+10h]
0x14009989b  mov     r14b, al
0x14009989e  mov     r10, [rdi]
0x1400998a1  jmp     short loc_1400998D7
0x1400998a3  mov     [rsp+178h+var_158], 0
0x1400998ab  lea     rcx, [r10+0D8h]
0x1400998b2  mov     r9d, [rsp+178h+var_158]
0x1400998b7  or      r9d, 2
0x1400998bb  call    SkAcquireRundownProtection
0x1400998c0  mov     ecx, r9d
0x1400998c3  or      ecx, 8
0x1400998c6  test    al, al
0x1400998c8  cmovz   ecx, r9d
0x1400998cc  lock or [r10+0ACh], ecx
0x1400998d4  mov     r10, [r10]
0x1400998d7  cmp     r10, rdi
0x1400998da  jnz     short loc_1400998A3
0x1400998dc  xor     edx, edx; Val
0x1400998de  lea     rcx, [rsp+178h+var_138]; void *
0x1400998e3  mov     r8d, 100h; Size
0x1400998e9  xor     ebx, ebx
0x1400998eb  call    memset_0
0x1400998f0  xor     ecx, ecx
0x1400998f2  cmp     cs:SkeNumberProcessors, ecx
0x1400998f8  jz      short loc_14009993E
0x1400998fa  lea     rax, SkeProcessorBlock
0x140099901  mov     edx, ecx
0x140099903  mov     rax, [rax+rcx*8]
0x140099907  cmp     [rax+40h], rsi
0x14009990b  jnz     short loc_14009991E
0x14009990d  shr     rdx, 5
0x140099911  mov     eax, ecx
0x140099913  and     eax, 1Fh
0x140099916  lock bts [rsp+rdx*4+178h+var_138], eax
0x14009991c  inc     ebx
0x14009991e  inc     ecx
0x140099920  cmp     ecx, cs:SkeNumberProcessors
0x140099926  jb      short loc_1400998FA
0x140099928  test    ebx, ebx
0x14009992a  jz      short loc_14009993E
0x14009992c  xor     r9d, r9d
0x14009992f  lea     rcx, [rsp+178h+var_138]
0x140099934  xor     r8d, r8d
0x140099937  xor     edx, edx
0x140099939  call    SkeGenericIpiCall
0x14009993e  mov     rbx, [rdi]
0x140099941  jmp     short loc_14009997B
0x140099943  test    r15b, r15b
0x140099946  jz      short loc_140099955
0x140099948  mov     r8d, r12d
0x14009994b  mov     dl, 1
0x14009994d  mov     rcx, rbx
0x140099950  call    SkiSetThreadExitStatus
0x140099955  mov     eax, [rbx+0ACh]
0x14009995b  test    al, 8
0x14009995d  jz      short loc_140099978
0x14009995f  lock and dword ptr [rbx+0ACh], 0FFFFFFF7h
0x140099967  lea     rcx, [rbx+0D8h]
0x14009996e  lea     rdx, [rsp+178h+var_150]
0x140099973  call    SkReleaseRundownProtection
0x140099978  mov     rbx, [rbx]
0x14009997b  cmp     rbx, rdi
0x14009997e  jnz     short loc_140099943
0x140099980  mov     dl, r14b
0x140099983  lea     rcx, [rsi+4]
0x140099987  call    SkReleaseSpinLockExclusive
0x14009998c  lea     rcx, [rsp+178h+var_150]
0x140099991  call    SkWakeDeferredRundownList
0x140099996  mov     rcx, [rsp+178h+var_38]
0x14009999e  xor     rcx, rsp; StackCookie
0x1400999a1  call    __security_check_cookie
0x1400999a6  lea     r11, [rsp+178h+var_28]
0x1400999ae  mov     rbx, [r11+38h]
0x1400999b2  mov     rbp, [r11+40h]
0x1400999b6  mov     rsp, r11
0x1400999b9  pop     r15
0x1400999bb  pop     r14
0x1400999bd  pop     r12
0x1400999bf  pop     rdi
0x1400999c0  pop     rsi
0x1400999c1  retn
```
