# GetIscServiceName

- ea: `0x18002b934`
- end: `0x18002ba17`
- name: `GetIscServiceName`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18000ff20`

## callees

- `0x180007aa0`
- `0x18002b934`
- `0x180033768`
- `0x180038010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002b957`
- `ntdll!RtlInitUnicodeString` at `0x18002b957`

## pseudocode

```c
__int64 __fastcall GetIscServiceName(__int64 a1, __int64 a2)
{
  unsigned int i; // r8d
  unsigned __int16 *v5; // rbx
  __int64 result; // rax
  unsigned __int16 v7; // r10
  WCHAR *v8; // r11
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, &Class);
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)(a1 + 4) )
      return EncodeUnicodeString(&DestinationString.Length, 0xFDE9u, a2, 0);
    v5 = (unsigned __int16 *)(*(_QWORD *)(a1 + 8) + 16LL * i);
    if ( (*((_DWORD *)v5 + 1) & 0xFFFFFFF) == 0x10 )
      break;
  }
  if ( *((_QWORD *)v5 + 1) && *(_DWORD *)v5 )
  {
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)&g_LsaFunctions + 152LL))(
               *(_QWORD *)(a1 + 8) + 16LL * i,
               *(_QWORD *)(a1 + 8) + 16LL * i);
    if ( (int)result < 0 )
      return result;
    if ( *(_DWORD *)v5 > 0xFFFFu )
      return 3221225485LL;
    v7 = ustrlencounted(*((_QWORD *)v5 + 1), *v5);
    if ( v7 )
    {
      if ( v7 > 0x200u )
        return 3221225485LL;
      DestinationString.Buffer = v8;
      DestinationString.MaximumLength = *v5;
      DestinationString.Length = 2 * v7;
    }
  }
  return EncodeUnicodeString(&DestinationString.Length, 0xFDE9u, a2, 0);
}

```

## disassembly

```asm
0x18002b934  push    rbx
0x18002b936  push    rbp
0x18002b937  push    rsi
0x18002b938  push    rdi
0x18002b939  sub     rsp, 38h
0x18002b93d  mov     rsi, rdx
0x18002b940  mov     rdi, rcx
0x18002b943  xorps   xmm0, xmm0
0x18002b946  lea     rdx, Class; SourceString
0x18002b94d  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18002b952  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x18002b957  call    cs:__imp_RtlInitUnicodeString
0x18002b95d  xor     ebp, ebp
0x18002b95f  mov     r8d, ebp
0x18002b962  cmp     r8d, [rdi+4]
0x18002b966  jnb     loc_18002B9F9
0x18002b96c  mov     ebx, r8d
0x18002b96f  shl     rbx, 4
0x18002b973  add     rbx, [rdi+8]
0x18002b977  mov     eax, [rbx+4]
0x18002b97a  and     eax, 0FFFFFFFh
0x18002b97f  cmp     eax, 10h
0x18002b982  jz      short loc_18002B989
0x18002b984  inc     r8d
0x18002b987  jmp     short loc_18002B962
0x18002b989  cmp     [rbx+8], rbp
0x18002b98d  jz      short loc_18002B9F9
0x18002b98f  cmp     [rbx], ebp
0x18002b991  jz      short loc_18002B9F9
0x18002b993  mov     rax, cs:g_LsaFunctions
0x18002b99a  mov     rdx, rbx
0x18002b99d  mov     rcx, rbx
0x18002b9a0  mov     rax, [rax+98h]
0x18002b9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9ac  test    eax, eax
0x18002b9ae  js      short loc_18002BA0E
0x18002b9b0  cmp     dword ptr [rbx], 0FFFFh
0x18002b9b6  jbe     short loc_18002B9BF
0x18002b9b8  mov     eax, 0C000000Dh
0x18002b9bd  jmp     short loc_18002BA0E
0x18002b9bf  mov     r11, [rbx+8]
0x18002b9c3  movzx   edx, word ptr [rbx]
0x18002b9c6  mov     rcx, r11
0x18002b9c9  call    ustrlencounted
0x18002b9ce  movzx   r10d, ax
0x18002b9d2  test    ax, ax
0x18002b9d5  jz      short loc_18002B9F9
0x18002b9d7  mov     eax, 200h
0x18002b9dc  cmp     r10w, ax
0x18002b9e0  ja      short loc_18002B9B8
0x18002b9e2  mov     [rsp+58h+DestinationString.Buffer], r11
0x18002b9e7  add     r10w, r10w
0x18002b9eb  movzx   eax, word ptr [rbx]
0x18002b9ee  mov     [rsp+58h+DestinationString.MaximumLength], ax
0x18002b9f3  mov     [rsp+58h+DestinationString.Length], r10w
0x18002b9f9  xor     r9d, r9d
0x18002b9fc  lea     rcx, [rsp+58h+DestinationString]
0x18002ba01  mov     r8, rsi
0x18002ba04  mov     edx, 0FDE9h
0x18002ba09  call    EncodeUnicodeString
0x18002ba0e  add     rsp, 38h
0x18002ba12  pop     rdi
0x18002ba13  pop     rsi
0x18002ba14  pop     rbp
0x18002ba15  pop     rbx
0x18002ba16  retn
```
