# _GetFileAttributesTag

- ea: `0x18000e0dc`
- end: `0x18000e279`
- name: `_GetFileAttributesTag`
- size: `413`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000dc78`

## callees

- `0x180003ce0`
- `0x18000d348`
- `0x18000d43c`
- `0x18000e0dc`
- `0x18000f1e4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000e247`
- `KERNEL32!CloseHandle` at `0x18000e247`
- `KERNEL32!CreateFileW` at `0x18000e19d`
- `KERNEL32!CreateFileW` at `0x18000e19d`
- `ntdll!NtQueryInformationFile` at `0x18000e20c`
- `ntdll!NtQueryInformationFile` at `0x18000e20c`

## pseudocode

```c
__int64 __fastcall GetFileAttributesTag(LPCWSTR lpFileName, _DWORD *a2, __int64 a3)
{
  __int64 v5; // rdx
  __int64 v6; // r8
  HANDLE FileW; // rsi
  int v8; // ebx
  unsigned int v9; // edi
  unsigned int v10; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-19h] BYREF
  int v13; // [rsp+50h] [rbp-9h] BYREF
  __int16 v14; // [rsp+54h] [rbp-5h]
  __int16 v15; // [rsp+56h] [rbp-3h]
  __int64 FileInformation; // [rsp+D0h] [rbp+77h] BYREF

  FileInformation = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "_GetFileAttributesTag", 1567);
  FileInformation = 0;
  IoStatusBlock = 0;
  if ( !lpFileName || !a2 )
  {
    v9 = -2147024809;
    v13 = -2147024809;
    v15 = 1575;
    goto LABEL_15;
  }
  v13 = 0;
  v14 = 1575;
  *a2 = -1;
  FileW = CreateFileW(lpFileName, 0x80u, 7u, 0, 3u, 0x2200000u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v13 = 0;
    v14 = 1596;
    FileInformation = 0;
    v10 = NtQueryInformationFile(FileW, &IoStatusBlock, &FileInformation, 8u, FileAttributeTagInformation);
    v13 = HRESULTFromNTSTATUS(v10);
    v8 = v13;
    if ( v13 >= 0 )
    {
      v8 = 0;
      *a2 = FileInformation;
      v14 = 1608;
      v13 = 0;
    }
    else
    {
      v15 = 1600;
    }
    goto LABEL_13;
  }
  v8 = 1;
  v13 = 1;
  v14 = 1593;
  v9 = 1;
  if ( FileW != (HANDLE)-1LL && FileW )
  {
LABEL_13:
    CloseHandle(FileW);
    v9 = v8;
  }
LABEL_15:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13, v5, v6);
  return v9;
}

```

## disassembly

```asm
0x18000e0dc  mov     [rsp-8+FileInformation], r8
0x18000e0e1  push    rbp
0x18000e0e2  push    rbx
0x18000e0e3  push    rsi
0x18000e0e4  push    rdi
0x18000e0e5  lea     rbp, [rsp-3Fh]
0x18000e0ea  sub     rsp, 98h
0x18000e0f1  mov     rdi, rdx
0x18000e0f4  mov     rbx, rcx
0x18000e0f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0fe  lea     rax, WPP_GLOBAL_Control
0x18000e105  cmp     rcx, rax
0x18000e108  jz      short loc_18000E128
0x18000e10a  test    dword ptr [rcx+1Ch], 20000000h
0x18000e111  jz      short loc_18000E128
0x18000e113  mov     rcx, [rcx+10h]
0x18000e117  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18000e11e  mov     edx, 30h ; '0'
0x18000e123  call    WPP_SF_
0x18000e128  mov     r8d, 61Fh; unsigned __int16
0x18000e12e  lea     rdx, aGetfileattribu; "_GetFileAttributesTag"
0x18000e135  lea     rcx, [rbp+57h+var_60]; this
0x18000e139  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e13e  mov     [rbp+57h+FileInformation], 0
0x18000e146  xorps   xmm0, xmm0
0x18000e149  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000e14d  test    rbx, rbx
0x18000e150  jz      loc_18000E251
0x18000e156  test    rdi, rdi
0x18000e159  jz      loc_18000E251
0x18000e15f  xor     r9d, r9d; lpSecurityAttributes
0x18000e162  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18000e16b  mov     eax, 627h
0x18000e170  mov     [rsp+0B0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18000e178  mov     edx, 80h; dwDesiredAccess
0x18000e17d  mov     [rbp+57h+var_60], 0
0x18000e184  mov     rcx, rbx; lpFileName
0x18000e187  mov     [rbp+57h+var_5C], ax
0x18000e18b  lea     r8d, [r9+7]; dwShareMode
0x18000e18f  mov     dword ptr [rdi], 0FFFFFFFFh
0x18000e195  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000e19d  call    cs:__imp_CreateFileW
0x18000e1a3  mov     rsi, rax
0x18000e1a6  lea     rcx, [rax+1]
0x18000e1aa  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18000e1b1  jnz     short loc_18000E1DB
0x18000e1b3  mov     ebx, 1
0x18000e1b8  mov     eax, 639h
0x18000e1bd  mov     [rbp+57h+var_60], ebx
0x18000e1c0  mov     [rbp+57h+var_5C], ax
0x18000e1c4  mov     edi, ebx
0x18000e1c6  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000e1ca  jz      loc_18000E262
0x18000e1d0  test    rsi, rsi
0x18000e1d3  jz      loc_18000E262
0x18000e1d9  jmp     short loc_18000E244
0x18000e1db  mov     eax, 63Ch
0x18000e1e0  mov     [rbp+57h+var_60], 0
0x18000e1e7  mov     r9d, 8; Length
0x18000e1ed  mov     [rbp+57h+var_5C], ax
0x18000e1f1  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18000e1f5  mov     [rbp+57h+FileInformation], 0
0x18000e1fd  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000e201  mov     [rsp+0B0h+dwCreationDisposition], 23h ; '#'; FileInformationClass
0x18000e209  mov     rcx, rsi; FileHandle
0x18000e20c  call    cs:__imp_NtQueryInformationFile
0x18000e212  mov     ecx, eax
0x18000e214  call    HRESULTFromNTSTATUS
0x18000e219  mov     [rbp+57h+var_60], eax
0x18000e21c  mov     ebx, eax
0x18000e21e  test    eax, eax
0x18000e220  jns     short loc_18000E22D
0x18000e222  mov     eax, 640h
0x18000e227  mov     [rbp+57h+var_5A], ax
0x18000e22b  jmp     short loc_18000E244
0x18000e22d  mov     eax, dword ptr [rbp+57h+FileInformation]
0x18000e230  xor     ebx, ebx
0x18000e232  mov     [rdi], eax
0x18000e234  mov     eax, 648h
0x18000e239  mov     [rbp+57h+var_5C], ax
0x18000e23d  mov     [rbp+57h+var_60], 0
0x18000e244  mov     rcx, rsi; hObject
0x18000e247  call    cs:__imp_CloseHandle
0x18000e24d  mov     edi, ebx
0x18000e24f  jmp     short loc_18000E262
0x18000e251  mov     edi, 80070057h
0x18000e256  mov     eax, 627h
0x18000e25b  mov     [rbp+57h+var_60], edi
0x18000e25e  mov     [rbp+57h+var_5A], ax
0x18000e262  lea     rcx, [rbp+57h+var_60]; this
0x18000e266  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e26b  mov     eax, edi
0x18000e26d  add     rsp, 98h
0x18000e274  pop     rdi
0x18000e275  pop     rsi
0x18000e276  pop     rbx
0x18000e277  pop     rbp
0x18000e278  retn
```
