# IsSynapseSqlBackendSession(void)

- ea: `0x100435fd0`
- end: `0x10043610e`
- name: `?IsSynapseSqlBackendSession@@YA_NXZ`
- size: `318`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x100435fd0`
- `0x100436120`

## callees

- `0x100435da0`
- `0x100435ef0`
- `0x100435fd0`
- `0x100436120`

## import_xrefs

- `sqlmin!GetXdbServerGlobals` at `0x100435ff7`
- `sqlmin!GetXdbServerGlobals` at `0x100436006`
- `sqlmin!GetXdbServerGlobals` at `0x100436015`
- `sqlmin!GetXdbServerGlobals` at `0x100436024`
- `sqlmin!GetXdbServerGlobals` at `0x1004360a1`
- `sqlmin!GetXdbServerGlobals` at `0x1004360b0`
- `sqlmin!GetXdbServerGlobals` at `0x1004360e8`
- `sqlmin!GetXdbServerGlobals` at `0x100435ff7`
- `sqlmin!GetXdbServerGlobals` at `0x100436006`
- `sqlmin!GetXdbServerGlobals` at `0x100436015`
- `sqlmin!GetXdbServerGlobals` at `0x100436024`
- `sqlmin!GetXdbServerGlobals` at `0x1004360a1`
- `sqlmin!GetXdbServerGlobals` at `0x1004360b0`
- `sqlmin!GetXdbServerGlobals` at `0x1004360e8`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100435fd4`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100436089`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100435fd4`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100436089`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100436070`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100436070`
- `sqldk!SystemThread_TlsOffset` at `0x100436049`
- `sqldk!SystemThread_TlsIndex` at `0x100436040`

## pseudocode

```c
bool IsSynapseSqlBackendSession(void)
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // rax
  struct CSessionTraceFlags *v3; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx

  do
  {
    if ( *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 1192) )
    {
      if ( *((_DWORD *)qword_10049F360 + 3626)
        && (*(_BYTE *)(GetXdbServerGlobals(v1, v0) + 12009) || *(_BYTE *)(GetXdbServerGlobals(v1, v0) + 12008))
        && !*(_BYTE *)(GetXdbServerGlobals(v1, v0) + 12004)
        || *(_BYTE *)(GetXdbServerGlobals(v1, v0) + 12004) )
      {
        v2 = *(_QWORD *)(SystemThread_TlsOffset
                       + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
        if ( !v2 )
          return !IsSynapseSqlFrontendSession();
        v3 = **(struct CSessionTraceFlags ***)(v2 + 56);
        if ( !v3 || !CSessionTraceFlags::CheckSessionTraceInternal(v3, 0x3275u) )
          return !IsSynapseSqlFrontendSession();
        return 1;
      }
      return 0;
    }
  }
  while ( *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 1192) );
  if ( *(_BYTE *)(GetXdbServerGlobals(v6, v5) + 12004) )
  {
    if ( *(_BYTE *)(GetXdbServerGlobals(v8, v7) + 12004) && !IsFidoDWFrontEndSession(v10, v9)
      || (unsigned int)IsVDWBackendSession() )
    {
      return 1;
    }
  }
  else if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    if ( *(_BYTE *)(GetXdbServerGlobals(v8, v7) + 12008) )
      return 1;
    if ( (unsigned int)IsVDWBackendSession() )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x100435fd0  sub     rsp, 28h
0x100435fd4  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x100435fda  cmp     byte ptr [rax+4A8h], 0
0x100435fe1  jz      loc_100436089
0x100435fe7  mov     rax, cs:qword_10049F360
0x100435fee  cmp     dword ptr [rax+38A8h], 0
0x100435ff5  jz      short loc_100436024
0x100435ff7  call    cs:__imp_GetXdbServerGlobals
0x100435ffd  cmp     byte ptr [rax+2EE9h], 0
0x100436004  jnz     short loc_100436015
0x100436006  call    cs:__imp_GetXdbServerGlobals
0x10043600c  cmp     byte ptr [rax+2EE8h], 0
0x100436013  jz      short loc_100436024
0x100436015  call    cs:__imp_GetXdbServerGlobals
0x10043601b  cmp     byte ptr [rax+2EE4h], 0
0x100436022  jz      short loc_100436037
0x100436024  call    cs:__imp_GetXdbServerGlobals
0x10043602a  cmp     byte ptr [rax+2EE4h], 0
0x100436031  jz      loc_100436107
0x100436037  mov     r8, gs:58h
0x100436040  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100436047  mov     edx, [rax]
0x100436049  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100436050  mov     ecx, [rax]
0x100436052  mov     rax, [r8+rdx*8]
0x100436056  mov     rax, [rcx+rax]
0x10043605a  test    rax, rax
0x10043605d  jz      short loc_10043607A
0x10043605f  mov     rax, [rax+38h]
0x100436063  mov     rcx, [rax]
0x100436066  test    rcx, rcx
0x100436069  jz      short loc_10043607A
0x10043606b  mov     edx, 3275h
0x100436070  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100436076  test    eax, eax
0x100436078  jnz     short loc_1004360D1
0x10043607a  call    ?IsSynapseSqlFrontendSession@@YA_NXZ; IsSynapseSqlFrontendSession(void)
0x10043607f  test    al, al
0x100436081  setz    al
0x100436084  add     rsp, 28h
0x100436088  retn
0x100436089  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x10043608f  cmp     byte ptr [rax+4A8h], 0
0x100436096  jz      short loc_1004360A1
0x100436098  add     rsp, 28h
0x10043609c  jmp     ?IsSynapseSqlBackendSession@@YA_NXZ; IsSynapseSqlBackendSession(void)
0x1004360a1  call    cs:__imp_GetXdbServerGlobals
0x1004360a7  cmp     byte ptr [rax+2EE4h], 0
0x1004360ae  jz      short loc_1004360D8
0x1004360b0  call    cs:__imp_GetXdbServerGlobals
0x1004360b6  cmp     byte ptr [rax+2EE4h], 0
0x1004360bd  jz      short loc_1004360C8
0x1004360bf  call    ?IsFidoDWFrontEndSession@@YA_NXZ; IsFidoDWFrontEndSession(void)
0x1004360c4  test    al, al
0x1004360c6  jz      short loc_1004360D1
0x1004360c8  call    ?IsVDWBackendSession@@YAHXZ; IsVDWBackendSession(void)
0x1004360cd  test    eax, eax
0x1004360cf  jz      short loc_100436107
0x1004360d1  mov     al, 1
0x1004360d3  add     rsp, 28h
0x1004360d7  retn
0x1004360d8  mov     rax, cs:qword_10049F360
0x1004360df  cmp     dword ptr [rax+38A8h], 0
0x1004360e6  jz      short loc_100436107
0x1004360e8  call    cs:__imp_GetXdbServerGlobals
0x1004360ee  cmp     byte ptr [rax+2EE8h], 0
0x1004360f5  jnz     short loc_1004360D1
0x1004360f7  call    ?IsVDWBackendSession@@YAHXZ; IsVDWBackendSession(void)
0x1004360fc  test    eax, eax
0x1004360fe  jz      short loc_100436107
0x100436100  mov     al, 1
0x100436102  add     rsp, 28h
0x100436106  retn
0x100436107  xor     al, al
0x100436109  add     rsp, 28h
0x10043610d  retn
```
