# TdxQueryAddressComplete

- ea: `0x1400159f0`
- end: `0x140015c18`
- name: `TdxQueryAddressComplete`
- size: `552`
- prototype: `void __fastcall(unsigned int **, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140005688`

## callees

- `0x140001980`
- `0x1400047d0`
- `0x1400054ec`
- `0x140010cac`
- `0x1400159f0`
- `0x1400184b0`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140015a96`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140015a96`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140015a86`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140015a86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015bd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015bd3`
- `ntoskrnl!IofCompleteRequest` at `0x140015be4`
- `ntoskrnl!IofCompleteRequest` at `0x140015be4`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140015aa5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140015aa5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140015a75`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140015a75`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015a2c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015a2c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015aca`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015aca`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140015b80`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140015b80`

## string_xrefs

- `0x140015bab`: `TdxQueryAddressComplete`

## pseudocode

```c
void __fastcall TdxQueryAddressComplete(unsigned int **a1, int a2)
{
  unsigned int *v2; // rsi
  unsigned int *v4; // rdi
  char *v5; // r15
  KSPIN_LOCK *v6; // r12
  KIRQL v7; // r13
  __int64 v8; // r8
  unsigned int **v9; // rcx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  char v12; // bl
  __int64 v13; // rdx
  _WORD *v14; // rcx
  int v15; // eax
  __int64 v16; // rax
  KIRQL Irql[4]; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-A5h] BYREF
  __int64 v19; // [rsp+38h] [rbp-A1h] BYREF
  _WORD v20[2]; // [rsp+40h] [rbp-99h] BYREF
  int v21; // [rsp+44h] [rbp-95h]
  __int64 v22; // [rsp+48h] [rbp-91h]
  int v23; // [rsp+50h] [rbp-89h] BYREF
  _BYTE v24[140]; // [rsp+54h] [rbp-85h] BYREF

  v2 = *a1;
  v4 = a1[1];
  v5 = (char *)a1[3];
  v6 = (KSPIN_LOCK *)(*a1 + 2);
  v7 = KeAcquireSpinLockRaiseToDpc(v6);
  v8 = *((_QWORD *)v4 + 21);
  if ( *(unsigned int **)(v8 + 8) != v4 + 42 || (v9 = (unsigned int **)*((_QWORD *)v4 + 22), *v9 != v4 + 42) )
    __fastfail(3u);
  *v9 = (unsigned int *)v8;
  *(_QWORD *)(v8 + 8) = v9;
  if ( !_InterlockedExchange64((volatile __int64 *)v4 + 13, 0) )
  {
    Irql[0] = 0;
    KeReleaseSpinLockFromDpcLevel(v6);
    IoAcquireCancelSpinLock(Irql);
    IoReleaseCancelSpinLock(Irql[0]);
    KeAcquireSpinLockAtDpcLevel(v6);
  }
  v10 = *v2;
  if ( v2[1] == 1 )
    v11 = v10 >> 6;
  else
    v11 = v10 >> 11;
  v12 = v11 & 1;
  KeReleaseSpinLock(v6, v7);
  *((_QWORD *)v4 + 7) = 0;
  if ( !a2 )
  {
    v19 = 0;
    v23 = 0;
    v18 = 134;
    if ( v12 && *(_WORD *)v5 == 23 && IN6_IS_ADDR_UNSPECIFIED((const IN6_ADDR *)(v5 + 8)) )
    {
      v20[0] = 2;
      v22 = 0;
      v14 = v20;
      v13 = 0;
      v20[1] = *((_WORD *)v5 + 1);
      v21 = 0;
    }
    else
    {
      LOBYTE(v13) = v12;
      v14 = v5;
    }
    v15 = SockAddrToTaList(v14, v13, v24, &v18);
    v19 = v15;
    if ( v15 )
    {
      RtlCopyKernelBufferToMdl(&v23, *((_QWORD *)v4 + 1), 0, v15 + 4LL, &v19);
      v16 = v19;
      a2 = 0;
    }
    else
    {
      v16 = v18;
      a2 = -1073741789;
    }
    *((_QWORD *)v4 + 7) = v16;
  }
  v4[12] = a2;
  if ( v2[1] == 2 )
    DbgTdxDereferenceConnection(v2, "TdxQueryAddressComplete", 485);
  else
    DbgTdxDereferenceTransportAddress(v2, "minio\\netio\\session\\tdi\\request.c", 487);
  ExFreePoolWithTag(v5, 0x49786454u);
  IofCompleteRequest((PIRP)v4, 0);
}

```

## disassembly

```asm
0x1400159f0  push    rbp
0x1400159f2  push    rbx
0x1400159f3  push    rsi
0x1400159f4  push    rdi
0x1400159f5  push    r12
0x1400159f7  push    r13
0x1400159f9  push    r14
0x1400159fb  push    r15
0x1400159fd  lea     rbp, [rsp-1Fh]
0x140015a02  sub     rsp, 0F8h
0x140015a09  mov     rax, cs:__security_cookie
0x140015a10  xor     rax, rsp
0x140015a13  mov     [rbp+57h+var_50], rax
0x140015a17  mov     rsi, [rcx]
0x140015a1a  mov     r14d, edx
0x140015a1d  mov     rdi, [rcx+8]
0x140015a21  mov     r15, [rcx+18h]
0x140015a25  lea     r12, [rsi+8]
0x140015a29  mov     rcx, r12; SpinLock
0x140015a2c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015a33  nop     dword ptr [rax+rax+00h]
0x140015a38  lea     rdx, [rdi+0A8h]
0x140015a3f  mov     r13b, al
0x140015a42  mov     r8, [rdx]
0x140015a45  cmp     [r8+8], rdx
0x140015a49  jnz     loc_140015C11
0x140015a4f  mov     rcx, [rdx+8]
0x140015a53  cmp     [rcx], rdx
0x140015a56  jnz     loc_140015C11
0x140015a5c  mov     [rcx], r8
0x140015a5f  xor     eax, eax
0x140015a61  mov     [r8+8], rcx
0x140015a65  xchg    rax, [rdi+68h]
0x140015a69  test    rax, rax
0x140015a6c  jnz     short loc_140015AB1
0x140015a6e  mov     rcx, r12; SpinLock
0x140015a71  mov     [rsp+130h+Irql], al
0x140015a75  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140015a7c  nop     dword ptr [rax+rax+00h]
0x140015a81  lea     rcx, [rsp+130h+Irql]; Irql
0x140015a86  call    cs:__imp_IoAcquireCancelSpinLock
0x140015a8d  nop     dword ptr [rax+rax+00h]
0x140015a92  mov     cl, [rsp+130h+Irql]; Irql
0x140015a96  call    cs:__imp_IoReleaseCancelSpinLock
0x140015a9d  nop     dword ptr [rax+rax+00h]
0x140015aa2  mov     rcx, r12; SpinLock
0x140015aa5  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140015aac  nop     dword ptr [rax+rax+00h]
0x140015ab1  cmp     dword ptr [rsi+4], 1
0x140015ab5  mov     ebx, [rsi]
0x140015ab7  jnz     short loc_140015ABE
0x140015ab9  shr     ebx, 6
0x140015abc  jmp     short loc_140015AC1
0x140015abe  shr     ebx, 0Bh
0x140015ac1  mov     dl, r13b; NewIrql
0x140015ac4  mov     rcx, r12; SpinLock
0x140015ac7  and     bl, 1
0x140015aca  call    cs:__imp_KeReleaseSpinLock
0x140015ad1  nop     dword ptr [rax+rax+00h]
0x140015ad6  xor     r12d, r12d
0x140015ad9  mov     [rdi+38h], r12
0x140015add  lea     r13d, [r12+2]
0x140015ae2  test    r14d, r14d
0x140015ae5  jnz     loc_140015B98
0x140015aeb  mov     [rsp+130h+var_F8], r12
0x140015af0  mov     [rsp+130h+var_E0], r12d
0x140015af5  mov     [rsp+130h+var_FC], 86h
0x140015afd  test    bl, bl
0x140015aff  jz      short loc_140015B3A
0x140015b01  cmp     word ptr [r15], 17h
0x140015b06  jnz     short loc_140015B3A
0x140015b08  lea     rcx, [r15+8]; a
0x140015b0c  call    IN6_IS_ADDR_UNSPECIFIED
0x140015b11  test    al, al
0x140015b13  jz      short loc_140015B3A
0x140015b15  xor     eax, eax
0x140015b17  mov     [rsp+130h+var_F0], r13w
0x140015b1d  mov     [rsp+130h+var_E8], rax
0x140015b22  lea     rcx, [rsp+130h+var_F0]
0x140015b27  movzx   eax, word ptr [r15+2]
0x140015b2c  xor     edx, edx
0x140015b2e  mov     [rsp+130h+var_EE], ax
0x140015b33  mov     [rsp+130h+var_EC], r12d
0x140015b38  jmp     short loc_140015B3F
0x140015b3a  mov     dl, bl
0x140015b3c  mov     rcx, r15
0x140015b3f  lea     r9, [rsp+130h+var_FC]
0x140015b44  lea     r8, [rsp+130h+var_DC]
0x140015b49  call    SockAddrToTaList
0x140015b4e  movsxd  r9, eax
0x140015b51  mov     [rsp+130h+var_F8], r9
0x140015b56  test    eax, eax
0x140015b58  jnz     short loc_140015B66
0x140015b5a  mov     eax, [rsp+130h+var_FC]
0x140015b5e  mov     r14d, 0C0000023h
0x140015b64  jmp     short loc_140015B94
0x140015b66  mov     rdx, [rdi+8]
0x140015b6a  lea     rax, [rsp+130h+var_F8]
0x140015b6f  add     r9, 4
0x140015b73  mov     [rsp+130h+var_110], rax
0x140015b78  xor     r8d, r8d
0x140015b7b  lea     rcx, [rsp+130h+var_E0]
0x140015b80  call    cs:__imp_RtlCopyKernelBufferToMdl
0x140015b87  nop     dword ptr [rax+rax+00h]
0x140015b8c  mov     rax, [rsp+130h+var_F8]
0x140015b91  mov     r14d, r12d
0x140015b94  mov     [rdi+38h], rax
0x140015b98  mov     [rdi+30h], r14d
0x140015b9c  mov     rcx, rsi
0x140015b9f  cmp     [rsi+4], r13d
0x140015ba3  jnz     short loc_140015BB9
0x140015ba5  mov     r8d, 1E5h
0x140015bab  lea     rdx, aTdxqueryaddres; "TdxQueryAddressComplete"
0x140015bb2  call    DbgTdxDereferenceConnection
0x140015bb7  jmp     short loc_140015BCB
0x140015bb9  mov     r8d, 1E7h
0x140015bbf  lea     rdx, aMinioNetioSess_0; "minio\\netio\\session\\tdi\\request.c"
0x140015bc6  call    DbgTdxDereferenceTransportAddress
0x140015bcb  mov     edx, 49786454h; Tag
0x140015bd0  mov     rcx, r15; P
0x140015bd3  call    cs:__imp_ExFreePoolWithTag
0x140015bda  nop     dword ptr [rax+rax+00h]
0x140015bdf  xor     edx, edx; PriorityBoost
0x140015be1  mov     rcx, rdi; Irp
0x140015be4  call    cs:__imp_IofCompleteRequest
0x140015beb  nop     dword ptr [rax+rax+00h]
0x140015bf0  mov     rcx, [rbp+57h+var_50]
0x140015bf4  xor     rcx, rsp; StackCookie
0x140015bf7  call    __security_check_cookie
0x140015bfc  add     rsp, 0F8h
0x140015c03  pop     r15
0x140015c05  pop     r14
0x140015c07  pop     r13
0x140015c09  pop     r12
0x140015c0b  pop     rdi
0x140015c0c  pop     rsi
0x140015c0d  pop     rbx
0x140015c0e  pop     rbp
0x140015c0f  retn
0x140015c11  mov     ecx, 3
0x140015c16  int     29h; Win8: RtlFailFast(ecx)
```
