# BlbutilQueryVolumeUniqueId(ushort *,uchar * *,ushort &)

- ea: `0x14008bd48`
- end: `0x14008bfdb`
- name: `?BlbutilQueryVolumeUniqueId@@YAJPEAGPEAPEAEAEAG@Z`
- size: `659`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int8 **, unsigned __int16 *)`
- caller_count: `13`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x14000faac`
- `0x140015558`
- `0x1400160a8`
- `0x140021210`
- `0x14004504c`
- `0x140045dec`
- `0x140049700`
- `0x14008f9ec`
- `0x1400ffcc0`
- `0x14010e004`
- `0x14010fc5c`
- `0x140115414`
- `0x140117318`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14003c434`
- `0x1400889f0`
- `0x14008bd48`
- `0x140134cd2`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14008bdfe`
- `KERNEL32!CreateFileW` at `0x14008bdfe`
- `KERNEL32!CloseHandle` at `0x14008bfc3`
- `KERNEL32!CloseHandle` at `0x14008bfc3`
- `KERNEL32!GetLastError` at `0x14008be0d`
- `KERNEL32!GetLastError` at `0x14008be91`
- `KERNEL32!GetLastError` at `0x14008becc`
- `KERNEL32!GetLastError` at `0x14008be0d`
- `KERNEL32!GetLastError` at `0x14008be91`
- `KERNEL32!GetLastError` at `0x14008becc`
- `KERNEL32!DeviceIoControl` at `0x14008be87`
- `KERNEL32!DeviceIoControl` at `0x14008be87`
- `ole32!CoTaskMemAlloc` at `0x14008bf54`
- `ole32!CoTaskMemAlloc` at `0x14008bf54`
- `ole32!CoTaskMemFree` at `0x14008bfa3`
- `ole32!CoTaskMemFree` at `0x14008bfab`
- `ole32!CoTaskMemFree` at `0x14008bfb4`
- `ole32!CoTaskMemFree` at `0x14008bfa3`
- `ole32!CoTaskMemFree` at `0x14008bfab`
- `ole32!CoTaskMemFree` at `0x14008bfb4`
- `ole32!CoTaskMemRealloc` at `0x14008be38`
- `ole32!CoTaskMemRealloc` at `0x14008be38`

## string_xrefs

- `0x14008bef0`: `pMountDevId->UniqueIdLength < dwBufSize`

## pseudocode

```c
__int64 __fastcall BlbutilQueryVolumeUniqueId(unsigned __int16 *a1, unsigned __int8 **a2, unsigned __int16 *a3)
{
  __int64 FileW; // r14
  unsigned __int16 *v5; // r13
  int v6; // eax
  WCHAR *v7; // r15
  signed int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rax
  signed int LastError; // eax
  DWORD i; // edi
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rsi
  signed int v15; // eax
  signed int v16; // eax
  void *v17; // rax
  void *v18; // rdi
  DWORD BytesReturned; // [rsp+80h] [rbp+8h] BYREF
  unsigned __int8 **v21; // [rsp+88h] [rbp+10h]
  unsigned __int16 *v22; // [rsp+90h] [rbp+18h]
  LPCWSTR lpFileName; // [rsp+98h] [rbp+20h] BYREF

  v22 = a3;
  v21 = a2;
  FileW = -1;
  *a2 = 0;
  *a3 = 0;
  v5 = 0;
  lpFileName = 0;
  BytesReturned = 0;
  if ( !a1 )
    BlbAssert("base\\stor\\blb\\util\\volumeutils.cpp", 0x30Bu, "pwszVolumeName != NULL");
  v6 = BlbutilDuplicateString(a1, (unsigned __int16 **)&lpFileName, 0);
  v7 = (WCHAR *)lpFileName;
  v8 = v6;
  if ( v6 >= 0 )
  {
    v9 = -1;
    do
      ++v9;
    while ( lpFileName[v9] );
    if ( (_DWORD)v9 )
    {
      v10 = (unsigned int)(v9 - 1);
      if ( lpFileName[v10] == 92 )
        lpFileName[v10] = 0;
    }
    FileW = (__int64)CreateFileW(v7, 0x80000000, 3u, 0, 3u, 0, 0);
    if ( FileW == -1 )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      for ( i = 256; i < 0x8000; i *= 2 )
      {
        v13 = (unsigned __int16 *)CoTaskMemRealloc(v5, i);
        v14 = v13;
        if ( !v13 )
          goto LABEL_35;
        v5 = v13;
        memset_0(v13, 0, i);
        if ( DeviceIoControl((HANDLE)FileW, 0x4D0000u, 0, 0, v5, i, &BytesReturned, 0) )
          goto LABEL_25;
        v15 = GetLastError();
        v8 = v15;
        if ( v15 == 122 || v15 == 234 )
        {
          v8 = 0;
        }
        else if ( v15 > 0 )
        {
          v8 = (unsigned __int16)v15 | 0x80070000;
        }
        if ( v8 < 0 )
          goto LABEL_36;
      }
      v16 = GetLastError();
      v8 = v16;
      if ( v16 > 0 )
        v8 = (unsigned __int16)v16 | 0x80070000;
      if ( v8 >= 0 )
      {
LABEL_25:
        if ( *v14 >= i )
          BlbAssert("base\\stor\\blb\\util\\volumeutils.cpp", 0x361u, "pMountDevId->UniqueIdLength < dwBufSize");
        if ( *v14 < i )
        {
          v17 = CoTaskMemAlloc(*v14);
          v18 = v17;
          if ( v17 )
          {
            memset_0(v17, 0, *v14);
            memcpy_0(v18, v14 + 1, *v14);
            *v22 = *v14;
            *v21 = (unsigned __int8 *)v18;
            goto LABEL_36;
          }
LABEL_35:
          v8 = -2147024882;
          goto LABEL_36;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4c89e0416b2b3a4e6cf04444c0dc1079_Traceguids);
        }
        v8 = -2147418113;
      }
    }
  }
LABEL_36:
  CoTaskMemFree(v5);
  CoTaskMemFree(0);
  CoTaskMemFree(v7);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14008bd48  mov     rax, rsp
0x14008bd4b  mov     [rax+18h], r8
0x14008bd4f  mov     [rax+10h], rdx
0x14008bd53  push    rbx
0x14008bd54  push    rsi
0x14008bd55  push    rdi
0x14008bd56  push    r12
0x14008bd58  push    r13
0x14008bd5a  push    r14
0x14008bd5c  push    r15
0x14008bd5e  sub     rsp, 40h
0x14008bd62  xor     edi, edi
0x14008bd64  or      r14, 0FFFFFFFFFFFFFFFFh
0x14008bd68  mov     [rdx], rdi
0x14008bd6b  mov     rbx, rcx
0x14008bd6e  mov     [r8], di
0x14008bd72  mov     r13d, edi
0x14008bd75  mov     [rax+20h], rdi
0x14008bd79  mov     [rax+8], edi
0x14008bd7c  test    rcx, rcx
0x14008bd7f  jnz     short loc_14008BD99
0x14008bd81  lea     r8, aPwszvolumename_0; "pwszVolumeName != NULL"
0x14008bd88  mov     edx, 30Bh; unsigned int
0x14008bd8d  lea     rcx, aBaseStorBlbUti_3; "base\\stor\\blb\\util\\volumeutils.cpp"
0x14008bd94  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14008bd99  xor     r8d, r8d; unsigned __int64
0x14008bd9c  lea     rdx, [rsp+78h+lpFileName]; unsigned __int16 **
0x14008bda4  mov     rcx, rbx; unsigned __int16 *
0x14008bda7  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14008bdac  mov     r15, [rsp+78h+lpFileName]
0x14008bdb4  mov     ebx, eax
0x14008bdb6  test    eax, eax
0x14008bdb8  js      loc_14008BFA0
0x14008bdbe  or      rax, 0FFFFFFFFFFFFFFFFh
0x14008bdc2  inc     rax
0x14008bdc5  cmp     [r15+rax*2], di
0x14008bdca  jnz     short loc_14008BDC2
0x14008bdcc  test    eax, eax
0x14008bdce  jz      short loc_14008BDDF
0x14008bdd0  dec     eax
0x14008bdd2  cmp     word ptr [r15+rax*2], 5Ch ; '\'
0x14008bdd8  jnz     short loc_14008BDDF
0x14008bdda  mov     [r15+rax*2], di
0x14008bddf  mov     [rsp+78h+hTemplateFile], rdi; hTemplateFile
0x14008bde4  mov     r8d, 3; dwShareMode
0x14008bdea  mov     [rsp+78h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x14008bdee  xor     r9d, r9d; lpSecurityAttributes
0x14008bdf1  mov     edx, 80000000h; dwDesiredAccess
0x14008bdf6  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x14008bdfb  mov     rcx, r15; lpFileName
0x14008bdfe  call    cs:__imp_CreateFileW
0x14008be04  mov     r14, rax
0x14008be07  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14008be0b  jnz     short loc_14008BE2B
0x14008be0d  call    cs:__imp_GetLastError
0x14008be13  mov     ebx, eax
0x14008be15  test    eax, eax
0x14008be17  jle     loc_14008BFA0
0x14008be1d  movzx   ebx, ax
0x14008be20  or      ebx, 80070000h
0x14008be26  jmp     loc_14008BFA0
0x14008be2b  mov     edi, 100h
0x14008be30  mov     edx, edi; cb
0x14008be32  mov     rcx, r13; pv
0x14008be35  mov     r12d, edi
0x14008be38  call    cs:__imp_CoTaskMemRealloc
0x14008be3e  mov     rsi, rax
0x14008be41  test    rax, rax
0x14008be44  jz      loc_14008BF9B
0x14008be4a  mov     r8d, r12d; Size
0x14008be4d  xor     edx, edx; Val
0x14008be4f  mov     rcx, rax; void *
0x14008be52  mov     r13, rax
0x14008be55  call    memset_0
0x14008be5a  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x14008be63  lea     rax, [rsp+78h+BytesReturned]
0x14008be6b  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x14008be70  xor     r9d, r9d; nInBufferSize
0x14008be73  mov     [rsp+78h+dwFlagsAndAttributes], edi; nOutBufferSize
0x14008be77  xor     r8d, r8d; lpInBuffer
0x14008be7a  mov     edx, 4D0000h; dwIoControlCode
0x14008be7f  mov     qword ptr [rsp+78h+dwCreationDisposition], r13; lpOutBuffer
0x14008be84  mov     rcx, r14; hDevice
0x14008be87  call    cs:__imp_DeviceIoControl
0x14008be8d  test    eax, eax
0x14008be8f  jnz     short loc_14008BEE9
0x14008be91  call    cs:__imp_GetLastError
0x14008be97  mov     ebx, eax
0x14008be99  cmp     eax, 7Ah ; 'z'
0x14008be9c  jz      short loc_14008BEB4
0x14008be9e  cmp     eax, 0EAh
0x14008bea3  jz      short loc_14008BEB4
0x14008bea5  test    eax, eax
0x14008bea7  jle     short loc_14008BEB6
0x14008bea9  movzx   ebx, ax
0x14008beac  or      ebx, 80070000h
0x14008beb2  jmp     short loc_14008BEB6
0x14008beb4  xor     ebx, ebx
0x14008beb6  test    ebx, ebx
0x14008beb8  js      loc_14008BFA0
0x14008bebe  add     edi, edi
0x14008bec0  cmp     edi, 8000h
0x14008bec6  jb      loc_14008BE30
0x14008becc  call    cs:__imp_GetLastError
0x14008bed2  mov     ebx, eax
0x14008bed4  test    eax, eax
0x14008bed6  jle     short loc_14008BEE1
0x14008bed8  movzx   ebx, ax
0x14008bedb  or      ebx, 80070000h
0x14008bee1  test    ebx, ebx
0x14008bee3  js      loc_14008BFA0
0x14008bee9  movzx   eax, word ptr [rsi]
0x14008beec  cmp     eax, edi
0x14008beee  jb      short loc_14008BF08
0x14008bef0  lea     r8, aPmountdevidUni; "pMountDevId->UniqueIdLength < dwBufSize"
0x14008bef7  mov     edx, 361h; unsigned int
0x14008befc  lea     rcx, aBaseStorBlbUti_3; "base\\stor\\blb\\util\\volumeutils.cpp"
0x14008bf03  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14008bf08  movzx   eax, word ptr [rsi]
0x14008bf0b  cmp     eax, edi
0x14008bf0d  jb      short loc_14008BF51
0x14008bf0f  mov     rcx, cs:WPP_GLOBAL_Control
0x14008bf16  lea     rdx, WPP_GLOBAL_Control
0x14008bf1d  cmp     rcx, rdx
0x14008bf20  jz      short loc_14008BF4A
0x14008bf22  test    byte ptr [rcx+1Ch], 1
0x14008bf26  jz      short loc_14008BF4A
0x14008bf28  cmp     byte ptr [rcx+19h], 2
0x14008bf2c  jb      short loc_14008BF4A
0x14008bf2e  mov     rcx, [rcx+10h]
0x14008bf32  lea     r8, WPP_4c89e0416b2b3a4e6cf04444c0dc1079_Traceguids
0x14008bf39  mov     edx, 0Fh
0x14008bf3e  mov     [rsp+78h+dwCreationDisposition], edi
0x14008bf42  mov     r9d, eax
0x14008bf45  call    WPP_SF_dd
0x14008bf4a  mov     ebx, 8000FFFFh
0x14008bf4f  jmp     short loc_14008BFA0
0x14008bf51  mov     rcx, rax; cb
0x14008bf54  call    cs:__imp_CoTaskMemAlloc
0x14008bf5a  mov     rdi, rax
0x14008bf5d  test    rax, rax
0x14008bf60  jz      short loc_14008BF9B
0x14008bf62  movzx   r8d, word ptr [rsi]; Size
0x14008bf66  xor     edx, edx; Val
0x14008bf68  mov     rcx, rax; void *
0x14008bf6b  call    memset_0
0x14008bf70  movzx   r8d, word ptr [rsi]; Size
0x14008bf74  lea     rdx, [rsi+2]; Src
0x14008bf78  mov     rcx, rdi; void *
0x14008bf7b  call    memcpy_0
0x14008bf80  movzx   eax, word ptr [rsi]
0x14008bf83  mov     rcx, [rsp+78h+arg_10]
0x14008bf8b  mov     [rcx], ax
0x14008bf8e  mov     rax, [rsp+78h+arg_8]
0x14008bf96  mov     [rax], rdi
0x14008bf99  jmp     short loc_14008BFA0
0x14008bf9b  mov     ebx, 8007000Eh
0x14008bfa0  mov     rcx, r13; pv
0x14008bfa3  call    cs:__imp_CoTaskMemFree
0x14008bfa9  xor     ecx, ecx; pv
0x14008bfab  call    cs:__imp_CoTaskMemFree
0x14008bfb1  mov     rcx, r15; pv
0x14008bfb4  call    cs:__imp_CoTaskMemFree
0x14008bfba  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14008bfbe  jz      short loc_14008BFC9
0x14008bfc0  mov     rcx, r14; hObject
0x14008bfc3  call    cs:__imp_CloseHandle
0x14008bfc9  mov     eax, ebx
0x14008bfcb  add     rsp, 40h
0x14008bfcf  pop     r15
0x14008bfd1  pop     r14
0x14008bfd3  pop     r13
0x14008bfd5  pop     r12
0x14008bfd7  pop     rdi
0x14008bfd8  pop     rsi
0x14008bfd9  pop     rbx
0x14008bfda  retn
```
