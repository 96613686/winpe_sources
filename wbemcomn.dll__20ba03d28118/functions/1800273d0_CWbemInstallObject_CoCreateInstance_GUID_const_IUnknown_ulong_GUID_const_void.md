# CWbemInstallObject::CoCreateInstance(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x1800273d0`
- end: `0x18002746e`
- name: `?CoCreateInstance@CWbemInstallObject@@SAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z`
- size: `158`
- prototype: `__int64 __fastcall(const struct _GUID *, struct IUnknown *, unsigned int, const struct _GUID *, void **ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800273d0`
- `0x18002adc0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800273f8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800273f8`

## pseudocode

```c
__int64 __fastcall CWbemInstallObject::CoCreateInstance(
        const struct _GUID *a1,
        struct IUnknown *a2,
        unsigned int a3,
        const struct _GUID *a4,
        void **ppv)
{
  int ClassObject; // edi
  LPVOID v8; // rbx
  LPVOID v9[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( CWbemInstallObject::m_bOffline )
  {
    v9[0] = 0;
    ClassObject = CWbemInstallObject::CoGetClassObject(a1, a3, 0, a4, v9);
    if ( ClassObject >= 0 )
    {
      v8 = v9[0];
      v9[1] = v9[0];
      ClassObject = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const struct _GUID *, void **))(*(_QWORD *)v9[0] + 24LL))(
                      v9[0],
                      0,
                      a4,
                      ppv);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  else
  {
    return (unsigned int)CoCreateInstance(a1, a2, a3, a4, ppv);
  }
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x1800273d0  mov     [rsp+arg_0], rbx
0x1800273d5  mov     [rsp+arg_8], rsi
0x1800273da  push    rdi
0x1800273db  sub     rsp, 40h
0x1800273df  mov     rsi, r9
0x1800273e2  mov     r10d, r8d
0x1800273e5  cmp     cs:?m_bOffline@CWbemInstallObject@@0_NA, 0; bool CWbemInstallObject::m_bOffline
0x1800273ec  jnz     short loc_180027412
0x1800273ee  mov     rax, [rsp+48h+arg_20]
0x1800273f3  mov     [rsp+48h+ppv], rax; ppv
0x1800273f8  call    cs:__imp_CoCreateInstance
0x1800273fe  mov     edi, eax
0x180027400  mov     eax, edi
0x180027402  mov     rbx, [rsp+48h+arg_0]
0x180027407  mov     rsi, [rsp+48h+arg_8]
0x18002740c  add     rsp, 40h
0x180027410  pop     rdi
0x180027411  retn
0x180027412  mov     [rsp+48h+var_18], 0
0x18002741b  lea     rax, [rsp+48h+var_18]
0x180027420  mov     [rsp+48h+ppv], rax; LPVOID *
0x180027425  xor     r8d, r8d; struct _COSERVERINFO *
0x180027428  mov     edx, r10d; unsigned int
0x18002742b  call    ?CoGetClassObject@CWbemInstallObject@@SAJAEBU_GUID@@KPEAU_COSERVERINFO@@0PEAPEAX@Z; CWbemInstallObject::CoGetClassObject(_GUID const &,ulong,_COSERVERINFO *,_GUID const &,void * *)
0x180027430  mov     edi, eax
0x180027432  test    eax, eax
0x180027434  js      short loc_180027400
0x180027436  mov     rbx, [rsp+48h+var_18]
0x18002743b  mov     [rsp+48h+var_10], rbx
0x180027440  mov     rcx, [rsp+48h+var_18]
0x180027445  mov     rax, [rcx]
0x180027448  mov     r9, [rsp+48h+arg_20]
0x18002744d  mov     r8, rsi
0x180027450  xor     edx, edx
0x180027452  mov     rax, [rax+18h]
0x180027456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002745b  mov     edi, eax
0x18002745d  mov     rax, [rbx]
0x180027460  mov     rcx, rbx
0x180027463  mov     rax, [rax+10h]
0x180027467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002746c  jmp     short loc_180027400
```
