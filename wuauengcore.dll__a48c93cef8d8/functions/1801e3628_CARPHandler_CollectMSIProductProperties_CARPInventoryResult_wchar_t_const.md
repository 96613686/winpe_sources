# CARPHandler::CollectMSIProductProperties(CARPInventoryResult *,wchar_t const *)

- ea: `0x1801e3628`
- end: `0x1801e39ed`
- name: `?CollectMSIProductProperties@CARPHandler@@AEAAJPEAVCARPInventoryResult@@PEB_W@Z`
- size: `965`
- prototype: `__int64 __fastcall(CARPHandler *__hidden this, struct CARPInventoryResult *, const wchar_t *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801e2f34`

## callees

- `0x18000c824`
- `0x18012b618`
- `0x18012d944`
- `0x18013618c`
- `0x1801e3628`
- `0x1801e39f4`
- `0x1801e4894`
- `0x1801e48c4`
- `0x1801e493c`
- `0x1801e4b30`
- `0x180238960`
- `0x180238984`
- `0x180239110`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801e3718`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801e37a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801e3718`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801e37a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801e36e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801e376f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801e36e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801e376f`
- `OLEAUT32!__imp_VariantInit` at `0x1801e3830`
- `OLEAUT32!__imp_VariantInit` at `0x1801e38ed`
- `OLEAUT32!__imp_VariantInit` at `0x1801e3830`
- `OLEAUT32!__imp_VariantInit` at `0x1801e38ed`
- `OLEAUT32!__imp_VariantClear` at `0x1801e3863`
- `OLEAUT32!__imp_VariantClear` at `0x1801e3863`

## string_xrefs

- `0x1801e372b`: `Software\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x1801e369e`: `Software\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x1801e36f5`: `SystemComponent`
- `0x1801e3782`: `SystemComponent`
- `0x1801e3975`: `Inventory: Product was not installed; skipping`
- `0x1801e37b4`: `Inventory: Product was a system component; skipping, ProductId = '%ws'`
- `0x1801e366a`: `Inventory: Collecting properties for MSI Application, ProductID = "%ws"`
- `0x1801e399e`: `Inventory: Done collecting properties for MSI Application, ProductID = "%ws"`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CARPHandler::CollectMSIProductProperties(
        __int64 (__fastcall **this)(const wchar_t *, const wchar_t *, wchar_t *, unsigned int *),
        struct CARPInventoryResult *a2,
        const wchar_t *a3)
{
  int MSIAppProperty; // esi
  BOOL v7; // ebx
  VARIANTARG *v8; // rbx
  __int64 v9; // r13
  unsigned int v10; // r14d
  char *v11; // rax
  char *v12; // rdi
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v15[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  MSIAppProperty = 0;
  WUTrace(0, 0, 0x20000, 5, 0, L"Inventory: Collecting properties for MSI Application, ProductID = \"%ws\"", a3);
  hKey = 0;
  v7 = 0;
  v15[0] = 0;
  if ( (int)StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall", a3) < 0 )
    goto LABEL_13;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    if ( RegQueryDwordValue(hKey, L"SystemComponent", v15) >= 0 )
      v7 = v15[0] == 1;
    RegCloseKey(hKey);
    if ( v7 )
      goto LABEL_12;
  }
  if ( (int)StringCchPrintfW(
              SubKey,
              0x104u,
              L"%s\\%s",
              L"Software\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall",
              a3) < 0
    || RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    goto LABEL_13;
  }
  v15[0] = 0;
  if ( RegQueryDwordValue(hKey, L"SystemComponent", v15) >= 0 && v15[0] == 1 )
    v7 = 1;
  RegCloseKey(hKey);
  if ( !v7 )
  {
LABEL_13:
    if ( ((unsigned int (__fastcall *)(const wchar_t *))this[71])(a3) == 5 )
    {
      v8 = (VARIANTARG *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v8 )
      {
        *(_QWORD *)&v8[1].vt = &CSusArrayList<CInventoryProperty *,CSusArrayListItemOpDelete<CInventoryProperty *>>::`vftable';
        v8[1].llVal = 0;
        v8[1].pRecInfo = 0;
        VariantInit(v8);
        *(_QWORD *)v15 = v8;
        MSIAppProperty = CARPHandler::GetMSIAppProperty(this, a3, (PCNZWCH *)(*((_QWORD *)a2 + 1) + 16LL), v8);
        if ( MSIAppProperty < 0
          || (MSIAppProperty = CInventoryRuleResult::AddResultInstance(
                                 (struct CARPInventoryResult *)((char *)a2 + 16),
                                 (struct CInventoryResultInstance *)v8),
              MSIAppProperty < 0) )
        {
          VariantClear(v8);
          CSusArrayList<CInventoryProperty *,CSusArrayListItemOpDelete<CInventoryProperty *>>::~CSusArrayList<CInventoryProperty *,CSusArrayListItemOpDelete<CInventoryProperty *>>(&v8[1]);
          operator delete(v8, (const struct std::nothrow_t *)0x30);
        }
        else
        {
          *(_QWORD *)v15 = 0;
          v9 = *((_QWORD *)a2 + 1);
          v10 = 0;
          if ( *(_DWORD *)(v9 + 52) )
          {
            while ( 1 )
            {
              hKey = *(HKEY *)(*(_QWORD *)(v9 + 40) + 8LL * v10);
              v11 = (char *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
              v12 = v11;
              if ( !v11 )
                break;
              *(_QWORD *)v11 = 0;
              VariantInit((VARIANTARG *)(v11 + 8));
              CARPHandler::GetMSIAppProperty(this, a3, (PCNZWCH *)&hKey, (struct tagVARIANT *)(v12 + 8));
              MSIAppProperty = SusSysAllocString((const wchar_t *)hKey, (wchar_t **)v12);
              if ( MSIAppProperty < 0
                || (MSIAppProperty = CInventoryResultInstance::AddPropery(
                                       (CInventoryResultInstance *)v8,
                                       (struct CInventoryProperty *)v12),
                    MSIAppProperty < 0) )
              {
                CInventoryProperty::~CInventoryProperty((CInventoryProperty *)v12);
                operator delete(v12, (const struct std::nothrow_t *)0x20);
                goto LABEL_29;
              }
              if ( ++v10 >= *(_DWORD *)(v9 + 52) )
                goto LABEL_29;
            }
            MSIAppProperty = -2147024882;
          }
        }
      }
      else
      {
        MSIAppProperty = -2147024882;
      }
    }
    else
    {
      WUTrace(0, 0, 0x20000, 5, 0, L"Inventory: Product was not installed; skipping");
    }
  }
  else
  {
LABEL_12:
    WUTrace(0, 0, 0x20000, 5, 0, L"Inventory: Product was a system component; skipping, ProductId = '%ws'", a3);
  }
LABEL_29:
  WUTrace(
    0,
    0,
    0x20000,
    5,
    MSIAppProperty,
    L"Inventory: Done collecting properties for MSI Application, ProductID = \"%ws\"",
    a3);
  return (unsigned int)MSIAppProperty;
}

```

## disassembly

```asm
0x1801e3628  mov     [rsp-8+arg_18], rbx
0x1801e362d  push    rbp
0x1801e362e  push    rsi
0x1801e362f  push    rdi
0x1801e3630  push    r12
0x1801e3632  push    r13
0x1801e3634  push    r14
0x1801e3636  push    r15
0x1801e3638  lea     rbp, [rsp-180h]
0x1801e3640  sub     rsp, 280h
0x1801e3647  mov     rax, cs:__security_cookie
0x1801e364e  xor     rax, rsp
0x1801e3651  mov     [rbp+1B0h+var_40], rax
0x1801e3658  mov     r15, r8
0x1801e365b  mov     r13, rdx
0x1801e365e  mov     r12, rcx
0x1801e3661  xor     edi, edi
0x1801e3663  mov     esi, edi
0x1801e3665  mov     [rsp+2B0h+var_280], r8
0x1801e366a  lea     rax, aInventoryColle_0; "Inventory: Collecting properties for MS"...
0x1801e3671  mov     [rsp+2B0h+var_288], rax
0x1801e3676  mov     [rsp+2B0h+phkResult], rdi
0x1801e367b  xor     edx, edx
0x1801e367d  xor     ecx, ecx
0x1801e367f  lea     r9d, [rdi+5]
0x1801e3683  mov     r8d, 20000h
0x1801e3689  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801e368e  mov     [rsp+2B0h+hKey], rdi
0x1801e3693  mov     ebx, edi
0x1801e3695  mov     [rsp+2B0h+var_260], edi
0x1801e3699  mov     [rsp+2B0h+phkResult], r15
0x1801e369e  lea     r9, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1801e36a5  lea     r8, aSS_0; "%s\\%s"
0x1801e36ac  mov     edx, 104h; unsigned __int64
0x1801e36b1  lea     rcx, [rsp+2B0h+SubKey]; Buffer
0x1801e36b6  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801e36bb  lea     r14d, [rdi+1]
0x1801e36bf  test    eax, eax
0x1801e36c1  js      loc_1801E37DD
0x1801e36c7  lea     rax, [rsp+2B0h+hKey]
0x1801e36cc  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1801e36d1  mov     r9d, 20019h; samDesired
0x1801e36d7  xor     r8d, r8d; ulOptions
0x1801e36da  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1801e36df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801e36e6  call    cs:__imp_RegOpenKeyExW
0x1801e36ec  test    eax, eax
0x1801e36ee  jnz     short loc_1801E3726
0x1801e36f0  lea     r8, [rsp+2B0h+var_260]; unsigned int *
0x1801e36f5  lea     rdx, aSystemcomponen; "SystemComponent"
0x1801e36fc  mov     rcx, [rsp+2B0h+hKey]; HKEY
0x1801e3701  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x1801e3706  test    eax, eax
0x1801e3708  js      short loc_1801E3713
0x1801e370a  cmp     [rsp+2B0h+var_260], r14d
0x1801e370f  cmovz   ebx, r14d
0x1801e3713  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1801e3718  call    cs:__imp_RegCloseKey
0x1801e371e  test    ebx, ebx
0x1801e3720  jnz     loc_1801E37AF
0x1801e3726  mov     [rsp+2B0h+phkResult], r15
0x1801e372b  lea     r9, aSoftwareWow643; "Software\\Wow6432Node\\Microsoft\\Windo"...
0x1801e3732  lea     r8, aSS_0; "%s\\%s"
0x1801e3739  mov     edx, 104h; unsigned __int64
0x1801e373e  lea     rcx, [rsp+2B0h+SubKey]; Buffer
0x1801e3743  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801e3748  test    eax, eax
0x1801e374a  js      loc_1801E37DD
0x1801e3750  lea     rax, [rsp+2B0h+hKey]
0x1801e3755  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1801e375a  mov     r9d, 20019h; samDesired
0x1801e3760  xor     r8d, r8d; ulOptions
0x1801e3763  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1801e3768  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801e376f  call    cs:__imp_RegOpenKeyExW
0x1801e3775  test    eax, eax
0x1801e3777  jnz     short loc_1801E37DD
0x1801e3779  mov     [rsp+2B0h+var_260], edi
0x1801e377d  lea     r8, [rsp+2B0h+var_260]; unsigned int *
0x1801e3782  lea     rdx, aSystemcomponen; "SystemComponent"
0x1801e3789  mov     rcx, [rsp+2B0h+hKey]; HKEY
0x1801e378e  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x1801e3793  test    eax, eax
0x1801e3795  js      short loc_1801E37A0
0x1801e3797  cmp     [rsp+2B0h+var_260], r14d
0x1801e379c  cmovz   ebx, r14d
0x1801e37a0  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1801e37a5  call    cs:__imp_RegCloseKey
0x1801e37ab  test    ebx, ebx
0x1801e37ad  jz      short loc_1801E37DD
0x1801e37af  mov     [rsp+2B0h+var_280], r15
0x1801e37b4  lea     rax, aInventoryProdu_0; "Inventory: Product was a system compone"...
0x1801e37bb  mov     [rsp+2B0h+var_288], rax
0x1801e37c0  mov     [rsp+2B0h+phkResult], rdi
0x1801e37c5  xor     edx, edx
0x1801e37c7  xor     ecx, ecx
0x1801e37c9  lea     r9d, [rdx+5]
0x1801e37cd  mov     r8d, 20000h
0x1801e37d3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801e37d8  jmp     loc_1801E3999
0x1801e37dd  mov     rcx, r15
0x1801e37e0  mov     rax, [r12+238h]
0x1801e37e8  call    _guard_dispatch_icall
0x1801e37ed  cmp     eax, 5
0x1801e37f0  jnz     loc_1801E3975
0x1801e37f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801e37fd  lea     r14d, [rax+2Bh]
0x1801e3801  mov     ecx, r14d; unsigned __int64
0x1801e3804  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801e3809  mov     rbx, rax
0x1801e380c  mov     [rsp+2B0h+var_270], rax
0x1801e3811  test    rax, rax
0x1801e3814  jz      loc_1801E396E
0x1801e381a  lea     rax, ??_7?$CSusArrayList@PEAVCInventoryProperty@@V?$CSusArrayListItemOpDelete@PEAVCInventoryProperty@@@@@@6B@; const CSusArrayList<CInventoryProperty *,CSusArrayListItemOpDelete<CInventoryProperty *>>::`vftable'
0x1801e3821  mov     [rbx+18h], rax
0x1801e3825  mov     [rbx+20h], rdi
0x1801e3829  mov     [rbx+28h], rdi
0x1801e382d  mov     rcx, rbx; pvarg
0x1801e3830  call    cs:__imp_VariantInit
0x1801e3836  mov     qword ptr [rsp+2B0h+var_260], rbx
0x1801e383b  test    rbx, rbx
0x1801e383e  jz      loc_1801E396E
0x1801e3844  mov     r8, [r13+8]
0x1801e3848  add     r8, 10h; wchar_t **
0x1801e384c  mov     r9, rbx; struct tagVARIANT *
0x1801e384f  mov     rdx, r15; wchar_t *
0x1801e3852  mov     rcx, r12; this
0x1801e3855  call    ?GetMSIAppProperty@CARPHandler@@AEAAJPEB_WAEBQEA_WPEAUtagVARIANT@@@Z; CARPHandler::GetMSIAppProperty(wchar_t const *,wchar_t * const &,tagVARIANT *)
0x1801e385a  mov     esi, eax
0x1801e385c  test    eax, eax
0x1801e385e  jns     short loc_1801E3882
0x1801e3860  mov     rcx, rbx; pvarg
0x1801e3863  call    cs:__imp_VariantClear
0x1801e3869  lea     rcx, [rbx+18h]
0x1801e386d  call    ??1?$CSusArrayList@PEAVCInventoryProperty@@V?$CSusArrayListItemOpDelete@PEAVCInventoryProperty@@@@@@UEAA@XZ; CSusArrayList<CInventoryProperty *,CSusArrayListItemOpDelete<CInventoryProperty *>>::~CSusArrayList<CInventoryProperty *,CSusArrayListItemOpDelete<CInventoryProperty *>>(void)
0x1801e3872  mov     rdx, r14; struct std::nothrow_t *
0x1801e3875  mov     rcx, rbx; void *
0x1801e3878  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801e387d  jmp     loc_1801E3999
0x1801e3882  lea     rcx, [r13+10h]; this
0x1801e3886  mov     rdx, rbx; struct CInventoryResultInstance *
0x1801e3889  call    ?AddResultInstance@CInventoryRuleResult@@QEAAJPEAVCInventoryResultInstance@@@Z; CInventoryRuleResult::AddResultInstance(CInventoryResultInstance *)
0x1801e388e  mov     esi, eax
0x1801e3890  test    eax, eax
0x1801e3892  js      short loc_1801E3860
0x1801e3894  mov     qword ptr [rsp+2B0h+var_260], rdi
0x1801e3899  mov     r13, [r13+8]
0x1801e389d  mov     r14d, edi
0x1801e38a0  mov     eax, [r13+34h]
0x1801e38a4  test    eax, eax
0x1801e38a6  jz      loc_1801E3973
0x1801e38ac  cmp     edi, eax
0x1801e38ae  jnb     loc_1801E3935
0x1801e38b4  mov     ecx, r14d
0x1801e38b7  mov     rax, [r13+28h]
0x1801e38bb  mov     rcx, [rax+rcx*8]
0x1801e38bf  mov     [rsp+2B0h+hKey], rcx
0x1801e38c4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801e38cb  mov     ecx, 20h ; ' '; unsigned __int64
0x1801e38d0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801e38d5  mov     rdi, rax
0x1801e38d8  mov     [rsp+2B0h+var_270], rax
0x1801e38dd  test    rax, rax
0x1801e38e0  jz      short loc_1801E395E
0x1801e38e2  mov     qword ptr [rax], 0
0x1801e38e9  lea     rcx, [rax+8]; pvarg
0x1801e38ed  call    cs:__imp_VariantInit
0x1801e38f3  mov     [rsp+2B0h+var_270], rdi
0x1801e38f8  test    rdi, rdi
0x1801e38fb  jz      short loc_1801E3967
0x1801e38fd  lea     r9, [rdi+8]; struct tagVARIANT *
0x1801e3901  lea     r8, [rsp+2B0h+hKey]; wchar_t **
0x1801e3906  mov     rdx, r15; wchar_t *
0x1801e3909  mov     rcx, r12; this
0x1801e390c  call    ?GetMSIAppProperty@CARPHandler@@AEAAJPEB_WAEBQEA_WPEAUtagVARIANT@@@Z; CARPHandler::GetMSIAppProperty(wchar_t const *,wchar_t * const &,tagVARIANT *)
0x1801e3911  mov     rdx, rdi; wchar_t **
0x1801e3914  mov     rcx, [rsp+2B0h+hKey]; wchar_t *
0x1801e3919  call    ?SusSysAllocString@@YAJPEB_WPEAPEA_W@Z; SusSysAllocString(wchar_t const *,wchar_t * *)
0x1801e391e  mov     esi, eax
0x1801e3920  test    eax, eax
0x1801e3922  js      short loc_1801E3947
0x1801e3924  mov     rdx, rdi; struct CInventoryProperty *
0x1801e3927  mov     rcx, rbx; this
0x1801e392a  call    ?AddPropery@CInventoryResultInstance@@QEAAJPEAVCInventoryProperty@@@Z; CInventoryResultInstance::AddPropery(CInventoryProperty *)
0x1801e392f  mov     esi, eax
0x1801e3931  test    eax, eax
0x1801e3933  js      short loc_1801E3947
0x1801e3935  inc     r14d
0x1801e3938  mov     eax, [r13+34h]
0x1801e393c  cmp     r14d, eax
0x1801e393f  jb      loc_1801E38B4
0x1801e3945  jmp     short loc_1801E3973
0x1801e3947  mov     rcx, rdi; this
0x1801e394a  call    ??1CInventoryProperty@@QEAA@XZ; CInventoryProperty::~CInventoryProperty(void)
0x1801e394f  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1801e3954  mov     rcx, rdi; void *
0x1801e3957  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801e395c  jmp     short loc_1801E3973
0x1801e395e  mov     [rsp+2B0h+var_270], 0
0x1801e3967  mov     esi, 8007000Eh
0x1801e396c  jmp     short loc_1801E3973
0x1801e396e  mov     esi, 8007000Eh
0x1801e3973  jmp     short loc_1801E3999
0x1801e3975  lea     rax, aInventoryProdu; "Inventory: Product was not installed; s"...
0x1801e397c  mov     [rsp+2B0h+var_288], rax
0x1801e3981  mov     [rsp+2B0h+phkResult], rdi
0x1801e3986  xor     edx, edx
0x1801e3988  xor     ecx, ecx
0x1801e398a  lea     r9d, [rdx+5]
0x1801e398e  mov     r8d, 20000h
0x1801e3994  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801e3999  mov     [rsp+2B0h+var_280], r15
0x1801e399e  lea     rax, aInventoryDoneC; "Inventory: Done collecting properties f"...
0x1801e39a5  mov     [rsp+2B0h+var_288], rax
0x1801e39aa  mov     dword ptr [rsp+2B0h+phkResult], esi
0x1801e39ae  xor     edx, edx
0x1801e39b0  xor     ecx, ecx
0x1801e39b2  lea     r9d, [rdx+5]
0x1801e39b6  mov     r8d, 20000h
0x1801e39bc  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801e39c1  mov     eax, esi
0x1801e39c3  mov     rcx, [rbp+1B0h+var_40]
0x1801e39ca  xor     rcx, rsp; StackCookie
0x1801e39cd  call    __security_check_cookie
0x1801e39d2  mov     rbx, [rsp+2B0h+arg_18]
0x1801e39da  add     rsp, 280h
0x1801e39e1  pop     r15
0x1801e39e3  pop     r14
0x1801e39e5  pop     r13
0x1801e39e7  pop     r12
0x1801e39e9  pop     rdi
0x1801e39ea  pop     rsi
0x1801e39eb  pop     rbp
0x1801e39ec  retn
```
