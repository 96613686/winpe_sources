# CSpp::_UpdateClientVolumes(_GUID,ulong,ushort const * const *,ushort const * const *)

- ea: `0x18001f31c`
- end: `0x18001f70b`
- name: `?_UpdateClientVolumes@CSpp@@AEAAJU_GUID@@KPEBQEBG1@Z`
- size: `1007`
- prototype: `__int64 __fastcall(CSpp *this, struct _GUID *, unsigned int, const unsigned __int16 *const *, const unsigned __int16 *const *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001be74`

## callees

- `0x180004188`
- `0x18000702c`
- `0x180008654`
- `0x18000e040`
- `0x1800141ac`
- `0x18001f31c`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002ce10`
- `0x18003532c`
- `0x180035b00`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001f621`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001f621`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f6bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f6d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f6bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f6d2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f65d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f65d`

## string_xrefs

- `0x18001f392`: `CSpp::_UpdateClientVolumes`

## pseudocode

```c
__int64 __fastcall CSpp::_UpdateClientVolumes(
        CSpp *this,
        struct _GUID *a2,
        unsigned int a3,
        const unsigned __int16 *const *a4,
        const unsigned __int16 *const *a5)
{
  HKEY v8; // rbx
  const BYTE **v9; // rsi
  BOOL v10; // ecx
  __int16 v11; // ax
  int v12; // eax
  int v13; // edi
  bool v14; // sf
  int v15; // eax
  __int64 v16; // rdx
  unsigned int i; // r14d
  const unsigned __int16 *v18; // rdx
  __int64 v19; // r8
  const unsigned __int16 *v20; // rdx
  const unsigned __int16 *v21; // rdx
  __int64 v22; // r8
  bool v23; // zf
  LSTATUS v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  int v28; // [rsp+30h] [rbp-B1h] BYREF
  __int16 v29; // [rsp+34h] [rbp-ADh]
  __int16 v30; // [rsp+36h] [rbp-ABh]
  unsigned __int16 *v31[2]; // [rsp+68h] [rbp-79h] BYREF
  HKEY v32; // [rsp+78h] [rbp-69h] BYREF
  void *Block; // [rsp+80h] [rbp-61h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-59h] BYREF
  const unsigned __int16 *const *v35; // [rsp+90h] [rbp-51h]
  GUID *rguid; // [rsp+98h] [rbp-49h]
  OLECHAR sz; // [rsp+A0h] [rbp-41h] BYREF
  _BYTE v38[78]; // [rsp+A2h] [rbp-3Fh] BYREF

  v35 = a4;
  rguid = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v28, "CSpp::_UpdateClientVolumes", 3507, 1);
  v8 = 0;
  hKey = 0;
  v32 = 0;
  Block = 0;
  v31[0] = (unsigned __int16 *)&FileName;
  v9 = 0;
  v31[1] = 0;
  sz = 0;
  memset_0(v38, 0, 0x4Cu);
  v10 = a3 == 0;
  v11 = 3516;
  if ( v10 != (a4 == 0) || (v29 = 3516, v11 = 3517, v10 != (a5 == 0)) )
  {
    v13 = -2147024809;
    goto LABEL_32;
  }
  v28 = 0;
  v29 = 3517;
  v12 = CSpp::_CreateRegKey(this, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SPP", &v32);
  v8 = v32;
  v13 = v12;
  v28 = v12;
  v14 = v12 < 0;
  v11 = 3519;
  if ( v14 )
    goto LABEL_33;
  v29 = 3519;
  v13 = CSpp::_CreateRegKey(this, v32, L"Clients", &hKey);
  v28 = v13;
  v11 = 3520;
  if ( v13 < 0 )
    goto LABEL_33;
  v29 = 3520;
  v15 = CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::CreateInstance(&Block);
  v9 = (const BYTE **)Block;
  v13 = v15;
  v28 = v15;
  v14 = v15 < 0;
  v11 = 3522;
  if ( v14 )
    goto LABEL_33;
  for ( i = 0; ; ++i )
  {
    v29 = v11;
    if ( i >= a3 )
      break;
    v13 = CBsString::Set((CBsString *)v31, v35[i]);
    v28 = v13;
    v11 = 3525;
    if ( v13 < 0 )
      goto LABEL_33;
    v29 = 3525;
    v13 = SxHexEncode((struct CBsString *)v31, v18);
    v28 = v13;
    if ( v13 < 0 )
    {
      v11 = 3526;
      goto LABEL_33;
    }
    v29 = 3526;
    v19 = -1;
    do
      ++v19;
    while ( v31[0][v19] );
    v13 = ExtendCopy(v9, v31[0]);
    v28 = v13;
    v11 = 3528;
    if ( v13 < 0 )
      goto LABEL_33;
    v29 = 3528;
    v13 = ExtendCopy(v9, L":");
    v28 = v13;
    v11 = 3529;
    if ( v13 < 0 )
      goto LABEL_33;
    v20 = a5[i];
    v29 = 3529;
    v28 = CBsString::Set((CBsString *)v31, v20);
    v13 = v28;
    v11 = 3532;
    if ( v28 < 0 )
      goto LABEL_33;
    v29 = 3532;
    v13 = SxHexEncode((struct CBsString *)v31, v21);
    v28 = v13;
    v11 = 3533;
    if ( v13 < 0 )
      goto LABEL_33;
    v22 = -1;
    v29 = 3533;
    do
      ++v22;
    while ( v31[0][v22] );
    v13 = ExtendCopy(v9, v31[0]);
    v28 = v13;
    v11 = 3534;
    if ( v13 < 0 )
      goto LABEL_33;
  }
  v13 = CSxSimpleArray<unsigned short>::Append(v9, v16);
  v28 = v13;
  v11 = 3536;
  if ( v13 < 0 )
    goto LABEL_33;
  v29 = 3536;
  v23 = StringFromGUID2(rguid, &sz, 39) == 0;
  v11 = 3538;
  if ( v23 )
  {
    v13 = -2147418113;
LABEL_32:
    v28 = v13;
    goto LABEL_33;
  }
  v29 = 3538;
  v28 = 0;
  v24 = RegSetValueExW(hKey, &sz, 0, 7u, v9[1], 2 * *((_DWORD *)v9 + 4));
  v13 = v24;
  if ( v24 > 0 )
    v13 = (unsigned __int16)v24 | 0x80070000;
  v28 = v13;
  v11 = 3545;
  if ( v13 >= 0 )
  {
    v29 = 3545;
    goto LABEL_34;
  }
LABEL_33:
  v30 = v11;
LABEL_34:
  CBsString::_Release(v31);
  if ( v9 )
    CSxSimpleArray<_GUID>::Release(v9);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  if ( (unsigned __int64)v8 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(v8);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v28, v25, v26);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001f31c  mov     [rsp-8+arg_10], rbx
0x18001f321  push    rbp
0x18001f322  push    rsi
0x18001f323  push    rdi
0x18001f324  push    r12
0x18001f326  push    r13
0x18001f328  push    r14
0x18001f32a  push    r15
0x18001f32c  lea     rbp, [rsp-1Fh]
0x18001f331  sub     rsp, 100h
0x18001f338  mov     rax, cs:__security_cookie
0x18001f33f  xor     rax, rsp
0x18001f342  mov     [rbp+4Fh+var_40], rax
0x18001f346  mov     r12, [rbp+4Fh+arg_20]
0x18001f34a  mov     rdi, r9
0x18001f34d  mov     [rbp+4Fh+var_A0], r9
0x18001f351  mov     r13d, r8d
0x18001f354  mov     [rbp+4Fh+rguid], rdx
0x18001f358  mov     r14, rcx
0x18001f35b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f362  lea     rax, WPP_GLOBAL_Control
0x18001f369  cmp     rcx, rax
0x18001f36c  jz      short loc_18001F38C
0x18001f36e  test    dword ptr [rcx+1Ch], 20000000h
0x18001f375  jz      short loc_18001F38C
0x18001f377  mov     rcx, [rcx+10h]
0x18001f37b  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001f382  mov     edx, 27h ; '''
0x18001f387  call    WPP_SF_
0x18001f38c  mov     r9d, 1; unsigned __int16
0x18001f392  lea     rdx, aCsppUpdateclie; "CSpp::_UpdateClientVolumes"
0x18001f399  mov     r8d, 0DB3h; unsigned __int16
0x18001f39f  lea     rcx, [rsp+130h+var_100]; this
0x18001f3a4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001f3a9  xor     r15d, r15d
0x18001f3ac  lea     rax, FileName
0x18001f3b3  mov     ebx, r15d
0x18001f3b6  mov     [rbp+4Fh+hKey], r15
0x18001f3ba  xor     edx, edx; Val
0x18001f3bc  mov     [rbp+4Fh+var_B8], rbx
0x18001f3c0  lea     rcx, [rbp+4Fh+var_8E]; void *
0x18001f3c4  mov     [rbp+4Fh+Block], r15
0x18001f3c8  lea     r8d, [r15+4Ch]; Size
0x18001f3cc  mov     [rbp+4Fh+var_C8], rax
0x18001f3d0  mov     esi, r15d
0x18001f3d3  mov     [rbp+4Fh+var_C0], r15
0x18001f3d7  mov     [rbp+4Fh+sz], r15w
0x18001f3dc  call    memset_0
0x18001f3e1  test    r13d, r13d
0x18001f3e4  mov     eax, r15d
0x18001f3e7  mov     ecx, r15d
0x18001f3ea  setz    cl
0x18001f3ed  test    rdi, rdi
0x18001f3f0  setz    al
0x18001f3f3  cmp     ecx, eax
0x18001f3f5  mov     eax, 0DBCh
0x18001f3fa  jnz     loc_18001F68D
0x18001f400  mov     [rsp+130h+var_FC], ax
0x18001f405  test    r12, r12
0x18001f408  mov     eax, r15d
0x18001f40b  setz    al
0x18001f40e  cmp     ecx, eax
0x18001f410  mov     eax, 0DBDh
0x18001f415  jnz     loc_18001F68D
0x18001f41b  lea     r9, [rbp+4Fh+var_B8]; HKEY *
0x18001f41f  mov     [rsp+130h+var_100], r15d
0x18001f424  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001f42b  mov     [rsp+130h+var_FC], ax
0x18001f430  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18001f437  mov     rcx, r14; this
0x18001f43a  call    ?_CreateRegKey@CSpp@@AEAAJPEAUHKEY__@@PEBGPEAPEAU2@@Z; CSpp::_CreateRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18001f43f  mov     rbx, [rbp+4Fh+var_B8]
0x18001f443  mov     edi, eax
0x18001f445  mov     [rsp+130h+var_100], eax
0x18001f449  test    eax, eax
0x18001f44b  mov     eax, 0DBFh
0x18001f450  js      loc_18001F696
0x18001f456  lea     r9, [rbp+4Fh+hKey]; HKEY *
0x18001f45a  mov     [rsp+130h+var_FC], ax
0x18001f45f  lea     r8, aClients; "Clients"
0x18001f466  mov     rdx, rbx; HKEY
0x18001f469  mov     rcx, r14; this
0x18001f46c  call    ?_CreateRegKey@CSpp@@AEAAJPEAUHKEY__@@PEBGPEAPEAU2@@Z; CSpp::_CreateRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18001f471  mov     edi, eax
0x18001f473  mov     [rsp+130h+var_100], eax
0x18001f477  test    eax, eax
0x18001f479  mov     eax, 0DC0h
0x18001f47e  js      loc_18001F696
0x18001f484  lea     rcx, [rbp+4Fh+Block]
0x18001f488  mov     [rsp+130h+var_FC], ax
0x18001f48d  call    ?CreateInstance@?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@SAJPEAPEAV1@@Z; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::CreateInstance(CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)> * *)
0x18001f492  mov     rsi, [rbp+4Fh+Block]
0x18001f496  mov     edi, eax
0x18001f498  mov     [rsp+130h+var_100], eax
0x18001f49c  test    eax, eax
0x18001f49e  mov     eax, 0DC2h
0x18001f4a3  js      loc_18001F696
0x18001f4a9  mov     r14d, r15d
0x18001f4ac  mov     [rsp+130h+var_FC], ax
0x18001f4b1  cmp     r14d, r13d
0x18001f4b4  jnb     loc_18001F5F3
0x18001f4ba  mov     rax, [rbp+4Fh+var_A0]
0x18001f4be  lea     rcx, [rbp+4Fh+var_C8]; this
0x18001f4c2  mov     r15d, r14d
0x18001f4c5  mov     rdx, [rax+r15*8]; unsigned __int16 *
0x18001f4c9  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001f4ce  mov     edi, eax
0x18001f4d0  mov     [rsp+130h+var_100], eax
0x18001f4d4  test    eax, eax
0x18001f4d6  mov     eax, 0DC5h
0x18001f4db  js      loc_18001F696
0x18001f4e1  lea     rcx, [rbp+4Fh+var_C8]; struct CBsString *
0x18001f4e5  mov     [rsp+130h+var_FC], ax
0x18001f4ea  call    ?SxHexEncode@@YAJPEAVCBsString@@PEBG@Z; SxHexEncode(CBsString *,ushort const *)
0x18001f4ef  mov     edi, eax
0x18001f4f1  mov     [rsp+130h+var_100], eax
0x18001f4f5  xor     eax, eax
0x18001f4f7  test    edi, edi
0x18001f4f9  js      loc_18001F5E9
0x18001f4ff  mov     rdx, [rbp+4Fh+var_C8]
0x18001f503  mov     ecx, 0DC6h
0x18001f508  mov     [rsp+130h+var_FC], cx
0x18001f50d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f511  inc     r8
0x18001f514  cmp     [rdx+r8*2], ax
0x18001f519  jnz     short loc_18001F511
0x18001f51b  mov     rcx, rsi
0x18001f51e  call    ExtendCopy
0x18001f523  mov     edi, eax
0x18001f525  mov     [rsp+130h+var_100], eax
0x18001f529  test    eax, eax
0x18001f52b  mov     eax, 0DC8h
0x18001f530  js      loc_18001F696
0x18001f536  mov     r8d, 1
0x18001f53c  mov     [rsp+130h+var_FC], ax
0x18001f541  lea     rdx, asc_18003A5DC; ":"
0x18001f548  mov     rcx, rsi
0x18001f54b  call    ExtendCopy
0x18001f550  mov     edi, eax
0x18001f552  mov     [rsp+130h+var_100], eax
0x18001f556  test    eax, eax
0x18001f558  mov     eax, 0DC9h
0x18001f55d  js      loc_18001F696
0x18001f563  mov     rdx, [r12+r15*8]; unsigned __int16 *
0x18001f567  lea     rcx, [rbp+4Fh+var_C8]; this
0x18001f56b  mov     [rsp+130h+var_FC], ax
0x18001f570  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18001f575  xor     r15d, r15d
0x18001f578  mov     [rsp+130h+var_100], eax
0x18001f57c  test    eax, eax
0x18001f57e  mov     edi, eax
0x18001f580  mov     eax, 0DCCh
0x18001f585  js      loc_18001F696
0x18001f58b  lea     rcx, [rbp+4Fh+var_C8]; struct CBsString *
0x18001f58f  mov     [rsp+130h+var_FC], ax
0x18001f594  call    ?SxHexEncode@@YAJPEAVCBsString@@PEBG@Z; SxHexEncode(CBsString *,ushort const *)
0x18001f599  mov     edi, eax
0x18001f59b  mov     [rsp+130h+var_100], eax
0x18001f59f  test    eax, eax
0x18001f5a1  mov     eax, 0DCDh
0x18001f5a6  js      loc_18001F696
0x18001f5ac  mov     rdx, [rbp+4Fh+var_C8]
0x18001f5b0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001f5b4  mov     [rsp+130h+var_FC], ax
0x18001f5b9  inc     r8
0x18001f5bc  cmp     [rdx+r8*2], r15w
0x18001f5c1  jnz     short loc_18001F5B9
0x18001f5c3  inc     r8d
0x18001f5c6  mov     rcx, rsi
0x18001f5c9  call    ExtendCopy
0x18001f5ce  mov     edi, eax
0x18001f5d0  mov     [rsp+130h+var_100], eax
0x18001f5d4  test    eax, eax
0x18001f5d6  mov     eax, 0DCEh
0x18001f5db  js      loc_18001F696
0x18001f5e1  inc     r14d
0x18001f5e4  jmp     loc_18001F4AC
0x18001f5e9  mov     eax, 0DC6h
0x18001f5ee  jmp     loc_18001F696
0x18001f5f3  mov     rcx, rsi
0x18001f5f6  call    ?Append@?$CSxSimpleArray@G@@QEAAJG@Z; CSxSimpleArray<ushort>::Append(ushort)
0x18001f5fb  mov     edi, eax
0x18001f5fd  mov     [rsp+130h+var_100], eax
0x18001f601  test    eax, eax
0x18001f603  mov     eax, 0DD0h
0x18001f608  js      loc_18001F696
0x18001f60e  mov     rcx, [rbp+4Fh+rguid]; rguid
0x18001f612  lea     rdx, [rbp+4Fh+sz]; lpsz
0x18001f616  mov     r8d, 27h ; '''; cchMax
0x18001f61c  mov     [rsp+130h+var_FC], ax
0x18001f621  call    cs:__imp_StringFromGUID2
0x18001f627  test    eax, eax
0x18001f629  mov     eax, 0DD2h
0x18001f62e  jz      short loc_18001F686
0x18001f630  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18001f634  lea     rdx, [rbp+4Fh+sz]; lpValueName
0x18001f638  mov     [rsp+130h+var_FC], ax
0x18001f63d  mov     r9d, 7; dwType
0x18001f643  mov     [rsp+130h+var_100], r15d
0x18001f648  xor     r8d, r8d; Reserved
0x18001f64b  mov     eax, [rsi+10h]
0x18001f64e  add     eax, eax
0x18001f650  mov     [rsp+130h+cbData], eax; cbData
0x18001f654  mov     rax, [rsi+8]
0x18001f658  mov     [rsp+130h+lpData], rax; lpData
0x18001f65d  call    cs:__imp_RegSetValueExW
0x18001f663  mov     edi, eax
0x18001f665  test    eax, eax
0x18001f667  jle     short loc_18001F672
0x18001f669  movzx   edi, ax
0x18001f66c  or      edi, 80070000h
0x18001f672  mov     [rsp+130h+var_100], edi
0x18001f676  mov     eax, 0DD9h
0x18001f67b  test    edi, edi
0x18001f67d  js      short loc_18001F696
0x18001f67f  mov     [rsp+130h+var_FC], ax
0x18001f684  jmp     short loc_18001F69B
0x18001f686  mov     edi, 8000FFFFh
0x18001f68b  jmp     short loc_18001F692
0x18001f68d  mov     edi, 80070057h
0x18001f692  mov     [rsp+130h+var_100], edi
0x18001f696  mov     [rsp+130h+var_FA], ax
0x18001f69b  lea     rcx, [rbp+4Fh+var_C8]; this
0x18001f69f  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001f6a4  test    rsi, rsi
0x18001f6a7  jz      short loc_18001F6B1
0x18001f6a9  mov     rcx, rsi; Block
0x18001f6ac  call    ?Release@?$CSxSimpleArray@U_GUID@@@@QEAAKXZ; CSxSimpleArray<_GUID>::Release(void)
0x18001f6b1  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18001f6b5  lea     rax, [rcx-1]
0x18001f6b9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f6bd  ja      short loc_18001F6C5
0x18001f6bf  call    cs:__imp_RegCloseKey
0x18001f6c5  lea     rcx, [rbx-1]
0x18001f6c9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001f6cd  ja      short loc_18001F6D8
0x18001f6cf  mov     rcx, rbx; hKey
0x18001f6d2  call    cs:__imp_RegCloseKey
0x18001f6d8  lea     rcx, [rsp+130h+var_100]; this
0x18001f6dd  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001f6e2  mov     eax, edi
0x18001f6e4  mov     rcx, [rbp+4Fh+var_40]
0x18001f6e8  xor     rcx, rsp; StackCookie
0x18001f6eb  call    __security_check_cookie
0x18001f6f0  mov     rbx, [rsp+130h+arg_10]
0x18001f6f8  add     rsp, 100h
0x18001f6ff  pop     r15
0x18001f701  pop     r14
0x18001f703  pop     r13
0x18001f705  pop     r12
0x18001f707  pop     rdi
0x18001f708  pop     rsi
0x18001f709  pop     rbp
0x18001f70a  retn
```
