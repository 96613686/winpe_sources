# CBlbBmrRestoreAsync::SetActiveSystemPartition(void)

- ea: `0x14007e85c`
- end: `0x14007ed59`
- name: `?SetActiveSystemPartition@CBlbBmrRestoreAsync@@AEAAJXZ`
- size: `1277`
- prototype: `__int64 __fastcall(CBlbBmrRestoreAsync *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task`

## callers

- `0x14007d630`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000cbcc`
- `0x140014260`
- `0x14007e85c`
- `0x14007ed60`
- `0x14007f520`
- `0x14007f634`
- `0x140088ba4`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14007e9ec`
- `KERNEL32!CreateFileW` at `0x14007e9ec`
- `KERNEL32!CloseHandle` at `0x14007eb2c`
- `KERNEL32!CloseHandle` at `0x14007ec75`
- `KERNEL32!CloseHandle` at `0x14007eb2c`
- `KERNEL32!CloseHandle` at `0x14007ec75`
- `KERNEL32!GetLastError` at `0x14007e9fb`
- `KERNEL32!GetLastError` at `0x14007eabf`
- `KERNEL32!GetLastError` at `0x14007e9fb`
- `KERNEL32!GetLastError` at `0x14007eabf`
- `KERNEL32!DeviceIoControl` at `0x14007eab5`
- `KERNEL32!DeviceIoControl` at `0x14007eab5`
- `ole32!CoTaskMemFree` at `0x14007ea54`
- `ole32!CoTaskMemFree` at `0x14007ec4a`
- `ole32!CoTaskMemFree` at `0x14007ec5f`
- `ole32!CoTaskMemFree` at `0x14007ea54`
- `ole32!CoTaskMemFree` at `0x14007ec4a`
- `ole32!CoTaskMemFree` at `0x14007ec5f`

## string_xrefs

- `0x14007e912`: `base\stor\blb\engine\service\bmr.cpp`
- `0x14007e906`: `wszSystemPartition != NULL`

## pseudocode

```c
__int64 __fastcall CBlbBmrRestoreAsync::SetActiveSystemPartition(CBlbBmrRestoreAsync *this)
{
  PVOID *v2; // rcx
  unsigned int v3; // r9d
  unsigned int *v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 v7; // r8
  const unsigned __int16 *v8; // rdi
  int v9; // eax
  signed int v10; // ebx
  __int64 FileW; // r14
  signed int LastError; // eax
  unsigned int i; // edi
  signed int v14; // eax
  __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // r8
  DWORD BytesReturned; // [rsp+70h] [rbp+8h] BYREF
  LPCWSTR lpFileName; // [rsp+78h] [rbp+10h] BYREF
  LPVOID lpOutBuffer; // [rsp+80h] [rbp+18h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = *((_DWORD *)this + 83);
  v4 = 0;
  lpOutBuffer = 0;
  v5 = 0;
  BytesReturned = 0;
  lpFileName = 0;
  while ( (unsigned int)v5 < v3 )
  {
    v6 = *((_QWORD *)this + 33);
    v7 = 192 * v5;
    if ( (*(_BYTE *)(192 * v5 + v6 + 76) & 2) != 0 && *(_DWORD *)(v7 + v6 + 20) == 9 )
    {
      v8 = *(const unsigned __int16 **)(v7 + v6 + 112);
      if ( !v8 )
        goto LABEL_11;
LABEL_12:
      v9 = BlbutilRemoveTrailingBackslash(v8, (unsigned __int16 **)&lpFileName);
      v10 = v9;
      if ( v9 >= 0 )
      {
        FileW = (__int64)CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
        if ( FileW == -1 )
        {
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError > 0 )
            v10 = (unsigned __int16)LastError | 0x80070000;
          v2 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              95,
              (unsigned int)&WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids,
              (_DWORD)lpFileName,
              v10);
LABEL_17:
            v2 = (PVOID *)WPP_GLOBAL_Control;
          }
        }
        else
        {
          for ( i = 32; ; i += 32 )
          {
            if ( v4 )
            {
              CoTaskMemFree(v4);
              lpOutBuffer = 0;
            }
            v10 = BlbutilMemalloc(&lpOutBuffer, 1u, i);
            if ( v10 < 0 )
              break;
            v4 = (unsigned int *)lpOutBuffer;
            if ( DeviceIoControl((HANDLE)FileW, 0x560000u, 0, 0, lpOutBuffer, i, &BytesReturned, 0) )
            {
              CloseHandle((HANDLE)FileW);
              FileW = -1;
              if ( i < 8 )
              {
                v2 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_ddD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    98,
                    &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids,
                    i,
                    8,
                    -2147024362);
                  v2 = (PVOID *)WPP_GLOBAL_Control;
                }
                v10 = -2147024362;
              }
              else if ( *v4 <= (i - 8) / 0x18 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    100,
                    (unsigned int)&WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids,
                    (_DWORD)lpFileName,
                    *v4);
                }
                v15 = 0;
                v10 = 0;
                while ( 1 )
                {
                  if ( (unsigned int)v15 >= *v4 )
                    goto LABEL_63;
                  v10 = SetDiskPartionActive(v4[6 * v15 + 2], *(_QWORD *)&v4[6 * v15 + 4]);
                  if ( v10 < 0 )
                    break;
                  v15 = (unsigned int)(v15 + 1);
                }
                v2 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_diD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v16,
                    v17,
                    v4[6 * v15 + 2],
                    *(_QWORD *)&v4[6 * v15 + 4],
                    v10);
LABEL_63:
                  v2 = (PVOID *)WPP_GLOBAL_Control;
                  goto LABEL_64;
                }
              }
              else
              {
                v2 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
                  v2 = (PVOID *)WPP_GLOBAL_Control;
                }
                v10 = -2147418113;
              }
              goto LABEL_64;
            }
            v14 = GetLastError();
            v10 = v14;
            if ( v14 != 234 && v14 != 122 )
            {
              if ( v14 > 0 )
                v10 = (unsigned __int16)v14 | 0x80070000;
              v2 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
                goto LABEL_17;
              }
              goto LABEL_64;
            }
          }
          v2 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
            v4 = (unsigned int *)lpOutBuffer;
            goto LABEL_17;
          }
          v4 = (unsigned int *)lpOutBuffer;
        }
      }
      else
      {
        FileW = -1;
        v2 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            94,
            (unsigned int)&WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids,
            (_DWORD)v8,
            v9);
          goto LABEL_17;
        }
      }
LABEL_64:
      if ( lpFileName )
      {
        CoTaskMemFree((LPVOID)lpFileName);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 )
      {
        CoTaskMemFree(v4);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( FileW != -1 )
      {
        CloseHandle((HANDLE)FileW);
        goto LABEL_70;
      }
      goto LABEL_71;
    }
    v5 = (unsigned int)(v5 + 1);
  }
  v8 = 0;
  if ( (_DWORD)v5 != v3 )
  {
LABEL_11:
    BlbAssert("base\\stor\\blb\\engine\\service\\bmr.cpp", 0x653u, "wszSystemPartition != NULL");
    goto LABEL_12;
  }
  v10 = 0;
  if ( v2 == &WPP_GLOBAL_Control )
    return (unsigned int)v10;
  if ( (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 3u )
  {
    WPP_SF_(v2[2], 93, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
LABEL_70:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_71:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 4u )
    WPP_SF_(v2[2], 102, &WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14007e85c  mov     [rsp+arg_18], rbx
0x14007e861  push    rbp
0x14007e862  push    rsi
0x14007e863  push    rdi
0x14007e864  push    r13
0x14007e866  push    r14
0x14007e868  sub     rsp, 40h
0x14007e86c  mov     rbx, rcx
0x14007e86f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e876  lea     rbp, WPP_GLOBAL_Control
0x14007e87d  mov     r13d, 1
0x14007e883  cmp     rcx, rbp
0x14007e886  jz      short loc_14007E8AF
0x14007e888  test    [rcx+1Ch], r13b
0x14007e88c  jz      short loc_14007E8AF
0x14007e88e  cmp     byte ptr [rcx+19h], 4
0x14007e892  jb      short loc_14007E8AF
0x14007e894  mov     rcx, [rcx+10h]
0x14007e898  lea     edx, [r13+5Bh]
0x14007e89c  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007e8a3  call    WPP_SF_
0x14007e8a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e8af  mov     r9d, [rbx+14Ch]
0x14007e8b6  xor     esi, esi
0x14007e8b8  mov     [rsp+68h+lpOutBuffer], rsi
0x14007e8c0  xor     edx, edx
0x14007e8c2  mov     [rsp+68h+BytesReturned], esi
0x14007e8c6  mov     [rsp+68h+lpFileName], 0
0x14007e8cf  cmp     edx, r9d
0x14007e8d2  jnb     loc_14007E984
0x14007e8d8  mov     rdi, [rbx+108h]
0x14007e8df  lea     r8, [rdx+rdx*2]
0x14007e8e3  shl     r8, 6
0x14007e8e7  test    byte ptr [r8+rdi+4Ch], 2
0x14007e8ed  jbe     short loc_14007E8F7
0x14007e8ef  cmp     dword ptr [r8+rdi+14h], 9
0x14007e8f5  jz      short loc_14007E8FC
0x14007e8f7  add     edx, r13d
0x14007e8fa  jmp     short loc_14007E8CF
0x14007e8fc  mov     rdi, [r8+rdi+70h]
0x14007e901  test    rdi, rdi
0x14007e904  jnz     short loc_14007E91E
0x14007e906  lea     r8, aWszsystemparti; "wszSystemPartition != NULL"
0x14007e90d  mov     edx, 653h; unsigned int
0x14007e912  lea     rcx, aBaseStorBlbEng_10; "base\\stor\\blb\\engine\\service\\bmr.c"...
0x14007e919  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007e91e  lea     rdx, [rsp+68h+lpFileName]; unsigned __int16 **
0x14007e923  mov     rcx, rdi; unsigned __int16 *
0x14007e926  call    ?BlbutilRemoveTrailingBackslash@@YAJPEBGPEAPEAG@Z; BlbutilRemoveTrailingBackslash(ushort const *,ushort * *)
0x14007e92b  mov     ebx, eax
0x14007e92d  test    eax, eax
0x14007e92f  jns     loc_14007E9C6
0x14007e935  or      r14, 0FFFFFFFFFFFFFFFFh
0x14007e939  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e940  cmp     rcx, rbp
0x14007e943  jz      loc_14007EC3D
0x14007e949  test    [rcx+1Ch], r13b
0x14007e94d  jz      loc_14007EC3D
0x14007e953  cmp     byte ptr [rcx+19h], 2
0x14007e957  jb      loc_14007EC3D
0x14007e95d  lea     edx, [r14+5Fh]
0x14007e961  mov     [rsp+68h+dwCreationDisposition], eax
0x14007e965  mov     r9, rdi
0x14007e968  mov     rcx, [rcx+10h]
0x14007e96c  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007e973  call    WPP_SF_Sd
0x14007e978  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e97f  jmp     loc_14007EC3D
0x14007e984  xor     edi, edi
0x14007e986  cmp     edx, r9d
0x14007e989  jnz     loc_14007E906
0x14007e98f  xor     ebx, ebx
0x14007e991  cmp     rcx, rbp
0x14007e994  jz      loc_14007ECA8
0x14007e99a  test    [rcx+1Ch], r13b
0x14007e99e  jz      loc_14007EC82
0x14007e9a4  cmp     byte ptr [rcx+19h], 3
0x14007e9a8  jb      loc_14007EC82
0x14007e9ae  mov     rcx, [rcx+10h]
0x14007e9b2  lea     edx, [rdi+5Dh]
0x14007e9b5  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007e9bc  call    WPP_SF_
0x14007e9c1  jmp     loc_14007EC7B
0x14007e9c6  mov     rcx, [rsp+68h+lpFileName]; lpFileName
0x14007e9cb  xor     r9d, r9d; lpSecurityAttributes
0x14007e9ce  mov     [rsp+68h+hTemplateFile], rsi; hTemplateFile
0x14007e9d3  mov     edx, 80000000h; dwDesiredAccess
0x14007e9d8  mov     [rsp+68h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x14007e9e0  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x14007e9e8  lea     r8d, [r9+3]; dwShareMode
0x14007e9ec  call    cs:__imp_CreateFileW
0x14007e9f2  mov     r14, rax
0x14007e9f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007e9f9  jnz     short loc_14007EA47
0x14007e9fb  call    cs:__imp_GetLastError
0x14007ea01  mov     ebx, eax
0x14007ea03  test    eax, eax
0x14007ea05  jle     short loc_14007EA10
0x14007ea07  movzx   ebx, ax
0x14007ea0a  or      ebx, 80070000h
0x14007ea10  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ea17  cmp     rcx, rbp
0x14007ea1a  jz      loc_14007EC3D
0x14007ea20  test    [rcx+1Ch], r13b
0x14007ea24  jz      loc_14007EC3D
0x14007ea2a  cmp     byte ptr [rcx+19h], 2
0x14007ea2e  jb      loc_14007EC3D
0x14007ea34  mov     r9, [rsp+68h+lpFileName]
0x14007ea39  mov     edx, 5Fh ; '_'
0x14007ea3e  mov     [rsp+68h+dwCreationDisposition], ebx
0x14007ea42  jmp     loc_14007E968
0x14007ea47  mov     edi, 20h ; ' '
0x14007ea4c  test    rsi, rsi
0x14007ea4f  jz      short loc_14007EA66
0x14007ea51  mov     rcx, rsi; pv
0x14007ea54  call    cs:__imp_CoTaskMemFree
0x14007ea5a  mov     [rsp+68h+lpOutBuffer], 0
0x14007ea66  mov     r8d, edi; unsigned int
0x14007ea69  lea     rcx, [rsp+68h+lpOutBuffer]; void **
0x14007ea71  mov     edx, r13d; unsigned int
0x14007ea74  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x14007ea79  mov     ebx, eax
0x14007ea7b  test    eax, eax
0x14007ea7d  js      loc_14007ED0F
0x14007ea83  mov     rsi, [rsp+68h+lpOutBuffer]
0x14007ea8b  lea     rax, [rsp+68h+BytesReturned]
0x14007ea90  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x14007ea99  xor     r9d, r9d; nInBufferSize
0x14007ea9c  mov     [rsp+68h+hTemplateFile], rax; lpBytesReturned
0x14007eaa1  xor     r8d, r8d; lpInBuffer
0x14007eaa4  mov     [rsp+68h+dwFlagsAndAttributes], edi; nOutBufferSize
0x14007eaa8  mov     edx, 560000h; dwIoControlCode
0x14007eaad  mov     rcx, r14; hDevice
0x14007eab0  mov     qword ptr [rsp+68h+dwCreationDisposition], rsi; lpOutBuffer
0x14007eab5  call    cs:__imp_DeviceIoControl
0x14007eabb  test    eax, eax
0x14007eabd  jnz     short loc_14007EB29
0x14007eabf  call    cs:__imp_GetLastError
0x14007eac5  mov     ebx, eax
0x14007eac7  cmp     eax, 0EAh
0x14007eacc  jz      short loc_14007EAD3
0x14007eace  cmp     eax, 7Ah ; 'z'
0x14007ead1  jnz     short loc_14007EADB
0x14007ead3  add     edi, 20h ; ' '
0x14007ead6  jmp     loc_14007EA4C
0x14007eadb  test    eax, eax
0x14007eadd  jle     short loc_14007EAE8
0x14007eadf  movzx   ebx, ax
0x14007eae2  or      ebx, 80070000h
0x14007eae8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007eaef  cmp     rcx, rbp
0x14007eaf2  jz      loc_14007EC3D
0x14007eaf8  test    [rcx+1Ch], r13b
0x14007eafc  jz      loc_14007EC3D
0x14007eb02  cmp     byte ptr [rcx+19h], 2
0x14007eb06  jb      loc_14007EC3D
0x14007eb0c  mov     rcx, [rcx+10h]
0x14007eb10  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007eb17  mov     edx, 61h ; 'a'
0x14007eb1c  mov     r9d, ebx
0x14007eb1f  call    WPP_SF_d
0x14007eb24  jmp     loc_14007E978
0x14007eb29  mov     rcx, r14; hObject
0x14007eb2c  call    cs:__imp_CloseHandle
0x14007eb32  or      r14, 0FFFFFFFFFFFFFFFFh
0x14007eb36  cmp     edi, 8
0x14007eb39  jb      loc_14007ECBE
0x14007eb3f  mov     r8d, [rsi]
0x14007eb42  lea     ecx, [rdi-8]
0x14007eb45  mov     rax, 0AAAAAAAAAAAAAAABh
0x14007eb4f  mul     rcx
0x14007eb52  shr     rdx, 4
0x14007eb56  cmp     r8d, edx
0x14007eb59  jbe     short loc_14007EB98
0x14007eb5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007eb62  cmp     rcx, rbp
0x14007eb65  jz      short loc_14007EB8E
0x14007eb67  test    [rcx+1Ch], r13b
0x14007eb6b  jz      short loc_14007EB8E
0x14007eb6d  cmp     byte ptr [rcx+19h], 2
0x14007eb71  jb      short loc_14007EB8E
0x14007eb73  mov     rcx, [rcx+10h]
0x14007eb77  lea     edx, [r14+64h]
0x14007eb7b  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007eb82  call    WPP_SF_
0x14007eb87  mov     rcx, cs:WPP_GLOBAL_Control
0x14007eb8e  mov     ebx, 8000FFFFh
0x14007eb93  jmp     loc_14007EC3D
0x14007eb98  mov     rcx, cs:WPP_GLOBAL_Control
0x14007eb9f  cmp     rcx, rbp
0x14007eba2  jz      short loc_14007EBCF
0x14007eba4  test    [rcx+1Ch], r13b
0x14007eba8  jz      short loc_14007EBCF
0x14007ebaa  cmp     byte ptr [rcx+19h], 4
0x14007ebae  jb      short loc_14007EBCF
0x14007ebb0  mov     r9, [rsp+68h+lpFileName]
0x14007ebb5  mov     edx, 64h ; 'd'
0x14007ebba  mov     rcx, [rcx+10h]
0x14007ebbe  mov     [rsp+68h+dwCreationDisposition], r8d
0x14007ebc3  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007ebca  call    WPP_SF_Sd
0x14007ebcf  xor     edi, edi
0x14007ebd1  xor     ebx, ebx
0x14007ebd3  cmp     edi, [rsi]
0x14007ebd5  jnb     short loc_14007EC2F
0x14007ebd7  lea     rbp, [rdi+rdi*2]
0x14007ebdb  mov     rdx, [rsi+rbp*8+10h]; __int64
0x14007ebe0  mov     ecx, [rsi+rbp*8+8]; unsigned int
0x14007ebe4  call    ?SetDiskPartionActive@@YAJK_J@Z; SetDiskPartionActive(ulong,__int64)
0x14007ebe9  mov     ebx, eax
0x14007ebeb  test    eax, eax
0x14007ebed  js      short loc_14007EBF4
0x14007ebef  add     edi, r13d
0x14007ebf2  jmp     short loc_14007EBD3
0x14007ebf4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ebfb  lea     rax, WPP_GLOBAL_Control
0x14007ec02  cmp     rcx, rax
0x14007ec05  jz      short loc_14007EC36
0x14007ec07  test    [rcx+1Ch], r13b
0x14007ec0b  jz      short loc_14007EC36
0x14007ec0d  cmp     byte ptr [rcx+19h], 2
0x14007ec11  jb      short loc_14007EC36
0x14007ec13  mov     rax, [rsi+rbp*8+10h]
0x14007ec18  mov     r9d, [rsi+rbp*8+8]
0x14007ec1d  mov     rcx, [rcx+10h]
0x14007ec21  mov     [rsp+68h+dwFlagsAndAttributes], ebx
0x14007ec25  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x14007ec2a  call    WPP_SF_diD
0x14007ec2f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ec36  lea     rbp, WPP_GLOBAL_Control
0x14007ec3d  cmp     [rsp+68h+lpFileName], 0
0x14007ec43  jz      short loc_14007EC57
0x14007ec45  mov     rcx, [rsp+68h+lpFileName]; pv
0x14007ec4a  call    cs:__imp_CoTaskMemFree
0x14007ec50  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ec57  test    rsi, rsi
0x14007ec5a  jz      short loc_14007EC6C
0x14007ec5c  mov     rcx, rsi; pv
0x14007ec5f  call    cs:__imp_CoTaskMemFree
0x14007ec65  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ec6c  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14007ec70  jz      short loc_14007EC82
0x14007ec72  mov     rcx, r14; hObject
0x14007ec75  call    cs:__imp_CloseHandle
0x14007ec7b  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ec82  cmp     rcx, rbp
0x14007ec85  jz      short loc_14007ECA8
0x14007ec87  test    [rcx+1Ch], r13b
0x14007ec8b  jz      short loc_14007ECA8
0x14007ec8d  cmp     byte ptr [rcx+19h], 4
0x14007ec91  jb      short loc_14007ECA8
0x14007ec93  mov     rcx, [rcx+10h]
0x14007ec97  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007ec9e  mov     edx, 66h ; 'f'
0x14007eca3  call    WPP_SF_
0x14007eca8  mov     eax, ebx
0x14007ecaa  mov     rbx, [rsp+68h+arg_18]
0x14007ecb2  add     rsp, 40h
0x14007ecb6  pop     r14
0x14007ecb8  pop     r13
0x14007ecba  pop     rdi
0x14007ecbb  pop     rsi
0x14007ecbc  pop     rbp
0x14007ecbd  retn
0x14007ecbe  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ecc5  cmp     rcx, rbp
0x14007ecc8  jz      short loc_14007ED05
0x14007ecca  test    [rcx+1Ch], r13b
0x14007ecce  jz      short loc_14007ED05
0x14007ecd0  cmp     byte ptr [rcx+19h], 2
0x14007ecd4  jb      short loc_14007ED05
0x14007ecd6  mov     rcx, [rcx+10h]
0x14007ecda  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007ece1  mov     edx, 62h ; 'b'
0x14007ece6  mov     [rsp+68h+dwFlagsAndAttributes], 80070216h
0x14007ecee  mov     r9d, edi
0x14007ecf1  mov     [rsp+68h+dwCreationDisposition], 8
0x14007ecf9  call    WPP_SF_ddD
0x14007ecfe  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ed05  mov     ebx, 80070216h
0x14007ed0a  jmp     loc_14007EC3D
0x14007ed0f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ed16  cmp     rcx, rbp
0x14007ed19  jz      short loc_14007ED4C
0x14007ed1b  test    [rcx+1Ch], r13b
0x14007ed1f  jz      short loc_14007ED4C
0x14007ed21  cmp     byte ptr [rcx+19h], 2
0x14007ed25  jb      short loc_14007ED4C
0x14007ed27  mov     rcx, [rcx+10h]
0x14007ed2b  lea     r8, WPP_384514a4dd4e3557dfddb7175096e6fb_Traceguids
0x14007ed32  mov     edx, 60h ; '`'
0x14007ed37  mov     r9d, eax
0x14007ed3a  call    WPP_SF_d
0x14007ed3f  mov     rsi, [rsp+68h+lpOutBuffer]
0x14007ed47  jmp     loc_14007E978
0x14007ed4c  mov     rsi, [rsp+68h+lpOutBuffer]
0x14007ed54  jmp     loc_14007EC3D
```
