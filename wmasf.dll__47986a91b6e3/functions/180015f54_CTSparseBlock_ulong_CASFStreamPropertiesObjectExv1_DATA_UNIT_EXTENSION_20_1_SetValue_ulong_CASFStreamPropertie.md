# CTSparseBlock<ulong,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1>::SetValue(ulong,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *)

- ea: `0x180015f54`
- end: `0x18001604d`
- name: `?SetValue@?$CTSparseBlock@KPEAU_DATA_UNIT_EXTENSION@CASFStreamPropertiesObjectExv1@@$0BE@$00@@QEAAJKPEAU_DATA_UNIT_EXTENSION@CASFStreamPropertiesObjectExv1@@@Z`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180015a70`

## callees

- `0x1800015d0`
- `0x180015f54`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CTSparseBlock<unsigned long,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1>::SetValue(
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
  *((_BYTE *)i + ((unsigned __int64)(unsigned int)v11 >> 3) + 24) |= *((_BYTE *)&CTSparseBlock<unsigned long,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1>::s_bSingleBitMasks
                                                                     + (v11 & 7));
  if ( (unsigned int)v11 >= 0x14 )
    return 2147549183LL;
  *(_QWORD *)&i[2 * v11 + 8] = a3;
  return 0;
}

```

## disassembly

```asm
0x180015f54  mov     [rsp+arg_10], rbx
0x180015f59  push    rbp
0x180015f5a  push    rsi
0x180015f5b  push    rdi
0x180015f5c  sub     rsp, 30h
0x180015f60  mov     rax, cs:__security_cookie
0x180015f67  xor     rax, rsp
0x180015f6a  mov     [rsp+48h+var_20], rax
0x180015f6f  mov     rbp, r8
0x180015f72  mov     edi, edx
0x180015f74  test    rcx, rcx
0x180015f77  jnz     short loc_180015F83
0x180015f79  mov     eax, 80004003h
0x180015f7e  jmp     loc_180016033
0x180015f83  xor     esi, esi
0x180015f85  mov     rbx, rcx
0x180015f88  test    rbx, rbx
0x180015f8b  jz      short loc_180015FA7
0x180015f8d  mov     eax, [rbx+8]
0x180015f90  cmp     edi, eax
0x180015f92  jb      short loc_180015FA7
0x180015f94  add     eax, 14h
0x180015f97  cmp     edi, eax
0x180015f99  jb      short loc_180015FF9
0x180015f9b  mov     rsi, rbx
0x180015f9e  mov     rbx, [rbx+0C0h]
0x180015fa5  jmp     short loc_180015F88
0x180015fa7  mov     rax, [rcx]
0x180015faa  lea     rdx, [rsp+48h+var_28]
0x180015faf  mov     [rsp+48h+var_28], 0
0x180015fb8  mov     rax, [rax]
0x180015fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fc0  test    eax, eax
0x180015fc2  js      short loc_180016033
0x180015fc4  mov     eax, 0CCCCCCCDh
0x180015fc9  mul     edi
0x180015fcb  mov     rax, [rsp+48h+var_28]
0x180015fd0  shr     edx, 4
0x180015fd3  lea     ecx, [rdx+rdx*4]
0x180015fd6  shl     ecx, 2
0x180015fd9  mov     [rax+8], ecx
0x180015fdc  mov     rax, [rsp+48h+var_28]
0x180015fe1  test    rsi, rsi
0x180015fe4  jz      short loc_180015FED
0x180015fe6  mov     [rsi+0C0h], rax
0x180015fed  mov     [rax+0C0h], rbx
0x180015ff4  mov     rbx, [rsp+48h+var_28]
0x180015ff9  sub     edi, [rbx+8]
0x180015ffc  mov     eax, edi
0x180015ffe  and     eax, 0FFFFFFF8h
0x180016001  cmp     eax, 18h
0x180016004  jnb     short loc_18001602E
0x180016006  mov     eax, edi
0x180016008  lea     r8, ?s_bSingleBitMasks@?$CTSparseBlock@KPEAU_DATA_UNIT_EXTENSION@CASFStreamPropertiesObjectExv1@@$0BE@$00@@0PAEA; uchar near * CTSparseBlock<ulong,CASFStreamPropertiesObjectExv1::_DATA_UNIT_EXTENSION *,20,1>::s_bSingleBitMasks
0x18001600f  and     eax, 7
0x180016012  mov     ecx, edi
0x180016014  shr     rcx, 3
0x180016018  mov     al, [rax+r8]
0x18001601c  or      [rcx+rbx+18h], al
0x180016020  cmp     edi, 14h
0x180016023  jnb     short loc_18001602E
0x180016025  mov     [rbx+rdi*8+20h], rbp
0x18001602a  xor     eax, eax
0x18001602c  jmp     short loc_180016033
0x18001602e  mov     eax, 8000FFFFh
0x180016033  mov     rcx, [rsp+48h+var_20]
0x180016038  xor     rcx, rsp; StackCookie
0x18001603b  call    __security_check_cookie
0x180016040  mov     rbx, [rsp+48h+arg_10]
0x180016045  add     rsp, 30h
0x180016049  pop     rdi
0x18001604a  pop     rsi
0x18001604b  pop     rbp
0x18001604c  retn
```
