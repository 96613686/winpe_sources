# AllocAndCopySid(void *,void * *)

- ea: `0x18033ae8c`
- end: `0x18033af14`
- name: `?AllocAndCopySid@@YAJPEAXPEAPEAX@Z`
- size: `136`
- prototype: `__int64 __fastcall(PSID pSourceSid, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b0dc8`

## callees

- `0x18033ae8c`
- `0x18033b018`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18033aea9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18033aea9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18033aeb6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18033aeb6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18033aee0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18033aee0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18033af01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18033af01`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18033aeca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18033aeca`

## pseudocode

```c
__int64 __fastcall AllocAndCopySid(PSID pSourceSid, void **a2)
{
  int Error; // ebx
  DWORD LengthSid; // ebp
  HLOCAL v6; // rax
  void *v7; // rdi

  *a2 = 0;
  Error = -2147024809;
  if ( IsValidSid(pSourceSid) )
  {
    LengthSid = GetLengthSid(pSourceSid);
    Error = -2147024882;
    v6 = LocalAlloc(0x40u, LengthSid);
    v7 = v6;
    if ( v6 )
    {
      if ( CopySid(LengthSid, v6, pSourceSid) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
          LocalFree(v7);
          return (unsigned int)Error;
        }
      }
      *a2 = v7;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18033ae8c  push    rbx
0x18033ae8e  push    rbp
0x18033ae8f  push    rsi
0x18033ae90  push    rdi
0x18033ae91  push    r14
0x18033ae93  sub     rsp, 20h
0x18033ae97  mov     r14, rdx
0x18033ae9a  mov     qword ptr [rdx], 0
0x18033aea1  mov     rsi, rcx
0x18033aea4  mov     ebx, 80070057h
0x18033aea9  call    cs:__imp_IsValidSid
0x18033aeaf  test    eax, eax
0x18033aeb1  jz      short loc_18033AF07
0x18033aeb3  mov     rcx, rsi; pSid
0x18033aeb6  call    cs:__imp_GetLengthSid
0x18033aebc  mov     edx, eax; uBytes
0x18033aebe  mov     ecx, 40h ; '@'; uFlags
0x18033aec3  mov     ebp, eax
0x18033aec5  mov     ebx, 8007000Eh
0x18033aeca  call    cs:__imp_LocalAlloc
0x18033aed0  mov     rdi, rax
0x18033aed3  test    rax, rax
0x18033aed6  jz      short loc_18033AF07
0x18033aed8  mov     r8, rsi; pSourceSid
0x18033aedb  mov     rdx, rax; pDestinationSid
0x18033aede  mov     ecx, ebp; nDestinationSidLength
0x18033aee0  call    cs:__imp_CopySid
0x18033aee6  test    eax, eax
0x18033aee8  jz      short loc_18033AEEE
0x18033aeea  xor     ebx, ebx
0x18033aeec  jmp     short loc_18033AEF9
0x18033aeee  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18033aef3  mov     ebx, eax
0x18033aef5  test    eax, eax
0x18033aef7  js      short loc_18033AEFE
0x18033aef9  mov     [r14], rdi
0x18033aefc  jmp     short loc_18033AF07
0x18033aefe  mov     rcx, rdi; hMem
0x18033af01  call    cs:__imp_LocalFree
0x18033af07  mov     eax, ebx
0x18033af09  add     rsp, 20h
0x18033af0d  pop     r14
0x18033af0f  pop     rdi
0x18033af10  pop     rsi
0x18033af11  pop     rbp
0x18033af12  pop     rbx
0x18033af13  retn
```
