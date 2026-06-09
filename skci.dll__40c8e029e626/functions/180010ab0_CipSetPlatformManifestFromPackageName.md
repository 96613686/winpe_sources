# CipSetPlatformManifestFromPackageName

- ea: `0x180010ab0`
- end: `0x180010bcc`
- name: `CipSetPlatformManifestFromPackageName`
- size: `284`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180045408`

## callees

- `0x180006f10`
- `0x180010ab0`
- `0x18004f3e8`

## import_xrefs

- `securekernel!SkFreePool` at `0x180010ba4`
- `securekernel!SkFreePool` at `0x180010ba4`
- `securekernel!RtlUnicodeToUTF8N` at `0x180010b0f`
- `securekernel!RtlUnicodeToUTF8N` at `0x180010b5a`
- `securekernel!RtlUnicodeToUTF8N` at `0x180010b0f`
- `securekernel!RtlUnicodeToUTF8N` at `0x180010b5a`

## pseudocode

```c
__int64 __fastcall CipSetPlatformManifestFromPackageName(__int64 a1, __int64 a2)
{
  unsigned int v3; // edx
  NTSTATUS v5; // ebx
  const WCHAR *v6; // r9
  ULONG UnicodeStringByteCount; // r14d
  CHAR *PoolHelper; // rax
  CHAR *v9; // rdi
  __int64 v10; // r9
  _DWORD v12[2]; // [rsp+30h] [rbp-10h] BYREF
  CHAR *v13; // [rsp+38h] [rbp-8h]
  ULONG UTF8StringActualByteCount; // [rsp+78h] [rbp+38h] BYREF
  char v15; // [rsp+80h] [rbp+40h] BYREF

  v3 = *(_DWORD *)a2;
  v12[1] = 0;
  UTF8StringActualByteCount = 0;
  if ( v3 >= 2 )
  {
    v6 = *(const WCHAR **)(a2 + 8);
    UnicodeStringByteCount = v3 - 2;
    if ( v6[(v3 >> 1) - 1] )
      UnicodeStringByteCount = v3;
    v5 = RtlUnicodeToUTF8N(0, 0, &UTF8StringActualByteCount, v6, UnicodeStringByteCount);
    if ( v5 >= 0 )
    {
      PoolHelper = (CHAR *)SkAllocatePoolHelper(258, UTF8StringActualByteCount, 1919109443);
      v9 = PoolHelper;
      if ( PoolHelper )
      {
        v5 = RtlUnicodeToUTF8N(
               PoolHelper,
               UTF8StringActualByteCount,
               &UTF8StringActualByteCount,
               *(PCWCH *)(a2 + 8),
               UnicodeStringByteCount);
        if ( v5 >= 0 )
        {
          v10 = *(_QWORD *)(a1 + 16);
          v12[0] = UTF8StringActualByteCount;
          v13 = v9;
          v5 = HashpHashMemory(32780, 1, v12, v10 + 72, &v15);
        }
        SkFreePool(1, v9);
      }
      else
      {
        return (unsigned int)-1073741801;
      }
    }
  }
  else
  {
    return (unsigned int)-1073741275;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180010ab0  mov     [rsp-28h+arg_0], rbx
0x180010ab5  mov     [rsp-28h+arg_18], rsi
0x180010aba  push    rbp
0x180010abb  push    rdi
0x180010abc  push    r12
0x180010abe  push    r14
0x180010ac0  push    r15
0x180010ac2  mov     rbp, rsp
0x180010ac5  sub     rsp, 40h
0x180010ac9  xor     r12d, r12d
0x180010acc  mov     rsi, rdx
0x180010acf  mov     edx, [rdx]
0x180010ad1  mov     r15, rcx
0x180010ad4  mov     [rbp+var_C], r12d
0x180010ad8  mov     [rbp+UTF8StringActualByteCount], r12d
0x180010adc  cmp     edx, 2
0x180010adf  jnb     short loc_180010AEB
0x180010ae1  mov     ebx, 0C0000225h
0x180010ae6  jmp     loc_180010BB0
0x180010aeb  mov     r9, [rsi+8]; UnicodeStringSource
0x180010aef  lea     r14d, [rdx-2]
0x180010af3  mov     eax, edx
0x180010af5  lea     r8, [rbp+UTF8StringActualByteCount]; UTF8StringActualByteCount
0x180010af9  shr     eax, 1
0x180010afb  dec     eax
0x180010afd  cmp     [r9+rax*2], r12w
0x180010b02  cmovnz  r14d, edx
0x180010b06  xor     edx, edx; UTF8StringMaxByteCount
0x180010b08  xor     ecx, ecx; UTF8StringDestination
0x180010b0a  mov     [rsp+40h+UnicodeStringByteCount], r14d; UnicodeStringByteCount
0x180010b0f  call    cs:__imp_RtlUnicodeToUTF8N
0x180010b16  nop     dword ptr [rax+rax+00h]
0x180010b1b  mov     ebx, eax
0x180010b1d  test    eax, eax
0x180010b1f  js      loc_180010BB0
0x180010b25  mov     edx, [rbp+UTF8StringActualByteCount]
0x180010b28  mov     ecx, 102h
0x180010b2d  mov     r8d, 72634943h
0x180010b33  call    SkAllocatePoolHelper
0x180010b38  mov     rdi, rax
0x180010b3b  test    rax, rax
0x180010b3e  jnz     short loc_180010B47
0x180010b40  mov     ebx, 0C0000017h
0x180010b45  jmp     short loc_180010BB0
0x180010b47  mov     r9, [rsi+8]; UnicodeStringSource
0x180010b4b  lea     r8, [rbp+UTF8StringActualByteCount]; UTF8StringActualByteCount
0x180010b4f  mov     edx, [rbp+UTF8StringActualByteCount]; UTF8StringMaxByteCount
0x180010b52  mov     rcx, rdi; UTF8StringDestination
0x180010b55  mov     [rsp+40h+UnicodeStringByteCount], r14d; UnicodeStringByteCount
0x180010b5a  call    cs:__imp_RtlUnicodeToUTF8N
0x180010b61  nop     dword ptr [rax+rax+00h]
0x180010b66  mov     ebx, eax
0x180010b68  test    eax, eax
0x180010b6a  js      short loc_180010B9C
0x180010b6c  mov     eax, [rbp+UTF8StringActualByteCount]
0x180010b6f  lea     r8, [rbp+var_10]
0x180010b73  mov     r9, [r15+10h]
0x180010b77  mov     edx, 1
0x180010b7c  mov     [rbp+var_10], eax
0x180010b7f  add     r9, 48h ; 'H'
0x180010b83  lea     rax, [rbp+arg_10]
0x180010b87  mov     [rbp+var_8], rdi
0x180010b8b  mov     ecx, 800Ch
0x180010b90  mov     qword ptr [rsp+40h+UnicodeStringByteCount], rax
0x180010b95  call    HashpHashMemory
0x180010b9a  mov     ebx, eax
0x180010b9c  mov     rdx, rdi
0x180010b9f  mov     ecx, 1
0x180010ba4  call    cs:__imp_SkFreePool
0x180010bab  nop     dword ptr [rax+rax+00h]
0x180010bb0  lea     r11, [rsp+40h+var_s0]
0x180010bb5  mov     eax, ebx
0x180010bb7  mov     rbx, [r11+30h]
0x180010bbb  mov     rsi, [r11+48h]
0x180010bbf  mov     rsp, r11
0x180010bc2  pop     r15
0x180010bc4  pop     r14
0x180010bc6  pop     r12
0x180010bc8  pop     rdi
0x180010bc9  pop     rbp
0x180010bca  retn
```
