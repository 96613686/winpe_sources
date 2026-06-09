# AreOptionsValidAndOptInLongPathAwareProcess(PATHCCH_OPTIONS &)

- ea: `0x180024c68`
- end: `0x180024d10`
- name: `?AreOptionsValidAndOptInLongPathAwareProcess@@YA_NAEAW4PATHCCH_OPTIONS@@@Z`
- size: `168`
- prototype: `bool __fastcall(enum PATHCCH_OPTIONS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x180026018`

## callees

- `0x180024c68`
- `0x18002a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180024cdf`
- `KERNEL32!GetProcAddress` at `0x180024cdf`
- `KERNEL32!GetModuleHandleW` at `0x180024ccf`
- `KERNEL32!GetModuleHandleW` at `0x180024ccf`

## string_xrefs

- `0x180024cc8`: `ntdll.dll`
- `0x180024cd8`: `RtlAreLongPathsEnabled`

## pseudocode

```c
char __fastcall AreOptionsValidAndOptInLongPathAwareProcess(enum PATHCCH_OPTIONS *a1)
{
  __int64 v2; // rdx
  unsigned __int32 v3; // r9d
  __int64 (*ProcAddress)(void); // rax
  HMODULE ModuleHandleW; // rax
  int v7; // ecx
  enum PATHCCH_OPTIONS v8; // ecx
  char v9; // al

  v2 = *a1 & 6;
  if ( (*a1 & 1) != 0 )
  {
    if ( (_DWORD)v2 && ((v2 - 1) & (unsigned int)v2) != 0 )
      return 0;
  }
  else if ( (_DWORD)v2 )
  {
    return 0;
  }
  v3 = *a1 & 0x11;
  if ( v3 && ((v3 - 1LL) & v3) != 0 )
    return 0;
  if ( (*a1 & 1) != 0 && !(_DWORD)v2 )
  {
    ProcAddress = (__int64 (*)(void))`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled;
    if ( `RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled
      || (ModuleHandleW = GetModuleHandleW(L"ntdll.dll"),
          ProcAddress = GetProcAddress(ModuleHandleW, "RtlAreLongPathsEnabled"),
          (`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled = (__int64)ProcAddress) != 0) )
    {
      v9 = ProcAddress();
      v7 = *a1;
      if ( v9 )
      {
        v8 = v7 | 2;
        goto LABEL_15;
      }
    }
    else
    {
      v7 = *a1;
    }
    v8 = v7 | 4;
LABEL_15:
    *a1 = v8;
  }
  return 1;
}

```

## disassembly

```asm
0x180024c68  push    rbx
0x180024c6a  sub     rsp, 20h
0x180024c6e  mov     r9d, [rcx]
0x180024c71  mov     rbx, rcx
0x180024c74  mov     edx, r9d
0x180024c77  mov     r8d, r9d
0x180024c7a  and     edx, 6
0x180024c7d  and     r8d, 1
0x180024c81  jz      short loc_180024C94
0x180024c83  test    edx, edx
0x180024c85  jz      short loc_180024C9D
0x180024c87  mov     ecx, edx
0x180024c89  lea     rax, [rdx-1]
0x180024c8d  test    rcx, rax
0x180024c90  jnz     short loc_180024CAF
0x180024c92  jmp     short loc_180024C9D
0x180024c94  test    edx, edx
0x180024c96  jz      short loc_180024C9D
0x180024c98  test    r8d, r8d
0x180024c9b  jz      short loc_180024CAF
0x180024c9d  and     r9d, 11h
0x180024ca1  jz      short loc_180024CB3
0x180024ca3  mov     ecx, r9d
0x180024ca6  lea     rax, [r9-1]
0x180024caa  test    rcx, rax
0x180024cad  jz      short loc_180024CB3
0x180024caf  xor     al, al
0x180024cb1  jmp     short loc_180024CFA
0x180024cb3  test    r8d, r8d
0x180024cb6  jz      short loc_180024CF8
0x180024cb8  test    edx, edx
0x180024cba  jnz     short loc_180024CF8
0x180024cbc  mov     rax, cs:?s_pfnRtlAreLongPathsEnabled@?1??RtlAreLongPathsEnabled@@9@4P6AEXZEA; uchar (*`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled)(void)
0x180024cc3  test    rax, rax
0x180024cc6  jnz     short loc_180024D00
0x180024cc8  lea     rcx, ModuleName; "ntdll.dll"
0x180024ccf  call    cs:__imp_GetModuleHandleW
0x180024cd5  mov     rcx, rax; hModule
0x180024cd8  lea     rdx, ProcName; "RtlAreLongPathsEnabled"
0x180024cdf  call    cs:__imp_GetProcAddress
0x180024ce5  mov     cs:?s_pfnRtlAreLongPathsEnabled@?1??RtlAreLongPathsEnabled@@9@4P6AEXZEA, rax; uchar (*`RtlAreLongPathsEnabled'::`2'::s_pfnRtlAreLongPathsEnabled)(void)
0x180024cec  test    rax, rax
0x180024cef  jnz     short loc_180024D00
0x180024cf1  mov     ecx, [rbx]
0x180024cf3  or      ecx, 4
0x180024cf6  mov     [rbx], ecx
0x180024cf8  mov     al, 1
0x180024cfa  add     rsp, 20h
0x180024cfe  pop     rbx
0x180024cff  retn
0x180024d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d05  mov     ecx, [rbx]
0x180024d07  test    al, al
0x180024d09  jz      short loc_180024CF3
0x180024d0b  or      ecx, 2
0x180024d0e  jmp     short loc_180024CF6
```
