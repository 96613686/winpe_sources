# PrincipalImpl::put_UserId(ushort *)

- ea: `0x180024eb0`
- end: `0x1800250a4`
- name: `?put_UserId@PrincipalImpl@@UEAAJPEAG@Z`
- size: `500`
- prototype: `int(PrincipalImpl *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180024eb0`
- `0x1800250ac`
- `0x1800251e4`
- `0x1800253a8`
- `0x180026120`
- `0x18003c664`
- `0x180052640`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180024f50`
- `msvcrt!_wcsnicmp` at `0x180024f50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024ffa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024ffa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024ef9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024ef9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024fd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024fd1`
- `OLEAUT32!__imp_SysAllocString` at `0x180024f7c`
- `OLEAUT32!__imp_SysAllocString` at `0x180024f7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180024f6d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002507c`
- `OLEAUT32!__imp_SysFreeString` at `0x180024f6d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002507c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002504b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002504b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PrincipalImpl::put_UserId(PrincipalImpl *this, unsigned __int16 *a2)
{
  char *v4; // rbx
  int v5; // r8d
  char *v6; // r9
  OLECHAR *v7; // rcx
  BSTR v8; // rax
  int v9; // r15d
  const unsigned __int16 *v10; // r8
  int *v12; // [rsp+28h] [rbp-E0h]
  char v13[48]; // [rsp+0h] [rbp-108h] BYREF
  int v14; // [rsp+30h] [rbp-D8h] BYREF
  HLOCAL hMem[3]; // [rsp+38h] [rbp-D0h] BYREF
  int v16; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE Sid[72]; // [rsp+58h] [rbp-B0h] BYREF
  int v18; // [rsp+A0h] [rbp-68h]
  wchar_t String2[8]; // [rsp+D0h] [rbp-38h] BYREF

  v4 = (char *)this + 16;
  if ( !this )
    v4 = 0;
  hMem[1] = v4;
  if ( v4 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  try
  {
    hMem[2] = v4;
    v14 = 0;
    if ( a2 )
    {
      wcscpy(String2, L"S-1-");
      if ( *a2 && !_wcsnicmp(a2, String2, 4u) )
        goto LABEL_8;
      ATL::CSid::CSid((ATL::CSid *)&v16);
      v9 = 0;
      hMem[0] = 0;
      *(_QWORD *)String2 = hMem;
      if ( ATL::CSid::LoadAccount((enum _SID_NAME_USE *)&v16, a2, v10)
        && (unsigned int)(v18 - 4) <= 1
        && ConvertSidToStringSidW(Sid, (LPWSTR *)hMem) )
      {
        ATL::CComBSTR::operator=((char *)this + 96);
        v9 = 1;
      }
      LocalFree(hMem[0]);
      ATL::CSid::~CSid((ATL::CSid *)&v16);
      if ( !v9 )
      {
LABEL_8:
        v7 = (OLECHAR *)*((_QWORD *)this + 12);
        if ( a2 != v7 )
        {
          SysFreeString(v7);
          v8 = SysAllocString(a2);
          *((_QWORD *)this + 12) = v8;
          if ( !v8 )
            ATL::PrivateAtlThrow(-2147024882);
        }
      }
    }
    else
    {
      SysFreeString(*((BSTR *)this + 12));
      *((_QWORD *)this + 12) = 0;
    }
  }
  catch ( ... )
  {
    tsched::KnownExceptionToHResult((tsched *)v7, v13, v5, v6, (unsigned __int8)&v14, v12);
  }
  if ( v4 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  return 0;
}

```

## disassembly

```asm
0x180024eb0  mov     [rsp+arg_10], rbx
0x180024eb5  mov     [rsp+arg_18], rsi
0x180024eba  push    rdi
0x180024ebb  push    r14
0x180024ebd  push    r15
0x180024ebf  sub     rsp, 0F0h
0x180024ec6  mov     rax, cs:__security_cookie
0x180024ecd  xor     rax, rsp
0x180024ed0  mov     [rsp+108h+var_28], rax
0x180024ed8  mov     r14, rdx
0x180024edb  mov     rsi, rcx
0x180024ede  lea     rbx, [rcx+10h]
0x180024ee2  xor     eax, eax
0x180024ee4  test    rcx, rcx
0x180024ee7  cmovz   rbx, rax
0x180024eeb  mov     [rsp+108h+var_C8], rbx
0x180024ef0  test    rbx, rbx
0x180024ef3  jz      short loc_180024F05
0x180024ef5  lea     rcx, [rbx+8]; lpCriticalSection
0x180024ef9  call    cs:__imp_EnterCriticalSection
0x180024f00  nop     dword ptr [rax+rax+00h]
0x180024f05  mov     [rsp+108h+var_C0], rbx
0x180024f0a  xor     edi, edi
0x180024f0c  mov     [rsp+108h+var_D8], edi
0x180024f10  test    r14, r14
0x180024f13  jz      loc_180025078
0x180024f19  movsd   xmm0, qword ptr cs:aS1; "S-1-"
0x180024f21  movsd   qword ptr [rsp+108h+String2], xmm0
0x180024f2a  movzx   eax, word ptr cs:aS1+8; ""
0x180024f31  mov     [rsp+108h+var_30], ax
0x180024f39  cmp     [r14], di
0x180024f3d  jz      short loc_180024F9B
0x180024f3f  mov     r8d, 4; MaxCount
0x180024f45  lea     rdx, [rsp+108h+String2]; String2
0x180024f4d  mov     rcx, r14; String1
0x180024f50  call    cs:__imp__wcsnicmp
0x180024f57  nop     dword ptr [rax+rax+00h]
0x180024f5c  test    eax, eax
0x180024f5e  jnz     short loc_180024F9B
0x180024f60  mov     rcx, [rsi+60h]; bstrString
0x180024f64  cmp     r14, rcx
0x180024f67  jz      loc_180024FF1
0x180024f6d  call    cs:__imp_SysFreeString
0x180024f74  nop     dword ptr [rax+rax+00h]
0x180024f79  mov     rcx, r14; psz
0x180024f7c  call    cs:__imp_SysAllocString
0x180024f83  nop     dword ptr [rax+rax+00h]
0x180024f88  mov     [rsi+60h], rax
0x180024f8c  test    rax, rax
0x180024f8f  jnz     short loc_180024FF1
0x180024f91  mov     ecx, 8007000Eh; int
0x180024f96  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180024f9b  lea     rcx, [rsp+108h+var_B8]; this
0x180024fa0  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x180024fa5  nop
0x180024fa6  xor     r15d, r15d
0x180024fa9  mov     [rsp+108h+hMem], r15
0x180024fae  lea     rax, [rsp+108h+hMem]
0x180024fb3  mov     qword ptr [rsp+108h+String2], rax
0x180024fbb  mov     rdx, r14; lpAccountName
0x180024fbe  lea     rcx, [rsp+108h+var_B8]; this
0x180024fc3  call    ?LoadAccount@CSid@ATL@@QEAA_NPEBG0@Z; ATL::CSid::LoadAccount(ushort const *,ushort const *)
0x180024fc8  test    al, al
0x180024fca  jnz     short loc_180025032
0x180024fcc  mov     rcx, [rsp+108h+hMem]; hMem
0x180024fd1  call    cs:__imp_LocalFree
0x180024fd8  nop     dword ptr [rax+rax+00h]
0x180024fdd  nop
0x180024fde  lea     rcx, [rsp+108h+var_B8]; this
0x180024fe3  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x180024fe8  test    r15d, r15d
0x180024feb  jz      loc_180024F60
0x180024ff1  test    rbx, rbx
0x180024ff4  jz      short loc_180025006
0x180024ff6  lea     rcx, [rbx+8]; lpCriticalSection
0x180024ffa  call    cs:__imp_LeaveCriticalSection
0x180025001  nop     dword ptr [rax+rax+00h]
0x180025006  mov     eax, edi
0x180025008  mov     rcx, [rsp+108h+var_28]
0x180025010  xor     rcx, rsp; StackCookie
0x180025013  call    __security_check_cookie
0x180025018  lea     r11, [rsp+108h+var_18]
0x180025020  mov     rbx, [r11+30h]
0x180025024  mov     rsi, [r11+38h]
0x180025028  mov     rsp, r11
0x18002502b  pop     r15
0x18002502d  pop     r14
0x18002502f  pop     rdi
0x180025030  retn
0x180025032  mov     eax, [rsp+108h+var_68]
0x180025039  add     eax, 0FFFFFFFCh
0x18002503c  cmp     eax, 1
0x18002503f  ja      short loc_180024FCC
0x180025041  lea     rdx, [rsp+108h+hMem]; StringSid
0x180025046  lea     rcx, [rsp+108h+Sid]; Sid
0x18002504b  call    cs:__imp_ConvertSidToStringSidW
0x180025052  nop     dword ptr [rax+rax+00h]
0x180025057  test    eax, eax
0x180025059  jz      loc_180024FCC
0x18002505f  mov     rdx, [rsp+108h+hMem]
0x180025064  lea     rcx, [rsi+60h]
0x180025068  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18002506d  mov     r15d, 1
0x180025073  jmp     loc_180024FCC
0x180025078  mov     rcx, [rsi+60h]; bstrString
0x18002507c  call    cs:__imp_SysFreeString
0x180025083  nop     dword ptr [rax+rax+00h]
0x180025088  mov     qword ptr [rsi+60h], 0
0x180025090  jmp     loc_180024FF1
0x180025095  mov     edi, [rsp+108h+var_D8]
0x180025099  mov     rbx, [rsp+108h+var_C8]
0x18002509e  jmp     loc_180024FF1
```
