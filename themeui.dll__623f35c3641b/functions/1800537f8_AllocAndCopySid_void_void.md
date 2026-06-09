# AllocAndCopySid(void *,void * *)

- ea: `0x1800537f8`
- end: `0x180053880`
- name: `?AllocAndCopySid@@YAJPEAXPEAPEAX@Z`
- size: `136`
- prototype: `__int64 __fastcall(PSID pSourceSid, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e0e8`

## callees

- `0x180030f64`
- `0x1800537f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005386d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005386d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053836`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053836`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180053815`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180053815`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180053822`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180053822`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005384c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005384c`

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
0x1800537f8  push    rbx
0x1800537fa  push    rbp
0x1800537fb  push    rsi
0x1800537fc  push    rdi
0x1800537fd  push    r14
0x1800537ff  sub     rsp, 20h
0x180053803  mov     r14, rdx
0x180053806  mov     qword ptr [rdx], 0
0x18005380d  mov     rsi, rcx
0x180053810  mov     ebx, 80070057h
0x180053815  call    cs:__imp_IsValidSid
0x18005381b  test    eax, eax
0x18005381d  jz      short loc_180053873
0x18005381f  mov     rcx, rsi; pSid
0x180053822  call    cs:__imp_GetLengthSid
0x180053828  mov     edx, eax; uBytes
0x18005382a  mov     ecx, 40h ; '@'; uFlags
0x18005382f  mov     ebp, eax
0x180053831  mov     ebx, 8007000Eh
0x180053836  call    cs:__imp_LocalAlloc
0x18005383c  mov     rdi, rax
0x18005383f  test    rax, rax
0x180053842  jz      short loc_180053873
0x180053844  mov     r8, rsi; pSourceSid
0x180053847  mov     rdx, rax; pDestinationSid
0x18005384a  mov     ecx, ebp; nDestinationSidLength
0x18005384c  call    cs:__imp_CopySid
0x180053852  test    eax, eax
0x180053854  jz      short loc_18005385A
0x180053856  xor     ebx, ebx
0x180053858  jmp     short loc_180053865
0x18005385a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005385f  mov     ebx, eax
0x180053861  test    eax, eax
0x180053863  js      short loc_18005386A
0x180053865  mov     [r14], rdi
0x180053868  jmp     short loc_180053873
0x18005386a  mov     rcx, rdi; hMem
0x18005386d  call    cs:__imp_LocalFree
0x180053873  mov     eax, ebx
0x180053875  add     rsp, 20h
0x180053879  pop     r14
0x18005387b  pop     rdi
0x18005387c  pop     rsi
0x18005387d  pop     rbp
0x18005387e  pop     rbx
0x18005387f  retn
```
