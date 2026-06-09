# GetExtentsFromVolumePath

- ea: `0x180008e84`
- end: `0x1800090dc`
- name: `GetExtentsFromVolumePath`
- size: `600`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180008c78`

## callees

- `0x180008d5c`
- `0x180008e84`
- `0x1800090e4`
- `0x1800094e4`
- `0x1800319f0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180008f83`
- `KERNEL32!HeapFree` at `0x1800090cb`
- `KERNEL32!HeapFree` at `0x180008f83`
- `KERNEL32!HeapFree` at `0x1800090cb`
- `KERNEL32!HeapAlloc` at `0x180008fe4`
- `KERNEL32!HeapAlloc` at `0x180008fe4`
- `KERNEL32!GetProcessHeap` at `0x180008f6f`
- `KERNEL32!GetProcessHeap` at `0x180008fcc`
- `KERNEL32!GetProcessHeap` at `0x1800090b7`
- `KERNEL32!GetProcessHeap` at `0x180008f6f`
- `KERNEL32!GetProcessHeap` at `0x180008fcc`
- `KERNEL32!GetProcessHeap` at `0x1800090b7`
- `KERNEL32!CloseHandle` at `0x180008f5a`
- `KERNEL32!CloseHandle` at `0x180008f5a`
- `KERNEL32!SetLastError` at `0x180008eb7`
- `KERNEL32!SetLastError` at `0x180008eb7`
- `KERNEL32!DeviceIoControl` at `0x18000903f`
- `KERNEL32!DeviceIoControl` at `0x18000903f`
- `KERNEL32!CreateFileW` at `0x180008f17`
- `KERNEL32!CreateFileW` at `0x180008f17`
- `ntdll!RtlSetThreadErrorMode` at `0x180008ee4`
- `ntdll!RtlSetThreadErrorMode` at `0x180008f96`
- `ntdll!RtlSetThreadErrorMode` at `0x180008ee4`
- `ntdll!RtlSetThreadErrorMode` at `0x180008f96`
- `ntdll!RtlGetThreadErrorMode` at `0x180008ecf`
- `ntdll!RtlGetThreadErrorMode` at `0x180008ecf`

## pseudocode

```c
_DWORD *__fastcall GetExtentsFromVolumePath(LPCWSTR lpFileName, int a2)
{
  ULONG v5; // r12d
  _DWORD *v6; // rdi
  ULONG ThreadErrorMode; // ebx
  HANDLE FileW; // rax
  void *v9; // r14
  int v10; // ebp
  _DWORD *VolumeDiskExtentsByHandle; // rax
  HANDLE v12; // rax
  HANDLE ProcessHeap; // rax
  _DWORD *v14; // rax
  __int64 DriveLayout; // rax
  void *v16; // rsi
  __int64 v17; // rdx
  int v18; // r8d
  HANDLE v19; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-48h] BYREF
  __int64 OutBuffer; // [rsp+48h] [rbp-40h] BYREF
  int v22; // [rsp+50h] [rbp-38h]

  if ( !lpFileName )
  {
    SetLastError(0x57u);
    return 0;
  }
  v5 = 0;
  v6 = 0;
  ThreadErrorMode = RtlGetThreadErrorMode();
  if ( RtlSetThreadErrorMode(ThreadErrorMode | 0x10, 0) >= 0 )
    v5 = ThreadErrorMode;
  FileW = CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  v9 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    v10 = 0;
    VolumeDiskExtentsByHandle = (_DWORD *)GetVolumeDiskExtentsByHandle(FileW);
    v6 = VolumeDiskExtentsByHandle;
    if ( VolumeDiskExtentsByHandle )
    {
      if ( *VolumeDiskExtentsByHandle == 1 || (unsigned int)IsVolumeRetainedByHandle(v9) )
LABEL_9:
        v10 = 1;
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v14 = HeapAlloc(ProcessHeap, 8u, 0x38u);
      v6 = v14;
      if ( v14 )
      {
        OutBuffer = 0;
        v22 = 0;
        BytesReturned = 0;
        *v14 = 1;
        if ( DeviceIoControl(v9, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &BytesReturned, 0) )
        {
          v6[2] = HIDWORD(OutBuffer);
          if ( a2 )
          {
            if ( v22 )
            {
              DriveLayout = GetDriveLayout();
              v16 = (void *)DriveLayout;
              if ( DriveLayout )
              {
                v17 = 0;
                if ( *(_DWORD *)(DriveLayout + 4) )
                {
                  v18 = v22;
                  do
                  {
                    if ( v10 )
                      break;
                    if ( v18 == *(_DWORD *)(DriveLayout + 144 * v17 + 72) )
                    {
                      v10 = 1;
                      *((_QWORD *)v6 + 2) = *(_QWORD *)(DriveLayout + 144 * v17 + 56);
                      *((_QWORD *)v6 + 3) = *(_QWORD *)(DriveLayout + 144 * v17 + 64);
                    }
                    v17 = (unsigned int)(v17 + 1);
                  }
                  while ( (unsigned int)v17 < *(_DWORD *)(DriveLayout + 4) );
                }
                v19 = GetProcessHeap();
                HeapFree(v19, 0, v16);
              }
            }
            goto LABEL_10;
          }
          goto LABEL_9;
        }
      }
    }
LABEL_10:
    CloseHandle(v9);
    if ( !v10 )
    {
      if ( v6 )
      {
        v12 = GetProcessHeap();
        HeapFree(v12, 0, v6);
        v6 = 0;
      }
    }
  }
  RtlSetThreadErrorMode(v5, 0);
  return v6;
}

```

## disassembly

```asm
0x180008e84  mov     [rsp+arg_8], rbx
0x180008e89  mov     [rsp+arg_10], rbp
0x180008e8e  push    rsi
0x180008e8f  push    rdi
0x180008e90  push    r12
0x180008e92  push    r14
0x180008e94  push    r15
0x180008e96  sub     rsp, 60h
0x180008e9a  mov     rax, cs:__security_cookie
0x180008ea1  xor     rax, rsp
0x180008ea4  mov     [rsp+88h+var_30], rax
0x180008ea9  mov     r15d, edx
0x180008eac  mov     rsi, rcx
0x180008eaf  test    rcx, rcx
0x180008eb2  jnz     short loc_180008ECA
0x180008eb4  lea     ecx, [rsi+57h]; dwErrCode
0x180008eb7  call    cs:__imp_SetLastError
0x180008ebe  nop     dword ptr [rax+rax+00h]
0x180008ec3  xor     eax, eax
0x180008ec5  jmp     loc_180008FA5
0x180008eca  xor     r12d, r12d
0x180008ecd  xor     edi, edi
0x180008ecf  call    cs:__imp_RtlGetThreadErrorMode
0x180008ed6  nop     dword ptr [rax+rax+00h]
0x180008edb  mov     ecx, eax
0x180008edd  xor     edx, edx; OldMode
0x180008edf  or      ecx, 10h; NewMode
0x180008ee2  mov     ebx, eax
0x180008ee4  call    cs:__imp_RtlSetThreadErrorMode
0x180008eeb  nop     dword ptr [rax+rax+00h]
0x180008ef0  mov     [rsp+88h+hTemplateFile], rdi; hTemplateFile
0x180008ef5  lea     r8d, [rdi+3]; dwShareMode
0x180008ef9  test    eax, eax
0x180008efb  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180008f03  mov     edx, 80000000h; dwDesiredAccess
0x180008f08  mov     [rsp+88h+dwCreationDisposition], r8d; dwCreationDisposition
0x180008f0d  cmovns  r12d, ebx
0x180008f11  mov     rcx, rsi; lpFileName
0x180008f14  xor     r9d, r9d; lpSecurityAttributes
0x180008f17  call    cs:__imp_CreateFileW
0x180008f1e  nop     dword ptr [rax+rax+00h]
0x180008f23  mov     r14, rax
0x180008f26  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008f2a  jz      short loc_180008F91
0x180008f2c  mov     rcx, rax; hDevice
0x180008f2f  xor     ebp, ebp
0x180008f31  call    GetVolumeDiskExtentsByHandle
0x180008f36  mov     rdi, rax
0x180008f39  test    rax, rax
0x180008f3c  jz      loc_180008FCC
0x180008f42  lea     ebx, [rbp+1]
0x180008f45  cmp     [rax], ebx
0x180008f47  jz      short loc_180008F55
0x180008f49  mov     rcx, r14
0x180008f4c  call    IsVolumeRetainedByHandle
0x180008f51  test    eax, eax
0x180008f53  jz      short loc_180008F57
0x180008f55  mov     ebp, ebx
0x180008f57  mov     rcx, r14; hObject
0x180008f5a  call    cs:__imp_CloseHandle
0x180008f61  nop     dword ptr [rax+rax+00h]
0x180008f66  test    ebp, ebp
0x180008f68  jnz     short loc_180008F91
0x180008f6a  test    rdi, rdi
0x180008f6d  jz      short loc_180008F91
0x180008f6f  call    cs:__imp_GetProcessHeap
0x180008f76  nop     dword ptr [rax+rax+00h]
0x180008f7b  mov     r8, rdi; lpMem
0x180008f7e  xor     edx, edx; dwFlags
0x180008f80  mov     rcx, rax; hHeap
0x180008f83  call    cs:__imp_HeapFree
0x180008f8a  nop     dword ptr [rax+rax+00h]
0x180008f8f  xor     edi, edi
0x180008f91  xor     edx, edx; OldMode
0x180008f93  mov     ecx, r12d; NewMode
0x180008f96  call    cs:__imp_RtlSetThreadErrorMode
0x180008f9d  nop     dword ptr [rax+rax+00h]
0x180008fa2  mov     rax, rdi
0x180008fa5  mov     rcx, [rsp+88h+var_30]
0x180008faa  xor     rcx, rsp; StackCookie
0x180008fad  call    __security_check_cookie
0x180008fb2  lea     r11, [rsp+88h+var_28]
0x180008fb7  mov     rbx, [r11+38h]
0x180008fbb  mov     rbp, [r11+40h]
0x180008fbf  mov     rsp, r11
0x180008fc2  pop     r15
0x180008fc4  pop     r14
0x180008fc6  pop     r12
0x180008fc8  pop     rdi
0x180008fc9  pop     rsi
0x180008fca  retn
0x180008fcc  call    cs:__imp_GetProcessHeap
0x180008fd3  nop     dword ptr [rax+rax+00h]
0x180008fd8  mov     edx, 8; dwFlags
0x180008fdd  mov     rcx, rax; hHeap
0x180008fe0  lea     r8d, [rdx+30h]; dwBytes
0x180008fe4  call    cs:__imp_HeapAlloc
0x180008feb  nop     dword ptr [rax+rax+00h]
0x180008ff0  mov     rdi, rax
0x180008ff3  test    rax, rax
0x180008ff6  jz      loc_180008F57
0x180008ffc  xor     eax, eax
0x180008ffe  xor     r9d, r9d; nInBufferSize
0x180009001  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x180009006  xor     r8d, r8d; lpInBuffer
0x180009009  mov     [rsp+88h+OutBuffer], rax
0x18000900e  mov     edx, 2D1080h; dwIoControlCode
0x180009013  mov     [rsp+88h+var_38], eax
0x180009017  mov     rcx, r14; hDevice
0x18000901a  lea     ebx, [rax+1]
0x18000901d  mov     [rsp+88h+BytesReturned], eax
0x180009021  lea     rax, [rsp+88h+BytesReturned]
0x180009026  mov     [rdi], ebx
0x180009028  mov     [rsp+88h+hTemplateFile], rax; lpBytesReturned
0x18000902d  lea     rax, [rsp+88h+OutBuffer]
0x180009032  mov     [rsp+88h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x18000903a  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; lpOutBuffer
0x18000903f  call    cs:__imp_DeviceIoControl
0x180009046  nop     dword ptr [rax+rax+00h]
0x18000904b  test    eax, eax
0x18000904d  jz      loc_180008F57
0x180009053  mov     ecx, dword ptr [rsp+88h+OutBuffer+4]
0x180009057  mov     [rdi+8], ecx
0x18000905a  test    r15d, r15d
0x18000905d  jz      loc_180008F55
0x180009063  cmp     [rsp+88h+var_38], ebp
0x180009067  jbe     loc_180008F57
0x18000906d  call    GetDriveLayout
0x180009072  mov     rsi, rax
0x180009075  test    rax, rax
0x180009078  jz      loc_180008F57
0x18000907e  xor     edx, edx
0x180009080  cmp     [rax+4], edx
0x180009083  jbe     short loc_1800090B7
0x180009085  mov     r8d, [rsp+88h+var_38]
0x18000908a  test    ebp, ebp
0x18000908c  jnz     short loc_1800090B7
0x18000908e  lea     rcx, [rdx+rdx*8]
0x180009092  add     rcx, rcx
0x180009095  cmp     r8d, [rsi+rcx*8+48h]
0x18000909a  jnz     short loc_1800090B0
0x18000909c  mov     rax, [rsi+rcx*8+38h]
0x1800090a1  mov     ebp, ebx
0x1800090a3  mov     [rdi+10h], rax
0x1800090a7  mov     rax, [rsi+rcx*8+40h]
0x1800090ac  mov     [rdi+18h], rax
0x1800090b0  add     edx, ebx
0x1800090b2  cmp     edx, [rsi+4]
0x1800090b5  jb      short loc_18000908A
0x1800090b7  call    cs:__imp_GetProcessHeap
0x1800090be  nop     dword ptr [rax+rax+00h]
0x1800090c3  mov     r8, rsi; lpMem
0x1800090c6  xor     edx, edx; dwFlags
0x1800090c8  mov     rcx, rax; hHeap
0x1800090cb  call    cs:__imp_HeapFree
0x1800090d2  nop     dword ptr [rax+rax+00h]
0x1800090d7  jmp     loc_180008F57
```
