# EnumKey(HKEY__ *,ushort *,IWbemClassObject *)

- ea: `0x180009774`
- end: `0x180009993`
- name: `?EnumKey@@YAJPEAUHKEY__@@PEAGPEAUIWbemClassObject@@@Z`
- size: `543`
- prototype: `LSTATUS __fastcall(HKEY, unsigned __int16 *, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800043c0`

## callees

- `0x180004390`
- `0x180009774`
- `0x180009c6c`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800097bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800097bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009817`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009817`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800098b9`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800098b9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009965`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180009965`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009847`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009847`
- `OLEAUT32!__imp_SysAllocString` at `0x1800098ce`
- `OLEAUT32!__imp_SysAllocString` at `0x1800098ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800098f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800098f1`
- `OLEAUT32!__imp_VariantClear` at `0x18000995b`
- `OLEAUT32!__imp_VariantClear` at `0x18000995b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180009886`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180009886`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180009907`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180009907`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800098e6`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800098e6`

## pseudocode

```c
LSTATUS __fastcall EnumKey(HKEY a1, unsigned __int16 *a2, struct IWbemClassObject *a3)
{
  LSTATUS result; // eax
  LSTATUS v5; // ebx
  OLECHAR *v6; // rax
  OLECHAR *v7; // rdi
  SAFEARRAY *v8; // rsi
  int v9; // eax
  DWORD i; // ecx
  BSTR v11; // rax
  OLECHAR *v12; // r14
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-19h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-15h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-11h] BYREF
  HKEY v16; // [rsp+70h] [rbp-9h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+78h] [rbp-1h] BYREF
  DWORD cValues; // [rsp+7Ch] [rbp+3h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+80h] [rbp+7h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp+Fh] BYREF
  void *v21[2]; // [rsp+A0h] [rbp+27h] BYREF
  LONG rgIndices; // [rsp+F8h] [rbp+7Fh] BYREF

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  hKey = 0;
  result = RegOpenKeyExW(a1, a2, 0, 9u, &hKey);
  if ( !result )
  {
    v16 = hKey;
    v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    if ( !v5 && cbMaxSubKeyLen )
    {
      v6 = (OLECHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(cbMaxSubKeyLen + 1, (unsigned int)(v5 + 2)));
      v7 = v6;
      if ( !v6 )
      {
        CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v16);
        return -2147217402;
      }
      v21[0] = v6;
      v21[1] = 0;
      rgsabound.lLbound = 0;
      rgsabound.cElements = cSubKeys;
      v8 = SafeArrayCreate(8u, 1u, &rgsabound);
      if ( v8 )
      {
        v9 = 0;
        for ( i = 0; ; i = rgIndices + 1 )
        {
          rgIndices = v9;
          if ( i >= cSubKeys )
            break;
          if ( !RegEnumKeyW(hKey, v9, v7, cbMaxSubKeyLen + 1) )
          {
            v7[cbMaxSubKeyLen] = 0;
            v11 = SysAllocString(v7);
            v12 = v11;
            if ( v11 )
            {
              v5 = SafeArrayPutElement(v8, &rgIndices, v11);
              SysFreeString(v12);
              if ( v5 < 0 )
              {
                SafeArrayDestroy(v8);
                goto LABEL_15;
              }
            }
          }
          v9 = rgIndices + 1;
        }
        *(_QWORD *)&pvarg.vt = 8200;
        *(_OWORD *)&pvarg.decVal.Lo32 = (unsigned __int64)v8;
        v5 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))a3->lpVtbl->Put)(
               a3,
               L"sNames",
               0,
               &pvarg,
               0);
        VariantClear(&pvarg);
        CWin32DefaultArena::WbemMemFree(v7);
      }
      else
      {
        v5 = -2147217402;
LABEL_15:
        CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v21);
      }
    }
    CRegCloseMe::~CRegCloseMe((CRegCloseMe *)&v16);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180009774  mov     [rsp-8+arg_0], rbx
0x180009779  mov     [rsp-8+arg_8], rsi
0x18000977e  push    rbp
0x18000977f  push    rdi
0x180009780  push    r12
0x180009782  push    r14
0x180009784  push    r15
0x180009786  lea     rbp, [rsp-37h]
0x18000978b  sub     rsp, 0B0h
0x180009792  mov     r15, r8
0x180009795  xor     r12d, r12d
0x180009798  mov     [rbp+57h+cSubKeys], r12d
0x18000979c  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x1800097a0  mov     [rbp+57h+cValues], r12d
0x1800097a4  mov     [rbp+57h+cbMaxValueNameLen], r12d
0x1800097a8  mov     [rbp+57h+hKey], r12
0x1800097ac  lea     rax, [rbp+57h+hKey]
0x1800097b0  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800097b5  lea     r9d, [r12+9]; samDesired
0x1800097ba  xor     r8d, r8d; ulOptions
0x1800097bd  call    cs:__imp_RegOpenKeyExW
0x1800097c3  test    eax, eax
0x1800097c5  jnz     loc_180009977
0x1800097cb  mov     rax, [rbp+57h+hKey]
0x1800097cf  mov     [rbp+57h+var_60], rax
0x1800097d3  mov     [rsp+0D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800097d8  mov     [rsp+0D0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800097dd  mov     [rsp+0D0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1800097e2  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x1800097e6  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800097eb  lea     rax, [rbp+57h+cValues]
0x1800097ef  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x1800097f4  mov     [rsp+0D0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800097f9  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1800097fd  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180009802  lea     rax, [rbp+57h+cSubKeys]
0x180009806  mov     [rsp+0D0h+phkResult], rax; lpcSubKeys
0x18000980b  xor     r9d, r9d; lpReserved
0x18000980e  xor     r8d, r8d; lpcchClass
0x180009811  xor     edx, edx; lpClass
0x180009813  mov     rcx, [rbp+57h+hKey]; hKey
0x180009817  call    cs:__imp_RegQueryInfoKeyW
0x18000981d  mov     ebx, eax
0x18000981f  test    eax, eax
0x180009821  jnz     loc_18000996C
0x180009827  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18000982a  test    eax, eax
0x18000982c  jz      loc_18000996C
0x180009832  lea     ecx, [rax+1]
0x180009835  lea     eax, [rbx+2]
0x180009838  mul     rcx
0x18000983b  lea     rcx, [r12-1]
0x180009840  cmovb   rax, rcx
0x180009844  mov     rcx, rax
0x180009847  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000984d  mov     rdi, rax
0x180009850  test    rax, rax
0x180009853  jnz     short loc_180009868
0x180009855  lea     rcx, [rbp+57h+var_60]; this
0x180009859  call    ??1CRegCloseMe@@QEAA@XZ; CRegCloseMe::~CRegCloseMe(void)
0x18000985e  mov     eax, 80041006h
0x180009863  jmp     loc_180009977
0x180009868  mov     [rbp+57h+var_30], rdi
0x18000986c  mov     [rbp+57h+var_28], r12
0x180009870  mov     [rbp+57h+rgsabound.lLbound], r12d
0x180009874  mov     eax, [rbp+57h+cSubKeys]
0x180009877  mov     [rbp+57h+rgsabound.cElements], eax
0x18000987a  mov     ecx, 8; vt
0x18000987f  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180009883  lea     edx, [rcx-7]; cDims
0x180009886  call    cs:__imp_SafeArrayCreate
0x18000988c  mov     rsi, rax
0x18000988f  test    rax, rax
0x180009892  jnz     short loc_18000989B
0x180009894  mov     ebx, 80041006h
0x180009899  jmp     short loc_18000990E
0x18000989b  mov     eax, r12d
0x18000989e  mov     ecx, r12d
0x1800098a1  mov     [rbp+57h+rgIndices], eax
0x1800098a4  cmp     ecx, [rbp+57h+cSubKeys]
0x1800098a7  jnb     short loc_180009919
0x1800098a9  mov     r9d, [rbp+57h+cbMaxSubKeyLen]
0x1800098ad  inc     r9d; cchName
0x1800098b0  mov     r8, rdi; lpName
0x1800098b3  mov     edx, eax; dwIndex
0x1800098b5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800098b9  call    cs:__imp_RegEnumKeyW
0x1800098bf  test    eax, eax
0x1800098c1  jnz     short loc_1800098FB
0x1800098c3  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x1800098c6  mov     [rdi+rcx*2], r12w
0x1800098cb  mov     rcx, rdi; psz
0x1800098ce  call    cs:__imp_SysAllocString
0x1800098d4  mov     r14, rax
0x1800098d7  test    rax, rax
0x1800098da  jz      short loc_1800098FB
0x1800098dc  mov     r8, rax; pv
0x1800098df  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x1800098e3  mov     rcx, rsi; psa
0x1800098e6  call    cs:__imp_SafeArrayPutElement
0x1800098ec  mov     ebx, eax
0x1800098ee  mov     rcx, r14; bstrString
0x1800098f1  call    cs:__imp_SysFreeString
0x1800098f7  test    ebx, ebx
0x1800098f9  js      short loc_180009904
0x1800098fb  mov     eax, [rbp+57h+rgIndices]
0x1800098fe  inc     eax
0x180009900  mov     ecx, eax
0x180009902  jmp     short loc_1800098A1
0x180009904  mov     rcx, rsi; psa
0x180009907  call    cs:__imp_SafeArrayDestroy
0x18000990d  nop
0x18000990e  lea     rcx, [rbp+57h+var_30]
0x180009912  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180009917  jmp     short loc_18000996C
0x180009919  xorps   xmm0, xmm0
0x18000991c  xor     eax, eax
0x18000991e  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180009922  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180009926  mov     eax, 2008h
0x18000992b  mov     word ptr [rbp+57h+pvarg], ax
0x18000992f  mov     qword ptr [rbp+57h+pvarg+8], rsi
0x180009933  mov     rax, [r15]
0x180009936  mov     dword ptr [rsp+0D0h+phkResult], r12d
0x18000993b  lea     r9, [rbp+57h+pvarg]
0x18000993f  xor     r8d, r8d
0x180009942  lea     rdx, aSnames; "sNames"
0x180009949  mov     rcx, r15
0x18000994c  mov     rax, [rax+28h]
0x180009950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009955  mov     ebx, eax
0x180009957  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000995b  call    cs:__imp_VariantClear
0x180009961  nop
0x180009962  mov     rcx, rdi
0x180009965  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000996b  nop
0x18000996c  lea     rcx, [rbp+57h+var_60]; this
0x180009970  call    ??1CRegCloseMe@@QEAA@XZ; CRegCloseMe::~CRegCloseMe(void)
0x180009975  mov     eax, ebx
0x180009977  lea     r11, [rsp+0D0h+var_20]
0x18000997f  mov     rbx, [r11+30h]
0x180009983  mov     rsi, [r11+38h]
0x180009987  mov     rsp, r11
0x18000998a  pop     r15
0x18000998c  pop     r14
0x18000998e  pop     r12
0x180009990  pop     rdi
0x180009991  pop     rbp
0x180009992  retn
```
