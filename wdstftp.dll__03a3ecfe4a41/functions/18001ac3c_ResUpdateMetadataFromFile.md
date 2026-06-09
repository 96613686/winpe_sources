# ResUpdateMetadataFromFile

- ea: `0x18001ac3c`
- end: `0x18001ae55`
- name: `ResUpdateMetadataFromFile`
- size: `537`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18000f124`

## callees

- `0x180011244`
- `0x180011a84`
- `0x18001a874`
- `0x18001ac3c`
- `0x18001b398`
- `0x1800607b0`
- `0x180060e5a`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001ae05`
- `KERNEL32!HeapFree` at `0x18001ae05`
- `KERNEL32!GetLastError` at `0x18001adc9`
- `KERNEL32!GetLastError` at `0x18001adc9`
- `KERNEL32!CloseHandle` at `0x18001ade0`
- `KERNEL32!CloseHandle` at `0x18001ade0`
- `KERNEL32!CreateFileW` at `0x18001acda`
- `KERNEL32!CreateFileW` at `0x18001acda`
- `KERNEL32!SetLastError` at `0x18001ad6e`
- `KERNEL32!SetLastError` at `0x18001ae17`
- `KERNEL32!SetLastError` at `0x18001ad6e`
- `KERNEL32!SetLastError` at `0x18001ae17`
- `KERNEL32!GetProcessHeap` at `0x18001adf1`
- `KERNEL32!GetProcessHeap` at `0x18001adf1`

## pseudocode

```c
__int64 __fastcall ResUpdateMetadataFromFile(__int64 a1, unsigned __int16 *a2)
{
  unsigned int v4; // ebp
  __int64 FileW; // r15
  __int64 v6; // rdi
  const WCHAR *v7; // rax
  WCHAR *v8; // r14
  DWORD LastError; // ebx
  __int64 FileResourceHeader; // rdx
  int v11; // r8d
  __int64 v12; // rax
  __int64 *v13; // rax
  int v14; // ecx
  HANDLE ProcessHeap; // rax
  int v17; // [rsp+30h] [rbp-A8h]
  int v18; // [rsp+38h] [rbp-A0h]
  int v19; // [rsp+48h] [rbp-90h]
  __int64 v20[5]; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v21[24]; // [rsp+88h] [rbp-50h] BYREF

  v4 = 0;
  memset_0(v20, 0, 0x40u);
  FileW = -1;
  v6 = 0;
  if ( a1 )
  {
    if ( *(_DWORD *)a1 == -17960958 )
    {
      v6 = *(_QWORD *)(a1 + 8);
    }
    else if ( *(_DWORD *)a1 == -17960959 )
    {
      v6 = a1;
    }
  }
  v7 = (const WCHAR *)WimPathDupe(a2);
  v8 = (WCHAR *)v7;
  if ( !v7
    || (FileW = (__int64)CreateFileW(v7, 0x80000000, 7u, 0, 3u, 0xA000000u, 0), FileW == -1)
    || (v4 = ResAddFromFileAndHandle(a1, (int)v8, FileW, 1, 0, 1, v17, v18, (__int64)v20, v19, 0, 0)) == 0 )
  {
LABEL_24:
    LastError = GetLastError();
    goto LABEL_25;
  }
  LastError = 2;
  SetHandleFlag(v6, 2);
  SetHandleFlag(a1, 1);
  if ( v6 )
  {
    FileResourceHeader = FindFileResourceHeader(v6, v21, 0, 0);
  }
  else
  {
    SetLastError(0x57u);
    FileResourceHeader = 0;
  }
  if ( FileResourceHeader )
  {
    v11 = -1;
    if ( a1 )
    {
      v12 = *(_QWORD *)(a1 + 64);
      if ( !v12 )
        v12 = a1;
      v11 = *(_DWORD *)(v12 + 32);
    }
    v13 = 0;
    if ( v6 )
      v13 = *(__int64 **)(v6 + 496);
    v14 = 1;
    v4 = 0;
    while ( v13 )
    {
      if ( v14 == v11 )
      {
        *v13 = FileResourceHeader;
        v4 = 1;
        goto LABEL_24;
      }
      v13 = (__int64 *)v13[1];
      ++v14;
    }
    goto LABEL_24;
  }
  v4 = 0;
LABEL_25:
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  if ( LastError )
    SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x18001ac3c  mov     [rsp+arg_10], rbx
0x18001ac41  mov     [rsp+arg_18], rbp
0x18001ac46  push    rsi
0x18001ac47  push    rdi
0x18001ac48  push    r13
0x18001ac4a  push    r14
0x18001ac4c  push    r15
0x18001ac4e  sub     rsp, 0B0h
0x18001ac55  mov     rax, cs:__security_cookie
0x18001ac5c  xor     rax, rsp
0x18001ac5f  mov     [rsp+0D8h+var_38], rax
0x18001ac67  mov     rbx, rdx
0x18001ac6a  mov     rsi, rcx
0x18001ac6d  xor     ebp, ebp
0x18001ac6f  lea     rcx, [rsp+0D8h+var_78]; void *
0x18001ac74  xor     edx, edx; Val
0x18001ac76  lea     r8d, [rbp+40h]; Size
0x18001ac7a  call    memset_0
0x18001ac7f  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001ac83  xor     edi, edi
0x18001ac85  test    rsi, rsi
0x18001ac88  jz      short loc_18001ACA2
0x18001ac8a  cmp     dword ptr [rsi], 0FEEDF002h
0x18001ac90  jnz     short loc_18001AC98
0x18001ac92  mov     rdi, [rsi+8]
0x18001ac96  jmp     short loc_18001ACA2
0x18001ac98  cmp     dword ptr [rsi], 0FEEDF001h
0x18001ac9e  cmovz   rdi, rsi
0x18001aca2  mov     rcx, rbx
0x18001aca5  call    WimPathDupe
0x18001acaa  mov     r14, rax
0x18001acad  test    rax, rax
0x18001acb0  jz      loc_18001ADC9
0x18001acb6  and     [rsp+0D8h+var_A8], rbp
0x18001acbb  xor     r9d, r9d; lpSecurityAttributes
0x18001acbe  mov     [rsp+0D8h+dwFlagsAndAttributes], 0A000000h; dwFlagsAndAttributes
0x18001acc6  mov     edx, 80000000h; dwDesiredAccess
0x18001accb  mov     rcx, rax; lpFileName
0x18001acce  mov     [rsp+0D8h+dwCreationDisposition], 3; DWORD
0x18001acd6  lea     r8d, [r9+7]; dwShareMode
0x18001acda  call    cs:__imp_CreateFileW
0x18001ace1  nop     dword ptr [rax+rax+00h]
0x18001ace6  mov     r15, rax
0x18001ace9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001aced  jz      loc_18001ADC9
0x18001acf3  and     [rsp+0D8h+var_80], rbp
0x18001acf8  lea     rax, [rsp+0D8h+var_78]
0x18001acfd  and     [rsp+0D8h+var_88], ebp
0x18001ad01  mov     r13d, 1
0x18001ad07  mov     [rsp+0D8h+var_98], rax; __int64
0x18001ad0c  mov     r9d, r13d; int
0x18001ad0f  mov     [rsp+0D8h+dwFlagsAndAttributes], r13d; BOOL
0x18001ad14  mov     r8, r15; int
0x18001ad17  and     [rsp+0D8h+dwCreationDisposition], ebp
0x18001ad1b  mov     rdx, r14; int
0x18001ad1e  mov     rcx, rsi; int
0x18001ad21  call    ResAddFromFileAndHandle
0x18001ad26  mov     ebp, eax
0x18001ad28  test    eax, eax
0x18001ad2a  jz      loc_18001ADC9
0x18001ad30  lea     ebx, [r13+1]
0x18001ad34  mov     rcx, rdi
0x18001ad37  mov     edx, ebx
0x18001ad39  call    SetHandleFlag
0x18001ad3e  mov     edx, r13d
0x18001ad41  mov     rcx, rsi
0x18001ad44  call    SetHandleFlag
0x18001ad49  test    rdi, rdi
0x18001ad4c  jz      short loc_18001AD69
0x18001ad4e  xor     r9d, r9d
0x18001ad51  lea     rdx, [rsp+0D8h+var_50]
0x18001ad59  xor     r8d, r8d
0x18001ad5c  mov     rcx, rdi
0x18001ad5f  call    FindFileResourceHeader
0x18001ad64  mov     rdx, rax
0x18001ad67  jmp     short loc_18001AD7C
0x18001ad69  mov     ecx, 57h ; 'W'; dwErrCode
0x18001ad6e  call    cs:__imp_SetLastError
0x18001ad75  nop     dword ptr [rax+rax+00h]
0x18001ad7a  xor     edx, edx
0x18001ad7c  test    rdx, rdx
0x18001ad7f  jz      loc_18001AE51
0x18001ad85  or      r8d, 0FFFFFFFFh
0x18001ad89  test    rsi, rsi
0x18001ad8c  jz      short loc_18001AD9D
0x18001ad8e  mov     rax, [rsi+40h]
0x18001ad92  test    rax, rax
0x18001ad95  cmovz   rax, rsi
0x18001ad99  mov     r8d, [rax+20h]
0x18001ad9d  xor     eax, eax
0x18001ad9f  test    rdi, rdi
0x18001ada2  jz      short loc_18001ADAB
0x18001ada4  mov     rax, [rdi+1F0h]
0x18001adab  mov     ecx, r13d
0x18001adae  xor     ebp, ebp
0x18001adb0  test    rax, rax
0x18001adb3  jz      short loc_18001ADC9
0x18001adb5  cmp     ecx, r8d
0x18001adb8  jz      short loc_18001ADC3
0x18001adba  mov     rax, [rax+8]
0x18001adbe  add     ecx, r13d
0x18001adc1  jmp     short loc_18001ADB0
0x18001adc3  mov     [rax], rdx
0x18001adc6  mov     ebp, r13d
0x18001adc9  call    cs:__imp_GetLastError
0x18001add0  nop     dword ptr [rax+rax+00h]
0x18001add5  mov     ebx, eax
0x18001add7  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18001addb  jz      short loc_18001ADEC
0x18001addd  mov     rcx, r15; hObject
0x18001ade0  call    cs:__imp_CloseHandle
0x18001ade7  nop     dword ptr [rax+rax+00h]
0x18001adec  test    r14, r14
0x18001adef  jz      short loc_18001AE11
0x18001adf1  call    cs:__imp_GetProcessHeap
0x18001adf8  nop     dword ptr [rax+rax+00h]
0x18001adfd  mov     r8, r14; lpMem
0x18001ae00  xor     edx, edx; dwFlags
0x18001ae02  mov     rcx, rax; hHeap
0x18001ae05  call    cs:__imp_HeapFree
0x18001ae0c  nop     dword ptr [rax+rax+00h]
0x18001ae11  test    ebx, ebx
0x18001ae13  jz      short loc_18001AE23
0x18001ae15  mov     ecx, ebx; dwErrCode
0x18001ae17  call    cs:__imp_SetLastError
0x18001ae1e  nop     dword ptr [rax+rax+00h]
0x18001ae23  mov     eax, ebp
0x18001ae25  mov     rcx, [rsp+0D8h+var_38]
0x18001ae2d  xor     rcx, rsp; StackCookie
0x18001ae30  call    __security_check_cookie
0x18001ae35  lea     r11, [rsp+0D8h+var_28]
0x18001ae3d  mov     rbx, [r11+40h]
0x18001ae41  mov     rbp, [r11+48h]
0x18001ae45  mov     rsp, r11
0x18001ae48  pop     r15
0x18001ae4a  pop     r14
0x18001ae4c  pop     r13
0x18001ae4e  pop     rdi
0x18001ae4f  pop     rsi
0x18001ae50  retn
0x18001ae51  xor     ebp, ebp
0x18001ae53  jmp     short loc_18001ADD7
```
