# Wsp::Health::Sid::Duplicate(_SID const *)

- ea: `0x18007a770`
- end: `0x18007a821`
- name: `?Duplicate@Sid@Health@Wsp@@QEAA_NPEBU_SID@@@Z`
- size: `177`
- prototype: `bool(Wsp::Health::Sid *__hidden this, const struct _SID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007b1a8`

## callees

- `0x180016318`
- `0x18007a5a8`
- `0x18007a620`
- `0x18007a770`
- `0x18008e010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007a79b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007a79b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007a7c8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007a7c8`

## pseudocode

```c
char __fastcall Wsp::Health::Sid::Duplicate(Wsp::Health::Sid *this, struct _SID *a2)
{
  unsigned __int8 LengthSid; // al
  unsigned int v5; // edx
  unsigned __int8 v6; // di
  const struct _SID *v7; // rbx
  char v8; // bl
  struct _SID *v10; // [rsp+50h] [rbp+8h] BYREF

  (*(void (__fastcall **)(Wsp::Health::Sid *))(*(_QWORD *)this + 8LL))(this);
  if ( !Wsp::Health::Sid::IsValidSid(a2) )
    return 0;
  LengthSid = GetLengthSid(a2);
  v6 = LengthSid;
  if ( !LengthSid )
    return 0;
  v10 = (struct _SID *)Wsp::Health::LocalHeap::Alloc(LengthSid, v5);
  v7 = v10;
  if ( !CopySid(v6, v10, a2) )
  {
    Wsp::Health::LocalHeapPtr<void>::Clear(&v10);
    return 0;
  }
  v10 = 0;
  if ( !v7 || Wsp::Health::Sid::IsValidSid(v7) )
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
0x18007a770  push    rbx
0x18007a772  push    rsi
0x18007a773  push    rdi
0x18007a774  push    r14
0x18007a776  sub     rsp, 28h
0x18007a77a  mov     rax, [rcx]
0x18007a77d  mov     rsi, rdx
0x18007a780  mov     r14, rcx
0x18007a783  mov     rax, [rax+8]
0x18007a787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a78c  mov     rcx, rsi; struct _SID *
0x18007a78f  call    ?IsValidSid@Sid@Health@Wsp@@SA_NPEBU_SID@@@Z; Wsp::Health::Sid::IsValidSid(_SID const *)
0x18007a794  test    al, al
0x18007a796  jz      short loc_18007A814
0x18007a798  mov     rcx, rsi; pSid
0x18007a79b  call    cs:__imp_GetLengthSid
0x18007a7a2  nop     dword ptr [rax+rax+00h]
0x18007a7a7  mov     edi, eax
0x18007a7a9  test    al, al
0x18007a7ab  jz      short loc_18007A814
0x18007a7ad  movzx   ecx, dil; uBytes
0x18007a7b1  call    ?Alloc@LocalHeap@Health@Wsp@@SAPEAX_KK@Z; Wsp::Health::LocalHeap::Alloc(unsigned __int64,ulong)
0x18007a7b6  movzx   ecx, dil; nDestinationSidLength
0x18007a7ba  mov     r8, rsi; pSourceSid
0x18007a7bd  mov     rdx, rax; pDestinationSid
0x18007a7c0  mov     [rsp+48h+arg_0], rax
0x18007a7c5  mov     rbx, rax
0x18007a7c8  call    cs:__imp_CopySid
0x18007a7cf  nop     dword ptr [rax+rax+00h]
0x18007a7d4  test    eax, eax
0x18007a7d6  jz      short loc_18007A80A
0x18007a7d8  mov     [rsp+48h+arg_0], 0
0x18007a7e1  test    rbx, rbx
0x18007a7e4  jz      short loc_18007A7F6
0x18007a7e6  mov     rcx, rbx; struct _SID *
0x18007a7e9  call    ?IsValidSid@Sid@Health@Wsp@@SA_NPEBU_SID@@@Z; Wsp::Health::Sid::IsValidSid(_SID const *)
0x18007a7ee  test    al, al
0x18007a7f0  jnz     short loc_18007A7F6
0x18007a7f2  xor     bl, bl
0x18007a7f4  jmp     short loc_18007A7FC
0x18007a7f6  mov     [r14+8], rbx
0x18007a7fa  mov     bl, 1
0x18007a7fc  lea     rcx, [rsp+48h+arg_0]
0x18007a801  call    ?Clear@?$LocalHeapPtr@X@Health@Wsp@@QEAAXXZ; Wsp::Health::LocalHeapPtr<void>::Clear(void)
0x18007a806  mov     al, bl
0x18007a808  jmp     short loc_18007A816
0x18007a80a  lea     rcx, [rsp+48h+arg_0]
0x18007a80f  call    ?Clear@?$LocalHeapPtr@X@Health@Wsp@@QEAAXXZ; Wsp::Health::LocalHeapPtr<void>::Clear(void)
0x18007a814  xor     al, al
0x18007a816  add     rsp, 28h
0x18007a81a  pop     r14
0x18007a81c  pop     rdi
0x18007a81d  pop     rsi
0x18007a81e  pop     rbx
0x18007a81f  retn
```
