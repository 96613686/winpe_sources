# CPropertyBag::get_OwnerSid(ushort * *)

- ea: `0x180091d20`
- end: `0x180091f40`
- name: `?get_OwnerSid@CPropertyBag@@UEAAJPEAPEAG@Z`
- size: `544`
- prototype: `__int64 __fastcall(CPropertyBag *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callees

- `0x1800020ba`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x180091d20`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180091e29`
- `ole32!CoTaskMemFree` at `0x180091e29`
- `OLEAUT32!__imp_SysAllocString` at `0x180091e90`
- `OLEAUT32!__imp_SysAllocString` at `0x180091e90`
- `OLEAUT32!__imp_SysFreeString` at `0x180091e1d`
- `OLEAUT32!__imp_SysFreeString` at `0x180091e1d`
- `KERNEL32!GetLastError` at `0x180091eb0`
- `KERNEL32!GetLastError` at `0x180091eb8`
- `KERNEL32!GetLastError` at `0x180091eb0`
- `KERNEL32!GetLastError` at `0x180091eb8`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180091dec`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180091dec`

## string_xrefs

- `0x180091eff`: `L"ConvertSidToStringSid"`
- `0x180091d59`: `base\fs\fsrm\service\pipeline\propertybag.cpp`
- `0x180091d65`: `CPropertyBag::get_OwnerSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CPropertyBag::get_OwnerSid(CPropertyBag *this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rax
  unsigned int v5; // ebx
  DWORD LastError; // edi
  signed int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // [rsp+28h] [rbp-1B0h]
  LPWSTR StringSid; // [rsp+40h] [rbp-198h] BYREF
  unsigned __int16 *v13; // [rsp+48h] [rbp-190h]
  int pExceptionObject; // [rsp+50h] [rbp-188h] BYREF
  _QWORD v15[3]; // [rsp+68h] [rbp-170h] BYREF
  int v16; // [rsp+80h] [rbp-158h]
  int v17; // [rsp+84h] [rbp-154h]
  int v18; // [rsp+88h] [rbp-150h]
  _BYTE v19[96]; // [rsp+90h] [rbp-148h] BYREF
  int v20; // [rsp+F0h] [rbp-E8h]
  void **v21; // [rsp+100h] [rbp-D8h] BYREF
  unsigned int v22; // [rsp+108h] [rbp-D0h]

  v13 = (unsigned __int16 *)v15;
  v15[0] = L"base\\fs\\fsrm\\service\\pipeline\\propertybag.cpp";
  v15[1] = L"CPropertyBag::get_OwnerSid";
  v15[2] = L"PROPBAGC";
  v16 = 393;
  v17 = 22;
  v18 = 255;
  v20 = 0x1000000;
  memset_0(v19, 0, sizeof(v19));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v21, (const struct CSrmDebugInfo *)v15, 0);
  StringSid = 0;
  if ( !ConvertSidToStringSidW((PSID)(*((_QWORD *)this + 10) + 136LL), &StringSid) )
  {
    LastError = GetLastError();
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    v13 = (unsigned __int16 *)v15;
    v10 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v15,
            (__int64)L"base\\fs\\fsrm\\service\\pipeline\\propertybag.cpp",
            (__int64)L"PROPBAGC",
            (__int64)L"CPropertyBag::get_OwnerSid",
            400,
            22);
    LODWORD(v11) = LastError;
    CSrmFunctionTracer::Throw(
      &v21,
      v10,
      v9,
      L"Win32 call %s failed [GetLastError() = %u]",
      "L\"ConvertSidToStringSid\"",
      v11);
  }
  if ( StringSid )
  {
    v4 = SysAllocString(StringSid);
    v13 = v4;
    if ( !v4 )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
  }
  else
  {
    v4 = 0;
    v13 = 0;
  }
  v13 = 0;
  *a2 = v4;
  SysFreeString(0);
  CoTaskMemFree(StringSid);
  StringSid = 0;
  v5 = v22;
  v21 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v21);
  return v5;
}

```

## disassembly

```asm
0x180091d20  mov     [rsp+arg_10], rbx
0x180091d25  mov     [rsp+arg_18], rdi
0x180091d2a  push    r12
0x180091d2c  push    r14
0x180091d2e  push    r15
0x180091d30  sub     rsp, 1C0h
0x180091d37  mov     rax, cs:__security_cookie
0x180091d3e  xor     rax, rsp
0x180091d41  mov     [rsp+1D8h+var_28], rax
0x180091d49  mov     rbx, rdx
0x180091d4c  mov     rdi, rcx
0x180091d4f  lea     rax, [rsp+1D8h+var_170]
0x180091d54  mov     [rsp+1D8h+var_190], rax
0x180091d59  lea     r14, aBaseFsFsrmServ_26; "base\\fs\\fsrm\\service\\pipeline\\prop"...
0x180091d60  mov     [rsp+1D8h+var_170], r14
0x180091d65  lea     r15, aCpropertybagGe; "CPropertyBag::get_OwnerSid"
0x180091d6c  mov     [rsp+1D8h+var_168], r15
0x180091d71  lea     r12, aPropbagc; "PROPBAGC"
0x180091d78  mov     [rsp+1D8h+var_160], r12
0x180091d7d  mov     [rsp+1D8h+var_158], 189h
0x180091d88  mov     [rsp+1D8h+var_154], 16h
0x180091d93  mov     [rsp+1D8h+var_150], 0FFh
0x180091d9e  mov     [rsp+1D8h+var_E8], 1000000h
0x180091da9  xor     edx, edx; Val
0x180091dab  lea     r8d, [rdx+60h]; Size
0x180091daf  lea     rcx, [rsp+1D8h+var_148]; void *
0x180091db7  call    memset_0
0x180091dbc  nop
0x180091dbd  xor     r8d, r8d
0x180091dc0  lea     rdx, [rsp+1D8h+var_170]
0x180091dc5  lea     rcx, [rsp+1D8h+var_D8]
0x180091dcd  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180091dd2  nop
0x180091dd3  mov     [rsp+1D8h+StringSid], 0
0x180091ddc  mov     rcx, [rdi+50h]
0x180091de0  add     rcx, 88h; Sid
0x180091de7  lea     rdx, [rsp+1D8h+StringSid]; StringSid
0x180091dec  call    cs:__imp_ConvertSidToStringSidW
0x180091df2  test    eax, eax
0x180091df4  jz      loc_180091EB0
0x180091dfa  mov     rcx, [rsp+1D8h+StringSid]; psz
0x180091dff  test    rcx, rcx
0x180091e02  jnz     loc_180091E90
0x180091e08  xor     eax, eax
0x180091e0a  mov     [rsp+1D8h+var_190], rax
0x180091e0f  mov     [rsp+1D8h+var_190], 0
0x180091e18  mov     [rbx], rax
0x180091e1b  xor     ecx, ecx; bstrString
0x180091e1d  call    cs:__imp_SysFreeString
0x180091e23  nop
0x180091e24  mov     rcx, [rsp+1D8h+StringSid]; pv
0x180091e29  call    cs:__imp_CoTaskMemFree
0x180091e2f  mov     [rsp+1D8h+StringSid], 0
0x180091e38  mov     [rsp+1D8h+StringSid], 0
0x180091e41  mov     ebx, [rsp+1D8h+var_D0]
0x180091e48  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180091e4f  mov     [rsp+1D8h+var_D8], rax
0x180091e57  lea     rcx, [rsp+1D8h+var_D8]; this
0x180091e5f  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180091e64  mov     eax, ebx
0x180091e66  mov     rcx, [rsp+1D8h+var_28]
0x180091e6e  xor     rcx, rsp; StackCookie
0x180091e71  call    __security_check_cookie
0x180091e76  lea     r11, [rsp+1D8h+var_18]
0x180091e7e  mov     rbx, [r11+30h]
0x180091e82  mov     rdi, [r11+38h]
0x180091e86  mov     rsp, r11
0x180091e89  pop     r15
0x180091e8b  pop     r14
0x180091e8d  pop     r12
0x180091e8f  retn
0x180091e90  call    cs:__imp_SysAllocString
0x180091e96  nop
0x180091e97  mov     [rsp+1D8h+var_190], rax
0x180091e9c  test    rax, rax
0x180091e9f  jz      loc_180091F25
0x180091ea5  jmp     loc_180091E0F
0x180091eaa  jmp     short loc_180091E41
0x180091eac  jmp     short loc_180091E41
0x180091eae  jmp     short loc_180091E41
0x180091eb0  call    cs:__imp_GetLastError
0x180091eb6  mov     edi, eax
0x180091eb8  call    cs:__imp_GetLastError
0x180091ebe  mov     ebx, eax
0x180091ec0  test    eax, eax
0x180091ec2  jle     short loc_180091ECD
0x180091ec4  movzx   ebx, ax
0x180091ec7  or      ebx, 80070000h
0x180091ecd  lea     rax, [rsp+1D8h+var_170]
0x180091ed2  mov     [rsp+1D8h+var_190], rax
0x180091ed7  mov     dword ptr [rsp+1D8h+var_1B0], 16h
0x180091edf  mov     dword ptr [rsp+1D8h+var_1B8], 190h
0x180091ee7  mov     r9, r15
0x180091eea  mov     r8, r12
0x180091eed  mov     rdx, r14
0x180091ef0  lea     rcx, [rsp+1D8h+var_170]
0x180091ef5  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x180091efa  nop
0x180091efb  mov     dword ptr [rsp+1D8h+var_1B0], edi
0x180091eff  lea     rcx, aLConvertsidtos; "L\"ConvertSidToStringSid\""
0x180091f06  mov     [rsp+1D8h+var_1B8], rcx
0x180091f0b  lea     r9, aWin32CallSFail; "Win32 call %s failed [GetLastError() = "...
0x180091f12  mov     r8d, ebx
0x180091f15  mov     rdx, rax
0x180091f18  lea     rcx, [rsp+1D8h+var_D8]
0x180091f20  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x180091f25  mov     [rsp+1D8h+pExceptionObject], 8007000Eh
0x180091f2d  lea     rdx, _TI1J; pThrowInfo
0x180091f34  lea     rcx, [rsp+1D8h+pExceptionObject]; pExceptionObject
0x180091f39  call    _CxxThrowException_0
```
