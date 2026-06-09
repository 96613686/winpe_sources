# IsVDWBackendSession(void)

- ea: `0x100436120`
- end: `0x10043618d`
- name: `?IsVDWBackendSession@@YAHXZ`
- size: `109`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x100435fd0`
- `0x1004361a0`

## callees

- `0x100435fd0`
- `0x100436120`

## import_xrefs

- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100436124`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100436124`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10043617c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10043617c`
- `sqldk!SystemThread_TlsOffset` at `0x100436155`
- `sqldk!SystemThread_TlsIndex` at `0x10043614c`

## pseudocode

```c
__int64 IsVDWBackendSession(void)
{
  unsigned int v1; // r9d
  __int64 v2; // rax
  struct CSessionTraceFlags *v3; // rcx

  if ( *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 1192) )
    return IsSynapseSqlBackendSession();
  v1 = 0;
  v2 = *(_QWORD *)(SystemThread_TlsOffset
                 + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
  if ( v2 )
  {
    v3 = **(struct CSessionTraceFlags ***)(v2 + 56);
    if ( v3 )
      return (unsigned int)CSessionTraceFlags::CheckSessionTraceInternal(v3, 0x3275u);
  }
  return v1;
}

```

## disassembly

```asm
0x100436120  sub     rsp, 28h
0x100436124  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x10043612a  cmp     byte ptr [rax+4A8h], 0
0x100436131  jz      short loc_100436140
0x100436133  call    ?IsSynapseSqlBackendSession@@YA_NXZ; IsSynapseSqlBackendSession(void)
0x100436138  movzx   eax, al
0x10043613b  add     rsp, 28h
0x10043613f  retn
0x100436140  mov     r8, gs:58h
0x100436149  xor     r9d, r9d
0x10043614c  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100436153  mov     edx, [rax]
0x100436155  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043615c  mov     ecx, [rax]
0x10043615e  mov     rax, [r8+rdx*8]
0x100436162  mov     rax, [rcx+rax]
0x100436166  test    rax, rax
0x100436169  jz      short loc_100436185
0x10043616b  mov     rax, [rax+38h]
0x10043616f  mov     rcx, [rax]
0x100436172  test    rcx, rcx
0x100436175  jz      short loc_100436185
0x100436177  mov     edx, 3275h
0x10043617c  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100436182  mov     r9d, eax
0x100436185  mov     eax, r9d
0x100436188  add     rsp, 28h
0x10043618c  retn
```
