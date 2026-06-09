# CSxWindowsUpdateEnumerator::_GetPackageDisplayName(ICbsPackage *,ushort * *)

- ea: `0x1800050dc`
- end: `0x18000546f`
- name: `?_GetPackageDisplayName@CSxWindowsUpdateEnumerator@@CAJPEAUICbsPackage@@PEAPEAG@Z`
- size: `915`
- prototype: `__int64 __fastcall(struct ICbsPackage *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x18000408c`

## callees

- `0x180003ce0`
- `0x1800050dc`
- `0x18000d348`
- `0x18000d43c`
- `0x180014e30`
- `0x180014ec8`
- `0x180014f38`
- `0x180015760`
- `0x180016010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800052ce`
- `msvcrt!_wcsicmp` at `0x1800052ce`
- `ole32!CoTaskMemFree` at `0x1800053b7`
- `ole32!CoTaskMemFree` at `0x1800053c5`
- `ole32!CoTaskMemFree` at `0x1800053d3`
- `ole32!CoTaskMemFree` at `0x1800053e1`
- `ole32!CoTaskMemFree` at `0x1800053ef`
- `ole32!CoTaskMemFree` at `0x1800053fd`
- `ole32!CoTaskMemFree` at `0x1800053b7`
- `ole32!CoTaskMemFree` at `0x1800053c5`
- `ole32!CoTaskMemFree` at `0x1800053d3`
- `ole32!CoTaskMemFree` at `0x1800053e1`
- `ole32!CoTaskMemFree` at `0x1800053ef`
- `ole32!CoTaskMemFree` at `0x1800053fd`

## string_xrefs

- `0x18000512c`: `CSxWindowsUpdateEnumerator::_GetPackageDisplayName`

## pseudocode

```c
__int64 __fastcall CSxWindowsUpdateEnumerator::_GetPackageDisplayName(struct ICbsPackage *a1, unsigned __int16 **a2)
{
  __int16 v4; // ax
  __int64 v5; // rax
  bool v6; // sf
  unsigned __int16 *v7; // rax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 *v12; // [rsp+20h] [rbp-39h] BYREF
  __int64 v13; // [rsp+28h] [rbp-31h]
  int v14; // [rsp+30h] [rbp-29h] BYREF
  __int16 v15; // [rsp+34h] [rbp-25h]
  __int16 v16; // [rsp+36h] [rbp-23h]
  unsigned __int16 *v17; // [rsp+68h] [rbp+Fh] BYREF
  unsigned __int16 *v18; // [rsp+70h] [rbp+17h] BYREF
  unsigned __int16 *v19; // [rsp+78h] [rbp+1Fh] BYREF
  _QWORD v20[6]; // [rsp+80h] [rbp+27h] BYREF
  wchar_t *String1; // [rsp+C0h] [rbp+67h] BYREF
  LPVOID pv; // [rsp+D0h] [rbp+77h] BYREF
  unsigned __int16 *v23; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v14,
    "CSxWindowsUpdateEnumerator::_GetPackageDisplayName",
    385);
  String1 = 0;
  v4 = 395;
  v20[0] = 0;
  v18 = 0;
  v17 = 0;
  v23 = 0;
  pv = 0;
  v19 = 0;
  v12 = qword_18001A620;
  v13 = 0;
  if ( !a1 || (v15 = 395, v4 = 396, !a2) )
  {
    v14 = -2147024809;
    goto LABEL_6;
  }
  v15 = 396;
  *a2 = 0;
  v5 = *(_QWORD *)a1;
  v14 = 0;
  v14 = (*(__int64 (__fastcall **)(struct ICbsPackage *, _QWORD *))(v5 + 24))(a1, v20);
  v4 = 400;
  if ( v14 < 0 )
    goto LABEL_6;
  v15 = 400;
  v14 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(*(_QWORD *)v20[0] + 64LL))(v20[0], &v18);
  v4 = 402;
  if ( v14 < 0 )
    goto LABEL_6;
  v15 = 402;
  v14 = (*(__int64 (__fastcall **)(struct ICbsPackage *, __int64, wchar_t **))(*(_QWORD *)a1 + 32LL))(a1, 2, &String1);
  v4 = 404;
  if ( v14 < 0 )
    goto LABEL_6;
  v15 = 404;
  v14 = (*(__int64 (__fastcall **)(struct ICbsPackage *, __int64, unsigned __int16 **))(*(_QWORD *)a1 + 32LL))(
          a1,
          9,
          &v17);
  v4 = 406;
  if ( v14 < 0 )
    goto LABEL_6;
  v15 = 406;
  v14 = (*(__int64 (__fastcall **)(struct ICbsPackage *, __int64, unsigned __int16 **))(*(_QWORD *)a1 + 32LL))(
          a1,
          8,
          &v23);
  v4 = 408;
  if ( v14 < 0 )
    goto LABEL_6;
  v15 = 408;
  v14 = (*(__int64 (__fastcall **)(struct ICbsPackage *, __int64, LPVOID *))(*(_QWORD *)a1 + 32LL))(a1, 10, &pv);
  v4 = 410;
  if ( v14 < 0 )
    goto LABEL_6;
  v15 = 410;
  v14 = (*(__int64 (__fastcall **)(struct ICbsPackage *, __int64, unsigned __int16 **))(*(_QWORD *)a1 + 32LL))(
          a1,
          7,
          &v19);
  v4 = 412;
  if ( v14 < 0 )
    goto LABEL_6;
  v15 = 412;
  if ( String1 )
  {
    if ( _wcsicmp(String1, L"default") )
    {
      if ( !String1 || !*String1 )
        goto LABEL_22;
      v14 = CBsString::Append((CBsString *)&v12, String1);
      v6 = v14 < 0;
      v4 = 423;
    }
    else
    {
      if ( !v17 || !*v17 )
        goto LABEL_22;
      v14 = CBsString::Append((CBsString *)&v12, v23, L" for ", v17);
      v6 = v14 < 0;
      v4 = 418;
    }
    if ( v6 )
      goto LABEL_6;
    v15 = v4;
  }
LABEL_22:
  if ( pv && *(_WORD *)pv && (_DWORD)v13 )
  {
    v14 = CBsString::Append((CBsString *)&v12, L" ", (const unsigned __int16 *)pv);
    v4 = 428;
    if ( v14 < 0 )
      goto LABEL_6;
    v15 = 428;
  }
  if ( v19 && *v19 )
  {
    if ( !(_DWORD)v13 )
    {
LABEL_33:
      CBsString::Append((CBsString *)&v12, v18);
      goto LABEL_34;
    }
    v14 = CBsString::Append((CBsString *)&v12, L" (", v19, L")");
    v4 = 433;
    if ( v14 >= 0 )
    {
      v15 = 433;
      goto LABEL_32;
    }
LABEL_6:
    v16 = v4;
    goto LABEL_37;
  }
LABEL_32:
  if ( !(_DWORD)v13 )
    goto LABEL_33;
LABEL_34:
  v7 = 0;
  v13 = 0;
  if ( v12 != qword_18001A620 )
    v7 = (unsigned __int16 *)v12;
  *a2 = v7;
  v12 = qword_18001A620;
LABEL_37:
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v23);
  v23 = 0;
  CoTaskMemFree(v17);
  v17 = 0;
  CoTaskMemFree(String1);
  String1 = 0;
  CoTaskMemFree(v18);
  v18 = 0;
  CoTaskMemFree(v19);
  v19 = 0;
  if ( v20[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v20[0] + 16LL))(v20[0]);
  v8 = v14;
  CBsString::_Release((CBsString *)&v12);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14, v9, v10);
  return v8;
}

```

## disassembly

```asm
0x1800050dc  push    rbp
0x1800050de  push    rbx
0x1800050df  push    rsi
0x1800050e0  push    rdi
0x1800050e1  push    r14
0x1800050e3  lea     rbp, [rsp-37h]
0x1800050e8  sub     rsp, 90h
0x1800050ef  mov     rdi, rdx
0x1800050f2  mov     rbx, rcx
0x1800050f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050fc  lea     rax, WPP_GLOBAL_Control
0x180005103  cmp     rcx, rax
0x180005106  jz      short loc_180005126
0x180005108  test    dword ptr [rcx+1Ch], 20000000h
0x18000510f  jz      short loc_180005126
0x180005111  mov     rcx, [rcx+10h]
0x180005115  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x18000511c  mov     edx, 10h
0x180005121  call    WPP_SF_
0x180005126  mov     r8d, 181h; unsigned __int16
0x18000512c  lea     rdx, aCsxwindowsupda_6; "CSxWindowsUpdateEnumerator::_GetPackage"...
0x180005133  lea     rcx, [rbp+57h+var_80]; this
0x180005137  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000513c  xor     esi, esi
0x18000513e  lea     r14, qword_18001A620
0x180005145  mov     [rbp+57h+String1], rsi
0x180005149  mov     eax, 18Bh
0x18000514e  mov     [rbp+57h+var_30], rsi
0x180005152  mov     [rbp+57h+var_40], rsi
0x180005156  mov     [rbp+57h+var_48], rsi
0x18000515a  mov     [rbp+57h+arg_18], rsi
0x18000515e  mov     [rbp+57h+pv], rsi
0x180005162  mov     [rbp+57h+var_38], rsi
0x180005166  mov     [rbp+57h+var_90], r14
0x18000516a  mov     [rbp+57h+var_88], rsi
0x18000516e  test    rbx, rbx
0x180005171  jnz     short loc_180005183
0x180005173  mov     [rbp+57h+var_80], 80070057h
0x18000517a  mov     [rbp+57h+var_7A], ax
0x18000517e  jmp     loc_1800053B3
0x180005183  mov     [rbp+57h+var_7C], ax
0x180005187  mov     eax, 18Ch
0x18000518c  test    rdi, rdi
0x18000518f  jz      short loc_180005173
0x180005191  mov     [rbp+57h+var_7C], ax
0x180005195  lea     rdx, [rbp+57h+var_30]
0x180005199  mov     [rdi], rsi
0x18000519c  mov     rcx, rbx
0x18000519f  mov     rax, [rbx]
0x1800051a2  mov     [rbp+57h+var_80], esi
0x1800051a5  mov     rax, [rax+18h]
0x1800051a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051ae  mov     [rbp+57h+var_80], eax
0x1800051b1  test    eax, eax
0x1800051b3  mov     eax, 190h
0x1800051b8  js      short loc_18000517A
0x1800051ba  mov     rcx, [rbp+57h+var_30]
0x1800051be  lea     rdx, [rbp+57h+var_40]
0x1800051c2  mov     [rbp+57h+var_7C], ax
0x1800051c6  mov     rax, [rcx]
0x1800051c9  mov     rax, [rax+40h]
0x1800051cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051d2  mov     [rbp+57h+var_80], eax
0x1800051d5  test    eax, eax
0x1800051d7  mov     eax, 192h
0x1800051dc  js      short loc_18000517A
0x1800051de  mov     [rbp+57h+var_7C], ax
0x1800051e2  lea     r8, [rbp+57h+String1]
0x1800051e6  mov     rax, [rbx]
0x1800051e9  mov     edx, 2
0x1800051ee  mov     rcx, rbx
0x1800051f1  mov     rax, [rax+20h]
0x1800051f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051fa  mov     [rbp+57h+var_80], eax
0x1800051fd  test    eax, eax
0x1800051ff  mov     eax, 194h
0x180005204  js      loc_18000517A
0x18000520a  mov     [rbp+57h+var_7C], ax
0x18000520e  lea     r8, [rbp+57h+var_48]
0x180005212  mov     rax, [rbx]
0x180005215  mov     edx, 9
0x18000521a  mov     rcx, rbx
0x18000521d  mov     rax, [rax+20h]
0x180005221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005226  mov     [rbp+57h+var_80], eax
0x180005229  test    eax, eax
0x18000522b  mov     eax, 196h
0x180005230  js      loc_18000517A
0x180005236  mov     [rbp+57h+var_7C], ax
0x18000523a  lea     r8, [rbp+57h+arg_18]
0x18000523e  mov     rax, [rbx]
0x180005241  mov     edx, 8
0x180005246  mov     rcx, rbx
0x180005249  mov     rax, [rax+20h]
0x18000524d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005252  mov     [rbp+57h+var_80], eax
0x180005255  test    eax, eax
0x180005257  mov     eax, 198h
0x18000525c  js      loc_18000517A
0x180005262  mov     [rbp+57h+var_7C], ax
0x180005266  lea     r8, [rbp+57h+pv]
0x18000526a  mov     rax, [rbx]
0x18000526d  mov     edx, 0Ah
0x180005272  mov     rcx, rbx
0x180005275  mov     rax, [rax+20h]
0x180005279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000527e  mov     [rbp+57h+var_80], eax
0x180005281  test    eax, eax
0x180005283  mov     eax, 19Ah
0x180005288  js      loc_18000517A
0x18000528e  mov     [rbp+57h+var_7C], ax
0x180005292  lea     r8, [rbp+57h+var_38]
0x180005296  mov     rax, [rbx]
0x180005299  mov     edx, 7
0x18000529e  mov     rcx, rbx
0x1800052a1  mov     rax, [rax+20h]
0x1800052a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052aa  mov     [rbp+57h+var_80], eax
0x1800052ad  test    eax, eax
0x1800052af  mov     eax, 19Ch
0x1800052b4  js      loc_18000517A
0x1800052ba  mov     rcx, [rbp+57h+String1]; String1
0x1800052be  mov     [rbp+57h+var_7C], ax
0x1800052c2  test    rcx, rcx
0x1800052c5  jz      short loc_180005313
0x1800052c7  lea     rdx, aDefault; "default"
0x1800052ce  call    cs:__imp__wcsicmp
0x1800052d4  test    eax, eax
0x1800052d6  jnz     loc_180005441
0x1800052dc  mov     r9, [rbp+57h+var_48]; unsigned __int16 *
0x1800052e0  test    r9, r9
0x1800052e3  jz      short loc_180005313
0x1800052e5  cmp     [r9], si
0x1800052e9  jz      short loc_180005313
0x1800052eb  mov     rdx, [rbp+57h+arg_18]; unsigned __int16 *
0x1800052ef  lea     r8, aFor; " for "
0x1800052f6  lea     rcx, [rbp+57h+var_90]; this
0x1800052fa  call    ?Append@CBsString@@QEAAJPEBG00@Z; CBsString::Append(ushort const *,ushort const *,ushort const *)
0x1800052ff  mov     [rbp+57h+var_80], eax
0x180005302  test    eax, eax
0x180005304  mov     eax, 1A2h
0x180005309  js      loc_18000517A
0x18000530f  mov     [rbp+57h+var_7C], ax
0x180005313  mov     r8, [rbp+57h+pv]; unsigned __int16 *
0x180005317  test    r8, r8
0x18000531a  jz      short loc_18000534B
0x18000531c  cmp     [r8], si
0x180005320  jz      short loc_18000534B
0x180005322  cmp     dword ptr [rbp+57h+var_88], esi
0x180005325  jz      short loc_18000534B
0x180005327  lea     rdx, asc_1800193B4; " "
0x18000532e  lea     rcx, [rbp+57h+var_90]; this
0x180005332  call    ?Append@CBsString@@QEAAJPEBG0@Z; CBsString::Append(ushort const *,ushort const *)
0x180005337  mov     [rbp+57h+var_80], eax
0x18000533a  test    eax, eax
0x18000533c  mov     eax, 1ACh
0x180005341  js      loc_18000517A
0x180005347  mov     [rbp+57h+var_7C], ax
0x18000534b  mov     r8, [rbp+57h+var_38]; unsigned __int16 *
0x18000534f  test    r8, r8
0x180005352  jz      short loc_18000538A
0x180005354  cmp     [r8], si
0x180005358  jz      short loc_18000538A
0x18000535a  cmp     dword ptr [rbp+57h+var_88], esi
0x18000535d  jz      short loc_18000538F
0x18000535f  lea     r9, asc_1800193B8; ")"
0x180005366  lea     rdx, asc_1800193BC; " ("
0x18000536d  lea     rcx, [rbp+57h+var_90]; this
0x180005371  call    ?Append@CBsString@@QEAAJPEBG00@Z; CBsString::Append(ushort const *,ushort const *,ushort const *)
0x180005376  mov     [rbp+57h+var_80], eax
0x180005379  test    eax, eax
0x18000537b  mov     eax, 1B1h
0x180005380  js      loc_18000517A
0x180005386  mov     [rbp+57h+var_7C], ax
0x18000538a  cmp     dword ptr [rbp+57h+var_88], esi
0x18000538d  jnz     short loc_18000539C
0x18000538f  mov     rdx, [rbp+57h+var_40]; unsigned __int16 *
0x180005393  lea     rcx, [rbp+57h+var_90]; this
0x180005397  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000539c  cmp     [rbp+57h+var_90], r14
0x1800053a0  mov     rax, rsi
0x1800053a3  mov     [rbp+57h+var_88], rsi
0x1800053a7  cmovnz  rax, [rbp+57h+var_90]
0x1800053ac  mov     [rdi], rax
0x1800053af  mov     [rbp+57h+var_90], r14
0x1800053b3  mov     rcx, [rbp+57h+pv]; pv
0x1800053b7  call    cs:__imp_CoTaskMemFree
0x1800053bd  mov     rcx, [rbp+57h+arg_18]; pv
0x1800053c1  mov     [rbp+57h+pv], rsi
0x1800053c5  call    cs:__imp_CoTaskMemFree
0x1800053cb  mov     rcx, [rbp+57h+var_48]; pv
0x1800053cf  mov     [rbp+57h+arg_18], rsi
0x1800053d3  call    cs:__imp_CoTaskMemFree
0x1800053d9  mov     rcx, [rbp+57h+String1]; pv
0x1800053dd  mov     [rbp+57h+var_48], rsi
0x1800053e1  call    cs:__imp_CoTaskMemFree
0x1800053e7  mov     rcx, [rbp+57h+var_40]; pv
0x1800053eb  mov     [rbp+57h+String1], rsi
0x1800053ef  call    cs:__imp_CoTaskMemFree
0x1800053f5  mov     rcx, [rbp+57h+var_38]; pv
0x1800053f9  mov     [rbp+57h+var_40], rsi
0x1800053fd  call    cs:__imp_CoTaskMemFree
0x180005403  mov     rcx, [rbp+57h+var_30]
0x180005407  mov     [rbp+57h+var_38], rsi
0x18000540b  test    rcx, rcx
0x18000540e  jz      short loc_18000541C
0x180005410  mov     rax, [rcx]
0x180005413  mov     rax, [rax+10h]
0x180005417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000541c  mov     ebx, [rbp+57h+var_80]
0x18000541f  lea     rcx, [rbp+57h+var_90]; this
0x180005423  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180005428  lea     rcx, [rbp+57h+var_80]; this
0x18000542c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180005431  mov     eax, ebx
0x180005433  add     rsp, 90h
0x18000543a  pop     r14
0x18000543c  pop     rdi
0x18000543d  pop     rsi
0x18000543e  pop     rbx
0x18000543f  pop     rbp
0x180005440  retn
0x180005441  mov     rdx, [rbp+57h+String1]; unsigned __int16 *
0x180005445  test    rdx, rdx
0x180005448  jz      loc_180005313
0x18000544e  cmp     [rdx], si
0x180005451  jz      loc_180005313
0x180005457  lea     rcx, [rbp+57h+var_90]; this
0x18000545b  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180005460  mov     [rbp+57h+var_80], eax
0x180005463  test    eax, eax
0x180005465  mov     eax, 1A7h
0x18000546a  jmp     loc_180005309
```
