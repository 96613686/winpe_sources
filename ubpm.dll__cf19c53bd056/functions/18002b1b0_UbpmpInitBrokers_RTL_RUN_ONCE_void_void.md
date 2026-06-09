# UbpmpInitBrokers(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18002b1b0`
- end: `0x18002b251`
- name: `?UbpmpInitBrokers@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `161`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002b1b0`
- `0x180032e38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b1ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b1ff`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002b1dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002b1dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b243`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b243`

## pseudocode

```c
__int64 __fastcall UbpmpInitBrokers(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  unsigned int v3; // ebx
  DWORD LastError; // eax
  PSECURITY_DESCRIPTOR v5; // rcx
  PSECURITY_DESCRIPTOR v7; // [rsp+20h] [rbp-18h] BYREF
  ULONG v8; // [rsp+58h] [rbp+20h] BYREF

  v3 = 1;
  v7 = 0;
  v8 = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;SY)", 1u, &v7, &v8) )
  {
    g_pSecurityDescriptor = v7;
    v5 = 0;
    v7 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids, LastError);
    }
    v5 = v7;
    v3 = 0;
  }
  if ( v5 )
    LocalFree(v5);
  return v3;
}

```

## disassembly

```asm
0x18002b1b0  mov     rax, rsp
0x18002b1b3  push    rbx
0x18002b1b4  sub     rsp, 30h
0x18002b1b8  mov     ebx, 1
0x18002b1bd  mov     qword ptr [rax-18h], 0
0x18002b1c5  mov     edx, ebx; StringSDRevision
0x18002b1c7  mov     dword ptr [rax+20h], 0
0x18002b1ce  lea     r9, [rax+20h]; SecurityDescriptorSize
0x18002b1d2  lea     r8, [rax-18h]; SecurityDescriptor
0x18002b1d6  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)"
0x18002b1dd  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002b1e3  test    eax, eax
0x18002b1e5  jnz     short loc_18002B22B
0x18002b1e7  mov     rax, cs:WPP_GLOBAL_Control
0x18002b1ee  lea     rcx, WPP_GLOBAL_Control
0x18002b1f5  cmp     rax, rcx
0x18002b1f8  jz      short loc_18002B222
0x18002b1fa  test    [rax+1Ch], bl
0x18002b1fd  jz      short loc_18002B222
0x18002b1ff  call    cs:__imp_GetLastError
0x18002b205  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b20c  lea     edx, [rbx+1Bh]
0x18002b20f  mov     r9d, eax
0x18002b212  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x18002b219  mov     rcx, [rcx+10h]
0x18002b21d  call    WPP_SF_d
0x18002b222  mov     rcx, [rsp+38h+var_18]
0x18002b227  xor     ebx, ebx
0x18002b229  jmp     short loc_18002B23E
0x18002b22b  mov     rcx, [rsp+38h+var_18]
0x18002b230  mov     cs:?g_pSecurityDescriptor@@3PEAXEA, rcx; void * g_pSecurityDescriptor
0x18002b237  xor     ecx, ecx; hMem
0x18002b239  mov     [rsp+38h+var_18], rcx
0x18002b23e  test    rcx, rcx
0x18002b241  jz      short loc_18002B249
0x18002b243  call    cs:__imp_LocalFree
0x18002b249  mov     eax, ebx
0x18002b24b  add     rsp, 30h
0x18002b24f  pop     rbx
0x18002b250  retn
```
