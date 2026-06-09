# SsUnregisterVolumeChange

- ea: `0x18002e448`
- end: `0x18002e599`
- name: `SsUnregisterVolumeChange`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002dbc0`

## callees

- `0x180020dc0`
- `0x18002e448`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e569`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e572`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e569`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e572`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e4ed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e4ed`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002e4ac`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002e4ac`
- `ntdll!RtlReleaseResource` at `0x18002e555`
- `ntdll!RtlReleaseResource` at `0x18002e588`
- `ntdll!RtlReleaseResource` at `0x18002e555`
- `ntdll!RtlReleaseResource` at `0x18002e588`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18002e55f`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x18002e55f`

## pseudocode

```c
void __fastcall SsUnregisterVolumeChange(__int64 a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  HLOCAL *v4; // rbx
  HLOCAL *v5; // rdx
  _QWORD *v6; // rax
  HLOCAL *v7; // rdx

  if ( !SsVolumeResourceInitialized )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v3 = 95;
LABEL_6:
      WPP_SF_(v2[2], v3, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids);
    }
    return;
  }
  RtlAcquireResourceExclusive(&SsVolumeResource, 1u);
  v4 = (HLOCAL *)SsVolumeList;
  v5 = (HLOCAL *)(a1 + 8);
  while ( 1 )
  {
    if ( v4 == &SsVolumeList )
    {
      RtlReleaseResource(&SsVolumeResource);
      return;
    }
    if ( *(_WORD *)a1 != 1 )
      break;
    if ( v4[2] == *v5 )
    {
LABEL_19:
      v6 = *v4;
      if ( *((HLOCAL **)*v4 + 1) != v4 || (v7 = (HLOCAL *)v4[1], *v7 != v4) )
        __fastfail(3u);
      *v7 = v6;
      v6[1] = v7;
      RtlReleaseResource(&SsVolumeResource);
      CM_Unregister_Notification(v4[2]);
      LocalFree(v4[3]);
      LocalFree(v4);
      return;
    }
LABEL_14:
    v4 = (HLOCAL *)*v4;
  }
  if ( *(_WORD *)a1 == 2 )
  {
    if ( CompareStringOrdinal((LPCWCH)v4[3], -1, *(LPCWCH *)(a1 + 8), -1, 1) == 2 )
      goto LABEL_19;
    v5 = (HLOCAL *)(a1 + 8);
    goto LABEL_14;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v3 = 96;
    goto LABEL_6;
  }
}

```

## disassembly

```asm
0x18002e448  mov     [rsp+arg_0], rbx
0x18002e44d  push    rdi
0x18002e44e  sub     rsp, 30h
0x18002e452  cmp     cs:SsVolumeResourceInitialized, 0
0x18002e459  mov     rdi, rcx
0x18002e45c  jnz     short loc_18002E4A3
0x18002e45e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e465  lea     rax, WPP_GLOBAL_Control
0x18002e46c  cmp     rcx, rax
0x18002e46f  jz      loc_18002E58E
0x18002e475  test    byte ptr [rcx+1Ch], 1
0x18002e479  jz      loc_18002E58E
0x18002e47f  cmp     byte ptr [rcx+19h], 1
0x18002e483  jb      loc_18002E58E
0x18002e489  mov     edx, 5Fh ; '_'
0x18002e48e  mov     rcx, [rcx+10h]
0x18002e492  lea     r8, WPP_539c1b1611e137709d0d7dc2103426d1_Traceguids
0x18002e499  call    WPP_SF_
0x18002e49e  jmp     loc_18002E58E
0x18002e4a3  mov     dl, 1; Wait
0x18002e4a5  lea     rcx, SsVolumeResource; Resource
0x18002e4ac  call    cs:__imp_RtlAcquireResourceExclusive
0x18002e4b2  mov     rbx, cs:SsVolumeList
0x18002e4b9  lea     rdx, [rdi+8]
0x18002e4bd  lea     rax, SsVolumeList
0x18002e4c4  cmp     rbx, rax
0x18002e4c7  jz      loc_18002E581
0x18002e4cd  movzx   ecx, word ptr [rdi]
0x18002e4d0  sub     ecx, 1
0x18002e4d3  jz      short loc_18002E4FE
0x18002e4d5  cmp     ecx, 1
0x18002e4d8  jnz     short loc_18002E50C
0x18002e4da  mov     r8, [rdi+8]; lpString2
0x18002e4de  or      r9d, 0FFFFFFFFh; cchCount2
0x18002e4e2  mov     [rsp+38h+bIgnoreCase], ecx; bIgnoreCase
0x18002e4e6  or      edx, r9d; cchCount1
0x18002e4e9  mov     rcx, [rbx+18h]; lpString1
0x18002e4ed  call    cs:__imp_CompareStringOrdinal
0x18002e4f3  cmp     eax, 2
0x18002e4f6  jz      short loc_18002E535
0x18002e4f8  lea     rdx, [rdi+8]
0x18002e4fc  jmp     short loc_18002E507
0x18002e4fe  mov     rax, [rdx]
0x18002e501  cmp     [rbx+10h], rax
0x18002e505  jz      short loc_18002E535
0x18002e507  mov     rbx, [rbx]
0x18002e50a  jmp     short loc_18002E4BD
0x18002e50c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e513  lea     rax, WPP_GLOBAL_Control
0x18002e51a  cmp     rcx, rax
0x18002e51d  jz      short loc_18002E58E
0x18002e51f  test    byte ptr [rcx+1Ch], 1
0x18002e523  jz      short loc_18002E58E
0x18002e525  cmp     byte ptr [rcx+19h], 1
0x18002e529  jb      short loc_18002E58E
0x18002e52b  mov     edx, 60h ; '`'
0x18002e530  jmp     loc_18002E48E
0x18002e535  mov     rax, [rbx]
0x18002e538  cmp     [rax+8], rbx
0x18002e53c  jnz     short loc_18002E57A
0x18002e53e  mov     rdx, [rbx+8]
0x18002e542  cmp     [rdx], rbx
0x18002e545  jnz     short loc_18002E57A
0x18002e547  mov     [rdx], rax
0x18002e54a  lea     rcx, SsVolumeResource; Resource
0x18002e551  mov     [rax+8], rdx
0x18002e555  call    cs:__imp_RtlReleaseResource
0x18002e55b  mov     rcx, [rbx+10h]
0x18002e55f  call    cs:__imp_CM_Unregister_Notification
0x18002e565  mov     rcx, [rbx+18h]; hMem
0x18002e569  call    cs:__imp_LocalFree
0x18002e56f  mov     rcx, rbx; hMem
0x18002e572  call    cs:__imp_LocalFree
0x18002e578  jmp     short loc_18002E58E
0x18002e57a  mov     ecx, 3
0x18002e57f  int     29h; Win8: RtlFailFast(ecx)
0x18002e581  lea     rcx, SsVolumeResource; Resource
0x18002e588  call    cs:__imp_RtlReleaseResource
0x18002e58e  mov     rbx, [rsp+38h+arg_0]
0x18002e593  add     rsp, 30h
0x18002e597  pop     rdi
0x18002e598  retn
```
