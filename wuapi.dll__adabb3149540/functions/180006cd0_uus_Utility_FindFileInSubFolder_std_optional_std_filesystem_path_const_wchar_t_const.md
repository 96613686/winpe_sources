# uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,wchar_t const *)

- ea: `0x180006cd0`
- end: `0x180006d8f`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEB_W@Z`
- size: `191`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006f90`

## callees

- `0x180006cd0`
- `0x180006d98`
- `0x1800085e8`

## pseudocode

```c
__int64 __fastcall uus::Utility::FindFileInSubFolder(__int64 a1, struct std::filesystem::path *a2)
{
  std::filesystem::path *FileInSubFolder; // rax
  char v4; // bl
  _BYTE v6[32]; // [rsp+28h] [rbp-60h] BYREF
  char v7; // [rsp+48h] [rbp-40h]
  _BYTE v8[48]; // [rsp+50h] [rbp-38h] BYREF

  if ( *((_BYTE *)a2 + 32) )
  {
    FileInSubFolder = uus::Utility::FindFileInSubFolder((std::filesystem::path *)v8, a2);
    v4 = 5;
  }
  else
  {
    v7 = 0;
    FileInSubFolder = (std::filesystem::path *)v6;
    v4 = 6;
  }
  *(_BYTE *)(a1 + 32) = 0;
  if ( *((_BYTE *)FileInSubFolder + 32) )
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_OWORD *)a1 = *(_OWORD *)FileInSubFolder;
    *(_OWORD *)(a1 + 16) = *((_OWORD *)FileInSubFolder + 1);
    *((_QWORD *)FileInSubFolder + 2) = 0;
    *((_QWORD *)FileInSubFolder + 3) = 7;
    *(_WORD *)FileInSubFolder = 0;
    *(_BYTE *)(a1 + 32) = 1;
  }
  if ( (v4 & 2) != 0 )
  {
    v4 &= ~2u;
    if ( v7 )
      std::wstring::~wstring(v6);
  }
  if ( (v4 & 1) != 0 && v8[32] )
    std::wstring::~wstring(v8);
  return a1;
}

```

## disassembly

```asm
0x180006cd0  mov     [rsp+arg_0], rbx
0x180006cd5  mov     [rsp+arg_8], rsi
0x180006cda  push    rdi
0x180006cdb  sub     rsp, 80h
0x180006ce2  xor     esi, esi
0x180006ce4  mov     rdi, rcx
0x180006ce7  mov     [rsp+88h+var_68], esi
0x180006ceb  cmp     [rdx+20h], sil
0x180006cef  jz      short loc_180006D00
0x180006cf1  lea     rcx, [rsp+88h+var_38]; this
0x180006cf6  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEB_W@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,wchar_t const *)
0x180006cfb  lea     ebx, [rsi+5]
0x180006cfe  jmp     short loc_180006D0F
0x180006d00  mov     [rsp+88h+var_40], sil
0x180006d05  lea     rax, [rsp+88h+var_60]
0x180006d0a  mov     ebx, 6
0x180006d0f  mov     [rdi+20h], sil
0x180006d13  cmp     [rax+20h], sil
0x180006d17  jz      short loc_180006D48
0x180006d19  xorps   xmm0, xmm0
0x180006d1c  movups  xmmword ptr [rdi], xmm0
0x180006d1f  mov     [rdi+10h], rsi
0x180006d23  mov     [rdi+18h], rsi
0x180006d27  movups  xmm0, xmmword ptr [rax]
0x180006d2a  movups  xmmword ptr [rdi], xmm0
0x180006d2d  movups  xmm1, xmmword ptr [rax+10h]
0x180006d31  movups  xmmword ptr [rdi+10h], xmm1
0x180006d35  mov     [rax+10h], rsi
0x180006d39  mov     qword ptr [rax+18h], 7
0x180006d41  mov     [rax], si
0x180006d44  mov     byte ptr [rdi+20h], 1
0x180006d48  test    bl, 2
0x180006d4b  jz      short loc_180006D61
0x180006d4d  and     ebx, 0FFFFFFFDh
0x180006d50  cmp     [rsp+88h+var_40], sil
0x180006d55  jz      short loc_180006D61
0x180006d57  lea     rcx, [rsp+88h+var_60]
0x180006d5c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006d61  test    bl, 1
0x180006d64  jz      short loc_180006D77
0x180006d66  cmp     [rsp+88h+var_18], sil
0x180006d6b  jz      short loc_180006D77
0x180006d6d  lea     rcx, [rsp+88h+var_38]
0x180006d72  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180006d77  lea     r11, [rsp+88h+var_8]
0x180006d7f  mov     rax, rdi
0x180006d82  mov     rbx, [r11+10h]
0x180006d86  mov     rsi, [r11+18h]
0x180006d8a  mov     rsp, r11
0x180006d8d  pop     rdi
0x180006d8e  retn
```
