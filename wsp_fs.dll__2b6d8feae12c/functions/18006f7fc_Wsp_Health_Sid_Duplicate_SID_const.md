# Wsp::Health::Sid::Duplicate(_SID const *)

- ea: `0x18006f7fc`
- end: `0x18006f8a2`
- name: `?Duplicate@Sid@Health@Wsp@@QEAA_NPEBU_SID@@@Z`
- size: `166`
- prototype: `bool(Wsp::Health::Sid *__hidden this, const struct _SID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006fe74`

## callees

- `0x18006f650`
- `0x18006f6b4`
- `0x18006f7fc`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006f828`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18006f828`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18006f81b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18006f86a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18006f81b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18006f86a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006f84f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18006f84f`

## pseudocode

```c
char __fastcall Wsp::Health::Sid::Duplicate(Wsp::Health::Sid *this, struct _SID *a2)
{
  unsigned __int8 LengthSid; // al
  unsigned int v5; // edx
  unsigned __int8 v6; // di
  PSID v7; // rbx
  char v8; // bl
  PSID v10; // [rsp+50h] [rbp+8h] BYREF

  (*(void (__fastcall **)(Wsp::Health::Sid *))(*(_QWORD *)this + 8LL))(this);
  if ( !IsValidSid(a2) )
    return 0;
  LengthSid = GetLengthSid(a2);
  v6 = LengthSid;
  if ( !LengthSid )
    return 0;
  v10 = Wsp::Health::LocalHeap::Alloc(LengthSid, v5);
  v7 = v10;
  if ( !CopySid(v6, v10, a2) )
  {
    Wsp::Health::LocalHeapPtr<void>::Clear(&v10);
    return 0;
  }
  v10 = 0;
  if ( !v7 || IsValidSid(v7) )
  {
    *((_QWORD *)this + 1) = v7;
    v8 = 1;
  }
  else
  {
    v8 = 0;
  }
  Wsp::Health::LocalHeapPtr<void>::Clear(&v10);
  return v8;
}

```

## disassembly

```asm
0x18006f7fc  push    rbx
0x18006f7fe  push    rsi
0x18006f7ff  push    rdi
0x18006f800  push    r14
0x18006f802  sub     rsp, 28h
0x18006f806  mov     rax, [rcx]
0x18006f809  mov     rsi, rdx
0x18006f80c  mov     r14, rcx
0x18006f80f  mov     rax, [rax+8]
0x18006f813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f818  mov     rcx, rsi; pSid
0x18006f81b  call    cs:__imp_IsValidSid
0x18006f821  test    eax, eax
0x18006f823  jz      short loc_18006F896
0x18006f825  mov     rcx, rsi; pSid
0x18006f828  call    cs:__imp_GetLengthSid
0x18006f82e  mov     edi, eax
0x18006f830  test    al, al
0x18006f832  jz      short loc_18006F896
0x18006f834  movzx   ecx, dil; uBytes
0x18006f838  call    ?Alloc@LocalHeap@Health@Wsp@@SAPEAX_KK@Z; Wsp::Health::LocalHeap::Alloc(unsigned __int64,ulong)
0x18006f83d  movzx   ecx, dil; nDestinationSidLength
0x18006f841  mov     r8, rsi; pSourceSid
0x18006f844  mov     rdx, rax; pDestinationSid
0x18006f847  mov     [rsp+48h+arg_0], rax
0x18006f84c  mov     rbx, rax
0x18006f84f  call    cs:__imp_CopySid
0x18006f855  test    eax, eax
0x18006f857  jz      short loc_18006F88C
0x18006f859  mov     [rsp+48h+arg_0], 0
0x18006f862  test    rbx, rbx
0x18006f865  jz      short loc_18006F878
0x18006f867  mov     rcx, rbx; pSid
0x18006f86a  call    cs:__imp_IsValidSid
0x18006f870  test    eax, eax
0x18006f872  jnz     short loc_18006F878
0x18006f874  xor     bl, bl
0x18006f876  jmp     short loc_18006F87E
0x18006f878  mov     [r14+8], rbx
0x18006f87c  mov     bl, 1
0x18006f87e  lea     rcx, [rsp+48h+arg_0]
0x18006f883  call    ?Clear@?$LocalHeapPtr@X@Health@Wsp@@QEAAXXZ; Wsp::Health::LocalHeapPtr<void>::Clear(void)
0x18006f888  mov     al, bl
0x18006f88a  jmp     short loc_18006F898
0x18006f88c  lea     rcx, [rsp+48h+arg_0]
0x18006f891  call    ?Clear@?$LocalHeapPtr@X@Health@Wsp@@QEAAXXZ; Wsp::Health::LocalHeapPtr<void>::Clear(void)
0x18006f896  xor     al, al
0x18006f898  add     rsp, 28h
0x18006f89c  pop     r14
0x18006f89e  pop     rdi
0x18006f89f  pop     rsi
0x18006f8a0  pop     rbx
0x18006f8a1  retn
```
