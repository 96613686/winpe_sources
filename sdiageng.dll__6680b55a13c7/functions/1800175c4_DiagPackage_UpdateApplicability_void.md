# DiagPackage::UpdateApplicability(void)

- ea: `0x1800175c4`
- end: `0x1800176d4`
- name: `?UpdateApplicability@DiagPackage@@AEAAJXZ`
- size: `272`
- prototype: `__int64 __fastcall(DiagPackage *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180016630`

## callees

- `0x1800175c4`
- `0x180026fa0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180017698`
- `msvcrt!_wcsicmp` at `0x1800176ac`
- `msvcrt!_wcsicmp` at `0x180017698`
- `msvcrt!_wcsicmp` at `0x1800176ac`
- `KERNEL32!GetNativeSystemInfo` at `0x1800175f5`
- `KERNEL32!GetNativeSystemInfo` at `0x1800175f5`
- `OLEAUT32!__imp_SysAllocString` at `0x18001765b`
- `OLEAUT32!__imp_SysAllocString` at `0x18001765b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800176bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800176bc`

## string_xrefs

- `0x180017618`: `DiagPackage::UpdateApplicability`

## pseudocode

```c
__int64 __fastcall DiagPackage::UpdateApplicability(DiagPackage *this)
{
  unsigned int v1; // ebx
  bool v2; // zf
  unsigned int v4; // r8d
  const OLECHAR **v5; // rcx
  const wchar_t *v6; // rax
  wchar_t *v7; // rsi
  struct _SYSTEM_INFO v9; // [rsp+20h] [rbp-38h] BYREF

  v1 = 0;
  v2 = (*(_BYTE *)this & 1) == 0;
  memset(&v9, 0, sizeof(v9));
  if ( !v2 )
  {
    GetNativeSystemInfo(&v9);
    if ( v9.wProcessorArchitecture == 0xFFFF )
    {
      v1 = -2147467259;
      v4 = 1751;
LABEL_4:
      SdpDebugTrace(1u, L"DiagPackage::UpdateApplicability", v4, v1);
      return v1;
    }
    if ( v9.wProcessorArchitecture != 9 && v9.wProcessorArchitecture != 6 )
    {
      v5 = (const OLECHAR **)*((_QWORD *)this + 1);
      if ( !v5 )
      {
        v1 = -2147467261;
        v4 = 1765;
        goto LABEL_4;
      }
      v6 = SysAllocString(*v5);
      v7 = (wchar_t *)v6;
      if ( !v6 )
      {
        v1 = -2147024882;
        SdpDebugTrace(1u, L"Settings::get_RequiredArchitecture", 0x423u, -2147024882);
        v4 = 1768;
        goto LABEL_4;
      }
      if ( !_wcsicmp(v6, L"ia64") || !_wcsicmp(v7, L"amd64") )
        *(_DWORD *)this &= ~1u;
      SysFreeString(v7);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800175c4  mov     rax, rsp
0x1800175c7  mov     [rax+8], rbx
0x1800175cb  mov     [rax+10h], rsi
0x1800175cf  push    rdi
0x1800175d0  sub     rsp, 50h
0x1800175d4  xorps   xmm0, xmm0
0x1800175d7  xor     ebx, ebx
0x1800175d9  test    byte ptr [rcx], 1
0x1800175dc  mov     rdi, rcx
0x1800175df  movups  xmmword ptr [rax-38h], xmm0
0x1800175e3  movups  xmmword ptr [rax-28h], xmm0
0x1800175e7  movups  xmmword ptr [rax-18h], xmm0
0x1800175eb  jz      loc_1800176C2
0x1800175f1  lea     rcx, [rax-38h]; lpSystemInfo
0x1800175f5  call    cs:__imp_GetNativeSystemInfo
0x1800175fb  movzx   eax, word ptr [rsp+58h+var_38]
0x180017600  mov     edx, 0FFFFh
0x180017605  cmp     ax, dx
0x180017608  jnz     short loc_18001762E
0x18001760a  mov     ebx, 80004005h
0x18001760f  mov     r8d, 6D7h; int
0x180017615  mov     r9d, ebx; int
0x180017618  lea     rdx, aDiagpackageUpd; "DiagPackage::UpdateApplicability"
0x18001761f  mov     ecx, 1; Level
0x180017624  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180017629  jmp     loc_1800176C2
0x18001762e  cmp     ax, 9
0x180017632  jz      loc_1800176C2
0x180017638  cmp     ax, 6
0x18001763c  jz      loc_1800176C2
0x180017642  mov     rcx, [rdi+8]
0x180017646  test    rcx, rcx
0x180017649  jnz     short loc_180017658
0x18001764b  mov     ebx, 80004003h
0x180017650  mov     r8d, 6E5h
0x180017656  jmp     short loc_180017615
0x180017658  mov     rcx, [rcx]; psz
0x18001765b  call    cs:__imp_SysAllocString
0x180017661  mov     rsi, rax
0x180017664  test    rax, rax
0x180017667  jnz     short loc_18001768E
0x180017669  mov     ebx, 8007000Eh
0x18001766e  lea     rdx, aSettingsGetReq; "Settings::get_RequiredArchitecture"
0x180017675  mov     r9d, ebx; int
0x180017678  lea     ecx, [rax+1]; Level
0x18001767b  mov     r8d, 423h; int
0x180017681  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180017686  mov     r8d, 6E8h
0x18001768c  jmp     short loc_180017615
0x18001768e  lea     rdx, aIa64; "ia64"
0x180017695  mov     rcx, rsi; String1
0x180017698  call    cs:__imp__wcsicmp
0x18001769e  test    eax, eax
0x1800176a0  jz      short loc_1800176B6
0x1800176a2  lea     rdx, aAmd64; "amd64"
0x1800176a9  mov     rcx, rsi; String1
0x1800176ac  call    cs:__imp__wcsicmp
0x1800176b2  test    eax, eax
0x1800176b4  jnz     short loc_1800176B9
0x1800176b6  and     dword ptr [rdi], 0FFFFFFFEh
0x1800176b9  mov     rcx, rsi; bstrString
0x1800176bc  call    cs:__imp_SysFreeString
0x1800176c2  mov     rsi, [rsp+58h+arg_8]
0x1800176c7  mov     eax, ebx
0x1800176c9  mov     rbx, [rsp+58h+arg_0]
0x1800176ce  add     rsp, 50h
0x1800176d2  pop     rdi
0x1800176d3  retn
```
