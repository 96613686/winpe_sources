# ReallocSPWORDPRONList(SPWORDPRONUNCIATIONLIST *,ulong)

- ea: `0x1800b113c`
- end: `0x1800b1193`
- name: `?ReallocSPWORDPRONList@@YAJPEAUSPWORDPRONUNCIATIONLIST@@K@Z`
- size: `87`
- prototype: `int(struct SPWORDPRONUNCIATIONLIST *, unsigned int)`
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b002c`
- `0x1800cbb38`
- `0x1800cea74`
- `0x1800ceeb0`
- `0x1800d09e0`
- `0x1800db960`
- `0x1800dbb28`
- `0x1800fd300`

## callees

- `0x1800b113c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800b115f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800b115f`

## pseudocode

```c
__int64 __fastcall ReallocSPWORDPRONList(struct SPWORDPRONUNCIATIONLIST *a1, ULONG a2)
{
  unsigned int v2; // edi
  BYTE *v5; // rax

  v2 = 0;
  if ( a1->ulSize >= a2 )
  {
    a1->pFirstWordPronunciation = (SPWORDPRONUNCIATION *)a1->pvBuffer;
  }
  else
  {
    v5 = (BYTE *)CoTaskMemRealloc(a1->pvBuffer, a2);
    if ( v5 )
    {
      a1->pvBuffer = v5;
      a1->pFirstWordPronunciation = (SPWORDPRONUNCIATION *)v5;
      a1->ulSize = a2;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800b113c  mov     [rsp+arg_0], rbx
0x1800b1141  mov     [rsp+arg_8], rsi
0x1800b1146  push    rdi
0x1800b1147  sub     rsp, 20h
0x1800b114b  mov     rax, [rcx+8]
0x1800b114f  xor     edi, edi
0x1800b1151  mov     rbx, rcx
0x1800b1154  mov     esi, edx
0x1800b1156  cmp     [rcx], edx
0x1800b1158  jnb     short loc_1800B117D
0x1800b115a  mov     edx, esi; cb
0x1800b115c  mov     rcx, rax; pv
0x1800b115f  call    cs:__imp_CoTaskMemRealloc
0x1800b1165  test    rax, rax
0x1800b1168  jnz     short loc_1800B1171
0x1800b116a  mov     edi, 8007000Eh
0x1800b116f  jmp     short loc_1800B1181
0x1800b1171  mov     [rbx+8], rax
0x1800b1175  mov     [rbx+10h], rax
0x1800b1179  mov     [rbx], esi
0x1800b117b  jmp     short loc_1800B1181
0x1800b117d  mov     [rcx+10h], rax
0x1800b1181  mov     rbx, [rsp+28h+arg_0]
0x1800b1186  mov     eax, edi
0x1800b1188  mov     rsi, [rsp+28h+arg_8]
0x1800b118d  add     rsp, 20h
0x1800b1191  pop     rdi
0x1800b1192  retn
```
