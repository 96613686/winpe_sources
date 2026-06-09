# CAANapConnection::Terminate(void)

- ea: `0x18000403c`
- end: `0x1800040db`
- name: `?Terminate@CAANapConnection@@QEAAJXZ`
- size: `159`
- prototype: `__int64 __fastcall(CAANapConnection *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180004cc0`
- `0x180005220`

## callees

- `0x180003b60`
- `0x18000403c`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800040cd`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800040cd`
- `ole32!CoTaskMemFree` at `0x18000408b`
- `ole32!CoTaskMemFree` at `0x180004095`
- `ole32!CoTaskMemFree` at `0x18000408b`
- `ole32!CoTaskMemFree` at `0x180004095`
- `CRYPT32!CertFreeCertificateChain` at `0x1800040c4`
- `CRYPT32!CertFreeCertificateChain` at `0x1800040c4`

## pseudocode

```c
__int64 __fastcall CAANapConnection::Terminate(CAANapConnection *this)
{
  __int64 v2; // rax
  void *v3; // rcx
  const CERT_CHAIN_CONTEXT *v4; // rcx

  if ( !*((_DWORD *)this + 6) )
  {
    *((_DWORD *)this + 6) = 1;
    CAANapEnforcementClientCallback::RemoveConnection(this, this);
    if ( *(_QWORD *)this )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
      *(_QWORD *)this = 0;
    }
    v2 = *((_QWORD *)this + 1);
    if ( v2 )
    {
      v3 = *(void **)(v2 + 8);
      if ( v3 )
        CoTaskMemFree(v3);
      CoTaskMemFree(*((LPVOID *)this + 1));
      *((_QWORD *)this + 1) = 0;
    }
    v4 = (const CERT_CHAIN_CONTEXT *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 5) = 0;
    if ( v4 )
      CertFreeCertificateChain(v4);
    operator delete(this);
  }
  return 0;
}

```

## disassembly

```asm
0x18000403c  push    rbx
0x18000403e  sub     rsp, 20h
0x180004042  cmp     dword ptr [rcx+18h], 0
0x180004046  mov     rbx, rcx
0x180004049  jnz     loc_1800040D3
0x18000404f  mov     rdx, rcx; struct CAANapConnection *
0x180004052  mov     dword ptr [rcx+18h], 1
0x180004059  call    ?RemoveConnection@CAANapEnforcementClientCallback@@QEAAJPEAVCAANapConnection@@@Z; CAANapEnforcementClientCallback::RemoveConnection(CAANapConnection *)
0x18000405e  mov     rcx, [rbx]
0x180004061  test    rcx, rcx
0x180004064  jz      short loc_180004079
0x180004066  mov     rax, [rcx]
0x180004069  mov     rax, [rax+10h]
0x18000406d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004072  mov     qword ptr [rbx], 0
0x180004079  mov     rax, [rbx+8]
0x18000407d  test    rax, rax
0x180004080  jz      short loc_1800040A3
0x180004082  mov     rcx, [rax+8]; pv
0x180004086  test    rcx, rcx
0x180004089  jz      short loc_180004091
0x18000408b  call    cs:__imp_CoTaskMemFree
0x180004091  mov     rcx, [rbx+8]; pv
0x180004095  call    cs:__imp_CoTaskMemFree
0x18000409b  mov     qword ptr [rbx+8], 0
0x1800040a3  mov     rcx, [rbx+38h]; pChainContext
0x1800040a7  mov     qword ptr [rbx+20h], 0
0x1800040af  mov     qword ptr [rbx+30h], 0
0x1800040b7  mov     qword ptr [rbx+28h], 0
0x1800040bf  test    rcx, rcx
0x1800040c2  jz      short loc_1800040CA
0x1800040c4  call    cs:__imp_CertFreeCertificateChain
0x1800040ca  mov     rcx, rbx
0x1800040cd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800040d3  xor     eax, eax
0x1800040d5  add     rsp, 20h
0x1800040d9  pop     rbx
0x1800040da  retn
```
