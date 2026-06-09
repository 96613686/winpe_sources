# CreateShortcutForExe

- ea: `0x1400072c0`
- end: `0x140007574`
- name: `CreateShortcutForExe`
- size: `692`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140007f74`

## callees

- `0x140004ca8`
- `0x1400072c0`
- `0x1400175a0`
- `0x140018010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140007462`
- `msvcrt!memcpy_s` at `0x140007462`
- `KERNEL32!GetFileAttributesW` at `0x14000731b`
- `KERNEL32!GetFileAttributesW` at `0x14000731b`
- `ole32!CoTaskMemAlloc` at `0x14000740d`
- `ole32!CoTaskMemAlloc` at `0x14000740d`
- `ole32!CoCreateInstance` at `0x140007350`
- `ole32!CoCreateInstance` at `0x140007350`
- `ole32!PropVariantClear` at `0x140007496`
- `ole32!PropVariantClear` at `0x140007496`

## pseudocode

```c
__int64 __fastcall CreateShortcutForExe(__int64 a1, __int64 a2, __int64 a3, _WORD *a4)
{
  __int64 result; // rax
  HRESULT v7; // eax
  LPVOID v8; // rcx
  int v9; // ebx
  void (*v10)(void); // rax
  int v11; // eax
  __int64 v12; // rcx
  void (*v13)(void); // rax
  __int64 v14; // rax
  __int64 v15; // rbx
  void *v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  LPVOID v22; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT pvar; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF

  result = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", a1, a2);
  if ( (int)result >= 0 )
  {
    if ( GetFileAttributesW(FileName) != -1 )
      return 0;
    ppv = 0;
    v7 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &GUID_000214f9_0000_0000_c000_000000000046, &ppv);
    v8 = ppv;
    v9 = v7;
    if ( v7 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 160LL))(ppv, a3);
      v8 = ppv;
      v9 = v11;
      if ( v11 >= 0 )
      {
        v24 = 0;
        v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
               ppv,
               &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
               &v24);
        if ( v9 < 0 )
          goto LABEL_9;
        memset(&pvar, 0, sizeof(pvar));
        if ( a4 )
        {
          v14 = -1;
          do
            ++v14;
          while ( a4[v14] );
          v15 = 2 * v14 + 2;
          v16 = CoTaskMemAlloc(v15);
          pvar.hVal.QuadPart = (LONGLONG)v16;
          if ( v16 )
          {
            memcpy_s(v16, v15, a4, v15);
            pvar.vt = 31;
            v9 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v24 + 48LL))(
                   v24,
                   &PKEY_AppUserModel_ID,
                   &pvar);
            PropVariantClear(&pvar);
            v12 = v24;
            if ( v9 < 0 )
              goto LABEL_10;
            v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 56LL))(v24);
            if ( v9 >= 0 )
            {
              v25 = 0;
              v18 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
                      ppv,
                      &GUID_0000010b_0000_0000_c000_000000000046,
                      &v25);
              v19 = v25;
              v9 = v18;
              if ( v18 >= 0 )
              {
                v20 = (*(__int64 (__fastcall **)(__int64, WCHAR *, __int64))(*(_QWORD *)v25 + 48LL))(v25, FileName, 1);
                v19 = v25;
                v9 = v20;
              }
              if ( v19 )
              {
                v25 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
              }
              v21 = v24;
              if ( !v24 )
              {
LABEL_30:
                v22 = ppv;
                if ( ppv )
                {
                  ppv = 0;
                  v10 = *(void (**)(void))(*(_QWORD *)v22 + 16LL);
                  goto LABEL_32;
                }
                return (unsigned int)v9;
              }
              v24 = 0;
              v13 = *(void (**)(void))(*(_QWORD *)v21 + 16LL);
LABEL_29:
              v13();
              goto LABEL_30;
            }
LABEL_9:
            v12 = v24;
LABEL_10:
            if ( !v12 )
              goto LABEL_30;
            v24 = 0;
            v13 = *(void (**)(void))(*(_QWORD *)v12 + 16LL);
            goto LABEL_29;
          }
          v9 = -2147024882;
        }
        else
        {
          v9 = -2147024809;
        }
        v17 = v24;
        memset(&pvar, 0, sizeof(pvar));
        if ( v24 )
        {
          v24 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        }
        v8 = ppv;
      }
    }
    if ( v8 )
    {
      ppv = 0;
      v10 = *(void (**)(void))(*(_QWORD *)v8 + 16LL);
LABEL_32:
      v10();
    }
    return (unsigned int)v9;
  }
  return result;
}

```

## disassembly

```asm
0x1400072c0  push    rbp
0x1400072c2  push    rbx
0x1400072c3  push    rsi
0x1400072c4  push    rdi
0x1400072c5  push    r14
0x1400072c7  lea     rbp, [rsp-180h]
0x1400072cf  sub     rsp, 280h
0x1400072d6  mov     rax, cs:__security_cookie
0x1400072dd  xor     rax, rsp
0x1400072e0  mov     [rbp+1A0h+var_30], rax
0x1400072e7  mov     rdi, r9
0x1400072ea  mov     [rsp+2A0h+ppv], rdx
0x1400072ef  mov     r9, rcx
0x1400072f2  mov     rsi, r8
0x1400072f5  lea     rcx, [rsp+2A0h+FileName]; unsigned __int16 *
0x1400072fa  mov     edx, 104h; unsigned __int64
0x1400072ff  lea     r8, aSS; "%s\\%s"
0x140007306  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000730b  xor     r14d, r14d
0x14000730e  test    eax, eax
0x140007310  js      loc_140007557
0x140007316  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x14000731b  call    cs:__imp_GetFileAttributesW
0x140007321  cmp     eax, 0FFFFFFFFh
0x140007324  jz      short loc_14000732D
0x140007326  xor     eax, eax
0x140007328  jmp     loc_140007557
0x14000732d  xor     edx, edx; pUnkOuter
0x14000732f  mov     [rsp+2A0h+var_270], r14
0x140007334  lea     rax, [rsp+2A0h+var_270]
0x140007339  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x140007340  mov     [rsp+2A0h+ppv], rax; ppv
0x140007345  lea     rcx, CLSID_ShellLink; rclsid
0x14000734c  lea     r8d, [rdx+1]; dwClsContext
0x140007350  call    cs:__imp_CoCreateInstance
0x140007356  mov     rcx, [rsp+2A0h+var_270]
0x14000735b  mov     ebx, eax
0x14000735d  test    eax, eax
0x14000735f  jns     short loc_14000737B
0x140007361  test    rcx, rcx
0x140007364  jz      loc_140007555
0x14000736a  mov     [rsp+2A0h+var_270], r14
0x14000736f  mov     rdx, [rcx]
0x140007372  mov     rax, [rdx+10h]
0x140007376  jmp     loc_140007550
0x14000737b  mov     rax, [rcx]
0x14000737e  mov     rdx, rsi
0x140007381  mov     rax, [rax+0A0h]
0x140007388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000738d  mov     rcx, [rsp+2A0h+var_270]
0x140007392  mov     ebx, eax
0x140007394  test    eax, eax
0x140007396  js      short loc_140007361
0x140007398  mov     [rsp+2A0h+var_268], r14
0x14000739d  lea     r8, [rsp+2A0h+var_268]
0x1400073a2  mov     rax, [rcx]
0x1400073a5  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x1400073ac  mov     rax, [rax]
0x1400073af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400073b4  mov     ebx, eax
0x1400073b6  test    eax, eax
0x1400073b8  jns     short loc_1400073D9
0x1400073ba  mov     rcx, [rsp+2A0h+var_268]
0x1400073bf  test    rcx, rcx
0x1400073c2  jz      loc_14000753A
0x1400073c8  mov     [rsp+2A0h+var_268], r14
0x1400073cd  mov     rdx, [rcx]
0x1400073d0  mov     rax, [rdx+10h]
0x1400073d4  jmp     loc_140007535
0x1400073d9  xor     eax, eax
0x1400073db  xorps   xmm0, xmm0
0x1400073de  mov     qword ptr [rsp+2A0h+pvar+10h], rax
0x1400073e3  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x1400073e8  test    rdi, rdi
0x1400073eb  jnz     short loc_1400073F4
0x1400073ed  mov     ebx, 80070057h
0x1400073f2  jmp     short loc_140007422
0x1400073f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400073f8  inc     rax
0x1400073fb  cmp     [rdi+rax*2], r14w
0x140007400  jnz     short loc_1400073F8
0x140007402  lea     rbx, ds:2[rax*2]
0x14000740a  mov     rcx, rbx; cb
0x14000740d  call    cs:__imp_CoTaskMemAlloc
0x140007413  mov     qword ptr [rsp+2A0h+pvar+8], rax
0x140007418  test    rax, rax
0x14000741b  jnz     short loc_140007456
0x14000741d  mov     ebx, 8007000Eh
0x140007422  mov     rcx, [rsp+2A0h+var_268]
0x140007427  xor     eax, eax
0x140007429  mov     qword ptr [rsp+2A0h+pvar+10h], rax
0x14000742e  xorps   xmm0, xmm0
0x140007431  movups  xmmword ptr [rsp+2A0h+pvar], xmm0
0x140007436  test    rcx, rcx
0x140007439  jz      short loc_14000744C
0x14000743b  mov     [rsp+2A0h+var_268], r14
0x140007440  mov     rax, [rcx]
0x140007443  mov     rax, [rax+10h]
0x140007447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000744c  mov     rcx, [rsp+2A0h+var_270]
0x140007451  jmp     loc_140007361
0x140007456  mov     r9, rbx; SourceSize
0x140007459  mov     r8, rdi; Source
0x14000745c  mov     rdx, rbx; DestinationSize
0x14000745f  mov     rcx, rax; Destination
0x140007462  call    cs:__imp_memcpy_s
0x140007468  mov     rcx, [rsp+2A0h+var_268]
0x14000746d  lea     r8, [rsp+2A0h+pvar]
0x140007472  mov     eax, 1Fh
0x140007477  lea     rdx, PKEY_AppUserModel_ID
0x14000747e  mov     word ptr [rsp+2A0h+pvar], ax
0x140007483  mov     rax, [rcx]
0x140007486  mov     rax, [rax+30h]
0x14000748a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000748f  lea     rcx, [rsp+2A0h+pvar]; pvar
0x140007494  mov     ebx, eax
0x140007496  call    cs:__imp_PropVariantClear
0x14000749c  mov     rcx, [rsp+2A0h+var_268]
0x1400074a1  test    ebx, ebx
0x1400074a3  js      loc_1400073BF
0x1400074a9  mov     rax, [rcx]
0x1400074ac  mov     rax, [rax+38h]
0x1400074b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074b5  mov     ebx, eax
0x1400074b7  test    eax, eax
0x1400074b9  js      loc_1400073BA
0x1400074bf  mov     rcx, [rsp+2A0h+var_270]
0x1400074c4  lea     r8, [rsp+2A0h+var_260]
0x1400074c9  mov     [rsp+2A0h+var_260], r14
0x1400074ce  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x1400074d5  mov     rax, [rcx]
0x1400074d8  mov     rax, [rax]
0x1400074db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400074e0  mov     rcx, [rsp+2A0h+var_260]
0x1400074e5  mov     ebx, eax
0x1400074e7  test    eax, eax
0x1400074e9  js      short loc_140007509
0x1400074eb  mov     rax, [rcx]
0x1400074ee  lea     rdx, [rsp+2A0h+FileName]
0x1400074f3  mov     r8d, 1
0x1400074f9  mov     rax, [rax+30h]
0x1400074fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007502  mov     rcx, [rsp+2A0h+var_260]
0x140007507  mov     ebx, eax
0x140007509  test    rcx, rcx
0x14000750c  jz      short loc_14000751F
0x14000750e  mov     [rsp+2A0h+var_260], r14
0x140007513  mov     rdx, [rcx]
0x140007516  mov     rax, [rdx+10h]
0x14000751a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000751f  mov     rcx, [rsp+2A0h+var_268]
0x140007524  test    rcx, rcx
0x140007527  jz      short loc_14000753A
0x140007529  mov     [rsp+2A0h+var_268], r14
0x14000752e  mov     rax, [rcx]
0x140007531  mov     rax, [rax+10h]
0x140007535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000753a  mov     rcx, [rsp+2A0h+var_270]
0x14000753f  test    rcx, rcx
0x140007542  jz      short loc_140007555
0x140007544  mov     [rsp+2A0h+var_270], r14
0x140007549  mov     rax, [rcx]
0x14000754c  mov     rax, [rax+10h]
0x140007550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007555  mov     eax, ebx
0x140007557  mov     rcx, [rbp+1A0h+var_30]
0x14000755e  xor     rcx, rsp; StackCookie
0x140007561  call    __security_check_cookie
0x140007566  add     rsp, 280h
0x14000756d  pop     r14
0x14000756f  pop     rdi
0x140007570  pop     rsi
0x140007571  pop     rbx
0x140007572  pop     rbp
0x140007573  retn
```
