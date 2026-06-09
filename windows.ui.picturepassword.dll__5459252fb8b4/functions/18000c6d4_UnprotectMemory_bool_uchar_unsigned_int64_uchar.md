# UnprotectMemory(bool,uchar *,unsigned __int64,uchar * *)

- ea: `0x18000c6d4`
- end: `0x18000c7b1`
- name: `?UnprotectMemory@@YAJ_NPEAE_KPEAPEAE@Z`
- size: `221`
- prototype: `int(bool, unsigned __int8 *, unsigned __int64, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006f80`
- `0x18000b318`
- `0x180012d7c`

## callees

- `0x180005a10`
- `0x1800063c0`
- `0x1800092b8`
- `0x18000a67c`
- `0x18000c6d4`
- `0x18001e3a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000c78c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000c78c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000c72e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000c72e`
- `CRYPT32!CryptUnprotectMemory` at `0x18000c762`
- `CRYPT32!CryptUnprotectMemory` at `0x18000c762`

## pseudocode

```c
__int64 __fastcall UnprotectMemory(void *a1, unsigned __int8 *a2, SIZE_T a3, unsigned __int8 **a4)
{
  char v7; // bp
  int Error; // ebx
  unsigned __int8 *v9; // rdx
  void *v10; // rdi
  void *pDataIn[5]; // [rsp+20h] [rbp-28h] BYREF
  DWORD cbDataIn; // [rsp+68h] [rbp+20h] BYREF

  *a4 = 0;
  pDataIn[0] = 0;
  v7 = (char)a1;
  Error = CTCoAllocPolicy::Alloc(a1, 1, a3, pDataIn);
  if ( Error < 0 )
    goto LABEL_11;
  v9 = a2;
  v10 = pDataIn[0];
  memcpy_0(pDataIn[0], v9, a3);
  if ( v7 )
  {
    Error = CoImpersonateClient();
    if ( Error < 0 )
      goto LABEL_11;
  }
  cbDataIn = 0;
  Error = ULongLongToULong(a3, &cbDataIn);
  if ( Error >= 0 )
  {
    if ( CryptUnprotectMemory(v10, cbDataIn, 2u) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_9;
    }
    pDataIn[0] = 0;
    *a4 = (unsigned __int8 *)v10;
  }
LABEL_9:
  if ( v7 )
    CoRevertToSelf();
LABEL_11:
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(pDataIn);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000c6d4  mov     rax, rsp
0x18000c6d7  mov     [rax+8], rbx
0x18000c6db  mov     [rax+10h], rbp
0x18000c6df  push    rsi
0x18000c6e0  push    rdi
0x18000c6e1  push    r14
0x18000c6e3  sub     rsp, 30h
0x18000c6e7  mov     r14, r9
0x18000c6ea  mov     qword ptr [r9], 0
0x18000c6f1  mov     rdi, rdx
0x18000c6f4  mov     qword ptr [rax-28h], 0
0x18000c6fc  lea     r9, [rax-28h]; void **
0x18000c700  mov     edx, 1; unsigned int
0x18000c705  mov     rsi, r8
0x18000c708  mov     bpl, cl
0x18000c70b  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000c710  mov     ebx, eax
0x18000c712  test    eax, eax
0x18000c714  js      short loc_18000C792
0x18000c716  mov     rdx, rdi; Src
0x18000c719  mov     r8, rsi; Size
0x18000c71c  mov     rdi, [rsp+48h+pDataIn]
0x18000c721  mov     rcx, rdi; void *
0x18000c724  call    memcpy_0
0x18000c729  test    bpl, bpl
0x18000c72c  jz      short loc_18000C73A
0x18000c72e  call    cs:__imp_CoImpersonateClient
0x18000c734  mov     ebx, eax
0x18000c736  test    eax, eax
0x18000c738  js      short loc_18000C792
0x18000c73a  lea     rdx, [rsp+48h+cbDataIn]; unsigned int *
0x18000c73f  mov     [rsp+48h+cbDataIn], 0
0x18000c747  mov     rcx, rsi; unsigned __int64
0x18000c74a  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000c74f  mov     ebx, eax
0x18000c751  test    eax, eax
0x18000c753  js      short loc_18000C787
0x18000c755  mov     edx, [rsp+48h+cbDataIn]; cbDataIn
0x18000c759  mov     r8d, 2; dwFlags
0x18000c75f  mov     rcx, rdi; pDataIn
0x18000c762  call    cs:__imp_CryptUnprotectMemory
0x18000c768  test    eax, eax
0x18000c76a  jz      short loc_18000C770
0x18000c76c  xor     ebx, ebx
0x18000c76e  jmp     short loc_18000C77B
0x18000c770  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000c775  mov     ebx, eax
0x18000c777  test    eax, eax
0x18000c779  js      short loc_18000C787
0x18000c77b  mov     [rsp+48h+pDataIn], 0
0x18000c784  mov     [r14], rdi
0x18000c787  test    bpl, bpl
0x18000c78a  jz      short loc_18000C792
0x18000c78c  call    cs:__imp_CoRevertToSelf
0x18000c792  lea     rcx, [rsp+48h+pDataIn]
0x18000c797  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18000c79c  mov     rbp, [rsp+48h+arg_8]
0x18000c7a1  mov     eax, ebx
0x18000c7a3  mov     rbx, [rsp+48h+arg_0]
0x18000c7a8  add     rsp, 30h
0x18000c7ac  pop     r14
0x18000c7ae  pop     rdi
0x18000c7af  pop     rsi
0x18000c7b0  retn
```
