# RemoveWiaHandlerFromWindowsAutoPlay(_GUID const *)

- ea: `0x180030720`
- end: `0x180030978`
- name: `?RemoveWiaHandlerFromWindowsAutoPlay@@YAXPEBU_GUID@@@Z`
- size: `600`
- prototype: `void __fastcall(const struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180030294`

## callees

- `0x18000f4fc`
- `0x180011638`
- `0x1800119c8`
- `0x180011a94`
- `0x180011ad0`
- `0x1800136a4`
- `0x180030720`
- `0x180033cc0`
- `0x18003c4d8`
- `0x1800456dc`

## import_xrefs

- `ole32!StringFromGUID2` at `0x1800307e9`
- `ole32!StringFromGUID2` at `0x1800307e9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800308f1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800308f1`

## string_xrefs

- `0x180030878`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\AutoplayHandlers\EventHandlers\WPD\Compat\WiaDeviceConnected`

## pseudocode

```c
void __fastcall RemoveWiaHandlerFromWindowsAutoPlay(const struct _GUID *a1)
{
  __int64 v1; // rcx
  const unsigned __int64 *v2; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v3; // [rsp+38h] [rbp-C8h] BYREF
  __int16 *v4; // [rsp+138h] [rbp+38h]
  __int64 v5; // [rsp+140h] [rbp+40h]
  __int64 v6; // [rsp+148h] [rbp+48h]
  char v7; // [rsp+150h] [rbp+50h]
  const unsigned __int64 *v8; // [rsp+160h] [rbp+60h] BYREF
  __int16 v9; // [rsp+168h] [rbp+68h] BYREF
  __int16 *v10; // [rsp+268h] [rbp+168h]
  __int64 v11; // [rsp+270h] [rbp+170h]
  __int64 v12; // [rsp+278h] [rbp+178h]
  char v13; // [rsp+280h] [rbp+180h]
  const unsigned __int64 *v14; // [rsp+290h] [rbp+190h] BYREF
  __int16 v15; // [rsp+298h] [rbp+198h] BYREF
  __int16 *v16; // [rsp+398h] [rbp+298h]
  __int64 v17; // [rsp+3A0h] [rbp+2A0h]
  __int64 v18; // [rsp+3A8h] [rbp+2A8h]
  char v19; // [rsp+3B0h] [rbp+2B0h]
  _QWORD v20[38]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _BYTE v21[312]; // [rsp+4F0h] [rbp+3F0h] BYREF
  HKEY hKey; // [rsp+628h] [rbp+528h]
  OLECHAR sz[40]; // [rsp+650h] [rbp+550h] BYREF

  v13 = 0;
  v11 = 128;
  v10 = &v9;
  v8 = &CSimpleStringBase<unsigned short>::`vftable';
  v9 = 0;
  v12 = 16;
  v4 = &v3;
  v3 = 0;
  v16 = &v15;
  v2 = &CSimpleStringBase<unsigned short>::`vftable';
  v5 = 128;
  v6 = 16;
  v7 = 0;
  v14 = &CSimpleStringBase<unsigned short>::`vftable';
  v17 = 128;
  v18 = 16;
  v19 = 0;
  v15 = 0;
  if ( a1 )
  {
    StringFromGUID2(a1, sz, 40);
    CSimpleStringBase<unsigned short>::Format(
      &v8,
      L"%wsWIA_%ws",
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AutoplayHandlers\\Handlers\\",
      sz);
    CSimpleStringBase<unsigned short>::Format(&v2, L"WIA_%ws", sz);
    if ( CSimpleStringBase<unsigned short>::Length(&v8) )
    {
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v20, v10);
      CSimpleReg::Delete(v1, v20);
      v20[0] = &CSimpleStringBase<unsigned short>::`vftable';
      CSimpleStringBase<unsigned short>::DeleteStorage(v20);
    }
    if ( CSimpleStringBase<unsigned short>::Length(&v2) )
    {
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(
        v20,
        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AutoplayHandlers\\EventHandlers\\WPD\\Compat\\WiaDeviceConnected");
      CSimpleReg::CSimpleReg((CSimpleReg *)v21, 983103);
      v20[0] = &CSimpleStringBase<unsigned short>::`vftable';
      CSimpleStringBase<unsigned short>::DeleteStorage(v20);
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v20, v4);
      if ( CSimpleReg::OK((CSimpleReg *)v21) )
        RegDeleteValueW(hKey, (LPCWSTR)v20[33]);
      v20[0] = &CSimpleStringBase<unsigned short>::`vftable';
      CSimpleStringBase<unsigned short>::DeleteStorage(v20);
      CSimpleReg::~CSimpleReg((CSimpleReg *)v21);
    }
    v14 = &CSimpleStringBase<unsigned short>::`vftable';
  }
  CSimpleStringBase<unsigned short>::DeleteStorage(&v14);
  v17 = 0;
  v2 = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(&v2);
  v8 = &CSimpleStringBase<unsigned short>::`vftable';
  v5 = 0;
  CSimpleStringBase<unsigned short>::DeleteStorage(&v8);
}

```

## disassembly

```asm
0x180030720  mov     [rsp-8+arg_8], rdi
0x180030725  push    rbp
0x180030726  lea     rbp, [rsp-5B0h]
0x18003072e  sub     rsp, 6B0h
0x180030735  mov     rax, cs:__security_cookie
0x18003073c  xor     rax, rsp
0x18003073f  mov     [rbp+5B0h+var_10], rax
0x180030746  mov     r8d, 80h
0x18003074c  mov     [rbp+5B0h+var_430], 0
0x180030753  lea     rax, [rbp+5B0h+var_548]
0x180030757  mov     [rbp+5B0h+var_440], r8
0x18003075e  mov     [rbp+5B0h+var_448], rax
0x180030765  lea     rdi, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18003076c  xor     eax, eax
0x18003076e  mov     [rbp+5B0h+var_550], rdi
0x180030772  mov     [rbp+5B0h+var_548], ax
0x180030776  lea     edx, [r8-70h]
0x18003077a  lea     rax, [rsp+6B0h+var_678]
0x18003077f  mov     [rbp+5B0h+var_438], rdx
0x180030786  mov     [rbp+5B0h+var_578], rax
0x18003078a  xor     eax, eax
0x18003078c  mov     [rsp+6B0h+var_678], ax
0x180030791  lea     rax, [rbp+5B0h+var_418]
0x180030798  mov     [rbp+5B0h+var_318], rax
0x18003079f  xor     eax, eax
0x1800307a1  mov     [rsp+6B0h+var_680], rdi
0x1800307a6  mov     [rbp+5B0h+var_570], r8
0x1800307aa  mov     [rbp+5B0h+var_568], rdx
0x1800307ae  mov     [rbp+5B0h+var_560], 0
0x1800307b2  mov     [rbp+5B0h+var_420], rdi
0x1800307b9  mov     [rbp+5B0h+var_310], r8
0x1800307c0  mov     [rbp+5B0h+var_308], rdx
0x1800307c7  mov     [rbp+5B0h+var_300], 0
0x1800307ce  mov     [rbp+5B0h+var_418], ax
0x1800307d5  test    rcx, rcx
0x1800307d8  jz      loc_18003091D
0x1800307de  lea     r8d, [rdx+18h]; cchMax
0x1800307e2  lea     rdx, [rbp+5B0h+sz]; lpsz
0x1800307e9  call    cs:__imp_StringFromGUID2
0x1800307ef  lea     r9, [rbp+5B0h+sz]
0x1800307f6  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800307fd  lea     rdx, aWswiaWs; "%wsWIA_%ws"
0x180030804  lea     rcx, [rbp+5B0h+var_550]
0x180030808  call    ?Format@?$CSimpleStringBase@G@@QEAAAEAV1@PEBGZZ; CSimpleStringBase<ushort>::Format(ushort const *,...)
0x18003080d  lea     r8, [rbp+5B0h+sz]
0x180030814  lea     rdx, aWiaWs; "WIA_%ws"
0x18003081b  lea     rcx, [rsp+6B0h+var_680]
0x180030820  call    ?Format@?$CSimpleStringBase@G@@QEAAAEAV1@PEBGZZ; CSimpleStringBase<ushort>::Format(ushort const *,...)
0x180030825  lea     rcx, [rbp+5B0h+var_550]
0x180030829  call    ?Length@?$CSimpleStringBase@G@@QEBA_KXZ; CSimpleStringBase<ushort>::Length(void)
0x18003082e  test    rax, rax
0x180030831  jz      short loc_180030865
0x180030833  mov     rdx, [rbp+5B0h+var_448]
0x18003083a  lea     rcx, [rbp+5B0h+var_2F0]
0x180030841  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180030846  lea     rdx, [rbp+5B0h+var_2F0]
0x18003084d  call    ?Delete@CSimpleReg@@SA_NPEAUHKEY__@@AEBV?$CSimpleStringBase@G@@@Z; CSimpleReg::Delete(HKEY__ *,CSimpleStringBase<ushort> const &)
0x180030852  lea     rcx, [rbp+5B0h+var_2F0]
0x180030859  mov     [rbp+5B0h+var_2F0], rdi
0x180030860  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180030865  lea     rcx, [rsp+6B0h+var_680]
0x18003086a  call    ?Length@?$CSimpleStringBase@G@@QEBA_KXZ; CSimpleStringBase<ushort>::Length(void)
0x18003086f  test    rax, rax
0x180030872  jz      loc_180030916
0x180030878  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003087f  lea     rcx, [rbp+5B0h+var_2F0]
0x180030886  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18003088b  xor     r9d, r9d
0x18003088e  mov     [rsp+6B0h+var_690], 0F003Fh; int
0x180030896  lea     r8, [rbp+5B0h+var_2F0]
0x18003089d  mov     rdx, 0FFFFFFFF80000002h
0x1800308a4  lea     rcx, [rbp+5B0h+var_1C0]; this
0x1800308ab  call    ??0CSimpleReg@@QEAA@PEAUHKEY__@@AEBV?$CSimpleStringBase@G@@_NKPEAU_SECURITY_ATTRIBUTES@@@Z; CSimpleReg::CSimpleReg(HKEY__ *,CSimpleStringBase<ushort> const &,bool,ulong,_SECURITY_ATTRIBUTES *)
0x1800308b0  lea     rcx, [rbp+5B0h+var_2F0]
0x1800308b7  mov     [rbp+5B0h+var_2F0], rdi
0x1800308be  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800308c3  mov     rdx, [rbp+5B0h+var_578]
0x1800308c7  lea     rcx, [rbp+5B0h+var_2F0]
0x1800308ce  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800308d3  lea     rcx, [rbp+5B0h+var_1C0]; this
0x1800308da  call    ?OK@CSimpleReg@@QEBA_NXZ; CSimpleReg::OK(void)
0x1800308df  test    al, al
0x1800308e1  jz      short loc_1800308F7
0x1800308e3  mov     rdx, [rbp+5B0h+lpValueName]; lpValueName
0x1800308ea  mov     rcx, [rbp+5B0h+hKey]; hKey
0x1800308f1  call    cs:__imp_RegDeleteValueW
0x1800308f7  lea     rcx, [rbp+5B0h+var_2F0]
0x1800308fe  mov     [rbp+5B0h+var_2F0], rdi
0x180030905  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18003090a  lea     rcx, [rbp+5B0h+var_1C0]; this
0x180030911  call    ??1CSimpleReg@@UEAA@XZ; CSimpleReg::~CSimpleReg(void)
0x180030916  mov     [rbp+5B0h+var_420], rdi
0x18003091d  lea     rcx, [rbp+5B0h+var_420]
0x180030924  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180030929  lea     rcx, [rsp+6B0h+var_680]
0x18003092e  mov     [rbp+5B0h+var_310], 0
0x180030939  mov     [rsp+6B0h+var_680], rdi
0x18003093e  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180030943  lea     rcx, [rbp+5B0h+var_550]
0x180030947  mov     [rbp+5B0h+var_550], rdi
0x18003094b  mov     [rbp+5B0h+var_570], 0
0x180030953  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180030958  mov     rcx, [rbp+5B0h+var_10]
0x18003095f  xor     rcx, rsp; StackCookie
0x180030962  call    __security_check_cookie
0x180030967  mov     rdi, [rsp+6B0h+arg_8]
0x18003096f  add     rsp, 6B0h
0x180030976  pop     rbp
0x180030977  retn
```
