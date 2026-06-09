# uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,wchar_t const *)

- ea: `0x1800082c0`
- end: `0x18000837f`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEB_W@Z`
- size: `191`
- prototype: `__int64 __fastcall(__int64, struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008848`

## callees

- `0x180008148`
- `0x1800082c0`
- `0x18000a98c`

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
0x1800082c0  mov     [rsp+arg_0], rbx
0x1800082c5  mov     [rsp+arg_8], rsi
0x1800082ca  push    rdi
0x1800082cb  sub     rsp, 80h
0x1800082d2  xor     esi, esi
0x1800082d4  mov     rdi, rcx
0x1800082d7  mov     [rsp+88h+var_68], esi
0x1800082db  cmp     [rdx+20h], sil
0x1800082df  jz      short loc_1800082F0
0x1800082e1  lea     rcx, [rsp+88h+var_38]; this
0x1800082e6  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEB_W@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,wchar_t const *)
0x1800082eb  lea     ebx, [rsi+5]
0x1800082ee  jmp     short loc_1800082FF
0x1800082f0  mov     [rsp+88h+var_40], sil
0x1800082f5  lea     rax, [rsp+88h+var_60]
0x1800082fa  mov     ebx, 6
0x1800082ff  mov     [rdi+20h], sil
0x180008303  cmp     [rax+20h], sil
0x180008307  jz      short loc_180008338
0x180008309  xorps   xmm0, xmm0
0x18000830c  movups  xmmword ptr [rdi], xmm0
0x18000830f  mov     [rdi+10h], rsi
0x180008313  mov     [rdi+18h], rsi
0x180008317  movups  xmm0, xmmword ptr [rax]
0x18000831a  movups  xmmword ptr [rdi], xmm0
0x18000831d  movups  xmm1, xmmword ptr [rax+10h]
0x180008321  movups  xmmword ptr [rdi+10h], xmm1
0x180008325  mov     [rax+10h], rsi
0x180008329  mov     qword ptr [rax+18h], 7
0x180008331  mov     [rax], si
0x180008334  mov     byte ptr [rdi+20h], 1
0x180008338  test    bl, 2
0x18000833b  jz      short loc_180008351
0x18000833d  and     ebx, 0FFFFFFFDh
0x180008340  cmp     [rsp+88h+var_40], sil
0x180008345  jz      short loc_180008351
0x180008347  lea     rcx, [rsp+88h+var_60]
0x18000834c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008351  test    bl, 1
0x180008354  jz      short loc_180008367
0x180008356  cmp     [rsp+88h+var_18], sil
0x18000835b  jz      short loc_180008367
0x18000835d  lea     rcx, [rsp+88h+var_38]
0x180008362  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008367  lea     r11, [rsp+88h+var_8]
0x18000836f  mov     rax, rdi
0x180008372  mov     rbx, [r11+10h]
0x180008376  mov     rsi, [r11+18h]
0x18000837a  mov     rsp, r11
0x18000837d  pop     rdi
0x18000837e  retn
```
