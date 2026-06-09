# I_CacheHashKeys

- ea: `0x18003852c`
- end: `0x1800385e8`
- name: `I_CacheHashKeys`
- size: `188`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180038284`
- `0x18003833c`
- `0x180038484`

## callees

- `0x18003852c`
- `0x1800385f0`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1800385c2`
- `bcrypt!BCryptFinishHash` at `0x1800385c2`
- `bcrypt!BCryptDestroyHash` at `0x1800385af`
- `bcrypt!BCryptDestroyHash` at `0x1800385d2`
- `bcrypt!BCryptDestroyHash` at `0x1800385af`
- `bcrypt!BCryptDestroyHash` at `0x1800385d2`
- `bcrypt!BCryptHashData` at `0x18003859b`
- `bcrypt!BCryptHashData` at `0x18003859b`
- `bcrypt!BCryptCreateHash` at `0x180038569`
- `bcrypt!BCryptCreateHash` at `0x180038569`

## pseudocode

```c
unsigned int __fastcall I_CacheHashKeys(__int64 a1, __int64 a2, UCHAR *a3)
{
  unsigned int v5; // eax
  int v6; // edx
  errcntrctlib *v7; // rcx
  unsigned int v8; // ebx
  unsigned int v9; // edi
  unsigned int v10; // ebx
  BCRYPT_HASH_HANDLE hHash; // [rsp+88h] [rbp+20h] BYREF

  hHash = 0;
  v5 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &hHash, 0, 0, 0, 0, 0);
  if ( v5 )
  {
    v7 = (errcntrctlib *)v5;
  }
  else
  {
    v8 = 2;
    while ( v8 )
    {
      --v8;
      v9 = BCryptHashData(hHash, *(PUCHAR *)(a1 + 16LL * v8 + 8), *(_DWORD *)(a1 + 16LL * v8), 0);
      if ( v9 )
      {
        BCryptDestroyHash(hHash);
        v7 = (errcntrctlib *)v9;
        return errcntrctlib::WIN32_FROM_NTSTATUS(v7, v6);
      }
    }
    v10 = BCryptFinishHash(hHash, a3, 0x20u, 0);
    BCryptDestroyHash(hHash);
    v7 = (errcntrctlib *)v10;
  }
  return errcntrctlib::WIN32_FROM_NTSTATUS(v7, v6);
}

```

## disassembly

```asm
0x18003852c  mov     rax, rsp
0x18003852f  push    rbx
0x180038530  push    rbp
0x180038531  push    rsi
0x180038532  push    rdi
0x180038533  sub     rsp, 48h
0x180038537  mov     dword ptr [rax-38h], 0
0x18003853e  lea     rdx, [rax+20h]; phHash
0x180038542  xor     r9d, r9d; cbHashObject
0x180038545  mov     dword ptr [rax-40h], 0
0x18003854c  mov     rbp, r8
0x18003854f  mov     qword ptr [rax+20h], 0
0x180038557  mov     rsi, rcx
0x18003855a  mov     qword ptr [rax-48h], 0
0x180038562  xor     r8d, r8d; pbHashObject
0x180038565  lea     ecx, [r9+41h]; hAlgorithm
0x180038569  call    cs:__imp_BCryptCreateHash
0x18003856f  test    eax, eax
0x180038571  jz      short loc_180038577
0x180038573  mov     ecx, eax
0x180038575  jmp     short loc_1800385DA
0x180038577  mov     ebx, 2
0x18003857c  mov     rcx, [rsp+68h+hHash]; hHash
0x180038584  xor     r9d, r9d; dwFlags
0x180038587  test    ebx, ebx
0x180038589  jz      short loc_1800385B9
0x18003858b  dec     ebx
0x18003858d  mov     edx, ebx
0x18003858f  add     rdx, rdx
0x180038592  mov     r8d, [rsi+rdx*8]; cbInput
0x180038596  mov     rdx, [rsi+rdx*8+8]; pbInput
0x18003859b  call    cs:__imp_BCryptHashData
0x1800385a1  mov     edi, eax
0x1800385a3  test    eax, eax
0x1800385a5  jz      short loc_18003857C
0x1800385a7  mov     rcx, [rsp+68h+hHash]; hHash
0x1800385af  call    cs:__imp_BCryptDestroyHash
0x1800385b5  mov     ecx, edi
0x1800385b7  jmp     short loc_1800385DA
0x1800385b9  mov     r8d, 20h ; ' '; cbOutput
0x1800385bf  mov     rdx, rbp; pbOutput
0x1800385c2  call    cs:__imp_BCryptFinishHash
0x1800385c8  mov     rcx, [rsp+68h+hHash]; hHash
0x1800385d0  mov     ebx, eax
0x1800385d2  call    cs:__imp_BCryptDestroyHash
0x1800385d8  mov     ecx, ebx; this
0x1800385da  call    ?WIN32_FROM_NTSTATUS@errcntrctlib@@YAKJ@Z; errcntrctlib::WIN32_FROM_NTSTATUS(long)
0x1800385df  add     rsp, 48h
0x1800385e3  pop     rdi
0x1800385e4  pop     rsi
0x1800385e5  pop     rbp
0x1800385e6  pop     rbx
0x1800385e7  retn
```
