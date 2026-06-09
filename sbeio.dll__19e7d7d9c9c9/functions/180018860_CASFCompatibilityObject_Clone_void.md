# CASFCompatibilityObject::Clone(void)

- ea: `0x180018860`
- end: `0x1800188c2`
- name: `?Clone@CASFCompatibilityObject@@UEAAPEAVCASFLonghandObject@@XZ`
- size: `98`
- prototype: `struct CASFLonghandObject *__fastcall(CASFCompatibilityObject *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011a0`
- `0x180018860`

## pseudocode

```c
struct CASFLonghandObject *__fastcall CASFCompatibilityObject::Clone(CASFCompatibilityObject *this)
{
  _QWORD *v2; // rdx
  struct CASFLonghandObject *result; // rax

  v2 = operator new(0x40u);
  result = 0;
  if ( v2 )
  {
    v2[5] = 0;
    *v2 = &CASFCompatibilityObject::`vftable';
    v2[1] = 100;
    v2[6] = 1;
    *((_WORD *)v2 + 28) = 258;
    *((GUID *)v2 + 1) = CLSID_CAsfCompatibilityObject;
    *((_BYTE *)v2 + 56) = *((_BYTE *)this + 56);
    *((_BYTE *)v2 + 57) = *((_BYTE *)this + 57);
    return (struct CASFLonghandObject *)v2;
  }
  return result;
}

```

## disassembly

```asm
0x180018860  push    rbx
0x180018862  sub     rsp, 20h
0x180018866  mov     rbx, rcx
0x180018869  mov     ecx, 40h ; '@'; Size
0x18001886e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018873  mov     rdx, rax
0x180018876  xor     eax, eax
0x180018878  test    rdx, rdx
0x18001887b  jz      short loc_1800188BC
0x18001887d  mov     [rdx+28h], rax
0x180018881  lea     rax, ??_7CASFCompatibilityObject@@6B@; const CASFCompatibilityObject::`vftable'
0x180018888  mov     [rdx], rax
0x18001888b  mov     qword ptr [rdx+8], 64h ; 'd'
0x180018893  mov     qword ptr [rdx+30h], 1
0x18001889b  movups  xmm0, xmmword ptr cs:CLSID_CAsfCompatibilityObject.Data1
0x1800188a2  mov     word ptr [rdx+38h], 102h
0x1800188a8  movdqu  xmmword ptr [rdx+10h], xmm0
0x1800188ad  mov     al, [rbx+38h]
0x1800188b0  mov     [rdx+38h], al
0x1800188b3  mov     al, [rbx+39h]
0x1800188b6  mov     [rdx+39h], al
0x1800188b9  mov     rax, rdx
0x1800188bc  add     rsp, 20h
0x1800188c0  pop     rbx
0x1800188c1  retn
```
