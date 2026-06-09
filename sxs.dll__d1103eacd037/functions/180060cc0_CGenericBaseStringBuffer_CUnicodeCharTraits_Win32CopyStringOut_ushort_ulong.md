# CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyStringOut(ushort *,ulong *)

- ea: `0x180060cc0`
- end: `0x180060e0e`
- name: `?Win32CopyStringOut@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAGPEAK@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180060390`

## callees

- `0x18000a804`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x18004ddc0`
- `0x18005d2b0`
- `0x18005d38c`
- `0x180060cc0`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060d3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060d54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060d8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060dca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060d3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060d54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060d8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060dca`

## pseudocode

```c
__int64 __fastcall CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyStringOut(__int64 a1, __int64 a2, _DWORD *a3)
{
  const char *v6; // rcx
  unsigned __int64 v7; // rcx
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-40h] BYREF
  int v11; // [rsp+28h] [rbp-38h] BYREF
  __int64 v12; // [rsp+30h] [rbp-30h]
  __int64 *v13; // [rsp+38h] [rbp-28h]
  __int64 v14; // [rsp+40h] [rbp-20h]
  int v15; // [rsp+48h] [rbp-18h]
  unsigned int *v16; // [rsp+50h] [rbp-10h]

  v10 = 0;
  v13 = &`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyStringOut'::`2'::__stc;
  v11 = 1;
  v16 = (unsigned int *)&v10;
  v12 = 0;
  v14 = 544438355;
  v15 = 1378;
  CFrame::BaseEnter((CFrame *)&v11);
  if ( a3 )
  {
    SetLastError(0);
    v7 = *(_QWORD *)(a1 + 32) + 1LL;
    if ( (unsigned int)*a3 >= v7 )
    {
      SetLastError(0);
      if ( (unsigned int)CCharTraitsBase<unsigned short,char>::Win32CopyIntoBuffer(
                           a2,
                           (unsigned int)*a3,
                           *(_QWORD *)(a1 + 16),
                           *(_QWORD *)(a1 + 32)) )
      {
        SetLastError(0);
        *v16 = 1;
      }
      else
      {
        *v16 = 0;
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyStringOut'::`42'::__callsite);
      }
    }
    else
    {
      *a3 = v7;
      CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v11, 0x7Au);
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)`CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyStringOut'::`29'::__callsite);
    }
  }
  else
  {
    v15 = 1384;
    FusionpTraceParameterCheck(v6);
    SetLastError(0x57u);
    *v16 = 0;
  }
  v8 = *v16;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v11);
  return v8;
}

```

## disassembly

```asm
0x180060cc0  mov     [rsp-18h+arg_18], rbx
0x180060cc5  push    rbp
0x180060cc6  push    rsi
0x180060cc7  push    rdi
0x180060cc8  mov     rbp, rsp
0x180060ccb  sub     rsp, 60h
0x180060ccf  mov     rax, cs:__security_cookie
0x180060cd6  xor     rax, rsp
0x180060cd9  mov     [rbp+var_8], rax
0x180060cdd  lea     rax, ?__stc@?1??Win32CopyStringOut@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAGPEAK@Z@4U_SXS_STATIC_TRACE_CONTEXT@@B; _SXS_STATIC_TRACE_CONTEXT const `CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32CopyStringOut(ushort *,ulong *)'::`2'::__stc
0x180060ce4  mov     [rbp+var_40], 0
0x180060ceb  mov     [rbp+var_28], rax
0x180060cef  mov     rdi, rcx
0x180060cf2  lea     rax, [rbp+var_40]
0x180060cf6  mov     [rbp+var_38], 1
0x180060cfd  lea     rcx, [rbp+var_38]; this
0x180060d01  mov     [rbp+var_10], rax
0x180060d05  mov     rbx, r8
0x180060d08  mov     [rbp+var_30], 0
0x180060d10  mov     rsi, rdx
0x180060d13  mov     [rbp+var_20], 20737853h
0x180060d1b  mov     [rbp+var_18], 562h
0x180060d22  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180060d27  test    rbx, rbx
0x180060d2a  jnz     short loc_180060D52
0x180060d2c  mov     [rbp+var_18], 568h
0x180060d33  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180060d38  lea     ecx, [rbx+57h]; dwErrCode
0x180060d3b  call    cs:__imp_SetLastError
0x180060d42  nop     dword ptr [rax+rax+00h]
0x180060d47  mov     rax, [rbp+var_10]
0x180060d4b  mov     [rax], ebx
0x180060d4d  jmp     loc_180060DE0
0x180060d52  xor     ecx, ecx; dwErrCode
0x180060d54  call    cs:__imp_SetLastError
0x180060d5b  nop     dword ptr [rax+rax+00h]
0x180060d60  mov     rcx, [rdi+20h]
0x180060d64  mov     eax, [rbx]
0x180060d66  inc     rcx
0x180060d69  cmp     rax, rcx
0x180060d6c  jnb     short loc_180060D8C
0x180060d6e  mov     [rbx], ecx
0x180060d70  mov     edx, 7Ah ; 'z'; unsigned int
0x180060d75  lea     rcx, [rbp+var_38]; this
0x180060d79  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180060d7e  lea     rcx, ?__callsite@?BN@??Win32CopyStringOut@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAGPEAK@Z@4U_CALL_SITE_INFO@@B; struct _CALL_SITE_INFO *
0x180060d85  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180060d8a  jmp     short loc_180060DE0
0x180060d8c  xor     ecx, ecx; dwErrCode
0x180060d8e  call    cs:__imp_SetLastError
0x180060d95  nop     dword ptr [rax+rax+00h]
0x180060d9a  mov     edx, [rbx]
0x180060d9c  mov     rcx, rsi
0x180060d9f  mov     r9, [rdi+20h]
0x180060da3  mov     r8, [rdi+10h]
0x180060da7  call    ?Win32CopyIntoBuffer@?$CCharTraitsBase@GD@@SAHQEAG_KPEBG1@Z; CCharTraitsBase<ushort,char>::Win32CopyIntoBuffer(ushort * const,unsigned __int64,ushort const *,unsigned __int64)
0x180060dac  test    eax, eax
0x180060dae  jnz     short loc_180060DC8
0x180060db0  mov     rax, [rbp+var_10]
0x180060db4  lea     rcx, ?__callsite@?CK@??Win32CopyStringOut@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEBAHPEAGPEAK@Z@4U_CALL_SITE_INFO@@B; struct _CALL_SITE_INFO *
0x180060dbb  mov     dword ptr [rax], 0
0x180060dc1  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180060dc6  jmp     short loc_180060DE0
0x180060dc8  xor     ecx, ecx; dwErrCode
0x180060dca  call    cs:__imp_SetLastError
0x180060dd1  nop     dword ptr [rax+rax+00h]
0x180060dd6  mov     rax, [rbp+var_10]
0x180060dda  mov     dword ptr [rax], 1
0x180060de0  mov     rax, [rbp+var_10]
0x180060de4  lea     rcx, [rbp+var_38]; this
0x180060de8  mov     ebx, [rax]
0x180060dea  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180060def  mov     eax, ebx
0x180060df1  mov     rcx, [rbp+var_8]
0x180060df5  xor     rcx, rsp; StackCookie
0x180060df8  call    __security_check_cookie
0x180060dfd  mov     rbx, [rsp+60h+arg_18]
0x180060e05  add     rsp, 60h
0x180060e09  pop     rdi
0x180060e0a  pop     rsi
0x180060e0b  pop     rbp
0x180060e0c  retn
```
