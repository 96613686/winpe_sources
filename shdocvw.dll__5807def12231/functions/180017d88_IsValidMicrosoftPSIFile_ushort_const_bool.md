# IsValidMicrosoftPSIFile(ushort const *,bool &)

- ea: `0x180017d88`
- end: `0x180017f30`
- name: `?IsValidMicrosoftPSIFile@@YA_NPEBGAEA_N@Z`
- size: `424`
- prototype: `bool __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005914`

## callees

- `0x1800058c0`
- `0x1800066d0`
- `0x180008320`
- `0x180009018`
- `0x180012224`
- `0x180017c98`
- `0x180017d88`
- `0x1800237e8`
- `0x180027c30`
- `0x180027c84`

## string_xrefs

- `0x180017ed0`: `StoreInstaller.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
char __fastcall IsValidMicrosoftPSIFile(const unsigned __int16 *a1, bool *a2)
{
  const wchar_t *v5; // rcx
  int v6; // [rsp+20h] [rbp-11E8h] BYREF
  _BYTE v7[36]; // [rsp+24h] [rbp-11E4h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-11C0h]
  int v9; // [rsp+50h] [rbp-11B8h]
  __int16 *v10; // [rsp+58h] [rbp-11B0h]
  int v11; // [rsp+60h] [rbp-11A8h]
  wchar_t *S1[2]; // [rsp+80h] [rbp-1188h] BYREF
  __int64 v13; // [rsp+90h] [rbp-1178h]
  unsigned __int64 v14; // [rsp+98h] [rbp-1170h]
  __int16 v15; // [rsp+A0h] [rbp-1168h] BYREF
  _BYTE v16[254]; // [rsp+A2h] [rbp-1166h] BYREF
  __int16 v17; // [rsp+1A0h] [rbp-1068h] BYREF
  _BYTE v18[4174]; // [rsp+1A2h] [rbp-1066h] BYREF

  *a2 = 0;
  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  v17 = 0;
  memset_0(v18, 0, 0x1046u);
  v6 = 88;
  memset_0(v7, 0, 0x54u);
  v10 = &v17;
  v11 = 2084;
  String1 = (wchar_t *)&v15;
  v9 = 128;
  if ( GetPublisherAndUrl(a1, 1, (struct SIGNATURE_INFO *)&v6) >= 0 && wcscmp_0(String1, L"Microsoft Corporation") )
    return 1;
  *(_OWORD *)S1 = 0;
  v13 = 0;
  v14 = 7;
  LOWORD(S1[0]) = 0;
  if ( !(unsigned __int8)GetOriginalFileName(a1, S1) )
    goto LABEL_10;
  v5 = (const wchar_t *)S1;
  if ( v14 > 7 )
    v5 = S1[0];
  if ( v13 == 18 && !wmemcmp(v5, L"StoreInstaller.exe", 0x12u) )
  {
LABEL_10:
    *a2 = IsValidMicrosoftCertificate(a1);
    std::wstring::_Tidy_deallocate(S1);
    return 1;
  }
  else
  {
    std::wstring::_Tidy_deallocate(S1);
    return 1;
  }
}

```

## disassembly

```asm
0x180017d88  mov     [rsp+arg_10], rbx
0x180017d8d  push    rdi
0x180017d8e  mov     eax, 1200h
0x180017d93  call    _alloca_probe
0x180017d98  sub     rsp, rax
0x180017d9b  mov     rax, cs:__security_cookie
0x180017da2  xor     rax, rsp
0x180017da5  mov     [rsp+1208h+var_18], rax
0x180017dad  mov     rdi, rdx
0x180017db0  mov     rbx, rcx
0x180017db3  mov     byte ptr [rdx], 0
0x180017db6  xor     eax, eax
0x180017db8  mov     [rsp+1208h+var_1168], ax
0x180017dc0  xor     edx, edx; Val
0x180017dc2  mov     r8d, 0FEh; Size
0x180017dc8  lea     rcx, [rsp+1208h+var_1166]; void *
0x180017dd0  call    memset_0
0x180017dd5  xor     eax, eax
0x180017dd7  mov     [rsp+1208h+var_1068], ax
0x180017ddf  xor     edx, edx; Val
0x180017de1  mov     r8d, 1046h; Size
0x180017de7  lea     rcx, [rsp+1208h+var_1066]; void *
0x180017def  call    memset_0
0x180017df4  mov     [rsp+1208h+var_11E8], 58h ; 'X'
0x180017dfc  xor     edx, edx; Val
0x180017dfe  lea     r8d, [rdx+54h]; Size
0x180017e02  lea     rcx, [rsp+1208h+var_11E4]; void *
0x180017e07  call    memset_0
0x180017e0c  lea     rax, [rsp+1208h+var_1068]
0x180017e14  mov     [rsp+1208h+var_11B0], rax
0x180017e19  mov     [rsp+1208h+var_11A8], 824h
0x180017e21  lea     rax, [rsp+1208h+var_1168]
0x180017e29  mov     [rsp+1208h+String1], rax
0x180017e2e  mov     [rsp+1208h+var_11B8], 80h
0x180017e36  lea     r8, [rsp+1208h+var_11E8]; struct SIGNATURE_INFO *
0x180017e3b  mov     dl, 1; bool
0x180017e3d  mov     rcx, rbx; unsigned __int16 *
0x180017e40  call    ?GetPublisherAndUrl@@YAJPEBG_NPEAUSIGNATURE_INFO@@@Z; GetPublisherAndUrl(ushort const *,bool,SIGNATURE_INFO *)
0x180017e45  test    eax, eax
0x180017e47  js      short loc_180017E65
0x180017e49  lea     rdx, aMicrosoftCorpo; "Microsoft Corporation"
0x180017e50  mov     rcx, [rsp+1208h+String1]; String1
0x180017e55  call    wcscmp_0
0x180017e5a  test    eax, eax
0x180017e5c  jz      short loc_180017E65
0x180017e5e  mov     al, 1
0x180017e60  jmp     loc_180017F0E
0x180017e65  xorps   xmm0, xmm0
0x180017e68  movups  xmmword ptr [rsp+1208h+S1], xmm0
0x180017e70  mov     [rsp+1208h+var_1178], 0
0x180017e7c  mov     [rsp+1208h+var_1170], 7
0x180017e88  xor     eax, eax
0x180017e8a  mov     word ptr [rsp+1208h+S1], ax
0x180017e92  lea     rdx, [rsp+1208h+S1]
0x180017e9a  mov     rcx, rbx
0x180017e9d  call    ?GetOriginalFileName@@YA_NPEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetOriginalFileName(ushort const *,std::wstring *)
0x180017ea2  test    al, al
0x180017ea4  jz      short loc_180017EF1
0x180017ea6  lea     rcx, [rsp+1208h+S1]
0x180017eae  cmp     [rsp+1208h+var_1170], 7
0x180017eb7  cmova   rcx, [rsp+1208h+S1]; S1
0x180017ec0  mov     r8d, 12h; N
0x180017ec6  cmp     [rsp+1208h+var_1178], r8
0x180017ece  jnz     short loc_180017EE0
0x180017ed0  lea     rdx, aStoreinstaller; "StoreInstaller.exe"
0x180017ed7  call    wmemcmp
0x180017edc  test    eax, eax
0x180017ede  jz      short loc_180017EF1
0x180017ee0  lea     rcx, [rsp+1208h+S1]
0x180017ee8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017eed  mov     al, 1
0x180017eef  jmp     short loc_180017F0E
0x180017ef1  mov     rcx, rbx; unsigned __int16 *
0x180017ef4  call    ?IsValidMicrosoftCertificate@@YA_NPEBG@Z; IsValidMicrosoftCertificate(ushort const *)
0x180017ef9  mov     [rdi], al
0x180017efb  lea     rcx, [rsp+1208h+S1]
0x180017f03  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017f08  mov     al, 1
0x180017f0a  jmp     short loc_180017F0E
0x180017f0c  xor     al, al
0x180017f0e  mov     rcx, [rsp+1208h+var_18]
0x180017f16  xor     rcx, rsp; StackCookie
0x180017f19  call    __security_check_cookie
0x180017f1e  mov     rbx, [rsp+1208h+arg_10]
0x180017f26  add     rsp, 1200h
0x180017f2d  pop     rdi
0x180017f2e  retn
```
