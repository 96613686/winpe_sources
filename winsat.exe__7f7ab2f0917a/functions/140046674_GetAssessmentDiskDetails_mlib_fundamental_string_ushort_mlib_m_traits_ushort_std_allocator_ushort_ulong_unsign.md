# GetAssessmentDiskDetails(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,ulong &,unsigned __int64 &)

- ea: `0x140046674`
- end: `0x1400468a0`
- name: `?GetAssessmentDiskDetails@@YAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAKAEA_K@Z`
- size: `556`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14000d65c`
- `0x140026110`
- `0x14004d72c`
- `0x14006be5c`

## callees

- `0x140001abc`
- `0x140003164`
- `0x140003611`
- `0x1400196bc`
- `0x140019a1c`
- `0x140046674`
- `0x140046f94`
- `0x14004752c`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1400467b4`
- `KERNEL32!DeviceIoControl` at `0x1400467b4`
- `KERNEL32!CreateFileW` at `0x14004670b`
- `KERNEL32!CreateFileW` at `0x14004670b`
- `KERNEL32!CloseHandle` at `0x1400467e9`
- `KERNEL32!CloseHandle` at `0x14004687e`
- `KERNEL32!CloseHandle` at `0x1400467e9`
- `KERNEL32!CloseHandle` at `0x14004687e`
- `KERNEL32!GetLastError` at `0x14004671f`
- `KERNEL32!GetLastError` at `0x1400467be`
- `KERNEL32!GetLastError` at `0x14004671f`
- `KERNEL32!GetLastError` at `0x1400467be`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall GetAssessmentDiskDetails(__int64 a1, unsigned int *a2, unsigned __int64 *a3)
{
  int *v6; // rsi
  unsigned int SystemDriveLetter; // ebx
  __int64 FileW; // r14
  signed int LastError; // eax
  int i; // ebx
  DWORD v11; // ebx
  int *v12; // rax
  unsigned int *v13; // r15
  signed int v14; // eax
  __int64 v15; // r9
  unsigned int *v16; // r8
  unsigned int j; // r10d
  unsigned int v18; // ecx
  DWORD BytesReturned; // [rsp+40h] [rbp-48h] BYREF
  __int64 v21; // [rsp+48h] [rbp-40h]
  unsigned int *v22; // [rsp+50h] [rbp-38h]
  int v23; // [rsp+A8h] [rbp+20h] BYREF

  v6 = 0;
  v22 = 0;
  v21 = -1;
  BytesReturned = 0;
  LOWORD(v23) = 0;
  SystemDriveLetter = GetSystemDriveLetter((unsigned __int16 *)&v23);
  if ( (SystemDriveLetter & 0x80000000) == 0 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::reserve(
      a1,
      16);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
      a1,
      L"\\\\.\\%C:",
      (unsigned __int16)v23);
    FileW = (__int64)CreateFileW(*(LPCWSTR *)(*(_QWORD *)a1 + 24LL), 0, 3u, 0, 3u, 0x80u, 0);
    v21 = FileW;
    if ( FileW == -1 )
    {
      LastError = GetLastError();
      SystemDriveLetter = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      for ( i = 1; ; i = *v6 )
      {
        if ( v6 )
          operator delete(v6);
        v11 = 24 * i + 32;
        v12 = (int *)operator new[](v11, (const struct std::nothrow_t *)std::nothrow);
        v6 = v12;
        v22 = (unsigned int *)v12;
        if ( !v12 )
        {
          SystemDriveLetter = -2147024882;
          goto LABEL_23;
        }
        memset_0(v12, 0, v11);
        v13 = (unsigned int *)(v6 + 2);
        if ( DeviceIoControl((HANDLE)FileW, 0x560000u, 0, 0, v6, v11, &BytesReturned, 0) )
          break;
        v14 = GetLastError();
        SystemDriveLetter = v14;
        if ( v14 != 234 )
        {
          if ( v14 > 0 )
            SystemDriveLetter = (unsigned __int16)v14 | 0x80070000;
          goto LABEL_22;
        }
      }
      CloseHandle((HANDLE)FileW);
      FileW = -1;
      v21 = -1;
      v15 = (unsigned int)*v6;
      if ( BytesReturned >= (unsigned __int64)(24 * v15 + 8) )
      {
        v16 = (unsigned int *)(v6 + 2);
        for ( j = 1; j < (unsigned int)v15; ++j )
        {
          if ( *(_QWORD *)&v13[6 * j + 4] > *((_QWORD *)v16 + 2) )
            v16 = &v13[6 * j];
        }
        v18 = *v16;
        *a2 = *v16;
        SystemDriveLetter = GetPhysicalDiskSize(v18, a3);
      }
      else
      {
        SystemDriveLetter = -2147024883;
      }
LABEL_22:
      operator delete(v6);
      if ( FileW == -1 )
        return SystemDriveLetter;
LABEL_23:
      CloseHandle((HANDLE)FileW);
    }
  }
  return SystemDriveLetter;
}

```

## disassembly

```asm
0x140046674  mov     rax, rsp
0x140046677  mov     [rax+8], rbx
0x14004667b  mov     [rax+10h], rsi
0x14004667f  push    rdi
0x140046680  push    r12
0x140046682  push    r13
0x140046684  push    r14
0x140046686  push    r15
0x140046688  sub     rsp, 60h
0x14004668c  mov     r12, r8
0x14004668f  mov     r13, rdx
0x140046692  mov     r14, rcx
0x140046695  xor     edi, edi
0x140046697  mov     esi, edi
0x140046699  mov     [rsp+88h+var_38], rdi
0x14004669e  mov     [rsp+88h+var_40], 0FFFFFFFFFFFFFFFFh
0x1400466a7  mov     [rax-48h], edi
0x1400466aa  mov     [rax+20h], di
0x1400466ae  lea     rcx, [rax+20h]; unsigned __int16 *
0x1400466b2  call    ?GetSystemDriveLetter@@YAJAEAG@Z; GetSystemDriveLetter(ushort &)
0x1400466b7  mov     ebx, eax
0x1400466b9  test    eax, eax
0x1400466bb  jns     short loc_1400466C2
0x1400466bd  jmp     loc_140046884
0x1400466c2  mov     edx, 10h
0x1400466c7  mov     rcx, r14
0x1400466ca  call    ?reserve@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAX_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::reserve(unsigned __int64)
0x1400466cf  movzx   r8d, word ptr [rsp+88h+arg_18]
0x1400466d8  lea     rdx, aC; "\\\\.\\%C:"
0x1400466df  mov     rcx, r14
0x1400466e2  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x1400466e7  mov     rcx, [r14]
0x1400466ea  mov     [rsp+88h+hTemplateFile], rdi; hTemplateFile
0x1400466ef  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400466f7  mov     r8d, 3; dwShareMode
0x1400466fd  mov     [rsp+88h+dwCreationDisposition], r8d; dwCreationDisposition
0x140046702  xor     r9d, r9d; lpSecurityAttributes
0x140046705  xor     edx, edx; dwDesiredAccess
0x140046707  mov     rcx, [rcx+18h]; lpFileName
0x14004670b  call    cs:__imp_CreateFileW
0x140046711  mov     r14, rax
0x140046714  mov     [rsp+88h+var_40], rax
0x140046719  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004671d  jnz     short loc_140046739
0x14004671f  call    cs:__imp_GetLastError
0x140046725  mov     ebx, eax
0x140046727  test    eax, eax
0x140046729  jle     short loc_140046734
0x14004672b  movzx   ebx, ax
0x14004672e  or      ebx, 80070000h
0x140046734  jmp     loc_140046884
0x140046739  mov     ebx, 1
0x14004673e  test    rsi, rsi
0x140046741  jz      short loc_14004674B
0x140046743  mov     rcx, rsi; Block
0x140046746  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004674b  lea     eax, [rbx+rbx*2]
0x14004674e  lea     ebx, ds:20h[rax*8]
0x140046755  mov     r15d, ebx
0x140046758  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14004675f  mov     ecx, ebx; unsigned __int64
0x140046761  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140046766  mov     rsi, rax
0x140046769  mov     [rsp+88h+var_38], rax
0x14004676e  test    rax, rax
0x140046771  jnz     short loc_14004677D
0x140046773  mov     ebx, 8007000Eh
0x140046778  jmp     loc_14004687B
0x14004677d  mov     r8, r15; Size
0x140046780  xor     edx, edx; Val
0x140046782  mov     rcx, rsi; void *
0x140046785  call    memset_0
0x14004678a  lea     r15, [rsi+8]
0x14004678e  mov     [rsp+88h+lpOverlapped], rdi; lpOverlapped
0x140046793  lea     rax, [rsp+88h+BytesReturned]
0x140046798  mov     [rsp+88h+hTemplateFile], rax; lpBytesReturned
0x14004679d  mov     [rsp+88h+dwFlagsAndAttributes], ebx; nOutBufferSize
0x1400467a1  mov     qword ptr [rsp+88h+dwCreationDisposition], rsi; lpOutBuffer
0x1400467a6  xor     r9d, r9d; nInBufferSize
0x1400467a9  xor     r8d, r8d; lpInBuffer
0x1400467ac  mov     edx, 560000h; dwIoControlCode
0x1400467b1  mov     rcx, r14; hDevice
0x1400467b4  call    cs:__imp_DeviceIoControl
0x1400467ba  test    eax, eax
0x1400467bc  jnz     short loc_1400467E6
0x1400467be  call    cs:__imp_GetLastError
0x1400467c4  mov     ebx, eax
0x1400467c6  cmp     eax, 0EAh
0x1400467cb  jz      short loc_1400467DF
0x1400467cd  test    eax, eax
0x1400467cf  jle     short loc_1400467DA
0x1400467d1  movzx   ebx, ax
0x1400467d4  or      ebx, 80070000h
0x1400467da  jmp     loc_14004686D
0x1400467df  mov     ebx, [rsi]
0x1400467e1  jmp     loc_14004673E
0x1400467e6  mov     rcx, r14; hObject
0x1400467e9  call    cs:__imp_CloseHandle
0x1400467ef  or      r14, 0FFFFFFFFFFFFFFFFh
0x1400467f3  mov     [rsp+88h+var_40], r14
0x1400467f8  mov     r9d, [rsi]
0x1400467fb  lea     rax, [r9+r9*2]
0x1400467ff  lea     rcx, ds:8[rax*8]
0x140046807  mov     eax, [rsp+88h+BytesReturned]
0x14004680b  cmp     rax, rcx
0x14004680e  jnb     short loc_140046817
0x140046810  mov     ebx, 8007000Dh
0x140046815  jmp     short loc_14004686D
0x140046817  mov     r8, r15
0x14004681a  mov     r10d, 1
0x140046820  cmp     r9d, r10d
0x140046823  jbe     short loc_140046844
0x140046825  mov     eax, r10d
0x140046828  lea     rcx, [rax+rax*2]
0x14004682c  lea     rdx, [r15+rcx*8]
0x140046830  mov     rax, [r8+10h]
0x140046834  cmp     [rdx+10h], rax
0x140046838  cmovg   r8, rdx
0x14004683c  inc     r10d
0x14004683f  cmp     r10d, r9d
0x140046842  jb      short loc_140046825
0x140046844  mov     ecx, [r8]; unsigned int
0x140046847  mov     [r13+0], ecx
0x14004684b  mov     rdx, r12; unsigned __int64 *
0x14004684e  call    ?GetPhysicalDiskSize@@YAJKAEA_K@Z; GetPhysicalDiskSize(ulong,unsigned __int64 &)
0x140046853  mov     ebx, eax
0x140046855  jmp     short loc_14004686D
0x140046857  mov     rsi, [rsp+88h+var_38]
0x14004685c  mov     ebx, [rsp+88h+arg_18]
0x140046863  mov     r14, [rsp+88h+var_40]
0x140046868  test    rsi, rsi
0x14004686b  jz      short loc_140046875
0x14004686d  mov     rcx, rsi; Block
0x140046870  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140046875  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x140046879  jz      short loc_140046884
0x14004687b  mov     rcx, r14; hObject
0x14004687e  call    cs:__imp_CloseHandle
0x140046884  mov     eax, ebx
0x140046886  lea     r11, [rsp+88h+var_28]
0x14004688b  mov     rbx, [r11+30h]
0x14004688f  mov     rsi, [r11+38h]
0x140046893  mov     rsp, r11
0x140046896  pop     r15
0x140046898  pop     r14
0x14004689a  pop     r13
0x14004689c  pop     r12
0x14004689e  pop     rdi
0x14004689f  retn
```
