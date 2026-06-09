# WimpFSFIntegrityValidateIntegrityFile

- ea: `0x14002a040`
- end: `0x14002a38b`
- name: `WimpFSFIntegrityValidateIntegrityFile`
- size: `843`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140028488`
- `0x1400288d4`

## callees

- `0x140011560`
- `0x14002a040`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14002a22b`
- `ntoskrnl!RtlCompareMemory` at `0x14002a258`
- `ntoskrnl!RtlCompareMemory` at `0x14002a22b`
- `ntoskrnl!RtlCompareMemory` at `0x14002a258`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a355`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a355`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a123`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a123`
- `FLTMGR!FltReadFile` at `0x14002a182`
- `FLTMGR!FltReadFile` at `0x14002a182`
- `FLTMGR!FltQueryInformationFile` at `0x14002a2c7`
- `FLTMGR!FltQueryInformationFile` at `0x14002a2c7`
- `cng!BCryptCreateHash` at `0x14002a0ff`
- `cng!BCryptCreateHash` at `0x14002a0ff`
- `cng!BCryptHashData` at `0x14002a1e2`
- `cng!BCryptHashData` at `0x14002a1e2`
- `cng!BCryptDestroyHash` at `0x14002a325`
- `cng!BCryptDestroyHash` at `0x14002a325`
- `cng!BCryptCloseAlgorithmProvider` at `0x14002a33c`
- `cng!BCryptCloseAlgorithmProvider` at `0x14002a33c`
- `cng!BCryptFinishHash` at `0x14002a208`
- `cng!BCryptFinishHash` at `0x14002a208`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002a0ce`
- `cng!BCryptOpenAlgorithmProvider` at `0x14002a0ce`

## pseudocode

```c
__int64 __fastcall WimpFSFIntegrityValidateIntegrityFile(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        void *a3,
        unsigned __int64 a4,
        char *a5,
        char *a6,
        _DWORD *a7,
        _QWORD *a8)
{
  UCHAR *PoolWithTag; // rdi
  NTSTATUS v12; // ebx
  struct _FLT_INSTANCE *v13; // rcx
  int v14; // r12d
  __int64 v15; // rcx
  char v16; // r14
  char v17; // r15
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rsi
  __int64 v22; // [rsp+50h] [rbp-79h]
  ULONG BytesRead; // [rsp+60h] [rbp-69h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+68h] [rbp-61h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+70h] [rbp-59h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+78h] [rbp-51h] BYREF
  void *Source2; // [rsp+80h] [rbp-49h]
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-41h]
  __int64 v29; // [rsp+90h] [rbp-39h]
  char *v30; // [rsp+98h] [rbp-31h]
  char *v31; // [rsp+A0h] [rbp-29h]
  _DWORD *v32; // [rsp+A8h] [rbp-21h]
  __int128 FileInformation; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-9h]

  v31 = a5;
  v30 = a6;
  PoolWithTag = 0;
  v32 = a7;
  Source2 = a3;
  FileObject = a2;
  v29 = a1;
  v34 = 0;
  phAlgorithm = 0;
  phHash = 0;
  ByteOffset.QuadPart = 0;
  BytesRead = 0;
  FileInformation = 0;
  v12 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( v12 >= 0 )
  {
    v12 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
    if ( v12 >= 0 )
    {
      PoolWithTag = (UCHAR *)ExAllocatePoolWithTag(PagedPool, 0x94u, 0x69637077u);
      if ( !PoolWithTag )
      {
        v12 = -1073741801;
        goto LABEL_30;
      }
      v13 = *(struct _FLT_INSTANCE **)(a1 + 120);
      ByteOffset.QuadPart = 0;
      v12 = FltReadFile(v13, a2, &ByteOffset, 0x74u, PoolWithTag, 0, &BytesRead, 0, 0);
      if ( v12 >= 0 )
      {
        if ( BytesRead != 116 )
        {
          v12 = -1073741116;
          goto LABEL_30;
        }
        v14 = 0;
        v15 = 0;
        v16 = 0;
        v17 = 0;
        if ( *(_DWORD *)PoolWithTag == 1766027095
          && *((_DWORD *)PoolWithTag + 1) == 1
          && *((_DWORD *)PoolWithTag + 12) >= 0x74u )
        {
          v12 = BCryptHashData(phHash, PoolWithTag, 0x54u, 0);
          if ( v12 < 0 )
            goto LABEL_30;
          v12 = BCryptFinishHash(phHash, PoolWithTag + 116, 0x20u, 0);
          if ( v12 < 0 )
            goto LABEL_30;
          if ( RtlCompareMemory(PoolWithTag + 116, PoolWithTag + 84, 0x20u) == 32
            && *((_QWORD *)PoolWithTag + 1) == a4
            && RtlCompareMemory(PoolWithTag + 16, Source2, 0x10u) == 16
            && (v18 = *((_QWORD *)PoolWithTag + 5), v18 <= a4) )
          {
            v15 = *((_QWORD *)PoolWithTag + 5);
            v22 = v15;
            if ( v18 >= a4 )
            {
              if ( a4 + 4095 < a4
                || (v19 = 16 * ((a4 + 4095) >> 12), v20 = v19 + *((unsigned int *)PoolWithTag + 12), v20 < v19) )
              {
                v12 = -1073741675;
                goto LABEL_30;
              }
              v12 = FltQueryInformationFile(
                      *(PFLT_INSTANCE *)(v29 + 120),
                      FileObject,
                      &FileInformation,
                      0x18u,
                      FileStandardInformation,
                      0);
              if ( v12 < 0 )
                goto LABEL_30;
              v15 = v22;
              if ( v20 == *((_QWORD *)&FileInformation + 1) )
              {
                v14 = *((_DWORD *)PoolWithTag + 12);
                v17 = 1;
                v16 = 1;
              }
            }
            else
            {
              v17 = 1;
            }
          }
          else
          {
            v15 = 0;
          }
        }
        *v30 = v16;
        *v31 = v17;
        if ( v32 )
          *v32 = v14;
        if ( a8 )
          *a8 = v15;
      }
    }
  }
LABEL_30:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0x69637077u);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14002a040  mov     [rsp-8+arg_18], rbx
0x14002a045  push    rbp
0x14002a046  push    rsi
0x14002a047  push    rdi
0x14002a048  push    r12
0x14002a04a  push    r13
0x14002a04c  push    r14
0x14002a04e  push    r15
0x14002a050  lea     rbp, [rsp-7]
0x14002a055  sub     rsp, 0D0h
0x14002a05c  mov     rax, cs:__security_cookie
0x14002a063  xor     rax, rsp
0x14002a066  mov     [rbp+37h+var_38], rax
0x14002a06a  mov     rax, [rbp+37h+arg_20]
0x14002a06e  mov     rsi, r9
0x14002a071  mov     r13, [rbp+37h+arg_38]
0x14002a075  mov     r15, rdx
0x14002a078  mov     [rbp+37h+var_60], rax
0x14002a07c  mov     r14, rcx
0x14002a07f  mov     rax, [rbp+37h+arg_28]
0x14002a083  xorps   xmm0, xmm0
0x14002a086  mov     [rbp+37h+var_68], rax
0x14002a08a  xor     r9d, r9d; dwFlags
0x14002a08d  mov     rax, [rbp+37h+arg_30]
0x14002a091  xor     edi, edi
0x14002a093  mov     [rbp+37h+var_58], rax
0x14002a097  xor     eax, eax
0x14002a099  mov     [rbp+37h+Source2], r8
0x14002a09d  xor     r8d, r8d; pszImplementation
0x14002a0a0  mov     [rbp+37h+FileObject], rdx
0x14002a0a4  lea     rdx, pszAlgId; "SHA256"
0x14002a0ab  mov     [rbp+37h+var_70], rcx
0x14002a0af  lea     rcx, [rbp+37h+phAlgorithm]; phAlgorithm
0x14002a0b3  mov     [rbp+37h+var_40], rax
0x14002a0b7  mov     [rbp+37h+phAlgorithm], rax
0x14002a0bb  mov     [rbp+37h+phHash], rax
0x14002a0bf  mov     qword ptr [rbp+37h+ByteOffset], rax
0x14002a0c3  mov     [rbp+37h+BytesRead], 0
0x14002a0ca  movups  [rbp+37h+FileInformation], xmm0
0x14002a0ce  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14002a0d5  nop     dword ptr [rax+rax+00h]
0x14002a0da  mov     ebx, eax
0x14002a0dc  test    eax, eax
0x14002a0de  js      loc_14002A31C
0x14002a0e4  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x14002a0e8  lea     rdx, [rbp+37h+phHash]; phHash
0x14002a0ec  mov     [rsp+100h+dwFlags], edi; dwFlags
0x14002a0f0  xor     r9d, r9d; cbHashObject
0x14002a0f3  mov     [rsp+100h+cbSecret], edi; cbSecret
0x14002a0f7  xor     r8d, r8d; pbHashObject
0x14002a0fa  mov     [rsp+100h+pbSecret], rdi; pbSecret
0x14002a0ff  call    cs:__imp_BCryptCreateHash
0x14002a106  nop     dword ptr [rax+rax+00h]
0x14002a10b  mov     ebx, eax
0x14002a10d  test    eax, eax
0x14002a10f  js      loc_14002A31C
0x14002a115  mov     edx, 94h; NumberOfBytes
0x14002a11a  lea     ecx, [rdi+1]; PoolType
0x14002a11d  mov     r8d, 69637077h; Tag
0x14002a123  call    cs:__imp_ExAllocatePoolWithTag
0x14002a12a  nop     dword ptr [rax+rax+00h]
0x14002a12f  mov     rdi, rax
0x14002a132  test    rax, rax
0x14002a135  jnz     short loc_14002A141
0x14002a137  mov     ebx, 0C0000017h
0x14002a13c  jmp     loc_14002A31C
0x14002a141  mov     rcx, [r14+78h]; InitiatingInstance
0x14002a145  lea     rax, [rbp+37h+BytesRead]
0x14002a149  mov     [rsp+100h+CallbackContext], 0; CallbackContext
0x14002a152  lea     r8, [rbp+37h+ByteOffset]; ByteOffset
0x14002a156  mov     [rsp+100h+CallbackRoutine], 0; CallbackRoutine
0x14002a15f  mov     r9d, 74h ; 't'; Length
0x14002a165  mov     qword ptr [rsp+100h+dwFlags], rax; BytesRead
0x14002a16a  mov     rdx, r15; FileObject
0x14002a16d  mov     [rsp+100h+cbSecret], 0; Flags
0x14002a175  mov     [rsp+100h+pbSecret], rdi; Buffer
0x14002a17a  mov     qword ptr [rbp+37h+ByteOffset], 0
0x14002a182  call    cs:__imp_FltReadFile
0x14002a189  nop     dword ptr [rax+rax+00h]
0x14002a18e  mov     ebx, eax
0x14002a190  test    eax, eax
0x14002a192  js      loc_14002A31C
0x14002a198  cmp     [rbp+37h+BytesRead], 74h ; 't'
0x14002a19c  jz      short loc_14002A1A8
0x14002a19e  mov     ebx, 0C00002C4h
0x14002a1a3  jmp     loc_14002A31C
0x14002a1a8  xor     r12d, r12d
0x14002a1ab  xor     ecx, ecx
0x14002a1ad  xor     r14b, r14b
0x14002a1b0  xor     r15b, r15b
0x14002a1b3  cmp     dword ptr [rdi], 69436F57h
0x14002a1b9  jnz     loc_14002A2F9
0x14002a1bf  cmp     dword ptr [rdi+4], 1
0x14002a1c3  jnz     loc_14002A2F9
0x14002a1c9  cmp     dword ptr [rdi+30h], 74h ; 't'
0x14002a1cd  jb      loc_14002A2F9
0x14002a1d3  mov     rcx, [rbp+37h+phHash]; hHash
0x14002a1d7  lea     r8d, [r12+54h]; cbInput
0x14002a1dc  xor     r9d, r9d; dwFlags
0x14002a1df  mov     rdx, rdi; pbInput
0x14002a1e2  call    cs:__imp_BCryptHashData
0x14002a1e9  nop     dword ptr [rax+rax+00h]
0x14002a1ee  mov     ebx, eax
0x14002a1f0  test    eax, eax
0x14002a1f2  js      loc_14002A31C
0x14002a1f8  mov     rcx, [rbp+37h+phHash]; hHash
0x14002a1fc  lea     r8d, [r12+20h]; cbOutput
0x14002a201  xor     r9d, r9d; dwFlags
0x14002a204  lea     rdx, [rdi+74h]; pbOutput
0x14002a208  call    cs:__imp_BCryptFinishHash
0x14002a20f  nop     dword ptr [rax+rax+00h]
0x14002a214  mov     ebx, eax
0x14002a216  test    eax, eax
0x14002a218  js      loc_14002A31C
0x14002a21e  lea     rdx, [rdi+54h]; Source2
0x14002a222  lea     r8d, [r12+20h]; Length
0x14002a227  lea     rcx, [rdi+74h]; Source1
0x14002a22b  call    cs:__imp_RtlCompareMemory
0x14002a232  nop     dword ptr [rax+rax+00h]
0x14002a237  cmp     rax, 20h ; ' '
0x14002a23b  jnz     loc_14002A2F6
0x14002a241  cmp     [rdi+8], rsi
0x14002a245  jnz     loc_14002A2F6
0x14002a24b  mov     rdx, [rbp+37h+Source2]; Source2
0x14002a24f  lea     rcx, [rdi+10h]; Source1
0x14002a253  lea     r8d, [r12+10h]; Length
0x14002a258  call    cs:__imp_RtlCompareMemory
0x14002a25f  nop     dword ptr [rax+rax+00h]
0x14002a264  cmp     rax, 10h
0x14002a268  jnz     loc_14002A2F6
0x14002a26e  mov     rax, [rdi+28h]
0x14002a272  cmp     rax, rsi
0x14002a275  ja      short loc_14002A2F6
0x14002a277  mov     rcx, rax
0x14002a27a  mov     [rbp+37h+var_B0], rax
0x14002a27e  jnb     short loc_14002A285
0x14002a280  mov     r15b, 1
0x14002a283  jmp     short loc_14002A2F9
0x14002a285  lea     rcx, [rsi+0FFFh]
0x14002a28c  cmp     rcx, rsi
0x14002a28f  jb      short loc_14002A2EF
0x14002a291  mov     esi, [rdi+30h]
0x14002a294  shr     rcx, 0Ch
0x14002a298  shl     rcx, 4
0x14002a29c  add     rsi, rcx
0x14002a29f  cmp     rsi, rcx
0x14002a2a2  jb      short loc_14002A2EF
0x14002a2a4  mov     rcx, [rbp+37h+var_70]
0x14002a2a8  lea     r8, [rbp+37h+FileInformation]; FileInformation
0x14002a2ac  mov     rdx, [rbp+37h+FileObject]; FileObject
0x14002a2b0  mov     r9d, 18h; Length
0x14002a2b6  mov     qword ptr [rsp+100h+cbSecret], r12; LengthReturned
0x14002a2bb  mov     dword ptr [rsp+100h+pbSecret], 5; FileInformationClass
0x14002a2c3  mov     rcx, [rcx+78h]; Instance
0x14002a2c7  call    cs:__imp_FltQueryInformationFile
0x14002a2ce  nop     dword ptr [rax+rax+00h]
0x14002a2d3  mov     ebx, eax
0x14002a2d5  test    eax, eax
0x14002a2d7  js      short loc_14002A31C
0x14002a2d9  mov     rcx, [rbp+37h+var_B0]
0x14002a2dd  cmp     rsi, qword ptr [rbp+37h+FileInformation+8]
0x14002a2e1  jnz     short loc_14002A2F9
0x14002a2e3  mov     r12d, [rdi+30h]
0x14002a2e7  mov     r15b, 1
0x14002a2ea  mov     r14b, r15b
0x14002a2ed  jmp     short loc_14002A2F9
0x14002a2ef  mov     ebx, 0C0000095h
0x14002a2f4  jmp     short loc_14002A31C
0x14002a2f6  mov     rcx, r12
0x14002a2f9  mov     rax, [rbp+37h+var_68]
0x14002a2fd  mov     [rax], r14b
0x14002a300  mov     rax, [rbp+37h+var_60]
0x14002a304  mov     [rax], r15b
0x14002a307  mov     rax, [rbp+37h+var_58]
0x14002a30b  test    rax, rax
0x14002a30e  jz      short loc_14002A313
0x14002a310  mov     [rax], r12d
0x14002a313  test    r13, r13
0x14002a316  jz      short loc_14002A31C
0x14002a318  mov     [r13+0], rcx
0x14002a31c  mov     rcx, [rbp+37h+phHash]; hHash
0x14002a320  test    rcx, rcx
0x14002a323  jz      short loc_14002A331
0x14002a325  call    cs:__imp_BCryptDestroyHash
0x14002a32c  nop     dword ptr [rax+rax+00h]
0x14002a331  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x14002a335  test    rcx, rcx
0x14002a338  jz      short loc_14002A348
0x14002a33a  xor     edx, edx; dwFlags
0x14002a33c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14002a343  nop     dword ptr [rax+rax+00h]
0x14002a348  test    rdi, rdi
0x14002a34b  jz      short loc_14002A361
0x14002a34d  mov     edx, 69637077h; Tag
0x14002a352  mov     rcx, rdi; P
0x14002a355  call    cs:__imp_ExFreePoolWithTag
0x14002a35c  nop     dword ptr [rax+rax+00h]
0x14002a361  mov     eax, ebx
0x14002a363  mov     rcx, [rbp+37h+var_38]
0x14002a367  xor     rcx, rsp; StackCookie
0x14002a36a  call    __security_check_cookie
0x14002a36f  mov     rbx, [rsp+100h+arg_18]
0x14002a377  add     rsp, 0D0h
0x14002a37e  pop     r15
0x14002a380  pop     r14
0x14002a382  pop     r13
0x14002a384  pop     r12
0x14002a386  pop     rdi
0x14002a387  pop     rsi
0x14002a388  pop     rbp
0x14002a389  retn
```
