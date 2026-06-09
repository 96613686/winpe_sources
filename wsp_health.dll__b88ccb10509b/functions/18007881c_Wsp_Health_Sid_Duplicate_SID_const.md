# Wsp::Health::Sid::Duplicate(_SID const *)

- ea: `0x18007881c`
- end: `0x1800788c2`
- name: `?Duplicate@Sid@Health@Wsp@@QEAA_NPEBU_SID@@@Z`
- size: `166`
- prototype: `bool(Wsp::Health::Sid *__hidden this, const struct _SID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800791b8`

## callees

- `0x180078664`
- `0x1800786c8`
- `0x18007881c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180078848`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180078848`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18007883b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18007888a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18007883b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18007888a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007886f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007886f`

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
0x18007881c  push    rbx
0x18007881e  push    rsi
0x18007881f  push    rdi
0x180078820  push    r14
0x180078822  sub     rsp, 28h
0x180078826  mov     rax, [rcx]
0x180078829  mov     rsi, rdx
0x18007882c  mov     r14, rcx
0x18007882f  mov     rax, [rax+8]
0x180078833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078838  mov     rcx, rsi; pSid
0x18007883b  call    cs:__imp_IsValidSid
0x180078841  test    eax, eax
0x180078843  jz      short loc_1800788B6
0x180078845  mov     rcx, rsi; pSid
0x180078848  call    cs:__imp_GetLengthSid
0x18007884e  mov     edi, eax
0x180078850  test    al, al
0x180078852  jz      short loc_1800788B6
0x180078854  movzx   ecx, dil; uBytes
0x180078858  call    ?Alloc@LocalHeap@Health@Wsp@@SAPEAX_KK@Z; Wsp::Health::LocalHeap::Alloc(unsigned __int64,ulong)
0x18007885d  movzx   ecx, dil; nDestinationSidLength
0x180078861  mov     r8, rsi; pSourceSid
0x180078864  mov     rdx, rax; pDestinationSid
0x180078867  mov     [rsp+48h+arg_0], rax
0x18007886c  mov     rbx, rax
0x18007886f  call    cs:__imp_CopySid
0x180078875  test    eax, eax
0x180078877  jz      short loc_1800788AC
0x180078879  mov     [rsp+48h+arg_0], 0
0x180078882  test    rbx, rbx
0x180078885  jz      short loc_180078898
0x180078887  mov     rcx, rbx; pSid
0x18007888a  call    cs:__imp_IsValidSid
0x180078890  test    eax, eax
0x180078892  jnz     short loc_180078898
0x180078894  xor     bl, bl
0x180078896  jmp     short loc_18007889E
0x180078898  mov     [r14+8], rbx
0x18007889c  mov     bl, 1
0x18007889e  lea     rcx, [rsp+48h+arg_0]
0x1800788a3  call    ?Clear@?$LocalHeapPtr@X@Health@Wsp@@QEAAXXZ; Wsp::Health::LocalHeapPtr<void>::Clear(void)
0x1800788a8  mov     al, bl
0x1800788aa  jmp     short loc_1800788B8
0x1800788ac  lea     rcx, [rsp+48h+arg_0]
0x1800788b1  call    ?Clear@?$LocalHeapPtr@X@Health@Wsp@@QEAAXXZ; Wsp::Health::LocalHeapPtr<void>::Clear(void)
0x1800788b6  xor     al, al
0x1800788b8  add     rsp, 28h
0x1800788bc  pop     r14
0x1800788be  pop     rdi
0x1800788bf  pop     rsi
0x1800788c0  pop     rbx
0x1800788c1  retn
```
