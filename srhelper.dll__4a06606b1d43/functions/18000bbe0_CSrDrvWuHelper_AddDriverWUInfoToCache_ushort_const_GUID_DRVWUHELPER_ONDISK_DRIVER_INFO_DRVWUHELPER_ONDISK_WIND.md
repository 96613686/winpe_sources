# CSrDrvWuHelper::_AddDriverWUInfoToCache(ushort const *,_GUID,_DRVWUHELPER_ONDISK_DRIVER_INFO *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)

- ea: `0x18000bbe0`
- end: `0x18000bdc7`
- name: `?_AddDriverWUInfoToCache@CSrDrvWuHelper@@CAJPEBGU_GUID@@PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@PEAU_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _GUID *__struct_ptr, struct _DRVWUHELPER_ONDISK_DRIVER_INFO *, struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18000a790`
- `0x18000ab80`
- `0x18000af70`

## callees

- `0x180002054`
- `0x1800022e4`
- `0x180003740`
- `0x180003854`
- `0x180003ce0`
- `0x18000bbe0`
- `0x18000bdd0`
- `0x18000d348`
- `0x18000d43c`
- `0x180015760`

## string_xrefs

- `0x18000bc36`: `CSrDrvWuHelper::_AddDriverWUInfoToCache`

## pseudocode

```c
__int64 __fastcall CSrDrvWuHelper::_AddDriverWUInfoToCache(
        const unsigned __int16 *a1,
        struct _GUID *a2,
        struct _DRVWUHELPER_ONDISK_DRIVER_INFO *a3,
        struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *a4)
{
  __int128 v4; // rdi
  int SppExternalMetadataDirectory; // ebx
  __int16 v8; // ax
  __int64 v9; // r8
  unsigned __int16 v10; // r9
  unsigned __int16 v11; // r9
  unsigned __int16 *v13[2]; // [rsp+20h] [rbp-69h] BYREF
  int v14; // [rsp+30h] [rbp-59h] BYREF
  __int16 v15; // [rsp+34h] [rbp-55h]
  __int16 v16; // [rsp+36h] [rbp-53h]
  __int128 v17; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v18[2]; // [rsp+80h] [rbp-9h] BYREF
  _QWORD v19[2]; // [rsp+90h] [rbp+7h] BYREF
  _QWORD v20[2]; // [rsp+A0h] [rbp+17h] BYREF
  _QWORD v21[6]; // [rsp+B0h] [rbp+27h] BYREF

  *((_QWORD *)&v4 + 1) = a4;
  *(_QWORD *)&v4 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v14,
    "CSrDrvWuHelper::_AddDriverWUInfoToCache",
    0x17Du,
    (unsigned __int16)a4);
  v20[1] = 0;
  v20[0] = qword_18001A620;
  v21[0] = qword_18001A620;
  v18[0] = qword_18001A620;
  v19[0] = qword_18001A620;
  v13[0] = (unsigned __int16 *)qword_18001A620;
  v21[1] = 0;
  v18[1] = 0;
  v19[1] = 0;
  v13[1] = 0;
  if ( v4 == 0 )
  {
    SppExternalMetadataDirectory = -2147024809;
    v8 = 386;
    v14 = -2147024809;
  }
  else
  {
    v14 = 0;
    v15 = 386;
    SppExternalMetadataDirectory = CSrDrvWuHelper::_CreateSppExternalMetadataDirectory(a1, (struct CBsString *)v13);
    v14 = SppExternalMetadataDirectory;
    v8 = 388;
    if ( SppExternalMetadataDirectory >= 0 )
    {
      v15 = 388;
      if ( (_QWORD)v4 )
      {
        SppExternalMetadataDirectory = CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::Initialize(
                                         (CBsString *)v20,
                                         v13[0],
                                         v9,
                                         v10);
        v14 = SppExternalMetadataDirectory;
        v8 = 392;
        if ( SppExternalMetadataDirectory < 0 )
          goto LABEL_6;
        v17 = (__int128)*a2;
        v15 = 392;
        SppExternalMetadataDirectory = CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::AddDataToCache(
                                         (__int64)v20,
                                         (__int64)&v17,
                                         v4,
                                         v11);
        v14 = SppExternalMetadataDirectory;
        v8 = 393;
        if ( SppExternalMetadataDirectory < 0 )
          goto LABEL_6;
        v15 = 393;
      }
      if ( !*((_QWORD *)&v4 + 1) )
        goto LABEL_16;
      SppExternalMetadataDirectory = CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::Initialize(
                                       (CBsString *)v18,
                                       v13[0]);
      v14 = SppExternalMetadataDirectory;
      v8 = 398;
      if ( SppExternalMetadataDirectory >= 0 )
      {
        v17 = (__int128)*a2;
        v15 = 398;
        SppExternalMetadataDirectory = CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::AddDataToCache(
                                         v18,
                                         &v17,
                                         *((_QWORD *)&v4 + 1));
        v14 = SppExternalMetadataDirectory;
        v8 = 399;
        if ( SppExternalMetadataDirectory >= 0 )
        {
          v15 = 399;
          goto LABEL_16;
        }
      }
    }
  }
LABEL_6:
  v16 = v8;
LABEL_16:
  CBsString::_Release((CBsString *)v13);
  CBsString::_Release((CBsString *)v19);
  CBsString::_Release((CBsString *)v18);
  CBsString::_Release((CBsString *)v21);
  CBsString::_Release((CBsString *)v20);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return (unsigned int)SppExternalMetadataDirectory;
}

```

## disassembly

```asm
0x18000bbe0  push    rbp
0x18000bbe2  push    rbx
0x18000bbe3  push    rsi
0x18000bbe4  push    rdi
0x18000bbe5  push    r14
0x18000bbe7  lea     rbp, [rsp-37h]
0x18000bbec  sub     rsp, 0C0h
0x18000bbf3  mov     rsi, r9
0x18000bbf6  mov     rdi, r8
0x18000bbf9  mov     r14, rdx
0x18000bbfc  mov     rbx, rcx
0x18000bbff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc06  lea     rax, WPP_GLOBAL_Control
0x18000bc0d  cmp     rcx, rax
0x18000bc10  jz      short loc_18000BC30
0x18000bc12  test    dword ptr [rcx+1Ch], 20000000h
0x18000bc19  jz      short loc_18000BC30
0x18000bc1b  mov     rcx, [rcx+10h]
0x18000bc1f  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000bc26  mov     edx, 13h
0x18000bc2b  call    WPP_SF_
0x18000bc30  mov     r8d, 17Dh; unsigned __int16
0x18000bc36  lea     rdx, aCsrdrvwuhelper_6; "CSrDrvWuHelper::_AddDriverWUInfoToCache"
0x18000bc3d  lea     rcx, [rbp+57h+var_B0]; this
0x18000bc41  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000bc46  mov     [rbp+57h+var_38], 0
0x18000bc4e  lea     rax, qword_18001A620
0x18000bc55  mov     [rbp+57h+var_40], rax
0x18000bc59  mov     [rbp+57h+var_30], rax
0x18000bc5d  mov     [rbp+57h+var_60], rax
0x18000bc61  mov     [rbp+57h+var_50], rax
0x18000bc65  mov     [rbp+57h+var_C0], rax
0x18000bc69  mov     [rbp+57h+var_28], 0
0x18000bc71  mov     [rbp+57h+var_58], 0
0x18000bc79  mov     [rbp+57h+var_48], 0
0x18000bc81  mov     [rbp+57h+var_B8], 0
0x18000bc89  test    rsi, rsi
0x18000bc8c  jnz     short loc_18000BCA9
0x18000bc8e  test    rdi, rdi
0x18000bc91  jnz     short loc_18000BCA9
0x18000bc93  mov     ebx, 80070057h
0x18000bc98  mov     eax, 182h
0x18000bc9d  mov     [rbp+57h+var_B0], ebx
0x18000bca0  mov     [rbp+57h+var_AA], ax
0x18000bca4  jmp     loc_18000BD81
0x18000bca9  mov     eax, 182h
0x18000bcae  mov     [rbp+57h+var_B0], 0
0x18000bcb5  lea     rdx, [rbp+57h+var_C0]; this
0x18000bcb9  mov     [rbp+57h+var_AC], ax
0x18000bcbd  mov     rcx, rbx; unsigned __int16 *
0x18000bcc0  call    ?_CreateSppExternalMetadataDirectory@CSrDrvWuHelper@@CAJPEBGPEAVCBsString@@@Z; CSrDrvWuHelper::_CreateSppExternalMetadataDirectory(ushort const *,CBsString *)
0x18000bcc5  mov     ebx, eax
0x18000bcc7  mov     [rbp+57h+var_B0], eax
0x18000bcca  test    eax, eax
0x18000bccc  mov     eax, 184h
0x18000bcd1  js      short loc_18000BCA0
0x18000bcd3  mov     [rbp+57h+var_AC], ax
0x18000bcd7  test    rdi, rdi
0x18000bcda  jz      short loc_18000BD2A
0x18000bcdc  mov     rdx, [rbp+57h+var_C0]; unsigned __int16 *
0x18000bce0  lea     rcx, [rbp+57h+var_40]; this
0x18000bce4  call    ?Initialize@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@QEAAJPEBG0@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::Initialize(ushort const *,ushort const *)
0x18000bce9  mov     ebx, eax
0x18000bceb  mov     [rbp+57h+var_B0], eax
0x18000bcee  test    eax, eax
0x18000bcf0  mov     eax, 188h
0x18000bcf5  js      short loc_18000BCA0
0x18000bcf7  movaps  xmm0, xmmword ptr [r14]
0x18000bcfb  lea     rdx, [rbp+57h+var_70]
0x18000bcff  mov     r8, rdi
0x18000bd02  movdqa  [rbp+57h+var_70], xmm0
0x18000bd07  lea     rcx, [rbp+57h+var_40]
0x18000bd0b  mov     [rbp+57h+var_AC], ax
0x18000bd0f  call    ?AddDataToCache@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@QEAAJU_GUID@@PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::AddDataToCache(_GUID,_DRVWUHELPER_ONDISK_DRIVER_INFO *)
0x18000bd14  mov     ebx, eax
0x18000bd16  mov     [rbp+57h+var_B0], eax
0x18000bd19  test    eax, eax
0x18000bd1b  mov     eax, 189h
0x18000bd20  js      loc_18000BCA0
0x18000bd26  mov     [rbp+57h+var_AC], ax
0x18000bd2a  test    rsi, rsi
0x18000bd2d  jz      short loc_18000BD81
0x18000bd2f  mov     rdx, [rbp+57h+var_C0]; unsigned __int16 *
0x18000bd33  lea     rcx, [rbp+57h+var_60]; this
0x18000bd37  call    ?Initialize@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@QEAAJPEBG0@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::Initialize(ushort const *,ushort const *)
0x18000bd3c  mov     ebx, eax
0x18000bd3e  mov     [rbp+57h+var_B0], eax
0x18000bd41  test    eax, eax
0x18000bd43  mov     eax, 18Eh
0x18000bd48  js      loc_18000BCA0
0x18000bd4e  movaps  xmm0, xmmword ptr [r14]
0x18000bd52  lea     rdx, [rbp+57h+var_70]
0x18000bd56  mov     r8, rsi
0x18000bd59  movdqa  [rbp+57h+var_70], xmm0
0x18000bd5e  lea     rcx, [rbp+57h+var_60]
0x18000bd62  mov     [rbp+57h+var_AC], ax
0x18000bd66  call    ?AddDataToCache@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@QEAAJU_GUID@@PEAU_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::AddDataToCache(_GUID,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)
0x18000bd6b  mov     ebx, eax
0x18000bd6d  mov     [rbp+57h+var_B0], eax
0x18000bd70  test    eax, eax
0x18000bd72  mov     eax, 18Fh
0x18000bd77  js      loc_18000BCA0
0x18000bd7d  mov     [rbp+57h+var_AC], ax
0x18000bd81  lea     rcx, [rbp+57h+var_C0]; this
0x18000bd85  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000bd8a  lea     rcx, [rbp+57h+var_50]; this
0x18000bd8e  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000bd93  lea     rcx, [rbp+57h+var_60]; this
0x18000bd97  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000bd9c  lea     rcx, [rbp+57h+var_30]; this
0x18000bda0  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000bda5  lea     rcx, [rbp+57h+var_40]; this
0x18000bda9  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000bdae  lea     rcx, [rbp+57h+var_B0]; this
0x18000bdb2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000bdb7  mov     eax, ebx
0x18000bdb9  add     rsp, 0C0h
0x18000bdc0  pop     r14
0x18000bdc2  pop     rdi
0x18000bdc3  pop     rsi
0x18000bdc4  pop     rbx
0x18000bdc5  pop     rbp
0x18000bdc6  retn
```
