# CProbedAssemblyInformation::SetManifestPath(ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> const &)

- ea: `0x180059980`
- end: `0x180059a8c`
- name: `?SetManifestPath@CProbedAssemblyInformation@@QEAAHKAEBV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z`
- size: `268`
- prototype: `__int64 __fastcall(CProbedAssemblyInformation *this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000d4d0`
- `0x180062568`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x180040760`
- `0x180059980`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800599f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059a0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059a46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800599f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059a0c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180059a46`

## pseudocode

```c
__int64 __fastcall CProbedAssemblyInformation::SetManifestPath(
        CProbedAssemblyInformation *this,
        __int64 a2,
        __int64 a3)
{
  unsigned int v5; // edx
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-40h] BYREF
  int v9; // [rsp+28h] [rbp-38h] BYREF
  __int64 v10; // [rsp+30h] [rbp-30h]
  __int64 *v11; // [rsp+38h] [rbp-28h]
  __int64 v12; // [rsp+40h] [rbp-20h]
  int v13; // [rsp+48h] [rbp-18h]
  unsigned int *v14; // [rsp+50h] [rbp-10h]

  v8 = 0;
  v11 = &qword_180072DA0;
  v9 = 1;
  v14 = (unsigned int *)&v8;
  v10 = 0;
  v12 = 544438355;
  v13 = 192;
  CFrame::BaseEnter((CFrame *)&v9);
  if ( *(_QWORD *)this )
  {
    SetLastError(0);
    if ( (unsigned int)CProbedAssemblyInformation::SetManifestPath(
                         this,
                         v5,
                         *(const unsigned __int16 **)(a3 + 16),
                         *(_QWORD *)(a3 + 32)) )
    {
      SetLastError(0);
      *v14 = 1;
    }
    else
    {
      *v14 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800788A8);
    }
  }
  else
  {
    SetLastError(0x54Fu);
    *v14 = 0;
  }
  v6 = *v14;
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v9);
  return v6;
}

```

## disassembly

```asm
0x180059980  mov     [rsp-8+arg_8], rbx
0x180059985  mov     [rsp-8+arg_18], rdi
0x18005998a  push    rbp
0x18005998b  mov     rbp, rsp
0x18005998e  sub     rsp, 60h
0x180059992  mov     rax, cs:__security_cookie
0x180059999  xor     rax, rsp
0x18005999c  mov     [rbp+var_8], rax
0x1800599a0  lea     rax, qword_180072DA0
0x1800599a7  mov     [rbp+var_40], 0
0x1800599ae  mov     [rbp+var_28], rax
0x1800599b2  mov     rdi, rcx
0x1800599b5  lea     rax, [rbp+var_40]
0x1800599b9  mov     [rbp+var_38], 1
0x1800599c0  lea     rcx, [rbp+var_38]; this
0x1800599c4  mov     [rbp+var_10], rax
0x1800599c8  mov     rbx, r8
0x1800599cb  mov     [rbp+var_30], 0
0x1800599d3  mov     [rbp+var_20], 20737853h
0x1800599db  mov     [rbp+var_18], 0C0h
0x1800599e2  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x1800599e7  cmp     qword ptr [rdi], 0
0x1800599eb  jnz     short loc_180059A0A
0x1800599ed  mov     ecx, 54Fh; dwErrCode
0x1800599f2  call    cs:__imp_SetLastError
0x1800599f9  nop     dword ptr [rax+rax+00h]
0x1800599fe  mov     rax, [rbp+var_10]
0x180059a02  mov     dword ptr [rax], 0
0x180059a08  jmp     short loc_180059A5C
0x180059a0a  xor     ecx, ecx; dwErrCode
0x180059a0c  call    cs:__imp_SetLastError
0x180059a13  nop     dword ptr [rax+rax+00h]
0x180059a18  mov     r9, [rbx+20h]; unsigned __int64
0x180059a1c  mov     rcx, rdi; this
0x180059a1f  mov     r8, [rbx+10h]; unsigned __int16 *
0x180059a23  call    ?SetManifestPath@CProbedAssemblyInformation@@QEAAHKPEBG_K@Z; CProbedAssemblyInformation::SetManifestPath(ulong,ushort const *,unsigned __int64)
0x180059a28  test    eax, eax
0x180059a2a  jnz     short loc_180059A44
0x180059a2c  mov     rax, [rbp+var_10]
0x180059a30  lea     rcx, off_1800788A8; struct _CALL_SITE_INFO *
0x180059a37  mov     dword ptr [rax], 0
0x180059a3d  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180059a42  jmp     short loc_180059A5C
0x180059a44  xor     ecx, ecx; dwErrCode
0x180059a46  call    cs:__imp_SetLastError
0x180059a4d  nop     dword ptr [rax+rax+00h]
0x180059a52  mov     rax, [rbp+var_10]
0x180059a56  mov     dword ptr [rax], 1
0x180059a5c  mov     rax, [rbp+var_10]
0x180059a60  lea     rcx, [rbp+var_38]; this
0x180059a64  mov     ebx, [rax]
0x180059a66  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180059a6b  mov     eax, ebx
0x180059a6d  mov     rcx, [rbp+var_8]
0x180059a71  xor     rcx, rsp; StackCookie
0x180059a74  call    __security_check_cookie
0x180059a79  lea     r11, [rsp+60h+var_s0]
0x180059a7e  mov     rbx, [r11+18h]
0x180059a82  mov     rdi, [r11+28h]
0x180059a86  mov     rsp, r11
0x180059a89  pop     rbp
0x180059a8a  retn
```
