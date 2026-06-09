# WIN32_COMPLETION_PACKET::InitializeStatic(void)

- ea: `0x180003fb0`
- end: `0x18000403c`
- name: `?InitializeStatic@WIN32_COMPLETION_PACKET@@SAJXZ`
- size: `140`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003d80`

## callees

- `0x180001f4c`
- `0x180003fb0`
- `0x1800041d0`

## import_xrefs

- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180003fff`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180003fff`

## string_xrefs

- `0x180003ff5`: `WIN32_COMPLETION_PACKET`

## pseudocode

```c
__int64 WIN32_COMPLETION_PACKET::InitializeStatic(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  _DWORD v2[4]; // [rsp+20h] [rbp-28h] BYREF

  v2[0] = 1;
  v2[1] = 100;
  v2[2] = 24;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( v0 )
  {
    WIN32_COMPLETION_PACKET::sm_Allocator = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                              v0,
                                              "WIN32_COMPLETION_PACKET",
                                              (const struct ALLOC_CACHE_CONFIGURATION *)v2,
                                              1);
    return WIN32_COMPLETION_PACKET::sm_Allocator == 0 ? 0x8007000E : 0;
  }
  else
  {
    WIN32_COMPLETION_PACKET::sm_Allocator = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180003fb0  sub     rsp, 48h
0x180003fb4  mov     rax, cs:__security_cookie
0x180003fbb  xor     rax, rsp
0x180003fbe  mov     [rsp+48h+var_18], rax
0x180003fc3  mov     ecx, 100h; Size
0x180003fc8  mov     [rsp+48h+var_28], 1
0x180003fd0  mov     [rsp+48h+var_24], 64h ; 'd'
0x180003fd8  mov     [rsp+48h+var_20], 18h
0x180003fe0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003fe5  test    rax, rax
0x180003fe8  jz      short loc_18000401A
0x180003fea  mov     r9d, 1
0x180003ff0  lea     r8, [rsp+48h+var_28]
0x180003ff5  lea     rdx, aWin32Completio; "WIN32_COMPLETION_PACKET"
0x180003ffc  mov     rcx, rax
0x180003fff  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x180004005  mov     cs:?sm_Allocator@WIN32_COMPLETION_PACKET@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * WIN32_COMPLETION_PACKET::sm_Allocator
0x18000400c  neg     rax
0x18000400f  sbb     eax, eax
0x180004011  not     eax
0x180004013  and     eax, 8007000Eh
0x180004018  jmp     short loc_18000402A
0x18000401a  mov     cs:?sm_Allocator@WIN32_COMPLETION_PACKET@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * WIN32_COMPLETION_PACKET::sm_Allocator
0x180004025  mov     eax, 8007000Eh
0x18000402a  mov     rcx, [rsp+48h+var_18]
0x18000402f  xor     rcx, rsp; StackCookie
0x180004032  call    __security_check_cookie
0x180004037  add     rsp, 48h
0x18000403b  retn
```
