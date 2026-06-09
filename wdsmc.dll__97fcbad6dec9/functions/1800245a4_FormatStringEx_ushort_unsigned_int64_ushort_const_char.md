# FormatStringEx(ushort * *,unsigned __int64,ushort const *,char *)

- ea: `0x1800245a4`
- end: `0x180024757`
- name: `?FormatStringEx@@YAKPEAPEAG_KPEBGPEAD@Z`
- size: `435`
- prototype: `unsigned int(unsigned __int16 **, unsigned __int64, const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180024760`

## callees

- `0x18001a9a8`
- `0x1800245a4`
- `0x180025914`
- `0x1800259d8`
- `0x180026694`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18002463a`
- `msvcrt!_vsnwprintf` at `0x18002463a`

## string_xrefs

- `0x18002467c`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`
- `0x1800246ab`: `onecore\base\eco\wds\wdslib\common\src\strutil.cpp`

## pseudocode

```c
__int64 __fastcall FormatStringEx(unsigned __int16 **a1, unsigned __int64 a2, const unsigned __int16 *a3, va_list a4)
{
  unsigned __int64 v4; // r14
  unsigned int v7; // esi
  unsigned __int64 v8; // rax
  const char *v9; // rdx
  wchar_t *v10; // rdi
  int v11; // ebx
  unsigned __int64 v12; // r15
  unsigned __int64 v13; // rbp
  int v14; // eax
  const char *v15; // rdx
  const char *v16; // r8
  unsigned int v17; // r9d
  unsigned __int64 v18; // rbp
  __int64 v19; // rax
  unsigned __int64 v20; // rcx
  const char *v21; // rdx
  const char *v22; // r8
  unsigned int v23; // r9d
  int v24; // eax

  v4 = a2;
  if ( !a2 )
    v4 = 256;
  v7 = 0;
  while ( 1 )
  {
    v8 = 2 * v4;
    if ( !is_mul_ok(v4, 2u) )
      v8 = -1;
    v10 = (wchar_t *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v10 )
      break;
    v11 = 0;
    v12 = v4;
    if ( v4 - 1 > 0x7FFFFFFE )
      v11 = -2147024809;
    if ( v11 < 0 )
    {
      if ( v4 )
        *v10 = 0;
    }
    else
    {
      v11 = 0;
      v13 = v4 - 1;
      v14 = _vsnwprintf(v10, v4 - 1, a3, a4);
      if ( v14 < 0 || v14 > v13 )
      {
        v11 = -2147024774;
      }
      else if ( v14 != v13 )
      {
        goto LABEL_19;
      }
      v10[v13] = 0;
    }
LABEL_19:
    if ( !v11 )
    {
      *a1 = v10;
      return v7;
    }
    if ( v11 != -2147024774 )
    {
      ElValidateHrLite(v11, v9, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp", 0x94Au);
      if ( (int)ElValidateHr(v11, v15, v16, v17) < 0 )
        goto LABEL_32;
    }
    v18 = v4 + 256;
    v19 = -1;
    v20 = v4;
    if ( v4 + 256 >= v4 )
      v19 = v4 + 256;
    v4 = v19;
    v11 = v18 < v20 ? 0x80070216 : 0;
    ElValidateHrLite(v11, v9, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\strutil.cpp", 0x94Eu);
    if ( v18 >= v12 )
      v24 = v11;
    else
      v24 = ElValidateHr(v11, v21, v22, v23);
    if ( v24 < 0 )
    {
      if ( v18 < v12 )
      {
LABEL_32:
        if ( (v11 & 0x1FFF0000) == 0x70000 )
        {
          v7 = (unsigned __int16)v11;
          goto LABEL_36;
        }
      }
      v7 = v11;
      goto LABEL_36;
    }
    operator delete(v10);
  }
  v7 = 8;
LABEL_36:
  if ( v10 )
    operator delete(v10);
  return v7;
}

```

## disassembly

```asm
0x1800245a4  mov     rax, rsp
0x1800245a7  mov     [rax+8], rbx
0x1800245ab  mov     [rax+10h], rbp
0x1800245af  mov     [rax+20h], rsi
0x1800245b3  mov     [rax+18h], r8
0x1800245b7  push    rdi
0x1800245b8  push    r12
0x1800245ba  push    r13
0x1800245bc  push    r14
0x1800245be  push    r15
0x1800245c0  sub     rsp, 20h
0x1800245c4  xor     ebp, ebp
0x1800245c6  mov     r14, rdx
0x1800245c9  test    rdx, rdx
0x1800245cc  mov     eax, 100h
0x1800245d1  mov     r13, r9
0x1800245d4  mov     r12, rcx
0x1800245d7  cmovz   r14, rax
0x1800245db  mov     esi, ebp
0x1800245dd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800245e4  mov     eax, 2
0x1800245e9  mul     r14
0x1800245ec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800245f3  cmovo   rax, rcx
0x1800245f7  mov     rcx, rax; unsigned __int64
0x1800245fa  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800245ff  mov     rdi, rax
0x180024602  test    rax, rax
0x180024605  jz      loc_180024726
0x18002460b  lea     rax, [r14-1]
0x18002460f  mov     ebx, ebp
0x180024611  cmp     rax, 7FFFFFFEh
0x180024617  mov     ecx, 80070057h
0x18002461c  mov     r15, r14
0x18002461f  cmova   ebx, ecx
0x180024622  test    ebx, ebx
0x180024624  js      short loc_18002465E
0x180024626  mov     r8, [rsp+48h+Format]; Format
0x18002462b  mov     ebx, ebp
0x18002462d  lea     rbp, [r14-1]
0x180024631  mov     r9, r13; Args
0x180024634  mov     rdx, rbp; BufferCount
0x180024637  mov     rcx, rdi; Buffer
0x18002463a  call    cs:__imp__vsnwprintf
0x180024640  xor     ecx, ecx
0x180024642  test    eax, eax
0x180024644  js      short loc_180024651
0x180024646  cdqe
0x180024648  cmp     rax, rbp
0x18002464b  ja      short loc_180024651
0x18002464d  jnz     short loc_18002465A
0x18002464f  jmp     short loc_180024656
0x180024651  mov     ebx, 8007007Ah
0x180024656  mov     [rdi+rbp*2], cx
0x18002465a  xor     ebp, ebp
0x18002465c  jmp     short loc_180024666
0x18002465e  test    r14, r14
0x180024661  jz      short loc_180024666
0x180024663  mov     [rdi], bp
0x180024666  test    ebx, ebx
0x180024668  jz      loc_180024720
0x18002466e  cmp     ebx, 8007007Ah
0x180024674  jz      short loc_18002469D
0x180024676  mov     r9d, 94Ah; unsigned int
0x18002467c  lea     r8, aOnecoreBaseEco_5; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180024683  mov     ecx, ebx; int
0x180024685  call    ?ElValidateHrLite@@YAJJPEBD0K@Z; ElValidateHrLite(long,char const *,char const *,ulong)
0x18002468a  test    ebx, ebx
0x18002468c  jns     short loc_180024697
0x18002468e  mov     ecx, ebx; int
0x180024690  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180024695  jmp     short loc_180024699
0x180024697  mov     eax, ebx
0x180024699  test    eax, eax
0x18002469b  js      short loc_180024700
0x18002469d  lea     rbp, [r14+100h]
0x1800246a4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800246a8  mov     rcx, r14
0x1800246ab  lea     r8, aOnecoreBaseEco_5; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800246b2  cmp     rbp, r14
0x1800246b5  mov     r9d, 94Eh; unsigned int
0x1800246bb  cmovnb  rax, rbp
0x1800246bf  cmp     rbp, rcx
0x1800246c2  mov     r14, rax
0x1800246c5  sbb     ebx, ebx
0x1800246c7  and     ebx, 80070216h
0x1800246cd  mov     ecx, ebx; int
0x1800246cf  call    ?ElValidateHrLite@@YAJJPEBD0K@Z; ElValidateHrLite(long,char const *,char const *,ulong)
0x1800246d4  cmp     rbp, r15
0x1800246d7  jnb     short loc_1800246E2
0x1800246d9  mov     ecx, ebx; int
0x1800246db  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800246e0  jmp     short loc_1800246E4
0x1800246e2  mov     eax, ebx
0x1800246e4  test    eax, eax
0x1800246e6  js      short loc_180024708
0x1800246e8  xor     ebp, ebp
0x1800246ea  test    rdi, rdi
0x1800246ed  jz      loc_1800245DD
0x1800246f3  mov     rcx, rdi; void *
0x1800246f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800246fb  jmp     loc_1800245DD
0x180024700  test    ebx, ebx
0x180024702  js      short loc_18002470D
0x180024704  mov     esi, ebx
0x180024706  jmp     short loc_18002472B
0x180024708  cmp     rbp, r15
0x18002470b  jnb     short loc_180024704
0x18002470d  mov     eax, ebx
0x18002470f  and     eax, 1FFF0000h
0x180024714  cmp     eax, 70000h
0x180024719  jnz     short loc_180024704
0x18002471b  movzx   esi, bx
0x18002471e  jmp     short loc_18002472B
0x180024720  mov     [r12], rdi
0x180024724  jmp     short loc_180024738
0x180024726  mov     esi, 8
0x18002472b  test    rdi, rdi
0x18002472e  jz      short loc_180024738
0x180024730  mov     rcx, rdi; void *
0x180024733  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024738  mov     rbx, [rsp+48h+arg_0]
0x18002473d  mov     eax, esi
0x18002473f  mov     rsi, [rsp+48h+arg_18]
0x180024744  mov     rbp, [rsp+48h+arg_8]
0x180024749  add     rsp, 20h
0x18002474d  pop     r15
0x18002474f  pop     r14
0x180024751  pop     r13
0x180024753  pop     r12
0x180024755  pop     rdi
0x180024756  retn
```
