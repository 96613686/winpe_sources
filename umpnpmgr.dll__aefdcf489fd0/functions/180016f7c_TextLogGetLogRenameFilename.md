# TextLogGetLogRenameFilename

- ea: `0x180016f7c`
- end: `0x18001704f`
- name: `TextLogGetLogRenameFilename`
- size: `211`
- prototype: `_BOOL8 __fastcall(__int64, void *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18001725c`

## callees

- `0x18000c650`
- `0x18000f210`
- `0x1800101d8`
- `0x180016f7c`
- `0x18001812c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017032`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017032`

## string_xrefs

- `0x180016fc5`: `SYSTEM\Setup\SetupapiLogRename`

## pseudocode

```c
_BOOL8 __fastcall TextLogGetLogRenameFilename(__int64 a1, void *a2, int a3)
{
  unsigned __int16 *FileTitle; // rsi
  DWORD v5; // ebx
  HANDLE KeyHandle[3]; // [rsp+30h] [rbp-18h] BYREF
  int v8; // [rsp+60h] [rbp+18h] BYREF
  __int64 v9; // [rsp+68h] [rbp+20h] BYREF

  v8 = a3;
  FileTitle = *(unsigned __int16 **)(a1 + 16);
  KeyHandle[0] = 0;
  v8 = 0;
  if ( !TextLogOffline )
    FileTitle = pSetupGetFileTitle(FileTitle);
  v5 = pSetupOpenKeyEx((void *)0xFFFFFFFF80000002LL, L"SYSTEM\\Setup\\SetupapiLogRename", 1u, KeyHandle);
  if ( !v5 )
  {
    LODWORD(v9) = 520;
    v5 = pSetupQueryValue(KeyHandle[0], FileTitle, &v8, a2, (unsigned int *)&v9);
    if ( !v5 && (v8 != 1 || (unsigned int)v9 <= 2) )
      v5 = 13;
  }
  if ( KeyHandle[0] )
    pSetupCloseKey((unsigned int)KeyHandle[0]);
  SetLastError(v5);
  return v5 == 0;
}

```

## disassembly

```asm
0x180016f7c  mov     rax, rsp
0x180016f7f  mov     [rax+8], rbx
0x180016f83  mov     [rax+10h], rbp
0x180016f87  mov     [rax+18h], r8d
0x180016f8b  push    rsi
0x180016f8c  sub     rsp, 40h
0x180016f90  cmp     cs:TextLogOffline, 0
0x180016f97  mov     rbp, rdx
0x180016f9a  mov     rsi, [rcx+10h]
0x180016f9e  mov     qword ptr [rax-18h], 0
0x180016fa6  mov     dword ptr [rax+18h], 0
0x180016fad  jnz     short loc_180016FBA
0x180016faf  mov     rcx, rsi
0x180016fb2  call    pSetupGetFileTitle
0x180016fb7  mov     rsi, rax
0x180016fba  lea     r9, [rsp+48h+KeyHandle]
0x180016fbf  mov     r8d, 1
0x180016fc5  lea     rdx, aSystemSetupSet; "SYSTEM\\Setup\\SetupapiLogRename"
0x180016fcc  mov     rcx, 0FFFFFFFF80000002h
0x180016fd3  call    pSetupOpenKeyEx
0x180016fd8  mov     ebx, eax
0x180016fda  test    eax, eax
0x180016fdc  jnz     short loc_18001701E
0x180016fde  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x180016fe3  lea     rax, [rsp+48h+arg_18]
0x180016fe8  mov     r9, rbp
0x180016feb  mov     [rsp+48h+var_28], rax; __int64
0x180016ff0  lea     r8, [rsp+48h+arg_10]
0x180016ff5  mov     dword ptr [rsp+48h+arg_18], 208h
0x180016ffd  mov     rdx, rsi; SourceString
0x180017000  call    pSetupQueryValue
0x180017005  mov     ebx, eax
0x180017007  test    eax, eax
0x180017009  jnz     short loc_18001701E
0x18001700b  cmp     [rsp+48h+arg_10], 1
0x180017010  jnz     short loc_180017019
0x180017012  cmp     dword ptr [rsp+48h+arg_18], 2
0x180017017  ja      short loc_18001701E
0x180017019  mov     ebx, 0Dh
0x18001701e  cmp     [rsp+48h+KeyHandle], 0
0x180017024  jz      short loc_180017030
0x180017026  mov     rcx, [rsp+48h+KeyHandle]
0x18001702b  call    pSetupCloseKey
0x180017030  mov     ecx, ebx; dwErrCode
0x180017032  call    cs:__imp_SetLastError
0x180017038  mov     rbp, [rsp+48h+arg_8]
0x18001703d  xor     eax, eax
0x18001703f  test    ebx, ebx
0x180017041  mov     rbx, [rsp+48h+arg_0]
0x180017046  setz    al
0x180017049  add     rsp, 40h
0x18001704d  pop     rsi
0x18001704e  retn
```
