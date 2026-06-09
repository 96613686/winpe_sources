# EndpointToPortNumber(ushort *,ushort &)

- ea: `0x18001efe8`
- end: `0x18001f037`
- name: `?EndpointToPortNumber@@YAJPEAGAEAG@Z`
- size: `79`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800059b0`
- `0x18000c1a0`
- `0x18000d6b0`
- `0x18000d7c0`
- `0x1800222b4`

## callees

- `0x18001efe8`

## import_xrefs

- `ntdll!wcstol` at `0x18001f005`
- `ntdll!wcstol` at `0x18001f005`

## pseudocode

```c
__int64 __fastcall EndpointToPortNumber(unsigned __int16 *a1, unsigned __int16 *a2)
{
  int v3; // eax
  wchar_t *EndPtr; // [rsp+40h] [rbp+18h] BYREF

  EndPtr = 0;
  v3 = wcstol(a1, &EndPtr, 10);
  if ( (unsigned int)(v3 - 1) > 0xFFFE || *EndPtr )
    return 1706;
  *a2 = v3;
  return 0;
}

```

## disassembly

```asm
0x18001efe8  mov     [rsp+arg_0], rbx
0x18001efed  push    rdi
0x18001efee  sub     rsp, 20h
0x18001eff2  xor     edi, edi
0x18001eff4  mov     rbx, rdx
0x18001eff7  lea     rdx, [rsp+28h+EndPtr]; EndPtr
0x18001effc  mov     [rsp+28h+EndPtr], rdi
0x18001f001  lea     r8d, [rdi+0Ah]; Radix
0x18001f005  call    cs:__imp_wcstol
0x18001f00b  lea     ecx, [rax-1]
0x18001f00e  cmp     ecx, 0FFFEh
0x18001f014  ja      short loc_18001F027
0x18001f016  mov     rcx, [rsp+28h+EndPtr]
0x18001f01b  cmp     [rcx], di
0x18001f01e  jnz     short loc_18001F027
0x18001f020  mov     [rbx], ax
0x18001f023  xor     eax, eax
0x18001f025  jmp     short loc_18001F02C
0x18001f027  mov     eax, 6AAh
0x18001f02c  mov     rbx, [rsp+28h+arg_0]
0x18001f031  add     rsp, 20h
0x18001f035  pop     rdi
0x18001f036  retn
```
