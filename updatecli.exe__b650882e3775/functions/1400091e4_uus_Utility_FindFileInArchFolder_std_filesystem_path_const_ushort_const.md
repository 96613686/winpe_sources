# uus::Utility::FindFileInArchFolder(std::filesystem::path const &,ushort const *)

- ea: `0x1400091e4`
- end: `0x1400092e3`
- name: `?FindFileInArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140007ea8`

## callees

- `0x140002130`
- `0x1400087c4`
- `0x1400091e4`
- `0x1400092ec`
- `0x1400093c0`
- `0x140009608`
- `0x14000969c`

## pseudocode

```c
__int64 __fastcall uus::Utility::FindFileInArchFolder(__int64 a1, __int64 a2)
{
  struct std::filesystem::path *GuestOrNativeArchFolder; // rax
  __int64 HostArchFolder; // rax
  __int16 v7; // [rsp+20h] [rbp-39h] BYREF
  __int64 v8; // [rsp+22h] [rbp-37h]
  int v9; // [rsp+2Ah] [rbp-2Fh]
  __int16 v10; // [rsp+2Eh] [rbp-2Bh]
  __m128i si128; // [rsp+30h] [rbp-29h]
  char v12; // [rsp+40h] [rbp-19h]
  __int64 v13; // [rsp+50h] [rbp-9h]
  _BYTE v14[40]; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v15[32]; // [rsp+80h] [rbp+27h] BYREF

  v13 = a1;
  GuestOrNativeArchFolder = (struct std::filesystem::path *)uus::Utility::GetGuestOrNativeArchFolder(v15, a2);
  uus::Utility::FindFileInSubFolder((std::filesystem::path *)&v7, GuestOrNativeArchFolder);
  std::wstring::~wstring(v15);
  if ( v12 )
  {
    *(_OWORD *)a1 = 0;
    *(_WORD *)a1 = v7;
    *(_QWORD *)(a1 + 2) = v8;
    *(_DWORD *)(a1 + 10) = v9;
    *(_WORD *)(a1 + 14) = v10;
    *(__m128i *)(a1 + 16) = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v7 = 0;
    *(_BYTE *)(a1 + 32) = 1;
LABEL_6:
    std::wstring::~wstring(&v7);
    return a1;
  }
  HostArchFolder = uus::Utility::GetHostArchFolder(v14, a2);
  uus::Utility::FindFileInSubFolder(a1, HostArchFolder);
  if ( v14[32] )
    std::wstring::~wstring(v14);
  if ( v12 )
    goto LABEL_6;
  return a1;
}

```

## disassembly

```asm
0x1400091e4  mov     [rsp-8+arg_10], rbx
0x1400091e9  mov     [rsp-8+arg_18], rdi
0x1400091ee  push    rbp
0x1400091ef  lea     rbp, [rsp-57h]
0x1400091f4  sub     rsp, 0B0h
0x1400091fb  mov     rax, cs:__security_cookie
0x140009202  xor     rax, rsp
0x140009205  mov     [rbp+57h+var_10], rax
0x140009209  mov     rdi, rdx
0x14000920c  mov     rbx, rcx
0x14000920f  mov     [rbp+57h+var_60], rcx
0x140009213  lea     rcx, [rbp+57h+var_30]
0x140009217  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x14000921c  nop
0x14000921d  mov     rdx, rax; struct std::filesystem::path *
0x140009220  lea     rcx, [rbp+57h+var_90]; this
0x140009224  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)
0x140009229  nop
0x14000922a  lea     rcx, [rbp+57h+var_30]
0x14000922e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009233  cmp     [rbp+57h+var_70], 0
0x140009237  jz      short loc_140009287
0x140009239  xorps   xmm0, xmm0
0x14000923c  movups  xmmword ptr [rbx], xmm0
0x14000923f  movzx   eax, [rbp+57h+var_90]
0x140009243  mov     [rbx], ax
0x140009246  movsd   xmm0, [rbp+57h+var_8E]
0x14000924b  movsd   qword ptr [rbx+2], xmm0
0x140009250  mov     eax, [rbp+57h+var_86]
0x140009253  mov     [rbx+0Ah], eax
0x140009256  movzx   eax, [rbp+57h+var_82]
0x14000925a  mov     [rbx+0Eh], ax
0x14000925e  mov     rcx, qword ptr [rbp+57h+var_80]
0x140009262  mov     [rbx+10h], rcx
0x140009266  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x14000926a  mov     [rbx+18h], rcx
0x14000926e  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140009276  movdqu  [rbp+57h+var_80], xmm0
0x14000927b  xor     ecx, ecx
0x14000927d  mov     [rbp+57h+var_90], cx
0x140009281  mov     byte ptr [rbx+20h], 1
0x140009285  jmp     short loc_1400092B6
0x140009287  mov     rdx, rdi
0x14000928a  lea     rcx, [rbp+57h+var_58]
0x14000928e  call    ?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z; uus::Utility::GetHostArchFolder(std::filesystem::path const &)
0x140009293  nop
0x140009294  mov     rdx, rax
0x140009297  mov     rcx, rbx
0x14000929a  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEBG@Z; uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,ushort const *)
0x14000929f  nop
0x1400092a0  cmp     [rbp+57h+var_38], 0
0x1400092a4  jz      short loc_1400092B0
0x1400092a6  lea     rcx, [rbp+57h+var_58]
0x1400092aa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400092af  nop
0x1400092b0  cmp     [rbp+57h+var_70], 0
0x1400092b4  jz      short loc_1400092BF
0x1400092b6  lea     rcx, [rbp+57h+var_90]
0x1400092ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400092bf  mov     rax, rbx
0x1400092c2  mov     rcx, [rbp+57h+var_10]
0x1400092c6  xor     rcx, rsp; StackCookie
0x1400092c9  call    __security_check_cookie
0x1400092ce  lea     r11, [rsp+0B0h+var_s0]
0x1400092d6  mov     rbx, [r11+20h]
0x1400092da  mov     rdi, [r11+28h]
0x1400092de  mov     rsp, r11
0x1400092e1  pop     rbp
0x1400092e2  retn
```
