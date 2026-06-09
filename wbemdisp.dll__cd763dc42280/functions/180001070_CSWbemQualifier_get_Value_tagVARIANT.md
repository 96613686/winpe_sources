# CSWbemQualifier::get_Value(tagVARIANT *)

- ea: `0x180001070`
- end: `0x180001149`
- name: `?get_Value@CSWbemQualifier@@UEAAJPEAUtagVARIANT@@@Z`
- size: `217`
- prototype: `int(CSWbemQualifier *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180001070`
- `0x1800019a0`
- `0x1800050dc`
- `0x180006300`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800010c0`
- `OLEAUT32!__imp_VariantInit` at `0x1800010c0`
- `OLEAUT32!__imp_VariantClear` at `0x18000109b`
- `OLEAUT32!__imp_VariantClear` at `0x180001112`
- `OLEAUT32!__imp_VariantClear` at `0x18000109b`
- `OLEAUT32!__imp_VariantClear` at `0x180001112`
- `OLEAUT32!__imp_VariantCopy` at `0x180001105`
- `OLEAUT32!__imp_VariantCopy` at `0x180001105`

## pseudocode

```c
__int64 __fastcall CSWbemQualifier::get_Value(CSWbemQualifier *this, struct tagVARIANT *a2)
{
  int v4; // ebx
  HRESULT v5; // eax
  VARIANTARG pvarg; // [rsp+30h] [rbp-28h] BYREF

  ResetLastErrors();
  if ( !a2 )
  {
    v4 = -2147217400;
LABEL_9:
    CDispatchHelp::RaiseException((CSWbemQualifier *)((char *)this + 32), v4);
    return (unsigned int)v4;
  }
  v4 = -2147217407;
  VariantClear(a2);
  if ( !*((_QWORD *)this + 3) )
    goto LABEL_9;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, VARIANTARG *, _QWORD))(**((_QWORD **)this + 3) + 24LL))(
         *((_QWORD *)this + 3),
         *((_QWORD *)this + 14),
         0,
         &pvarg,
         0);
  if ( !v4 )
  {
    if ( (pvarg.vt & 0x2000) != 0 )
      v5 = ConvertArrayRev(a2, &pvarg);
    else
      v5 = VariantCopy(a2, &pvarg);
    v4 = v5;
  }
  VariantClear(&pvarg);
  if ( v4 < 0 )
    goto LABEL_9;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001070  mov     [rsp+arg_0], rbx
0x180001075  mov     [rsp+arg_8], rsi
0x18000107a  push    rdi
0x18000107b  sub     rsp, 50h
0x18000107f  mov     rdi, rdx
0x180001082  mov     rsi, rcx
0x180001085  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x18000108a  test    rdi, rdi
0x18000108d  jz      loc_180001142
0x180001093  mov     rcx, rdi; pvarg
0x180001096  mov     ebx, 80041001h
0x18000109b  call    cs:__imp_VariantClear
0x1800010a1  cmp     qword ptr [rsi+18h], 0
0x1800010a6  jz      loc_18000112E
0x1800010ac  xorps   xmm0, xmm0
0x1800010af  lea     rcx, [rsp+58h+pvarg]; pvarg
0x1800010b4  xor     eax, eax
0x1800010b6  movups  xmmword ptr [rsp+58h+pvarg], xmm0
0x1800010bb  mov     qword ptr [rsp+58h+pvarg+10h], rax
0x1800010c0  call    cs:__imp_VariantInit
0x1800010c6  mov     rcx, [rsi+18h]
0x1800010ca  lea     r9, [rsp+58h+pvarg]
0x1800010cf  mov     rdx, [rsi+70h]
0x1800010d3  xor     r8d, r8d
0x1800010d6  mov     [rsp+58h+var_38], 0
0x1800010df  mov     rax, [rcx]
0x1800010e2  mov     rax, [rax+18h]
0x1800010e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010eb  mov     ebx, eax
0x1800010ed  test    eax, eax
0x1800010ef  jnz     short loc_18000110D
0x1800010f1  mov     eax, 2000h
0x1800010f6  lea     rdx, [rsp+58h+pvarg]; struct tagVARIANT *
0x1800010fb  mov     rcx, rdi; struct tagVARIANT *
0x1800010fe  test    word ptr [rsp+58h+pvarg], ax
0x180001103  jnz     short loc_18000113B
0x180001105  call    cs:__imp_VariantCopy
0x18000110b  mov     ebx, eax
0x18000110d  lea     rcx, [rsp+58h+pvarg]; pvarg
0x180001112  call    cs:__imp_VariantClear
0x180001118  test    ebx, ebx
0x18000111a  js      short loc_18000112E
0x18000111c  mov     rsi, [rsp+58h+arg_8]
0x180001121  mov     eax, ebx
0x180001123  mov     rbx, [rsp+58h+arg_0]
0x180001128  add     rsp, 50h
0x18000112c  pop     rdi
0x18000112d  retn
0x18000112e  lea     rcx, [rsi+20h]; this
0x180001132  mov     edx, ebx; int
0x180001134  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x180001139  jmp     short loc_18000111C
0x18000113b  call    ?ConvertArrayRev@@YAJPEAUtagVARIANT@@0@Z; ConvertArrayRev(tagVARIANT *,tagVARIANT *)
0x180001140  jmp     short loc_18000110B
0x180001142  mov     ebx, 80041008h
0x180001147  jmp     short loc_18000112E
```
