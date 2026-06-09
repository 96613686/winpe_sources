# SampMakeSid(void *,ulong,void * *)

- ea: `0x1800036b0`
- end: `0x180003751`
- name: `?SampMakeSid@@YAJPEAXKPEAPEAX@Z`
- size: `161`
- prototype: `__int64 __fastcall(PSID SourceSid, unsigned int, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180001a30`

## callees

- `0x1800036b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003714`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003714`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800036df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800036df`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800036c4`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000372e`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800036c4`
- `ntdll!RtlSubAuthorityCountSid` at `0x18000372e`
- `ntdll!RtlLengthRequiredSid` at `0x1800036d0`
- `ntdll!RtlLengthRequiredSid` at `0x1800036d0`
- `ntdll!RtlSubAuthoritySid` at `0x18000373b`
- `ntdll!RtlSubAuthoritySid` at `0x18000373b`
- `ntdll!RtlCopySid` at `0x180003705`
- `ntdll!RtlCopySid` at `0x180003705`

## pseudocode

```c
__int64 __fastcall SampMakeSid(PSID SourceSid, ULONG a2, void **a3)
{
  ULONG v6; // ebp
  ULONG v7; // esi
  HLOCAL v8; // rax
  __int64 result; // rax
  NTSTATUS v10; // eax
  PSID v11; // rcx
  unsigned int v12; // edi
  PUCHAR v13; // rax

  v6 = *RtlSubAuthorityCountSid(SourceSid);
  v7 = RtlLengthRequiredSid(v6 + 1);
  v8 = LocalAlloc(0x40u, v7);
  *a3 = v8;
  if ( !v8 )
    return 3221225495LL;
  v10 = RtlCopySid(v7, v8, SourceSid);
  v11 = *a3;
  v12 = v10;
  if ( v10 >= 0 )
  {
    v13 = RtlSubAuthorityCountSid(v11);
    ++*v13;
    *RtlSubAuthoritySid(*a3, v6) = a2;
    return 0;
  }
  else
  {
    LocalFree(v11);
    result = v12;
    *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800036b0  push    rbx
0x1800036b2  push    rbp
0x1800036b3  push    rsi
0x1800036b4  push    rdi
0x1800036b5  push    r14
0x1800036b7  sub     rsp, 20h
0x1800036bb  mov     rbx, r8
0x1800036be  mov     r14d, edx
0x1800036c1  mov     rdi, rcx
0x1800036c4  call    cs:__imp_RtlSubAuthorityCountSid
0x1800036ca  movzx   ebp, byte ptr [rax]
0x1800036cd  lea     ecx, [rbp+1]; SubAuthorityCount
0x1800036d0  call    cs:__imp_RtlLengthRequiredSid
0x1800036d6  mov     edx, eax; uBytes
0x1800036d8  mov     ecx, 40h ; '@'; uFlags
0x1800036dd  mov     esi, eax
0x1800036df  call    cs:__imp_LocalAlloc
0x1800036e5  mov     [rbx], rax
0x1800036e8  test    rax, rax
0x1800036eb  jnz     short loc_1800036FD
0x1800036ed  mov     eax, 0C0000017h
0x1800036f2  add     rsp, 20h
0x1800036f6  pop     r14
0x1800036f8  pop     rdi
0x1800036f9  pop     rsi
0x1800036fa  pop     rbp
0x1800036fb  pop     rbx
0x1800036fc  retn
0x1800036fd  mov     r8, rdi; SourceSid
0x180003700  mov     rdx, rax; DestinationSid
0x180003703  mov     ecx, esi; DestinationSidLength
0x180003705  call    cs:__imp_RtlCopySid
0x18000370b  mov     rcx, [rbx]; Sid
0x18000370e  mov     edi, eax
0x180003710  test    eax, eax
0x180003712  jns     short loc_18000372E
0x180003714  call    cs:__imp_LocalFree
0x18000371a  mov     eax, edi
0x18000371c  mov     qword ptr [rbx], 0
0x180003723  add     rsp, 20h
0x180003727  pop     r14
0x180003729  pop     rdi
0x18000372a  pop     rsi
0x18000372b  pop     rbp
0x18000372c  pop     rbx
0x18000372d  retn
0x18000372e  call    cs:__imp_RtlSubAuthorityCountSid
0x180003734  mov     edx, ebp; SubAuthority
0x180003736  inc     byte ptr [rax]
0x180003738  mov     rcx, [rbx]; Sid
0x18000373b  call    cs:__imp_RtlSubAuthoritySid
0x180003741  mov     [rax], r14d
0x180003744  xor     eax, eax
0x180003746  add     rsp, 20h
0x18000374a  pop     r14
0x18000374c  pop     rdi
0x18000374d  pop     rsi
0x18000374e  pop     rbp
0x18000374f  pop     rbx
0x180003750  retn
```
