# CHpAllocator::ServerInitialize(void)

- ea: `0x18000a86c`
- end: `0x18000a90f`
- name: `?ServerInitialize@CHpAllocator@@AEAAKXZ`
- size: `163`
- prototype: `unsigned int __fastcall(CHpAllocator *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005b00`
- `0x180008790`

## callees

- `0x18000a86c`
- `0x18003ce78`

## import_xrefs

- `KERNEL32!HeapSetInformation` at `0x18000a8cb`
- `KERNEL32!HeapSetInformation` at `0x18000a8cb`
- `KERNEL32!HeapCreate` at `0x18000a87b`
- `KERNEL32!HeapCreate` at `0x18000a87b`
- `KERNEL32!GetLastError` at `0x18000a893`
- `KERNEL32!GetLastError` at `0x18000a8db`
- `KERNEL32!GetLastError` at `0x18000a893`
- `KERNEL32!GetLastError` at `0x18000a8db`

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
0x18000a86c  push    rbx
0x18000a86e  sub     rsp, 20h
0x18000a872  xor     r8d, r8d; dwMaximumSize
0x18000a875  xor     edx, edx; dwInitialSize
0x18000a877  xor     ecx, ecx; flOptions
0x18000a879  xor     ebx, ebx
0x18000a87b  call    cs:__imp_HeapCreate
0x18000a882  nop     dword ptr [rax+rax+00h]
0x18000a887  mov     cs:hHeap, rax
0x18000a88e  test    rax, rax
0x18000a891  jnz     short loc_18000A8BE
0x18000a893  call    cs:__imp_GetLastError
0x18000a89a  nop     dword ptr [rax+rax+00h]
0x18000a89f  mov     r9d, 0DBh; unsigned int
0x18000a8a5  lea     r8, aBaseEcoWdsWdsl; "base\\eco\\wds\\wdslib\\hpalloc\\hpallo"...
0x18000a8ac  mov     ecx, eax; unsigned int
0x18000a8ae  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000a8b3  mov     ebx, eax
0x18000a8b5  test    eax, eax
0x18000a8b7  jnz     short loc_18000A907
0x18000a8b9  lea     ebx, [rax+1Fh]
0x18000a8bc  jmp     short loc_18000A907
0x18000a8be  xor     r9d, r9d; HeapInformationLength
0x18000a8c1  xor     r8d, r8d; HeapInformation
0x18000a8c4  mov     rcx, rax; HeapHandle
0x18000a8c7  lea     edx, [r9+1]; HeapInformationClass
0x18000a8cb  call    cs:__imp_HeapSetInformation
0x18000a8d2  nop     dword ptr [rax+rax+00h]
0x18000a8d7  test    eax, eax
0x18000a8d9  jnz     short loc_18000A907
0x18000a8db  call    cs:__imp_GetLastError
0x18000a8e2  nop     dword ptr [rax+rax+00h]
0x18000a8e7  mov     r9d, 0E8h; unsigned int
0x18000a8ed  lea     r8, aBaseEcoWdsWdsl; "base\\eco\\wds\\wdslib\\hpalloc\\hpallo"...
0x18000a8f4  mov     ecx, eax; unsigned int
0x18000a8f6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000a8fb  mov     ebx, 1Fh
0x18000a900  test    eax, eax
0x18000a902  cmovz   eax, ebx
0x18000a905  mov     ebx, eax
0x18000a907  mov     eax, ebx
0x18000a909  add     rsp, 20h
0x18000a90d  pop     rbx
0x18000a90e  retn
```
