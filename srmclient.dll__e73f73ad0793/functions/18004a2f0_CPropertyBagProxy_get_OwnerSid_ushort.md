# CPropertyBagProxy::get_OwnerSid(ushort * *)

- ea: `0x18004a2f0`
- end: `0x18004a510`
- name: `?get_OwnerSid@CPropertyBagProxy@@UEAAJPEAPEAG@Z`
- size: `544`
- prototype: `__int64 __fastcall(CPropertyBagProxy *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callees

- `0x1800020ba`
- `0x18004a2f0`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18004a3f9`
- `ole32!CoTaskMemFree` at `0x18004a3f9`
- `OLEAUT32!__imp_SysAllocString` at `0x18004a460`
- `OLEAUT32!__imp_SysAllocString` at `0x18004a460`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a3ed`
- `OLEAUT32!__imp_SysFreeString` at `0x18004a3ed`
- `KERNEL32!GetLastError` at `0x18004a480`
- `KERNEL32!GetLastError` at `0x18004a488`
- `KERNEL32!GetLastError` at `0x18004a480`
- `KERNEL32!GetLastError` at `0x18004a488`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18004a3bc`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18004a3bc`

## string_xrefs

- `0x18004a329`: `base\fs\fsrm\service\modulewrp\propertybagproxy.cpp`
- `0x18004a4cf`: `L"ConvertSidToStringSid"`
- `0x18004a335`: `CPropertyBagProxy::get_OwnerSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CPropertyBagProxy::get_OwnerSid(CPropertyBagProxy *this, unsigned __int16 **a2)
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
  v15[0] = L"base\\fs\\fsrm\\service\\modulewrp\\propertybagproxy.cpp";
  v15[1] = L"CPropertyBagProxy::get_OwnerSid";
  v15[2] = L"PROPBGPC";
  v16 = 380;
  v17 = 22;
  v18 = 255;
  v20 = 0x1000000;
  memset_0(v19, 0, sizeof(v19));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v21, (const struct CSrmDebugInfo *)v15, 0);
  StringSid = 0;
  if ( !ConvertSidToStringSidW((PSID)(*((_QWORD *)this + 9) + 136LL), &StringSid) )
  {
    LastError = GetLastError();
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    v13 = (unsigned __int16 *)v15;
    v10 = CSrmDebugInfo::CSrmDebugInfo(
            (__int64)v15,
            (__int64)L"base\\fs\\fsrm\\service\\modulewrp\\propertybagproxy.cpp",
            (__int64)L"PROPBGPC",
            (__int64)L"CPropertyBagProxy::get_OwnerSid",
            387,
            24);
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
0x18004a2f0  mov     [rsp+arg_10], rbx
0x18004a2f5  mov     [rsp+arg_18], rdi
0x18004a2fa  push    r12
0x18004a2fc  push    r14
0x18004a2fe  push    r15
0x18004a300  sub     rsp, 1C0h
0x18004a307  mov     rax, cs:__security_cookie
0x18004a30e  xor     rax, rsp
0x18004a311  mov     [rsp+1D8h+var_28], rax
0x18004a319  mov     rbx, rdx
0x18004a31c  mov     rdi, rcx
0x18004a31f  lea     rax, [rsp+1D8h+var_170]
0x18004a324  mov     [rsp+1D8h+var_190], rax
0x18004a329  lea     r14, aBaseFsFsrmServ_8; "base\\fs\\fsrm\\service\\modulewrp\\pro"...
0x18004a330  mov     [rsp+1D8h+var_170], r14
0x18004a335  lea     r15, aCpropertybagpr_19; "CPropertyBagProxy::get_OwnerSid"
0x18004a33c  mov     [rsp+1D8h+var_168], r15
0x18004a341  lea     r12, aPropbgpc; "PROPBGPC"
0x18004a348  mov     [rsp+1D8h+var_160], r12
0x18004a34d  mov     [rsp+1D8h+var_158], 17Ch
0x18004a358  mov     [rsp+1D8h+var_154], 16h
0x18004a363  mov     [rsp+1D8h+var_150], 0FFh
0x18004a36e  mov     [rsp+1D8h+var_E8], 1000000h
0x18004a379  xor     edx, edx; Val
0x18004a37b  lea     r8d, [rdx+60h]; Size
0x18004a37f  lea     rcx, [rsp+1D8h+var_148]; void *
0x18004a387  call    memset_0
0x18004a38c  nop
0x18004a38d  xor     r8d, r8d
0x18004a390  lea     rdx, [rsp+1D8h+var_170]
0x18004a395  lea     rcx, [rsp+1D8h+var_D8]
0x18004a39d  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18004a3a2  nop
0x18004a3a3  mov     [rsp+1D8h+StringSid], 0
0x18004a3ac  mov     rcx, [rdi+48h]
0x18004a3b0  add     rcx, 88h; Sid
0x18004a3b7  lea     rdx, [rsp+1D8h+StringSid]; StringSid
0x18004a3bc  call    cs:__imp_ConvertSidToStringSidW
0x18004a3c2  test    eax, eax
0x18004a3c4  jz      loc_18004A480
0x18004a3ca  mov     rcx, [rsp+1D8h+StringSid]; psz
0x18004a3cf  test    rcx, rcx
0x18004a3d2  jnz     loc_18004A460
0x18004a3d8  xor     eax, eax
0x18004a3da  mov     [rsp+1D8h+var_190], rax
0x18004a3df  mov     [rsp+1D8h+var_190], 0
0x18004a3e8  mov     [rbx], rax
0x18004a3eb  xor     ecx, ecx; bstrString
0x18004a3ed  call    cs:__imp_SysFreeString
0x18004a3f3  nop
0x18004a3f4  mov     rcx, [rsp+1D8h+StringSid]; pv
0x18004a3f9  call    cs:__imp_CoTaskMemFree
0x18004a3ff  mov     [rsp+1D8h+StringSid], 0
0x18004a408  mov     [rsp+1D8h+StringSid], 0
0x18004a411  mov     ebx, [rsp+1D8h+var_D0]
0x18004a418  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18004a41f  mov     [rsp+1D8h+var_D8], rax
0x18004a427  lea     rcx, [rsp+1D8h+var_D8]; this
0x18004a42f  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18004a434  mov     eax, ebx
0x18004a436  mov     rcx, [rsp+1D8h+var_28]
0x18004a43e  xor     rcx, rsp; StackCookie
0x18004a441  call    __security_check_cookie
0x18004a446  lea     r11, [rsp+1D8h+var_18]
0x18004a44e  mov     rbx, [r11+30h]
0x18004a452  mov     rdi, [r11+38h]
0x18004a456  mov     rsp, r11
0x18004a459  pop     r15
0x18004a45b  pop     r14
0x18004a45d  pop     r12
0x18004a45f  retn
0x18004a460  call    cs:__imp_SysAllocString
0x18004a466  nop
0x18004a467  mov     [rsp+1D8h+var_190], rax
0x18004a46c  test    rax, rax
0x18004a46f  jz      loc_18004A4F5
0x18004a475  jmp     loc_18004A3DF
0x18004a47a  jmp     short loc_18004A411
0x18004a47c  jmp     short loc_18004A411
0x18004a47e  jmp     short loc_18004A411
0x18004a480  call    cs:__imp_GetLastError
0x18004a486  mov     edi, eax
0x18004a488  call    cs:__imp_GetLastError
0x18004a48e  mov     ebx, eax
0x18004a490  test    eax, eax
0x18004a492  jle     short loc_18004A49D
0x18004a494  movzx   ebx, ax
0x18004a497  or      ebx, 80070000h
0x18004a49d  lea     rax, [rsp+1D8h+var_170]
0x18004a4a2  mov     [rsp+1D8h+var_190], rax
0x18004a4a7  mov     dword ptr [rsp+1D8h+var_1B0], 18h
0x18004a4af  mov     dword ptr [rsp+1D8h+var_1B8], 183h
0x18004a4b7  mov     r9, r15
0x18004a4ba  mov     r8, r12
0x18004a4bd  mov     rdx, r14
0x18004a4c0  lea     rcx, [rsp+1D8h+var_170]
0x18004a4c5  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18004a4ca  nop
0x18004a4cb  mov     dword ptr [rsp+1D8h+var_1B0], edi
0x18004a4cf  lea     rcx, aLConvertsidtos; "L\"ConvertSidToStringSid\""
0x18004a4d6  mov     [rsp+1D8h+var_1B8], rcx
0x18004a4db  lea     r9, aWin32CallSFail; "Win32 call %s failed [GetLastError() = "...
0x18004a4e2  mov     r8d, ebx
0x18004a4e5  mov     rdx, rax
0x18004a4e8  lea     rcx, [rsp+1D8h+var_D8]
0x18004a4f0  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x18004a4f5  mov     [rsp+1D8h+pExceptionObject], 8007000Eh
0x18004a4fd  lea     rdx, _TI1J; pThrowInfo
0x18004a504  lea     rcx, [rsp+1D8h+pExceptionObject]; pExceptionObject
0x18004a509  call    _CxxThrowException_0
```
