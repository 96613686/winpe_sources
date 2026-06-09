# SxShouldCreateScopedSnapshots(uchar *)

- ea: `0x140006ab0`
- end: `0x140006c37`
- name: `?SxShouldCreateScopedSnapshots@@YAJPEAE@Z`
- size: `391`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004a70`
- `0x1400050f0`

## callees

- `0x140002e1c`
- `0x140002e44`
- `0x14000595c`
- `0x140006ab0`
- `0x14000e324`
- `0x14000e41c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140006b43`
- `ADVAPI32!RegOpenKeyExW` at `0x140006b43`
- `ADVAPI32!RegCloseKey` at `0x140006bf4`
- `ADVAPI32!RegCloseKey` at `0x140006c0d`
- `ADVAPI32!RegCloseKey` at `0x140006bf4`
- `ADVAPI32!RegCloseKey` at `0x140006c0d`

## string_xrefs

- `0x140006af9`: `SxShouldCreateScopedSnapshots`

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

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids);
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
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids,
          (unsigned int)v3);
      }
      v9 = 0;
      v10 = 323;
    }
    else
    {
      v4 = v11;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids, v11);
      }
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
0x140006ab0  mov     [rsp-18h+arg_10], rbx
0x140006ab5  push    rbp
0x140006ab6  push    rdi
0x140006ab7  push    r14
0x140006ab9  mov     rbp, rsp
0x140006abc  sub     rsp, 70h
0x140006ac0  mov     rdi, rcx
0x140006ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x140006aca  lea     r14, WPP_GLOBAL_Control
0x140006ad1  cmp     rcx, r14
0x140006ad4  jz      short loc_140006AF4
0x140006ad6  test    dword ptr [rcx+1Ch], 20000000h
0x140006add  jz      short loc_140006AF4
0x140006adf  mov     rcx, [rcx+10h]
0x140006ae3  lea     r8, WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids
0x140006aea  mov     edx, 13h
0x140006aef  call    WPP_SF_
0x140006af4  mov     ebx, 1
0x140006af9  lea     rdx, aSxshouldcreate; "SxShouldCreateScopedSnapshots"
0x140006b00  mov     r9d, ebx; unsigned __int16
0x140006b03  lea     rcx, [rbp+var_40]; this
0x140006b07  mov     r8d, 133h; unsigned __int16
0x140006b0d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140006b12  lea     rax, [rbp+hKey]
0x140006b16  mov     [rdi], bl
0x140006b18  mov     r9d, 2001Fh; samDesired
0x140006b1e  mov     [rsp+70h+phkResult], rax; phkResult
0x140006b23  xor     r8d, r8d; ulOptions
0x140006b26  mov     [rbp+hKey], 0
0x140006b2e  lea     rdx, c_wszRegistryKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x140006b35  mov     [rbp+arg_0], 0
0x140006b3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140006b43  call    cs:__imp_RegOpenKeyExW
0x140006b49  test    eax, eax
0x140006b4b  jnz     loc_140006BE6
0x140006b51  mov     rcx, [rbp+hKey]; hKey
0x140006b55  lea     r8, [rbp+arg_0]; unsigned int *
0x140006b59  mov     r9d, ebx; int
0x140006b5c  lea     rdx, c_wszScopeSnapshots; "ScopeSnapshots"
0x140006b63  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x140006b68  test    eax, eax
0x140006b6a  js      short loc_140006BA9
0x140006b6c  cmp     eax, ebx
0x140006b6e  jz      short loc_140006BA9
0x140006b70  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b77  mov     ebx, [rbp+arg_0]
0x140006b7a  cmp     rcx, r14
0x140006b7d  jz      short loc_140006BA0
0x140006b7f  test    dword ptr [rcx+1Ch], 8000000h
0x140006b86  jz      short loc_140006BA0
0x140006b88  mov     rcx, [rcx+10h]
0x140006b8c  lea     r8, WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids
0x140006b93  mov     edx, 15h
0x140006b98  mov     r9d, ebx
0x140006b9b  call    WPP_SF_d
0x140006ba0  test    ebx, ebx
0x140006ba2  setnz   al
0x140006ba5  mov     [rdi], al
0x140006ba7  jmp     short loc_140006BE6
0x140006ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x140006bb0  cmp     rcx, r14
0x140006bb3  jz      short loc_140006BD6
0x140006bb5  test    dword ptr [rcx+1Ch], 8000000h
0x140006bbc  jz      short loc_140006BD6
0x140006bbe  mov     rcx, [rcx+10h]
0x140006bc2  lea     r8, WPP_5db9067f32c63af338ecd18e5c6d1769_Traceguids
0x140006bc9  mov     edx, 14h
0x140006bce  mov     r9d, eax
0x140006bd1  call    WPP_SF_d
0x140006bd6  mov     eax, 143h
0x140006bdb  mov     [rbp+var_40], 0
0x140006be2  mov     [rbp+var_3C], ax
0x140006be6  mov     rcx, [rbp+hKey]; hKey
0x140006bea  lea     rax, [rcx-1]
0x140006bee  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140006bf2  ja      short loc_140006C00
0x140006bf4  call    cs:__imp_RegCloseKey
0x140006bfa  xor     ecx, ecx; hKey
0x140006bfc  mov     [rbp+hKey], rcx
0x140006c00  mov     ebx, [rbp+var_40]
0x140006c03  lea     rdx, [rcx-1]
0x140006c07  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140006c0b  ja      short loc_140006C1B
0x140006c0d  call    cs:__imp_RegCloseKey
0x140006c13  mov     [rbp+hKey], 0
0x140006c1b  lea     rcx, [rbp+var_40]; this
0x140006c1f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140006c24  mov     eax, ebx
0x140006c26  mov     rbx, [rsp+70h+arg_10]
0x140006c2e  add     rsp, 70h
0x140006c32  pop     r14
0x140006c34  pop     rdi
0x140006c35  pop     rbp
0x140006c36  retn
```
