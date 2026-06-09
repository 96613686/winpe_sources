# IsRemovableReady

- ea: `0x18000efec`
- end: `0x18000f1cb`
- name: `IsRemovableReady`
- size: `479`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1800119c4`

## callees

- `0x18000efec`
- `0x180072e08`
- `0x180072f14`
- `0x180093698`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x18000f07a`
- `ntdll!RtlSetThreadErrorMode` at `0x18000f18b`
- `ntdll!RtlSetThreadErrorMode` at `0x18000f07a`
- `ntdll!RtlSetThreadErrorMode` at `0x18000f18b`
- `ntdll!RtlGetThreadErrorMode` at `0x18000f065`
- `ntdll!RtlGetThreadErrorMode` at `0x18000f065`
- `KERNEL32!CreateFileW` at `0x18000f0cd`
- `KERNEL32!CreateFileW` at `0x18000f0cd`
- `KERNEL32!GetLastError` at `0x18000f0e7`
- `KERNEL32!GetLastError` at `0x18000f0e7`
- `KERNEL32!CloseHandle` at `0x18000f172`
- `KERNEL32!CloseHandle` at `0x18000f1a7`
- `KERNEL32!CloseHandle` at `0x18000f172`
- `KERNEL32!CloseHandle` at `0x18000f1a7`
- `KERNEL32!DeviceIoControl` at `0x18000f157`
- `KERNEL32!DeviceIoControl` at `0x18000f157`

## string_xrefs

- `0x18000f00f`: `IsRemovableReady`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "IsRemovableReady", 0x1BBu, 1u);
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
0x18000efec  push    rbp
0x18000efee  push    rbx
0x18000efef  push    rsi
0x18000eff0  push    rdi
0x18000eff1  lea     rbp, [rsp-3Fh]
0x18000eff6  sub     rsp, 88h
0x18000effd  mov     rdi, rdx
0x18000f000  mov     rbx, rcx
0x18000f003  mov     r9d, 1; unsigned __int16
0x18000f009  mov     r8d, 1BBh; unsigned __int16
0x18000f00f  lea     rdx, aIsremovablerea; "IsRemovableReady"
0x18000f016  lea     rcx, [rbp+57h+var_60]; this
0x18000f01a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000f01f  mov     [rbp+57h+BytesReturned], 0
0x18000f026  test    rdi, rdi
0x18000f029  jz      short loc_18000F031
0x18000f02b  mov     dword ptr [rdi], 0
0x18000f031  mov     eax, 1C4h
0x18000f036  test    rbx, rbx
0x18000f039  jnz     short loc_18000F04C
0x18000f03b  mov     edi, 80070057h
0x18000f040  mov     [rbp+57h+var_60], edi
0x18000f043  mov     [rbp+57h+var_5A], ax
0x18000f047  jmp     loc_18000F1B3
0x18000f04c  mov     [rbp+57h+var_5C], ax
0x18000f050  mov     eax, 1C5h
0x18000f055  test    rdi, rdi
0x18000f058  jz      short loc_18000F03B
0x18000f05a  mov     [rbp+57h+var_60], 0
0x18000f061  mov     [rbp+57h+var_5C], ax
0x18000f065  call    cs:__imp_RtlGetThreadErrorMode
0x18000f06c  nop     dword ptr [rax+rax+00h]
0x18000f071  mov     esi, eax
0x18000f073  mov     ecx, eax
0x18000f075  or      ecx, 10h; NewMode
0x18000f078  xor     edx, edx; OldMode
0x18000f07a  call    cs:__imp_RtlSetThreadErrorMode
0x18000f081  nop     dword ptr [rax+rax+00h]
0x18000f086  mov     ecx, eax
0x18000f088  call    HRESULTFromNTSTATUS
0x18000f08d  mov     [rbp+57h+var_60], eax
0x18000f090  test    eax, eax
0x18000f092  mov     eax, 1CBh
0x18000f097  jns     short loc_18000F0A2
0x18000f099  mov     [rbp+57h+var_5A], ax
0x18000f09d  jmp     loc_18000F17E
0x18000f0a2  mov     [rbp+57h+var_5C], ax
0x18000f0a6  mov     [rsp+0A0h+hTemplateFile], 0; hTemplateFile
0x18000f0af  mov     [rsp+0A0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000f0b7  mov     r8d, 3; dwShareMode
0x18000f0bd  mov     [rsp+0A0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000f0c2  xor     r9d, r9d; lpSecurityAttributes
0x18000f0c5  mov     edx, 80000000h; dwDesiredAccess
0x18000f0ca  mov     rcx, rbx; lpFileName
0x18000f0cd  call    cs:__imp_CreateFileW
0x18000f0d4  nop     dword ptr [rax+rax+00h]
0x18000f0d9  mov     rbx, rax
0x18000f0dc  inc     rax
0x18000f0df  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000f0e5  jnz     short loc_18000F126
0x18000f0e7  call    cs:__imp_GetLastError
0x18000f0ee  nop     dword ptr [rax+rax+00h]
0x18000f0f3  cmp     eax, 15h
0x18000f0f6  jz      short loc_18000F112
0x18000f0f8  test    eax, eax
0x18000f0fa  jle     short loc_18000F104
0x18000f0fc  movzx   eax, ax
0x18000f0ff  or      eax, 80070000h
0x18000f104  mov     [rbp+57h+var_60], eax
0x18000f107  mov     eax, 1E0h
0x18000f10c  mov     [rbp+57h+var_5A], ax
0x18000f110  jmp     short loc_18000F165
0x18000f112  mov     [rbp+57h+var_60], 0
0x18000f119  mov     eax, 1E0h
0x18000f11e  mov     [rbp+57h+var_5C], ax
0x18000f122  xor     eax, eax
0x18000f124  jmp     short loc_18000F163
0x18000f126  mov     [rsp+0A0h+lpOverlapped], 0; lpOverlapped
0x18000f12f  lea     rax, [rbp+57h+BytesReturned]
0x18000f133  mov     [rsp+0A0h+hTemplateFile], rax; lpBytesReturned
0x18000f138  mov     [rsp+0A0h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18000f140  mov     qword ptr [rsp+0A0h+dwCreationDisposition], 0; lpOutBuffer
0x18000f149  xor     r9d, r9d; nInBufferSize
0x18000f14c  xor     r8d, r8d; lpInBuffer
0x18000f14f  mov     edx, 2D4800h; dwIoControlCode
0x18000f154  mov     rcx, rbx; hDevice
0x18000f157  call    cs:__imp_DeviceIoControl
0x18000f15e  nop     dword ptr [rax+rax+00h]
0x18000f163  mov     [rdi], eax
0x18000f165  lea     rax, [rbx-1]
0x18000f169  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000f16d  ja      short loc_18000F182
0x18000f16f  mov     rcx, rbx; hObject
0x18000f172  call    cs:__imp_CloseHandle
0x18000f179  nop     dword ptr [rax+rax+00h]
0x18000f17e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f182  cmp     esi, 0FFFFFFFFh
0x18000f185  jz      short loc_18000F197
0x18000f187  xor     edx, edx; OldMode
0x18000f189  mov     ecx, esi; NewMode
0x18000f18b  call    cs:__imp_RtlSetThreadErrorMode
0x18000f192  nop     dword ptr [rax+rax+00h]
0x18000f197  mov     edi, [rbp+57h+var_60]
0x18000f19a  lea     rcx, [rbx-1]
0x18000f19e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000f1a2  ja      short loc_18000F1B3
0x18000f1a4  mov     rcx, rbx; hObject
0x18000f1a7  call    cs:__imp_CloseHandle
0x18000f1ae  nop     dword ptr [rax+rax+00h]
0x18000f1b3  lea     rcx, [rbp+57h+var_60]; this
0x18000f1b7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000f1bc  mov     eax, edi
0x18000f1be  add     rsp, 88h
0x18000f1c5  pop     rdi
0x18000f1c6  pop     rsi
0x18000f1c7  pop     rbx
0x18000f1c8  pop     rbp
0x18000f1c9  retn
```
