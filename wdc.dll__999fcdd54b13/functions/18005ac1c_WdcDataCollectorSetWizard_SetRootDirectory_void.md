# WdcDataCollectorSetWizard::SetRootDirectory(void)

- ea: `0x18005ac1c`
- end: `0x18005adf4`
- name: `?SetRootDirectory@WdcDataCollectorSetWizard@@AEAAJXZ`
- size: `472`
- prototype: `__int64 __fastcall(WdcDataCollectorSetWizard *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18005a110`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18001cb20`
- `0x18005ac1c`
- `0x18005b4b4`
- `0x180068cd8`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005ac6d`
- `OLEAUT32!__imp_SysAllocString` at `0x18005adb1`
- `OLEAUT32!__imp_SysAllocString` at `0x18005ac6d`
- `OLEAUT32!__imp_SysAllocString` at `0x18005adb1`
- `OLEAUT32!__imp_SysFreeString` at `0x18005acf3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005acf3`

## string_xrefs

- `0x18005ac41`: `WdcDataCollectorSetWizard::SetRootDirectory`
- `0x18005acd8`: `WdcDataCollectorSetWizard::SetRootDirectory`
- `0x18005ad6b`: `WdcDataCollectorSetWizard::SetRootDirectory`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorSetWizard::SetRootDirectory(const unsigned __int16 **this)
{
  int v2; // eax
  const char *v3; // rdx
  __int64 v4; // rcx
  int v5; // r8d
  unsigned int v6; // ebx
  OLECHAR *v7; // rsi
  OLECHAR *v8; // rdi
  int v9; // eax
  const char *v10; // rdx
  int v11; // r8d
  int v13; // eax
  unsigned __int64 v14; // rdx
  __int64 v15; // [rsp+20h] [rbp-38h]

  v2 = WdcDataCollectorSetWizard::Verify((WdcDataCollectorSetWizard *)this);
  v6 = v2;
  if ( v2 < 0 )
  {
    LODWORD(v15) = v2;
LABEL_3:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetwizard.cpp",
      "WdcDataCollectorSetWizard::SetRootDirectory",
      0,
      L"FAILURE: 0x%08x",
      v15);
    return v6;
  }
  if ( *(_DWORD *)(v4 + 560) )
  {
    v8 = (OLECHAR *)WdcAlloc(0x800u, v3, v5);
    if ( !v8 )
      goto LABEL_7;
    *v8 = 0;
    if ( (this[69]
       || (v13 = (*(__int64 (__fastcall **)(const unsigned __int16 *, char *))(*(_QWORD *)this[64] + 176LL))(
                   this[64],
                   (char *)this + 552),
           v6 = v13,
           v13 >= 0))
      && (v13 = StringCchCopyW(v8, 0x400u, this[69]), v6 = v13, v13 >= 0)
      && (v13 = WdcPathCat(v8, v14, this[66]), v6 = v13, v13 >= 0) )
    {
      v7 = SysAllocString(v8);
      if ( v7 )
        goto LABEL_9;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      v6 = -2147024882;
      LODWORD(v15) = -2147024882;
    }
    else
    {
      LODWORD(v15) = v13;
    }
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetwizard.cpp",
      "WdcDataCollectorSetWizard::SetRootDirectory",
      0,
      L"FAILURE: 0x%08x",
      v15);
LABEL_13:
    WdcFree(v8, v10, v11);
    return v6;
  }
  v7 = SysAllocString(L"%LOCALAPPDATA%\\");
  if ( !v7 )
  {
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
      "WdcAssignString",
      0,
      L"FAILURE: 0x%08x",
      -2147024882);
LABEL_7:
    v6 = -2147024882;
    LODWORD(v15) = -2147024882;
    goto LABEL_3;
  }
  v8 = 0;
LABEL_9:
  v9 = (*(__int64 (__fastcall **)(const unsigned __int16 *, OLECHAR *))(*(_QWORD *)this[64] + 184LL))(this[64], v7);
  v6 = v9;
  if ( v9 < 0 )
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetwizard.cpp",
      "WdcDataCollectorSetWizard::SetRootDirectory",
      0,
      L"FAILURE: 0x%08x",
      v9);
  SysFreeString(v7);
  if ( v8 )
    goto LABEL_13;
  return v6;
}

```

## disassembly

```asm
0x18005ac1c  push    rbx
0x18005ac1e  push    rbp
0x18005ac1f  push    rsi
0x18005ac20  push    rdi
0x18005ac21  sub     rsp, 38h
0x18005ac25  mov     rbp, rcx
0x18005ac28  call    ?Verify@WdcDataCollectorSetWizard@@AEAAJXZ; WdcDataCollectorSetWizard::Verify(void)
0x18005ac2d  mov     ebx, eax
0x18005ac2f  test    eax, eax
0x18005ac31  jns     short loc_18005AC59
0x18005ac33  mov     dword ptr [rsp+58h+var_38], eax
0x18005ac37  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18005ac3e  xor     r8d, r8d; int
0x18005ac41  lea     rdx, aWdcdatacollect_107; "WdcDataCollectorSetWizard::SetRootDirec"...
0x18005ac48  lea     rcx, aBaseDiagnosisP_0; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18005ac4f  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18005ac54  jmp     loc_18005AD06
0x18005ac59  cmp     dword ptr [rcx+230h], 0
0x18005ac60  jnz     loc_18005AD11
0x18005ac66  lea     rcx, aLocalappdata; "%LOCALAPPDATA%\\"
0x18005ac6d  call    cs:__imp_SysAllocString
0x18005ac73  mov     rsi, rax
0x18005ac76  test    rax, rax
0x18005ac79  jnz     short loc_18005ACA9
0x18005ac7b  mov     esi, 8007000Eh
0x18005ac80  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18005ac87  xor     r8d, r8d; int
0x18005ac8a  mov     dword ptr [rsp+58h+var_38], esi
0x18005ac8e  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18005ac95  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18005ac9c  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18005aca1  mov     ebx, esi
0x18005aca3  mov     dword ptr [rsp+58h+var_38], esi
0x18005aca7  jmp     short loc_18005AC37
0x18005aca9  xor     edi, edi
0x18005acab  mov     rcx, [rbp+200h]
0x18005acb2  mov     rdx, rsi
0x18005acb5  mov     rax, [rcx]
0x18005acb8  mov     rax, [rax+0B8h]
0x18005acbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005acc4  mov     ebx, eax
0x18005acc6  test    eax, eax
0x18005acc8  jns     short loc_18005ACF0
0x18005acca  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18005acd1  mov     dword ptr [rsp+58h+var_38], eax
0x18005acd5  xor     r8d, r8d; int
0x18005acd8  lea     rdx, aWdcdatacollect_107; "WdcDataCollectorSetWizard::SetRootDirec"...
0x18005acdf  lea     rcx, aBaseDiagnosisP_0; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18005ace6  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18005aceb  test    rsi, rsi
0x18005acee  jz      short loc_18005ACF9
0x18005acf0  mov     rcx, rsi; bstrString
0x18005acf3  call    cs:__imp_SysFreeString
0x18005acf9  test    rdi, rdi
0x18005acfc  jz      short loc_18005AD06
0x18005acfe  mov     rcx, rdi; void *
0x18005ad01  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18005ad06  mov     eax, ebx
0x18005ad08  add     rsp, 38h
0x18005ad0c  pop     rdi
0x18005ad0d  pop     rsi
0x18005ad0e  pop     rbp
0x18005ad0f  pop     rbx
0x18005ad10  retn
0x18005ad11  mov     ecx, 800h; dwBytes
0x18005ad16  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18005ad1b  mov     rdi, rax
0x18005ad1e  test    rax, rax
0x18005ad21  jnz     short loc_18005AD2D
0x18005ad23  mov     esi, 8007000Eh
0x18005ad28  jmp     loc_18005ACA1
0x18005ad2d  xor     eax, eax
0x18005ad2f  lea     rsi, [rbp+228h]
0x18005ad36  mov     [rdi], ax
0x18005ad39  cmp     [rsi], rax
0x18005ad3c  jnz     short loc_18005AD83
0x18005ad3e  mov     rcx, [rbp+200h]
0x18005ad45  mov     rdx, rsi
0x18005ad48  mov     rax, [rcx]
0x18005ad4b  mov     rax, [rax+0B0h]
0x18005ad52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad57  mov     ebx, eax
0x18005ad59  test    eax, eax
0x18005ad5b  jns     short loc_18005AD83
0x18005ad5d  mov     dword ptr [rsp+58h+var_38], eax
0x18005ad61  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18005ad68  xor     r8d, r8d; int
0x18005ad6b  lea     rdx, aWdcdatacollect_107; "WdcDataCollectorSetWizard::SetRootDirec"...
0x18005ad72  lea     rcx, aBaseDiagnosisP_0; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18005ad79  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18005ad7e  jmp     loc_18005ACFE
0x18005ad83  mov     r8, [rsi]; unsigned __int16 *
0x18005ad86  mov     edx, 400h; unsigned __int64
0x18005ad8b  mov     rcx, rdi; unsigned __int16 *
0x18005ad8e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005ad93  mov     ebx, eax
0x18005ad95  test    eax, eax
0x18005ad97  js      short loc_18005AD5D
0x18005ad99  mov     r8, [rbp+210h]; unsigned __int16 *
0x18005ada0  mov     rcx, rdi; unsigned __int16 *
0x18005ada3  call    ?WdcPathCat@@YAJPEAG_KPEBG@Z; WdcPathCat(ushort *,unsigned __int64,ushort const *)
0x18005ada8  mov     ebx, eax
0x18005adaa  test    eax, eax
0x18005adac  js      short loc_18005AD5D
0x18005adae  mov     rcx, rdi; psz
0x18005adb1  call    cs:__imp_SysAllocString
0x18005adb7  mov     rsi, rax
0x18005adba  test    rax, rax
0x18005adbd  jnz     loc_18005ACAB
0x18005adc3  mov     esi, 8007000Eh
0x18005adc8  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18005adcf  xor     r8d, r8d; int
0x18005add2  mov     dword ptr [rsp+58h+var_38], esi
0x18005add6  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18005addd  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18005ade4  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18005ade9  mov     ebx, esi
0x18005adeb  mov     dword ptr [rsp+58h+var_38], esi
0x18005adef  jmp     loc_18005AD61
```
