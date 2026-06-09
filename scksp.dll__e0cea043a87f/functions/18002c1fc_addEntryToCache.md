# addEntryToCache

- ea: `0x18002c1fc`
- end: `0x18002c2ee`
- name: `addEntryToCache`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18002c108`

## callees

- `0x180009e82`
- `0x18002c188`
- `0x18002c1fc`
- `0x18002c388`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c2df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c2df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c223`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c223`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002c288`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002c288`

## pseudocode

```c
void __fastcall addEntryToCache(__int64 a1, const wchar_t *a2)
{
  __int64 Cache; // rdi
  int i; // r8d
  wchar_t *v6; // rbx
  unsigned int v7; // r8d
  int j; // edx

  Cache = getCache();
  if ( Cache )
  {
    AcquireSRWLockExclusive(g_pHandleCacheLock);
    for ( i = 0; i < 8; ++i )
    {
      v6 = (wchar_t *)(Cache + 224LL * i);
      if ( !*(_QWORD *)v6 )
      {
        if ( v6 )
        {
LABEL_12:
          if ( StringCchCopyW(v6 + 12, 0x21u, a2) >= 0 )
          {
            *((_QWORD *)v6 + 2) = 0;
            *(_QWORD *)v6 = a1;
            *((_QWORD *)v6 + 1) = 1;
          }
          else
          {
            memset_0(v6, 0, 0xE0u);
          }
          goto LABEL_15;
        }
        break;
      }
    }
    v7 = g_handleCacheNextReplace;
    for ( j = 0; j < 8; ++j )
    {
      v6 = (wchar_t *)(Cache + 224LL * v7);
      v7 = ((_BYTE)v7 + 1) & 7;
      g_handleCacheNextReplace = v7;
      if ( !*((_QWORD *)v6 + 1) )
      {
        BCryptCloseAlgorithmProvider(*(BCRYPT_ALG_HANDLE *)v6, 0);
        memset_0(v6, 0, 0xE0u);
        goto LABEL_12;
      }
    }
LABEL_15:
    ReleaseSRWLockExclusive(g_pHandleCacheLock);
  }
}

```

## disassembly

```asm
0x18002c1fc  push    rbx
0x18002c1fe  push    rbp
0x18002c1ff  push    rsi
0x18002c200  push    rdi
0x18002c201  sub     rsp, 28h
0x18002c205  mov     rbp, rdx
0x18002c208  mov     rsi, rcx
0x18002c20b  call    getCache
0x18002c210  mov     rdi, rax
0x18002c213  test    rax, rax
0x18002c216  jz      loc_18002C2E5
0x18002c21c  mov     rcx, cs:g_pHandleCacheLock; SRWLock
0x18002c223  call    cs:__imp_AcquireSRWLockExclusive
0x18002c229  xor     r8d, r8d
0x18002c22c  cmp     r8d, 8
0x18002c230  jge     short loc_18002C24F
0x18002c232  movsxd  rax, r8d
0x18002c235  imul    rbx, rax, 0E0h
0x18002c23c  add     rbx, rdi
0x18002c23f  cmp     qword ptr [rbx], 0
0x18002c243  jz      short loc_18002C24A
0x18002c245  inc     r8d
0x18002c248  jmp     short loc_18002C22C
0x18002c24a  test    rbx, rbx
0x18002c24d  jnz     short loc_18002C29E
0x18002c24f  mov     r8d, cs:g_handleCacheNextReplace
0x18002c256  xor     edx, edx
0x18002c258  cmp     edx, 8
0x18002c25b  jge     short loc_18002C2D8
0x18002c25d  mov     eax, r8d
0x18002c260  imul    rbx, rax, 0E0h
0x18002c267  add     rbx, rdi
0x18002c26a  inc     r8d
0x18002c26d  and     r8d, 7
0x18002c271  mov     cs:g_handleCacheNextReplace, r8d
0x18002c278  cmp     qword ptr [rbx+8], 0
0x18002c27d  jz      short loc_18002C283
0x18002c27f  inc     edx
0x18002c281  jmp     short loc_18002C258
0x18002c283  mov     rcx, [rbx]; hAlgorithm
0x18002c286  xor     edx, edx; dwFlags
0x18002c288  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002c28e  xor     edx, edx; Val
0x18002c290  mov     r8d, 0E0h; Size
0x18002c296  mov     rcx, rbx; void *
0x18002c299  call    memset_0
0x18002c29e  lea     rcx, [rbx+18h]; pszDest
0x18002c2a2  mov     r8, rbp; pszSrc
0x18002c2a5  mov     edx, 21h ; '!'; cchDest
0x18002c2aa  call    StringCchCopyW
0x18002c2af  test    eax, eax
0x18002c2b1  jns     short loc_18002C2C5
0x18002c2b3  xor     edx, edx; Val
0x18002c2b5  mov     r8d, 0E0h; Size
0x18002c2bb  mov     rcx, rbx; void *
0x18002c2be  call    memset_0
0x18002c2c3  jmp     short loc_18002C2D8
0x18002c2c5  mov     qword ptr [rbx+10h], 0
0x18002c2cd  mov     [rbx], rsi
0x18002c2d0  mov     qword ptr [rbx+8], 1
0x18002c2d8  mov     rcx, cs:g_pHandleCacheLock; SRWLock
0x18002c2df  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c2e5  add     rsp, 28h
0x18002c2e9  pop     rdi
0x18002c2ea  pop     rsi
0x18002c2eb  pop     rbp
0x18002c2ec  pop     rbx
0x18002c2ed  retn
```
