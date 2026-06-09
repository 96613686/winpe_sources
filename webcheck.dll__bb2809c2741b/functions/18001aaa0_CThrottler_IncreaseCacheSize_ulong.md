# CThrottler::IncreaseCacheSize(ulong *)

- ea: `0x18001aaa0`
- end: `0x18001ab4c`
- name: `?IncreaseCacheSize@CThrottler@@AEAAJPEAK@Z`
- size: `172`
- prototype: `__int64 __fastcall(CThrottler *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019f80`
- `0x18001a03c`

## callees

- `0x18001aaa0`
- `0x18001cb54`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001ab2b`
- `KERNEL32!LocalFree` at `0x18001ab2b`
- `WININET!SetUrlCacheConfigInfoW` at `0x18001ab1a`
- `WININET!SetUrlCacheConfigInfoW` at `0x18001ab1a`

## pseudocode

```c
__int64 __fastcall CThrottler::IncreaseCacheSize(CThrottler *this, unsigned int *a2)
{
  unsigned int v4; // ebp
  int CacheInfo; // eax
  unsigned int v6; // ebx
  DWORD v7; // edi
  LPINTERNET_CACHE_CONFIG_INFOW v8; // rsi
  int v9; // eax
  DWORD v10; // eax
  unsigned int v12; // [rsp+58h] [rbp+10h] BYREF
  int v13; // [rsp+60h] [rbp+18h] BYREF
  LPINTERNET_CACHE_CONFIG_INFOW lpCacheConfigInfo; // [rsp+68h] [rbp+20h] BYREF

  lpCacheConfigInfo = 0;
  v12 = 0;
  v13 = 0;
  v4 = -2147467259;
  CacheInfo = GetCacheInfo(&lpCacheConfigInfo, &v12, &v13);
  v6 = v12;
  if ( CacheInfo >= 0 )
  {
    v7 = *((_DWORD *)this + 27);
    v8 = lpCacheConfigInfo;
    if ( v12 < v7 )
    {
      v9 = *((_DWORD *)this + 28);
      if ( v9 )
      {
        v10 = v12 + v9;
        lpCacheConfigInfo->dwContainer = 0;
        if ( v10 <= v7 )
          v7 = v10;
        v8->dwQuota = v7;
        if ( SetUrlCacheConfigInfoW(v8, 0x800u) )
        {
          v4 = 0;
          v6 = v7;
        }
      }
    }
    LocalFree(v8);
  }
  if ( a2 )
    *a2 = v6;
  return v4;
}

```

## disassembly

```asm
0x18001aaa0  mov     rax, rsp
0x18001aaa3  mov     [rax+8], rbx
0x18001aaa7  push    rbp
0x18001aaa8  push    rsi
0x18001aaa9  push    rdi
0x18001aaaa  push    r14
0x18001aaac  push    r15
0x18001aaae  sub     rsp, 20h
0x18001aab2  mov     r14, rdx
0x18001aab5  mov     qword ptr [rax+20h], 0
0x18001aabd  mov     r15, rcx
0x18001aac0  mov     dword ptr [rax+10h], 0
0x18001aac7  lea     rdx, [rax+10h]
0x18001aacb  mov     dword ptr [rax+18h], 0
0x18001aad2  lea     rcx, [rax+20h]
0x18001aad6  mov     ebp, 80004005h
0x18001aadb  lea     r8, [rax+18h]
0x18001aadf  call    GetCacheInfo
0x18001aae4  mov     ebx, [rsp+48h+arg_8]
0x18001aae8  test    eax, eax
0x18001aaea  js      short loc_18001AB31
0x18001aaec  mov     edi, [r15+6Ch]
0x18001aaf0  mov     rsi, [rsp+48h+lpCacheConfigInfo]
0x18001aaf5  cmp     ebx, edi
0x18001aaf7  jnb     short loc_18001AB28
0x18001aaf9  mov     eax, [r15+70h]
0x18001aafd  test    eax, eax
0x18001aaff  jz      short loc_18001AB28
0x18001ab01  add     eax, ebx
0x18001ab03  mov     dword ptr [rsi+4], 0
0x18001ab0a  cmp     eax, edi
0x18001ab0c  mov     edx, 800h; dwFieldControl
0x18001ab11  mov     rcx, rsi; lpCacheConfigInfo
0x18001ab14  cmovbe  edi, eax
0x18001ab17  mov     [rsi+8], edi
0x18001ab1a  call    cs:__imp_SetUrlCacheConfigInfoW
0x18001ab20  test    eax, eax
0x18001ab22  jz      short loc_18001AB28
0x18001ab24  xor     ebp, ebp
0x18001ab26  mov     ebx, edi
0x18001ab28  mov     rcx, rsi; hMem
0x18001ab2b  call    cs:__imp_LocalFree
0x18001ab31  test    r14, r14
0x18001ab34  jz      short loc_18001AB39
0x18001ab36  mov     [r14], ebx
0x18001ab39  mov     rbx, [rsp+48h+arg_0]
0x18001ab3e  mov     eax, ebp
0x18001ab40  add     rsp, 20h
0x18001ab44  pop     r15
0x18001ab46  pop     r14
0x18001ab48  pop     rdi
0x18001ab49  pop     rsi
0x18001ab4a  pop     rbp
0x18001ab4b  retn
```
