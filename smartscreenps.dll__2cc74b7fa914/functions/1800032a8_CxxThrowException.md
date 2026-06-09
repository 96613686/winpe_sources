# _CxxThrowException

- ea: `0x1800032a8`
- end: `0x18000334e`
- name: `_CxxThrowException`
- size: `166`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002014`
- `0x18000203c`
- `0x180003e48`
- `0x180004304`
- `0x180008d14`
- `0x180008ed0`
- `0x180009060`
- `0x180009740`

## callees

- `0x1800032a8`
- `0x18000e010`

## import_xrefs

- `ntdll!RtlPcToFileHeader` at `0x1800032f7`
- `ntdll!RtlPcToFileHeader` at `0x1800032f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003338`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003338`

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
0x1800032a8  mov     [rsp+arg_10], rbx
0x1800032ad  mov     [rsp+arg_18], rsi
0x1800032b2  push    rdi
0x1800032b3  sub     rsp, 50h
0x1800032b7  mov     rbx, rdx
0x1800032ba  mov     rsi, rcx
0x1800032bd  mov     edi, 19930520h
0x1800032c2  test    rdx, rdx
0x1800032c5  jz      short loc_1800032E3
0x1800032c7  test    byte ptr [rdx], 10h
0x1800032ca  jz      short loc_1800032E3
0x1800032cc  mov     rcx, [rcx]
0x1800032cf  add     rcx, 0FFFFFFFFFFFFFFF8h
0x1800032d3  mov     rax, [rcx]
0x1800032d6  mov     rbx, [rax+30h]
0x1800032da  mov     rax, [rax+40h]
0x1800032de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032e3  xor     eax, eax
0x1800032e5  mov     [rsp+58h+BaseOfImage], rax
0x1800032ea  test    rbx, rbx
0x1800032ed  jz      short loc_180003311
0x1800032ef  lea     rdx, [rsp+58h+BaseOfImage]; BaseOfImage
0x1800032f4  mov     rcx, rbx; PcValue
0x1800032f7  call    cs:__imp_RtlPcToFileHeader
0x1800032fd  mov     [rsp+58h+BaseOfImage], rax
0x180003302  test    byte ptr [rbx], 8
0x180003305  jnz     short loc_18000330C
0x180003307  test    rax, rax
0x18000330a  jnz     short loc_180003311
0x18000330c  mov     edi, 1994000h
0x180003311  mov     edx, 1; dwExceptionFlags
0x180003316  mov     [rsp+58h+Arguments], rdi
0x18000331b  lea     r9, [rsp+58h+Arguments]; lpArguments
0x180003320  mov     [rsp+58h+var_28], rsi
0x180003325  mov     ecx, 0E06D7363h; dwExceptionCode
0x18000332a  mov     [rsp+58h+var_20], rbx
0x18000332f  mov     [rsp+58h+var_18], rax
0x180003334  lea     r8d, [rdx+3]; nNumberOfArguments
0x180003338  call    cs:__imp_RaiseException
0x18000333e  mov     rbx, [rsp+58h+arg_10]
0x180003343  mov     rsi, [rsp+58h+arg_18]
0x180003348  add     rsp, 50h
0x18000334c  pop     rdi
0x18000334d  retn
```
