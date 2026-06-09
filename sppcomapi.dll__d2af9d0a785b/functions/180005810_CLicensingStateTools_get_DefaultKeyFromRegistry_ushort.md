# CLicensingStateTools::get_DefaultKeyFromRegistry(ushort * *)

- ea: `0x180005810`
- end: `0x180005917`
- name: `?get_DefaultKeyFromRegistry@CLicensingStateTools@@UEAAJPEAPEAG@Z`
- size: `263`
- prototype: `__int64 __fastcall(CLicensingStateTools *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180003520`
- `0x180004288`
- `0x180004d98`
- `0x180005810`
- `0x18003af34`
- `0x18003b714`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800058e6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800058e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000589e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000589e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800058fa`

## pseudocode

```c
__int64 __fastcall CLicensingStateTools::get_DefaultKeyFromRegistry(
        CLicensingStateTools *this,
        unsigned __int16 **a2,
        int a3)
{
  unsigned __int16 *v3; // rsi
  unsigned __int16 *v4; // rbx
  unsigned int v6; // edi
  int ProductKeyFromRegistry; // eax
  int v8; // eax
  int v9; // eax
  HLOCAL hMem; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int16 *v12; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int16 *v13; // [rsp+58h] [rbp+20h] BYREF

  v3 = 0;
  v4 = 0;
  v12 = 0;
  v13 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_15;
  }
  hMem = 0;
  ProductKeyFromRegistry = ReadProductKeyFromRegistry(0, (__int64)&hMem, a3);
  v6 = ProductKeyFromRegistry;
  if ( ProductKeyFromRegistry >= 0 )
  {
    v8 = CMiscHelpersT<CEmptyType>::AssignString(hMem, &v12, 0x7FFFFFFF);
    v6 = v8;
    if ( v8 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
    v3 = v12;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)ProductKeyFromRegistry);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( hMem )
    LocalFree(hMem);
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_3;
  v9 = CreateBSTR(v3, &v13);
  v6 = v9;
  if ( v9 >= 0 )
  {
    *a2 = v13;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v9);
    v4 = v13;
  }
LABEL_15:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v4 )
    SysFreeString(v4);
  if ( v3 )
    LocalFree(v3);
  return v6;
}

```

## disassembly

```asm
0x180005810  mov     [rsp+arg_0], rbx
0x180005815  push    rsi
0x180005816  push    rdi
0x180005817  push    r14
0x180005819  sub     rsp, 20h
0x18000581d  xor     esi, esi
0x18000581f  xor     ebx, ebx
0x180005821  mov     [rsp+38h+arg_10], rsi
0x180005826  mov     r14, rdx
0x180005829  mov     [rsp+38h+arg_18], rbx
0x18000582e  test    rdx, rdx
0x180005831  jnz     short loc_180005844
0x180005833  mov     edi, 80070057h
0x180005838  mov     ecx, edi
0x18000583a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000583f  jmp     loc_1800058D7
0x180005844  lea     rdx, [rsp+38h+hMem]
0x180005849  mov     [rsp+38h+hMem], rbx
0x18000584e  xor     ecx, ecx
0x180005850  call    ?ReadProductKeyFromRegistry@@YAJW4PKEY_LOCATION@@PEAPEAG@Z; ReadProductKeyFromRegistry(PKEY_LOCATION,ushort * *)
0x180005855  mov     edi, eax
0x180005857  test    eax, eax
0x180005859  jns     short loc_180005864
0x18000585b  mov     ecx, eax
0x18000585d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180005862  jmp     short loc_18000588B
0x180005864  mov     rcx, [rsp+38h+hMem]
0x180005869  lea     rdx, [rsp+38h+arg_10]
0x18000586e  mov     r8d, 7FFFFFFFh
0x180005874  call    ?AssignString@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAGI@Z; CMiscHelpersT<CEmptyType>::AssignString(ushort const *,ushort * *,uint)
0x180005879  mov     edi, eax
0x18000587b  test    eax, eax
0x18000587d  jns     short loc_180005886
0x18000587f  mov     ecx, eax
0x180005881  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180005886  mov     rsi, [rsp+38h+arg_10]
0x18000588b  mov     ecx, edi
0x18000588d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180005892  cmp     [rsp+38h+hMem], rbx
0x180005897  jz      short loc_1800058AA
0x180005899  mov     rcx, [rsp+38h+hMem]; hMem
0x18000589e  call    cs:__imp_LocalFree
0x1800058a5  nop     dword ptr [rax+rax+00h]
0x1800058aa  test    edi, edi
0x1800058ac  js      short loc_180005838
0x1800058ae  lea     rdx, [rsp+38h+arg_18]; unsigned __int16 **
0x1800058b3  mov     rcx, rsi; unsigned __int16 *
0x1800058b6  call    ?CreateBSTR@@YAJPEBGPEAPEAG@Z; CreateBSTR(ushort const *,ushort * *)
0x1800058bb  mov     edi, eax
0x1800058bd  test    eax, eax
0x1800058bf  jns     short loc_1800058CF
0x1800058c1  mov     ecx, eax
0x1800058c3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800058c8  mov     rbx, [rsp+38h+arg_18]
0x1800058cd  jmp     short loc_1800058D7
0x1800058cf  mov     rax, [rsp+38h+arg_18]
0x1800058d4  mov     [r14], rax
0x1800058d7  mov     ecx, edi
0x1800058d9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800058de  test    rbx, rbx
0x1800058e1  jz      short loc_1800058F2
0x1800058e3  mov     rcx, rbx; bstrString
0x1800058e6  call    cs:__imp_SysFreeString
0x1800058ed  nop     dword ptr [rax+rax+00h]
0x1800058f2  test    rsi, rsi
0x1800058f5  jz      short loc_180005906
0x1800058f7  mov     rcx, rsi; hMem
0x1800058fa  call    cs:__imp_LocalFree
0x180005901  nop     dword ptr [rax+rax+00h]
0x180005906  mov     rbx, [rsp+38h+arg_0]
0x18000590b  mov     eax, edi
0x18000590d  add     rsp, 20h
0x180005911  pop     r14
0x180005913  pop     rdi
0x180005914  pop     rsi
0x180005915  retn
```
