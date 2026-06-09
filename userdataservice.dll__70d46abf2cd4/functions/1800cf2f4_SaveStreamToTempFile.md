# _SaveStreamToTempFile

- ea: `0x1800cf2f4`
- end: `0x1800cf4c5`
- name: `_SaveStreamToTempFile`
- size: `465`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, const unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800cd644`
- `0x1800ce664`

## callees

- `0x180008ee8`
- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x180035c40`
- `0x1800cf2f4`
- `0x18012c76a`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `MessagingDataModel2!Messaging_GetMediaTempFolder` at `0x1800cf35b`
- `MessagingDataModel2!Messaging_GetMediaTempFolder` at `0x1800cf35b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf3b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf3b5`
- `UserDataTypeHelperUtil!CopyStream` at `0x1800cf437`
- `UserDataTypeHelperUtil!CopyStream` at `0x1800cf437`
- `UserDataTypeHelperUtil!CreateWrapFileNameStm` at `0x1800cf401`
- `UserDataTypeHelperUtil!CreateWrapFileNameStm` at `0x1800cf401`
- `UserDataPlatformHelperUtil!GetTempFileNameWithExt` at `0x1800cf3ab`
- `UserDataPlatformHelperUtil!GetTempFileNameWithExt` at `0x1800cf3ab`

## string_xrefs

- `0x1800cf333`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x1800cf3d4`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`
- `0x1800cf417`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatprop.cpp`

## pseudocode

```c
__int64 __fastcall SaveStreamToTempFile(const unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3, __int64 a4)
{
  unsigned int v8; // ebx
  int MediaTempFolder; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rcx
  const unsigned __int16 *v13; // r8
  signed int LastError; // eax
  int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v21[5]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v22[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( a2 )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v21);
    MediaTempFolder = Messaging_GetMediaTempFolder(v21);
    v8 = MediaTempFolder;
    if ( MediaTempFolder < 0 )
    {
      v10 = 970;
      v11 = 1;
      v12 = (unsigned int)MediaTempFolder;
LABEL_11:
      Log_HREvent(
        v12,
        v11,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
        v10);
LABEL_23:
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v21);
      return v8;
    }
    memset_0(v22, 0, 0x208u);
    v13 = L".dat";
    if ( a3 )
      v13 = a3;
    if ( !GetTempFileNameWithExt(v21[0], a1, v13, 0, v22) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v10 = 979;
      v11 = 0;
      v12 = v8;
      goto LABEL_11;
    }
    v20 = 0;
    v15 = CreateWrapFileNameStm(v22, 1, 0, &v20);
    v8 = v15;
    if ( v15 >= 0 )
    {
      v15 = CopyStream(a2, v20);
      v8 = v15;
      if ( v15 >= 0 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 64LL))(v20, 0);
        v8 = v15;
        if ( v15 >= 0 )
        {
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                  a4,
                                  v22) )
          {
            ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v20);
            v8 = 0;
            goto LABEL_23;
          }
          v8 = -2147024882;
          v16 = 988;
          v18 = 2147942414LL;
          v17 = 0;
          goto LABEL_15;
        }
        v16 = 986;
      }
      else
      {
        v16 = 984;
      }
    }
    else
    {
      v16 = 982;
    }
    v17 = 1;
    v18 = (unsigned int)v15;
LABEL_15:
    Log_HREvent(
      v18,
      v17,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
      v16);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v20);
    goto LABEL_23;
  }
  v8 = -2147024809;
  Log_HREvent(
    2147942487LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatprop.cpp",
    967);
  return v8;
}

```

## disassembly

```asm
0x1800cf2f4  push    rbp
0x1800cf2f6  push    rbx
0x1800cf2f7  push    rsi
0x1800cf2f8  push    rdi
0x1800cf2f9  push    r14
0x1800cf2fb  push    r15
0x1800cf2fd  lea     rbp, [rsp-188h]
0x1800cf305  sub     rsp, 288h
0x1800cf30c  mov     rax, cs:__security_cookie
0x1800cf313  xor     rax, rsp
0x1800cf316  mov     [rbp+1B0h+var_40], rax
0x1800cf31d  mov     r14, r9
0x1800cf320  mov     rdi, r8
0x1800cf323  mov     rsi, rdx
0x1800cf326  mov     r15, rcx
0x1800cf329  test    rdx, rdx
0x1800cf32c  jnz     short loc_1800CF34C
0x1800cf32e  mov     ebx, 80070057h
0x1800cf333  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800cf33a  mov     ecx, ebx
0x1800cf33c  mov     r9d, 3C7h
0x1800cf342  call    Log_HREvent
0x1800cf347  jmp     loc_1800CF4A4
0x1800cf34c  lea     rcx, [rsp+2B0h+var_278]; void *
0x1800cf351  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800cf356  lea     rcx, [rsp+2B0h+var_278]
0x1800cf35b  call    cs:__imp_Messaging_GetMediaTempFolder
0x1800cf361  mov     ebx, eax
0x1800cf363  test    eax, eax
0x1800cf365  jns     short loc_1800CF376
0x1800cf367  mov     r9d, 3CAh
0x1800cf36d  mov     edx, 1
0x1800cf372  mov     ecx, eax
0x1800cf374  jmp     short loc_1800CF3D4
0x1800cf376  xor     edx, edx; Val
0x1800cf378  lea     rcx, [rsp+2B0h+var_250]; void *
0x1800cf37d  mov     r8d, 208h; Size
0x1800cf383  call    memset_0
0x1800cf388  mov     rcx, [rsp+2B0h+var_278]
0x1800cf38d  lea     rax, [rsp+2B0h+var_250]
0x1800cf392  test    rdi, rdi
0x1800cf395  mov     [rsp+2B0h+var_290], rax
0x1800cf39a  lea     r8, aDat; ".dat"
0x1800cf3a1  mov     rdx, r15
0x1800cf3a4  cmovnz  r8, rdi
0x1800cf3a8  xor     r9d, r9d
0x1800cf3ab  call    cs:__imp_?GetTempFileNameWithExt@@YAIPEBG00IPEAG@Z; GetTempFileNameWithExt(ushort const *,ushort const *,ushort const *,uint,ushort *)
0x1800cf3b1  test    eax, eax
0x1800cf3b3  jnz     short loc_1800CF3E5
0x1800cf3b5  call    cs:__imp_GetLastError
0x1800cf3bb  mov     ebx, eax
0x1800cf3bd  test    eax, eax
0x1800cf3bf  jle     short loc_1800CF3CA
0x1800cf3c1  movzx   ebx, ax
0x1800cf3c4  or      ebx, 80070000h
0x1800cf3ca  mov     r9d, 3D3h
0x1800cf3d0  xor     edx, edx
0x1800cf3d2  mov     ecx, ebx
0x1800cf3d4  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800cf3db  call    Log_HREvent
0x1800cf3e0  jmp     loc_1800CF49A
0x1800cf3e5  xor     r8d, r8d
0x1800cf3e8  mov     [rsp+2B0h+var_280], 0
0x1800cf3f1  lea     r9, [rsp+2B0h+var_280]
0x1800cf3f6  lea     rcx, [rsp+2B0h+var_250]
0x1800cf3fb  lea     edi, [r8+1]
0x1800cf3ff  mov     edx, edi
0x1800cf401  call    cs:__imp_CreateWrapFileNameStm
0x1800cf407  mov     ebx, eax
0x1800cf409  test    eax, eax
0x1800cf40b  jns     short loc_1800CF42F
0x1800cf40d  mov     r9d, 3D6h
0x1800cf413  mov     edx, edi
0x1800cf415  mov     ecx, eax
0x1800cf417  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800cf41e  call    Log_HREvent
0x1800cf423  lea     rcx, [rsp+2B0h+var_280]
0x1800cf428  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800cf42d  jmp     short loc_1800CF49A
0x1800cf42f  mov     rdx, [rsp+2B0h+var_280]
0x1800cf434  mov     rcx, rsi
0x1800cf437  call    cs:__imp_CopyStream
0x1800cf43d  mov     ebx, eax
0x1800cf43f  test    eax, eax
0x1800cf441  jns     short loc_1800CF44B
0x1800cf443  mov     r9d, 3D8h
0x1800cf449  jmp     short loc_1800CF413
0x1800cf44b  mov     rcx, [rsp+2B0h+var_280]
0x1800cf450  xor     edx, edx
0x1800cf452  mov     rax, [rcx]
0x1800cf455  mov     rax, [rax+40h]
0x1800cf459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf45e  mov     ebx, eax
0x1800cf460  test    eax, eax
0x1800cf462  jns     short loc_1800CF46C
0x1800cf464  mov     r9d, 3DAh
0x1800cf46a  jmp     short loc_1800CF413
0x1800cf46c  lea     rdx, [rsp+2B0h+var_250]
0x1800cf471  mov     rcx, r14
0x1800cf474  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800cf479  test    al, al
0x1800cf47b  jnz     short loc_1800CF48E
0x1800cf47d  mov     ebx, 8007000Eh
0x1800cf482  mov     r9d, 3DCh
0x1800cf488  mov     ecx, ebx
0x1800cf48a  xor     edx, edx
0x1800cf48c  jmp     short loc_1800CF417
0x1800cf48e  lea     rcx, [rsp+2B0h+var_280]
0x1800cf493  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800cf498  xor     ebx, ebx
0x1800cf49a  lea     rcx, [rsp+2B0h+var_278]; void *
0x1800cf49f  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800cf4a4  mov     eax, ebx
0x1800cf4a6  mov     rcx, [rbp+1B0h+var_40]
0x1800cf4ad  xor     rcx, rsp; StackCookie
0x1800cf4b0  call    __security_check_cookie
0x1800cf4b5  add     rsp, 288h
0x1800cf4bc  pop     r15
0x1800cf4be  pop     r14
0x1800cf4c0  pop     rdi
0x1800cf4c1  pop     rsi
0x1800cf4c2  pop     rbx
0x1800cf4c3  pop     rbp
0x1800cf4c4  retn
```
