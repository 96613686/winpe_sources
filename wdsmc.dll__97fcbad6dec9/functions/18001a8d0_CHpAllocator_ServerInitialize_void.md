# CHpAllocator::ServerInitialize(void)

- ea: `0x18001a8d0`
- end: `0x18001a95b`
- name: `?ServerInitialize@CHpAllocator@@AEAAKXZ`
- size: `139`
- prototype: `unsigned int __fastcall(CHpAllocator *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008ff0`
- `0x180009400`

## callees

- `0x18001a8d0`
- `0x180025850`

## import_xrefs

- `KERNEL32!HeapSetInformation` at `0x18001a923`
- `KERNEL32!HeapSetInformation` at `0x18001a923`
- `KERNEL32!HeapCreate` at `0x18001a8df`
- `KERNEL32!HeapCreate` at `0x18001a8df`
- `KERNEL32!GetLastError` at `0x18001a8f1`
- `KERNEL32!GetLastError` at `0x18001a92d`
- `KERNEL32!GetLastError` at `0x18001a8f1`
- `KERNEL32!GetLastError` at `0x18001a92d`

## pseudocode

```c
__int64 __fastcall CHpAllocator::ServerInitialize(CHpAllocator *this)
{
  unsigned int v1; // ebx
  HANDLE v2; // rax
  DWORD v3; // eax
  const char *v4; // rdx
  DWORD LastError; // eax
  const char *v6; // rdx
  unsigned int v7; // eax

  v1 = 0;
  v2 = HeapCreate(0, 0, 0);
  hHeap = v2;
  if ( v2 )
  {
    if ( !HeapSetInformation(v2, HeapEnableTerminationOnCorruption, 0, 0) )
    {
      LastError = GetLastError();
      v7 = ElValidateWin32(LastError, v6, "base\\eco\\wds\\wdslib\\hpalloc\\hpallocator.cpp", 0xE8u);
      if ( !v7 )
        return 31;
      return v7;
    }
  }
  else
  {
    v3 = GetLastError();
    v1 = ElValidateWin32(v3, v4, "base\\eco\\wds\\wdslib\\hpalloc\\hpallocator.cpp", 0xDBu);
    if ( !v1 )
      return 31;
  }
  return v1;
}

```

## disassembly

```asm
0x18001a8d0  push    rbx
0x18001a8d2  sub     rsp, 20h
0x18001a8d6  xor     r8d, r8d; dwMaximumSize
0x18001a8d9  xor     edx, edx; dwInitialSize
0x18001a8db  xor     ecx, ecx; flOptions
0x18001a8dd  xor     ebx, ebx
0x18001a8df  call    cs:__imp_HeapCreate
0x18001a8e5  mov     cs:hHeap, rax
0x18001a8ec  test    rax, rax
0x18001a8ef  jnz     short loc_18001A916
0x18001a8f1  call    cs:__imp_GetLastError
0x18001a8f7  mov     r9d, 0DBh; unsigned int
0x18001a8fd  lea     r8, aBaseEcoWdsWdsl_4; "base\\eco\\wds\\wdslib\\hpalloc\\hpallo"...
0x18001a904  mov     ecx, eax; unsigned int
0x18001a906  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001a90b  mov     ebx, eax
0x18001a90d  test    eax, eax
0x18001a90f  jnz     short loc_18001A953
0x18001a911  lea     ebx, [rax+1Fh]
0x18001a914  jmp     short loc_18001A953
0x18001a916  xor     r9d, r9d; HeapInformationLength
0x18001a919  xor     r8d, r8d; HeapInformation
0x18001a91c  mov     rcx, rax; HeapHandle
0x18001a91f  lea     edx, [r9+1]; HeapInformationClass
0x18001a923  call    cs:__imp_HeapSetInformation
0x18001a929  test    eax, eax
0x18001a92b  jnz     short loc_18001A953
0x18001a92d  call    cs:__imp_GetLastError
0x18001a933  mov     r9d, 0E8h; unsigned int
0x18001a939  lea     r8, aBaseEcoWdsWdsl_4; "base\\eco\\wds\\wdslib\\hpalloc\\hpallo"...
0x18001a940  mov     ecx, eax; unsigned int
0x18001a942  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001a947  mov     ebx, 1Fh
0x18001a94c  test    eax, eax
0x18001a94e  cmovz   eax, ebx
0x18001a951  mov     ebx, eax
0x18001a953  mov     eax, ebx
0x18001a955  add     rsp, 20h
0x18001a959  pop     rbx
0x18001a95a  retn
```
