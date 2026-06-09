# CTSparseBlock<ulong,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::SetValue(ulong,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *)

- ea: `0x180025614`
- end: `0x18002570d`
- name: `?SetValue@?$CTSparseBlock@KPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@$0BE@$00@@QEAAJKPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@@Z`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800174b4`
- `0x18001feb0`

## callees

- `0x1800015f0`
- `0x180025614`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::SetValue(
        _DWORD *a1,
        unsigned int a2,
        __int64 (__fastcall **a3)(_QWORD, _QWORD *))
{
  __int64 result; // rax
  _DWORD *v6; // rsi
  _DWORD *i; // rbx
  unsigned int v8; // eax
  __int64 (__fastcall **v9)(_DWORD *, _DWORD **); // rax
  _QWORD *v10; // rax
  __int64 v11; // rdi
  _DWORD *v12; // [rsp+20h] [rbp-28h] BYREF

  if ( !a1 )
    return 2147500035LL;
  v6 = 0;
  for ( i = a1; i; i = (_DWORD *)*((_QWORD *)i + 24) )
  {
    v8 = i[2];
    if ( a2 < v8 )
      break;
    if ( a2 < v8 + 20 )
      goto LABEL_12;
    v6 = i;
  }
  v9 = *(__int64 (__fastcall ***)(_DWORD *, _DWORD **))a1;
  v12 = 0;
  result = (*v9)(a1, &v12);
  if ( (int)result < 0 )
    return result;
  v12[2] = 20 * (a2 / 0x14);
  v10 = v12;
  if ( v6 )
    *((_QWORD *)v6 + 24) = v12;
  v10[24] = i;
  i = v12;
LABEL_12:
  v11 = a2 - i[2];
  if ( ((unsigned int)v11 & 0xFFFFFFF8) >= 0x18 )
    return 2147549183LL;
  *((_BYTE *)i + ((unsigned __int64)(unsigned int)v11 >> 3) + 24) |= CTSparseBlock<unsigned long,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::s_bSingleBitMasks[v11 & 7];
  if ( (unsigned int)v11 >= 0x14 )
    return 2147549183LL;
  *(_QWORD *)&i[2 * v11 + 8] = a3;
  return 0;
}

```

## disassembly

```asm
0x180025614  mov     [rsp+arg_10], rbx
0x180025619  push    rbp
0x18002561a  push    rsi
0x18002561b  push    rdi
0x18002561c  sub     rsp, 30h
0x180025620  mov     rax, cs:__security_cookie
0x180025627  xor     rax, rsp
0x18002562a  mov     [rsp+48h+var_20], rax
0x18002562f  mov     rbp, r8
0x180025632  mov     edi, edx
0x180025634  test    rcx, rcx
0x180025637  jnz     short loc_180025643
0x180025639  mov     eax, 80004003h
0x18002563e  jmp     loc_1800256F3
0x180025643  xor     esi, esi
0x180025645  mov     rbx, rcx
0x180025648  test    rbx, rbx
0x18002564b  jz      short loc_180025667
0x18002564d  mov     eax, [rbx+8]
0x180025650  cmp     edi, eax
0x180025652  jb      short loc_180025667
0x180025654  add     eax, 14h
0x180025657  cmp     edi, eax
0x180025659  jb      short loc_1800256B9
0x18002565b  mov     rsi, rbx
0x18002565e  mov     rbx, [rbx+0C0h]
0x180025665  jmp     short loc_180025648
0x180025667  mov     rax, [rcx]
0x18002566a  lea     rdx, [rsp+48h+var_28]
0x18002566f  mov     [rsp+48h+var_28], 0
0x180025678  mov     rax, [rax]
0x18002567b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025680  test    eax, eax
0x180025682  js      short loc_1800256F3
0x180025684  mov     eax, 0CCCCCCCDh
0x180025689  mul     edi
0x18002568b  mov     rax, [rsp+48h+var_28]
0x180025690  shr     edx, 4
0x180025693  lea     ecx, [rdx+rdx*4]
0x180025696  shl     ecx, 2
0x180025699  mov     [rax+8], ecx
0x18002569c  mov     rax, [rsp+48h+var_28]
0x1800256a1  test    rsi, rsi
0x1800256a4  jz      short loc_1800256AD
0x1800256a6  mov     [rsi+0C0h], rax
0x1800256ad  mov     [rax+0C0h], rbx
0x1800256b4  mov     rbx, [rsp+48h+var_28]
0x1800256b9  sub     edi, [rbx+8]
0x1800256bc  mov     eax, edi
0x1800256be  and     eax, 0FFFFFFF8h
0x1800256c1  cmp     eax, 18h
0x1800256c4  jnb     short loc_1800256EE
0x1800256c6  mov     eax, edi
0x1800256c8  lea     r8, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAU_EXTENSION_SYSTEM_RECORD@CASFStreamPropertiesObjectEx@@$0BE@$00@@0PAEA; uchar near * CTSparseBlock<ulong,CASFStreamPropertiesObjectEx::_EXTENSION_SYSTEM_RECORD *,20,1>::s_bSingleBitMasks
0x1800256cf  and     eax, 7
0x1800256d2  mov     ecx, edi
0x1800256d4  shr     rcx, 3
0x1800256d8  mov     al, [rax+r8]
0x1800256dc  or      [rcx+rbx+18h], al
0x1800256e0  cmp     edi, 14h
0x1800256e3  jnb     short loc_1800256EE
0x1800256e5  mov     [rbx+rdi*8+20h], rbp
0x1800256ea  xor     eax, eax
0x1800256ec  jmp     short loc_1800256F3
0x1800256ee  mov     eax, 8000FFFFh
0x1800256f3  mov     rcx, [rsp+48h+var_20]
0x1800256f8  xor     rcx, rsp; StackCookie
0x1800256fb  call    __security_check_cookie
0x180025700  mov     rbx, [rsp+48h+arg_10]
0x180025705  add     rsp, 30h
0x180025709  pop     rdi
0x18002570a  pop     rsi
0x18002570b  pop     rbp
0x18002570c  retn
```
