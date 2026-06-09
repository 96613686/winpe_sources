# CSafeArray::SetRawData(void *,int,int)

- ea: `0x180026000`
- end: `0x180026081`
- name: `?SetRawData@CSafeArray@@QEAAHPEAXHH@Z`
- size: `129`
- prototype: `int(CSafeArray *__hidden this, void *, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180026000`
- `0x18002ee96`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002603a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002603a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180026064`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180026064`

## pseudocode

```c
__int64 __fastcall CSafeArray::SetRawData(CSafeArray *this, void *a2, int a3, int a4)
{
  SAFEARRAY *v8; // rcx
  HRESULT v9; // ebx
  void *ppvData; // [rsp+20h] [rbp-38h] BYREF

  if ( a3 < 0 || (unsigned int)a3 > *((_DWORD *)this + 6) || a4 != *((_DWORD *)this + 5) )
    return 1;
  v8 = (SAFEARRAY *)*((_QWORD *)this + 4);
  ppvData = 0;
  v9 = SafeArrayAccessData(v8, &ppvData);
  if ( v9 >= 0 )
  {
    memcpy_0(ppvData, a2, a4 * a3);
    *(_DWORD *)this = a3 - 1;
    SafeArrayUnaccessData(*((SAFEARRAY **)this + 4));
  }
  return (unsigned int)v9 >> 31;
}

```

## disassembly

```asm
0x180026000  push    rbx
0x180026002  push    rbp
0x180026003  push    rsi
0x180026004  push    rdi
0x180026005  push    r14
0x180026007  sub     rsp, 30h
0x18002600b  mov     ebp, r9d
0x18002600e  mov     esi, r8d
0x180026011  mov     r14, rdx
0x180026014  mov     rdi, rcx
0x180026017  test    r8d, r8d
0x18002601a  js      short loc_18002607A
0x18002601c  cmp     r8d, [rcx+18h]
0x180026020  ja      short loc_18002607A
0x180026022  cmp     r9d, [rcx+14h]
0x180026026  jnz     short loc_18002607A
0x180026028  mov     rcx, [rcx+20h]; psa
0x18002602c  lea     rdx, [rsp+58h+ppvData]; ppvData
0x180026031  mov     [rsp+58h+ppvData], 0
0x18002603a  call    cs:__imp_SafeArrayAccessData
0x180026040  mov     ebx, eax
0x180026042  test    eax, eax
0x180026044  js      short loc_18002606A
0x180026046  mov     ecx, esi
0x180026048  mov     rdx, r14; Src
0x18002604b  imul    ecx, ebp
0x18002604e  movsxd  r8, ecx; Size
0x180026051  mov     rcx, [rsp+58h+ppvData]; void *
0x180026056  call    memcpy_0
0x18002605b  lea     ecx, [rsi-1]
0x18002605e  mov     [rdi], ecx
0x180026060  mov     rcx, [rdi+20h]; psa
0x180026064  call    cs:__imp_SafeArrayUnaccessData
0x18002606a  shr     ebx, 1Fh
0x18002606d  mov     eax, ebx
0x18002606f  add     rsp, 30h
0x180026073  pop     r14
0x180026075  pop     rdi
0x180026076  pop     rsi
0x180026077  pop     rbp
0x180026078  pop     rbx
0x180026079  retn
0x18002607a  mov     eax, 1
0x18002607f  jmp     short loc_18002606F
```
