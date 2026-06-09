# SxGetSystemVolumeGlobalPath(CBsString *)

- ea: `0x180091be0`
- end: `0x180091dfb`
- name: `?SxGetSystemVolumeGlobalPath@@YAJPEAVCBsString@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(struct CBsString *this)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x180040968`
- `0x1800919e8`

## callees

- `0x18006d058`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f660`
- `0x180091be0`
- `0x180099bdc`
- `0x18009a378`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180091c74`
- `ntdll!NtQuerySystemInformation` at `0x180091cf3`
- `ntdll!NtQuerySystemInformation` at `0x180091c74`
- `ntdll!NtQuerySystemInformation` at `0x180091cf3`
- `ole32!CoTaskMemFree` at `0x180091dc1`
- `ole32!CoTaskMemFree` at `0x180091dc1`
- `ole32!CoTaskMemAlloc` at `0x180091cb4`
- `ole32!CoTaskMemAlloc` at `0x180091cb4`

## string_xrefs

- `0x180091c0e`: `SxGetSystemVolumeGlobalPath`

## pseudocode

```c
__int64 __fastcall SxGetSystemVolumeGlobalPath(struct CBsString *this)
{
  const unsigned __int16 **v2; // rbx
  NTSTATUS v3; // eax
  __int16 v4; // ax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  const unsigned __int16 *v8; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v9; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v10; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v11; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v12; // [rsp+50h] [rbp-B0h]
  ULONG ReturnLength; // [rsp+60h] [rbp-A0h] BYREF
  int v14; // [rsp+68h] [rbp-98h] BYREF
  __int16 v15; // [rsp+6Ch] [rbp-94h]
  __int16 v16; // [rsp+6Eh] [rbp-92h]
  unsigned __int16 v17; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v18[526]; // [rsp+A2h] [rbp-5Eh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "SxGetSystemVolumeGlobalPath", 951, 1);
  v17 = 0;
  v2 = 0;
  memset_0(v18, 0, 0x206u);
  ReturnLength = 0;
  if ( !this )
  {
    v14 = -2147024809;
    v4 = 960;
    goto LABEL_18;
  }
  CBsString::Empty(this);
  v14 = 0;
  v15 = 960;
  v3 = NtQuerySystemInformation(MaxSystemInfoClass, 0, 0, &ReturnLength);
  if ( v3 < 0 && v3 != -1073741789 && v3 != -2147483643 && v3 != -1073741820 )
  {
    v14 = HRESULTFromNTSTATUS((unsigned int)v3);
    v4 = 972;
    if ( v14 < 0 )
    {
LABEL_18:
      v16 = v4;
      goto LABEL_19;
    }
    v15 = 972;
  }
  v2 = (const unsigned __int16 **)CoTaskMemAlloc(ReturnLength);
  v4 = 981;
  if ( !v2 )
  {
    v14 = -2147024882;
    goto LABEL_18;
  }
  v14 = 0;
  v15 = 981;
  v5 = NtQuerySystemInformation(MaxSystemInfoClass, v2, ReturnLength, &ReturnLength);
  v14 = HRESULTFromNTSTATUS(v5);
  v4 = 986;
  if ( v14 < 0 )
    goto LABEL_18;
  v15 = 986;
  if ( (unsigned __int64)*(unsigned __int16 *)v2 + 2 > 0x208 )
  {
    v14 = HRESULTFromNTSTATUS(3221225507LL);
    v4 = 990;
    if ( v14 < 0 )
      goto LABEL_18;
    v15 = 990;
  }
  v14 = StringCchCopyNW(&v17, 0x104u, v2[1], (unsigned __int64)*(unsigned __int16 *)v2 >> 1);
  v4 = 995;
  if ( v14 < 0 )
    goto LABEL_18;
  v15 = 995;
  v14 = CBsString::SetPath(this, L"\\\\?\\GLOBALROOT", &v17, L"\\", 0, 0, v8, v9, v10, v11, v12);
  v4 = 1002;
  if ( v14 < 0 )
    goto LABEL_18;
  v15 = 1002;
LABEL_19:
  CoTaskMemFree(v2);
  v6 = v14;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return v6;
}

```

## disassembly

```asm
0x180091be0  mov     [rsp-8+arg_8], rbx
0x180091be5  mov     [rsp-8+arg_10], rdi
0x180091bea  push    rbp
0x180091beb  lea     rbp, [rsp-1C0h]
0x180091bf3  sub     rsp, 2C0h
0x180091bfa  mov     rax, cs:__security_cookie
0x180091c01  xor     rax, rsp
0x180091c04  mov     [rbp+1C0h+var_10], rax
0x180091c0b  mov     rdi, rcx
0x180091c0e  lea     rdx, aSxgetsystemvol_0; "SxGetSystemVolumeGlobalPath"
0x180091c15  lea     rcx, [rsp+2C0h+var_258]; this
0x180091c1a  mov     r9d, 1; unsigned __int16
0x180091c20  mov     r8d, 3B7h; unsigned __int16
0x180091c26  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180091c2b  xor     eax, eax
0x180091c2d  lea     rcx, [rbp+1C0h+var_21E]; void *
0x180091c31  xor     edx, edx; Val
0x180091c33  mov     [rbp+1C0h+var_220], ax
0x180091c37  mov     r8d, 206h; Size
0x180091c3d  xor     ebx, ebx
0x180091c3f  call    memset_0
0x180091c44  mov     [rsp+2C0h+ReturnLength], ebx
0x180091c48  test    rdi, rdi
0x180091c4b  jz      loc_180091DAC
0x180091c51  mov     rcx, rdi; this
0x180091c54  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180091c59  mov     eax, 3C0h
0x180091c5e  mov     [rsp+2C0h+var_258], ebx
0x180091c62  lea     r9, [rsp+2C0h+ReturnLength]; ReturnLength
0x180091c67  mov     [rsp+2C0h+var_254], ax
0x180091c6c  xor     r8d, r8d; SystemInformationLength
0x180091c6f  lea     ecx, [rbx+62h]; SystemInformationClass
0x180091c72  xor     edx, edx; SystemInformation
0x180091c74  call    cs:__imp_NtQuerySystemInformation
0x180091c7a  test    eax, eax
0x180091c7c  jns     short loc_180091CB0
0x180091c7e  cmp     eax, 0C0000023h
0x180091c83  jz      short loc_180091CB0
0x180091c85  cmp     eax, 80000005h
0x180091c8a  jz      short loc_180091CB0
0x180091c8c  cmp     eax, 0C0000004h
0x180091c91  jz      short loc_180091CB0
0x180091c93  mov     ecx, eax
0x180091c95  call    HRESULTFromNTSTATUS
0x180091c9a  mov     [rsp+2C0h+var_258], eax
0x180091c9e  test    eax, eax
0x180091ca0  mov     eax, 3CCh
0x180091ca5  js      loc_180091DB9
0x180091cab  mov     [rsp+2C0h+var_254], ax
0x180091cb0  mov     ecx, [rsp+2C0h+ReturnLength]; cb
0x180091cb4  call    cs:__imp_CoTaskMemAlloc
0x180091cba  mov     rbx, rax
0x180091cbd  test    rax, rax
0x180091cc0  mov     eax, 3D5h
0x180091cc5  jnz     short loc_180091CD4
0x180091cc7  mov     [rsp+2C0h+var_258], 8007000Eh
0x180091ccf  jmp     loc_180091DB9
0x180091cd4  mov     r8d, [rsp+2C0h+ReturnLength]; SystemInformationLength
0x180091cd9  lea     r9, [rsp+2C0h+ReturnLength]; ReturnLength
0x180091cde  mov     rdx, rbx; SystemInformation
0x180091ce1  mov     [rsp+2C0h+var_258], 0
0x180091ce9  mov     ecx, 62h ; 'b'; SystemInformationClass
0x180091cee  mov     [rsp+2C0h+var_254], ax
0x180091cf3  call    cs:__imp_NtQuerySystemInformation
0x180091cf9  mov     ecx, eax
0x180091cfb  call    HRESULTFromNTSTATUS
0x180091d00  mov     [rsp+2C0h+var_258], eax
0x180091d04  test    eax, eax
0x180091d06  mov     eax, 3DAh
0x180091d0b  js      loc_180091DB9
0x180091d11  mov     [rsp+2C0h+var_254], ax
0x180091d16  movzx   eax, word ptr [rbx]
0x180091d19  add     rax, 2
0x180091d1d  cmp     rax, 208h
0x180091d23  jbe     short loc_180091D41
0x180091d25  mov     ecx, 0C0000023h
0x180091d2a  call    HRESULTFromNTSTATUS
0x180091d2f  mov     [rsp+2C0h+var_258], eax
0x180091d33  test    eax, eax
0x180091d35  mov     eax, 3DEh
0x180091d3a  js      short loc_180091DB9
0x180091d3c  mov     [rsp+2C0h+var_254], ax
0x180091d41  movzx   r9d, word ptr [rbx]
0x180091d45  lea     rcx, [rbp+1C0h+var_220]; unsigned __int16 *
0x180091d49  mov     r8, [rbx+8]; unsigned __int16 *
0x180091d4d  mov     edx, 104h; unsigned __int64
0x180091d52  shr     r9, 1; unsigned __int64
0x180091d55  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180091d5a  mov     [rsp+2C0h+var_258], eax
0x180091d5e  test    eax, eax
0x180091d60  mov     eax, 3E3h
0x180091d65  js      short loc_180091DB9
0x180091d67  mov     [rsp+2C0h+var_298], 0; unsigned __int16 *
0x180091d70  lea     r9, Str; "\\"
0x180091d77  lea     r8, [rbp+1C0h+var_220]; unsigned __int16 *
0x180091d7b  mov     [rsp+2C0h+var_2A0], 0; unsigned __int16 *
0x180091d84  lea     rdx, aGlobalroot; "\\\\?\\GLOBALROOT"
0x180091d8b  mov     [rsp+2C0h+var_254], ax
0x180091d90  mov     rcx, rdi; this
0x180091d93  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180091d98  mov     [rsp+2C0h+var_258], eax
0x180091d9c  test    eax, eax
0x180091d9e  mov     eax, 3EAh
0x180091da3  js      short loc_180091DB9
0x180091da5  mov     [rsp+2C0h+var_254], ax
0x180091daa  jmp     short loc_180091DBE
0x180091dac  mov     [rsp+2C0h+var_258], 80070057h
0x180091db4  mov     eax, 3C0h
0x180091db9  mov     [rsp+2C0h+var_252], ax
0x180091dbe  mov     rcx, rbx; pv
0x180091dc1  call    cs:__imp_CoTaskMemFree
0x180091dc7  mov     ebx, [rsp+2C0h+var_258]
0x180091dcb  lea     rcx, [rsp+2C0h+var_258]; this
0x180091dd0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180091dd5  mov     eax, ebx
0x180091dd7  mov     rcx, [rbp+1C0h+var_10]
0x180091dde  xor     rcx, rsp; StackCookie
0x180091de1  call    __security_check_cookie
0x180091de6  lea     r11, [rsp+2C0h+var_s0]
0x180091dee  mov     rbx, [r11+18h]
0x180091df2  mov     rdi, [r11+20h]
0x180091df6  mov     rsp, r11
0x180091df9  pop     rbp
0x180091dfa  retn
```
