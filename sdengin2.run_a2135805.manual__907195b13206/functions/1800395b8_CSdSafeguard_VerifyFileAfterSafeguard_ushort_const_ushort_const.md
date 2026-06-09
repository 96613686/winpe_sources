# CSdSafeguard::_VerifyFileAfterSafeguard(ushort const *,ushort const *)

- ea: `0x1800395b8`
- end: `0x180039771`
- name: `?_VerifyFileAfterSafeguard@CSdSafeguard@@AEAAJPEBG0@Z`
- size: `441`
- prototype: `int(CSdSafeguard *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180037bc0`

## callees

- `0x1800395b8`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1800396cb`
- `KERNEL32!ReadFile` at `0x1800396cb`
- `KERNEL32!VirtualAlloc` at `0x180039636`
- `KERNEL32!VirtualAlloc` at `0x180039636`
- `KERNEL32!CreateFileW` at `0x180039685`
- `KERNEL32!CreateFileW` at `0x180039685`
- `KERNEL32!CloseHandle` at `0x180039733`
- `KERNEL32!CloseHandle` at `0x180039733`
- `KERNEL32!VirtualFree` at `0x180039717`
- `KERNEL32!VirtualFree` at `0x180039717`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "CSdSafeguard::_VerifyFileAfterSafeguard", 0x474u, 1u);
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
0x1800395b8  mov     [rsp-8+NumberOfBytesRead], rcx
0x1800395bd  push    rbp
0x1800395be  push    rbx
0x1800395bf  push    rdi
0x1800395c0  push    r14
0x1800395c2  lea     rbp, [rsp-3Fh]
0x1800395c7  sub     rsp, 88h
0x1800395ce  mov     rdi, r8
0x1800395d1  mov     rbx, rdx
0x1800395d4  mov     r14d, 1
0x1800395da  mov     r9d, r14d; unsigned __int16
0x1800395dd  mov     r8d, 474h; unsigned __int16
0x1800395e3  lea     rdx, aCsdsafeguardVe; "CSdSafeguard::_VerifyFileAfterSafeguard"
0x1800395ea  lea     rcx, [rbp+57h+var_60]; this
0x1800395ee  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800395f3  mov     dword ptr [rbp+57h+NumberOfBytesRead], 0
0x1800395fa  mov     eax, 47Bh
0x1800395ff  test    rbx, rbx
0x180039602  jz      loc_18003974C
0x180039608  mov     [rbp+57h+var_5C], ax
0x18003960c  mov     eax, 47Ch
0x180039611  test    rdi, rdi
0x180039614  jz      loc_18003974C
0x18003961a  mov     [rbp+57h+var_60], 0
0x180039621  mov     [rbp+57h+var_5C], ax
0x180039625  mov     edx, 100000h; dwSize
0x18003962a  xor     ecx, ecx; lpAddress
0x18003962c  lea     r9d, [r14+3]; flProtect
0x180039630  mov     r8d, 1000h; flAllocationType
0x180039636  call    cs:__imp_VirtualAlloc
0x18003963d  nop     dword ptr [rax+rax+00h]
0x180039642  mov     rbx, rax
0x180039645  mov     ecx, 482h
0x18003964a  test    rax, rax
0x18003964d  jz      loc_180039741
0x180039653  mov     [rbp+57h+var_60], 0
0x18003965a  mov     [rbp+57h+var_5C], cx
0x18003965e  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x180039667  mov     [rsp+0A0h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x18003966f  mov     [rsp+0A0h+dwCreationDisposition], 3; dwCreationDisposition
0x180039677  xor     r9d, r9d; lpSecurityAttributes
0x18003967a  mov     r8d, r14d; dwShareMode
0x18003967d  mov     edx, 80000000h; dwDesiredAccess
0x180039682  mov     rcx, rdi; lpFileName
0x180039685  call    cs:__imp_CreateFileW
0x18003968c  nop     dword ptr [rax+rax+00h]
0x180039691  mov     rdi, rax
0x180039694  lea     rcx, [rax-1]
0x180039698  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18003969c  ja      short loc_1800396FB
0x18003969e  mov     [rbp+57h+var_60], 0
0x1800396a5  mov     ecx, 48Ch
0x1800396aa  mov     [rbp+57h+var_5C], cx
0x1800396ae  lea     r14d, [rcx+4]
0x1800396b2  mov     qword ptr [rsp+0A0h+dwCreationDisposition], 0; lpOverlapped
0x1800396bb  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800396bf  mov     r8d, 100000h; nNumberOfBytesToRead
0x1800396c5  mov     rdx, rbx; lpBuffer
0x1800396c8  mov     rcx, rdi; hFile
0x1800396cb  call    cs:__imp_ReadFile
0x1800396d2  nop     dword ptr [rax+rax+00h]
0x1800396d7  test    eax, eax
0x1800396d9  jz      short loc_1800396EF
0x1800396db  mov     [rbp+57h+var_60], 0
0x1800396e2  mov     [rbp+57h+var_5C], r14w
0x1800396e7  cmp     dword ptr [rbp+57h+NumberOfBytesRead], 0
0x1800396eb  jnz     short loc_1800396B2
0x1800396ed  jmp     short loc_18003970C
0x1800396ef  call    GetLastFailureAsHRESULT
0x1800396f4  mov     [rbp+57h+var_5A], r14w
0x1800396f9  jmp     short loc_180039709
0x1800396fb  call    GetLastFailureAsHRESULT
0x180039700  mov     ecx, 48Ch
0x180039705  mov     [rbp+57h+var_5A], cx
0x180039709  mov     [rbp+57h+var_60], eax
0x18003970c  xor     edx, edx; dwSize
0x18003970e  mov     r8d, 8000h; dwFreeType
0x180039714  mov     rcx, rbx; lpAddress
0x180039717  call    cs:__imp_VirtualFree
0x18003971e  nop     dword ptr [rax+rax+00h]
0x180039723  mov     ebx, [rbp+57h+var_60]
0x180039726  lea     rax, [rdi-1]
0x18003972a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003972e  ja      short loc_180039758
0x180039730  mov     rcx, rdi; hObject
0x180039733  call    cs:__imp_CloseHandle
0x18003973a  nop     dword ptr [rax+rax+00h]
0x18003973f  jmp     short loc_180039758
0x180039741  mov     ebx, 8007000Eh
0x180039746  mov     [rbp+57h+var_5A], cx
0x18003974a  jmp     short loc_180039755
0x18003974c  mov     [rbp+57h+var_5A], ax
0x180039750  mov     ebx, 80070057h
0x180039755  mov     [rbp+57h+var_60], ebx
0x180039758  lea     rcx, [rbp+57h+var_60]; this
0x18003975c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180039761  mov     eax, ebx
0x180039763  add     rsp, 88h
0x18003976a  pop     r14
0x18003976c  pop     rdi
0x18003976d  pop     rbx
0x18003976e  pop     rbp
0x18003976f  retn
```
