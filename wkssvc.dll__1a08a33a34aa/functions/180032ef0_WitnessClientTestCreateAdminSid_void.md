# WitnessClientTestCreateAdminSid(void)

- ea: `0x180032ef0`
- end: `0x180032fb8`
- name: `?WitnessClientTestCreateAdminSid@@YAKXZ`
- size: `200`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180032fc0`

## callees

- `0x18000c1b4`
- `0x180024550`
- `0x180032ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f63`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180032f09`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180032f53`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180032f09`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180032f53`

## pseudocode

```c
__int64 WitnessClientTestCreateAdminSid(void)
{
  DWORD LastError; // ebx
  void *v1; // rax
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF

  LastError = 0;
  cbSid = 0;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, 0, &cbSid) )
  {
    if ( GetLastError() == 122 )
    {
      v1 = MemoryAlloc(cbSid);
      g_AdminSid = v1;
      if ( v1 )
      {
        if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v1, &cbSid) )
          LastError = GetLastError();
      }
      else
      {
        LastError = 1450;
      }
    }
    else
    {
      LastError = 31;
    }
  }
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
      10,
      WPP_928f46f8e8b33892db621c8a8e2317d7_Traceguids,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180032ef0  push    rbx
0x180032ef2  sub     rsp, 20h
0x180032ef6  xor     ebx, ebx
0x180032ef8  lea     r9, [rsp+28h+cbSid]; cbSid
0x180032efd  xor     r8d, r8d; pSid
0x180032f00  mov     [rsp+28h+cbSid], ebx
0x180032f04  xor     edx, edx; DomainSid
0x180032f06  lea     ecx, [rbx+1Ah]; WellKnownSidType
0x180032f09  call    cs:__imp_CreateWellKnownSid
0x180032f10  nop     dword ptr [rax+rax+00h]
0x180032f15  test    eax, eax
0x180032f17  jnz     short loc_180032F78
0x180032f19  call    cs:__imp_GetLastError
0x180032f20  nop     dword ptr [rax+rax+00h]
0x180032f25  cmp     eax, 7Ah ; 'z'
0x180032f28  jnz     short loc_180032F73
0x180032f2a  mov     ecx, [rsp+28h+cbSid]; unsigned __int64
0x180032f2e  call    ?MemoryAlloc@@YAPEAX_K@Z; MemoryAlloc(unsigned __int64)
0x180032f33  mov     cs:?g_AdminSid@@3PEAXEA, rax; void * g_AdminSid
0x180032f3a  test    rax, rax
0x180032f3d  jnz     short loc_180032F46
0x180032f3f  mov     ebx, 5AAh
0x180032f44  jmp     short loc_180032F78
0x180032f46  xor     edx, edx; DomainSid
0x180032f48  lea     r9, [rsp+28h+cbSid]; cbSid
0x180032f4d  mov     r8, rax; pSid
0x180032f50  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180032f53  call    cs:__imp_CreateWellKnownSid
0x180032f5a  nop     dword ptr [rax+rax+00h]
0x180032f5f  test    eax, eax
0x180032f61  jnz     short loc_180032F78
0x180032f63  call    cs:__imp_GetLastError
0x180032f6a  nop     dword ptr [rax+rax+00h]
0x180032f6f  mov     ebx, eax
0x180032f71  jmp     short loc_180032F78
0x180032f73  mov     ebx, 1Fh
0x180032f78  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180032f7f  lea     rax, WPP_witness_GLOBAL_Control
0x180032f86  cmp     rcx, rax
0x180032f89  jz      short loc_180032FAF
0x180032f8b  test    byte ptr [rcx+1Ch], 1
0x180032f8f  jz      short loc_180032FAF
0x180032f91  cmp     byte ptr [rcx+19h], 3
0x180032f95  jb      short loc_180032FAF
0x180032f97  mov     rcx, [rcx+10h]
0x180032f9b  lea     r8, WPP_928f46f8e8b33892db621c8a8e2317d7_Traceguids
0x180032fa2  mov     edx, 0Ah
0x180032fa7  mov     r9d, ebx
0x180032faa  call    WPP_SF_d
0x180032faf  mov     eax, ebx
0x180032fb1  add     rsp, 20h
0x180032fb5  pop     rbx
0x180032fb6  retn
```
