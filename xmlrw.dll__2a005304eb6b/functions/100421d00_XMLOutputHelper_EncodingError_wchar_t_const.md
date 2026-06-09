# XMLOutputHelper::EncodingError(wchar_t const *)

- ea: `0x100421d00`
- end: `0x100421f05`
- name: `?EncodingError@XMLOutputHelper@@MEAAJPEB_W@Z`
- size: `517`
- prototype: `__int64 __fastcall(XMLOutputHelper *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x100421ba0`
- `0x100421d00`
- `0x100423100`
- `0x100426580`

## pseudocode

```c
__int64 __fastcall XMLOutputHelper::EncodingError(XMLOutputHelper *this, const wchar_t *a2)
{
  unsigned __int16 *v3; // rbx
  __int64 v4; // r8
  unsigned __int16 v5; // ax
  __int64 result; // rax
  unsigned __int16 v7; // ax
  unsigned int v8; // r9d
  int v9; // ecx
  __int64 v10; // r8
  wchar_t *v11; // rdx
  wchar_t v12; // ax
  wchar_t *v13; // rax
  unsigned int v14; // edi
  int v15; // r8d
  int v16; // esi
  __int64 v17; // rdx
  wchar_t *v18; // rcx
  char *v19; // r10
  wchar_t v20; // ax
  wchar_t *v21; // rax
  unsigned int v22; // r8d
  wchar_t v23[3]; // [rsp+20h] [rbp-68h] BYREF
  wchar_t v24[29]; // [rsp+26h] [rbp-62h] BYREF

  v3 = (unsigned __int16 *)*((_QWORD *)this + 541);
  *(_WORD *)(*((_QWORD *)this + 542) + 2LL) = 2048;
  v4 = *((_QWORD *)this + 3);
  if ( (unsigned __int64)a2 < v4 + 2 * (unsigned __int64)(*v3 & 0x3FFF) )
    return 2147500037LL;
  while ( (unsigned __int64)a2 >= v4 + 2 * (unsigned __int64)v3[1] )
  {
    v5 = v3[2];
    v3 += 2;
    if ( (unsigned __int64)a2 < v4 + 2 * (unsigned __int64)(v5 & 0x3FFF) )
      return 2147500037LL;
  }
  v7 = *a2 + 10240;
  _mm_lfence();
  if ( v7 > 0x3FFu )
    v8 = *a2;
  else
    v8 = (*a2 << 10) + a2[1] - 56613888;
  v9 = *v3 >> 14;
  if ( !v9 )
  {
    v22 = XMLOutputHelper::entitizeUniChar(v8, v23);
    goto LABEL_30;
  }
  if ( v9 != 1 )
    return 2147500037LL;
  v10 = 32;
  v11 = v23;
  do
  {
    if ( v10 == -2147483614 )
      break;
    v12 = *(wchar_t *)((char *)v11 + (char *)L"]]>" - (char *)v23);
    if ( !v12 )
      break;
    *v11++ = v12;
    --v10;
  }
  while ( v10 );
  v13 = v11 - 1;
  v14 = -2147024774;
  if ( v10 )
    v13 = v11;
  *v13 = 0;
  result = 2147942522LL;
  if ( v10 )
  {
    v15 = XMLOutputHelper::entitizeUniChar(v8, v24) + 3;
    v16 = 32 - v15;
    v17 = 32 - v15;
    v18 = &v23[v15];
    if ( (unsigned __int64)(v17 - 1) > 0x7FFFFFFE )
    {
      result = 2147942487LL;
      v14 = -2147024809;
      if ( v16 )
        return result;
    }
    else
    {
      v19 = (char *)((char *)L"<![CDATA[" - (char *)v18);
      do
      {
        if ( !(2147483646LL - v16 + v17) )
          break;
        v20 = *(wchar_t *)((char *)v18 + (_QWORD)v19);
        if ( !v20 )
          break;
        *v18++ = v20;
        --v17;
      }
      while ( v17 );
      v21 = v18 - 1;
      if ( v17 )
      {
        v21 = v18;
        v14 = 0;
      }
      *v21 = 0;
    }
    result = v14;
    if ( !v14 )
    {
      v22 = v15 + 9;
LABEL_30:
      *((_QWORD *)this + 541) = v3;
      return EncodingWriter::WriteString((XMLOutputHelper *)((char *)this + 48), v23, v22);
    }
  }
  return result;
}

```

## disassembly

```asm
0x100421d00  mov     [rsp+arg_10], rbx
0x100421d05  mov     [rsp+arg_18], rbp
0x100421d0a  push    rsi
0x100421d0b  push    rdi
0x100421d0c  push    r14
0x100421d0e  sub     rsp, 70h
0x100421d12  mov     rax, cs:__security_cookie
0x100421d19  xor     rax, rsp
0x100421d1c  mov     [rsp+88h+var_28], rax
0x100421d21  mov     rax, [rcx+10F0h]
0x100421d28  mov     rbp, rcx
0x100421d2b  mov     rbx, [rcx+10E8h]
0x100421d32  mov     ecx, 800h
0x100421d37  mov     [rax+2], cx
0x100421d3b  movzx   eax, word ptr [rbx]
0x100421d3e  mov     r8, [rbp+18h]
0x100421d42  and     eax, 3FFFh
0x100421d47  lea     rax, [r8+rax*2]
0x100421d4b  cmp     rdx, rax
0x100421d4e  jb      short loc_100421D73
0x100421d50  movzx   eax, word ptr [rbx+2]
0x100421d54  lea     rcx, [r8+rax*2]
0x100421d58  cmp     rdx, rcx
0x100421d5b  jb      short loc_100421D9A
0x100421d5d  movzx   eax, word ptr [rbx+4]
0x100421d61  add     rbx, 4
0x100421d65  and     eax, 3FFFh
0x100421d6a  lea     rax, [r8+rax*2]
0x100421d6e  cmp     rdx, rax
0x100421d71  jnb     short loc_100421D50
0x100421d73  mov     eax, 80004005h
0x100421d78  mov     rcx, [rsp+88h+var_28]
0x100421d7d  xor     rcx, rsp; StackCookie
0x100421d80  call    __security_check_cookie
0x100421d85  lea     r11, [rsp+88h+var_18]
0x100421d8a  mov     rbx, [r11+30h]
0x100421d8e  mov     rbp, [r11+38h]
0x100421d92  mov     rsp, r11
0x100421d95  pop     r14
0x100421d97  pop     rdi
0x100421d98  pop     rsi
0x100421d99  retn
0x100421d9a  movzx   eax, word ptr [rdx]
0x100421d9d  mov     ecx, 2800h
0x100421da2  add     ax, cx
0x100421da5  mov     ecx, 3FFh
0x100421daa  lfence
0x100421dad  cmp     ax, cx
0x100421db0  ja      short loc_100421DC9
0x100421db2  movzx   ecx, word ptr [rdx]
0x100421db5  movzx   r9d, word ptr [rdx+2]
0x100421dba  shl     ecx, 0Ah
0x100421dbd  add     r9d, 0FCA02400h
0x100421dc4  add     r9d, ecx
0x100421dc7  jmp     short loc_100421DCD
0x100421dc9  movzx   r9d, word ptr [rdx]
0x100421dcd  movzx   ecx, word ptr [rbx]
0x100421dd0  shr     ecx, 0Eh
0x100421dd3  test    ecx, ecx
0x100421dd5  jz      loc_100421EDB
0x100421ddb  cmp     ecx, 1
0x100421dde  jnz     short loc_100421D73
0x100421de0  mov     esi, 20h ; ' '
0x100421de5  lea     rcx, asc_1004488F8; "]]>"
0x100421dec  lea     rax, [rsp+88h+var_68]
0x100421df1  mov     r8d, esi
0x100421df4  sub     rcx, rax
0x100421df7  lea     rdx, [rsp+88h+var_68]
0x100421dfc  nop     dword ptr [rax+00h]
0x100421e00  lea     rax, [r8+7FFFFFDEh]
0x100421e07  test    rax, rax
0x100421e0a  jz      short loc_100421E22
0x100421e0c  movzx   eax, word ptr [rcx+rdx]
0x100421e10  test    ax, ax
0x100421e13  jz      short loc_100421E22
0x100421e15  mov     [rdx], ax
0x100421e18  add     rdx, 2
0x100421e1c  sub     r8, 1
0x100421e20  jnz     short loc_100421E00
0x100421e22  test    r8, r8
0x100421e25  lea     rax, [rdx-2]
0x100421e29  mov     edi, 8007007Ah
0x100421e2e  cmovnz  rax, rdx
0x100421e32  xor     r14d, r14d
0x100421e35  test    r8, r8
0x100421e38  mov     [rax], r14w
0x100421e3c  mov     eax, edi
0x100421e3e  cmovnz  eax, r14d
0x100421e42  jz      loc_100421D78
0x100421e48  lea     rdx, [rsp+88h+var_62]; wchar_t *
0x100421e4d  mov     ecx, r9d; unsigned int
0x100421e50  call    ?entitizeUniChar@XMLOutputHelper@@SAHKPEA_W@Z; XMLOutputHelper::entitizeUniChar(ulong,wchar_t *)
0x100421e55  lea     rcx, [rsp+88h+var_68]
0x100421e5a  mov     r9d, 7FFFFFFEh
0x100421e60  lea     r8d, [rax+3]
0x100421e64  sub     esi, r8d
0x100421e67  movsxd  rax, r8d
0x100421e6a  movsxd  rdx, esi
0x100421e6d  lea     rcx, [rcx+rax*2]
0x100421e71  lea     rax, [rdx-1]
0x100421e75  cmp     rax, r9
0x100421e78  ja      short loc_100421EBC
0x100421e7a  sub     r9, rdx
0x100421e7d  lea     r10, aCdata_0; "<![CDATA["
0x100421e84  sub     r10, rcx
0x100421e87  lea     rax, [r9+rdx]
0x100421e8b  test    rax, rax
0x100421e8e  jz      short loc_100421EA7
0x100421e90  movzx   eax, word ptr [r10+rcx]
0x100421e95  test    ax, ax
0x100421e98  jz      short loc_100421EA7
0x100421e9a  mov     [rcx], ax
0x100421e9d  add     rcx, 2
0x100421ea1  sub     rdx, 1
0x100421ea5  jnz     short loc_100421E87
0x100421ea7  test    rdx, rdx
0x100421eaa  lea     rax, [rcx-2]
0x100421eae  cmovnz  rax, rcx
0x100421eb2  cmovnz  edi, r14d
0x100421eb6  mov     [rax], r14w
0x100421eba  jmp     short loc_100421ECB
0x100421ebc  mov     eax, 80070057h
0x100421ec1  mov     edi, eax
0x100421ec3  test    esi, esi
0x100421ec5  jnz     loc_100421D78
0x100421ecb  mov     eax, edi
0x100421ecd  test    edi, edi
0x100421ecf  jnz     loc_100421D78
0x100421ed5  add     r8d, 9
0x100421ed9  jmp     short loc_100421EEB
0x100421edb  lea     rdx, [rsp+88h+var_68]; wchar_t *
0x100421ee0  mov     ecx, r9d; unsigned int
0x100421ee3  call    ?entitizeUniChar@XMLOutputHelper@@SAHKPEA_W@Z; XMLOutputHelper::entitizeUniChar(ulong,wchar_t *)
0x100421ee8  mov     r8d, eax; unsigned int
0x100421eeb  lea     rcx, [rbp+30h]; this
0x100421eef  mov     [rbp+10E8h], rbx
0x100421ef6  lea     rdx, [rsp+88h+var_68]; wchar_t *
0x100421efb  call    ?WriteString@EncodingWriter@@QEAAJPEB_WI@Z; EncodingWriter::WriteString(wchar_t const *,uint)
0x100421f00  jmp     loc_100421D78
```
