# TSCopyClientString(void *,ulong,uchar,_UNICODE_STRING *,ulong)

- ea: `0x1800139d0`
- end: `0x180013aca`
- name: `?TSCopyClientString@@YAJPEAXKEPEAU_UNICODE_STRING@@K@Z`
- size: `250`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned __int8, struct _UNICODE_STRING *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180015304`

## callees

- `0x1800032c0`
- `0x180005ed0`
- `0x1800139d0`
- `0x18001d010`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x180013a89`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180013a89`

## pseudocode

```c
__int64 __fastcall TSCopyClientString(void *a1, unsigned int a2, char a3, struct _UNICODE_STRING *a4, unsigned int a5)
{
  NTSTATUS v8; // ebx
  unsigned __int64 v9; // rdi
  WCHAR *v10; // rax
  WCHAR *v11; // rsi
  _STRING SourceString; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF

  if ( a2 > a5 )
    return (unsigned int)-1073741811;
  v9 = (2LL - (a3 != 0)) * a2;
  if ( v9 > 0xFFFFFFFF )
    return (unsigned int)-1073741675;
  if ( (unsigned int)v9 > 0xFFFE )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    v10 = (WCHAR *)TSAllocate((unsigned int)v9);
    v11 = v10;
    if ( v10 )
    {
      v8 = ((__int64 (__fastcall *)(_QWORD, _QWORD, WCHAR *, void *))TSGlobalLsaFunctions->CopyFromClientBuffer)(
             0,
             (unsigned int)v9,
             v10,
             a1);
      if ( v8 >= 0 )
      {
        if ( !a3 )
        {
          a4->Buffer = v11;
          a4->Length = v9;
          a4->MaximumLength = v9;
          return (unsigned int)v8;
        }
        *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
        SourceString.Buffer = (PCHAR)v11;
        SourceString.Length = v9;
        SourceString.MaximumLength = v9;
        DestinationString = 0;
        v8 = RtlAnsiStringToUnicodeString(&DestinationString, &SourceString, 1u);
        if ( v8 >= 0 )
          *a4 = DestinationString;
      }
      TSFree(v11);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800139d0  push    rbx
0x1800139d2  push    rbp
0x1800139d3  push    rsi
0x1800139d4  push    rdi
0x1800139d5  push    r14
0x1800139d7  sub     rsp, 50h
0x1800139db  mov     r14, r9
0x1800139de  mov     al, r8b
0x1800139e1  neg     al
0x1800139e3  mov     bpl, r8b
0x1800139e6  mov     rbx, rcx
0x1800139e9  sbb     r9, r9
0x1800139ec  add     r9, 2
0x1800139f0  cmp     edx, [rsp+78h+arg_20]
0x1800139f7  jbe     short loc_180013A03
0x1800139f9  mov     ebx, 0C000000Dh
0x1800139fe  jmp     loc_180013ABD
0x180013a03  mov     edi, edx
0x180013a05  mov     eax, 0FFFFFFFFh
0x180013a0a  imul    rdi, r9
0x180013a0e  cmp     rdi, rax
0x180013a11  ja      loc_180013AB8
0x180013a17  cmp     edi, 0FFFEh
0x180013a1d  ja      short loc_1800139F9
0x180013a1f  mov     ecx, edi; Size
0x180013a21  call    ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x180013a26  mov     rsi, rax
0x180013a29  test    rax, rax
0x180013a2c  jnz     short loc_180013A38
0x180013a2e  mov     ebx, 0C000009Ah
0x180013a33  jmp     loc_180013ABD
0x180013a38  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x180013a3f  mov     r9, rbx
0x180013a42  mov     r8, rsi
0x180013a45  mov     edx, edi
0x180013a47  xor     ecx, ecx
0x180013a49  mov     rax, [rax+50h]
0x180013a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a52  mov     ebx, eax
0x180013a54  test    eax, eax
0x180013a56  js      short loc_180013A9F
0x180013a58  test    bpl, bpl
0x180013a5b  jz      short loc_180013AA9
0x180013a5d  xorps   xmm0, xmm0
0x180013a60  lea     rdx, [rsp+78h+SourceString]; SourceString
0x180013a65  movups  xmmword ptr [rsp+78h+SourceString.Length], xmm0
0x180013a6a  mov     [rsp+78h+SourceString.Buffer], rsi
0x180013a6f  mov     r8b, 1; AllocateDestinationString
0x180013a72  xorps   xmm1, xmm1
0x180013a75  mov     [rsp+78h+SourceString.Length], di
0x180013a7a  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180013a7f  mov     [rsp+78h+SourceString.MaximumLength], di
0x180013a84  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm1
0x180013a89  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180013a8f  mov     ebx, eax
0x180013a91  test    eax, eax
0x180013a93  js      short loc_180013A9F
0x180013a95  movups  xmm0, xmmword ptr [rsp+78h+DestinationString.Length]
0x180013a9a  movdqu  xmmword ptr [r14], xmm0
0x180013a9f  mov     rcx, rsi; void *
0x180013aa2  call    ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x180013aa7  jmp     short loc_180013ABD
0x180013aa9  mov     [r14+8], rsi
0x180013aad  mov     [r14], di
0x180013ab1  mov     [r14+2], di
0x180013ab6  jmp     short loc_180013ABD
0x180013ab8  mov     ebx, 0C0000095h
0x180013abd  mov     eax, ebx
0x180013abf  add     rsp, 50h
0x180013ac3  pop     r14
0x180013ac5  pop     rdi
0x180013ac6  pop     rsi
0x180013ac7  pop     rbp
0x180013ac8  pop     rbx
0x180013ac9  retn
```
