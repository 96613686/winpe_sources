# ElValidateHr_3

- ea: `0x1800077f8`
- end: `0x180007853`
- name: `ElValidateHr_3`
- size: `91`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180007720`
- `0x180007aa0`
- `0x180007c30`

## callees

- `0x180003130`
- `0x1800077f8`
- `0x18000785c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000781b`
- `KERNEL32!GetLastError` at `0x18000781b`
- `KERNEL32!SetLastError` at `0x180007839`
- `KERNEL32!SetLastError` at `0x180007839`

## pseudocode

```c
__int64 __fastcall ElValidateHr_3(__int64 a1)
{
  int v1; // ebx
  DWORD LastError; // edi

  v1 = a1;
  ElValidateHrLite(a1, &word_180013F66, "base\\eco\\wds\\wdsimage\\src\\enumimagegroups.cpp");
  if ( v1 < 0 )
  {
    LastError = GetLastError();
    if ( (g_uErrLibFlags & 1) != 0 )
      ElTraceErrorInfo();
    SetLastError(LastError);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800077f8  mov     [rsp+arg_0], rbx
0x1800077fd  push    rdi
0x1800077fe  sub     rsp, 20h
0x180007802  lea     r8, aBaseEcoWdsWdsi_3; "base\\eco\\wds\\wdsimage\\src\\enumimag"...
0x180007809  mov     ebx, ecx
0x18000780b  lea     rdx, word_180013F66
0x180007812  call    ElValidateHrLite
0x180007817  test    ebx, ebx
0x180007819  jns     short loc_180007845
0x18000781b  call    cs:__imp_GetLastError
0x180007822  nop     dword ptr [rax+rax+00h]
0x180007827  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18000782e  mov     edi, eax
0x180007830  jz      short loc_180007837
0x180007832  call    ElTraceErrorInfo
0x180007837  mov     ecx, edi; dwErrCode
0x180007839  call    cs:__imp_SetLastError
0x180007840  nop     dword ptr [rax+rax+00h]
0x180007845  mov     eax, ebx
0x180007847  mov     rbx, [rsp+28h+arg_0]
0x18000784c  add     rsp, 20h
0x180007850  pop     rdi
0x180007851  retn
```
