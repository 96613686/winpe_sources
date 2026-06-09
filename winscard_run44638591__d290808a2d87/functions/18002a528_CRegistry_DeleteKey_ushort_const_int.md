# CRegistry::DeleteKey(ushort const *,int)

- ea: `0x18002a528`
- end: `0x18002a5f9`
- name: `?DeleteKey@CRegistry@@QEBAXPEBGH@Z`
- size: `209`
- prototype: `void __fastcall(CRegistry *__hidden this, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001b448`
- `0x18002a528`
- `0x18002acb0`

## callees

- `0x180002180`
- `0x180002220`
- `0x180014440`
- `0x180015ac0`
- `0x18002a528`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002a5b2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002a5b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRegistry::DeleteKey(CRegistry *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v5; // rax
  LSTATUS v6; // eax
  ulong v7; // [rsp+38h] [rbp-50h] BYREF
  LSTATUS pExceptionObject; // [rsp+3Ch] [rbp-4Ch] BYREF
  ulong v9; // [rsp+40h] [rbp-48h] BYREF
  ulong v10; // [rsp+44h] [rbp-44h] BYREF
  _DWORD phkResult[16]; // [rsp+48h] [rbp-40h] BYREF

  if ( *((_DWORD *)this + 10) )
  {
    v9 = *((_DWORD *)this + 10);
    throw &v9;
  }
  try
  {
    CRegistry::CRegistry(phkResult, *(HKEY *)this, a2, 0x2000Eu, 0xFFFFFFE0);
    if ( !(unsigned int)CRegistry::Status((CRegistry *)phkResult, 1) )
    {
      while ( 1 )
      {
        v5 = CRegistry::Subkey((CRegistry *)phkResult, 0);
        if ( !v5 )
          break;
        CRegistry::DeleteKey((CRegistry *)phkResult, v5, 0);
      }
    }
    CRegistry::~CRegistry((CRegistry *)phkResult);
    v6 = RegDeleteKeyExW(*(HKEY *)this, a2, 0, 0);
  }
  catch ( ulong v10 )
  {
    v7 = v10;
    throw &v7;
  }
  if ( v6 )
  {
    pExceptionObject = v6;
    throw (ulong *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x18002a528  mov     [rsp+arg_10], rbx
0x18002a52d  push    rdi
0x18002a52e  sub     rsp, 80h
0x18002a535  mov     rdi, rdx
0x18002a538  mov     rbx, rcx
0x18002a53b  mov     eax, [rcx+28h]
0x18002a53e  test    eax, eax
0x18002a540  jnz     loc_18002A5D2
0x18002a546  mov     [rsp+88h+dwOptions], 0FFFFFFE0h; dwOptions
0x18002a54e  mov     r9d, 2000Eh; samDesired
0x18002a554  mov     r8, rdx; lpSubKey
0x18002a557  mov     rdx, [rcx]; hKey
0x18002a55a  lea     rcx, [rsp+88h+phkResult]; phkResult
0x18002a55f  call    ??0CRegistry@@QEAA@PEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::CRegistry(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x18002a564  nop
0x18002a565  mov     edx, 1; int
0x18002a56a  lea     rcx, [rsp+88h+phkResult]; this
0x18002a56f  call    ?Status@CRegistry@@QEBAJH@Z; CRegistry::Status(int)
0x18002a574  test    eax, eax
0x18002a576  jnz     short loc_18002A59B
0x18002a578  xor     edx, edx; unsigned int
0x18002a57a  lea     rcx, [rsp+88h+phkResult]; this
0x18002a57f  call    ?Subkey@CRegistry@@QEAAPEBGK@Z; CRegistry::Subkey(ulong)
0x18002a584  test    rax, rax
0x18002a587  jz      short loc_18002A59B
0x18002a589  xor     r8d, r8d; int
0x18002a58c  mov     rdx, rax; unsigned __int16 *
0x18002a58f  lea     rcx, [rsp+88h+phkResult]; this
0x18002a594  call    ?DeleteKey@CRegistry@@QEBAXPEBGH@Z; CRegistry::DeleteKey(ushort const *,int)
0x18002a599  jmp     short loc_18002A578
0x18002a59b  lea     rcx, [rsp+88h+phkResult]; this
0x18002a5a0  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002a5a5  nop
0x18002a5a6  xor     r9d, r9d; Reserved
0x18002a5a9  xor     r8d, r8d; samDesired
0x18002a5ac  mov     rdx, rdi; lpSubKey
0x18002a5af  mov     rcx, [rbx]; hKey
0x18002a5b2  call    cs:__imp_RegDeleteKeyExW
0x18002a5b8  test    eax, eax
0x18002a5ba  jz      short loc_18002A5E8
0x18002a5bc  mov     [rsp+88h+pExceptionObject], eax
0x18002a5c0  lea     rdx, _TI1K; pThrowInfo
0x18002a5c7  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18002a5cc  call    _CxxThrowException_0
0x18002a5d2  mov     [rsp+88h+var_48], eax
0x18002a5d6  lea     rdx, _TI1K; pThrowInfo
0x18002a5dd  lea     rcx, [rsp+88h+var_48]; pExceptionObject
0x18002a5e2  call    _CxxThrowException_0
0x18002a5e8  mov     rbx, [rsp+88h+arg_10]
0x18002a5f0  add     rsp, 80h
0x18002a5f7  pop     rdi
0x18002a5f8  retn
```
