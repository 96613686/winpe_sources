# XMLParser<GenericLexerSource>::OpenStartElementTag(ushort const *)

- ea: `0x180013d60`
- end: `0x180013db4`
- name: `?OpenStartElementTag@?$XMLParser@VGenericLexerSource@@@@AEAAXPEBG@Z`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013a0c`

## callees

- `0x180013450`
- `0x1800134f8`
- `0x180013d60`

## pseudocode

```c
__int64 __fastcall XMLParser<GenericLexerSource>::OpenStartElementTag(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // rbx
  int v6; // edi
  __int64 v7; // rdx
  __int64 result; // rax

  v2 = -1;
  do
    ++v2;
  while ( *(_WORD *)(a2 + 2 * v2) );
  v3 = XMLParser<GenericLexerSource>::HashStringCaseSensitive();
  v5 = v4 + 8;
  v6 = v3;
  if ( (unsigned int)(*(_DWORD *)(v4 + 44) + 2) > *(_DWORD *)(v4 + 40) )
    wmi::Stack<unsigned long,6,16>::Extend(v5);
  v7 = *(int *)(v5 + 36);
  result = *(_QWORD *)(v5 + 24);
  *(_DWORD *)(v5 + 36) = v7 + 1;
  *(_DWORD *)(result + 4 * v7 + 4) = v6;
  return result;
}

```

## disassembly

```asm
0x180013d60  mov     [rsp+arg_0], rbx
0x180013d65  push    rdi
0x180013d66  sub     rsp, 20h
0x180013d6a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180013d6e  inc     r8
0x180013d71  cmp     word ptr [rdx+r8*2], 0
0x180013d77  jnz     short loc_180013D6E
0x180013d79  call    ?HashStringCaseSensitive@?$XMLParser@VGenericLexerSource@@@@AEAAKPEBGK@Z; XMLParser<GenericLexerSource>::HashStringCaseSensitive(ushort const *,ulong)
0x180013d7e  lea     rbx, [rcx+8]
0x180013d82  mov     edi, eax
0x180013d84  mov     ecx, [rbx+24h]
0x180013d87  add     ecx, 2
0x180013d8a  cmp     ecx, [rbx+20h]
0x180013d8d  jbe     short loc_180013D97
0x180013d8f  mov     rcx, rbx
0x180013d92  call    ?Extend@?$Stack@K$05$0BA@@wmi@@AEAAXXZ; wmi::Stack<ulong,6,16>::Extend(void)
0x180013d97  movsxd  rdx, dword ptr [rbx+24h]
0x180013d9b  mov     rax, [rbx+18h]
0x180013d9f  lea     ecx, [rdx+1]
0x180013da2  mov     [rbx+24h], ecx
0x180013da5  mov     rbx, [rsp+28h+arg_0]
0x180013daa  mov     [rax+rdx*4+4], edi
0x180013dae  add     rsp, 20h
0x180013db2  pop     rdi
0x180013db3  retn
```
