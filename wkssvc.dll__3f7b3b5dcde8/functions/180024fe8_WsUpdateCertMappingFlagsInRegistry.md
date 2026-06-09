# WsUpdateCertMappingFlagsInRegistry

- ea: `0x180024fe8`
- end: `0x180025218`
- name: `WsUpdateCertMappingFlagsInRegistry`
- size: `560`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800206ec`

## callees

- `0x180022b54`
- `0x180022b7c`
- `0x180023534`
- `0x18002373c`
- `0x180024fe8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180025141`
- `ntdll!RtlNtStatusToDosError` at `0x180025141`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1800250f3`
- `ntdll!RtlQueryRegistryValuesEx` at `0x1800250f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002500a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025034`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002504e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025083`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002500a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025034`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002504e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025083`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800250fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800251f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800251fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025203`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800250fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800251f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800251fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025203`

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
            &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids,
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
            (unsigned int)&WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids,
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids);
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
0x180024fe8  push    rbx
0x180024fea  push    rbp
0x180024feb  push    rsi
0x180024fec  push    rdi
0x180024fed  push    r14
0x180024fef  push    r15
0x180024ff1  sub     rsp, 38h
0x180024ff5  mov     esi, 10h
0x180024ffa  mov     r15d, edx
0x180024ffd  mov     rbp, rcx
0x180025000  mov     edx, esi; uBytes
0x180025002  mov     r14d, r8d
0x180025005  lea     ebx, [rsi+30h]
0x180025008  mov     ecx, ebx; uFlags
0x18002500a  call    cs:__imp_LocalAlloc
0x180025010  mov     rdi, rax
0x180025013  test    rax, rax
0x180025016  jnz     short loc_180025020
0x180025018  lea     ebx, [rsi-8]
0x18002501b  jmp     loc_180025209
0x180025020  mov     dword ptr [rax], 0
0x180025026  mov     rax, [rax+8]
0x18002502a  test    rax, rax
0x18002502d  jnz     short loc_18002506B
0x18002502f  mov     rdx, rsi; uBytes
0x180025032  mov     ecx, ebx; uFlags
0x180025034  call    cs:__imp_LocalAlloc
0x18002503a  mov     [rdi+8], rax
0x18002503e  test    rax, rax
0x180025041  jz      loc_1800251D9
0x180025047  mov     edx, 3C0h; uBytes
0x18002504c  mov     ecx, ebx; uFlags
0x18002504e  call    cs:__imp_LocalAlloc
0x180025054  mov     rcx, [rdi+8]
0x180025058  mov     [rcx+8], rax
0x18002505c  mov     rax, [rdi+8]
0x180025060  cmp     qword ptr [rax+8], 0
0x180025065  jz      loc_1800251D9
0x18002506b  mov     dword ptr [rax+4], 0
0x180025072  mov     edx, 70h ; 'p'; uBytes
0x180025077  mov     rax, [rdi+8]
0x18002507b  mov     ecx, ebx; uFlags
0x18002507d  mov     dword ptr [rax], 0Ah
0x180025083  call    cs:__imp_LocalAlloc
0x180025089  mov     rbx, rax
0x18002508c  test    rax, rax
0x18002508f  jz      loc_1800251A5
0x180025095  lea     rax, EnumerateServerCertificate
0x18002509c  mov     [rbx+8], esi
0x18002509f  mov     r9, rdi
0x1800250a2  mov     [rbx], rax
0x1800250a5  mov     r8, rbx
0x1800250a8  mov     [rbx+10h], rbp
0x1800250ac  lea     rdx, Path
0x1800250b3  mov     qword ptr [rbx+18h], 0
0x1800250bb  xor     ecx, ecx
0x1800250bd  mov     dword ptr [rbx+20h], 0
0x1800250c4  mov     qword ptr [rbx+28h], 0
0x1800250cc  mov     dword ptr [rbx+30h], 0
0x1800250d3  mov     qword ptr [rbx+38h], 0
0x1800250db  mov     dword ptr [rbx+40h], 0
0x1800250e2  mov     qword ptr [rbx+48h], 0
0x1800250ea  mov     [rsp+68h+var_48], 0
0x1800250f3  call    cs:__imp_RtlQueryRegistryValuesEx
0x1800250f9  mov     rcx, rbx; hMem
0x1800250fc  mov     esi, eax
0x1800250fe  call    cs:__imp_LocalFree
0x180025104  lea     rbx, WPP_GLOBAL_Control
0x18002510b  test    esi, esi
0x18002510d  jns     short loc_180025147
0x18002510f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180025116  cmp     rcx, rbx
0x180025119  jz      short loc_18002513F
0x18002511b  test    byte ptr [rcx+1Ch], 2
0x18002511f  jz      short loc_18002513F
0x180025121  cmp     byte ptr [rcx+19h], 1
0x180025125  jb      short loc_18002513F
0x180025127  mov     rcx, [rcx+10h]
0x18002512b  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x180025132  mov     edx, 29h ; ')'
0x180025137  mov     r9d, esi
0x18002513a  call    WPP_SF_d
0x18002513f  mov     ecx, esi; Status
0x180025141  call    cs:__imp_RtlNtStatusToDosError
0x180025147  mov     rax, [rdi+8]
0x18002514b  cmp     dword ptr [rax+4], 1
0x18002514f  jnz     short loc_180025168
0x180025151  mov     rcx, [rax+8]
0x180025155  mov     r8d, r15d
0x180025158  mov     rdx, rbp
0x18002515b  mov     [rcx+54h], r14d
0x18002515f  call    WsAddCertMappingToRegistry
0x180025164  mov     ebx, eax
0x180025166  jmp     short loc_1800251DE
0x180025168  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002516f  cmp     rcx, rbx
0x180025172  jz      short loc_18002519E
0x180025174  test    byte ptr [rcx+1Ch], 2
0x180025178  jz      short loc_18002519E
0x18002517a  cmp     byte ptr [rcx+19h], 1
0x18002517e  jb      short loc_18002519E
0x180025180  mov     eax, [rax]
0x180025182  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x180025189  mov     rcx, [rcx+10h]
0x18002518d  mov     edx, 2Ah ; '*'
0x180025192  mov     r9, rbp
0x180025195  mov     dword ptr [rsp+68h+var_48], eax
0x180025199  call    WPP_SF_Sd
0x18002519e  mov     ebx, 1Fh
0x1800251a3  jmp     short loc_1800251DE
0x1800251a5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800251ac  lea     rbx, WPP_GLOBAL_Control
0x1800251b3  cmp     rcx, rbx
0x1800251b6  jz      short loc_1800251D9
0x1800251b8  test    byte ptr [rcx+1Ch], 2
0x1800251bc  jz      short loc_1800251D9
0x1800251be  cmp     byte ptr [rcx+19h], 1
0x1800251c2  jb      short loc_1800251D9
0x1800251c4  mov     rcx, [rcx+10h]
0x1800251c8  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x1800251cf  mov     edx, 2Bh ; '+'
0x1800251d4  call    WPP_SF_
0x1800251d9  mov     ebx, 8
0x1800251de  mov     rax, [rdi+8]
0x1800251e2  test    rax, rax
0x1800251e5  jz      short loc_180025200
0x1800251e7  mov     rcx, [rax+8]; hMem
0x1800251eb  test    rcx, rcx
0x1800251ee  jz      short loc_1800251F6
0x1800251f0  call    cs:__imp_LocalFree
0x1800251f6  mov     rcx, [rdi+8]; hMem
0x1800251fa  call    cs:__imp_LocalFree
0x180025200  mov     rcx, rdi; hMem
0x180025203  call    cs:__imp_LocalFree
0x180025209  mov     eax, ebx
0x18002520b  add     rsp, 38h
0x18002520f  pop     r15
0x180025211  pop     r14
0x180025213  pop     rdi
0x180025214  pop     rsi
0x180025215  pop     rbp
0x180025216  pop     rbx
0x180025217  retn
```
