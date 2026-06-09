# ForgetReader(ulong,ushort const *)

- ea: `0x18002acb0`
- end: `0x18002ad83`
- name: `?ForgetReader@@YAXKPEBG@Z`
- size: `211`
- prototype: `void(unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025170`
- `0x180027630`

## callees

- `0x180002220`
- `0x180013c90`
- `0x18002a528`
- `0x18002acb0`
- `0x18002ef20`

## string_xrefs

- `0x18002ad35`: `SOFTWARE\Microsoft\Cryptography\Calais\Readers`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ForgetReader(int a1, const unsigned __int16 *a2)
{
  int v3; // r8d
  HKEY phkResult[5]; // [rsp+30h] [rbp-30h] BYREF
  int v5; // [rsp+58h] [rbp-8h]
  ulong pExceptionObject; // [rsp+80h] [rbp+20h] BYREF

  phkResult[2] = (HKEY)&CBuffer::`vftable';
  phkResult[3] = 0;
  phkResult[4] = 0;
  phkResult[0] = 0;
  v5 = 1010;
  v3 = 0;
  while ( dword_180039DB0[4 * v3] != a1 )
  {
    if ( (unsigned int)++v3 >= 2 )
    {
      pExceptionObject = -2146435055;
      throw &pExceptionObject;
    }
  }
  if ( !a2 || !*a2 )
  {
    pExceptionObject = -2146435055;
    throw &pExceptionObject;
  }
  CRegistry::Open(
    phkResult,
    *(HKEY *)&dword_180039DB0[4 * v3 + 2],
    L"SOFTWARE\\Microsoft\\Cryptography\\Calais\\Readers",
    0x20006u,
    0xFFFFFFE0);
  CRegistry::DeleteKey((CRegistry *)phkResult, a2);
  CRegistry::~CRegistry((CRegistry *)phkResult);
}

```

## disassembly

```asm
0x18002acb0  mov     [rsp-8+arg_0], rbx
0x18002acb5  push    rbp
0x18002acb6  mov     rbp, rsp
0x18002acb9  sub     rsp, 60h
0x18002acbd  mov     rbx, rdx
0x18002acc0  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18002acc7  mov     [rbp+var_20], rax
0x18002accb  xor     edx, edx
0x18002accd  mov     [rbp+var_18], rdx
0x18002acd1  mov     [rbp+var_10], rdx
0x18002acd5  mov     [rbp+phkResult], rdx
0x18002acd9  mov     [rbp+var_8], 3F2h
0x18002ace0  mov     r8d, edx
0x18002ace3  lea     r10, dword_180039DB0
0x18002acea  mov     eax, r8d
0x18002aced  add     rax, rax
0x18002acf0  cmp     [r10+rax*8], ecx
0x18002acf4  jz      short loc_18002AD17
0x18002acf6  inc     r8d
0x18002acf9  cmp     r8d, 2
0x18002acfd  jb      short loc_18002ACEA
0x18002acff  mov     [rbp+pExceptionObject], 80100011h
0x18002ad06  lea     rdx, _TI1K; pThrowInfo
0x18002ad0d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002ad11  call    _CxxThrowException_0
0x18002ad17  test    rbx, rbx
0x18002ad1a  jz      short loc_18002AD6B
0x18002ad1c  cmp     dx, [rbx]
0x18002ad1f  jz      short loc_18002AD6B
0x18002ad21  mov     edx, r8d
0x18002ad24  add     rdx, rdx
0x18002ad27  mov     [rsp+60h+dwOptions], 0FFFFFFE0h; dwOptions
0x18002ad2f  mov     r9d, 20006h; samDesired
0x18002ad35  lea     r8, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Cryptography\\Cala"...
0x18002ad3c  mov     rdx, [r10+rdx*8+8]; hKey
0x18002ad41  lea     rcx, [rbp+phkResult]; phkResult
0x18002ad45  call    ?Open@CRegistry@@QEAAXPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x18002ad4a  mov     rdx, rbx; unsigned __int16 *
0x18002ad4d  lea     rcx, [rbp+phkResult]; this
0x18002ad51  call    ?DeleteKey@CRegistry@@QEBAXPEBGH@Z; CRegistry::DeleteKey(ushort const *,int)
0x18002ad56  nop
0x18002ad57  lea     rcx, [rbp+phkResult]; this
0x18002ad5b  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18002ad60  mov     rbx, [rsp+60h+arg_0]
0x18002ad65  add     rsp, 60h
0x18002ad69  pop     rbp
0x18002ad6a  retn
0x18002ad6b  mov     [rbp+pExceptionObject], 80100011h
0x18002ad72  lea     rdx, _TI1K; pThrowInfo
0x18002ad79  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002ad7d  call    _CxxThrowException_0
```
