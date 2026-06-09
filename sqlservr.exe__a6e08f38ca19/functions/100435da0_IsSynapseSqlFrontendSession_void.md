# IsSynapseSqlFrontendSession(void)

- ea: `0x100435da0`
- end: `0x100435ee6`
- name: `?IsSynapseSqlFrontendSession@@YA_NXZ`
- size: `326`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x100435fd0`
- `0x1004361a0`

## callees

- `0x100435da0`
- `0x1004361a0`

## import_xrefs

- `sqlmin!GetXdbServerGlobals` at `0x100435e0e`
- `sqlmin!GetXdbServerGlobals` at `0x100435e1d`
- `sqlmin!GetXdbServerGlobals` at `0x100435e2c`
- `sqlmin!GetXdbServerGlobals` at `0x100435e3b`
- `sqlmin!GetXdbServerGlobals` at `0x100435e0e`
- `sqlmin!GetXdbServerGlobals` at `0x100435e1d`
- `sqlmin!GetXdbServerGlobals` at `0x100435e2c`
- `sqlmin!GetXdbServerGlobals` at `0x100435e3b`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100435da4`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100435da4`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100435df0`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100435df0`
- `sqldk!SystemThread_TlsOffset` at `0x100435dc9`
- `sqldk!SystemThread_TlsOffset` at `0x100435e67`
- `sqldk!SystemThread_TlsIndex` at `0x100435dc0`
- `sqldk!SystemThread_TlsIndex` at `0x100435e5e`

## pseudocode

```c
bool IsSynapseSqlFrontendSession(void)
{
  __int64 v0; // rdx
  struct CSessionTraceFlags *v1; // rcx
  __int64 v2; // rax

  if ( !*(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 1192) )
    return (unsigned int)IsVDWFrontendInstance() != 0;
  v0 = SystemThread_TlsIndex;
  v1 = (struct CSessionTraceFlags *)SystemThread_TlsOffset;
  v2 = *(_QWORD *)(SystemThread_TlsOffset
                 + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
  return (!v2
       || (v1 = **(struct CSessionTraceFlags ***)(v2 + 56)) == 0
       || !CSessionTraceFlags::CheckSessionTraceInternal(v1, 0x3275u))
      && (*((_DWORD *)qword_10049F360 + 3626)
       && (*(_BYTE *)(GetXdbServerGlobals(v1, v0) + 12009) || *(_BYTE *)(GetXdbServerGlobals(v1, v0) + 12008))
       && !*(_BYTE *)(GetXdbServerGlobals(v1, v0) + 12004)
       || *(_BYTE *)(GetXdbServerGlobals(v1, v0) + 12004))
      && *((_DWORD *)qword_10049F360 + 3626)
      && *(_QWORD *)(SystemThread_TlsOffset
                   + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex))
      && (*(char *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                          + SystemThread_TlsOffset)
                              + 72LL)
                  + 270LL) < 0
       || (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                              + SystemThread_TlsIndex)
                                            + SystemThread_TlsOffset)
                                + 72LL)
                    + 270LL)
         & 8) != 0);
}

```

## disassembly

```asm
0x100435da0  sub     rsp, 28h
0x100435da4  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x100435daa  cmp     byte ptr [rax+4A8h], 0
0x100435db1  jz      loc_100435ED7
0x100435db7  mov     r8, gs:58h
0x100435dc0  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100435dc7  mov     edx, [rax]
0x100435dc9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100435dd0  mov     ecx, [rax]
0x100435dd2  mov     rax, [r8+rdx*8]
0x100435dd6  mov     rax, [rcx+rax]
0x100435dda  test    rax, rax
0x100435ddd  jz      short loc_100435DFE
0x100435ddf  mov     rax, [rax+38h]
0x100435de3  mov     rcx, [rax]
0x100435de6  test    rcx, rcx
0x100435de9  jz      short loc_100435DFE
0x100435deb  mov     edx, 3275h
0x100435df0  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100435df6  test    eax, eax
0x100435df8  jnz     loc_100435ED0
0x100435dfe  mov     rax, cs:qword_10049F360
0x100435e05  cmp     dword ptr [rax+38A8h], 0
0x100435e0c  jz      short loc_100435E3B
0x100435e0e  call    cs:__imp_GetXdbServerGlobals
0x100435e14  cmp     byte ptr [rax+2EE9h], 0
0x100435e1b  jnz     short loc_100435E2C
0x100435e1d  call    cs:__imp_GetXdbServerGlobals
0x100435e23  cmp     byte ptr [rax+2EE8h], 0
0x100435e2a  jz      short loc_100435E3B
0x100435e2c  call    cs:__imp_GetXdbServerGlobals
0x100435e32  cmp     byte ptr [rax+2EE4h], 0
0x100435e39  jz      short loc_100435E4E
0x100435e3b  call    cs:__imp_GetXdbServerGlobals
0x100435e41  cmp     byte ptr [rax+2EE4h], 0
0x100435e48  jz      loc_100435ED0
0x100435e4e  mov     rax, cs:qword_10049F360
0x100435e55  cmp     dword ptr [rax+38A8h], 0
0x100435e5c  jz      short loc_100435ED0
0x100435e5e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100435e65  mov     ecx, [rax]
0x100435e67  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100435e6e  lea     rdx, ds:0[rcx*8]
0x100435e76  mov     r8d, [rax]
0x100435e79  mov     rax, gs:58h
0x100435e82  mov     rcx, [rax+rdx]
0x100435e86  cmp     qword ptr [r8+rcx], 0
0x100435e8b  jz      short loc_100435ED0
0x100435e8d  mov     rax, gs:58h
0x100435e96  mov     rcx, [rax+rdx]
0x100435e9a  mov     rax, [rcx+r8]
0x100435e9e  mov     rcx, [rax+48h]
0x100435ea2  cmp     byte ptr [rcx+10Eh], 0
0x100435ea9  jl      short loc_100435EC9
0x100435eab  mov     rax, gs:58h
0x100435eb4  mov     rcx, [rax+rdx]
0x100435eb8  mov     rax, [rcx+r8]
0x100435ebc  mov     rcx, [rax+48h]
0x100435ec0  test    byte ptr [rcx+10Eh], 8
0x100435ec7  jz      short loc_100435ED0
0x100435ec9  mov     al, 1
0x100435ecb  add     rsp, 28h
0x100435ecf  retn
0x100435ed0  xor     al, al
0x100435ed2  add     rsp, 28h
0x100435ed6  retn
0x100435ed7  call    ?IsVDWFrontendInstance@@YAHXZ; IsVDWFrontendInstance(void)
0x100435edc  test    eax, eax
0x100435ede  setnz   al
0x100435ee1  add     rsp, 28h
0x100435ee5  retn
```
