# CWbemDispatchMgr::MapInParameter(tagVARIANT *,tagVARIANT *,long)

- ea: `0x180002df8`
- end: `0x180002eee`
- name: `?MapInParameter@CWbemDispatchMgr@@AEAAJPEAUtagVARIANT@@0J@Z`
- size: `246`
- prototype: `__int64 __fastcall(CWbemDispatchMgr *__hidden this, struct tagVARIANT *, struct tagVARIANT *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180002bc0`
- `0x180002df8`

## callees

- `0x180002df8`
- `0x180002ef4`
- `0x180025074`
- `0x180025414`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180002e4d`
- `OLEAUT32!__imp_VariantCopy` at `0x180002e4d`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002e78`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002e78`

## pseudocode

```c
int __fastcall CWbemDispatchMgr::MapInParameter(
        CWbemDispatchMgr *this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        int a4)
{
  int result; // eax

  if ( a3 && a3->vt >= 2u )
  {
    if ( ((a3->vt - 8204) & 0xBFFF) != 0 )
    {
      if ( (a4 & 0x2000) == 0 || ((a3->vt - 9) & 0xBFFF) != 0 )
      {
        if ( a3->vt == 16396 )
        {
          return CWbemDispatchMgr::MapInParameter(this, a2, a3->pvarVal, a4);
        }
        else
        {
          result = VariantCopy(a2, a3);
          if ( result >= 0 )
          {
            result = MapToCIMOMObject(a2);
            if ( (a2->vt & 0x4000) != 0 )
              return VariantChangeType(a2, a2, 0, a2->vt & 0xBFFF);
          }
        }
      }
      else
      {
        return ConvertDispatchToArray(a2, a3, a4 & 0xFFFFDFFF, 0, 1u);
      }
    }
    else
    {
      result = ConvertArray(a2, a3, 0, 1);
      if ( result >= 0 )
        return MapToCIMOMObject(a2);
    }
  }
  else
  {
    result = 0;
    a2->vt = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180002df8  mov     [rsp+arg_0], rbx
0x180002dfd  push    rdi
0x180002dfe  sub     rsp, 30h
0x180002e02  mov     r11d, r9d
0x180002e05  mov     r10, r8
0x180002e08  mov     rbx, rdx
0x180002e0b  test    r8, r8
0x180002e0e  jz      loc_180002E97
0x180002e14  cmp     word ptr [r8], 2
0x180002e19  jb      short loc_180002E97
0x180002e1b  movzx   eax, word ptr [r8]
0x180002e1f  mov     edx, 200Ch
0x180002e24  sub     ax, dx
0x180002e27  mov     edi, 0BFFFh
0x180002e2c  test    di, ax
0x180002e2f  jz      loc_180002ECC
0x180002e35  bt      r9d, 0Dh
0x180002e3a  jb      short loc_180002EA0
0x180002e3c  mov     eax, 400Ch
0x180002e41  cmp     ax, [r8]
0x180002e45  jz      short loc_180002E80
0x180002e47  mov     rdx, r10; pvargSrc
0x180002e4a  mov     rcx, rbx; pvargDest
0x180002e4d  call    cs:__imp_VariantCopy
0x180002e53  test    eax, eax
0x180002e55  js      short loc_180002E8C
0x180002e57  mov     rcx, rbx; struct tagVARIANT *
0x180002e5a  call    ?MapToCIMOMObject@@YAJPEAUtagVARIANT@@@Z; MapToCIMOMObject(tagVARIANT *)
0x180002e5f  movzx   r9d, word ptr [rbx]
0x180002e63  bt      r9w, 0Eh
0x180002e69  jnb     short loc_180002E8C
0x180002e6b  and     r9w, di; vt
0x180002e6f  xor     r8d, r8d; wFlags
0x180002e72  mov     rdx, rbx; pvarSrc
0x180002e75  mov     rcx, rbx; pvargDest
0x180002e78  call    cs:__imp_VariantChangeType
0x180002e7e  jmp     short loc_180002E8C
0x180002e80  mov     r8, [r8+8]; struct tagVARIANT *
0x180002e84  mov     rdx, rbx; struct tagVARIANT *
0x180002e87  call    ?MapInParameter@CWbemDispatchMgr@@AEAAJPEAUtagVARIANT@@0J@Z; CWbemDispatchMgr::MapInParameter(tagVARIANT *,tagVARIANT *,long)
0x180002e8c  mov     rbx, [rsp+38h+arg_0]
0x180002e91  add     rsp, 30h
0x180002e95  pop     rdi
0x180002e96  retn
0x180002e97  xor     eax, eax
0x180002e99  mov     word ptr [rdx], 1
0x180002e9e  jmp     short loc_180002E8C
0x180002ea0  movzx   eax, word ptr [r8]
0x180002ea4  sub     ax, 9
0x180002ea8  test    di, ax
0x180002eab  jnz     short loc_180002E3C
0x180002ead  btr     r11d, 0Dh
0x180002eb2  mov     [rsp+38h+var_18], 1; unsigned __int16
0x180002eb9  mov     r8d, r11d; int
0x180002ebc  xor     r9d, r9d; int
0x180002ebf  mov     rdx, r10; struct tagVARIANT *
0x180002ec2  mov     rcx, rbx; struct tagVARIANT *
0x180002ec5  call    ?ConvertDispatchToArray@@YAJPEAUtagVARIANT@@0JHG@Z; ConvertDispatchToArray(tagVARIANT *,tagVARIANT *,long,int,ushort)
0x180002eca  jmp     short loc_180002E8C
0x180002ecc  mov     r9d, 1; unsigned __int16
0x180002ed2  xor     r8d, r8d; int
0x180002ed5  mov     rdx, r10; struct tagVARIANT *
0x180002ed8  mov     rcx, rbx; struct tagVARIANT *
0x180002edb  call    ?ConvertArray@@YAJPEAUtagVARIANT@@0HG@Z; ConvertArray(tagVARIANT *,tagVARIANT *,int,ushort)
0x180002ee0  test    eax, eax
0x180002ee2  js      short loc_180002E8C
0x180002ee4  mov     rcx, rbx; struct tagVARIANT *
0x180002ee7  call    ?MapToCIMOMObject@@YAJPEAUtagVARIANT@@@Z; MapToCIMOMObject(tagVARIANT *)
0x180002eec  jmp     short loc_180002E8C
```
