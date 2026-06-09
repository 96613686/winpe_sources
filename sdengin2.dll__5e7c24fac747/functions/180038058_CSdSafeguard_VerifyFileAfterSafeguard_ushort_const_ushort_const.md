# CSdSafeguard::_VerifyFileAfterSafeguard(ushort const *,ushort const *)

- ea: `0x180038058`
- end: `0x1800381f2`
- name: `?_VerifyFileAfterSafeguard@CSdSafeguard@@AEAAJPEBG0@Z`
- size: `410`
- prototype: `int(CSdSafeguard *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180036730`

## callees

- `0x180038058`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18003815f`
- `KERNEL32!ReadFile` at `0x18003815f`
- `KERNEL32!VirtualAlloc` at `0x1800380d6`
- `KERNEL32!VirtualAlloc` at `0x1800380d6`
- `KERNEL32!CreateFileW` at `0x18003811f`
- `KERNEL32!CreateFileW` at `0x18003811f`
- `KERNEL32!CloseHandle` at `0x1800381bb`
- `KERNEL32!CloseHandle` at `0x1800381bb`
- `KERNEL32!VirtualFree` at `0x1800381a5`
- `KERNEL32!VirtualFree` at `0x1800381a5`

## pseudocode

```c
__int64 __fastcall CSdSafeguard::_VerifyFileAfterSafeguard(
        CSdSafeguard *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int16 v5; // ax
  void *v6; // rbx
  char *FileW; // rdi
  __int64 v8; // rcx
  unsigned int LastFailureAsHRESULT; // eax
  unsigned int v10; // ebx
  unsigned int v12; // [rsp+40h] [rbp-9h] BYREF
  __int16 v13; // [rsp+44h] [rbp-5h]
  __int16 v14; // [rsp+46h] [rbp-3h]
  CSdSafeguard *NumberOfBytesRead; // [rsp+B0h] [rbp+67h] BYREF

  NumberOfBytesRead = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "CSdSafeguard::_VerifyFileAfterSafeguard", 1140, 1);
  LODWORD(NumberOfBytesRead) = 0;
  v5 = 1147;
  if ( !a2 || (v13 = 1147, v5 = 1148, !a3) )
  {
    v14 = v5;
    v10 = -2147024809;
    goto LABEL_16;
  }
  v12 = 0;
  v13 = 1148;
  v6 = VirtualAlloc(0, 0x100000u, 0x1000u, 4u);
  if ( !v6 )
  {
    v10 = -2147024882;
    v14 = 1154;
LABEL_16:
    v12 = v10;
    goto LABEL_17;
  }
  v12 = 0;
  v13 = 1154;
  FileW = (char *)CreateFileW(a3, 0x80000000, 1u, 0, 3u, 0x20000000u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(FileW - 1);
    v14 = 1164;
  }
  else
  {
    v12 = 0;
    v13 = 1164;
    while ( ReadFile(FileW, v6, 0x100000u, (LPDWORD)&NumberOfBytesRead, 0) )
    {
      v12 = 0;
      v13 = 1168;
      if ( !(_DWORD)NumberOfBytesRead )
        goto LABEL_12;
    }
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
    v14 = 1168;
  }
  v12 = LastFailureAsHRESULT;
LABEL_12:
  VirtualFree(v6, 0, 0x8000u);
  v10 = v12;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
LABEL_17:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return v10;
}

```

## disassembly

```asm
0x180038058  mov     [rsp-8+NumberOfBytesRead], rcx
0x18003805d  push    rbp
0x18003805e  push    rbx
0x18003805f  push    rdi
0x180038060  push    r14
0x180038062  lea     rbp, [rsp-3Fh]
0x180038067  sub     rsp, 88h
0x18003806e  mov     rdi, r8
0x180038071  mov     rbx, rdx
0x180038074  mov     r14d, 1
0x18003807a  mov     r9d, r14d; unsigned __int16
0x18003807d  mov     r8d, 474h; unsigned __int16
0x180038083  lea     rdx, aCsdsafeguardVe; "CSdSafeguard::_VerifyFileAfterSafeguard"
0x18003808a  lea     rcx, [rbp+57h+var_60]; this
0x18003808e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180038093  mov     dword ptr [rbp+57h+NumberOfBytesRead], 0
0x18003809a  mov     eax, 47Bh
0x18003809f  test    rbx, rbx
0x1800380a2  jz      loc_1800381CE
0x1800380a8  mov     [rbp+57h+var_5C], ax
0x1800380ac  mov     eax, 47Ch
0x1800380b1  test    rdi, rdi
0x1800380b4  jz      loc_1800381CE
0x1800380ba  mov     [rbp+57h+var_60], 0
0x1800380c1  mov     [rbp+57h+var_5C], ax
0x1800380c5  mov     edx, 100000h; dwSize
0x1800380ca  xor     ecx, ecx; lpAddress
0x1800380cc  lea     r9d, [r14+3]; flProtect
0x1800380d0  mov     r8d, 1000h; flAllocationType
0x1800380d6  call    cs:__imp_VirtualAlloc
0x1800380dc  mov     rbx, rax
0x1800380df  mov     ecx, 482h
0x1800380e4  test    rax, rax
0x1800380e7  jz      loc_1800381C3
0x1800380ed  mov     [rbp+57h+var_60], 0
0x1800380f4  mov     [rbp+57h+var_5C], cx
0x1800380f8  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x180038101  mov     [rsp+0A0h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x180038109  mov     [rsp+0A0h+dwCreationDisposition], 3; dwCreationDisposition
0x180038111  xor     r9d, r9d; lpSecurityAttributes
0x180038114  mov     r8d, r14d; dwShareMode
0x180038117  mov     edx, 80000000h; dwDesiredAccess
0x18003811c  mov     rcx, rdi; lpFileName
0x18003811f  call    cs:__imp_CreateFileW
0x180038125  mov     rdi, rax
0x180038128  lea     rcx, [rax-1]
0x18003812c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180038130  ja      short loc_180038189
0x180038132  mov     [rbp+57h+var_60], 0
0x180038139  mov     ecx, 48Ch
0x18003813e  mov     [rbp+57h+var_5C], cx
0x180038142  lea     r14d, [rcx+4]
0x180038146  mov     qword ptr [rsp+0A0h+dwCreationDisposition], 0; lpOverlapped
0x18003814f  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180038153  mov     r8d, 100000h; nNumberOfBytesToRead
0x180038159  mov     rdx, rbx; lpBuffer
0x18003815c  mov     rcx, rdi; hFile
0x18003815f  call    cs:__imp_ReadFile
0x180038165  test    eax, eax
0x180038167  jz      short loc_18003817D
0x180038169  mov     [rbp+57h+var_60], 0
0x180038170  mov     [rbp+57h+var_5C], r14w
0x180038175  cmp     dword ptr [rbp+57h+NumberOfBytesRead], 0
0x180038179  jnz     short loc_180038146
0x18003817b  jmp     short loc_18003819A
0x18003817d  call    GetLastFailureAsHRESULT
0x180038182  mov     [rbp+57h+var_5A], r14w
0x180038187  jmp     short loc_180038197
0x180038189  call    GetLastFailureAsHRESULT
0x18003818e  mov     ecx, 48Ch
0x180038193  mov     [rbp+57h+var_5A], cx
0x180038197  mov     [rbp+57h+var_60], eax
0x18003819a  xor     edx, edx; dwSize
0x18003819c  mov     r8d, 8000h; dwFreeType
0x1800381a2  mov     rcx, rbx; lpAddress
0x1800381a5  call    cs:__imp_VirtualFree
0x1800381ab  mov     ebx, [rbp+57h+var_60]
0x1800381ae  lea     rax, [rdi-1]
0x1800381b2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800381b6  ja      short loc_1800381DA
0x1800381b8  mov     rcx, rdi; hObject
0x1800381bb  call    cs:__imp_CloseHandle
0x1800381c1  jmp     short loc_1800381DA
0x1800381c3  mov     ebx, 8007000Eh
0x1800381c8  mov     [rbp+57h+var_5A], cx
0x1800381cc  jmp     short loc_1800381D7
0x1800381ce  mov     [rbp+57h+var_5A], ax
0x1800381d2  mov     ebx, 80070057h
0x1800381d7  mov     [rbp+57h+var_60], ebx
0x1800381da  lea     rcx, [rbp+57h+var_60]; this
0x1800381de  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800381e3  mov     eax, ebx
0x1800381e5  add     rsp, 88h
0x1800381ec  pop     r14
0x1800381ee  pop     rdi
0x1800381ef  pop     rbx
0x1800381f0  pop     rbp
0x1800381f1  retn
```
