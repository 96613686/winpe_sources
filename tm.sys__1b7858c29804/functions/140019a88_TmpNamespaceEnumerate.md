# TmpNamespaceEnumerate

- ea: `0x140019a88`
- end: `0x140019cfe`
- name: `TmpNamespaceEnumerate`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400168d0`

## callees

- `0x140019a88`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140019aec`
- `ntoskrnl!KeWaitForSingleObject` at `0x140019aec`
- `ntoskrnl!KeReleaseMutex` at `0x140019cd6`
- `ntoskrnl!KeReleaseMutex` at `0x140022cbb`
- `ntoskrnl!KeReleaseMutex` at `0x140019cd6`
- `ntoskrnl!KeReleaseMutex` at `0x140022cbb`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022c6c`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022c89`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022c6c`
- `ntoskrnl!ExSystemExceptionFilter` at `0x140022c89`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x140019b92`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x140019b92`

## pseudocode

```c
__int64 __fastcall TmpNamespaceEnumerate(__int64 a1, void *a2, __int64 a3, int a4, _DWORD *a5)
{
  unsigned int v8; // ebx
  unsigned int v9; // esi
  unsigned int v10; // r13d
  _QWORD *v11; // rax
  void *Buffer; // rcx
  _QWORD *v13; // r12
  _BYTE *v14; // r8
  _OWORD *v15; // rdx
  ULONG DeleteCount; // [rsp+4Ch] [rbp-6Ch] BYREF
  _OWORD *v18; // [rsp+50h] [rbp-68h]
  _QWORD *v19; // [rsp+58h] [rbp-60h]
  PVOID RestartKey; // [rsp+60h] [rbp-58h] BYREF
  _OWORD *v21; // [rsp+68h] [rbp-50h]
  PRKMUTEX Mutex; // [rsp+70h] [rbp-48h]
  __int128 v23; // [rsp+78h] [rbp-40h] BYREF

  v18 = (_OWORD *)a3;
  RestartKey = 0;
  DeleteCount = 0;
  v8 = 0;
  v9 = 0;
  v23 = 0;
  Mutex = (PRKMUTEX)(a1 + 104);
  KeWaitForSingleObject((PVOID)(a1 + 104), Executive, 0, 0, 0);
  *a5 = 0;
  v10 = (unsigned int)(a4 - 20) >> 4;
  v11 = (_QWORD *)(a1 + 96);
  if ( v10 )
  {
    DWORD2(v23) = 1;
    Buffer = a2;
    *(_QWORD *)&v23 = a2;
    v13 = (_QWORD *)(a1 + 96);
    v19 = v11;
    *v11 = &v23;
    *a5 += 20;
    while ( v9 < v10 )
    {
      v21 = 0;
      v14 = RtlEnumerateGenericTableLikeADirectory((PRTL_AVL_TABLE)a1, 0, 0, 1u, &RestartKey, &DeleteCount, Buffer);
      if ( !v14 )
        break;
      v15 = &v14[*(unsigned __int16 *)(a1 + 162) - (unsigned __int64)*(unsigned __int16 *)(a1 + 160) - 32];
      v21 = v15;
      if ( !*v14 )
      {
        *(_OWORD *)(16LL * v9++ + a3 + 20) = *v15;
        *a5 += 16;
      }
      Buffer = a2;
    }
    if ( v9 )
    {
      *(_DWORD *)(a3 + 16) = v9;
      *v18 = *(_OWORD *)(a3 + 16LL * (v9 - 1) + 20);
      if ( v9 < v10 )
        v8 = -2147483622;
    }
    else
    {
      v8 = -2147483622;
      *a5 = 0;
    }
    v11 = v13;
  }
  else
  {
    v8 = -1073741811;
  }
  *v11 = 0;
  KeReleaseMutex(Mutex, 0);
  return v8;
}

```

## disassembly

```asm
0x140019a88  mov     rax, rsp
0x140019a8b  mov     [rax+20h], rbx
0x140019a8f  mov     [rax+18h], r8
0x140019a93  mov     [rax+10h], rdx
0x140019a97  mov     [rax+8], rcx
0x140019a9b  push    rsi
0x140019a9c  push    r12
0x140019a9e  push    r13
0x140019aa0  push    r14
0x140019aa2  push    r15
0x140019aa4  sub     rsp, 90h
0x140019aab  mov     r13d, r9d
0x140019aae  mov     r14, r8
0x140019ab1  mov     r12, rcx
0x140019ab4  mov     [rsp+0B8h+var_68], r8
0x140019ab9  mov     qword ptr [rax-58h], 0
0x140019ac1  mov     dword ptr [rax-6Ch], 0
0x140019ac8  xor     ebx, ebx
0x140019aca  xor     esi, esi
0x140019acc  mov     [rax-74h], esi
0x140019acf  xorps   xmm0, xmm0
0x140019ad2  movups  xmmword ptr [rax-40h], xmm0
0x140019ad6  add     rcx, 68h ; 'h'; Object
0x140019ada  mov     [rsp+0B8h+Mutex], rcx
0x140019adf  mov     [rsp+0B8h+Timeout], rsi; Timeout
0x140019ae4  xor     r9d, r9d; Alertable
0x140019ae7  xor     r8d, r8d; WaitMode
0x140019aea  xor     edx, edx; WaitReason
0x140019aec  call    cs:__imp_KeWaitForSingleObject
0x140019af3  nop     dword ptr [rax+rax+00h]
0x140019af8  mov     r15, [rsp+0B8h+arg_20]
0x140019b00  mov     [r15], esi
0x140019b03  add     r13d, 0FFFFFFECh
0x140019b07  shr     r13d, 4
0x140019b0b  mov     [rsp+0B8h+var_70], r13d
0x140019b10  lea     rax, [r12+60h]
0x140019b15  test    r13d, r13d
0x140019b18  jnz     short loc_140019B28
0x140019b1a  mov     ebx, 0C000000Dh
0x140019b1f  mov     [rsp+0B8h+var_78], ebx
0x140019b23  jmp     loc_140019CC8
0x140019b28  mov     [rsp+0B8h+var_38], 1
0x140019b33  mov     rcx, [rsp+0B8h+arg_8]
0x140019b3b  mov     [rsp+0B8h+var_40], rcx
0x140019b40  mov     r12, rax
0x140019b43  mov     [rsp+0B8h+var_60], rax
0x140019b48  lea     rdx, [rsp+0B8h+var_40]
0x140019b4d  mov     [rax], rdx
0x140019b50  add     dword ptr [r15], 14h
0x140019b54  cmp     esi, r13d
0x140019b57  jnb     loc_140019C4A
0x140019b5d  mov     [rsp+0B8h+var_50], 0
0x140019b66  mov     [rsp+0B8h+Buffer], rcx; Buffer
0x140019b6b  lea     rax, [rsp+0B8h+var_6C]
0x140019b70  mov     [rsp+0B8h+DeleteCount], rax; DeleteCount
0x140019b75  lea     rax, [rsp+0B8h+RestartKey]
0x140019b7a  mov     [rsp+0B8h+Timeout], rax; RestartKey
0x140019b7f  mov     r9d, 1; NextFlag
0x140019b85  xor     r8d, r8d; MatchData
0x140019b88  xor     edx, edx; MatchFunction
0x140019b8a  mov     rcx, [rsp+0B8h+Table]; Table
0x140019b92  call    cs:__imp_RtlEnumerateGenericTableLikeADirectory
0x140019b99  nop     dword ptr [rax+rax+00h]
0x140019b9e  mov     r8, rax
0x140019ba1  test    rax, rax
0x140019ba4  jz      loc_140019C4A
0x140019baa  mov     rax, [rsp+0B8h+Table]
0x140019bb2  movzx   edx, word ptr [rax+0A2h]
0x140019bb9  movzx   eax, word ptr [rax+0A0h]
0x140019bc0  sub     rdx, rax
0x140019bc3  add     rdx, 0FFFFFFFFFFFFFFE0h
0x140019bc7  add     rdx, r8
0x140019bca  mov     [rsp+0B8h+var_50], rdx
0x140019bcf  cmp     byte ptr [r8], 0
0x140019bd3  jz      short loc_140019BE2
0x140019bd5  mov     rcx, [rsp+0B8h+arg_8]
0x140019bdd  jmp     loc_140019B54
0x140019be2  cmp     [rsp+0B8h+arg_28], 0
0x140019bea  jnz     short loc_140019BFE
0x140019bec  mov     eax, esi
0x140019bee  shl     rax, 4
0x140019bf2  movups  xmm0, xmmword ptr [rdx]
0x140019bf5  movdqu  xmmword ptr [rax+r14+14h], xmm0
0x140019bfc  jmp     short loc_140019C3E
0x140019bfe  mov     eax, esi
0x140019c00  add     rax, rax
0x140019c03  movups  xmm0, xmmword ptr [rdx]
0x140019c06  movdqu  xmmword ptr [r14+rax*8+14h], xmm0
0x140019c0d  jmp     short loc_140019C33
0x140019c0f  mov     ebx, eax
0x140019c11  mov     [rsp+0B8h+var_78], eax
0x140019c15  mov     r15, [rsp+0B8h+arg_20]
0x140019c1d  mov     r14, [rsp+0B8h+arg_10]
0x140019c25  mov     esi, [rsp+0B8h+var_74]
0x140019c29  mov     r13d, [rsp+0B8h+var_70]
0x140019c2e  mov     r12, [rsp+0B8h+var_60]
0x140019c33  mov     rax, r12
0x140019c36  test    ebx, ebx
0x140019c38  js      loc_140019CC8
0x140019c3e  inc     esi
0x140019c40  mov     [rsp+0B8h+var_74], esi
0x140019c44  add     dword ptr [r15], 10h
0x140019c48  jmp     short loc_140019BD5
0x140019c4a  test    esi, esi
0x140019c4c  jz      short loc_140019CB3
0x140019c4e  cmp     [rsp+0B8h+arg_28], 0
0x140019c56  jnz     short loc_140019C73
0x140019c58  mov     [r14+10h], esi
0x140019c5c  lea     ecx, [rsi-1]
0x140019c5f  add     rcx, rcx
0x140019c62  movups  xmm0, xmmword ptr [r14+rcx*8+14h]
0x140019c68  mov     rax, [rsp+0B8h+var_68]
0x140019c6d  movdqu  xmmword ptr [rax], xmm0
0x140019c71  jmp     short loc_140019CA2
0x140019c73  mov     [r14+10h], esi
0x140019c77  lea     ecx, [rsi-1]
0x140019c7a  add     rcx, rcx
0x140019c7d  movups  xmm0, xmmword ptr [r14+rcx*8+14h]
0x140019c83  mov     rax, [rsp+0B8h+var_68]
0x140019c88  movdqu  xmmword ptr [rax], xmm0
0x140019c8c  jmp     short loc_140019CA2
0x140019c8e  mov     ebx, eax
0x140019c90  mov     [rsp+0B8h+var_78], eax
0x140019c94  mov     esi, [rsp+0B8h+var_74]
0x140019c98  mov     r13d, [rsp+0B8h+var_70]
0x140019c9d  mov     r12, [rsp+0B8h+var_60]
0x140019ca2  mov     eax, 8000001Ah
0x140019ca7  cmp     esi, r13d
0x140019caa  cmovb   ebx, eax
0x140019cad  mov     [rsp+0B8h+var_78], ebx
0x140019cb1  jmp     short loc_140019CC5
0x140019cb3  mov     eax, 8000001Ah
0x140019cb8  mov     ebx, eax
0x140019cba  mov     [rsp+0B8h+var_78], eax
0x140019cbe  mov     dword ptr [r15], 0
0x140019cc5  mov     rax, r12
0x140019cc8  mov     qword ptr [rax], 0
0x140019ccf  xor     edx, edx; Wait
0x140019cd1  mov     rcx, [rsp+0B8h+Mutex]; Mutex
0x140019cd6  call    cs:__imp_KeReleaseMutex
0x140019cdd  nop     dword ptr [rax+rax+00h]
0x140019ce2  mov     eax, ebx
0x140019ce4  mov     rbx, [rsp+0B8h+arg_18]
0x140019cec  add     rsp, 90h
0x140019cf3  pop     r15
0x140019cf5  pop     r14
0x140019cf7  pop     r13
0x140019cf9  pop     r12
0x140019cfb  pop     rsi
0x140019cfc  retn
0x140022c63  push    rbp
0x140022c65  sub     rsp, 40h
0x140022c69  mov     rbp, rdx
0x140022c6c  call    cs:__imp_ExSystemExceptionFilter
0x140022c73  nop     dword ptr [rax+rax+00h]
0x140022c78  nop
0x140022c79  add     rsp, 40h
0x140022c7d  pop     rbp
0x140022c7e  retn
0x140022c80  push    rbp
0x140022c82  sub     rsp, 40h
0x140022c86  mov     rbp, rdx
0x140022c89  call    cs:__imp_ExSystemExceptionFilter
0x140022c90  nop     dword ptr [rax+rax+00h]
0x140022c95  nop
0x140022c96  add     rsp, 40h
0x140022c9a  pop     rbp
0x140022c9b  retn
0x140022c9d  push    rbp
0x140022c9f  sub     rsp, 40h
0x140022ca3  mov     rbp, rdx
0x140022ca6  mov     rcx, [rbp+0C0h]
0x140022cad  mov     qword ptr [rcx+60h], 0
0x140022cb5  add     rcx, 68h ; 'h'; Mutex
0x140022cb9  xor     edx, edx; Wait
0x140022cbb  call    cs:__imp_KeReleaseMutex
0x140022cc2  nop     dword ptr [rax+rax+00h]
0x140022cc7  nop
0x140022cc8  add     rsp, 40h
0x140022ccc  pop     rbp
0x140022ccd  retn
```
