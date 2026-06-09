# CSdRestoreImpl::_SetAltLocation(ushort const *)

- ea: `0x1800307c4`
- end: `0x180030b07`
- name: `?_SetAltLocation@CSdRestoreImpl@@AEAAJPEBG@Z`
- size: `835`
- prototype: `__int64 __fastcall(CSdRestoreImpl *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180028300`

## callees

- `0x180008240`
- `0x180011274`
- `0x1800307c4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180070ac0`
- `0x18008f5d0`
- `0x180099484`
- `0x18009a22c`
- `0x18009a24c`
- `0x18009a3ac`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180030a1c`
- `KERNEL32!CreateFileW` at `0x180030a1c`
- `KERNEL32!GetLastError` at `0x180030a2b`
- `KERNEL32!GetLastError` at `0x180030a2b`
- `KERNEL32!CloseHandle` at `0x180030ac0`
- `KERNEL32!CloseHandle` at `0x180030ac0`
- `KERNEL32!GetFileAttributesW` at `0x180030934`
- `KERNEL32!GetFileAttributesW` at `0x180030934`
- `ole32!CoRevertToSelf` at `0x180030aa9`
- `ole32!CoRevertToSelf` at `0x180030aa9`
- `ole32!CoImpersonateClient` at `0x1800309d4`
- `ole32!CoImpersonateClient` at `0x1800309d4`
- `ole32!StringFromGUID2` at `0x1800309a0`
- `ole32!StringFromGUID2` at `0x1800309a0`
- `ole32!CoCreateGuid` at `0x180030976`
- `ole32!CoCreateGuid` at `0x180030976`

## pseudocode

```c
__int64 __fastcall CSdRestoreImpl::_SetAltLocation(CSdRestoreImpl *this, const unsigned __int16 *a2)
{
  __int64 FileW; // rbx
  int v5; // r15d
  __int16 v6; // ax
  const unsigned __int16 **v7; // rdi
  DWORD FileAttributesW; // eax
  char v9; // cl
  __int64 v10; // rcx
  unsigned int v11; // edi
  HRESULT StorageDevice; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v14; // [rsp+44h] [rbp-BCh]
  __int16 v15; // [rsp+46h] [rbp-BAh]
  LPCWSTR lpFileName[3]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v17[13]; // [rsp+90h] [rbp-70h] BYREF
  int v18; // [rsp+FCh] [rbp-4h]
  GUID pguid; // [rsp+120h] [rbp+20h] BYREF
  OLECHAR sz[40]; // [rsp+130h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&StorageDevice,
    "CSdRestoreImpl::_SetAltLocation",
    0x1397u,
    1u);
  memset_0(v17, 0, 0x90u);
  pguid = 0;
  memset_0(sz, 0, sizeof(sz));
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpFileName[1] = 0;
  FileW = -1;
  v5 = 0;
  v6 = 5024;
  if ( !a2 || (v14 = 5024, v6 = 5025, !*a2) )
  {
    StorageDevice = -2147024809;
LABEL_3:
    v15 = v6;
    goto LABEL_26;
  }
  StorageDevice = 0;
  v14 = 5025;
  v7 = (const unsigned __int16 **)((char *)this + 160);
  StorageDevice = CBsString::Set((CSdRestoreImpl *)((char *)this + 160), a2);
  v6 = 5027;
  if ( StorageDevice < 0 )
    goto LABEL_3;
  v14 = 5027;
  StorageDevice = CBsString::AntiCanonicalize((CSdRestoreImpl *)((char *)this + 160));
  v6 = 5028;
  if ( StorageDevice < 0 )
    goto LABEL_3;
  v14 = 5028;
  StorageDevice = QueryStorageDevice(*v7, (struct _SD_STORAGE_DEVICE_PROP *)v17);
  v6 = 5030;
  if ( StorageDevice < 0 )
    goto LABEL_3;
  v14 = 5030;
  v6 = 5031;
  if ( !v18 )
    goto LABEL_9;
  StorageDevice = 0;
  v14 = 5031;
  StorageDevice = CBsString::Trailing((CSdRestoreImpl *)((char *)this + 160), 0x5Cu);
  v6 = 5034;
  if ( StorageDevice < 0 )
    goto LABEL_3;
  v14 = 5034;
  FileAttributesW = GetFileAttributesW(*v7);
  v9 = FileAttributesW;
  if ( FileAttributesW == -1 )
  {
    StorageDevice = GetLastFailureAsHRESULT(0xFFFFFFFFLL);
    v6 = 5036;
    goto LABEL_3;
  }
  v14 = 5036;
  v6 = 5037;
  if ( (v9 & 0x10) == 0 )
  {
LABEL_9:
    StorageDevice = -2130706181;
    goto LABEL_3;
  }
  StorageDevice = 0;
  v14 = 5037;
  StorageDevice = CoCreateGuid(&pguid);
  v6 = 5039;
  if ( StorageDevice < 0 )
    goto LABEL_3;
  v14 = 5039;
  StringFromGUID2(&pguid, sz, 40);
  StorageDevice = CBsString::Set((CBsString *)lpFileName, *v7, sz);
  v6 = 5041;
  if ( StorageDevice < 0 )
    goto LABEL_3;
  v14 = 5041;
  if ( *((_DWORD *)this + 14) == 11 )
  {
    StorageDevice = CoImpersonateClient();
    v6 = 5046;
    if ( StorageDevice < 0 )
      goto LABEL_3;
    v14 = 5046;
    v5 = 1;
  }
  FileW = (__int64)CreateFileW(lpFileName[0], 0xC0000000, 4u, 0, 1u, 0x4000000u, 0);
  if ( FileW == -1 )
  {
    if ( GetLastError() == 5 )
    {
      StorageDevice = -2130706384;
      v6 = 5053;
    }
    else
    {
      StorageDevice = GetLastFailureAsHRESULT(v10);
      v6 = 5055;
    }
    goto LABEL_3;
  }
  StorageDevice = 0;
  v14 = 5055;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids, *v7);
LABEL_26:
  CleanupStorageDeviceProp(v17);
  if ( v5 )
    CoRevertToSelf();
  v11 = StorageDevice;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&StorageDevice);
  return v11;
}

```

## disassembly

```asm
0x1800307c4  mov     [rsp-8+arg_10], rbx
0x1800307c9  mov     [rsp-8+arg_18], rsi
0x1800307ce  push    rbp
0x1800307cf  push    rdi
0x1800307d0  push    r12
0x1800307d2  push    r14
0x1800307d4  push    r15
0x1800307d6  lea     rbp, [rsp-90h]
0x1800307de  sub     rsp, 190h
0x1800307e5  mov     rax, cs:__security_cookie
0x1800307ec  xor     rax, rsp
0x1800307ef  mov     [rbp+0B0h+var_30], rax
0x1800307f6  mov     rsi, rdx
0x1800307f9  mov     r14, rcx
0x1800307fc  mov     r9d, 1; unsigned __int16
0x180030802  mov     r8d, 1397h; unsigned __int16
0x180030808  lea     rdx, aCsdrestoreimpl_18; "CSdRestoreImpl::_SetAltLocation"
0x18003080f  lea     rcx, [rsp+1B0h+var_170]; this
0x180030814  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180030819  xor     edx, edx; Val
0x18003081b  mov     r8d, 90h; Size
0x180030821  lea     rcx, [rbp+0B0h+var_120]; void *
0x180030825  call    memset_0
0x18003082a  xorps   xmm0, xmm0
0x18003082d  movups  xmmword ptr [rbp+0B0h+pguid.Data1], xmm0
0x180030831  xor     edx, edx; Val
0x180030833  lea     r8d, [rdx+50h]; Size
0x180030837  lea     rcx, [rbp+0B0h+sz]; void *
0x18003083b  call    memset_0
0x180030840  lea     rax, qword_1800E8530
0x180030847  mov     [rsp+1B0h+lpFileName], rax
0x18003084c  xor     r12d, r12d
0x18003084f  mov     [rbp+0B0h+var_130], r12
0x180030853  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180030857  mov     r15d, r12d
0x18003085a  mov     eax, 13A0h
0x18003085f  test    rsi, rsi
0x180030862  jnz     short loc_180030876
0x180030864  mov     [rsp+1B0h+var_170], 80070057h
0x18003086c  mov     [rsp+1B0h+var_16A], ax
0x180030871  jmp     loc_180030A9B
0x180030876  mov     [rsp+1B0h+var_16C], ax
0x18003087b  mov     eax, 13A1h
0x180030880  cmp     [rsi], r12w
0x180030884  jz      short loc_180030864
0x180030886  mov     [rsp+1B0h+var_170], r12d
0x18003088b  mov     [rsp+1B0h+var_16C], ax
0x180030890  lea     rdi, [r14+0A0h]
0x180030897  mov     rdx, rsi; unsigned __int16 *
0x18003089a  mov     rcx, rdi; this
0x18003089d  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800308a2  mov     [rsp+1B0h+var_170], eax
0x1800308a6  test    eax, eax
0x1800308a8  mov     eax, 13A3h
0x1800308ad  js      short loc_18003086C
0x1800308af  mov     [rsp+1B0h+var_16C], ax
0x1800308b4  mov     rcx, rdi; this
0x1800308b7  call    ?AntiCanonicalize@CBsString@@QEAAJXZ; CBsString::AntiCanonicalize(void)
0x1800308bc  mov     [rsp+1B0h+var_170], eax
0x1800308c0  test    eax, eax
0x1800308c2  mov     eax, 13A4h
0x1800308c7  js      short loc_18003086C
0x1800308c9  mov     [rsp+1B0h+var_16C], ax
0x1800308ce  lea     rdx, [rbp+0B0h+var_120]; struct _SD_STORAGE_DEVICE_PROP *
0x1800308d2  mov     rcx, [rdi]; unsigned __int16 *
0x1800308d5  call    ?QueryStorageDevice@@YAJPEBGPEAU_SD_STORAGE_DEVICE_PROP@@@Z; QueryStorageDevice(ushort const *,_SD_STORAGE_DEVICE_PROP *)
0x1800308da  mov     [rsp+1B0h+var_170], eax
0x1800308de  test    eax, eax
0x1800308e0  mov     eax, 13A6h
0x1800308e5  js      short loc_18003086C
0x1800308e7  mov     [rsp+1B0h+var_16C], ax
0x1800308ec  mov     eax, 13A7h
0x1800308f1  cmp     [rbp+0B0h+var_B4], r12d
0x1800308f5  jnz     short loc_180030904
0x1800308f7  mov     [rsp+1B0h+var_170], 810000FBh
0x1800308ff  jmp     loc_18003086C
0x180030904  mov     [rsp+1B0h+var_170], r12d
0x180030909  mov     [rsp+1B0h+var_16C], ax
0x18003090e  mov     edx, 5Ch ; '\'; unsigned __int16
0x180030913  mov     rcx, rdi; this
0x180030916  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18003091b  mov     [rsp+1B0h+var_170], eax
0x18003091f  test    eax, eax
0x180030921  mov     eax, 13AAh
0x180030926  js      loc_18003086C
0x18003092c  mov     [rsp+1B0h+var_16C], ax
0x180030931  mov     rcx, [rdi]; lpFileName
0x180030934  call    cs:__imp_GetFileAttributesW
0x18003093a  mov     ecx, eax
0x18003093c  cmp     eax, 0FFFFFFFFh
0x18003093f  jnz     short loc_180030954
0x180030941  call    GetLastFailureAsHRESULT
0x180030946  mov     [rsp+1B0h+var_170], eax
0x18003094a  mov     eax, 13ACh
0x18003094f  jmp     loc_18003086C
0x180030954  mov     eax, 13ACh
0x180030959  mov     [rsp+1B0h+var_16C], ax
0x18003095e  mov     eax, 13ADh
0x180030963  test    cl, 10h
0x180030966  jz      short loc_1800308F7
0x180030968  mov     [rsp+1B0h+var_170], r12d
0x18003096d  mov     [rsp+1B0h+var_16C], ax
0x180030972  lea     rcx, [rbp+0B0h+pguid]; pguid
0x180030976  call    cs:__imp_CoCreateGuid
0x18003097c  mov     [rsp+1B0h+var_170], eax
0x180030980  test    eax, eax
0x180030982  mov     eax, 13AFh
0x180030987  js      loc_18003086C
0x18003098d  mov     [rsp+1B0h+var_16C], ax
0x180030992  mov     r8d, 28h ; '('; cchMax
0x180030998  lea     rdx, [rbp+0B0h+sz]; lpsz
0x18003099c  lea     rcx, [rbp+0B0h+pguid]; rguid
0x1800309a0  call    cs:__imp_StringFromGUID2
0x1800309a6  lea     r8, [rbp+0B0h+sz]; unsigned __int16 *
0x1800309aa  mov     rdx, [rdi]; unsigned __int16 *
0x1800309ad  lea     rcx, [rsp+1B0h+lpFileName]; this
0x1800309b2  call    ?Set@CBsString@@QEAAJPEBG0@Z; CBsString::Set(ushort const *,ushort const *)
0x1800309b7  mov     [rsp+1B0h+var_170], eax
0x1800309bb  test    eax, eax
0x1800309bd  mov     eax, 13B1h
0x1800309c2  js      loc_18003086C
0x1800309c8  mov     [rsp+1B0h+var_16C], ax
0x1800309cd  cmp     dword ptr [r14+38h], 0Bh
0x1800309d2  jnz     short loc_1800309F6
0x1800309d4  call    cs:__imp_CoImpersonateClient
0x1800309da  mov     [rsp+1B0h+var_170], eax
0x1800309de  test    eax, eax
0x1800309e0  mov     eax, 13B6h
0x1800309e5  js      loc_18003086C
0x1800309eb  mov     [rsp+1B0h+var_16C], ax
0x1800309f0  mov     r15d, 1
0x1800309f6  mov     [rsp+1B0h+hTemplateFile], r12; hTemplateFile
0x1800309fb  mov     [rsp+1B0h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x180030a03  mov     [rsp+1B0h+dwCreationDisposition], 1; dwCreationDisposition
0x180030a0b  xor     r9d, r9d; lpSecurityAttributes
0x180030a0e  mov     edx, 0C0000000h; dwDesiredAccess
0x180030a13  lea     r8d, [r9+4]; dwShareMode
0x180030a17  mov     rcx, [rsp+1B0h+lpFileName]; lpFileName
0x180030a1c  call    cs:__imp_CreateFileW
0x180030a22  mov     rbx, rax
0x180030a25  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030a29  jnz     short loc_180030A5B
0x180030a2b  call    cs:__imp_GetLastError
0x180030a31  cmp     eax, 5
0x180030a34  jnz     short loc_180030A48
0x180030a36  mov     [rsp+1B0h+var_170], 81000030h
0x180030a3e  mov     eax, 13BDh
0x180030a43  jmp     loc_18003086C
0x180030a48  call    GetLastFailureAsHRESULT
0x180030a4d  mov     [rsp+1B0h+var_170], eax
0x180030a51  mov     eax, 13BFh
0x180030a56  jmp     loc_18003086C
0x180030a5b  mov     [rsp+1B0h+var_170], r12d
0x180030a60  mov     eax, 13BFh
0x180030a65  mov     [rsp+1B0h+var_16C], ax
0x180030a6a  lea     rax, WPP_GLOBAL_Control
0x180030a71  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a78  cmp     rcx, rax
0x180030a7b  jz      short loc_180030A9B
0x180030a7d  test    byte ptr [rcx+1Ch], 80h
0x180030a81  jz      short loc_180030A9B
0x180030a83  mov     edx, 61h ; 'a'
0x180030a88  mov     r9, [rdi]
0x180030a8b  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x180030a92  mov     rcx, [rcx+10h]
0x180030a96  call    WPP_SF_S
0x180030a9b  lea     rcx, [rbp+0B0h+var_120]; unsigned __int16 **
0x180030a9f  call    ?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x180030aa4  test    r15d, r15d
0x180030aa7  jz      short loc_180030AAF
0x180030aa9  call    cs:__imp_CoRevertToSelf
0x180030aaf  mov     edi, [rsp+1B0h+var_170]
0x180030ab3  lea     rcx, [rbx-1]
0x180030ab7  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180030abb  ja      short loc_180030AC6
0x180030abd  mov     rcx, rbx; hObject
0x180030ac0  call    cs:__imp_CloseHandle
0x180030ac6  lea     rcx, [rsp+1B0h+lpFileName]; this
0x180030acb  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180030ad0  lea     rcx, [rsp+1B0h+var_170]; this
0x180030ad5  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180030ada  mov     eax, edi
0x180030adc  mov     rcx, [rbp+0B0h+var_30]
0x180030ae3  xor     rcx, rsp; StackCookie
0x180030ae6  call    __security_check_cookie
0x180030aeb  lea     r11, [rsp+1B0h+var_20]
0x180030af3  mov     rbx, [r11+40h]
0x180030af7  mov     rsi, [r11+48h]
0x180030afb  mov     rsp, r11
0x180030afe  pop     r15
0x180030b00  pop     r14
0x180030b02  pop     r12
0x180030b04  pop     rdi
0x180030b05  pop     rbp
0x180030b06  retn
```
