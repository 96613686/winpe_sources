# SpGetSubTokenFromToken(ISpObjectToken *,ushort const *,ISpObjectToken * *,int)

- ea: `0x1800b1240`
- end: `0x1800b1399`
- name: `?SpGetSubTokenFromToken@@YAJPEAUISpObjectToken@@PEBGPEAPEAU1@H@Z`
- size: `345`
- prototype: `int(struct ISpObjectToken *, const unsigned __int16 *, struct ISpObjectToken **, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800af810`
- `0x1800c879c`

## callees

- `0x180002db8`
- `0x180004a18`
- `0x1800061d0`
- `0x18000725c`
- `0x1800b1210`
- `0x1800b1240`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b131c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b131c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SpGetSubTokenFromToken(
        struct ISpObjectToken *a1,
        const unsigned __int16 *a2,
        struct ISpObjectToken **a3)
{
  __int64 v6; // r8
  HRESULT v7; // edi
  __int64 v8; // rbx
  struct ISpObjectToken *v9; // rax
  __int64 v10; // rdx
  __int64 v12; // [rsp+30h] [rbp-20h] BYREF
  __int64 v13; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v14[2]; // [rsp+40h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+20h] BYREF

  if ( a1 && !(unsigned int)SPIsBadStringPtr(a2, (unsigned int)a2) && v6 )
    v7 = 0;
  else
    v7 = -2147467261;
  v14[0] = 0;
  if ( v7 >= 0 )
    v7 = ((__int64 (__fastcall *)(struct ISpObjectToken *, const unsigned __int16 *, _QWORD *))a1->lpVtbl->OpenKey)(
           a1,
           a2,
           v14);
  v13 = 0;
  if ( v7 >= 0 )
    v7 = ((__int64 (__fastcall *)(struct ISpObjectToken *, __int64 *))a1->lpVtbl->GetId)(a1, &v13);
  v8 = 0;
  v12 = 0;
  if ( v7 >= 0 )
  {
    CSpDynamicString::operator=((CSpDynamicString *)&v12, (CSpDynamicString *)&v13);
    CSpDynamicString::Append2HR((CSpDynamicString *)&v12, L"\\", a2);
    v8 = v12;
  }
  ppv = 0;
  if ( v7 >= 0 )
  {
    v7 = CoCreateInstance(&CLSID_SpObjectToken, 0, 0x17u, &GUID_b8aab0cf_346f_49d8_9499_c8b03f161d51, &ppv);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, _QWORD))(*(_QWORD *)ppv + 200LL))(ppv, v13, v8, v14[0]);
      if ( v7 >= 0 )
      {
        v9 = (struct ISpObjectToken *)ppv;
        ppv = 0;
        *a3 = v9;
      }
    }
  }
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&ppv, a2);
  CSpDynamicString::_free((CSpDynamicString *)&v12);
  CSpDynamicString::_free((CSpDynamicString *)&v13);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(v14, v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800b1240  mov     [rsp-18h+arg_8], rbx
0x1800b1245  mov     [rsp-18h+arg_10], rsi
0x1800b124a  push    rbp
0x1800b124b  push    rdi
0x1800b124c  push    r14
0x1800b124e  mov     rbp, rsp
0x1800b1251  sub     rsp, 50h
0x1800b1255  mov     r14, r8
0x1800b1258  mov     rsi, rdx
0x1800b125b  mov     rbx, rcx
0x1800b125e  test    rcx, rcx
0x1800b1261  jz      short loc_1800B1278
0x1800b1263  mov     rcx, rdx; unsigned __int16 *
0x1800b1266  call    ?SPIsBadStringPtr@@YAHPEBGK@Z; SPIsBadStringPtr(ushort const *,ulong)
0x1800b126b  test    eax, eax
0x1800b126d  jnz     short loc_1800B1278
0x1800b126f  test    r8, r8
0x1800b1272  jz      short loc_1800B1278
0x1800b1274  xor     edi, edi
0x1800b1276  jmp     short loc_1800B127D
0x1800b1278  mov     edi, 80004003h
0x1800b127d  mov     [rbp+var_10], 0
0x1800b1285  test    edi, edi
0x1800b1287  js      short loc_1800B12A1
0x1800b1289  mov     rax, [rbx]
0x1800b128c  lea     r8, [rbp+var_10]
0x1800b1290  mov     rdx, rsi
0x1800b1293  mov     rcx, rbx
0x1800b1296  mov     rax, [rax+48h]
0x1800b129a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b129f  mov     edi, eax
0x1800b12a1  mov     [rbp+var_18], 0
0x1800b12a9  test    edi, edi
0x1800b12ab  js      short loc_1800B12C5
0x1800b12ad  mov     rax, [rbx]
0x1800b12b0  lea     rdx, [rbp+var_18]
0x1800b12b4  mov     rcx, rbx
0x1800b12b7  mov     rax, [rax+80h]
0x1800b12be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b12c3  mov     edi, eax
0x1800b12c5  xor     ebx, ebx
0x1800b12c7  mov     [rbp+var_20], rbx
0x1800b12cb  test    edi, edi
0x1800b12cd  js      short loc_1800B12F3
0x1800b12cf  lea     rdx, [rbp+var_18]; CSpDynamicString *
0x1800b12d3  lea     rcx, [rbp+var_20]; this
0x1800b12d7  call    ??4CSpDynamicString@@QEAAPEAGAEBV0@@Z; CSpDynamicString::operator=(CSpDynamicString const &)
0x1800b12dc  mov     r8, rsi; unsigned __int16 *
0x1800b12df  lea     rdx, asc_18010F97C; "\\"
0x1800b12e6  lea     rcx, [rbp+var_20]; this
0x1800b12ea  call    ?Append2HR@CSpDynamicString@@QEAAJPEBG0@Z; CSpDynamicString::Append2HR(ushort const *,ushort const *)
0x1800b12ef  mov     rbx, [rbp+var_20]
0x1800b12f3  mov     [rbp+arg_0], 0
0x1800b12fb  test    edi, edi
0x1800b12fd  js      short loc_1800B135B
0x1800b12ff  lea     rax, [rbp+arg_0]
0x1800b1303  mov     [rsp+50h+ppv], rax; ppv
0x1800b1308  lea     r9, _GUID_b8aab0cf_346f_49d8_9499_c8b03f161d51; riid
0x1800b130f  xor     edx, edx; pUnkOuter
0x1800b1311  lea     r8d, [rdx+17h]; dwClsContext
0x1800b1315  lea     rcx, CLSID_SpObjectToken; rclsid
0x1800b131c  call    cs:__imp_CoCreateInstance
0x1800b1322  mov     edi, eax
0x1800b1324  test    eax, eax
0x1800b1326  js      short loc_1800B135B
0x1800b1328  mov     rcx, [rbp+arg_0]
0x1800b132c  mov     rax, [rcx]
0x1800b132f  mov     r9, [rbp+var_10]
0x1800b1333  mov     r8, rbx
0x1800b1336  mov     rdx, [rbp+var_18]
0x1800b133a  mov     rax, [rax+0C8h]
0x1800b1341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1346  mov     edi, eax
0x1800b1348  test    eax, eax
0x1800b134a  js      short loc_1800B135B
0x1800b134c  mov     rax, [rbp+arg_0]
0x1800b1350  mov     [rbp+arg_0], 0
0x1800b1358  mov     [r14], rax
0x1800b135b  lea     rcx, [rbp+arg_0]
0x1800b135f  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800b1364  nop
0x1800b1365  lea     rcx, [rbp+var_20]; this
0x1800b1369  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x1800b136e  nop
0x1800b136f  lea     rcx, [rbp+var_18]; this
0x1800b1373  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x1800b1378  nop
0x1800b1379  lea     rcx, [rbp+var_10]
0x1800b137d  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800b1382  mov     eax, edi
0x1800b1384  lea     r11, [rsp+50h+var_s0]
0x1800b1389  mov     rbx, [r11+28h]
0x1800b138d  mov     rsi, [r11+30h]
0x1800b1391  mov     rsp, r11
0x1800b1394  pop     r14
0x1800b1396  pop     rdi
0x1800b1397  pop     rbp
0x1800b1398  retn
```
