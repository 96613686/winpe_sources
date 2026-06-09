# CSWbemObjectObjectPath::GetStrVal(ushort * *,ushort *)

- ea: `0x180016ea4`
- end: `0x180016f9d`
- name: `?GetStrVal@CSWbemObjectObjectPath@@AEAAJPEAPEAGPEAG@Z`
- size: `249`
- prototype: `__int64 __fastcall(CSWbemObjectObjectPath *__hidden this, unsigned __int16 **, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180016e90`
- `0x18001fdf0`
- `0x1800201d0`
- `0x1800202f0`
- `0x180020370`

## callees

- `0x1800050dc`
- `0x180006300`
- `0x180016ea4`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180016f57`
- `OLEAUT32!__imp_SysAllocString` at `0x180016f92`
- `OLEAUT32!__imp_SysAllocString` at `0x180016f57`
- `OLEAUT32!__imp_SysAllocString` at `0x180016f92`
- `OLEAUT32!__imp_VariantInit` at `0x180016eef`
- `OLEAUT32!__imp_VariantInit` at `0x180016eef`
- `OLEAUT32!__imp_VariantClear` at `0x180016f2b`
- `OLEAUT32!__imp_VariantClear` at `0x180016f2b`

## pseudocode

```c
__int64 __fastcall CSWbemObjectObjectPath::GetStrVal(
        CSWbemObjectObjectPath *this,
        unsigned __int16 **a2,
        unsigned __int16 *a3)
{
  int v6; // ebx
  const OLECHAR *bstrVal; // rcx
  VARIANTARG pvarg; // [rsp+40h] [rbp-48h] BYREF

  ResetLastErrors();
  if ( !a2 )
  {
    v6 = -2147217400;
    goto LABEL_12;
  }
  *a2 = 0;
  v6 = -2147217407;
  if ( !*((_QWORD *)this + 3) )
  {
LABEL_12:
    CDispatchHelp::RaiseException((CSWbemObjectObjectPath *)((char *)this + 40), v6);
    return (unsigned int)v6;
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( (*(unsigned int (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(**((_QWORD **)this + 3) + 32LL))(
         *((_QWORD *)this + 3),
         a3,
         0,
         &pvarg,
         0,
         0) )
  {
    goto LABEL_4;
  }
  if ( pvarg.vt == 8 )
  {
    bstrVal = pvarg.bstrVal;
LABEL_10:
    *a2 = SysAllocString(bstrVal);
    v6 = 0;
    goto LABEL_4;
  }
  if ( pvarg.vt == 1 )
  {
    bstrVal = &SystemName;
    goto LABEL_10;
  }
LABEL_4:
  VariantClear(&pvarg);
  if ( !*a2 )
    *a2 = SysAllocString(&SystemName);
  if ( v6 < 0 )
    goto LABEL_12;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016ea4  push    rbx
0x180016ea6  push    rbp
0x180016ea7  push    rsi
0x180016ea8  push    rdi
0x180016ea9  sub     rsp, 68h
0x180016ead  mov     rbp, r8
0x180016eb0  mov     rdi, rdx
0x180016eb3  mov     rsi, rcx
0x180016eb6  call    ?ResetLastErrors@@YAXXZ; ResetLastErrors(void)
0x180016ebb  test    rdi, rdi
0x180016ebe  jz      loc_180016F64
0x180016ec4  mov     qword ptr [rdi], 0
0x180016ecb  mov     ebx, 80041001h
0x180016ed0  cmp     qword ptr [rsi+18h], 0
0x180016ed5  jz      loc_180016F69
0x180016edb  xorps   xmm0, xmm0
0x180016ede  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180016ee3  xor     eax, eax
0x180016ee5  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x180016eea  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x180016eef  call    cs:__imp_VariantInit
0x180016ef5  mov     rcx, [rsi+18h]
0x180016ef9  lea     r9, [rsp+88h+pvarg]
0x180016efe  mov     [rsp+88h+var_60], 0
0x180016f07  xor     r8d, r8d
0x180016f0a  mov     rdx, rbp
0x180016f0d  mov     [rsp+88h+var_68], 0
0x180016f16  mov     rax, [rcx]
0x180016f19  mov     rax, [rax+20h]
0x180016f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f22  test    eax, eax
0x180016f24  jz      short loc_180016F46
0x180016f26  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180016f2b  call    cs:__imp_VariantClear
0x180016f31  cmp     qword ptr [rdi], 0
0x180016f35  jz      short loc_180016F8B
0x180016f37  test    ebx, ebx
0x180016f39  js      short loc_180016F69
0x180016f3b  mov     eax, ebx
0x180016f3d  add     rsp, 68h
0x180016f41  pop     rdi
0x180016f42  pop     rsi
0x180016f43  pop     rbp
0x180016f44  pop     rbx
0x180016f45  retn
0x180016f46  mov     eax, 8
0x180016f4b  cmp     ax, word ptr [rsp+88h+pvarg]
0x180016f50  jnz     short loc_180016F76
0x180016f52  mov     rcx, qword ptr [rsp+88h+pvarg+8]; psz
0x180016f57  call    cs:__imp_SysAllocString
0x180016f5d  mov     [rdi], rax
0x180016f60  xor     ebx, ebx
0x180016f62  jmp     short loc_180016F26
0x180016f64  mov     ebx, 80041008h
0x180016f69  lea     rcx, [rsi+28h]; this
0x180016f6d  mov     edx, ebx; int
0x180016f6f  call    ?RaiseException@CDispatchHelp@@QEAAXJ@Z; CDispatchHelp::RaiseException(long)
0x180016f74  jmp     short loc_180016F3B
0x180016f76  mov     eax, 1
0x180016f7b  cmp     ax, word ptr [rsp+88h+pvarg]
0x180016f80  jnz     short loc_180016F26
0x180016f82  lea     rcx, SystemName
0x180016f89  jmp     short loc_180016F57
0x180016f8b  lea     rcx, SystemName; psz
0x180016f92  call    cs:__imp_SysAllocString
0x180016f98  mov     [rdi], rax
0x180016f9b  jmp     short loc_180016F37
```
