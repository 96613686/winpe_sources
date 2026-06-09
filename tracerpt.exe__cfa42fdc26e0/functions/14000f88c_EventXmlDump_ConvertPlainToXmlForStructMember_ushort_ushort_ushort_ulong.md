# EventXmlDump::ConvertPlainToXmlForStructMember(ushort *,ushort *,ushort *,ulong *)

- ea: `0x14000f88c`
- end: `0x14000fa9c`
- name: `?ConvertPlainToXmlForStructMember@EventXmlDump@@QEAAKPEAG00PEAK@Z`
- size: `528`
- prototype: `__int64 __fastcall(EventXmlDump *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000f104`

## callees

- `0x14000f6f0`
- `0x14000f88c`
- `0x140011610`

## pseudocode

```c
__int64 __fastcall EventXmlDump::ConvertPlainToXmlForStructMember(
        EventXmlDump *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  EventXmlDump *v7; // rcx
  unsigned int v8; // edi
  unsigned __int16 *v9; // r15
  unsigned __int64 v10; // r8
  __int64 result; // rax
  unsigned __int16 *v12; // r12
  __int64 v13; // rbx
  unsigned __int16 *v14; // r11
  const wchar_t *v15; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // r9
  __int64 v18; // r10
  __int64 v19; // r13
  unsigned __int16 *v20; // rcx
  unsigned int v21; // r10d
  unsigned __int64 v22; // rax
  EventXmlDump *v23; // rcx
  unsigned __int64 v24; // rbx
  unsigned __int16 *v25; // r12
  unsigned __int16 *v26; // rcx
  unsigned int v27; // [rsp+28h] [rbp-10h]
  unsigned int v28; // [rsp+28h] [rbp-10h]
  unsigned __int64 v29; // [rsp+80h] [rbp+48h] BYREF
  unsigned __int16 *v30; // [rsp+88h] [rbp+50h]
  __int64 v31; // [rsp+90h] [rbp+58h]
  unsigned __int16 *v32; // [rsp+98h] [rbp+60h]

  v32 = a4;
  v30 = a2;
  HIDWORD(v29) = HIDWORD(this);
  v31 = 0;
  LODWORD(v29) = 0;
  EventXmlDump::ConvertPlainToXml(this, a2, 0, (unsigned int *)&v29);
  v8 = ((unsigned int)v29 >> 1) + 21;
  if ( a3 )
  {
    LODWORD(v29) = 0;
    EventXmlDump::ConvertPlainToXml(v7, a3, 0, (unsigned int *)&v29);
    v8 += ((unsigned int)v29 >> 1) - 1;
  }
  v9 = a5;
  v10 = *(unsigned int *)a5;
  if ( v10 < 2 * (unsigned __int64)v8 )
  {
    *(_DWORD *)a5 = 2 * v8;
    return 122;
  }
  v12 = 0;
  v13 = 0;
  if ( !(v10 >> 1) )
    return 13;
  v14 = a4;
  v15 = L"<Data Name=\"";
  v16 = 2147483646;
  v17 = v10 >> 1;
  v18 = 0;
  do
  {
    if ( !v16 )
      break;
    if ( *v15 == (_WORD)v31 )
      break;
    *v14++ = *v15++;
    --v16;
    ++v18;
    --v17;
  }
  while ( v17 );
  v19 = v18 - 1;
  v20 = v14 - 1;
  if ( v17 )
    v19 = v18;
  v21 = v17 == 0 ? 0x8007007A : 0;
  if ( v17 )
    v20 = v14;
  *v20 = 0;
  if ( (int)(v21 + 0x80000000) < 0 || v21 == -2147024774 )
  {
    v12 = &v32[v19];
    v13 = (v10 & 1) + 2 * ((v10 >> 1) - v19);
  }
  if ( !v17 )
    return 13;
  LODWORD(v29) = v13;
  result = EventXmlDump::ConvertPlainToXml((EventXmlDump *)0x80000000LL, v30, v12, (unsigned int *)&v29);
  if ( (_DWORD)result )
    return result;
  v22 = (unsigned int)v29 - 2LL;
  v29 = 2LL - (unsigned int)v29 + v13;
  a5 = &v12[v22 >> 1];
  if ( (int)StringCbCatExW(a5, v29, L"\">", &a5, &v29, v27) < 0 )
    return 13;
  v24 = v29;
  if ( a3 )
  {
    v25 = a5;
    result = EventXmlDump::ConvertPlainToXml(v23, a3, a5, (unsigned int *)&v29);
    if ( (_DWORD)result )
      return result;
    v24 += 2LL - (unsigned int)v29;
    v26 = &v25[((unsigned __int64)(unsigned int)v29 - 2) >> 1];
  }
  else
  {
    v26 = a5;
  }
  if ( (int)StringCbCatExW(v26, v24, L"</Data>", 0, 0, v28) < 0 )
    return 13;
  *(_DWORD *)v9 = 2 * v8;
  return 0;
}

```

## disassembly

```asm
0x14000f88c  mov     [rsp-40h+arg_18], r9
0x14000f891  mov     [rsp-40h+arg_8], rdx
0x14000f896  mov     [rsp-40h+arg_0], rcx
0x14000f89b  push    rbp
0x14000f89c  push    rbx
0x14000f89d  push    rsi
0x14000f89e  push    rdi
0x14000f89f  push    r12
0x14000f8a1  push    r13
0x14000f8a3  push    r14
0x14000f8a5  push    r15
0x14000f8a7  mov     rbp, rsp
0x14000f8aa  sub     rsp, 38h
0x14000f8ae  mov     rsi, r9
0x14000f8b1  mov     r14, r8
0x14000f8b4  xor     r13d, r13d
0x14000f8b7  lea     r9, [rbp+arg_0]; unsigned int *
0x14000f8bb  xor     r8d, r8d; unsigned __int16 *
0x14000f8be  mov     [rbp+arg_10], r13
0x14000f8c2  mov     dword ptr [rbp+arg_0], r13d
0x14000f8c6  call    ?ConvertPlainToXml@EventXmlDump@@QEAAKPEAG0PEAK@Z; EventXmlDump::ConvertPlainToXml(ushort *,ushort *,ulong *)
0x14000f8cb  mov     edi, dword ptr [rbp+arg_0]
0x14000f8ce  shr     edi, 1
0x14000f8d0  add     edi, 15h
0x14000f8d3  test    r14, r14
0x14000f8d6  jz      short loc_14000F8F4
0x14000f8d8  lea     r9, [rbp+arg_0]; unsigned int *
0x14000f8dc  mov     dword ptr [rbp+arg_0], r13d
0x14000f8e0  xor     r8d, r8d; unsigned __int16 *
0x14000f8e3  mov     rdx, r14; unsigned __int16 *
0x14000f8e6  call    ?ConvertPlainToXml@EventXmlDump@@QEAAKPEAG0PEAK@Z; EventXmlDump::ConvertPlainToXml(ushort *,ushort *,ulong *)
0x14000f8eb  mov     eax, dword ptr [rbp+arg_0]
0x14000f8ee  shr     eax, 1
0x14000f8f0  dec     eax
0x14000f8f2  add     edi, eax
0x14000f8f4  mov     r15, [rbp+arg_20]
0x14000f8f8  mov     eax, edi
0x14000f8fa  add     rax, rax
0x14000f8fd  mov     r8d, [r15]
0x14000f900  cmp     r8, rax
0x14000f903  jnb     short loc_14000F915
0x14000f905  lea     eax, [rdi+rdi]
0x14000f908  mov     [r15], eax
0x14000f90b  mov     eax, 7Ah ; 'z'
0x14000f910  jmp     loc_14000FA8B
0x14000f915  mov     rdx, r8
0x14000f918  mov     r12, r13
0x14000f91b  shr     rdx, 1
0x14000f91e  mov     rbx, r13
0x14000f921  jz      loc_14000FA86
0x14000f927  mov     r11, rsi
0x14000f92a  lea     rcx, aDataName_1; "<Data Name=\""
0x14000f931  mov     esi, 2
0x14000f936  mov     eax, 7FFFFFFEh
0x14000f93b  mov     r9, rdx
0x14000f93e  mov     r10, r13
0x14000f941  test    rax, rax
0x14000f944  jz      short loc_14000F967
0x14000f946  movzx   r13d, word ptr [rcx]
0x14000f94a  cmp     r13w, word ptr [rbp+arg_10]
0x14000f94f  jz      short loc_14000F967
0x14000f951  mov     [r11], r13w
0x14000f955  add     rcx, rsi
0x14000f958  add     r11, rsi
0x14000f95b  dec     rax
0x14000f95e  inc     r10
0x14000f961  sub     r9, 1
0x14000f965  jnz     short loc_14000F941
0x14000f967  test    r9, r9
0x14000f96a  lea     r13, [r10-1]
0x14000f96e  mov     rax, r9
0x14000f971  lea     rcx, [r11-2]
0x14000f975  cmovnz  r13, r10
0x14000f979  neg     rax
0x14000f97c  sbb     r10d, r10d
0x14000f97f  xor     eax, eax
0x14000f981  not     r10d
0x14000f984  and     r10d, 8007007Ah
0x14000f98b  test    r9, r9
0x14000f98e  cmovnz  rcx, r11
0x14000f992  mov     [rcx], ax
0x14000f995  mov     ecx, 80000000h; this
0x14000f99a  lea     eax, [r10+rcx]
0x14000f99e  test    ecx, eax
0x14000f9a0  jnz     short loc_14000F9AB
0x14000f9a2  cmp     r10d, 8007007Ah
0x14000f9a9  jnz     short loc_14000F9BE
0x14000f9ab  mov     rax, [rbp+arg_18]
0x14000f9af  sub     rdx, r13
0x14000f9b2  and     r8d, 1
0x14000f9b6  lea     r12, [rax+r13*2]
0x14000f9ba  lea     rbx, [r8+rdx*2]
0x14000f9be  xor     r13d, r13d
0x14000f9c1  test    r10d, r10d
0x14000f9c4  js      loc_14000FA86
0x14000f9ca  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x14000f9ce  lea     r9, [rbp+arg_0]; unsigned int *
0x14000f9d2  mov     r8, r12; unsigned __int16 *
0x14000f9d5  mov     dword ptr [rbp+arg_0], ebx
0x14000f9d8  call    ?ConvertPlainToXml@EventXmlDump@@QEAAKPEAG0PEAK@Z; EventXmlDump::ConvertPlainToXml(ushort *,ushort *,ulong *)
0x14000f9dd  test    eax, eax
0x14000f9df  jnz     loc_14000FA8B
0x14000f9e5  mov     ecx, dword ptr [rbp+arg_0]
0x14000f9e8  lea     r9, [rbp+arg_20]; unsigned __int16 **
0x14000f9ec  mov     rax, rsi
0x14000f9ef  lea     r8, asc_140045C18; "\">"
0x14000f9f6  sub     rax, rcx
0x14000f9f9  add     rbx, rax
0x14000f9fc  lea     rax, [rcx-2]
0x14000fa00  mov     [rbp+arg_0], rbx
0x14000fa04  shr     rax, 1
0x14000fa07  mov     rdx, rbx; unsigned __int64
0x14000fa0a  lea     rcx, [r12+rax*2]; unsigned __int16 *
0x14000fa0e  lea     rax, [rbp+arg_0]
0x14000fa12  mov     [rbp+arg_20], rcx
0x14000fa16  mov     [rsp+38h+var_18], rax; unsigned __int64 *
0x14000fa1b  call    ?StringCbCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x14000fa20  test    eax, eax
0x14000fa22  js      short loc_14000FA86
0x14000fa24  mov     rbx, [rbp+arg_0]
0x14000fa28  test    r14, r14
0x14000fa2b  jz      short loc_14000FA5D
0x14000fa2d  mov     r12, [rbp+arg_20]
0x14000fa31  lea     r9, [rbp+arg_0]; unsigned int *
0x14000fa35  mov     r8, r12; unsigned __int16 *
0x14000fa38  mov     dword ptr [rbp+arg_0], ebx
0x14000fa3b  mov     rdx, r14; unsigned __int16 *
0x14000fa3e  call    ?ConvertPlainToXml@EventXmlDump@@QEAAKPEAG0PEAK@Z; EventXmlDump::ConvertPlainToXml(ushort *,ushort *,ulong *)
0x14000fa43  test    eax, eax
0x14000fa45  jnz     short loc_14000FA8B
0x14000fa47  mov     eax, dword ptr [rbp+arg_0]
0x14000fa4a  sub     rsi, rax
0x14000fa4d  add     rax, 0FFFFFFFFFFFFFFFEh
0x14000fa51  add     rbx, rsi
0x14000fa54  shr     rax, 1
0x14000fa57  lea     rcx, [r12+rax*2]
0x14000fa5b  jmp     short loc_14000FA61
0x14000fa5d  mov     rcx, [rbp+arg_20]; unsigned __int16 *
0x14000fa61  xor     r9d, r9d; unsigned __int16 **
0x14000fa64  mov     [rsp+38h+var_18], r13; unsigned __int64 *
0x14000fa69  lea     r8, aData_5; "</Data>"
0x14000fa70  mov     rdx, rbx; unsigned __int64
0x14000fa73  call    ?StringCbCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x14000fa78  test    eax, eax
0x14000fa7a  js      short loc_14000FA86
0x14000fa7c  lea     eax, [rdi+rdi]
0x14000fa7f  mov     [r15], eax
0x14000fa82  xor     eax, eax
0x14000fa84  jmp     short loc_14000FA8B
0x14000fa86  mov     eax, 0Dh
0x14000fa8b  add     rsp, 38h
0x14000fa8f  pop     r15
0x14000fa91  pop     r14
0x14000fa93  pop     r13
0x14000fa95  pop     r12
0x14000fa97  pop     rdi
0x14000fa98  pop     rsi
0x14000fa99  pop     rbx
0x14000fa9a  pop     rbp
0x14000fa9b  retn
```
