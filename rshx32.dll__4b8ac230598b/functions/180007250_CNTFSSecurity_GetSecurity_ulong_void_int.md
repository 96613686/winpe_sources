# CNTFSSecurity::GetSecurity(ulong,void * *,int)

- ea: `0x180007250`
- end: `0x180007294`
- name: `?GetSecurity@CNTFSSecurity@@UEAAJKPEAPEAXH@Z`
- size: `68`
- prototype: `__int64 __fastcall(CNTFSSecurity *__hidden this, unsigned int, void **, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007250`
- `0x18000c230`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::GetSecurity(CNTFSSecurity *this, unsigned int a2, void **a3, int a4)
{
  if ( !a3 )
    return 2147500035LL;
  if ( !a2 )
    return 2147942487LL;
  *a3 = 0;
  if ( a4 )
    return 2147500033LL;
  else
    return CSecurityInformation::GetSecurity(this, a2, a3, 0);
}

```

## disassembly

```asm
0x180007250  sub     rsp, 28h
0x180007254  test    r8, r8
0x180007257  jnz     short loc_180007263
0x180007259  mov     eax, 80004003h
0x18000725e  add     rsp, 28h
0x180007262  retn
0x180007263  test    edx, edx
0x180007265  jnz     short loc_180007271
0x180007267  mov     eax, 80070057h
0x18000726c  add     rsp, 28h
0x180007270  retn
0x180007271  mov     qword ptr [r8], 0
0x180007278  test    r9d, r9d
0x18000727b  jz      short loc_180007287
0x18000727d  mov     eax, 80004001h
0x180007282  add     rsp, 28h
0x180007286  retn
0x180007287  xor     r9d, r9d; int
0x18000728a  call    ?GetSecurity@CSecurityInformation@@UEAAJKPEAPEAXH@Z; CSecurityInformation::GetSecurity(ulong,void * *,int)
0x18000728f  add     rsp, 28h
0x180007293  retn
```
