# SampGetCurrentClientSid(void *,void * *,int *)

- ea: `0x18001ca48`
- end: `0x18001cbeb`
- name: `?SampGetCurrentClientSid@@YAJPEAXPEAPEAXPEAH@Z`
- size: `419`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **, int *)`
- caller_count: `8`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800261c0`
- `0x180078d20`
- `0x180089a6c`
- `0x180089cd0`
- `0x18008db68`
- `0x180090cb0`
- `0x18009c9ac`
- `0x18009d178`

## callees

- `0x180012a28`
- `0x18001ca48`
- `0x18001cfa0`
- `0x180027e24`
- `0x18002d720`
- `0x18008ecd0`
- `0x1800bb788`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18001cacf`
- `ntdll!NtQueryInformationToken` at `0x18001cacf`
- `ntdll!RtlLengthSid` at `0x18001cb63`
- `ntdll!RtlLengthSid` at `0x18001cb63`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001cae8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001cae8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001caa0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cb72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001caa0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cb72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cafa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cbaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cafa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cbaa`
- `RPCRT4!RpcRevertToSelf` at `0x18001cb22`
- `RPCRT4!RpcRevertToSelf` at `0x18001cb22`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x18001cb1a`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtUnImpersonateAnyClient` at `0x18001cb1a`

## pseudocode

```c
__int64 __fastcall SampGetCurrentClientSid(__int64 TokenHandle, void **a2, int *a3)
{
  int v3; // ebx
  __int64 v6; // rbp
  PSID *v7; // rsi
  int v8; // eax
  NTSTATUS v9; // edi
  int v10; // ebx
  int v11; // ebx
  SIZE_T v12; // rbx
  HLOCAL v13; // rax
  ULONG TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF
  int v16; // [rsp+68h] [rbp+10h] BYREF

  v3 = 0;
  *a2 = 0;
  TokenInformationLength = 0;
  v16 = 0;
  v6 = TokenHandle;
  if ( !TokenHandle )
  {
    v7 = 0;
    v8 = SampImpersonateClient(&v16);
    v3 = v16;
    v9 = v8;
    if ( v8 < 0 )
      goto LABEL_10;
    v6 = -5;
  }
  TokenInformationLength = 84;
  v7 = (PSID *)LocalAlloc(0x40u, 0x54u);
  if ( !v7 )
  {
    v9 = -1073741670;
    goto LABEL_10;
  }
  v9 = NtQueryInformationToken((HANDLE)v6, TokenUser, v7, TokenInformationLength, &TokenInformationLength);
  if ( v9 >= 0 )
  {
    if ( CheckTokenMembership((HANDLE)v6, SampAdministratorsAliasSid, a3) )
      goto LABEL_10;
    v9 = -1073741823;
  }
  LocalFree(v7);
  v7 = 0;
LABEL_10:
  v10 = v3 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 == 1 && (int)SampShouldCallNtdsaApiSet() >= 0 )
        NtdsaExtUnImpersonateAnyClient();
    }
    else
    {
      RpcRevertToSelf();
    }
  }
  else
  {
    SamIRevertNullSession();
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 76, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, (unsigned int)v9, v9);
  if ( v9 >= 0 )
  {
    v12 = RtlLengthSid(*v7);
    v13 = LocalAlloc(0x40u, v12);
    *a2 = v13;
    if ( v13 )
    {
      memset_0(v13, 0, v12);
      memcpy_0(*a2, *v7, v12);
    }
    else
    {
      v9 = -1073741670;
    }
  }
  if ( v7 )
    LocalFree(v7);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 73, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, (unsigned int)v9, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001ca48  mov     rax, rsp
0x18001ca4b  mov     [rax+18h], rbx
0x18001ca4f  push    rbp
0x18001ca50  push    rsi
0x18001ca51  push    rdi
0x18001ca52  push    r14
0x18001ca54  push    r15
0x18001ca56  sub     rsp, 30h
0x18001ca5a  xor     ebx, ebx
0x18001ca5c  mov     qword ptr [rdx], 0
0x18001ca63  mov     dword ptr [rax+8], 0
0x18001ca6a  mov     r14, r8
0x18001ca6d  mov     [rax+10h], ebx
0x18001ca70  mov     r15, rdx
0x18001ca73  mov     rbp, rcx
0x18001ca76  test    rcx, rcx
0x18001ca79  jnz     short loc_18001CA94
0x18001ca7b  lea     rcx, [rax+10h]
0x18001ca7f  xor     esi, esi
0x18001ca81  call    SampImpersonateClient
0x18001ca86  mov     ebx, [rsp+58h+arg_8]
0x18001ca8a  mov     edi, eax
0x18001ca8c  test    eax, eax
0x18001ca8e  js      short loc_18001CB02
0x18001ca90  lea     rbp, [rsi-5]
0x18001ca94  mov     edx, 54h ; 'T'; uBytes
0x18001ca99  mov     [rsp+58h+TokenInformationLength], edx
0x18001ca9d  lea     ecx, [rdx-14h]; uFlags
0x18001caa0  call    cs:__imp_LocalAlloc
0x18001caa6  mov     rsi, rax
0x18001caa9  test    rax, rax
0x18001caac  jnz     short loc_18001CAB5
0x18001caae  mov     edi, 0C000009Ah
0x18001cab3  jmp     short loc_18001CB02
0x18001cab5  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18001caba  lea     rax, [rsp+58h+TokenInformationLength]
0x18001cabf  mov     r8, rsi; TokenInformation
0x18001cac2  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18001cac7  mov     edx, 1; TokenInformationClass
0x18001cacc  mov     rcx, rbp; TokenHandle
0x18001cacf  call    cs:__imp_NtQueryInformationToken
0x18001cad5  mov     edi, eax
0x18001cad7  test    eax, eax
0x18001cad9  js      short loc_18001CAF7
0x18001cadb  mov     rdx, cs:SampAdministratorsAliasSid; SidToCheck
0x18001cae2  mov     r8, r14; IsMember
0x18001cae5  mov     rcx, rbp; TokenHandle
0x18001cae8  call    cs:__imp_CheckTokenMembership
0x18001caee  test    eax, eax
0x18001caf0  jnz     short loc_18001CB02
0x18001caf2  mov     edi, 0C0000001h
0x18001caf7  mov     rcx, rsi; hMem
0x18001cafa  call    cs:__imp_LocalFree
0x18001cb00  xor     esi, esi
0x18001cb02  sub     ebx, 1
0x18001cb05  jz      short loc_18001CB2A
0x18001cb07  sub     ebx, 1
0x18001cb0a  jz      short loc_18001CB22
0x18001cb0c  cmp     ebx, 1
0x18001cb0f  jnz     short loc_18001CB2F
0x18001cb11  call    ?SampShouldCallNtdsaApiSet@@YAJXZ; SampShouldCallNtdsaApiSet(void)
0x18001cb16  test    eax, eax
0x18001cb18  js      short loc_18001CB2F
0x18001cb1a  call    cs:__imp_NtdsaExtUnImpersonateAnyClient
0x18001cb20  jmp     short loc_18001CB2F
0x18001cb22  call    cs:__imp_RpcRevertToSelf
0x18001cb28  jmp     short loc_18001CB2F
0x18001cb2a  call    SamIRevertNullSession
0x18001cb2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb36  mov     ebp, 20000h
0x18001cb3b  test    [rcx+44h], ebp
0x18001cb3e  jz      short loc_18001CB5C
0x18001cb40  mov     rcx, [rcx+38h]
0x18001cb44  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18001cb4b  mov     edx, 4Ch ; 'L'
0x18001cb50  mov     dword ptr [rsp+58h+ReturnLength], edi
0x18001cb54  mov     r9d, edi
0x18001cb57  call    WPP_SF_Dd
0x18001cb5c  test    edi, edi
0x18001cb5e  js      short loc_18001CBA2
0x18001cb60  mov     rcx, [rsi]; Sid
0x18001cb63  call    cs:__imp_RtlLengthSid
0x18001cb69  mov     edx, eax; uBytes
0x18001cb6b  mov     ecx, 40h ; '@'; uFlags
0x18001cb70  mov     ebx, eax
0x18001cb72  call    cs:__imp_LocalAlloc
0x18001cb78  mov     [r15], rax
0x18001cb7b  test    rax, rax
0x18001cb7e  jnz     short loc_18001CB87
0x18001cb80  mov     edi, 0C000009Ah
0x18001cb85  jmp     short loc_18001CBA2
0x18001cb87  mov     r8, rbx; Size
0x18001cb8a  xor     edx, edx; Val
0x18001cb8c  mov     rcx, rax; void *
0x18001cb8f  call    memset_0
0x18001cb94  mov     rdx, [rsi]; Src
0x18001cb97  mov     r8, rbx; Size
0x18001cb9a  mov     rcx, [r15]; void *
0x18001cb9d  call    memcpy_0
0x18001cba2  test    rsi, rsi
0x18001cba5  jz      short loc_18001CBB0
0x18001cba7  mov     rcx, rsi; hMem
0x18001cbaa  call    cs:__imp_LocalFree
0x18001cbb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbb7  test    [rcx+44h], ebp
0x18001cbba  jz      short loc_18001CBD8
0x18001cbbc  mov     rcx, [rcx+38h]
0x18001cbc0  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18001cbc7  mov     edx, 49h ; 'I'
0x18001cbcc  mov     dword ptr [rsp+58h+ReturnLength], edi
0x18001cbd0  mov     r9d, edi
0x18001cbd3  call    WPP_SF_Dd
0x18001cbd8  mov     rbx, [rsp+58h+arg_10]
0x18001cbdd  mov     eax, edi
0x18001cbdf  add     rsp, 30h
0x18001cbe3  pop     r15
0x18001cbe5  pop     r14
0x18001cbe7  pop     rdi
0x18001cbe8  pop     rsi
0x18001cbe9  pop     rbp
0x18001cbea  retn
```
