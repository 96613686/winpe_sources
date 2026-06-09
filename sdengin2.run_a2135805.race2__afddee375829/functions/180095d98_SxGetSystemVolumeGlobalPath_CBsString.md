# SxGetSystemVolumeGlobalPath(CBsString *)

- ea: `0x180095d98`
- end: `0x180095fcc`
- name: `?SxGetSystemVolumeGlobalPath@@YAJPEAVCBsString@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(struct CBsString *this)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x180042170`
- `0x180095b94`

## callees

- `0x18006fd18`
- `0x180072e08`
- `0x180072f14`
- `0x180093698`
- `0x180095d98`
- `0x18009e234`
- `0x18009ea34`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180095e2c`
- `ntdll!NtQuerySystemInformation` at `0x180095eb7`
- `ntdll!NtQuerySystemInformation` at `0x180095e2c`
- `ntdll!NtQuerySystemInformation` at `0x180095eb7`
- `ole32!CoTaskMemFree` at `0x180095f8b`
- `ole32!CoTaskMemFree` at `0x180095f8b`
- `ole32!CoTaskMemAlloc` at `0x180095e72`
- `ole32!CoTaskMemAlloc` at `0x180095e72`

## string_xrefs

- `0x180095dc6`: `SxGetSystemVolumeGlobalPath`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "SxGetSystemVolumeGlobalPath", 0x3B7u, 1u);
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
0x180095d98  mov     [rsp-8+arg_8], rbx
0x180095d9d  mov     [rsp-8+arg_10], rdi
0x180095da2  push    rbp
0x180095da3  lea     rbp, [rsp-1C0h]
0x180095dab  sub     rsp, 2C0h
0x180095db2  mov     rax, cs:__security_cookie
0x180095db9  xor     rax, rsp
0x180095dbc  mov     [rbp+1C0h+var_10], rax
0x180095dc3  mov     rdi, rcx
0x180095dc6  lea     rdx, aSxgetsystemvol_0; "SxGetSystemVolumeGlobalPath"
0x180095dcd  lea     rcx, [rsp+2C0h+var_258]; this
0x180095dd2  mov     r9d, 1; unsigned __int16
0x180095dd8  mov     r8d, 3B7h; unsigned __int16
0x180095dde  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180095de3  xor     eax, eax
0x180095de5  lea     rcx, [rbp+1C0h+var_21E]; void *
0x180095de9  xor     edx, edx; Val
0x180095deb  mov     [rbp+1C0h+var_220], ax
0x180095def  mov     r8d, 206h; Size
0x180095df5  xor     ebx, ebx
0x180095df7  call    memset_0
0x180095dfc  mov     [rsp+2C0h+ReturnLength], ebx
0x180095e00  test    rdi, rdi
0x180095e03  jz      loc_180095F76
0x180095e09  mov     rcx, rdi; this
0x180095e0c  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180095e11  mov     eax, 3C0h
0x180095e16  mov     [rsp+2C0h+var_258], ebx
0x180095e1a  lea     r9, [rsp+2C0h+ReturnLength]; ReturnLength
0x180095e1f  mov     [rsp+2C0h+var_254], ax
0x180095e24  xor     r8d, r8d; SystemInformationLength
0x180095e27  lea     ecx, [rbx+62h]; SystemInformationClass
0x180095e2a  xor     edx, edx; SystemInformation
0x180095e2c  call    cs:__imp_NtQuerySystemInformation
0x180095e33  nop     dword ptr [rax+rax+00h]
0x180095e38  test    eax, eax
0x180095e3a  jns     short loc_180095E6E
0x180095e3c  cmp     eax, 0C0000023h
0x180095e41  jz      short loc_180095E6E
0x180095e43  cmp     eax, 80000005h
0x180095e48  jz      short loc_180095E6E
0x180095e4a  cmp     eax, 0C0000004h
0x180095e4f  jz      short loc_180095E6E
0x180095e51  mov     ecx, eax
0x180095e53  call    HRESULTFromNTSTATUS
0x180095e58  mov     [rsp+2C0h+var_258], eax
0x180095e5c  test    eax, eax
0x180095e5e  mov     eax, 3CCh
0x180095e63  js      loc_180095F83
0x180095e69  mov     [rsp+2C0h+var_254], ax
0x180095e6e  mov     ecx, [rsp+2C0h+ReturnLength]; cb
0x180095e72  call    cs:__imp_CoTaskMemAlloc
0x180095e79  nop     dword ptr [rax+rax+00h]
0x180095e7e  mov     rbx, rax
0x180095e81  test    rax, rax
0x180095e84  mov     eax, 3D5h
0x180095e89  jnz     short loc_180095E98
0x180095e8b  mov     [rsp+2C0h+var_258], 8007000Eh
0x180095e93  jmp     loc_180095F83
0x180095e98  mov     r8d, [rsp+2C0h+ReturnLength]; SystemInformationLength
0x180095e9d  lea     r9, [rsp+2C0h+ReturnLength]; ReturnLength
0x180095ea2  mov     rdx, rbx; SystemInformation
0x180095ea5  mov     [rsp+2C0h+var_258], 0
0x180095ead  mov     ecx, 62h ; 'b'; SystemInformationClass
0x180095eb2  mov     [rsp+2C0h+var_254], ax
0x180095eb7  call    cs:__imp_NtQuerySystemInformation
0x180095ebe  nop     dword ptr [rax+rax+00h]
0x180095ec3  mov     ecx, eax
0x180095ec5  call    HRESULTFromNTSTATUS
0x180095eca  mov     [rsp+2C0h+var_258], eax
0x180095ece  test    eax, eax
0x180095ed0  mov     eax, 3DAh
0x180095ed5  js      loc_180095F83
0x180095edb  mov     [rsp+2C0h+var_254], ax
0x180095ee0  movzx   eax, word ptr [rbx]
0x180095ee3  add     rax, 2
0x180095ee7  cmp     rax, 208h
0x180095eed  jbe     short loc_180095F0B
0x180095eef  mov     ecx, 0C0000023h
0x180095ef4  call    HRESULTFromNTSTATUS
0x180095ef9  mov     [rsp+2C0h+var_258], eax
0x180095efd  test    eax, eax
0x180095eff  mov     eax, 3DEh
0x180095f04  js      short loc_180095F83
0x180095f06  mov     [rsp+2C0h+var_254], ax
0x180095f0b  movzx   r9d, word ptr [rbx]
0x180095f0f  lea     rcx, [rbp+1C0h+var_220]; unsigned __int16 *
0x180095f13  mov     r8, [rbx+8]; unsigned __int16 *
0x180095f17  mov     edx, 104h; unsigned __int64
0x180095f1c  shr     r9, 1; unsigned __int64
0x180095f1f  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180095f24  mov     [rsp+2C0h+var_258], eax
0x180095f28  test    eax, eax
0x180095f2a  mov     eax, 3E3h
0x180095f2f  js      short loc_180095F83
0x180095f31  mov     [rsp+2C0h+var_298], 0; unsigned __int16 *
0x180095f3a  lea     r9, Str; "\\"
0x180095f41  lea     r8, [rbp+1C0h+var_220]; unsigned __int16 *
0x180095f45  mov     [rsp+2C0h+var_2A0], 0; unsigned __int16 *
0x180095f4e  lea     rdx, aGlobalroot; "\\\\?\\GLOBALROOT"
0x180095f55  mov     [rsp+2C0h+var_254], ax
0x180095f5a  mov     rcx, rdi; this
0x180095f5d  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180095f62  mov     [rsp+2C0h+var_258], eax
0x180095f66  test    eax, eax
0x180095f68  mov     eax, 3EAh
0x180095f6d  js      short loc_180095F83
0x180095f6f  mov     [rsp+2C0h+var_254], ax
0x180095f74  jmp     short loc_180095F88
0x180095f76  mov     [rsp+2C0h+var_258], 80070057h
0x180095f7e  mov     eax, 3C0h
0x180095f83  mov     [rsp+2C0h+var_252], ax
0x180095f88  mov     rcx, rbx; pv
0x180095f8b  call    cs:__imp_CoTaskMemFree
0x180095f92  nop     dword ptr [rax+rax+00h]
0x180095f97  mov     ebx, [rsp+2C0h+var_258]
0x180095f9b  lea     rcx, [rsp+2C0h+var_258]; this
0x180095fa0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180095fa5  mov     eax, ebx
0x180095fa7  mov     rcx, [rbp+1C0h+var_10]
0x180095fae  xor     rcx, rsp; StackCookie
0x180095fb1  call    __security_check_cookie
0x180095fb6  lea     r11, [rsp+2C0h+var_s0]
0x180095fbe  mov     rbx, [r11+18h]
0x180095fc2  mov     rdi, [r11+20h]
0x180095fc6  mov     rsp, r11
0x180095fc9  pop     rbp
0x180095fca  retn
```
