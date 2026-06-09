# CRowsetProps::IsValidValue(ulong,tagDBPROP *)

- ea: `0x383853650`
- end: `0x3838536c0`
- name: `?IsValidValue@CRowsetProps@@EEAAJKPEAUtagDBPROP@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(CRowsetProps *__hidden this, unsigned int, struct tagDBPROP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x383853650`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x3838e75ea`
- `OLEAUT32!__imp_SysStringLen` at `0x3838e75ea`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x3838e7635`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x3838e7635`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x3838e7642`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x3838e7642`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x3838e766b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x3838e766b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x3838e7657`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x3838e7657`

## pseudocode

```c
_BOOL8 __fastcall CRowsetProps::IsValidValue(CRowsetProps *this, int a2, struct tagDBPROP *a3)
{
  VARTYPE vt; // r9
  SHORT iVal; // ax
  _BOOL8 result; // rax
  LONG lVal; // eax
  int v7; // edx
  int v8; // edx
  bool v9; // zf
  unsigned int Lo; // eax
  SAFEARRAY *parray; // rdi
  LONG v12; // eax
  LONG plUbound; // [rsp+40h] [rbp+18h] BYREF
  LONG plLbound; // [rsp+48h] [rbp+20h] BYREF

  vt = a3->vValue.vt;
  plLbound = 0;
  plUbound = 0;
  if ( vt == 11 )
  {
    iVal = a3->vValue.iVal;
    if ( iVal != -1 )
    {
      if ( iVal )
        return 1;
    }
  }
  if ( !a2 )
  {
    switch ( a3->dwPropertyID )
    {
      case 0x22u:
        if ( vt != 3 )
          return 1;
        lVal = a3->vValue.lVal;
        if ( lVal < 0 )
          return 1;
        return lVal > 65534;
      case 0x49u:
      case 0x4Eu:
        if ( vt != 3 )
          return 1;
        return a3->vValue.lVal < 0;
      case 0x75u:
        return vt != 3 || (a3->vValue.lVal & 7) != a3->vValue.lVal;
      case 0xC6u:
      case 0xECu:
        if ( vt != 3 )
          return 1;
        v12 = a3->vValue.lVal;
        goto LABEL_56;
      case 0xC9u:
        if ( vt != 3 )
          return 1;
        return (a3->vValue.lVal & 0xFFFFFFFE) != 0;
      case 0xE7u:
        if ( vt != 3 )
          return 1;
        v12 = a3->vValue.lVal;
        if ( !v12 )
          return 0;
LABEL_56:
        if ( v12 == 1 )
          return 0;
        v9 = v12 == 2;
        break;
      case 0xEEu:
        return vt != 11;
      default:
        return 0;
    }
    return !v9;
  }
  v7 = a2 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      if ( v8 != 1 )
        return 0;
      if ( a3->dwPropertyID == 19 )
      {
LABEL_19:
        v9 = vt == 8;
        return !v9;
      }
    }
    else
    {
      if ( a3->dwPropertyID == 286 )
      {
        v9 = vt == 13;
        return !v9;
      }
      if ( a3->dwPropertyID == 287 && vt == 8 )
      {
        result = 0;
        *((_WORD *)this + 343) = 1;
        return result;
      }
    }
    return 1;
  }
  else
  {
    switch ( a3->dwPropertyID )
    {
      case 8u:
        if ( vt != 3 )
          return 1;
        if ( a3->vValue.lVal >= 0 )
          return 0;
        result = 1;
        break;
      case 9u:
        goto LABEL_19;
      case 0xCu:
      case 0xDu:
      case 0xEu:
      case 0x14u:
      case 0x17u:
        return vt != 11;
      case 0x11u:
        if ( vt != 19 )
          return 1;
        Lo = a3->vValue.cyVal.Lo;
        if ( !Lo )
          return 1;
        if ( Lo <= 0x7FFFFFFF )
          return 0;
        result = 1;
        break;
      case 0x12u:
      case 0x13u:
        if ( vt != 8 )
          return 1;
        if ( SysStringLen(a3->vValue.bstrVal) <= 0x7D0 )
          return 0;
        result = 1;
        break;
      case 0x15u:
        v9 = vt == 18;
        return !v9;
      case 0x16u:
        if ( vt != 8210 )
          return 1;
        parray = a3->vValue.parray;
        if ( parray
          && SafeArrayGetDim(a3->vValue.parray) == 1
          && SafeArrayGetElemsize(parray) == 2
          && SafeArrayGetLBound(parray, 1u, &plLbound) >= 0
          && SafeArrayGetUBound(parray, 1u, &plUbound) >= 0
          && plUbound - plLbound < 0xFFFF )
        {
          return 0;
        }
        result = 1;
        break;
      default:
        return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x383853650  push    rbx
0x383853652  sub     rsp, 20h
0x383853656  movzx   r9d, word ptr [r8+30h]
0x38385365b  xor     eax, eax
0x38385365d  mov     r10, rcx
0x383853660  mov     [rsp+28h+plLbound], eax
0x383853664  mov     [rsp+28h+plUbound], eax
0x383853668  cmp     r9w, 0Bh
0x38385366d  jnz     short loc_38385367E
0x38385366f  movzx   eax, word ptr [r8+38h]
0x383853674  cmp     ax, 0FFFFh
0x383853678  jnz     loc_38385AE77
0x38385367e  mov     [rsp+28h+arg_0], rdi
0x383853683  test    edx, edx
0x383853685  jnz     loc_3838E74FB
0x38385368b  mov     eax, [r8]
0x38385368e  add     eax, 0FFFFFFDEh; switch 205 cases
0x383853691  cmp     eax, 0CCh
0x383853696  ja      short def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x383853698  lea     rdx, cs:383800000h
0x38385369f  movzx   eax, ds:(byte_383853570 - 383800000h)[rdx+rax]
0x3838536a7  mov     ecx, ds:(jpt_3838536B1 - 383800000h)[rdx+rax*4]
0x3838536ae  add     rcx, rdx
0x3838536b1  jmp     rcx; switch jump
0x3838536b3  xor     eax, eax; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x3838536b5  mov     rdi, [rsp+28h+arg_0]
0x3838536ba  add     rsp, 20h
0x3838536be  pop     rbx
0x3838536bf  retn
0x38385ae77  test    ax, ax
0x38385ae7a  jz      loc_38385367E
0x38385ae80  jmp     loc_3838E74F0
0x38385ae85  cmp     r9w, 3; jumptable 00000003838536B1 case 34
0x38385ae8a  jnz     loc_3838E773D
0x38385ae90  mov     eax, [r8+38h]
0x38385ae94  test    eax, eax
0x38385ae96  js      loc_3838E773D
0x38385ae9c  cmp     eax, 0FFFEh
0x38385aea1  jle     def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x38385aea7  jmp     loc_3838E76AE
0x383868d5f  cmp     r9w, 3; jumptable 00000003838536B1 case 117
0x383868d64  jnz     loc_3838E773D
0x383868d6a  mov     ecx, [r8+38h]
0x383868d6e  mov     eax, ecx
0x383868d70  and     eax, 7
0x383868d73  cmp     eax, ecx
0x383868d75  jnz     loc_3838E773D
0x383868d7b  jmp     def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x3838e74f0  mov     eax, 1
0x3838e74f5  add     rsp, 20h
0x3838e74f9  pop     rbx
0x3838e74fa  retn
0x3838e74fb  dec     edx
0x3838e74fd  jz      short loc_3838E7561
0x3838e74ff  dec     edx
0x3838e7501  jz      short loc_3838E751F
0x3838e7503  dec     edx
0x3838e7505  jnz     def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x3838e750b  cmp     dword ptr [r8], 13h
0x3838e750f  jnz     loc_3838E773D
0x3838e7515  cmp     r9w, 8; jumptable 00000003838E7581 case 9
0x3838e751a  jmp     loc_3838E771C
0x3838e751f  mov     ecx, [r8]
0x3838e7522  sub     ecx, 11Eh
0x3838e7528  jz      short loc_3838E7557
0x3838e752a  dec     ecx
0x3838e752c  jnz     loc_3838E773D
0x3838e7532  cmp     r9w, 8
0x3838e7537  jnz     loc_3838E773D
0x3838e753d  mov     rdi, [rsp+28h+arg_0]
0x3838e7542  mov     ebx, 1
0x3838e7547  xor     eax, eax
0x3838e7549  mov     [r10+2AEh], bx
0x3838e7551  add     rsp, 20h
0x3838e7555  pop     rbx
0x3838e7556  retn
0x3838e7557  cmp     r9w, 0Dh
0x3838e755c  jmp     loc_3838E771C
0x3838e7561  mov     eax, [r8]
0x3838e7564  add     eax, 0FFFFFFF8h; switch 16 cases
0x3838e7567  cmp     eax, 0Fh
0x3838e756a  ja      def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x3838e7570  lea     rdx, cs:383800000h
0x3838e7577  mov     eax, ds:(jpt_3838E7581 - 383800000h)[rdx+rax*4]
0x3838e757e  add     rax, rdx
0x3838e7581  jmp     rax; switch jump
0x3838e7583  cmp     r9w, 3; jumptable 00000003838E7581 case 8
0x3838e7588  jnz     loc_3838E773D
0x3838e758e  cmp     dword ptr [r8+38h], 0
0x3838e7593  jge     def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x3838e7599  mov     eax, 1
0x3838e759e  mov     rdi, [rsp+28h+arg_0]
0x3838e75a3  add     rsp, 20h
0x3838e75a7  pop     rbx
0x3838e75a8  retn
0x3838e75a9  cmp     r9w, 13h; jumptable 00000003838E7581 case 17
0x3838e75ae  jnz     loc_3838E773D
0x3838e75b4  mov     eax, [r8+38h]
0x3838e75b8  test    eax, eax
0x3838e75ba  jz      loc_3838E773D
0x3838e75c0  cmp     eax, 7FFFFFFFh
0x3838e75c5  jbe     def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x3838e75cb  mov     eax, 1
0x3838e75d0  mov     rdi, [rsp+28h+arg_0]
0x3838e75d5  add     rsp, 20h
0x3838e75d9  pop     rbx
0x3838e75da  retn
0x3838e75db  cmp     r9w, 8; jumptable 00000003838E7581 cases 18,19
0x3838e75e0  jnz     loc_3838E773D
0x3838e75e6  mov     rcx, [r8+38h]; pbstr
0x3838e75ea  call    cs:__imp_SysStringLen
0x3838e75f0  cmp     eax, 7D0h
0x3838e75f5  jbe     def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x3838e75fb  mov     eax, 1
0x3838e7600  mov     rdi, [rsp+28h+arg_0]
0x3838e7605  add     rsp, 20h
0x3838e7609  pop     rbx
0x3838e760a  retn
0x3838e760b  cmp     r9w, 12h; jumptable 00000003838E7581 case 21
0x3838e7610  jmp     loc_3838E771C
0x3838e7615  mov     eax, 2012h; jumptable 00000003838E7581 case 22
0x3838e761a  cmp     r9w, ax
0x3838e761e  jnz     loc_3838E773D
0x3838e7624  mov     rdi, [r8+38h]
0x3838e7628  mov     ebx, 1
0x3838e762d  test    rdi, rdi
0x3838e7630  jz      short loc_3838E7688
0x3838e7632  mov     rcx, rdi; psa
0x3838e7635  call    cs:__imp_SafeArrayGetDim
0x3838e763b  cmp     eax, ebx
0x3838e763d  jnz     short loc_3838E7688
0x3838e763f  mov     rcx, rdi; psa
0x3838e7642  call    cs:__imp_SafeArrayGetElemsize
0x3838e7648  cmp     eax, 2
0x3838e764b  jnz     short loc_3838E7688
0x3838e764d  lea     r8, [rsp+28h+plLbound]; plLbound
0x3838e7652  mov     edx, ebx; nDim
0x3838e7654  mov     rcx, rdi; psa
0x3838e7657  call    cs:__imp_SafeArrayGetLBound
0x3838e765d  test    eax, eax
0x3838e765f  js      short loc_3838E7688
0x3838e7661  lea     r8, [rsp+28h+plUbound]; plUbound
0x3838e7666  mov     edx, ebx; nDim
0x3838e7668  mov     rcx, rdi; psa
0x3838e766b  call    cs:__imp_SafeArrayGetUBound
0x3838e7671  test    eax, eax
0x3838e7673  js      short loc_3838E7688
0x3838e7675  mov     eax, [rsp+28h+plUbound]
0x3838e7679  sub     eax, [rsp+28h+plLbound]
0x3838e767d  cmp     eax, 0FFFFh
0x3838e7682  jl      def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x3838e7688  mov     eax, ebx
0x3838e768a  mov     rdi, [rsp+28h+arg_0]
0x3838e768f  add     rsp, 20h
0x3838e7693  pop     rbx
0x3838e7694  retn
0x3838e7695  cmp     r9w, 3; jumptable 00000003838536B1 case 231
0x3838e769a  jnz     loc_3838E773D
0x3838e76a0  mov     eax, [r8+38h]
0x3838e76a4  test    eax, eax
0x3838e76a6  jz      def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x3838e76ac  jmp     short loc_3838E7710
0x3838e76ae  mov     eax, 1
0x3838e76b3  mov     rdi, [rsp+28h+arg_0]
0x3838e76b8  add     rsp, 20h
0x3838e76bc  pop     rbx
0x3838e76bd  retn
0x3838e76be  cmp     r9w, 3; jumptable 00000003838536B1 cases 73,78
0x3838e76c3  jnz     short loc_3838E773D
0x3838e76c5  cmp     dword ptr [r8+38h], 0
0x3838e76ca  jge     def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x3838e76d0  mov     eax, 1
0x3838e76d5  mov     rdi, [rsp+28h+arg_0]
0x3838e76da  add     rsp, 20h
0x3838e76de  pop     rbx
0x3838e76df  retn
0x3838e76e0  cmp     r9w, 3; jumptable 00000003838536B1 case 201
0x3838e76e5  jnz     short loc_3838E773D
0x3838e76e7  test    dword ptr [r8+38h], 0FFFFFFFEh
0x3838e76ef  jz      def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x3838e76f5  mov     eax, 1
0x3838e76fa  mov     rdi, [rsp+28h+arg_0]
0x3838e76ff  add     rsp, 20h
0x3838e7703  pop     rbx
0x3838e7704  retn
0x3838e7705  cmp     r9w, 3; jumptable 00000003838536B1 cases 198,236
0x3838e770a  jnz     short loc_3838E773D
0x3838e770c  mov     eax, [r8+38h]
0x3838e7710  cmp     eax, 1
0x3838e7713  jz      def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x3838e7719  cmp     eax, 2
0x3838e771c  jz      def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x3838e7722  mov     eax, 1
0x3838e7727  mov     rdi, [rsp+28h+arg_0]
0x3838e772c  add     rsp, 20h
0x3838e7730  pop     rbx
0x3838e7731  retn
0x3838e7732  cmp     r9w, 0Bh; jumptable 00000003838536B1 case 238
0x3838e7737  jz      def_3838536B1; jumptable 00000003838536B1 default case, cases 35-72,74-77,79-116,118-197,199,200,202-230,232-235,237
0x3838e773d  mov     eax, 1
0x3838e7742  mov     rdi, [rsp+28h+arg_0]
0x3838e7747  add     rsp, 20h
0x3838e774b  pop     rbx
0x3838e774c  retn
```
