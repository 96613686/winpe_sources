# ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)

- ea: `0x140002b40`
- end: `0x140002c3d`
- name: `?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z`
- size: `253`
- prototype: `char __fastcall(ATL::CDacl *this, const struct ATL::CSid *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400022d0`

## callees

- `0x140002b40`
- `0x140002e30`
- `0x140003060`
- `0x1400072bc`
- `0x140007f24`
- `0x14000c010`

## import_xrefs

- `msvcrt!free` at `0x140002bd5`
- `msvcrt!free` at `0x140002bd5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140002b62`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140002b62`

## pseudocode

```c
char __fastcall ATL::CDacl::AddAllowedAce(ATL::CDacl *this, const struct ATL::CSid *a2)
{
  ATL::CDacl *v3; // rdi
  ATL::CDacl::CAccessAce *v5; // rax
  ATL::CDacl::CAccessAce *v6; // rbx
  unsigned __int64 v7; // r14
  ATL::CDacl::CAccessAce *v9; // [rsp+68h] [rbp+10h]

  v3 = this;
  if ( !*((_BYTE *)a2 + 76) || !IsValidSid((char *)a2 + 8) )
    return 0;
  if ( *((_BYTE *)v3 + 16) )
  {
    (*(void (__fastcall **)(ATL::CDacl *))(*(_QWORD *)v3 + 16LL))(v3);
    *((_BYTE *)v3 + 16) = 0;
  }
  try
  {
    v5 = (ATL::CDacl::CAccessAce *)operator new(0x98u);
    if ( v5 )
      v6 = ATL::CDacl::CAccessAce::CAccessAce(v5, a2);
    else
      v6 = 0;
    v9 = v6;
  }
  catch ( ... )
  {
    v3 = this;
    v6 = v9;
  }
  if ( !v6
    || (v7 = *((_QWORD *)v3 + 4), v7 >= *((_QWORD *)v3 + 5))
    && !(unsigned __int8)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(
                           (char *)v3 + 24,
                           v7 + 1) )
  {
    ATL::PrivateAtlThrow(-2147024882);
  }
  *(_QWORD *)(*((_QWORD *)v3 + 3) + 8 * v7) = v6;
  ++*((_QWORD *)v3 + 4);
  free(*((void **)v3 + 1));
  *((_QWORD *)v3 + 1) = 0;
  return 1;
}

```

## disassembly

```asm
0x140002b40  mov     [rsp+arg_10], rbx
0x140002b45  mov     [rsp+arg_0], rcx
0x140002b4a  push    rsi
0x140002b4b  push    rdi
0x140002b4c  push    r14
0x140002b4e  sub     rsp, 40h
0x140002b52  mov     rbx, rdx
0x140002b55  mov     rdi, rcx
0x140002b58  cmp     byte ptr [rdx+4Ch], 0
0x140002b5c  jz      short loc_140002B6C
0x140002b5e  lea     rcx, [rdx+8]; pSid
0x140002b62  call    cs:__imp_IsValidSid
0x140002b68  test    eax, eax
0x140002b6a  jnz     short loc_140002B7C
0x140002b6c  xor     al, al
0x140002b6e  mov     rbx, [rsp+58h+arg_10]
0x140002b73  add     rsp, 40h
0x140002b77  pop     r14
0x140002b79  pop     rdi
0x140002b7a  pop     rsi
0x140002b7b  retn
0x140002b7c  cmp     byte ptr [rdi+10h], 0
0x140002b80  jnz     loc_140002C15
0x140002b86  mov     [rsp+58h+arg_8], 0
0x140002b8f  mov     ecx, 98h; Size
0x140002b94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002b99  mov     [rsp+58h+var_28], rax
0x140002b9e  test    rax, rax
0x140002ba1  jz      short loc_140002BF3
0x140002ba3  mov     rdx, rbx; struct ATL::CSid *
0x140002ba6  mov     rcx, rax; this
0x140002ba9  call    ??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z; ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)
0x140002bae  mov     rbx, rax
0x140002bb1  mov     [rsp+58h+arg_8], rbx
0x140002bb6  test    rbx, rbx
0x140002bb9  jz      short loc_140002BF7
0x140002bbb  mov     r14, [rdi+20h]
0x140002bbf  cmp     r14, [rdi+28h]
0x140002bc3  jnb     short loc_140002C02
0x140002bc5  mov     rax, [rdi+18h]
0x140002bc9  mov     [rax+r14*8], rbx
0x140002bcd  inc     qword ptr [rdi+20h]
0x140002bd1  mov     rcx, [rdi+8]; Block
0x140002bd5  call    cs:__imp_free
0x140002bdb  mov     qword ptr [rdi+8], 0
0x140002be3  mov     al, 1
0x140002be5  mov     rbx, [rsp+58h+arg_10]
0x140002bea  add     rsp, 40h
0x140002bee  pop     r14
0x140002bf0  pop     rdi
0x140002bf1  pop     rsi
0x140002bf2  retn
0x140002bf3  xor     ebx, ebx
0x140002bf5  jmp     short loc_140002BB1
0x140002bf7  mov     ecx, 8007000Eh; int
0x140002bfc  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x140002c02  lea     rdx, [r14+1]
0x140002c06  lea     rcx, [rdi+18h]
0x140002c0a  call    ?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::GrowBuffer(unsigned __int64)
0x140002c0f  test    al, al
0x140002c11  jnz     short loc_140002BC5
0x140002c13  jmp     short loc_140002BF7
0x140002c15  mov     rax, [rdi]
0x140002c18  mov     rcx, rdi
0x140002c1b  mov     rax, [rax+10h]
0x140002c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c24  mov     byte ptr [rdi+10h], 0
0x140002c28  jmp     loc_140002B86
0x140002c2d  mov     rdi, [rsp+58h+arg_0]
0x140002c32  mov     rbx, [rsp+58h+arg_8]
0x140002c37  jmp     loc_140002BB6
```
