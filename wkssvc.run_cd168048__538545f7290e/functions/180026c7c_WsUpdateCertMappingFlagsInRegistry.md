# WsUpdateCertMappingFlagsInRegistry

- ea: `0x180026c7c`
- end: `0x180026ee9`
- name: `WsUpdateCertMappingFlagsInRegistry`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180021ea8`

## callees

- `0x180024520`
- `0x180024550`
- `0x180024f38`
- `0x180025164`
- `0x180026c7c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180026df9`
- `ntdll!RtlNtStatusToDosError` at `0x180026df9`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180026d9f`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180026d9f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026c9e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026cce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026cee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026d29`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026c9e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026cce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026cee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026d29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026db0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026eae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026ebe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026ecd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026db0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026eae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026ebe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026ecd`

## pseudocode

```c
__int64 __fastcall WsUpdateCertMappingFlagsInRegistry(const WCHAR *a1, unsigned int a2, int a3)
{
  HLOCAL *v6; // rax
  HLOCAL *v7; // rdi
  ULONG v8; // ebx
  _DWORD *v9; // rax
  HLOCAL v10; // rax
  _DWORD *v11; // rbx
  NTSTATUS RegistryValues; // esi
  _QWORD *v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rax
  void *v16; // rcx

  v6 = (HLOCAL *)LocalAlloc(0x40u, 0x10u);
  v7 = v6;
  if ( !v6 )
    return 8;
  *(_DWORD *)v6 = 0;
  v9 = v6[1];
  if ( v9
    || (v10 = LocalAlloc(0x40u, 0x10u), (v7[1] = v10) != 0)
    && (*((_QWORD *)v7[1] + 1) = LocalAlloc(0x40u, 0x3C0u), v9 = v7[1], *((_QWORD *)v9 + 1)) )
  {
    v9[1] = 0;
    *(_DWORD *)v7[1] = 10;
    v11 = LocalAlloc(0x40u, 0x70u);
    if ( v11 )
    {
      v11[2] = 16;
      *(_QWORD *)v11 = EnumerateServerCertificate;
      *((_QWORD *)v11 + 2) = a1;
      *((_QWORD *)v11 + 3) = 0;
      v11[8] = 0;
      *((_QWORD *)v11 + 5) = 0;
      v11[12] = 0;
      *((_QWORD *)v11 + 7) = 0;
      v11[16] = 0;
      *((_QWORD *)v11 + 9) = 0;
      RegistryValues = RtlQueryRegistryValuesEx(0, &Path, v11, v7, 0);
      LocalFree(v11);
      if ( RegistryValues < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids,
            (unsigned int)RegistryValues);
        }
        RtlNtStatusToDosError(RegistryValues);
      }
      v13 = v7[1];
      if ( *((_DWORD *)v13 + 1) == 1 )
      {
        v14 = v13[1];
        *(_DWORD *)(v14 + 84) = a3;
        v8 = WsAddCertMappingToRegistry(v14, a1, a2);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            (unsigned int)&WPP_abf29b036dd53d344014067ca7a3b351_Traceguids,
            (_DWORD)a1,
            *(_DWORD *)v13);
        }
        v8 = 31;
      }
      goto LABEL_25;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids);
    }
  }
  v8 = 8;
LABEL_25:
  v15 = v7[1];
  if ( v15 )
  {
    v16 = (void *)v15[1];
    if ( v16 )
      LocalFree(v16);
    LocalFree(v7[1]);
  }
  LocalFree(v7);
  return v8;
}

```

## disassembly

```asm
0x180026c7c  push    rbx
0x180026c7e  push    rbp
0x180026c7f  push    rsi
0x180026c80  push    rdi
0x180026c81  push    r14
0x180026c83  push    r15
0x180026c85  sub     rsp, 38h
0x180026c89  mov     esi, 10h
0x180026c8e  mov     r15d, edx
0x180026c91  mov     rbp, rcx
0x180026c94  mov     edx, esi; uBytes
0x180026c96  mov     r14d, r8d
0x180026c99  lea     ebx, [rsi+30h]
0x180026c9c  mov     ecx, ebx; uFlags
0x180026c9e  call    cs:__imp_LocalAlloc
0x180026ca5  nop     dword ptr [rax+rax+00h]
0x180026caa  mov     rdi, rax
0x180026cad  test    rax, rax
0x180026cb0  jnz     short loc_180026CBA
0x180026cb2  lea     ebx, [rsi-8]
0x180026cb5  jmp     loc_180026ED9
0x180026cba  mov     dword ptr [rax], 0
0x180026cc0  mov     rax, [rax+8]
0x180026cc4  test    rax, rax
0x180026cc7  jnz     short loc_180026D11
0x180026cc9  mov     rdx, rsi; uBytes
0x180026ccc  mov     ecx, ebx; uFlags
0x180026cce  call    cs:__imp_LocalAlloc
0x180026cd5  nop     dword ptr [rax+rax+00h]
0x180026cda  mov     [rdi+8], rax
0x180026cde  test    rax, rax
0x180026ce1  jz      loc_180026E97
0x180026ce7  mov     edx, 3C0h; uBytes
0x180026cec  mov     ecx, ebx; uFlags
0x180026cee  call    cs:__imp_LocalAlloc
0x180026cf5  nop     dword ptr [rax+rax+00h]
0x180026cfa  mov     rcx, [rdi+8]
0x180026cfe  mov     [rcx+8], rax
0x180026d02  mov     rax, [rdi+8]
0x180026d06  cmp     qword ptr [rax+8], 0
0x180026d0b  jz      loc_180026E97
0x180026d11  mov     dword ptr [rax+4], 0
0x180026d18  mov     edx, 70h ; 'p'; uBytes
0x180026d1d  mov     rax, [rdi+8]
0x180026d21  mov     ecx, ebx; uFlags
0x180026d23  mov     dword ptr [rax], 0Ah
0x180026d29  call    cs:__imp_LocalAlloc
0x180026d30  nop     dword ptr [rax+rax+00h]
0x180026d35  mov     rbx, rax
0x180026d38  test    rax, rax
0x180026d3b  jz      loc_180026E63
0x180026d41  lea     rax, EnumerateServerCertificate
0x180026d48  mov     [rbx+8], esi
0x180026d4b  mov     r9, rdi
0x180026d4e  mov     [rbx], rax
0x180026d51  mov     r8, rbx
0x180026d54  mov     [rbx+10h], rbp
0x180026d58  lea     rdx, Path
0x180026d5f  mov     qword ptr [rbx+18h], 0
0x180026d67  xor     ecx, ecx
0x180026d69  mov     dword ptr [rbx+20h], 0
0x180026d70  mov     qword ptr [rbx+28h], 0
0x180026d78  mov     dword ptr [rbx+30h], 0
0x180026d7f  mov     qword ptr [rbx+38h], 0
0x180026d87  mov     dword ptr [rbx+40h], 0
0x180026d8e  mov     qword ptr [rbx+48h], 0
0x180026d96  mov     [rsp+68h+var_48], 0
0x180026d9f  call    cs:__imp_RtlQueryRegistryValuesEx
0x180026da6  nop     dword ptr [rax+rax+00h]
0x180026dab  mov     rcx, rbx; hMem
0x180026dae  mov     esi, eax
0x180026db0  call    cs:__imp_LocalFree
0x180026db7  nop     dword ptr [rax+rax+00h]
0x180026dbc  lea     rbx, WPP_GLOBAL_Control
0x180026dc3  test    esi, esi
0x180026dc5  jns     short loc_180026E05
0x180026dc7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180026dce  cmp     rcx, rbx
0x180026dd1  jz      short loc_180026DF7
0x180026dd3  test    byte ptr [rcx+1Ch], 2
0x180026dd7  jz      short loc_180026DF7
0x180026dd9  cmp     byte ptr [rcx+19h], 1
0x180026ddd  jb      short loc_180026DF7
0x180026ddf  mov     rcx, [rcx+10h]
0x180026de3  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180026dea  mov     edx, 29h ; ')'
0x180026def  mov     r9d, esi
0x180026df2  call    WPP_SF_d
0x180026df7  mov     ecx, esi; Status
0x180026df9  call    cs:__imp_RtlNtStatusToDosError
0x180026e00  nop     dword ptr [rax+rax+00h]
0x180026e05  mov     rax, [rdi+8]
0x180026e09  cmp     dword ptr [rax+4], 1
0x180026e0d  jnz     short loc_180026E26
0x180026e0f  mov     rcx, [rax+8]
0x180026e13  mov     r8d, r15d
0x180026e16  mov     rdx, rbp
0x180026e19  mov     [rcx+54h], r14d
0x180026e1d  call    WsAddCertMappingToRegistry
0x180026e22  mov     ebx, eax
0x180026e24  jmp     short loc_180026E9C
0x180026e26  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180026e2d  cmp     rcx, rbx
0x180026e30  jz      short loc_180026E5C
0x180026e32  test    byte ptr [rcx+1Ch], 2
0x180026e36  jz      short loc_180026E5C
0x180026e38  cmp     byte ptr [rcx+19h], 1
0x180026e3c  jb      short loc_180026E5C
0x180026e3e  mov     eax, [rax]
0x180026e40  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180026e47  mov     rcx, [rcx+10h]
0x180026e4b  mov     edx, 2Ah ; '*'
0x180026e50  mov     r9, rbp
0x180026e53  mov     dword ptr [rsp+68h+var_48], eax
0x180026e57  call    WPP_SF_Sd
0x180026e5c  mov     ebx, 1Fh
0x180026e61  jmp     short loc_180026E9C
0x180026e63  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180026e6a  lea     rbx, WPP_GLOBAL_Control
0x180026e71  cmp     rcx, rbx
0x180026e74  jz      short loc_180026E97
0x180026e76  test    byte ptr [rcx+1Ch], 2
0x180026e7a  jz      short loc_180026E97
0x180026e7c  cmp     byte ptr [rcx+19h], 1
0x180026e80  jb      short loc_180026E97
0x180026e82  mov     rcx, [rcx+10h]
0x180026e86  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180026e8d  mov     edx, 2Bh ; '+'
0x180026e92  call    WPP_SF_
0x180026e97  mov     ebx, 8
0x180026e9c  mov     rax, [rdi+8]
0x180026ea0  test    rax, rax
0x180026ea3  jz      short loc_180026ECA
0x180026ea5  mov     rcx, [rax+8]; hMem
0x180026ea9  test    rcx, rcx
0x180026eac  jz      short loc_180026EBA
0x180026eae  call    cs:__imp_LocalFree
0x180026eb5  nop     dword ptr [rax+rax+00h]
0x180026eba  mov     rcx, [rdi+8]; hMem
0x180026ebe  call    cs:__imp_LocalFree
0x180026ec5  nop     dword ptr [rax+rax+00h]
0x180026eca  mov     rcx, rdi; hMem
0x180026ecd  call    cs:__imp_LocalFree
0x180026ed4  nop     dword ptr [rax+rax+00h]
0x180026ed9  mov     eax, ebx
0x180026edb  add     rsp, 38h
0x180026edf  pop     r15
0x180026ee1  pop     r14
0x180026ee3  pop     rdi
0x180026ee4  pop     rsi
0x180026ee5  pop     rbp
0x180026ee6  pop     rbx
0x180026ee7  retn
```
