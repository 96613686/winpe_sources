# WldpCanExecuteFileFromDetachedSignature

- ea: `0x18002ecc0`
- end: `0x18002f2e6`
- name: `WldpCanExecuteFileFromDetachedSignature`
- size: `1574`
- prototype: `__int64 __usercall@<rax>(void *Buf1@<rcx>, __int64, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callees

- `0x180016f74`
- `0x18001d9b4`
- `0x1800201f4`
- `0x1800213bc`
- `0x180021ec0`
- `0x1800282b0`
- `0x18002d4e8`
- `0x18002d870`
- `0x18002e1a0`
- `0x18002e210`
- `0x18002e4d4`
- `0x18002ecc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ee44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002eed3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002ef9d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002ef9d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002ee3a`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002eec9`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002effc`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002f01e`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002f0d8`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002f0fa`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002f1ed`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002f20f`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002ee3a`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002eec9`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002effc`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002f01e`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002f0d8`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002f0fa`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002f1ed`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18002f20f`

## string_xrefs

- `0x18002f176`: `onecore\base\ngscb\wldp\dll\canexecute.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WldpCanExecuteFileFromDetachedSignature(
        _QWORD *Buf1,
        unsigned int a2,
        void *a3,
        void *a4,
        __int64 a5,
        _DWORD *a6)
{
  const char *v7; // r9
  unsigned int v8; // ebx
  __int64 result; // rax
  signed int LastError; // eax
  unsigned int v11; // ebx
  signed int v12; // eax
  unsigned int v13; // ebx
  int v14; // edx
  int IsFileWithDetachedSignatureTrusted; // r14d
  int v16; // ebx
  char v17; // al
  unsigned int v18; // ebx
  int v19; // [rsp+20h] [rbp-138h]
  int v20; // [rsp+30h] [rbp-128h] BYREF
  unsigned int v21; // [rsp+34h] [rbp-124h] BYREF
  __int64 v22; // [rsp+38h] [rbp-120h] BYREF
  _DWORD **v23; // [rsp+40h] [rbp-118h]
  _DWORD *v24; // [rsp+48h] [rbp-110h]
  _DWORD *v25; // [rsp+50h] [rbp-108h]
  char v26; // [rsp+58h] [rbp-100h]
  unsigned int v27; // [rsp+60h] [rbp-F8h] BYREF
  _DWORD *v28; // [rsp+68h] [rbp-F0h] BYREF
  HANDLE v29; // [rsp+70h] [rbp-E8h] BYREF
  HANDLE hFile; // [rsp+78h] [rbp-E0h] BYREF
  LARGE_INTEGER liDistanceToMove; // [rsp+80h] [rbp-D8h]
  union _LARGE_INTEGER NewFilePointer; // [rsp+88h] [rbp-D0h] BYREF
  union _LARGE_INTEGER v33; // [rsp+90h] [rbp-C8h] BYREF
  __int64 v34; // [rsp+98h] [rbp-C0h] BYREF
  HANDLE *v35; // [rsp+A0h] [rbp-B8h] BYREF
  LARGE_INTEGER *v36; // [rsp+A8h] [rbp-B0h]
  HANDLE *v37; // [rsp+B0h] [rbp-A8h]
  LARGE_INTEGER *v38; // [rsp+B8h] [rbp-A0h]
  char v39; // [rsp+C0h] [rbp-98h]
  _QWORD v40[4]; // [rsp+D0h] [rbp-88h] BYREF
  _QWORD v41[4]; // [rsp+F0h] [rbp-68h] BYREF
  GUID ActivityId; // [rsp+110h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v27 = a2;
  hFile = a3;
  v29 = a4;
  v28 = a6;
  try
  {
    v21 = 0;
    v20 = 0;
    ActivityId = 0;
    liDistanceToMove.QuadPart = 0;
    NewFilePointer.QuadPart = 0;
    v33.QuadPart = 0;
    v34 = 0;
    v40[0] = Buf1;
    v40[1] = &v28;
    v40[2] = &v27;
    v40[3] = &v20;
    wil::ScopeExit__lambda_e91d72e47c575060e9e5d062f7455a10___(&v22, v40);
    if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL
      && (char *)v29 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL
      && IsKnownHost(Buf1) )
    {
      GetSystemStateForHost(Buf1, &v34);
      if ( (v34 & 4) == 0 )
      {
        *v28 = 1;
        v8 = v20;
        if ( v26 )
        {
          v26 = 0;
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::GetImpl'::`2'::impl) )
            EmitTelemetry(v22, 0, 3, **v23, *v24, *v25);
        }
        return v8;
      }
      if ( !SetFilePointerEx(hFile, liDistanceToMove, &NewFilePointer, 1u) )
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        v20 = v11;
        if ( v26 )
        {
          v26 = 0;
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::GetImpl'::`2'::impl) )
            EmitTelemetry(v22, 0, 3, **v23, *v24, *v25);
        }
        return v11;
      }
      if ( !SetFilePointerEx(v29, liDistanceToMove, &v33, 1u) )
      {
        v12 = GetLastError();
        v13 = v12;
        if ( v12 > 0 )
          v13 = (unsigned __int16)v12 | 0x80070000;
        v20 = v13;
        if ( v26 )
        {
          v26 = 0;
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::GetImpl'::`2'::impl) )
            EmitTelemetry(v22, 0, 3, **v23, *v24, *v25);
        }
        return v13;
      }
      v41[0] = &hFile;
      v41[1] = &NewFilePointer;
      v41[2] = &v29;
      v41[3] = &v33;
      wil::ScopeExit__lambda_90e66dca0f80c570f86a999a69da7912___(&v35, v41);
      EventActivityIdControl(3u, &ActivityId);
      IsFileWithDetachedSignatureTrusted = WldpIsFileWithDetachedSignatureTrusted(hFile, v29, &ActivityId, &v21);
      v20 = IsFileWithDetachedSignatureTrusted;
      if ( IsFileWithDetachedSignatureTrusted < 0 )
      {
        if ( v39 )
        {
          v39 = 0;
          SetFilePointerEx(*v35, *v36, 0, 0);
          SetFilePointerEx(*v37, *v38, 0, 0);
        }
        if ( v26 )
        {
          v26 = 0;
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::GetImpl'::`2'::impl) )
            EmitTelemetry(v22, 0, 3, **v23, *v24, *v25);
        }
        return (unsigned int)IsFileWithDetachedSignatureTrusted;
      }
      if ( v21 == 1 )
        goto LABEL_41;
      if ( v21 != 3 )
      {
        v16 = WldpRemapExecutionPolicy(Buf1, v14, v28);
        v20 = v16;
        if ( v16 < 0 )
        {
          if ( v39 )
          {
            v39 = 0;
            SetFilePointerEx(*v35, *v36, 0, 0);
            SetFilePointerEx(*v37, *v38, 0, 0);
          }
          if ( v26 )
          {
            v26 = 0;
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::GetImpl'::`2'::impl) )
              EmitTelemetry(v22, 0, 3, **v23, *v24, *v25);
          }
          return (unsigned int)v16;
        }
        goto LABEL_45;
      }
      v17 = 1;
      if ( (v34 & 8) != 0 )
LABEL_41:
        v17 = 0;
      if ( v17 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x34B,
          (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\canexecute.cpp",
          (const char *)0x8000FFFFLL,
          v19);
      *v28 = 1;
LABEL_45:
      WldpLogCanExecute(Buf1, v27, a5, 3, *v28, &ActivityId);
      v18 = v20;
      if ( v39 )
      {
        v39 = 0;
        SetFilePointerEx(*v35, *v36, 0, 0);
        SetFilePointerEx(*v37, *v38, 0, 0);
      }
      if ( v26 )
      {
        v26 = 0;
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::GetImpl'::`2'::impl) )
          EmitTelemetry(v22, 0, 3, **v23, *v24, *v25);
      }
      return v18;
    }
    v20 = -2147024809;
    if ( v26 )
    {
      v26 = 0;
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::GetImpl'::`2'::impl) )
        EmitTelemetry(v22, 0, 3, **v23, *v24, *v25);
    }
    result = 2147942487LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x35F,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\canexecute.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18002ecc0  mov     r11, rsp
0x18002ecc3  push    rbx
0x18002ecc4  push    rsi
0x18002ecc5  push    r12
0x18002ecc7  push    r14
0x18002ecc9  push    r15
0x18002eccb  sub     rsp, 130h
0x18002ecd2  mov     rax, cs:__security_cookie
0x18002ecd9  xor     rax, rsp
0x18002ecdc  mov     [rsp+158h+var_38], rax
0x18002ece4  mov     rsi, rcx
0x18002ece7  mov     [rsp+158h+var_F8], edx
0x18002eceb  mov     [rsp+158h+hFile], r8
0x18002ecf0  mov     [rsp+158h+var_E8], r9
0x18002ecf5  mov     r15, [rsp+158h+arg_20]
0x18002ecfd  mov     rax, [rsp+158h+arg_28]
0x18002ed05  mov     [rsp+158h+var_F0], rax
0x18002ed0a  xor     r12d, r12d
0x18002ed0d  mov     [rsp+158h+var_124], r12d
0x18002ed12  mov     [rsp+158h+var_128], r12d
0x18002ed17  xorps   xmm0, xmm0
0x18002ed1a  movups  xmmword ptr [r11-48h], xmm0
0x18002ed1f  mov     [r11-0D8h], r12
0x18002ed26  mov     [r11-0D0h], r12
0x18002ed2d  mov     [r11-0C8h], r12
0x18002ed34  mov     [r11-0C0h], r12
0x18002ed3b  mov     [r11-88h], rcx
0x18002ed42  lea     rax, [rsp+158h+var_F0]
0x18002ed47  mov     [r11-80h], rax
0x18002ed4b  lea     rax, [rsp+158h+var_F8]
0x18002ed50  mov     [r11-78h], rax
0x18002ed54  lea     rax, [rsp+158h+var_128]
0x18002ed59  mov     [r11-70h], rax
0x18002ed5d  lea     rdx, [r11-88h]
0x18002ed64  lea     rcx, [rsp+158h+var_120]
0x18002ed69  call    wil__ScopeExit__lambda_e91d72e47c575060e9e5d062f7455a10___
0x18002ed6e  nop
0x18002ed6f  mov     rax, [rsp+158h+hFile]
0x18002ed74  dec     rax
0x18002ed77  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ed7b  ja      loc_18002F267
0x18002ed81  mov     rax, [rsp+158h+var_E8]
0x18002ed86  dec     rax
0x18002ed89  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ed8d  ja      loc_18002F267
0x18002ed93  mov     rcx, rsi; Buf1
0x18002ed96  call    IsKnownHost
0x18002ed9b  test    al, al
0x18002ed9d  jz      loc_18002F267
0x18002eda3  lea     rdx, [rsp+158h+var_C0]
0x18002edab  mov     rcx, rsi; Buf1
0x18002edae  call    GetSystemStateForHost
0x18002edb3  lea     ebx, [r12+1]
0x18002edb8  test    byte ptr [rsp+158h+var_C0], 4
0x18002edc0  jnz     short loc_18002EE22
0x18002edc2  mov     rax, [rsp+158h+var_F0]
0x18002edc7  mov     [rax], ebx
0x18002edc9  mov     ebx, [rsp+158h+var_128]
0x18002edcd  cmp     [rsp+158h+var_100], r12b
0x18002edd2  jz      short loc_18002EE1B
0x18002edd4  mov     [rsp+158h+var_100], r12b
0x18002edd9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::GetImpl(void)'::`2'::impl
0x18002ede0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::__private_IsEnabled(void)
0x18002ede5  test    al, al
0x18002ede7  jnz     short loc_18002EE1B
0x18002ede9  mov     rax, [rsp+158h+var_118]
0x18002edee  mov     r9, [rax]
0x18002edf1  mov     rcx, [rsp+158h+var_108]
0x18002edf6  mov     edx, [rcx]
0x18002edf8  mov     dword ptr [rsp+158h+var_130], edx
0x18002edfc  mov     rcx, [rsp+158h+var_110]
0x18002ee01  mov     edx, [rcx]
0x18002ee03  mov     [rsp+158h+var_138], edx
0x18002ee07  mov     r9d, [r9]
0x18002ee0a  xor     edx, edx
0x18002ee0c  lea     r8d, [r12+3]
0x18002ee11  mov     rcx, [rsp+158h+var_120]
0x18002ee16  call    EmitTelemetry
0x18002ee1b  mov     eax, ebx
0x18002ee1d  jmp     loc_18002F2C5
0x18002ee22  mov     r9d, ebx; dwMoveMethod
0x18002ee25  lea     r8, [rsp+158h+NewFilePointer]; lpNewFilePointer
0x18002ee2d  mov     rdx, qword ptr [rsp+158h+liDistanceToMove]; liDistanceToMove
0x18002ee35  mov     rcx, [rsp+158h+hFile]; hFile
0x18002ee3a  call    cs:__imp_SetFilePointerEx
0x18002ee40  test    eax, eax
0x18002ee42  jnz     short loc_18002EEB1
0x18002ee44  call    cs:__imp_GetLastError
0x18002ee4a  mov     ebx, eax
0x18002ee4c  test    eax, eax
0x18002ee4e  jle     short loc_18002EE59
0x18002ee50  movzx   ebx, ax
0x18002ee53  or      ebx, 80070000h
0x18002ee59  mov     [rsp+158h+var_128], ebx
0x18002ee5d  cmp     [rsp+158h+var_100], r12b
0x18002ee62  jz      short loc_18002EEAA
0x18002ee64  mov     [rsp+158h+var_100], r12b
0x18002ee69  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::GetImpl(void)'::`2'::impl
0x18002ee70  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::__private_IsEnabled(void)
0x18002ee75  test    al, al
0x18002ee77  jnz     short loc_18002EEAA
0x18002ee79  mov     rax, [rsp+158h+var_118]
0x18002ee7e  mov     r9, [rax]
0x18002ee81  mov     rcx, [rsp+158h+var_108]
0x18002ee86  mov     edx, [rcx]
0x18002ee88  mov     dword ptr [rsp+158h+var_130], edx
0x18002ee8c  mov     rcx, [rsp+158h+var_110]
0x18002ee91  mov     edx, [rcx]
0x18002ee93  mov     [rsp+158h+var_138], edx
0x18002ee97  mov     r9d, [r9]
0x18002ee9a  xor     edx, edx
0x18002ee9c  lea     r8d, [rdx+3]
0x18002eea0  mov     rcx, [rsp+158h+var_120]
0x18002eea5  call    EmitTelemetry
0x18002eeaa  mov     eax, ebx
0x18002eeac  jmp     loc_18002F2C5
0x18002eeb1  mov     r9d, ebx; dwMoveMethod
0x18002eeb4  lea     r8, [rsp+158h+var_C8]; lpNewFilePointer
0x18002eebc  mov     rdx, qword ptr [rsp+158h+liDistanceToMove]; liDistanceToMove
0x18002eec4  mov     rcx, [rsp+158h+var_E8]; hFile
0x18002eec9  call    cs:__imp_SetFilePointerEx
0x18002eecf  test    eax, eax
0x18002eed1  jnz     short loc_18002EF40
0x18002eed3  call    cs:__imp_GetLastError
0x18002eed9  mov     ebx, eax
0x18002eedb  test    eax, eax
0x18002eedd  jle     short loc_18002EEE8
0x18002eedf  movzx   ebx, ax
0x18002eee2  or      ebx, 80070000h
0x18002eee8  mov     [rsp+158h+var_128], ebx
0x18002eeec  cmp     [rsp+158h+var_100], r12b
0x18002eef1  jz      short loc_18002EF39
0x18002eef3  mov     [rsp+158h+var_100], r12b
0x18002eef8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::GetImpl(void)'::`2'::impl
0x18002eeff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::__private_IsEnabled(void)
0x18002ef04  test    al, al
0x18002ef06  jnz     short loc_18002EF39
0x18002ef08  mov     rax, [rsp+158h+var_118]
0x18002ef0d  mov     r9, [rax]
0x18002ef10  mov     rcx, [rsp+158h+var_108]
0x18002ef15  mov     edx, [rcx]
0x18002ef17  mov     dword ptr [rsp+158h+var_130], edx
0x18002ef1b  mov     rcx, [rsp+158h+var_110]
0x18002ef20  mov     edx, [rcx]
0x18002ef22  mov     [rsp+158h+var_138], edx
0x18002ef26  mov     r9d, [r9]
0x18002ef29  xor     edx, edx
0x18002ef2b  lea     r8d, [rdx+3]
0x18002ef2f  mov     rcx, [rsp+158h+var_120]
0x18002ef34  call    EmitTelemetry
0x18002ef39  mov     eax, ebx
0x18002ef3b  jmp     loc_18002F2C5
0x18002ef40  lea     rax, [rsp+158h+hFile]
0x18002ef45  mov     [rsp+158h+var_68], rax
0x18002ef4d  lea     rax, [rsp+158h+NewFilePointer]
0x18002ef55  mov     [rsp+158h+var_60], rax
0x18002ef5d  lea     rax, [rsp+158h+var_E8]
0x18002ef62  mov     [rsp+158h+var_58], rax
0x18002ef6a  lea     rax, [rsp+158h+var_C8]
0x18002ef72  mov     [rsp+158h+var_50], rax
0x18002ef7a  lea     rdx, [rsp+158h+var_68]
0x18002ef82  lea     rcx, [rsp+158h+var_B8]
0x18002ef8a  call    wil__ScopeExit__lambda_90e66dca0f80c570f86a999a69da7912___
0x18002ef8f  nop
0x18002ef90  lea     rdx, [rsp+158h+ActivityId]; ActivityId
0x18002ef98  mov     ecx, 3; ControlCode
0x18002ef9d  call    cs:__imp_EventActivityIdControl
0x18002efa3  lea     r9, [rsp+158h+var_124]; unsigned int *
0x18002efa8  lea     r8, [rsp+158h+ActivityId]; struct _GUID *
0x18002efb0  mov     rdx, [rsp+158h+var_E8]; void *
0x18002efb5  mov     rcx, [rsp+158h+hFile]; void *
0x18002efba  call    ?WldpIsFileWithDetachedSignatureTrusted@@YAJPEAX0AEBU_GUID@@PEAK@Z; WldpIsFileWithDetachedSignatureTrusted(void *,void *,_GUID const &,ulong *)
0x18002efbf  mov     r14d, eax
0x18002efc2  mov     [rsp+158h+var_128], eax
0x18002efc6  test    eax, eax
0x18002efc8  jns     loc_18002F07A
0x18002efce  cmp     [rsp+158h+var_98], r12b
0x18002efd6  jz      short loc_18002F025
0x18002efd8  mov     [rsp+158h+var_98], r12b
0x18002efe0  xor     r9d, r9d; dwMoveMethod
0x18002efe3  xor     r8d, r8d; lpNewFilePointer
0x18002efe6  mov     rdx, [rsp+158h+var_B0]
0x18002efee  mov     rdx, [rdx]; liDistanceToMove
0x18002eff1  mov     rcx, [rsp+158h+var_B8]
0x18002eff9  mov     rcx, [rcx]; hFile
0x18002effc  call    cs:__imp_SetFilePointerEx
0x18002f002  xor     r9d, r9d; dwMoveMethod
0x18002f005  xor     r8d, r8d; lpNewFilePointer
0x18002f008  mov     rdx, [rsp+158h+var_A0]
0x18002f010  mov     rdx, [rdx]; liDistanceToMove
0x18002f013  mov     rcx, [rsp+158h+var_A8]
0x18002f01b  mov     rcx, [rcx]; hFile
0x18002f01e  call    cs:__imp_SetFilePointerEx
0x18002f024  nop
0x18002f025  cmp     [rsp+158h+var_100], r12b
0x18002f02a  jz      short loc_18002F072
0x18002f02c  mov     [rsp+158h+var_100], r12b
0x18002f031  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::GetImpl(void)'::`2'::impl
0x18002f038  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::__private_IsEnabled(void)
0x18002f03d  test    al, al
0x18002f03f  jnz     short loc_18002F072
0x18002f041  mov     rax, [rsp+158h+var_118]
0x18002f046  mov     r9, [rax]
0x18002f049  mov     rax, [rsp+158h+var_108]
0x18002f04e  mov     ecx, [rax]
0x18002f050  mov     dword ptr [rsp+158h+var_130], ecx
0x18002f054  mov     rax, [rsp+158h+var_110]
0x18002f059  mov     ecx, [rax]
0x18002f05b  mov     [rsp+158h+var_138], ecx
0x18002f05f  mov     r9d, [r9]
0x18002f062  xor     edx, edx
0x18002f064  lea     r8d, [rdx+3]
0x18002f068  mov     rcx, [rsp+158h+var_120]
0x18002f06d  call    EmitTelemetry
0x18002f072  mov     eax, r14d
0x18002f075  jmp     loc_18002F2C5
0x18002f07a  cmp     [rsp+158h+var_124], ebx
0x18002f07e  jz      loc_18002F161
0x18002f084  cmp     [rsp+158h+var_124], 3
0x18002f089  jz      loc_18002F155
0x18002f08f  mov     r8, [rsp+158h+var_F0]
0x18002f094  mov     rcx, rsi
0x18002f097  call    WldpRemapExecutionPolicy
0x18002f09c  mov     ebx, eax
0x18002f09e  mov     [rsp+158h+var_128], eax
0x18002f0a2  test    eax, eax
0x18002f0a4  jns     loc_18002F18E
0x18002f0aa  cmp     [rsp+158h+var_98], r12b
0x18002f0b2  jz      short loc_18002F101
0x18002f0b4  mov     [rsp+158h+var_98], r12b
0x18002f0bc  xor     r9d, r9d; dwMoveMethod
0x18002f0bf  xor     r8d, r8d; lpNewFilePointer
0x18002f0c2  mov     rdx, [rsp+158h+var_B0]
0x18002f0ca  mov     rdx, [rdx]; liDistanceToMove
0x18002f0cd  mov     rcx, [rsp+158h+var_B8]
0x18002f0d5  mov     rcx, [rcx]; hFile
0x18002f0d8  call    cs:__imp_SetFilePointerEx
0x18002f0de  xor     r9d, r9d; dwMoveMethod
0x18002f0e1  xor     r8d, r8d; lpNewFilePointer
0x18002f0e4  mov     rdx, [rsp+158h+var_A0]
0x18002f0ec  mov     rdx, [rdx]; liDistanceToMove
0x18002f0ef  mov     rcx, [rsp+158h+var_A8]
0x18002f0f7  mov     rcx, [rcx]; hFile
0x18002f0fa  call    cs:__imp_SetFilePointerEx
0x18002f100  nop
0x18002f101  cmp     [rsp+158h+var_100], r12b
0x18002f106  jz      short loc_18002F14E
0x18002f108  mov     [rsp+158h+var_100], r12b
0x18002f10d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::GetImpl(void)'::`2'::impl
0x18002f114  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ScriptPerformance_Slowdown>::__private_IsEnabled(void)
0x18002f119  test    al, al
0x18002f11b  jnz     short loc_18002F14E
0x18002f11d  mov     rax, [rsp+158h+var_118]
0x18002f122  mov     r9, [rax]
0x18002f125  mov     rax, [rsp+158h+var_108]
0x18002f12a  mov     ecx, [rax]
0x18002f12c  mov     dword ptr [rsp+158h+var_130], ecx
0x18002f130  mov     rax, [rsp+158h+var_110]
0x18002f135  mov     ecx, [rax]
0x18002f137  mov     [rsp+158h+var_138], ecx
0x18002f13b  mov     r9d, [r9]
0x18002f13e  xor     edx, edx
0x18002f140  lea     r8d, [rdx+3]
0x18002f144  mov     rcx, [rsp+158h+var_120]
0x18002f149  call    EmitTelemetry
0x18002f14e  mov     eax, ebx
0x18002f150  jmp     loc_18002F2C5
0x18002f155  test    byte ptr [rsp+158h+var_C0], 8
0x18002f15d  mov     al, bl
0x18002f15f  jz      short loc_18002F164
0x18002f161  mov     al, r12b
0x18002f164  mov     rcx, [rsp+158h]; this
0x18002f16c  test    al, al
0x18002f16e  jz      short loc_18002F187
0x18002f170  mov     r9d, 8000FFFFh; char *
0x18002f176  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\wldp\\dll\\canexe"...
0x18002f17d  mov     edx, 34Bh; void *
0x18002f182  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f187  mov     rax, [rsp+158h+var_F0]
0x18002f18c  mov     [rax], ebx
0x18002f18e  lea     rax, [rsp+158h+ActivityId]
0x18002f196  mov     [rsp+158h+var_130], rax
0x18002f19b  mov     rax, [rsp+158h+var_F0]
0x18002f1a0  mov     edx, [rax]
0x18002f1a2  mov     [rsp+158h+var_138], edx
0x18002f1a6  mov     r9d, 3
0x18002f1ac  mov     r8, r15
0x18002f1af  mov     edx, [rsp+158h+var_F8]
0x18002f1b3  mov     rcx, rsi
0x18002f1b6  call    ?WldpLogCanExecute@@YAXAEBU_GUID@@W4WLDP_EXECUTION_EVALUATION_OPTIONS@@PEBGW4_WLDP_SUBJECT_TYPE@@W4WLDP_EXECUTION_POLICY@@0@Z; WldpLogCanExecute(_GUID const &,WLDP_EXECUTION_EVALUATION_OPTIONS,ushort const *,_WLDP_SUBJECT_TYPE,WLDP_EXECUTION_POLICY,_GUID const &)
0x18002f1bb  mov     ebx, [rsp+158h+var_128]
0x18002f1bf  cmp     [rsp+158h+var_98], r12b
0x18002f1c7  jz      short loc_18002F216
0x18002f1c9  mov     [rsp+158h+var_98], r12b
0x18002f1d1  xor     r9d, r9d; dwMoveMethod
0x18002f1d4  xor     r8d, r8d; lpNewFilePointer
0x18002f1d7  mov     rdx, [rsp+158h+var_B0]
0x18002f1df  mov     rdx, [rdx]; liDistanceToMove
0x18002f1e2  mov     rcx, [rsp+158h+var_B8]
0x18002f1ea  mov     rcx, [rcx]; hFile
  ... truncated ...
```
