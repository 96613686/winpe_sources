# SxShouldCreateScopedSnapshots(uchar *)

- ea: `0x18002f358`
- end: `0x18002f4df`
- name: `?SxShouldCreateScopedSnapshots@@YAJPEAE@Z`
- size: `391`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bb24`

## callees

- `0x180020710`
- `0x180020738`
- `0x180026874`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002e2ac`
- `0x18002f358`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f49c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f4b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f49c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f4b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f3eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f3eb`

## string_xrefs

- `0x18002f3a1`: `SxShouldCreateScopedSnapshots`

## pseudocode

```c
__int64 __fastcall SxShouldCreateScopedSnapshots(bool *a1)
{
  __int64 v2; // r8
  int v3; // eax
  unsigned int v4; // ebx
  HKEY v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  unsigned int v9; // [rsp+30h] [rbp-40h] BYREF
  __int16 v10; // [rsp+34h] [rbp-3Ch]
  unsigned int v11; // [rsp+90h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+28h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "SxShouldCreateScopedSnapshots", 307, 1);
  *a1 = 1;
  hKey = 0;
  v11 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SystemRestore",
          0,
          0x2001Fu,
          &hKey) )
  {
    v3 = SxRegReadDWORD(hKey, L"ScopeSnapshots", &v11, 1);
    if ( v3 < 0 || v3 == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          &WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids,
          (unsigned int)v3);
      v9 = 0;
      v10 = 323;
    }
    else
    {
      v4 = v11;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids, v11);
      *a1 = v4 != 0;
    }
  }
  v5 = hKey;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    v5 = 0;
    hKey = 0;
  }
  v6 = v9;
  v7 = (__int64)v5 - 1;
  if ( (unsigned __int64)v5 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(v5);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9, v7, v2);
  return v6;
}

```

## disassembly

```asm
0x18002f358  mov     [rsp-18h+arg_10], rbx
0x18002f35d  push    rbp
0x18002f35e  push    rdi
0x18002f35f  push    r14
0x18002f361  mov     rbp, rsp
0x18002f364  sub     rsp, 70h
0x18002f368  mov     rdi, rcx
0x18002f36b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f372  lea     r14, WPP_GLOBAL_Control
0x18002f379  cmp     rcx, r14
0x18002f37c  jz      short loc_18002F39C
0x18002f37e  test    dword ptr [rcx+1Ch], 20000000h
0x18002f385  jz      short loc_18002F39C
0x18002f387  mov     rcx, [rcx+10h]
0x18002f38b  lea     r8, WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids
0x18002f392  mov     edx, 13h
0x18002f397  call    WPP_SF_
0x18002f39c  mov     ebx, 1
0x18002f3a1  lea     rdx, aSxshouldcreate; "SxShouldCreateScopedSnapshots"
0x18002f3a8  mov     r9d, ebx; unsigned __int16
0x18002f3ab  lea     rcx, [rbp+var_40]; this
0x18002f3af  mov     r8d, 133h; unsigned __int16
0x18002f3b5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002f3ba  lea     rax, [rbp+hKey]
0x18002f3be  mov     [rdi], bl
0x18002f3c0  mov     r9d, 2001Fh; samDesired
0x18002f3c6  mov     [rsp+70h+phkResult], rax; phkResult
0x18002f3cb  xor     r8d, r8d; ulOptions
0x18002f3ce  mov     [rbp+hKey], 0
0x18002f3d6  lea     rdx, c_wszRegistryKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002f3dd  mov     [rbp+arg_0], 0
0x18002f3e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f3eb  call    cs:__imp_RegOpenKeyExW
0x18002f3f1  test    eax, eax
0x18002f3f3  jnz     loc_18002F48E
0x18002f3f9  mov     rcx, [rbp+hKey]; hKey
0x18002f3fd  lea     r8, [rbp+arg_0]; unsigned int *
0x18002f401  mov     r9d, ebx; int
0x18002f404  lea     rdx, c_wszScopeSnapshots; "ScopeSnapshots"
0x18002f40b  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18002f410  test    eax, eax
0x18002f412  js      short loc_18002F451
0x18002f414  cmp     eax, ebx
0x18002f416  jz      short loc_18002F451
0x18002f418  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f41f  mov     ebx, [rbp+arg_0]
0x18002f422  cmp     rcx, r14
0x18002f425  jz      short loc_18002F448
0x18002f427  test    dword ptr [rcx+1Ch], 8000000h
0x18002f42e  jz      short loc_18002F448
0x18002f430  mov     rcx, [rcx+10h]
0x18002f434  lea     r8, WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids
0x18002f43b  mov     edx, 15h
0x18002f440  mov     r9d, ebx
0x18002f443  call    WPP_SF_d
0x18002f448  test    ebx, ebx
0x18002f44a  setnz   al
0x18002f44d  mov     [rdi], al
0x18002f44f  jmp     short loc_18002F48E
0x18002f451  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f458  cmp     rcx, r14
0x18002f45b  jz      short loc_18002F47E
0x18002f45d  test    dword ptr [rcx+1Ch], 8000000h
0x18002f464  jz      short loc_18002F47E
0x18002f466  mov     rcx, [rcx+10h]
0x18002f46a  lea     r8, WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids
0x18002f471  mov     edx, 14h
0x18002f476  mov     r9d, eax
0x18002f479  call    WPP_SF_D
0x18002f47e  mov     eax, 143h
0x18002f483  mov     [rbp+var_40], 0
0x18002f48a  mov     [rbp+var_3C], ax
0x18002f48e  mov     rcx, [rbp+hKey]; hKey
0x18002f492  lea     rax, [rcx-1]
0x18002f496  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002f49a  ja      short loc_18002F4A8
0x18002f49c  call    cs:__imp_RegCloseKey
0x18002f4a2  xor     ecx, ecx; hKey
0x18002f4a4  mov     [rbp+hKey], rcx
0x18002f4a8  mov     ebx, [rbp+var_40]
0x18002f4ab  lea     rdx, [rcx-1]
0x18002f4af  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002f4b3  ja      short loc_18002F4C3
0x18002f4b5  call    cs:__imp_RegCloseKey
0x18002f4bb  mov     [rbp+hKey], 0
0x18002f4c3  lea     rcx, [rbp+var_40]; this
0x18002f4c7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002f4cc  mov     eax, ebx
0x18002f4ce  mov     rbx, [rsp+70h+arg_10]
0x18002f4d6  add     rsp, 70h
0x18002f4da  pop     r14
0x18002f4dc  pop     rdi
0x18002f4dd  pop     rbp
0x18002f4de  retn
```
