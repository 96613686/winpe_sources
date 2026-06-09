# CleanupDeserializedRequest(tagUPNP_CONTROL_REQUEST *)

- ea: `0x180003960`
- end: `0x1800039cd`
- name: `?CleanupDeserializedRequest@@YAXPEAUtagUPNP_CONTROL_REQUEST@@@Z`
- size: `109`
- prototype: `void __fastcall(struct tagUPNP_CONTROL_REQUEST *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004c94`
- `0x18000512c`

## callees

- `0x180003960`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800039ad`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800039ad`
- `OLEAUT32!__imp_SysFreeString` at `0x180003975`
- `OLEAUT32!__imp_SysFreeString` at `0x180003975`
- `OLEAUT32!__imp_VariantClear` at `0x18000399c`
- `OLEAUT32!__imp_VariantClear` at `0x18000399c`

## pseudocode

```c
void __fastcall CleanupDeserializedRequest(struct tagUPNP_CONTROL_REQUEST *a1)
{
  OLECHAR *v2; // rcx
  __int64 i; // rdi

  v2 = *(OLECHAR **)a1;
  if ( v2 )
  {
    SysFreeString(v2);
    *(_QWORD *)a1 = 0;
  }
  if ( *((_QWORD *)a1 + 2) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 2); i = (unsigned int)(i + 1) )
      VariantClear((VARIANTARG *)(*((_QWORD *)a1 + 2) + 24 * i));
    free(*((void **)a1 + 2));
    *((_QWORD *)a1 + 2) = 0;
    *((_DWORD *)a1 + 2) = 0;
  }
}

```

## disassembly

```asm
0x180003960  mov     [rsp+arg_0], rbx
0x180003965  push    rdi
0x180003966  sub     rsp, 20h
0x18000396a  mov     rbx, rcx
0x18000396d  mov     rcx, [rcx]; bstrString
0x180003970  test    rcx, rcx
0x180003973  jz      short loc_180003982
0x180003975  call    cs:__imp_SysFreeString
0x18000397b  mov     qword ptr [rbx], 0
0x180003982  cmp     qword ptr [rbx+10h], 0
0x180003987  jz      short loc_1800039C2
0x180003989  xor     edi, edi
0x18000398b  cmp     [rbx+8], edi
0x18000398e  jbe     short loc_1800039A9
0x180003990  mov     rax, [rbx+10h]
0x180003994  lea     rcx, [rdi+rdi*2]
0x180003998  lea     rcx, [rax+rcx*8]; pvarg
0x18000399c  call    cs:__imp_VariantClear
0x1800039a2  inc     edi
0x1800039a4  cmp     edi, [rbx+8]
0x1800039a7  jb      short loc_180003990
0x1800039a9  mov     rcx, [rbx+10h]; Block
0x1800039ad  call    cs:__imp_free
0x1800039b3  mov     qword ptr [rbx+10h], 0
0x1800039bb  mov     dword ptr [rbx+8], 0
0x1800039c2  mov     rbx, [rsp+28h+arg_0]
0x1800039c7  add     rsp, 20h
0x1800039cb  pop     rdi
0x1800039cc  retn
```
