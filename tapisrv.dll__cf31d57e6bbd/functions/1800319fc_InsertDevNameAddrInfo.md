# InsertDevNameAddrInfo

- ea: `0x1800319fc`
- end: `0x180031d79`
- name: `InsertDevNameAddrInfo`
- size: `893`
- prototype: `__int64 __fastcall(int, __int64 *, _DWORD *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18002ff78`
- `0x180030218`

## callees

- `0x180001600`
- `0x180006f24`
- `0x1800070e8`
- `0x18001c7c0`
- `0x180021640`
- `0x18002c8d4`
- `0x1800319fc`
- `0x180031d80`
- `0x180040010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180031b60`
- `KERNEL32!HeapAlloc` at `0x180031c7b`
- `KERNEL32!HeapAlloc` at `0x180031b60`
- `KERNEL32!HeapAlloc` at `0x180031c7b`
- `KERNEL32!GetCurrentThreadId` at `0x180031a64`
- `KERNEL32!GetCurrentThreadId` at `0x180031d20`
- `KERNEL32!GetCurrentThreadId` at `0x180031a64`
- `KERNEL32!GetCurrentThreadId` at `0x180031d20`
- `KERNEL32!LeaveCriticalSection` at `0x180031d46`
- `KERNEL32!LeaveCriticalSection` at `0x180031d46`
- `KERNEL32!EnterCriticalSection` at `0x180031a54`
- `KERNEL32!EnterCriticalSection` at `0x180031a54`

## pseudocode

```c
__int64 __fastcall InsertDevNameAddrInfo(int a1, __int64 *a2, _DWORD *a3, unsigned int a4, unsigned int a5)
{
  __int64 v5; // rbx
  size_t v8; // rdx
  char *LineLookupEntry; // rax
  unsigned int v10; // r8d
  char *v11; // r15
  char *v12; // r14
  char *v13; // r8
  unsigned int *v14; // rdi
  unsigned int *v15; // rsi
  unsigned int v16; // ebp
  unsigned int v17; // eax
  unsigned int v18; // ebx
  unsigned int *v19; // rbx
  unsigned int v20; // eax
  int v21; // ecx
  __int128 *v22; // r9
  unsigned int v23; // r12d
  unsigned int i; // ebp
  unsigned int *v25; // r14
  size_t v26; // rdx
  __int64 v30; // [rsp+40h] [rbp-688h]
  __int128 v32; // [rsp+50h] [rbp-678h] BYREF
  _BYTE v33[688]; // [rsp+60h] [rbp-668h] BYREF
  _BYTE Mem[880]; // [rsp+310h] [rbp-3B8h] BYREF

  v5 = *a2;
  v30 = *a2;
  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 1034;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(pszDest, v8, "erver\\tapimmc.c");
  if ( a1 )
  {
    LineLookupEntry = GetLineLookupEntry(a4);
    v11 = LineLookupEntry;
    if ( LineLookupEntry && *((_DWORD *)LineLookupEntry + 8) == v10 )
    {
      v12 = (char *)v10;
      goto LABEL_8;
    }
LABEL_41:
    v18 = 1;
    goto LABEL_42;
  }
  LineLookupEntry = GetPhoneLookupEntry(a4);
  v12 = LineLookupEntry;
  if ( !LineLookupEntry || *((_DWORD *)LineLookupEntry + 8) != (_DWORD)v13 )
    goto LABEL_41;
  v11 = v13;
LABEL_8:
  v14 = (unsigned int *)Mem;
  v15 = (unsigned int *)v33;
  v16 = 876;
  *(_DWORD *)(v5 + 40LL * a5 + 28) = *(_DWORD *)(*((_QWORD *)LineLookupEntry + 3) + 32LL);
  while ( 1 )
  {
    InitTapiStruct(v14, v16, 0x124u, 1);
    v17 = a1
        ? (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *))(*((_QWORD *)v11 + 3) + 352LL))(
            a4,
            *(unsigned int *)v11,
            0,
            v14)
        : (*(unsigned __int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *))(*((_QWORD *)v12 + 3) + 752LL))(
            a4,
            *(unsigned int *)v12,
            0,
            v14);
    v18 = v17;
    if ( v17 )
      break;
    if ( v14[1] <= *v14 )
    {
      v20 = v14[7];
      v32 = *(_OWORD *)L"Unknown";
      *(_DWORD *)(v30 + 40LL * a5 + 24) = v20;
      if ( a1 && a3 )
        *a3 = v14[28];
      v21 = v14[8];
      if ( !v21 || (v22 = (__int128 *)((char *)v14 + v14[9]), !*(_WORD *)v22) )
      {
        v21 = 16;
        v22 = &v32;
      }
      if ( (unsigned int)InsertInfoListString(a2, a5, 8, v22, v21, 0) )
      {
LABEL_36:
        v18 = -2147483580;
        break;
      }
      if ( a1 )
      {
        v23 = 684;
        for ( i = 0; i < v14[12]; ++i )
        {
          while ( 1 )
          {
            InitTapiStruct(v15, v23, 0xE4u, 1);
            v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int *))(*((_QWORD *)v11 + 3)
                                                                                            + 272LL))(
                    a4,
                    i,
                    *(unsigned int *)v11,
                    0,
                    v15);
            if ( v18 )
              break;
            if ( v15[1] <= *v15 )
            {
              if ( (unsigned int)InsertInfoListString(a2, a5, 16, (char *)v15 + v15[5], v15[4], i >= v14[12] - 1) )
                goto LABEL_36;
              break;
            }
            v23 += 256;
            v25 = (unsigned int *)HeapAlloc(ghTapisrvHeap, v18 + 8, v23);
            if ( !v25 )
              goto LABEL_37;
            if ( v15 != (unsigned int *)v33 )
              ServerFree(v15);
            v15 = v25;
          }
        }
      }
      break;
    }
    v16 += 256;
    v19 = (unsigned int *)HeapAlloc(ghTapisrvHeap, v17 + 8, v16);
    if ( !v19 )
      goto LABEL_36;
    if ( v14 != (unsigned int *)Mem )
      ServerFree(v14);
    v14 = v19;
  }
LABEL_37:
  if ( v14 != (unsigned int *)Mem )
    ServerFree(v14);
  if ( v15 != (unsigned int *)v33 )
    ServerFree(v15);
LABEL_42:
  dword_1800519F8 = 1271;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v26, "erver\\tapimmc.c");
  LeaveCriticalSection(&CriticalSection);
  return v18;
}

```

## disassembly

```asm
0x1800319fc  mov     [rsp+arg_0], rbx
0x180031a01  push    rbp
0x180031a02  push    rsi
0x180031a03  push    rdi
0x180031a04  push    r12
0x180031a06  push    r13
0x180031a08  push    r14
0x180031a0a  push    r15
0x180031a0c  sub     rsp, 690h
0x180031a13  mov     rax, cs:__security_cookie
0x180031a1a  xor     rax, rsp
0x180031a1d  mov     [rsp+6C8h+var_48], rax
0x180031a25  mov     rbx, [rdx]
0x180031a28  mov     r12d, ecx
0x180031a2b  mov     ebp, [rsp+6C8h+arg_20]
0x180031a32  lea     rcx, CriticalSection; lpCriticalSection
0x180031a39  mov     [rsp+6C8h+var_694], ebp
0x180031a3d  mov     edi, r9d
0x180031a40  mov     [rsp+6C8h+var_688], rbx
0x180031a45  mov     [rsp+6C8h+var_698], r9d
0x180031a4a  mov     [rsp+6C8h+var_680], r8
0x180031a4f  mov     [rsp+6C8h+var_690], rdx
0x180031a54  call    cs:__imp_EnterCriticalSection
0x180031a5a  mov     cs:dword_1800519E0, 40Ah
0x180031a64  call    cs:__imp_GetCurrentThreadId
0x180031a6a  lea     r8, aPrintscanTapiS_1+10h; pszSrc
0x180031a71  mov     cs:dword_1800519E4, eax
0x180031a77  lea     rcx, pszDest; pszDest
0x180031a7e  call    StringCbCopyA
0x180031a83  xor     r8d, r8d
0x180031a86  mov     ecx, edi
0x180031a88  test    r12d, r12d
0x180031a8b  jz      short loc_180031AAD
0x180031a8d  call    GetLineLookupEntry
0x180031a92  mov     r15, rax
0x180031a95  test    rax, rax
0x180031a98  jz      loc_180031D11
0x180031a9e  cmp     [rax+20h], r8d
0x180031aa2  jnz     loc_180031D11
0x180031aa8  mov     r14d, r8d
0x180031aab  jmp     short loc_180031ACB
0x180031aad  call    GetPhoneLookupEntry
0x180031ab2  mov     r14, rax
0x180031ab5  test    rax, rax
0x180031ab8  jz      loc_180031D11
0x180031abe  cmp     [rax+20h], r8d
0x180031ac2  jnz     loc_180031D11
0x180031ac8  mov     r15, r8
0x180031acb  mov     rcx, [rax+18h]
0x180031acf  lea     r13, ds:0[rbp*4]
0x180031ad7  add     r13, rbp
0x180031ada  lea     rdi, [rsp+6C8h+Mem]
0x180031ae2  lea     rsi, [rsp+6C8h+var_668]
0x180031ae7  mov     ebp, 36Ch
0x180031aec  mov     eax, [rcx+20h]
0x180031aef  mov     [rbx+r13*8+1Ch], eax
0x180031af4  mov     r9d, 1
0x180031afa  mov     r8d, 124h
0x180031b00  mov     edx, ebp
0x180031b02  mov     rcx, rdi
0x180031b05  call    InitTapiStruct
0x180031b0a  mov     ecx, [rsp+6C8h+var_698]
0x180031b0e  xor     r8d, r8d
0x180031b11  mov     r9, rdi
0x180031b14  test    r12d, r12d
0x180031b17  jz      short loc_180031B29
0x180031b19  mov     rax, [r15+18h]
0x180031b1d  mov     edx, [r15]
0x180031b20  mov     rax, [rax+160h]
0x180031b27  jmp     short loc_180031B37
0x180031b29  mov     rax, [r14+18h]
0x180031b2d  mov     edx, [r14]
0x180031b30  mov     rax, [rax+2F0h]
0x180031b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b3c  mov     ebx, eax
0x180031b3e  test    eax, eax
0x180031b40  jnz     loc_180031CE8
0x180031b46  mov     eax, [rdi]
0x180031b48  cmp     [rdi+4], eax
0x180031b4b  jbe     short loc_180031B8F
0x180031b4d  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180031b54  lea     edx, [rbx+8]; dwFlags
0x180031b57  add     ebp, 100h
0x180031b5d  mov     r8d, ebp; dwBytes
0x180031b60  call    cs:__imp_HeapAlloc
0x180031b66  mov     rbx, rax
0x180031b69  test    rax, rax
0x180031b6c  jz      loc_180031CE3
0x180031b72  lea     rax, [rsp+6C8h+Mem]
0x180031b7a  cmp     rdi, rax
0x180031b7d  jz      short loc_180031B87
0x180031b7f  mov     rcx, rdi; lpMem
0x180031b82  call    ServerFree
0x180031b87  mov     rdi, rbx
0x180031b8a  jmp     loc_180031AF4
0x180031b8f  movups  xmm0, xmmword ptr cs:aUnknown; "Unknown"
0x180031b96  mov     rcx, [rsp+6C8h+var_688]
0x180031b9b  xor     r14d, r14d
0x180031b9e  mov     eax, [rdi+1Ch]
0x180031ba1  movdqu  [rsp+6C8h+var_678], xmm0
0x180031ba7  mov     [rcx+r13*8+18h], eax
0x180031bac  test    r12d, r12d
0x180031baf  jz      short loc_180031BC0
0x180031bb1  mov     rcx, [rsp+6C8h+var_680]
0x180031bb6  test    rcx, rcx
0x180031bb9  jz      short loc_180031BC0
0x180031bbb  mov     eax, [rdi+70h]
0x180031bbe  mov     [rcx], eax
0x180031bc0  mov     ecx, [rdi+20h]
0x180031bc3  test    ecx, ecx
0x180031bc5  jz      short loc_180031BD4
0x180031bc7  mov     r9d, [rdi+24h]
0x180031bcb  add     r9, rdi
0x180031bce  cmp     [r9], r14w
0x180031bd2  jnz     short loc_180031BDE
0x180031bd4  mov     ecx, 10h
0x180031bd9  lea     r9, [rsp+6C8h+var_678]
0x180031bde  mov     r13d, [rsp+6C8h+var_694]
0x180031be3  mov     r8d, 8
0x180031be9  mov     [rsp+6C8h+var_6A0], r14d
0x180031bee  mov     edx, r13d
0x180031bf1  mov     dword ptr [rsp+6C8h+var_6A8], ecx
0x180031bf5  mov     rcx, [rsp+6C8h+var_690]
0x180031bfa  call    InsertInfoListString
0x180031bff  test    eax, eax
0x180031c01  jnz     loc_180031CE3
0x180031c07  test    r12d, r12d
0x180031c0a  jz      loc_180031CE8
0x180031c10  mov     r12d, 2ACh
0x180031c16  mov     ebp, r14d
0x180031c19  cmp     ebp, [rdi+30h]
0x180031c1c  jnb     loc_180031CE8
0x180031c22  mov     r9d, 1
0x180031c28  mov     r8d, 0E4h
0x180031c2e  mov     edx, r12d
0x180031c31  mov     rcx, rsi
0x180031c34  call    InitTapiStruct
0x180031c39  mov     rax, [r15+18h]
0x180031c3d  xor     r9d, r9d
0x180031c40  mov     r8d, [r15]
0x180031c43  mov     edx, ebp
0x180031c45  mov     ecx, [rsp+6C8h+var_698]
0x180031c49  mov     [rsp+6C8h+var_6A8], rsi
0x180031c4e  mov     rax, [rax+110h]
0x180031c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c5a  mov     ebx, eax
0x180031c5c  test    eax, eax
0x180031c5e  jnz     short loc_180031CDC
0x180031c60  mov     eax, [rsi]
0x180031c62  cmp     [rsi+4], eax
0x180031c65  jbe     short loc_180031CA6
0x180031c67  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180031c6e  lea     edx, [rbx+8]; dwFlags
0x180031c71  add     r12d, 100h
0x180031c78  mov     r8d, r12d; dwBytes
0x180031c7b  call    cs:__imp_HeapAlloc
0x180031c81  mov     r14, rax
0x180031c84  test    rax, rax
0x180031c87  jz      short loc_180031CE8
0x180031c89  lea     rax, [rsp+6C8h+var_668]
0x180031c8e  cmp     rsi, rax
0x180031c91  jz      short loc_180031C9B
0x180031c93  mov     rcx, rsi; lpMem
0x180031c96  call    ServerFree
0x180031c9b  mov     rsi, r14
0x180031c9e  xor     r14d, r14d
0x180031ca1  jmp     loc_180031C22
0x180031ca6  mov     eax, [rdi+30h]
0x180031ca9  mov     ecx, r14d
0x180031cac  mov     r9d, [rsi+14h]
0x180031cb0  dec     eax
0x180031cb2  cmp     ebp, eax
0x180031cb4  mov     r8d, 10h
0x180031cba  mov     eax, [rsi+10h]
0x180031cbd  mov     edx, r13d
0x180031cc0  setnb   cl
0x180031cc3  add     r9, rsi
0x180031cc6  mov     [rsp+6C8h+var_6A0], ecx
0x180031cca  mov     rcx, [rsp+6C8h+var_690]
0x180031ccf  mov     dword ptr [rsp+6C8h+var_6A8], eax
0x180031cd3  call    InsertInfoListString
0x180031cd8  test    eax, eax
0x180031cda  jnz     short loc_180031CE3
0x180031cdc  inc     ebp
0x180031cde  jmp     loc_180031C19
0x180031ce3  mov     ebx, 80000044h
0x180031ce8  lea     rax, [rsp+6C8h+Mem]
0x180031cf0  cmp     rdi, rax
0x180031cf3  jz      short loc_180031CFD
0x180031cf5  mov     rcx, rdi; lpMem
0x180031cf8  call    ServerFree
0x180031cfd  lea     rax, [rsp+6C8h+var_668]
0x180031d02  cmp     rsi, rax
0x180031d05  jz      short loc_180031D16
0x180031d07  mov     rcx, rsi; lpMem
0x180031d0a  call    ServerFree
0x180031d0f  jmp     short loc_180031D16
0x180031d11  mov     ebx, 1
0x180031d16  mov     cs:dword_1800519F8, 4F7h
0x180031d20  call    cs:__imp_GetCurrentThreadId
0x180031d26  lea     r8, aPrintscanTapiS_1+10h; pszSrc
0x180031d2d  mov     cs:dword_1800519FC, eax
0x180031d33  lea     rcx, byte_1800519E8; pszDest
0x180031d3a  call    StringCbCopyA
0x180031d3f  lea     rcx, CriticalSection; lpCriticalSection
0x180031d46  call    cs:__imp_LeaveCriticalSection
0x180031d4c  mov     eax, ebx
0x180031d4e  mov     rcx, [rsp+6C8h+var_48]
0x180031d56  xor     rcx, rsp; StackCookie
0x180031d59  call    __security_check_cookie
0x180031d5e  mov     rbx, [rsp+6C8h+arg_0]
0x180031d66  add     rsp, 690h
0x180031d6d  pop     r15
0x180031d6f  pop     r14
0x180031d71  pop     r13
0x180031d73  pop     r12
0x180031d75  pop     rdi
0x180031d76  pop     rsi
0x180031d77  pop     rbp
0x180031d78  retn
```
