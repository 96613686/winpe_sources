# PrincipalImpl::put_UserId(ushort *)

- ea: `0x1800231d0`
- end: `0x180023387`
- name: `?put_UserId@PrincipalImpl@@UEAAJPEAG@Z`
- size: `439`
- prototype: `int(PrincipalImpl *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800231d0`
- `0x180023390`
- `0x1800234b8`
- `0x180023664`
- `0x180024460`
- `0x180039524`
- `0x18004e950`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18002326a`
- `msvcrt!_wcsnicmp` at `0x18002326a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800232f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800232f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023219`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023219`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800232d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800232d5`
- `OLEAUT32!__imp_SysAllocString` at `0x180023286`
- `OLEAUT32!__imp_SysAllocString` at `0x180023286`
- `OLEAUT32!__imp_SysFreeString` at `0x18002327d`
- `OLEAUT32!__imp_SysFreeString` at `0x180023365`
- `OLEAUT32!__imp_SysFreeString` at `0x18002327d`
- `OLEAUT32!__imp_SysFreeString` at `0x180023365`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002333e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002333e`

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
  __int64 v12; // r8
  int *v13; // [rsp+28h] [rbp-E0h]
  char v14[48]; // [rsp+0h] [rbp-108h] BYREF
  int v15; // [rsp+30h] [rbp-D8h] BYREF
  HLOCAL hMem[3]; // [rsp+38h] [rbp-D0h] BYREF
  int v17; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE Sid[72]; // [rsp+58h] [rbp-B0h] BYREF
  int v19; // [rsp+A0h] [rbp-68h]
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
    v15 = 0;
    if ( a2 )
    {
      wcscpy(String2, L"S-1-");
      if ( *a2 && !_wcsnicmp(a2, String2, 4u) )
        goto LABEL_8;
      ATL::CSid::CSid((ATL::CSid *)&v17);
      v9 = 0;
      hMem[0] = 0;
      *(_QWORD *)String2 = hMem;
      if ( ATL::CSid::LoadAccount((enum _SID_NAME_USE *)&v17, a2, v10)
        && (unsigned int)(v19 - 4) <= 1
        && ConvertSidToStringSidW(Sid, (LPWSTR *)hMem) )
      {
        ATL::CComBSTR::operator=((char *)this + 96, hMem[0], v12);
        v9 = 1;
      }
      LocalFree(hMem[0]);
      ATL::CSid::~CSid((ATL::CSid *)&v17);
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
    tsched::KnownExceptionToHResult((tsched *)v7, v14, v5, v6, (unsigned __int8)&v15, v13);
  }
  if ( v4 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  return 0;
}

```

## disassembly

```asm
0x1800231d0  mov     [rsp+arg_10], rbx
0x1800231d5  mov     [rsp+arg_18], rsi
0x1800231da  push    rdi
0x1800231db  push    r14
0x1800231dd  push    r15
0x1800231df  sub     rsp, 0F0h
0x1800231e6  mov     rax, cs:__security_cookie
0x1800231ed  xor     rax, rsp
0x1800231f0  mov     [rsp+108h+var_28], rax
0x1800231f8  mov     r14, rdx
0x1800231fb  mov     rsi, rcx
0x1800231fe  lea     rbx, [rcx+10h]
0x180023202  xor     eax, eax
0x180023204  test    rcx, rcx
0x180023207  cmovz   rbx, rax
0x18002320b  mov     [rsp+108h+var_C8], rbx
0x180023210  test    rbx, rbx
0x180023213  jz      short loc_18002321F
0x180023215  lea     rcx, [rbx+8]; lpCriticalSection
0x180023219  call    cs:__imp_EnterCriticalSection
0x18002321f  mov     [rsp+108h+var_C0], rbx
0x180023224  xor     edi, edi
0x180023226  mov     [rsp+108h+var_D8], edi
0x18002322a  test    r14, r14
0x18002322d  jz      loc_180023361
0x180023233  movsd   xmm0, qword ptr cs:aS1; "S-1-"
0x18002323b  movsd   qword ptr [rsp+108h+String2], xmm0
0x180023244  movzx   eax, word ptr cs:aS1+8; ""
0x18002324b  mov     [rsp+108h+var_30], ax
0x180023253  cmp     [r14], di
0x180023257  jz      short loc_18002329F
0x180023259  mov     r8d, 4; MaxCount
0x18002325f  lea     rdx, [rsp+108h+String2]; String2
0x180023267  mov     rcx, r14; String1
0x18002326a  call    cs:__imp__wcsnicmp
0x180023270  test    eax, eax
0x180023272  jnz     short loc_18002329F
0x180023274  mov     rcx, [rsi+60h]; bstrString
0x180023278  cmp     r14, rcx
0x18002327b  jz      short loc_1800232EB
0x18002327d  call    cs:__imp_SysFreeString
0x180023283  mov     rcx, r14; psz
0x180023286  call    cs:__imp_SysAllocString
0x18002328c  mov     [rsi+60h], rax
0x180023290  test    rax, rax
0x180023293  jnz     short loc_1800232EB
0x180023295  mov     ecx, 8007000Eh; int
0x18002329a  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002329f  lea     rcx, [rsp+108h+var_B8]; this
0x1800232a4  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x1800232a9  nop
0x1800232aa  xor     r15d, r15d
0x1800232ad  mov     [rsp+108h+hMem], r15
0x1800232b2  lea     rax, [rsp+108h+hMem]
0x1800232b7  mov     qword ptr [rsp+108h+String2], rax
0x1800232bf  mov     rdx, r14; lpAccountName
0x1800232c2  lea     rcx, [rsp+108h+var_B8]; this
0x1800232c7  call    ?LoadAccount@CSid@ATL@@QEAA_NPEBG0@Z; ATL::CSid::LoadAccount(ushort const *,ushort const *)
0x1800232cc  test    al, al
0x1800232ce  jnz     short loc_180023325
0x1800232d0  mov     rcx, [rsp+108h+hMem]; hMem
0x1800232d5  call    cs:__imp_LocalFree
0x1800232db  nop
0x1800232dc  lea     rcx, [rsp+108h+var_B8]; this
0x1800232e1  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x1800232e6  test    r15d, r15d
0x1800232e9  jz      short loc_180023274
0x1800232eb  test    rbx, rbx
0x1800232ee  jz      short loc_1800232FA
0x1800232f0  lea     rcx, [rbx+8]; lpCriticalSection
0x1800232f4  call    cs:__imp_LeaveCriticalSection
0x1800232fa  mov     eax, edi
0x1800232fc  mov     rcx, [rsp+108h+var_28]
0x180023304  xor     rcx, rsp; StackCookie
0x180023307  call    __security_check_cookie
0x18002330c  lea     r11, [rsp+108h+var_18]
0x180023314  mov     rbx, [r11+30h]
0x180023318  mov     rsi, [r11+38h]
0x18002331c  mov     rsp, r11
0x18002331f  pop     r15
0x180023321  pop     r14
0x180023323  pop     rdi
0x180023324  retn
0x180023325  mov     eax, [rsp+108h+var_68]
0x18002332c  add     eax, 0FFFFFFFCh
0x18002332f  cmp     eax, 1
0x180023332  ja      short loc_1800232D0
0x180023334  lea     rdx, [rsp+108h+hMem]; StringSid
0x180023339  lea     rcx, [rsp+108h+Sid]; Sid
0x18002333e  call    cs:__imp_ConvertSidToStringSidW
0x180023344  test    eax, eax
0x180023346  jz      short loc_1800232D0
0x180023348  mov     rdx, [rsp+108h+hMem]
0x18002334d  lea     rcx, [rsi+60h]
0x180023351  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180023356  mov     r15d, 1
0x18002335c  jmp     loc_1800232D0
0x180023361  mov     rcx, [rsi+60h]; bstrString
0x180023365  call    cs:__imp_SysFreeString
0x18002336b  mov     qword ptr [rsi+60h], 0
0x180023373  jmp     loc_1800232EB
0x180023378  mov     edi, [rsp+108h+var_D8]
0x18002337c  mov     rbx, [rsp+108h+var_C8]
0x180023381  jmp     loc_1800232EB
```
