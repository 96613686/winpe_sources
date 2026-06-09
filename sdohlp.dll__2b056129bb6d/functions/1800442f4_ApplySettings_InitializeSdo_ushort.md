# ApplySettings::InitializeSdo(ushort *)

- ea: `0x1800442f4`
- end: `0x1800444cf`
- name: `?InitializeSdo@ApplySettings@@AEAAJPEAG@Z`
- size: `475`
- prototype: `__int64 __fastcall(LPVOID *ppv, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180043eec`

## callees

- `0x180042a80`
- `0x1800442f4`
- `0x1800471b4`
- `0x180058010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004432e`
- `KERNEL32!GetLastError` at `0x1800443b9`
- `KERNEL32!GetLastError` at `0x180044442`
- `KERNEL32!GetLastError` at `0x18004432e`
- `KERNEL32!GetLastError` at `0x1800443b9`
- `KERNEL32!GetLastError` at `0x180044442`
- `ole32!CoCreateInstance` at `0x180044322`
- `ole32!CoCreateInstance` at `0x180044322`

## string_xrefs

- `0x180044377`: `CoCi(CLSID_IASSDOHelper)`
- `0x18004438b`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180044416`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180044493`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x18004447f`: `IIASSDOHelper->GetIasService`

## pseudocode

```c
__int64 __fastcall ApplySettings::InitializeSdo(LPVOID *ppv, unsigned __int16 *a2)
{
  unsigned int Instance; // edi
  signed int LastError; // eax
  char v6; // bl
  const char *v7; // rsi
  int v8; // r8d
  int v9; // r9d
  int v10; // edx
  signed int v11; // eax
  signed int v12; // eax

  Instance = CoCreateInstance(&CLSID_IASSDOHelper, 0, 3u, &IID_IIASSDOHelper, ppv);
  if ( Instance )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = LastError;
    }
    else
    {
      v6 = 5;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = "CoCi(CLSID_IASSDOHelper)";
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
      v10 = 12;
LABEL_28:
      WPP_SF_ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v8, v9, (__int64)v7, v6);
    }
  }
  else
  {
    Instance = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(*(_QWORD *)*ppv + 56LL))(*ppv, a2);
    if ( Instance )
    {
      v11 = GetLastError();
      v6 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v6 = v11;
      }
      else
      {
        v6 = 5;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = "IIASSDOHelper->Initialize";
        WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
        v10 = 13;
        goto LABEL_28;
      }
    }
    else
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*ppv + 80LL))(*ppv, ppv + 1);
      if ( Instance )
      {
        v12 = GetLastError();
        v6 = v12;
        if ( v12 )
        {
          if ( v12 > 0 )
            v6 = v12;
        }
        else
        {
          v6 = 5;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v7 = "IIASSDOHelper->GetIasService";
          WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
          v10 = 14;
          goto LABEL_28;
        }
      }
    }
  }
  return Instance;
}

```

## disassembly

```asm
0x1800442f4  mov     [rsp+arg_0], rbx
0x1800442f9  mov     [rsp+arg_8], rsi
0x1800442fe  push    rdi
0x1800442ff  sub     rsp, 30h
0x180044303  mov     rsi, rdx
0x180044306  mov     [rsp+38h+ppv], rcx; ppv
0x18004430b  xor     edx, edx; pUnkOuter
0x18004430d  lea     r9, IID_IIASSDOHelper; riid
0x180044314  mov     rbx, rcx
0x180044317  lea     rcx, CLSID_IASSDOHelper; rclsid
0x18004431e  lea     r8d, [rdx+3]; dwClsContext
0x180044322  call    cs:__imp_CoCreateInstance
0x180044328  mov     edi, eax
0x18004432a  test    eax, eax
0x18004432c  jz      short loc_1800443A1
0x18004432e  call    cs:__imp_GetLastError
0x180044334  mov     ebx, eax
0x180044336  test    eax, eax
0x180044338  jz      short loc_180044347
0x18004433a  jle     short loc_18004434C
0x18004433c  movzx   ebx, ax
0x18004433f  or      ebx, 80070000h
0x180044345  jmp     short loc_18004434C
0x180044347  mov     ebx, 80004005h
0x18004434c  mov     rcx, cs:WPP_GLOBAL_Control
0x180044353  lea     rax, WPP_GLOBAL_Control
0x18004435a  cmp     rcx, rax
0x18004435d  jz      loc_1800444BD
0x180044363  cmp     byte ptr [rcx+19h], 2
0x180044367  jb      loc_1800444BD
0x18004436d  test    byte ptr [rcx+1Ch], 10h
0x180044371  jz      loc_1800444BD
0x180044377  lea     rsi, aCociClsidIassd; "CoCi(CLSID_IASSDOHelper)"
0x18004437e  mov     r9d, ebx
0x180044381  mov     r8, rsi
0x180044384  lea     rdx, aNpsds; "NPSDS"
0x18004438b  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180044392  call    WppDbgPrint
0x180044397  mov     edx, 0Ch
0x18004439c  jmp     loc_1800444A4
0x1800443a1  mov     rcx, [rbx]
0x1800443a4  mov     rdx, rsi
0x1800443a7  mov     rax, [rcx]
0x1800443aa  mov     rax, [rax+38h]
0x1800443ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443b3  mov     edi, eax
0x1800443b5  test    eax, eax
0x1800443b7  jz      short loc_180044429
0x1800443b9  call    cs:__imp_GetLastError
0x1800443bf  mov     ebx, eax
0x1800443c1  test    eax, eax
0x1800443c3  jz      short loc_1800443D2
0x1800443c5  jle     short loc_1800443D7
0x1800443c7  movzx   ebx, ax
0x1800443ca  or      ebx, 80070000h
0x1800443d0  jmp     short loc_1800443D7
0x1800443d2  mov     ebx, 80004005h
0x1800443d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800443de  lea     rax, WPP_GLOBAL_Control
0x1800443e5  cmp     rcx, rax
0x1800443e8  jz      loc_1800444BD
0x1800443ee  cmp     byte ptr [rcx+19h], 2
0x1800443f2  jb      loc_1800444BD
0x1800443f8  test    byte ptr [rcx+1Ch], 10h
0x1800443fc  jz      loc_1800444BD
0x180044402  lea     rsi, aIiassdohelperI; "IIASSDOHelper->Initialize"
0x180044409  mov     r9d, ebx
0x18004440c  mov     r8, rsi
0x18004440f  lea     rdx, aNpsds; "NPSDS"
0x180044416  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18004441d  call    WppDbgPrint
0x180044422  mov     edx, 0Dh
0x180044427  jmp     short loc_1800444A4
0x180044429  mov     rcx, [rbx]
0x18004442c  lea     rdx, [rbx+8]
0x180044430  mov     rax, [rcx]
0x180044433  mov     rax, [rax+50h]
0x180044437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004443c  mov     edi, eax
0x18004443e  test    eax, eax
0x180044440  jz      short loc_1800444BD
0x180044442  call    cs:__imp_GetLastError
0x180044448  mov     ebx, eax
0x18004444a  test    eax, eax
0x18004444c  jz      short loc_18004445B
0x18004444e  jle     short loc_180044460
0x180044450  movzx   ebx, ax
0x180044453  or      ebx, 80070000h
0x180044459  jmp     short loc_180044460
0x18004445b  mov     ebx, 80004005h
0x180044460  mov     rcx, cs:WPP_GLOBAL_Control
0x180044467  lea     rax, WPP_GLOBAL_Control
0x18004446e  cmp     rcx, rax
0x180044471  jz      short loc_1800444BD
0x180044473  cmp     byte ptr [rcx+19h], 2
0x180044477  jb      short loc_1800444BD
0x180044479  test    byte ptr [rcx+1Ch], 10h
0x18004447d  jz      short loc_1800444BD
0x18004447f  lea     rsi, aIiassdohelperG; "IIASSDOHelper->GetIasService"
0x180044486  mov     r9d, ebx
0x180044489  mov     r8, rsi
0x18004448c  lea     rdx, aNpsds; "NPSDS"
0x180044493  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18004449a  call    WppDbgPrint
0x18004449f  mov     edx, 0Eh
0x1800444a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800444ab  mov     [rsp+38h+var_10], ebx
0x1800444af  mov     [rsp+38h+ppv], rsi
0x1800444b4  mov     rcx, [rcx+10h]
0x1800444b8  call    WPP_SF_ssd
0x1800444bd  mov     rbx, [rsp+38h+arg_0]
0x1800444c2  mov     eax, edi
0x1800444c4  mov     rsi, [rsp+38h+arg_8]
0x1800444c9  add     rsp, 30h
0x1800444cd  pop     rdi
0x1800444ce  retn
```
