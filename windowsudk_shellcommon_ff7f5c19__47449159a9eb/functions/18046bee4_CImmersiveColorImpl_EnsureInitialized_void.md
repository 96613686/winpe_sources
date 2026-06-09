# CImmersiveColorImpl::EnsureInitialized(void)

- ea: `0x18046bee4`
- end: `0x18046c089`
- name: `?EnsureInitialized@CImmersiveColorImpl@@SAJXZ`
- size: `421`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18046c28c`
- `0x18046c9b0`

## callees

- `0x1800b0dc8`
- `0x18011e218`
- `0x180156c38`
- `0x180414194`
- `0x18046be6c`
- `0x18046bee4`
- `0x18046c4bc`
- `0x18046c530`
- `0x18046c8a4`
- `0x18046cdd8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18046c032`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18046c03d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18046c032`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18046c03d`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18046bf39`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18046bf4d`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18046bf39`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18046bf4d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18046bf74`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18046bf74`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18046bfbe`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18046bfbe`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18046c019`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18046c019`

## pseudocode

```c
__int64 CImmersiveColorImpl::EnsureInitialized(void)
{
  int v0; // ebx
  volatile bool v1; // bl
  char v2; // di
  HANDLE FileMappingW; // rax
  struct IMMERSIVE_COLOR_PREFERENCE *v4; // rcx
  LPWSTR StringSid; // [rsp+40h] [rbp+8h] BYREF
  PSID Sid; // [rsp+48h] [rbp+10h] BYREF

  v0 = 0;
  if ( !g_fColorDataInitialized )
  {
    v0 = CImmersiveColorImpl::AcquireColorMutex();
    if ( v0 >= 0 )
    {
      if ( g_fColorDataInitialized )
      {
LABEL_19:
        CImmersiveColorImpl::ReleaseColorMutex();
        return (unsigned int)v0;
      }
      v1 = 1;
      v2 = 0;
      FileMappingW = OpenFileMappingW(0xF001Fu, 1, L"Local\\SessionImmersiveColorPreference");
      if ( !FileMappingW )
      {
        FileMappingW = OpenFileMappingW(4u, 1, L"Local\\SessionImmersiveColorPreference");
        v1 = 0;
        if ( !FileMappingW )
        {
          FileMappingW = CreateFileMappingW(
                           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                           0,
                           4u,
                           0,
                           8u,
                           L"Local\\SessionImmersiveColorPreference");
          if ( !FileMappingW )
          {
LABEL_18:
            v0 = -2147467259;
            goto LABEL_19;
          }
          v1 = 1;
          v2 = 1;
        }
      }
      g_hColorPreferenceMapping = FileMappingW;
      g_fColorPreferenceMappingWritable = v1;
      g_pcpColorPreference = (BYTE *)MapViewOfFile(FileMappingW, v1 ? 983071 : 4, 0, 0, 8u);
      if ( g_pcpColorPreference )
      {
        v0 = 0;
        if ( v2 )
        {
          CImmersiveColorImpl::GetColorPreferenceFromRegistry(g_pcpColorPreference);
          if ( !IsCurrentUserLocalSystem() )
          {
            Sid = 0;
            if ( (int)GetCurrentUserSid(&Sid) >= 0 )
            {
              StringSid = 0;
              if ( ConvertSidToStringSidW(Sid, &StringSid) )
              {
                CImmersiveColorImpl::SetACLOnSharedObjectsforUser(StringSid);
                LocalFree(StringSid);
              }
              LocalFree(Sid);
            }
          }
        }
        if ( (unsigned int)IsOS_OS_ANYSERVER() )
          g_cpDefaultColorPreference = g_cpDefaultServerColorPreference;
        CImmersiveColorImpl::GetDefaultColorPreferenceFromRegistry(v4);
        RefreshImmersiveColorPolicyState();
        g_fColorDataInitialized = 1;
        goto LABEL_19;
      }
      goto LABEL_18;
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18046bee4  mov     [rsp+arg_10], rbx
0x18046bee9  mov     [rsp+arg_18], rbp
0x18046beee  push    rdi
0x18046beef  sub     rsp, 30h
0x18046bef3  mov     al, cs:?g_fColorDataInitialized@@3_NC; bool volatile g_fColorDataInitialized
0x18046bef9  xor     ebx, ebx
0x18046befb  test    al, al
0x18046befd  jnz     loc_18046C077
0x18046bf03  call    ?AcquireColorMutex@CImmersiveColorImpl@@SAJXZ; CImmersiveColorImpl::AcquireColorMutex(void)
0x18046bf08  mov     ebx, eax
0x18046bf0a  test    eax, eax
0x18046bf0c  js      loc_18046C077
0x18046bf12  mov     cl, cs:?g_fColorDataInitialized@@3_NC; bool volatile g_fColorDataInitialized
0x18046bf18  test    cl, cl
0x18046bf1a  jnz     loc_18046C072
0x18046bf20  lea     rbp, aLocalSessionim; "Local\\SessionImmersiveColorPreference"
0x18046bf27  mov     edx, 1; bInheritHandle
0x18046bf2c  mov     r8, rbp; lpName
0x18046bf2f  mov     ecx, 0F001Fh; dwDesiredAccess
0x18046bf34  mov     bl, 1
0x18046bf36  xor     dil, dil
0x18046bf39  call    cs:__imp_OpenFileMappingW
0x18046bf3f  test    rax, rax
0x18046bf42  jnz     short loc_18046BF88
0x18046bf44  mov     r8, rbp; lpName
0x18046bf47  lea     edx, [rax+1]; bInheritHandle
0x18046bf4a  lea     ecx, [rax+4]; dwDesiredAccess
0x18046bf4d  call    cs:__imp_OpenFileMappingW
0x18046bf53  xor     bl, bl
0x18046bf55  test    rax, rax
0x18046bf58  jnz     short loc_18046BF88
0x18046bf5a  mov     [rsp+38h+lpName], rbp; lpName
0x18046bf5f  lea     r8d, [rax+4]; flProtect
0x18046bf63  xor     r9d, r9d; dwMaximumSizeHigh
0x18046bf66  mov     [rsp+38h+dwMaximumSizeLow], 8; dwMaximumSizeLow
0x18046bf6e  xor     edx, edx; lpFileMappingAttributes
0x18046bf70  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18046bf74  call    cs:__imp_CreateFileMappingW
0x18046bf7a  test    rax, rax
0x18046bf7d  jz      loc_18046C06D
0x18046bf83  mov     bl, 1
0x18046bf85  mov     dil, bl
0x18046bf88  mov     cs:?g_hColorPreferenceMapping@@3REAXEA, rax; void * g_hColorPreferenceMapping
0x18046bf8f  mov     cs:?g_fColorPreferenceMappingWritable@@3_NC, bl; bool volatile g_fColorPreferenceMappingWritable
0x18046bf95  mov     al, cs:?g_fColorPreferenceMappingWritable@@3_NC; bool volatile g_fColorPreferenceMappingWritable
0x18046bf9b  mov     rcx, cs:?g_hColorPreferenceMapping@@3REAXEA; hFileMappingObject
0x18046bfa2  neg     al
0x18046bfa4  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 8; dwNumberOfBytesToMap
0x18046bfad  sbb     edx, edx
0x18046bfaf  xor     r9d, r9d; dwFileOffsetLow
0x18046bfb2  and     edx, 0F001Bh
0x18046bfb8  xor     r8d, r8d; dwFileOffsetHigh
0x18046bfbb  add     edx, 4; dwDesiredAccess
0x18046bfbe  call    cs:__imp_MapViewOfFile
0x18046bfc4  mov     cs:?g_pcpColorPreference@@3REAUIMMERSIVE_COLOR_PREFERENCE@@EA, rax; IMMERSIVE_COLOR_PREFERENCE * g_pcpColorPreference
0x18046bfcb  mov     rax, cs:?g_pcpColorPreference@@3REAUIMMERSIVE_COLOR_PREFERENCE@@EA; IMMERSIVE_COLOR_PREFERENCE * g_pcpColorPreference
0x18046bfd2  test    rax, rax
0x18046bfd5  jz      loc_18046C06D
0x18046bfdb  xor     ebx, ebx
0x18046bfdd  test    dil, dil
0x18046bfe0  jz      short loc_18046C043
0x18046bfe2  mov     rcx, cs:?g_pcpColorPreference@@3REAUIMMERSIVE_COLOR_PREFERENCE@@EA; lpData
0x18046bfe9  call    ?GetColorPreferenceFromRegistry@CImmersiveColorImpl@@CAJPEAUIMMERSIVE_COLOR_PREFERENCE@@@Z; CImmersiveColorImpl::GetColorPreferenceFromRegistry(IMMERSIVE_COLOR_PREFERENCE *)
0x18046bfee  call    ?IsCurrentUserLocalSystem@@YA_NXZ; IsCurrentUserLocalSystem(void)
0x18046bff3  test    al, al
0x18046bff5  jnz     short loc_18046C043
0x18046bff7  lea     rcx, [rsp+38h+Sid]; void **
0x18046bffc  mov     [rsp+38h+Sid], rbx
0x18046c001  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x18046c006  test    eax, eax
0x18046c008  js      short loc_18046C043
0x18046c00a  mov     rcx, [rsp+38h+Sid]; Sid
0x18046c00f  lea     rdx, [rsp+38h+StringSid]; StringSid
0x18046c014  mov     [rsp+38h+StringSid], rbx
0x18046c019  call    cs:__imp_ConvertSidToStringSidW
0x18046c01f  test    eax, eax
0x18046c021  jz      short loc_18046C038
0x18046c023  mov     rcx, [rsp+38h+StringSid]; unsigned __int16 *
0x18046c028  call    ?SetACLOnSharedObjectsforUser@CImmersiveColorImpl@@SAJPEBG@Z; CImmersiveColorImpl::SetACLOnSharedObjectsforUser(ushort const *)
0x18046c02d  mov     rcx, [rsp+38h+StringSid]; hMem
0x18046c032  call    cs:__imp_LocalFree
0x18046c038  mov     rcx, [rsp+38h+Sid]; hMem
0x18046c03d  call    cs:__imp_LocalFree
0x18046c043  call    ?IsOS_OS_ANYSERVER@@YAHXZ; IsOS_OS_ANYSERVER(void)
0x18046c048  test    eax, eax
0x18046c04a  jz      short loc_18046C05A
0x18046c04c  mov     rax, cs:?g_cpDefaultServerColorPreference@@3UIMMERSIVE_COLOR_PREFERENCE@@A; IMMERSIVE_COLOR_PREFERENCE g_cpDefaultServerColorPreference
0x18046c053  mov     cs:?g_cpDefaultColorPreference@@3UIMMERSIVE_COLOR_PREFERENCE@@A, rax; IMMERSIVE_COLOR_PREFERENCE g_cpDefaultColorPreference
0x18046c05a  call    ?GetDefaultColorPreferenceFromRegistry@CImmersiveColorImpl@@CAJPEAUIMMERSIVE_COLOR_PREFERENCE@@@Z; CImmersiveColorImpl::GetDefaultColorPreferenceFromRegistry(IMMERSIVE_COLOR_PREFERENCE *)
0x18046c05f  call    RefreshImmersiveColorPolicyState
0x18046c064  mov     cs:?g_fColorDataInitialized@@3_NC, 1; bool volatile g_fColorDataInitialized
0x18046c06b  jmp     short loc_18046C072
0x18046c06d  mov     ebx, 80004005h
0x18046c072  call    ?ReleaseColorMutex@CImmersiveColorImpl@@SAXXZ; CImmersiveColorImpl::ReleaseColorMutex(void)
0x18046c077  mov     rbp, [rsp+38h+arg_18]
0x18046c07c  mov     eax, ebx
0x18046c07e  mov     rbx, [rsp+38h+arg_10]
0x18046c083  add     rsp, 30h
0x18046c087  pop     rdi
0x18046c088  retn
```
