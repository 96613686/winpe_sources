# CTlsClientSession::~CTlsClientSession(void)

- ea: `0x18003eec0`
- end: `0x18003ef83`
- name: `??1CTlsClientSession@@UEAA@XZ`
- size: `195`
- prototype: `void __fastcall(CTlsClientSession *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003ee70`

## callees

- `0x180014240`
- `0x18003eec0`
- `0x18003ef90`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ef69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ef71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ef69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ef71`
- `ntdll!RtlDeleteResource` at `0x18003ef53`
- `ntdll!RtlDeleteResource` at `0x18003ef53`
- `CRYPT32!CryptMemFree` at `0x18003ef04`
- `CRYPT32!CryptMemFree` at `0x18003ef04`

## pseudocode

```c
void __fastcall CTlsClientSession::~CTlsClientSession(CTlsClientSession *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &CTlsClientSession::`vftable';
  v2 = (void *)*((_QWORD *)this + 29);
  if ( v2 )
  {
    if ( LsaTable )
      (*(void (**)(void))(LsaTable + 48))();
    else
      LocalFree(v2);
  }
  v3 = (void *)*((_QWORD *)this + 31);
  if ( v3 )
    CryptMemFree(v3);
  v4 = (void *)*((_QWORD *)this + 36);
  if ( v4 )
    SPExternalFree(v4);
  v5 = (void *)*((_QWORD *)this + 33);
  if ( v5 )
  {
    if ( LsaTable )
      (*(void (**)(void))(LsaTable + 48))();
    else
      LocalFree(v5);
  }
  *(_QWORD *)this = &CTlsSession::`vftable';
  CTlsSession::ClearState(this);
  if ( !*((_DWORD *)this + 18) )
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 80));
  *(_QWORD *)this = &IAllocate::`vftable';
}

```

## disassembly

```asm
0x18003eec0  push    rbx
0x18003eec2  sub     rsp, 20h
0x18003eec6  lea     rax, ??_7CTlsClientSession@@6B@; const CTlsClientSession::`vftable'
0x18003eecd  mov     rbx, rcx
0x18003eed0  mov     [rcx], rax
0x18003eed3  mov     rcx, [rcx+0E8h]; hMem
0x18003eeda  test    rcx, rcx
0x18003eedd  jz      short loc_18003EEF8
0x18003eedf  mov     rax, cs:LsaTable
0x18003eee6  test    rax, rax
0x18003eee9  jz      loc_18003EF71
0x18003eeef  mov     rax, [rax+30h]
0x18003eef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eef8  mov     rcx, [rbx+0F8h]; pv
0x18003eeff  test    rcx, rcx
0x18003ef02  jz      short loc_18003EF0A
0x18003ef04  call    cs:__imp_CryptMemFree
0x18003ef0a  mov     rcx, [rbx+120h]; void *
0x18003ef11  test    rcx, rcx
0x18003ef14  jnz     short loc_18003EF7C
0x18003ef16  mov     rcx, [rbx+108h]; hMem
0x18003ef1d  test    rcx, rcx
0x18003ef20  jz      short loc_18003EF37
0x18003ef22  mov     rax, cs:LsaTable
0x18003ef29  test    rax, rax
0x18003ef2c  jz      short loc_18003EF69
0x18003ef2e  mov     rax, [rax+30h]
0x18003ef32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef37  lea     rax, ??_7CTlsSession@@6B@; const CTlsSession::`vftable'
0x18003ef3e  mov     rcx, rbx; this
0x18003ef41  mov     [rbx], rax
0x18003ef44  call    ?ClearState@CTlsSession@@AEAAXXZ; CTlsSession::ClearState(void)
0x18003ef49  cmp     dword ptr [rbx+48h], 0
0x18003ef4d  jnz     short loc_18003EF59
0x18003ef4f  lea     rcx, [rbx+50h]; Resource
0x18003ef53  call    cs:__imp_RtlDeleteResource
0x18003ef59  lea     rax, ??_7IAllocate@@6B@; const IAllocate::`vftable'
0x18003ef60  mov     [rbx], rax
0x18003ef63  add     rsp, 20h
0x18003ef67  pop     rbx
0x18003ef68  retn
0x18003ef69  call    cs:__imp_LocalFree
0x18003ef6f  jmp     short loc_18003EF37
0x18003ef71  call    cs:__imp_LocalFree
0x18003ef77  jmp     loc_18003EEF8
0x18003ef7c  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18003ef81  jmp     short loc_18003EF16
```
