# CWbemParseDN::ParseImpersonationLevel(ushort *,ulong *,WbemImpersonationLevelEnum *)

- ea: `0x180010bbc`
- end: `0x180010c7b`
- name: `?ParseImpersonationLevel@CWbemParseDN@@CA_NPEAGPEAKPEAW4WbemImpersonationLevelEnum@@@Z`
- size: `191`
- prototype: `bool __fastcall(unsigned __int16 *, unsigned int *, enum WbemImpersonationLevelEnum *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fe0c`

## callees

- `0x180010bbc`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180010be5`
- `msvcrt!_wcsnicmp` at `0x180010c09`
- `msvcrt!_wcsnicmp` at `0x180010c2e`
- `msvcrt!_wcsnicmp` at `0x180010c56`
- `msvcrt!_wcsnicmp` at `0x180010be5`
- `msvcrt!_wcsnicmp` at `0x180010c09`
- `msvcrt!_wcsnicmp` at `0x180010c2e`
- `msvcrt!_wcsnicmp` at `0x180010c56`

## string_xrefs

- `0x180010c1d`: `impersonate`

## pseudocode

```c
char __fastcall CWbemParseDN::ParseImpersonationLevel(
        unsigned __int16 *a1,
        unsigned int *a2,
        enum WbemImpersonationLevelEnum *a3)
{
  char v6; // si

  v6 = 1;
  if ( _wcsnicmp(&a1[*a2], L"anonymous", 9u) )
  {
    if ( _wcsnicmp(&a1[*a2], L"identify", 8u) )
    {
      if ( !_wcsnicmp(&a1[*a2], L"impersonate", 0xBu) )
      {
        *a3 = wbemImpersonationLevelImpersonate;
        *a2 += 11;
        return v6;
      }
      if ( _wcsnicmp(&a1[*a2], L"delegate", 8u) )
        return 0;
      *a3 = wbemImpersonationLevelDelegate;
    }
    else
    {
      *a3 = wbemImpersonationLevelIdentify;
    }
    *a2 += 8;
    return v6;
  }
  *a3 = wbemImpersonationLevelAnonymous;
  *a2 += 9;
  return v6;
}

```

## disassembly

```asm
0x180010bbc  push    rbx
0x180010bbe  push    rsi
0x180010bbf  push    rdi
0x180010bc0  push    r14
0x180010bc2  sub     rsp, 28h
0x180010bc6  mov     eax, [rdx]
0x180010bc8  mov     rdi, r8
0x180010bcb  mov     rbx, rdx
0x180010bce  mov     r14, rcx
0x180010bd1  mov     esi, 1
0x180010bd6  lea     rdx, aAnonymous; "anonymous"
0x180010bdd  lea     rcx, [rcx+rax*2]; String1
0x180010be1  lea     r8d, [rsi+8]; MaxCount
0x180010be5  call    cs:__imp__wcsnicmp
0x180010beb  test    eax, eax
0x180010bed  jnz     short loc_180010BF6
0x180010bef  mov     [rdi], esi
0x180010bf1  add     dword ptr [rbx], 9
0x180010bf4  jmp     short loc_180010C6E
0x180010bf6  mov     eax, [rbx]
0x180010bf8  lea     rdx, aIdentify; "identify"
0x180010bff  mov     r8d, 8; MaxCount
0x180010c05  lea     rcx, [r14+rax*2]; String1
0x180010c09  call    cs:__imp__wcsnicmp
0x180010c0f  test    eax, eax
0x180010c11  jnz     short loc_180010C1B
0x180010c13  mov     dword ptr [rdi], 2
0x180010c19  jmp     short loc_180010C66
0x180010c1b  mov     eax, [rbx]
0x180010c1d  lea     rdx, aImpersonate; "impersonate"
0x180010c24  mov     r8d, 0Bh; MaxCount
0x180010c2a  lea     rcx, [r14+rax*2]; String1
0x180010c2e  call    cs:__imp__wcsnicmp
0x180010c34  test    eax, eax
0x180010c36  jnz     short loc_180010C43
0x180010c38  mov     dword ptr [rdi], 3
0x180010c3e  add     dword ptr [rbx], 0Bh
0x180010c41  jmp     short loc_180010C6E
0x180010c43  mov     eax, [rbx]
0x180010c45  lea     rdx, aDelegate; "delegate"
0x180010c4c  mov     r8d, 8; MaxCount
0x180010c52  lea     rcx, [r14+rax*2]; String1
0x180010c56  call    cs:__imp__wcsnicmp
0x180010c5c  test    eax, eax
0x180010c5e  jnz     short loc_180010C6B
0x180010c60  mov     dword ptr [rdi], 4
0x180010c66  add     dword ptr [rbx], 8
0x180010c69  jmp     short loc_180010C6E
0x180010c6b  xor     sil, sil
0x180010c6e  mov     al, sil
0x180010c71  add     rsp, 28h
0x180010c75  pop     r14
0x180010c77  pop     rdi
0x180010c78  pop     rsi
0x180010c79  pop     rbx
0x180010c7a  retn
```
