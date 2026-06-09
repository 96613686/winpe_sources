# SxIsCsvFile(ushort const *,uchar *)

- ea: `0x18002ecd0`
- end: `0x18002eecd`
- name: `?SxIsCsvFile@@YAJPEBGPEAE@Z`
- size: `509`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000c910`
- `0x18001a664`
- `0x180024640`

## callees

- `0x180020710`
- `0x180020908`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`
- `0x18002ecd0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002ed88`
- `KERNEL32!CreateFileW` at `0x18002ed88`
- `KERNEL32!DeviceIoControl` at `0x18002ede7`
- `KERNEL32!DeviceIoControl` at `0x18002ee5c`
- `KERNEL32!DeviceIoControl` at `0x18002ede7`
- `KERNEL32!DeviceIoControl` at `0x18002ee5c`
- `KERNEL32!CloseHandle` at `0x18002eeac`
- `KERNEL32!CloseHandle` at `0x18002eeac`

## pseudocode

```c
__int64 __fastcall SxIsCsvFile(LPCWSTR lpFileName, unsigned __int8 *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int LastFailureAsHRESULT; // ebx
  __int64 v7; // rcx
  HANDLE FileW; // rdi
  int v10; // [rsp+40h] [rbp-19h] BYREF
  __int16 v11; // [rsp+44h] [rbp-15h]
  __int16 v12; // [rsp+46h] [rbp-13h]
  DWORD BytesReturned; // [rsp+C8h] [rbp+6Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "SxIsCsvFile", 2513, 1);
  BytesReturned = 0;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    v12 = 2517;
    v10 = -2147024809;
    goto LABEL_22;
  }
  v10 = 0;
  v11 = 2517;
  *a2 = 0;
  FileW = CreateFileW(lpFileName, 0x100000u, 3u, 0, 3u, 0x2000000u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v11 = 2529;
    v10 = 0;
    if ( DeviceIoControl(FileW, 0x90248u, 0, 0, 0, 0, &BytesReturned, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids, lpFileName);
      *a2 = 1;
      LastFailureAsHRESULT = 0;
      v11 = 2542;
      v10 = 0;
      goto LABEL_21;
    }
    BytesReturned = 0;
    if ( DeviceIoControl(FileW, 0x9025Cu, 0, 0, 0, 0, &BytesReturned, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids, lpFileName);
      *a2 = 1;
      LastFailureAsHRESULT = v10;
      goto LABEL_21;
    }
    LastFailureAsHRESULT = v10;
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7);
    v10 = LastFailureAsHRESULT;
    v12 = 2529;
  }
  if ( FileW != (HANDLE)-1LL && FileW )
LABEL_21:
    CloseHandle(FileW);
LABEL_22:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10, v4, v5);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18002ecd0  push    rbp
0x18002ecd2  push    rbx
0x18002ecd3  push    rsi
0x18002ecd4  push    rdi
0x18002ecd5  push    r14
0x18002ecd7  push    r15
0x18002ecd9  lea     rbp, [rsp-2Fh]
0x18002ecde  sub     rsp, 88h
0x18002ece5  mov     rbx, rdx
0x18002ece8  mov     rsi, rcx
0x18002eceb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ecf2  lea     r15, WPP_GLOBAL_Control
0x18002ecf9  cmp     rcx, r15
0x18002ecfc  jz      short loc_18002ED1C
0x18002ecfe  test    dword ptr [rcx+1Ch], 20000000h
0x18002ed05  jz      short loc_18002ED1C
0x18002ed07  mov     rcx, [rcx+10h]
0x18002ed0b  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18002ed12  mov     edx, 47h ; 'G'
0x18002ed17  call    WPP_SF_
0x18002ed1c  mov     r9d, 1; unsigned __int16
0x18002ed22  lea     rdx, aSxiscsvfile; "SxIsCsvFile"
0x18002ed29  mov     r8d, 9D1h; unsigned __int16
0x18002ed2f  lea     rcx, [rbp+57h+var_70]; this
0x18002ed33  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002ed38  xor     r14d, r14d
0x18002ed3b  mov     eax, 9D5h
0x18002ed40  mov     [rbp+57h+BytesReturned], r14d
0x18002ed44  test    rbx, rbx
0x18002ed47  jnz     short loc_18002ED5A
0x18002ed49  mov     ebx, 80070057h
0x18002ed4e  mov     [rbp+57h+var_6A], ax
0x18002ed52  mov     [rbp+57h+var_70], ebx
0x18002ed55  jmp     loc_18002EEB2
0x18002ed5a  mov     [rsp+0B0h+hTemplateFile], r14; hTemplateFile
0x18002ed5f  mov     r8d, 3; dwShareMode
0x18002ed65  mov     [rbp+57h+var_70], r14d
0x18002ed69  xor     r9d, r9d; lpSecurityAttributes
0x18002ed6c  mov     [rbp+57h+var_6C], ax
0x18002ed70  mov     edx, 100000h; dwDesiredAccess
0x18002ed75  mov     [rsp+0B0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002ed7d  mov     rcx, rsi; lpFileName
0x18002ed80  mov     [rsp+0B0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002ed85  mov     [rbx], r14b
0x18002ed88  call    cs:__imp_CreateFileW
0x18002ed8e  mov     rdi, rax
0x18002ed91  inc     rax
0x18002ed94  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002ed9a  jnz     short loc_18002EDB4
0x18002ed9c  call    GetLastFailureAsHRESULT
0x18002eda1  mov     ebx, eax
0x18002eda3  mov     [rbp+57h+var_70], eax
0x18002eda6  mov     eax, 9E1h
0x18002edab  mov     [rbp+57h+var_6A], ax
0x18002edaf  jmp     loc_18002EE9E
0x18002edb4  mov     [rsp+0B0h+lpOverlapped], r14; lpOverlapped
0x18002edb9  mov     eax, 9E1h
0x18002edbe  mov     [rbp+57h+var_6C], ax
0x18002edc2  xor     r9d, r9d; nInBufferSize
0x18002edc5  lea     rax, [rbp+57h+BytesReturned]
0x18002edc9  mov     [rbp+57h+var_70], r14d
0x18002edcd  mov     [rsp+0B0h+hTemplateFile], rax; lpBytesReturned
0x18002edd2  xor     r8d, r8d; lpInBuffer
0x18002edd5  mov     [rsp+0B0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x18002edda  mov     edx, 90248h; dwIoControlCode
0x18002eddf  mov     rcx, rdi; hDevice
0x18002ede2  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14; lpOutBuffer
0x18002ede7  call    cs:__imp_DeviceIoControl
0x18002eded  test    eax, eax
0x18002edef  jz      short loc_18002EE32
0x18002edf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002edf8  cmp     rcx, r15
0x18002edfb  jz      short loc_18002EE1E
0x18002edfd  test    dword ptr [rcx+1Ch], 10000000h
0x18002ee04  jz      short loc_18002EE1E
0x18002ee06  mov     rcx, [rcx+10h]
0x18002ee0a  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18002ee11  mov     edx, 48h ; 'H'
0x18002ee16  mov     r9, rsi
0x18002ee19  call    WPP_SF_S
0x18002ee1e  mov     byte ptr [rbx], 1
0x18002ee21  mov     eax, 9EEh
0x18002ee26  mov     ebx, r14d
0x18002ee29  mov     [rbp+57h+var_6C], ax
0x18002ee2d  mov     [rbp+57h+var_70], ebx
0x18002ee30  jmp     short loc_18002EEA9
0x18002ee32  mov     [rsp+0B0h+lpOverlapped], r14; lpOverlapped
0x18002ee37  lea     rax, [rbp+57h+BytesReturned]
0x18002ee3b  mov     [rsp+0B0h+hTemplateFile], rax; lpBytesReturned
0x18002ee40  xor     r9d, r9d; nInBufferSize
0x18002ee43  mov     [rsp+0B0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x18002ee48  xor     r8d, r8d; lpInBuffer
0x18002ee4b  mov     edx, 9025Ch; dwIoControlCode
0x18002ee50  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14; lpOutBuffer
0x18002ee55  mov     rcx, rdi; hDevice
0x18002ee58  mov     [rbp+57h+BytesReturned], r14d
0x18002ee5c  call    cs:__imp_DeviceIoControl
0x18002ee62  test    eax, eax
0x18002ee64  jz      short loc_18002EE9B
0x18002ee66  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee6d  cmp     rcx, r15
0x18002ee70  jz      short loc_18002EE93
0x18002ee72  test    dword ptr [rcx+1Ch], 10000000h
0x18002ee79  jz      short loc_18002EE93
0x18002ee7b  mov     rcx, [rcx+10h]
0x18002ee7f  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18002ee86  mov     edx, 49h ; 'I'
0x18002ee8b  mov     r9, rsi
0x18002ee8e  call    WPP_SF_S
0x18002ee93  mov     byte ptr [rbx], 1
0x18002ee96  mov     ebx, [rbp+57h+var_70]
0x18002ee99  jmp     short loc_18002EEA9
0x18002ee9b  mov     ebx, [rbp+57h+var_70]
0x18002ee9e  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002eea2  jz      short loc_18002EEB2
0x18002eea4  test    rdi, rdi
0x18002eea7  jz      short loc_18002EEB2
0x18002eea9  mov     rcx, rdi; hObject
0x18002eeac  call    cs:__imp_CloseHandle
0x18002eeb2  lea     rcx, [rbp+57h+var_70]; this
0x18002eeb6  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002eebb  mov     eax, ebx
0x18002eebd  add     rsp, 88h
0x18002eec4  pop     r15
0x18002eec6  pop     r14
0x18002eec8  pop     rdi
0x18002eec9  pop     rsi
0x18002eeca  pop     rbx
0x18002eecb  pop     rbp
0x18002eecc  retn
```
