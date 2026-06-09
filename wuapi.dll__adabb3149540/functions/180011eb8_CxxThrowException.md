# _CxxThrowException

- ea: `0x180011eb8`
- end: `0x180011f5e`
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
- `0x180005524`
- `0x180005a98`
- `0x180005e1c`
- `0x180006948`
- `0x180006a74`
- `0x18000f138`
- `0x18000f1a4`
- `0x180010af4`
- `0x180012aec`
- `0x180012fec`

## callees

- `0x180011eb8`
- `0x180015a00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011f48`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011f48`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlPcToFileHeader` at `0x180011f07`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlPcToFileHeader` at `0x180011f07`

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
0x180011eb8  mov     [rsp+arg_10], rbx
0x180011ebd  mov     [rsp+arg_18], rsi
0x180011ec2  push    rdi
0x180011ec3  sub     rsp, 50h
0x180011ec7  mov     rbx, rdx
0x180011eca  mov     rsi, rcx
0x180011ecd  mov     edi, 19930520h
0x180011ed2  test    rdx, rdx
0x180011ed5  jz      short loc_180011EF3
0x180011ed7  test    byte ptr [rdx], 10h
0x180011eda  jz      short loc_180011EF3
0x180011edc  mov     rcx, [rcx]
0x180011edf  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180011ee3  mov     rax, [rcx]
0x180011ee6  mov     rbx, [rax+30h]
0x180011eea  mov     rax, [rax+40h]
0x180011eee  call    _guard_dispatch_icall
0x180011ef3  xor     eax, eax
0x180011ef5  mov     [rsp+58h+BaseOfImage], rax
0x180011efa  test    rbx, rbx
0x180011efd  jz      short loc_180011F21
0x180011eff  lea     rdx, [rsp+58h+BaseOfImage]; BaseOfImage
0x180011f04  mov     rcx, rbx; PcValue
0x180011f07  call    cs:__imp_RtlPcToFileHeader
0x180011f0d  mov     [rsp+58h+BaseOfImage], rax
0x180011f12  test    byte ptr [rbx], 8
0x180011f15  jnz     short loc_180011F1C
0x180011f17  test    rax, rax
0x180011f1a  jnz     short loc_180011F21
0x180011f1c  mov     edi, 1994000h
0x180011f21  mov     edx, 1; dwExceptionFlags
0x180011f26  mov     [rsp+58h+Arguments], rdi
0x180011f2b  lea     r9, [rsp+58h+Arguments]; lpArguments
0x180011f30  mov     [rsp+58h+var_28], rsi
0x180011f35  mov     ecx, 0E06D7363h; dwExceptionCode
0x180011f3a  mov     [rsp+58h+var_20], rbx
0x180011f3f  mov     [rsp+58h+var_18], rax
0x180011f44  lea     r8d, [rdx+3]; nNumberOfArguments
0x180011f48  call    cs:__imp_RaiseException
0x180011f4e  mov     rbx, [rsp+58h+arg_10]
0x180011f53  mov     rsi, [rsp+58h+arg_18]
0x180011f58  add     rsp, 50h
0x180011f5c  pop     rdi
0x180011f5d  retn
```
