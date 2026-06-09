# uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)

- ea: `0x140007060`
- end: `0x1400070f1`
- name: `?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140007320`

## callees

- `0x140006d08`
- `0x140007060`
- `0x140009214`
- `0x140009340`
- `0x14001aa60`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
std::filesystem::path *__fastcall uus::Utility::GetGuestOrNativeArchFolder(
        std::filesystem::path *a1,
        struct std::filesystem::path *a2)
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
  std::wstring::_Construct<1,wchar_t const *>(&v6, uus::Const::archX64);
  std::filesystem::operator/(a1, a2, &v6);
  std::wstring::~wstring(&v6);
  return a1;
}

```

## disassembly

```asm
0x140007060  mov     [rsp+arg_10], rbx
0x140007065  push    rdi
0x140007066  sub     rsp, 60h
0x14000706a  mov     rax, cs:__security_cookie
0x140007071  xor     rax, rsp
0x140007074  mov     [rsp+68h+var_18], rax
0x140007079  mov     rdi, rdx
0x14000707c  mov     rbx, rcx
0x14000707f  mov     [rsp+68h+var_40], rcx
0x140007084  xor     ecx, ecx
0x140007086  mov     rdx, cs:?archX64@Const@uus@@2PEB_WEB; wchar_t const * const uus::Const::archX64
0x14000708d  or      r8, 0FFFFFFFFFFFFFFFFh
0x140007091  inc     r8
0x140007094  cmp     [rdx+r8*2], cx
0x140007099  jnz     short loc_140007091
0x14000709b  xorps   xmm0, xmm0
0x14000709e  movups  [rsp+68h+var_38], xmm0
0x1400070a3  mov     [rsp+68h+var_28], rcx
0x1400070a8  mov     [rsp+68h+var_20], rcx
0x1400070ad  lea     rcx, [rsp+68h+var_38]
0x1400070b2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400070b7  nop
0x1400070b8  lea     r8, [rsp+68h+var_38]; void *
0x1400070bd  mov     rdx, rdi; struct std::filesystem::path *
0x1400070c0  mov     rcx, rbx; Src
0x1400070c3  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1400070c8  nop
0x1400070c9  lea     rcx, [rsp+68h+var_38]
0x1400070ce  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400070d3  mov     rax, rbx
0x1400070d6  mov     rcx, [rsp+68h+var_18]
0x1400070db  xor     rcx, rsp; StackCookie
0x1400070de  call    __security_check_cookie
0x1400070e3  mov     rbx, [rsp+68h+arg_10]
0x1400070eb  add     rsp, 60h
0x1400070ef  pop     rdi
0x1400070f0  retn
```
