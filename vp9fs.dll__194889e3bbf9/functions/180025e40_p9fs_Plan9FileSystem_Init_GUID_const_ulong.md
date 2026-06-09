# p9fs::Plan9FileSystem::Init(_GUID const *,ulong)

- ea: `0x180025e40`
- end: `0x180025eb5`
- name: `?Init@Plan9FileSystem@p9fs@@UEAAJPEBU_GUID@@K@Z`
- size: `117`
- prototype: `int(p9fs::Plan9FileSystem *__hidden this, const struct _GUID *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180009fe4`
- `0x180025460`
- `0x180025e40`
- `0x18002b720`

## import_xrefs

- `WS2_32!__imp_closesocket` at `0x180025ea0`
- `WS2_32!__imp_closesocket` at `0x180025ea0`

## string_xrefs

- `0x180025e5e`: `onecore\vm\dv\storage\plan9\dll\windows\p9fs.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall p9fs::Plan9FileSystem::Init(p9fs::Plan9FileSystem *this, struct _GUID *a2, int a3)
{
  p9fs::Socket *v3; // rbx
  __int64 result; // rax
  void *v5; // rdx
  const char *v6; // r9
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  SOCKET s; // [rsp+30h] [rbp+8h] BYREF

  v3 = (p9fs::Plan9FileSystem *)((char *)this + 16);
  if ( *((_QWORD *)this + 3) == -1 )
  {
    try
    {
      p9fs::CreateListenHvSocket(&s, a2, a3);
      v5 = (void *)s;
      s = -1;
      p9fs::Socket::Reset(v3, v5);
      if ( s != -1 )
        closesocket(s);
      result = 0;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x2CD,
                             (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
                             v6);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C7,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
      (const char *)0x8000000DLL,
      v7);
    return 2147483661LL;
  }
  return result;
}

```

## disassembly

```asm
0x180025e40  push    rbx; int
0x180025e42  sub     rsp, 20h
0x180025e46  lea     rbx, [rcx+10h]
0x180025e4a  cmp     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180025e4f  jz      short loc_180025E73
0x180025e51  mov     rcx, [rsp+28h]; this
0x180025e56  mov     ebx, 8000000Dh
0x180025e5b  mov     r9d, ebx; char *
0x180025e5e  lea     r8, aOnecoreVmDvSto_8; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180025e65  mov     edx, 2C7h; void *
0x180025e6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025e6f  mov     eax, ebx
0x180025e71  jmp     short loc_180025EAE
0x180025e73  lea     rcx, [rsp+28h+s]
0x180025e78  call    ?CreateListenHvSocket@p9fs@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEBU_GUID@@K@Z; p9fs::CreateListenHvSocket(_GUID const &,ulong)
0x180025e7d  nop
0x180025e7e  mov     rdx, [rsp+28h+s]; unsigned __int64
0x180025e83  mov     [rsp+28h+s], 0FFFFFFFFFFFFFFFFh
0x180025e8c  mov     rcx, rbx; this
0x180025e8f  call    ?Reset@Socket@p9fs@@QEAAX_K@Z; p9fs::Socket::Reset(unsigned __int64)
0x180025e94  nop
0x180025e95  mov     rcx, [rsp+28h+s]; s
0x180025e9a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180025e9e  jz      short loc_180025EA6
0x180025ea0  call    cs:__imp_closesocket
0x180025ea6  xor     eax, eax
0x180025ea8  jmp     short loc_180025EAE
0x180025eaa  mov     eax, dword ptr [rsp+28h+s]
0x180025eae  add     rsp, 20h
0x180025eb2  pop     rbx
0x180025eb3  retn
```
