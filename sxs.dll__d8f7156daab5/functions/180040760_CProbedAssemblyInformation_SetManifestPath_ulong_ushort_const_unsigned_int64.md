# CProbedAssemblyInformation::SetManifestPath(ulong,ushort const *,unsigned __int64)

- ea: `0x180040760`
- end: `0x180040870`
- name: `?SetManifestPath@CProbedAssemblyInformation@@QEAAHKPEBG_K@Z`
- size: `272`
- prototype: `__int64 __fastcall(CProbedAssemblyInformation *__hidden this, unsigned int, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18004029c`
- `0x180059980`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180013af0`
- `0x18001c270`
- `0x180040760`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800407cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800407f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040840`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800407cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800407f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040840`

## pseudocode

```c
__int64 __fastcall CProbedAssemblyInformation::SetManifestPath(
        CProbedAssemblyInformation *this,
        __int64 a2,
        const unsigned __int16 *a3,
        size_t a4)
{
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-40h] BYREF
  int v10; // [rsp+28h] [rbp-38h] BYREF
  __int64 v11; // [rsp+30h] [rbp-30h]
  __int64 *v12; // [rsp+38h] [rbp-28h]
  __int64 v13; // [rsp+40h] [rbp-20h]
  int v14; // [rsp+48h] [rbp-18h]
  unsigned int *v15; // [rsp+50h] [rbp-10h]

  v9 = 0;
  v12 = &qword_180070EF0;
  v10 = 1;
  v15 = (unsigned int *)&v9;
  v11 = 0;
  v13 = 544438355;
  v14 = 216;
  CFrame::BaseEnter((CFrame *)&v10);
  if ( *(_QWORD *)this )
  {
    SetLastError(0);
    if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign((__int64)this + 16, a3, a4) )
    {
      *((_DWORD *)this + 2) = 2;
      SetLastError(0);
      *v15 = 1;
    }
    else
    {
      *v15 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180078888);
    }
  }
  else
  {
    SetLastError(0x54Fu);
    *v15 = 0;
  }
  v7 = *v15;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v10);
  return v7;
}

```

## disassembly

```asm
0x180040760  mov     [rsp-18h+arg_8], rbx
0x180040765  push    rbp
0x180040766  push    rsi
0x180040767  push    rdi
0x180040768  mov     rbp, rsp
0x18004076b  sub     rsp, 60h
0x18004076f  mov     rax, cs:__security_cookie
0x180040776  xor     rax, rsp
0x180040779  mov     [rbp+var_8], rax
0x18004077d  lea     rax, qword_180070EF0
0x180040784  mov     [rbp+var_40], 0
0x18004078b  mov     [rbp+var_28], rax
0x18004078f  mov     rbx, rcx
0x180040792  lea     rax, [rbp+var_40]
0x180040796  mov     [rbp+var_38], 1
0x18004079d  lea     rcx, [rbp+var_38]; this
0x1800407a1  mov     [rbp+var_10], rax
0x1800407a5  mov     rsi, r9
0x1800407a8  mov     [rbp+var_30], 0
0x1800407b0  mov     rdi, r8
0x1800407b3  mov     [rbp+var_20], 20737853h
0x1800407bb  mov     [rbp+var_18], 0D8h
0x1800407c2  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800407c7  cmp     qword ptr [rbx], 0
0x1800407cb  jz      short loc_18004083B
0x1800407cd  xor     ecx, ecx; dwErrCode
0x1800407cf  call    cs:__imp_SetLastError
0x1800407d6  nop     dword ptr [rax+rax+00h]
0x1800407db  lea     rcx, [rbx+10h]
0x1800407df  mov     r8, rsi
0x1800407e2  mov     rdx, rdi
0x1800407e5  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)
0x1800407ea  test    eax, eax
0x1800407ec  jz      short loc_180040858
0x1800407ee  xor     ecx, ecx; dwErrCode
0x1800407f0  mov     dword ptr [rbx+8], 2
0x1800407f7  call    cs:__imp_SetLastError
0x1800407fe  nop     dword ptr [rax+rax+00h]
0x180040803  mov     rax, [rbp+var_10]
0x180040807  mov     dword ptr [rax], 1
0x18004080d  mov     rax, [rbp+var_10]
0x180040811  lea     rcx, [rbp+var_38]; this
0x180040815  mov     ebx, [rax]
0x180040817  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x18004081c  mov     eax, ebx
0x18004081e  mov     rcx, [rbp+var_8]
0x180040822  xor     rcx, rsp; StackCookie
0x180040825  call    __security_check_cookie
0x18004082a  mov     rbx, [rsp+60h+arg_8]
0x180040832  add     rsp, 60h
0x180040836  pop     rdi
0x180040837  pop     rsi
0x180040838  pop     rbp
0x180040839  retn
0x18004083b  mov     ecx, 54Fh; dwErrCode
0x180040840  call    cs:__imp_SetLastError
0x180040847  nop     dword ptr [rax+rax+00h]
0x18004084c  mov     rax, [rbp+var_10]
0x180040850  mov     dword ptr [rax], 0
0x180040856  jmp     short loc_18004080D
0x180040858  mov     rax, [rbp+var_10]
0x18004085c  lea     rcx, off_180078888; struct _CALL_SITE_INFO *
0x180040863  mov     dword ptr [rax], 0
0x180040869  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18004086e  jmp     short loc_18004080D
```
