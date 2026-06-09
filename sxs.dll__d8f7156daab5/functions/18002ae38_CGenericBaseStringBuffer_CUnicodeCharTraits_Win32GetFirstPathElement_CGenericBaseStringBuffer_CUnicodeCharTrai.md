# CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32GetFirstPathElement(CGenericBaseStringBuffer<CUnicodeCharTraits> &,int)

- ea: `0x18002ae38`
- end: `0x18002af55`
- name: `?Win32GetFirstPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHAEAV1@H@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002aa40`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180013af0`
- `0x18001c270`
- `0x18002ae38`
- `0x180057a3c`
- `0x180057b54`
- `0x180057c04`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ae9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aeee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002af11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ae9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002aeee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002af11`

## pseudocode

```c
__int64 __fastcall CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32GetFirstPathElement(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 PathElement; // rax
  char **v6; // rcx
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-40h] BYREF
  int v10; // [rsp+28h] [rbp-38h] BYREF
  __int64 v11; // [rsp+30h] [rbp-30h]
  __int64 *v12; // [rsp+38h] [rbp-28h]
  __int64 v13; // [rsp+40h] [rbp-20h]
  int v14; // [rsp+48h] [rbp-18h]
  unsigned int *v15; // [rsp+50h] [rbp-10h]

  v9 = 0;
  v12 = &`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32GetFirstPathElement'::`2'::__stc;
  v10 = 1;
  v15 = (unsigned int *)&v9;
  v11 = 0;
  v13 = 544438355;
  v14 = 1084;
  CFrame::BaseEnter((CFrame *)&v10);
  SetLastError(0);
  v4 = *(_QWORD *)(a1 + 32);
  PathElement = CGenericBaseStringBuffer<CUnicodeCharTraits>::CchWithoutFirstPathElement(a1);
  if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(
                       a2,
                       *(const void **)(a1 + 16),
                       v4 - PathElement) )
  {
    CGenericBaseStringBuffer<CUnicodeCharTraits>::RemoveLeadingPathSeparators(a2);
    SetLastError(0);
    if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveFirstPathElement(a1) )
    {
      SetLastError(0);
      *v15 = 1;
      goto LABEL_7;
    }
    v6 = `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32GetFirstPathElement'::`30'::__callsite;
  }
  else
  {
    v6 = `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32GetFirstPathElement'::`15'::__callsite;
  }
  *v15 = 0;
  FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v6);
LABEL_7:
  v7 = *v15;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v10);
  return v7;
}

```

## disassembly

```asm
0x18002ae38  mov     [rsp-18h+arg_10], rbx
0x18002ae3d  push    rbp
0x18002ae3e  push    rsi
0x18002ae3f  push    rdi
0x18002ae40  mov     rbp, rsp
0x18002ae43  sub     rsp, 60h
0x18002ae47  mov     rax, cs:__security_cookie
0x18002ae4e  xor     rax, rsp
0x18002ae51  mov     [rbp+var_8], rax
0x18002ae55  lea     rax, ?__stc@?1??Win32GetFirstPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHAEAV2@H@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32GetFirstPathElement(CGenericBaseStringBuffer<CUnicodeCharTraits> &,int)'::`2'::__stc
0x18002ae5c  mov     [rbp+var_40], 0
0x18002ae63  mov     [rbp+var_28], rax
0x18002ae67  mov     rdi, rcx
0x18002ae6a  lea     rax, [rbp+var_40]
0x18002ae6e  mov     [rbp+var_38], 1
0x18002ae75  lea     rcx, [rbp+var_38]; this
0x18002ae79  mov     [rbp+var_10], rax
0x18002ae7d  mov     rsi, rdx
0x18002ae80  mov     [rbp+var_30], 0
0x18002ae88  mov     [rbp+var_20], 20737853h
0x18002ae90  mov     [rbp+var_18], 43Ch
0x18002ae97  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002ae9c  xor     ecx, ecx; dwErrCode
0x18002ae9e  call    cs:__imp_SetLastError
0x18002aea5  nop     dword ptr [rax+rax+00h]
0x18002aeaa  mov     rbx, [rdi+20h]
0x18002aeae  mov     rcx, rdi
0x18002aeb1  call    ?CchWithoutFirstPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBA_KXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::CchWithoutFirstPathElement(void)
0x18002aeb6  mov     rdx, [rdi+10h]
0x18002aeba  sub     rbx, rax
0x18002aebd  mov     r8, rbx
0x18002aec0  mov     rcx, rsi
0x18002aec3  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)
0x18002aec8  test    eax, eax
0x18002aeca  jnz     short loc_18002AEE4
0x18002aecc  lea     rcx, ?__callsite@?P@??Win32GetFirstPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHAEAV2@H@Z@4U_CALL_SITE_INFO@@B; struct _CALL_SITE_INFO *
0x18002aed3  mov     rax, [rbp+var_10]
0x18002aed7  mov     dword ptr [rax], 0
0x18002aedd  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18002aee2  jmp     short loc_18002AF27
0x18002aee4  mov     rcx, rsi
0x18002aee7  call    ?RemoveLeadingPathSeparators@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::RemoveLeadingPathSeparators(void)
0x18002aeec  xor     ecx, ecx; dwErrCode
0x18002aeee  call    cs:__imp_SetLastError
0x18002aef5  nop     dword ptr [rax+rax+00h]
0x18002aefa  mov     rcx, rdi
0x18002aefd  call    ?Win32RemoveFirstPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveFirstPathElement(void)
0x18002af02  test    eax, eax
0x18002af04  jnz     short loc_18002AF0F
0x18002af06  lea     rcx, ?__callsite@?BO@??Win32GetFirstPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHAEAV2@H@Z@4U_CALL_SITE_INFO@@B; _CALL_SITE_INFO const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32GetFirstPathElement(CGenericBaseStringBuffer<CUnicodeCharTraits> &,int)'::`30'::__callsite
0x18002af0d  jmp     short loc_18002AED3
0x18002af0f  xor     ecx, ecx; dwErrCode
0x18002af11  call    cs:__imp_SetLastError
0x18002af18  nop     dword ptr [rax+rax+00h]
0x18002af1d  mov     rax, [rbp+var_10]
0x18002af21  mov     dword ptr [rax], 1
0x18002af27  mov     rax, [rbp+var_10]
0x18002af2b  lea     rcx, [rbp+var_38]; this
0x18002af2f  mov     ebx, [rax]
0x18002af31  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18002af36  mov     eax, ebx
0x18002af38  mov     rcx, [rbp+var_8]
0x18002af3c  xor     rcx, rsp; StackCookie
0x18002af3f  call    __security_check_cookie
0x18002af44  mov     rbx, [rsp+60h+arg_10]
0x18002af4c  add     rsp, 60h
0x18002af50  pop     rdi
0x18002af51  pop     rsi
0x18002af52  pop     rbp
0x18002af53  retn
```
