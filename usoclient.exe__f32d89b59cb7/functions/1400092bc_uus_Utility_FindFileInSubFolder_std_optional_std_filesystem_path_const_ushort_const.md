# uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,ushort const *)

- ea: `0x1400092bc`
- end: `0x140009387`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEBG@Z`
- size: `203`
- prototype: `__int64 __fastcall(__int64, struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400091b4`

## callees

- `0x1400087e4`
- `0x1400092bc`
- `0x140009390`

## pseudocode

```c
__int64 __fastcall uus::Utility::FindFileInSubFolder(__int64 a1, struct std::filesystem::path *a2)
{
  char **FileInSubFolder; // rcx
  char v4; // bl
  char *v6[4]; // [rsp+28h] [rbp-60h] BYREF
  char v7; // [rsp+48h] [rbp-40h]
  char *v8[4]; // [rsp+50h] [rbp-38h] BYREF
  char v9; // [rsp+70h] [rbp-18h]

  if ( *((_BYTE *)a2 + 32) )
  {
    FileInSubFolder = (char **)uus::Utility::FindFileInSubFolder((std::filesystem::path *)v8, a2);
    v4 = 5;
  }
  else
  {
    v7 = 0;
    FileInSubFolder = v6;
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
    FileInSubFolder[2] = 0;
    FileInSubFolder[3] = (char *)7;
    *(_WORD *)FileInSubFolder = 0;
    *(_BYTE *)(a1 + 32) = 1;
  }
  if ( (v4 & 2) != 0 )
  {
    v4 &= ~2u;
    if ( v7 )
      std::wstring::~wstring(v6);
  }
  if ( (v4 & 1) != 0 && v9 )
    std::wstring::~wstring(v8);
  return a1;
}

```

## disassembly

```asm
0x1400092bc  mov     [rsp+arg_0], rbx
0x1400092c1  push    rdi
0x1400092c2  sub     rsp, 80h
0x1400092c9  cmp     byte ptr [rdx+20h], 0
0x1400092cd  mov     rdi, rcx
0x1400092d0  mov     [rsp+88h+var_68], 0
0x1400092d8  jz      short loc_1400092EE
0x1400092da  lea     rcx, [rsp+88h+var_38]; this
0x1400092df  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)
0x1400092e4  mov     rcx, rax
0x1400092e7  mov     ebx, 5
0x1400092ec  jmp     short loc_1400092FD
0x1400092ee  mov     [rsp+88h+var_40], 0
0x1400092f3  lea     rcx, [rsp+88h+var_60]
0x1400092f8  mov     ebx, 6
0x1400092fd  mov     byte ptr [rdi+20h], 0
0x140009301  cmp     byte ptr [rcx+20h], 0
0x140009305  jz      short loc_140009344
0x140009307  xorps   xmm0, xmm0
0x14000930a  xor     eax, eax
0x14000930c  movups  xmmword ptr [rdi], xmm0
0x14000930f  mov     qword ptr [rdi+10h], 0
0x140009317  mov     qword ptr [rdi+18h], 0
0x14000931f  movups  xmm0, xmmword ptr [rcx]
0x140009322  movups  xmmword ptr [rdi], xmm0
0x140009325  movups  xmm1, xmmword ptr [rcx+10h]
0x140009329  movups  xmmword ptr [rdi+10h], xmm1
0x14000932d  mov     qword ptr [rcx+10h], 0
0x140009335  mov     qword ptr [rcx+18h], 7
0x14000933d  mov     [rcx], ax
0x140009340  mov     byte ptr [rdi+20h], 1
0x140009344  test    bl, 2
0x140009347  jz      short loc_14000935D
0x140009349  and     ebx, 0FFFFFFFDh
0x14000934c  cmp     [rsp+88h+var_40], 0
0x140009351  jz      short loc_14000935D
0x140009353  lea     rcx, [rsp+88h+var_60]
0x140009358  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000935d  test    bl, 1
0x140009360  jz      short loc_140009373
0x140009362  cmp     [rsp+88h+var_18], 0
0x140009367  jz      short loc_140009373
0x140009369  lea     rcx, [rsp+88h+var_38]
0x14000936e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140009373  mov     rbx, [rsp+88h+arg_0]
0x14000937b  mov     rax, rdi
0x14000937e  add     rsp, 80h
0x140009385  pop     rdi
0x140009386  retn
```
