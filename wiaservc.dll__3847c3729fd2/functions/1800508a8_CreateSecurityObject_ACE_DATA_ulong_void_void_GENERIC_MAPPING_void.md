# CreateSecurityObject(ACE_DATA *,ulong,void *,void *,_GENERIC_MAPPING *,void * *)

- ea: `0x1800508a8`
- end: `0x180050964`
- name: `?CreateSecurityObject@@YAKPEAUACE_DATA@@KPEAX1PEAU_GENERIC_MAPPING@@PEAPEAX@Z`
- size: `188`
- prototype: `unsigned int __fastcall(struct ACE_DATA *, unsigned int, void *, void *, struct _GENERIC_MAPPING *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180050c60`

## callees

- `0x1800504d4`
- `0x1800508a8`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180050956`
- `KERNEL32!LocalFree` at `0x180077873`
- `KERNEL32!LocalFree` at `0x180050956`
- `KERNEL32!LocalFree` at `0x180077873`
- `KERNEL32!GetLastError` at `0x1800508ff`
- `KERNEL32!GetLastError` at `0x1800508ff`
- `KERNEL32!CloseHandle` at `0x180050946`
- `KERNEL32!CloseHandle` at `0x180077863`
- `KERNEL32!CloseHandle` at `0x180050946`
- `KERNEL32!CloseHandle` at `0x180077863`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800508ec`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800508ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800508db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800508db`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurity` at `0x180050930`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurity` at `0x180050930`

## pseudocode

```c
__int64 __fastcall CreateSecurityObject(struct ACE_DATA *a1, unsigned int a2, void *a3, void *a4)
{
  unsigned int LastError; // ebx
  HANDLE CurrentProcess; // rax
  PSECURITY_DESCRIPTOR CreatorDescriptor; // [rsp+50h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+20h] BYREF

  CreatorDescriptor = 0;
  TokenHandle = 0;
  LastError = CreateSecurityDescriptorHelper(a1, a2, a3, a4, &CreatorDescriptor);
  if ( !LastError )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      TokenHandle = (void *)-1LL;
LABEL_4:
      LastError = GetLastError();
      goto LABEL_7;
    }
    if ( !CreatePrivateObjectSecurity(0, CreatorDescriptor, &sdApiObject, 0, TokenHandle, &ApiObjectMapping) )
      goto LABEL_4;
    LastError = 0;
  }
LABEL_7:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( CreatorDescriptor )
    LocalFree(CreatorDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x1800508a8  mov     r11, rsp
0x1800508ab  mov     [r11+20h], r9
0x1800508af  mov     [r11+18h], r8
0x1800508b3  push    rbx
0x1800508b4  sub     rsp, 30h
0x1800508b8  mov     qword ptr [r11+18h], 0
0x1800508c0  mov     qword ptr [r11+20h], 0
0x1800508c8  lea     rax, [r11+18h]
0x1800508cc  mov     [r11-18h], rax
0x1800508d0  call    ?CreateSecurityDescriptorHelper@@YAKPEAUACE_DATA@@KPEAX1PEAPEAX@Z; CreateSecurityDescriptorHelper(ACE_DATA *,ulong,void *,void *,void * *)
0x1800508d5  mov     ebx, eax
0x1800508d7  test    eax, eax
0x1800508d9  jnz     short loc_18005093C
0x1800508db  call    cs:__imp_GetCurrentProcess
0x1800508e1  mov     rcx, rax; ProcessHandle
0x1800508e4  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800508e9  lea     edx, [rbx+8]; DesiredAccess
0x1800508ec  call    cs:__imp_OpenProcessToken
0x1800508f2  test    eax, eax
0x1800508f4  jnz     short loc_180050909
0x1800508f6  mov     [rsp+38h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800508ff  call    cs:__imp_GetLastError
0x180050905  mov     ebx, eax
0x180050907  jmp     short loc_18005093C
0x180050909  lea     rax, ?ApiObjectMapping@@3U_GENERIC_MAPPING@@A; _GENERIC_MAPPING ApiObjectMapping
0x180050910  mov     [rsp+38h+GenericMapping], rax; GenericMapping
0x180050915  mov     rax, [rsp+38h+TokenHandle]
0x18005091a  mov     [rsp+38h+Token], rax; Token
0x18005091f  xor     r9d, r9d; IsDirectoryObject
0x180050922  lea     r8, ?sdApiObject@@3PEAXEA; NewDescriptor
0x180050929  mov     rdx, [rsp+38h+CreatorDescriptor]; CreatorDescriptor
0x18005092e  xor     ecx, ecx; ParentDescriptor
0x180050930  call    cs:__imp_CreatePrivateObjectSecurity
0x180050936  test    eax, eax
0x180050938  jz      short loc_1800508FF
0x18005093a  xor     ebx, ebx
0x18005093c  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180050941  test    rcx, rcx
0x180050944  jz      short loc_18005094C
0x180050946  call    cs:__imp_CloseHandle
0x18005094c  mov     rcx, [rsp+38h+CreatorDescriptor]; hMem
0x180050951  test    rcx, rcx
0x180050954  jz      short loc_18005095C
0x180050956  call    cs:__imp_LocalFree
0x18005095c  mov     eax, ebx
0x18005095e  add     rsp, 30h
0x180050962  pop     rbx
0x180050963  retn
0x180077851  push    rbp
0x180077853  sub     rsp, 30h
0x180077857  mov     rbp, rdx
0x18007785a  mov     rcx, [rbp+58h]; hObject
0x18007785e  test    rcx, rcx
0x180077861  jz      short loc_18007786A
0x180077863  call    cs:__imp_CloseHandle
0x180077869  nop
0x18007786a  mov     rcx, [rbp+50h]; hMem
0x18007786e  test    rcx, rcx
0x180077871  jz      short loc_18007787A
0x180077873  call    cs:__imp_LocalFree
0x180077879  nop
0x18007787a  add     rsp, 30h
0x18007787e  pop     rbp
0x18007787f  retn
```
