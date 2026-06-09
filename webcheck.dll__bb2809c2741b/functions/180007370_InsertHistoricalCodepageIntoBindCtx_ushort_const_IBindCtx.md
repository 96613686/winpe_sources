# InsertHistoricalCodepageIntoBindCtx(ushort const *,IBindCtx *)

- ea: `0x180007370`
- end: `0x1800074c9`
- name: `?InsertHistoricalCodepageIntoBindCtx@@YAJPEBGPEAUIBindCtx@@@Z`
- size: `345`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IBindCtx *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800062d0`

## callees

- `0x180003950`
- `0x180007370`
- `0x18000c1d0`
- `0x180029280`
- `0x180029310`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000743b`
- `ole32!CoCreateInstance` at `0x18000743b`

## pseudocode

```c
__int64 __fastcall InsertHistoricalCodepageIntoBindCtx(const unsigned __int16 *a1, struct IBindCtx *a2)
{
  unsigned int v3; // r9d
  HRESULT v4; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  tagPROPVARIANT v7; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v8[2088]; // [rsp+50h] [rbp-B0h] BYREF

  if ( a1 && a2 )
  {
    memset(&v7, 0, sizeof(v7));
    v7.vt = 19;
    StringCchCopyW(v8, 0x824u, a1);
    v4 = IntSiteHelper(v8, &stru_18002DC40, &v7, v3, 0);
    if ( v4 >= 0 )
    {
      if ( v7.lVal )
      {
        ppv = 0;
        v4 = CoCreateInstance(&CLSID_HTMLLoadOptions, 0, 1u, &IID_IHtmlLoadOptions, &ppv);
        if ( v4 >= 0 )
        {
          if ( ppv )
          {
            v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, ULONG *, __int64))(*(_QWORD *)ppv + 32LL))(
                   ppv,
                   0,
                   &v7.ulVal,
                   4);
            if ( v4 >= 0 )
              ((void (__fastcall *)(struct IBindCtx *, const wchar_t *, LPVOID))a2->lpVtbl->RegisterObjectParam)(
                a2,
                L"__HTMLLOADOPTIONS",
                ppv);
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007370  mov     [rsp-8+arg_10], rbx
0x180007375  mov     [rsp-8+arg_18], rdi
0x18000737a  push    rbp
0x18000737b  lea     rbp, [rsp-0FB0h]
0x180007383  mov     eax, 10B0h
0x180007388  call    _alloca_probe
0x18000738d  sub     rsp, rax
0x180007390  mov     rax, cs:__security_cookie
0x180007397  xor     rax, rsp
0x18000739a  mov     [rbp+0FB0h+var_10], rax
0x1800073a1  mov     rdi, rdx
0x1800073a4  test    rcx, rcx
0x1800073a7  jz      loc_18000749E
0x1800073ad  test    rdx, rdx
0x1800073b0  jz      loc_18000749E
0x1800073b6  xor     eax, eax
0x1800073b8  mov     r8, rcx; unsigned __int16 *
0x1800073bb  mov     qword ptr [rsp+10B0h+var_1078+10h], rax
0x1800073c0  lea     rcx, [rsp+10B0h+var_1060]; unsigned __int16 *
0x1800073c5  mov     eax, 13h
0x1800073ca  xorps   xmm0, xmm0
0x1800073cd  movups  xmmword ptr [rsp+10B0h+var_1078], xmm0
0x1800073d2  mov     edx, 824h; unsigned __int64
0x1800073d7  mov     word ptr [rsp+10B0h+var_1078], ax
0x1800073dc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800073e1  lea     r8, [rsp+10B0h+var_1078]; struct tagPROPVARIANT *
0x1800073e6  mov     dword ptr [rsp+10B0h+ppv], 0; int
0x1800073ee  lea     rdx, stru_18002DC40; struct tagPROPSPEC *
0x1800073f5  lea     rcx, [rsp+10B0h+var_1060]; unsigned __int16 *
0x1800073fa  call    ?IntSiteHelper@@YAJPEBGPEBUtagPROPSPEC@@PEAUtagPROPVARIANT@@IH@Z; IntSiteHelper(ushort const *,tagPROPSPEC const *,tagPROPVARIANT *,uint,int)
0x1800073ff  mov     ebx, eax
0x180007401  test    eax, eax
0x180007403  js      loc_1800074A3
0x180007409  cmp     dword ptr [rsp+10B0h+var_1078+8], 0
0x18000740e  jz      loc_1800074A3
0x180007414  xor     edx, edx; pUnkOuter
0x180007416  mov     [rsp+10B0h+var_1080], 0
0x18000741f  lea     rax, [rsp+10B0h+var_1080]
0x180007424  lea     r9, IID_IHtmlLoadOptions; riid
0x18000742b  mov     [rsp+10B0h+ppv], rax; ppv
0x180007430  lea     rcx, CLSID_HTMLLoadOptions; rclsid
0x180007437  lea     r8d, [rdx+1]; dwClsContext
0x18000743b  call    cs:__imp_CoCreateInstance
0x180007441  mov     ebx, eax
0x180007443  test    eax, eax
0x180007445  js      short loc_1800074A3
0x180007447  mov     rcx, [rsp+10B0h+var_1080]
0x18000744c  test    rcx, rcx
0x18000744f  jz      short loc_1800074A3
0x180007451  mov     rax, [rcx]
0x180007454  lea     r8, [rsp+10B0h+var_1078+8]
0x180007459  mov     r9d, 4
0x18000745f  xor     edx, edx
0x180007461  mov     rax, [rax+20h]
0x180007465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000746a  mov     ebx, eax
0x18000746c  test    eax, eax
0x18000746e  js      short loc_18000748B
0x180007470  mov     rax, [rdi]
0x180007473  lea     rdx, aHtmlloadoption; "__HTMLLOADOPTIONS"
0x18000747a  mov     r8, [rsp+10B0h+var_1080]
0x18000747f  mov     rcx, rdi
0x180007482  mov     rax, [rax+48h]
0x180007486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000748b  mov     rcx, [rsp+10B0h+var_1080]
0x180007490  mov     rax, [rcx]
0x180007493  mov     rax, [rax+10h]
0x180007497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000749c  jmp     short loc_1800074A3
0x18000749e  mov     ebx, 80070057h
0x1800074a3  mov     eax, ebx
0x1800074a5  mov     rcx, [rbp+0FB0h+var_10]
0x1800074ac  xor     rcx, rsp; StackCookie
0x1800074af  call    __security_check_cookie
0x1800074b4  lea     r11, [rsp+10B0h+var_s0]
0x1800074bc  mov     rbx, [r11+20h]
0x1800074c0  mov     rdi, [r11+28h]
0x1800074c4  mov     rsp, r11
0x1800074c7  pop     rbp
0x1800074c8  retn
```
