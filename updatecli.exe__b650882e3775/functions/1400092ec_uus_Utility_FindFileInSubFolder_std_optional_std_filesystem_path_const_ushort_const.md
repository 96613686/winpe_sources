# uus::Utility::FindFileInSubFolder(std::optional<std::filesystem::path> const &,ushort const *)

- ea: `0x1400092ec`
- end: `0x1400093b7`
- name: `?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBV34@PEBG@Z`
- size: `203`
- prototype: `__int64 __fastcall(__int64, struct std::filesystem::path *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400091e4`

## callees

- `0x1400087c4`
- `0x1400092ec`
- `0x1400093c0`

## pseudocode

```c
__int64 __fastcall uus::Utility::FindFileInSubFolder(__int64 a1, struct std::filesystem::path *a2)
{
  std::filesystem::path *FileInSubFolder; // rcx
  char v4; // bl
  char *v6[4]; // [rsp+28h] [rbp-60h] BYREF
  char v7; // [rsp+48h] [rbp-40h]
  char *v8[4]; // [rsp+50h] [rbp-38h] BYREF
  char v9; // [rsp+70h] [rbp-18h]

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
  if ( (v4 & 1) != 0 && v9 )
    std::wstring::~wstring(v8);
  return a1;
}

```

## disassembly

```asm
0x1400092ec  mov     [rsp+arg_0], rbx
0x1400092f1  push    rdi
0x1400092f2  sub     rsp, 80h
0x1400092f9  cmp     byte ptr [rdx+20h], 0
0x1400092fd  mov     rdi, rcx
0x140009300  mov     [rsp+88h+var_68], 0
0x140009308  jz      short loc_14000931E
0x14000930a  lea     rcx, [rsp+88h+var_38]; this
0x14000930f  call    ?FindFileInSubFolder@Utility@uus@@SA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@4@PEBG@Z; uus::Utility::FindFileInSubFolder(std::filesystem::path const &,ushort const *)
0x140009314  mov     rcx, rax
0x140009317  mov     ebx, 5
0x14000931c  jmp     short loc_14000932D
0x14000931e  mov     [rsp+88h+var_40], 0
0x140009323  lea     rcx, [rsp+88h+var_60]
0x140009328  mov     ebx, 6
0x14000932d  mov     byte ptr [rdi+20h], 0
0x140009331  cmp     byte ptr [rcx+20h], 0
0x140009335  jz      short loc_140009374
0x140009337  xorps   xmm0, xmm0
0x14000933a  xor     eax, eax
0x14000933c  movups  xmmword ptr [rdi], xmm0
0x14000933f  mov     qword ptr [rdi+10h], 0
0x140009347  mov     qword ptr [rdi+18h], 0
0x14000934f  movups  xmm0, xmmword ptr [rcx]
0x140009352  movups  xmmword ptr [rdi], xmm0
0x140009355  movups  xmm1, xmmword ptr [rcx+10h]
0x140009359  movups  xmmword ptr [rdi+10h], xmm1
0x14000935d  mov     qword ptr [rcx+10h], 0
0x140009365  mov     qword ptr [rcx+18h], 7
0x14000936d  mov     [rcx], ax
0x140009370  mov     byte ptr [rdi+20h], 1
0x140009374  test    bl, 2
0x140009377  jz      short loc_14000938D
0x140009379  and     ebx, 0FFFFFFFDh
0x14000937c  cmp     [rsp+88h+var_40], 0
0x140009381  jz      short loc_14000938D
0x140009383  lea     rcx, [rsp+88h+var_60]
0x140009388  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000938d  test    bl, 1
0x140009390  jz      short loc_1400093A3
0x140009392  cmp     [rsp+88h+var_18], 0
0x140009397  jz      short loc_1400093A3
0x140009399  lea     rcx, [rsp+88h+var_38]
0x14000939e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400093a3  mov     rbx, [rsp+88h+arg_0]
0x1400093ab  mov     rax, rdi
0x1400093ae  add     rsp, 80h
0x1400093b5  pop     rdi
0x1400093b6  retn
```
