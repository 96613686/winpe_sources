# SOSEnableIoRgV2Callback(bool,CFeatureSwitchesExecEnv)

- ea: `0x100429b50`
- end: `0x100429cc3`
- name: `?SOSEnableIoRgV2Callback@@YAX_NW4CFeatureSwitchesExecEnv@@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10042a380`

## callees

- `0x100429b50`

## import_xrefs

- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100429c25`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100429c25`
- `sqlmin!GetXdbServerGlobals` at `0x100429b71`
- `sqlmin!GetXdbServerGlobals` at `0x100429c07`
- `sqlmin!GetXdbServerGlobals` at `0x100429c16`
- `sqlmin!GetXdbServerGlobals` at `0x100429c44`
- `sqlmin!GetXdbServerGlobals` at `0x100429b71`
- `sqlmin!GetXdbServerGlobals` at `0x100429c07`
- `sqlmin!GetXdbServerGlobals` at `0x100429c16`
- `sqlmin!GetXdbServerGlobals` at `0x100429c44`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100429c60`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100429c94`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100429bd3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100429bd3`
- `sqldk!SystemThread_TlsOffset` at `0x100429bac`
- `sqldk!SystemThread_TlsIndex` at `0x100429ba3`
- `sqldk!?GetManager@SOS_IOResourceManager@@SAPEAV1@XZ` at `0x100429c36`
- `sqldk!?GetManager@SOS_IOResourceManager@@SAPEAV1@XZ` at `0x100429c70`
- `sqldk!?GetManager@SOS_IOResourceManager@@SAPEAV1@XZ` at `0x100429ca4`
- `sqldk!?GetManager@SOS_IOResourceManager@@SAPEAV1@XZ` at `0x100429cb0`
- `sqldk!?GetManager@SOS_IOResourceManager@@SAPEAV1@XZ` at `0x100429c36`
- `sqldk!?GetManager@SOS_IOResourceManager@@SAPEAV1@XZ` at `0x100429c70`
- `sqldk!?GetManager@SOS_IOResourceManager@@SAPEAV1@XZ` at `0x100429ca4`
- `sqldk!?GetManager@SOS_IOResourceManager@@SAPEAV1@XZ` at `0x100429cb0`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x100429c53`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x100429c87`

## pseudocode

```c
__int64 __fastcall SOSEnableIoRgV2Callback(_BOOL8 a1, __int64 a2)
{
  bool v2; // bl
  __int64 v3; // rdx
  struct CSessionTraceFlags *v4; // rcx
  __int64 v5; // rax
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 Manager; // rax

  v2 = a1;
  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    v2 = a1 && *(_BYTE *)(GetXdbServerGlobals(a1, a2) + 16924);
    if ( (*(_BYTE *)(qword_10049F340 + 1250) & 0x10) == 0 )
    {
      v3 = SystemThread_TlsIndex;
      v4 = (struct CSessionTraceFlags *)SystemThread_TlsOffset;
      v5 = *(_QWORD *)(SystemThread_TlsOffset
                     + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
      if ( (!v5
         || (v4 = **(struct CSessionTraceFlags ***)(v5 + 56)) == 0
         || !CSessionTraceFlags::CheckSessionTraceInternal(v4, 0x2714u))
        && *((_DWORD *)qword_10049F360 + 3635)
        && ((*((_BYTE *)qword_10049F360 + 48500) & 1) != 0
         || !*((_DWORD *)qword_10049F360 + 3626) && *(_BYTE *)(GetXdbServerGlobals(v4, v3) + 12004)
         || *(_BYTE *)(GetXdbServerGlobals(v4, v3) + 12004)) )
      {
        if ( *(_BYTE *)(CFeatureSwitchesMin::ExportCurrentInstance() + 602) )
        {
          v2 = 0;
          goto LABEL_17;
        }
      }
    }
  }
  if ( !v2
    || (SOS_PublicGlobals::sm_ResourceManager[104] & 1) == 0
    || (*(_BYTE *)(&SOS_PublicGlobals::sm_traceFlags + 24) & 0x10) != 0 )
  {
LABEL_17:
    result = SOS_IOResourceManager::GetManager();
    *(_DWORD *)(result + 64) &= ~4u;
    if ( !v2 )
      return result;
    goto LABEL_18;
  }
  Manager = SOS_IOResourceManager::GetManager();
  *(_DWORD *)(Manager + 64) |= 4u;
LABEL_18:
  if ( *(_BYTE *)(GetXdbServerGlobals(v8, v7) + 17112)
    && (SOS_PublicGlobals::sm_ResourceManager[104] & 1) != 0
    && (*(_BYTE *)(&SOS_PublicGlobals::sm_traceFlags + 24) & 0x10) == 0 )
  {
    result = SOS_IOResourceManager::GetManager();
    *(_DWORD *)(result + 64) |= 0x400u;
  }
  else
  {
    result = SOS_IOResourceManager::GetManager();
    *(_DWORD *)(result + 64) &= ~0x400u;
  }
  return result;
}

```

## disassembly

```asm
0x100429b50  push    rbx
0x100429b52  sub     rsp, 20h
0x100429b56  mov     rax, cs:qword_10049F360
0x100429b5d  movzx   ebx, cl
0x100429b60  cmp     dword ptr [rax+38A8h], 0
0x100429b67  jz      loc_100429C83
0x100429b6d  test    cl, cl
0x100429b6f  jz      short loc_100429B84
0x100429b71  call    cs:__imp_GetXdbServerGlobals
0x100429b77  cmp     byte ptr [rax+421Ch], 0
0x100429b7e  jz      short loc_100429B84
0x100429b80  mov     bl, 1
0x100429b82  jmp     short loc_100429B86
0x100429b84  xor     bl, bl
0x100429b86  mov     rax, cs:qword_10049F340
0x100429b8d  test    byte ptr [rax+4E2h], 10h
0x100429b94  jnz     loc_100429C83
0x100429b9a  mov     r8, gs:58h
0x100429ba3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100429baa  mov     edx, [rax]
0x100429bac  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100429bb3  mov     ecx, [rax]
0x100429bb5  mov     rax, [r8+rdx*8]
0x100429bb9  mov     rax, [rcx+rax]
0x100429bbd  test    rax, rax
0x100429bc0  jz      short loc_100429BE1
0x100429bc2  mov     rax, [rax+38h]
0x100429bc6  mov     rcx, [rax]
0x100429bc9  test    rcx, rcx
0x100429bcc  jz      short loc_100429BE1
0x100429bce  mov     edx, 2714h
0x100429bd3  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100429bd9  test    eax, eax
0x100429bdb  jnz     loc_100429C83
0x100429be1  mov     rax, cs:qword_10049F360
0x100429be8  cmp     dword ptr [rax+38CCh], 0
0x100429bef  jz      loc_100429C83
0x100429bf5  test    byte ptr [rax+0BD74h], 1
0x100429bfc  jnz     short loc_100429C25
0x100429bfe  cmp     dword ptr [rax+38A8h], 0
0x100429c05  jnz     short loc_100429C16
0x100429c07  call    cs:__imp_GetXdbServerGlobals
0x100429c0d  cmp     byte ptr [rax+2EE4h], 0
0x100429c14  jnz     short loc_100429C25
0x100429c16  call    cs:__imp_GetXdbServerGlobals
0x100429c1c  cmp     byte ptr [rax+2EE4h], 0
0x100429c23  jz      short loc_100429C83
0x100429c25  call    cs:__imp_?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ; CFeatureSwitchesMin::ExportCurrentInstance(void)
0x100429c2b  cmp     byte ptr [rax+25Ah], 0
0x100429c32  jz      short loc_100429C83
0x100429c34  xor     bl, bl
0x100429c36  call    cs:__imp_?GetManager@SOS_IOResourceManager@@SAPEAV1@XZ; SOS_IOResourceManager::GetManager(void)
0x100429c3c  and     dword ptr [rax+40h], 0FFFFFFFBh
0x100429c40  test    bl, bl
0x100429c42  jz      short loc_100429CBD
0x100429c44  call    cs:__imp_GetXdbServerGlobals
0x100429c4a  cmp     byte ptr [rax+42D8h], 0
0x100429c51  jz      short loc_100429CB0
0x100429c53  mov     rax, cs:__imp_?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A; SOS_ResourceManager SOS_PublicGlobals::sm_ResourceManager
0x100429c5a  test    byte ptr [rax+68h], 1
0x100429c5e  jz      short loc_100429CB0
0x100429c60  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100429c67  test    byte ptr [rax+0C0h], 10h
0x100429c6e  jnz     short loc_100429CB0
0x100429c70  call    cs:__imp_?GetManager@SOS_IOResourceManager@@SAPEAV1@XZ; SOS_IOResourceManager::GetManager(void)
0x100429c76  or      dword ptr [rax+40h], 400h
0x100429c7d  add     rsp, 20h
0x100429c81  pop     rbx
0x100429c82  retn
0x100429c83  test    bl, bl
0x100429c85  jz      short loc_100429C36
0x100429c87  mov     rax, cs:__imp_?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A; SOS_ResourceManager SOS_PublicGlobals::sm_ResourceManager
0x100429c8e  test    byte ptr [rax+68h], 1
0x100429c92  jz      short loc_100429C36
0x100429c94  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x100429c9b  test    byte ptr [rax+0C0h], 10h
0x100429ca2  jnz     short loc_100429C36
0x100429ca4  call    cs:__imp_?GetManager@SOS_IOResourceManager@@SAPEAV1@XZ; SOS_IOResourceManager::GetManager(void)
0x100429caa  or      dword ptr [rax+40h], 4
0x100429cae  jmp     short loc_100429C44
0x100429cb0  call    cs:__imp_?GetManager@SOS_IOResourceManager@@SAPEAV1@XZ; SOS_IOResourceManager::GetManager(void)
0x100429cb6  and     dword ptr [rax+40h], 0FFFFFBFFh
0x100429cbd  add     rsp, 20h
0x100429cc1  pop     rbx
0x100429cc2  retn
```
