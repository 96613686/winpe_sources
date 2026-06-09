# SxGetSystemVolumeGlobalPath(CBsString *)

- ea: `0x1800297ac`
- end: `0x1800299be`
- name: `?SxGetSystemVolumeGlobalPath@@YAJPEAVCBsString@@@Z`
- size: `530`
- prototype: `__int64 __fastcall(struct CBsString *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800295bc`

## callees

- `0x1800268b4`
- `0x1800269ac`
- `0x180026ca0`
- `0x1800297ac`
- `0x18002d778`
- `0x180034f3c`
- `0x180035390`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180029840`
- `ntdll!NtQuerySystemInformation` at `0x1800298bf`
- `ntdll!NtQuerySystemInformation` at `0x180029840`
- `ntdll!NtQuerySystemInformation` at `0x1800298bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029880`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029880`

## string_xrefs

- `0x1800297da`: `SxGetSystemVolumeGlobalPath`

## pseudocode

```c
__int64 __fastcall SxGetSystemVolumeGlobalPath(struct CBsString *this)
{
  const unsigned __int16 **v2; // rbx
  NTSTATUS v3; // eax
  __int16 v4; // ax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  const unsigned __int16 *v10; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v11; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v12; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v13; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v14; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v15; // [rsp+50h] [rbp-B0h]
  ULONG ReturnLength; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+68h] [rbp-98h] BYREF
  __int16 v18; // [rsp+6Ch] [rbp-94h]
  __int16 v19; // [rsp+6Eh] [rbp-92h]
  unsigned __int16 v20; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v21[526]; // [rsp+A2h] [rbp-5Eh] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "SxGetSystemVolumeGlobalPath", 951, 1);
  v20 = 0;
  v2 = 0;
  memset_0(v21, 0, 0x206u);
  ReturnLength = 0;
  if ( !this )
  {
    v17 = -2147024809;
    v4 = 960;
    goto LABEL_18;
  }
  CBsString::Empty(this);
  v17 = 0;
  v18 = 960;
  v3 = NtQuerySystemInformation(MaxSystemInfoClass, 0, 0, &ReturnLength);
  if ( v3 < 0 && v3 != -1073741789 && v3 != -2147483643 && v3 != -1073741820 )
  {
    v17 = HRESULTFromNTSTATUS((unsigned int)v3);
    v4 = 972;
    if ( v17 < 0 )
    {
LABEL_18:
      v19 = v4;
      goto LABEL_19;
    }
    v18 = 972;
  }
  v2 = (const unsigned __int16 **)CoTaskMemAlloc(ReturnLength);
  v4 = 981;
  if ( !v2 )
  {
    v17 = -2147024882;
    goto LABEL_18;
  }
  v17 = 0;
  v18 = 981;
  v5 = NtQuerySystemInformation(MaxSystemInfoClass, v2, ReturnLength, &ReturnLength);
  v17 = HRESULTFromNTSTATUS(v5);
  v4 = 986;
  if ( v17 < 0 )
    goto LABEL_18;
  v18 = 986;
  if ( (unsigned __int64)*(unsigned __int16 *)v2 + 2 > 0x208 )
  {
    v17 = HRESULTFromNTSTATUS(3221225507LL);
    v4 = 990;
    if ( v17 < 0 )
      goto LABEL_18;
    v18 = 990;
  }
  v17 = StringCchCopyNW(&v20, 0x104u, v2[1], (unsigned __int64)*(unsigned __int16 *)v2 >> 1);
  v4 = 995;
  if ( v17 < 0 )
    goto LABEL_18;
  v18 = 995;
  v17 = CBsString::SetPath(this, L"\\\\?\\GLOBALROOT", &v20, L"\\", 0, v10, v11, v12, v13, v14, v15);
  v4 = 1002;
  if ( v17 < 0 )
    goto LABEL_18;
  v18 = 1002;
LABEL_19:
  CoTaskMemFree(v2);
  v6 = v17;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17, v7, v8);
  return v6;
}

```

## disassembly

```asm
0x1800297ac  mov     [rsp-8+arg_8], rbx
0x1800297b1  mov     [rsp-8+arg_10], rdi
0x1800297b6  push    rbp
0x1800297b7  lea     rbp, [rsp-1C0h]
0x1800297bf  sub     rsp, 2C0h
0x1800297c6  mov     rax, cs:__security_cookie
0x1800297cd  xor     rax, rsp
0x1800297d0  mov     [rbp+1C0h+var_10], rax
0x1800297d7  mov     rdi, rcx
0x1800297da  lea     rdx, aSxgetsystemvol_0; "SxGetSystemVolumeGlobalPath"
0x1800297e1  lea     rcx, [rsp+2C0h+var_258]; this
0x1800297e6  mov     r9d, 1; unsigned __int16
0x1800297ec  mov     r8d, 3B7h; unsigned __int16
0x1800297f2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800297f7  xor     eax, eax
0x1800297f9  lea     rcx, [rbp+1C0h+var_21E]; void *
0x1800297fd  xor     edx, edx; Val
0x1800297ff  mov     [rbp+1C0h+var_220], ax
0x180029803  mov     r8d, 206h; Size
0x180029809  xor     ebx, ebx
0x18002980b  call    memset_0
0x180029810  mov     [rsp+2C0h+ReturnLength], ebx
0x180029814  test    rdi, rdi
0x180029817  jz      loc_18002996F
0x18002981d  mov     rcx, rdi; this
0x180029820  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180029825  mov     eax, 3C0h
0x18002982a  mov     [rsp+2C0h+var_258], ebx
0x18002982e  lea     r9, [rsp+2C0h+ReturnLength]; ReturnLength
0x180029833  mov     [rsp+2C0h+var_254], ax
0x180029838  xor     r8d, r8d; SystemInformationLength
0x18002983b  lea     ecx, [rbx+62h]; SystemInformationClass
0x18002983e  xor     edx, edx; SystemInformation
0x180029840  call    cs:__imp_NtQuerySystemInformation
0x180029846  test    eax, eax
0x180029848  jns     short loc_18002987C
0x18002984a  cmp     eax, 0C0000023h
0x18002984f  jz      short loc_18002987C
0x180029851  cmp     eax, 80000005h
0x180029856  jz      short loc_18002987C
0x180029858  cmp     eax, 0C0000004h
0x18002985d  jz      short loc_18002987C
0x18002985f  mov     ecx, eax
0x180029861  call    HRESULTFromNTSTATUS
0x180029866  mov     [rsp+2C0h+var_258], eax
0x18002986a  test    eax, eax
0x18002986c  mov     eax, 3CCh
0x180029871  js      loc_18002997C
0x180029877  mov     [rsp+2C0h+var_254], ax
0x18002987c  mov     ecx, [rsp+2C0h+ReturnLength]; cb
0x180029880  call    cs:__imp_CoTaskMemAlloc
0x180029886  mov     rbx, rax
0x180029889  test    rax, rax
0x18002988c  mov     eax, 3D5h
0x180029891  jnz     short loc_1800298A0
0x180029893  mov     [rsp+2C0h+var_258], 8007000Eh
0x18002989b  jmp     loc_18002997C
0x1800298a0  mov     r8d, [rsp+2C0h+ReturnLength]; SystemInformationLength
0x1800298a5  lea     r9, [rsp+2C0h+ReturnLength]; ReturnLength
0x1800298aa  mov     rdx, rbx; SystemInformation
0x1800298ad  mov     [rsp+2C0h+var_258], 0
0x1800298b5  mov     ecx, 62h ; 'b'; SystemInformationClass
0x1800298ba  mov     [rsp+2C0h+var_254], ax
0x1800298bf  call    cs:__imp_NtQuerySystemInformation
0x1800298c5  mov     ecx, eax
0x1800298c7  call    HRESULTFromNTSTATUS
0x1800298cc  mov     [rsp+2C0h+var_258], eax
0x1800298d0  test    eax, eax
0x1800298d2  mov     eax, 3DAh
0x1800298d7  js      loc_18002997C
0x1800298dd  mov     [rsp+2C0h+var_254], ax
0x1800298e2  movzx   eax, word ptr [rbx]
0x1800298e5  add     rax, 2
0x1800298e9  cmp     rax, 208h
0x1800298ef  jbe     short loc_18002990D
0x1800298f1  mov     ecx, 0C0000023h
0x1800298f6  call    HRESULTFromNTSTATUS
0x1800298fb  mov     [rsp+2C0h+var_258], eax
0x1800298ff  test    eax, eax
0x180029901  mov     eax, 3DEh
0x180029906  js      short loc_18002997C
0x180029908  mov     [rsp+2C0h+var_254], ax
0x18002990d  movzx   r9d, word ptr [rbx]
0x180029911  lea     rcx, [rbp+1C0h+var_220]; unsigned __int16 *
0x180029915  mov     r8, [rbx+8]; unsigned __int16 *
0x180029919  mov     edx, 104h; unsigned __int64
0x18002991e  shr     r9, 1; unsigned __int64
0x180029921  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180029926  mov     [rsp+2C0h+var_258], eax
0x18002992a  test    eax, eax
0x18002992c  mov     eax, 3E3h
0x180029931  js      short loc_18002997C
0x180029933  lea     r9, asc_18003A0A0; "\\"
0x18002993a  mov     [rsp+2C0h+var_254], ax
0x18002993f  lea     r8, [rbp+1C0h+var_220]; unsigned __int16 *
0x180029943  mov     [rsp+2C0h+var_2A0], 0; unsigned __int16 *
0x18002994c  lea     rdx, aGlobalroot; "\\\\?\\GLOBALROOT"
0x180029953  mov     rcx, rdi; this
0x180029956  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18002995b  mov     [rsp+2C0h+var_258], eax
0x18002995f  test    eax, eax
0x180029961  mov     eax, 3EAh
0x180029966  js      short loc_18002997C
0x180029968  mov     [rsp+2C0h+var_254], ax
0x18002996d  jmp     short loc_180029981
0x18002996f  mov     [rsp+2C0h+var_258], 80070057h
0x180029977  mov     eax, 3C0h
0x18002997c  mov     [rsp+2C0h+var_252], ax
0x180029981  mov     rcx, rbx; pv
0x180029984  call    cs:__imp_CoTaskMemFree
0x18002998a  mov     ebx, [rsp+2C0h+var_258]
0x18002998e  lea     rcx, [rsp+2C0h+var_258]; this
0x180029993  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180029998  mov     eax, ebx
0x18002999a  mov     rcx, [rbp+1C0h+var_10]
0x1800299a1  xor     rcx, rsp; StackCookie
0x1800299a4  call    __security_check_cookie
0x1800299a9  lea     r11, [rsp+2C0h+var_s0]
0x1800299b1  mov     rbx, [r11+18h]
0x1800299b5  mov     rdi, [r11+20h]
0x1800299b9  mov     rsp, r11
0x1800299bc  pop     rbp
0x1800299bd  retn
```
