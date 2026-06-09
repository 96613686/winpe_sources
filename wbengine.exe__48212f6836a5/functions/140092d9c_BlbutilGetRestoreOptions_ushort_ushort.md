# BlbutilGetRestoreOptions(ushort *,ushort * *)

- ea: `0x140092d9c`
- end: `0x14009313c`
- name: `?BlbutilGetRestoreOptions@@YAJPEAGPEAPEAG@Z`
- size: `928`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x14007c82c`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14001358c`
- `0x1400142d8`
- `0x140088ba4`
- `0x140092d9c`
- `0x140134d20`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140092e8e`
- `KERNEL32!CreateFileW` at `0x140092e8e`
- `KERNEL32!CloseHandle` at `0x1400930e0`
- `KERNEL32!CloseHandle` at `0x1400930e0`
- `KERNEL32!GetLastError` at `0x140092e9d`
- `KERNEL32!GetLastError` at `0x140092f17`
- `KERNEL32!GetLastError` at `0x140092e9d`
- `KERNEL32!GetLastError` at `0x140092f17`
- `KERNEL32!DeviceIoControl` at `0x140092f0d`
- `KERNEL32!DeviceIoControl` at `0x140092f0d`
- `ole32!CoTaskMemAlloc` at `0x140092ec5`
- `ole32!CoTaskMemAlloc` at `0x140092f67`
- `ole32!CoTaskMemAlloc` at `0x140092ec5`
- `ole32!CoTaskMemAlloc` at `0x140092f67`
- `ole32!CoTaskMemFree` at `0x140092f36`
- `ole32!CoTaskMemFree` at `0x1400930a5`
- `ole32!CoTaskMemFree` at `0x1400930b3`
- `ole32!CoTaskMemFree` at `0x1400930d1`
- `ole32!CoTaskMemFree` at `0x140092f36`
- `ole32!CoTaskMemFree` at `0x1400930a5`
- `ole32!CoTaskMemFree` at `0x1400930b3`
- `ole32!CoTaskMemFree` at `0x1400930d1`

## pseudocode

```c
__int64 __fastcall BlbutilGetRestoreOptions(unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 FileW; // r12
  signed int v5; // ebx
  signed int LastError; // eax
  unsigned int v7; // eax
  _DWORD *v8; // rax
  _DWORD *v9; // rsi
  signed int v10; // eax
  unsigned __int16 *v11; // rdi
  unsigned int v12; // r15d
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // r13
  unsigned __int64 v15; // rax
  __int64 i; // r14
  __int64 v17; // r14
  size_t Size; // [rsp+40h] [rbp-39h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int64 v21; // [rsp+50h] [rbp-29h]
  unsigned __int16 **v22; // [rsp+58h] [rbp-21h]
  unsigned __int16 *v23; // [rsp+60h] [rbp-19h]
  unsigned __int16 v24[8]; // [rsp+68h] [rbp-11h] BYREF
  __int128 v25; // [rsp+78h] [rbp-1h]
  __int64 v26; // [rsp+88h] [rbp+Fh]

  v22 = a2;
  v23 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_dc2849744a45317b735236505766376f_Traceguids);
  }
  FileW = -1;
  lpFileName = 0;
  LODWORD(Size) = 0;
  if ( !a2 )
    BlbAssert("base\\stor\\blb\\util\\blbutility.cpp", 0x37Fu, "pwszRestoreOptions");
  *a2 = 0;
  *(_OWORD *)v24 = *(_OWORD *)L"\"ExcludeDisk\"=\"%d\",";
  v26 = *(_QWORD *)L"d\",";
  v25 = *(_OWORD *)L"Disk\"=\"%d\",";
  v5 = BlbutilRemoveTrailingBackslash(a1, (unsigned __int16 **)&lpFileName);
  if ( v5 >= 0 )
  {
    FileW = (__int64)CreateFileW(lpFileName, 0, 3u, 0, 3u, 0, 0);
    if ( FileW == -1 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v7 = 32;
      LODWORD(Size) = 32;
      while ( 1 )
      {
        v8 = CoTaskMemAlloc(v7);
        v9 = v8;
        if ( !v8 )
        {
          v5 = -2147024882;
          goto LABEL_41;
        }
        memset_0(v8, 0, (unsigned int)Size);
        if ( DeviceIoControl((HANDLE)FileW, 0x560000u, 0, 0, v9, Size, (LPDWORD)&Size, 0) )
          break;
        v10 = GetLastError();
        if ( v10 != 234 )
        {
          v11 = 0;
          if ( v10 > 0 )
            v5 = (unsigned __int16)v10 | 0x80070000;
          else
            v5 = v10;
          goto LABEL_38;
        }
        LODWORD(Size) = 24 * *v9 + 8;
        CoTaskMemFree(v9);
        v7 = Size;
      }
      v12 = 42 * *v9;
      v13 = (unsigned __int16 *)CoTaskMemAlloc(v12);
      v11 = v13;
      if ( v13 )
      {
        memset_0(v13, 0, v12);
        v14 = v11;
        v15 = (unsigned int)(Size - 8) / 0x18uLL;
        v21 = v15;
        if ( (_DWORD)v15 != *v9 )
        {
          BlbAssert("base\\stor\\blb\\util\\blbutility.cpp", 0x3D2u, "cDiskExtents == pExtents->NumberOfDiskExtents");
          LODWORD(v15) = v21;
        }
        for ( i = 0; (unsigned int)i < (unsigned int)v15; i = (unsigned int)(i + 1) )
        {
          v5 = StringCchPrintfW(v14, (unsigned __int64)v12 >> 1, v24, (unsigned int)v9[6 * i + 2]);
          v15 = -1;
          do
            ++v15;
          while ( v11[v15] );
          if ( v5 < 0 )
            goto LABEL_38;
          v14 = &v11[v15];
          v12 += -2 * v15;
          LODWORD(v15) = v21;
        }
        v17 = -1;
        do
          ++v17;
        while ( v11[v17] );
        if ( *v9 )
        {
          if ( (unsigned int)v17 <= 1 )
            BlbAssert("base\\stor\\blb\\util\\blbutility.cpp", 0x3E6u, "cRestoreOptionStrLength > 1");
          v11[(unsigned int)(v17 - 1)] = 0;
          *v22 = v11;
          v11 = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_SS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              49,
              (unsigned int)WPP_dc2849744a45317b735236505766376f_Traceguids,
              (_DWORD)v23,
              0);
          }
        }
      }
      else
      {
        v5 = -2147024882;
      }
LABEL_38:
      CoTaskMemFree(v9);
      if ( v11 )
        CoTaskMemFree(v11);
    }
  }
LABEL_41:
  if ( lpFileName )
    CoTaskMemFree((LPVOID)lpFileName);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_dc2849744a45317b735236505766376f_Traceguids);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140092d9c  mov     [rsp-8+arg_10], rbx
0x140092da1  push    rbp
0x140092da2  push    rsi
0x140092da3  push    rdi
0x140092da4  push    r12
0x140092da6  push    r13
0x140092da8  push    r14
0x140092daa  push    r15
0x140092dac  lea     rbp, [rsp-27h]
0x140092db1  sub     rsp, 0A0h
0x140092db8  mov     rax, cs:__security_cookie
0x140092dbf  xor     rax, rsp
0x140092dc2  mov     [rbp+57h+var_40], rax
0x140092dc6  mov     rbx, rdx
0x140092dc9  mov     [rbp+57h+var_78], rdx
0x140092dcd  mov     rdi, rcx
0x140092dd0  mov     [rbp+57h+var_70], rcx
0x140092dd4  mov     rcx, cs:WPP_GLOBAL_Control
0x140092ddb  lea     rsi, WPP_GLOBAL_Control
0x140092de2  cmp     rcx, rsi
0x140092de5  jz      short loc_140092E08
0x140092de7  test    byte ptr [rcx+1Ch], 20h
0x140092deb  jz      short loc_140092E08
0x140092ded  cmp     byte ptr [rcx+19h], 4
0x140092df1  jb      short loc_140092E08
0x140092df3  mov     rcx, [rcx+10h]
0x140092df7  lea     r8, WPP_dc2849744a45317b735236505766376f_Traceguids
0x140092dfe  mov     edx, 30h ; '0'
0x140092e03  call    WPP_SF_
0x140092e08  xor     r13d, r13d
0x140092e0b  or      r12, 0FFFFFFFFFFFFFFFFh
0x140092e0f  mov     [rbp+57h+lpFileName], r13
0x140092e13  mov     dword ptr [rbp+57h+Size], r13d
0x140092e17  test    rbx, rbx
0x140092e1a  jnz     short loc_140092E34
0x140092e1c  lea     r8, aPwszrestoreopt; "pwszRestoreOptions"
0x140092e23  mov     edx, 37Fh; unsigned int
0x140092e28  lea     rcx, aBaseStorBlbUti_5; "base\\stor\\blb\\util\\blbutility.cpp"
0x140092e2f  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140092e34  mov     [rbx], r13
0x140092e37  lea     rdx, [rbp+57h+lpFileName]; unsigned __int16 **
0x140092e3b  movups  xmm0, xmmword ptr cs:aExcludediskD; "\"ExcludeDisk\"=\"%d\","
0x140092e42  mov     rcx, rdi; unsigned __int16 *
0x140092e45  movups  xmm1, xmmword ptr cs:aExcludediskD+10h; "Disk\"=\"%d\","
0x140092e4c  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x140092e50  movsd   xmm0, qword ptr cs:aExcludediskD+20h; "d\","
0x140092e58  movsd   [rbp+57h+var_48], xmm0
0x140092e5d  movups  [rbp+57h+var_58], xmm1
0x140092e61  call    ?BlbutilRemoveTrailingBackslash@@YAJPEBGPEAPEAG@Z; BlbutilRemoveTrailingBackslash(ushort const *,ushort * *)
0x140092e66  mov     ebx, eax
0x140092e68  test    eax, eax
0x140092e6a  js      loc_1400930C7
0x140092e70  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x140092e74  mov     r8d, 3; dwShareMode
0x140092e7a  mov     [rsp+0D0h+hTemplateFile], r13; hTemplateFile
0x140092e7f  xor     r9d, r9d; lpSecurityAttributes
0x140092e82  mov     [rsp+0D0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x140092e87  xor     edx, edx; dwDesiredAccess
0x140092e89  mov     [rsp+0D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x140092e8e  call    cs:__imp_CreateFileW
0x140092e94  mov     r12, rax
0x140092e97  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140092e9b  jnz     short loc_140092EBB
0x140092e9d  call    cs:__imp_GetLastError
0x140092ea3  mov     ebx, eax
0x140092ea5  test    eax, eax
0x140092ea7  jle     loc_1400930C7
0x140092ead  movzx   ebx, ax
0x140092eb0  or      ebx, 80070000h
0x140092eb6  jmp     loc_1400930C7
0x140092ebb  mov     eax, 20h ; ' '
0x140092ec0  mov     dword ptr [rbp+57h+Size], eax
0x140092ec3  mov     ecx, eax; cb
0x140092ec5  call    cs:__imp_CoTaskMemAlloc
0x140092ecb  mov     rsi, rax
0x140092ece  test    rax, rax
0x140092ed1  jz      loc_1400930BB
0x140092ed7  mov     r8d, dword ptr [rbp+57h+Size]; Size
0x140092edb  xor     edx, edx; Val
0x140092edd  mov     rcx, rax; void *
0x140092ee0  call    memset_0
0x140092ee5  lea     rax, [rbp+57h+Size]
0x140092ee9  mov     [rsp+0D0h+lpOverlapped], r13; lpOverlapped
0x140092eee  mov     [rsp+0D0h+hTemplateFile], rax; lpBytesReturned
0x140092ef3  xor     r9d, r9d; nInBufferSize
0x140092ef6  mov     eax, dword ptr [rbp+57h+Size]
0x140092ef9  xor     r8d, r8d; lpInBuffer
0x140092efc  mov     [rsp+0D0h+dwFlagsAndAttributes], eax; nOutBufferSize
0x140092f00  mov     edx, 560000h; dwIoControlCode
0x140092f05  mov     rcx, r12; hDevice
0x140092f08  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rsi; lpOutBuffer
0x140092f0d  call    cs:__imp_DeviceIoControl
0x140092f13  test    eax, eax
0x140092f15  jnz     short loc_140092F5D
0x140092f17  call    cs:__imp_GetLastError
0x140092f1d  cmp     eax, 0EAh
0x140092f22  jnz     short loc_140092F41
0x140092f24  mov     eax, [rsi]
0x140092f26  lea     ecx, [rax+rax*2]
0x140092f29  lea     ecx, ds:8[rcx*8]
0x140092f30  mov     dword ptr [rbp+57h+Size], ecx
0x140092f33  mov     rcx, rsi; pv
0x140092f36  call    cs:__imp_CoTaskMemFree
0x140092f3c  mov     eax, dword ptr [rbp+57h+Size]
0x140092f3f  jmp     short loc_140092EC3
0x140092f41  mov     rdi, r13
0x140092f44  test    eax, eax
0x140092f46  jg      short loc_140092F4F
0x140092f48  mov     ebx, eax
0x140092f4a  jmp     loc_1400930A2
0x140092f4f  movzx   ebx, ax
0x140092f52  or      ebx, 80070000h
0x140092f58  jmp     loc_1400930A2
0x140092f5d  imul    r15d, [rsi], 2Ah ; '*'
0x140092f61  mov     ecx, r15d; cb
0x140092f64  mov     r14d, r15d
0x140092f67  call    cs:__imp_CoTaskMemAlloc
0x140092f6d  mov     rdi, rax
0x140092f70  test    rax, rax
0x140092f73  jnz     short loc_140092F7F
0x140092f75  mov     ebx, 8007000Eh
0x140092f7a  jmp     loc_1400930A2
0x140092f7f  mov     r8, r14; Size
0x140092f82  xor     edx, edx; Val
0x140092f84  mov     rcx, rdi; void *
0x140092f87  call    memset_0
0x140092f8c  mov     ecx, dword ptr [rbp+57h+Size]
0x140092f8f  mov     rax, 0AAAAAAAAAAAAAAABh
0x140092f99  add     ecx, 0FFFFFFF8h
0x140092f9c  mov     r13, rdi
0x140092f9f  mul     rcx
0x140092fa2  mov     rax, rdx
0x140092fa5  shr     rax, 4
0x140092fa9  mov     [rbp+57h+var_80], rax
0x140092fad  cmp     eax, [rsi]
0x140092faf  jz      short loc_140092FCD
0x140092fb1  lea     r8, aCdiskextentsPe; "cDiskExtents == pExtents->NumberOfDiskE"...
0x140092fb8  mov     edx, 3D2h; unsigned int
0x140092fbd  lea     rcx, aBaseStorBlbUti_5; "base\\stor\\blb\\util\\blbutility.cpp"
0x140092fc4  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140092fc9  mov     rax, [rbp+57h+var_80]
0x140092fcd  xor     r14d, r14d
0x140092fd0  cmp     r14d, eax
0x140092fd3  jnb     short loc_14009301E
0x140092fd5  lea     r9, [r14+r14*2]
0x140092fd9  mov     edx, r15d
0x140092fdc  mov     r9d, [rsi+r9*8+8]
0x140092fe1  lea     r8, [rbp+57h+var_68]; unsigned __int16 *
0x140092fe5  shr     rdx, 1; unsigned __int64
0x140092fe8  mov     rcx, r13; unsigned __int16 *
0x140092feb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140092ff0  mov     ebx, eax
0x140092ff2  or      rax, 0FFFFFFFFFFFFFFFFh
0x140092ff6  xor     r13d, r13d
0x140092ff9  inc     rax
0x140092ffc  cmp     [rdi+rax*2], r13w
0x140093001  jnz     short loc_140092FF9
0x140093003  test    ebx, ebx
0x140093005  js      loc_1400930A2
0x14009300b  lea     r13, [rdi+rax*2]
0x14009300f  imul    eax, -2
0x140093012  add     r15d, eax
0x140093015  mov     rax, [rbp+57h+var_80]
0x140093019  inc     r14d
0x14009301c  jmp     short loc_140092FD0
0x14009301e  or      r14, 0FFFFFFFFFFFFFFFFh
0x140093022  xor     r13d, r13d
0x140093025  inc     r14
0x140093028  cmp     [rdi+r14*2], r13w
0x14009302d  jnz     short loc_140093025
0x14009302f  cmp     [rsi], r13d
0x140093032  jbe     short loc_1400930A2
0x140093034  cmp     r14d, 1
0x140093038  ja      short loc_140093052
0x14009303a  lea     r8, aCrestoreoption; "cRestoreOptionStrLength > 1"
0x140093041  mov     edx, 3E6h; unsigned int
0x140093046  lea     rcx, aBaseStorBlbUti_5; "base\\stor\\blb\\util\\blbutility.cpp"
0x14009304d  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140093052  lea     eax, [r14-1]
0x140093056  mov     [rdi+rax*2], r13w
0x14009305b  mov     rax, [rbp+57h+var_78]
0x14009305f  mov     [rax], rdi
0x140093062  mov     rdi, r13
0x140093065  mov     rcx, cs:WPP_GLOBAL_Control
0x14009306c  lea     rax, WPP_GLOBAL_Control
0x140093073  cmp     rcx, rax
0x140093076  jz      short loc_1400930A2
0x140093078  test    byte ptr [rcx+1Ch], 1
0x14009307c  jz      short loc_1400930A2
0x14009307e  cmp     byte ptr [rcx+19h], 4
0x140093082  jb      short loc_1400930A2
0x140093084  mov     r9, [rbp+57h+var_70]
0x140093088  lea     r8, WPP_dc2849744a45317b735236505766376f_Traceguids
0x14009308f  mov     rcx, [rcx+10h]
0x140093093  mov     edx, 31h ; '1'
0x140093098  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r13
0x14009309d  call    WPP_SF_SS
0x1400930a2  mov     rcx, rsi; pv
0x1400930a5  call    cs:__imp_CoTaskMemFree
0x1400930ab  test    rdi, rdi
0x1400930ae  jz      short loc_1400930C0
0x1400930b0  mov     rcx, rdi; pv
0x1400930b3  call    cs:__imp_CoTaskMemFree
0x1400930b9  jmp     short loc_1400930C0
0x1400930bb  mov     ebx, 8007000Eh
0x1400930c0  lea     rsi, WPP_GLOBAL_Control
0x1400930c7  cmp     [rbp+57h+lpFileName], r13
0x1400930cb  jz      short loc_1400930D7
0x1400930cd  mov     rcx, [rbp+57h+lpFileName]; pv
0x1400930d1  call    cs:__imp_CoTaskMemFree
0x1400930d7  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x1400930db  jz      short loc_1400930E6
0x1400930dd  mov     rcx, r12; hObject
0x1400930e0  call    cs:__imp_CloseHandle
0x1400930e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400930ed  cmp     rcx, rsi
0x1400930f0  jz      short loc_140093113
0x1400930f2  test    byte ptr [rcx+1Ch], 20h
0x1400930f6  jz      short loc_140093113
0x1400930f8  cmp     byte ptr [rcx+19h], 4
0x1400930fc  jb      short loc_140093113
0x1400930fe  mov     rcx, [rcx+10h]
0x140093102  lea     r8, WPP_dc2849744a45317b735236505766376f_Traceguids
0x140093109  mov     edx, 32h ; '2'
0x14009310e  call    WPP_SF_
0x140093113  mov     eax, ebx
0x140093115  mov     rcx, [rbp+57h+var_40]
0x140093119  xor     rcx, rsp; StackCookie
0x14009311c  call    __security_check_cookie
0x140093121  mov     rbx, [rsp+0D0h+arg_10]
0x140093129  add     rsp, 0A0h
0x140093130  pop     r15
0x140093132  pop     r14
0x140093134  pop     r13
0x140093136  pop     r12
0x140093138  pop     rdi
0x140093139  pop     rsi
0x14009313a  pop     rbp
0x14009313b  retn
```
