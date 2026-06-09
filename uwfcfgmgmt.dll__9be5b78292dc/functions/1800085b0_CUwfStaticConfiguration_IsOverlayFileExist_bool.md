# CUwfStaticConfiguration::IsOverlayFileExist(bool *)

- ea: `0x1800085b0`
- end: `0x180008666`
- name: `?IsOverlayFileExist@CUwfStaticConfiguration@@QEAAJPEA_N@Z`
- size: `182`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1800169c4`

## callees

- `0x180007ad0`
- `0x1800085b0`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180008630`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008630`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180008639`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180008639`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180008619`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180008619`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::IsOverlayFileExist(CUwfStaticConfiguration *this, bool *a2)
{
  __int64 FirstFileW; // rdi
  int OverlayFileName; // ebx
  LPCWSTR lpFileName; // [rsp+20h] [rbp-278h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-268h] BYREF

  FirstFileW = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  lpFileName = 0;
  *a2 = 0;
  OverlayFileName = CUwfStaticConfiguration::GetOverlayFileName(this, (unsigned __int16 **)&lpFileName);
  if ( OverlayFileName >= 0 )
  {
    FirstFileW = (__int64)FindFirstFileW(lpFileName, &FindFileData);
    if ( FirstFileW != -1 )
      *a2 = 1;
  }
  operator delete[]((void *)lpFileName);
  FindClose((HANDLE)FirstFileW);
  return (unsigned int)OverlayFileName;
}

```

## disassembly

```asm
0x1800085b0  mov     [rsp+arg_10], rbx
0x1800085b5  mov     [rsp+arg_18], rsi
0x1800085ba  push    rdi
0x1800085bb  sub     rsp, 290h
0x1800085c2  mov     rax, cs:__security_cookie
0x1800085c9  xor     rax, rsp
0x1800085cc  mov     [rsp+298h+var_18], rax
0x1800085d4  mov     rsi, rdx
0x1800085d7  mov     rbx, rcx
0x1800085da  xor     edx, edx; Val
0x1800085dc  lea     rcx, [rsp+298h+FindFileData]; void *
0x1800085e1  mov     r8d, 250h; Size
0x1800085e7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800085eb  call    memset_0
0x1800085f0  lea     rdx, [rsp+298h+lpFileName]; unsigned __int16 **
0x1800085f5  mov     [rsp+298h+lpFileName], 0
0x1800085fe  mov     rcx, rbx; this
0x180008601  mov     byte ptr [rsi], 0
0x180008604  call    ?GetOverlayFileName@CUwfStaticConfiguration@@QEAAJPEAPEAG@Z; CUwfStaticConfiguration::GetOverlayFileName(ushort * *)
0x180008609  mov     ebx, eax
0x18000860b  test    eax, eax
0x18000860d  js      short loc_18000862B
0x18000860f  mov     rcx, [rsp+298h+lpFileName]; lpFileName
0x180008614  lea     rdx, [rsp+298h+FindFileData]; lpFindFileData
0x180008619  call    cs:__imp_FindFirstFileW
0x18000861f  mov     rdi, rax
0x180008622  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008626  jz      short loc_18000862B
0x180008628  mov     byte ptr [rsi], 1
0x18000862b  mov     rcx, [rsp+298h+lpFileName]
0x180008630  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008636  mov     rcx, rdi; hFindFile
0x180008639  call    cs:__imp_FindClose
0x18000863f  mov     eax, ebx
0x180008641  mov     rcx, [rsp+298h+var_18]
0x180008649  xor     rcx, rsp; StackCookie
0x18000864c  call    __security_check_cookie
0x180008651  lea     r11, [rsp+298h+var_8]
0x180008659  mov     rbx, [r11+20h]
0x18000865d  mov     rsi, [r11+28h]
0x180008661  mov     rsp, r11
0x180008664  pop     rdi
0x180008665  retn
```
