# p9fs::File::ReadDir(unsigned __int64,p9fs::SpanWriter &,bool)

- ea: `0x180020a60`
- end: `0x180020bf5`
- name: `?ReadDir@File@p9fs@@UEAAJ_KAEAVSpanWriter@2@_N@Z`
- size: `405`
- prototype: `__int64 __fastcall(p9fs::File *__hidden this, unsigned __int64, struct p9fs::SpanWriter *, bool)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180004120`
- `0x180004144`
- `0x180004534`
- `0x180020a60`
- `0x180022a5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020ac8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020b5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020b73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020bd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020ac8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020b5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020b73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020bd2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020aa7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020aa7`
- `lxutil!LxUtilFsReadDir` at `0x180020bbe`
- `lxutil!LxUtilFsReadDir` at `0x180020bbe`
- `lxutil!LxUtilDirectoryEnumeratorCleanup` at `0x180020b09`
- `lxutil!LxUtilDirectoryEnumeratorCleanup` at `0x180020b09`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall p9fs::File::ReadDir(RTL_SRWLOCK *this, PVOID a2, struct p9fs::SpanWriter *a3, char a4)
{
  RTL_SRWLOCK *v9; // rbx
  _OWORD *v10; // rax
  PVOID Ptr; // rsi
  _OWORD *v12; // rax
  unsigned int v13; // esi
  char v14; // [rsp+30h] [rbp-40h]
  unsigned int v15; // [rsp+34h] [rbp-3Ch]
  _QWORD v16[2]; // [rsp+40h] [rbp-30h] BYREF
  char v17; // [rsp+50h] [rbp-20h]
  int v18; // [rsp+51h] [rbp-1Fh]
  __int16 v19; // [rsp+55h] [rbp-1Bh]
  char v20; // [rsp+57h] [rbp-19h]
  __int64 v21; // [rsp+58h] [rbp-18h] BYREF

  if ( *((char *)this[9].Ptr + 48) < 0 )
    return 4294967283LL;
  v9 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  if ( (((unsigned __int64)this[6].Ptr + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    if ( !this[12].Ptr )
    {
      v10 = operator new(0x28u);
      *v10 = 0;
      v10[1] = 0;
      *((_QWORD *)v10 + 4) = 0;
      Ptr = this[12].Ptr;
      this[12].Ptr = v10;
      if ( Ptr )
      {
        LxUtilDirectoryEnumeratorCleanup(Ptr);
        operator delete(Ptr, 0x28u);
      }
      v12 = this[12].Ptr;
      *v12 = 0;
      v12[1] = 0;
      *((_QWORD *)v12 + 4) = 0;
    }
    if ( a2 != this[13].Ptr )
      this[13].Ptr = a2;
    p9fs::File::WriteDotEntries((struct p9fs::File *)this);
    if ( v14 )
    {
      if ( (_BYTE)v15 )
      {
        if ( v9 )
          ReleaseSRWLockExclusive(v9);
        return 0;
      }
      else
      {
        v21 = (__int64)this[13].Ptr - 2;
        v16[0] = this;
        v16[1] = a3;
        v17 = a4;
        v18 = 0;
        v19 = 0;
        v20 = 0;
        v13 = LxUtilFsReadDir((char *)this[9].Ptr + 32, this[6].Ptr, this[12].Ptr, &v21, v16);
        LOBYTE(this[14].Ptr) = 0;
        if ( v9 )
          ReleaseSRWLockExclusive(v9);
        return v13;
      }
    }
    else
    {
      if ( v9 )
        ReleaseSRWLockExclusive(v9);
      return v15;
    }
  }
  else
  {
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    return 4294967287LL;
  }
}

```

## disassembly

```asm
0x180020a60  push    rbp
0x180020a62  push    rbx
0x180020a63  push    rsi
0x180020a64  push    rdi
0x180020a65  push    r12
0x180020a67  push    r14
0x180020a69  push    r15
0x180020a6b  mov     rbp, rsp
0x180020a6e  sub     rsp, 70h
0x180020a72  mov     rax, cs:__security_cookie
0x180020a79  xor     rax, rsp
0x180020a7c  mov     [rbp+var_10], rax
0x180020a80  mov     r12b, r9b
0x180020a83  mov     r15, r8
0x180020a86  mov     r14, rdx
0x180020a89  mov     rdi, rcx
0x180020a8c  mov     rax, [rcx+48h]
0x180020a90  test    byte ptr [rax+30h], 80h
0x180020a94  jz      short loc_180020AA0
0x180020a96  mov     eax, 0FFFFFFF3h
0x180020a9b  jmp     loc_180020BDA
0x180020aa0  lea     rbx, [rcx+8]
0x180020aa4  mov     rcx, rbx; SRWLock
0x180020aa7  call    cs:__imp_AcquireSRWLockExclusive
0x180020aad  mov     [rbp+var_38], rbx
0x180020ab1  mov     rax, [rdi+30h]
0x180020ab5  inc     rax
0x180020ab8  test    rax, 0FFFFFFFFFFFFFFFEh
0x180020abe  jnz     short loc_180020AD8
0x180020ac0  test    rbx, rbx
0x180020ac3  jz      short loc_180020ACE
0x180020ac5  mov     rcx, rbx; SRWLock
0x180020ac8  call    cs:__imp_ReleaseSRWLockExclusive
0x180020ace  mov     eax, 0FFFFFFF7h
0x180020ad3  jmp     loc_180020BDA
0x180020ad8  cmp     qword ptr [rdi+60h], 0
0x180020add  jnz     short loc_180020B30
0x180020adf  mov     ecx, 28h ; '('; Size
0x180020ae4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020ae9  xorps   xmm0, xmm0
0x180020aec  xor     ecx, ecx
0x180020aee  movups  xmmword ptr [rax], xmm0
0x180020af1  movups  xmmword ptr [rax+10h], xmm0
0x180020af5  mov     [rax+20h], rcx
0x180020af9  mov     rsi, [rdi+60h]
0x180020afd  mov     [rdi+60h], rax
0x180020b01  test    rsi, rsi
0x180020b04  jz      short loc_180020B1C
0x180020b06  mov     rcx, rsi
0x180020b09  call    cs:__imp_LxUtilDirectoryEnumeratorCleanup
0x180020b0f  mov     edx, 28h ; '('; unsigned __int64
0x180020b14  mov     rcx, rsi; void *
0x180020b17  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020b1c  xorps   xmm0, xmm0
0x180020b1f  xor     ecx, ecx
0x180020b21  mov     rax, [rdi+60h]
0x180020b25  movups  xmmword ptr [rax], xmm0
0x180020b28  movups  xmmword ptr [rax+10h], xmm0
0x180020b2c  mov     [rax+20h], rcx
0x180020b30  cmp     r14, [rdi+68h]
0x180020b34  jz      short loc_180020B3A
0x180020b36  mov     [rdi+68h], r14
0x180020b3a  mov     r9b, r12b
0x180020b3d  mov     r8, r15
0x180020b40  lea     rdx, [rbp+var_40]
0x180020b44  mov     rcx, rdi; struct p9fs::File *
0x180020b47  call    ?WriteDotEntries@File@p9fs@@AEAA?AV?$BasicExpected@_NJ@util@@AEAVSpanWriter@2@_N@Z; p9fs::File::WriteDotEntries(p9fs::SpanWriter &,bool)
0x180020b4c  cmp     [rbp+var_40], 0
0x180020b50  jnz     short loc_180020B65
0x180020b52  test    rbx, rbx
0x180020b55  jz      short loc_180020B60
0x180020b57  mov     rcx, rbx; SRWLock
0x180020b5a  call    cs:__imp_ReleaseSRWLockExclusive
0x180020b60  mov     eax, [rbp+var_3C]
0x180020b63  jmp     short loc_180020BDA
0x180020b65  cmp     byte ptr [rbp+var_3C], 0
0x180020b69  jz      short loc_180020B7D
0x180020b6b  test    rbx, rbx
0x180020b6e  jz      short loc_180020B79
0x180020b70  mov     rcx, rbx; SRWLock
0x180020b73  call    cs:__imp_ReleaseSRWLockExclusive
0x180020b79  xor     eax, eax
0x180020b7b  jmp     short loc_180020BDA
0x180020b7d  mov     rax, [rdi+68h]
0x180020b81  sub     rax, 2
0x180020b85  mov     [rbp+var_18], rax
0x180020b89  mov     [rbp+var_30], rdi
0x180020b8d  mov     [rbp+var_28], r15
0x180020b91  mov     [rbp+var_20], r12b
0x180020b95  xor     eax, eax
0x180020b97  mov     [rbp+var_1F], eax
0x180020b9a  mov     [rbp+var_1B], ax
0x180020b9e  mov     [rbp+var_19], al
0x180020ba1  mov     rcx, [rdi+48h]
0x180020ba5  add     rcx, 20h ; ' '
0x180020ba9  lea     rax, [rbp+var_30]
0x180020bad  mov     [rsp+70h+var_50], rax
0x180020bb2  lea     r9, [rbp+var_18]
0x180020bb6  mov     r8, [rdi+60h]
0x180020bba  mov     rdx, [rdi+30h]
0x180020bbe  call    cs:__imp_LxUtilFsReadDir
0x180020bc4  mov     esi, eax
0x180020bc6  mov     byte ptr [rdi+70h], 0
0x180020bca  test    rbx, rbx
0x180020bcd  jz      short loc_180020BD8
0x180020bcf  mov     rcx, rbx; SRWLock
0x180020bd2  call    cs:__imp_ReleaseSRWLockExclusive
0x180020bd8  mov     eax, esi
0x180020bda  mov     rcx, [rbp+var_10]
0x180020bde  xor     rcx, rsp; StackCookie
0x180020be1  call    __security_check_cookie
0x180020be6  add     rsp, 70h
0x180020bea  pop     r15
0x180020bec  pop     r14
0x180020bee  pop     r12
0x180020bf0  pop     rdi
0x180020bf1  pop     rsi
0x180020bf2  pop     rbx
0x180020bf3  pop     rbp
0x180020bf4  retn
```
