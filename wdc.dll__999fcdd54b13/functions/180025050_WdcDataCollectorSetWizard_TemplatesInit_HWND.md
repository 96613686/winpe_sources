# WdcDataCollectorSetWizard::TemplatesInit(HWND__ *)

- ea: `0x180025050`
- end: `0x180025293`
- name: `?TemplatesInit@WdcDataCollectorSetWizard@@AEAAJPEAUHWND__@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(WdcDataCollectorSetWizard *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030440`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x180025050`
- `0x18002e740`
- `0x180030f10`
- `0x180086010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800250f5`
- `ADVAPI32!RegOpenKeyExW` at `0x1800250f5`
- `ADVAPI32!RegEnumValueW` at `0x18002514d`
- `ADVAPI32!RegEnumValueW` at `0x18002514d`
- `ADVAPI32!RegQueryValueExW` at `0x1800251a1`
- `ADVAPI32!RegQueryValueExW` at `0x1800251a1`
- `ADVAPI32!RegCloseKey` at `0x180025273`
- `ADVAPI32!RegCloseKey` at `0x180025273`
- `USER32!GetDlgItem` at `0x180025090`
- `USER32!GetDlgItem` at `0x180025090`

## string_xrefs

- `0x1800250d5`: `Software\Microsoft\PLA\Templates`
- `0x180025224`: `WdcDataCollectorSetWizard::TemplatesInit`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorSetWizard::TemplatesInit(WdcDataCollectorSetWizard *this, HWND a2)
{
  const char *v4; // rdx
  int v5; // r8d
  BYTE *v6; // rax
  const char *v7; // rdx
  int v8; // r8d
  BYTE *v9; // rsi
  WCHAR *v10; // rdi
  signed int v11; // ebx
  WCHAR *v12; // rax
  LSTATUS v13; // eax
  const char *v14; // rdx
  int v15; // r8d
  DWORD v16; // r14d
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  struct IXMLDOMDocument *v19; // rcx
  int v20; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-40h]
  DWORD Type; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v24; // [rsp+44h] [rbp-1Ch] BYREF
  struct IXMLDOMDocument *v25; // [rsp+48h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  DWORD cchValueName; // [rsp+B0h] [rbp+50h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+58h] BYREF

  Type = 0;
  cbData = 0;
  hKey = 0;
  cchValueName = 0;
  v24 = 0;
  v25 = 0;
  GetDlgItem(a2, 2901);
  v6 = (BYTE *)WdcAlloc(0x800u, v4, v5);
  v9 = v6;
  if ( !v6 )
  {
    v10 = 0;
LABEL_3:
    v11 = -2147024882;
    LODWORD(phkResult) = -2147024882;
LABEL_32:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetwizard.cpp",
      "WdcDataCollectorSetWizard::TemplatesInit",
      0,
      L"FAILURE: 0x%08x",
      phkResult);
    goto LABEL_33;
  }
  *(_WORD *)v6 = 0;
  v12 = (WCHAR *)WdcAlloc(0x800u, v7, v8);
  v10 = v12;
  if ( !v12 )
    goto LABEL_3;
  *v12 = 0;
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\PLA\\Templates", 0, 0x20019u, &hKey);
  v11 = 0;
  if ( v13 )
  {
    if ( v13 > 0 )
      v11 = (unsigned __int16)v13 | 0x80070000;
    else
      v11 = v13;
  }
  if ( v11 < 0 )
  {
LABEL_31:
    LODWORD(phkResult) = v11;
    goto LABEL_32;
  }
  v16 = 0;
  while ( v11 >= 0 )
  {
    cchValueName = 1024;
    v17 = RegEnumValueW(hKey, v16, v10, &cchValueName, 0, 0, 0, 0);
    v11 = v17;
    if ( v17 )
    {
      if ( v17 > 0 )
        v11 = (unsigned __int16)v17 | 0x80070000;
      if ( (_WORD)v11 == 259 )
      {
        v11 = 0;
        break;
      }
    }
    else
    {
      v11 = 0;
    }
    if ( v11 < 0 )
      goto LABEL_31;
    cbData = 2048;
    v18 = RegQueryValueExW(hKey, v10, 0, &Type, v9, &cbData);
    v11 = 0;
    if ( v18 )
    {
      if ( v18 > 0 )
        v11 = (unsigned __int16)v18 | 0x80070000;
      else
        v11 = v18;
    }
    if ( v11 < 0 )
      goto LABEL_31;
    v19 = v25;
    if ( v25 )
    {
      ((void (__fastcall *)(struct IXMLDOMDocument *))v25->lpVtbl->Release)(v25);
      v25 = 0;
    }
    if ( WdcDataCollectorSetWizard::TemplateGet((WdcDataCollectorSetWizard *)v19, (unsigned __int16 *)v9, &v25) >= 0 )
    {
      v20 = WdcDataCollectorSetWizard::TemplateLoad(this, a2, v25, &v24);
      v11 = v20;
      if ( v20 < 0 )
      {
        LODWORD(phkResult) = v20;
        goto LABEL_32;
      }
    }
    else
    {
      v11 = 0;
    }
    ++v16;
  }
LABEL_33:
  if ( v25 )
  {
    ((void (__fastcall *)(struct IXMLDOMDocument *))v25->lpVtbl->Release)(v25);
    v25 = 0;
  }
  if ( v9 )
    WdcFree(v9, v14, v15);
  if ( v10 )
    WdcFree(v10, v14, v15);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180025050  mov     [rsp-38h+arg_0], rbx
0x180025055  push    rbp
0x180025056  push    rsi
0x180025057  push    rdi
0x180025058  push    r12
0x18002505a  push    r13
0x18002505c  push    r14
0x18002505e  push    r15
0x180025060  mov     rbp, rsp
0x180025063  sub     rsp, 60h
0x180025067  xor     r13d, r13d
0x18002506a  mov     r15, rdx
0x18002506d  mov     r12, rcx
0x180025070  mov     [rbp+Type], r13d
0x180025074  mov     rcx, r15; hDlg
0x180025077  mov     [rbp+cbData], r13d
0x18002507b  mov     edx, 0B55h; nIDDlgItem
0x180025080  mov     [rbp+hKey], r13
0x180025084  mov     [rbp+cchValueName], r13d
0x180025088  mov     [rbp+var_1C], r13d
0x18002508c  mov     [rbp+var_18], r13
0x180025090  call    cs:__imp_GetDlgItem
0x180025096  mov     ebx, 800h
0x18002509b  mov     ecx, ebx; dwBytes
0x18002509d  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800250a2  mov     rsi, rax
0x1800250a5  test    rax, rax
0x1800250a8  jnz     short loc_1800250BD
0x1800250aa  mov     edi, r13d
0x1800250ad  mov     ecx, 8007000Eh
0x1800250b2  mov     ebx, ecx
0x1800250b4  mov     dword ptr [rsp+60h+phkResult], ecx
0x1800250b8  jmp     loc_18002521A
0x1800250bd  mov     rcx, rbx; dwBytes
0x1800250c0  mov     [rax], r13w
0x1800250c4  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800250c9  mov     rdi, rax
0x1800250cc  test    rax, rax
0x1800250cf  jz      short loc_1800250AD
0x1800250d1  mov     [rax], r13w
0x1800250d5  lea     rdx, SubKey; "Software\\Microsoft\\PLA\\Templates"
0x1800250dc  lea     rax, [rbp+hKey]
0x1800250e0  mov     r9d, 20019h; samDesired
0x1800250e6  xor     r8d, r8d; ulOptions
0x1800250e9  mov     [rsp+60h+phkResult], rax; phkResult
0x1800250ee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800250f5  call    cs:__imp_RegOpenKeyExW
0x1800250fb  mov     ebx, r13d
0x1800250fe  test    eax, eax
0x180025100  jz      short loc_180025111
0x180025102  jg      short loc_180025108
0x180025104  mov     ebx, eax
0x180025106  jmp     short loc_180025111
0x180025108  movzx   ebx, ax
0x18002510b  or      ebx, 80070000h
0x180025111  test    ebx, ebx
0x180025113  js      loc_180025216
0x180025119  mov     r14d, r13d
0x18002511c  test    ebx, ebx
0x18002511e  js      loc_180025237
0x180025124  mov     rcx, [rbp+hKey]; hKey
0x180025128  lea     r9, [rbp+cchValueName]; lpcchValueName
0x18002512c  mov     [rsp+60h+lpcbData], r13; lpcbData
0x180025131  mov     r8, rdi; lpValueName
0x180025134  mov     [rsp+60h+lpData], r13; lpData
0x180025139  mov     edx, r14d; dwIndex
0x18002513c  mov     [rsp+60h+lpType], r13; lpType
0x180025141  mov     [rsp+60h+phkResult], r13; lpReserved
0x180025146  mov     [rbp+cchValueName], 400h
0x18002514d  call    cs:__imp_RegEnumValueW
0x180025153  mov     ebx, eax
0x180025155  test    eax, eax
0x180025157  jz      short loc_180025173
0x180025159  jle     short loc_180025164
0x18002515b  movzx   ebx, ax
0x18002515e  or      ebx, 80070000h
0x180025164  cmp     bx, 103h
0x180025169  jnz     short loc_180025176
0x18002516b  mov     ebx, r13d
0x18002516e  jmp     loc_180025237
0x180025173  mov     ebx, r13d
0x180025176  test    ebx, ebx
0x180025178  js      loc_180025216
0x18002517e  mov     rcx, [rbp+hKey]; hKey
0x180025182  lea     rax, [rbp+cbData]
0x180025186  mov     [rsp+60h+lpType], rax; lpcbData
0x18002518b  lea     r9, [rbp+Type]; lpType
0x18002518f  xor     r8d, r8d; lpReserved
0x180025192  mov     [rsp+60h+phkResult], rsi; lpData
0x180025197  mov     rdx, rdi; lpValueName
0x18002519a  mov     [rbp+cbData], 800h
0x1800251a1  call    cs:__imp_RegQueryValueExW
0x1800251a7  mov     ebx, r13d
0x1800251aa  test    eax, eax
0x1800251ac  jz      short loc_1800251BD
0x1800251ae  jg      short loc_1800251B4
0x1800251b0  mov     ebx, eax
0x1800251b2  jmp     short loc_1800251BD
0x1800251b4  movzx   ebx, ax
0x1800251b7  or      ebx, 80070000h
0x1800251bd  test    ebx, ebx
0x1800251bf  js      short loc_180025216
0x1800251c1  mov     rcx, [rbp+var_18]
0x1800251c5  test    rcx, rcx
0x1800251c8  jz      short loc_1800251DA
0x1800251ca  mov     rax, [rcx]
0x1800251cd  mov     rax, [rax+10h]
0x1800251d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251d6  mov     [rbp+var_18], r13
0x1800251da  lea     r8, [rbp+var_18]; struct IXMLDOMDocument **
0x1800251de  mov     rdx, rsi; unsigned __int16 *
0x1800251e1  call    ?TemplateGet@WdcDataCollectorSetWizard@@AEAAJPEAGPEAPEAUIXMLDOMDocument@@@Z; WdcDataCollectorSetWizard::TemplateGet(ushort *,IXMLDOMDocument * *)
0x1800251e6  test    eax, eax
0x1800251e8  jns     short loc_1800251EF
0x1800251ea  mov     ebx, r13d
0x1800251ed  jmp     short loc_180025208
0x1800251ef  mov     r8, [rbp+var_18]; struct IXMLDOMDocument *
0x1800251f3  lea     r9, [rbp+var_1C]; unsigned int *
0x1800251f7  mov     rdx, r15; HWND
0x1800251fa  mov     rcx, r12; this
0x1800251fd  call    ?TemplateLoad@WdcDataCollectorSetWizard@@AEAAJPEAUHWND__@@PEAUIXMLDOMDocument@@PEAK@Z; WdcDataCollectorSetWizard::TemplateLoad(HWND__ *,IXMLDOMDocument *,ulong *)
0x180025202  mov     ebx, eax
0x180025204  test    eax, eax
0x180025206  js      short loc_180025210
0x180025208  inc     r14d
0x18002520b  jmp     loc_18002511C
0x180025210  mov     dword ptr [rsp+60h+phkResult], eax
0x180025214  jmp     short loc_18002521A
0x180025216  mov     dword ptr [rsp+60h+phkResult], ebx
0x18002521a  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180025221  xor     r8d, r8d; int
0x180025224  lea     rdx, aWdcdatacollect_45; "WdcDataCollectorSetWizard::TemplatesIni"...
0x18002522b  lea     rcx, aBaseDiagnosisP_0; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180025232  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180025237  mov     rcx, [rbp+var_18]
0x18002523b  test    rcx, rcx
0x18002523e  jz      short loc_180025250
0x180025240  mov     rax, [rcx]
0x180025243  mov     rax, [rax+10h]
0x180025247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002524c  mov     [rbp+var_18], r13
0x180025250  test    rsi, rsi
0x180025253  jz      short loc_18002525D
0x180025255  mov     rcx, rsi; void *
0x180025258  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18002525d  test    rdi, rdi
0x180025260  jz      short loc_18002526A
0x180025262  mov     rcx, rdi; void *
0x180025265  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18002526a  mov     rcx, [rbp+hKey]; hKey
0x18002526e  test    rcx, rcx
0x180025271  jz      short loc_180025279
0x180025273  call    cs:__imp_RegCloseKey
0x180025279  mov     eax, ebx
0x18002527b  mov     rbx, [rsp+60h+arg_0]
0x180025283  add     rsp, 60h
0x180025287  pop     r15
0x180025289  pop     r14
0x18002528b  pop     r13
0x18002528d  pop     r12
0x18002528f  pop     rdi
0x180025290  pop     rsi
0x180025291  pop     rbp
0x180025292  retn
```
