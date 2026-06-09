# JobStore::RegOpenTaskOverrideKey(ushort const *,ulong,ulong,HKEY__ * *)

- ea: `0x18006e43c`
- end: `0x18006e528`
- name: `?RegOpenTaskOverrideKey@JobStore@@AEBAJPEBGKKPEAPEAUHKEY__@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(JobStore *this, const unsigned __int16 *, REGSAM, int, HKEY *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b5a0`
- `0x180017e70`
- `0x180023b60`
- `0x18006c840`

## callees

- `0x180040930`
- `0x180049b74`
- `0x18006e43c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006e517`
- `OLEAUT32!__imp_SysFreeString` at `0x18006e517`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e4cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e4cc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006e4ba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006e4ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall JobStore::RegOpenTaskOverrideKey(
        JobStore *this,
        const unsigned __int16 *a2,
        REGSAM a3,
        int a4,
        HKEY *a5)
{
  OLECHAR *v8; // rbx
  JobStore *v9; // rcx
  const WCHAR *v10; // rdx
  HKEY v11; // rcx
  int v12; // edi
  LSTATUS v13; // eax
  BSTR bstrString[7]; // [rsp+50h] [rbp-38h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp+8h] BYREF

  phkResult = 0;
  v8 = 0;
  bstrString[0] = 0;
  if ( !*((_QWORD *)this + 3) )
  {
    *a5 = 0;
LABEL_12:
    v12 = 0;
    goto LABEL_13;
  }
  ATL::CComBSTR::operator=(bstrString, a2);
  v8 = bstrString[0];
  JobStore::ReverseSlashesInString(v9, bstrString[0]);
  v11 = (HKEY)*((_QWORD *)this + 3);
  if ( a4 == 1 )
  {
    v12 = RegCreateKeyExW(v11, v10, 0, 0, 0, a3, 0, &phkResult, 0);
  }
  else
  {
    v13 = RegOpenKeyExW(v11, v10, 0, a3, &phkResult);
    v12 = v13;
    if ( v13 == 161 || v13 == 2 )
    {
      phkResult = 0;
      goto LABEL_12;
    }
  }
  if ( !v12 )
  {
    *a5 = phkResult;
    goto LABEL_12;
  }
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
LABEL_13:
  SysFreeString(v8);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18006e43c  mov     rax, rsp
0x18006e43f  push    rbx
0x18006e440  push    rbp
0x18006e441  push    rsi
0x18006e442  push    rdi
0x18006e443  sub     rsp, 68h
0x18006e447  mov     ebp, r9d
0x18006e44a  mov     esi, r8d
0x18006e44d  mov     rdi, rcx
0x18006e450  mov     qword ptr [rax+8], 0
0x18006e458  xor     ebx, ebx
0x18006e45a  mov     [rax-38h], rbx
0x18006e45e  cmp     [rcx+18h], rbx
0x18006e462  jnz     short loc_18006E474
0x18006e464  mov     rax, [rsp+88h+arg_20]
0x18006e46c  mov     [rax], rbx
0x18006e46f  jmp     loc_18006E512
0x18006e474  lea     rcx, [rsp+88h+bstrString]
0x18006e479  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18006e47e  mov     rbx, [rsp+88h+bstrString]
0x18006e483  mov     rdx, rbx; unsigned __int16 *
0x18006e486  call    ?ReverseSlashesInString@JobStore@@AEBAXPEAG@Z; JobStore::ReverseSlashesInString(ushort *)
0x18006e48b  mov     rcx, [rdi+18h]; hKey
0x18006e48f  lea     rax, [rsp+88h+arg_0]
0x18006e497  xor     r8d, r8d; ulOptions
0x18006e49a  cmp     ebp, 1
0x18006e49d  jnz     short loc_18006E4C4
0x18006e49f  mov     [rsp+88h+lpdwDisposition], r8; lpdwDisposition
0x18006e4a4  mov     [rsp+88h+phkResult], rax; phkResult
0x18006e4a9  mov     [rsp+88h+lpSecurityAttributes], r8; lpSecurityAttributes
0x18006e4ae  mov     [rsp+88h+samDesired], esi; samDesired
0x18006e4b2  mov     [rsp+88h+dwOptions], r8d; dwOptions
0x18006e4b7  xor     r9d, r9d; lpClass
0x18006e4ba  call    cs:__imp_RegCreateKeyExW
0x18006e4c0  mov     edi, eax
0x18006e4c2  jmp     short loc_18006E4E0
0x18006e4c4  mov     qword ptr [rsp+88h+dwOptions], rax; phkResult
0x18006e4c9  mov     r9d, esi; samDesired
0x18006e4cc  call    cs:__imp_RegOpenKeyExW
0x18006e4d2  mov     edi, eax
0x18006e4d4  cmp     eax, 0A1h
0x18006e4d9  jz      short loc_18006E506
0x18006e4db  cmp     eax, 2
0x18006e4de  jz      short loc_18006E506
0x18006e4e0  test    edi, edi
0x18006e4e2  jz      short loc_18006E4F1
0x18006e4e4  jle     short loc_18006E514
0x18006e4e6  movzx   edi, di
0x18006e4e9  or      edi, 80070000h
0x18006e4ef  jmp     short loc_18006E514
0x18006e4f1  mov     rcx, [rsp+88h+arg_20]
0x18006e4f9  mov     rax, [rsp+88h+arg_0]
0x18006e501  mov     [rcx], rax
0x18006e504  jmp     short loc_18006E512
0x18006e506  mov     [rsp+88h+arg_0], 0
0x18006e512  xor     edi, edi
0x18006e514  mov     rcx, rbx; bstrString
0x18006e517  call    cs:__imp_SysFreeString
0x18006e51d  mov     eax, edi
0x18006e51f  add     rsp, 68h
0x18006e523  pop     rdi
0x18006e524  pop     rsi
0x18006e525  pop     rbp
0x18006e526  pop     rbx
0x18006e527  retn
```
