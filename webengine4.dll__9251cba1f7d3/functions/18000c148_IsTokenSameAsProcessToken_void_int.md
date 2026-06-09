# IsTokenSameAsProcessToken(void *,int *)

- ea: `0x18000c148`
- end: `0x18000c203`
- name: `?IsTokenSameAsProcessToken@@YAJPEAXPEAH@Z`
- size: `187`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000bdb0`

## callees

- `0x18000c030`
- `0x18000c148`
- `0x18004d350`
- `0x18004d754`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000c1ec`
- `KERNEL32!CloseHandle` at `0x18000c1ec`
- `KERNEL32!GetCurrentProcess` at `0x18000c189`
- `KERNEL32!GetCurrentProcess` at `0x18000c189`
- `ADVAPI32!OpenProcessToken` at `0x18000c19b`
- `ADVAPI32!OpenProcessToken` at `0x18000c19b`
- `ADVAPI32!EqualSid` at `0x18000c1c9`
- `ADVAPI32!EqualSid` at `0x18000c1c9`

## pseudocode

```c
__int64 __fastcall IsTokenSameAsProcessToken(void *a1, int *a2)
{
  unsigned int SidFromToken; // ebx
  HANDLE CurrentProcess; // rax
  PSID pSid2; // [rsp+40h] [rbp+20h] BYREF
  PSID pSid1; // [rsp+50h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+38h] BYREF

  if ( !a1 || !a2 )
    return 2147942487LL;
  *a2 = 0;
  pSid2 = 0;
  pSid1 = 0;
  TokenHandle = 0;
  SidFromToken = CProcessEntry::GetSidFromToken(a1, &pSid2);
  if ( !SidFromToken )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
      SidFromToken = CProcessEntry::GetSidFromToken(TokenHandle, &pSid1);
      if ( !SidFromToken )
        *a2 = EqualSid(pSid1, pSid2);
    }
    else
    {
      SidFromToken = GetLastWin32Error();
    }
  }
  MemFree(pSid2);
  MemFree(pSid1);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return SidFromToken;
}

```

## disassembly

```asm
0x18000c148  push    rbp
0x18000c14a  push    rbx
0x18000c14b  push    rdi
0x18000c14c  mov     rbp, rsp
0x18000c14f  sub     rsp, 20h
0x18000c153  mov     rdi, rdx
0x18000c156  test    rcx, rcx
0x18000c159  jz      loc_18000C1F6
0x18000c15f  test    rdx, rdx
0x18000c162  jz      loc_18000C1F6
0x18000c168  and     dword ptr [rdx], 0
0x18000c16b  lea     rdx, [rbp+pSid2]; void **
0x18000c16f  and     [rbp+pSid2], 0
0x18000c174  and     [rbp+pSid1], 0
0x18000c179  and     [rbp+TokenHandle], 0
0x18000c17e  call    ?GetSidFromToken@CProcessEntry@@CAJPEAXPEAPEAX@Z; CProcessEntry::GetSidFromToken(void *,void * *)
0x18000c183  mov     ebx, eax
0x18000c185  test    eax, eax
0x18000c187  jnz     short loc_18000C1D1
0x18000c189  call    cs:__imp_GetCurrentProcess
0x18000c18f  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000c193  mov     edx, 20008h; DesiredAccess
0x18000c198  mov     rcx, rax; ProcessHandle
0x18000c19b  call    cs:__imp_OpenProcessToken
0x18000c1a1  test    eax, eax
0x18000c1a3  jnz     short loc_18000C1AE
0x18000c1a5  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18000c1aa  mov     ebx, eax
0x18000c1ac  jmp     short loc_18000C1D1
0x18000c1ae  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000c1b2  lea     rdx, [rbp+pSid1]; void **
0x18000c1b6  call    ?GetSidFromToken@CProcessEntry@@CAJPEAXPEAPEAX@Z; CProcessEntry::GetSidFromToken(void *,void * *)
0x18000c1bb  mov     ebx, eax
0x18000c1bd  test    eax, eax
0x18000c1bf  jnz     short loc_18000C1D1
0x18000c1c1  mov     rdx, [rbp+pSid2]; pSid2
0x18000c1c5  mov     rcx, [rbp+pSid1]; pSid1
0x18000c1c9  call    cs:__imp_EqualSid
0x18000c1cf  mov     [rdi], eax
0x18000c1d1  mov     rcx, [rbp+pSid2]; lpMem
0x18000c1d5  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18000c1da  mov     rcx, [rbp+pSid1]; lpMem
0x18000c1de  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18000c1e3  mov     rcx, [rbp+TokenHandle]; hObject
0x18000c1e7  test    rcx, rcx
0x18000c1ea  jz      short loc_18000C1F2
0x18000c1ec  call    cs:__imp_CloseHandle
0x18000c1f2  mov     eax, ebx
0x18000c1f4  jmp     short loc_18000C1FB
0x18000c1f6  mov     eax, 80070057h
0x18000c1fb  add     rsp, 20h
0x18000c1ff  pop     rdi
0x18000c200  pop     rbx
0x18000c201  pop     rbp
0x18000c202  retn
```
