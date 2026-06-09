# uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,ushort const *)

- ea: `0x18000946c`
- end: `0x180009537`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEBG@Z`
- size: `203`
- prototype: `__int64 __fastcall(__int64, struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009364`

## callees

- `0x180008b08`
- `0x18000946c`
- `0x180009540`

## pseudocode

```c
__int64 __fastcall uus::Utility::FindFileInSubFolder(__int64 a1, struct std::filesystem::path *a2)
{
  std::filesystem::path *FileInSubFolder; // rcx
  char v4; // bl
  _BYTE v6[32]; // [rsp+28h] [rbp-60h] BYREF
  char v7; // [rsp+48h] [rbp-40h]
  _BYTE v8[56]; // [rsp+50h] [rbp-38h] BYREF

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
0x18000946c  mov     [rsp+arg_0], rbx
0x180009471  push    rdi
0x180009472  sub     rsp, 80h
0x180009479  cmp     byte ptr [rdx+20h], 0
0x18000947d  mov     rdi, rcx
0x180009480  mov     [rsp+88h+var_68], 0
0x180009488  jz      short loc_18000949E
0x18000948a  lea     rcx, [rsp+88h+var_38]; this
0x18000948f  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)
0x180009494  mov     rcx, rax
0x180009497  mov     ebx, 5
0x18000949c  jmp     short loc_1800094AD
0x18000949e  mov     [rsp+88h+var_40], 0
0x1800094a3  lea     rcx, [rsp+88h+var_60]
0x1800094a8  mov     ebx, 6
0x1800094ad  mov     byte ptr [rdi+20h], 0
0x1800094b1  cmp     byte ptr [rcx+20h], 0
0x1800094b5  jz      short loc_1800094F4
0x1800094b7  xorps   xmm0, xmm0
0x1800094ba  xor     eax, eax
0x1800094bc  movups  xmmword ptr [rdi], xmm0
0x1800094bf  mov     qword ptr [rdi+10h], 0
0x1800094c7  mov     qword ptr [rdi+18h], 0
0x1800094cf  movups  xmm0, xmmword ptr [rcx]
0x1800094d2  movups  xmmword ptr [rdi], xmm0
0x1800094d5  movups  xmm1, xmmword ptr [rcx+10h]
0x1800094d9  movups  xmmword ptr [rdi+10h], xmm1
0x1800094dd  mov     qword ptr [rcx+10h], 0
0x1800094e5  mov     qword ptr [rcx+18h], 7
0x1800094ed  mov     [rcx], ax
0x1800094f0  mov     byte ptr [rdi+20h], 1
0x1800094f4  test    bl, 2
0x1800094f7  jz      short loc_18000950D
0x1800094f9  and     ebx, 0FFFFFFFDh
0x1800094fc  cmp     [rsp+88h+var_40], 0
0x180009501  jz      short loc_18000950D
0x180009503  lea     rcx, [rsp+88h+var_60]
0x180009508  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000950d  test    bl, 1
0x180009510  jz      short loc_180009523
0x180009512  cmp     [rsp+88h+var_18], 0
0x180009517  jz      short loc_180009523
0x180009519  lea     rcx, [rsp+88h+var_38]
0x18000951e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009523  mov     rbx, [rsp+88h+arg_0]
0x18000952b  mov     rax, rdi
0x18000952e  add     rsp, 80h
0x180009535  pop     rdi
0x180009536  retn
```
