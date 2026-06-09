# uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)

- ea: `0x180006b3c`
- end: `0x180006bcd`
- name: `?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z`
- size: `145`
- prototype: `void *__fastcall(void *, struct std::filesystem::path *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180006f90`
- `0x180007158`

## callees

- `0x1800061a4`
- `0x180006b3c`
- `0x1800085e8`
- `0x180008868`
- `0x18000fce0`

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
0x180006b3c  mov     [rsp+arg_10], rbx
0x180006b41  push    rdi
0x180006b42  sub     rsp, 60h
0x180006b46  mov     rax, cs:__security_cookie
0x180006b4d  xor     rax, rsp
0x180006b50  mov     [rsp+68h+var_18], rax
0x180006b55  mov     rdi, rdx
0x180006b58  mov     rbx, rcx
0x180006b5b  mov     [rsp+68h+var_40], rcx
0x180006b60  xor     ecx, ecx
0x180006b62  mov     rdx, cs:?archX64@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archX64
0x180006b69  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006b6d  inc     r8
0x180006b70  cmp     [rdx+r8*2], cx
0x180006b75  jnz     short loc_180006B6D
0x180006b77  xorps   xmm0, xmm0
0x180006b7a  movups  [rsp+68h+var_38], xmm0
0x180006b7f  mov     [rsp+68h+var_28], rcx
0x180006b84  mov     [rsp+68h+var_20], rcx
0x180006b89  lea     rcx, [rsp+68h+var_38]
0x180006b8e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006b93  nop
0x180006b94  lea     r8, [rsp+68h+var_38]; void *
0x180006b99  mov     rdx, rdi; struct std::filesystem::path *
0x180006b9c  mov     rcx, rbx; Src
0x180006b9f  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180006ba4  nop
0x180006ba5  lea     rcx, [rsp+68h+var_38]
0x180006baa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006baf  mov     rax, rbx
0x180006bb2  mov     rcx, [rsp+68h+var_18]
0x180006bb7  xor     rcx, rsp; StackCookie
0x180006bba  call    __security_check_cookie
0x180006bbf  mov     rbx, [rsp+68h+arg_10]
0x180006bc7  add     rsp, 60h
0x180006bcb  pop     rdi
0x180006bcc  retn
```
