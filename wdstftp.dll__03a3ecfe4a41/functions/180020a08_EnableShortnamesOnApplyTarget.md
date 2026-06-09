# EnableShortnamesOnApplyTarget

- ea: `0x180020a08`
- end: `0x180020cbf`
- name: `EnableShortnamesOnApplyTarget`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180020cc8`

## callees

- `0x1800112ac`
- `0x180020a08`
- `0x1800219c4`
- `0x18004012c`
- `0x1800607b0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180020bf0`
- `KERNEL32!DeviceIoControl` at `0x180020bf0`
- `KERNEL32!HeapFree` at `0x180020c73`
- `KERNEL32!HeapFree` at `0x180061c34`
- `KERNEL32!HeapFree` at `0x180020c73`
- `KERNEL32!HeapFree` at `0x180061c34`
- `KERNEL32!GetLastError` at `0x180020b5f`
- `KERNEL32!GetLastError` at `0x180020b7e`
- `KERNEL32!GetLastError` at `0x180020c00`
- `KERNEL32!GetLastError` at `0x180020c1f`
- `KERNEL32!GetLastError` at `0x180020b5f`
- `KERNEL32!GetLastError` at `0x180020b7e`
- `KERNEL32!GetLastError` at `0x180020c00`
- `KERNEL32!GetLastError` at `0x180020c1f`
- `KERNEL32!CloseHandle` at `0x180020c88`
- `KERNEL32!CloseHandle` at `0x180061c4b`
- `KERNEL32!CloseHandle` at `0x180020c88`
- `KERNEL32!CloseHandle` at `0x180061c4b`
- `KERNEL32!CreateFileW` at `0x180020b45`
- `KERNEL32!CreateFileW` at `0x180020b45`
- `KERNEL32!GetProcessHeap` at `0x180020c5f`
- `KERNEL32!GetProcessHeap` at `0x180061c20`
- `KERNEL32!GetProcessHeap` at `0x180020c5f`
- `KERNEL32!GetProcessHeap` at `0x180061c20`

## pseudocode

```c
__int64 __fastcall EnableShortnamesOnApplyTarget(__int64 a1, __int64 a2)
{
  signed int VolumeRootFromPath; // ebx
  __int64 FileW; // r14
  WCHAR *v5; // rdi
  __int16 DriveLetter; // ax
  __int64 v7; // rdx
  const WCHAR *v8; // rcx
  __int64 v9; // rax
  WCHAR *v10; // rax
  signed int LastError; // eax
  __int64 v12; // rdx
  signed int v13; // ecx
  signed int v14; // eax
  unsigned int v15; // r8d
  signed int v16; // eax
  signed int v17; // ecx
  signed int v18; // eax
  HANDLE ProcessHeap; // rax
  LPCWSTR lpFileName; // [rsp+48h] [rbp-60h] BYREF
  __int64 v22; // [rsp+50h] [rbp-58h]
  DWORD BytesReturned; // [rsp+58h] [rbp-50h] BYREF
  WCHAR *v24; // [rsp+60h] [rbp-48h]
  __int64 InBuffer; // [rsp+68h] [rbp-40h] BYREF
  __int64 v26; // [rsp+70h] [rbp-38h]
  __int64 v27; // [rsp+78h] [rbp-30h] BYREF
  int v28; // [rsp+80h] [rbp-28h]
  wchar_t v29; // [rsp+84h] [rbp-24h]

  VolumeRootFromPath = 0;
  FileW = -1;
  v22 = -1;
  v5 = 0;
  lpFileName = 0;
  v27 = *(_QWORD *)L"\\\\.\\?:";
  v28 = *(_DWORD *)L"?:";
  v29 = asc_1800690C8[6];
  InBuffer = 0;
  v26 = 0;
  DriveLetter = ExtractDriveLetter(a2);
  if ( DriveLetter )
  {
    LOWORD(v28) = DriveLetter;
    v8 = (const WCHAR *)&v27;
  }
  else
  {
    if ( a2 )
    {
      VolumeRootFromPath = GetVolumeRootFromPath(a2, &lpFileName);
      v5 = (WCHAR *)lpFileName;
    }
    else
    {
      VolumeRootFromPath = -2147024809;
    }
    if ( VolumeRootFromPath >= 0 )
    {
      if ( v5 && *v5 )
      {
        v9 = -1;
        do
          ++v9;
        while ( v5[v9] );
        v10 = &v5[v9 - 1];
        v24 = v10;
        while ( v10 >= v5 && *v10 == 92 )
        {
          *v10-- = 0;
          v24 = v10;
        }
      }
    }
    else
    {
      UtilReportError((__int64)L"EnableShortnamesOnApplyTarget", v7, 0x1E2u, VolumeRootFromPath);
    }
    v8 = v5;
  }
  if ( VolumeRootFromPath >= 0 )
  {
    FileW = (__int64)CreateFileW(v8, 0xC0000000, 3u, 0, 3u, 0x2000000u, 0);
    v22 = FileW;
    if ( FileW == -1 )
    {
      LastError = GetLastError();
      v13 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v13 = LastError;
      if ( v13 >= 0 )
      {
        VolumeRootFromPath = -2147467259;
      }
      else
      {
        v14 = GetLastError();
        VolumeRootFromPath = (unsigned __int16)v14 | 0x80070000;
        if ( v14 <= 0 )
          VolumeRootFromPath = v14;
      }
      if ( VolumeRootFromPath < 0 )
      {
        v15 = 519;
LABEL_38:
        UtilReportError((__int64)L"EnableShortnamesOnApplyTarget", v12, v15, VolumeRootFromPath);
      }
    }
    else
    {
      InBuffer = 0x100000000LL;
      LODWORD(v26) = 1;
      if ( !DeviceIoControl((HANDLE)FileW, 0x90238u, &InBuffer, 0x10u, 0, 0, &BytesReturned, 0) )
      {
        v16 = GetLastError();
        v17 = (unsigned __int16)v16 | 0x80070000;
        if ( v16 <= 0 )
          v17 = v16;
        if ( v17 >= 0 )
        {
          VolumeRootFromPath = -2147467259;
        }
        else
        {
          v18 = GetLastError();
          VolumeRootFromPath = (unsigned __int16)v18 | 0x80070000;
          if ( v18 <= 0 )
            VolumeRootFromPath = v18;
        }
        if ( VolumeRootFromPath < 0 )
        {
          v15 = 545;
          goto LABEL_38;
        }
      }
    }
  }
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)VolumeRootFromPath;
}

```

## disassembly

```asm
0x180020a08  mov     r11, rsp
0x180020a0b  mov     [r11+8], rbx
0x180020a0f  mov     [r11+18h], rsi
0x180020a13  push    rdi
0x180020a14  push    r14
0x180020a16  push    r15
0x180020a18  sub     rsp, 90h
0x180020a1f  mov     rax, cs:__security_cookie
0x180020a26  xor     rax, rsp
0x180020a29  mov     [rsp+0A8h+var_20], rax
0x180020a31  mov     rsi, rdx
0x180020a34  xor     r15d, r15d
0x180020a37  mov     ebx, r15d
0x180020a3a  or      r14, 0FFFFFFFFFFFFFFFFh
0x180020a3e  mov     [r11-58h], r14
0x180020a42  mov     edi, r15d
0x180020a45  mov     [r11-60h], r15
0x180020a49  movsd   xmm0, qword ptr cs:asc_1800690C8; "\\\\.\\?:"
0x180020a51  movsd   [rsp+0A8h+var_30], xmm0
0x180020a57  mov     eax, dword ptr cs:asc_1800690C8+8; "?:"
0x180020a5d  mov     [r11-28h], eax
0x180020a61  movzx   eax, word ptr cs:asc_1800690C8+0Ch; ""
0x180020a68  mov     [r11-24h], ax
0x180020a6d  xor     eax, eax
0x180020a6f  mov     [r11-40h], rax
0x180020a73  mov     [r11-38h], rax
0x180020a77  mov     rcx, rdx
0x180020a7a  call    ExtractDriveLetter
0x180020a7f  test    ax, ax
0x180020a82  jz      short loc_180020A96
0x180020a84  mov     word ptr [rsp+0A8h+var_28], ax
0x180020a8c  lea     rcx, [rsp+0A8h+var_30]
0x180020a91  jmp     loc_180020B1D
0x180020a96  test    rsi, rsi
0x180020a99  jz      short loc_180020AB5
0x180020a9b  lea     rdx, [rsp+0A8h+lpFileName]
0x180020aa0  mov     rcx, rsi
0x180020aa3  call    GetVolumeRootFromPath
0x180020aa8  mov     ebx, eax
0x180020aaa  mov     [rsp+0A8h+var_68], eax
0x180020aae  mov     rdi, [rsp+0A8h+lpFileName]
0x180020ab3  jmp     short loc_180020ABE
0x180020ab5  mov     ebx, 80070057h
0x180020aba  mov     [rsp+0A8h+var_68], ebx
0x180020abe  test    ebx, ebx
0x180020ac0  jns     short loc_180020ADB
0x180020ac2  mov     r9d, ebx
0x180020ac5  mov     r8d, 1E2h
0x180020acb  lea     rcx, aEnableshortnam; "EnableShortnamesOnApplyTarget"
0x180020ad2  call    UtilReportError
0x180020ad7  test    ebx, ebx
0x180020ad9  js      short loc_180020B1A
0x180020adb  test    rdi, rdi
0x180020ade  jz      short loc_180020B1A
0x180020ae0  cmp     [rdi], r15w
0x180020ae4  jz      short loc_180020B1A
0x180020ae6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020aea  inc     rax
0x180020aed  cmp     [rdi+rax*2], r15w
0x180020af2  jnz     short loc_180020AEA
0x180020af4  dec     rax
0x180020af7  lea     rax, [rdi+rax*2]
0x180020afb  mov     [rsp+0A8h+var_48], rax
0x180020b00  cmp     rax, rdi
0x180020b03  jb      short loc_180020B1A
0x180020b05  cmp     word ptr [rax], 5Ch ; '\'
0x180020b09  jnz     short loc_180020B1A
0x180020b0b  mov     [rax], r15w
0x180020b0f  sub     rax, 2
0x180020b13  mov     [rsp+0A8h+var_48], rax
0x180020b18  jmp     short loc_180020B00
0x180020b1a  mov     rcx, rdi; lpFileName
0x180020b1d  test    ebx, ebx
0x180020b1f  js      loc_180020C5A
0x180020b25  mov     [rsp+0A8h+hTemplateFile], r15; hTemplateFile
0x180020b2a  mov     [rsp+0A8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180020b32  mov     r8d, 3; dwShareMode
0x180020b38  mov     [rsp+0A8h+dwCreationDisposition], r8d; dwCreationDisposition
0x180020b3d  xor     r9d, r9d; lpSecurityAttributes
0x180020b40  mov     edx, 0C0000000h; dwDesiredAccess
0x180020b45  call    cs:__imp_CreateFileW
0x180020b4c  nop     dword ptr [rax+rax+00h]
0x180020b51  mov     r14, rax
0x180020b54  mov     [rsp+0A8h+var_58], rax
0x180020b59  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020b5d  jnz     short loc_180020BB2
0x180020b5f  call    cs:__imp_GetLastError
0x180020b66  nop     dword ptr [rax+rax+00h]
0x180020b6b  movzx   ecx, ax
0x180020b6e  mov     esi, 80070000h
0x180020b73  or      ecx, esi
0x180020b75  test    eax, eax
0x180020b77  cmovle  ecx, eax
0x180020b7a  test    ecx, ecx
0x180020b7c  jns     short loc_180020B96
0x180020b7e  call    cs:__imp_GetLastError
0x180020b85  nop     dword ptr [rax+rax+00h]
0x180020b8a  movzx   ebx, ax
0x180020b8d  or      ebx, esi
0x180020b8f  test    eax, eax
0x180020b91  cmovle  ebx, eax
0x180020b94  jmp     short loc_180020B9B
0x180020b96  mov     ebx, 80004005h
0x180020b9b  mov     [rsp+0A8h+var_68], ebx
0x180020b9f  test    ebx, ebx
0x180020ba1  jns     loc_180020C5A
0x180020ba7  mov     r8d, 207h
0x180020bad  jmp     loc_180020C4A
0x180020bb2  mov     [rsp+0A8h+InBuffer], r15d
0x180020bb7  mov     eax, 1
0x180020bbc  mov     [rsp+0A8h+var_3C], eax
0x180020bc0  mov     dword ptr [rsp+0A8h+var_38], eax
0x180020bc4  mov     [rsp+0A8h+lpOverlapped], r15; lpOverlapped
0x180020bc9  lea     rax, [rsp+0A8h+BytesReturned]
0x180020bce  mov     [rsp+0A8h+hTemplateFile], rax; lpBytesReturned
0x180020bd3  mov     [rsp+0A8h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x180020bd8  mov     qword ptr [rsp+0A8h+dwCreationDisposition], r15; lpOutBuffer
0x180020bdd  mov     r9d, 10h; nInBufferSize
0x180020be3  lea     r8, [rsp+0A8h+InBuffer]; lpInBuffer
0x180020be8  mov     edx, 90238h; dwIoControlCode
0x180020bed  mov     rcx, r14; hDevice
0x180020bf0  call    cs:__imp_DeviceIoControl
0x180020bf7  nop     dword ptr [rax+rax+00h]
0x180020bfc  test    eax, eax
0x180020bfe  jnz     short loc_180020C5A
0x180020c00  call    cs:__imp_GetLastError
0x180020c07  nop     dword ptr [rax+rax+00h]
0x180020c0c  movzx   ecx, ax
0x180020c0f  mov     esi, 80070000h
0x180020c14  or      ecx, esi
0x180020c16  test    eax, eax
0x180020c18  cmovle  ecx, eax
0x180020c1b  test    ecx, ecx
0x180020c1d  jns     short loc_180020C37
0x180020c1f  call    cs:__imp_GetLastError
0x180020c26  nop     dword ptr [rax+rax+00h]
0x180020c2b  movzx   ebx, ax
0x180020c2e  or      ebx, esi
0x180020c30  test    eax, eax
0x180020c32  cmovle  ebx, eax
0x180020c35  jmp     short loc_180020C3C
0x180020c37  mov     ebx, 80004005h
0x180020c3c  mov     [rsp+0A8h+var_68], ebx
0x180020c40  test    ebx, ebx
0x180020c42  jns     short loc_180020C5A
0x180020c44  mov     r8d, 221h
0x180020c4a  mov     r9d, ebx
0x180020c4d  lea     rcx, aEnableshortnam; "EnableShortnamesOnApplyTarget"
0x180020c54  call    UtilReportError
0x180020c59  nop
0x180020c5a  test    rdi, rdi
0x180020c5d  jz      short loc_180020C7F
0x180020c5f  call    cs:__imp_GetProcessHeap
0x180020c66  nop     dword ptr [rax+rax+00h]
0x180020c6b  mov     rcx, rax; hHeap
0x180020c6e  mov     r8, rdi; lpMem
0x180020c71  xor     edx, edx; dwFlags
0x180020c73  call    cs:__imp_HeapFree
0x180020c7a  nop     dword ptr [rax+rax+00h]
0x180020c7f  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180020c83  jz      short loc_180020C94
0x180020c85  mov     rcx, r14; hObject
0x180020c88  call    cs:__imp_CloseHandle
0x180020c8f  nop     dword ptr [rax+rax+00h]
0x180020c94  mov     eax, ebx
0x180020c96  mov     rcx, [rsp+0A8h+var_20]
0x180020c9e  xor     rcx, rsp; StackCookie
0x180020ca1  call    __security_check_cookie
0x180020ca6  lea     r11, [rsp+0A8h+var_18]
0x180020cae  mov     rbx, [r11+20h]
0x180020cb2  mov     rsi, [r11+30h]
0x180020cb6  mov     rsp, r11
0x180020cb9  pop     r15
0x180020cbb  pop     r14
0x180020cbd  pop     rdi
0x180020cbe  retn
0x180061c0d  push    rbx
0x180061c0f  push    rbp
0x180061c10  sub     rsp, 48h
0x180061c14  mov     rbp, rdx
0x180061c17  mov     rbx, [rbp+48h]
0x180061c1b  test    rbx, rbx
0x180061c1e  jz      short loc_180061C41
0x180061c20  call    cs:__imp_GetProcessHeap
0x180061c27  nop     dword ptr [rax+rax+00h]
0x180061c2c  mov     rcx, rax; hHeap
0x180061c2f  mov     r8, rbx; lpMem
0x180061c32  xor     edx, edx; dwFlags
0x180061c34  call    cs:__imp_HeapFree
0x180061c3b  nop     dword ptr [rax+rax+00h]
0x180061c40  nop
0x180061c41  mov     rcx, [rbp+50h]; hObject
0x180061c45  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180061c49  jz      short loc_180061C58
0x180061c4b  call    cs:__imp_CloseHandle
0x180061c52  nop     dword ptr [rax+rax+00h]
0x180061c57  nop
0x180061c58  add     rsp, 48h
0x180061c5c  pop     rbp
0x180061c5d  pop     rbx
0x180061c5e  retn
```
