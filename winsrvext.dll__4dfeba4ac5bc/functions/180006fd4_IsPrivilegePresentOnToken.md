# IsPrivilegePresentOnToken

- ea: `0x180006fd4`
- end: `0x1800070a6`
- name: `IsPrivilegePresentOnToken`
- size: `210`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180008a7c`

## callees

- `0x180006fd4`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180007021`
- `KERNELBASE!LocalAlloc` at `0x180007021`
- `ntdll!NtQueryInformationToken` at `0x180007007`
- `ntdll!NtQueryInformationToken` at `0x18000704d`
- `ntdll!NtQueryInformationToken` at `0x180007007`
- `ntdll!NtQueryInformationToken` at `0x18000704d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000708a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000708a`

## pseudocode

```c
__int64 __fastcall IsPrivilegePresentOnToken(HANDLE TokenHandle, __int64 a2)
{
  unsigned int v2; // ebx
  unsigned int v3; // esi
  _DWORD *v5; // rdi
  __int64 v6; // rcx
  unsigned int v8; // [rsp+5Ch] [rbp+14h]
  SIZE_T uBytes; // [rsp+60h] [rbp+18h] BYREF

  v8 = HIDWORD(a2);
  LODWORD(uBytes) = 0;
  v2 = a2;
  v3 = 0;
  if ( NtQueryInformationToken(TokenHandle, TokenPrivileges, 0, 0, (PULONG)&uBytes) == -1073741789 )
  {
    v5 = LocalAlloc(0x40u, (unsigned int)uBytes);
    if ( v5 )
    {
      if ( NtQueryInformationToken(TokenHandle, TokenPrivileges, v5, uBytes, (PULONG)&uBytes) >= 0 )
      {
        v6 = 0;
        if ( *v5 )
        {
          while ( *(_QWORD *)&v5[3 * v6 + 1] != __PAIR64__(v8, v2) )
          {
            v6 = (unsigned int)(v6 + 1);
            if ( (unsigned int)v6 >= *v5 )
              goto LABEL_8;
          }
          v3 = 1;
        }
      }
LABEL_8:
      LocalFree(v5);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180006fd4  mov     rax, rsp
0x180006fd7  mov     [rax+8], rbx
0x180006fdb  mov     [rax+10h], rdx
0x180006fdf  push    rbp
0x180006fe0  push    rsi
0x180006fe1  push    rdi
0x180006fe2  sub     rsp, 30h
0x180006fe6  mov     dword ptr [rax+18h], 0
0x180006fed  lea     rax, [rax+18h]
0x180006ff1  mov     rbx, rdx
0x180006ff4  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180006ff9  xor     esi, esi
0x180006ffb  xor     r9d, r9d; TokenInformationLength
0x180006ffe  xor     r8d, r8d; TokenInformation
0x180007001  mov     rbp, rcx
0x180007004  lea     edx, [rsi+3]; TokenInformationClass
0x180007007  call    cs:__imp_NtQueryInformationToken
0x18000700e  nop     dword ptr [rax+rax+00h]
0x180007013  cmp     eax, 0C0000023h
0x180007018  jnz     short loc_180007096
0x18000701a  mov     edx, dword ptr [rsp+48h+uBytes]; uBytes
0x18000701e  lea     ecx, [rsi+40h]; uFlags
0x180007021  call    cs:__imp_LocalAlloc
0x180007028  nop     dword ptr [rax+rax+00h]
0x18000702d  mov     rdi, rax
0x180007030  test    rax, rax
0x180007033  jz      short loc_180007096
0x180007035  mov     r9d, dword ptr [rsp+48h+uBytes]; TokenInformationLength
0x18000703a  lea     rax, [rsp+48h+uBytes]
0x18000703f  mov     r8, rdi; TokenInformation
0x180007042  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180007047  lea     edx, [rsi+3]; TokenInformationClass
0x18000704a  mov     rcx, rbp; TokenHandle
0x18000704d  call    cs:__imp_NtQueryInformationToken
0x180007054  nop     dword ptr [rax+rax+00h]
0x180007059  test    eax, eax
0x18000705b  js      short loc_180007087
0x18000705d  xor     ecx, ecx
0x18000705f  cmp     [rdi], ecx
0x180007061  jbe     short loc_180007087
0x180007063  lea     rax, [rcx+rcx*2]
0x180007067  mov     rax, [rdi+rax*4+4]
0x18000706c  cmp     eax, ebx
0x18000706e  jnz     short loc_18000707A
0x180007070  shr     rax, 20h
0x180007074  cmp     eax, [rsp+48h+arg_C]
0x180007078  jz      short loc_180007082
0x18000707a  inc     ecx
0x18000707c  cmp     ecx, [rdi]
0x18000707e  jb      short loc_180007063
0x180007080  jmp     short loc_180007087
0x180007082  mov     esi, 1
0x180007087  mov     rcx, rdi; hMem
0x18000708a  call    cs:__imp_LocalFree
0x180007091  nop     dword ptr [rax+rax+00h]
0x180007096  mov     rbx, [rsp+48h+arg_0]
0x18000709b  mov     eax, esi
0x18000709d  add     rsp, 30h
0x1800070a1  pop     rdi
0x1800070a2  pop     rsi
0x1800070a3  pop     rbp
0x1800070a4  retn
```
