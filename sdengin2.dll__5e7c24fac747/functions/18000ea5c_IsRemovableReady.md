# IsRemovableReady

- ea: `0x18000ea5c`
- end: `0x18000ec0a`
- name: `IsRemovableReady`
- size: `430`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180011274`

## callees

- `0x18000ea5c`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f660`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x18000eae4`
- `ntdll!RtlSetThreadErrorMode` at `0x18000ebd7`
- `ntdll!RtlSetThreadErrorMode` at `0x18000eae4`
- `ntdll!RtlSetThreadErrorMode` at `0x18000ebd7`
- `ntdll!RtlGetThreadErrorMode` at `0x18000ead5`
- `ntdll!RtlGetThreadErrorMode` at `0x18000ead5`
- `KERNEL32!CreateFileW` at `0x18000eb31`
- `KERNEL32!CreateFileW` at `0x18000eb31`
- `KERNEL32!GetLastError` at `0x18000eb45`
- `KERNEL32!GetLastError` at `0x18000eb45`
- `KERNEL32!CloseHandle` at `0x18000ebc4`
- `KERNEL32!CloseHandle` at `0x18000ebed`
- `KERNEL32!CloseHandle` at `0x18000ebc4`
- `KERNEL32!CloseHandle` at `0x18000ebed`
- `KERNEL32!DeviceIoControl` at `0x18000ebaf`
- `KERNEL32!DeviceIoControl` at `0x18000ebaf`

## string_xrefs

- `0x18000ea7f`: `IsRemovableReady`

## pseudocode

```c
__int64 __fastcall IsRemovableReady(LPCWSTR lpFileName, BOOL *a2)
{
  __int16 v4; // ax
  unsigned int v5; // edi
  ULONG ThreadErrorMode; // esi
  unsigned int v7; // eax
  __int64 FileW; // rbx
  signed int LastError; // eax
  BOOL v10; // eax
  int v12; // [rsp+40h] [rbp-9h] BYREF
  __int16 v13; // [rsp+44h] [rbp-5h]
  __int16 v14; // [rsp+46h] [rbp-3h]
  DWORD BytesReturned; // [rsp+B0h] [rbp+67h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "IsRemovableReady", 443, 1);
  BytesReturned = 0;
  if ( a2 )
    *a2 = 0;
  v4 = 452;
  if ( !lpFileName || (v13 = 452, v4 = 453, !a2) )
  {
    v5 = -2147024809;
    v12 = -2147024809;
    v14 = v4;
    goto LABEL_23;
  }
  v12 = 0;
  v13 = 453;
  ThreadErrorMode = RtlGetThreadErrorMode();
  v7 = RtlSetThreadErrorMode(ThreadErrorMode | 0x10, 0);
  v12 = HRESULTFromNTSTATUS(v7);
  if ( v12 < 0 )
  {
    v14 = 459;
LABEL_18:
    FileW = -1;
    goto LABEL_19;
  }
  v13 = 459;
  FileW = (__int64)CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0, 0);
  if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v10 = DeviceIoControl((HANDLE)FileW, 0x2D4800u, 0, 0, 0, 0, &BytesReturned, 0);
    goto LABEL_15;
  }
  LastError = GetLastError();
  if ( LastError == 21 )
  {
    v12 = 0;
    v13 = 480;
    v10 = 0;
LABEL_15:
    *a2 = v10;
    goto LABEL_16;
  }
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v12 = LastError;
  v14 = 480;
LABEL_16:
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle((HANDLE)FileW);
    goto LABEL_18;
  }
LABEL_19:
  if ( ThreadErrorMode != -1 )
    RtlSetThreadErrorMode(ThreadErrorMode, 0);
  v5 = v12;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
LABEL_23:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return v5;
}

```

## disassembly

```asm
0x18000ea5c  push    rbp
0x18000ea5e  push    rbx
0x18000ea5f  push    rsi
0x18000ea60  push    rdi
0x18000ea61  lea     rbp, [rsp-3Fh]
0x18000ea66  sub     rsp, 88h
0x18000ea6d  mov     rdi, rdx
0x18000ea70  mov     rbx, rcx
0x18000ea73  mov     r9d, 1; unsigned __int16
0x18000ea79  mov     r8d, 1BBh; unsigned __int16
0x18000ea7f  lea     rdx, aIsremovablerea; "IsRemovableReady"
0x18000ea86  lea     rcx, [rbp+57h+var_60]; this
0x18000ea8a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000ea8f  mov     [rbp+57h+BytesReturned], 0
0x18000ea96  test    rdi, rdi
0x18000ea99  jz      short loc_18000EAA1
0x18000ea9b  mov     dword ptr [rdi], 0
0x18000eaa1  mov     eax, 1C4h
0x18000eaa6  test    rbx, rbx
0x18000eaa9  jnz     short loc_18000EABC
0x18000eaab  mov     edi, 80070057h
0x18000eab0  mov     [rbp+57h+var_60], edi
0x18000eab3  mov     [rbp+57h+var_5A], ax
0x18000eab7  jmp     loc_18000EBF3
0x18000eabc  mov     [rbp+57h+var_5C], ax
0x18000eac0  mov     eax, 1C5h
0x18000eac5  test    rdi, rdi
0x18000eac8  jz      short loc_18000EAAB
0x18000eaca  mov     [rbp+57h+var_60], 0
0x18000ead1  mov     [rbp+57h+var_5C], ax
0x18000ead5  call    cs:__imp_RtlGetThreadErrorMode
0x18000eadb  mov     esi, eax
0x18000eadd  mov     ecx, eax
0x18000eadf  or      ecx, 10h; NewMode
0x18000eae2  xor     edx, edx; OldMode
0x18000eae4  call    cs:__imp_RtlSetThreadErrorMode
0x18000eaea  mov     ecx, eax
0x18000eaec  call    HRESULTFromNTSTATUS
0x18000eaf1  mov     [rbp+57h+var_60], eax
0x18000eaf4  test    eax, eax
0x18000eaf6  mov     eax, 1CBh
0x18000eafb  jns     short loc_18000EB06
0x18000eafd  mov     [rbp+57h+var_5A], ax
0x18000eb01  jmp     loc_18000EBCA
0x18000eb06  mov     [rbp+57h+var_5C], ax
0x18000eb0a  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x18000eb13  mov     [rsp+0A0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000eb1b  mov     r8d, 3; dwShareMode
0x18000eb21  mov     [rsp+0A0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000eb26  xor     r9d, r9d; lpSecurityAttributes
0x18000eb29  mov     edx, 80000000h; dwDesiredAccess
0x18000eb2e  mov     rcx, rbx; lpFileName
0x18000eb31  call    cs:__imp_CreateFileW
0x18000eb37  mov     rbx, rax
0x18000eb3a  inc     rax
0x18000eb3d  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000eb43  jnz     short loc_18000EB7E
0x18000eb45  call    cs:__imp_GetLastError
0x18000eb4b  cmp     eax, 15h
0x18000eb4e  jz      short loc_18000EB6A
0x18000eb50  test    eax, eax
0x18000eb52  jle     short loc_18000EB5C
0x18000eb54  movzx   eax, ax
0x18000eb57  or      eax, 80070000h
0x18000eb5c  mov     [rbp+57h+var_60], eax
0x18000eb5f  mov     eax, 1E0h
0x18000eb64  mov     [rbp+57h+var_5A], ax
0x18000eb68  jmp     short loc_18000EBB7
0x18000eb6a  mov     [rbp+57h+var_60], 0
0x18000eb71  mov     eax, 1E0h
0x18000eb76  mov     [rbp+57h+var_5C], ax
0x18000eb7a  xor     eax, eax
0x18000eb7c  jmp     short loc_18000EBB5
0x18000eb7e  mov     [rsp+0A0h+lpOverlapped], 0; lpOverlapped
0x18000eb87  lea     rax, [rbp+57h+BytesReturned]
0x18000eb8b  mov     [rsp+0A0h+hTemplateFile], rax; lpBytesReturned
0x18000eb90  mov     [rsp+0A0h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18000eb98  mov     qword ptr [rsp+0A0h+dwCreationDisposition], 0; lpOutBuffer
0x18000eba1  xor     r9d, r9d; nInBufferSize
0x18000eba4  xor     r8d, r8d; lpInBuffer
0x18000eba7  mov     edx, 2D4800h; dwIoControlCode
0x18000ebac  mov     rcx, rbx; hDevice
0x18000ebaf  call    cs:__imp_DeviceIoControl
0x18000ebb5  mov     [rdi], eax
0x18000ebb7  lea     rax, [rbx-1]
0x18000ebbb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ebbf  ja      short loc_18000EBCE
0x18000ebc1  mov     rcx, rbx; hObject
0x18000ebc4  call    cs:__imp_CloseHandle
0x18000ebca  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ebce  cmp     esi, 0FFFFFFFFh
0x18000ebd1  jz      short loc_18000EBDD
0x18000ebd3  xor     edx, edx; OldMode
0x18000ebd5  mov     ecx, esi; NewMode
0x18000ebd7  call    cs:__imp_RtlSetThreadErrorMode
0x18000ebdd  mov     edi, [rbp+57h+var_60]
0x18000ebe0  lea     rcx, [rbx-1]
0x18000ebe4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000ebe8  ja      short loc_18000EBF3
0x18000ebea  mov     rcx, rbx; hObject
0x18000ebed  call    cs:__imp_CloseHandle
0x18000ebf3  lea     rcx, [rbp+57h+var_60]; this
0x18000ebf7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000ebfc  mov     eax, edi
0x18000ebfe  add     rsp, 88h
0x18000ec05  pop     rdi
0x18000ec06  pop     rsi
0x18000ec07  pop     rbx
0x18000ec08  pop     rbp
0x18000ec09  retn
```
