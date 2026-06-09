# SdpPathExists(ushort const *,int *)

- ea: `0x1800027f8`
- end: `0x1800028c8`
- name: `?SdpPathExists@@YAJPEBGPEAH@Z`
- size: `208`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180005d60`
- `0x18000a86c`

## callees

- `0x1800027f8`
- `0x180026fa0`
- `0x180029882`
- `0x1800298c0`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x180002872`
- `KERNEL32!FindFirstFileW` at `0x180002872`
- `KERNEL32!FindClose` at `0x18000289b`
- `KERNEL32!FindClose` at `0x18000289b`

## string_xrefs

- `0x180002845`: `SdpPathExists`

## pseudocode

```c
__int64 __fastcall SdpPathExists(LPCWSTR lpFileName, int *a2)
{
  int v4; // r8d
  unsigned int v5; // edi
  char *FirstFileW; // rdx
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-268h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !lpFileName )
  {
    v4 = 419;
LABEL_3:
    v5 = -2147024809;
    SdpDebugTrace(1u, L"SdpPathExists", v4, -2147024809);
    return v5;
  }
  if ( !a2 )
  {
    v4 = 420;
    goto LABEL_3;
  }
  v5 = 0;
  FirstFileW = (char *)FindFirstFileW(lpFileName, &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    *a2 = 0;
  }
  else
  {
    *a2 = 1;
    FindClose(FirstFileW);
  }
  return v5;
}

```

## disassembly

```asm
0x1800027f8  mov     [rsp+arg_10], rbx
0x1800027fd  mov     [rsp+arg_18], rsi
0x180002802  push    rdi
0x180002803  sub     rsp, 280h
0x18000280a  mov     rax, cs:__security_cookie
0x180002811  xor     rax, rsp
0x180002814  mov     [rsp+288h+var_18], rax
0x18000281c  mov     rbx, rdx
0x18000281f  mov     rsi, rcx
0x180002822  xor     edx, edx; Val
0x180002824  lea     rcx, [rsp+288h+FindFileData]; void *
0x180002829  mov     r8d, 250h; Size
0x18000282f  call    memset_0
0x180002834  test    rsi, rsi
0x180002837  jnz     short loc_18000285B
0x180002839  mov     r8d, 1A3h; int
0x18000283f  mov     r9d, 80070057h; int
0x180002845  lea     rdx, aSdppathexists; "SdpPathExists"
0x18000284c  mov     ecx, 1; Level
0x180002851  mov     edi, r9d
0x180002854  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180002859  jmp     short loc_1800028A1
0x18000285b  test    rbx, rbx
0x18000285e  jnz     short loc_180002868
0x180002860  mov     r8d, 1A4h
0x180002866  jmp     short loc_18000283F
0x180002868  lea     rdx, [rsp+288h+FindFileData]; lpFindFileData
0x18000286d  mov     rcx, rsi; lpFileName
0x180002870  xor     edi, edi
0x180002872  call    cs:__imp_FindFirstFileW
0x180002878  mov     rdx, rax
0x18000287b  dec     rax
0x18000287e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002882  ja      short loc_18000288C
0x180002884  mov     dword ptr [rbx], 1
0x18000288a  jmp     short loc_180002898
0x18000288c  mov     [rbx], edi
0x18000288e  lea     rcx, [rdx-1]
0x180002892  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180002896  ja      short loc_1800028A1
0x180002898  mov     rcx, rdx; hFindFile
0x18000289b  call    cs:__imp_FindClose
0x1800028a1  mov     eax, edi
0x1800028a3  mov     rcx, [rsp+288h+var_18]
0x1800028ab  xor     rcx, rsp; StackCookie
0x1800028ae  call    __security_check_cookie
0x1800028b3  lea     r11, [rsp+288h+var_8]
0x1800028bb  mov     rbx, [r11+20h]
0x1800028bf  mov     rsi, [r11+28h]
0x1800028c3  mov     rsp, r11
0x1800028c6  pop     rdi
0x1800028c7  retn
```
