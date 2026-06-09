# ElValidateHr_4

- ea: `0x1800086e4`
- end: `0x18000873f`
- name: `ElValidateHr_4`
- size: `91`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180007d60`
- `0x180007ec8`
- `0x180007fd4`
- `0x1800081b8`
- `0x1800083b4`
- `0x18000844c`
- `0x180008820`
- `0x180008950`
- `0x180008a10`

## callees

- `0x180003130`
- `0x18000785c`
- `0x1800086e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008707`
- `KERNEL32!GetLastError` at `0x180008707`
- `KERNEL32!SetLastError` at `0x180008725`
- `KERNEL32!SetLastError` at `0x180008725`

## pseudocode

```c
__int64 __fastcall ElValidateHr_4(__int64 a1)
{
  int v1; // ebx
  DWORD LastError; // edi

  v1 = a1;
  ElValidateHrLite(a1, &word_180013F66, "base\\eco\\wds\\wdsimage\\src\\enumimages.cpp");
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
0x1800086e4  mov     [rsp+arg_0], rbx
0x1800086e9  push    rdi
0x1800086ea  sub     rsp, 20h
0x1800086ee  lea     r8, aBaseEcoWdsWdsi_6; "base\\eco\\wds\\wdsimage\\src\\enumimag"...
0x1800086f5  mov     ebx, ecx
0x1800086f7  lea     rdx, word_180013F66
0x1800086fe  call    ElValidateHrLite
0x180008703  test    ebx, ebx
0x180008705  jns     short loc_180008731
0x180008707  call    cs:__imp_GetLastError
0x18000870e  nop     dword ptr [rax+rax+00h]
0x180008713  test    cs:?g_uErrLibFlags@@3KA, 1; ulong g_uErrLibFlags
0x18000871a  mov     edi, eax
0x18000871c  jz      short loc_180008723
0x18000871e  call    ElTraceErrorInfo
0x180008723  mov     ecx, edi; dwErrCode
0x180008725  call    cs:__imp_SetLastError
0x18000872c  nop     dword ptr [rax+rax+00h]
0x180008731  mov     eax, ebx
0x180008733  mov     rbx, [rsp+28h+arg_0]
0x180008738  add     rsp, 20h
0x18000873c  pop     rdi
0x18000873d  retn
```
