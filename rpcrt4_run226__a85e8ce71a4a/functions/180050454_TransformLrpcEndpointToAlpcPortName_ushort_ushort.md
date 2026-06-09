# TransformLrpcEndpointToAlpcPortName(ushort *,ushort * *)

- ea: `0x180050454`
- end: `0x1800504f8`
- name: `?TransformLrpcEndpointToAlpcPortName@@YAJPEAGPEAPEAG@Z`
- size: `164`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006abf0`
- `0x18008f5b8`

## callees

- `0x18002d420`
- `0x180050454`
- `0x180050500`

## import_xrefs

- `ntdll!wcsstr` at `0x180050473`
- `ntdll!wcsstr` at `0x180050473`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x18005048a`
- `ntdll!RtlGetAppContainerNamedObjectPath` at `0x18005048a`
- `ntdll!RtlFreeUnicodeString` at `0x1800504f0`
- `ntdll!RtlFreeUnicodeString` at `0x1800504f0`

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
0x180050454  mov     [rsp+arg_0], rbx
0x180050459  push    rdi
0x18005045a  sub     rsp, 30h
0x18005045e  mov     rbx, rdx
0x180050461  xorps   xmm0, xmm0
0x180050464  lea     rdx, aRpcControl; "\\RPC Control\\"
0x18005046b  mov     rdi, rcx
0x18005046e  movups  xmmword ptr [rsp+38h+UnicodeString.Length], xmm0
0x180050473  call    cs:__imp_wcsstr
0x180050479  test    rax, rax
0x18005047c  jnz     short loc_1800504CF
0x18005047e  lea     r9, [rsp+38h+UnicodeString]
0x180050483  xor     r8d, r8d
0x180050486  xor     edx, edx
0x180050488  xor     ecx, ecx
0x18005048a  call    cs:__imp_RtlGetAppContainerNamedObjectPath
0x180050490  test    eax, eax
0x180050492  js      short loc_18005049E
0x180050494  mov     rcx, [rsp+38h+UnicodeString.Buffer]; Src
0x180050499  test    rcx, rcx
0x18005049c  jnz     short loc_1800504D9
0x18005049e  mov     r8, rdi; unsigned __int16 *
0x1800504a1  lea     rdx, aRpcControl; "\\RPC Control\\"
0x1800504a8  lea     rcx, Src; Src
0x1800504af  call    ?DuplicateString3@@YAPEAGPEBG00@Z; DuplicateString3(ushort const *,ushort const *,ushort const *)
0x1800504b4  mov     [rbx], rax
0x1800504b7  mov     rax, [rbx]
0x1800504ba  mov     rbx, [rsp+38h+arg_0]
0x1800504bf  neg     rax
0x1800504c2  sbb     eax, eax
0x1800504c4  not     eax
0x1800504c6  and     eax, 0Eh
0x1800504c9  add     rsp, 30h
0x1800504cd  pop     rdi
0x1800504ce  retn
0x1800504cf  mov     rcx, rdi; Src
0x1800504d2  call    ?DuplicateString@@YAPEAGPEBG@Z; DuplicateString(ushort const *)
0x1800504d7  jmp     short loc_1800504B4
0x1800504d9  mov     r8, rdi; unsigned __int16 *
0x1800504dc  lea     rdx, aRpcControl; "\\RPC Control\\"
0x1800504e3  call    ?DuplicateString3@@YAPEAGPEBG00@Z; DuplicateString3(ushort const *,ushort const *,ushort const *)
0x1800504e8  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x1800504ed  mov     [rbx], rax
0x1800504f0  call    cs:__imp_RtlFreeUnicodeString
0x1800504f6  jmp     short loc_1800504B7
```
