# CAutoplayDialog::_PopulateUIForDeviceStage(IAutoplayDeviceHandler *)

- ea: `0x18019114c`
- end: `0x1801913d2`
- name: `?_PopulateUIForDeviceStage@CAutoplayDialog@@AEAAJPEAUIAutoplayDeviceHandler@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(CAutoplayDialog *__hidden this, struct IAutoplayDeviceHandler *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bdd30`

## callees

- `0x18000b7e8`
- `0x1800885ec`
- `0x18018b380`
- `0x18018c290`
- `0x18019114c`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801912e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801913a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801912e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801913a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801912c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801912cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801912d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801912c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801912cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801912d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801911b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180191344`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801911b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180191344`

## pseudocode

```c
__int64 __fastcall CAutoplayDialog::_PopulateUIForDeviceStage(CAutoplayDialog *this, struct IAutoplayDeviceHandler *a2)
{
  HRESULT v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rax
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  LPVOID v9; // [rsp+38h] [rbp-18h] BYREF
  LPVOID v10[2]; // [rsp+40h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+38h] BYREF

  hMem = 0;
  v4 = SHFormatResMessageArgAlloc(&_ImageBase, 9913, &hMem);
  if ( v4 >= 0 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
    v4 = CoCreateInstance(&CLSID_AutoplayHandler, 0, 3u, &GUID_d38d6ad9_8a0f_4d03_9a5b_cb3ca657a39f, &ppv);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)ppv + 24LL))(ppv, L"MSDoDxp");
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 128LL))(ppv, *((_QWORD *)this + 2));
        if ( v4 >= 0 )
        {
          v5 = *(_QWORD *)a2;
          v10[0] = 0;
          v4 = (*(__int64 (__fastcall **)(struct IAutoplayDeviceHandler *, LPVOID *))(v5 + 72))(a2, v10);
          if ( v4 >= 0 )
          {
            v9 = 0;
            v4 = SHFormatResMessageArgAlloc(&_ImageBase, 9928, &v9);
            if ( v4 >= 0 )
            {
              v4 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 112LL))(ppv, v9);
              if ( v4 >= 0 )
              {
                v6 = *(_QWORD *)a2;
                pv = 0;
                v4 = (*(__int64 (__fastcall **)(struct IAutoplayDeviceHandler *, LPVOID *))(v6 + 64))(a2, &pv);
                if ( v4 >= 0 )
                {
                  v4 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 120LL))(ppv, pv);
                  if ( v4 >= 0 )
                    v4 = CAutoPlayHandlerChooser::AddHandlerToNewGroup(this, ppv, hMem, 0);
                  CoTaskMemFree(pv);
                }
              }
              CoTaskMemFree(v9);
            }
            CoTaskMemFree(v10[0]);
          }
        }
      }
    }
    LocalFree(hMem);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
    if ( v4 >= 0 )
    {
      v4 = SHFormatResMessageArgAlloc(&_ImageBase, 9904, &hMem);
      if ( v4 >= 0 )
      {
        ppv = 0;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
        v4 = CoCreateInstance(&CLSID_AutoplayHandler, 0, 3u, &GUID_d38d6ad9_8a0f_4d03_9a5b_cb3ca657a39f, &ppv);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(LPVOID, const WCHAR *))(*(_QWORD *)ppv + 24LL))(ppv, L"MSTakeNoAction");
          if ( v4 >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 128LL))(ppv, *((_QWORD *)this + 2));
            if ( v4 >= 0 )
              v4 = CAutoPlayHandlerChooser::AddHandlerToNewGroup(this, ppv, hMem, 4);
          }
        }
        LocalFree(hMem);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
        if ( v4 >= 0 )
          CAutoPlayHandlerChooser::SelectHandler(this, 0);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18019114c  mov     [rsp-18h+arg_0], rbx
0x180191151  push    rbp
0x180191152  push    rsi
0x180191153  push    rdi
0x180191154  mov     rbp, rsp
0x180191157  sub     rsp, 50h
0x18019115b  mov     rsi, rdx
0x18019115e  mov     [rbp+hMem], 0
0x180191166  mov     rdi, rcx
0x180191169  lea     r8, [rbp+hMem]
0x18019116d  mov     edx, 26B9h
0x180191172  lea     rcx, __ImageBase
0x180191179  call    SHFormatResMessageArgAlloc
0x18019117e  mov     ebx, eax
0x180191180  test    eax, eax
0x180191182  js      loc_1801913C3
0x180191188  lea     rcx, [rbp+arg_10]
0x18019118c  mov     [rbp+arg_10], 0
0x180191194  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180191199  xor     edx, edx; pUnkOuter
0x18019119b  lea     rax, [rbp+arg_10]
0x18019119f  lea     r9, _GUID_d38d6ad9_8a0f_4d03_9a5b_cb3ca657a39f; riid
0x1801911a6  mov     [rsp+50h+ppv], rax; ppv
0x1801911ab  lea     rcx, CLSID_AutoplayHandler; rclsid
0x1801911b2  lea     r8d, [rdx+3]; dwClsContext
0x1801911b6  call    cs:__imp_CoCreateInstance
0x1801911bc  mov     ebx, eax
0x1801911be  test    eax, eax
0x1801911c0  js      loc_1801912DC
0x1801911c6  mov     rcx, [rbp+arg_10]
0x1801911ca  lea     rdx, aMsdodxp; "MSDoDxp"
0x1801911d1  mov     rax, [rcx]
0x1801911d4  mov     rax, [rax+18h]
0x1801911d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801911dd  mov     ebx, eax
0x1801911df  test    eax, eax
0x1801911e1  js      loc_1801912DC
0x1801911e7  mov     rcx, [rbp+arg_10]
0x1801911eb  mov     rdx, [rdi+10h]
0x1801911ef  mov     rax, [rcx]
0x1801911f2  mov     rax, [rax+80h]
0x1801911f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801911fe  mov     ebx, eax
0x180191200  test    eax, eax
0x180191202  js      loc_1801912DC
0x180191208  mov     rax, [rsi]
0x18019120b  lea     rdx, [rbp+var_10]
0x18019120f  mov     rcx, rsi
0x180191212  mov     [rbp+var_10], 0
0x18019121a  mov     rax, [rax+48h]
0x18019121e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180191223  mov     ebx, eax
0x180191225  test    eax, eax
0x180191227  js      loc_1801912DC
0x18019122d  mov     r9, [rbp+var_10]
0x180191231  lea     r8, [rbp+var_18]
0x180191235  mov     edx, 26C8h
0x18019123a  mov     [rbp+var_18], 0
0x180191242  lea     rcx, __ImageBase
0x180191249  call    SHFormatResMessageArgAlloc
0x18019124e  mov     ebx, eax
0x180191250  test    eax, eax
0x180191252  js      short loc_1801912D2
0x180191254  mov     rcx, [rbp+arg_10]
0x180191258  mov     rdx, [rbp+var_18]
0x18019125c  mov     rax, [rcx]
0x18019125f  mov     rax, [rax+70h]
0x180191263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180191268  mov     ebx, eax
0x18019126a  test    eax, eax
0x18019126c  js      short loc_1801912C8
0x18019126e  mov     rax, [rsi]
0x180191271  lea     rdx, [rbp+pv]
0x180191275  mov     rcx, rsi
0x180191278  mov     [rbp+pv], 0
0x180191280  mov     rax, [rax+40h]
0x180191284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180191289  mov     ebx, eax
0x18019128b  test    eax, eax
0x18019128d  js      short loc_1801912C8
0x18019128f  mov     rcx, [rbp+arg_10]
0x180191293  mov     rdx, [rbp+pv]
0x180191297  mov     rax, [rcx]
0x18019129a  mov     rax, [rax+78h]
0x18019129e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801912a3  mov     ebx, eax
0x1801912a5  test    eax, eax
0x1801912a7  js      short loc_1801912BE
0x1801912a9  mov     r8, [rbp+hMem]
0x1801912ad  xor     r9d, r9d
0x1801912b0  mov     rdx, [rbp+arg_10]
0x1801912b4  mov     rcx, rdi
0x1801912b7  call    ?AddHandlerToNewGroup@CAutoPlayHandlerChooser@@MEAAJPEAUIAutoplayHandler@@PEAGW4tag_GROUPIDS@@@Z; CAutoPlayHandlerChooser::AddHandlerToNewGroup(IAutoplayHandler *,ushort *,tag_GROUPIDS)
0x1801912bc  mov     ebx, eax
0x1801912be  mov     rcx, [rbp+pv]; pv
0x1801912c2  call    cs:__imp_CoTaskMemFree
0x1801912c8  mov     rcx, [rbp+var_18]; pv
0x1801912cc  call    cs:__imp_CoTaskMemFree
0x1801912d2  mov     rcx, [rbp+var_10]; pv
0x1801912d6  call    cs:__imp_CoTaskMemFree
0x1801912dc  mov     rcx, [rbp+hMem]; hMem
0x1801912e0  call    cs:__imp_LocalFree
0x1801912e6  lea     rcx, [rbp+arg_10]
0x1801912ea  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801912ef  test    ebx, ebx
0x1801912f1  js      loc_1801913C3
0x1801912f7  lea     r8, [rbp+hMem]
0x1801912fb  mov     edx, 26B0h
0x180191300  lea     rcx, __ImageBase
0x180191307  call    SHFormatResMessageArgAlloc
0x18019130c  mov     ebx, eax
0x18019130e  test    eax, eax
0x180191310  js      loc_1801913C3
0x180191316  lea     rcx, [rbp+arg_10]
0x18019131a  mov     [rbp+arg_10], 0
0x180191322  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180191327  xor     edx, edx; pUnkOuter
0x180191329  lea     rax, [rbp+arg_10]
0x18019132d  lea     r9, _GUID_d38d6ad9_8a0f_4d03_9a5b_cb3ca657a39f; riid
0x180191334  mov     [rsp+50h+ppv], rax; ppv
0x180191339  lea     rcx, CLSID_AutoplayHandler; rclsid
0x180191340  lea     r8d, [rdx+3]; dwClsContext
0x180191344  call    cs:__imp_CoCreateInstance
0x18019134a  mov     ebx, eax
0x18019134c  test    eax, eax
0x18019134e  js      short loc_1801913A2
0x180191350  mov     rcx, [rbp+arg_10]
0x180191354  lea     rdx, aMstakenoaction; "MSTakeNoAction"
0x18019135b  mov     rax, [rcx]
0x18019135e  mov     rax, [rax+18h]
0x180191362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180191367  mov     ebx, eax
0x180191369  test    eax, eax
0x18019136b  js      short loc_1801913A2
0x18019136d  mov     rcx, [rbp+arg_10]
0x180191371  mov     rdx, [rdi+10h]
0x180191375  mov     rax, [rcx]
0x180191378  mov     rax, [rax+80h]
0x18019137f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180191384  mov     ebx, eax
0x180191386  test    eax, eax
0x180191388  js      short loc_1801913A2
0x18019138a  mov     r8, [rbp+hMem]
0x18019138e  mov     r9d, 4
0x180191394  mov     rdx, [rbp+arg_10]
0x180191398  mov     rcx, rdi
0x18019139b  call    ?AddHandlerToNewGroup@CAutoPlayHandlerChooser@@MEAAJPEAUIAutoplayHandler@@PEAGW4tag_GROUPIDS@@@Z; CAutoPlayHandlerChooser::AddHandlerToNewGroup(IAutoplayHandler *,ushort *,tag_GROUPIDS)
0x1801913a0  mov     ebx, eax
0x1801913a2  mov     rcx, [rbp+hMem]; hMem
0x1801913a6  call    cs:__imp_LocalFree
0x1801913ac  lea     rcx, [rbp+arg_10]
0x1801913b0  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801913b5  test    ebx, ebx
0x1801913b7  js      short loc_1801913C3
0x1801913b9  xor     edx, edx; unsigned __int16 *
0x1801913bb  mov     rcx, rdi; this
0x1801913be  call    ?SelectHandler@CAutoPlayHandlerChooser@@MEAAJPEBG@Z; CAutoPlayHandlerChooser::SelectHandler(ushort const *)
0x1801913c3  mov     eax, ebx
0x1801913c5  mov     rbx, [rsp+50h+arg_0]
0x1801913ca  add     rsp, 50h
0x1801913ce  pop     rdi
0x1801913cf  pop     rsi
0x1801913d0  pop     rbp
0x1801913d1  retn
```
