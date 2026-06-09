# CEnumArray::Next(ulong,tagVARIANT *,ulong *)

- ea: `0x1800380d0`
- end: `0x180038140`
- name: `?Next@CEnumArray@@UEAAJKPEAUtagVARIANT@@PEAK@Z`
- size: `112`
- prototype: `HRESULT __fastcall(CEnumArray *this, unsigned int, struct tagVARIANT *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800380d0`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18003810f`
- `OLEAUT32!__imp_VariantCopy` at `0x18003810f`

## pseudocode

```c
HRESULT __fastcall CEnumArray::Next(CEnumArray *this, unsigned int a2, struct tagVARIANT *a3, unsigned int *a4)
{
  unsigned int v4; // ebx
  __int64 v9; // rax
  HRESULT result; // eax

  v4 = 0;
  if ( *((_QWORD *)this + 2) )
  {
    while ( v4 < a2 )
    {
      v9 = *((unsigned int *)this + 12);
      if ( *((_DWORD *)this + 13) <= (unsigned int)v9 )
        break;
      result = VariantCopy(a3, (const VARIANTARG *)(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL) + 24 * v9));
      if ( result < 0 )
        return result;
      ++*((_DWORD *)this + 12);
      ++a3;
      ++v4;
    }
  }
  if ( a4 )
    *a4 = v4;
  return a2 != v4;
}

```

## disassembly

```asm
0x1800380d0  push    rbx
0x1800380d2  push    rbp
0x1800380d3  push    rsi
0x1800380d4  push    rdi
0x1800380d5  push    r14
0x1800380d7  sub     rsp, 20h
0x1800380db  xor     ebx, ebx
0x1800380dd  mov     rsi, r9
0x1800380e0  mov     rbp, r8
0x1800380e3  mov     r14d, edx
0x1800380e6  mov     rdi, rcx
0x1800380e9  cmp     [rcx+10h], rbx
0x1800380ed  jz      short loc_180038124
0x1800380ef  cmp     ebx, r14d
0x1800380f2  jnb     short loc_180038124
0x1800380f4  mov     eax, [rdi+30h]
0x1800380f7  cmp     [rdi+34h], eax
0x1800380fa  jbe     short loc_180038124
0x1800380fc  lea     rdx, [rax+rax*2]
0x180038100  mov     rax, [rdi+10h]
0x180038104  mov     rcx, [rax+10h]
0x180038108  lea     rdx, [rcx+rdx*8]; pvargSrc
0x18003810c  mov     rcx, rbp; pvargDest
0x18003810f  call    cs:__imp_VariantCopy
0x180038115  test    eax, eax
0x180038117  js      short loc_180038131
0x180038119  inc     dword ptr [rdi+30h]
0x18003811c  add     rbp, 18h
0x180038120  inc     ebx
0x180038122  jmp     short loc_1800380EF
0x180038124  test    rsi, rsi
0x180038127  jnz     short loc_18003813C
0x180038129  xor     eax, eax
0x18003812b  cmp     r14d, ebx
0x18003812e  setnz   al
0x180038131  add     rsp, 20h
0x180038135  pop     r14
0x180038137  pop     rdi
0x180038138  pop     rsi
0x180038139  pop     rbp
0x18003813a  pop     rbx
0x18003813b  retn
0x18003813c  mov     [rsi], ebx
0x18003813e  jmp     short loc_180038129
```
