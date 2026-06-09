# Wsp::Health::Sid::Duplicate(_SID const *)

- ea: `0x180071150`
- end: `0x180071201`
- name: `?Duplicate@Sid@Health@Wsp@@QEAA_NPEBU_SID@@@Z`
- size: `177`
- prototype: `bool(Wsp::Health::Sid *__hidden this, const struct _SID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180071830`

## callees

- `0x180019198`
- `0x180070f80`
- `0x180070ff8`
- `0x180071150`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007117b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007117b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800711a8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800711a8`

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
0x180071150  push    rbx
0x180071152  push    rsi
0x180071153  push    rdi
0x180071154  push    r14
0x180071156  sub     rsp, 28h
0x18007115a  mov     rax, [rcx]
0x18007115d  mov     rsi, rdx
0x180071160  mov     r14, rcx
0x180071163  mov     rax, [rax+8]
0x180071167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007116c  mov     rcx, rsi; struct _SID *
0x18007116f  call    ?IsValidSid@Sid@Health@Wsp@@SA_NPEBU_SID@@@Z; Wsp::Health::Sid::IsValidSid(_SID const *)
0x180071174  test    al, al
0x180071176  jz      short loc_1800711F4
0x180071178  mov     rcx, rsi; pSid
0x18007117b  call    cs:__imp_GetLengthSid
0x180071182  nop     dword ptr [rax+rax+00h]
0x180071187  mov     edi, eax
0x180071189  test    al, al
0x18007118b  jz      short loc_1800711F4
0x18007118d  movzx   ecx, dil; uBytes
0x180071191  call    ?Alloc@LocalHeap@Health@Wsp@@SAPEAX_KK@Z; Wsp::Health::LocalHeap::Alloc(unsigned __int64,ulong)
0x180071196  movzx   ecx, dil; nDestinationSidLength
0x18007119a  mov     r8, rsi; pSourceSid
0x18007119d  mov     rdx, rax; pDestinationSid
0x1800711a0  mov     [rsp+48h+arg_0], rax
0x1800711a5  mov     rbx, rax
0x1800711a8  call    cs:__imp_CopySid
0x1800711af  nop     dword ptr [rax+rax+00h]
0x1800711b4  test    eax, eax
0x1800711b6  jz      short loc_1800711EA
0x1800711b8  mov     [rsp+48h+arg_0], 0
0x1800711c1  test    rbx, rbx
0x1800711c4  jz      short loc_1800711D6
0x1800711c6  mov     rcx, rbx; struct _SID *
0x1800711c9  call    ?IsValidSid@Sid@Health@Wsp@@SA_NPEBU_SID@@@Z; Wsp::Health::Sid::IsValidSid(_SID const *)
0x1800711ce  test    al, al
0x1800711d0  jnz     short loc_1800711D6
0x1800711d2  xor     bl, bl
0x1800711d4  jmp     short loc_1800711DC
0x1800711d6  mov     [r14+8], rbx
0x1800711da  mov     bl, 1
0x1800711dc  lea     rcx, [rsp+48h+arg_0]
0x1800711e1  call    ?Clear@?$LocalHeapPtr@X@Health@Wsp@@QEAAXXZ; Wsp::Health::LocalHeapPtr<void>::Clear(void)
0x1800711e6  mov     al, bl
0x1800711e8  jmp     short loc_1800711F6
0x1800711ea  lea     rcx, [rsp+48h+arg_0]
0x1800711ef  call    ?Clear@?$LocalHeapPtr@X@Health@Wsp@@QEAAXXZ; Wsp::Health::LocalHeapPtr<void>::Clear(void)
0x1800711f4  xor     al, al
0x1800711f6  add     rsp, 28h
0x1800711fa  pop     r14
0x1800711fc  pop     rdi
0x1800711fd  pop     rsi
0x1800711fe  pop     rbx
0x1800711ff  retn
```
