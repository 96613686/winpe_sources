# SsRemoveAliasFromRegistry

- ea: `0x180025fc4`
- end: `0x1800260bb`
- name: `SsRemoveAliasFromRegistry`
- size: `247`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002bf00`

## callees

- `0x18001e80c`
- `0x180025fc4`
- `0x180026838`
- `0x1800268d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026000`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026000`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800260a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800260a8`
- `ntdll!RtlDeleteRegistryValue` at `0x180026050`
- `ntdll!RtlDeleteRegistryValue` at `0x180026050`
- `ntdll!RtlNtStatusToDosError` at `0x18002609d`
- `ntdll!RtlNtStatusToDosError` at `0x18002609d`

## pseudocode

```c
__int64 __fastcall SsRemoveAliasFromRegistry(const wchar_t **a1)
{
  __int64 v2; // rax
  SIZE_T v3; // rdi
  wchar_t *v4; // rax
  wchar_t *v5; // rbx
  ULONG v7; // esi
  const wchar_t *v8; // r8
  int v9; // edi

  if ( *a1 )
  {
    v2 = -1;
    do
      ++v2;
    while ( (*a1)[v2] );
  }
  else
  {
    v2 = 1;
  }
  v3 = 2 * v2 + 2;
  v4 = (wchar_t *)LocalAlloc(0x40u, v3);
  v5 = v4;
  if ( !v4 )
    return 1450;
  v7 = 0;
  memset_0(v4, 0, v3);
  v8 = *a1;
  if ( !*a1 )
    v8 = L"*";
  StringCbCopyW(v5, v3, v8);
  v9 = RtlDeleteRegistryValue(1u, L"LanmanServer\\Aliases", v5);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
          v9,
          (__int64)v5);
    }
    v7 = RtlNtStatusToDosError(v9);
  }
  LocalFree(v5);
  return v7;
}

```

## disassembly

```asm
0x180025fc4  push    rbx
0x180025fc6  push    rbp
0x180025fc7  push    rsi
0x180025fc8  push    rdi
0x180025fc9  push    r14
0x180025fcb  sub     rsp, 30h
0x180025fcf  mov     rdx, [rcx]
0x180025fd2  xor     ebp, ebp
0x180025fd4  mov     r14, rcx
0x180025fd7  test    rdx, rdx
0x180025fda  jz      short loc_180025FEB
0x180025fdc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025fe0  inc     rax
0x180025fe3  cmp     [rdx+rax*2], bp
0x180025fe7  jnz     short loc_180025FE0
0x180025fe9  jmp     short loc_180025FF0
0x180025feb  mov     eax, 1
0x180025ff0  lea     rdi, ds:2[rax*2]
0x180025ff8  mov     ecx, 40h ; '@'; uFlags
0x180025ffd  mov     rdx, rdi; uBytes
0x180026000  call    cs:__imp_LocalAlloc
0x180026006  mov     rbx, rax
0x180026009  test    rax, rax
0x18002600c  jnz     short loc_180026018
0x18002600e  mov     eax, 5AAh
0x180026013  jmp     loc_1800260B0
0x180026018  mov     r8, rdi; Size
0x18002601b  xor     edx, edx; Val
0x18002601d  mov     rcx, rbx; void *
0x180026020  mov     esi, ebp
0x180026022  call    memset_0
0x180026027  mov     r8, [r14]
0x18002602a  mov     rdx, rdi; cbDest
0x18002602d  mov     rcx, rbx; pszDest
0x180026030  test    r8, r8
0x180026033  jnz     short loc_18002603C
0x180026035  lea     r8, pszSrc; "*"
0x18002603c  call    StringCbCopyW
0x180026041  mov     r8, rbx; ValueName
0x180026044  lea     rdx, aLanmanserverAl; "LanmanServer\\Aliases"
0x18002604b  mov     ecx, 1; RelativeTo
0x180026050  call    cs:__imp_RtlDeleteRegistryValue
0x180026056  mov     edi, eax
0x180026058  test    eax, eax
0x18002605a  jns     short loc_1800260A5
0x18002605c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026063  lea     rax, WPP_GLOBAL_Control
0x18002606a  cmp     rcx, rax
0x18002606d  jz      short loc_18002609B
0x18002606f  test    dword ptr [rcx+1Ch], 100h
0x180026076  jz      short loc_18002609B
0x180026078  cmp     byte ptr [rcx+19h], 1
0x18002607c  jb      short loc_18002609B
0x18002607e  mov     rcx, [rcx+10h]
0x180026082  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180026089  mov     edx, 51h ; 'Q'
0x18002608e  mov     [rsp+58h+var_38], rbx
0x180026093  mov     r9d, edi
0x180026096  call    WPP_SF_dS
0x18002609b  mov     ecx, edi; Status
0x18002609d  call    cs:__imp_RtlNtStatusToDosError
0x1800260a3  mov     esi, eax
0x1800260a5  mov     rcx, rbx; hMem
0x1800260a8  call    cs:__imp_LocalFree
0x1800260ae  mov     eax, esi
0x1800260b0  add     rsp, 30h
0x1800260b4  pop     r14
0x1800260b6  pop     rdi
0x1800260b7  pop     rsi
0x1800260b8  pop     rbp
0x1800260b9  pop     rbx
0x1800260ba  retn
```
