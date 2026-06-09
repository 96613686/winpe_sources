# CShortcutTF::Normalize(CEngineLocaleHandler *,ushort const *,ushort * * *,ulong *)

- ea: `0x1800d1164`
- end: `0x1800d1372`
- name: `?Normalize@CShortcutTF@@AEAAJPEAVCEngineLocaleHandler@@PEBGPEAPEAPEAGPEAK@Z`
- size: `526`
- prototype: `__int64 __fastcall(CShortcutTF *__hidden this, struct CEngineLocaleHandler *, const unsigned __int16 *, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d0f8c`

## callees

- `0x1800040b8`
- `0x1800d1164`
- `0x1800d1940`
- `0x180102010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800d1302`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1313`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1324`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1302`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1313`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d1324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d134f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d134f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d1211`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d1211`

## pseudocode

```c
__int64 __fastcall CShortcutTF::Normalize(
        CShortcutTF *this,
        struct CEngineLocaleHandler *a2,
        const unsigned __int16 *a3,
        unsigned __int16 ***a4,
        unsigned int *a5)
{
  __int64 v6; // r8
  __int64 (__fastcall *v8)(struct CEngineLocaleHandler *, const unsigned __int16 *, __int64, _QWORD, __int128 *); // rax
  int v9; // edi
  unsigned int v10; // edx
  unsigned int i; // ecx
  __int64 v12; // rax
  size_t v13; // r15
  unsigned __int16 **v14; // rax
  unsigned __int16 **v15; // rbx
  unsigned int v16; // ecx
  unsigned int v17; // esi
  unsigned __int16 *v18; // r14
  unsigned __int16 *v19; // r13
  const unsigned __int16 *v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rax
  unsigned int v24; // [rsp+30h] [rbp-50h]
  BSTR bstrString; // [rsp+40h] [rbp-40h] BYREF
  BSTR v26; // [rsp+48h] [rbp-38h] BYREF
  __int128 v27; // [rsp+50h] [rbp-30h] BYREF
  __int128 v28; // [rsp+60h] [rbp-20h]
  LPVOID pv[2]; // [rsp+70h] [rbp-10h]
  unsigned __int16 *v30; // [rsp+C0h] [rbp+40h] BYREF
  BSTR v31; // [rsp+C8h] [rbp+48h] BYREF
  unsigned __int16 ***v32; // [rsp+D8h] [rbp+58h]

  v32 = a4;
  v30 = (unsigned __int16 *)this;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  v8 = *(__int64 (__fastcall **)(struct CEngineLocaleHandler *, const unsigned __int16 *, __int64, _QWORD, __int128 *))(*(_QWORD *)a2 + 80LL);
  v27 = 0;
  v28 = 0;
  *(_OWORD *)pv = 0;
  v9 = v8(a2, a3, v6, 0, &v27);
  if ( v9 >= 0 )
  {
    v10 = 0;
    for ( i = 0; i < (unsigned int)v27; v10 += 2 * v12 + 10 )
    {
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(*(_QWORD *)(v28 + 8LL * i) + 2 * v12) );
      ++i;
    }
    v13 = v10;
    v14 = (unsigned __int16 **)CoTaskMemAlloc(v10);
    v15 = v14;
    if ( v14 )
    {
      memset_0(v14, 0, v13);
      v16 = v27;
      v17 = 0;
      v18 = (unsigned __int16 *)&v15[(unsigned int)v27];
      v30 = v18;
      if ( (_DWORD)v27 )
      {
        v19 = (unsigned __int16 *)&v15[(unsigned int)v27];
        do
        {
          bstrString = 0;
          v31 = 0;
          v26 = 0;
          (*(void (__fastcall **)(struct CEngineLocaleHandler *, _QWORD, _QWORD, BSTR *, BSTR *))(*(_QWORD *)a2 + 48LL))(
            a2,
            *(_QWORD *)(v28 + 8LL * v17),
            0,
            &bstrString,
            &v31);
          v20 = v31;
          v21 = -1;
          v15[v17] = v18;
          do
            ++v21;
          while ( v20[v21] );
          v22 = -1;
          do
            ++v22;
          while ( *(_WORD *)(*(_QWORD *)(v28 + 8LL * v17) + 2 * v22) );
          if ( (unsigned int)v21 <= (unsigned int)v22 )
            LODWORD(v22) = v21;
          v9 = StringCchCopyNExW(
                 v18,
                 ((unsigned __int64)v15 + v13 - (_QWORD)v19) >> 1,
                 v20,
                 (unsigned int)v22,
                 &v30,
                 (unsigned __int64 *)&v26,
                 v24);
          v18 = v30 + 1;
          v30 = v18;
          v19 = v18;
          if ( bstrString )
            SysFreeString(bstrString);
          if ( v31 )
            SysFreeString(v31);
          if ( v26 )
            SysFreeString(v26);
          v16 = v27;
          ++v17;
        }
        while ( v17 < (unsigned int)v27 );
      }
      *v32 = v15;
      *a5 = v16;
    }
    else
    {
      v9 = -2147024882;
    }
  }
  if ( pv[1] )
    CoTaskMemFree(pv[1]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800d1164  mov     [rsp-38h+arg_10], rbx
0x1800d1169  mov     [rsp-38h+arg_18], r9
0x1800d116e  mov     [rsp-38h+arg_0], rcx
0x1800d1173  push    rbp
0x1800d1174  push    rsi
0x1800d1175  push    rdi
0x1800d1176  push    r12
0x1800d1178  push    r13
0x1800d117a  push    r14
0x1800d117c  push    r15
0x1800d117e  mov     rbp, rsp
0x1800d1181  sub     rsp, 80h
0x1800d1188  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800d118c  mov     r10, r8
0x1800d118f  mov     r8, rbx
0x1800d1192  xor     r13d, r13d
0x1800d1195  mov     r12, rdx
0x1800d1198  inc     r8
0x1800d119b  cmp     [r10+r8*2], r13w
0x1800d11a0  jnz     short loc_1800D1198
0x1800d11a2  mov     rax, [rdx]
0x1800d11a5  lea     rcx, [rbp+var_30]
0x1800d11a9  xorps   xmm0, xmm0
0x1800d11ac  mov     [rsp+80h+var_60], rcx
0x1800d11b1  xor     r9d, r9d
0x1800d11b4  mov     rdx, r10
0x1800d11b7  mov     rcx, r12
0x1800d11ba  mov     rax, [rax+50h]
0x1800d11be  movups  [rbp+var_30], xmm0
0x1800d11c2  movups  [rbp+var_20], xmm0
0x1800d11c6  movups  xmmword ptr [rbp+pv], xmm0
0x1800d11ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d11cf  mov     edi, eax
0x1800d11d1  test    eax, eax
0x1800d11d3  js      loc_1800D1346
0x1800d11d9  mov     r8d, dword ptr [rbp+var_30]
0x1800d11dd  mov     edx, r13d
0x1800d11e0  mov     ecx, r13d
0x1800d11e3  test    r8d, r8d
0x1800d11e6  jz      short loc_1800D120C
0x1800d11e8  mov     r10, qword ptr [rbp+var_20]
0x1800d11ec  mov     eax, ecx
0x1800d11ee  mov     r9, [r10+rax*8]
0x1800d11f2  mov     rax, rbx
0x1800d11f5  inc     rax
0x1800d11f8  cmp     [r9+rax*2], r13w
0x1800d11fd  jnz     short loc_1800D11F5
0x1800d11ff  lea     edx, [rdx+rax*2]
0x1800d1202  inc     ecx
0x1800d1204  add     edx, 0Ah
0x1800d1207  cmp     ecx, r8d
0x1800d120a  jb      short loc_1800D11EC
0x1800d120c  mov     ecx, edx; cb
0x1800d120e  mov     r15d, edx
0x1800d1211  call    cs:__imp_CoTaskMemAlloc
0x1800d1217  mov     rbx, rax
0x1800d121a  test    rax, rax
0x1800d121d  jnz     short loc_1800D1229
0x1800d121f  mov     edi, 8007000Eh
0x1800d1224  jmp     loc_1800D1346
0x1800d1229  mov     r8, r15; Size
0x1800d122c  xor     edx, edx; Val
0x1800d122e  mov     rcx, rbx; void *
0x1800d1231  call    memset_0
0x1800d1236  mov     ecx, dword ptr [rbp+var_30]
0x1800d1239  mov     esi, r13d
0x1800d123c  lea     r14, [rbx+rcx*8]
0x1800d1240  mov     [rbp+arg_0], r14
0x1800d1244  test    ecx, ecx
0x1800d1246  jz      loc_1800D1339
0x1800d124c  mov     r13, r14
0x1800d124f  xor     eax, eax
0x1800d1251  mov     rdx, qword ptr [rbp+var_20]
0x1800d1255  lea     rcx, [rbp+var_38]
0x1800d1259  mov     [rbp+bstrString], rax
0x1800d125d  lea     r9, [rbp+bstrString]
0x1800d1261  mov     [rbp+arg_8], rax
0x1800d1265  xor     r8d, r8d
0x1800d1268  mov     [rbp+var_38], rax
0x1800d126c  mov     rax, [r12]
0x1800d1270  mov     [rsp+80h+var_58], rcx; unsigned __int64 *
0x1800d1275  lea     rcx, [rbp+arg_8]
0x1800d1279  mov     [rsp+80h+var_60], rcx
0x1800d127e  mov     rcx, r12
0x1800d1281  mov     edi, esi
0x1800d1283  mov     rax, [rax+30h]
0x1800d1287  mov     rdx, [rdx+rdi*8]
0x1800d128b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1290  mov     r8, [rbp+arg_8]; unsigned __int16 *
0x1800d1294  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800d1298  mov     rdx, r10
0x1800d129b  mov     [rbx+rdi*8], r14
0x1800d129f  xor     r9d, r9d
0x1800d12a2  inc     rdx
0x1800d12a5  cmp     [r8+rdx*2], r9w
0x1800d12aa  jnz     short loc_1800D12A2
0x1800d12ac  mov     rax, qword ptr [rbp+var_20]
0x1800d12b0  mov     rcx, [rax+rdi*8]
0x1800d12b4  mov     rax, r10
0x1800d12b7  inc     rax
0x1800d12ba  cmp     [rcx+rax*2], r9w
0x1800d12bf  jnz     short loc_1800D12B7
0x1800d12c1  cmp     edx, eax
0x1800d12c3  mov     rcx, r14; unsigned __int16 *
0x1800d12c6  cmovbe  eax, edx
0x1800d12c9  mov     rdx, r15
0x1800d12cc  sub     rdx, r13
0x1800d12cf  mov     r9d, eax; unsigned __int64
0x1800d12d2  add     rdx, rbx
0x1800d12d5  lea     rax, [rbp+arg_0]
0x1800d12d9  shr     rdx, 1; unsigned __int64
0x1800d12dc  mov     [rsp+80h+var_60], rax; unsigned __int16 **
0x1800d12e1  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800d12e6  mov     r14, [rbp+arg_0]
0x1800d12ea  mov     edi, eax
0x1800d12ec  mov     rcx, [rbp+bstrString]; bstrString
0x1800d12f0  add     r14, 2
0x1800d12f4  xor     eax, eax
0x1800d12f6  mov     [rbp+arg_0], r14
0x1800d12fa  mov     r13, r14
0x1800d12fd  test    rcx, rcx
0x1800d1300  jz      short loc_1800D130A
0x1800d1302  call    cs:__imp_SysFreeString
0x1800d1308  xor     eax, eax
0x1800d130a  mov     rcx, [rbp+arg_8]; bstrString
0x1800d130e  test    rcx, rcx
0x1800d1311  jz      short loc_1800D131B
0x1800d1313  call    cs:__imp_SysFreeString
0x1800d1319  xor     eax, eax
0x1800d131b  mov     rcx, [rbp+var_38]; bstrString
0x1800d131f  test    rcx, rcx
0x1800d1322  jz      short loc_1800D132C
0x1800d1324  call    cs:__imp_SysFreeString
0x1800d132a  xor     eax, eax
0x1800d132c  mov     ecx, dword ptr [rbp+var_30]
0x1800d132f  inc     esi
0x1800d1331  cmp     esi, ecx
0x1800d1333  jb      loc_1800D1251
0x1800d1339  mov     rax, [rbp+arg_18]
0x1800d133d  mov     [rax], rbx
0x1800d1340  mov     rax, [rbp+arg_20]
0x1800d1344  mov     [rax], ecx
0x1800d1346  mov     rcx, [rbp+pv+8]; pv
0x1800d134a  test    rcx, rcx
0x1800d134d  jz      short loc_1800D1355
0x1800d134f  call    cs:__imp_CoTaskMemFree
0x1800d1355  mov     rbx, [rsp+80h+arg_10]
0x1800d135d  mov     eax, edi
0x1800d135f  add     rsp, 80h
0x1800d1366  pop     r15
0x1800d1368  pop     r14
0x1800d136a  pop     r13
0x1800d136c  pop     r12
0x1800d136e  pop     rdi
0x1800d136f  pop     rsi
0x1800d1370  pop     rbp
0x1800d1371  retn
```
