# SxIsVolumeOnSharedDiskAndOnline(ushort const *,int *)

- ea: `0x18002aad4`
- end: `0x18002ad77`
- name: `?SxIsVolumeOnSharedDiskAndOnline@@YAJPEBGPEAH@Z`
- size: `675`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180014ef0`

## callees

- `0x180020710`
- `0x180020af4`
- `0x18002182c`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002aad4`
- `0x18002d6e8`
- `0x18003532c`
- `0x180035464`
- `0x180035b00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002aca0`
- `KERNEL32!GetLastError` at `0x18002aca0`
- `KERNEL32!CreateFileW` at `0x18002abea`
- `KERNEL32!CreateFileW` at `0x18002abea`
- `KERNEL32!DeviceIoControl` at `0x18002ac96`
- `KERNEL32!DeviceIoControl` at `0x18002ac96`
- `KERNEL32!CloseHandle` at `0x18002ac1f`
- `KERNEL32!CloseHandle` at `0x18002ac1f`

## pseudocode

```c
__int64 __fastcall SxIsVolumeOnSharedDiskAndOnline(const unsigned __int16 *a1, int *a2)
{
  unsigned __int16 v4; // dx
  int LastFailureAsHRESULT; // ebx
  __int16 v6; // ax
  LPCWSTR v7; // r15
  const WCHAR *v8; // rcx
  __int64 v9; // rcx
  HANDLE FileW; // rdi
  __int64 v11; // rdx
  __int64 v12; // r8
  DWORD LastError; // eax
  __int64 v15; // rcx
  const wchar_t *v16; // rax
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-19h] BYREF
  int v18; // [rsp+50h] [rbp-9h] BYREF
  __int16 v19; // [rsp+54h] [rbp-5h]
  __int16 v20; // [rsp+56h] [rbp-3h]
  DWORD BytesReturned; // [rsp+D0h] [rbp+77h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "SxIsVolumeOnSharedDiskAndOnline", 2867, 1);
  BytesReturned = 0;
  lpFileName[0] = &FileName;
  lpFileName[1] = 0;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)lpFileName, a1);
  v18 = LastFailureAsHRESULT;
  v6 = 2875;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_5;
  v19 = 2875;
  CBsString::UnTrailing((CBsString *)lpFileName, v4);
  v6 = 2878;
  if ( !a1 || (v19 = 2878, v6 = 2879, !a2) )
  {
    LastFailureAsHRESULT = -2147024809;
    v18 = -2147024809;
LABEL_5:
    v20 = v6;
    goto LABEL_14;
  }
  v7 = lpFileName[0];
  v8 = lpFileName[0];
  v18 = 0;
  v19 = 2879;
  *a2 = 0;
  FileW = CreateFileW(v8, 0, 3u, 0, 3u, 0, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
    v18 = LastFailureAsHRESULT;
    v20 = 2894;
    goto LABEL_11;
  }
  v19 = 2894;
  v18 = 0;
  if ( DeviceIoControl(FileW, 0x560030u, 0, 0, 0, 0, &BytesReturned, 0) )
  {
    LastFailureAsHRESULT = v18;
    *a2 = 1;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 31 && LastError != 1 )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v15);
      v18 = LastFailureAsHRESULT;
      v20 = 2912;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) == 0 )
        goto LABEL_13;
      WPP_SF_sSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        (unsigned int)&WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
        (unsigned int)"dwError == ERROR_GEN_FAILURE || dwError == ERROR_INVALID_FUNCTION",
        (__int64)v7,
        LastFailureAsHRESULT);
      goto LABEL_28;
    }
    LastFailureAsHRESULT = 0;
    v18 = 0;
    v19 = 2912;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    v16 = &word_18003B6A0;
    if ( !*a2 )
      v16 = L"not";
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      71,
      (unsigned int)&WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
      (_DWORD)a1,
      (__int64)v16);
LABEL_28:
    LastFailureAsHRESULT = v18;
LABEL_13:
    CloseHandle(FileW);
    goto LABEL_14;
  }
LABEL_11:
  if ( FileW != (HANDLE)-1LL && FileW )
    goto LABEL_13;
LABEL_14:
  CBsString::_Release((unsigned __int16 **)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v18, v11, v12);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18002aad4  mov     [rsp-8+arg_0], rbx
0x18002aad9  mov     [rsp-8+arg_8], rsi
0x18002aade  push    rbp
0x18002aadf  push    rdi
0x18002aae0  push    r13
0x18002aae2  push    r14
0x18002aae4  push    r15
0x18002aae6  lea     rbp, [rsp-37h]
0x18002aaeb  sub     rsp, 90h
0x18002aaf2  mov     rsi, rdx
0x18002aaf5  mov     r14, rcx
0x18002aaf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aaff  lea     r13, WPP_GLOBAL_Control
0x18002ab06  cmp     rcx, r13
0x18002ab09  jz      short loc_18002AB29
0x18002ab0b  test    dword ptr [rcx+1Ch], 20000000h
0x18002ab12  jz      short loc_18002AB29
0x18002ab14  mov     rcx, [rcx+10h]
0x18002ab18  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x18002ab1f  mov     edx, 45h ; 'E'
0x18002ab24  call    WPP_SF_
0x18002ab29  mov     r9d, 1; unsigned __int16
0x18002ab2f  lea     rdx, aSxisvolumeonsh; "SxIsVolumeOnSharedDiskAndOnline"
0x18002ab36  mov     r8d, 0B33h; unsigned __int16
0x18002ab3c  lea     rcx, [rbp+57h+var_60]; this
0x18002ab40  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002ab45  lea     rax, FileName
0x18002ab4c  mov     [rbp+57h+BytesReturned], 0
0x18002ab53  mov     rdx, r14; unsigned __int16 *
0x18002ab56  mov     [rbp+57h+lpFileName], rax
0x18002ab5a  lea     rcx, [rbp+57h+lpFileName]; this
0x18002ab5e  mov     [rbp+57h+var_68], 0
0x18002ab66  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18002ab6b  mov     ebx, eax
0x18002ab6d  mov     [rbp+57h+var_60], eax
0x18002ab70  test    eax, eax
0x18002ab72  mov     eax, 0B3Bh
0x18002ab77  jns     short loc_18002AB82
0x18002ab79  mov     [rbp+57h+var_5A], ax
0x18002ab7d  jmp     loc_18002AC25
0x18002ab82  lea     rcx, [rbp+57h+lpFileName]; this
0x18002ab86  mov     [rbp+57h+var_5C], ax
0x18002ab8a  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x18002ab8f  mov     eax, 0B3Eh
0x18002ab94  test    r14, r14
0x18002ab97  jnz     short loc_18002ABA3
0x18002ab99  mov     ebx, 80070057h
0x18002ab9e  mov     [rbp+57h+var_60], ebx
0x18002aba1  jmp     short loc_18002AB79
0x18002aba3  mov     [rbp+57h+var_5C], ax
0x18002aba7  mov     eax, 0B3Fh
0x18002abac  test    rsi, rsi
0x18002abaf  jz      short loc_18002AB99
0x18002abb1  mov     r15, [rbp+57h+lpFileName]
0x18002abb5  mov     r8d, 3; dwShareMode
0x18002abbb  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18002abc4  mov     rcx, r15; lpFileName
0x18002abc7  mov     [rbp+57h+var_60], 0
0x18002abce  xor     r9d, r9d; lpSecurityAttributes
0x18002abd1  mov     [rbp+57h+var_5C], ax
0x18002abd5  xor     edx, edx; dwDesiredAccess
0x18002abd7  mov     [rsp+0B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18002abdf  mov     dword ptr [rsi], 0
0x18002abe5  mov     [rsp+0B0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002abea  call    cs:__imp_CreateFileW
0x18002abf0  mov     rdi, rax
0x18002abf3  inc     rax
0x18002abf6  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002abfc  jnz     short loc_18002AC55
0x18002abfe  call    GetLastFailureAsHRESULT
0x18002ac03  mov     ebx, eax
0x18002ac05  mov     [rbp+57h+var_60], eax
0x18002ac08  mov     eax, 0B4Eh
0x18002ac0d  mov     [rbp+57h+var_5A], ax
0x18002ac11  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002ac15  jz      short loc_18002AC25
0x18002ac17  test    rdi, rdi
0x18002ac1a  jz      short loc_18002AC25
0x18002ac1c  mov     rcx, rdi; hObject
0x18002ac1f  call    cs:__imp_CloseHandle
0x18002ac25  lea     rcx, [rbp+57h+lpFileName]; this
0x18002ac29  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18002ac2e  lea     rcx, [rbp+57h+var_60]; this
0x18002ac32  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002ac37  lea     r11, [rsp+0B0h+var_20]
0x18002ac3f  mov     eax, ebx
0x18002ac41  mov     rbx, [r11+30h]
0x18002ac45  mov     rsi, [r11+38h]
0x18002ac49  mov     rsp, r11
0x18002ac4c  pop     r15
0x18002ac4e  pop     r14
0x18002ac50  pop     r13
0x18002ac52  pop     rdi
0x18002ac53  pop     rbp
0x18002ac54  retn
0x18002ac55  mov     [rsp+0B0h+lpOverlapped], 0; lpOverlapped
0x18002ac5e  mov     eax, 0B4Eh
0x18002ac63  mov     [rbp+57h+var_5C], ax
0x18002ac67  xor     r9d, r9d; nInBufferSize
0x18002ac6a  lea     rax, [rbp+57h+BytesReturned]
0x18002ac6e  mov     [rbp+57h+var_60], 0
0x18002ac75  mov     [rsp+0B0h+hTemplateFile], rax; lpBytesReturned
0x18002ac7a  xor     r8d, r8d; lpInBuffer
0x18002ac7d  mov     [rsp+0B0h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18002ac85  mov     edx, 560030h; dwIoControlCode
0x18002ac8a  mov     rcx, rdi; hDevice
0x18002ac8d  mov     qword ptr [rsp+0B0h+dwCreationDisposition], 0; lpOutBuffer
0x18002ac96  call    cs:__imp_DeviceIoControl
0x18002ac9c  test    eax, eax
0x18002ac9e  jnz     short loc_18002AD17
0x18002aca0  call    cs:__imp_GetLastError
0x18002aca6  cmp     eax, 1Fh
0x18002aca9  jz      short loc_18002AD07
0x18002acab  cmp     eax, 1
0x18002acae  jz      short loc_18002AD07
0x18002acb0  call    GetLastFailureAsHRESULT
0x18002acb5  mov     ebx, eax
0x18002acb7  mov     [rbp+57h+var_60], eax
0x18002acba  mov     eax, 0B60h
0x18002acbf  mov     [rbp+57h+var_5A], ax
0x18002acc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002acca  cmp     rcx, r13
0x18002accd  jz      loc_18002AC1C
0x18002acd3  test    dword ptr [rcx+1Ch], 2000000h
0x18002acda  jz      loc_18002AC1C
0x18002ace0  mov     rcx, [rcx+10h]
0x18002ace4  lea     r9, aDwerrorErrorGe; "dwError == ERROR_GEN_FAILURE || dwError"...
0x18002aceb  mov     edx, 46h ; 'F'
0x18002acf0  mov     [rsp+0B0h+dwFlagsAndAttributes], ebx
0x18002acf4  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x18002acfb  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r15
0x18002ad00  call    WPP_SF_sSd
0x18002ad05  jmp     short loc_18002AD6F
0x18002ad07  xor     ebx, ebx
0x18002ad09  mov     eax, 0B60h
0x18002ad0e  mov     [rbp+57h+var_60], ebx
0x18002ad11  mov     [rbp+57h+var_5C], ax
0x18002ad15  jmp     short loc_18002AD20
0x18002ad17  mov     ebx, [rbp+57h+var_60]
0x18002ad1a  mov     dword ptr [rsi], 1
0x18002ad20  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad27  cmp     rcx, r13
0x18002ad2a  jz      loc_18002AC11
0x18002ad30  test    dword ptr [rcx+1Ch], 8000000h
0x18002ad37  jz      loc_18002AC11
0x18002ad3d  cmp     dword ptr [rsi], 0
0x18002ad40  lea     rdx, aNot; "not"
0x18002ad47  mov     rcx, [rcx+10h]
0x18002ad4b  lea     rax, word_18003B6A0
0x18002ad52  cmovz   rax, rdx
0x18002ad56  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x18002ad5d  mov     edx, 47h ; 'G'
0x18002ad62  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x18002ad67  mov     r9, r14
0x18002ad6a  call    WPP_SF_SS
0x18002ad6f  mov     ebx, [rbp+57h+var_60]
0x18002ad72  jmp     loc_18002AC1C
```
