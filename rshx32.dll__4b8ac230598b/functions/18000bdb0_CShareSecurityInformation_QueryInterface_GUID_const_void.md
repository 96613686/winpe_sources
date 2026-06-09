# CShareSecurityInformation::QueryInterface(_GUID const &,void * *)

- ea: `0x18000bdb0`
- end: `0x18000bdf8`
- name: `?QueryInterface@CShareSecurityInformation@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `72`
- prototype: `__int64 __fastcall(CShareSecurityInformation *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bdb0`

## pseudocode

```c
__int64 __fastcall CShareSecurityInformation::QueryInterface(
        CShareSecurityInformation *this,
        const struct _GUID *a2,
        void **a3)
{
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISecurityInformation.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_ISecurityInformation.Data4 )
  {
    *a3 = this;
    ++*((_DWORD *)this + 6);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x18000bdb0  mov     rax, [rdx]
0x18000bdb3  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000bdba  jnz     short loc_18000BDC9
0x18000bdbc  mov     rax, [rdx+8]
0x18000bdc0  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000bdc7  jz      short loc_18000BDE2
0x18000bdc9  mov     rax, [rdx]
0x18000bdcc  cmp     rax, qword ptr cs:IID_ISecurityInformation.Data1
0x18000bdd3  jnz     short loc_18000BDEB
0x18000bdd5  mov     rax, [rdx+8]
0x18000bdd9  cmp     rax, qword ptr cs:IID_ISecurityInformation.Data4
0x18000bde0  jnz     short loc_18000BDEB
0x18000bde2  mov     [r8], rcx
0x18000bde5  inc     dword ptr [rcx+18h]
0x18000bde8  xor     eax, eax
0x18000bdea  retn
0x18000bdeb  mov     qword ptr [r8], 0
0x18000bdf2  mov     eax, 80004002h
0x18000bdf7  retn
```
