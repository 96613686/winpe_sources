# SecpCreateBinding(ushort *)

- ea: `0x18000edb4`
- end: `0x18000ee26`
- name: `?SecpCreateBinding@@YAPEAU_SECP_DLL_BINDING@@PEAG@Z`
- size: `114`
- prototype: `struct _SECP_DLL_BINDING *__fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800070d0`
- `0x18001caa0`

## callees

- `0x18000edb4`
- `0x18000ee2c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000edca`
- `ntdll!RtlInitUnicodeString` at `0x18000edca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ee15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ee15`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000edd7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000edd7`

## pseudocode

```c
struct _UNICODE_STRING *__fastcall SecpCreateBinding(PCWSTR SourceString)
{
  struct _UNICODE_STRING *v1; // rax
  struct _UNICODE_STRING *v2; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v1 = (struct _UNICODE_STRING *)LocalAlloc(0, 0x38u);
  v2 = v1;
  if ( v1 )
  {
    *v1 = 0;
    v1[1] = 0;
    v1[2] = 0;
    *(_QWORD *)&v1[3].Length = 0;
    *(_DWORD *)&v1[2].Length = 1;
    if ( !(unsigned int)SecpDuplicateString(v1 + 1, &DestinationString) )
    {
      LocalFree(v2);
      return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000edb4  push    rbx
0x18000edb6  sub     rsp, 30h
0x18000edba  xorps   xmm0, xmm0
0x18000edbd  mov     rdx, rcx; SourceString
0x18000edc0  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x18000edc5  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x18000edca  call    cs:__imp_RtlInitUnicodeString
0x18000edd0  mov     edx, 38h ; '8'; uBytes
0x18000edd5  xor     ecx, ecx; uFlags
0x18000edd7  call    cs:__imp_LocalAlloc
0x18000eddd  mov     rbx, rax
0x18000ede0  test    rax, rax
0x18000ede3  jz      short loc_18000EE1D
0x18000ede5  xorps   xmm0, xmm0
0x18000ede8  lea     rcx, [rbx+10h]; struct _UNICODE_STRING *
0x18000edec  movups  xmmword ptr [rbx], xmm0
0x18000edef  xor     eax, eax
0x18000edf1  lea     rdx, [rsp+38h+DestinationString]; struct _UNICODE_STRING *
0x18000edf6  movups  xmmword ptr [rbx+10h], xmm0
0x18000edfa  movups  xmmword ptr [rbx+20h], xmm0
0x18000edfe  mov     [rbx+30h], rax
0x18000ee02  mov     dword ptr [rbx+20h], 1
0x18000ee09  call    ?SecpDuplicateString@@YAHPEAU_UNICODE_STRING@@0@Z; SecpDuplicateString(_UNICODE_STRING *,_UNICODE_STRING *)
0x18000ee0e  test    eax, eax
0x18000ee10  jnz     short loc_18000EE1D
0x18000ee12  mov     rcx, rbx; hMem
0x18000ee15  call    cs:__imp_LocalFree
0x18000ee1b  xor     ebx, ebx
0x18000ee1d  mov     rax, rbx
0x18000ee20  add     rsp, 30h
0x18000ee24  pop     rbx
0x18000ee25  retn
```
