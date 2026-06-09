# p9fs::util::HResultToLinuxError(long)

- ea: `0x18001c970`
- end: `0x18001c9c0`
- name: `?HResultToLinuxError@util@p9fs@@YAJJ@Z`
- size: `80`
- prototype: `__int64 __fastcall(p9fs::util *__hidden this, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001f430`
- `0x180020600`
- `0x1800221d0`
- `0x180031eea`

## callees

- `0x18001c970`
- `0x18001c9ec`

## string_xrefs

- `0x18001c993`: `onecore\vm\dv\storage\plan9\dll\windows\p9errors.cpp`

## pseudocode

```c
__int64 __fastcall p9fs::util::HResultToLinuxError(p9fs::util *this)
{
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( (unsigned int)((_DWORD)this + 2147024894) <= 1 )
    return 4294967294LL;
  if ( (_DWORD)this == -2147024891 )
    return 4294967283LL;
  if ( !(_DWORD)this )
    return 0;
  wil::details::in1diag3::Log_Hr(
    retaddr,
    (void *)0x17,
    (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9errors.cpp",
    (const char *)(unsigned int)this,
    v2);
  return 4294967291LL;
}

```

## disassembly

```asm
0x18001c970  sub     rsp, 28h
0x18001c974  lea     eax, [rcx+7FF8FFFEh]
0x18001c97a  mov     r9d, ecx; char *
0x18001c97d  cmp     eax, 1
0x18001c980  jbe     short loc_18001C9B6
0x18001c982  cmp     ecx, 80070005h
0x18001c988  jz      short loc_18001C9AF
0x18001c98a  test    ecx, ecx
0x18001c98c  jz      short loc_18001C9AB
0x18001c98e  mov     rcx, [rsp+28h]; this
0x18001c993  lea     r8, aOnecoreVmDvSto_11; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x18001c99a  mov     edx, 17h; void *
0x18001c99f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001c9a4  mov     eax, 0FFFFFFFBh
0x18001c9a9  jmp     short loc_18001C9BB
0x18001c9ab  xor     eax, eax
0x18001c9ad  jmp     short loc_18001C9BB
0x18001c9af  mov     eax, 0FFFFFFF3h
0x18001c9b4  jmp     short loc_18001C9BB
0x18001c9b6  mov     eax, 0FFFFFFFEh
0x18001c9bb  add     rsp, 28h
0x18001c9bf  retn
```
