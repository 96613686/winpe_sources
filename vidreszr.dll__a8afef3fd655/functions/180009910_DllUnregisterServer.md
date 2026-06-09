# DllUnregisterServer

- ea: `0x180009910`
- end: `0x180009b24`
- name: `DllUnregisterServer`
- size: `532`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180009910`
- `0x180014378`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800099f4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180009ac4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800099f4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180009ac4`
- `MFPlat!MFTUnregister` at `0x180009ae3`
- `MFPlat!MFTUnregister` at `0x180009ae3`
- `msdmo!DMOUnregister` at `0x1800099dd`
- `msdmo!DMOUnregister` at `0x180009a0b`
- `msdmo!DMOUnregister` at `0x1800099dd`
- `msdmo!DMOUnregister` at `0x180009a0b`

## string_xrefs

- `0x1800099a3`: `CLSID\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}`
- `0x180009a21`: `CLSID\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LSTATUS v0; // r15d
  HRESULT v1; // eax
  LSTATUS v2; // ebx
  int v3; // eax
  HRESULT v5; // ecx
  int Data2; // [rsp+20h] [rbp-158h]
  __int64 v7; // [rsp+20h] [rbp-158h]
  int Data3; // [rsp+28h] [rbp-150h]
  __int64 v9; // [rsp+28h] [rbp-150h]
  int v10; // [rsp+30h] [rbp-148h]
  __int64 v11; // [rsp+30h] [rbp-148h]
  int v12; // [rsp+38h] [rbp-140h]
  __int64 v13; // [rsp+38h] [rbp-140h]
  int v14; // [rsp+40h] [rbp-138h]
  __int64 v15; // [rsp+40h] [rbp-138h]
  int v16; // [rsp+48h] [rbp-130h]
  __int64 v17; // [rsp+48h] [rbp-130h]
  int v18; // [rsp+50h] [rbp-128h]
  __int64 v19; // [rsp+50h] [rbp-128h]
  int v20; // [rsp+58h] [rbp-120h]
  __int64 v21; // [rsp+58h] [rbp-120h]
  int v22; // [rsp+60h] [rbp-118h]
  __int64 v23; // [rsp+60h] [rbp-118h]
  int v24; // [rsp+68h] [rbp-110h]
  __int64 v25; // [rsp+68h] [rbp-110h]
  CLSID clsidMFT; // [rsp+80h] [rbp-F8h] BYREF
  WCHAR SubKey[80]; // [rsp+90h] [rbp-E8h] BYREF

  v24 = CLSID_CResizerDMO.Data4[7];
  v22 = CLSID_CResizerDMO.Data4[6];
  v20 = CLSID_CResizerDMO.Data4[5];
  v18 = CLSID_CResizerDMO.Data4[4];
  v16 = CLSID_CResizerDMO.Data4[3];
  v14 = CLSID_CResizerDMO.Data4[2];
  v12 = CLSID_CResizerDMO.Data4[1];
  v10 = CLSID_CResizerDMO.Data4[0];
  Data3 = CLSID_CResizerDMO.Data3;
  Data2 = CLSID_CResizerDMO.Data2;
  v0 = StringCchPrintfW(
         SubKey,
         0x50u,
         L"CLSID\\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
         CLSID_CResizerDMO.Data1,
         Data2,
         Data3,
         v10,
         v12,
         v14,
         v16,
         v18,
         v20,
         v22,
         v24);
  if ( v0 >= 0 )
  {
    v0 = RegDeleteTreeW(HKEY_CLASSES_ROOT, SubKey);
    v1 = DMOUnregister(&CLSID_CResizerDMO, &DMOCATEGORY_VIDEO_EFFECT);
    if ( v0 >= 0 )
      v0 = v1;
  }
  else
  {
    DMOUnregister(&CLSID_CResizerDMO, &DMOCATEGORY_VIDEO_EFFECT);
  }
  LODWORD(v25) = CLSID_CResizerDMO.Data4[7];
  LODWORD(v23) = CLSID_CResizerDMO.Data4[6];
  LODWORD(v21) = CLSID_CResizerDMO.Data4[5];
  LODWORD(v19) = CLSID_CResizerDMO.Data4[4];
  LODWORD(v17) = CLSID_CResizerDMO.Data4[3];
  LODWORD(v15) = CLSID_CResizerDMO.Data4[2];
  LODWORD(v13) = CLSID_CResizerDMO.Data4[1];
  LODWORD(v11) = CLSID_CResizerDMO.Data4[0];
  LODWORD(v9) = CLSID_CResizerDMO.Data3;
  LODWORD(v7) = CLSID_CResizerDMO.Data2;
  v2 = StringCchPrintfW(
         SubKey,
         0x50u,
         L"CLSID\\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
         CLSID_CResizerDMO.Data1,
         v7,
         v9,
         v11,
         v13,
         v15,
         v17,
         v19,
         v21,
         v23,
         v25);
  if ( v2 >= 0 )
    v2 = RegDeleteTreeW(HKEY_CLASSES_ROOT, SubKey);
  clsidMFT = CLSID_CResizerDMO;
  v3 = MFTUnregister(&clsidMFT);
  if ( v0 < 0 )
    return v0;
  if ( v2 < 0 )
    return v2;
  v5 = 0;
  if ( v3 < 0 )
    return v3;
  return v5;
}

```

## disassembly

```asm
0x180009910  push    rbx
0x180009912  push    rbp
0x180009913  push    rsi
0x180009914  push    rdi
0x180009915  push    r14
0x180009917  push    r15
0x180009919  sub     rsp, 148h
0x180009920  mov     rax, cs:__security_cookie
0x180009927  xor     rax, rsp
0x18000992a  mov     [rsp+178h+var_48], rax
0x180009932  movzx   r9d, cs:CLSID_CResizerDMO.Data4+2
0x18000993a  movzx   r8d, cs:CLSID_CResizerDMO.Data4+1
0x180009942  movzx   edx, cs:CLSID_CResizerDMO.Data4
0x180009949  movzx   ecx, cs:CLSID_CResizerDMO.Data3
0x180009950  movzx   esi, cs:CLSID_CResizerDMO.Data4+7
0x180009957  movzx   edi, cs:CLSID_CResizerDMO.Data4+6
0x18000995e  movzx   ebx, cs:CLSID_CResizerDMO.Data4+5
0x180009965  movzx   r11d, cs:CLSID_CResizerDMO.Data4+4
0x18000996d  movzx   r10d, cs:CLSID_CResizerDMO.Data4+3
0x180009975  movzx   eax, cs:CLSID_CResizerDMO.Data2
0x18000997c  mov     dword ptr [rsp+178h+var_110], esi
0x180009980  mov     dword ptr [rsp+178h+var_118], edi
0x180009984  mov     dword ptr [rsp+178h+var_120], ebx
0x180009988  mov     dword ptr [rsp+178h+var_128], r11d
0x18000998d  mov     dword ptr [rsp+178h+var_130], r10d
0x180009992  mov     dword ptr [rsp+178h+var_138], r9d
0x180009997  mov     r9d, cs:CLSID_CResizerDMO.Data1
0x18000999e  mov     dword ptr [rsp+178h+var_140], r8d
0x1800099a3  lea     r8, aClsid08x04x04x; "CLSID\\{%08x-%04x-%04x-%02x%02x-%02x%02"...
0x1800099aa  mov     dword ptr [rsp+178h+var_148], edx
0x1800099ae  mov     edx, 50h ; 'P'; unsigned __int64
0x1800099b3  mov     dword ptr [rsp+178h+var_150], ecx
0x1800099b7  lea     rcx, [rsp+178h+SubKey]; unsigned __int16 *
0x1800099bf  mov     dword ptr [rsp+178h+var_158], eax
0x1800099c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800099c8  mov     r15d, eax
0x1800099cb  test    eax, eax
0x1800099cd  jns     short loc_1800099E5
0x1800099cf  lea     rdx, DMOCATEGORY_VIDEO_EFFECT; guidCategory
0x1800099d6  lea     rcx, CLSID_CResizerDMO; clsidDMO
0x1800099dd  call    cs:__imp_DMOUnregister
0x1800099e3  jmp     short loc_180009A19
0x1800099e5  lea     rdx, [rsp+178h+SubKey]; lpSubKey
0x1800099ed  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800099f4  call    cs:__imp_RegDeleteTreeW
0x1800099fa  lea     rdx, DMOCATEGORY_VIDEO_EFFECT; guidCategory
0x180009a01  mov     r15d, eax
0x180009a04  lea     rcx, CLSID_CResizerDMO; clsidDMO
0x180009a0b  call    cs:__imp_DMOUnregister
0x180009a11  test    r15d, r15d
0x180009a14  js      short loc_180009A19
0x180009a16  mov     r15d, eax
0x180009a19  movzx   r9d, cs:CLSID_CResizerDMO.Data4
0x180009a21  lea     r8, aClsid08x04x04x; "CLSID\\{%08x-%04x-%04x-%02x%02x-%02x%02"...
0x180009a28  movzx   ecx, cs:CLSID_CResizerDMO.Data3
0x180009a2f  mov     edx, 50h ; 'P'; unsigned __int64
0x180009a34  movzx   r14d, cs:CLSID_CResizerDMO.Data4+7
0x180009a3c  movzx   ebp, cs:CLSID_CResizerDMO.Data4+6
0x180009a43  movzx   esi, cs:CLSID_CResizerDMO.Data4+5
0x180009a4a  movzx   edi, cs:CLSID_CResizerDMO.Data4+4
0x180009a51  movzx   ebx, cs:CLSID_CResizerDMO.Data4+3
0x180009a58  movzx   r11d, cs:CLSID_CResizerDMO.Data4+2
0x180009a60  movzx   r10d, cs:CLSID_CResizerDMO.Data4+1
0x180009a68  movzx   eax, cs:CLSID_CResizerDMO.Data2
0x180009a6f  mov     dword ptr [rsp+178h+var_110], r14d
0x180009a74  mov     dword ptr [rsp+178h+var_118], ebp
0x180009a78  mov     dword ptr [rsp+178h+var_120], esi
0x180009a7c  mov     dword ptr [rsp+178h+var_128], edi
0x180009a80  mov     dword ptr [rsp+178h+var_130], ebx
0x180009a84  mov     dword ptr [rsp+178h+var_138], r11d
0x180009a89  mov     dword ptr [rsp+178h+var_140], r10d
0x180009a8e  mov     dword ptr [rsp+178h+var_148], r9d
0x180009a93  mov     r9d, cs:CLSID_CResizerDMO.Data1
0x180009a9a  mov     dword ptr [rsp+178h+var_150], ecx
0x180009a9e  lea     rcx, [rsp+178h+SubKey]; unsigned __int16 *
0x180009aa6  mov     dword ptr [rsp+178h+var_158], eax
0x180009aaa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009aaf  mov     ebx, eax
0x180009ab1  test    eax, eax
0x180009ab3  js      short loc_180009ACC
0x180009ab5  lea     rdx, [rsp+178h+SubKey]; lpSubKey
0x180009abd  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180009ac4  call    cs:__imp_RegDeleteTreeW
0x180009aca  mov     ebx, eax
0x180009acc  movups  xmm0, xmmword ptr cs:CLSID_CResizerDMO.Data1
0x180009ad3  lea     rcx, [rsp+178h+clsidMFT]; clsidMFT
0x180009adb  movaps  xmmword ptr [rsp+178h+clsidMFT.Data1], xmm0
0x180009ae3  call    cs:__imp_MFTUnregister
0x180009ae9  test    r15d, r15d
0x180009aec  jns     short loc_180009AF3
0x180009aee  mov     eax, r15d
0x180009af1  jmp     short loc_180009B04
0x180009af3  test    ebx, ebx
0x180009af5  jns     short loc_180009AFB
0x180009af7  mov     eax, ebx
0x180009af9  jmp     short loc_180009B04
0x180009afb  xor     ecx, ecx
0x180009afd  test    eax, eax
0x180009aff  cmovs   ecx, eax
0x180009b02  mov     eax, ecx
0x180009b04  mov     rcx, [rsp+178h+var_48]
0x180009b0c  xor     rcx, rsp; StackCookie
0x180009b0f  call    __security_check_cookie
0x180009b14  add     rsp, 148h
0x180009b1b  pop     r15
0x180009b1d  pop     r14
0x180009b1f  pop     rdi
0x180009b20  pop     rsi
0x180009b21  pop     rbp
0x180009b22  pop     rbx
0x180009b23  retn
```
