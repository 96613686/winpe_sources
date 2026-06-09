# CThumbnailCache::_ValidateCallingThread(void)

- ea: `0x18000cb34`
- end: `0x18000cb7e`
- name: `?_ValidateCallingThread@CThumbnailCache@@AEAAJXZ`
- size: `74`
- prototype: `int(CThumbnailCache *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180013870`
- `0x180013a70`
- `0x180014ae0`
- `0x180014fd0`
- `0x18002cc40`
- `0x18002e470`

## callees

- `0x18000bfd8`
- `0x18000cb34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb46`

## string_xrefs

- `0x18000cb61`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`

## pseudocode

```c
__int64 __fastcall CThumbnailCache::_ValidateCallingThread(CThumbnailCache *this)
{
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( (*((_BYTE *)this + 768) & 8) != 0 || *((_DWORD *)this + 191) == GetCurrentThreadId() )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1326,
    (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
    (const char *)0x800705A4LL,
    v2);
  return 2147943844LL;
}

```

## disassembly

```asm
0x18000cb34  push    rbx; int
0x18000cb36  sub     rsp, 20h
0x18000cb3a  test    byte ptr [rcx+300h], 8
0x18000cb41  mov     rbx, rcx
0x18000cb44  jnz     short loc_18000CB54
0x18000cb46  call    cs:__imp_GetCurrentThreadId
0x18000cb4c  cmp     [rbx+2FCh], eax
0x18000cb52  jnz     short loc_18000CB5C
0x18000cb54  xor     eax, eax
0x18000cb56  add     rsp, 20h
0x18000cb5a  pop     rbx
0x18000cb5b  retn
0x18000cb5c  mov     rcx, [rsp+28h]; this
0x18000cb61  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18000cb68  mov     ebx, 800705A4h
0x18000cb6d  mov     edx, 1326h; void *
0x18000cb72  mov     r9d, ebx; char *
0x18000cb75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb7a  mov     eax, ebx
0x18000cb7c  jmp     short loc_18000CB56
```
