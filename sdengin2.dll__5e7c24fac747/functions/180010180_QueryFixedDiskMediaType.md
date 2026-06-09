# QueryFixedDiskMediaType

- ea: `0x180010180`
- end: `0x180010484`
- name: `QueryFixedDiskMediaType`
- size: `772`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task`

## callees

- `0x18000dfc4`
- `0x180010180`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180010294`
- `KERNEL32!CreateFileW` at `0x180010294`
- `KERNEL32!GetLastError` at `0x1800102ef`
- `KERNEL32!GetLastError` at `0x1800102ef`
- `KERNEL32!CloseHandle` at `0x180010429`
- `KERNEL32!CloseHandle` at `0x180010429`
- `KERNEL32!DeviceIoControl` at `0x1800102e5`
- `KERNEL32!DeviceIoControl` at `0x18001036e`
- `KERNEL32!DeviceIoControl` at `0x1800102e5`
- `KERNEL32!DeviceIoControl` at `0x18001036e`
- `ole32!CoTaskMemFree` at `0x18001040a`
- `ole32!CoTaskMemFree` at `0x18001040a`
- `ole32!CoTaskMemAlloc` at `0x18001032c`
- `ole32!CoTaskMemAlloc` at `0x18001032c`

## pseudocode

```c
__int64 __fastcall QueryFixedDiskMediaType(LPCWSTR lpFileName, int *a2, _DWORD *a3, __int64 a4)
{
  int v8; // r15d
  __int64 v9; // rcx
  int *v10; // rax
  __int16 v11; // ax
  unsigned __int64 v12; // rax
  bool v13; // cc
  __int64 v14; // rcx
  HANDLE FileW; // rsi
  __int64 v16; // rcx
  unsigned int LastFailureAsHRESULT; // ebx
  __int16 v18; // ax
  DWORD v19; // edi
  _DWORD *v20; // rbx
  __int64 v21; // rcx
  __int16 v22; // ax
  int v23; // edi
  int v24; // eax
  int v26; // [rsp+40h] [rbp-49h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-45h] BYREF
  int v28; // [rsp+48h] [rbp-41h] BYREF
  __int16 v29; // [rsp+4Ch] [rbp-3Dh]
  __int16 v30; // [rsp+4Eh] [rbp-3Bh]
  _OWORD OutBuffer[2]; // [rsp+80h] [rbp-9h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v28, "QueryFixedDiskMediaType", 876, 1);
  v8 = 0;
  v26 = 0;
  memset(OutBuffer, 0, sizeof(OutBuffer));
  BytesReturned = 0;
  if ( a2 )
  {
    v9 = 4;
    v10 = a2;
    do
    {
      *(_BYTE *)v10 = 0;
      v10 = (int *)((char *)v10 + 1);
      --v9;
    }
    while ( v9 );
  }
  v11 = 889;
  if ( !lpFileName )
    goto LABEL_37;
  v29 = 889;
  v12 = -1;
  do
    ++v12;
  while ( lpFileName[v12] );
  v13 = v12 <= 2;
  v11 = 890;
  if ( v13 || (v29 = 890, v11 = 891, !a2) || (v29 = 891, v11 = 892, !a3) || (v29 = 892, v11 = 893, !a4) )
  {
LABEL_37:
    LastFailureAsHRESULT = -2147024809;
    v28 = -2147024809;
    v30 = v11;
    goto LABEL_38;
  }
  v28 = 0;
  v29 = 893;
  *a3 = 1;
  FileW = CreateFileW(lpFileName, 0, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14);
    v28 = LastFailureAsHRESULT;
    v30 = 904;
    goto LABEL_38;
  }
  v28 = 0;
  v29 = 904;
  if ( DeviceIoControl(FileW, 0x560000u, 0, 0, OutBuffer, 0x20u, &BytesReturned, 0) || GetLastError() == 234 )
  {
    v28 = 0;
    v29 = 915;
    v19 = 24 * LODWORD(OutBuffer[0]) + 8;
    v20 = CoTaskMemAlloc(v19);
    v18 = 920;
    if ( !v20 )
    {
      LastFailureAsHRESULT = -2147024882;
      v28 = -2147024882;
      goto LABEL_33;
    }
    v28 = 0;
    v29 = 920;
    if ( DeviceIoControl(FileW, 0x560000u, 0, 0, v20, v19, &BytesReturned, 0) )
    {
      v28 = 0;
      v29 = 929;
      v22 = 930;
      if ( *v20 )
      {
        v29 = 930;
        v23 = 0;
        if ( *v20 )
        {
          while ( 1 )
          {
            if ( v8 )
              goto LABEL_25;
            v28 = IsDiskHotPluggable(v20[6 * v23 + 2], &v26);
            if ( v28 < 0 )
              break;
            v29 = 934;
            if ( (unsigned int)++v23 >= *v20 )
            {
              if ( !v26 )
                goto LABEL_27;
LABEL_25:
              v24 = 11;
              goto LABEL_28;
            }
            v8 = v26;
          }
          v30 = 934;
        }
        else
        {
LABEL_27:
          v24 = 6;
LABEL_28:
          *a2 = v24;
        }
        goto LABEL_31;
      }
      v28 = -2147418113;
    }
    else
    {
      v28 = GetLastFailureAsHRESULT(v21);
      v22 = 929;
    }
    v30 = v22;
LABEL_31:
    CoTaskMemFree(v20);
    LastFailureAsHRESULT = v28;
    goto LABEL_34;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v16);
  v28 = LastFailureAsHRESULT;
  v18 = 915;
LABEL_33:
  v30 = v18;
LABEL_34:
  if ( FileW )
    CloseHandle(FileW);
LABEL_38:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v28);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180010180  mov     [rsp-8+arg_18], rbx
0x180010185  push    rbp
0x180010186  push    rsi
0x180010187  push    rdi
0x180010188  push    r12
0x18001018a  push    r13
0x18001018c  push    r14
0x18001018e  push    r15
0x180010190  lea     rbp, [rsp-27h]
0x180010195  sub     rsp, 0B0h
0x18001019c  mov     rax, cs:__security_cookie
0x1800101a3  xor     rax, rsp
0x1800101a6  mov     [rbp+57h+var_40], rax
0x1800101aa  mov     rsi, r9
0x1800101ad  mov     rdi, r8
0x1800101b0  mov     r14, rdx
0x1800101b3  mov     rbx, rcx
0x1800101b6  mov     r9d, 1; unsigned __int16
0x1800101bc  mov     r8d, 36Ch; unsigned __int16
0x1800101c2  lea     rdx, aQueryfixeddisk; "QueryFixedDiskMediaType"
0x1800101c9  lea     rcx, [rbp+57h+var_98]; this
0x1800101cd  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800101d2  xor     r12d, r12d
0x1800101d5  mov     r15d, r12d
0x1800101d8  mov     [rbp+57h+var_A0], r12d
0x1800101dc  xorps   xmm0, xmm0
0x1800101df  movups  [rbp+57h+OutBuffer], xmm0
0x1800101e3  movups  [rbp+57h+var_50], xmm0
0x1800101e7  mov     [rbp+57h+BytesReturned], r12d
0x1800101eb  test    r14, r14
0x1800101ee  jz      short loc_180010204
0x1800101f0  lea     ecx, [r12+4]
0x1800101f5  mov     rax, r14
0x1800101f8  mov     [rax], r12b
0x1800101fb  inc     rax
0x1800101fe  sub     rcx, 1
0x180010202  jnz     short loc_1800101F8
0x180010204  mov     eax, 379h
0x180010209  test    rbx, rbx
0x18001020c  jz      loc_180010446
0x180010212  mov     [rbp+57h+var_94], ax
0x180010216  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001021a  inc     rax
0x18001021d  cmp     [rbx+rax*2], r12w
0x180010222  jnz     short loc_18001021A
0x180010224  cmp     rax, 2
0x180010228  mov     eax, 37Ah
0x18001022d  jbe     loc_180010446
0x180010233  mov     [rbp+57h+var_94], ax
0x180010237  mov     eax, 37Bh
0x18001023c  test    r14, r14
0x18001023f  jz      loc_180010446
0x180010245  mov     [rbp+57h+var_94], ax
0x180010249  mov     eax, 37Ch
0x18001024e  test    rdi, rdi
0x180010251  jz      loc_180010446
0x180010257  mov     [rbp+57h+var_94], ax
0x18001025b  mov     eax, 37Dh
0x180010260  test    rsi, rsi
0x180010263  jz      loc_180010446
0x180010269  mov     [rbp+57h+var_98], r12d
0x18001026d  mov     [rbp+57h+var_94], ax
0x180010271  mov     dword ptr [rdi], 1
0x180010277  mov     [rsp+0E0h+hTemplateFile], r12; hTemplateFile
0x18001027c  mov     [rsp+0E0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180010281  mov     r8d, 3; dwShareMode
0x180010287  mov     [rsp+0E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001028c  xor     r9d, r9d; lpSecurityAttributes
0x18001028f  xor     edx, edx; dwDesiredAccess
0x180010291  mov     rcx, rbx; lpFileName
0x180010294  call    cs:__imp_CreateFileW
0x18001029a  mov     rsi, rax
0x18001029d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800102a1  jz      loc_180010431
0x1800102a7  mov     [rbp+57h+var_98], r12d
0x1800102ab  mov     ecx, 388h
0x1800102b0  mov     [rbp+57h+var_94], cx
0x1800102b4  mov     [rsp+0E0h+lpOverlapped], r12; lpOverlapped
0x1800102b9  lea     rax, [rbp+57h+BytesReturned]
0x1800102bd  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x1800102c2  mov     [rsp+0E0h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x1800102ca  lea     rax, [rbp+57h+OutBuffer]
0x1800102ce  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; lpOutBuffer
0x1800102d3  xor     r9d, r9d; nInBufferSize
0x1800102d6  xor     r8d, r8d; lpInBuffer
0x1800102d9  mov     r13d, 560000h
0x1800102df  mov     edx, r13d; dwIoControlCode
0x1800102e2  mov     rcx, rsi; hDevice
0x1800102e5  call    cs:__imp_DeviceIoControl
0x1800102eb  test    eax, eax
0x1800102ed  jnz     short loc_180010310
0x1800102ef  call    cs:__imp_GetLastError
0x1800102f5  cmp     eax, 0EAh
0x1800102fa  jz      short loc_180010310
0x1800102fc  call    GetLastFailureAsHRESULT
0x180010301  mov     ebx, eax
0x180010303  mov     [rbp+57h+var_98], eax
0x180010306  mov     eax, 393h
0x18001030b  jmp     loc_18001041D
0x180010310  mov     [rbp+57h+var_98], r12d
0x180010314  mov     eax, 393h
0x180010319  mov     [rbp+57h+var_94], ax
0x18001031d  mov     eax, dword ptr [rbp+57h+OutBuffer]
0x180010320  lea     ecx, [rax+rax*2]
0x180010323  lea     edi, ds:8[rcx*8]
0x18001032a  mov     ecx, edi; cb
0x18001032c  call    cs:__imp_CoTaskMemAlloc
0x180010332  mov     rbx, rax
0x180010335  test    rax, rax
0x180010338  mov     eax, 398h
0x18001033d  jz      loc_180010415
0x180010343  mov     [rbp+57h+var_98], r12d
0x180010347  mov     [rbp+57h+var_94], ax
0x18001034b  mov     [rsp+0E0h+lpOverlapped], r12; lpOverlapped
0x180010350  lea     rax, [rbp+57h+BytesReturned]
0x180010354  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x180010359  mov     [rsp+0E0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x18001035d  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rbx; lpOutBuffer
0x180010362  xor     r9d, r9d; nInBufferSize
0x180010365  xor     r8d, r8d; lpInBuffer
0x180010368  mov     edx, r13d; dwIoControlCode
0x18001036b  mov     rcx, rsi; hDevice
0x18001036e  call    cs:__imp_DeviceIoControl
0x180010374  test    eax, eax
0x180010376  jnz     short loc_180010387
0x180010378  call    GetLastFailureAsHRESULT
0x18001037d  mov     [rbp+57h+var_98], eax
0x180010380  mov     eax, 3A1h
0x180010385  jmp     short loc_180010403
0x180010387  mov     [rbp+57h+var_98], r12d
0x18001038b  mov     eax, 3A1h
0x180010390  mov     [rbp+57h+var_94], ax
0x180010394  mov     eax, 3A2h
0x180010399  cmp     [rbx], r12d
0x18001039c  jz      short loc_1800103FC
0x18001039e  mov     [rbp+57h+var_94], ax
0x1800103a2  mov     edi, r12d
0x1800103a5  cmp     [rbx], r12d
0x1800103a8  jbe     short loc_1800103F2
0x1800103aa  lea     r13d, [rax+4]
0x1800103ae  test    r15d, r15d
0x1800103b1  jnz     short loc_1800103E4
0x1800103b3  mov     eax, edi
0x1800103b5  lea     rcx, [rax+rax*2]
0x1800103b9  lea     rdx, [rbp+57h+var_A0]
0x1800103bd  mov     ecx, [rbx+rcx*8+8]
0x1800103c1  call    IsDiskHotPluggable
0x1800103c6  mov     [rbp+57h+var_98], eax
0x1800103c9  test    eax, eax
0x1800103cb  js      short loc_1800103EB
0x1800103cd  mov     [rbp+57h+var_94], r13w
0x1800103d2  inc     edi
0x1800103d4  cmp     edi, [rbx]
0x1800103d6  jnb     short loc_1800103DE
0x1800103d8  mov     r15d, [rbp+57h+var_A0]
0x1800103dc  jmp     short loc_1800103AE
0x1800103de  cmp     [rbp+57h+var_A0], r12d
0x1800103e2  jz      short loc_1800103F2
0x1800103e4  mov     eax, 0Bh
0x1800103e9  jmp     short loc_1800103F7
0x1800103eb  mov     [rbp+57h+var_92], r13w
0x1800103f0  jmp     short loc_180010407
0x1800103f2  mov     eax, 6
0x1800103f7  mov     [r14], eax
0x1800103fa  jmp     short loc_180010407
0x1800103fc  mov     [rbp+57h+var_98], 8000FFFFh
0x180010403  mov     [rbp+57h+var_92], ax
0x180010407  mov     rcx, rbx; pv
0x18001040a  call    cs:__imp_CoTaskMemFree
0x180010410  mov     ebx, [rbp+57h+var_98]
0x180010413  jmp     short loc_180010421
0x180010415  mov     ebx, 8007000Eh
0x18001041a  mov     [rbp+57h+var_98], ebx
0x18001041d  mov     [rbp+57h+var_92], ax
0x180010421  test    rsi, rsi
0x180010424  jz      short loc_180010452
0x180010426  mov     rcx, rsi; hObject
0x180010429  call    cs:__imp_CloseHandle
0x18001042f  jmp     short loc_180010452
0x180010431  call    GetLastFailureAsHRESULT
0x180010436  mov     ebx, eax
0x180010438  mov     [rbp+57h+var_98], eax
0x18001043b  mov     ecx, 388h
0x180010440  mov     [rbp+57h+var_92], cx
0x180010444  jmp     short loc_180010452
0x180010446  mov     ebx, 80070057h
0x18001044b  mov     [rbp+57h+var_98], ebx
0x18001044e  mov     [rbp+57h+var_92], ax
0x180010452  lea     rcx, [rbp+57h+var_98]; this
0x180010456  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001045b  mov     eax, ebx
0x18001045d  mov     rcx, [rbp+57h+var_40]
0x180010461  xor     rcx, rsp; StackCookie
0x180010464  call    __security_check_cookie
0x180010469  mov     rbx, [rsp+0E0h+arg_18]
0x180010471  add     rsp, 0B0h
0x180010478  pop     r15
0x18001047a  pop     r14
0x18001047c  pop     r13
0x18001047e  pop     r12
0x180010480  pop     rdi
0x180010481  pop     rsi
0x180010482  pop     rbp
0x180010483  retn
```
