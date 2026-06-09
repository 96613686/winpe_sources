# ConvertTextToUnicode

- ea: `0x1800019e0`
- end: `0x180001b1b`
- name: `ConvertTextToUnicode`
- size: `315`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001300`
- `0x180001490`
- `0x180001b30`

## callees

- `0x1800019e0`
- `0x18000e010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180001af7`
- `KERNEL32!SetLastError` at `0x180001af7`
- `OLEAUT32!__imp_SysAllocString` at `0x180001b03`
- `OLEAUT32!__imp_SysAllocString` at `0x180001b03`
- `OLEAUT32!__imp_SysFreeString` at `0x180001a9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180001a9f`
- `ole32!CoInitialize` at `0x180001a12`
- `ole32!CoInitialize` at `0x180001a12`
- `ole32!CoUninitialize` at `0x180001abf`
- `ole32!CoUninitialize` at `0x180001abf`
- `ole32!CoCreateInstance` at `0x180001a42`
- `ole32!CoCreateInstance` at `0x180001a42`

## pseudocode

```c
__int64 __fastcall ConvertTextToUnicode(__int64 a1, unsigned int a2, BSTR *a3)
{
  DWORD v4; // esi
  unsigned int v5; // ebx
  int v8; // edi
  BSTR v10; // rax
  LPVOID ppv; // [rsp+30h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+20h] BYREF

  ppv = 0;
  v4 = 0;
  bstrString = 0;
  v5 = 0;
  if ( CoInitialize(0) < 0 )
  {
    v8 = 0;
  }
  else
  {
    v8 = 1;
    if ( CoCreateInstance(&CLSID_ScriptletConstructor, 0, 1u, &IID_IConvertXMLBytesToUnicode, &ppv) < 0 )
    {
      v4 = 8;
    }
    else if ( (*(int (__fastcall **)(LPVOID, __int64, _QWORD, BSTR *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                ppv,
                a1,
                a2,
                &bstrString,
                0) < 0 )
    {
      v4 = 8;
    }
    else
    {
      if ( *bstrString != 0xFEFF )
      {
        *a3 = bstrString;
        bstrString = 0;
LABEL_6:
        v5 = 1;
        goto LABEL_7;
      }
      v10 = SysAllocString(bstrString + 1);
      *a3 = v10;
      if ( v10 )
        goto LABEL_6;
      v4 = 8;
    }
  }
LABEL_7:
  SysFreeString(bstrString);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v8 )
    CoUninitialize();
  if ( !v5 )
    SetLastError(v4);
  return v5;
}

```

## disassembly

```asm
0x1800019e0  mov     rax, rsp
0x1800019e3  mov     [rax+8], rbx
0x1800019e7  mov     [rax+10h], rbp
0x1800019eb  push    rsi
0x1800019ec  push    rdi
0x1800019ed  push    r12
0x1800019ef  push    r14
0x1800019f1  push    r15
0x1800019f3  sub     rsp, 40h
0x1800019f7  xor     r12d, r12d
0x1800019fa  mov     r15, rcx
0x1800019fd  xor     ecx, ecx; pvReserved
0x1800019ff  mov     [rax-38h], r12
0x180001a03  mov     esi, r12d
0x180001a06  mov     [rax+20h], r12
0x180001a0a  mov     ebx, r12d
0x180001a0d  mov     r14, r8
0x180001a10  mov     ebp, edx
0x180001a12  call    cs:__imp_CoInitialize
0x180001a18  test    eax, eax
0x180001a1a  js      loc_180001AE9
0x180001a20  lea     rax, [rsp+68h+var_38]
0x180001a25  mov     edi, 1
0x180001a2a  mov     r8d, edi; dwClsContext
0x180001a2d  mov     [rsp+68h+ppv], rax; ppv
0x180001a32  lea     r9, IID_IConvertXMLBytesToUnicode; riid
0x180001a39  xor     edx, edx; pUnkOuter
0x180001a3b  lea     rcx, CLSID_ScriptletConstructor; rclsid
0x180001a42  call    cs:__imp_CoCreateInstance
0x180001a48  test    eax, eax
0x180001a4a  js      loc_180001AE2
0x180001a50  mov     rcx, [rsp+68h+var_38]
0x180001a55  lea     r9, [rsp+68h+bstrString]
0x180001a5d  mov     r8d, ebp
0x180001a60  mov     [rsp+68h+ppv], r12
0x180001a65  mov     rdx, r15
0x180001a68  mov     rax, [rcx]
0x180001a6b  mov     rax, [rax+18h]
0x180001a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a74  test    eax, eax
0x180001a76  js      short loc_180001AEE
0x180001a78  mov     rax, [rsp+68h+bstrString]
0x180001a80  mov     ecx, 0FEFFh
0x180001a85  cmp     cx, [rax]
0x180001a88  jz      short loc_180001AFF
0x180001a8a  mov     [r14], rax
0x180001a8d  mov     [rsp+68h+bstrString], r12
0x180001a95  mov     ebx, edi
0x180001a97  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180001a9f  call    cs:__imp_SysFreeString
0x180001aa5  mov     rcx, [rsp+68h+var_38]
0x180001aaa  test    rcx, rcx
0x180001aad  jz      short loc_180001ABB
0x180001aaf  mov     rax, [rcx]
0x180001ab2  mov     rax, [rax+10h]
0x180001ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001abb  test    edi, edi
0x180001abd  jz      short loc_180001AC5
0x180001abf  call    cs:__imp_CoUninitialize
0x180001ac5  test    ebx, ebx
0x180001ac7  jz      short loc_180001AF5
0x180001ac9  mov     rbp, [rsp+68h+arg_8]
0x180001ace  mov     eax, ebx
0x180001ad0  mov     rbx, [rsp+68h+arg_0]
0x180001ad5  add     rsp, 40h
0x180001ad9  pop     r15
0x180001adb  pop     r14
0x180001add  pop     r12
0x180001adf  pop     rdi
0x180001ae0  pop     rsi
0x180001ae1  retn
0x180001ae2  mov     esi, 8
0x180001ae7  jmp     short loc_180001A97
0x180001ae9  mov     edi, r12d
0x180001aec  jmp     short loc_180001A97
0x180001aee  mov     esi, 8
0x180001af3  jmp     short loc_180001A97
0x180001af5  mov     ecx, esi; dwErrCode
0x180001af7  call    cs:__imp_SetLastError
0x180001afd  jmp     short loc_180001AC9
0x180001aff  lea     rcx, [rax+2]; psz
0x180001b03  call    cs:__imp_SysAllocString
0x180001b09  mov     [r14], rax
0x180001b0c  test    rax, rax
0x180001b0f  jnz     short loc_180001A95
0x180001b11  mov     esi, 8
0x180001b16  jmp     loc_180001A97
```
