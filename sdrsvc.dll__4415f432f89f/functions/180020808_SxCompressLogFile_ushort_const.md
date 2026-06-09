# SxCompressLogFile(ushort const *)

- ea: `0x180020808`
- end: `0x180020974`
- name: `?SxCompressLogFile@@YAJPEBG@Z`
- size: `364`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001698c`
- `0x180021068`

## callees

- `0x18000ea0c`
- `0x18001586c`
- `0x180015974`
- `0x18001c58c`
- `0x180020808`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002094e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002094e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002089f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002089f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002091e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002091e`

## string_xrefs

- `0x180020856`: `SxCompressLogFile`

## pseudocode

```c
__int64 __fastcall SxCompressLogFile(LPCWSTR lpFileName)
{
  char *FileW; // rdi
  unsigned int LastFailureAsHRESULT; // ebx
  __int64 v4; // rcx
  unsigned int v6; // [rsp+40h] [rbp-40h] BYREF
  __int16 v7; // [rsp+44h] [rbp-3Ch]
  __int16 v8; // [rsp+46h] [rbp-3Ah]
  __int16 InBuffer; // [rsp+98h] [rbp+18h] BYREF
  DWORD BytesReturned; // [rsp+A0h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v6, "SxCompressLogFile", 247, 1);
  InBuffer = 1;
  BytesReturned = 0;
  FileW = (char *)CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v6 = 0;
    v7 = 261;
    if ( DeviceIoControl(FileW, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
    {
      LastFailureAsHRESULT = 0;
      v6 = 0;
      v7 = 270;
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v4);
      v6 = LastFailureAsHRESULT;
      v8 = 270;
    }
    goto LABEL_11;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(FileW + 1);
  v6 = LastFailureAsHRESULT;
  v8 = 261;
  if ( FileW != (char *)-1LL && FileW )
LABEL_11:
    CloseHandle(FileW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v6);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180020808  mov     [rsp-8+arg_0], rbx
0x18002080d  mov     [rsp-8+arg_18], rdi
0x180020812  push    rbp
0x180020813  mov     rbp, rsp
0x180020816  sub     rsp, 80h
0x18002081d  mov     rbx, rcx
0x180020820  mov     rcx, cs:WPP_GLOBAL_Control
0x180020827  lea     rax, WPP_GLOBAL_Control
0x18002082e  cmp     rcx, rax
0x180020831  jz      short loc_180020851
0x180020833  test    dword ptr [rcx+1Ch], 20000000h
0x18002083a  jz      short loc_180020851
0x18002083c  mov     rcx, [rcx+10h]
0x180020840  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x180020847  mov     edx, 0Eh
0x18002084c  call    WPP_SF_
0x180020851  mov     edi, 1
0x180020856  lea     rdx, aSxcompresslogf; "SxCompressLogFile"
0x18002085d  mov     r9d, edi; unsigned __int16
0x180020860  lea     rcx, [rbp+var_40]; this
0x180020864  mov     r8d, 0F7h; unsigned __int16
0x18002086a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002086f  lea     r8d, [rdi+2]; dwShareMode
0x180020873  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18002087c  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180020884  xor     r9d, r9d; lpSecurityAttributes
0x180020887  mov     edx, 0C0000000h; dwDesiredAccess
0x18002088c  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x180020891  mov     rcx, rbx; lpFileName
0x180020894  mov     [rbp+InBuffer], di
0x180020898  mov     [rbp+BytesReturned], 0
0x18002089f  call    cs:__imp_CreateFileW
0x1800208a5  mov     rdi, rax
0x1800208a8  lea     rcx, [rax+1]
0x1800208ac  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1800208b3  jnz     short loc_1800208D9
0x1800208b5  call    GetLastFailureAsHRESULT
0x1800208ba  mov     ebx, eax
0x1800208bc  mov     [rbp+var_40], eax
0x1800208bf  mov     eax, 105h
0x1800208c4  mov     [rbp+var_3A], ax
0x1800208c8  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800208cc  jz      loc_180020954
0x1800208d2  test    rdi, rdi
0x1800208d5  jz      short loc_180020954
0x1800208d7  jmp     short loc_18002094B
0x1800208d9  mov     [rsp+80h+lpOverlapped], 0; lpOverlapped
0x1800208e2  lea     r8, [rbp+InBuffer]; lpInBuffer
0x1800208e6  mov     eax, 105h
0x1800208eb  mov     [rbp+var_40], 0
0x1800208f2  mov     [rbp+var_3C], ax
0x1800208f6  mov     r9d, 2; nInBufferSize
0x1800208fc  lea     rax, [rbp+BytesReturned]
0x180020900  mov     edx, 9C040h; dwIoControlCode
0x180020905  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x18002090a  mov     rcx, rdi; hDevice
0x18002090d  mov     [rsp+80h+dwFlagsAndAttributes], 0; nOutBufferSize
0x180020915  mov     qword ptr [rsp+80h+dwCreationDisposition], 0; lpOutBuffer
0x18002091e  call    cs:__imp_DeviceIoControl
0x180020924  test    eax, eax
0x180020926  jnz     short loc_18002093D
0x180020928  call    GetLastFailureAsHRESULT
0x18002092d  mov     ebx, eax
0x18002092f  mov     [rbp+var_40], eax
0x180020932  mov     eax, 10Eh
0x180020937  mov     [rbp+var_3A], ax
0x18002093b  jmp     short loc_18002094B
0x18002093d  xor     ebx, ebx
0x18002093f  mov     eax, 10Eh
0x180020944  mov     [rbp+var_40], ebx
0x180020947  mov     [rbp+var_3C], ax
0x18002094b  mov     rcx, rdi; hObject
0x18002094e  call    cs:__imp_CloseHandle
0x180020954  lea     rcx, [rbp+var_40]; this
0x180020958  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002095d  lea     r11, [rsp+80h+var_s0]
0x180020965  mov     eax, ebx
0x180020967  mov     rbx, [r11+10h]
0x18002096b  mov     rdi, [r11+28h]
0x18002096f  mov     rsp, r11
0x180020972  pop     rbp
0x180020973  retn
```
