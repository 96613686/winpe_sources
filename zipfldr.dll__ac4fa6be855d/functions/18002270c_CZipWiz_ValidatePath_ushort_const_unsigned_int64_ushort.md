# CZipWiz::_ValidatePath(ushort const *,unsigned __int64,ushort *)

- ea: `0x18002270c`
- end: `0x180022908`
- name: `?_ValidatePath@CZipWiz@@AEAAJPEBG_KPEAG@Z`
- size: `508`
- prototype: `int(CZipWiz *__hidden this, const unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024cb4`

## callees

- `0x18002270c`
- `0x180022910`
- `0x180022ee8`
- `0x180036f50`
- `0x180071010`

## import_xrefs

- `SHLWAPI!PathStripToRootW` at `0x1800227aa`
- `SHLWAPI!PathStripToRootW` at `0x1800227aa`
- `SHLWAPI!PathAddBackslashW` at `0x1800228b2`
- `SHLWAPI!PathAddBackslashW` at `0x1800228b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800228bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800228bd`

## pseudocode

```c
__int64 __fastcall CZipWiz::_ValidatePath(CZipWiz *this, const unsigned __int16 *a2, __int64 a3, unsigned __int16 *a4)
{
  __int64 v4; // rsi
  __int64 v5; // rdi
  __int64 v7; // rax
  __int64 v8; // r8
  WCHAR *v9; // r9
  const unsigned __int16 *v10; // r14
  const unsigned __int16 *v11; // rcx
  WCHAR *v12; // rcx
  signed int v13; // ebx
  const struct _GUID *v14; // rdx
  _WORD *v15; // rdx
  _WORD *v16; // rcx
  int i; // edx
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  void *v20; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v22[264]; // [rsp+250h] [rbp+150h] BYREF

  v4 = 2147483646;
  v5 = 260;
  v7 = 2147483646;
  v8 = 260;
  v9 = pszPath;
  v10 = a2;
  v11 = a2;
  do
  {
    if ( !v7 )
      break;
    if ( !*v11 )
      break;
    *v9++ = *v11++;
    --v7;
    --v8;
  }
  while ( v8 );
  v12 = v9 - 1;
  v13 = v8 == 0 ? 0x8007007A : 0;
  if ( v8 )
    v12 = v9;
  *v12 = 0;
  if ( v8 )
  {
    if ( PathStripToRootW(pszPath) )
    {
      v20 = 0;
      v13 = CreateItemFromUserInput(pszPath, v14, &v20);
      if ( v13 >= 0 )
      {
        pv = 0;
        v13 = (*(__int64 (__fastcall **)(void *, __int64, LPVOID *))(*(_QWORD *)v20 + 40LL))(v20, 2147844096LL, &pv);
        if ( v13 >= 0 )
        {
          v15 = v22;
          do
          {
            if ( !v4 )
              break;
            if ( !*v10 )
              break;
            *v15++ = *v10++;
            --v4;
            --v5;
          }
          while ( v5 );
          v16 = v15 - 1;
          v13 = v5 == 0 ? 0x8007007A : 0;
          if ( v5 )
            v16 = v15;
          *v16 = 0;
          if ( v5 )
          {
            for ( i = 0; pszPath[i] == v22[i]; ++i )
            {
              if ( !v22[i] )
                break;
            }
            v13 = StringCchPrintfW(a4, 0x103u, L"%s%s", pv, &v22[i]);
            if ( v13 >= 0 )
              PathAddBackslashW(a4);
          }
          CoTaskMemFree(pv);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
      }
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002270c  mov     [rsp-8+arg_0], rbx
0x180022711  mov     [rsp-8+arg_8], rsi
0x180022716  push    rbp
0x180022717  push    rdi
0x180022718  push    r12
0x18002271a  push    r14
0x18002271c  push    r15
0x18002271e  lea     rbp, [rsp-370h]
0x180022726  sub     rsp, 470h
0x18002272d  mov     rax, cs:__security_cookie
0x180022734  xor     rax, rsp
0x180022737  mov     [rbp+390h+var_30], rax
0x18002273e  mov     esi, 7FFFFFFEh
0x180022743  mov     edi, 104h
0x180022748  mov     r15, r9
0x18002274b  mov     eax, esi
0x18002274d  mov     r8d, edi
0x180022750  lea     r9, [rsp+490h+pszPath]
0x180022755  mov     r14, rdx
0x180022758  mov     rcx, rdx
0x18002275b  xor     r12d, r12d
0x18002275e  test    rax, rax
0x180022761  jz      short loc_180022780
0x180022763  movzx   edx, word ptr [rcx]
0x180022766  test    dx, dx
0x180022769  jz      short loc_180022780
0x18002276b  mov     [r9], dx
0x18002276f  add     rcx, 2
0x180022773  add     r9, 2
0x180022777  dec     rax
0x18002277a  sub     r8, 1
0x18002277e  jnz     short loc_18002275E
0x180022780  mov     rax, r8
0x180022783  lea     rcx, [r9-2]
0x180022787  neg     rax
0x18002278a  sbb     ebx, ebx
0x18002278c  not     ebx
0x18002278e  and     ebx, 8007007Ah
0x180022794  test    r8, r8
0x180022797  cmovnz  rcx, r9
0x18002279b  mov     [rcx], r12w
0x18002279f  jz      loc_1800228DB
0x1800227a5  lea     rcx, [rsp+490h+pszPath]; pszPath
0x1800227aa  call    cs:__imp_PathStripToRootW
0x1800227b0  test    eax, eax
0x1800227b2  jz      loc_1800228D6
0x1800227b8  lea     r8, [rsp+490h+var_458]; void **
0x1800227bd  mov     [rsp+490h+var_458], r12
0x1800227c2  lea     rcx, [rsp+490h+pszPath]; unsigned __int16 *
0x1800227c7  call    ?CreateItemFromUserInput@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateItemFromUserInput(ushort const *,_GUID const &,void * *)
0x1800227cc  mov     ebx, eax
0x1800227ce  test    eax, eax
0x1800227d0  js      loc_1800228DB
0x1800227d6  mov     rcx, [rsp+490h+var_458]
0x1800227db  lea     r8, [rsp+490h+pv]
0x1800227e0  mov     [rsp+490h+pv], r12
0x1800227e5  mov     edx, 80058000h
0x1800227ea  mov     rax, [rcx]
0x1800227ed  mov     rax, [rax+28h]
0x1800227f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227f6  mov     ebx, eax
0x1800227f8  test    eax, eax
0x1800227fa  js      loc_1800228C3
0x180022800  lea     rdx, [rbp+390h+var_240]
0x180022807  test    rsi, rsi
0x18002280a  jz      short loc_180022829
0x18002280c  movzx   eax, word ptr [r14]
0x180022810  test    ax, ax
0x180022813  jz      short loc_180022829
0x180022815  mov     [rdx], ax
0x180022818  add     r14, 2
0x18002281c  add     rdx, 2
0x180022820  dec     rsi
0x180022823  sub     rdi, 1
0x180022827  jnz     short loc_180022807
0x180022829  mov     rax, rdi
0x18002282c  lea     rcx, [rdx-2]
0x180022830  neg     rax
0x180022833  sbb     ebx, ebx
0x180022835  not     ebx
0x180022837  and     ebx, 8007007Ah
0x18002283d  test    rdi, rdi
0x180022840  cmovnz  rcx, rdx
0x180022844  mov     [rcx], r12w
0x180022848  jz      short loc_1800228B8
0x18002284a  movzx   eax, [rbp+390h+var_240]
0x180022851  mov     edx, r12d
0x180022854  cmp     [rsp+490h+pszPath], ax
0x180022859  jnz     short loc_18002287D
0x18002285b  movsxd  rax, edx
0x18002285e  cmp     [rbp+rax*2+390h+var_240], r12w
0x180022867  jz      short loc_18002287D
0x180022869  inc     edx
0x18002286b  movsxd  rcx, edx
0x18002286e  movzx   eax, [rbp+rcx*2+390h+var_240]
0x180022876  cmp     [rsp+rcx*2+490h+pszPath], ax
0x18002287b  jz      short loc_18002285B
0x18002287d  mov     r9, [rsp+490h+pv]
0x180022882  lea     r8, aSS_0; "%s%s"
0x180022889  movsxd  rax, edx
0x18002288c  mov     rcx, r15; unsigned __int16 *
0x18002288f  lea     rdx, [rbp+390h+var_240]
0x180022896  lea     rdx, [rdx+rax*2]
0x18002289a  mov     [rsp+490h+var_470], rdx
0x18002289f  mov     edx, 103h; unsigned __int64
0x1800228a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800228a9  mov     ebx, eax
0x1800228ab  test    eax, eax
0x1800228ad  js      short loc_1800228B8
0x1800228af  mov     rcx, r15; pszPath
0x1800228b2  call    cs:__imp_PathAddBackslashW
0x1800228b8  mov     rcx, [rsp+490h+pv]; pv
0x1800228bd  call    cs:__imp_CoTaskMemFree
0x1800228c3  mov     rcx, [rsp+490h+var_458]
0x1800228c8  mov     rax, [rcx]
0x1800228cb  mov     rax, [rax+10h]
0x1800228cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228d4  jmp     short loc_1800228DB
0x1800228d6  mov     ebx, 80004005h
0x1800228db  mov     eax, ebx
0x1800228dd  mov     rcx, [rbp+390h+var_30]
0x1800228e4  xor     rcx, rsp; StackCookie
0x1800228e7  call    __security_check_cookie
0x1800228ec  lea     r11, [rsp+490h+var_20]
0x1800228f4  mov     rbx, [r11+30h]
0x1800228f8  mov     rsi, [r11+38h]
0x1800228fc  mov     rsp, r11
0x1800228ff  pop     r15
0x180022901  pop     r14
0x180022903  pop     r12
0x180022905  pop     rdi
0x180022906  pop     rbp
0x180022907  retn
```
