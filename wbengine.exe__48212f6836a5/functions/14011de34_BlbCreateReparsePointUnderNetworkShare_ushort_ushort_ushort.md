# BlbCreateReparsePointUnderNetworkShare(ushort *,ushort *,ushort * *)

- ea: `0x14011de34`
- end: `0x14011e299`
- name: `?BlbCreateReparsePointUnderNetworkShare@@YAJPEAG0PEAPEAG@Z`
- size: `1125`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14004a690`
- `0x14004b420`

## callees

- `0x1400063b4`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x140051e98`
- `0x14008863c`
- `0x140094084`
- `0x1400945d0`
- `0x1400fefd4`
- `0x1400ff23c`
- `0x14011de34`
- `0x140134cd2`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x14011df0a`
- `KERNEL32!CreateDirectoryW` at `0x14011df0a`
- `KERNEL32!CreateFileW` at `0x14011dfc6`
- `KERNEL32!CreateFileW` at `0x14011dfc6`
- `KERNEL32!CloseHandle` at `0x14011e208`
- `KERNEL32!CloseHandle` at `0x14011e208`
- `KERNEL32!GetLastError` at `0x14011df1f`
- `KERNEL32!GetLastError` at `0x14011e008`
- `KERNEL32!GetLastError` at `0x14011e10c`
- `KERNEL32!GetLastError` at `0x14011df1f`
- `KERNEL32!GetLastError` at `0x14011e008`
- `KERNEL32!GetLastError` at `0x14011e10c`
- `KERNEL32!DeviceIoControl` at `0x14011e102`
- `KERNEL32!DeviceIoControl` at `0x14011e102`
- `ole32!CoTaskMemAlloc` at `0x14011e070`
- `ole32!CoTaskMemAlloc` at `0x14011e170`
- `ole32!CoTaskMemAlloc` at `0x14011e070`
- `ole32!CoTaskMemAlloc` at `0x14011e170`
- `ole32!CoTaskMemFree` at `0x14011e1fe`
- `ole32!CoTaskMemFree` at `0x14011e216`
- `ole32!CoTaskMemFree` at `0x14011e22b`
- `ole32!CoTaskMemFree` at `0x14011e239`
- `ole32!CoTaskMemFree` at `0x14011e248`
- `ole32!CoTaskMemFree` at `0x14011e1fe`
- `ole32!CoTaskMemFree` at `0x14011e216`
- `ole32!CoTaskMemFree` at `0x14011e22b`
- `ole32!CoTaskMemFree` at `0x14011e239`
- `ole32!CoTaskMemFree` at `0x14011e248`

## string_xrefs

- `0x14011e198`: `WsbMountedVolumes`
- `0x14011deb4`: `pwszNetShareName != NULL`

## pseudocode

```c
__int64 __fastcall BlbCreateReparsePointUnderNetworkShare(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rdi
  void *v7; // r14
  int ReparsePointForMountedVolume; // eax
  WCHAR *v9; // rsi
  int ReparseDirectoryNameForMountedVolume; // ebx
  BOOL v11; // ebx
  signed int v12; // eax
  int appended; // eax
  __int64 v14; // rbx
  signed int LastError; // eax
  char *v16; // rax
  unsigned __int16 *v17; // r15
  unsigned __int64 v18; // rbx
  signed int v19; // eax
  unsigned __int16 *v20; // rax
  unsigned int v21; // r11d
  LPCWSTR lpPathName; // [rsp+40h] [rbp-28h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+48h] [rbp-20h] BYREF
  DWORD BytesReturned; // [rsp+B0h] [rbp+48h] BYREF
  unsigned __int16 *v26; // [rsp+B8h] [rbp+50h]
  void *Src; // [rsp+C0h] [rbp+58h] BYREF
  LPVOID pv; // [rsp+C8h] [rbp+60h] BYREF

  v26 = a2;
  v3 = 0;
  Src = 0;
  BytesReturned = 0;
  lpPathName = 0;
  pv = 0;
  v7 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !a1 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbnetworkutils.cpp", 0x235u, "wszDeviceName != NULL");
  if ( !a2 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbnetworkutils.cpp", 0x236u, "wszVolumeGuid != NULL");
  if ( !a3 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbnetworkutils.cpp", 0x237u, "pwszNetShareName != NULL");
  *a3 = 0;
  ReparsePointForMountedVolume = BlbGetReparsePointForMountedVolume(a1, a2, (unsigned __int16 **)&lpPathName);
  v9 = (WCHAR *)lpPathName;
  ReparseDirectoryNameForMountedVolume = ReparsePointForMountedVolume;
  if ( ReparsePointForMountedVolume >= 0 )
  {
    ReparseDirectoryNameForMountedVolume = BlbutilCreateSecurityDescriptorForAdminsAndBOs(&SecurityAttributes);
    if ( ReparseDirectoryNameForMountedVolume >= 0 )
    {
      v11 = CreateDirectoryW(v9, &SecurityAttributes);
      BlbutilFreeSecurityDescriptor(&SecurityAttributes);
      if ( v11 )
      {
LABEL_17:
        appended = BlbutilAppendString(a1, L"\\", (unsigned __int16 **)&Src);
        v7 = Src;
        ReparseDirectoryNameForMountedVolume = appended;
        if ( appended >= 0 )
        {
          v14 = -1;
          do
            ++v14;
          while ( *((_WORD *)Src + v14) );
          Src = CreateFileW(v9, 0xC0000000, 3u, 0, 3u, 0x2200080u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          if ( Src == (void *)-1LL )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids, v9);
            }
            LastError = GetLastError();
            ReparseDirectoryNameForMountedVolume = LastError;
            if ( LastError > 0 )
              ReparseDirectoryNameForMountedVolume = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v16 = (char *)CoTaskMemAlloc(0x4000u);
            v17 = (unsigned __int16 *)v16;
            if ( v16 )
            {
              *(_DWORD *)v16 = -1610612733;
              v18 = (unsigned __int16)(2 * v14);
              *((_WORD *)v16 + 5) = v18;
              *((_WORD *)v16 + 2) = v18 + 12;
              *(_DWORD *)(v16 + 6) = 0;
              *((_WORD *)v16 + 6) = v18 + 2;
              *((_WORD *)v16 + 7) = 0;
              memcpy_0(v16 + 16, v7, (unsigned int)v18);
              v17[9] = 63;
              *(_DWORD *)&v17[(v18 >> 1) + 8] = 0;
              if ( DeviceIoControl(Src, 0x900A4u, v17, v17[2] + 8, 0, 0, &BytesReturned, 0) )
              {
                v20 = (unsigned __int16 *)CoTaskMemAlloc(0x208u);
                v3 = v20;
                if ( v20 )
                {
                  memset_0(v20, 0, 0x208u);
                  ReparseDirectoryNameForMountedVolume = StringCchCopyW(v3, 0x104u, L"WsbMountedVolumes");
                  if ( ReparseDirectoryNameForMountedVolume >= 0 )
                  {
                    ReparseDirectoryNameForMountedVolume = StringCchCatW(v3, v21, L"\\");
                    if ( ReparseDirectoryNameForMountedVolume >= 0 )
                    {
                      ReparseDirectoryNameForMountedVolume = BlbGetReparseDirectoryNameForMountedVolume(
                                                               a1,
                                                               v26,
                                                               (unsigned __int16 **)&pv);
                      if ( ReparseDirectoryNameForMountedVolume >= 0 )
                      {
                        ReparseDirectoryNameForMountedVolume = StringCchCatW(v3, 260, (unsigned __int16 *)pv);
                        if ( ReparseDirectoryNameForMountedVolume >= 0 )
                        {
                          *a3 = v3;
                          v3 = 0;
                        }
                      }
                    }
                  }
                }
                else
                {
                  ReparseDirectoryNameForMountedVolume = -2147024882;
                }
              }
              else
              {
                v19 = GetLastError();
                ReparseDirectoryNameForMountedVolume = v19;
                if ( v19 > 0 )
                  ReparseDirectoryNameForMountedVolume = (unsigned __int16)v19 | 0x80070000;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids);
                }
              }
              CoTaskMemFree(v17);
            }
            else
            {
              ReparseDirectoryNameForMountedVolume = -2147024882;
            }
            CloseHandle(Src);
            if ( v3 )
              CoTaskMemFree(v3);
          }
        }
        goto LABEL_50;
      }
      v12 = GetLastError();
      ReparseDirectoryNameForMountedVolume = v12;
      if ( v12 > 0 )
        ReparseDirectoryNameForMountedVolume = (unsigned __int16)v12 | 0x80070000;
      if ( ReparseDirectoryNameForMountedVolume == -2147024713 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids, v9);
        }
        goto LABEL_17;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids,
          (_DWORD)v9,
          ReparseDirectoryNameForMountedVolume);
      }
    }
  }
LABEL_50:
  if ( v7 )
    CoTaskMemFree(v7);
  if ( v9 )
    CoTaskMemFree(v9);
  if ( pv )
    CoTaskMemFree(pv);
  if ( ReparseDirectoryNameForMountedVolume < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      (unsigned int)WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids,
      (_DWORD)a1,
      ReparseDirectoryNameForMountedVolume);
  }
  return (unsigned int)ReparseDirectoryNameForMountedVolume;
}

```

## disassembly

```asm
0x14011de34  mov     [rsp-40h+arg_8], rdx
0x14011de39  push    rbp
0x14011de3a  push    rbx
0x14011de3b  push    rsi
0x14011de3c  push    rdi
0x14011de3d  push    r12
0x14011de3f  push    r13
0x14011de41  push    r14
0x14011de43  push    r15
0x14011de45  mov     rbp, rsp
0x14011de48  sub     rsp, 68h
0x14011de4c  xor     edi, edi
0x14011de4e  lea     rsi, aBaseStorBlbEng_42; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x14011de55  xor     eax, eax
0x14011de57  mov     [rbp+Src], rdi
0x14011de5b  mov     [rbp+BytesReturned], edi
0x14011de5e  xorps   xmm0, xmm0
0x14011de61  mov     [rbp+lpPathName], rdi
0x14011de65  mov     r13, r8
0x14011de68  mov     [rbp+pv], rdi
0x14011de6c  mov     rbx, rdx
0x14011de6f  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x14011de73  mov     r12, rcx
0x14011de76  mov     r14d, edi
0x14011de79  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x14011de7d  test    rcx, rcx
0x14011de80  jnz     short loc_14011DE96
0x14011de82  lea     r8, aWszdevicenameN; "wszDeviceName != NULL"
0x14011de89  mov     edx, 235h; unsigned int
0x14011de8e  mov     rcx, rsi; char *
0x14011de91  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14011de96  test    rbx, rbx
0x14011de99  jnz     short loc_14011DEAF
0x14011de9b  lea     r8, aWszvolumeguidN; "wszVolumeGuid != NULL"
0x14011dea2  mov     edx, 236h; unsigned int
0x14011dea7  mov     rcx, rsi; char *
0x14011deaa  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14011deaf  test    r13, r13
0x14011deb2  jnz     short loc_14011DEC8
0x14011deb4  lea     r8, aPwsznetsharena; "pwszNetShareName != NULL"
0x14011debb  mov     edx, 237h; unsigned int
0x14011dec0  mov     rcx, rsi; char *
0x14011dec3  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14011dec8  lea     r8, [rbp+lpPathName]; unsigned __int16 **
0x14011decc  mov     [r13+0], rdi
0x14011ded0  mov     rdx, rbx; unsigned __int16 *
0x14011ded3  mov     rcx, r12; unsigned __int16 *
0x14011ded6  call    ?BlbGetReparsePointForMountedVolume@@YAJPEAG0PEAPEAG@Z; BlbGetReparsePointForMountedVolume(ushort *,ushort *,ushort * *)
0x14011dedb  mov     rsi, [rbp+lpPathName]
0x14011dedf  mov     ebx, eax
0x14011dee1  lea     r15, WPP_GLOBAL_Control
0x14011dee8  test    eax, eax
0x14011deea  js      loc_14011E223
0x14011def0  lea     rcx, [rbp+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x14011def4  call    ?BlbutilCreateSecurityDescriptorForAdminsAndBOs@@YAJPEAU_SECURITY_ATTRIBUTES@@@Z; BlbutilCreateSecurityDescriptorForAdminsAndBOs(_SECURITY_ATTRIBUTES *)
0x14011def9  mov     ebx, eax
0x14011defb  test    eax, eax
0x14011defd  js      loc_14011E223
0x14011df03  lea     rdx, [rbp+SecurityAttributes]; lpSecurityAttributes
0x14011df07  mov     rcx, rsi; lpPathName
0x14011df0a  call    cs:__imp_CreateDirectoryW
0x14011df10  lea     rcx, [rbp+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x14011df14  mov     ebx, eax
0x14011df16  call    ?BlbutilFreeSecurityDescriptor@@YAXPEAU_SECURITY_ATTRIBUTES@@@Z; BlbutilFreeSecurityDescriptor(_SECURITY_ATTRIBUTES *)
0x14011df1b  test    ebx, ebx
0x14011df1d  jnz     short loc_14011DF70
0x14011df1f  call    cs:__imp_GetLastError
0x14011df25  mov     ebx, eax
0x14011df27  test    eax, eax
0x14011df29  jle     short loc_14011DF34
0x14011df2b  movzx   ebx, ax
0x14011df2e  or      ebx, 80070000h
0x14011df34  cmp     ebx, 800700B7h
0x14011df3a  jnz     loc_14011E026
0x14011df40  mov     rcx, cs:WPP_GLOBAL_Control
0x14011df47  cmp     rcx, r15
0x14011df4a  jz      short loc_14011DF70
0x14011df4c  test    byte ptr [rcx+1Ch], 1
0x14011df50  jz      short loc_14011DF70
0x14011df52  cmp     byte ptr [rcx+19h], 3
0x14011df56  jb      short loc_14011DF70
0x14011df58  mov     rcx, [rcx+10h]
0x14011df5c  lea     r8, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids
0x14011df63  mov     edx, 1Eh
0x14011df68  mov     r9, rsi
0x14011df6b  call    WPP_SF_S
0x14011df70  lea     r8, [rbp+Src]; unsigned __int16 **
0x14011df74  mov     rcx, r12; unsigned __int16 *
0x14011df77  lea     rdx, asc_14013C090; "\\"
0x14011df7e  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x14011df83  mov     r14, [rbp+Src]
0x14011df87  mov     ebx, eax
0x14011df89  test    eax, eax
0x14011df8b  js      loc_14011E223
0x14011df91  or      rax, 0FFFFFFFFFFFFFFFFh
0x14011df95  mov     rbx, rax
0x14011df98  inc     rbx
0x14011df9b  cmp     [r14+rbx*2], di
0x14011dfa0  jnz     short loc_14011DF98
0x14011dfa2  mov     [rsp+68h+hTemplateFile], rax; hTemplateFile
0x14011dfa7  xor     r9d, r9d; lpSecurityAttributes
0x14011dfaa  mov     eax, 3
0x14011dfaf  mov     [rsp+68h+dwFlagsAndAttributes], 2200080h; dwFlagsAndAttributes
0x14011dfb7  mov     r8d, eax; dwShareMode
0x14011dfba  mov     [rsp+68h+dwCreationDisposition], eax; dwCreationDisposition
0x14011dfbe  mov     edx, 0C0000000h; dwDesiredAccess
0x14011dfc3  mov     rcx, rsi; lpFileName
0x14011dfc6  call    cs:__imp_CreateFileW
0x14011dfcc  mov     [rbp+Src], rax
0x14011dfd0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14011dfd4  jnz     loc_14011E06B
0x14011dfda  mov     rcx, cs:WPP_GLOBAL_Control
0x14011dfe1  cmp     rcx, r15
0x14011dfe4  jz      short loc_14011E008
0x14011dfe6  test    byte ptr [rcx+1Ch], 1
0x14011dfea  jz      short loc_14011E008
0x14011dfec  cmp     byte ptr [rcx+19h], 2
0x14011dff0  jb      short loc_14011E008
0x14011dff2  mov     rcx, [rcx+10h]
0x14011dff6  lea     edx, [rax+21h]
0x14011dff9  mov     r9, rsi
0x14011dffc  lea     r8, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids
0x14011e003  call    WPP_SF_S
0x14011e008  call    cs:__imp_GetLastError
0x14011e00e  mov     ebx, eax
0x14011e010  test    eax, eax
0x14011e012  jle     loc_14011E223
0x14011e018  movzx   ebx, ax
0x14011e01b  or      ebx, 80070000h
0x14011e021  jmp     loc_14011E223
0x14011e026  mov     rcx, cs:WPP_GLOBAL_Control
0x14011e02d  cmp     rcx, r15
0x14011e030  jz      loc_14011E223
0x14011e036  test    byte ptr [rcx+1Ch], 1
0x14011e03a  jz      loc_14011E223
0x14011e040  cmp     byte ptr [rcx+19h], 2
0x14011e044  jb      loc_14011E223
0x14011e04a  mov     rcx, [rcx+10h]
0x14011e04e  lea     r8, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids
0x14011e055  mov     edx, 1Fh
0x14011e05a  mov     [rsp+68h+dwCreationDisposition], ebx
0x14011e05e  mov     r9, rsi
0x14011e061  call    WPP_SF_Sd
0x14011e066  jmp     loc_14011E223
0x14011e06b  mov     ecx, 4000h; cb
0x14011e070  call    cs:__imp_CoTaskMemAlloc
0x14011e076  mov     r15, rax
0x14011e079  test    rax, rax
0x14011e07c  jnz     short loc_14011E088
0x14011e07e  mov     ebx, 8007000Eh
0x14011e083  jmp     loc_14011E204
0x14011e088  mov     dword ptr [rax], 0A0000003h
0x14011e08e  lea     rcx, [r15+10h]; void *
0x14011e092  add     bx, bx
0x14011e095  mov     rdx, r14; Src
0x14011e098  movzx   ebx, bx
0x14011e09b  mov     r8d, ebx; Size
0x14011e09e  mov     [r15+0Ah], bx
0x14011e0a3  lea     eax, [rbx+0Ch]
0x14011e0a6  mov     [r15+4], ax
0x14011e0ab  xor     eax, eax
0x14011e0ad  mov     [r15+6], eax
0x14011e0b1  lea     eax, [rbx+2]
0x14011e0b4  mov     [r15+0Ch], ax
0x14011e0b9  xor     eax, eax
0x14011e0bb  mov     [r15+0Eh], ax
0x14011e0c0  call    memcpy_0
0x14011e0c5  xor     ecx, ecx
0x14011e0c7  mov     word ptr [r15+12h], 3Fh ; '?'
0x14011e0ce  mov     [rsp+68h+lpOverlapped], rcx; lpOverlapped
0x14011e0d3  lea     rax, [rbp+BytesReturned]
0x14011e0d7  mov     [rsp+68h+hTemplateFile], rax; lpBytesReturned
0x14011e0dc  mov     r8, r15; lpInBuffer
0x14011e0df  mov     [rsp+68h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x14011e0e3  mov     edx, 900A4h; dwIoControlCode
0x14011e0e8  mov     qword ptr [rsp+68h+dwCreationDisposition], rcx; lpOutBuffer
0x14011e0ed  shr     rbx, 1
0x14011e0f0  mov     [r15+rbx*2+10h], ecx
0x14011e0f5  movzx   r9d, word ptr [r15+4]
0x14011e0fa  mov     rcx, [rbp+Src]; hDevice
0x14011e0fe  add     r9d, 8; nInBufferSize
0x14011e102  call    cs:__imp_DeviceIoControl
0x14011e108  test    eax, eax
0x14011e10a  jnz     short loc_14011E169
0x14011e10c  call    cs:__imp_GetLastError
0x14011e112  mov     ebx, eax
0x14011e114  test    eax, eax
0x14011e116  jle     short loc_14011E121
0x14011e118  movzx   ebx, ax
0x14011e11b  or      ebx, 80070000h
0x14011e121  mov     rcx, cs:WPP_GLOBAL_Control
0x14011e128  lea     rax, WPP_GLOBAL_Control
0x14011e12f  cmp     rcx, rax
0x14011e132  jz      loc_14011E1FB
0x14011e138  test    byte ptr [rcx+1Ch], 1
0x14011e13c  jz      loc_14011E1FB
0x14011e142  cmp     byte ptr [rcx+19h], 2
0x14011e146  jb      loc_14011E1FB
0x14011e14c  mov     rcx, [rcx+10h]
0x14011e150  lea     r8, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids
0x14011e157  mov     edx, 21h ; '!'
0x14011e15c  mov     r9d, ebx
0x14011e15f  call    WPP_SF_d
0x14011e164  jmp     loc_14011E1FB
0x14011e169  mov     ebx, 208h
0x14011e16e  mov     ecx, ebx; cb
0x14011e170  call    cs:__imp_CoTaskMemAlloc
0x14011e176  mov     rdi, rax
0x14011e179  test    rax, rax
0x14011e17c  jnz     short loc_14011E185
0x14011e17e  mov     ebx, 8007000Eh
0x14011e183  jmp     short loc_14011E1FB
0x14011e185  mov     r8, rbx; Size
0x14011e188  xor     edx, edx; Val
0x14011e18a  mov     rcx, rdi; void *
0x14011e18d  call    memset_0
0x14011e192  mov     r11d, 104h
0x14011e198  lea     r8, netname; "WsbMountedVolumes"
0x14011e19f  mov     edx, r11d; unsigned __int64
0x14011e1a2  mov     rcx, rdi; unsigned __int16 *
0x14011e1a5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14011e1aa  mov     ebx, eax
0x14011e1ac  test    eax, eax
0x14011e1ae  js      short loc_14011E1FB
0x14011e1b0  lea     r8, asc_14013C090; "\\"
0x14011e1b7  mov     edx, r11d; unsigned __int64
0x14011e1ba  mov     rcx, rdi; unsigned __int16 *
0x14011e1bd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14011e1c2  mov     ebx, eax
0x14011e1c4  test    eax, eax
0x14011e1c6  js      short loc_14011E1FB
0x14011e1c8  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x14011e1cc  lea     r8, [rbp+pv]; unsigned __int16 **
0x14011e1d0  mov     rcx, r12; unsigned __int16 *
0x14011e1d3  call    ?BlbGetReparseDirectoryNameForMountedVolume@@YAJPEAG0PEAPEAG@Z; BlbGetReparseDirectoryNameForMountedVolume(ushort *,ushort *,ushort * *)
0x14011e1d8  mov     ebx, eax
0x14011e1da  test    eax, eax
0x14011e1dc  js      short loc_14011E1FB
0x14011e1de  mov     r8, [rbp+pv]; unsigned __int16 *
0x14011e1e2  mov     edx, 104h; unsigned __int64
0x14011e1e7  mov     rcx, rdi; unsigned __int16 *
0x14011e1ea  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14011e1ef  mov     ebx, eax
0x14011e1f1  test    eax, eax
0x14011e1f3  js      short loc_14011E1FB
0x14011e1f5  mov     [r13+0], rdi
0x14011e1f9  xor     edi, edi
0x14011e1fb  mov     rcx, r15; pv
0x14011e1fe  call    cs:__imp_CoTaskMemFree
0x14011e204  mov     rcx, [rbp+Src]; hObject
0x14011e208  call    cs:__imp_CloseHandle
0x14011e20e  test    rdi, rdi
0x14011e211  jz      short loc_14011E21C
0x14011e213  mov     rcx, rdi; pv
0x14011e216  call    cs:__imp_CoTaskMemFree
0x14011e21c  lea     r15, WPP_GLOBAL_Control
0x14011e223  test    r14, r14
0x14011e226  jz      short loc_14011E231
0x14011e228  mov     rcx, r14; pv
0x14011e22b  call    cs:__imp_CoTaskMemFree
0x14011e231  test    rsi, rsi
0x14011e234  jz      short loc_14011E23F
0x14011e236  mov     rcx, rsi; pv
0x14011e239  call    cs:__imp_CoTaskMemFree
0x14011e23f  mov     rcx, [rbp+pv]; pv
0x14011e243  test    rcx, rcx
0x14011e246  jz      short loc_14011E24E
0x14011e248  call    cs:__imp_CoTaskMemFree
0x14011e24e  test    ebx, ebx
0x14011e250  jns     short loc_14011E286
0x14011e252  mov     rcx, cs:WPP_GLOBAL_Control
0x14011e259  cmp     rcx, r15
0x14011e25c  jz      short loc_14011E286
0x14011e25e  test    byte ptr [rcx+1Ch], 1
0x14011e262  jz      short loc_14011E286
0x14011e264  cmp     byte ptr [rcx+19h], 2
0x14011e268  jb      short loc_14011E286
0x14011e26a  mov     rcx, [rcx+10h]
0x14011e26e  lea     r8, WPP_94c6ea76801837b238af0538cad4a1a5_Traceguids
0x14011e275  mov     edx, 22h ; '"'
0x14011e27a  mov     [rsp+68h+dwCreationDisposition], ebx
0x14011e27e  mov     r9, r12
0x14011e281  call    WPP_SF_Sd
0x14011e286  mov     eax, ebx
0x14011e288  add     rsp, 68h
0x14011e28c  pop     r15
0x14011e28e  pop     r14
0x14011e290  pop     r13
0x14011e292  pop     r12
0x14011e294  pop     rdi
0x14011e295  pop     rsi
0x14011e296  pop     rbx
0x14011e297  pop     rbp
0x14011e298  retn
```
