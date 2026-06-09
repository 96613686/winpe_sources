# ProtectMemory(bool,uchar const *,unsigned __int64,uchar * *,unsigned __int64 *)

- ea: `0x18000c438`
- end: `0x18000c54f`
- name: `?ProtectMemory@@YAJ_NPEBE_KPEAPEAEPEA_K@Z`
- size: `279`
- prototype: `__int64 __fastcall(void *, const unsigned __int8 *, size_t, unsigned __int8 **, unsigned __int64 *cbDataIn)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006f80`
- `0x180012d7c`

## callees

- `0x180005a10`
- `0x1800063c0`
- `0x1800092b8`
- `0x18000a67c`
- `0x18000c438`
- `0x18001e3a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000c526`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000c526`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000c4c4`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000c4c4`
- `CRYPT32!CryptProtectMemory` at `0x18000c4f8`
- `CRYPT32!CryptProtectMemory` at `0x18000c4f8`

## pseudocode

```c
__int64 __fastcall ProtectMemory(
        void *a1,
        const unsigned __int8 *a2,
        size_t a3,
        unsigned __int8 **a4,
        unsigned __int64 *cbDataIn)
{
  unsigned __int64 *v5; // r12
  char v9; // bp
  SIZE_T v10; // rsi
  int Error; // ebx
  size_t v12; // r8
  void *v13; // rdi
  void *pDataIn; // [rsp+60h] [rbp+18h] BYREF

  v5 = cbDataIn;
  *a4 = 0;
  pDataIn = 0;
  *v5 = 0;
  v9 = (char)a1;
  v10 = a3 + (-(__int64)((a3 & 0xF) != 0) & (16 - (a3 & 0xF)));
  Error = CTCoAllocPolicy::Alloc(a1, 1, v10, &pDataIn);
  if ( Error < 0 )
    goto LABEL_11;
  v12 = a3;
  v13 = pDataIn;
  memcpy_0(pDataIn, a2, v12);
  if ( v9 )
  {
    Error = CoImpersonateClient();
    if ( Error < 0 )
      goto LABEL_11;
  }
  LODWORD(cbDataIn) = 0;
  Error = ULongLongToULong(v10, (unsigned int *)&cbDataIn);
  if ( Error >= 0 )
  {
    if ( CryptProtectMemory(v13, (DWORD)cbDataIn, 2u) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_9;
    }
    pDataIn = 0;
    *a4 = (unsigned __int8 *)v13;
    *v5 = v10;
  }
LABEL_9:
  if ( v9 )
    CoRevertToSelf();
LABEL_11:
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pDataIn);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000c438  mov     r11, rsp
0x18000c43b  mov     [r11+8], rbx
0x18000c43f  mov     [r11+10h], rbp
0x18000c443  push    rsi
0x18000c444  push    rdi
0x18000c445  push    r12
0x18000c447  push    r14
0x18000c449  push    r15
0x18000c44b  sub     rsp, 20h
0x18000c44f  mov     r12, qword ptr [rsp+48h+cbDataIn]
0x18000c454  mov     rax, r8
0x18000c457  and     eax, 0Fh
0x18000c45a  mov     qword ptr [r9], 0
0x18000c461  mov     r15, r9
0x18000c464  mov     qword ptr [r11+18h], 0
0x18000c46c  mov     rdi, r8
0x18000c46f  lea     r9, [r11+18h]; void **
0x18000c473  mov     r14, rdx
0x18000c476  mov     qword ptr [r12], 0
0x18000c47e  mov     esi, 10h
0x18000c483  mov     edx, 1; unsigned int
0x18000c488  sub     rsi, rax
0x18000c48b  mov     bpl, cl
0x18000c48e  neg     rax
0x18000c491  sbb     rax, rax
0x18000c494  and     rsi, rax
0x18000c497  add     rsi, r8
0x18000c49a  mov     r8, rsi; unsigned __int64
0x18000c49d  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000c4a2  mov     ebx, eax
0x18000c4a4  test    eax, eax
0x18000c4a6  js      loc_18000C52C
0x18000c4ac  mov     r8, rdi; Size
0x18000c4af  mov     rdx, r14; Src
0x18000c4b2  mov     rdi, [rsp+48h+pDataIn]
0x18000c4b7  mov     rcx, rdi; void *
0x18000c4ba  call    memcpy_0
0x18000c4bf  test    bpl, bpl
0x18000c4c2  jz      short loc_18000C4D0
0x18000c4c4  call    cs:__imp_CoImpersonateClient
0x18000c4ca  mov     ebx, eax
0x18000c4cc  test    eax, eax
0x18000c4ce  js      short loc_18000C52C
0x18000c4d0  lea     rdx, [rsp+48h+cbDataIn]; unsigned int *
0x18000c4d5  mov     [rsp+48h+cbDataIn], 0
0x18000c4dd  mov     rcx, rsi; unsigned __int64
0x18000c4e0  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000c4e5  mov     ebx, eax
0x18000c4e7  test    eax, eax
0x18000c4e9  js      short loc_18000C521
0x18000c4eb  mov     edx, [rsp+48h+cbDataIn]; cbDataIn
0x18000c4ef  mov     r8d, 2; dwFlags
0x18000c4f5  mov     rcx, rdi; pDataIn
0x18000c4f8  call    cs:__imp_CryptProtectMemory
0x18000c4fe  test    eax, eax
0x18000c500  jz      short loc_18000C506
0x18000c502  xor     ebx, ebx
0x18000c504  jmp     short loc_18000C511
0x18000c506  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000c50b  mov     ebx, eax
0x18000c50d  test    eax, eax
0x18000c50f  js      short loc_18000C521
0x18000c511  mov     [rsp+48h+pDataIn], 0
0x18000c51a  mov     [r15], rdi
0x18000c51d  mov     [r12], rsi
0x18000c521  test    bpl, bpl
0x18000c524  jz      short loc_18000C52C
0x18000c526  call    cs:__imp_CoRevertToSelf
0x18000c52c  lea     rcx, [rsp+48h+pDataIn]
0x18000c531  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18000c536  mov     rbp, [rsp+48h+arg_8]
0x18000c53b  mov     eax, ebx
0x18000c53d  mov     rbx, [rsp+48h+arg_0]
0x18000c542  add     rsp, 20h
0x18000c546  pop     r15
0x18000c548  pop     r14
0x18000c54a  pop     r12
0x18000c54c  pop     rdi
0x18000c54d  pop     rsi
0x18000c54e  retn
```
