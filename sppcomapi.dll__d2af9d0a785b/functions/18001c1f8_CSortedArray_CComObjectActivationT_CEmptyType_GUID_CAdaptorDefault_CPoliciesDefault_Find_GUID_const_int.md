# CSortedArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Find(_GUID const &,int *)

- ea: `0x18001c1f8`
- end: `0x18001c2fa`
- name: `?Find@?$CSortedArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NAEBU_GUID@@PEAH@Z`
- size: `258`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001ca2c`
- `0x18001deb0`

## callees

- `0x18001c1f8`
- `0x18003c506`

## pseudocode

```c
char __fastcall CSortedArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Find(
        __int64 a1,
        const void *a2,
        int *a3)
{
  int v3; // r14d
  int *v5; // rdi
  int v6; // ebp
  unsigned int v7; // esi
  char v8; // bl
  __int64 v9; // rdi
  signed int v10; // r13d
  __int64 v12; // [rsp+60h] [rbp+8h]

  v3 = *(_DWORD *)(a1 + 4);
  v5 = a3;
  v12 = *(_QWORD *)(a1 + 8);
  if ( v3 )
  {
    v6 = 0;
    v7 = *(_DWORD *)(a1 + 4);
    if ( v3 <= 0 )
      goto LABEL_10;
    v8 = 1;
    v9 = *(_QWORD *)(a1 + 8);
    do
    {
      v10 = (v7 >> 1) + v6;
      if ( memcmp_0((const void *)(*(_QWORD *)(v9 + 8LL * v10) + 4LL), a2, 0x10u) < 0 )
      {
        v6 = v10 + 1;
        v7 += -1 - (v7 >> 1);
      }
      else
      {
        v7 >>= 1;
      }
    }
    while ( (int)v7 > 0 );
    v5 = a3;
    if ( v6 >= v3 || memcmp_0(a2, (const void *)(*(_QWORD *)(v12 + 8LL * v6) + 4LL), 0x10u) < 0 )
LABEL_10:
      v8 = 0;
    if ( v5 )
      *v5 = v6;
  }
  else
  {
    v8 = 0;
    if ( a3 )
      *a3 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x18001c1f8  mov     [rsp+arg_8], rbx
0x18001c1fd  mov     [rsp+arg_10], r8
0x18001c202  push    rbp
0x18001c203  push    rsi
0x18001c204  push    rdi
0x18001c205  push    r12
0x18001c207  push    r13
0x18001c209  push    r14
0x18001c20b  push    r15
0x18001c20d  sub     rsp, 20h
0x18001c211  mov     r14d, [rcx+4]
0x18001c215  mov     r12, rdx
0x18001c218  mov     rdx, [rcx+8]
0x18001c21c  mov     rdi, r8
0x18001c21f  mov     [rsp+58h+arg_0], rdx
0x18001c224  test    r14d, r14d
0x18001c227  jz      loc_18001C2D4
0x18001c22d  xor     ebp, ebp
0x18001c22f  mov     esi, r14d
0x18001c232  test    r14d, r14d
0x18001c235  jle     loc_18001C2C9
0x18001c23b  lea     ebx, [rbp+1]
0x18001c23e  mov     rdi, rdx
0x18001c241  mov     r15d, esi
0x18001c244  mov     r8d, 10h; Size
0x18001c24a  shr     r15d, 1
0x18001c24d  mov     rdx, r12; Buf2
0x18001c250  lea     r13d, [r15+rbp]
0x18001c254  movsxd  rax, r13d
0x18001c257  mov     rcx, [rdi+rax*8]
0x18001c25b  add     rcx, 4; Buf1
0x18001c25f  call    memcmp_0
0x18001c264  mov     ecx, eax
0x18001c266  test    eax, eax
0x18001c268  jle     short loc_18001C26E
0x18001c26a  mov     eax, ebx
0x18001c26c  jmp     short loc_18001C274
0x18001c26e  xor     eax, eax
0x18001c270  test    ecx, ecx
0x18001c272  js      short loc_18001C27D
0x18001c274  test    eax, eax
0x18001c276  js      short loc_18001C27D
0x18001c278  mov     esi, r15d
0x18001c27b  jmp     short loc_18001C289
0x18001c27d  or      eax, 0FFFFFFFFh
0x18001c280  lea     ebp, [r13+1]
0x18001c284  sub     eax, r15d
0x18001c287  add     esi, eax
0x18001c289  test    esi, esi
0x18001c28b  jg      short loc_18001C241
0x18001c28d  mov     rdi, [rsp+58h+arg_10]
0x18001c292  cmp     ebp, r14d
0x18001c295  jge     short loc_18001C2C9
0x18001c297  mov     rdx, [rsp+58h+arg_0]
0x18001c29c  mov     r8d, 10h; Size
0x18001c2a2  movsxd  rax, ebp
0x18001c2a5  mov     rcx, r12; Buf1
0x18001c2a8  mov     rdx, [rdx+rax*8]
0x18001c2ac  add     rdx, 4; Buf2
0x18001c2b0  call    memcmp_0
0x18001c2b5  mov     ecx, eax
0x18001c2b7  test    eax, eax
0x18001c2b9  jle     short loc_18001C2BF
0x18001c2bb  mov     eax, ebx
0x18001c2bd  jmp     short loc_18001C2C5
0x18001c2bf  xor     eax, eax
0x18001c2c1  test    ecx, ecx
0x18001c2c3  js      short loc_18001C2C9
0x18001c2c5  test    eax, eax
0x18001c2c7  jns     short loc_18001C2CB
0x18001c2c9  xor     bl, bl
0x18001c2cb  test    rdi, rdi
0x18001c2ce  jz      short loc_18001C2E2
0x18001c2d0  mov     [rdi], ebp
0x18001c2d2  jmp     short loc_18001C2E2
0x18001c2d4  xor     bl, bl
0x18001c2d6  test    r8, r8
0x18001c2d9  jz      short loc_18001C2E2
0x18001c2db  mov     dword ptr [r8], 0
0x18001c2e2  mov     al, bl
0x18001c2e4  mov     rbx, [rsp+58h+arg_8]
0x18001c2e9  add     rsp, 20h
0x18001c2ed  pop     r15
0x18001c2ef  pop     r14
0x18001c2f1  pop     r13
0x18001c2f3  pop     r12
0x18001c2f5  pop     rdi
0x18001c2f6  pop     rsi
0x18001c2f7  pop     rbp
0x18001c2f8  retn
```
