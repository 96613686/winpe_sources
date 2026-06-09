# CallFavoriteDataManager::_SaveDataToFile(void)

- ea: `0x1800c5a90`
- end: `0x1800c5d59`
- name: `?_SaveDataToFile@CallFavoriteDataManager@@AEAAJXZ`
- size: `713`
- prototype: `__int64 __fastcall(CallFavoriteDataManager *__hidden this)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18004fbac`
- `0x1800c2164`
- `0x1800c2678`
- `0x1800c32d0`
- `0x1800c3624`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x180035040`
- `0x180035670`
- `0x1800c545c`
- `0x1800c5a90`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5d05`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800c5cfb`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800c5cfb`
- `XmlLite!CreateXmlWriter` at `0x1800c5b8e`
- `XmlLite!CreateXmlWriter` at `0x1800c5b8e`
- `UserDataTypeHelperUtil!CreateWrapFileNameStm` at `0x1800c5b1d`
- `UserDataTypeHelperUtil!CreateWrapFileNameStm` at `0x1800c5b1d`

## string_xrefs

- `0x1800c5aee`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c5b2f`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`
- `0x1800c5ba5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\callfavorite.cpp`

## pseudocode

```c
__int64 __fastcall CallFavoriteDataManager::_SaveDataToFile(LPCWSTR *this)
{
  __int64 v2; // r9
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v5; // r9
  HRESULT v6; // eax
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  signed int LastError; // eax
  LPCWSTR lpExistingFileName[4]; // [rsp+30h] [rbp-20h] BYREF
  void *ppvObject; // [rsp+70h] [rbp+20h] BYREF
  __int64 v14; // [rsp+78h] [rbp+28h] BYREF
  __int64 v15; // [rsp+80h] [rbp+30h]

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpExistingFileName);
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          lpExistingFileName,
                          this[2],
                          this[3] - this[2]) )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             lpExistingFileName,
                             L".tmp") )
    {
      v2 = 1125;
      goto LABEL_5;
    }
    v14 = 0;
    v4 = CreateWrapFileNameStm(lpExistingFileName[0], 1, 0, &v14);
    v3 = v4;
    if ( v4 < 0 )
    {
      v5 = 1128;
LABEL_8:
      Log_HREvent(
        (unsigned int)v4,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
        v5);
LABEL_9:
      ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v14);
      goto LABEL_37;
    }
    v15 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 48LL))(v14, 0);
    v3 = v4;
    if ( v4 < 0 )
    {
      v5 = 1131;
      goto LABEL_8;
    }
    ppvObject = 0;
    v6 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
    v3 = v6;
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v14);
      v3 = v6;
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvObject + 208LL))(ppvObject, 0);
        v3 = v6;
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
                 ppvObject,
                 0,
                 L"Data",
                 0);
          v3 = v6;
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD, const wchar_t *))(*(_QWORD *)ppvObject + 56LL))(
                   ppvObject,
                   0,
                   L"Version",
                   0,
                   L"1");
            v3 = v6;
            if ( v6 >= 0 )
            {
              v6 = CallFavoriteDataManager::_SaveData((CallFavoriteDataManager *)this, (struct IXmlWriter *)ppvObject);
              v3 = v6;
              if ( v6 >= 0 )
              {
                v6 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 136LL))(ppvObject);
                v3 = v6;
                if ( v6 >= 0 )
                {
                  v6 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 112LL))(ppvObject);
                  v3 = v6;
                  if ( v6 >= 0 )
                  {
                    v6 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject);
                    v3 = v6;
                    if ( v6 >= 0 )
                    {
                      if ( CopyFileW(lpExistingFileName[0], this[2], 0) )
                      {
                        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppvObject);
                        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v14);
                        v3 = 0;
                        goto LABEL_37;
                      }
                      LastError = GetLastError();
                      v3 = LastError;
                      if ( LastError > 0 )
                        v3 = (unsigned __int16)LastError | 0x80070000;
                      v7 = 1148;
                      v8 = 0;
                      v9 = v3;
                      goto LABEL_15;
                    }
                    v7 = 1146;
                  }
                  else
                  {
                    v7 = 1145;
                  }
                }
                else
                {
                  v7 = 1144;
                }
              }
              else
              {
                v7 = 1142;
              }
            }
            else
            {
              v7 = 1140;
            }
          }
          else
          {
            v7 = 1139;
          }
        }
        else
        {
          v7 = 1137;
        }
      }
      else
      {
        v7 = 1136;
      }
    }
    else
    {
      v7 = 1134;
    }
    v8 = 1;
    v9 = (unsigned int)v6;
LABEL_15:
    Log_HREvent(
      v9,
      v8,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
      v7);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&ppvObject);
    goto LABEL_9;
  }
  v2 = 1124;
LABEL_5:
  v3 = -2147024882;
  Log_HREvent(
    2147942414LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\callfavorite.cpp",
    v2);
LABEL_37:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpExistingFileName);
  return v3;
}

```

## disassembly

```asm
0x1800c5a90  mov     [rsp-18h+arg_18], rbx
0x1800c5a95  push    rbp
0x1800c5a96  push    rdi
0x1800c5a97  push    r14
0x1800c5a99  mov     rbp, rsp
0x1800c5a9c  sub     rsp, 50h
0x1800c5aa0  mov     rdi, rcx
0x1800c5aa3  lea     rcx, [rbp+lpExistingFileName]; void *
0x1800c5aa7  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800c5aac  mov     rdx, [rdi+10h]
0x1800c5ab0  lea     rcx, [rbp+lpExistingFileName]
0x1800c5ab4  mov     r8, [rdi+18h]
0x1800c5ab8  sub     r8, rdx
0x1800c5abb  sar     r8, 1
0x1800c5abe  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800c5ac3  test    al, al
0x1800c5ac5  jnz     short loc_1800C5ACF
0x1800c5ac7  mov     r9d, 464h
0x1800c5acd  jmp     short loc_1800C5AE9
0x1800c5acf  lea     rdx, aTmp; ".tmp"
0x1800c5ad6  lea     rcx, [rbp+lpExistingFileName]
0x1800c5ada  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800c5adf  test    al, al
0x1800c5ae1  jnz     short loc_1800C5B03
0x1800c5ae3  mov     r9d, 465h
0x1800c5ae9  mov     ebx, 8007000Eh
0x1800c5aee  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c5af5  mov     ecx, ebx
0x1800c5af7  xor     edx, edx
0x1800c5af9  call    Log_HREvent
0x1800c5afe  jmp     loc_1800C5D3D
0x1800c5b03  mov     rcx, [rbp+lpExistingFileName]
0x1800c5b07  lea     r9, [rbp+arg_8]
0x1800c5b0b  xor     r8d, r8d
0x1800c5b0e  mov     [rbp+arg_8], 0
0x1800c5b16  lea     r14d, [r8+1]
0x1800c5b1a  mov     edx, r14d
0x1800c5b1d  call    cs:__imp_CreateWrapFileNameStm
0x1800c5b23  mov     ebx, eax
0x1800c5b25  test    eax, eax
0x1800c5b27  jns     short loc_1800C5B4E
0x1800c5b29  mov     r9d, 468h
0x1800c5b2f  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c5b36  mov     edx, r14d
0x1800c5b39  mov     ecx, eax
0x1800c5b3b  call    Log_HREvent
0x1800c5b40  lea     rcx, [rbp+arg_8]
0x1800c5b44  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800c5b49  jmp     loc_1800C5D3D
0x1800c5b4e  mov     rcx, [rbp+arg_8]
0x1800c5b52  mov     [rbp+arg_10], 0
0x1800c5b5a  mov     rdx, [rbp+arg_10]
0x1800c5b5e  mov     rax, [rcx]
0x1800c5b61  mov     rax, [rax+30h]
0x1800c5b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5b6a  mov     ebx, eax
0x1800c5b6c  test    eax, eax
0x1800c5b6e  jns     short loc_1800C5B78
0x1800c5b70  mov     r9d, 46Bh
0x1800c5b76  jmp     short loc_1800C5B2F
0x1800c5b78  xor     r8d, r8d; pMalloc
0x1800c5b7b  mov     [rbp+ppvObject], 0
0x1800c5b83  lea     rdx, [rbp+ppvObject]; ppvObject
0x1800c5b87  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x1800c5b8e  call    cs:__imp_CreateXmlWriter
0x1800c5b94  mov     ebx, eax
0x1800c5b96  test    eax, eax
0x1800c5b98  jns     short loc_1800C5BBC
0x1800c5b9a  mov     r9d, 46Eh
0x1800c5ba0  mov     edx, r14d
0x1800c5ba3  mov     ecx, eax
0x1800c5ba5  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800c5bac  call    Log_HREvent
0x1800c5bb1  lea     rcx, [rbp+ppvObject]
0x1800c5bb5  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800c5bba  jmp     short loc_1800C5B40
0x1800c5bbc  mov     rcx, [rbp+ppvObject]
0x1800c5bc0  mov     rdx, [rbp+arg_8]
0x1800c5bc4  mov     rax, [rcx]
0x1800c5bc7  mov     rax, [rax+18h]
0x1800c5bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5bd0  mov     ebx, eax
0x1800c5bd2  test    eax, eax
0x1800c5bd4  jns     short loc_1800C5BDE
0x1800c5bd6  mov     r9d, 470h
0x1800c5bdc  jmp     short loc_1800C5BA0
0x1800c5bde  mov     rcx, [rbp+ppvObject]
0x1800c5be2  xor     edx, edx
0x1800c5be4  mov     rax, [rcx]
0x1800c5be7  mov     rax, [rax+0D0h]
0x1800c5bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5bf3  mov     ebx, eax
0x1800c5bf5  test    eax, eax
0x1800c5bf7  jns     short loc_1800C5C01
0x1800c5bf9  mov     r9d, 471h
0x1800c5bff  jmp     short loc_1800C5BA0
0x1800c5c01  mov     rcx, [rbp+ppvObject]
0x1800c5c05  lea     r8, aData; "Data"
0x1800c5c0c  xor     r9d, r9d
0x1800c5c0f  xor     edx, edx
0x1800c5c11  mov     rax, [rcx]
0x1800c5c14  mov     rax, [rax+0D8h]
0x1800c5c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5c20  mov     ebx, eax
0x1800c5c22  test    eax, eax
0x1800c5c24  jns     short loc_1800C5C31
0x1800c5c26  mov     r9d, 473h
0x1800c5c2c  jmp     loc_1800C5BA0
0x1800c5c31  mov     rcx, [rbp+ppvObject]
0x1800c5c35  lea     rdx, a1_0; "1"
0x1800c5c3c  mov     [rsp+50h+var_30], rdx
0x1800c5c41  lea     r8, aVersion; "Version"
0x1800c5c48  xor     r9d, r9d
0x1800c5c4b  xor     edx, edx
0x1800c5c4d  mov     rax, [rcx]
0x1800c5c50  mov     rax, [rax+38h]
0x1800c5c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5c59  mov     ebx, eax
0x1800c5c5b  test    eax, eax
0x1800c5c5d  jns     short loc_1800C5C6A
0x1800c5c5f  mov     r9d, 474h
0x1800c5c65  jmp     loc_1800C5BA0
0x1800c5c6a  mov     rdx, [rbp+ppvObject]; struct IXmlWriter *
0x1800c5c6e  mov     rcx, rdi; this
0x1800c5c71  call    ?_SaveData@CallFavoriteDataManager@@AEAAJPEAUIXmlWriter@@@Z; CallFavoriteDataManager::_SaveData(IXmlWriter *)
0x1800c5c76  mov     ebx, eax
0x1800c5c78  test    eax, eax
0x1800c5c7a  jns     short loc_1800C5C87
0x1800c5c7c  mov     r9d, 476h
0x1800c5c82  jmp     loc_1800C5BA0
0x1800c5c87  mov     rcx, [rbp+ppvObject]
0x1800c5c8b  mov     rax, [rcx]
0x1800c5c8e  mov     rax, [rax+88h]
0x1800c5c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5c9a  mov     ebx, eax
0x1800c5c9c  test    eax, eax
0x1800c5c9e  jns     short loc_1800C5CAB
0x1800c5ca0  mov     r9d, 478h
0x1800c5ca6  jmp     loc_1800C5BA0
0x1800c5cab  mov     rcx, [rbp+ppvObject]
0x1800c5caf  mov     rax, [rcx]
0x1800c5cb2  mov     rax, [rax+70h]
0x1800c5cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5cbb  mov     ebx, eax
0x1800c5cbd  test    eax, eax
0x1800c5cbf  jns     short loc_1800C5CCC
0x1800c5cc1  mov     r9d, 479h
0x1800c5cc7  jmp     loc_1800C5BA0
0x1800c5ccc  mov     rcx, [rbp+ppvObject]
0x1800c5cd0  mov     rax, [rcx]
0x1800c5cd3  mov     rax, [rax+0F8h]
0x1800c5cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5cdf  mov     ebx, eax
0x1800c5ce1  test    eax, eax
0x1800c5ce3  jns     short loc_1800C5CF0
0x1800c5ce5  mov     r9d, 47Ah
0x1800c5ceb  jmp     loc_1800C5BA0
0x1800c5cf0  mov     rdx, [rdi+10h]; lpNewFileName
0x1800c5cf4  xor     r8d, r8d; bFailIfExists
0x1800c5cf7  mov     rcx, [rbp+lpExistingFileName]; lpExistingFileName
0x1800c5cfb  call    cs:__imp_CopyFileW
0x1800c5d01  test    eax, eax
0x1800c5d03  jnz     short loc_1800C5D29
0x1800c5d05  call    cs:__imp_GetLastError
0x1800c5d0b  mov     ebx, eax
0x1800c5d0d  test    eax, eax
0x1800c5d0f  jle     short loc_1800C5D1A
0x1800c5d11  movzx   ebx, ax
0x1800c5d14  or      ebx, 80070000h
0x1800c5d1a  mov     r9d, 47Ch
0x1800c5d20  xor     edx, edx
0x1800c5d22  mov     ecx, ebx
0x1800c5d24  jmp     loc_1800C5BA5
0x1800c5d29  lea     rcx, [rbp+ppvObject]
0x1800c5d2d  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800c5d32  lea     rcx, [rbp+arg_8]
0x1800c5d36  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800c5d3b  xor     ebx, ebx
0x1800c5d3d  lea     rcx, [rbp+lpExistingFileName]; void *
0x1800c5d41  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800c5d46  mov     eax, ebx
0x1800c5d48  mov     rbx, [rsp+50h+arg_18]
0x1800c5d50  add     rsp, 50h
0x1800c5d54  pop     r14
0x1800c5d56  pop     rdi
0x1800c5d57  pop     rbp
0x1800c5d58  retn
```
