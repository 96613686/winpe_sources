# WdiAddFileToInstance

- ea: `0x180009570`
- end: `0x18000978f`
- name: `WdiAddFileToInstance`
- size: `543`
- prototype: `__int64 __fastcall(__int64, const wchar_t *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180002ba0`
- `0x1800072f0`
- `0x180009474`
- `0x180009570`
- `0x18000f1c2`
- `0x18000f1f0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800096ba`
- `msvcrt!wcsrchr` at `0x1800096ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000972c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000972c`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18000971e`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x18000971e`

## pseudocode

```c
__int64 __fastcall WdiAddFileToInstance(__int64 a1, const wchar_t *a2)
{
  unsigned int v4; // ebx
  int v5; // ecx
  int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  int v9; // r8d
  wchar_t *v10; // rax
  const wchar_t *v11; // rax
  signed int LastError; // eax
  WCHAR NewFileName[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(NewFileName, 0, 0x208u);
  if ( !a1 )
  {
    v4 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddFileToInstance",
      1792,
      (int)L"Error = %d",
      87);
    return v4;
  }
  if ( !a2 )
  {
    v4 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiAddFileToInstance",
      1793,
      (int)L"Error = %d",
      87);
    return v4;
  }
  v5 = *(_DWORD *)(a1 + 16);
  if ( v5 )
  {
    if ( v5 != 1 )
    {
      v4 = -2147020579;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
        (int)L"WdiAddFileToInstance",
        1834,
        (int)L"Error = %d",
        221);
      return v4;
    }
    if ( !*(_QWORD *)(a1 + 88) && !*(_QWORD *)(a1 + 96) )
      return (unsigned int)-2147020579;
    _InterlockedOr((volatile signed __int32 *)(a1 + 108), 1u);
    v6 = WdipVerifyDirectory(a1 + 88, a1 + 40, NewFileName, 260);
    v4 = v6;
    if ( v6 < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
        (int)L"WdiAddFileToInstance",
        1814,
        (int)L"Error = %d",
        v6);
      return v4;
    }
  }
  else
  {
    v7 = *(_QWORD *)(a1 + 40);
    if ( !v7 )
    {
      v4 = -2147024809;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
        (int)L"WdiAddFileToInstance",
        1820,
        (int)L"Error = %d",
        87);
      return v4;
    }
    *(_DWORD *)(v7 + 120) |= 8u;
    v8 = WdipVerifyDirectory(*(_QWORD *)(a1 + 40) + 48LL, *(_QWORD *)(a1 + 40) + 64LL, NewFileName, 260);
    v4 = v8;
    if ( v8 < 0 )
    {
      v9 = 1828;
LABEL_28:
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
        (int)L"WdiAddFileToInstance",
        v9,
        (int)L"Error = %d",
        v8);
      return v4;
    }
  }
  v10 = wcsrchr(a2, 0x5Cu);
  if ( v10 )
    v11 = v10 + 1;
  else
    v11 = a2;
  v8 = StringCchPrintfW(NewFileName, 0x104u, L"%s\\%s", NewFileName, v11);
  v4 = v8;
  if ( v8 < 0 )
  {
    v9 = 1852;
    goto LABEL_28;
  }
  if ( CopyFileExW(a2, NewFileName, 0, 0, 0, 0) )
    return 0;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    LOBYTE(v8) = v4;
    v9 = 1859;
    goto LABEL_28;
  }
  return v4;
}

```

## disassembly

```asm
0x180009570  mov     [rsp+arg_10], rbx
0x180009575  push    rdi
0x180009576  sub     rsp, 250h
0x18000957d  mov     rax, cs:__security_cookie
0x180009584  xor     rax, rsp
0x180009587  mov     [rsp+258h+var_18], rax
0x18000958f  mov     rdi, rdx
0x180009592  mov     rbx, rcx
0x180009595  xor     edx, edx; Val
0x180009597  lea     rcx, [rsp+258h+NewFileName]; void *
0x18000959c  mov     r8d, 208h; Size
0x1800095a2  call    memset_0
0x1800095a7  test    rbx, rbx
0x1800095aa  jnz     short loc_1800095C4
0x1800095ac  mov     ebx, 80070057h
0x1800095b1  mov     dword ptr [rsp+258h+pbCancel], 57h ; 'W'
0x1800095b9  mov     r8d, 700h
0x1800095bf  jmp     loc_180009752
0x1800095c4  test    rdi, rdi
0x1800095c7  jnz     short loc_1800095E1
0x1800095c9  mov     ebx, 80070057h
0x1800095ce  mov     dword ptr [rsp+258h+pbCancel], 57h ; 'W'
0x1800095d6  mov     r8d, 701h
0x1800095dc  jmp     loc_180009752
0x1800095e1  mov     ecx, [rbx+10h]
0x1800095e4  test    ecx, ecx
0x1800095e6  jz      short loc_18000965D
0x1800095e8  cmp     ecx, 1
0x1800095eb  jz      short loc_180009605
0x1800095ed  mov     ebx, 800710DDh
0x1800095f2  mov     dword ptr [rsp+258h+pbCancel], 10DDh
0x1800095fa  mov     r8d, 72Ah
0x180009600  jmp     loc_180009752
0x180009605  lea     rcx, [rbx+58h]
0x180009609  mov     rax, [rcx]
0x18000960c  cmp     rax, cs:qword_180011870
0x180009613  jnz     short loc_18000962C
0x180009615  mov     rax, [rcx+8]
0x180009619  cmp     rax, cs:qword_180011878
0x180009620  jnz     short loc_18000962C
0x180009622  mov     ebx, 800710DDh
0x180009627  jmp     loc_18000976C
0x18000962c  lock or dword ptr [rbx+6Ch], 1
0x180009631  lea     rdx, [rbx+28h]
0x180009635  mov     r9d, 104h
0x18000963b  lea     r8, [rsp+258h+NewFileName]
0x180009640  call    WdipVerifyDirectory
0x180009645  mov     ebx, eax
0x180009647  test    eax, eax
0x180009649  jns     short loc_1800096B2
0x18000964b  movzx   ecx, ax
0x18000964e  mov     r8d, 716h
0x180009654  mov     dword ptr [rsp+258h+pbCancel], ecx
0x180009658  jmp     loc_180009752
0x18000965d  mov     rax, [rbx+28h]
0x180009661  test    rax, rax
0x180009664  jnz     short loc_18000967E
0x180009666  mov     ebx, 80070057h
0x18000966b  mov     dword ptr [rsp+258h+pbCancel], 57h ; 'W'
0x180009673  mov     r8d, 71Ch
0x180009679  jmp     loc_180009752
0x18000967e  or      dword ptr [rax+78h], 8
0x180009682  lea     r8, [rsp+258h+NewFileName]
0x180009687  mov     rcx, [rbx+28h]
0x18000968b  mov     r9d, 104h
0x180009691  lea     rdx, [rcx+40h]
0x180009695  add     rcx, 30h ; '0'
0x180009699  call    WdipVerifyDirectory
0x18000969e  mov     ebx, eax
0x1800096a0  test    eax, eax
0x1800096a2  jns     short loc_1800096B2
0x1800096a4  movzx   eax, ax
0x1800096a7  mov     r8d, 724h
0x1800096ad  jmp     loc_18000974E
0x1800096b2  mov     edx, 5Ch ; '\'; Ch
0x1800096b7  mov     rcx, rdi; Str
0x1800096ba  call    cs:__imp_wcsrchr
0x1800096c0  test    rax, rax
0x1800096c3  jnz     short loc_1800096CA
0x1800096c5  mov     rax, rdi
0x1800096c8  jmp     short loc_1800096CE
0x1800096ca  add     rax, 2
0x1800096ce  lea     r9, [rsp+258h+NewFileName]
0x1800096d3  mov     [rsp+258h+pbCancel], rax
0x1800096d8  lea     r8, aSS; "%s\\%s"
0x1800096df  mov     edx, 104h; unsigned __int64
0x1800096e4  lea     rcx, [rsp+258h+NewFileName]; unsigned __int16 *
0x1800096e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800096ee  mov     ebx, eax
0x1800096f0  test    eax, eax
0x1800096f2  jns     short loc_1800096FF
0x1800096f4  movzx   eax, ax
0x1800096f7  mov     r8d, 73Ch
0x1800096fd  jmp     short loc_18000974E
0x1800096ff  mov     [rsp+258h+dwCopyFlags], 0; dwCopyFlags
0x180009707  lea     rdx, [rsp+258h+NewFileName]; lpNewFileName
0x18000970c  xor     r9d, r9d; lpData
0x18000970f  mov     [rsp+258h+pbCancel], 0; pbCancel
0x180009718  xor     r8d, r8d; lpProgressRoutine
0x18000971b  mov     rcx, rdi; lpExistingFileName
0x18000971e  call    cs:__imp_CopyFileExW
0x180009724  test    eax, eax
0x180009726  jz      short loc_18000972C
0x180009728  xor     ebx, ebx
0x18000972a  jmp     short loc_18000976C
0x18000972c  call    cs:__imp_GetLastError
0x180009732  mov     ebx, eax
0x180009734  test    eax, eax
0x180009736  jle     short loc_180009741
0x180009738  movzx   ebx, ax
0x18000973b  or      ebx, 80070000h
0x180009741  test    ebx, ebx
0x180009743  jns     short loc_18000976C
0x180009745  movzx   eax, bx
0x180009748  mov     r8d, 743h; int
0x18000974e  mov     dword ptr [rsp+258h+pbCancel], eax; Args
0x180009752  lea     r9, aErrorD_0; "Error = %d"
0x180009759  lea     rdx, aWdiaddfiletoin_0; "WdiAddFileToInstance"
0x180009760  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180009767  call    WdipTraceError
0x18000976c  mov     eax, ebx
0x18000976e  mov     rcx, [rsp+258h+var_18]
0x180009776  xor     rcx, rsp; StackCookie
0x180009779  call    __security_check_cookie
0x18000977e  mov     rbx, [rsp+258h+arg_10]
0x180009786  add     rsp, 250h
0x18000978d  pop     rdi
0x18000978e  retn
```
