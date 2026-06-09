# _GetFileAttributesTag

- ea: `0x18002f10c`
- end: `0x18002f2aa`
- name: `_GetFileAttributesTag`
- size: `414`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18002ea8c`

## callees

- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d778`
- `0x18002f10c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002f1d3`
- `KERNEL32!CreateFileW` at `0x18002f1d3`
- `KERNEL32!CloseHandle` at `0x18002f278`
- `KERNEL32!CloseHandle` at `0x18002f278`
- `ntdll!NtQueryInformationFile` at `0x18002f23d`
- `ntdll!NtQueryInformationFile` at `0x18002f23d`

## pseudocode

```c
__int64 __fastcall GetFileAttributesTag(LPCWSTR lpFileName, _DWORD *a2, __int64 a3)
{
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  HANDLE FileW; // rsi
  unsigned int v9; // edi
  unsigned int v10; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-19h] BYREF
  int v13; // [rsp+50h] [rbp-9h] BYREF
  __int16 v14; // [rsp+54h] [rbp-5h]
  __int16 v15; // [rsp+56h] [rbp-3h]
  __int64 FileInformation; // [rsp+D0h] [rbp+77h] BYREF

  FileInformation = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  v5 = 1;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "_GetFileAttributesTag", 1567, 1);
  FileInformation = 0;
  IoStatusBlock = 0;
  if ( !lpFileName || !a2 )
  {
    v9 = -2147024809;
    v13 = -2147024809;
    v15 = 1575;
    goto LABEL_15;
  }
  v14 = 1575;
  v13 = 0;
  *a2 = -1;
  FileW = CreateFileW(lpFileName, 0x80u, 7u, 0, 3u, 0x2200000u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v13 = 0;
    v14 = 1596;
    FileInformation = 0;
    v10 = NtQueryInformationFile(FileW, &IoStatusBlock, &FileInformation, 8u, FileAttributeTagInformation);
    v13 = HRESULTFromNTSTATUS(v10);
    v5 = v13;
    if ( v13 >= 0 )
    {
      v5 = 0;
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
  v13 = 1;
  v14 = 1593;
  v9 = 1;
  if ( FileW != (HANDLE)-1LL && FileW )
  {
LABEL_13:
    CloseHandle(FileW);
    v9 = v5;
  }
LABEL_15:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13, v6, v7);
  return v9;
}

```

## disassembly

```asm
0x18002f10c  mov     [rsp-8+FileInformation], r8
0x18002f111  push    rbp
0x18002f112  push    rbx
0x18002f113  push    rsi
0x18002f114  push    rdi
0x18002f115  lea     rbp, [rsp-3Fh]
0x18002f11a  sub     rsp, 98h
0x18002f121  mov     rdi, rdx
0x18002f124  mov     rsi, rcx
0x18002f127  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f12e  lea     rax, WPP_GLOBAL_Control
0x18002f135  cmp     rcx, rax
0x18002f138  jz      short loc_18002F158
0x18002f13a  test    dword ptr [rcx+1Ch], 20000000h
0x18002f141  jz      short loc_18002F158
0x18002f143  mov     rcx, [rcx+10h]
0x18002f147  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18002f14e  mov     edx, 30h ; '0'
0x18002f153  call    WPP_SF_
0x18002f158  mov     ebx, 1
0x18002f15d  lea     rdx, aGetfileattribu; "_GetFileAttributesTag"
0x18002f164  mov     r9d, ebx; unsigned __int16
0x18002f167  lea     rcx, [rbp+57h+var_60]; this
0x18002f16b  mov     r8d, 61Fh; unsigned __int16
0x18002f171  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002f176  mov     [rbp+57h+FileInformation], 0
0x18002f17e  xorps   xmm0, xmm0
0x18002f181  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18002f185  test    rsi, rsi
0x18002f188  jz      loc_18002F282
0x18002f18e  test    rdi, rdi
0x18002f191  jz      loc_18002F282
0x18002f197  mov     eax, 627h
0x18002f19c  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18002f1a5  mov     [rsp+0B0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18002f1ad  lea     edx, [rbx+7Fh]; dwDesiredAccess
0x18002f1b0  xor     r9d, r9d; lpSecurityAttributes
0x18002f1b3  mov     [rbp+57h+var_5C], ax
0x18002f1b7  lea     r8d, [rbx+6]; dwShareMode
0x18002f1bb  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002f1c3  mov     rcx, rsi; lpFileName
0x18002f1c6  mov     [rbp+57h+var_60], 0
0x18002f1cd  mov     dword ptr [rdi], 0FFFFFFFFh
0x18002f1d3  call    cs:__imp_CreateFileW
0x18002f1d9  mov     rsi, rax
0x18002f1dc  lea     rcx, [rax+1]
0x18002f1e0  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18002f1e7  jnz     short loc_18002F20C
0x18002f1e9  mov     eax, 639h
0x18002f1ee  mov     [rbp+57h+var_60], ebx
0x18002f1f1  mov     [rbp+57h+var_5C], ax
0x18002f1f5  mov     edi, ebx
0x18002f1f7  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002f1fb  jz      loc_18002F293
0x18002f201  test    rsi, rsi
0x18002f204  jz      loc_18002F293
0x18002f20a  jmp     short loc_18002F275
0x18002f20c  mov     eax, 63Ch
0x18002f211  mov     [rbp+57h+var_60], 0
0x18002f218  mov     r9d, 8; Length
0x18002f21e  mov     [rbp+57h+var_5C], ax
0x18002f222  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18002f226  mov     [rbp+57h+FileInformation], 0
0x18002f22e  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002f232  mov     [rsp+0B0h+dwCreationDisposition], 23h ; '#'; FileInformationClass
0x18002f23a  mov     rcx, rsi; FileHandle
0x18002f23d  call    cs:__imp_NtQueryInformationFile
0x18002f243  mov     ecx, eax
0x18002f245  call    HRESULTFromNTSTATUS
0x18002f24a  mov     [rbp+57h+var_60], eax
0x18002f24d  mov     ebx, eax
0x18002f24f  test    eax, eax
0x18002f251  jns     short loc_18002F25E
0x18002f253  mov     eax, 640h
0x18002f258  mov     [rbp+57h+var_5A], ax
0x18002f25c  jmp     short loc_18002F275
0x18002f25e  mov     eax, dword ptr [rbp+57h+FileInformation]
0x18002f261  xor     ebx, ebx
0x18002f263  mov     [rdi], eax
0x18002f265  mov     eax, 648h
0x18002f26a  mov     [rbp+57h+var_5C], ax
0x18002f26e  mov     [rbp+57h+var_60], 0
0x18002f275  mov     rcx, rsi; hObject
0x18002f278  call    cs:__imp_CloseHandle
0x18002f27e  mov     edi, ebx
0x18002f280  jmp     short loc_18002F293
0x18002f282  mov     edi, 80070057h
0x18002f287  mov     eax, 627h
0x18002f28c  mov     [rbp+57h+var_60], edi
0x18002f28f  mov     [rbp+57h+var_5A], ax
0x18002f293  lea     rcx, [rbp+57h+var_60]; this
0x18002f297  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002f29c  mov     eax, edi
0x18002f29e  add     rsp, 98h
0x18002f2a5  pop     rdi
0x18002f2a6  pop     rsi
0x18002f2a7  pop     rbx
0x18002f2a8  pop     rbp
0x18002f2a9  retn
```
