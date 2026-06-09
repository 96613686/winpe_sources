# CSrDrvWuHelper::_GetDriverWUInfoFromCache(ushort const *,_GUID,_DRVWUHELPER_ONDISK_DRIVER_INFO *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)

- ea: `0x18000c468`
- end: `0x18000c6d8`
- name: `?_GetDriverWUInfoFromCache@CSrDrvWuHelper@@CAJPEBGU_GUID@@PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@PEAU_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@Z`
- size: `624`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _GUID *__struct_ptr, struct _DRVWUHELPER_ONDISK_DRIVER_INFO *, struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ab80`
- `0x18000af70`

## callees

- `0x180003360`
- `0x180003550`
- `0x180003740`
- `0x180003854`
- `0x180003ce0`
- `0x18000c468`
- `0x18000d348`
- `0x18000d43c`
- `0x180014f38`
- `0x180015590`
- `0x180015760`

## string_xrefs

- `0x18000c4c0`: `CSrDrvWuHelper::_GetDriverWUInfoFromCache`
- `0x18000c585`: `System Volume Information\SPP\SppGroupCache`

## pseudocode

```c
__int64 __fastcall CSrDrvWuHelper::_GetDriverWUInfoFromCache(
        const unsigned __int16 *a1,
        struct _GUID *a2,
        struct _DRVWUHELPER_ONDISK_DRIVER_INFO *a3,
        struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *a4)
{
  __int16 v8; // ax
  int DataFromCache; // ebx
  const unsigned __int16 *v10; // r9
  __int64 v11; // r8
  unsigned __int16 v12; // r9
  __int64 v13; // rdi
  __int64 v14; // rcx
  struct _DRVWUHELPER_ONDISK_DRIVER_INFO *v15; // rax
  struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned __int16 *v20; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h]
  int v22; // [rsp+70h] [rbp-90h] BYREF
  __int16 v23; // [rsp+74h] [rbp-8Ch]
  __int16 v24; // [rsp+76h] [rbp-8Ah]
  __int128 v25; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v26[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v27[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v28[2]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v29[8]; // [rsp+F0h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v22, "CSrDrvWuHelper::_GetDriverWUInfoFromCache", 333);
  v28[1] = 0;
  v28[0] = qword_18001A620;
  v29[0] = qword_18001A620;
  v26[0] = qword_18001A620;
  v27[0] = qword_18001A620;
  v20 = (unsigned __int16 *)qword_18001A620;
  v29[1] = 0;
  v26[1] = 0;
  v27[1] = 0;
  v21 = 0;
  v8 = 338;
  if ( (a3 == 0) == (a4 == 0) )
  {
    DataFromCache = -2147024809;
    v22 = -2147024809;
    goto LABEL_6;
  }
  v22 = 0;
  v23 = 338;
  DataFromCache = CBsString::Append((CBsString *)&v20, a1);
  v22 = DataFromCache;
  v8 = 340;
  if ( DataFromCache < 0 )
    goto LABEL_6;
  v23 = 340;
  if ( !(_DWORD)v21 )
  {
    DataFromCache = -2147020579;
    v22 = -2147020579;
LABEL_11:
    v8 = 341;
    goto LABEL_6;
  }
  v22 = CBsString::_CombinePathImpl((CBsString *)&v20, L"System Volume Information\\SPP\\SppGroupCache", 0, v10);
  DataFromCache = v22;
  if ( v22 < 0 )
    goto LABEL_11;
  v13 = 16;
  v23 = 341;
  if ( a3 )
  {
    v14 = 16;
    v15 = a3;
    do
    {
      *(_BYTE *)v15 = 0;
      v15 = (struct _DRVWUHELPER_ONDISK_DRIVER_INFO *)((char *)v15 + 1);
      --v14;
    }
    while ( v14 );
    DataFromCache = CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::Initialize(
                      (CBsString *)v28,
                      v20,
                      v11,
                      v12);
    v22 = DataFromCache;
    v8 = 346;
    if ( DataFromCache < 0 )
      goto LABEL_6;
    v25 = (__int128)*a2;
    v23 = 346;
    DataFromCache = CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&long Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&long Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::GetDataFromCache(
                      v28,
                      &v25,
                      a3);
    v22 = DataFromCache;
    v8 = 347;
    if ( DataFromCache < 0 )
      goto LABEL_6;
    v23 = 347;
  }
  if ( !a4 )
    goto LABEL_24;
  v16 = a4;
  do
  {
    *(_BYTE *)v16 = 0;
    v16 = (struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)((char *)v16 + 1);
    --v13;
  }
  while ( v13 );
  DataFromCache = CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::Initialize(
                    (CBsString *)v26,
                    v20);
  v22 = DataFromCache;
  v8 = 353;
  if ( DataFromCache >= 0 )
  {
    v25 = (__int128)*a2;
    v23 = 353;
    DataFromCache = CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&long Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&long Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::GetDataFromCache(
                      v26,
                      &v25,
                      a4);
    v22 = DataFromCache;
    v8 = 354;
    if ( DataFromCache >= 0 )
    {
      v23 = 354;
      goto LABEL_24;
    }
  }
LABEL_6:
  v24 = v8;
LABEL_24:
  CBsString::_Release((CBsString *)&v20);
  CBsString::_Release((CBsString *)v27);
  CBsString::_Release((CBsString *)v26);
  CBsString::_Release((CBsString *)v29);
  CBsString::_Release((CBsString *)v28);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v22, v17, v18);
  return (unsigned int)DataFromCache;
}

```

## disassembly

```asm
0x18000c468  push    rbp
0x18000c46a  push    rbx
0x18000c46b  push    rsi
0x18000c46c  push    rdi
0x18000c46d  push    r14
0x18000c46f  push    r15
0x18000c471  lea     rbp, [rsp-8]
0x18000c476  sub     rsp, 108h
0x18000c47d  mov     r14, r9
0x18000c480  mov     rsi, r8
0x18000c483  mov     r15, rdx
0x18000c486  mov     rbx, rcx
0x18000c489  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c490  lea     rax, WPP_GLOBAL_Control
0x18000c497  cmp     rcx, rax
0x18000c49a  jz      short loc_18000C4BA
0x18000c49c  test    dword ptr [rcx+1Ch], 20000000h
0x18000c4a3  jz      short loc_18000C4BA
0x18000c4a5  mov     rcx, [rcx+10h]
0x18000c4a9  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000c4b0  mov     edx, 12h
0x18000c4b5  call    WPP_SF_
0x18000c4ba  mov     r8d, 14Dh; unsigned __int16
0x18000c4c0  lea     rdx, aCsrdrvwuhelper_9; "CSrDrvWuHelper::_GetDriverWUInfoFromCac"...
0x18000c4c7  lea     rcx, [rsp+130h+var_C0]; this
0x18000c4cc  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000c4d1  lea     rax, qword_18001A620
0x18000c4d8  mov     [rbp+30h+var_48], 0
0x18000c4e0  xor     ecx, ecx
0x18000c4e2  mov     [rbp+30h+var_50], rax
0x18000c4e6  test    rsi, rsi
0x18000c4e9  mov     [rbp+30h+var_40], rax
0x18000c4ed  mov     [rbp+30h+var_70], rax
0x18000c4f1  setz    cl
0x18000c4f4  mov     [rbp+30h+var_60], rax
0x18000c4f8  mov     [rsp+130h+var_D0], rax
0x18000c4fd  xor     eax, eax
0x18000c4ff  test    r14, r14
0x18000c502  mov     [rbp+30h+var_38], 0
0x18000c50a  mov     [rbp+30h+var_68], 0
0x18000c512  setz    al
0x18000c515  mov     [rbp+30h+var_58], 0
0x18000c51d  cmp     ecx, eax
0x18000c51f  mov     [rsp+130h+var_C8], 0
0x18000c528  mov     eax, 152h
0x18000c52d  jnz     short loc_18000C542
0x18000c52f  mov     ebx, 80070057h
0x18000c534  mov     [rsp+130h+var_C0], ebx
0x18000c538  mov     [rsp+130h+var_BA], ax
0x18000c53d  jmp     loc_18000C68E
0x18000c542  mov     [rsp+130h+var_C0], 0
0x18000c54a  mov     [rsp+130h+var_BC], ax
0x18000c54f  mov     rdx, rbx; unsigned __int16 *
0x18000c552  lea     rcx, [rsp+130h+var_D0]; this
0x18000c557  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000c55c  mov     ebx, eax
0x18000c55e  mov     [rsp+130h+var_C0], eax
0x18000c562  test    eax, eax
0x18000c564  mov     eax, 154h
0x18000c569  js      short loc_18000C538
0x18000c56b  cmp     dword ptr [rsp+130h+var_C8], 0
0x18000c570  mov     [rsp+130h+var_BC], ax
0x18000c575  jnz     short loc_18000C582
0x18000c577  mov     ebx, 800710DDh
0x18000c57c  mov     [rsp+130h+var_C0], ebx
0x18000c580  jmp     short loc_18000C5A0
0x18000c582  xor     r8d, r8d; unsigned __int16 *
0x18000c585  lea     rdx, aSystemVolumeIn_0; "System Volume Information\\SPP\\SppGrou"...
0x18000c58c  lea     rcx, [rsp+130h+var_D0]; this
0x18000c591  call    ?_CombinePathImpl@CBsString@@AEAAJPEBG000000000@Z; CBsString::_CombinePathImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000c596  mov     [rsp+130h+var_C0], eax
0x18000c59a  mov     ebx, eax
0x18000c59c  test    eax, eax
0x18000c59e  jns     short loc_18000C5A7
0x18000c5a0  mov     eax, 155h
0x18000c5a5  jmp     short loc_18000C538
0x18000c5a7  mov     eax, 155h
0x18000c5ac  mov     edi, 10h
0x18000c5b1  mov     [rsp+130h+var_BC], ax
0x18000c5b6  test    rsi, rsi
0x18000c5b9  jz      short loc_18000C623
0x18000c5bb  mov     ecx, edi
0x18000c5bd  mov     rax, rsi
0x18000c5c0  mov     byte ptr [rax], 0
0x18000c5c3  inc     rax
0x18000c5c6  sub     rcx, 1
0x18000c5ca  jnz     short loc_18000C5C0
0x18000c5cc  mov     rdx, [rsp+130h+var_D0]; unsigned __int16 *
0x18000c5d1  lea     rcx, [rbp+30h+var_50]; this
0x18000c5d5  call    ?Initialize@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@QEAAJPEBG0@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::Initialize(ushort const *,ushort const *)
0x18000c5da  mov     ebx, eax
0x18000c5dc  mov     [rsp+130h+var_C0], eax
0x18000c5e0  test    eax, eax
0x18000c5e2  mov     eax, 15Ah
0x18000c5e7  js      loc_18000C538
0x18000c5ed  movaps  xmm0, xmmword ptr [r15]
0x18000c5f1  lea     rdx, [rbp+30h+var_80]
0x18000c5f5  mov     r8, rsi
0x18000c5f8  movdqa  [rbp+30h+var_80], xmm0
0x18000c5fd  lea     rcx, [rbp+30h+var_50]
0x18000c601  mov     [rsp+130h+var_BC], ax
0x18000c606  call    ?GetDataFromCache@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_DRIVER_INFO@@$1?Write_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_DRIVER_INFO@@YAJ01@Z@@QEAAJU_GUID@@PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_DRIVER_INFO,&Write_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *),&Read_DRVWUHELPER_ONDISK_DRIVER_INFO(void *,_DRVWUHELPER_ONDISK_DRIVER_INFO *)>::GetDataFromCache(_GUID,_DRVWUHELPER_ONDISK_DRIVER_INFO *)
0x18000c60b  mov     ebx, eax
0x18000c60d  mov     [rsp+130h+var_C0], eax
0x18000c611  test    eax, eax
0x18000c613  mov     eax, 15Bh
0x18000c618  js      loc_18000C538
0x18000c61e  mov     [rsp+130h+var_BC], ax
0x18000c623  test    r14, r14
0x18000c626  jz      short loc_18000C68E
0x18000c628  mov     rax, r14
0x18000c62b  mov     byte ptr [rax], 0
0x18000c62e  inc     rax
0x18000c631  sub     rdi, 1
0x18000c635  jnz     short loc_18000C62B
0x18000c637  mov     rdx, [rsp+130h+var_D0]; unsigned __int16 *
0x18000c63c  lea     rcx, [rbp+30h+var_70]; this
0x18000c640  call    ?Initialize@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@QEAAJPEBG0@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::Initialize(ushort const *,ushort const *)
0x18000c645  mov     ebx, eax
0x18000c647  mov     [rsp+130h+var_C0], eax
0x18000c64b  test    eax, eax
0x18000c64d  mov     eax, 161h
0x18000c652  js      loc_18000C538
0x18000c658  movaps  xmm0, xmmword ptr [r15]
0x18000c65c  lea     rdx, [rbp+30h+var_80]
0x18000c660  mov     r8, r14
0x18000c663  movdqa  [rbp+30h+var_80], xmm0
0x18000c668  lea     rcx, [rbp+30h+var_70]
0x18000c66c  mov     [rsp+130h+var_BC], ax
0x18000c671  call    ?GetDataFromCache@?$CSxOnDiskCache@U_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@$1?Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJPEAXPEAU1@@Z$1?Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@YAJ01@Z@@QEAAJU_GUID@@PEAU_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@Z; CSxOnDiskCache<_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO,&Write_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *),&Read_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO(void *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)>::GetDataFromCache(_GUID,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)
0x18000c676  mov     ebx, eax
0x18000c678  mov     [rsp+130h+var_C0], eax
0x18000c67c  test    eax, eax
0x18000c67e  mov     eax, 162h
0x18000c683  js      loc_18000C538
0x18000c689  mov     [rsp+130h+var_BC], ax
0x18000c68e  lea     rcx, [rsp+130h+var_D0]; this
0x18000c693  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000c698  lea     rcx, [rbp+30h+var_60]; this
0x18000c69c  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000c6a1  lea     rcx, [rbp+30h+var_70]; this
0x18000c6a5  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000c6aa  lea     rcx, [rbp+30h+var_40]; this
0x18000c6ae  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000c6b3  lea     rcx, [rbp+30h+var_50]; this
0x18000c6b7  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000c6bc  lea     rcx, [rsp+130h+var_C0]; this
0x18000c6c1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000c6c6  mov     eax, ebx
0x18000c6c8  add     rsp, 108h
0x18000c6cf  pop     r15
0x18000c6d1  pop     r14
0x18000c6d3  pop     rdi
0x18000c6d4  pop     rsi
0x18000c6d5  pop     rbx
0x18000c6d6  pop     rbp
0x18000c6d7  retn
```
