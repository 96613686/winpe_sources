# UL_DISCONNECT_CONTEXT::Initialize(void)

- ea: `0x180015b2c`
- end: `0x180015bb8`
- name: `?Initialize@UL_DISCONNECT_CONTEXT@@SAJXZ`
- size: `140`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180001060`

## callees

- `0x18001358c`
- `0x180015b2c`
- `0x1800160a0`

## import_xrefs

- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180015b7b`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180015b7b`

## pseudocode

```c
__int64 UL_DISCONNECT_CONTEXT::Initialize(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  _DWORD v2[4]; // [rsp+20h] [rbp-28h] BYREF

  v2[0] = 1;
  v2[1] = 100;
  v2[2] = 56;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( v0 )
  {
    UL_DISCONNECT_CONTEXT::sm_pachDisconnects = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                                  v0,
                                                  "UL_DISCONNECT_CONTEXT",
                                                  (const struct ALLOC_CACHE_CONFIGURATION *)v2,
                                                  1);
    return UL_DISCONNECT_CONTEXT::sm_pachDisconnects == 0 ? 0x80070008 : 0;
  }
  else
  {
    UL_DISCONNECT_CONTEXT::sm_pachDisconnects = 0;
    return 2147942408LL;
  }
}

```

## disassembly

```asm
0x180015b2c  sub     rsp, 48h
0x180015b30  mov     rax, cs:__security_cookie
0x180015b37  xor     rax, rsp
0x180015b3a  mov     [rsp+48h+var_18], rax
0x180015b3f  mov     ecx, 100h; Size
0x180015b44  mov     [rsp+48h+var_28], 1
0x180015b4c  mov     [rsp+48h+var_24], 64h ; 'd'
0x180015b54  mov     [rsp+48h+var_20], 38h ; '8'
0x180015b5c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015b61  test    rax, rax
0x180015b64  jz      short loc_180015B96
0x180015b66  mov     r9d, 1
0x180015b6c  lea     r8, [rsp+48h+var_28]
0x180015b71  lea     rdx, aUlDisconnectCo_0; "UL_DISCONNECT_CONTEXT"
0x180015b78  mov     rcx, rax
0x180015b7b  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x180015b81  mov     cs:?sm_pachDisconnects@UL_DISCONNECT_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * UL_DISCONNECT_CONTEXT::sm_pachDisconnects
0x180015b88  neg     rax
0x180015b8b  sbb     eax, eax
0x180015b8d  not     eax
0x180015b8f  and     eax, 80070008h
0x180015b94  jmp     short loc_180015BA6
0x180015b96  mov     cs:?sm_pachDisconnects@UL_DISCONNECT_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * UL_DISCONNECT_CONTEXT::sm_pachDisconnects
0x180015ba1  mov     eax, 80070008h
0x180015ba6  mov     rcx, [rsp+48h+var_18]
0x180015bab  xor     rcx, rsp; StackCookie
0x180015bae  call    __security_check_cookie
0x180015bb3  add     rsp, 48h
0x180015bb7  retn
```
