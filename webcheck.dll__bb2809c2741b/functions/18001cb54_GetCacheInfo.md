# GetCacheInfo

- ea: `0x18001cb54`
- end: `0x18001cbf6`
- name: `GetCacheInfo`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001aaa0`

## callees

- `0x18001cb54`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18001cb80`
- `KERNEL32!LocalAlloc` at `0x18001cb80`
- `KERNEL32!LocalFree` at `0x18001cbda`
- `KERNEL32!LocalFree` at `0x18001cbda`
- `WININET!GetUrlCacheConfigInfoW` at `0x18001cba5`
- `WININET!GetUrlCacheConfigInfoW` at `0x18001cba5`

## pseudocode

```c
__int64 __fastcall GetCacheInfo(struct _INTERNET_CACHE_CONFIG_INFOW **a1, DWORD *a2, _DWORD *a3)
{
  struct _INTERNET_CACHE_CONFIG_INFOW *v6; // rax
  struct _INTERNET_CACHE_CONFIG_INFOW *v7; // rdi
  unsigned int v8; // ebx
  DWORD cbCacheConfigInfo; // [rsp+58h] [rbp+20h] BYREF

  cbCacheConfigInfo = 560;
  v6 = (struct _INTERNET_CACHE_CONFIG_INFOW *)LocalAlloc(0x40u, 0x230u);
  v7 = v6;
  if ( v6 )
  {
    v6->dwStructSize = 560;
    if ( GetUrlCacheConfigInfoW(v6, &cbCacheConfigInfo, 0x100u)
      && cbCacheConfigInfo >= 0x12C
      && v7->dwNumCachePaths == 1 )
    {
      v8 = 0;
      *a2 = v7->dwQuota;
      *a1 = v7;
      *a3 = 10;
    }
    else
    {
      v8 = -2147467259;
      LocalFree(v7);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v8;
}

```

## disassembly

```asm
0x18001cb54  mov     [rsp+arg_0], rbx
0x18001cb59  mov     [rsp+arg_8], rsi
0x18001cb5e  push    rdi
0x18001cb5f  push    r14
0x18001cb61  push    r15
0x18001cb63  sub     rsp, 20h
0x18001cb67  mov     ebx, 230h
0x18001cb6c  mov     r14, rdx
0x18001cb6f  mov     r15, rcx
0x18001cb72  mov     [rsp+38h+cbCacheConfigInfo], ebx
0x18001cb76  mov     edx, ebx; uBytes
0x18001cb78  mov     ecx, 40h ; '@'; uFlags
0x18001cb7d  mov     rsi, r8
0x18001cb80  call    cs:__imp_LocalAlloc
0x18001cb86  mov     rdi, rax
0x18001cb89  test    rax, rax
0x18001cb8c  jnz     short loc_18001CB95
0x18001cb8e  mov     ebx, 8007000Eh
0x18001cb93  jmp     short loc_18001CBE0
0x18001cb95  mov     r8d, 100h; dwFieldControl
0x18001cb9b  mov     [rax], ebx
0x18001cb9d  lea     rdx, [rsp+38h+cbCacheConfigInfo]; lpcbCacheConfigInfo
0x18001cba2  mov     rcx, rdi; lpCacheConfigInfo
0x18001cba5  call    cs:__imp_GetUrlCacheConfigInfoW
0x18001cbab  test    eax, eax
0x18001cbad  jz      short loc_18001CBD2
0x18001cbaf  cmp     [rsp+38h+cbCacheConfigInfo], 12Ch
0x18001cbb7  jb      short loc_18001CBD2
0x18001cbb9  cmp     dword ptr [rdi+18h], 1
0x18001cbbd  jnz     short loc_18001CBD2
0x18001cbbf  mov     eax, [rdi+8]
0x18001cbc2  xor     ebx, ebx
0x18001cbc4  mov     [r14], eax
0x18001cbc7  mov     [r15], rdi
0x18001cbca  mov     dword ptr [rsi], 0Ah
0x18001cbd0  jmp     short loc_18001CBE0
0x18001cbd2  mov     ebx, 80004005h
0x18001cbd7  mov     rcx, rdi; hMem
0x18001cbda  call    cs:__imp_LocalFree
0x18001cbe0  mov     rsi, [rsp+38h+arg_8]
0x18001cbe5  mov     eax, ebx
0x18001cbe7  mov     rbx, [rsp+38h+arg_0]
0x18001cbec  add     rsp, 20h
0x18001cbf0  pop     r15
0x18001cbf2  pop     r14
0x18001cbf4  pop     rdi
0x18001cbf5  retn
```
