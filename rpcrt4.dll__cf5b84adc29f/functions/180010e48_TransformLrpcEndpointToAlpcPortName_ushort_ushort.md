# TransformLrpcEndpointToAlpcPortName(ushort *,ushort * *)

- ea: `0x180010e48`
- end: `0x180010eff`
- name: `?TransformLrpcEndpointToAlpcPortName@@YAJPEAGPEAPEAG@Z`
- size: `183`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aea0`
- `0x180093b40`

## callees

- `0x180010e48`
- `0x180010f10`
- `0x18002e750`

## import_xrefs

- `ntdll!wcsstr` at `0x180010e67`
- `ntdll!wcsstr` at `0x180010e67`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x180010e84`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x180010e84`
- `ntdll!RtlFreeUnicodeString` at `0x180010ef1`
- `ntdll!RtlFreeUnicodeString` at `0x180010ef1`

## pseudocode

```c
__int64 __fastcall TransformLrpcEndpointToAlpcPortName(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rax
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF

  UnicodeString = 0;
  if ( wcsstr(a1, L"\\RPC Control\\") )
  {
    v4 = DuplicateString(a1);
  }
  else
  {
    if ( (int)RtlGetAppContainerNamedObjectPath(0, 0, 0, &UnicodeString) >= 0 && UnicodeString.Buffer )
    {
      *a2 = DuplicateString3(UnicodeString.Buffer, L"\\RPC Control\\", a1);
      RtlFreeUnicodeString(&UnicodeString);
      return *a2 == 0 ? 0xE : 0;
    }
    v4 = DuplicateString3(&Src, L"\\RPC Control\\", a1);
  }
  *a2 = v4;
  return *a2 == 0 ? 0xE : 0;
}

```

## disassembly

```asm
0x180010e48  mov     [rsp+arg_0], rbx
0x180010e4d  push    rdi
0x180010e4e  sub     rsp, 30h
0x180010e52  mov     rbx, rdx
0x180010e55  xorps   xmm0, xmm0
0x180010e58  lea     rdx, aRpcControl; "\\RPC Control\\"
0x180010e5f  mov     rdi, rcx
0x180010e62  movups  xmmword ptr [rsp+38h+UnicodeString.Length], xmm0
0x180010e67  call    cs:__imp_wcsstr
0x180010e6e  nop     dword ptr [rax+rax+00h]
0x180010e73  test    rax, rax
0x180010e76  jnz     short loc_180010ED0
0x180010e78  lea     r9, [rsp+38h+UnicodeString]
0x180010e7d  xor     r8d, r8d
0x180010e80  xor     edx, edx
0x180010e82  xor     ecx, ecx
0x180010e84  call    cs:__imp_RtlGetAppContainerNamedObjectPath
0x180010e8b  nop     dword ptr [rax+rax+00h]
0x180010e90  test    eax, eax
0x180010e92  js      short loc_180010E9E
0x180010e94  mov     rcx, [rsp+38h+UnicodeString.Buffer]; Src
0x180010e99  test    rcx, rcx
0x180010e9c  jnz     short loc_180010EDA
0x180010e9e  mov     r8, rdi; unsigned __int16 *
0x180010ea1  lea     rdx, aRpcControl; "\\RPC Control\\"
0x180010ea8  lea     rcx, Src; Src
0x180010eaf  call    ?DuplicateString3@@YAPEAGPEBG00@Z; DuplicateString3(ushort const *,ushort const *,ushort const *)
0x180010eb4  mov     [rbx], rax
0x180010eb7  mov     rax, [rbx]
0x180010eba  mov     rbx, [rsp+38h+arg_0]
0x180010ebf  neg     rax
0x180010ec2  sbb     eax, eax
0x180010ec4  not     eax
0x180010ec6  and     eax, 0Eh
0x180010ec9  add     rsp, 30h
0x180010ecd  pop     rdi
0x180010ece  retn
0x180010ed0  mov     rcx, rdi; Src
0x180010ed3  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x180010ed8  jmp     short loc_180010EB4
0x180010eda  mov     r8, rdi; unsigned __int16 *
0x180010edd  lea     rdx, aRpcControl; "\\RPC Control\\"
0x180010ee4  call    ?DuplicateString3@@YAPEAGPEBG00@Z; DuplicateString3(ushort const *,ushort const *,ushort const *)
0x180010ee9  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x180010eee  mov     [rbx], rax
0x180010ef1  call    cs:__imp_RtlFreeUnicodeString
0x180010ef8  nop     dword ptr [rax+rax+00h]
0x180010efd  jmp     short loc_180010EB7
```
