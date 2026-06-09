# ATL::CAxHostWindow::put_OptionKeyPath(ushort *)

- ea: `0x140009650`
- end: `0x1400096c5`
- name: `?put_OptionKeyPath@CAxHostWindow@ATL@@UEAAJPEAG@Z`
- size: `117`
- prototype: `int(ATL::CAxHostWindow *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140009650`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140009670`
- `OLEAUT32!__imp_SysAllocString` at `0x140009670`
- `OLEAUT32!__imp_SysFreeString` at `0x140009667`
- `OLEAUT32!__imp_SysFreeString` at `0x140009667`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::put_OptionKeyPath(BSTR *this, unsigned __int16 *a2)
{
  BSTR v4; // rax
  bool v5; // al
  char *v6; // rdi
  int v7; // edx
  int v8; // ecx

  SysFreeString(this[24]);
  v4 = SysAllocString(a2);
  this[24] = v4;
  if ( !a2 )
  {
    if ( !v4 )
    {
      v5 = 1;
      return !v5 ? 0x8007000E : 0;
    }
LABEL_9:
    v5 = 0;
    return !v5 ? 0x8007000E : 0;
  }
  if ( !v4 )
    goto LABEL_9;
  v6 = (char *)((char *)a2 - (char *)v4);
  do
  {
    v7 = *(unsigned __int16 *)&v6[(_QWORD)v4];
    v8 = *v4 - v7;
    if ( v8 )
      break;
    ++v4;
  }
  while ( v7 );
  v5 = v8 == 0;
  return !v5 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x140009650  mov     [rsp+arg_0], rbx
0x140009655  push    rdi
0x140009656  sub     rsp, 20h
0x14000965a  mov     rbx, rcx
0x14000965d  mov     rdi, rdx
0x140009660  mov     rcx, [rcx+0C0h]; bstrString
0x140009667  call    cs:__imp_SysFreeString
0x14000966d  mov     rcx, rdi; psz
0x140009670  call    cs:__imp_SysAllocString
0x140009676  mov     [rbx+0C0h], rax
0x14000967d  test    rdi, rdi
0x140009680  jnz     short loc_14000968B
0x140009682  test    rax, rax
0x140009685  jnz     short loc_1400096AD
0x140009687  mov     al, 1
0x140009689  jmp     short loc_1400096AF
0x14000968b  test    rax, rax
0x14000968e  jz      short loc_1400096AD
0x140009690  sub     rdi, rax
0x140009693  movzx   ecx, word ptr [rax]
0x140009696  movzx   edx, word ptr [rax+rdi]
0x14000969a  sub     ecx, edx
0x14000969c  jnz     short loc_1400096A6
0x14000969e  add     rax, 2
0x1400096a2  test    edx, edx
0x1400096a4  jnz     short loc_140009693
0x1400096a6  test    ecx, ecx
0x1400096a8  setz    al
0x1400096ab  jmp     short loc_1400096AF
0x1400096ad  xor     al, al
0x1400096af  mov     rbx, [rsp+28h+arg_0]
0x1400096b4  neg     al
0x1400096b6  sbb     eax, eax
0x1400096b8  not     eax
0x1400096ba  and     eax, 8007000Eh
0x1400096bf  add     rsp, 20h
0x1400096c3  pop     rdi
0x1400096c4  retn
```
