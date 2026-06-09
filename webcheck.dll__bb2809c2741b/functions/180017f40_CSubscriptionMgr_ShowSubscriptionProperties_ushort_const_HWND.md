# CSubscriptionMgr::ShowSubscriptionProperties(ushort const *,HWND__ *)

- ea: `0x180017f40`
- end: `0x1800182ad`
- name: `?ShowSubscriptionProperties@CSubscriptionMgr@@UEAAJPEBGPEAUHWND__@@@Z`
- size: `877`
- prototype: `__int64 __fastcall(CSubscriptionMgr *__hidden this, const unsigned __int16 *, HWND)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003950`
- `0x18000bb8c`
- `0x18000e28c`
- `0x180017f40`
- `0x180018934`
- `0x18001c5c0`
- `0x18001c728`
- `0x180028018`
- `0x18002924e`
- `0x180029280`
- `0x180029310`
- `0x18002a010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180017fbf`
- `KERNEL32!LocalAlloc` at `0x180017fbf`
- `ole32!CoTaskMemFree` at `0x180018264`
- `ole32!CoTaskMemFree` at `0x18001827b`
- `ole32!CoTaskMemFree` at `0x180018264`
- `ole32!CoTaskMemFree` at `0x18001827b`
- `ole32!CoCreateInstance` at `0x1800180a2`
- `ole32!CoCreateInstance` at `0x1800180a2`

## pseudocode

```c
__int64 __fastcall CSubscriptionMgr::ShowSubscriptionProperties(
        CSubscriptionMgr *this,
        const unsigned __int16 *a2,
        HWND a3)
{
  const unsigned __int16 *v3; // r12
  struct OOEBuf *v5; // rax
  struct OOEBuf **v6; // r14
  HRESULT Instance; // esi
  int v8; // eax
  char *v9; // r13
  __int64 (__fastcall ***v10)(_QWORD, GUID *, LPVOID *); // rcx
  HINSTANCE v11; // rbx
  void *v12; // rcx
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  HWND v16; // [rsp+40h] [rbp-C0h]
  _DWORD v17[2]; // [rsp+50h] [rbp-B0h] BYREF
  HWND v18; // [rsp+58h] [rbp-A8h]
  HINSTANCE v19; // [rsp+60h] [rbp-A0h]
  char *v20; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+78h] [rbp-88h]
  int v22; // [rsp+80h] [rbp-80h]
  _QWORD *v23; // [rsp+88h] [rbp-78h]
  PROPSHEETPAGEW_V4 constPropSheetPagePointer; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v25[10]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v26[264]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v27[2088]; // [rsp+380h] [rbp+280h] BYREF

  v16 = a3;
  v3 = (const unsigned __int16 *)((char *)this + 48);
  pv = 0;
  v15 = 0;
  StringCchCopyW((unsigned __int16 *)this + 24, 0x824u, a2);
  v5 = (struct OOEBuf *)*((_QWORD *)this + 657);
  v6 = (struct OOEBuf **)((char *)this + 5256);
  if ( v5 || (v5 = (struct OOEBuf *)LocalAlloc(0x40u, 0x1590u), (*v6 = v5) != 0) )
  {
    GetDefaultOOEBuf(v5, SUBSTYPE_URL);
    v8 = LoadSubscription(v3, &pv);
    v9 = (char *)pv;
    if ( v8 < 0 )
    {
      CreateCookie((char *)*v6 + 116);
      StringCchCopyW((unsigned __int16 *)this + 2108, 0x104u, v3);
      StringCchCopyW((unsigned __int16 *)*v6 + 278, 0x825u, v3);
      StringCchCopyW((unsigned __int16 *)*v6 + 2363, 0x105u, v3);
    }
    else
    {
      StringCchCopyW(
        (unsigned __int16 *)this + 2108,
        0x104u,
        (const unsigned __int16 *)((char *)pv + *((_QWORD *)pv + 26) + 8));
      CopyToOOEBuf(v9 + 8, *v6);
      *((_DWORD *)*v6 + 1376) = 16;
    }
    Instance = CoCreateInstance((const IID *const)((char *)*v6 + 152), 0, 1u, &IID_IUnknown, (LPVOID *)this + 658);
    if ( Instance >= 0 )
    {
      v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, LPVOID *))*((_QWORD *)this + 658);
      pv = 0;
      Instance = (**v10)(v10, &IID_ISubscriptionAgentShellExt, &pv);
      if ( Instance >= 0 )
      {
        StringCchCopyW(v27, 0x825u, (const unsigned __int16 *)*v6 + 278);
        StringCchCopyW(v26, 0x105u, (const unsigned __int16 *)*v6 + 2363);
        Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, unsigned __int16 *, unsigned __int16 *, int))(*(_QWORD *)pv + 24LL))(
                     pv,
                     (__int64)*v6 + 116,
                     v27,
                     v26,
                     -1);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
        if ( Instance >= 0 )
        {
          memset_0(v17, 0, 0x60u);
          memset_0(v25, 0, sizeof(v25));
          v18 = v16;
          v17[0] = 96;
          v20 = (char *)this + 4216;
          v11 = g_hinstMUI;
          v17[1] = 33554433;
          v19 = g_hinstMUI;
          v21 = 0;
          v22 = 0;
          v23 = v25;
          memset_0(&constPropSheetPagePointer, 0, sizeof(constPropSheetPagePointer));
          *(_QWORD *)&constPropSheetPagePointer.dwSize = 104;
          constPropSheetPagePointer.lParam = (LPARAM)this - 16;
          constPropSheetPagePointer.hInstance = v11;
          constPropSheetPagePointer.pfnDlgProc = (DLGPROC)SummaryPropDlgProc;
          constPropSheetPagePointer.pszTemplate = (LPCWSTR)6026;
          v25[0] = CreatePropertySheetPageW(&constPropSheetPagePointer);
          ++v21;
          if ( v25[0] )
          {
            if ( (*((_BYTE *)*v6 + 5504) & 0x10) == 0
              || (Instance = (*(__int64 (__fastcall **)(char *, __int64 (__fastcall *)(struct _PSP *, __int64), _DWORD *))(*((_QWORD *)this - 2) + 24LL))(
                               (char *)this - 16,
                               _AddOnePropSheetPage,
                               v17),
                  Instance >= 0) )
            {
              if ( PropertySheet(v17) >= 0 )
              {
                Instance = LoadSubscription(v3, &v15);
                if ( Instance >= 0 )
                {
                  v12 = (void *)*((_QWORD *)this + 3);
                  if ( v12 )
                    CoTaskMemFree(v12);
                  *((_QWORD *)this + 3) = v15;
                }
              }
              else
              {
                Instance = -2147467259;
              }
            }
          }
        }
      }
    }
    if ( v9 )
      CoTaskMemFree(v9);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180017f40  mov     [rsp-8+arg_18], rbx
0x180017f45  push    rbp
0x180017f46  push    rsi
0x180017f47  push    rdi
0x180017f48  push    r12
0x180017f4a  push    r13
0x180017f4c  push    r14
0x180017f4e  push    r15
0x180017f50  lea     rbp, [rsp-12E0h]
0x180017f58  mov     eax, 13E0h
0x180017f5d  call    _alloca_probe
0x180017f62  sub     rsp, rax
0x180017f65  mov     rax, cs:__security_cookie
0x180017f6c  xor     rax, rsp
0x180017f6f  mov     [rbp+1310h+var_40], rax
0x180017f76  mov     [rsp+1410h+var_13D0], r8
0x180017f7b  lea     r12, [rcx+30h]
0x180017f7f  mov     r8, rdx; unsigned __int16 *
0x180017f82  mov     [rsp+1410h+pv], 0
0x180017f8b  mov     r15, rcx
0x180017f8e  mov     [rsp+1410h+var_13D8], 0
0x180017f97  mov     edx, 824h; unsigned __int64
0x180017f9c  mov     rcx, r12; unsigned __int16 *
0x180017f9f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017fa4  mov     rax, [r15+1488h]
0x180017fab  lea     r14, [r15+1488h]
0x180017fb2  test    rax, rax
0x180017fb5  jnz     short loc_180017FD7
0x180017fb7  mov     edx, 1590h; uBytes
0x180017fbc  lea     ecx, [rax+40h]; uFlags
0x180017fbf  call    cs:__imp_LocalAlloc
0x180017fc5  mov     [r14], rax
0x180017fc8  test    rax, rax
0x180017fcb  jnz     short loc_180017FD7
0x180017fcd  mov     esi, 8007000Eh
0x180017fd2  jmp     loc_180018281
0x180017fd7  xor     edx, edx; enum SUBSCRIPTIONTYPE
0x180017fd9  mov     rcx, rax; struct OOEBuf *
0x180017fdc  call    ?GetDefaultOOEBuf@@YAJPEAUOOEBuf@@W4SUBSCRIPTIONTYPE@@@Z; GetDefaultOOEBuf(OOEBuf *,SUBSCRIPTIONTYPE)
0x180017fe1  lea     rdx, [rsp+1410h+pv]
0x180017fe6  mov     rcx, r12
0x180017fe9  lea     rbx, [r15+1078h]
0x180017ff0  call    LoadSubscription
0x180017ff5  mov     r13, [rsp+1410h+pv]
0x180017ffa  test    eax, eax
0x180017ffc  js      short loc_180018035
0x180017ffe  mov     r8, [r13+0D0h]
0x180018005  mov     edx, 104h; unsigned __int64
0x18001800a  add     r8, 8
0x18001800e  mov     rcx, rbx; unsigned __int16 *
0x180018011  add     r8, r13; unsigned __int16 *
0x180018014  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018019  mov     rdx, [r14]
0x18001801c  lea     rcx, [r13+8]
0x180018020  call    CopyToOOEBuf
0x180018025  mov     r11, [r14]
0x180018028  mov     dword ptr [r11+1580h], 10h
0x180018033  jmp     short loc_18001807F
0x180018035  mov     rcx, [r14]
0x180018038  add     rcx, 74h ; 't'
0x18001803c  call    CreateCookie
0x180018041  mov     r8, r12; unsigned __int16 *
0x180018044  mov     edx, 104h; unsigned __int64
0x180018049  mov     rcx, rbx; unsigned __int16 *
0x18001804c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018051  mov     rcx, [r14]
0x180018054  mov     r8, r12; unsigned __int16 *
0x180018057  add     rcx, 22Ch; unsigned __int16 *
0x18001805e  mov     edx, 825h; unsigned __int64
0x180018063  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018068  mov     rcx, [r14]
0x18001806b  mov     r8, r12; unsigned __int16 *
0x18001806e  add     rcx, 1276h; unsigned __int16 *
0x180018075  mov     edx, 105h; unsigned __int64
0x18001807a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001807f  mov     rcx, [r14]
0x180018082  lea     rdi, [r15+1490h]
0x180018089  xor     edx, edx; pUnkOuter
0x18001808b  mov     [rsp+1410h+ppv], rdi; ppv
0x180018090  add     rcx, 98h; rclsid
0x180018097  lea     r9, IID_IUnknown; riid
0x18001809e  lea     r8d, [rdx+1]; dwClsContext
0x1800180a2  call    cs:__imp_CoCreateInstance
0x1800180a8  mov     esi, eax
0x1800180aa  test    eax, eax
0x1800180ac  js      loc_180018273
0x1800180b2  mov     rcx, [rdi]
0x1800180b5  lea     r8, [rsp+1410h+pv]
0x1800180ba  mov     [rsp+1410h+pv], 0
0x1800180c3  lea     rdx, IID_ISubscriptionAgentShellExt
0x1800180ca  mov     rax, [rcx]
0x1800180cd  mov     rax, [rax]
0x1800180d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180d5  mov     esi, eax
0x1800180d7  test    eax, eax
0x1800180d9  js      loc_180018273
0x1800180df  mov     r8, [r14]
0x1800180e2  lea     rcx, [rbp+1310h+var_1090]; unsigned __int16 *
0x1800180e9  add     r8, 22Ch; unsigned __int16 *
0x1800180f0  mov     edx, 825h; unsigned __int64
0x1800180f5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800180fa  mov     r8, [r14]
0x1800180fd  lea     rcx, [rbp+1310h+var_12A0]; unsigned __int16 *
0x180018101  add     r8, 1276h; unsigned __int16 *
0x180018108  mov     edx, 105h; unsigned __int64
0x18001810d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018112  mov     rcx, [rsp+1410h+pv]
0x180018117  lea     r9, [rbp+1310h+var_12A0]
0x18001811b  mov     rdx, [r14]
0x18001811e  lea     r8, [rbp+1310h+var_1090]
0x180018125  add     rdx, 74h ; 't'
0x180018129  mov     dword ptr [rsp+1410h+ppv], 0FFFFFFFFh
0x180018131  mov     rax, [rcx]
0x180018134  mov     rax, [rax+18h]
0x180018138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001813d  mov     rcx, [rsp+1410h+pv]
0x180018142  mov     esi, eax
0x180018144  mov     rax, [rcx]
0x180018147  mov     rax, [rax+10h]
0x18001814b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018150  test    esi, esi
0x180018152  js      loc_180018273
0x180018158  mov     edi, 60h ; '`'
0x18001815d  lea     rcx, [rsp+1410h+var_13C0]; void *
0x180018162  mov     r8d, edi; Size
0x180018165  xor     edx, edx; Val
0x180018167  call    memset_0
0x18001816c  xor     edx, edx; Val
0x18001816e  lea     r8d, [rdi-10h]; Size
0x180018172  lea     rcx, [rbp+1310h+var_12F0]; void *
0x180018176  call    memset_0
0x18001817b  mov     rax, [rsp+1410h+var_13D0]
0x180018180  lea     rcx, [rbp+1310h+constPropSheetPagePointer]; void *
0x180018184  mov     [rsp+1410h+var_13B8], rax
0x180018189  xor     edx, edx; Val
0x18001818b  lea     rax, [rbp+1310h+var_12F0]
0x18001818f  mov     [rsp+1410h+var_13C0], edi
0x180018193  xor     edi, edi
0x180018195  mov     [rsp+1410h+var_13A0], rbx
0x18001819a  mov     rbx, cs:g_hinstMUI
0x1800181a1  mov     [rsp+1410h+var_13BC], 2000001h
0x1800181a9  mov     [rsp+1410h+var_13B0], rbx
0x1800181ae  lea     r8d, [rdi+68h]; Size
0x1800181b2  mov     [rsp+1410h+var_1398], edi
0x1800181b6  mov     [rbp+1310h+var_1390], edi
0x1800181b9  mov     [rbp+1310h+var_1388], rax
0x1800181bd  call    memset_0
0x1800181c2  lea     rax, [r15-10h]
0x1800181c6  mov     qword ptr [rbp+1310h+constPropSheetPagePointer.dwSize], 68h ; 'h'
0x1800181ce  mov     [rbp+1310h+constPropSheetPagePointer.lParam], rax
0x1800181d2  lea     rcx, [rbp+1310h+constPropSheetPagePointer]; constPropSheetPagePointer
0x1800181d6  lea     rax, ?SummaryPropDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; SummaryPropDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800181dd  mov     [rbp+1310h+constPropSheetPagePointer.hInstance], rbx
0x1800181e1  mov     [rbp+1310h+constPropSheetPagePointer.pfnDlgProc], rax
0x1800181e5  mov     qword ptr [rbp+1310h+constPropSheetPagePointer.10h], 178Ah
0x1800181ed  call    CreatePropertySheetPageW
0x1800181f2  lea     rcx, [rbp+1310h+var_12F0]
0x1800181f6  mov     [rcx+rdi*8], rax
0x1800181fa  inc     [rsp+1410h+var_1398]
0x1800181fe  cmp     [rbp+1310h+var_12F0], rdi
0x180018202  jz      short loc_180018273
0x180018204  mov     rax, [r14]
0x180018207  test    byte ptr [rax+1580h], 10h
0x18001820e  jz      short loc_180018232
0x180018210  lea     rcx, [r15-10h]
0x180018214  mov     rax, [rcx]
0x180018217  lea     r8, [rsp+1410h+var_13C0]
0x18001821c  lea     rdx, ?_AddOnePropSheetPage@@YAHPEAU_PSP@@_J@Z; _AddOnePropSheetPage(_PSP *,__int64)
0x180018223  mov     rax, [rax+18h]
0x180018227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001822c  mov     esi, eax
0x18001822e  test    eax, eax
0x180018230  js      short loc_180018273
0x180018232  lea     rcx, [rsp+1410h+var_13C0]
0x180018237  call    PropertySheet
0x18001823c  test    rax, rax
0x18001823f  jns     short loc_180018248
0x180018241  mov     esi, 80004005h
0x180018246  jmp     short loc_180018273
0x180018248  lea     rdx, [rsp+1410h+var_13D8]
0x18001824d  mov     rcx, r12
0x180018250  call    LoadSubscription
0x180018255  mov     esi, eax
0x180018257  test    eax, eax
0x180018259  js      short loc_180018273
0x18001825b  mov     rcx, [r15+18h]; pv
0x18001825f  test    rcx, rcx
0x180018262  jz      short loc_18001826A
0x180018264  call    cs:__imp_CoTaskMemFree
0x18001826a  mov     rax, [rsp+1410h+var_13D8]
0x18001826f  mov     [r15+18h], rax
0x180018273  test    r13, r13
0x180018276  jz      short loc_180018281
0x180018278  mov     rcx, r13; pv
0x18001827b  call    cs:__imp_CoTaskMemFree
0x180018281  mov     eax, esi
0x180018283  mov     rcx, [rbp+1310h+var_40]
0x18001828a  xor     rcx, rsp; StackCookie
0x18001828d  call    __security_check_cookie
0x180018292  mov     rbx, [rsp+1410h+arg_18]
0x18001829a  add     rsp, 13E0h
0x1800182a1  pop     r15
0x1800182a3  pop     r14
0x1800182a5  pop     r13
0x1800182a7  pop     r12
0x1800182a9  pop     rdi
0x1800182aa  pop     rsi
0x1800182ab  pop     rbp
0x1800182ac  retn
```
