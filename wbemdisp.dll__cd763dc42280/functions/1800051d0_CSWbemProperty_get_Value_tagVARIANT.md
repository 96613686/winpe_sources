# CSWbemProperty::get_Value(tagVARIANT *)

- ea: `0x1800051d0`
- end: `0x1800052c8`
- name: `?get_Value@CSWbemProperty@@UEAAJPEAUtagVARIANT@@@Z`
- size: `248`
- prototype: `int(CSWbemProperty *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x1800019a0`
- `0x1800050dc`
- `0x1800051d0`
- `0x180005bf0`
- `0x180006300`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180005220`
- `OLEAUT32!__imp_VariantInit` at `0x180005220`
- `OLEAUT32!__imp_VariantClear` at `0x1800051fb`
- `OLEAUT32!__imp_VariantClear` at `0x180005291`
- `OLEAUT32!__imp_VariantClear` at `0x1800051fb`
- `OLEAUT32!__imp_VariantClear` at `0x180005291`
- `OLEAUT32!__imp_VariantCopy` at `0x180005284`
- `OLEAUT32!__imp_VariantCopy` at `0x180005284`

## pseudocode

```c
__int64 __fastcall CSWbemProperty::get_Value(CSWbemProperty *this, struct tagVARIANT *a2)
{
  int v4; // ebx
  HRESULT v5; // eax
  VARIANTARG pvarg; // [rsp+40h] [rbp-28h] BYREF

  ResetLastErrors();
  if ( !a2 )
  {
    v4 = -2147217400;
LABEL_9:
    CDispatchHelp::RaiseException((CSWbemProperty *)((char *)this + 48), v4);
    return (unsigned int)v4;
  }
  v4 = -2147217407;
  VariantClear(a2);
  if ( !*((_QWORD *)this + 5) )
    goto LABEL_9;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, VARIANTARG *))(**((_QWORD **)this + 5) + 32LL))(
         *((_QWORD *)this + 5),
         *((_QWORD *)this + 16),
         0,
         &pvarg);
  if ( !v4 )
  {
    MapFromCIMOMObject(
      *((struct CSWbemServices **)this + 3),
      &pvarg,
      *((struct ISWbemInternalObject **)this + 4),
      *((unsigned __int16 **)this + 16),
      0);
    if ( (pvarg.vt & 0x2000) != 0 )
      v5 = ConvertArrayRev(a2, &pvarg);
    else
      v5 = VariantCopy(a2, &pvarg);
    v4 = v5;
    VariantClear(&pvarg);
  }
  if ( v4 < 0 )
    goto LABEL_9;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800051d0  mov     [rsp+arg_0], rbx
0x1800051d5  mov     [rsp+arg_8], rsi
0x1800051da  push    rdi
0x1800051db  sub     rsp, 60h
0x1800051df  mov     rdi, rdx
0x1800051e2  mov     rsi, rcx
0x1800051e5  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x1800051ea  test    rdi, rdi
0x1800051ed  jz      loc_1800052C1
0x1800051f3  mov     rcx, rdi; pvarg
0x1800051f6  mov     ebx, 80041001h
0x1800051fb  call    cs:__imp_VariantClear
0x180005201  cmp     qword ptr [rsi+28h], 0
0x180005206  jz      loc_1800052AD
0x18000520c  xorps   xmm0, xmm0
0x18000520f  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180005214  xor     eax, eax
0x180005216  movups  xmmword ptr [rsp+68h+pvarg], xmm0
0x18000521b  mov     qword ptr [rsp+68h+pvarg+10h], rax
0x180005220  call    cs:__imp_VariantInit
0x180005226  mov     rcx, [rsi+28h]
0x18000522a  lea     r9, [rsp+68h+pvarg]
0x18000522f  xor     edx, edx
0x180005231  xor     r8d, r8d
0x180005234  mov     [rsp+68h+var_40], rdx
0x180005239  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18000523e  mov     rax, [rcx]
0x180005241  mov     rdx, [rsi+80h]
0x180005248  mov     rax, [rax+20h]
0x18000524c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005251  mov     ebx, eax
0x180005253  test    eax, eax
0x180005255  jnz     short loc_180005297
0x180005257  mov     r9, [rsi+80h]; unsigned __int16 *
0x18000525e  lea     rdx, [rsp+68h+pvarg]; struct tagVARIANT *
0x180005263  mov     r8, [rsi+20h]; struct ISWbemInternalObject *
0x180005267  mov     rcx, [rsi+18h]; struct CSWbemServices *
0x18000526b  call    ?MapFromCIMOMObject@@YAJPEAVCSWbemServices@@PEAUtagVARIANT@@PEAUISWbemInternalObject@@PEAGJ@Z; MapFromCIMOMObject(CSWbemServices *,tagVARIANT *,ISWbemInternalObject *,ushort *,long)
0x180005270  mov     eax, 2000h
0x180005275  lea     rdx, [rsp+68h+pvarg]; struct tagVARIANT *
0x18000527a  mov     rcx, rdi; struct tagVARIANT *
0x18000527d  test    word ptr [rsp+68h+pvarg], ax
0x180005282  jnz     short loc_1800052BA
0x180005284  call    cs:__imp_VariantCopy
0x18000528a  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18000528f  mov     ebx, eax
0x180005291  call    cs:__imp_VariantClear
0x180005297  test    ebx, ebx
0x180005299  js      short loc_1800052AD
0x18000529b  mov     rsi, [rsp+68h+arg_8]
0x1800052a0  mov     eax, ebx
0x1800052a2  mov     rbx, [rsp+68h+arg_0]
0x1800052a7  add     rsp, 60h
0x1800052ab  pop     rdi
0x1800052ac  retn
0x1800052ad  lea     rcx, [rsi+30h]; this
0x1800052b1  mov     edx, ebx; int
0x1800052b3  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x1800052b8  jmp     short loc_18000529B
0x1800052ba  call    ?ConvertArrayRev@@YAJPEAUtagVARIANT@@0@Z; ConvertArrayRev(tagVARIANT *,tagVARIANT *)
0x1800052bf  jmp     short loc_18000528A
0x1800052c1  mov     ebx, 80041008h
0x1800052c6  jmp     short loc_1800052AD
```
