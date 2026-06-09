# CParamProps::IsValidValue(ulong,tagDBPROP *)

- ea: `0x383a4b4c0`
- end: `0x383a4b653`
- name: `?IsValidValue@CParamProps@@EEAAJKPEAUtagDBPROP@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(CParamProps *__hidden this, unsigned int, struct tagDBPROP *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x383a4b4c0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x383a4b579`
- `OLEAUT32!__imp_SysStringLen` at `0x383a4b579`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x383a4b5ba`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x383a4b5ba`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x383a4b5c8`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x383a4b5c8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x383a4b5f5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x383a4b5f5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x383a4b5de`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x383a4b5de`

## pseudocode

```c
__int64 __fastcall CParamProps::IsValidValue(CParamProps *this, int a2, struct tagDBPROP *a3)
{
  int v4; // eax
  __int64 result; // rax
  int v6; // eax
  bool v7; // zf
  UINT v8; // eax
  SAFEARRAY *parray; // rdi
  unsigned int v10; // eax
  unsigned int v11; // eax
  LONG plUbound; // [rsp+38h] [rbp+10h] BYREF
  LONG plLbound; // [rsp+40h] [rbp+18h] BYREF

  plLbound = 0;
  plUbound = 0;
  if ( a2 )
    return 1;
  switch ( a3->dwPropertyID )
  {
    case 0x18u:
    case 0x19u:
    case 0x1Au:
      v4 = *((_DWORD *)this + 144);
      if ( v4 != 141 && v4 != 130 )
        return 1;
      goto LABEL_12;
    case 0x1Bu:
    case 0x1Cu:
    case 0x1Du:
    case 0x26u:
      v6 = *((_DWORD *)this + 144);
      goto LABEL_7;
    case 0x27u:
    case 0x28u:
      v6 = *((_DWORD *)this + 144);
      if ( v6 == 143 )
        goto LABEL_12;
LABEL_7:
      if ( v6 == 132 )
        goto LABEL_12;
      v7 = v6 == 128;
LABEL_9:
      if ( v7 )
      {
LABEL_12:
        switch ( a3->dwPropertyID )
        {
          case 0x18u:
          case 0x19u:
          case 0x1Au:
          case 0x1Bu:
          case 0x1Cu:
          case 0x1Du:
          case 0x26u:
          case 0x27u:
          case 0x28u:
            if ( a3->vValue.vt != 8 )
              return 1;
            v8 = SysStringLen(a3->vValue.bstrVal);
            if ( !v8 || v8 > 0x80uLL )
              return 1;
            goto LABEL_29;
          case 0x1Eu:
          case 0x1Fu:
          case 0x20u:
          case 0x21u:
          case 0x22u:
          case 0x23u:
          case 0x24u:
          case 0x25u:
            return 1;
          case 0x29u:
          case 0x2Au:
            if ( a3->vValue.vt != 8210 )
              return 1;
            parray = a3->vValue.parray;
            if ( !parray
              || SafeArrayGetDim(a3->vValue.parray) != 1
              || SafeArrayGetElemsize(parray) != 2
              || SafeArrayGetLBound(parray, 1u, &plLbound) < 0
              || SafeArrayGetUBound(parray, 1u, &plUbound) < 0 )
            {
              return 1;
            }
            v10 = plUbound - plLbound;
            if ( a3->dwPropertyID == 41 )
            {
              if ( v10 >= 0x400 )
                return 1;
            }
            else
            {
              v11 = v10 + 1;
              if ( v11 > 0x800 || (v11 & 1) != 0 )
                return 1;
            }
LABEL_29:
            result = 0;
            break;
          default:
            return 1;
        }
      }
      else
      {
        result = 1;
      }
      break;
    case 0x29u:
    case 0x2Au:
      v7 = *((_DWORD *)this + 144) == 143;
      goto LABEL_9;
    default:
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x383a4b4c0  push    rbx
0x383a4b4c2  sub     rsp, 20h
0x383a4b4c6  xor     eax, eax
0x383a4b4c8  mov     rbx, r8
0x383a4b4cb  mov     r8, rcx
0x383a4b4ce  mov     [rsp+28h+plLbound], eax
0x383a4b4d2  mov     [rsp+28h+plUbound], eax
0x383a4b4d6  test    edx, edx
0x383a4b4d8  jnz     short def_383A4B4F6; jumptable 0000000383A4B4F6 default case, cases 30-37
0x383a4b4da  mov     edx, [rbx]
0x383a4b4dc  add     edx, 0FFFFFFE8h; switch 19 cases
0x383a4b4df  cmp     edx, 12h
0x383a4b4e2  ja      short def_383A4B4F6; jumptable 0000000383A4B4F6 default case, cases 30-37
0x383a4b4e4  lea     r9, cs:383800000h
0x383a4b4eb  mov     ecx, ds:(jpt_383A4B4F6 - 383800000h)[r9+rdx*4]
0x383a4b4f3  add     rcx, r9
0x383a4b4f6  jmp     rcx; switch jump
0x383a4b4f8  mov     eax, [r8+240h]; jumptable 0000000383A4B4F6 cases 24-26
0x383a4b4ff  cmp     eax, 8Dh
0x383a4b504  jz      short loc_383A4B546
0x383a4b506  cmp     eax, 82h
0x383a4b50b  jz      short loc_383A4B546
0x383a4b50d  mov     eax, 1; jumptable 0000000383A4B4F6 default case, cases 30-37
0x383a4b512  add     rsp, 20h
0x383a4b516  pop     rbx
0x383a4b517  retn
0x383a4b518  mov     eax, [r8+240h]; jumptable 0000000383A4B4F6 cases 27-29,38
0x383a4b51f  cmp     eax, 84h
0x383a4b524  jz      short loc_383A4B546
0x383a4b526  cmp     eax, 80h
0x383a4b52b  jz      short loc_383A4B546
0x383a4b52d  mov     eax, 1
0x383a4b532  add     rsp, 20h
0x383a4b536  pop     rbx
0x383a4b537  retn
0x383a4b538  mov     eax, [r8+240h]; jumptable 0000000383A4B4F6 cases 39,40
0x383a4b53f  cmp     eax, 8Fh
0x383a4b544  jnz     short loc_383A4B51F
0x383a4b546  mov     [rsp+28h+arg_0], rdi
0x383a4b54b  movzx   eax, ds:(byte_383A4B6AC - 383800000h)[r9+rdx]
0x383a4b554  mov     ecx, ds:(jpt_383A4B55F - 383800000h)[r9+rax*4]
0x383a4b55c  add     rcx, r9
0x383a4b55f  jmp     rcx; switch jump
0x383a4b561  cmp     dword ptr [r8+240h], 8Fh; jumptable 0000000383A4B4F6 cases 41,42
0x383a4b56c  jmp     short loc_383A4B52B
0x383a4b56e  cmp     word ptr [rbx+30h], 8; jumptable 0000000383A4B55F cases 24-29,38-40
0x383a4b573  jnz     short loc_383A4B593; jumptable 0000000383A4B55F cases 30-37
0x383a4b575  mov     rcx, [rbx+38h]; pbstr
0x383a4b579  call    cs:__imp_SysStringLen
0x383a4b57f  mov     r11d, eax
0x383a4b582  test    eax, eax
0x383a4b584  jz      short loc_383A4B593; jumptable 0000000383A4B55F cases 30-37
0x383a4b586  cmp     r11, 80h
0x383a4b58d  jbe     loc_383A4B646
0x383a4b593  mov     eax, 1; jumptable 0000000383A4B55F cases 30-37
0x383a4b598  mov     rdi, [rsp+28h+arg_0]
0x383a4b59d  add     rsp, 20h
0x383a4b5a1  pop     rbx
0x383a4b5a2  retn
0x383a4b5a3  mov     eax, 2012h; jumptable 0000000383A4B55F cases 41,42
0x383a4b5a8  cmp     [rbx+30h], ax
0x383a4b5ac  jnz     short loc_383A4B593; jumptable 0000000383A4B55F cases 30-37
0x383a4b5ae  mov     rdi, [rbx+38h]
0x383a4b5b2  test    rdi, rdi
0x383a4b5b5  jz      short loc_383A4B593; jumptable 0000000383A4B55F cases 30-37
0x383a4b5b7  mov     rcx, rdi; psa
0x383a4b5ba  call    cs:__imp_SafeArrayGetDim
0x383a4b5c0  cmp     eax, 1
0x383a4b5c3  jnz     short loc_383A4B593; jumptable 0000000383A4B55F cases 30-37
0x383a4b5c5  mov     rcx, rdi; psa
0x383a4b5c8  call    cs:__imp_SafeArrayGetElemsize
0x383a4b5ce  cmp     eax, 2
0x383a4b5d1  jnz     short loc_383A4B593; jumptable 0000000383A4B55F cases 30-37
0x383a4b5d3  lea     r8, [rsp+28h+plLbound]; plLbound
0x383a4b5d8  lea     edx, [rax-1]; nDim
0x383a4b5db  mov     rcx, rdi; psa
0x383a4b5de  call    cs:__imp_SafeArrayGetLBound
0x383a4b5e4  test    eax, eax
0x383a4b5e6  js      short loc_383A4B593; jumptable 0000000383A4B55F cases 30-37
0x383a4b5e8  lea     r8, [rsp+28h+plUbound]; plUbound
0x383a4b5ed  mov     edx, 1; nDim
0x383a4b5f2  mov     rcx, rdi; psa
0x383a4b5f5  call    cs:__imp_SafeArrayGetUBound
0x383a4b5fb  test    eax, eax
0x383a4b5fd  js      short loc_383A4B593; jumptable 0000000383A4B55F cases 30-37
0x383a4b5ff  mov     eax, [rsp+28h+plUbound]
0x383a4b603  sub     eax, [rsp+28h+plLbound]
0x383a4b607  cmp     dword ptr [rbx], 29h ; ')'
0x383a4b60a  jnz     short loc_383A4B623
0x383a4b60c  cmp     eax, 400h
0x383a4b611  jb      short loc_383A4B646
0x383a4b613  mov     eax, 1
0x383a4b618  mov     rdi, [rsp+28h+arg_0]
0x383a4b61d  add     rsp, 20h
0x383a4b621  pop     rbx
0x383a4b622  retn
0x383a4b623  inc     eax
0x383a4b625  cmp     eax, 800h
0x383a4b62a  ja      loc_383A4B593; jumptable 0000000383A4B55F cases 30-37
0x383a4b630  and     eax, 80000001h
0x383a4b635  jge     short loc_383A4B63E
0x383a4b637  dec     eax
0x383a4b639  or      eax, 0FFFFFFFEh
0x383a4b63c  inc     eax
0x383a4b63e  test    eax, eax
0x383a4b640  jnz     loc_383A4B593; jumptable 0000000383A4B55F cases 30-37
0x383a4b646  xor     eax, eax
0x383a4b648  mov     rdi, [rsp+28h+arg_0]
0x383a4b64d  add     rsp, 20h
0x383a4b651  pop     rbx
0x383a4b652  retn
```
