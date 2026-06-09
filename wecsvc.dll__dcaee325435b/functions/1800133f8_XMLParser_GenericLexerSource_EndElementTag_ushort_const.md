# XMLParser<GenericLexerSource>::EndElementTag(ushort const *)

- ea: `0x1800133f8`
- end: `0x18001344a`
- name: `?EndElementTag@?$XMLParser@VGenericLexerSource@@@@AEAAXPEBG@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013a0c`

## callees

- `0x18000195c`
- `0x180013310`
- `0x1800133f8`
- `0x1800134f8`

## pseudocode

```c
__int64 __fastcall XMLParser<GenericLexerSource>::EndElementTag(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  int *v3; // r11
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rcx
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

  result = 0;
  v3 = (int *)(a1 + 44);
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(a2 + 2 * v4) );
    result = XMLParser<GenericLexerSource>::HashStringCaseSensitive();
    v5 = *v3;
    if ( (_DWORD)result != *(_DWORD *)(*(_QWORD *)(v6 + 32) + 4 * v5) )
    {
      wmi::GenericException::GenericException((wmi::GenericException *)pExceptionObject, v5);
      throw (wmi::GenericException *)pExceptionObject;
    }
  }
  --*v3;
  return result;
}

```

## disassembly

```asm
0x1800133f8  sub     rsp, 68h
0x1800133fc  xor     eax, eax
0x1800133fe  lea     r11, [rcx+2Ch]
0x180013402  test    rdx, rdx
0x180013405  jz      short loc_180013426
0x180013407  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001340b  inc     r8
0x18001340e  cmp     [rdx+r8*2], ax
0x180013413  jnz     short loc_18001340B
0x180013415  call    ?HashStringCaseSensitive@?$XMLParser@VGenericLexerSource@@@@AEAAKPEBGK@Z; XMLParser<GenericLexerSource>::HashStringCaseSensitive(ushort const *,ulong)
0x18001341a  movsxd  rdx, dword ptr [r11]; unsigned int
0x18001341d  mov     rcx, [rcx+20h]
0x180013421  cmp     eax, [rcx+rdx*4]
0x180013424  jnz     short loc_18001342E
0x180013426  dec     dword ptr [r11]
0x180013429  add     rsp, 68h
0x18001342d  retn
0x18001342e  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180013433  call    ??0GenericException@wmi@@QEAA@K@Z; wmi::GenericException::GenericException(ulong)
0x180013438  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001343f  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180013444  call    _CxxThrowException_0
```
