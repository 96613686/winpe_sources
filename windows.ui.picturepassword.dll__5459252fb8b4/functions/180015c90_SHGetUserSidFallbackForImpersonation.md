# SHGetUserSidFallbackForImpersonation

- ea: `0x180015c90`
- end: `0x180015d50`
- name: `SHGetUserSidFallbackForImpersonation`
- size: `192`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006d54`

## callees

- `0x1800063c0`
- `0x1800092b8`
- `0x1800159d4`
- `0x180015c90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015d2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015d2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015d35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015d35`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180015d0b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180015d0b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015cd8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180015cd8`

## pseudocode

```c
__int64 __fastcall SHGetUserSidFallbackForImpersonation(void *a1, _QWORD *a2)
{
  int Error; // ebx
  PSID *v4; // rsi
  DWORD LengthSid; // eax
  DWORD v6; // ebp
  void *v7; // rcx
  PSID v8; // rdi
  PSID pDestinationSid; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  pDestinationSid = 0;
  Error = SHQueryToken<_TOKEN_USER>(a1, (DWORD)a2, 1, &pDestinationSid);
  if ( Error >= 0 )
  {
    v4 = (PSID *)pDestinationSid;
    LengthSid = GetLengthSid(*(PSID *)pDestinationSid);
    pDestinationSid = 0;
    v6 = LengthSid;
    Error = CTCoAllocPolicy::Alloc(v7, 1, LengthSid, &pDestinationSid);
    if ( Error < 0 )
    {
LABEL_8:
      LocalFree(v4);
      return (unsigned int)Error;
    }
    v8 = pDestinationSid;
    if ( CopySid(v6, pDestinationSid, *v4) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_7:
        CoTaskMemFree(v8);
        goto LABEL_8;
      }
    }
    *a2 = v8;
    v8 = 0;
    goto LABEL_7;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180015c90  mov     rax, rsp
0x180015c93  mov     [rax+10h], rbx
0x180015c97  mov     [rax+18h], rbp
0x180015c9b  mov     [rax+8], rcx
0x180015c9f  push    rsi
0x180015ca0  push    rdi
0x180015ca1  push    r14
0x180015ca3  sub     rsp, 20h
0x180015ca7  mov     edi, 1
0x180015cac  mov     qword ptr [rdx], 0
0x180015cb3  mov     r8d, edi
0x180015cb6  mov     qword ptr [rax+8], 0
0x180015cbe  lea     r9, [rax+8]
0x180015cc2  mov     r14, rdx
0x180015cc5  call    ??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z; SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)
0x180015cca  mov     ebx, eax
0x180015ccc  test    eax, eax
0x180015cce  js      short loc_180015D3B
0x180015cd0  mov     rsi, [rsp+38h+pDestinationSid]
0x180015cd5  mov     rcx, [rsi]; pSid
0x180015cd8  call    cs:__imp_GetLengthSid
0x180015cde  lea     r9, [rsp+38h+pDestinationSid]; void **
0x180015ce3  mov     [rsp+38h+pDestinationSid], 0
0x180015cec  mov     r8d, eax; unsigned __int64
0x180015cef  mov     edx, edi; unsigned int
0x180015cf1  mov     ebp, eax
0x180015cf3  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180015cf8  mov     ebx, eax
0x180015cfa  test    eax, eax
0x180015cfc  js      short loc_180015D32
0x180015cfe  mov     rdi, [rsp+38h+pDestinationSid]
0x180015d03  mov     ecx, ebp; nDestinationSidLength
0x180015d05  mov     r8, [rsi]; pSourceSid
0x180015d08  mov     rdx, rdi; pDestinationSid
0x180015d0b  call    cs:__imp_CopySid
0x180015d11  test    eax, eax
0x180015d13  jz      short loc_180015D19
0x180015d15  xor     ebx, ebx
0x180015d17  jmp     short loc_180015D24
0x180015d19  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180015d1e  mov     ebx, eax
0x180015d20  test    eax, eax
0x180015d22  js      short loc_180015D29
0x180015d24  mov     [r14], rdi
0x180015d27  xor     edi, edi
0x180015d29  mov     rcx, rdi; pv
0x180015d2c  call    cs:__imp_CoTaskMemFree
0x180015d32  mov     rcx, rsi; hMem
0x180015d35  call    cs:__imp_LocalFree
0x180015d3b  mov     rbp, [rsp+38h+arg_10]
0x180015d40  mov     eax, ebx
0x180015d42  mov     rbx, [rsp+38h+arg_8]
0x180015d47  add     rsp, 20h
0x180015d4b  pop     r14
0x180015d4d  pop     rdi
0x180015d4e  pop     rsi
0x180015d4f  retn
```
