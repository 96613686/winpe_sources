# SampGetCurrentOwnerAndPrimaryGroup

- ea: `0x18008ed40`
- end: `0x18008ee9d`
- name: `SampGetCurrentOwnerAndPrimaryGroup`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000ae10`

## callees

- `0x18001cfa0`
- `0x18001d0d0`
- `0x180027e24`
- `0x18008ed40`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18008edd3`
- `ntdll!NtQueryInformationToken` at `0x18008ee18`
- `ntdll!NtQueryInformationToken` at `0x18008edd3`
- `ntdll!NtQueryInformationToken` at `0x18008ee18`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008eda0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008edec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008eda0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008edec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ee2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ee41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ee2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008ee41`

## pseudocode

```c
__int64 __fastcall SampGetCurrentOwnerAndPrimaryGroup(HLOCAL *a1, HLOCAL *a2)
{
  char v4; // bp
  int v5; // ebx
  HLOCAL v6; // rax
  HLOCAL v7; // rax
  ULONG TokenInformationLength; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v10; // [rsp+58h] [rbp+10h] BYREF

  *a1 = 0;
  TokenInformationLength = 0;
  v10 = 0;
  v4 = 0;
  *a2 = 0;
  v5 = SampImpersonateClient((int *)&v10);
  if ( v5 >= 0 )
  {
    v4 = 1;
    TokenInformationLength = 76;
    v6 = LocalAlloc(0x40u, 0x4Cu);
    *a1 = v6;
    if ( !v6 )
    {
LABEL_3:
      v5 = -1073741670;
      goto LABEL_7;
    }
    v5 = NtQueryInformationToken(
           (HANDLE)0xFFFFFFFFFFFFFFFBLL,
           TokenOwner,
           v6,
           TokenInformationLength,
           &TokenInformationLength);
    if ( v5 >= 0 )
    {
      TokenInformationLength = 76;
      v7 = LocalAlloc(0x40u, 0x4Cu);
      *a2 = v7;
      if ( !v7 )
        goto LABEL_3;
      v5 = NtQueryInformationToken(
             (HANDLE)0xFFFFFFFFFFFFFFFBLL,
             TokenPrimaryGroup,
             v7,
             TokenInformationLength,
             &TokenInformationLength);
      if ( v5 >= 0 )
      {
LABEL_12:
        SampRevertToSelf(v10);
        goto LABEL_13;
      }
    }
  }
LABEL_7:
  if ( *a1 )
  {
    LocalFree(*a1);
    *a1 = 0;
  }
  if ( *a2 )
  {
    LocalFree(*a2);
    *a2 = 0;
  }
  if ( v4 )
    goto LABEL_12;
LABEL_13:
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 74, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, (unsigned int)v5, v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18008ed40  mov     rax, rsp
0x18008ed43  mov     [rax+18h], rbx
0x18008ed47  mov     [rax+20h], rbp
0x18008ed4b  push    rsi
0x18008ed4c  push    rdi
0x18008ed4d  push    r15
0x18008ed4f  sub     rsp, 30h
0x18008ed53  mov     qword ptr [rcx], 0
0x18008ed5a  mov     rdi, rcx
0x18008ed5d  lea     rcx, [rax+10h]
0x18008ed61  mov     dword ptr [rax+8], 0
0x18008ed68  mov     rsi, rdx
0x18008ed6b  mov     dword ptr [rax+10h], 0
0x18008ed72  xor     bpl, bpl
0x18008ed75  mov     qword ptr [rdx], 0
0x18008ed7c  call    SampImpersonateClient
0x18008ed81  mov     ebx, eax
0x18008ed83  test    eax, eax
0x18008ed85  js      loc_18008EE24
0x18008ed8b  mov     r15d, 4Ch ; 'L'
0x18008ed91  mov     bpl, 1
0x18008ed94  mov     edx, r15d; uBytes
0x18008ed97  mov     [rsp+48h+TokenInformationLength], r15d
0x18008ed9c  lea     ecx, [r15-0Ch]; uFlags
0x18008eda0  call    cs:__imp_LocalAlloc
0x18008eda6  mov     [rdi], rax
0x18008eda9  test    rax, rax
0x18008edac  jnz     short loc_18008EDB5
0x18008edae  mov     ebx, 0C000009Ah
0x18008edb3  jmp     short loc_18008EE24
0x18008edb5  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18008edba  lea     r8, [rsp+48h+TokenInformationLength]
0x18008edbf  mov     [rsp+48h+ReturnLength], r8; ReturnLength
0x18008edc4  mov     edx, 4; TokenInformationClass
0x18008edc9  mov     r8, rax; TokenInformation
0x18008edcc  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x18008edd3  call    cs:__imp_NtQueryInformationToken
0x18008edd9  mov     ebx, eax
0x18008eddb  test    eax, eax
0x18008eddd  js      short loc_18008EE24
0x18008eddf  mov     rdx, r15; uBytes
0x18008ede2  mov     [rsp+48h+TokenInformationLength], r15d
0x18008ede7  mov     ecx, 40h ; '@'; uFlags
0x18008edec  call    cs:__imp_LocalAlloc
0x18008edf2  mov     [rsi], rax
0x18008edf5  test    rax, rax
0x18008edf8  jz      short loc_18008EDAE
0x18008edfa  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18008edff  lea     rdx, [rsp+48h+TokenInformationLength]
0x18008ee04  mov     [rsp+48h+ReturnLength], rdx; ReturnLength
0x18008ee09  mov     r8, rax; TokenInformation
0x18008ee0c  mov     edx, 5; TokenInformationClass
0x18008ee11  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x18008ee18  call    cs:__imp_NtQueryInformationToken
0x18008ee1e  mov     ebx, eax
0x18008ee20  test    eax, eax
0x18008ee22  jns     short loc_18008EE53
0x18008ee24  mov     rcx, [rdi]; hMem
0x18008ee27  test    rcx, rcx
0x18008ee2a  jz      short loc_18008EE39
0x18008ee2c  call    cs:__imp_LocalFree
0x18008ee32  mov     qword ptr [rdi], 0
0x18008ee39  mov     rcx, [rsi]; hMem
0x18008ee3c  test    rcx, rcx
0x18008ee3f  jz      short loc_18008EE4E
0x18008ee41  call    cs:__imp_LocalFree
0x18008ee47  mov     qword ptr [rsi], 0
0x18008ee4e  test    bpl, bpl
0x18008ee51  jz      short loc_18008EE5C
0x18008ee53  mov     ecx, [rsp+48h+arg_8]
0x18008ee57  call    SampRevertToSelf
0x18008ee5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ee63  test    dword ptr [rcx+44h], 20000h
0x18008ee6a  jz      short loc_18008EE88
0x18008ee6c  mov     rcx, [rcx+38h]
0x18008ee70  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18008ee77  mov     edx, 4Ah ; 'J'
0x18008ee7c  mov     dword ptr [rsp+48h+ReturnLength], ebx
0x18008ee80  mov     r9d, ebx
0x18008ee83  call    WPP_SF_Dd
0x18008ee88  mov     rbp, [rsp+48h+arg_18]
0x18008ee8d  mov     eax, ebx
0x18008ee8f  mov     rbx, [rsp+48h+arg_10]
0x18008ee94  add     rsp, 30h
0x18008ee98  pop     r15
0x18008ee9a  pop     rdi
0x18008ee9b  pop     rsi
0x18008ee9c  retn
```
