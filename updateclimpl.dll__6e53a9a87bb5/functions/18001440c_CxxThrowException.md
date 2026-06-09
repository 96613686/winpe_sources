# _CxxThrowException

- ea: `0x18001440c`
- end: `0x1800144b2`
- name: `_CxxThrowException`
- size: `166`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x1800057b8`
- `0x180005800`
- `0x180005820`
- `0x180005960`
- `0x180008408`
- `0x1800097f4`
- `0x18000a400`
- `0x18000d4f0`
- `0x18000db38`
- `0x18000dba4`
- `0x18000dc10`
- `0x18000dc7c`
- `0x180012608`
- `0x180015922`
- `0x180015b72`
- `0x180015c33`
- `0x180015c92`

## callees

- `0x18001440c`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001449c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001449c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlPcToFileHeader` at `0x18001445b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlPcToFileHeader` at `0x18001445b`

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
0x18001440c  mov     [rsp+arg_10], rbx
0x180014411  mov     [rsp+arg_18], rsi
0x180014416  push    rdi
0x180014417  sub     rsp, 50h
0x18001441b  mov     rbx, rdx
0x18001441e  mov     rsi, rcx
0x180014421  mov     edi, 19930520h
0x180014426  test    rdx, rdx
0x180014429  jz      short loc_180014447
0x18001442b  test    byte ptr [rdx], 10h
0x18001442e  jz      short loc_180014447
0x180014430  mov     rcx, [rcx]
0x180014433  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180014437  mov     rax, [rcx]
0x18001443a  mov     rbx, [rax+30h]
0x18001443e  mov     rax, [rax+40h]
0x180014442  call    _guard_dispatch_icall
0x180014447  xor     eax, eax
0x180014449  mov     [rsp+58h+BaseOfImage], rax
0x18001444e  test    rbx, rbx
0x180014451  jz      short loc_180014475
0x180014453  lea     rdx, [rsp+58h+BaseOfImage]; BaseOfImage
0x180014458  mov     rcx, rbx; PcValue
0x18001445b  call    cs:__imp_RtlPcToFileHeader
0x180014461  mov     [rsp+58h+BaseOfImage], rax
0x180014466  test    byte ptr [rbx], 8
0x180014469  jnz     short loc_180014470
0x18001446b  test    rax, rax
0x18001446e  jnz     short loc_180014475
0x180014470  mov     edi, 1994000h
0x180014475  mov     edx, 1; dwExceptionFlags
0x18001447a  mov     [rsp+58h+Arguments], rdi
0x18001447f  lea     r9, [rsp+58h+Arguments]; lpArguments
0x180014484  mov     [rsp+58h+var_28], rsi
0x180014489  mov     ecx, 0E06D7363h; dwExceptionCode
0x18001448e  mov     [rsp+58h+var_20], rbx
0x180014493  mov     [rsp+58h+var_18], rax
0x180014498  lea     r8d, [rdx+3]; nNumberOfArguments
0x18001449c  call    cs:__imp_RaiseException
0x1800144a2  mov     rbx, [rsp+58h+arg_10]
0x1800144a7  mov     rsi, [rsp+58h+arg_18]
0x1800144ac  add     rsp, 50h
0x1800144b0  pop     rdi
0x1800144b1  retn
```
