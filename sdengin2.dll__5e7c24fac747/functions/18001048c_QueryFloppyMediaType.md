# QueryFloppyMediaType

- ea: `0x18001048c`
- end: `0x180010791`
- name: `QueryFloppyMediaType`
- size: `773`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x180010cc0`

## callees

- `0x18000be7c`
- `0x18001048c`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800105ab`
- `KERNEL32!CreateFileW` at `0x1800105ab`
- `KERNEL32!GetLastError` at `0x180010613`
- `KERNEL32!GetLastError` at `0x180010613`
- `KERNEL32!CloseHandle` at `0x18001074a`
- `KERNEL32!CloseHandle` at `0x18001074a`
- `KERNEL32!DeviceIoControl` at `0x180010605`
- `KERNEL32!DeviceIoControl` at `0x1800106a1`
- `KERNEL32!DeviceIoControl` at `0x180010605`
- `KERNEL32!DeviceIoControl` at `0x1800106a1`
- `ole32!CoTaskMemFree` at `0x18001064e`
- `ole32!CoTaskMemFree` at `0x18001071b`
- `ole32!CoTaskMemFree` at `0x18001064e`
- `ole32!CoTaskMemFree` at `0x18001071b`
- `ole32!CoTaskMemAlloc` at `0x18001065a`
- `ole32!CoTaskMemAlloc` at `0x18001065a`

## pseudocode

```c
__int64 __fastcall QueryFloppyMediaType(LPCWSTR lpFileName, _BYTE *a2, _DWORD *a3, _DWORD *a4)
{
  __int64 v8; // rcx
  _BYTE *v9; // rax
  __int16 v10; // ax
  char *FileW; // rsi
  void *v12; // rdi
  DWORD v13; // r15d
  signed int LastError; // eax
  signed int LastFailureAsHRESULT; // ebx
  __int16 v16; // ax
  int *p_OutBuffer; // rbx
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v22; // [rsp+4Ch] [rbp-B4h]
  __int16 v23; // [rsp+4Eh] [rbp-B2h]
  int OutBuffer; // [rsp+80h] [rbp-80h] BYREF
  char v25[236]; // [rsp+84h] [rbp-7Ch] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v21, "QueryFloppyMediaType", 1314, 1);
  OutBuffer = 0;
  memset_0(v25, 0, sizeof(v25));
  BytesReturned = 0;
  v20 = 0;
  if ( a2 )
  {
    v8 = 4;
    v9 = a2;
    do
    {
      *v9++ = 0;
      --v8;
    }
    while ( v8 );
  }
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !lpFileName || !*lpFileName )
  {
    v10 = 1330;
LABEL_38:
    LastFailureAsHRESULT = -2147024809;
    v23 = v10;
    v21 = -2147024809;
    goto LABEL_39;
  }
  v22 = 1330;
  v10 = 1331;
  if ( !a2 )
    goto LABEL_38;
  v22 = 1331;
  v10 = 1332;
  if ( !a3 )
    goto LABEL_38;
  v22 = 1332;
  v10 = 1333;
  if ( !a4 )
    goto LABEL_38;
  v21 = 0;
  v22 = 1333;
  *a3 = 0;
  *a4 = 1;
  FileW = (char *)CreateFileW(lpFileName, 0, 3u, 0, 3u, 0, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(FileW - 1);
    v21 = LastFailureAsHRESULT;
    v23 = 1345;
  }
  else
  {
    v12 = 0;
    v13 = 240;
    v21 = 0;
    v22 = 1345;
    if ( !DeviceIoControl(FileW, 0x2D0C00u, 0, 0, &OutBuffer, 0xF0u, &BytesReturned, 0) )
    {
      while ( 1 )
      {
        LastError = GetLastError();
        LastFailureAsHRESULT = LastError;
        if ( LastError != 122 && LastError != 234 )
        {
          if ( LastError > 0 )
            LastFailureAsHRESULT = (unsigned __int16)LastError | 0x80070000;
          v21 = LastFailureAsHRESULT;
          v16 = 1366;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_26;
          v22 = 1366;
        }
        if ( v12 )
          CoTaskMemFree(v12);
        v13 *= 2;
        v12 = CoTaskMemAlloc(v13);
        if ( !v12 )
          break;
        v21 = 0;
        v22 = 1381;
        p_OutBuffer = (int *)v12;
        if ( DeviceIoControl(FileW, 0x2D0C00u, 0, 0, v12, v13, &BytesReturned, 0) )
          goto LABEL_29;
      }
      LastFailureAsHRESULT = -2147024882;
      v21 = -2147024882;
      v23 = 1381;
      goto LABEL_36;
    }
    p_OutBuffer = &OutBuffer;
LABEL_29:
    LastFailureAsHRESULT = FindLargestFloppyMediaType(p_OutBuffer, BytesReturned / 0x18uLL, a2, &v20);
    v21 = LastFailureAsHRESULT;
    v16 = 1399;
    if ( LastFailureAsHRESULT < 0 )
    {
LABEL_26:
      v23 = v16;
    }
    else
    {
      v22 = 1399;
      *a4 = v20 == 0;
    }
    if ( v12 )
    {
      CoTaskMemFree(v12);
      LastFailureAsHRESULT = v21;
LABEL_36:
      CloseHandle(FileW);
      goto LABEL_39;
    }
  }
  if ( FileW != (char *)-1LL && FileW )
    goto LABEL_36;
LABEL_39:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v21);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001048c  push    rbp
0x18001048e  push    rbx
0x18001048f  push    rsi
0x180010490  push    rdi
0x180010491  push    r12
0x180010493  push    r13
0x180010495  push    r14
0x180010497  push    r15
0x180010499  lea     rbp, [rsp-88h]
0x1800104a1  sub     rsp, 188h
0x1800104a8  mov     rax, cs:__security_cookie
0x1800104af  xor     rax, rsp
0x1800104b2  mov     [rbp+0C0h+var_50], rax
0x1800104b6  mov     r14, r9
0x1800104b9  mov     rbx, r8
0x1800104bc  mov     r12, rdx
0x1800104bf  mov     rdi, rcx
0x1800104c2  mov     r9d, 1; unsigned __int16
0x1800104c8  mov     r8d, 522h; unsigned __int16
0x1800104ce  lea     rdx, aQueryfloppymed; "QueryFloppyMediaType"
0x1800104d5  lea     rcx, [rsp+1C0h+var_178]; this
0x1800104da  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800104df  xor     r13d, r13d
0x1800104e2  mov     [rbp+0C0h+OutBuffer], r13d
0x1800104e6  xor     edx, edx; Val
0x1800104e8  mov     r8d, 0ECh; Size
0x1800104ee  lea     rcx, [rbp+0C0h+var_13C]; void *
0x1800104f2  call    memset_0
0x1800104f7  mov     [rsp+1C0h+BytesReturned], r13d
0x1800104fc  mov     [rsp+1C0h+var_17C], r13d
0x180010501  test    r12, r12
0x180010504  jz      short loc_180010519
0x180010506  lea     ecx, [r13+4]
0x18001050a  mov     rax, r12
0x18001050d  mov     [rax], r13b
0x180010510  inc     rax
0x180010513  sub     rcx, 1
0x180010517  jnz     short loc_18001050D
0x180010519  test    rbx, rbx
0x18001051c  jz      short loc_180010521
0x18001051e  mov     [rbx], r13d
0x180010521  test    r14, r14
0x180010524  jz      short loc_180010529
0x180010526  mov     [r14], r13d
0x180010529  test    rdi, rdi
0x18001052c  jz      loc_180010752
0x180010532  cmp     [rdi], r13w
0x180010536  jz      loc_180010752
0x18001053c  mov     eax, 532h
0x180010541  mov     [rsp+1C0h+var_174], ax
0x180010546  mov     eax, 533h
0x18001054b  test    r12, r12
0x18001054e  jz      loc_180010757
0x180010554  mov     [rsp+1C0h+var_174], ax
0x180010559  mov     eax, 534h
0x18001055e  test    rbx, rbx
0x180010561  jz      loc_180010757
0x180010567  mov     [rsp+1C0h+var_174], ax
0x18001056c  mov     eax, 535h
0x180010571  test    r14, r14
0x180010574  jz      loc_180010757
0x18001057a  mov     [rsp+1C0h+var_178], r13d
0x18001057f  mov     [rsp+1C0h+var_174], ax
0x180010584  mov     [rbx], r13d
0x180010587  mov     dword ptr [r14], 1
0x18001058e  mov     [rsp+1C0h+hTemplateFile], r13; hTemplateFile
0x180010593  mov     [rsp+1C0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180010598  mov     r8d, 3; dwShareMode
0x18001059e  mov     [rsp+1C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800105a3  xor     r9d, r9d; lpSecurityAttributes
0x1800105a6  xor     edx, edx; dwDesiredAccess
0x1800105a8  mov     rcx, rdi; lpFileName
0x1800105ab  call    cs:__imp_CreateFileW
0x1800105b1  mov     rsi, rax
0x1800105b4  lea     rcx, [rax-1]
0x1800105b8  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800105bc  ja      loc_180010727
0x1800105c2  mov     rdi, r13
0x1800105c5  mov     r15d, 0F0h
0x1800105cb  mov     [rsp+1C0h+var_178], r13d
0x1800105d0  mov     eax, 541h
0x1800105d5  mov     [rsp+1C0h+var_174], ax
0x1800105da  mov     [rsp+1C0h+lpOverlapped], r13; lpOverlapped
0x1800105df  lea     rax, [rsp+1C0h+BytesReturned]
0x1800105e4  mov     [rsp+1C0h+hTemplateFile], rax; lpBytesReturned
0x1800105e9  mov     [rsp+1C0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x1800105ee  lea     rax, [rbp+0C0h+OutBuffer]
0x1800105f2  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rax; lpOutBuffer
0x1800105f7  xor     r9d, r9d; nInBufferSize
0x1800105fa  xor     r8d, r8d; lpInBuffer
0x1800105fd  mov     edx, 2D0C00h; dwIoControlCode
0x180010602  mov     rcx, rsi; hDevice
0x180010605  call    cs:__imp_DeviceIoControl
0x18001060b  test    eax, eax
0x18001060d  jnz     loc_1800106C8
0x180010613  call    cs:__imp_GetLastError
0x180010619  mov     ebx, eax
0x18001061b  cmp     eax, 7Ah ; 'z'
0x18001061e  jz      short loc_180010646
0x180010620  cmp     eax, 0EAh
0x180010625  jz      short loc_180010646
0x180010627  test    eax, eax
0x180010629  jle     short loc_180010634
0x18001062b  movzx   ebx, ax
0x18001062e  or      ebx, 80070000h
0x180010634  mov     [rsp+1C0h+var_178], ebx
0x180010638  mov     eax, 556h
0x18001063d  test    ebx, ebx
0x18001063f  js      short loc_1800106B1
0x180010641  mov     [rsp+1C0h+var_174], ax
0x180010646  test    rdi, rdi
0x180010649  jz      short loc_180010654
0x18001064b  mov     rcx, rdi; pv
0x18001064e  call    cs:__imp_CoTaskMemFree
0x180010654  add     r15d, r15d
0x180010657  mov     ecx, r15d; cb
0x18001065a  call    cs:__imp_CoTaskMemAlloc
0x180010660  mov     rdi, rax
0x180010663  test    rax, rax
0x180010666  mov     eax, 565h
0x18001066b  jz      short loc_1800106B8
0x18001066d  mov     [rsp+1C0h+var_178], r13d
0x180010672  mov     [rsp+1C0h+var_174], ax
0x180010677  mov     rbx, rdi
0x18001067a  mov     [rsp+1C0h+lpOverlapped], r13; lpOverlapped
0x18001067f  lea     rax, [rsp+1C0h+BytesReturned]
0x180010684  mov     [rsp+1C0h+hTemplateFile], rax; lpBytesReturned
0x180010689  mov     [rsp+1C0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x18001068e  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rdi; lpOutBuffer
0x180010693  xor     r9d, r9d; nInBufferSize
0x180010696  xor     r8d, r8d; lpInBuffer
0x180010699  mov     edx, 2D0C00h; dwIoControlCode
0x18001069e  mov     rcx, rsi; hDevice
0x1800106a1  call    cs:__imp_DeviceIoControl
0x1800106a7  test    eax, eax
0x1800106a9  jz      loc_180010613
0x1800106af  jmp     short loc_1800106CC
0x1800106b1  mov     [rsp+1C0h+var_172], ax
0x1800106b6  jmp     short loc_180010713
0x1800106b8  mov     ebx, 8007000Eh
0x1800106bd  mov     [rsp+1C0h+var_178], ebx
0x1800106c1  mov     [rsp+1C0h+var_172], ax
0x1800106c6  jmp     short loc_180010747
0x1800106c8  lea     rbx, [rbp+0C0h+OutBuffer]
0x1800106cc  mov     edx, [rsp+1C0h+BytesReturned]
0x1800106d0  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800106da  mul     rdx
0x1800106dd  shr     rdx, 4
0x1800106e1  lea     r9, [rsp+1C0h+var_17C]
0x1800106e6  mov     r8, r12
0x1800106e9  mov     rcx, rbx
0x1800106ec  call    FindLargestFloppyMediaType
0x1800106f1  mov     ebx, eax
0x1800106f3  mov     [rsp+1C0h+var_178], eax
0x1800106f7  test    eax, eax
0x1800106f9  mov     eax, 577h
0x1800106fe  js      short loc_1800106B1
0x180010700  mov     [rsp+1C0h+var_174], ax
0x180010705  mov     eax, r13d
0x180010708  cmp     [rsp+1C0h+var_17C], r13d
0x18001070d  setz    al
0x180010710  mov     [r14], eax
0x180010713  test    rdi, rdi
0x180010716  jz      short loc_18001073C
0x180010718  mov     rcx, rdi; pv
0x18001071b  call    cs:__imp_CoTaskMemFree
0x180010721  mov     ebx, [rsp+1C0h+var_178]
0x180010725  jmp     short loc_180010747
0x180010727  call    GetLastFailureAsHRESULT
0x18001072c  mov     ebx, eax
0x18001072e  mov     [rsp+1C0h+var_178], eax
0x180010732  mov     eax, 541h
0x180010737  mov     [rsp+1C0h+var_172], ax
0x18001073c  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180010740  jz      short loc_180010765
0x180010742  test    rsi, rsi
0x180010745  jz      short loc_180010765
0x180010747  mov     rcx, rsi; hObject
0x18001074a  call    cs:__imp_CloseHandle
0x180010750  jmp     short loc_180010765
0x180010752  mov     eax, 532h
0x180010757  mov     ebx, 80070057h
0x18001075c  mov     [rsp+1C0h+var_172], ax
0x180010761  mov     [rsp+1C0h+var_178], ebx
0x180010765  lea     rcx, [rsp+1C0h+var_178]; this
0x18001076a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001076f  mov     eax, ebx
0x180010771  mov     rcx, [rbp+0C0h+var_50]
0x180010775  xor     rcx, rsp; StackCookie
0x180010778  call    __security_check_cookie
0x18001077d  add     rsp, 188h
0x180010784  pop     r15
0x180010786  pop     r14
0x180010788  pop     r13
0x18001078a  pop     r12
0x18001078c  pop     rdi
0x18001078d  pop     rsi
0x18001078e  pop     rbx
0x18001078f  pop     rbp
0x180010790  retn
```
