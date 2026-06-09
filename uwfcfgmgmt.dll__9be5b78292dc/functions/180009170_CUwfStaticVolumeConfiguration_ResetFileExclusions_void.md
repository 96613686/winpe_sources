# CUwfStaticVolumeConfiguration::ResetFileExclusions(void)

- ea: `0x180009170`
- end: `0x1800091e9`
- name: `?ResetFileExclusions@CUwfStaticVolumeConfiguration@@QEAAJXZ`
- size: `121`
- prototype: `__int64 __fastcall(CUwfStaticVolumeConfiguration *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180006c80`

## callees

- `0x180009170`
- `0x18000e480`
- `0x18000e4d0`
- `0x180011a30`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800091cd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800091cd`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::ResetFileExclusions(CUwfStaticVolumeConfiguration *this)
{
  struct _MULTISZ *v2; // rax
  struct _MULTISZ *v3; // rdi
  int v4; // ebx

  v2 = (struct _MULTISZ *)MultiSzAlloc(&dword_18001FAA4);
  v3 = v2;
  if ( v2 )
  {
    v4 = CUwfRegKey::SetMultiSzValue(
           (CUwfStaticVolumeConfiguration *)((char *)this + 16),
           L"FileExceptionsUserDefined",
           v2);
    if ( v4 >= 0 )
      v4 = CUwfRegKey::SetDWORDValue(
             (CUwfStaticVolumeConfiguration *)((char *)this + 16),
             L"NumFileExceptionsUserDefined",
             0);
  }
  else
  {
    v4 = -2147024882;
  }
  operator delete[](v3);
  if ( v4 < 0 )
    *(_DWORD *)(*((_QWORD *)this + 3) + 16LL) = v4;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180009170  push    rbx
0x180009172  push    rbp
0x180009173  push    rsi
0x180009174  push    rdi
0x180009175  sub     rsp, 28h
0x180009179  mov     rsi, rcx
0x18000917c  mov     edx, 2
0x180009181  lea     rcx, dword_18001FAA4; Src
0x180009188  call    MultiSzAlloc
0x18000918d  mov     rdi, rax
0x180009190  test    rax, rax
0x180009193  jnz     short loc_18000919C
0x180009195  mov     ebx, 8007000Eh
0x18000919a  jmp     short loc_1800091CA
0x18000919c  mov     r8, rdi; struct _MULTISZ *
0x18000919f  lea     rdx, Value; "FileExceptionsUserDefined"
0x1800091a6  lea     rcx, [rsi+10h]; this
0x1800091aa  call    ?SetMultiSzValue@CUwfRegKey@@QEAAJPEBGQEAU_MULTISZ@@@Z; CUwfRegKey::SetMultiSzValue(ushort const *,_MULTISZ * const)
0x1800091af  mov     ebx, eax
0x1800091b1  test    eax, eax
0x1800091b3  js      short loc_1800091CA
0x1800091b5  xor     r8d, r8d; unsigned int
0x1800091b8  lea     rdx, aNumfileexcepti; "NumFileExceptionsUserDefined"
0x1800091bf  lea     rcx, [rsi+10h]; this
0x1800091c3  call    ?SetDWORDValue@CUwfRegKey@@QEAAJPEBGK@Z; CUwfRegKey::SetDWORDValue(ushort const *,ulong)
0x1800091c8  mov     ebx, eax
0x1800091ca  mov     rcx, rdi
0x1800091cd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800091d3  test    ebx, ebx
0x1800091d5  jns     short loc_1800091DE
0x1800091d7  mov     rax, [rsi+18h]
0x1800091db  mov     [rax+10h], ebx
0x1800091de  mov     eax, ebx
0x1800091e0  add     rsp, 28h
0x1800091e4  pop     rdi
0x1800091e5  pop     rsi
0x1800091e6  pop     rbp
0x1800091e7  pop     rbx
0x1800091e8  retn
```
