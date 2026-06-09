# _GetFileAttributesTag

- ea: `0x18001e098`
- end: `0x18001e2d3`
- name: `_GetFileAttributesTag`
- size: `571`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x18001cecc`
- `0x18001d4dc`

## callees

- `0x18000ea0c`
- `0x1800150f4`
- `0x18001586c`
- `0x180015974`
- `0x18001c58c`
- `0x18001c61c`
- `0x18001e098`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e293`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e293`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e17c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001e17c`
- `ntdll!NtQueryInformationFile` at `0x18001e251`
- `ntdll!NtQueryInformationFile` at `0x18001e251`

## pseudocode

```c
__int64 __fastcall GetFileAttributesTag(LPCWSTR lpFileName, _DWORD *a2, _DWORD *a3, int a4)
{
  unsigned int LastFailureAsHRESULT; // ebx
  HANDLE FileW; // rax
  __int64 v10; // rcx
  void *v11; // rdi
  unsigned int v12; // eax
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-31h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-19h] BYREF
  int v16; // [rsp+50h] [rbp-9h] BYREF
  __int16 v17; // [rsp+54h] [rbp-5h]
  __int16 v18; // [rsp+56h] [rbp-3h]
  __int64 FileInformation; // [rsp+C0h] [rbp+67h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  LastFailureAsHRESULT = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "_GetFileAttributesTag", 1567, 1);
  FileInformation = 0;
  IoStatusBlock = 0;
  if ( a3 )
    *a3 = 0;
  if ( !lpFileName || !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    v16 = -2147024809;
    v18 = 1575;
    goto LABEL_25;
  }
  v16 = 0;
  v17 = 1575;
  *a2 = -1;
  FileW = CreateFileW(lpFileName, 0x80u, 7u, 0, 3u, 0x2200000u, 0);
  v11 = FileW;
  if ( a4 )
  {
    if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v16 = 1;
      v17 = 1593;
      goto LABEL_15;
    }
LABEL_18:
    v16 = 0;
    v17 = 1596;
    FileInformation = 0;
    v12 = NtQueryInformationFile(FileW, &IoStatusBlock, &FileInformation, 8u, FileAttributeTagInformation);
    v16 = HRESULTFromNTSTATUS(v12);
    LastFailureAsHRESULT = v16;
    if ( v16 >= 0 )
    {
      *a2 = FileInformation;
      if ( a3 )
        *a3 = HIDWORD(FileInformation);
      LastFailureAsHRESULT = 0;
      v16 = 0;
      v17 = 1608;
    }
    else
    {
      v18 = 1600;
    }
    goto LABEL_23;
  }
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_18;
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
  v16 = LastFailureAsHRESULT;
  v18 = 1596;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    LODWORD(dwFlagsAndAttributes) = LastFailureAsHRESULT;
    WPP_SF_sSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      49,
      (unsigned int)WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids,
      (unsigned int)"sh.IsValid()",
      (__int64)lpFileName,
      dwFlagsAndAttributes);
    LastFailureAsHRESULT = v16;
  }
LABEL_15:
  if ( v11 != (void *)-1LL && v11 )
LABEL_23:
    CloseHandle(v11);
LABEL_25:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001e098  mov     [rsp-8+arg_8], rbx
0x18001e09d  mov     [rsp-8+arg_10], rsi
0x18001e0a2  push    rbp
0x18001e0a3  push    rdi
0x18001e0a4  push    r12
0x18001e0a6  push    r14
0x18001e0a8  push    r15
0x18001e0aa  lea     rbp, [rsp-37h]
0x18001e0af  sub     rsp, 90h
0x18001e0b6  mov     r12d, r9d
0x18001e0b9  mov     rsi, r8
0x18001e0bc  mov     r14, rdx
0x18001e0bf  mov     r15, rcx
0x18001e0c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0c9  lea     rax, WPP_GLOBAL_Control
0x18001e0d0  cmp     rcx, rax
0x18001e0d3  jz      short loc_18001E0F3
0x18001e0d5  test    dword ptr [rcx+1Ch], 20000000h
0x18001e0dc  jz      short loc_18001E0F3
0x18001e0de  mov     rcx, [rcx+10h]
0x18001e0e2  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18001e0e9  mov     edx, 30h ; '0'
0x18001e0ee  call    WPP_SF_
0x18001e0f3  mov     ebx, 1
0x18001e0f8  lea     rdx, aGetfileattribu; "_GetFileAttributesTag"
0x18001e0ff  mov     r9d, ebx; unsigned __int16
0x18001e102  lea     rcx, [rbp+57h+var_60]; this
0x18001e106  mov     r8d, 61Fh; unsigned __int16
0x18001e10c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001e111  mov     [rbp+57h+FileInformation], 0
0x18001e119  xorps   xmm0, xmm0
0x18001e11c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18001e120  test    rsi, rsi
0x18001e123  jz      short loc_18001E12B
0x18001e125  mov     dword ptr [rsi], 0
0x18001e12b  test    r15, r15
0x18001e12e  jz      loc_18001E29B
0x18001e134  test    r14, r14
0x18001e137  jz      loc_18001E29B
0x18001e13d  xor     r9d, r9d; lpSecurityAttributes
0x18001e140  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18001e149  mov     eax, 627h
0x18001e14e  mov     dword ptr [rsp+0B0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18001e156  mov     edx, 80h; dwDesiredAccess
0x18001e15b  mov     [rbp+57h+var_60], 0
0x18001e162  mov     rcx, r15; lpFileName
0x18001e165  mov     [rbp+57h+var_5C], ax
0x18001e169  lea     r8d, [r9+7]; dwShareMode
0x18001e16d  mov     dword ptr [r14], 0FFFFFFFFh
0x18001e174  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18001e17c  call    cs:__imp_CreateFileW
0x18001e182  mov     rdi, rax
0x18001e185  test    r12d, r12d
0x18001e188  jz      short loc_18001E1A9
0x18001e18a  lea     rcx, [rax+1]
0x18001e18e  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18001e195  jnz     loc_18001E220
0x18001e19b  mov     eax, 639h
0x18001e1a0  mov     [rbp+57h+var_60], ebx
0x18001e1a3  mov     [rbp+57h+var_5C], ax
0x18001e1a7  jmp     short loc_18001E20B
0x18001e1a9  inc     rax
0x18001e1ac  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001e1b2  jnz     short loc_18001E220
0x18001e1b4  call    GetLastFailureAsHRESULT
0x18001e1b9  mov     ebx, eax
0x18001e1bb  mov     [rbp+57h+var_60], eax
0x18001e1be  mov     eax, 63Ch
0x18001e1c3  mov     [rbp+57h+var_5A], ax
0x18001e1c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1ce  lea     rax, WPP_GLOBAL_Control
0x18001e1d5  cmp     rcx, rax
0x18001e1d8  jz      short loc_18001E20B
0x18001e1da  test    dword ptr [rcx+1Ch], 2000000h
0x18001e1e1  jz      short loc_18001E20B
0x18001e1e3  mov     rcx, [rcx+10h]
0x18001e1e7  lea     r9, aShIsvalid; "sh.IsValid()"
0x18001e1ee  mov     edx, 31h ; '1'
0x18001e1f3  mov     dword ptr [rsp+0B0h+dwFlagsAndAttributes], ebx
0x18001e1f7  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18001e1fe  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r15
0x18001e203  call    WPP_SF_sSd
0x18001e208  mov     ebx, [rbp+57h+var_60]
0x18001e20b  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001e20f  jz      loc_18001E2AC
0x18001e215  test    rdi, rdi
0x18001e218  jz      loc_18001E2AC
0x18001e21e  jmp     short loc_18001E290
0x18001e220  mov     eax, 63Ch
0x18001e225  mov     [rbp+57h+var_60], 0
0x18001e22c  mov     r9d, 8; Length
0x18001e232  mov     [rbp+57h+var_5C], ax
0x18001e236  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18001e23a  mov     [rbp+57h+FileInformation], 0
0x18001e242  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001e246  mov     [rsp+0B0h+dwCreationDisposition], 23h ; '#'; FileInformationClass
0x18001e24e  mov     rcx, rdi; FileHandle
0x18001e251  call    cs:__imp_NtQueryInformationFile
0x18001e257  mov     ecx, eax
0x18001e259  call    HRESULTFromNTSTATUS
0x18001e25e  mov     [rbp+57h+var_60], eax
0x18001e261  mov     ebx, eax
0x18001e263  test    eax, eax
0x18001e265  jns     short loc_18001E272
0x18001e267  mov     eax, 640h
0x18001e26c  mov     [rbp+57h+var_5A], ax
0x18001e270  jmp     short loc_18001E290
0x18001e272  mov     eax, dword ptr [rbp+57h+FileInformation]
0x18001e275  mov     [r14], eax
0x18001e278  test    rsi, rsi
0x18001e27b  jz      short loc_18001E282
0x18001e27d  mov     eax, dword ptr [rbp+57h+FileInformation+4]
0x18001e280  mov     [rsi], eax
0x18001e282  xor     ebx, ebx
0x18001e284  mov     eax, 648h
0x18001e289  mov     [rbp+57h+var_60], ebx
0x18001e28c  mov     [rbp+57h+var_5C], ax
0x18001e290  mov     rcx, rdi; hObject
0x18001e293  call    cs:__imp_CloseHandle
0x18001e299  jmp     short loc_18001E2AC
0x18001e29b  mov     ebx, 80070057h
0x18001e2a0  mov     eax, 627h
0x18001e2a5  mov     [rbp+57h+var_60], ebx
0x18001e2a8  mov     [rbp+57h+var_5A], ax
0x18001e2ac  lea     rcx, [rbp+57h+var_60]; this
0x18001e2b0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001e2b5  lea     r11, [rsp+0B0h+var_20]
0x18001e2bd  mov     eax, ebx
0x18001e2bf  mov     rbx, [r11+38h]
0x18001e2c3  mov     rsi, [r11+40h]
0x18001e2c7  mov     rsp, r11
0x18001e2ca  pop     r15
0x18001e2cc  pop     r14
0x18001e2ce  pop     r12
0x18001e2d0  pop     rdi
0x18001e2d1  pop     rbp
0x18001e2d2  retn
```
