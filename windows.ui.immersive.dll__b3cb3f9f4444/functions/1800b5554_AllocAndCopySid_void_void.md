# AllocAndCopySid(void *,void * *)

- ea: `0x1800b5554`
- end: `0x1800b55fb`
- name: `?AllocAndCopySid@@YAJPEAXPEAPEAX@Z`
- size: `167`
- prototype: `__int64 __fastcall(PSID pSourceSid, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003c41c`
- `0x1800dc47c`

## callees

- `0x18003d244`
- `0x1800b5554`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b55e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b55e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b559e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b559e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b5584`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800b5584`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b5571`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800b5571`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800b55ba`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800b55ba`

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
0x1800b5554  push    rbx
0x1800b5556  push    rbp
0x1800b5557  push    rsi
0x1800b5558  push    rdi
0x1800b5559  push    r14
0x1800b555b  sub     rsp, 20h
0x1800b555f  mov     r14, rdx
0x1800b5562  mov     qword ptr [rdx], 0
0x1800b5569  mov     rsi, rcx
0x1800b556c  mov     ebx, 80070057h
0x1800b5571  call    cs:__imp_IsValidSid
0x1800b5578  nop     dword ptr [rax+rax+00h]
0x1800b557d  test    eax, eax
0x1800b557f  jz      short loc_1800B55ED
0x1800b5581  mov     rcx, rsi; pSid
0x1800b5584  call    cs:__imp_GetLengthSid
0x1800b558b  nop     dword ptr [rax+rax+00h]
0x1800b5590  mov     edx, eax; uBytes
0x1800b5592  mov     ecx, 40h ; '@'; uFlags
0x1800b5597  mov     ebp, eax
0x1800b5599  mov     ebx, 8007000Eh
0x1800b559e  call    cs:__imp_LocalAlloc
0x1800b55a5  nop     dword ptr [rax+rax+00h]
0x1800b55aa  mov     rdi, rax
0x1800b55ad  test    rax, rax
0x1800b55b0  jz      short loc_1800B55ED
0x1800b55b2  mov     r8, rsi; pSourceSid
0x1800b55b5  mov     rdx, rax; pDestinationSid
0x1800b55b8  mov     ecx, ebp; nDestinationSidLength
0x1800b55ba  call    cs:__imp_CopySid
0x1800b55c1  nop     dword ptr [rax+rax+00h]
0x1800b55c6  test    eax, eax
0x1800b55c8  jz      short loc_1800B55CE
0x1800b55ca  xor     ebx, ebx
0x1800b55cc  jmp     short loc_1800B55D9
0x1800b55ce  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b55d3  mov     ebx, eax
0x1800b55d5  test    eax, eax
0x1800b55d7  js      short loc_1800B55DE
0x1800b55d9  mov     [r14], rdi
0x1800b55dc  jmp     short loc_1800B55ED
0x1800b55de  mov     rcx, rdi; hMem
0x1800b55e1  call    cs:__imp_LocalFree
0x1800b55e8  nop     dword ptr [rax+rax+00h]
0x1800b55ed  mov     eax, ebx
0x1800b55ef  add     rsp, 20h
0x1800b55f3  pop     r14
0x1800b55f5  pop     rdi
0x1800b55f6  pop     rsi
0x1800b55f7  pop     rbp
0x1800b55f8  pop     rbx
0x1800b55f9  retn
```
