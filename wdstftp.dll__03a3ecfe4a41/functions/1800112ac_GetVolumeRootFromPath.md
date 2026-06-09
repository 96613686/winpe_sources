# GetVolumeRootFromPath

- ea: `0x1800112ac`
- end: `0x1800114ad`
- name: `GetVolumeRootFromPath`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180020a08`

## callees

- `0x180010efc`
- `0x1800112ac`
- `0x1800219c4`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180011309`
- `msvcrt!wcsrchr` at `0x180011434`
- `msvcrt!wcsrchr` at `0x180011309`
- `msvcrt!wcsrchr` at `0x180011434`
- `KERNEL32!GetVolumeInformationW` at `0x18001134a`
- `KERNEL32!GetVolumeInformationW` at `0x18001134a`
- `KERNEL32!HeapFree` at `0x180011480`
- `KERNEL32!HeapFree` at `0x180011480`
- `KERNEL32!GetLastError` at `0x18001135e`
- `KERNEL32!GetLastError` at `0x18001137b`
- `KERNEL32!GetLastError` at `0x180011394`
- `KERNEL32!GetLastError` at `0x1800113b1`
- `KERNEL32!GetLastError` at `0x18001135e`
- `KERNEL32!GetLastError` at `0x18001137b`
- `KERNEL32!GetLastError` at `0x180011394`
- `KERNEL32!GetLastError` at `0x1800113b1`
- `KERNEL32!GetProcessHeap` at `0x18001146c`
- `KERNEL32!GetProcessHeap` at `0x18001146c`

## string_xrefs

- `0x1800113da`: `GetVolumeRootFromPath`
- `0x180011414`: `GetVolumeRootFromPath`

## pseudocode

```c
__int64 __fastcall GetVolumeRootFromPath(const WCHAR *a1, WCHAR **a2)
{
  signed int v3; // ebx
  wchar_t *v4; // rsi
  int v5; // ebp
  const wchar_t *v7; // rax
  WCHAR *v8; // rdi
  __int64 v9; // rdx
  signed int v10; // ecx
  signed int v11; // eax
  signed int v12; // eax
  __int64 v13; // rdx
  signed int LastError; // ecx
  signed int v15; // eax
  signed int v16; // eax
  wchar_t *v17; // rax
  HANDLE ProcessHeap; // rax

  v3 = 0;
  v4 = 0;
  v5 = 1;
  if ( !a2 )
    return 2147942487LL;
  v7 = (const wchar_t *)AllocAddPath(a1, 0);
  v8 = (WCHAR *)v7;
  if ( v7 )
  {
    v4 = wcsrchr(v7, 0x5Cu);
    goto LABEL_5;
  }
  LastError = GetLastError();
  v15 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v15 = LastError;
  if ( v15 >= 0 )
  {
    v3 = -2147467259;
  }
  else
  {
    v16 = GetLastError();
    v3 = (unsigned __int16)v16 | 0x80070000;
    if ( v16 <= 0 )
      v3 = v16;
  }
  if ( v3 < 0 )
  {
    UtilReportError((__int64)L"GetVolumeRootFromPath", v13, 0x1EAu, v3);
    return (unsigned int)v3;
  }
LABEL_5:
  while ( v5 )
  {
    v5 = 0;
    if ( !GetVolumeInformationW(v8, 0, 0, 0, 0, 0, 0, 0) )
    {
      v10 = GetLastError();
      v11 = (unsigned __int16)v10 | 0x80070000;
      if ( v10 <= 0 )
        v11 = v10;
      if ( v11 >= 0 )
      {
        v3 = -2147467259;
      }
      else
      {
        v12 = GetLastError();
        v3 = (unsigned __int16)v12 | 0x80070000;
        if ( v12 <= 0 )
          v3 = v12;
      }
    }
    if ( v3 == -2147024752 || (unsigned int)(v3 + 2147024894) <= 1 )
    {
      *v4 = 0;
      v17 = wcsrchr(v8, 0x5Cu);
      v4 = v17;
      if ( v17 )
      {
        v17[1] = 0;
        v3 = 0;
        v5 = 1;
      }
      goto LABEL_30;
    }
    if ( v3 < 0 )
    {
      UtilReportError((__int64)L"GetVolumeRootFromPath", v9, 0x21Cu, v3);
LABEL_30:
      if ( v3 < 0 )
        break;
    }
  }
  if ( v3 >= 0 )
  {
    *a2 = v8;
    v8 = 0;
  }
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800112ac  mov     rax, rsp
0x1800112af  mov     [rax+8], rbx
0x1800112b3  mov     [rax+10h], rbp
0x1800112b7  mov     [rax+18h], rsi
0x1800112bb  mov     [rax+20h], rdi
0x1800112bf  push    r13
0x1800112c1  push    r14
0x1800112c3  push    r15
0x1800112c5  sub     rsp, 40h
0x1800112c9  xor     r15d, r15d
0x1800112cc  mov     r14, rdx
0x1800112cf  mov     ebx, r15d
0x1800112d2  mov     esi, r15d
0x1800112d5  lea     ebp, [r15+1]
0x1800112d9  test    rdx, rdx
0x1800112dc  jnz     short loc_1800112E8
0x1800112de  mov     eax, 80070057h
0x1800112e3  jmp     loc_18001148E
0x1800112e8  xor     edx, edx; STRSAFE_PCNZWCH
0x1800112ea  call    AllocAddPath
0x1800112ef  mov     rdi, rax
0x1800112f2  mov     r13d, 80070000h
0x1800112f8  test    rax, rax
0x1800112fb  jz      loc_180011394
0x180011301  mov     edx, 5Ch ; '\'; Ch
0x180011306  mov     rcx, rax; Str
0x180011309  call    cs:__imp_wcsrchr
0x180011310  nop     dword ptr [rax+rax+00h]
0x180011315  mov     rsi, rax
0x180011318  test    ebp, ebp
0x18001131a  jz      loc_18001145D
0x180011320  mov     ebp, r15d
0x180011323  test    ebx, ebx
0x180011325  js      loc_1800113F6
0x18001132b  mov     [rsp+58h+nFileSystemNameSize], r15d; nFileSystemNameSize
0x180011330  xor     r9d, r9d; lpVolumeSerialNumber
0x180011333  mov     [rsp+58h+lpFileSystemNameBuffer], r15; lpFileSystemNameBuffer
0x180011338  xor     r8d, r8d; nVolumeNameSize
0x18001133b  mov     [rsp+58h+lpFileSystemFlags], r15; lpFileSystemFlags
0x180011340  xor     edx, edx; lpVolumeNameBuffer
0x180011342  mov     rcx, rdi; lpRootPathName
0x180011345  mov     [rsp+58h+lpMaximumComponentLength], r15; lpMaximumComponentLength
0x18001134a  call    cs:__imp_GetVolumeInformationW
0x180011351  nop     dword ptr [rax+rax+00h]
0x180011356  test    eax, eax
0x180011358  jnz     loc_1800113F6
0x18001135e  call    cs:__imp_GetLastError
0x180011365  nop     dword ptr [rax+rax+00h]
0x18001136a  mov     ecx, eax
0x18001136c  movzx   eax, ax
0x18001136f  or      eax, r13d
0x180011372  test    ecx, ecx
0x180011374  cmovle  eax, ecx
0x180011377  test    eax, eax
0x180011379  jns     short loc_1800113F1
0x18001137b  call    cs:__imp_GetLastError
0x180011382  nop     dword ptr [rax+rax+00h]
0x180011387  movzx   ebx, ax
0x18001138a  or      ebx, r13d
0x18001138d  test    eax, eax
0x18001138f  cmovle  ebx, eax
0x180011392  jmp     short loc_1800113F6
0x180011394  call    cs:__imp_GetLastError
0x18001139b  nop     dword ptr [rax+rax+00h]
0x1800113a0  mov     ecx, eax
0x1800113a2  movzx   eax, ax
0x1800113a5  or      eax, r13d
0x1800113a8  test    ecx, ecx
0x1800113aa  cmovle  eax, ecx
0x1800113ad  test    eax, eax
0x1800113af  jns     short loc_1800113CA
0x1800113b1  call    cs:__imp_GetLastError
0x1800113b8  nop     dword ptr [rax+rax+00h]
0x1800113bd  movzx   ebx, ax
0x1800113c0  or      ebx, r13d
0x1800113c3  test    eax, eax
0x1800113c5  cmovle  ebx, eax
0x1800113c8  jmp     short loc_1800113CF
0x1800113ca  mov     ebx, 80004005h
0x1800113cf  test    ebx, ebx
0x1800113d1  jns     loc_180011318
0x1800113d7  mov     r9d, ebx
0x1800113da  lea     rcx, aGetvolumerootf; "GetVolumeRootFromPath"
0x1800113e1  mov     r8d, 1EAh
0x1800113e7  call    UtilReportError
0x1800113ec  jmp     loc_18001148C
0x1800113f1  mov     ebx, 80004005h
0x1800113f6  cmp     ebx, 80070090h
0x1800113fc  jz      short loc_180011428
0x1800113fe  lea     eax, [rbx+7FF8FFFEh]
0x180011404  cmp     eax, 1
0x180011407  jbe     short loc_180011428
0x180011409  test    ebx, ebx
0x18001140b  jns     loc_180011318
0x180011411  mov     r9d, ebx
0x180011414  lea     rcx, aGetvolumerootf; "GetVolumeRootFromPath"
0x18001141b  mov     r8d, 21Ch
0x180011421  call    UtilReportError
0x180011426  jmp     short loc_180011455
0x180011428  mov     edx, 5Ch ; '\'; Ch
0x18001142d  mov     [rsi], r15w
0x180011431  mov     rcx, rdi; Str
0x180011434  call    cs:__imp_wcsrchr
0x18001143b  nop     dword ptr [rax+rax+00h]
0x180011440  mov     rsi, rax
0x180011443  test    rax, rax
0x180011446  jz      short loc_180011455
0x180011448  mov     [rax+2], r15w
0x18001144d  mov     ebx, r15d
0x180011450  mov     ebp, 1
0x180011455  test    ebx, ebx
0x180011457  jns     loc_180011318
0x18001145d  test    ebx, ebx
0x18001145f  js      short loc_180011467
0x180011461  mov     [r14], rdi
0x180011464  mov     rdi, r15
0x180011467  test    rdi, rdi
0x18001146a  jz      short loc_18001148C
0x18001146c  call    cs:__imp_GetProcessHeap
0x180011473  nop     dword ptr [rax+rax+00h]
0x180011478  mov     r8, rdi; lpMem
0x18001147b  xor     edx, edx; dwFlags
0x18001147d  mov     rcx, rax; hHeap
0x180011480  call    cs:__imp_HeapFree
0x180011487  nop     dword ptr [rax+rax+00h]
0x18001148c  mov     eax, ebx
0x18001148e  mov     rbx, [rsp+58h+arg_0]
0x180011493  mov     rbp, [rsp+58h+arg_8]
0x180011498  mov     rsi, [rsp+58h+arg_10]
0x18001149d  mov     rdi, [rsp+58h+arg_18]
0x1800114a2  add     rsp, 40h
0x1800114a6  pop     r15
0x1800114a8  pop     r14
0x1800114aa  pop     r13
0x1800114ac  retn
```
