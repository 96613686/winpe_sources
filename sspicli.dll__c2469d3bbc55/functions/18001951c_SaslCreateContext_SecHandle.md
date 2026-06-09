# SaslCreateContext(_SecHandle *)

- ea: `0x18001951c`
- end: `0x1800195be`
- name: `?SaslCreateContext@@YAPEAU_SASL_CONTEXT@@PEAU_SecHandle@@@Z`
- size: `162`
- prototype: `struct _SASL_CONTEXT *__fastcall(struct _SecHandle *)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800199c0`
- `0x180019eb0`
- `0x18001a060`

## callees

- `0x18001951c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800195aa`
- `ntdll!RtlLeaveCriticalSection` at `0x1800195aa`
- `ntdll!RtlEnterCriticalSection` at `0x180019570`
- `ntdll!RtlEnterCriticalSection` at `0x180019570`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019531`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019531`

## pseudocode

```c
struct _SASL_CONTEXT *__fastcall SaslCreateContext(struct _SecHandle *a1)
{
  _DWORD *v2; // rax
  _DWORD *v3; // rbx
  __int128 v4; // xmm0
  struct _SASL_CONTEXT *v5; // rax

  v2 = LocalAlloc(0x40u, 0x50u);
  v3 = v2;
  if ( v2 )
  {
    v4 = (__int128)*a1;
    v2[15] = SaslGlobalRecvSize;
    v2[14] = SaslGlobalSendSize;
    v2[11] = SaslGlobalAuthZID;
    *((_OWORD *)v2 + 1) = v4;
    v2[10] = 0;
    RtlEnterCriticalSection(&SaslLock);
    v5 = SaslContextList;
    if ( *((struct _SASL_CONTEXT ***)SaslContextList + 1) != &SaslContextList )
      __fastfail(3u);
    *((_QWORD *)v3 + 1) = &SaslContextList;
    *(_QWORD *)v3 = v5;
    *((_QWORD *)v5 + 1) = v3;
    SaslContextList = (struct _SASL_CONTEXT *)v3;
    RtlLeaveCriticalSection(&SaslLock);
  }
  return (struct _SASL_CONTEXT *)v3;
}

```

## disassembly

```asm
0x18001951c  mov     [rsp+arg_0], rbx
0x180019521  push    rdi
0x180019522  sub     rsp, 20h
0x180019526  mov     edx, 50h ; 'P'; uBytes
0x18001952b  mov     rdi, rcx
0x18001952e  lea     ecx, [rdx-10h]; uFlags
0x180019531  call    cs:__imp_LocalAlloc
0x180019537  mov     rbx, rax
0x18001953a  test    rax, rax
0x18001953d  jz      short loc_1800195B0
0x18001953f  movups  xmm0, xmmword ptr [rdi]
0x180019542  mov     ecx, cs:?SaslGlobalRecvSize@@3KA; ulong SaslGlobalRecvSize
0x180019548  mov     [rax+3Ch], ecx
0x18001954b  mov     ecx, cs:?SaslGlobalSendSize@@3KA; ulong SaslGlobalSendSize
0x180019551  mov     [rax+38h], ecx
0x180019554  mov     ecx, cs:?SaslGlobalAuthZID@@3W4_SASL_AUTHZID_STATE@@A; _SASL_AUTHZID_STATE SaslGlobalAuthZID
0x18001955a  mov     [rax+2Ch], ecx
0x18001955d  lea     rcx, SaslLock; CriticalSection
0x180019564  movdqu  xmmword ptr [rax+10h], xmm0
0x180019569  mov     dword ptr [rax+28h], 0
0x180019570  call    cs:__imp_RtlEnterCriticalSection
0x180019576  mov     rax, cs:SaslContextList
0x18001957d  lea     rcx, SaslContextList
0x180019584  cmp     [rax+8], rcx
0x180019588  jz      short loc_180019591
0x18001958a  mov     ecx, 3
0x18001958f  int     29h; Win8: RtlFailFast(ecx)
0x180019591  mov     [rbx+8], rcx
0x180019595  lea     rcx, SaslLock; CriticalSection
0x18001959c  mov     [rbx], rax
0x18001959f  mov     [rax+8], rbx
0x1800195a3  mov     cs:SaslContextList, rbx
0x1800195aa  call    cs:__imp_RtlLeaveCriticalSection
0x1800195b0  mov     rax, rbx
0x1800195b3  mov     rbx, [rsp+28h+arg_0]
0x1800195b8  add     rsp, 20h
0x1800195bc  pop     rdi
0x1800195bd  retn
```
