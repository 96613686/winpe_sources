# DBSession::SetContext(void)

- ea: `0x18000fcb0`
- end: `0x180010020`
- name: `?SetContext@DBSession@@UEAAJXZ`
- size: `880`
- prototype: `__int64 __fastcall(DBSession *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800068f0`
- `0x18000fcb0`
- `0x180045990`
- `0x180067c1c`
- `0x18006f180`
- `0x18007d4e4`
- `0x18007d540`
- `0x18007d59c`
- `0x1800c50f0`

## import_xrefs

- `ESENT!JetGetErrorInfoW` at `0x18000fd71`
- `ESENT!JetGetErrorInfoW` at `0x18000fd71`
- `ESENT!JetSetSessionContext` at `0x18000fcee`
- `ESENT!JetSetSessionContext` at `0x18000fcee`

## string_xrefs

- `0x18000ff6f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000ffa5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000fe42`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x18001000b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x18000febb`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`
- `0x18000fecf`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`
- `0x18000ff08`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`
- `0x18000ffc6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`

## pseudocode

```c
__int64 __fastcall DBSession::SetContext(DBSession *this)
{
  JET_ERR v1; // eax
  __int64 v2; // rcx
  int v3; // ebx
  __int64 v4; // r8
  unsigned int v6; // edi
  int v7; // eax
  int v8; // [rsp+30h] [rbp-69h] BYREF
  JET_ERR v9; // [rsp+38h] [rbp-61h] BYREF
  int v10; // [rsp+40h] [rbp-59h] BYREF
  __int128 v11; // [rsp+44h] [rbp-55h]
  __int128 v12; // [rsp+54h] [rbp-45h]
  __int128 v13; // [rsp+64h] [rbp-35h]
  __int128 v14; // [rsp+74h] [rbp-25h]
  __int128 v15; // [rsp+84h] [rbp-15h]
  __int128 v16; // [rsp+94h] [rbp-5h]
  __int128 v17; // [rsp+A4h] [rbp+Bh]
  __int128 v18; // [rsp+B4h] [rbp+1Bh]
  __int128 v19; // [rsp+C4h] [rbp+2Bh]
  int v20; // [rsp+D4h] [rbp+3Bh]

  if ( *((_QWORD *)this + 27) == -1 )
  {
    Log_UnistoreHREvent_0(
      2147549183LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      231);
    return 2147549183LL;
  }
  v1 = JetSetSessionContext(*((_QWORD *)this + 27), *((unsigned int *)this + 57));
  v3 = v1;
  if ( g_fInProc && !dword_18010D924 )
  {
    if ( v1 != -1414 )
    {
      v9 = v1;
      if ( v1 >= 0 )
        return 0;
      v10 = 152;
      v20 = 0;
      v11 = 0;
      v12 = 0;
      v13 = 0;
      v14 = 0;
      v15 = 0;
      v16 = 0;
      v17 = 0;
      v18 = 0;
      v19 = 0;
      if ( (int)JetGetErrorInfoW(&v9, &v10, 152, 1, 0) < 0 )
        goto LABEL_7;
      v2 = (unsigned int)(DWORD1(v11) - 10);
      if ( DWORD1(v11) != 10 )
      {
        v2 = (unsigned int)(DWORD1(v11) - 11);
        if ( DWORD1(v11) == 11 )
        {
          v8 = v9;
          UnistoreTelemetry::JetInconsistentError<unsigned long>(&v8);
        }
        else if ( DWORD1(v11) == 12 )
        {
          v8 = v9;
          UnistoreTelemetry::JetFragmentationError<unsigned long>(&v8);
        }
LABEL_7:
        if ( g_breakOnJetError && g_breakOnJetError == v3 )
          Log_AssertionEvent(
            v2,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
            25);
        if ( v3 == -1811 )
        {
          v6 = -2147024894;
        }
        else
        {
          if ( v3 == -1601 || v3 == -1603 || v3 == -1017 )
          {
            v6 = -2147024871;
            goto LABEL_33;
          }
          if ( v3 == -1605 || v3 == -1525 )
          {
            v6 = -2147024713;
            goto LABEL_33;
          }
          if ( v3 != -346 )
          {
            if ( v3 == -529 || v3 == -1808 || v3 == -510 )
            {
              v6 = -2147024784;
              goto LABEL_33;
            }
            if ( v3 == -1054 )
            {
              Log_AssertionEvent(
                v2,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
                59);
            }
            else if ( v3 == -1102 )
            {
              Log_AssertionEvent(
                v2,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
                62);
            }
            else
            {
              if ( v3 == -1069 )
              {
                v4 = 65;
              }
              else
              {
                if ( v3 != -1086 )
                  goto LABEL_32;
                v4 = 71;
              }
              Log_AssertionEvent(
                v2,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
                v4);
              __int2c();
            }
LABEL_32:
            v6 = -v3 | 0x80C80000;
LABEL_33:
            if ( v3 == -1912 || v6 == -1912 )
              return v6;
            goto LABEL_52;
          }
          v6 = -2147024872;
        }
LABEL_52:
        Log_UnistoreHREvent_0(
          v6,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
          234);
        return v6;
      }
      if ( v9 == -1414 )
        goto LABEL_7;
    }
    v7 = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"CorruptReason", v3);
    if ( v7 >= 0 )
    {
      v8 = v3;
      UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&v8);
      if ( (unsigned int)IsJetCorruptionError(v3) )
      {
        Log_AssertionEvent(
          v2,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          109);
        __int2c();
      }
    }
    else
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v7,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        102);
    }
  }
  if ( v3 < 0 )
    goto LABEL_7;
  return 0;
}

```

## disassembly

```asm
0x18000fcb0  push    rbp
0x18000fcb2  lea     rbp, [rsp-57h]
0x18000fcb7  sub     rsp, 0F0h
0x18000fcbe  mov     rax, cs:__security_cookie
0x18000fcc5  xor     rax, rsp
0x18000fcc8  mov     [rbp+57h+var_10], rax
0x18000fccc  mov     rax, [rcx+0D8h]
0x18000fcd3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fcd7  jz      loc_18000FE3C
0x18000fcdd  mov     edx, [rcx+0E4h]; ulContext
0x18000fce3  mov     rcx, rax; sesid
0x18000fce6  mov     [rsp+0F0h+arg_8], rbx
0x18000fcee  call    cs:__imp_JetSetSessionContext
0x18000fcf4  cmp     cs:?g_fInProc@@3HA, 0; int g_fInProc
0x18000fcfb  mov     ebx, eax
0x18000fcfd  jz      loc_18000FE5C
0x18000fd03  cmp     cs:dword_18010D924, 0
0x18000fd0a  jnz     loc_18000FE5C
0x18000fd10  cmp     eax, 0FFFFFA7Ah
0x18000fd15  jz      loc_18000FF48
0x18000fd1b  mov     [rbp+57h+var_B8], eax
0x18000fd1e  test    eax, eax
0x18000fd20  jns     loc_18000FE64
0x18000fd26  xorps   xmm0, xmm0
0x18000fd29  mov     [rbp+57h+var_B0], 98h
0x18000fd30  xor     eax, eax
0x18000fd32  lea     rdx, [rbp+57h+var_B0]
0x18000fd36  mov     r9d, 1
0x18000fd3c  mov     [rbp+57h+var_1C], eax
0x18000fd3f  mov     r8d, 98h
0x18000fd45  mov     [rsp+0F0h+var_D0], eax
0x18000fd49  lea     rcx, [rbp+57h+var_B8]
0x18000fd4d  movups  [rbp+57h+var_AC], xmm0
0x18000fd51  movups  [rbp+57h+var_9C], xmm0
0x18000fd55  movups  [rbp+57h+var_8C], xmm0
0x18000fd59  movups  [rbp+57h+var_7C], xmm0
0x18000fd5d  movups  [rbp+57h+var_6C], xmm0
0x18000fd61  movups  [rbp+57h+var_5C], xmm0
0x18000fd65  movups  [rbp+57h+var_4C], xmm0
0x18000fd69  movups  [rbp+57h+var_3C], xmm0
0x18000fd6d  movups  [rbp+57h+var_2C], xmm0
0x18000fd71  call    cs:__imp_JetGetErrorInfoW
0x18000fd77  test    eax, eax
0x18000fd79  jns     loc_18000FE83
0x18000fd7f  mov     eax, cs:?g_breakOnJetError@@3JA; long g_breakOnJetError
0x18000fd85  mov     [rsp+0F0h+arg_10], rdi
0x18000fd8d  test    eax, eax
0x18000fd8f  jnz     loc_18000FFB8
0x18000fd95  cmp     ebx, 0FFFFF8EDh
0x18000fd9b  jz      loc_18000FFD7
0x18000fda1  cmp     ebx, 0FFFFF9BFh
0x18000fda7  jz      loc_18000FF20
0x18000fdad  cmp     ebx, 0FFFFF9BDh
0x18000fdb3  jz      loc_18000FF20
0x18000fdb9  cmp     ebx, 0FFFFFC07h
0x18000fdbf  jz      loc_18000FF20
0x18000fdc5  cmp     ebx, 0FFFFF9BBh
0x18000fdcb  jz      loc_18000FFEF
0x18000fdd1  cmp     ebx, 0FFFFFA0Bh
0x18000fdd7  jz      loc_18000FFEF
0x18000fddd  cmp     ebx, 0FFFFFEA6h
0x18000fde3  jz      loc_18000FFDE
0x18000fde9  cmp     ebx, 0FFFFFDEFh
0x18000fdef  jz      loc_18000FFE5
0x18000fdf5  cmp     ebx, 0FFFFF8F0h
0x18000fdfb  jz      loc_18000FFE5
0x18000fe01  cmp     ebx, 0FFFFFE02h
0x18000fe07  jz      loc_18000FFE5
0x18000fe0d  cmp     ebx, 0FFFFFBE2h
0x18000fe13  jz      loc_18000FF02
0x18000fe19  cmp     ebx, 0FFFFFBB2h
0x18000fe1f  jz      loc_18000FEB5
0x18000fe25  cmp     ebx, 0FFFFFBD3h
0x18000fe2b  jnz     loc_18000FF16
0x18000fe31  mov     r8d, 41h ; 'A'
0x18000fe37  jmp     loc_18000FECF
0x18000fe3c  mov     r9d, 0E7h
0x18000fe42  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000fe49  xor     edx, edx
0x18000fe4b  mov     ecx, 8000FFFFh
0x18000fe50  call    Log_UnistoreHREvent_0
0x18000fe55  mov     eax, 8000FFFFh
0x18000fe5a  jmp     short loc_18000FE6E
0x18000fe5c  test    ebx, ebx
0x18000fe5e  js      loc_18000FD7F
0x18000fe64  xor     eax, eax
0x18000fe66  mov     rbx, [rsp+0F0h+arg_8]
0x18000fe6e  mov     rcx, [rbp+57h+var_10]
0x18000fe72  xor     rcx, rsp; StackCookie
0x18000fe75  call    __security_check_cookie
0x18000fe7a  add     rsp, 0F0h
0x18000fe81  pop     rbp
0x18000fe82  retn
0x18000fe83  mov     ecx, dword ptr [rbp+57h+var_AC+4]
0x18000fe86  sub     ecx, 0Ah
0x18000fe89  jz      loc_18000FF3B
0x18000fe8f  sub     ecx, 1
0x18000fe92  jz      loc_18000FF27
0x18000fe98  cmp     ecx, 1
0x18000fe9b  jnz     loc_18000FD7F
0x18000fea1  mov     eax, [rbp+57h+var_B8]
0x18000fea4  lea     rcx, [rbp+57h+var_C0]
0x18000fea8  mov     [rbp+57h+var_C0], eax
0x18000feab  call    ??$JetFragmentationError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetFragmentationError<ulong>(ulong &&)
0x18000feb0  jmp     loc_18000FD7F
0x18000feb5  mov     r8d, 3Eh ; '>'
0x18000febb  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000fec2  call    Log_AssertionEvent
0x18000fec7  jmp     short loc_18000FEDD
0x18000fec9  mov     r8d, 47h ; 'G'
0x18000fecf  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000fed6  call    Log_AssertionEvent
0x18000fedb  int     2Ch; Windows NT - assertion failure
0x18000fedd  mov     edi, ebx
0x18000fedf  neg     edi
0x18000fee1  or      edi, 80C80000h
0x18000fee7  cmp     ebx, 0FFFFF888h
0x18000feed  jnz     loc_18000FFF9
0x18000fef3  mov     eax, edi
0x18000fef5  mov     rdi, [rsp+0F0h+arg_10]
0x18000fefd  jmp     loc_18000FE66
0x18000ff02  mov     r8d, 3Bh ; ';'
0x18000ff08  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ff0f  call    Log_AssertionEvent
0x18000ff14  jmp     short loc_18000FEDD
0x18000ff16  cmp     ebx, 0FFFFFBC2h
0x18000ff1c  jnz     short loc_18000FEDD
0x18000ff1e  jmp     short loc_18000FEC9
0x18000ff20  mov     edi, 80070019h
0x18000ff25  jmp     short loc_18000FEE7
0x18000ff27  mov     eax, [rbp+57h+var_B8]
0x18000ff2a  lea     rcx, [rbp+57h+var_C0]
0x18000ff2e  mov     [rbp+57h+var_C0], eax
0x18000ff31  call    ??$JetInconsistentError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetInconsistentError<ulong>(ulong &&)
0x18000ff36  jmp     loc_18000FD7F
0x18000ff3b  cmp     [rbp+57h+var_B8], 0FFFFFA7Ah
0x18000ff42  jz      loc_18000FD7F
0x18000ff48  mov     r9d, ebx; unsigned int
0x18000ff4b  lea     r8, ?c_wszUnistoreRegistryCorruptAfterMount@@3QBGB; "CorruptReason"
0x18000ff52  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x18000ff59  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000ff60  call    ?RegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; RegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18000ff65  test    eax, eax
0x18000ff67  jns     short loc_18000FF84
0x18000ff69  mov     r9d, 66h ; 'f'
0x18000ff6f  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ff76  xor     edx, edx
0x18000ff78  mov     ecx, eax
0x18000ff7a  call    Log_UnistoreHREvent_0
0x18000ff7f  jmp     loc_18000FE5C
0x18000ff84  lea     rcx, [rbp+57h+var_C0]
0x18000ff88  mov     [rbp+57h+var_C0], ebx
0x18000ff8b  call    ??$MarkStoreCorruption@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::MarkStoreCorruption<ulong>(ulong &&)
0x18000ff90  mov     ecx, ebx; int
0x18000ff92  call    ?IsJetCorruptionError@@YAHJ@Z; IsJetCorruptionError(long)
0x18000ff97  test    eax, eax
0x18000ff99  jz      loc_18000FE5C
0x18000ff9f  mov     r8d, 6Dh ; 'm'
0x18000ffa5  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ffac  call    Log_AssertionEvent
0x18000ffb1  int     2Ch; Windows NT - assertion failure
0x18000ffb3  jmp     loc_18000FE5C
0x18000ffb8  cmp     eax, ebx
0x18000ffba  jnz     loc_18000FD95
0x18000ffc0  mov     r8d, 19h
0x18000ffc6  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ffcd  call    Log_AssertionEvent
0x18000ffd2  jmp     loc_18000FD95
0x18000ffd7  mov     edi, 80070002h
0x18000ffdc  jmp     short loc_180010005
0x18000ffde  mov     edi, 80070018h
0x18000ffe3  jmp     short loc_180010005
0x18000ffe5  mov     edi, 80070070h
0x18000ffea  jmp     loc_18000FEE7
0x18000ffef  mov     edi, 800700B7h
0x18000fff4  jmp     loc_18000FEE7
0x18000fff9  cmp     edi, 0FFFFF888h
0x18000ffff  jz      loc_18000FEF3
0x180010005  mov     r9d, 0EAh
0x18001000b  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180010012  xor     edx, edx
0x180010014  mov     ecx, edi
0x180010016  call    Log_UnistoreHREvent_0
0x18001001b  jmp     loc_18000FEF3
```
