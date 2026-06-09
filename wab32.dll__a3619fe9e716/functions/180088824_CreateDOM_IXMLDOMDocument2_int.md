# CreateDOM(IXMLDOMDocument2 * *,int *)

- ea: `0x180088824`
- end: `0x180088a11`
- name: `?CreateDOM@@YAJPEAPEAUIXMLDOMDocument2@@PEAH@Z`
- size: `493`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 **, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800830a0`
- `0x180089f30`

## callees

- `0x180002818`
- `0x180088824`
- `0x180093010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180088874`
- `ole32!CoCreateInstance` at `0x180088874`
- `OLEAUT32!__imp_SysAllocString` at `0x18008888b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800888fd`
- `OLEAUT32!__imp_SysAllocString` at `0x18008888b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800888fd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800889e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800889f5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800889e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800889f5`

## pseudocode

```c
__int64 __fastcall CreateDOM(LPVOID *a1, int *a2)
{
  OLECHAR *v4; // rdi
  OLECHAR *v5; // rsi
  HRESULT v6; // ebx
  BSTR v7; // rax
  BSTR v8; // rdx
  __int64 (__fastcall *v9)(LPVOID, BSTR, __int128 *); // rax
  BSTR v10; // rax
  BSTR v11; // rdx
  __int64 (__fastcall *v12)(LPVOID, BSTR, __int128 *); // rax
  __int128 v14; // [rsp+30h] [rbp-40h]
  __int128 v15; // [rsp+30h] [rbp-40h]
  __int128 v16; // [rsp+50h] [rbp-20h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h]
  LPVOID ppv; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+38h]

  *a1 = 0;
  *a2 = 0;
  ppv = 0;
  v4 = 0;
  v14 = 0;
  v5 = 0;
  v6 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &ppv);
  if ( v6 >= 0 )
  {
    v7 = SysAllocString(L"NewParser");
    v4 = v7;
    if ( !v7 )
    {
LABEL_3:
      v6 = -2147024882;
      goto LABEL_12;
    }
    LOWORD(v14) = 11;
    v8 = v7;
    v17 = 0;
    WORD4(v14) = -1;
    v9 = *(__int64 (__fastcall **)(LPVOID, BSTR, __int128 *))(*(_QWORD *)ppv + 640LL);
    v16 = v14;
    v6 = v9(ppv, v8, &v16);
    v19 = 0;
    v15 = 0;
    if ( v6 >= 0 )
    {
      v10 = SysAllocString(L"MultipleErrorMessages");
      v5 = v10;
      if ( !v10 )
        goto LABEL_3;
      LOWORD(v15) = 11;
      v11 = v10;
      v17 = v19;
      WORD4(v15) = -1;
      v12 = *(__int64 (__fastcall **)(LPVOID, BSTR, __int128 *))(*(_QWORD *)ppv + 640LL);
      v16 = v15;
      v6 = v12(ppv, v11, &v16);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 504LL))(ppv, 0);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 560LL))(ppv, 0xFFFFFFFFLL);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 544LL))(ppv, 0);
            if ( v6 >= 0 )
            {
              v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 576LL))(ppv, 0);
              if ( v6 >= 0 )
              {
                v6 = 0;
                *a1 = ppv;
                ppv = 0;
                *a2 = 1;
              }
            }
          }
        }
      }
    }
  }
LABEL_12:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&ppv);
  if ( v5 )
    SysFreeString(v5);
  if ( v4 )
    SysFreeString(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180088824  mov     [rsp-28h+arg_10], rbx
0x180088829  push    rbp
0x18008882a  push    rsi
0x18008882b  push    rdi
0x18008882c  push    r14
0x18008882e  push    r15
0x180088830  mov     rbp, rsp
0x180088833  sub     rsp, 70h
0x180088837  xor     eax, eax
0x180088839  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x180088840  mov     [rcx], rax
0x180088843  mov     r14, rdx
0x180088846  mov     [rdx], eax
0x180088848  mov     r15, rcx
0x18008884b  mov     [rbp+var_30], rax
0x18008884f  lea     rcx, CLSID_DOMDocument60; rclsid
0x180088856  mov     [rbp+arg_0], rax
0x18008885a  xorps   xmm0, xmm0
0x18008885d  lea     rax, [rbp+arg_0]
0x180088861  xor     edi, edi
0x180088863  xor     edx, edx; pUnkOuter
0x180088865  mov     [rsp+70h+ppv], rax; ppv
0x18008886a  movups  [rbp+var_40], xmm0
0x18008886e  xor     esi, esi
0x180088870  lea     r8d, [rdi+1]; dwClsContext
0x180088874  call    cs:__imp_CoCreateInstance
0x18008887a  mov     ebx, eax
0x18008887c  test    eax, eax
0x18008887e  js      loc_1800889D6
0x180088884  lea     rcx, aNewparser; "NewParser"
0x18008888b  call    cs:__imp_SysAllocString
0x180088891  mov     rdi, rax
0x180088894  test    rax, rax
0x180088897  jnz     short loc_1800888A3
0x180088899  mov     ebx, 8007000Eh
0x18008889e  jmp     loc_1800889D6
0x1800888a3  mov     rcx, [rbp+arg_0]
0x1800888a7  lea     r8, [rbp+var_20]
0x1800888ab  movsd   xmm1, [rbp+var_30]
0x1800888b0  mov     eax, 0Bh
0x1800888b5  mov     word ptr [rbp+var_40], ax
0x1800888b9  mov     rdx, rdi
0x1800888bc  or      eax, 0FFFFFFFFh
0x1800888bf  movsd   [rbp+var_10], xmm1
0x1800888c4  mov     word ptr [rbp+var_40+8], ax
0x1800888c8  mov     rax, [rcx]
0x1800888cb  movups  xmm0, [rbp+var_40]
0x1800888cf  mov     rax, [rax+280h]
0x1800888d6  movaps  [rbp+var_20], xmm0
0x1800888da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800888df  mov     ebx, eax
0x1800888e1  xorps   xmm0, xmm0
0x1800888e4  xor     eax, eax
0x1800888e6  mov     [rbp+arg_8], rax
0x1800888ea  movups  [rbp+var_40], xmm0
0x1800888ee  test    ebx, ebx
0x1800888f0  js      loc_1800889D6
0x1800888f6  lea     rcx, aMultipleerrorm; "MultipleErrorMessages"
0x1800888fd  call    cs:__imp_SysAllocString
0x180088903  mov     rsi, rax
0x180088906  test    rax, rax
0x180088909  jz      short loc_180088899
0x18008890b  mov     rcx, [rbp+arg_0]
0x18008890f  lea     r8, [rbp+var_20]
0x180088913  movsd   xmm1, [rbp+arg_8]
0x180088918  mov     eax, 0Bh
0x18008891d  mov     word ptr [rbp+var_40], ax
0x180088921  mov     rdx, rsi
0x180088924  or      eax, 0FFFFFFFFh
0x180088927  movsd   [rbp+var_10], xmm1
0x18008892c  mov     word ptr [rbp+var_40+8], ax
0x180088930  mov     rax, [rcx]
0x180088933  movups  xmm0, [rbp+var_40]
0x180088937  mov     rax, [rax+280h]
0x18008893e  movaps  [rbp+var_20], xmm0
0x180088942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088947  mov     ebx, eax
0x180088949  test    eax, eax
0x18008894b  js      loc_1800889D6
0x180088951  mov     rcx, [rbp+arg_0]
0x180088955  xor     edx, edx
0x180088957  mov     rax, [rcx]
0x18008895a  mov     rax, [rax+1F8h]
0x180088961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088966  mov     ebx, eax
0x180088968  test    eax, eax
0x18008896a  js      short loc_1800889D6
0x18008896c  mov     rcx, [rbp+arg_0]
0x180088970  or      edx, 0FFFFFFFFh
0x180088973  mov     rax, [rcx]
0x180088976  mov     rax, [rax+230h]
0x18008897d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088982  mov     ebx, eax
0x180088984  test    eax, eax
0x180088986  js      short loc_1800889D6
0x180088988  mov     rcx, [rbp+arg_0]
0x18008898c  xor     edx, edx
0x18008898e  mov     rax, [rcx]
0x180088991  mov     rax, [rax+220h]
0x180088998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008899d  mov     ebx, eax
0x18008899f  test    eax, eax
0x1800889a1  js      short loc_1800889D6
0x1800889a3  mov     rcx, [rbp+arg_0]
0x1800889a7  xor     edx, edx
0x1800889a9  mov     rax, [rcx]
0x1800889ac  mov     rax, [rax+240h]
0x1800889b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800889b8  mov     ebx, eax
0x1800889ba  test    eax, eax
0x1800889bc  js      short loc_1800889D6
0x1800889be  mov     rax, [rbp+arg_0]
0x1800889c2  xor     ebx, ebx
0x1800889c4  mov     [r15], rax
0x1800889c7  mov     [rbp+arg_0], 0
0x1800889cf  mov     dword ptr [r14], 1
0x1800889d6  lea     rcx, [rbp+arg_0]
0x1800889da  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800889df  test    rsi, rsi
0x1800889e2  jz      short loc_1800889ED
0x1800889e4  mov     rcx, rsi; bstrString
0x1800889e7  call    cs:__imp_SysFreeString
0x1800889ed  test    rdi, rdi
0x1800889f0  jz      short loc_1800889FB
0x1800889f2  mov     rcx, rdi; bstrString
0x1800889f5  call    cs:__imp_SysFreeString
0x1800889fb  mov     eax, ebx
0x1800889fd  mov     rbx, [rsp+70h+arg_10]
0x180088a05  add     rsp, 70h
0x180088a09  pop     r15
0x180088a0b  pop     r14
0x180088a0d  pop     rdi
0x180088a0e  pop     rsi
0x180088a0f  pop     rbp
0x180088a10  retn
```
