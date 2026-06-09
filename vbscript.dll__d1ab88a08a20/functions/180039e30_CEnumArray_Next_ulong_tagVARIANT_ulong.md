# CEnumArray::Next(ulong,tagVARIANT *,ulong *)

- ea: `0x180039e30`
- end: `0x180039ea7`
- name: `?Next@CEnumArray@@UEAAJKPEAUtagVARIANT@@PEAK@Z`
- size: `119`
- prototype: `HRESULT __fastcall(CEnumArray *this, unsigned int, struct tagVARIANT *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180039e30`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180039e6f`
- `OLEAUT32!__imp_VariantCopy` at `0x180039e6f`

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
0x180039e30  push    rbx
0x180039e32  push    rbp
0x180039e33  push    rsi
0x180039e34  push    rdi
0x180039e35  push    r14
0x180039e37  sub     rsp, 20h
0x180039e3b  xor     ebx, ebx
0x180039e3d  mov     rsi, r9
0x180039e40  mov     rbp, r8
0x180039e43  mov     r14d, edx
0x180039e46  mov     rdi, rcx
0x180039e49  cmp     [rcx+10h], rbx
0x180039e4d  jz      short loc_180039E8A
0x180039e4f  cmp     ebx, r14d
0x180039e52  jnb     short loc_180039E8A
0x180039e54  mov     eax, [rdi+30h]
0x180039e57  cmp     [rdi+34h], eax
0x180039e5a  jbe     short loc_180039E8A
0x180039e5c  lea     rdx, [rax+rax*2]
0x180039e60  mov     rax, [rdi+10h]
0x180039e64  mov     rcx, [rax+10h]
0x180039e68  lea     rdx, [rcx+rdx*8]; pvargSrc
0x180039e6c  mov     rcx, rbp; pvargDest
0x180039e6f  call    cs:__imp_VariantCopy
0x180039e76  nop     dword ptr [rax+rax+00h]
0x180039e7b  test    eax, eax
0x180039e7d  js      short loc_180039E97
0x180039e7f  inc     dword ptr [rdi+30h]
0x180039e82  add     rbp, 18h
0x180039e86  inc     ebx
0x180039e88  jmp     short loc_180039E4F
0x180039e8a  test    rsi, rsi
0x180039e8d  jnz     short loc_180039EA3
0x180039e8f  xor     eax, eax
0x180039e91  cmp     r14d, ebx
0x180039e94  setnz   al
0x180039e97  add     rsp, 20h
0x180039e9b  pop     r14
0x180039e9d  pop     rdi
0x180039e9e  pop     rsi
0x180039e9f  pop     rbp
0x180039ea0  pop     rbx
0x180039ea1  retn
0x180039ea3  mov     [rsi], ebx
0x180039ea5  jmp     short loc_180039E8F
```
