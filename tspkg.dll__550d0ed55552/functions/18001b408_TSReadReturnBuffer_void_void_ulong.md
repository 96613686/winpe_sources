# TSReadReturnBuffer(void *,void * *,ulong *)

- ea: `0x18001b408`
- end: `0x18001b642`
- name: `?TSReadReturnBuffer@@YAJPEAXPEAPEAXPEAK@Z`
- size: `570`
- prototype: `__int64 __fastcall(void *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001aa90`

## callees

- `0x1800032c0`
- `0x18000b550`
- `0x18001b408`
- `0x18001bf4c`
- `0x18001c63c`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4df`

## pseudocode

```c
__int64 __fastcall TSReadReturnBuffer(void *a1, void **a2, unsigned int *a3)
{
  void *v6; // rsp
  void **v7; // rdi
  _DWORD *v8; // rax
  signed int LastError; // ebx
  char *v10; // rsi
  __int64 v11; // r14
  char *v12; // rax
  unsigned int v13; // r15d
  int v15; // [rsp+0h] [rbp-30h] BYREF
  unsigned int v16; // [rsp+30h] [rbp+0h] BYREF
  void *v17; // [rsp+38h] [rbp+8h] BYREF

  v17 = a1;
  v16 = 0;
  if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x648
    || (unsigned __int64)(g_ulAdditionalProbeSize + 1616) < 0x648
    || !(unsigned int)VerifyStackAvailable()
    || (v6 = alloca(1616), &v15 == (int *)-48LL)
    || (v16 = 1801679955, (v7 = &v17) == 0) )
  {
    v8 = (_DWORD *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(1616);
    v7 = (void **)v8;
    if ( v8 )
    {
      *v8 = 1885431112;
      v7 = (void **)(v8 + 2);
    }
  }
  if ( !v7 )
  {
    LOWORD(LastError) = 14;
    return (unsigned __int16)LastError | 0xC0070000;
  }
  v10 = 0;
  if ( (unsigned int)((__int64 (__fastcall *)(void *, __int64, void **, __int64, unsigned int *))WTSVirtualChannelReadFunc)(
                       a1,
                       30000,
                       v7,
                       1608,
                       &v16) )
  {
    if ( v16 >= 0x20
      && (v11 = *(unsigned int *)v7, (unsigned int)v11 >= 0x18)
      && *((_DWORD *)v7 + 2) == 1319945160
      && !*((_DWORD *)v7 + 4)
      && *((_DWORD *)v7 + 3) == v11 - 24
      && !*((_DWORD *)v7 + 5)
      && (*((_BYTE *)v7 + 4) & 1) != 0 )
    {
      if ( (unsigned int)v11 <= 0xA00000 )
      {
        v12 = (char *)TSAllocate(*(unsigned int *)v7);
        v10 = v12;
        if ( v12 )
        {
          v13 = v16 - 8;
          memcpy_0(v12, v7 + 1, v16 - 8);
          while ( v13 < (unsigned int)v11 )
          {
            if ( !(unsigned int)((__int64 (__fastcall *)(void *, __int64, void **, __int64, unsigned int *))WTSVirtualChannelReadFunc)(
                                  v17,
                                  30000,
                                  v7,
                                  1608,
                                  &v16) )
              goto LABEL_11;
            v16 -= 8;
            memcpy_0(&v10[v13], v7 + 1, v16);
            v13 += v16;
          }
          LastError = 0;
          *a2 = v10;
          *a3 = v11;
        }
        else
        {
          LastError = 14;
        }
      }
      else
      {
        LastError = 111;
      }
    }
    else
    {
      LastError = 7065;
    }
  }
  else
  {
LABEL_11:
    LastError = GetLastError();
  }
  if ( *((_DWORD *)v7 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( LastError )
  {
    if ( v10 )
      ((void (__fastcall *)(char *))TSGlobalLsaFunctions->FreeLsaHeap)(v10);
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0xC0070000;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001b408  push    rbp
0x18001b40a  push    rbx
0x18001b40b  push    rsi
0x18001b40c  push    rdi
0x18001b40d  push    r12
0x18001b40f  push    r13
0x18001b411  push    r14
0x18001b413  push    r15
0x18001b415  sub     rsp, 58h
0x18001b419  lea     rbp, [rsp+30h]
0x18001b41e  mov     rax, cs:__security_cookie
0x18001b425  xor     rax, rbp
0x18001b428  mov     [rbp+60h+var_50], rax
0x18001b42c  mov     esi, 650h
0x18001b431  mov     [rbp+60h+var_58], rcx
0x18001b435  mov     r12, r8
0x18001b438  mov     [rbp+60h+var_60], 0
0x18001b43f  mov     r13, rdx
0x18001b442  mov     rbx, rcx
0x18001b445  lea     r14d, [rsi-8]
0x18001b449  cmp     cs:g_ulMaxStackAllocSize, r14
0x18001b450  jb      short loc_18001B488
0x18001b452  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001b459  add     rcx, rsi
0x18001b45c  cmp     rcx, r14
0x18001b45f  jb      short loc_18001B488
0x18001b461  call    VerifyStackAvailable
0x18001b466  test    eax, eax
0x18001b468  jz      short loc_18001B488
0x18001b46a  mov     eax, [rsp+90h+var_90]
0x18001b46d  sub     rsp, rsi
0x18001b470  lea     rdi, [rsp+90h+var_60]
0x18001b475  mov     eax, [rdi]
0x18001b477  test    rdi, rdi
0x18001b47a  jz      short loc_18001B488
0x18001b47c  mov     dword ptr [rdi], 6B637453h
0x18001b482  add     rdi, 8
0x18001b486  jnz     short loc_18001B4A9
0x18001b488  mov     rax, cs:g_pfnAllocate
0x18001b48f  mov     rcx, rsi
0x18001b492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b497  mov     rdi, rax
0x18001b49a  test    rax, rax
0x18001b49d  jz      short loc_18001B4A9
0x18001b49f  mov     dword ptr [rax], 70616548h
0x18001b4a5  add     rdi, 8
0x18001b4a9  test    rdi, rdi
0x18001b4ac  jnz     short loc_18001B4B6
0x18001b4ae  lea     ebx, [rdi+0Eh]
0x18001b4b1  jmp     loc_18001B61A
0x18001b4b6  lea     rax, [rbp+60h+var_60]
0x18001b4ba  mov     r9d, r14d
0x18001b4bd  mov     [rsp+90h+var_70], rax
0x18001b4c2  mov     r8, rdi
0x18001b4c5  mov     rax, cs:?WTSVirtualChannelReadFunc@@3P6AHPEAXKPEADKPEAK@ZEA; int (*WTSVirtualChannelReadFunc)(void *,ulong,char *,ulong,ulong *)
0x18001b4cc  mov     edx, 7530h
0x18001b4d1  mov     rcx, rbx
0x18001b4d4  xor     esi, esi
0x18001b4d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4db  test    eax, eax
0x18001b4dd  jnz     short loc_18001B4EC
0x18001b4df  call    cs:__imp_GetLastError
0x18001b4e5  mov     ebx, eax
0x18001b4e7  jmp     loc_18001B5E2
0x18001b4ec  cmp     [rbp+60h+var_60], 20h ; ' '
0x18001b4f0  jb      loc_18001B5DD
0x18001b4f6  mov     r14d, [rdi]
0x18001b4f9  cmp     r14d, 18h
0x18001b4fd  jb      loc_18001B5DD
0x18001b503  lea     rbx, [rdi+8]
0x18001b507  cmp     dword ptr [rbx], 4EACC3C8h
0x18001b50d  jnz     loc_18001B5DD
0x18001b513  cmp     [rbx+8], esi
0x18001b516  jnz     loc_18001B5DD
0x18001b51c  mov     ecx, [rbx+4]
0x18001b51f  lea     rax, [r14-18h]
0x18001b523  cmp     rcx, rax
0x18001b526  jnz     loc_18001B5DD
0x18001b52c  cmp     [rbx+0Ch], esi
0x18001b52f  jnz     loc_18001B5DD
0x18001b535  test    byte ptr [rdi+4], 1
0x18001b539  jz      loc_18001B5DD
0x18001b53f  cmp     r14d, 0A00000h
0x18001b546  jbe     short loc_18001B552
0x18001b548  mov     ebx, 6Fh ; 'o'
0x18001b54d  jmp     loc_18001B5E2
0x18001b552  mov     rcx, r14; Size
0x18001b555  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x18001b55a  mov     rsi, rax
0x18001b55d  test    rax, rax
0x18001b560  jnz     short loc_18001B567
0x18001b562  lea     ebx, [rax+0Eh]
0x18001b565  jmp     short loc_18001B5E2
0x18001b567  mov     r15d, [rbp+60h+var_60]
0x18001b56b  mov     rdx, rbx; Src
0x18001b56e  add     r15d, 0FFFFFFF8h
0x18001b572  mov     rcx, rsi; void *
0x18001b575  mov     r8d, r15d; Size
0x18001b578  call    memcpy_0
0x18001b57d  cmp     r15d, r14d
0x18001b580  jnb     short loc_18001B5D1
0x18001b582  mov     rcx, [rbp+60h+var_58]
0x18001b586  lea     rax, [rbp+60h+var_60]
0x18001b58a  mov     [rsp+90h+var_70], rax
0x18001b58f  mov     r9d, 648h
0x18001b595  mov     rax, cs:?WTSVirtualChannelReadFunc@@3P6AHPEAXKPEADKPEAK@ZEA; int (*WTSVirtualChannelReadFunc)(void *,ulong,char *,ulong,ulong *)
0x18001b59c  mov     r8, rdi
0x18001b59f  mov     edx, 7530h
0x18001b5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5a9  test    eax, eax
0x18001b5ab  jz      loc_18001B4DF
0x18001b5b1  mov     eax, [rbp+60h+var_60]
0x18001b5b4  mov     rdx, rbx; Src
0x18001b5b7  add     eax, 0FFFFFFF8h
0x18001b5ba  mov     ecx, r15d
0x18001b5bd  mov     r8d, eax; Size
0x18001b5c0  add     rcx, rsi; void *
0x18001b5c3  mov     [rbp+60h+var_60], eax
0x18001b5c6  call    memcpy_0
0x18001b5cb  add     r15d, [rbp+60h+var_60]
0x18001b5cf  jmp     short loc_18001B57D
0x18001b5d1  xor     ebx, ebx
0x18001b5d3  mov     [r13+0], rsi
0x18001b5d7  mov     [r12], r14d
0x18001b5db  jmp     short loc_18001B5E2
0x18001b5dd  mov     ebx, 1B99h
0x18001b5e2  lea     rcx, [rdi-8]
0x18001b5e6  cmp     dword ptr [rcx], 70616548h
0x18001b5ec  jnz     short loc_18001B5FA
0x18001b5ee  mov     rax, cs:g_pfnFree
0x18001b5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5fa  test    ebx, ebx
0x18001b5fc  jz      short loc_18001B623
0x18001b5fe  test    rsi, rsi
0x18001b601  jz      short loc_18001B616
0x18001b603  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x18001b60a  mov     rcx, rsi
0x18001b60d  mov     rax, [rax+30h]
0x18001b611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b616  test    ebx, ebx
0x18001b618  jle     short loc_18001B623
0x18001b61a  movzx   ebx, bx
0x18001b61d  or      ebx, 0C0070000h
0x18001b623  mov     eax, ebx
0x18001b625  mov     rcx, [rbp+60h+var_50]
0x18001b629  xor     rcx, rbp; StackCookie
0x18001b62c  call    __security_check_cookie
0x18001b631  lea     rsp, [rbp+28h]
0x18001b635  pop     r15
0x18001b637  pop     r14
0x18001b639  pop     r13
0x18001b63b  pop     r12
0x18001b63d  pop     rdi
0x18001b63e  pop     rsi
0x18001b63f  pop     rbx
0x18001b640  pop     rbp
0x18001b641  retn
```
