# DecryptSecurityData(ulong,tagDSSecurityData *,ulong *,tagDSSecurityData * *)

- ea: `0x180032c70`
- end: `0x180032e96`
- name: `?DecryptSecurityData@@YAJKPEAUtagDSSecurityData@@PEAKPEAPEAU1@@Z`
- size: `550`
- prototype: `__int64 __fastcall(unsigned int, struct tagDSSecurityData *, unsigned int *, struct tagDSSecurityData **)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003de00`

## callees

- `0x180003950`
- `0x180003974`
- `0x18000a7b4`
- `0x180032c70`
- `0x180032e9c`
- `0x180042547`
- `0x180042583`
- `0x180042630`
- `0x1800492e0`
- `0x1800496a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032d56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032df1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032df1`
- `CRYPT32!CryptUnprotectData` at `0x180032d45`
- `CRYPT32!CryptUnprotectData` at `0x180032d45`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DecryptSecurityData(
        unsigned int a1,
        struct tagDSSecurityData *a2,
        unsigned int *a3,
        struct tagDSSecurityData **a4)
{
  unsigned int v4; // r15d
  struct tagDSSecurityData *v5; // rbx
  unsigned int v6; // esi
  unsigned int LastError; // edi
  __int64 v9; // r12
  const char *v10; // r9
  void *v11; // rax
  unsigned __int64 cbData; // rdi
  unsigned __int64 v13; // r14
  int v14; // r14d
  int *v15; // rax
  int v16; // edi
  struct tagDSSecurityData *v17; // rax
  __int64 v19; // rdx
  int pPromptStruct; // [rsp+20h] [rbp-59h]
  int pPromptStructa; // [rsp+20h] [rbp-59h]
  int v22; // [rsp+40h] [rbp-39h]
  struct tagDSSecurityData *v23; // [rsp+48h] [rbp-31h]
  BYTE *pbData; // [rsp+50h] [rbp-29h]
  DATA_BLOB pDataOut; // [rsp+68h] [rbp-11h] BYREF
  DATA_BLOB pDataIn; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = 0;
  v5 = 0;
  v23 = a2;
  v6 = -2147024882;
  if ( a1 )
  {
    v5 = (struct tagDSSecurityData *)SafeSusComAllocArray(a1, 0x10u);
    LastError = v5 == 0 ? 0x8007000E : 0;
    if ( !v5 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37F,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\uhshared.cpp",
        (const char *)LastError,
        pPromptStruct);
      goto LABEL_27;
    }
    a2 = v23;
  }
  v22 = 0;
  if ( !a1 )
  {
LABEL_21:
    *a3 = v4;
    v17 = v5;
    v5 = 0;
    *a4 = v17;
    v6 = 0;
    goto LABEL_22;
  }
  v9 = 0;
  while ( 1 )
  {
    pDataIn.cbData = *(_DWORD *)((char *)a2 + v9);
    pDataIn.pbData = *(BYTE **)((char *)a2 + v9 + 8);
    *(&pDataIn.cbData + 1) = 0;
    pDataOut = 0;
    if ( !CryptUnprotectData(&pDataIn, 0, 0, 0, 0, 1u, &pDataOut) )
      break;
    v11 = CoTaskMemAlloc(pDataOut.cbData);
    *(_QWORD *)((char *)v5 + v9 + 8) = v11;
    if ( !v11 )
    {
      v19 = 919;
      goto LABEL_24;
    }
    *(_DWORD *)((char *)v5 + v9) = pDataOut.cbData;
    cbData = pDataOut.cbData;
    v13 = pDataOut.cbData;
    pbData = pDataOut.pbData;
    if ( !pDataOut.cbData )
      goto LABEL_10;
    if ( pDataOut.pbData )
    {
      memmove(v11, pDataOut.pbData, pDataOut.cbData);
LABEL_10:
      v14 = 0;
      goto LABEL_19;
    }
    memset(v11, 0, pDataOut.cbData);
    if ( !pbData )
    {
      v15 = (int *)o__errno_0();
      v16 = 22;
LABEL_15:
      *v15 = v16;
      invalid_parameter_noinfo();
      v14 = v16;
      goto LABEL_19;
    }
    if ( v13 < cbData )
    {
      v15 = (int *)o__errno_0();
      v16 = 34;
      goto LABEL_15;
    }
    v14 = 22;
LABEL_19:
    memset(pDataOut.pbData, 0, pDataOut.cbData);
    LocalFree(pDataOut.pbData);
    if ( v14 )
    {
      v19 = 931;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\uhshared.cpp",
        (const char *)0x8007000ELL,
        pPromptStructa);
      goto LABEL_22;
    }
    ++v4;
    a2 = v23;
    v9 += 16;
    if ( ++v22 >= a1 )
      goto LABEL_21;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x393,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\shared\\uhshared.cpp",
                v10);
LABEL_27:
  v6 = LastError;
LABEL_22:
  FreeSecurityData(v4, v5);
  return v6;
}

```

## disassembly

```asm
0x180032c70  push    rbp
0x180032c72  push    rbx
0x180032c73  push    rsi
0x180032c74  push    rdi
0x180032c75  push    r12
0x180032c77  push    r13
0x180032c79  push    r14
0x180032c7b  push    r15
0x180032c7d  lea     rbp, [rsp-1Fh]
0x180032c82  sub     rsp, 98h
0x180032c89  mov     rax, cs:__security_cookie
0x180032c90  xor     rax, rsp
0x180032c93  mov     [rbp+57h+var_48], rax
0x180032c97  xor     r15d, r15d
0x180032c9a  mov     [rbp+57h+var_70], r9
0x180032c9e  xor     ebx, ebx
0x180032ca0  mov     [rbp+57h+var_78], r8
0x180032ca4  mov     [rbp+57h+var_88], rdx
0x180032ca8  mov     esi, 8007000Eh
0x180032cad  mov     r13d, ecx
0x180032cb0  test    ecx, ecx
0x180032cb2  jz      short loc_180032CF1
0x180032cb4  mov     ecx, r13d; unsigned __int64
0x180032cb7  lea     edx, [rbx+10h]; unsigned __int64
0x180032cba  call    ?SafeSusComAllocArray@@YAPEAX_K0@Z; SafeSusComAllocArray(unsigned __int64,unsigned __int64)
0x180032cbf  mov     rbx, rax
0x180032cc2  neg     rax
0x180032cc5  sbb     edi, edi
0x180032cc7  not     edi
0x180032cc9  and     edi, esi
0x180032ccb  test    rbx, rbx
0x180032cce  jnz     short loc_180032CED
0x180032cd0  mov     rcx, [rbp+5Fh]; this
0x180032cd4  lea     r8, aCW1SSrcClientE_18; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180032cdb  mov     r9d, edi; char *
0x180032cde  mov     edx, 37Fh; void *
0x180032ce3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032ce8  jmp     loc_180032E92
0x180032ced  mov     rdx, [rbp+57h+var_88]
0x180032cf1  mov     [rbp+57h+var_90], r15d
0x180032cf5  test    r13d, r13d
0x180032cf8  jz      loc_180032E18
0x180032cfe  xor     r12d, r12d
0x180032d01  mov     eax, [r12+rdx]
0x180032d05  lea     rcx, [rbp+57h+pDataIn]; pDataIn
0x180032d09  mov     [rbp+57h+pDataIn.cbData], eax
0x180032d0c  xorps   xmm0, xmm0
0x180032d0f  mov     rax, [r12+rdx+8]
0x180032d14  xor     r9d, r9d; pvReserved
0x180032d17  mov     [rbp+57h+pDataIn.pbData], rax
0x180032d1b  xor     r8d, r8d; pOptionalEntropy
0x180032d1e  lea     rax, [rbp+57h+var_68]
0x180032d22  mov     dword ptr [rbp+57h+pDataIn+4], 0
0x180032d29  mov     [rsp+0D0h+pDataOut], rax; pDataOut
0x180032d2e  xor     edx, edx; ppszDataDescr
0x180032d30  mov     [rsp+0D0h+dwFlags], 1; dwFlags
0x180032d38  mov     [rsp+0D0h+pPromptStruct], 0; int
0x180032d41  movups  xmmword ptr [rbp+57h+var_68.cbData], xmm0
0x180032d45  call    cs:__imp_CryptUnprotectData
0x180032d4b  test    eax, eax
0x180032d4d  jz      loc_180032E7B
0x180032d53  mov     ecx, [rbp+57h+var_68.cbData]; cb
0x180032d56  call    cs:__imp_CoTaskMemAlloc
0x180032d5c  mov     [r12+rbx+8], rax
0x180032d61  mov     rcx, rax; void *
0x180032d64  test    rax, rax
0x180032d67  jz      loc_180032E74
0x180032d6d  mov     eax, [rbp+57h+var_68.cbData]
0x180032d70  mov     [r12+rbx], eax
0x180032d74  mov     edi, [rbp+57h+var_68.cbData]
0x180032d77  mov     rax, [rbp+57h+var_68.pbData]
0x180032d7b  mov     r14d, [rbp+57h+var_68.cbData]
0x180032d7f  mov     [rbp+57h+var_80], rax
0x180032d83  test    rdi, rdi
0x180032d86  jnz     short loc_180032D8D
0x180032d88  xor     r14d, r14d
0x180032d8b  jmp     short loc_180032DE2
0x180032d8d  test    rax, rax
0x180032d90  jz      short loc_180032DA4
0x180032d92  cmp     r14, rdi
0x180032d95  jb      short loc_180032DA4
0x180032d97  mov     r8, rdi; Size
0x180032d9a  mov     rdx, rax; Src
0x180032d9d  call    memmove
0x180032da2  jmp     short loc_180032D88
0x180032da4  mov     r8, r14; Size
0x180032da7  xor     edx, edx; Val
0x180032da9  call    memset
0x180032dae  cmp     [rbp+57h+var_80], 0
0x180032db3  jnz     short loc_180032DCB
0x180032db5  call    _o__errno_0
0x180032dba  mov     edi, 16h
0x180032dbf  mov     [rax], edi
0x180032dc1  call    _invalid_parameter_noinfo
0x180032dc6  mov     r14d, edi
0x180032dc9  jmp     short loc_180032DE2
0x180032dcb  cmp     r14, rdi
0x180032dce  jnb     short loc_180032DDC
0x180032dd0  call    _o__errno_0
0x180032dd5  mov     edi, 22h ; '"'
0x180032dda  jmp     short loc_180032DBF
0x180032ddc  mov     r14d, 16h
0x180032de2  mov     ecx, [rbp+57h+var_68.cbData]
0x180032de5  xor     eax, eax
0x180032de7  mov     rdi, [rbp+57h+var_68.pbData]
0x180032deb  rep stosb
0x180032ded  mov     rcx, [rbp+57h+var_68.pbData]; hMem
0x180032df1  call    cs:__imp_LocalFree
0x180032df7  test    r14d, r14d
0x180032dfa  jnz     short loc_180032E5A
0x180032dfc  mov     edi, [rbp+57h+var_90]
0x180032dff  inc     r15d
0x180032e02  mov     rdx, [rbp+57h+var_88]
0x180032e06  inc     edi
0x180032e08  add     r12, 10h
0x180032e0c  mov     [rbp+57h+var_90], edi
0x180032e0f  cmp     edi, r13d
0x180032e12  jb      loc_180032D01
0x180032e18  mov     rax, [rbp+57h+var_78]
0x180032e1c  mov     rcx, [rbp+57h+var_70]
0x180032e20  mov     [rax], r15d
0x180032e23  mov     rax, rbx
0x180032e26  xor     ebx, ebx
0x180032e28  mov     [rcx], rax
0x180032e2b  xor     esi, esi
0x180032e2d  mov     rdx, rbx; struct tagDSSecurityData *
0x180032e30  mov     ecx, r15d; unsigned int
0x180032e33  call    ?FreeSecurityData@@YAXKPEAUtagDSSecurityData@@@Z; FreeSecurityData(ulong,tagDSSecurityData *)
0x180032e38  mov     eax, esi
0x180032e3a  mov     rcx, [rbp+57h+var_48]
0x180032e3e  xor     rcx, rsp; StackCookie
0x180032e41  call    __security_check_cookie
0x180032e46  add     rsp, 98h
0x180032e4d  pop     r15
0x180032e4f  pop     r14
0x180032e51  pop     r13
0x180032e53  pop     r12
0x180032e55  pop     rdi
0x180032e56  pop     rsi
0x180032e57  pop     rbx
0x180032e58  pop     rbp
0x180032e59  retn
0x180032e5a  mov     edx, 3A3h; void *
0x180032e5f  mov     rcx, [rbp+5Fh]; this
0x180032e63  lea     r8, aCW1SSrcClientE_18; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180032e6a  mov     r9d, esi; char *
0x180032e6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032e72  jmp     short loc_180032E2D
0x180032e74  mov     edx, 397h
0x180032e79  jmp     short loc_180032E5F
0x180032e7b  mov     rcx, [rbp+5Fh]; this
0x180032e7f  lea     r8, aCW1SSrcClientE_18; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180032e86  mov     edx, 393h; void *
0x180032e8b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180032e90  mov     edi, eax
0x180032e92  mov     esi, edi
0x180032e94  jmp     short loc_180032E2D
```
