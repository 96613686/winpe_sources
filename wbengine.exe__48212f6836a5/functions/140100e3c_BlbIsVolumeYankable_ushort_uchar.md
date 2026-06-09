# BlbIsVolumeYankable(ushort *,uchar *)

- ea: `0x140100e3c`
- end: `0x14010111c`
- name: `?BlbIsVolumeYankable@@YAJPEAGPEAE@Z`
- size: `736`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x14010158c`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x140014260`
- `0x14003c434`
- `0x140088ba4`
- `0x140100e3c`
- `0x1401169a8`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140100ea0`
- `KERNEL32!CreateFileW` at `0x140100ea0`
- `KERNEL32!CloseHandle` at `0x1401010b2`
- `KERNEL32!CloseHandle` at `0x1401010b2`
- `KERNEL32!GetLastError` at `0x140100eb3`
- `KERNEL32!GetLastError` at `0x140100f67`
- `KERNEL32!GetLastError` at `0x140100eb3`
- `KERNEL32!GetLastError` at `0x140100f67`
- `KERNEL32!DeviceIoControl` at `0x140100f5d`
- `KERNEL32!DeviceIoControl` at `0x140100f5d`
- `ole32!CoTaskMemAlloc` at `0x140100f15`
- `ole32!CoTaskMemAlloc` at `0x140100f15`
- `ole32!CoTaskMemFree` at `0x140100f88`
- `ole32!CoTaskMemFree` at `0x140101066`
- `ole32!CoTaskMemFree` at `0x1401010cd`
- `ole32!CoTaskMemFree` at `0x140100f88`
- `ole32!CoTaskMemFree` at `0x140101066`
- `ole32!CoTaskMemFree` at `0x1401010cd`

## pseudocode

```c
__int64 __fastcall BlbIsVolumeYankable(unsigned __int16 *a1, unsigned __int8 *a2)
{
  int v3; // edi
  signed int IsDiskYankable; // ebx
  void *v5; // rsi
  DWORD v6; // eax
  PVOID *v7; // rcx
  unsigned int v8; // eax
  _DWORD *v9; // rax
  _DWORD *v10; // rdi
  DWORD LastError; // eax
  unsigned __int8 v12; // r15
  unsigned int v13; // r14d
  __int64 v14; // rsi
  HANDLE FileW; // [rsp+40h] [rbp-10h]
  int v17; // [rsp+90h] [rbp+40h]
  unsigned __int8 v18; // [rsp+98h] [rbp+48h] BYREF
  size_t Size; // [rsp+A0h] [rbp+50h] BYREF
  LPCWSTR lpFileName; // [rsp+A8h] [rbp+58h] BYREF

  v17 = (int)a1;
  *a2 = 0;
  v3 = (int)a1;
  lpFileName = 0;
  LODWORD(Size) = 0;
  v18 = 0;
  IsDiskYankable = BlbutilRemoveTrailingBackslash(a1, (unsigned __int16 **)&lpFileName);
  if ( IsDiskYankable < 0 )
  {
LABEL_39:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_40;
  }
  FileW = CreateFileW(lpFileName, 0, 3u, 0, 3u, 0, 0);
  v5 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v8 = 32;
    LODWORD(Size) = 32;
    while ( 1 )
    {
      v9 = CoTaskMemAlloc(v8);
      v10 = v9;
      if ( !v9 )
        break;
      memset_0(v9, 0, (unsigned int)Size);
      if ( DeviceIoControl(FileW, 0x560000u, 0, 0, v10, Size, (LPDWORD)&Size, 0) )
      {
        if ( (unsigned int)Size < 8 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids);
          }
          IsDiskYankable = -2147024362;
        }
        else
        {
          v12 = 0;
          v13 = ((int)Size - 8) / 0x18u;
          if ( v13 != *v10 )
            BlbAssert(
              "base\\stor\\blb\\engine\\blbengutils\\blbvolumeutils.cpp",
              0xA6u,
              "cDiskExtents == pExtents->NumberOfDiskExtents");
          v14 = 0;
          IsDiskYankable = 0;
          while ( (unsigned int)v14 < v13 )
          {
            IsDiskYankable = BlbIsDiskYankable(v10[6 * v14 + 2], &v18);
            if ( IsDiskYankable < 0 )
              goto LABEL_30;
            if ( v18 )
            {
              v12 = 1;
              break;
            }
            v14 = (unsigned int)(v14 + 1);
          }
          *a2 = v12;
LABEL_30:
          v5 = FileW;
        }
        goto LABEL_31;
      }
      LastError = GetLastError();
      IsDiskYankable = LastError;
      if ( LastError != 234 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            (unsigned int)WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids,
            (_DWORD)lpFileName,
            LastError);
        }
        if ( IsDiskYankable > 0 )
          IsDiskYankable = (unsigned __int16)IsDiskYankable | 0x80070000;
LABEL_31:
        CoTaskMemFree(v10);
        goto LABEL_38;
      }
      LODWORD(Size) = 24 * *v10 + 8;
      CoTaskMemFree(v10);
      v8 = Size;
    }
    IsDiskYankable = -2147024882;
LABEL_38:
    CloseHandle(v5);
    v3 = v17;
    goto LABEL_39;
  }
  v6 = GetLastError();
  IsDiskYankable = v6;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids,
      (_DWORD)lpFileName,
      v6);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( IsDiskYankable > 0 )
    IsDiskYankable = (unsigned __int16)IsDiskYankable | 0x80070000;
LABEL_40:
  if ( lpFileName )
  {
    CoTaskMemFree((LPVOID)lpFileName);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( IsDiskYankable < 0 && v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 2u )
    WPP_SF_Sd(
      (unsigned int)v7[2],
      13,
      (unsigned int)WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids,
      v3,
      IsDiskYankable);
  return (unsigned int)IsDiskYankable;
}

```

## disassembly

```asm
0x140100e3c  mov     [rsp-38h+arg_0], rcx
0x140100e41  push    rbp
0x140100e42  push    rbx
0x140100e43  push    rsi
0x140100e44  push    rdi
0x140100e45  push    r13
0x140100e47  push    r14
0x140100e49  push    r15
0x140100e4b  mov     rbp, rsp
0x140100e4e  sub     rsp, 50h
0x140100e52  xor     r14d, r14d
0x140100e55  mov     r13, rdx
0x140100e58  mov     [rdx], r14b
0x140100e5b  mov     rdi, rcx
0x140100e5e  lea     rdx, [rbp+lpFileName]; unsigned __int16 **
0x140100e62  mov     [rbp+lpFileName], r14
0x140100e66  mov     dword ptr [rbp+Size], r14d
0x140100e6a  mov     [rbp+arg_8], r14b
0x140100e6e  call    ?BlbutilRemoveTrailingBackslash@@YAJPEBGPEAPEAG@Z; BlbutilRemoveTrailingBackslash(ushort const *,ushort * *)
0x140100e73  lea     r15, WPP_GLOBAL_Control
0x140100e7a  mov     ebx, eax
0x140100e7c  test    eax, eax
0x140100e7e  js      loc_1401010BC
0x140100e84  mov     rcx, [rbp+lpFileName]; lpFileName
0x140100e88  lea     r8d, [r14+3]; dwShareMode
0x140100e8c  mov     [rsp+50h+hTemplateFile], r14; hTemplateFile
0x140100e91  xor     r9d, r9d; lpSecurityAttributes
0x140100e94  mov     [rsp+50h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x140100e99  xor     edx, edx; dwDesiredAccess
0x140100e9b  mov     [rsp+50h+dwCreationDisposition], r8d; dwCreationDisposition
0x140100ea0  call    cs:__imp_CreateFileW
0x140100ea6  mov     [rbp+var_10], rax
0x140100eaa  mov     rsi, rax
0x140100ead  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140100eb1  jnz     short loc_140100F0B
0x140100eb3  call    cs:__imp_GetLastError
0x140100eb9  mov     ebx, eax
0x140100ebb  mov     rcx, cs:WPP_GLOBAL_Control
0x140100ec2  cmp     rcx, r15
0x140100ec5  jz      short loc_140100EF5
0x140100ec7  test    byte ptr [rcx+1Ch], 1
0x140100ecb  jz      short loc_140100EF5
0x140100ecd  cmp     byte ptr [rcx+19h], 2
0x140100ed1  jb      short loc_140100EF5
0x140100ed3  mov     r9, [rbp+lpFileName]
0x140100ed7  lea     edx, [rsi+0Bh]
0x140100eda  mov     rcx, [rcx+10h]
0x140100ede  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x140100ee5  mov     [rsp+50h+dwCreationDisposition], eax
0x140100ee9  call    WPP_SF_Sd
0x140100eee  mov     rcx, cs:WPP_GLOBAL_Control
0x140100ef5  test    ebx, ebx
0x140100ef7  jle     loc_1401010C3
0x140100efd  movzx   ebx, bx
0x140100f00  or      ebx, 80070000h
0x140100f06  jmp     loc_1401010C3
0x140100f0b  mov     eax, 20h ; ' '
0x140100f10  mov     dword ptr [rbp+Size], eax
0x140100f13  mov     ecx, eax; cb
0x140100f15  call    cs:__imp_CoTaskMemAlloc
0x140100f1b  mov     rdi, rax
0x140100f1e  test    rax, rax
0x140100f21  jz      loc_1401010AA
0x140100f27  mov     r8d, dword ptr [rbp+Size]; Size
0x140100f2b  xor     edx, edx; Val
0x140100f2d  mov     rcx, rax; void *
0x140100f30  call    memset_0
0x140100f35  lea     rax, [rbp+Size]
0x140100f39  mov     [rsp+50h+lpOverlapped], r14; lpOverlapped
0x140100f3e  mov     [rsp+50h+hTemplateFile], rax; lpBytesReturned
0x140100f43  xor     r9d, r9d; nInBufferSize
0x140100f46  mov     eax, dword ptr [rbp+Size]
0x140100f49  xor     r8d, r8d; lpInBuffer
0x140100f4c  mov     [rsp+50h+dwFlagsAndAttributes], eax; nOutBufferSize
0x140100f50  mov     edx, 560000h; dwIoControlCode
0x140100f55  mov     rcx, rsi; hDevice
0x140100f58  mov     qword ptr [rsp+50h+dwCreationDisposition], rdi; lpOutBuffer
0x140100f5d  call    cs:__imp_DeviceIoControl
0x140100f63  test    eax, eax
0x140100f65  jnz     short loc_140100FDE
0x140100f67  call    cs:__imp_GetLastError
0x140100f6d  mov     ebx, eax
0x140100f6f  cmp     eax, 0EAh
0x140100f74  jnz     short loc_140100F93
0x140100f76  mov     eax, [rdi]
0x140100f78  lea     ecx, [rax+rax*2]
0x140100f7b  lea     ecx, ds:8[rcx*8]
0x140100f82  mov     dword ptr [rbp+Size], ecx
0x140100f85  mov     rcx, rdi; pv
0x140100f88  call    cs:__imp_CoTaskMemFree
0x140100f8e  mov     eax, dword ptr [rbp+Size]
0x140100f91  jmp     short loc_140100F13
0x140100f93  mov     rcx, cs:WPP_GLOBAL_Control
0x140100f9a  cmp     rcx, r15
0x140100f9d  jz      short loc_140100FC8
0x140100f9f  test    byte ptr [rcx+1Ch], 1
0x140100fa3  jz      short loc_140100FC8
0x140100fa5  cmp     byte ptr [rcx+19h], 2
0x140100fa9  jb      short loc_140100FC8
0x140100fab  mov     r9, [rbp+lpFileName]
0x140100faf  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x140100fb6  mov     rcx, [rcx+10h]
0x140100fba  mov     edx, 0Bh
0x140100fbf  mov     [rsp+50h+dwCreationDisposition], ebx
0x140100fc3  call    WPP_SF_Sd
0x140100fc8  test    ebx, ebx
0x140100fca  jle     loc_140101063
0x140100fd0  movzx   ebx, bx
0x140100fd3  or      ebx, 80070000h
0x140100fd9  jmp     loc_140101063
0x140100fde  mov     r9d, dword ptr [rbp+Size]
0x140100fe2  cmp     r9d, 8
0x140100fe6  jb      loc_14010106E
0x140100fec  mov     r15b, r14b
0x140100fef  lea     ecx, [r9-8]
0x140100ff3  mov     rax, 0AAAAAAAAAAAAAAABh
0x140100ffd  mul     rcx
0x140101000  mov     r14, rdx
0x140101003  shr     r14, 4
0x140101007  cmp     r14d, [rdi]
0x14010100a  jz      short loc_140101024
0x14010100c  lea     r8, aCdiskextentsPe; "cDiskExtents == pExtents->NumberOfDiskE"...
0x140101013  mov     edx, 0A6h; unsigned int
0x140101018  lea     rcx, aBaseStorBlbEng_43; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x14010101f  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140101024  xor     esi, esi
0x140101026  xor     ebx, ebx
0x140101028  cmp     esi, r14d
0x14010102b  jnb     short loc_140101051
0x14010102d  lea     rcx, [rsi+rsi*2]
0x140101031  mov     ecx, [rdi+rcx*8+8]; unsigned int
0x140101035  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x140101039  call    ?BlbIsDiskYankable@@YAJKPEAE@Z; BlbIsDiskYankable(ulong,uchar *)
0x14010103e  mov     ebx, eax
0x140101040  test    eax, eax
0x140101042  js      short loc_140101055
0x140101044  cmp     [rbp+arg_8], r15b
0x140101048  jnz     short loc_14010104E
0x14010104a  inc     esi
0x14010104c  jmp     short loc_140101028
0x14010104e  mov     r15b, 1
0x140101051  mov     [r13+0], r15b
0x140101055  mov     rsi, [rbp+var_10]
0x140101059  lea     r15, WPP_GLOBAL_Control
0x140101060  xor     r14d, r14d
0x140101063  mov     rcx, rdi; pv
0x140101066  call    cs:__imp_CoTaskMemFree
0x14010106c  jmp     short loc_1401010AF
0x14010106e  mov     rcx, cs:WPP_GLOBAL_Control
0x140101075  cmp     rcx, r15
0x140101078  jz      short loc_1401010A3
0x14010107a  test    byte ptr [rcx+1Ch], 1
0x14010107e  jz      short loc_1401010A3
0x140101080  cmp     byte ptr [rcx+19h], 2
0x140101084  jb      short loc_1401010A3
0x140101086  mov     rcx, [rcx+10h]
0x14010108a  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x140101091  mov     edx, 0Ch
0x140101096  mov     [rsp+50h+dwCreationDisposition], 8
0x14010109e  call    WPP_SF_dd
0x1401010a3  mov     ebx, 80070216h
0x1401010a8  jmp     short loc_140101063
0x1401010aa  mov     ebx, 8007000Eh
0x1401010af  mov     rcx, rsi; hObject
0x1401010b2  call    cs:__imp_CloseHandle
0x1401010b8  mov     rdi, [rbp+arg_0]
0x1401010bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1401010c3  cmp     [rbp+lpFileName], r14
0x1401010c7  jz      short loc_1401010DA
0x1401010c9  mov     rcx, [rbp+lpFileName]; pv
0x1401010cd  call    cs:__imp_CoTaskMemFree
0x1401010d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1401010da  test    ebx, ebx
0x1401010dc  jns     short loc_14010110B
0x1401010de  cmp     rcx, r15
0x1401010e1  jz      short loc_14010110B
0x1401010e3  test    byte ptr [rcx+1Ch], 1
0x1401010e7  jz      short loc_14010110B
0x1401010e9  cmp     byte ptr [rcx+19h], 2
0x1401010ed  jb      short loc_14010110B
0x1401010ef  mov     rcx, [rcx+10h]
0x1401010f3  lea     r8, WPP_ac926ebcd8713fa3b2309f2035630ff8_Traceguids
0x1401010fa  mov     edx, 0Dh
0x1401010ff  mov     [rsp+50h+dwCreationDisposition], ebx
0x140101103  mov     r9, rdi
0x140101106  call    WPP_SF_Sd
0x14010110b  mov     eax, ebx
0x14010110d  add     rsp, 50h
0x140101111  pop     r15
0x140101113  pop     r14
0x140101115  pop     r13
0x140101117  pop     rdi
0x140101118  pop     rsi
0x140101119  pop     rbx
0x14010111a  pop     rbp
0x14010111b  retn
```
