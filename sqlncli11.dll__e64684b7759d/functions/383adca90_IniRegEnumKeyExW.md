# IniRegEnumKeyExW

- ea: `0x383adca90`
- end: `0x383adcd03`
- name: `IniRegEnumKeyExW`
- size: `627`
- prototype: `__int64 __fastcall(int, int, int, int, LPDWORD lpReserved, LPWSTR lpClass, LPDWORD, PFILETIME)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x383adc860`

## callees

- `0x3838427d0`
- `0x383adca90`
- `0x383add760`
- `0x383add980`

## import_xrefs

- `MSVCR100!wcschr` at `0x383adcbe7`
- `MSVCR100!wcschr` at `0x383adcbe7`
- `KERNEL32!SetLastError` at `0x383adcb24`
- `KERNEL32!SetLastError` at `0x383adcc9a`
- `KERNEL32!SetLastError` at `0x383adcb24`
- `KERNEL32!SetLastError` at `0x383adcc9a`
- `KERNEL32!CompareStringW` at `0x383adcbce`
- `KERNEL32!CompareStringW` at `0x383adcbce`
- `KERNEL32!HeapFree` at `0x383adcc70`
- `KERNEL32!HeapFree` at `0x383adcc91`
- `KERNEL32!HeapFree` at `0x383adcc70`
- `KERNEL32!HeapFree` at `0x383adcc91`
- `KERNEL32!GetProcessHeap` at `0x383adcc60`
- `KERNEL32!GetProcessHeap` at `0x383adcc83`
- `KERNEL32!GetProcessHeap` at `0x383adcc60`
- `KERNEL32!GetProcessHeap` at `0x383adcc83`
- `KERNEL32!DebugBreak` at `0x383adcac6`
- `KERNEL32!DebugBreak` at `0x383adcad7`
- `KERNEL32!DebugBreak` at `0x383adcae8`
- `KERNEL32!DebugBreak` at `0x383adcaf9`
- `KERNEL32!DebugBreak` at `0x383adcac6`
- `KERNEL32!DebugBreak` at `0x383adcad7`
- `KERNEL32!DebugBreak` at `0x383adcae8`
- `KERNEL32!DebugBreak` at `0x383adcaf9`
- `ADVAPI32!RegEnumKeyExW` at `0x383adccf4`
- `ADVAPI32!RegEnumKeyExW` at `0x383adccf4`

## pseudocode

```c
LSTATUS __fastcall IniRegEnumKeyExW(
        HKEY a1,
        DWORD a2,
        WCHAR *a3,
        DWORD *a4,
        LPDWORD lpReserved,
        LPWSTR lpClass,
        LPDWORD lpcchClass,
        PFILETIME lpftLastWriteTime)
{
  __int64 Path; // rax
  WCHAR *v10; // r13
  __int64 v12; // rsi
  DWORD v13; // r14d
  _WORD *RawString; // rax
  const WCHAR *lpString2; // rdi
  int v16; // r15d
  __int64 v17; // rbx
  int cchCount2; // eax
  DWORD v19; // ebp
  __int64 v20; // rax
  bool v21; // zf
  HANDLE ProcessHeap; // rax
  HANDLE v23; // rax
  void *lpMem; // [rsp+40h] [rbp-48h]

  if ( !dword_383B1F178 )
    return RegEnumKeyExW(a1, a2, a3, a4, lpReserved, lpClass, lpcchClass, lpftLastWriteTime);
  if ( lpReserved )
    DebugBreak();
  if ( lpClass )
    DebugBreak();
  if ( lpcchClass )
    DebugBreak();
  if ( lpftLastWriteTime )
    DebugBreak();
  Path = IniRegMakePath(a1, &WideCharStr);
  v10 = (WCHAR *)Path;
  if ( !Path )
  {
    SetLastError(8u);
    return 8;
  }
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(Path + 2 * v12) );
  v13 = 259;
  RawString = (_WORD *)IniRegGetRawString(0, 0);
  lpMem = RawString;
  lpString2 = RawString;
  if ( !RawString )
  {
    v13 = 8;
    goto LABEL_35;
  }
  v16 = 0;
  if ( !*RawString )
    goto LABEL_33;
  while ( 1 )
  {
    v17 = -1;
    do
      ++v17;
    while ( lpString2[v17] );
    cchCount2 = v12;
    if ( (unsigned int)v17 < (unsigned int)v12 )
      cchCount2 = v17;
    if ( CompareStringW(0x400u, 1u, v10, v12, lpString2, cchCount2) != 2 || wcschr(&lpString2[(unsigned int)v12], 0x5Cu) )
      goto LABEL_24;
    v19 = v17 - v12;
    if ( v16 == a2 )
      break;
    ++v16;
LABEL_24:
    v20 = (unsigned int)(v17 + 1);
    v21 = lpString2[v20] == 0;
    lpString2 += v20;
    if ( v21 )
      goto LABEL_33;
  }
  if ( a3 )
  {
    if ( *a4 <= v19 + 1 )
    {
      v13 = 234;
      goto LABEL_32;
    }
    memcpy(a3, &lpString2[(unsigned int)v12], 2 * v19 + 2);
LABEL_31:
    v13 = 0;
LABEL_32:
    *a4 = v19;
  }
  else if ( a4 )
  {
    goto LABEL_31;
  }
LABEL_33:
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, lpMem);
LABEL_35:
  v23 = GetProcessHeap();
  HeapFree(v23, 0, v10);
  SetLastError(v13);
  return v13;
}

```

## disassembly

```asm
0x383adca90  mov     [rsp+arg_18], r9
0x383adca95  mov     [rsp+arg_10], r8
0x383adca9a  mov     [rsp+arg_8], edx
0x383adca9e  push    rbx
0x383adca9f  sub     rsp, 80h
0x383adcaa6  cmp     cs:dword_383B1F178, 0
0x383adcaad  mov     rbx, rcx
0x383adcab0  jz      loc_383ADCCC0
0x383adcab6  cmp     [rsp+88h+lpReserved], 0
0x383adcabf  mov     [rsp+88h+var_28], r13
0x383adcac4  jz      short loc_383ADCACC
0x383adcac6  call    cs:__imp_DebugBreak
0x383adcacc  cmp     [rsp+88h+lpClass], 0
0x383adcad5  jz      short loc_383ADCADD
0x383adcad7  call    cs:__imp_DebugBreak
0x383adcadd  cmp     [rsp+88h+arg_30], 0
0x383adcae6  jz      short loc_383ADCAEE
0x383adcae8  call    cs:__imp_DebugBreak
0x383adcaee  cmp     [rsp+88h+arg_38], 0
0x383adcaf7  jz      short loc_383ADCAFF
0x383adcaf9  call    cs:__imp_DebugBreak
0x383adcaff  lea     rdx, WideCharStr
0x383adcb06  mov     rcx, rbx
0x383adcb09  mov     [rsp+88h+var_30], r14
0x383adcb0e  call    IniRegMakePath
0x383adcb13  mov     r13, rax
0x383adcb16  test    rax, rax
0x383adcb19  jnz     short loc_383ADCB40
0x383adcb1b  mov     r14d, 8
0x383adcb21  mov     ecx, r14d; dwErrCode
0x383adcb24  call    cs:__imp_SetLastError
0x383adcb2a  mov     r13, [rsp+88h+var_28]
0x383adcb2f  mov     eax, r14d
0x383adcb32  mov     r14, [rsp+88h+var_30]
0x383adcb37  add     rsp, 80h
0x383adcb3e  pop     rbx
0x383adcb3f  retn
0x383adcb40  mov     [rsp+88h+var_10], rsi
0x383adcb45  mov     [rsp+88h+var_18], rdi
0x383adcb4a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x383adcb4e  xchg    ax, ax
0x383adcb50  inc     rsi
0x383adcb53  cmp     word ptr [rax+rsi*2], 0
0x383adcb58  jnz     short loc_383ADCB50
0x383adcb5a  xor     edx, edx; lpKeyName
0x383adcb5c  xor     ecx, ecx; lpAppName
0x383adcb5e  mov     r14d, 103h
0x383adcb64  call    IniRegGetRawString
0x383adcb69  mov     [rsp+88h+lpMem], rax
0x383adcb6e  mov     rdi, rax
0x383adcb71  test    rax, rax
0x383adcb74  jz      loc_383ADCC7D
0x383adcb7a  mov     [rsp+88h+var_38], r15
0x383adcb7f  xor     r15d, r15d
0x383adcb82  cmp     [rax], r15w
0x383adcb86  jz      loc_383ADCC60
0x383adcb8c  mov     [rsp+88h+arg_0], rbp
0x383adcb94  mov     [rsp+88h+var_20], r12
0x383adcb99  nop     dword ptr [rax+00000000h]
0x383adcba0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x383adcba4  inc     rbx
0x383adcba7  cmp     word ptr [rdi+rbx*2], 0
0x383adcbac  jnz     short loc_383ADCBA4
0x383adcbae  mov     eax, esi
0x383adcbb0  cmp     ebx, esi
0x383adcbb2  mov     r9d, esi; cchCount1
0x383adcbb5  cmovb   eax, ebx
0x383adcbb8  mov     r8, r13; lpString1
0x383adcbbb  mov     edx, 1; dwCmpFlags
0x383adcbc0  mov     [rsp+88h+cchCount2], eax; cchCount2
0x383adcbc4  mov     ecx, 400h; Locale
0x383adcbc9  mov     [rsp+88h+lpString2], rdi; lpString2
0x383adcbce  call    cs:__imp_CompareStringW
0x383adcbd4  cmp     eax, 2
0x383adcbd7  jnz     short loc_383ADCC03
0x383adcbd9  mov     eax, esi
0x383adcbdb  mov     edx, 5Ch ; '\'; Ch
0x383adcbe0  lea     r12, [rdi+rax*2]
0x383adcbe4  mov     rcx, r12; Str
0x383adcbe7  call    cs:__imp_wcschr
0x383adcbed  test    rax, rax
0x383adcbf0  jnz     short loc_383ADCC03
0x383adcbf2  mov     ebp, ebx
0x383adcbf4  sub     ebp, esi
0x383adcbf6  cmp     r15d, [rsp+88h+arg_8]
0x383adcbfe  jz      short loc_383ADCC13
0x383adcc00  inc     r15d
0x383adcc03  lea     eax, [rbx+1]
0x383adcc06  cmp     word ptr [rdi+rax*2], 0
0x383adcc0b  lea     rdi, [rdi+rax*2]
0x383adcc0f  jnz     short loc_383ADCBA0
0x383adcc11  jmp     short loc_383ADCC53
0x383adcc13  mov     rcx, [rsp+88h+arg_10]; void *
0x383adcc1b  mov     rbx, [rsp+88h+arg_18]
0x383adcc23  test    rcx, rcx
0x383adcc26  jz      short loc_383ADCC49
0x383adcc28  lea     eax, [rbp+1]
0x383adcc2b  cmp     [rbx], eax
0x383adcc2d  ja      short loc_383ADCC37
0x383adcc2f  mov     r14d, 0EAh
0x383adcc35  jmp     short loc_383ADCC51
0x383adcc37  lea     r8d, ds:2[rbp*2]; Size
0x383adcc3f  mov     rdx, r12; Src
0x383adcc42  call    memcpy
0x383adcc47  jmp     short loc_383ADCC4E
0x383adcc49  test    rbx, rbx
0x383adcc4c  jz      short loc_383ADCC53
0x383adcc4e  xor     r14d, r14d
0x383adcc51  mov     [rbx], ebp
0x383adcc53  mov     rbp, [rsp+88h+arg_0]
0x383adcc5b  mov     r12, [rsp+88h+var_20]
0x383adcc60  call    cs:__imp_GetProcessHeap
0x383adcc66  mov     r8, [rsp+88h+lpMem]; lpMem
0x383adcc6b  xor     edx, edx; dwFlags
0x383adcc6d  mov     rcx, rax; hHeap
0x383adcc70  call    cs:__imp_HeapFree
0x383adcc76  mov     r15, [rsp+88h+var_38]
0x383adcc7b  jmp     short loc_383ADCC83
0x383adcc7d  mov     r14d, 8
0x383adcc83  call    cs:__imp_GetProcessHeap
0x383adcc89  mov     r8, r13; lpMem
0x383adcc8c  xor     edx, edx; dwFlags
0x383adcc8e  mov     rcx, rax; hHeap
0x383adcc91  call    cs:__imp_HeapFree
0x383adcc97  mov     ecx, r14d; dwErrCode
0x383adcc9a  call    cs:__imp_SetLastError
0x383adcca0  mov     rdi, [rsp+88h+var_18]
0x383adcca5  mov     rsi, [rsp+88h+var_10]
0x383adccaa  mov     r13, [rsp+88h+var_28]
0x383adccaf  mov     eax, r14d
0x383adccb2  mov     r14, [rsp+88h+var_30]
0x383adccb7  add     rsp, 80h
0x383adccbe  pop     rbx
0x383adccbf  retn
0x383adccc0  mov     rax, [rsp+88h+arg_38]
0x383adccc8  mov     [rsp+88h+lpftLastWriteTime], rax; lpftLastWriteTime
0x383adcccd  mov     rax, [rsp+88h+arg_30]
0x383adccd5  mov     [rsp+88h+lpcchClass], rax; lpcchClass
0x383adccda  mov     rax, [rsp+88h+lpClass]
0x383adcce2  mov     qword ptr [rsp+88h+cchCount2], rax; lpClass
0x383adcce7  mov     rax, [rsp+88h+lpReserved]
0x383adccef  mov     [rsp+88h+lpString2], rax; lpReserved
0x383adccf4  call    cs:__imp_RegEnumKeyExW
0x383adccfa  add     rsp, 80h
0x383adcd01  pop     rbx
0x383adcd02  retn
```
