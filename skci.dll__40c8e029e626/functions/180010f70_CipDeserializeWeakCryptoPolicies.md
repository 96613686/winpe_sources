# CipDeserializeWeakCryptoPolicies

- ea: `0x180010f70`
- end: `0x180011057`
- name: `CipDeserializeWeakCryptoPolicies`
- size: `231`
- prototype: `__int64 __fastcall(void *Src, size_t MaxCount)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010bd4`

## callees

- `0x180006f10`
- `0x180010f70`
- `0x18003392c`

## import_xrefs

- `securekernel!SkFreePool` at `0x18001103d`
- `securekernel!SkFreePool` at `0x18001103d`

## pseudocode

```c
__int64 __fastcall CipDeserializeWeakCryptoPolicies(void *Src, size_t MaxCount)
{
  size_t v2; // rbx
  _DWORD *PoolHelper; // rax
  _DWORD *v5; // rdi
  unsigned int v6; // ebx
  __int64 v7; // rsi
  _DWORD *i; // rcx
  unsigned int v9; // ebx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  _DWORD *v12; // r9
  __int128 v13; // xmm0
  __int64 v14; // rcx

  v2 = (unsigned int)MaxCount;
  PoolHelper = SkAllocatePoolHelper(258, (unsigned int)MaxCount, 1668499779);
  v5 = PoolHelper;
  if ( PoolHelper )
  {
    v7 = 0;
    memcpy_0(PoolHelper, Src, v2);
    for ( i = v5; (unsigned int)v2 >= 0x30; i = &v12[v10 / 4] )
    {
      if ( (unsigned int)v7 >= 2 )
        break;
      v9 = v2 - 48;
      v10 = 32 * i[8];
      if ( v10 > v9 )
        break;
      v11 = 6 * v7;
      v12 = i + 12;
      *(_OWORD *)&g_CiWeakCryptoPolicy[v11] = *(_OWORD *)i;
      *(_OWORD *)&g_CiWeakCryptoPolicy[v11 + 2] = *((_OWORD *)i + 1);
      v13 = *((_OWORD *)i + 2);
      v14 = (__int64)(i + 12);
      if ( !v10 )
        v14 = 0;
      v7 = (unsigned int)(v7 + 1);
      *(_OWORD *)&g_CiWeakCryptoPolicy[v11 + 4] = v13;
      g_CiWeakCryptoPolicy[v11 + 5] = v14;
      LODWORD(v2) = v9 - v10;
      if ( !(_DWORD)v2 )
      {
        v6 = 0;
        g_CiWeakCryptoPolicies = v7;
        qword_18003F120 = (__int64)g_CiWeakCryptoPolicy;
        return v6;
      }
    }
    v6 = -1073741306;
    SkFreePool(1, v5);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return v6;
}

```

## disassembly

```asm
0x180010f70  push    rbx
0x180010f72  push    rbp
0x180010f73  push    rsi
0x180010f74  push    rdi
0x180010f75  push    r14
0x180010f77  sub     rsp, 20h
0x180010f7b  mov     ebx, edx
0x180010f7d  mov     r14, rcx
0x180010f80  mov     edx, edx
0x180010f82  mov     ecx, 102h
0x180010f87  mov     r8d, 63734943h
0x180010f8d  call    SkAllocatePoolHelper
0x180010f92  mov     rdi, rax
0x180010f95  test    rax, rax
0x180010f98  jnz     short loc_180010FA4
0x180010f9a  mov     ebx, 0C0000017h
0x180010f9f  jmp     loc_180011049
0x180010fa4  xor     esi, esi
0x180010fa6  mov     r8, rbx; MaxCount
0x180010fa9  mov     rdx, r14; Src
0x180010fac  mov     rcx, rdi; void *
0x180010faf  call    memcpy_0
0x180010fb4  mov     rcx, rdi
0x180010fb7  lea     r10, g_CiWeakCryptoPolicy
0x180010fbe  cmp     ebx, 30h ; '0'
0x180010fc1  jb      short loc_180011030
0x180010fc3  cmp     esi, 2
0x180010fc6  jnb     short loc_180011030
0x180010fc8  mov     r8d, [rcx+20h]
0x180010fcc  add     ebx, 0FFFFFFD0h
0x180010fcf  shl     r8d, 5
0x180010fd3  cmp     r8d, ebx
0x180010fd6  ja      short loc_180011030
0x180010fd8  movups  xmm0, xmmword ptr [rcx]
0x180010fdb  xor     eax, eax
0x180010fdd  lea     rdx, [rsi+rsi*2]
0x180010fe1  add     rdx, rdx
0x180010fe4  lea     r9, [rcx+30h]
0x180010fe8  test    r8d, r8d
0x180010feb  movups  xmmword ptr [r10+rdx*8], xmm0
0x180010ff0  movups  xmm1, xmmword ptr [rcx+10h]
0x180010ff4  movups  xmmword ptr [r10+rdx*8+10h], xmm1
0x180010ffa  movups  xmm0, xmmword ptr [rcx+20h]
0x180010ffe  mov     rcx, r9
0x180011001  cmovz   rcx, rax
0x180011005  inc     esi
0x180011007  movups  xmmword ptr [r10+rdx*8+20h], xmm0
0x18001100d  mov     [r10+rdx*8+28h], rcx
0x180011012  sub     ebx, r8d
0x180011015  jz      short loc_18001101F
0x180011017  mov     ecx, r8d
0x18001101a  add     rcx, r9
0x18001101d  jmp     short loc_180010FBE
0x18001101f  xor     ebx, ebx
0x180011021  mov     cs:g_CiWeakCryptoPolicies, esi
0x180011027  mov     cs:qword_18003F120, r10
0x18001102e  jmp     short loc_180011049
0x180011030  mov     ebx, 0C0000206h
0x180011035  mov     rdx, rdi
0x180011038  mov     ecx, 1
0x18001103d  call    cs:__imp_SkFreePool
0x180011044  nop     dword ptr [rax+rax+00h]
0x180011049  mov     eax, ebx
0x18001104b  add     rsp, 20h
0x18001104f  pop     r14
0x180011051  pop     rdi
0x180011052  pop     rsi
0x180011053  pop     rbp
0x180011054  pop     rbx
0x180011055  retn
```
