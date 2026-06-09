# uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)

- ea: `0x180009a60`
- end: `0x180009af1`
- name: `?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z`
- size: `145`
- prototype: `void *__fastcall(void *, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180008848`
- `0x18000a430`

## callees

- `0x1800098b8`
- `0x180009a60`
- `0x18000a620`
- `0x18000a98c`
- `0x18000fc90`

## pseudocode

```c
void *__fastcall uus::Utility::GetGuestOrNativeArchFolder(void *a1, struct std::filesystem::path *a2)
{
  __int64 v4; // r8
  __int128 v6; // [rsp+30h] [rbp-38h] BYREF
  __int64 v7; // [rsp+40h] [rbp-28h]
  __int64 v8; // [rsp+48h] [rbp-20h]

  v4 = -1;
  do
    ++v4;
  while ( uus::Const::archX64[v4] );
  v6 = 0;
  v7 = 0;
  v8 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v6, uus::Const::archX64, v4);
  std::filesystem::operator/(a1, a2, &v6);
  std::wstring::~wstring(&v6);
  return a1;
}

```

## disassembly

```asm
0x180009a60  mov     [rsp+arg_10], rbx
0x180009a65  push    rdi
0x180009a66  sub     rsp, 60h
0x180009a6a  mov     rax, cs:__security_cookie
0x180009a71  xor     rax, rsp
0x180009a74  mov     [rsp+68h+var_18], rax
0x180009a79  mov     rdi, rdx
0x180009a7c  mov     rbx, rcx
0x180009a7f  mov     [rsp+68h+var_40], rcx
0x180009a84  xor     ecx, ecx
0x180009a86  mov     rdx, cs:?archX64@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archX64
0x180009a8d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009a91  inc     r8
0x180009a94  cmp     [rdx+r8*2], cx
0x180009a99  jnz     short loc_180009A91
0x180009a9b  xorps   xmm0, xmm0
0x180009a9e  movups  [rsp+68h+var_38], xmm0
0x180009aa3  mov     [rsp+68h+var_28], rcx
0x180009aa8  mov     [rsp+68h+var_20], rcx
0x180009aad  lea     rcx, [rsp+68h+var_38]
0x180009ab2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180009ab7  nop
0x180009ab8  lea     r8, [rsp+68h+var_38]; void *
0x180009abd  mov     rdx, rdi; struct std::filesystem::path *
0x180009ac0  mov     rcx, rbx; Src
0x180009ac3  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180009ac8  nop
0x180009ac9  lea     rcx, [rsp+68h+var_38]
0x180009ace  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009ad3  mov     rax, rbx
0x180009ad6  mov     rcx, [rsp+68h+var_18]
0x180009adb  xor     rcx, rsp; StackCookie
0x180009ade  call    __security_check_cookie
0x180009ae3  mov     rbx, [rsp+68h+arg_10]
0x180009aeb  add     rsp, 60h
0x180009aef  pop     rdi
0x180009af0  retn
```
