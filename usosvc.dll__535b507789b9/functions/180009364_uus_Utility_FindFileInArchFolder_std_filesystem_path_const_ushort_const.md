# uus::Utility::FindFileInArchFolder(std::filesystem::path const &,ushort const *)

- ea: `0x180009364`
- end: `0x180009463`
- name: `?FindFileInArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800081ec`

## callees

- `0x1800026d0`
- `0x180008b08`
- `0x180009364`
- `0x18000946c`
- `0x180009540`
- `0x1800097fc`
- `0x180009890`

## pseudocode

```c
__int64 __fastcall uus::Utility::FindFileInArchFolder(__int64 a1, struct std::filesystem::path *a2)
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
  HostArchFolder = uus::Utility::GetHostArchFolder((__int64)v14, a2);
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
0x180009364  mov     [rsp-8+arg_10], rbx
0x180009369  mov     [rsp-8+arg_18], rdi
0x18000936e  push    rbp
0x18000936f  lea     rbp, [rsp-57h]
0x180009374  sub     rsp, 0B0h
0x18000937b  mov     rax, cs:__security_cookie
0x180009382  xor     rax, rsp
0x180009385  mov     [rbp+57h+var_10], rax
0x180009389  mov     rdi, rdx
0x18000938c  mov     rbx, rcx
0x18000938f  mov     [rbp+57h+var_60], rcx
0x180009393  lea     rcx, [rbp+57h+var_30]
0x180009397  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x18000939c  nop
0x18000939d  mov     rdx, rax; struct std::filesystem::path *
0x1800093a0  lea     rcx, [rbp+57h+var_90]; this
0x1800093a4  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)
0x1800093a9  nop
0x1800093aa  lea     rcx, [rbp+57h+var_30]
0x1800093ae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800093b3  cmp     [rbp+57h+var_70], 0
0x1800093b7  jz      short loc_180009407
0x1800093b9  xorps   xmm0, xmm0
0x1800093bc  movups  xmmword ptr [rbx], xmm0
0x1800093bf  movzx   eax, [rbp+57h+var_90]
0x1800093c3  mov     [rbx], ax
0x1800093c6  movsd   xmm0, [rbp+57h+var_8E]
0x1800093cb  movsd   qword ptr [rbx+2], xmm0
0x1800093d0  mov     eax, [rbp+57h+var_86]
0x1800093d3  mov     [rbx+0Ah], eax
0x1800093d6  movzx   eax, [rbp+57h+var_82]
0x1800093da  mov     [rbx+0Eh], ax
0x1800093de  mov     rcx, qword ptr [rbp+57h+var_80]
0x1800093e2  mov     [rbx+10h], rcx
0x1800093e6  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x1800093ea  mov     [rbx+18h], rcx
0x1800093ee  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800093f6  movdqu  [rbp+57h+var_80], xmm0
0x1800093fb  xor     ecx, ecx
0x1800093fd  mov     [rbp+57h+var_90], cx
0x180009401  mov     byte ptr [rbx+20h], 1
0x180009405  jmp     short loc_180009436
0x180009407  mov     rdx, rdi
0x18000940a  lea     rcx, [rbp+57h+var_58]
0x18000940e  call    ?GetHostArchFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@@Z; uus::Utility::GetHostArchFolder(std::filesystem::path const &)
0x180009413  nop
0x180009414  mov     rdx, rax
0x180009417  mov     rcx, rbx
0x18000941a  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEBG@Z; uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,ushort const *)
0x18000941f  nop
0x180009420  cmp     [rbp+57h+var_38], 0
0x180009424  jz      short loc_180009430
0x180009426  lea     rcx, [rbp+57h+var_58]
0x18000942a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000942f  nop
0x180009430  cmp     [rbp+57h+var_70], 0
0x180009434  jz      short loc_18000943F
0x180009436  lea     rcx, [rbp+57h+var_90]
0x18000943a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000943f  mov     rax, rbx
0x180009442  mov     rcx, [rbp+57h+var_10]
0x180009446  xor     rcx, rsp; StackCookie
0x180009449  call    __security_check_cookie
0x18000944e  lea     r11, [rsp+0B0h+var_s0]
0x180009456  mov     rbx, [r11+20h]
0x18000945a  mov     rdi, [r11+28h]
0x18000945e  mov     rsp, r11
0x180009461  pop     rbp
0x180009462  retn
```
