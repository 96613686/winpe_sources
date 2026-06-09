# _GetFileAttributesTag

- ea: `0x140007954`
- end: `0x140007af2`
- name: `_GetFileAttributesTag`
- size: `414`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x1400074d8`

## callees

- `0x140002e1c`
- `0x140006d58`
- `0x140007954`
- `0x14000e324`
- `0x14000e41c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140007ac0`
- `KERNEL32!CloseHandle` at `0x140007ac0`
- `KERNEL32!CreateFileW` at `0x140007a1b`
- `KERNEL32!CreateFileW` at `0x140007a1b`
- `ntdll!NtQueryInformationFile` at `0x140007a85`
- `ntdll!NtQueryInformationFile` at `0x140007a85`

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
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
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
0x140007954  mov     [rsp-8+FileInformation], r8
0x140007959  push    rbp
0x14000795a  push    rbx
0x14000795b  push    rsi
0x14000795c  push    rdi
0x14000795d  lea     rbp, [rsp-3Fh]
0x140007962  sub     rsp, 98h
0x140007969  mov     rdi, rdx
0x14000796c  mov     rsi, rcx
0x14000796f  mov     rcx, cs:WPP_GLOBAL_Control
0x140007976  lea     rax, WPP_GLOBAL_Control
0x14000797d  cmp     rcx, rax
0x140007980  jz      short loc_1400079A0
0x140007982  test    dword ptr [rcx+1Ch], 20000000h
0x140007989  jz      short loc_1400079A0
0x14000798b  mov     rcx, [rcx+10h]
0x14000798f  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x140007996  mov     edx, 30h ; '0'
0x14000799b  call    WPP_SF_
0x1400079a0  mov     ebx, 1
0x1400079a5  lea     rdx, aGetfileattribu; "_GetFileAttributesTag"
0x1400079ac  mov     r9d, ebx; unsigned __int16
0x1400079af  lea     rcx, [rbp+57h+var_60]; this
0x1400079b3  mov     r8d, 61Fh; unsigned __int16
0x1400079b9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1400079be  mov     [rbp+57h+FileInformation], 0
0x1400079c6  xorps   xmm0, xmm0
0x1400079c9  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400079cd  test    rsi, rsi
0x1400079d0  jz      loc_140007ACA
0x1400079d6  test    rdi, rdi
0x1400079d9  jz      loc_140007ACA
0x1400079df  mov     eax, 627h
0x1400079e4  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x1400079ed  mov     [rsp+0B0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1400079f5  lea     edx, [rbx+7Fh]; dwDesiredAccess
0x1400079f8  xor     r9d, r9d; lpSecurityAttributes
0x1400079fb  mov     [rbp+57h+var_5C], ax
0x1400079ff  lea     r8d, [rbx+6]; dwShareMode
0x140007a03  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x140007a0b  mov     rcx, rsi; lpFileName
0x140007a0e  mov     [rbp+57h+var_60], 0
0x140007a15  mov     dword ptr [rdi], 0FFFFFFFFh
0x140007a1b  call    cs:__imp_CreateFileW
0x140007a21  mov     rsi, rax
0x140007a24  lea     rcx, [rax+1]
0x140007a28  test    rcx, 0FFFFFFFFFFFFFFFEh
0x140007a2f  jnz     short loc_140007A54
0x140007a31  mov     eax, 639h
0x140007a36  mov     [rbp+57h+var_60], ebx
0x140007a39  mov     [rbp+57h+var_5C], ax
0x140007a3d  mov     edi, ebx
0x140007a3f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140007a43  jz      loc_140007ADB
0x140007a49  test    rsi, rsi
0x140007a4c  jz      loc_140007ADB
0x140007a52  jmp     short loc_140007ABD
0x140007a54  mov     eax, 63Ch
0x140007a59  mov     [rbp+57h+var_60], 0
0x140007a60  mov     r9d, 8; Length
0x140007a66  mov     [rbp+57h+var_5C], ax
0x140007a6a  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140007a6e  mov     [rbp+57h+FileInformation], 0
0x140007a76  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140007a7a  mov     [rsp+0B0h+dwCreationDisposition], 23h ; '#'; FileInformationClass
0x140007a82  mov     rcx, rsi; FileHandle
0x140007a85  call    cs:__imp_NtQueryInformationFile
0x140007a8b  mov     ecx, eax
0x140007a8d  call    HRESULTFromNTSTATUS
0x140007a92  mov     [rbp+57h+var_60], eax
0x140007a95  mov     ebx, eax
0x140007a97  test    eax, eax
0x140007a99  jns     short loc_140007AA6
0x140007a9b  mov     eax, 640h
0x140007aa0  mov     [rbp+57h+var_5A], ax
0x140007aa4  jmp     short loc_140007ABD
0x140007aa6  mov     eax, dword ptr [rbp+57h+FileInformation]
0x140007aa9  xor     ebx, ebx
0x140007aab  mov     [rdi], eax
0x140007aad  mov     eax, 648h
0x140007ab2  mov     [rbp+57h+var_5C], ax
0x140007ab6  mov     [rbp+57h+var_60], 0
0x140007abd  mov     rcx, rsi; hObject
0x140007ac0  call    cs:__imp_CloseHandle
0x140007ac6  mov     edi, ebx
0x140007ac8  jmp     short loc_140007ADB
0x140007aca  mov     edi, 80070057h
0x140007acf  mov     eax, 627h
0x140007ad4  mov     [rbp+57h+var_60], edi
0x140007ad7  mov     [rbp+57h+var_5A], ax
0x140007adb  lea     rcx, [rbp+57h+var_60]; this
0x140007adf  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140007ae4  mov     eax, edi
0x140007ae6  add     rsp, 98h
0x140007aed  pop     rdi
0x140007aee  pop     rsi
0x140007aef  pop     rbx
0x140007af0  pop     rbp
0x140007af1  retn
```
