# SampEnableAuditPrivilege(void)

- ea: `0x180079688`
- end: `0x1800797c4`
- name: `?SampEnableAuditPrivilege@@YAJXZ`
- size: `316`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800799a8`

## callees

- `0x180027e24`
- `0x180079688`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x1800796b0`
- `ntdll!NtOpenProcessToken` at `0x1800796b0`
- `ntdll!NtAdjustPrivilegesToken` at `0x180079760`
- `ntdll!NtAdjustPrivilegesToken` at `0x180079760`
- `ntdll!RtlFreeHeap` at `0x18007977a`
- `ntdll!RtlFreeHeap` at `0x18007977a`
- `ntdll!RtlAllocateHeap` at `0x1800796f6`
- `ntdll!RtlAllocateHeap` at `0x1800796f6`
- `ntdll!NtClose` at `0x180079785`
- `ntdll!NtClose` at `0x180079785`

## pseudocode

```c
__int64 SampEnableAuditPrivilege(void)
{
  NTSTATUS v0; // ebx
  PUNICODE_STRING v1; // rcx
  __int64 v2; // rdx
  char *Heap; // rax
  void *v4; // rdi
  __int64 v5; // r9
  ULONG ReturnLength; // [rsp+40h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp+10h] BYREF
  __int64 v9; // [rsp+50h] [rbp+18h]

  TokenHandle = 0;
  ReturnLength = 0;
  v0 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x20u, &TokenHandle);
  if ( v0 >= 0 )
  {
    v9 = 21;
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x64u);
    v4 = Heap;
    if ( Heap )
    {
      *(_DWORD *)Heap = 1;
      *(_QWORD *)(Heap + 4) = v9;
      *((_DWORD *)Heap + 3) = 2;
      v0 = NtAdjustPrivilegesToken(TokenHandle, 0, (PTOKEN_PRIVILEGES)Heap, 0, 0, &ReturnLength);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
      NtClose(TokenHandle);
      v1 = WPP_GLOBAL_Control;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v2 = 192;
        goto LABEL_9;
      }
    }
    else
    {
      v1 = WPP_GLOBAL_Control;
      v0 = -1073741670;
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v2 = 191;
        v5 = 3221225626LL;
LABEL_10:
        WPP_SF_Dd(v1[3].Buffer, v2, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v5, v0);
      }
    }
  }
  else
  {
    v1 = WPP_GLOBAL_Control;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v2 = 190;
LABEL_9:
      v5 = (unsigned int)v0;
      goto LABEL_10;
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180079688  mov     rax, rsp
0x18007968b  mov     [rax+20h], rbx
0x18007968f  push    rdi
0x180079690  sub     rsp, 30h
0x180079694  lea     r8, [rax+10h]; TokenHandle
0x180079698  mov     qword ptr [rax+10h], 0
0x1800796a0  mov     edx, 20h ; ' '; DesiredAccess
0x1800796a5  mov     dword ptr [rax+8], 0
0x1800796ac  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800796b0  call    cs:__imp_NtOpenProcessToken
0x1800796b6  mov     ebx, eax
0x1800796b8  test    eax, eax
0x1800796ba  jns     short loc_1800796DA
0x1800796bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800796c3  test    dword ptr [rcx+44h], 20000h
0x1800796ca  jz      loc_1800797B7
0x1800796d0  mov     edx, 0BEh
0x1800796d5  jmp     loc_1800797A0
0x1800796da  mov     rcx, gs:60h
0x1800796e3  xor     edx, edx; Flags
0x1800796e5  mov     [rsp+38h+arg_10], 15h
0x1800796ee  mov     rcx, [rcx+30h]; HeapHandle
0x1800796f2  lea     r8d, [rdx+64h]; Size
0x1800796f6  call    cs:__imp_RtlAllocateHeap
0x1800796fc  mov     rdi, rax
0x1800796ff  test    rax, rax
0x180079702  jnz     short loc_18007972A
0x180079704  mov     rcx, cs:WPP_GLOBAL_Control
0x18007970b  mov     ebx, 0C000009Ah
0x180079710  test    dword ptr [rcx+44h], 20000h
0x180079717  jz      loc_1800797B7
0x18007971d  mov     edx, 0BFh
0x180079722  mov     r9d, 0C000009Ah
0x180079728  jmp     short loc_1800797A3
0x18007972a  mov     dword ptr [rax], 1
0x180079730  xor     r9d, r9d; BufferLength
0x180079733  mov     rax, [rsp+38h+arg_10]
0x180079738  mov     r8, rdi; NewState
0x18007973b  mov     [rdi+4], rax
0x18007973f  xor     edx, edx; DisableAllPrivileges
0x180079741  lea     rax, [rsp+38h+arg_0]
0x180079746  mov     dword ptr [rdi+0Ch], 2
0x18007974d  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180079752  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180079757  mov     [rsp+38h+PreviousState], 0; PreviousState
0x180079760  call    cs:__imp_NtAdjustPrivilegesToken
0x180079766  mov     rcx, gs:60h
0x18007976f  mov     r8, rdi; P
0x180079772  xor     edx, edx; Flags
0x180079774  mov     ebx, eax
0x180079776  mov     rcx, [rcx+30h]; HeapHandle
0x18007977a  call    cs:__imp_RtlFreeHeap
0x180079780  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x180079785  call    cs:__imp_NtClose
0x18007978b  mov     rcx, cs:WPP_GLOBAL_Control
0x180079792  test    dword ptr [rcx+44h], 20000h
0x180079799  jz      short loc_1800797B7
0x18007979b  mov     edx, 0C0h
0x1800797a0  mov     r9d, ebx
0x1800797a3  mov     rcx, [rcx+38h]
0x1800797a7  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x1800797ae  mov     dword ptr [rsp+38h+PreviousState], ebx
0x1800797b2  call    WPP_SF_Dd
0x1800797b7  mov     eax, ebx
0x1800797b9  mov     rbx, [rsp+38h+arg_18]
0x1800797be  add     rsp, 30h
0x1800797c2  pop     rdi
0x1800797c3  retn
```
