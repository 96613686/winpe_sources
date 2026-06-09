# _CxxThrowException

- ea: `0x180011e68`
- end: `0x180011f0e`
- name: `_CxxThrowException`
- size: `166`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180002fe8`
- `0x180003030`
- `0x180003050`
- `0x180003190`
- `0x180006cac`
- `0x180007240`
- `0x1800080ec`
- `0x180008ebc`
- `0x18000a7a0`
- `0x18000f0e8`
- `0x18000f154`
- `0x180010aa4`
- `0x180012a9c`
- `0x180012f9c`

## callees

- `0x180011e68`
- `0x1800159b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011ef8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011ef8`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlPcToFileHeader` at `0x180011eb7`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlPcToFileHeader` at `0x180011eb7`

## pseudocode

```c
void __stdcall __noreturn CxxThrowException(void *pExceptionObject, _ThrowInfo *pThrowInfo)
{
  _ThrowInfo *v2; // rbx
  ULONG_PTR v4; // rdi
  __int64 v5; // rcx
  PVOID v6; // rax
  PVOID BaseOfImage; // [rsp+20h] [rbp-38h] BYREF
  ULONG_PTR Arguments[6]; // [rsp+28h] [rbp-30h] BYREF

  v2 = pThrowInfo;
  v4 = 429065504;
  if ( pThrowInfo && (pThrowInfo->attributes & 0x10) != 0 )
  {
    v5 = *(_QWORD *)pExceptionObject - 8LL;
    v2 = *(_ThrowInfo **)(*(_QWORD *)v5 + 48LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 64LL))(v5);
  }
  v6 = 0;
  BaseOfImage = 0;
  if ( v2 )
  {
    v6 = RtlPcToFileHeader(v2, &BaseOfImage);
    BaseOfImage = v6;
    if ( (v2->attributes & 8) != 0 || !v6 )
      v4 = 26820608;
  }
  Arguments[0] = v4;
  Arguments[1] = (ULONG_PTR)pExceptionObject;
  Arguments[2] = (ULONG_PTR)v2;
  Arguments[3] = (ULONG_PTR)v6;
  RaiseException(0xE06D7363, 1u, 4u, Arguments);
}

```

## disassembly

```asm
0x180011e68  mov     [rsp+arg_10], rbx
0x180011e6d  mov     [rsp+arg_18], rsi
0x180011e72  push    rdi
0x180011e73  sub     rsp, 50h
0x180011e77  mov     rbx, rdx
0x180011e7a  mov     rsi, rcx
0x180011e7d  mov     edi, 19930520h
0x180011e82  test    rdx, rdx
0x180011e85  jz      short loc_180011EA3
0x180011e87  test    byte ptr [rdx], 10h
0x180011e8a  jz      short loc_180011EA3
0x180011e8c  mov     rcx, [rcx]
0x180011e8f  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180011e93  mov     rax, [rcx]
0x180011e96  mov     rbx, [rax+30h]
0x180011e9a  mov     rax, [rax+40h]
0x180011e9e  call    _guard_dispatch_icall
0x180011ea3  xor     eax, eax
0x180011ea5  mov     [rsp+58h+BaseOfImage], rax
0x180011eaa  test    rbx, rbx
0x180011ead  jz      short loc_180011ED1
0x180011eaf  lea     rdx, [rsp+58h+BaseOfImage]; BaseOfImage
0x180011eb4  mov     rcx, rbx; PcValue
0x180011eb7  call    cs:__imp_RtlPcToFileHeader
0x180011ebd  mov     [rsp+58h+BaseOfImage], rax
0x180011ec2  test    byte ptr [rbx], 8
0x180011ec5  jnz     short loc_180011ECC
0x180011ec7  test    rax, rax
0x180011eca  jnz     short loc_180011ED1
0x180011ecc  mov     edi, 1994000h
0x180011ed1  mov     edx, 1; dwExceptionFlags
0x180011ed6  mov     [rsp+58h+Arguments], rdi
0x180011edb  lea     r9, [rsp+58h+Arguments]; lpArguments
0x180011ee0  mov     [rsp+58h+var_28], rsi
0x180011ee5  mov     ecx, 0E06D7363h; dwExceptionCode
0x180011eea  mov     [rsp+58h+var_20], rbx
0x180011eef  mov     [rsp+58h+var_18], rax
0x180011ef4  lea     r8d, [rdx+3]; nNumberOfArguments
0x180011ef8  call    cs:__imp_RaiseException
0x180011efe  mov     rbx, [rsp+58h+arg_10]
0x180011f03  mov     rsi, [rsp+58h+arg_18]
0x180011f08  add     rsp, 50h
0x180011f0c  pop     rdi
0x180011f0d  retn
```
