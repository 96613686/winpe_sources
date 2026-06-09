# TpmApiRegistryGetAlgorithmProvider(ushort * *,ulong *)

- ea: `0x140033e18`
- end: `0x140033f60`
- name: `?TpmApiRegistryGetAlgorithmProvider@@YAJPEAPEAGPEAK@Z`
- size: `328`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140033d74`

## callees

- `0x140032c60`
- `0x140032c88`
- `0x140033e18`
- `0x140033f68`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140033e68`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033e7f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033e68`
- `ntoskrnl!RtlInitUnicodeString` at `0x140033e7f`

## string_xrefs

- `0x140033e55`: `\Registry\Machine\System\CurrentControlSet\Control\BitLocker`

## pseudocode

```c
__int64 __fastcall TpmApiRegistryGetAlgorithmProvider(unsigned __int16 **a1, unsigned int *a2)
{
  int Value; // eax
  unsigned int v5; // edi
  int v6; // ebx
  void *v7; // r8
  _WORD *v8; // rax
  unsigned __int64 v9; // rdx
  struct _UNICODE_STRING v11; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v13; // [rsp+70h] [rbp+20h] BYREF
  void *v14; // [rsp+78h] [rbp+28h] BYREF

  *a1 = 0;
  *a2 = 0;
  v13 = 0;
  v14 = 0;
  DestinationString = 0;
  v11 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\BitLocker");
  RtlInitUnicodeString(&v11, L"AlgorithmProvider");
  Value = TpmApiRegistryGetValue(&DestinationString, &v11, 1, 0, &v13);
  v5 = v13;
  v6 = Value;
  if ( Value != -1073741789 )
    goto LABEL_10;
  TpmApiCallbackAlloc(0, v13, &v14);
  v7 = v14;
  if ( v14 )
  {
    v13 = v5;
    v6 = TpmApiRegistryGetValue(&DestinationString, &v11, 1, v14, &v13);
    if ( v6 >= 0 )
    {
      if ( v13 == v5 && v13 >= 2 && (v13 & 1) == 0 )
      {
        v8 = v14;
        v9 = (unsigned __int64)v13 >> 1;
        *a2 = v13;
        v7 = 0;
        v8[v9 - 1] = 0;
        *a1 = (unsigned __int16 *)v14;
        v14 = 0;
        goto LABEL_11;
      }
      v6 = -1073741811;
    }
LABEL_10:
    v7 = v14;
    goto LABEL_11;
  }
  v6 = -1073741801;
LABEL_11:
  TpmApiCallbackFree(0, v5, v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140033e18  mov     [rsp-18h+arg_10], rbx
0x140033e1d  mov     [rsp-18h+arg_18], rsi
0x140033e22  push    rbp
0x140033e23  push    rdi
0x140033e24  push    r14
0x140033e26  mov     rbp, rsp
0x140033e29  sub     rsp, 50h
0x140033e2d  mov     rsi, rdx
0x140033e30  mov     qword ptr [rcx], 0
0x140033e37  mov     r14, rcx
0x140033e3a  mov     dword ptr [rdx], 0
0x140033e40  xorps   xmm0, xmm0
0x140033e43  mov     [rbp+arg_0], 0
0x140033e4a  xorps   xmm1, xmm1
0x140033e4d  mov     [rbp+arg_8], 0
0x140033e55  lea     rdx, aRegistryMachin_21; "\\Registry\\Machine\\System\\CurrentCon"...
0x140033e5c  lea     rcx, [rbp+DestinationString]; DestinationString
0x140033e60  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140033e64  movups  xmmword ptr [rbp+var_20.Length], xmm1
0x140033e68  call    cs:__imp_RtlInitUnicodeString
0x140033e6f  nop     dword ptr [rax+rax+00h]
0x140033e74  lea     rdx, aAlgorithmprovi; "AlgorithmProvider"
0x140033e7b  lea     rcx, [rbp+var_20]; DestinationString
0x140033e7f  call    cs:__imp_RtlInitUnicodeString
0x140033e86  nop     dword ptr [rax+rax+00h]
0x140033e8b  xor     r9d, r9d; void *
0x140033e8e  lea     rax, [rbp+arg_0]
0x140033e92  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140033e96  mov     [rsp+50h+var_30], rax; unsigned int *
0x140033e9b  lea     rcx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x140033e9f  lea     r8d, [r9+1]; unsigned int
0x140033ea3  call    ?TpmApiRegistryGetValue@@YAJPEAU_UNICODE_STRING@@0KPEAXPEAK@Z; TpmApiRegistryGetValue(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *,ulong *)
0x140033ea8  mov     edi, [rbp+arg_0]
0x140033eab  mov     ebx, eax
0x140033ead  cmp     eax, 0C0000023h
0x140033eb2  jnz     loc_140033F3B
0x140033eb8  lea     r8, [rbp+arg_8]
0x140033ebc  mov     edx, edi
0x140033ebe  xor     ecx, ecx
0x140033ec0  call    TpmApiCallbackAlloc
0x140033ec5  mov     r8, [rbp+arg_8]
0x140033ec9  test    r8, r8
0x140033ecc  jnz     short loc_140033ED5
0x140033ece  mov     ebx, 0C0000017h
0x140033ed3  jmp     short loc_140033F3F
0x140033ed5  lea     rax, [rbp+arg_0]
0x140033ed9  mov     [rbp+arg_0], edi
0x140033edc  mov     r9, r8; void *
0x140033edf  mov     [rsp+50h+var_30], rax; unsigned int *
0x140033ee4  mov     r8d, 1; unsigned int
0x140033eea  lea     rdx, [rbp+var_20]; struct _UNICODE_STRING *
0x140033eee  lea     rcx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x140033ef2  call    ?TpmApiRegistryGetValue@@YAJPEAU_UNICODE_STRING@@0KPEAXPEAK@Z; TpmApiRegistryGetValue(_UNICODE_STRING *,_UNICODE_STRING *,ulong,void *,ulong *)
0x140033ef7  mov     ebx, eax
0x140033ef9  test    eax, eax
0x140033efb  js      short loc_140033F3B
0x140033efd  mov     r8d, [rbp+arg_0]
0x140033f01  cmp     r8d, edi
0x140033f04  jnz     short loc_140033F36
0x140033f06  cmp     r8d, 2
0x140033f0a  jb      short loc_140033F36
0x140033f0c  test    r8b, 1
0x140033f10  jnz     short loc_140033F36
0x140033f12  mov     rax, [rbp+arg_8]
0x140033f16  mov     edx, r8d
0x140033f19  shr     rdx, 1
0x140033f1c  xor     ecx, ecx
0x140033f1e  mov     [rsi], r8d
0x140033f21  xor     r8d, r8d
0x140033f24  mov     [rax+rdx*2-2], cx
0x140033f29  mov     rax, [rbp+arg_8]
0x140033f2d  mov     [r14], rax
0x140033f30  mov     [rbp+arg_8], r8
0x140033f34  jmp     short loc_140033F3F
0x140033f36  mov     ebx, 0C000000Dh
0x140033f3b  mov     r8, [rbp+arg_8]
0x140033f3f  mov     edx, edi
0x140033f41  xor     ecx, ecx
0x140033f43  call    TpmApiCallbackFree
0x140033f48  lea     r11, [rsp+50h+var_s0]
0x140033f4d  mov     eax, ebx
0x140033f4f  mov     rbx, [r11+30h]
0x140033f53  mov     rsi, [r11+38h]
0x140033f57  mov     rsp, r11
0x140033f5a  pop     r14
0x140033f5c  pop     rdi
0x140033f5d  pop     rbp
0x140033f5e  retn
```
