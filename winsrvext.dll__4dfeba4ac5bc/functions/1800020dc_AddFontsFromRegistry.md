# AddFontsFromRegistry

- ea: `0x1800020dc`
- end: `0x180002224`
- name: `AddFontsFromRegistry`
- size: `328`
- prototype: `_DWORD *__fastcall(HANDLE KeyHandle, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180002aec`

## callees

- `0x1800020dc`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18000210e`
- `KERNELBASE!LocalAlloc` at `0x18000216a`
- `KERNELBASE!LocalAlloc` at `0x18000210e`
- `KERNELBASE!LocalAlloc` at `0x18000216a`
- `ntdll!NtEnumerateValueKey` at `0x180002147`
- `ntdll!NtEnumerateValueKey` at `0x1800021b2`
- `ntdll!NtEnumerateValueKey` at `0x180002147`
- `ntdll!NtEnumerateValueKey` at `0x1800021b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002181`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002181`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021fe`
- `GDI32!GdiAddFontResourceW` at `0x1800021e2`
- `GDI32!GdiAddFontResourceW` at `0x1800021e2`

## pseudocode

```c
_DWORD *__fastcall AddFontsFromRegistry(HANDLE KeyHandle, unsigned int a2)
{
  ULONG Length; // r14d
  _DWORD *result; // rax
  _DWORD *v6; // rbx
  unsigned int v7; // edi
  ULONG i; // esi
  NTSTATUS v9; // eax
  _DWORD *v10; // rbp
  ULONG ResultLength; // [rsp+70h] [rbp+18h] BYREF

  ResultLength = 0;
  Length = 1064;
  result = LocalAlloc(0x40u, 0x428u);
  v6 = result;
  if ( result )
  {
    v7 = 0;
    for ( i = 0; ; ++i )
    {
      v9 = NtEnumerateValueKey(KeyHandle, i, KeyValueFullInformation, v6, Length, &ResultLength);
      if ( v9 == -2147483643 || v9 == -1073741789 )
      {
        v10 = LocalAlloc(0x40u, ResultLength);
        if ( !v10 )
          continue;
        LocalFree(v6);
        Length = ResultLength;
        v6 = v10;
        v9 = NtEnumerateValueKey(KeyHandle, i, KeyValueFullInformation, v10, ResultLength, &ResultLength);
        if ( v9 == -2147483643 || v9 == -1073741789 )
          continue;
      }
      if ( v9 < 0 )
      {
        LocalFree(v6);
        return (_DWORD *)v7;
      }
      if ( v6[1] == 1 )
      {
        if ( (unsigned int)GdiAddFontResourceW((char *)v6 + (unsigned int)v6[2], a2, 0) )
          ++v7;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800020dc  mov     [rsp+arg_0], rbx
0x1800020e1  mov     [rsp+arg_8], rbp
0x1800020e6  push    rsi
0x1800020e7  push    rdi
0x1800020e8  push    r12
0x1800020ea  push    r14
0x1800020ec  push    r15
0x1800020ee  sub     rsp, 30h
0x1800020f2  mov     r12d, edx
0x1800020f5  mov     [rsp+58h+arg_10], 0
0x1800020fd  mov     r15, rcx
0x180002100  mov     r14d, 428h
0x180002106  mov     edx, r14d; uBytes
0x180002109  mov     ecx, 40h ; '@'; uFlags
0x18000210e  call    cs:__imp_LocalAlloc
0x180002115  nop     dword ptr [rax+rax+00h]
0x18000211a  mov     rbx, rax
0x18000211d  test    rax, rax
0x180002120  jz      loc_18000220C
0x180002126  xor     edi, edi
0x180002128  xor     esi, esi
0x18000212a  lea     rax, [rsp+58h+arg_10]
0x18000212f  mov     r9, rbx; KeyValueInformation
0x180002132  mov     [rsp+58h+ResultLength], rax; ResultLength
0x180002137  mov     r8d, 1; KeyValueInformationClass
0x18000213d  mov     edx, esi; Index
0x18000213f  mov     [rsp+58h+Length], r14d; Length
0x180002144  mov     rcx, r15; KeyHandle
0x180002147  call    cs:__imp_NtEnumerateValueKey
0x18000214e  nop     dword ptr [rax+rax+00h]
0x180002153  cmp     eax, 80000005h
0x180002158  jz      short loc_180002161
0x18000215a  cmp     eax, 0C0000023h
0x18000215f  jnz     short loc_1800021CC
0x180002161  mov     edx, [rsp+58h+arg_10]; uBytes
0x180002165  mov     ecx, 40h ; '@'; uFlags
0x18000216a  call    cs:__imp_LocalAlloc
0x180002171  nop     dword ptr [rax+rax+00h]
0x180002176  mov     rbp, rax
0x180002179  test    rax, rax
0x18000217c  jz      short loc_1800021F4
0x18000217e  mov     rcx, rbx; hMem
0x180002181  call    cs:__imp_LocalFree
0x180002188  nop     dword ptr [rax+rax+00h]
0x18000218d  mov     r14d, [rsp+58h+arg_10]
0x180002192  lea     rax, [rsp+58h+arg_10]
0x180002197  mov     [rsp+58h+ResultLength], rax; ResultLength
0x18000219c  mov     r9, rbp; KeyValueInformation
0x18000219f  mov     r8d, 1; KeyValueInformationClass
0x1800021a5  mov     [rsp+58h+Length], r14d; Length
0x1800021aa  mov     edx, esi; Index
0x1800021ac  mov     rcx, r15; KeyHandle
0x1800021af  mov     rbx, rbp
0x1800021b2  call    cs:__imp_NtEnumerateValueKey
0x1800021b9  nop     dword ptr [rax+rax+00h]
0x1800021be  cmp     eax, 80000005h
0x1800021c3  jz      short loc_1800021F4
0x1800021c5  cmp     eax, 0C0000023h
0x1800021ca  jz      short loc_1800021F4
0x1800021cc  test    eax, eax
0x1800021ce  js      short loc_1800021FB
0x1800021d0  cmp     dword ptr [rbx+4], 1
0x1800021d4  jnz     short loc_1800021F4
0x1800021d6  mov     ecx, [rbx+8]
0x1800021d9  xor     r8d, r8d
0x1800021dc  add     rcx, rbx
0x1800021df  mov     edx, r12d
0x1800021e2  call    cs:__imp_GdiAddFontResourceW
0x1800021e9  nop     dword ptr [rax+rax+00h]
0x1800021ee  test    eax, eax
0x1800021f0  jz      short loc_1800021F4
0x1800021f2  inc     edi
0x1800021f4  inc     esi
0x1800021f6  jmp     loc_18000212A
0x1800021fb  mov     rcx, rbx; hMem
0x1800021fe  call    cs:__imp_LocalFree
0x180002205  nop     dword ptr [rax+rax+00h]
0x18000220a  mov     eax, edi
0x18000220c  mov     rbx, [rsp+58h+arg_0]
0x180002211  mov     rbp, [rsp+58h+arg_8]
0x180002216  add     rsp, 30h
0x18000221a  pop     r15
0x18000221c  pop     r14
0x18000221e  pop     r12
0x180002220  pop     rdi
0x180002221  pop     rsi
0x180002222  retn
```
