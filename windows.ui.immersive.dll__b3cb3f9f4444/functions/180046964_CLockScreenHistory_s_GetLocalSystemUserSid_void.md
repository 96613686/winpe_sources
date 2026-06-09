# CLockScreenHistory::s_GetLocalSystemUserSid(void * *)

- ea: `0x180046964`
- end: `0x180046a27`
- name: `?s_GetLocalSystemUserSid@CLockScreenHistory@@SAJPEAPEAX@Z`
- size: `195`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000c600`

## callees

- `0x18003d244`
- `0x180046964`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046a08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046a08`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800469b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800469b9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180046991`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800469e1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180046991`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800469e1`

## pseudocode

```c
__int64 __fastcall CLockScreenHistory::s_GetLocalSystemUserSid(void **a1)
{
  int Error; // ebx
  HLOCAL v3; // rax
  void *v4; // rdi
  SIZE_T uBytes; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  LODWORD(uBytes) = 0;
  if ( CreateWellKnownSid(WinLocalSystemSid, 0, 0, (DWORD *)&uBytes) )
  {
    return 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error == -2147024774 )
    {
      v3 = LocalAlloc(0, (unsigned int)uBytes);
      v4 = v3;
      if ( v3 )
      {
        if ( CreateWellKnownSid(WinLocalSystemSid, 0, v3, (DWORD *)&uBytes) )
        {
          Error = 0;
        }
        else
        {
          Error = ResultFromKnownLastError();
          if ( Error < 0 )
          {
            LocalFree(v4);
            return (unsigned int)Error;
          }
        }
        *a1 = v4;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180046964  mov     rax, rsp
0x180046967  mov     [rax+10h], rbx
0x18004696b  mov     [rax+18h], rsi
0x18004696f  push    rdi
0x180046970  sub     rsp, 20h
0x180046974  xor     edx, edx; DomainSid
0x180046976  mov     qword ptr [rcx], 0
0x18004697d  mov     rsi, rcx
0x180046980  mov     dword ptr [rax+8], 0
0x180046987  lea     r9, [rax+8]; cbSid
0x18004698b  xor     r8d, r8d; pSid
0x18004698e  lea     ecx, [rdx+16h]; WellKnownSidType
0x180046991  call    cs:__imp_CreateWellKnownSid
0x180046998  nop     dword ptr [rax+rax+00h]
0x18004699d  test    eax, eax
0x18004699f  jz      short loc_1800469A5
0x1800469a1  xor     ebx, ebx
0x1800469a3  jmp     short loc_180046A14
0x1800469a5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800469aa  mov     ebx, eax
0x1800469ac  cmp     eax, 8007007Ah
0x1800469b1  jnz     short loc_180046A14
0x1800469b3  mov     edx, dword ptr [rsp+28h+uBytes]; uBytes
0x1800469b7  xor     ecx, ecx; uFlags
0x1800469b9  call    cs:__imp_LocalAlloc
0x1800469c0  nop     dword ptr [rax+rax+00h]
0x1800469c5  mov     rdi, rax
0x1800469c8  test    rax, rax
0x1800469cb  jnz     short loc_1800469D4
0x1800469cd  mov     ebx, 8007000Eh
0x1800469d2  jmp     short loc_180046A14
0x1800469d4  xor     edx, edx; DomainSid
0x1800469d6  lea     r9, [rsp+28h+uBytes]; cbSid
0x1800469db  mov     r8, rdi; pSid
0x1800469de  lea     ecx, [rdx+16h]; WellKnownSidType
0x1800469e1  call    cs:__imp_CreateWellKnownSid
0x1800469e8  nop     dword ptr [rax+rax+00h]
0x1800469ed  test    eax, eax
0x1800469ef  jz      short loc_1800469F5
0x1800469f1  xor     ebx, ebx
0x1800469f3  jmp     short loc_180046A00
0x1800469f5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800469fa  mov     ebx, eax
0x1800469fc  test    eax, eax
0x1800469fe  js      short loc_180046A05
0x180046a00  mov     [rsi], rdi
0x180046a03  jmp     short loc_180046A14
0x180046a05  mov     rcx, rdi; hMem
0x180046a08  call    cs:__imp_LocalFree
0x180046a0f  nop     dword ptr [rax+rax+00h]
0x180046a14  mov     rsi, [rsp+28h+arg_10]
0x180046a19  mov     eax, ebx
0x180046a1b  mov     rbx, [rsp+28h+arg_8]
0x180046a20  add     rsp, 20h
0x180046a24  pop     rdi
0x180046a25  retn
```
