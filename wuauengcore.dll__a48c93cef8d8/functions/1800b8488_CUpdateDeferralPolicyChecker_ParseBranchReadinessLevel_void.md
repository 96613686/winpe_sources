# CUpdateDeferralPolicyChecker::ParseBranchReadinessLevel(void)

- ea: `0x1800b8488`
- end: `0x1800b86a2`
- name: `?ParseBranchReadinessLevel@CUpdateDeferralPolicyChecker@@AEAAXXZ`
- size: `538`
- prototype: `void __fastcall(CUpdateDeferralPolicyChecker *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b67b0`

## callees

- `0x1800b8488`
- `0x18012b618`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b84d5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b851f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b8565`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b85af`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b85f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b8643`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b84d5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b851f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b8565`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b85af`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b85f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b8643`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b849e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b84b4`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b84f0`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b84fe`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b8536`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b8544`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b8580`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b858e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b85ca`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b85d8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b8614`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b8622`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b849e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b84b4`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b84f0`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b84fe`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b8536`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b8544`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b8580`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b858e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b85ca`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b85d8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b8614`
- `OLEAUT32!__imp_SysStringLen` at `0x1800b8622`

## string_xrefs

- `0x1800b8667`: `Unknown value for "BranchReadinessLevel" = "%ws"`

## pseudocode

```c
void __fastcall CUpdateDeferralPolicyChecker::ParseBranchReadinessLevel(CUpdateDeferralPolicyChecker *this)
{
  UINT cchCount2; // eax
  UINT v3; // eax
  UINT v4; // eax
  UINT v5; // eax
  UINT v6; // eax
  UINT v7; // eax

  if ( SysStringLen(*((BSTR *)this + 2))
    && (cchCount2 = SysStringLen(*((BSTR *)this + 2)),
        CompareStringW(0x400u, 0, L"CB", -1, *((PCNZWCH *)this + 2), cchCount2) == 2) )
  {
    *((_DWORD *)this + 3) = 16;
  }
  else if ( SysStringLen(*((BSTR *)this + 2))
         && (v3 = SysStringLen(*((BSTR *)this + 2)),
             CompareStringW(0x400u, 0, L"WIF", -1, *((PCNZWCH *)this + 2), v3) == 2) )
  {
    *((_DWORD *)this + 3) = 2;
  }
  else if ( SysStringLen(*((BSTR *)this + 2))
         && (v4 = SysStringLen(*((BSTR *)this + 2)),
             CompareStringW(0x400u, 0, L"WIS", -1, *((PCNZWCH *)this + 2), v4) == 2) )
  {
    *((_DWORD *)this + 3) = 4;
  }
  else if ( SysStringLen(*((BSTR *)this + 2))
         && (v5 = SysStringLen(*((BSTR *)this + 2)),
             CompareStringW(0x400u, 0, L"RP", -1, *((PCNZWCH *)this + 2), v5) == 2) )
  {
    *((_DWORD *)this + 3) = 8;
  }
  else if ( SysStringLen(*((BSTR *)this + 2))
         && (v6 = SysStringLen(*((BSTR *)this + 2)),
             CompareStringW(0x400u, 0, L"RPQU", -1, *((PCNZWCH *)this + 2), v6) == 2) )
  {
    *((_DWORD *)this + 3) = 64;
  }
  else if ( SysStringLen(*((BSTR *)this + 2))
         && (v7 = SysStringLen(*((BSTR *)this + 2)),
             CompareStringW(0x400u, 0, L"Canary", -1, *((PCNZWCH *)this + 2), v7) == 2) )
  {
    *((_DWORD *)this + 3) = 128;
  }
  else
  {
    if ( *((_QWORD *)this + 2) )
      WUTrace(0, 0, 1, 3, 0, L"Unknown value for \"BranchReadinessLevel\" = \"%ws\"", *((_QWORD *)this + 2));
    *((_DWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x1800b8488  mov     [rsp+arg_0], rbx
0x1800b848d  mov     [rsp+arg_8], rbp
0x1800b8492  push    rsi
0x1800b8493  sub     rsp, 40h
0x1800b8497  mov     rbx, rcx
0x1800b849a  mov     rcx, [rcx+10h]; pbstr
0x1800b849e  call    cs:__imp_SysStringLen
0x1800b84a4  or      esi, 0FFFFFFFFh
0x1800b84a7  mov     ebp, 400h
0x1800b84ac  test    eax, eax
0x1800b84ae  jz      short loc_1800B84EC
0x1800b84b0  mov     rcx, [rbx+10h]; pbstr
0x1800b84b4  call    cs:__imp_SysStringLen
0x1800b84ba  mov     [rsp+48h+cchCount2], eax; cchCount2
0x1800b84be  mov     r9d, esi; cchCount1
0x1800b84c1  mov     rax, [rbx+10h]
0x1800b84c5  lea     r8, aCb; "CB"
0x1800b84cc  xor     edx, edx; dwCmpFlags
0x1800b84ce  mov     [rsp+48h+lpString2], rax; lpString2
0x1800b84d3  mov     ecx, ebp; Locale
0x1800b84d5  call    cs:__imp_CompareStringW
0x1800b84db  cmp     eax, 2
0x1800b84de  jnz     short loc_1800B84EC
0x1800b84e0  mov     dword ptr [rbx+0Ch], 10h
0x1800b84e7  jmp     loc_1800B8692
0x1800b84ec  mov     rcx, [rbx+10h]; pbstr
0x1800b84f0  call    cs:__imp_SysStringLen
0x1800b84f6  test    eax, eax
0x1800b84f8  jz      short loc_1800B8532
0x1800b84fa  mov     rcx, [rbx+10h]; pbstr
0x1800b84fe  call    cs:__imp_SysStringLen
0x1800b8504  mov     [rsp+48h+cchCount2], eax; cchCount2
0x1800b8508  mov     r9d, esi; cchCount1
0x1800b850b  mov     rax, [rbx+10h]
0x1800b850f  lea     r8, aWif; "WIF"
0x1800b8516  xor     edx, edx; dwCmpFlags
0x1800b8518  mov     [rsp+48h+lpString2], rax; lpString2
0x1800b851d  mov     ecx, ebp; Locale
0x1800b851f  call    cs:__imp_CompareStringW
0x1800b8525  cmp     eax, 2
0x1800b8528  jnz     short loc_1800B8532
0x1800b852a  mov     [rbx+0Ch], eax
0x1800b852d  jmp     loc_1800B8692
0x1800b8532  mov     rcx, [rbx+10h]; pbstr
0x1800b8536  call    cs:__imp_SysStringLen
0x1800b853c  test    eax, eax
0x1800b853e  jz      short loc_1800B857C
0x1800b8540  mov     rcx, [rbx+10h]; pbstr
0x1800b8544  call    cs:__imp_SysStringLen
0x1800b854a  mov     [rsp+48h+cchCount2], eax; cchCount2
0x1800b854e  mov     r9d, esi; cchCount1
0x1800b8551  mov     rax, [rbx+10h]
0x1800b8555  lea     r8, aWis; "WIS"
0x1800b855c  xor     edx, edx; dwCmpFlags
0x1800b855e  mov     [rsp+48h+lpString2], rax; lpString2
0x1800b8563  mov     ecx, ebp; Locale
0x1800b8565  call    cs:__imp_CompareStringW
0x1800b856b  cmp     eax, 2
0x1800b856e  jnz     short loc_1800B857C
0x1800b8570  mov     dword ptr [rbx+0Ch], 4
0x1800b8577  jmp     loc_1800B8692
0x1800b857c  mov     rcx, [rbx+10h]; pbstr
0x1800b8580  call    cs:__imp_SysStringLen
0x1800b8586  test    eax, eax
0x1800b8588  jz      short loc_1800B85C6
0x1800b858a  mov     rcx, [rbx+10h]; pbstr
0x1800b858e  call    cs:__imp_SysStringLen
0x1800b8594  mov     [rsp+48h+cchCount2], eax; cchCount2
0x1800b8598  mov     r9d, esi; cchCount1
0x1800b859b  mov     rax, [rbx+10h]
0x1800b859f  lea     r8, aRp; "RP"
0x1800b85a6  xor     edx, edx; dwCmpFlags
0x1800b85a8  mov     [rsp+48h+lpString2], rax; lpString2
0x1800b85ad  mov     ecx, ebp; Locale
0x1800b85af  call    cs:__imp_CompareStringW
0x1800b85b5  cmp     eax, 2
0x1800b85b8  jnz     short loc_1800B85C6
0x1800b85ba  mov     dword ptr [rbx+0Ch], 8
0x1800b85c1  jmp     loc_1800B8692
0x1800b85c6  mov     rcx, [rbx+10h]; pbstr
0x1800b85ca  call    cs:__imp_SysStringLen
0x1800b85d0  test    eax, eax
0x1800b85d2  jz      short loc_1800B8610
0x1800b85d4  mov     rcx, [rbx+10h]; pbstr
0x1800b85d8  call    cs:__imp_SysStringLen
0x1800b85de  mov     [rsp+48h+cchCount2], eax; cchCount2
0x1800b85e2  mov     r9d, esi; cchCount1
0x1800b85e5  mov     rax, [rbx+10h]
0x1800b85e9  lea     r8, aRpqu; "RPQU"
0x1800b85f0  xor     edx, edx; dwCmpFlags
0x1800b85f2  mov     [rsp+48h+lpString2], rax; lpString2
0x1800b85f7  mov     ecx, ebp; Locale
0x1800b85f9  call    cs:__imp_CompareStringW
0x1800b85ff  cmp     eax, 2
0x1800b8602  jnz     short loc_1800B8610
0x1800b8604  mov     dword ptr [rbx+0Ch], 40h ; '@'
0x1800b860b  jmp     loc_1800B8692
0x1800b8610  mov     rcx, [rbx+10h]; pbstr
0x1800b8614  call    cs:__imp_SysStringLen
0x1800b861a  test    eax, eax
0x1800b861c  jz      short loc_1800B8657
0x1800b861e  mov     rcx, [rbx+10h]; pbstr
0x1800b8622  call    cs:__imp_SysStringLen
0x1800b8628  mov     [rsp+48h+cchCount2], eax; cchCount2
0x1800b862c  mov     r9d, esi; cchCount1
0x1800b862f  mov     rax, [rbx+10h]
0x1800b8633  lea     r8, aCanary; "Canary"
0x1800b863a  xor     edx, edx; dwCmpFlags
0x1800b863c  mov     [rsp+48h+lpString2], rax; lpString2
0x1800b8641  mov     ecx, ebp; Locale
0x1800b8643  call    cs:__imp_CompareStringW
0x1800b8649  cmp     eax, 2
0x1800b864c  jnz     short loc_1800B8657
0x1800b864e  mov     dword ptr [rbx+0Ch], 80h
0x1800b8655  jmp     short loc_1800B8692
0x1800b8657  mov     rax, [rbx+10h]
0x1800b865b  test    rax, rax
0x1800b865e  jz      short loc_1800B868B
0x1800b8660  mov     [rsp+48h+var_18], rax
0x1800b8665  xor     edx, edx
0x1800b8667  lea     rax, aUnknownValueFo; "Unknown value for \"BranchReadinessLeve"...
0x1800b866e  xor     ecx, ecx
0x1800b8670  mov     qword ptr [rsp+48h+cchCount2], rax
0x1800b8675  mov     [rsp+48h+lpString2], 0
0x1800b867e  lea     r9d, [rdx+3]
0x1800b8682  lea     r8d, [rdx+1]
0x1800b8686  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800b868b  mov     dword ptr [rbx+0Ch], 0
0x1800b8692  mov     rbx, [rsp+48h+arg_0]
0x1800b8697  mov     rbp, [rsp+48h+arg_8]
0x1800b869c  add     rsp, 40h
0x1800b86a0  pop     rsi
0x1800b86a1  retn
```
