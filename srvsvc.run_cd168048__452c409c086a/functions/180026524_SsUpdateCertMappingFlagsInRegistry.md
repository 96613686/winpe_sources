# SsUpdateCertMappingFlagsInRegistry

- ea: `0x180026524`
- end: `0x18002675f`
- name: `SsUpdateCertMappingFlagsInRegistry`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180033cb4`

## callees

- `0x180020dc0`
- `0x180020de8`
- `0x1800215e8`
- `0x180024644`
- `0x180026524`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026548`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026572`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002658c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800265c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026548`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026572`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002658c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800265c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002663c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026735`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002673f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026748`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002663c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026735`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002673f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026748`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180026631`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180026631`
- `ntdll!RtlNtStatusToDosError` at `0x180026683`
- `ntdll!RtlNtStatusToDosError` at `0x180026683`

## pseudocode

```c
__int64 __fastcall SsUpdateCertMappingFlagsInRegistry(const WCHAR *a1, int a2, int a3)
{
  HLOCAL *v6; // rax
  HLOCAL *v7; // rdi
  ULONG v8; // ebx
  _DWORD *v9; // rax
  HLOCAL v10; // rax
  _DWORD *v11; // rbx
  NTSTATUS RegistryValues; // ebp
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
      RegistryValues = RtlQueryRegistryValuesEx(0, &word_18005E1CC, v11, v7, 0);
      LocalFree(v11);
      if ( RegistryValues < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            114,
            WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
            (unsigned int)RegistryValues);
        }
        RtlNtStatusToDosError(RegistryValues);
      }
      v13 = v7[1];
      if ( *((_DWORD *)v13 + 1) == 1 )
      {
        v14 = v13[1];
        *(_DWORD *)(v14 + 84) = a3;
        v8 = SsAddCertMappingToRegistry(v14, a1, a2);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            115,
            (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
            (_DWORD)a1,
            *(_DWORD *)v13);
        }
        v8 = 31;
      }
      goto LABEL_25;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids);
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
0x180026524  push    rbx
0x180026526  push    rbp
0x180026527  push    rsi
0x180026528  push    rdi
0x180026529  push    r12
0x18002652b  push    r14
0x18002652d  push    r15
0x18002652f  sub     rsp, 30h
0x180026533  mov     esi, 10h
0x180026538  mov     r12d, edx
0x18002653b  mov     r14, rcx
0x18002653e  mov     edx, esi; uBytes
0x180026540  mov     r15d, r8d
0x180026543  lea     ebx, [rsi+30h]
0x180026546  mov     ecx, ebx; uFlags
0x180026548  call    cs:__imp_LocalAlloc
0x18002654e  mov     rdi, rax
0x180026551  test    rax, rax
0x180026554  jnz     short loc_18002655E
0x180026556  lea     ebx, [rsi-8]
0x180026559  jmp     loc_18002674E
0x18002655e  mov     dword ptr [rax], 0
0x180026564  mov     rax, [rax+8]
0x180026568  test    rax, rax
0x18002656b  jnz     short loc_1800265A9
0x18002656d  mov     rdx, rsi; uBytes
0x180026570  mov     ecx, ebx; uFlags
0x180026572  call    cs:__imp_LocalAlloc
0x180026578  mov     [rdi+8], rax
0x18002657c  test    rax, rax
0x18002657f  jz      loc_18002671E
0x180026585  mov     edx, 3C0h; uBytes
0x18002658a  mov     ecx, ebx; uFlags
0x18002658c  call    cs:__imp_LocalAlloc
0x180026592  mov     rcx, [rdi+8]
0x180026596  mov     [rcx+8], rax
0x18002659a  mov     rax, [rdi+8]
0x18002659e  cmp     qword ptr [rax+8], 0
0x1800265a3  jz      loc_18002671E
0x1800265a9  mov     dword ptr [rax+4], 0
0x1800265b0  mov     edx, 70h ; 'p'; uBytes
0x1800265b5  mov     rax, [rdi+8]
0x1800265b9  mov     ecx, ebx; uFlags
0x1800265bb  mov     dword ptr [rax], 0Ah
0x1800265c1  call    cs:__imp_LocalAlloc
0x1800265c7  mov     rbx, rax
0x1800265ca  test    rax, rax
0x1800265cd  jz      loc_1800266E6
0x1800265d3  lea     rax, EnumerateServerCertificate
0x1800265da  mov     [rbx+8], esi
0x1800265dd  mov     r9, rdi
0x1800265e0  mov     [rbx], rax
0x1800265e3  mov     r8, rbx
0x1800265e6  mov     [rbx+10h], r14
0x1800265ea  lea     rdx, word_18005E1CC
0x1800265f1  mov     qword ptr [rbx+18h], 0
0x1800265f9  xor     ecx, ecx
0x1800265fb  mov     dword ptr [rbx+20h], 0
0x180026602  mov     qword ptr [rbx+28h], 0
0x18002660a  mov     dword ptr [rbx+30h], 0
0x180026611  mov     qword ptr [rbx+38h], 0
0x180026619  mov     dword ptr [rbx+40h], 0
0x180026620  mov     qword ptr [rbx+48h], 0
0x180026628  mov     [rsp+68h+var_48], 0
0x180026631  call    cs:__imp_RtlQueryRegistryValuesEx
0x180026637  mov     rcx, rbx; hMem
0x18002663a  mov     ebp, eax
0x18002663c  call    cs:__imp_LocalFree
0x180026642  lea     rbx, WPP_GLOBAL_Control
0x180026649  mov     esi, 100h
0x18002664e  test    ebp, ebp
0x180026650  jns     short loc_180026689
0x180026652  mov     rcx, cs:WPP_GLOBAL_Control
0x180026659  cmp     rcx, rbx
0x18002665c  jz      short loc_180026681
0x18002665e  test    [rcx+1Ch], esi
0x180026661  jz      short loc_180026681
0x180026663  cmp     byte ptr [rcx+19h], 1
0x180026667  jb      short loc_180026681
0x180026669  mov     rcx, [rcx+10h]
0x18002666d  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180026674  mov     edx, 72h ; 'r'
0x180026679  mov     r9d, ebp
0x18002667c  call    WPP_SF_d
0x180026681  mov     ecx, ebp; Status
0x180026683  call    cs:__imp_RtlNtStatusToDosError
0x180026689  mov     rax, [rdi+8]
0x18002668d  cmp     dword ptr [rax+4], 1
0x180026691  jnz     short loc_1800266AA
0x180026693  mov     rcx, [rax+8]
0x180026697  mov     r8d, r12d
0x18002669a  mov     rdx, r14
0x18002669d  mov     [rcx+54h], r15d
0x1800266a1  call    SsAddCertMappingToRegistry
0x1800266a6  mov     ebx, eax
0x1800266a8  jmp     short loc_180026723
0x1800266aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800266b1  cmp     rcx, rbx
0x1800266b4  jz      short loc_1800266DF
0x1800266b6  test    [rcx+1Ch], esi
0x1800266b9  jz      short loc_1800266DF
0x1800266bb  cmp     byte ptr [rcx+19h], 1
0x1800266bf  jb      short loc_1800266DF
0x1800266c1  mov     eax, [rax]
0x1800266c3  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x1800266ca  mov     rcx, [rcx+10h]
0x1800266ce  mov     edx, 73h ; 's'
0x1800266d3  mov     r9, r14
0x1800266d6  mov     dword ptr [rsp+68h+var_48], eax
0x1800266da  call    WPP_SF_Sd
0x1800266df  mov     ebx, 1Fh
0x1800266e4  jmp     short loc_180026723
0x1800266e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800266ed  lea     rbx, WPP_GLOBAL_Control
0x1800266f4  cmp     rcx, rbx
0x1800266f7  jz      short loc_18002671E
0x1800266f9  mov     esi, 100h
0x1800266fe  test    [rcx+1Ch], esi
0x180026701  jz      short loc_18002671E
0x180026703  cmp     byte ptr [rcx+19h], 1
0x180026707  jb      short loc_18002671E
0x180026709  mov     rcx, [rcx+10h]
0x18002670d  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180026714  mov     edx, 74h ; 't'
0x180026719  call    WPP_SF_
0x18002671e  mov     ebx, 8
0x180026723  mov     rax, [rdi+8]
0x180026727  test    rax, rax
0x18002672a  jz      short loc_180026745
0x18002672c  mov     rcx, [rax+8]; hMem
0x180026730  test    rcx, rcx
0x180026733  jz      short loc_18002673B
0x180026735  call    cs:__imp_LocalFree
0x18002673b  mov     rcx, [rdi+8]; hMem
0x18002673f  call    cs:__imp_LocalFree
0x180026745  mov     rcx, rdi; hMem
0x180026748  call    cs:__imp_LocalFree
0x18002674e  mov     eax, ebx
0x180026750  add     rsp, 30h
0x180026754  pop     r15
0x180026756  pop     r14
0x180026758  pop     r12
0x18002675a  pop     rdi
0x18002675b  pop     rsi
0x18002675c  pop     rbp
0x18002675d  pop     rbx
0x18002675e  retn
```
