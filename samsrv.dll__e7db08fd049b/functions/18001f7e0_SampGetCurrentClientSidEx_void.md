# SampGetCurrentClientSidEx(void * *)

- ea: `0x18001f7e0`
- end: `0x18001f8f0`
- name: `?SampGetCurrentClientSidEx@@YAJPEAPEAX@Z`
- size: `272`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005ed6c`

## callees

- `0x18001ce50`
- `0x18001f7e0`
- `0x180027e24`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18001f858`
- `ntdll!RtlLengthSid` at `0x18001f858`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f867`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f867`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f8c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f8c4`
- `LSASRV!LsaIRetrieveCurrentUserSid` at `0x18001f809`
- `LSASRV!LsaIRetrieveCurrentUserSid` at `0x18001f809`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001f831`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001f831`

## pseudocode

```c
__int64 __fastcall SampGetCurrentClientSidEx(void **a1)
{
  struct _TOKEN_USER *v2; // rdi
  int v3; // esi
  int v4; // ebx
  SIZE_T v6; // rbp
  HLOCAL v7; // rax
  int CurrentUser; // eax
  int v9; // [rsp+60h] [rbp+8h] BYREF
  PVOID Buffer; // [rsp+68h] [rbp+10h] BYREF
  struct _TOKEN_USER *v11; // [rsp+70h] [rbp+18h] BYREF

  *a1 = 0;
  v2 = 0;
  Buffer = 0;
  v11 = 0;
  v3 = 1;
  v4 = LsaIRetrieveCurrentUserSid(&Buffer);
  if ( v4 < 0 )
  {
    v9 = 0;
    CurrentUser = SampGetCurrentUser(0, (HLOCAL *)&v11, &v9);
    v2 = v11;
    v4 = CurrentUser;
    if ( CurrentUser >= 0 )
    {
      v3 = 0;
      Buffer = v11->User.Sid;
    }
  }
  if ( Buffer )
  {
    v6 = RtlLengthSid(Buffer);
    v7 = LocalAlloc(0x40u, v6);
    *a1 = v7;
    if ( v7 )
      memcpy_0(v7, Buffer, v6);
    else
      v4 = -1073741670;
  }
  if ( v2 )
    LocalFree(v2);
  if ( v3 )
    LsaFreeMemory(Buffer);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 75, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, (unsigned int)v4, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001f7e0  push    rbx
0x18001f7e2  push    rbp
0x18001f7e3  push    rsi
0x18001f7e4  push    rdi
0x18001f7e5  push    r14
0x18001f7e7  sub     rsp, 30h
0x18001f7eb  xor     ebp, ebp
0x18001f7ed  mov     r14, rcx
0x18001f7f0  mov     [rcx], rbp
0x18001f7f3  mov     edi, ebp
0x18001f7f5  lea     rcx, [rsp+58h+Buffer]
0x18001f7fa  mov     [rsp+58h+Buffer], rbp
0x18001f7ff  mov     [rsp+58h+arg_10], rbp
0x18001f804  mov     esi, 1
0x18001f809  call    cs:__imp_LsaIRetrieveCurrentUserSid
0x18001f80f  mov     ebx, eax
0x18001f811  test    eax, eax
0x18001f813  js      short loc_18001F88E
0x18001f815  mov     rcx, [rsp+58h+Buffer]; Sid
0x18001f81a  test    rcx, rcx
0x18001f81d  jnz     short loc_18001F858
0x18001f81f  test    rdi, rdi
0x18001f822  jnz     loc_18001F8C1
0x18001f828  test    esi, esi
0x18001f82a  jz      short loc_18001F837
0x18001f82c  mov     rcx, [rsp+58h+Buffer]; Buffer
0x18001f831  call    cs:__imp_LsaFreeMemory
0x18001f837  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f83e  test    dword ptr [rcx+44h], 20000h
0x18001f845  jnz     loc_18001F8CF
0x18001f84b  mov     eax, ebx
0x18001f84d  add     rsp, 30h
0x18001f851  pop     r14
0x18001f853  pop     rdi
0x18001f854  pop     rsi
0x18001f855  pop     rbp
0x18001f856  pop     rbx
0x18001f857  retn
0x18001f858  call    cs:__imp_RtlLengthSid
0x18001f85e  mov     edx, eax; uBytes
0x18001f860  mov     ecx, 40h ; '@'; uFlags
0x18001f865  mov     ebp, eax
0x18001f867  call    cs:__imp_LocalAlloc
0x18001f86d  mov     [r14], rax
0x18001f870  test    rax, rax
0x18001f873  jnz     short loc_18001F87C
0x18001f875  mov     ebx, 0C000009Ah
0x18001f87a  jmp     short loc_18001F81F
0x18001f87c  mov     rdx, [rsp+58h+Buffer]; Src
0x18001f881  mov     r8, rbp; Size
0x18001f884  mov     rcx, rax; void *
0x18001f887  call    memcpy_0
0x18001f88c  jmp     short loc_18001F81F
0x18001f88e  lea     r8, [rsp+58h+arg_0]; int *
0x18001f893  mov     [rsp+58h+arg_0], ebp
0x18001f897  lea     rdx, [rsp+58h+arg_10]; struct _TOKEN_USER **
0x18001f89c  xor     ecx, ecx; TokenHandle
0x18001f89e  call    ?SampGetCurrentUser@@YAJPEAXPEAPEAU_TOKEN_USER@@PEAH@Z; SampGetCurrentUser(void *,_TOKEN_USER * *,int *)
0x18001f8a3  mov     rdi, [rsp+58h+arg_10]
0x18001f8a8  mov     ebx, eax
0x18001f8aa  test    eax, eax
0x18001f8ac  js      loc_18001F815
0x18001f8b2  mov     rax, [rdi]
0x18001f8b5  mov     esi, ebp
0x18001f8b7  mov     [rsp+58h+Buffer], rax
0x18001f8bc  jmp     loc_18001F815
0x18001f8c1  mov     rcx, rdi; hMem
0x18001f8c4  call    cs:__imp_LocalFree
0x18001f8ca  jmp     loc_18001F828
0x18001f8cf  mov     rcx, [rcx+38h]
0x18001f8d3  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18001f8da  mov     edx, 4Bh ; 'K'
0x18001f8df  mov     [rsp+58h+var_38], ebx
0x18001f8e3  mov     r9d, ebx
0x18001f8e6  call    WPP_SF_Dd
0x18001f8eb  jmp     loc_18001F84B
```
