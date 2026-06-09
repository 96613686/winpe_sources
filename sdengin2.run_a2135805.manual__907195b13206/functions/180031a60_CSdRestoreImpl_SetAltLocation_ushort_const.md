# CSdRestoreImpl::_SetAltLocation(ushort const *)

- ea: `0x180031a60`
- end: `0x180031dd4`
- name: `?_SetAltLocation@CSdRestoreImpl@@AEAAJPEBG@Z`
- size: `884`
- prototype: `int(CSdRestoreImpl *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18002935c`

## callees

- `0x1800083e4`
- `0x1800119c4`
- `0x180031a60`
- `0x180072e08`
- `0x180072f14`
- `0x180073ad8`
- `0x1800935fc`
- `0x18009da98`
- `0x18009e8e4`
- `0x18009e904`
- `0x18009ea6c`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180031cd0`
- `KERNEL32!CreateFileW` at `0x180031cd0`
- `KERNEL32!GetLastError` at `0x180031ce5`
- `KERNEL32!GetLastError` at `0x180031ce5`
- `KERNEL32!CloseHandle` at `0x180031d86`
- `KERNEL32!CloseHandle` at `0x180031d86`
- `KERNEL32!GetFileAttributesW` at `0x180031bd0`
- `KERNEL32!GetFileAttributesW` at `0x180031bd0`
- `ole32!CoRevertToSelf` at `0x180031d69`
- `ole32!CoRevertToSelf` at `0x180031d69`
- `ole32!CoImpersonateClient` at `0x180031c82`
- `ole32!CoImpersonateClient` at `0x180031c82`
- `ole32!StringFromGUID2` at `0x180031c48`
- `ole32!StringFromGUID2` at `0x180031c48`
- `ole32!CoCreateGuid` at `0x180031c18`
- `ole32!CoCreateGuid` at `0x180031c18`

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
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
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
0x180031a60  mov     [rsp-8+arg_10], rbx
0x180031a65  mov     [rsp-8+arg_18], rsi
0x180031a6a  push    rbp
0x180031a6b  push    rdi
0x180031a6c  push    r12
0x180031a6e  push    r14
0x180031a70  push    r15
0x180031a72  lea     rbp, [rsp-90h]
0x180031a7a  sub     rsp, 190h
0x180031a81  mov     rax, cs:__security_cookie
0x180031a88  xor     rax, rsp
0x180031a8b  mov     [rbp+0B0h+var_30], rax
0x180031a92  mov     rsi, rdx
0x180031a95  mov     r14, rcx
0x180031a98  mov     r9d, 1; unsigned __int16
0x180031a9e  mov     r8d, 1397h; unsigned __int16
0x180031aa4  lea     rdx, aCsdrestoreimpl_18; "CSdRestoreImpl::_SetAltLocation"
0x180031aab  lea     rcx, [rsp+1B0h+var_170]; this
0x180031ab0  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180031ab5  xor     edx, edx; Val
0x180031ab7  mov     r8d, 90h; Size
0x180031abd  lea     rcx, [rbp+0B0h+var_120]; void *
0x180031ac1  call    memset_0
0x180031ac6  xorps   xmm0, xmm0
0x180031ac9  movups  xmmword ptr [rbp+0B0h+pguid.Data1], xmm0
0x180031acd  xor     edx, edx; Val
0x180031acf  lea     r8d, [rdx+50h]; Size
0x180031ad3  lea     rcx, [rbp+0B0h+sz]; void *
0x180031ad7  call    memset_0
0x180031adc  lea     rax, qword_1800EE510
0x180031ae3  mov     [rsp+1B0h+lpFileName], rax
0x180031ae8  xor     r12d, r12d
0x180031aeb  mov     [rbp+0B0h+var_130], r12
0x180031aef  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180031af3  mov     r15d, r12d
0x180031af6  mov     eax, 13A0h
0x180031afb  test    rsi, rsi
0x180031afe  jnz     short loc_180031B12
0x180031b00  mov     [rsp+1B0h+var_170], 80070057h
0x180031b08  mov     [rsp+1B0h+var_16A], ax
0x180031b0d  jmp     loc_180031D5B
0x180031b12  mov     [rsp+1B0h+var_16C], ax
0x180031b17  mov     eax, 13A1h
0x180031b1c  cmp     [rsi], r12w
0x180031b20  jz      short loc_180031B00
0x180031b22  mov     [rsp+1B0h+var_170], r12d
0x180031b27  mov     [rsp+1B0h+var_16C], ax
0x180031b2c  lea     rdi, [r14+0A0h]
0x180031b33  mov     rdx, rsi; unsigned __int16 *
0x180031b36  mov     rcx, rdi; this
0x180031b39  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180031b3e  mov     [rsp+1B0h+var_170], eax
0x180031b42  test    eax, eax
0x180031b44  mov     eax, 13A3h
0x180031b49  js      short loc_180031B08
0x180031b4b  mov     [rsp+1B0h+var_16C], ax
0x180031b50  mov     rcx, rdi; this
0x180031b53  call    ?AntiCanonicalize@CBsString@@QEAAJXZ; CBsString::AntiCanonicalize(void)
0x180031b58  mov     [rsp+1B0h+var_170], eax
0x180031b5c  test    eax, eax
0x180031b5e  mov     eax, 13A4h
0x180031b63  js      short loc_180031B08
0x180031b65  mov     [rsp+1B0h+var_16C], ax
0x180031b6a  lea     rdx, [rbp+0B0h+var_120]; struct _SD_STORAGE_DEVICE_PROP *
0x180031b6e  mov     rcx, [rdi]; unsigned __int16 *
0x180031b71  call    ?QueryStorageDevice@@YAJPEBGPEAU_SD_STORAGE_DEVICE_PROP@@@Z; QueryStorageDevice(ushort const *,_SD_STORAGE_DEVICE_PROP *)
0x180031b76  mov     [rsp+1B0h+var_170], eax
0x180031b7a  test    eax, eax
0x180031b7c  mov     eax, 13A6h
0x180031b81  js      short loc_180031B08
0x180031b83  mov     [rsp+1B0h+var_16C], ax
0x180031b88  mov     eax, 13A7h
0x180031b8d  cmp     [rbp+0B0h+var_B4], r12d
0x180031b91  jnz     short loc_180031BA0
0x180031b93  mov     [rsp+1B0h+var_170], 810000FBh
0x180031b9b  jmp     loc_180031B08
0x180031ba0  mov     [rsp+1B0h+var_170], r12d
0x180031ba5  mov     [rsp+1B0h+var_16C], ax
0x180031baa  mov     edx, 5Ch ; '\'; unsigned __int16
0x180031baf  mov     rcx, rdi; this
0x180031bb2  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x180031bb7  mov     [rsp+1B0h+var_170], eax
0x180031bbb  test    eax, eax
0x180031bbd  mov     eax, 13AAh
0x180031bc2  js      loc_180031B08
0x180031bc8  mov     [rsp+1B0h+var_16C], ax
0x180031bcd  mov     rcx, [rdi]; lpFileName
0x180031bd0  call    cs:__imp_GetFileAttributesW
0x180031bd7  nop     dword ptr [rax+rax+00h]
0x180031bdc  mov     ecx, eax
0x180031bde  cmp     eax, 0FFFFFFFFh
0x180031be1  jnz     short loc_180031BF6
0x180031be3  call    GetLastFailureAsHRESULT
0x180031be8  mov     [rsp+1B0h+var_170], eax
0x180031bec  mov     eax, 13ACh
0x180031bf1  jmp     loc_180031B08
0x180031bf6  mov     eax, 13ACh
0x180031bfb  mov     [rsp+1B0h+var_16C], ax
0x180031c00  mov     eax, 13ADh
0x180031c05  test    cl, 10h
0x180031c08  jz      short loc_180031B93
0x180031c0a  mov     [rsp+1B0h+var_170], r12d
0x180031c0f  mov     [rsp+1B0h+var_16C], ax
0x180031c14  lea     rcx, [rbp+0B0h+pguid]; pguid
0x180031c18  call    cs:__imp_CoCreateGuid
0x180031c1f  nop     dword ptr [rax+rax+00h]
0x180031c24  mov     [rsp+1B0h+var_170], eax
0x180031c28  test    eax, eax
0x180031c2a  mov     eax, 13AFh
0x180031c2f  js      loc_180031B08
0x180031c35  mov     [rsp+1B0h+var_16C], ax
0x180031c3a  mov     r8d, 28h ; '('; cchMax
0x180031c40  lea     rdx, [rbp+0B0h+sz]; lpsz
0x180031c44  lea     rcx, [rbp+0B0h+pguid]; rguid
0x180031c48  call    cs:__imp_StringFromGUID2
0x180031c4f  nop     dword ptr [rax+rax+00h]
0x180031c54  lea     r8, [rbp+0B0h+sz]; unsigned __int16 *
0x180031c58  mov     rdx, [rdi]; unsigned __int16 *
0x180031c5b  lea     rcx, [rsp+1B0h+lpFileName]; this
0x180031c60  call    ?Set@CBsString@@QEAAJPEBG0@Z; CBsString::Set(ushort const *,ushort const *)
0x180031c65  mov     [rsp+1B0h+var_170], eax
0x180031c69  test    eax, eax
0x180031c6b  mov     eax, 13B1h
0x180031c70  js      loc_180031B08
0x180031c76  mov     [rsp+1B0h+var_16C], ax
0x180031c7b  cmp     dword ptr [r14+38h], 0Bh
0x180031c80  jnz     short loc_180031CAA
0x180031c82  call    cs:__imp_CoImpersonateClient
0x180031c89  nop     dword ptr [rax+rax+00h]
0x180031c8e  mov     [rsp+1B0h+var_170], eax
0x180031c92  test    eax, eax
0x180031c94  mov     eax, 13B6h
0x180031c99  js      loc_180031B08
0x180031c9f  mov     [rsp+1B0h+var_16C], ax
0x180031ca4  mov     r15d, 1
0x180031caa  mov     [rsp+1B0h+hTemplateFile], r12; hTemplateFile
0x180031caf  mov     [rsp+1B0h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x180031cb7  mov     [rsp+1B0h+dwCreationDisposition], 1; dwCreationDisposition
0x180031cbf  xor     r9d, r9d; lpSecurityAttributes
0x180031cc2  mov     edx, 0C0000000h; dwDesiredAccess
0x180031cc7  lea     r8d, [r9+4]; dwShareMode
0x180031ccb  mov     rcx, [rsp+1B0h+lpFileName]; lpFileName
0x180031cd0  call    cs:__imp_CreateFileW
0x180031cd7  nop     dword ptr [rax+rax+00h]
0x180031cdc  mov     rbx, rax
0x180031cdf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031ce3  jnz     short loc_180031D1B
0x180031ce5  call    cs:__imp_GetLastError
0x180031cec  nop     dword ptr [rax+rax+00h]
0x180031cf1  cmp     eax, 5
0x180031cf4  jnz     short loc_180031D08
0x180031cf6  mov     [rsp+1B0h+var_170], 81000030h
0x180031cfe  mov     eax, 13BDh
0x180031d03  jmp     loc_180031B08
0x180031d08  call    GetLastFailureAsHRESULT
0x180031d0d  mov     [rsp+1B0h+var_170], eax
0x180031d11  mov     eax, 13BFh
0x180031d16  jmp     loc_180031B08
0x180031d1b  mov     [rsp+1B0h+var_170], r12d
0x180031d20  mov     eax, 13BFh
0x180031d25  mov     [rsp+1B0h+var_16C], ax
0x180031d2a  lea     rax, WPP_GLOBAL_Control
0x180031d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180031d38  cmp     rcx, rax
0x180031d3b  jz      short loc_180031D5B
0x180031d3d  test    byte ptr [rcx+1Ch], 80h
0x180031d41  jz      short loc_180031D5B
0x180031d43  mov     edx, 61h ; 'a'
0x180031d48  mov     r9, [rdi]
0x180031d4b  lea     r8, WPP_052bc5b66f273e09fada3dec80af9ee3_Traceguids
0x180031d52  mov     rcx, [rcx+10h]
0x180031d56  call    WPP_SF_S
0x180031d5b  lea     rcx, [rbp+0B0h+var_120]; unsigned __int16 **
0x180031d5f  call    ?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x180031d64  test    r15d, r15d
0x180031d67  jz      short loc_180031D75
0x180031d69  call    cs:__imp_CoRevertToSelf
0x180031d70  nop     dword ptr [rax+rax+00h]
0x180031d75  mov     edi, [rsp+1B0h+var_170]
0x180031d79  lea     rcx, [rbx-1]
0x180031d7d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180031d81  ja      short loc_180031D92
0x180031d83  mov     rcx, rbx; hObject
0x180031d86  call    cs:__imp_CloseHandle
0x180031d8d  nop     dword ptr [rax+rax+00h]
0x180031d92  lea     rcx, [rsp+1B0h+lpFileName]; this
0x180031d97  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180031d9c  lea     rcx, [rsp+1B0h+var_170]; this
0x180031da1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180031da6  mov     eax, edi
0x180031da8  mov     rcx, [rbp+0B0h+var_30]
0x180031daf  xor     rcx, rsp; StackCookie
0x180031db2  call    __security_check_cookie
0x180031db7  lea     r11, [rsp+1B0h+var_20]
0x180031dbf  mov     rbx, [r11+40h]
0x180031dc3  mov     rsi, [r11+48h]
0x180031dc7  mov     rsp, r11
0x180031dca  pop     r15
0x180031dcc  pop     r14
0x180031dce  pop     r12
0x180031dd0  pop     rdi
0x180031dd1  pop     rbp
0x180031dd2  retn
```
